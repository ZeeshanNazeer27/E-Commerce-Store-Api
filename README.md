# API Testing Project: DummyJSON E-commerce API

A practice project where I tested REST API requests in Postman. It was built while learning API testing, using DummyJSON's public test API (https://dummyjson.com/docs). It is not a real product or client project.

## Tools
Postman, REST API, JSON

## Requests 
| # | Request | Method | Endpoint | Expected status | What the test checks |
|---|---------|--------|----------|-----------------|----------------------|
| 1 | Login | POST | /auth/login | 200 | Status code. Saves the access token as `token` |
| 2 | Get User Profile | GET | /auth/me | 200 | Status code. Uses the saved token |
| 3 | Get Products | GET | /products | 200 | Status code. Saves the first product's ID as `products_id` |
| 4 | Get Single Product | GET | /products/{{products_id}} | 200 | Status code |
| 5 | Add Cart | POST | /carts/add | 201 | Status code. Cart contains products. Saves the cart ID as `cart_id` |

## Error checks
- Get User Profile with the auth token removed: "Access Token is required"
- Add Cart with a user ID that does not exist: "Product with id '11111' not found"

## Notes
DummyJSON is a test API. Actions like adding to a cart are simulated, so the data is not saved on the server.
