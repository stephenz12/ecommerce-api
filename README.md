E-Commerce Flask REST API

This project is a RESTful API built with Flask, SQLAlchemy, and Marshmallow that models a simple e-commerce system with users, orders, and products, including proper relational mappings.

The API supports full CRUD operations and demonstrates many-to-many relationships between orders and products.

 Features

Flask REST API

MySQL database with SQLAlchemy ORM

Many-to-many relationship between Orders and Products

Marshmallow schemas for JSON serialization

Full CRUD endpoints

Clean project structure following best practices

 Data Models
User

id

name

email (unique)

Product

id

product_name

price

Order

id

order_date

user_id

products (many-to-many)

Relationships

One User → Many Orders

Many Orders ↔ Many Products

Implemented using an association table (order_product)
API Endpoints
Users

POST /users — Create a user

GET /users — Get all users

DELETE /users/<id> — Delete a user

Products

POST /products — Create a product

GET /products — Get all products

DELETE /products/<id> — Delete a product

Orders

POST /orders — Create an order for a user

GET /orders/user/<user_id> — Get all orders for a user

PUT /orders/<order_id>/add_product/<product_id> — Add a product to an order

DELETE /orders/<id> — Delete an order

Tech Stack

Python 3

Flask

Flask-SQLAlchemy

Flask-Marshmallow

Marshmallow-SQLAlchemy

MySQL

Running the Project
1. Clone the repository
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name

2. Create and activate a virtual environment
python -m venv venv
venv\Scripts\activate  # Windows

3. Install dependencies
pip install flask flask-sqlalchemy flask-marshmallow marshmallow-sqlalchemy mysql-connector-python

4. Configure the database

Update the database URI in app.py:

app.config['SQLALCHEMY_DATABASE_URI'] = 'mysql+mysqlconnector://user:password@localhost/db_name'

5. Run the server
python app.py


The API will be available at:

http://127.0.0.1:5000

 Testing

All endpoints were tested using Postman.

 What This Project Demonstrates

RESTful API design

SQLAlchemy relationships

Proper serialization with Marshmallow

Error handling for invalid input

Clean Git practices (virtual environment excluded)

 Notes

Database tables are created automatically using db.create_all()

This project focuses on backend functionality only

Authentication is intentionally omitted for simplicity
 Author

