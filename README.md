# Swiggy-Schema
Swiggy Database Schema Design

A database schema design project that models the core workflow of a food delivery platform inspired by Swiggy. It describes how customers discover restaurants, place orders, make payments, and receive deliveries.

## Project Overview

The schema organizes the main records involved in a food delivery transaction and the relationships between them. It is intended to make common platform workflows easier to understand, query, and extend.

## Core Areas Modeled

- **Customers** — customer profiles and contact details
- **Restaurants** — restaurant information and availability
- **Menu items** — dishes offered by restaurants, with prices and availability
- **Orders** — customer orders, timestamps, totals, and order status
- **Order items** — line items connecting orders to menu items, including quantity and price at order time
- **Payments** — payment method, amount, and payment status
- **Delivery partners** — delivery partner profiles and availability
- **Deliveries** — assignment and delivery progress for an order
- **Addresses** — customer delivery locations

## Main Relationships

- A customer can place many orders.
- A restaurant can offer many menu items and receive many orders.
- An order contains one or more order items.
- Each order item refers to a menu item and stores the quantity and purchase-time price.
- An order can have payment information and a delivery record.
- A delivery partner can complete many deliveries over time.
- A customer can save multiple delivery addresses.

## Database Design Notes

- Primary keys uniquely identify records.
- Foreign keys represent relationships between entities and help preserve referential integrity.
- The order-items table handles the many-to-many relationship between orders and menu items.
- Storing the item price on each order item preserves the price charged when the order was placed, even if the menu price changes later.
- Order, payment, and delivery statuses can be represented with constrained values or lookup tables, depending on the database and project scope.

