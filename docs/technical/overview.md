I'll analyze the codebase to understand the complete supply chain management system. Let me start by examining the key components and data flow.
Search files...
Let me continue examining the key models and controllers to understand the complete workflow:
Read file: app/models/request_contract.rb
Read file: app/models/inventory.rb
Read file: app/models/item.rb
Read file: app/models/user.rb
Now let me examine the order management and shipping workflow:
Read file: app/controllers/api/v1/orders_controller.rb
Ran tool
Search files...
Let me examine the database schema to get a complete picture of the data relationships:
Read file: db/schema.rb
Search files...
Now let me create a comprehensive diagram to visualize the complete supply chain management system:
Ran tool
Based on my analysis of the codebase, here's how the complete request, confirmation, shipment, and supply chain management system works:

## **Supply Chain Management System Overview**

This is a multi-tier B2B supply chain platform that connects **Producers → Brokers → Retailers → Consumers** with automated request routing, pricing, and order fulfillment.

### **🏗️ Core Architecture**

**User Hierarchy:**
- **Admin**: System administrator with full access
- **Producer**: Creates and owns original items/inventory
- **Broker/Wholesaler**: Intermediary traders who buy from producers and sell to retailers
- **Retailer**: Sells to consumers, can also act as intermediaries
- **Consumer**: End buyers who purchase from retailers

**Key Models:**
- `Item`: Product definition with category, grade, pricing
- `Inventory`: Actual stock owned by users with quantities and status
- `RequestContract`: Master contract for a supply chain request
- `ItemRequest`: Individual step in the supply chain
- `Order`: Groups related requests for shipment
- `Relationship`: Network connections between users

### **📋 Request & Confirmation Workflow**

#### **1. Request Creation**
```ruby
# When a user requests an item
POST /v1/items/:inventory_id/requests
```

**Path Finding Algorithm:**
- System uses **Dijkstra-like shortest path** algorithm to find optimal route
- Searches up to `MAX_DEPTH = 5` relationship levels
- Calculates total cost including markups at each step
- Creates multi-step `RequestContract` with individual `ItemRequest` per hop

**Example Chain:** Consumer → Retailer → Broker → Producer
- Creates 3 `ItemRequest` records (one per relationship)
- Each has different pricing based on cumulative markups

#### **2. Confirmation Process**
```ruby
POST /v1/items/requests/:request_id/accept
```

**Status Flow:**
- `pending` → User receives request, can accept/decline
- `accepted` → Request confirmed, inventory becomes `reserved`
- `reserved` → Inventory locked for this request chain
- `completed` → Item shipped and received
- `cancelled` → Request terminated

**Multi-Step Confirmation:**
- Each step in chain must be individually accepted
- Contract only proceeds when ALL steps are `accepted`
- Inventory status changes to `reserved` when contract is fully accepted

### **🚚 Shipment & Order Management**

#### **3. Order Creation**
```ruby
# Orders group related requests between two users
Order.create(user_id: sender, friend_id: receiver)
```

**Order Aggregation:**
- Multiple `ItemRequest`s between same users get grouped into `Order`
- Orders have status: `pending` → `shipped` → `signed`
- Enables bulk shipping and receiving

#### **4. Shipping Process**
```ruby
POST /v1/items/requests/:request_id/ship
```

**Shipping Workflow:**
- Only inventory owner can ship
- Updates `shipped_at` timestamp
- Changes `ItemRequest` status to `completed`
- Order status becomes `shipped`

#### **5. Receiving/Signing**
```ruby
POST /v1/items/requests/:request_id/sign
```

**Ownership Transfer:**
- Receiver "signs" to confirm receipt
- **Inventory ownership transfers** to receiver
- Updates `signed_at` timestamp
- If multi-step chain, creates next order automatically

### **💰 Pricing & Markup System**

**Hierarchical Pricing:**
1. **Base Price**: Producer's original price
2. **Relationship Markup**: Custom markup between specific users
3. **Category Markup**: Default markup by product category
4. **Global Default**: System-wide default markup

```ruby
# Price calculation in helpers/item_helper.rb
def get_relation_price(user_id, friend_id)
  # 1. Check custom relationship price
  relation_price = UserRelationshipPrice.find_by(user_id: user_id, friend_id: friend_id)
  return relation_price.price if relation_price&.price
  
  # 2. Fall back to user's category markup
  return get_user_markup(user_id)
end
```

**Final Price = Base Price + Sum(Markups for each step in chain)**

### **📊 Dashboard Views by User Type**

**Producer Dashboard:**
- **My Store**: Items they've created
- **Requested**: Incoming requests for their items
- **Shipped**: Items they've sent out

**Broker/Retailer Dashboard:**
- **Available**: Items they can purchase from network
- **Requested**: Items they've requested from others
- **Holding**: Items they own (received from others)
- **Shipped**: Items they've sent to customers
- **My Store**: Items they're selling

**Consumer Dashboard:**
- **Available**: Items from connected retailers
- **Requested**: Items they've requested
- Simplified view with unit options (oz, bottles, etc.)

### **🔄 Multi-Tier Chain Example**

**Scenario:** Consumer wants apples from Producer
1. **Path Discovery**: Consumer → Retailer → Broker → Producer
2. **Contract Creation**: 
   - `RequestContract` with `steps: 3`
   - 3 `ItemRequest` records created
3. **Acceptance Chain**:
   - Producer accepts (step 3)
   - Broker accepts (step 2) 
   - Retailer accepts (step 1)
4. **Shipping Chain**:
   - Producer ships to Broker
   - Broker receives & signs → ownership transfers
   - Broker ships to Retailer  
   - Retailer receives & signs → ownership transfers
   - Retailer ships to Consumer
   - Consumer receives & signs → final ownership transfer

### **🎯 Key Features**

**Smart Routing**: Automatically finds shortest/cheapest path through supply network
**Atomic Transactions**: Full chain must be accepted or entire request fails
**Inventory Management**: Real-time status tracking (available/reserved/shipped)
**Flexible Pricing**: Relationship-based markups with fallbacks
**Order Batching**: Multiple items between users grouped for efficiency
**Ownership Tracking**: Clear chain of custody with timestamps
**Role-Based Access**: Different capabilities based on user type

This system enables complex B2B supply chains to operate efficiently with automated routing, transparent pricing, and reliable order fulfillment tracking.
