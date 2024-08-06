# E-CommerceConnect

This project is a functional Express.js API for an e-commerce application, connected to a PostgreSQL database using Sequelize ORM. The back end allows for the creation, retrieval, updating, and deletion of categories, products, and tags.

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [Database Models](#database-models)
- [Associations](#associations)
- [API Routes](#api-routes)
- [License](#license)

## Installation
Clone the repository:

```bash
git clone https://github.com/ElijahWard4/E-CommerceConnect.git
cd E-CommerceConnect
```

Install dependencies:

```bash
npm install
```

Set up environment variables:

Create a .env file in the root directory and add your PostgreSQL database credentials:

```env
DB_NAME=your_database_name
DB_USER=your_postgresql_username
DB_PASSWORD=your_postgresql_password
```

Create and seed the database:

```bash
npm run seed
```

Start the server:

```bash
npm start
```

## Usage
After starting the server, you can test the API routes using Insomnia or any other API client. The available endpoints allow you to perform CRUD operations on categories, products, and tags.

## Database Models
The database contains the following models:

### Category
- id: Integer, primary key, auto increment, not null.
- category_name: String, not null.

### Product
- id: Integer, primary key, auto increment, not null.
- product_name: String, not null.
- price: Decimal, not null, validates as decimal.
- stock: Integer, not null, default value of 10, validates as numeric.
- category_id: Integer, references Category model's id.

### Tag
- id: Integer, primary key, auto increment, not null.
- tag_name: String.

### ProductTag
- id: Integer, primary key, auto increment, not null.
- product_id: Integer, references Product model's id.
- tag_id: Integer, references Tag model's id.

## Associations
The models are associated as follows:

- Product belongs to Category, and Category has many Product models.
- Product belongs to many Tag models, and Tag belongs to many Product models through ProductTag.

## API Routes
The following routes are available:

### Category Routes
- GET /api/categories: Get all categories.
- GET /api/categories/:id: Get a single category by ID.
- POST /api/categories: Create a new category.
- PUT /api/categories/:id: Update a category by ID.
- DELETE /api/categories/:id: Delete a category by ID.

### Product Routes
- GET /api/products: Get all products.
- GET /api/products/:id: Get a single product by ID.
- POST /api/products: Create a new product.
- PUT /api/products/:id: Update a product by ID.
- DELETE /api/products/:id: Delete a product by ID.

### Tag Routes
- GET /api/tags: Get all tags.
- GET /api/tags/:id: Get a single tag by ID.
- POST /api/tags: Create a new tag.
- PUT /api/tags/:id: Update a tag by ID.
- DELETE /api/tags/:id: Delete a tag by ID.

## License
This project is licensed under the MIT License.

Feel free to customize the repository URL, environment variable details, or any other sections as per your project's specifics.
