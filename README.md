# Restaurant-Management-System

Restaurant Management System

Main Entities and Their Relationships

1. Customers
customer_id (PK): Unique ID for each customer.
name: Full name of the customer.
phone: Contact number.
email: Email address.
 One customer can place multiple orders.

2. Staff
staff_id (PK): Unique ID for each staff member.
name: Staff member's name.
phone: Contact number.
role_id (FK): Refers to the role they perform.
 Each staff has one role defined in the Roles table.

3. Roles (Lookup Table)
role_id (PK): Unique ID for a role.
role_name: Name of the role (Waiter, Chef, etc.)
 One role can be assigned to many staff.

4. Tables (Restaurant Seating)
table_id (PK): Unique table ID in the restaurant.
seating_capacity: Number of seats at the table.
status: Table availability — 'available', 'occupied', etc.
 Tables are assigned during order placement.

5. Menu
item_id (PK): Unique ID for the dish.
item_name: Name of the menu item.
description: Details about the dish.
price: Price of the item.
category_id (FK): Refers to category like Main Course, Dessert.

6. Categories (Lookup Table)
category_id (PK): Unique ID per category.
category_name: e.g., Appetizer, Main Course, Dessert.
 Helps categorize menu items.

7. Orders
order_id (PK): Unique ID per order.
customer_id (FK): Who placed the order.
staff_id (FK): Who handled the order.
table_id (FK): Where customer was seated.
order_time: Time when order was placed.
status: Status like 'pending', 'completed', etc.
 Linked to both customer and staff.

8. Order_Items
order_item_id (PK): Unique line item row.
order_id (FK): Links to order.
item_id (FK): Which dish was ordered.
quantity: How many of the item were ordered.
Represents many-to-many connection between orders and menu.

9. Payments
payment_id (PK): Unique payment transaction ID.
order_id (FK): Payment is for which order.
amount: Total bill amount.
method_id (FK): Refers to payment method used.
payment_time: When payment was made.
status: e.g., 'paid', 'unpaid'.

10. Payment_Methods (Lookup Table)
method_id (PK): Payment method ID.
method_name: e.g., Cash, Card, UPI.

 Relationships (Simplified in words)
 
One Customer → Many Orders
One Staff → Many Orders
One Role → Many Staff
One Order → Many Order Items
One Menu Item → Can be in Many Order Items
One Order → One Payment
One Payment Method → Many Payments
One Category → Many Menu Items
One Order → Belongs to One Table
