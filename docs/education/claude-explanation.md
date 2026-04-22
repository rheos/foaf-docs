You're absolutely right - let me add a proper **Current Project State** section based on what I analyzed from your actual codebase:

# Current Project State (From Codebase Analysis)

## System Architecture Overview

### Backend: Rails API (Port 3001)
- **Ruby on Rails** application serving JSON API
- **MySQL database** with comprehensive supply chain modeling
- **JWT authentication** with session management
- **File uploads** via CarrierWave with S3 integration
- **Docker containerization** with docker-compose setup

### Frontend: React SPA (Port 3000) 
- **React 18** with Redux for state management
- **Real-time dashboard** with multiple inventory views
- **Mobile-responsive design** with viewport handling
- **Toast notifications** for user feedback
- **Activity tracking** with session timeout detection

## Database Schema (Key Tables)

### Core Entities
```sql
users - User accounts with role-based permissions
items - Product definitions (name, category, grade, price)
inventories - Actual stock owned by users
categories - Product categories (herbs/greens, tinctures, etc.)
grades - Quality ratings (C, B, A, AA, AAA, A+, A++)
item_units - Measurement units (lbs, oz, boxes, bottles, grams)
```

### Supply Chain Management
```sql
request_contracts - Master contract for supply chain requests
  ├── user_id, item_id, inventory_id
  ├── quantity, status (pending/accepted/completed/cancelled)
  ├── steps, current_step (for multi-hop routing)
  
item_requests - Individual steps in supply chain
  ├── user_id, friend_id (sender/receiver for this step)
  ├── price, status, step (position in chain)
  ├── accepted_at, shipped_at, signed_at (workflow timestamps)
  ├── order_id (for grouping shipments)

orders - Grouped shipments between users
  ├── user_id, friend_id, order_status
  ├── estimated_date, shipped_on, signed_on
  ├── order_total, order_label
```

### Network & Relationships
```sql
relationships - User connections with pricing
  ├── user_id, friend_id, status
  ├── user_label, friend_label (custom names)
  ├── actions_state, friend_actions_state (permissions)

user_relationship_prices - Custom markups between users
  ├── user_id, friend_id, category_id
  ├── price (markup amount), relationship_id

user_groups - Role assignments
  ├── user_id, group_label (consumer/producer/broker/retailer/admin)
```

## Current User Roles & Hierarchy

### User Types (from seeds.rb)
```
Admin (bob) - System administrator
├── Producer (dianna, sara, john) - Create original items
├── Broker (peter, paul, mary, bruce, clark, barry) - Intermediaries  
├── Retailer (arthur, oliver) - Sell to consumers
└── Consumer (mark) - End buyers

Invitation System:
- Users invite others with specific roles
- Creates parent-child relationships 
- Establishes network depth and invitation limits
```

### Role Capabilities
- **Producers**: Create items, manage inventory, ship to network
- **Brokers**: Buy from producers, sell to retailers, route requests
- **Retailers**: Buy from network, sell to consumers, unit options
- **Consumers**: Browse available items, make requests with units
- **Admin**: Full system access, manage global settings

## Supply Chain Workflow (Current Implementation)

### 1. Request Creation Algorithm
**File**: `app/controllers/api/v1/item_requests_controller.rb`
```ruby
# Multi-hop pathfinding (lines 75-119)
MAX_DEPTH = 5
contacts = [{ user_id: current_user.id, path: [], prices: [], total: 0 }]
shortest = { total: BigDecimal::INFINITY, path: [], prices: [] }

# Dijkstra-like algorithm finds optimal route through relationships
# Creates RequestContract with calculated steps
# Generates ItemRequest for each hop with pricing
```

### 2. Request Statuses & State Machine
```ruby
# RequestContract statuses
enum status: [:pending, :accepted, :completed, :cancelled]

# ItemRequest statuses  
enum status: [:pending, :accepted, :completed, :cancelled, :reserved]

# Inventory statuses
enum status: [:unavailable, :available, :reserved, :in_order]
```

