
# E-Commerce Website

A fully functional e-commerce website built using Node.js, Express, MongoDB, and other modern web technologies. This project allows users to browse products, add them to their cart, and complete the purchase through a simple checkout process.

## Features

- Browse products by categories
- User registration and login (authentication)
- Add products to the cart and manage items
- Checkout and order confirmation
- Admin panel to manage products and orders
- Secure payments (integration with payment gateways)

## Prerequisites

Before you begin, ensure you have met the following requirements:

- Node.js (v14 or above) installed
- MongoDB (local or MongoDB Atlas) running
- npm (Node Package Manager) installed
- A payment gateway account (for integration with services like Stripe or PayPal)

## Installation

1. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/your-username/ecommerce-website.git
   cd ecommerce-website
   ```

2. Install the required dependencies:

   ```bash
   npm install
   ```

3. Set up your MongoDB database:
   - If you're using MongoDB Atlas, create a database cluster and get the connection string.
   - If you're using local MongoDB, ensure it's running on the default port (`27017`).

4. Configure your environment variables:
   Create a `.env` file in the root of your project and add the following:

   ```bash
   MONGODB_URI=mongodb://localhost:27017/ecommerce
   PORT=5000
   SECRET_KEY=your-secret-key
   PAYMENT_GATEWAY_API_KEY=your-payment-gateway-api-key
   ```

   Replace `MONGODB_URI` with your MongoDB connection string if you're using MongoDB Atlas and provide the necessary API keys.

## Usage

1. Start the application:

   ```bash
   npm start
   ```

2. Visit `http://localhost:5000` in your browser.

3. You can browse products, add them to your cart, and proceed to checkout.

4. Admin users can log in and manage products and orders from the admin panel.

## API Endpoints

### POST `/register`
Registers a new user.

**Request body:**
```json
{
  "username": "john_doe",
  "email": "john@example.com",
  "password": "yourpassword"
}
```

### POST `/login`
Logs in a user.

**Request body:**
```json
{
  "email": "john@example.com",
  "password": "yourpassword"
}
```

### GET `/products`
Gets a list of products.

**Response:**
```json
[
  {
    "id": "1",
    "name": "Product 1",
    "price": 29.99,
    "description": "A great product"
  },
  {
    "id": "2",
    "name": "Product 2",
    "price": 19.99,
    "description": "Another great product"
  }
]
```

### POST `/checkout`
Checks out the cart and processes the payment.

**Request body:**
```json
{
  "userId": "12345",
  "cart": [
    {
      "productId": "1",
      "quantity": 2
    },
    {
      "productId": "2",
      "quantity": 1
    }
  ],
  "paymentDetails": {
    "cardNumber": "4111111111111111",
    "expirationDate": "12/25",
    "cvv": "123"
  }
}
```

**Response:**
```json
{
  "status": "success",
  "orderId": "67890",
  "totalAmount": 79.97
}
```

## Contributing

If you want to contribute to this project, feel free to fork the repository, make changes, and submit a pull request. You can also open issues for any bugs or feature requests.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
```

This `README.md` provides a comprehensive overview of your e-commerce website, installation steps, API details, and usage instructions. Modify it according to your project's specific features and configurations.
