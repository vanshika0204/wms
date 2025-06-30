# wms

Following is the structure of a relational schema for WMS modules like Inventory, Orders, Clients : 

1. Modular Format for Expandability:
The four core entities - Clients, Products, Inventory, and Orders - are clear, independent tables that add modularity and will be clear for additional expandability (e.g., returns, shipments) if the application gets there.

2. Normalization to Reduce Redundancy:
The data has been normalized in a way that does not require duplication of information to avoid redundancy. For instance, the information on products is actually stored in the Products table, not repeated in the Inventory and Order_Items tables.

3. Foreign Keys for Relationship Enforcement:
Relationships are maintained by the use of foreign keys (e.g., client_id in Orders, product_id in Inventory) that ensure valid links between related data and help prevent orphan records.

4. Multiple Relationships Supported:
The Order_Items table provides a way to refer to both Orders and Products. It establishes a relationship between the two entities since there can be multiple products in an order that may exist in other orders, identified by the primary key in Products.

5. Future Proofing with Timestamps & Status Columns:
Instead of dates, fields like updated_at in Inventory and status in Orders can help keep track of the state of a row and allow for things like real-time updates or workflow management.