### 3. Multi-Step Approval Process
**File**: `app/models/item_request.rb`
```ruby
def accept_request
  # Updates status to accepted/reserved
  # Creates or updates Order for shipment grouping
  # Changes inventory status to reserved when all steps accepted
end

def ship
  # Sets shipped_at timestamp
  # Changes status to completed  
end

def sign  
  # Records signed_at timestamp
  # Transfers inventory ownership to recipient
  # Creates next order in chain if multi-step
  # Completes contract when final step signed
end
```

### 4. Pricing System
**File**: `app/helpers/item_helper.rb`
```ruby
def get_relation_price(user_id, friend_id)
  # 1. Check custom relationship price
  relation_price = UserRelationshipPrice.find_by(user_id: user_id, friend_id: friend_id)
  return relation_price.price if relation_price&.price
  
  # 2. Fall back to category markup
  # 3. Fall back to global default
end

# Final price = base_price + sum(markups_in_chain)
```

## Frontend Dashboard Architecture

### Dashboard Views by User Type
**File**: `platform/src/pages/dashboard/index.js`

#### Producer Dashboard
- **My Store**: Items they've created and own
- **Requested**: Incoming requests for their items  
- **Shipped**: Items they've sent out
- **Around**: Geographic area items

#### Broker/Retailer Dashboard  
- **Available**: Items they can purchase from network
- **Requested**: Items they've requested from others
- **Holding**: Items they own (received inventory)
- **Shipped**: Items they've sent to customers
- **My Store**: Items they're selling

#### Consumer Dashboard
- **Available**: Items from connected retailers with unit options
- **Requested**: Items they've requested

### Key React Components
```javascript
// platform/src/components/inventory/sections/
available.js - Browse and request items
requested.js - Track pending requests  
holding.js - Manage owned inventory
shipped.js - View shipping history
my.js - Manage personal store items
```

## Current API Endpoints

### Core Supply Chain Operations
```
POST /v1/items/:inventory_id/requests - Create supply chain request
POST /v1/items/requests/:id/accept - Accept request step
POST /v1/items/requests/:id/ship - Ship order
POST /v1/items/requests/:id/sign - Receive/sign order
POST /v1/items/requests/:id/cancel - Cancel request

GET /v1/items - Browse available items with relationship filtering
GET /v1/items/:inventory_id/requests - View requests for item
GET /v1/items/reserve - Get reserved/holding items
GET /v1/items/my_items - Get user's inventory
GET /v1/items/shipped - Get shipping history
```

### User & Relationship Management
```
POST /v1/sessions - JWT authentication
GET /v1/users/contact_list - Get network relationships
POST /v1/user_relationship_prices - Set custom markups
POST /v1/users/accept_invitation - Join network via invitation code
```

## Docker Infrastructure

### Services (docker-compose.yml)
```yaml
backend: Rails API (port 3001)
frontend: React app (port 3000)  
db: MySQL 8.0
```

### Environment Configuration
- **Development**: localhost with hot reloading
- **Production**: Containerized with S3 file storage
- **CORS**: Configured for cross-origin requests

## Current Limitations (Pre-Mutual Credit)

### Payment Model
- **No payment tracking** - transactions complete without financial obligation records
- **No credit lines** - each transaction is independent
- **No debt management** - no system for tracking who owes what
- **External settlements** - payments happen outside the system

### Network Effects
- **Linear growth** - each user must find direct relationships
- **Limited routing** - 5-hop maximum depth
- **Price accumulation** - markups compound through chain
- **Settlement friction** - no netting or offset mechanisms

## Ready for Mutual Credit Enhancement

### Strong Foundation
✅ **User relationship network** established  
✅ **Multi-hop routing** algorithm working  
✅ **Complex state management** for supply chains  
✅ **Role-based permissions** system  
✅ **Transaction completion** hooks for credit creation  
✅ **Pricing/markup** infrastructure  

### Extension Points
✅ **Relationship model** can add credit_limit fields  
✅ **ItemRequest.sign** can create credit transactions  
✅ **User model** can track credit balances  
✅ **Dashboard** can add financial overview sections  
✅ **API controllers** can add credit management endpoints  

The current system is perfectly positioned to evolve into a mutual credit platform with minimal disruption to existing functionality.

---

*This reflects the actual state of your codebase as analyzed from the Rails backend and React frontend code.*
