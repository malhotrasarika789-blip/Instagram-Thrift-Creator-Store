# Instagram Thrift Creator Store ER Diagram

## Overview
This project represents an Entity Relationship (ER) Diagram for an Instagram-based thrift store system.  
It models how creators sell thrift products, manage inventory, and handle customer orders.

---

## Entities Included

- Users (Customers / Creators)
- Products
- Orders
- Order Items
- Payments
- Shipping
- Inventory
- Handmade / Featured Products

---

## Key Features

- Creator-based selling system (Instagram thrift model)
- Buyers and sellers managed in a single Users table
- Proper use of Primary Keys (PK) and Foreign Keys (FK)
- Inventory tracking for product availability
- Complete order lifecycle:
  - Product listing → Order → Payment → Shipping

---

##  Relationships

- A User can place multiple Orders
- A Creator (User) can list multiple Products
- An Order can contain multiple Products (via Order Items)
- Each Order has one Payment
- Each Order has one Shipping Detail
- Products are linked with Inventory

---

## Tools Used

- Eraser (ER Diagram design tool)

---

##  ER Diagram

![alt text](<Screenshot 2026-04-06 204505-1.png>)

---

## Submission Notes

- Diagram is clear and readable  
- All entities and attributes are properly labeled  
- PK and FK are clearly marked  
- Single board used  

---

## Author

Sarika Malhotra