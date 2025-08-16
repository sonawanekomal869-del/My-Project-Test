# Ecommerce Backend API

A Node.js backend API for ecommerce product browsing functionality.

## Features

- ✅ Product browsing with all products
- ✅ Search products by name/keywords
- ✅ Filter products by category, price, and availability
- ✅ Get products by ID
- ✅ Get products by category
- ✅ Get all categories
- ✅ Comprehensive API testing
- ✅ Health check endpoint

## Product Data Structure

Each product contains:
- **ID**: Unique identifier
- **Name**: Product name
- **Description**: Product description
- **Price**: Product price (number)
- **Stock Quantity**: Available stock (number)
- **Category**: Product category
- **Images**: Array of image URLs

## Quick Start

### 1. Install Dependencies

```bash
npm install
```

### 2. Start the Server

```bash
# Development mode (with auto-restart)
npm run dev

# Production mode
npm start
```

The server will start on `http://localhost:3000`

### 3. Test the API

```bash
# Run automated tests
npm test

# Run tests in watch mode
npm run test:watch

# Run manual API tests
node test-api.js
```

## API Endpoints

### Health Check
```
GET /api/health
```
Returns server health status.

### Get All Products
```
GET /api/products
```
Returns all products with optional filters.

**Query Parameters:**
- `search`: Search term for name/description/category
- `category`: Filter by category
- `minPrice`: Minimum price filter
- `maxPrice`: Maximum price filter
- `availability`: Filter by stock availability ('inStock' or 'outOfStock')

**Example:**
```
GET /api/products?search=iPhone&category=Electronics&minPrice=500&maxPrice=1000
```

### Get Product by ID
```
GET /api/products/:id
```
Returns a specific product by ID.

**Example:**
```
GET /api/products/1
```

### Get Products by Category
```
GET /api/products/category/:category
```
Returns all products in a specific category.

**Example:**
```
GET /api/products/category/Electronics
```

### Search Products
```
GET /api/products/search/:query
```
Returns products matching the search query.

**Example:**
```
GET /api/products/search/iPhone
```

### Get All Categories
```
GET /api/categories
```
Returns all available product categories.

## API Response Format

All API responses follow this format:

```json
{
  "success": true,
  "data": [...],
  "total": 5,
  "message": "Products retrieved successfully"
}
```

Error responses:
```json
{
  "success": false,
  "message": "Error message"
}
```

## Testing

### Automated Tests (Jest + Supertest)

The project includes comprehensive automated tests covering:
- All API endpoints
- Response formats
- Error handling
- Data validation
- Filter functionality
- Search functionality

Run tests:
```bash
npm test
```

### Manual API Testing

Use the included test script for manual testing:
```bash
node test-api.js
```

This script will:
- Check if the server is running
- Test all endpoints
- Display detailed results
- Show sample data
- Provide a test summary

## Sample Data

The API comes with sample products:
- iPhone 15 Pro (Electronics)
- MacBook Air M2 (Electronics)
- Nike Air Max 270 (Footwear)
- Samsung 4K Smart TV (Electronics)
- Adidas Ultraboost 22 (Footwear)

## Development

### Project Structure
```
ecommerce-backend/
├── server.js          # Main server file
├── package.json       # Dependencies and scripts
├── jest.config.js     # Jest configuration
├── test-api.js        # Manual API testing script
├── tests/
│   └── api.test.js    # Automated tests
└── README.md          # This file
```

### Adding New Features

1. **Add new endpoints** in `server.js`
2. **Add tests** in `tests/api.test.js`
3. **Update test cases** in `test-api.js`
4. **Update documentation** in this README

## Production Considerations

For production deployment:
- Replace in-memory data with a database (MongoDB, PostgreSQL, etc.)
- Add authentication and authorization
- Implement rate limiting
- Add input validation
- Set up proper logging
- Configure environment variables
- Add API documentation (Swagger/OpenAPI)

## License

ISC
# My-Project-Test
