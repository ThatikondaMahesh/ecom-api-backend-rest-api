# 🟢 Node.js E-commerce Backend REST API

## 📝 Project Description
This project is a 🟢 Node.js-based backend application for an 🛒 e-commerce platform. It provides 🌐 RESTful APIs to manage various features such as 📦 products, 🛍️ orders, 🛒 cart items, and ❤️ likes. It also includes 🔒 JWT-based authentication and 🛠️ middleware for security and smooth operations. The project uses 🍃 MongoDB as the database and follows a 🧩 modular architecture with clean 🖋️ code separation for 🚀 scalability and 🛠️ maintainability.

---

## 🗂️ Project Structure

```
ECOM-API-BACKEND-REST-API
|-- 📂 node_modules/
|-- 📂 src/
    |-- 📂 config/
        |-- 📄 mongodb.js
        |-- 📄 mongooseConfig.js
    |-- 📂 error-handler/
        |-- 📄 applicationError.js
    |-- 📂 middleware/
        |-- 📄 authMiddleware.js
    |-- 📂 features/
        |-- 📂 cartItems/
            |-- 📄 cartItems.controller.js
            |-- 📄 cartItems.model.js
            |-- 📄 cartItems.repository.js
            |-- 📄 cartItems.routes.js
            |-- 📄 cartItems.schema.js
        |-- 📂 like/
            |-- 📄 like.controller.js
            |-- 📄 like.repository.js
            |-- 📄 like.routes.js
            |-- 📄 like.schema.js
        |-- 📂 order/
            |-- 📄 info.txt
            |-- 📄 order.controller.js
            |-- 📄 order.model.js
            |-- 📄 order.repository.js
            |-- 📄 order.routes.js
        |-- 📂 product/
            |-- 📄 category.schema.js
            |-- 📄 product.controller.js
            |-- 📄 product.model.js
            |-- 📄 product.repository.js
            |-- 📄 product.routes.js
            |-- 📄 product.schema.js
    |-- 📂 auth/
        |-- 📄 jwtService.js
|-- 📄 package.json
|-- 📄 README.md
```

---

## ⭐ Key Features

1. **🛍️ Product Management**
   - ✏️ Create, ✏️ update, ❌ delete, and 🔍 retrieve product details.
   - Associated with 🏷️ categories.

2. **🛒 Cart Management**
   - ➕ Add, ➖ remove, and 👁️ view items in the shopping cart.
   - 🛒 Cart operations are linked to 👤 users.

3. **📦 Order Management**
   - 🛒 Place and 👀 retrieve orders.
   - Maintain 🗂️ order history for 👤 users.

4. **❤️ Likes**
   - 🔄 Manage product likes by 👤 users.

5. **🔒 JWT Authentication**
   - 👤 User login and 🔑 token generation.
   - 🔒 Protect routes with 🛠️ middleware.

---

## 💻 Technologies Used

- **🟢 Node.js**: JavaScript runtime for building 🚀 scalable applications.
- **⚙️ Express.js**: Framework for creating 🌐 RESTful APIs.
- **🍃 MongoDB**: 🛢️ NoSQL database for data storage.
- **🖋️ Mongoose**: ODM (Object Data Modeling) library for 🍃 MongoDB.
- **🔒 JSON Web Tokens (JWT)**: Secure user authentication.

---

## ⚙️ Installation and Setup

1. **📥 Clone the repository**:
   ```bash
   git clone https://github.com/ThatikondaMahesh/ecom-api-backend-rest-api.git
   ```

2. **⬇️ Install dependencies**:
   ```bash
   npm install
   ```

3. **🛠️ Set up MongoDB**:
   - Configure the `mongodb.js` file in the `src/config/` directory with your 🍃 MongoDB connection string.

4. **🔧 Set up JWT**:
   - Add a 🔑 secret key in your `.env` file for token generation and validation.

5. **▶️ Run the application**:
   ```bash
   node server
   ```

6. **🌐 Access the API**:
   The API will run on `http://localhost:3000` (default port).

---

## 📡 API Endpoints

### 🛍️ Product APIs
- **📥 GET** `/products` - 👁️ Get all products.
- **➕ POST** `/products` - ✏️ Create a new product.
- **✏️ PUT** `/products/:id` - ✏️ Update a product.
- **❌ DELETE** `/products/:id` - ❌ Delete a product.

### 🛒 Cart APIs
- **📥 GET** `/cart-items` - 👁️ View items in the cart.
- **➕ POST** `/cart-items` - ➕ Add an item to the cart.
- **❌ DELETE** `/cart-items/:id` - ➖ Remove an item from the cart.

### 📦 Order APIs
- **📥 GET** `/orders` - 👁️ Get user orders.
- **➕ POST** `/orders` - 🛒 Place a new order.

### ❤️ Like APIs
- **➕ POST** `/likes` - ❤️ Like a product.
- **❌ DELETE** `/likes/:id` - ❌ Remove like from a product.

### 🔒 Authentication APIs
- **➕ POST** `/auth/login` - Authenticate user and generate 🔑 JWT.
- **📥 GET** `/auth/protected-route` - Access a protected route (requires token).

---

## 🛡️ JWT Authentication and Middleware

1. **🔑 JWT Generation**:
   - After 👤 user login, a 🔑 JWT token is generated and sent as a response.

2. **🛡️ Middleware**:
   - `authMiddleware.js`: Verifies the token on protected routes to ensure 👤 user authentication.

3. **🔒 Example Usage**:
   - Add `authMiddleware` to routes that require authentication:
     ```javascript
     const { authMiddleware } = require('../middleware/authMiddleware');
     router.get('/protected-route', authMiddleware, (req, res) => {
       res.send('Access granted!');
     });
     ```

---

## ⚠️ Error Handling

⚙️ Custom error handling middleware is implemented in the `src/error-handler/applicationError.js` file to standardize 🌐 API responses and manage errors gracefully.

---

## 🗂️ Folder Explanation

- **`⚙️ config`**: Contains ⚙️ configuration files for 🍃 MongoDB and 🖋️ Mongoose.
- **`⚠️ error-handler`**: Handles ⚠️ application-level errors.
- **`🛡️ middleware`**: Includes 🛡️ authentication middleware for verifying JWT tokens.
- **`🧩 features`**: Contains feature-specific modules (e.g., 🛒 cartItems, ❤️ like, 📦 order, 🛍️ product).
  - Each feature has its own 📂 controller, 📂 model, 📂 repository, 📂 routes, and 📂 schema files for separation of concerns.

---

## 🤝 Contributing
👥 Contributions are welcome! Feel free to open ⚠️ issues or submit ➕ pull requests for improvements.

---

## 📜 License
This project is licensed under the [📝 MIT License](LICENSE).

---

## 🙋 Author
- **Your Name**:T.Mahesh
- **📧 Email**: thatimahesh766@gmail.com
- **🔗 GitHub**: [GitHub](https://github.com/ThatikondaMahesh/)

