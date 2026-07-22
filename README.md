# 🛒 Multi-Vendor E-commerce Platform

A **Full-Stack Multi-Vendor E-commerce Platform** built using **FastAPI, PostgreSQL, React, and Tailwind CSS**. The platform allows multiple vendors to sell products, customers to purchase from different vendors, and administrators to manage the entire marketplace.

---

# 🚀 Features

## 👨‍💼 Admin
- Dashboard Analytics
- Manage Customers
- Manage Vendors
- Approve / Reject Vendors
- Manage Products
- Manage Orders
- Manage Coupons
- View Sales Analytics
- Delete Customers
- Activate / Deactivate Coupons

---

## 🛍 Vendor
- Vendor Registration & Login
- Add Products
- Edit Products
- Upload Product Images
- Soft Delete Products
- View Vendor Orders
- Update Order Status
- Vendor Dashboard Analytics
- Sales Summary
- Revenue Overview

---

## 👤 Customer
- Register & Login
- Browse Products
- Product Details
- Search Products
- Filter Products
- Sort Products
- Add to Cart
- Update Cart Quantity
- Wishlist
- Checkout
- Coupon Selection
- Order History
- Review Purchased Products
- Profile Management
- Change Password

---

# ⭐ Core Functionalities

- JWT Authentication
- Role-Based Authorization
- Vendor Approval System
- Product CRUD Operations
- Product Image Upload
- Shopping Cart
- Wishlist
- Coupon & Discount System
- Payment Simulation
- Order Splitting (Multi-Vendor)
- Email Notifications
- Product Reviews
- Profile Management
- Dashboard Analytics
- Responsive UI

---

# 🏗 Tech Stack

## Backend
- FastAPI
- PostgreSQL
- SQLAlchemy ORM
- JWT Authentication
- Pydantic
- Python

## Frontend
- React
- Vite
- Tailwind CSS
- Axios
- React Router DOM
- Recharts

---

# 📦 Order Splitting Logic

One of the important features of this project is **Order Splitting**.

If a customer purchases products from multiple vendors, the system automatically creates **separate orders** for each vendor.

### Example

```
Customer Cart

Mouse ---------- Vendor A
Keyboard ------- Vendor A
Headphones ----- Vendor B
```

After Checkout

```
Order #101
Vendor A

• Mouse
• Keyboard

---------------------

Order #102
Vendor B

• Headphones
```

### Benefits

- Vendors see only their own orders.
- Easier order management.
- Independent shipping.
- Separate vendor analytics.
- Better scalability.

---

# 🎟 Coupon System

### Admin

- Create Coupons
- Activate Coupons
- Deactivate Coupons
- Delete Coupons

### Customer

- View Available Coupons
- Apply Eligible Coupons
- Automatic Discount Calculation
- Change Applied Coupon
- Minimum Order Validation

Supported Coupon Types

- Flat Discount
- Percentage Discount

---

# ⭐ Product Review System

Customers can review products **only after purchasing them**.

Features

- 1–5 Star Rating
- Product Comments
- Prevent Duplicate Reviews
- Reviewed Badge
- Product Review History

---

# ❤️ Wishlist

Customers can

- Add Products
- Remove Products
- Open Product from Wishlist
- Move to Cart

---

# 📊 Analytics

## Admin Dashboard

- Total Users
- Total Vendors
- Total Customers
- Total Products
- Total Orders
- Revenue Overview
- Charts

---

## Vendor Dashboard

- Total Products
- Total Orders
- Revenue
- Sales Statistics

---

# 🗂 Database Tables

```
users
products
cart_items
orders
order_items
payments
wishlists
reviews
coupons
```

---

# 🔐 Authentication

JWT Token Based Authentication

Roles

- Admin
- Vendor
- Customer

Protected APIs require

```
Authorization: Bearer <token>
```

---

# 📁 Project Structure

```
backend/
│
├── app/
│   ├── routes/
│   ├── services/
│   ├── models.py
│   ├── schemas.py
│   ├── dependencies.py
│   ├── middleware.py
│   ├── database.py
│   └── main.py
│
├── uploads/
└── requirements.txt

frontend/
│
├── src/
│   ├── pages/
│   ├── layouts/
│   ├── components/
│   ├── api/
│   └── App.jsx
```

---

# ⚙ Backend Setup

```bash
cd backend

python -m venv venv

venv\Scripts\activate

pip install -r requirements.txt

uvicorn app.main:app --reload
```

Backend

```
http://127.0.0.1:8000
```

Swagger Docs

```
http://127.0.0.1:8000/docs
```

---

# ⚙ Frontend Setup

```bash
cd frontend

npm install

npm run dev
```

Frontend

```
http://localhost:5173
```

---

# 🔑 Environment Variables

Create a `.env` file inside the backend folder.

```env
DATABASE_URL=postgresql+psycopg2://postgres:password@localhost:5432/multivendor_ecommerce

SECRET_KEY=your_secret_key

ALGORITHM=HS256

ACCESS_TOKEN_EXPIRE_MINUTES=60

EMAIL_HOST=smtp.gmail.com

EMAIL_PORT=587

EMAIL_USERNAME=your_email@gmail.com

EMAIL_PASSWORD=your_app_password
```

---

# 📡 API Endpoints

## Authentication

```
POST   /auth/register
POST   /auth/login
```

---

## Products

```
GET    /products/
GET    /products/{id}
POST   /products/
PUT    /products/{id}
DELETE /products/{id}
GET    /products/my-products
```

---

## Cart

```
POST   /cart/add
GET    /cart/
PUT    /cart/{id}
DELETE /cart/{id}
DELETE /cart/
```

---

## Orders

```
POST   /orders/checkout
GET    /orders/my-orders
GET    /orders/vendor-orders
PUT    /orders/{id}/status
```

---

## Wishlist

```
POST   /wishlist/
GET    /wishlist/
DELETE /wishlist/{id}
```

---

## Reviews

```
POST   /reviews/
GET    /reviews/product/{id}
GET    /reviews/check/{id}
```

---

## Coupons

```
POST   /coupons/
GET    /coupons/
GET    /coupons/available
POST   /coupons/apply
PUT    /coupons/{id}/toggle
DELETE /coupons/{id}
```

---

## Profile

```
GET    /profile/me
PUT    /profile/me
PUT    /profile/change-password
```

---

## Admin

```
GET    /admin/dashboard
GET    /admin/users
GET    /admin/vendors
GET    /admin/products
GET    /admin/orders
PUT    /admin/vendors/{id}/approve
DELETE /admin/customers/{id}
```

---

# 💳 Payment Simulation

The payment system is simulated.

On Success

- Payment Status → SUCCESS
- Order Status → PAID
- Stock Reduced
- Cart Cleared
- Confirmation Email Sent

On Failure

- Payment Status → FAILED
- Order Status → FAILED
- Stock Unchanged
- Cart Preserved

---

# 🚚 Order Status Flow

```
Pending
   ↓
Paid
   ↓
Shipped
   ↓
Delivered
```

Failed orders cannot be shipped or delivered.

---

---

# 👨‍💻 Author

**Syed Mahammad Shareef**
#### Python Developer
