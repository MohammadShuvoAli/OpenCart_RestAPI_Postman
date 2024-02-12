# OpenCart RestAPI Cart Module Testing

This project involves testing the OpenCart RestAPI Cart Module using Postman. The tests include creating a session/token, adding products to the cart, viewing cart contents, editing product quantity in the cart, and removing products from the cart. The tests are exported in Postman format and are suitable for command-line execution using Newman. Integration with Jenkins is also set up for automated testing.

## Project Structure

- **Create Session/Token**
  - Endpoint: `{{baseURL}}api/login`
  - Method: POST
  - Parameters: `username`, `key`
  - Tests: Validates status code (200) and success message. Captures `api_token` for future use.

- **Add Product to Cart**
  - Endpoint: `{{baseURL}}api/cart/add`
  - Method: POST
  - Authentication: API key using `api_token`
  - Parameters: `product_id`, `quantity`
  - Tests: Validates status code (200) and success message.

- **Cart Content**
  - Endpoint: `{{baseURL}}api/cart/products`
  - Method: GET
  - Authentication: API key using `api_token`
  - Tests: Validates status code (200) and captures `cart_id` for future use.

- **Edit Product Quantity in Cart**
  - Endpoint: `{{baseURL}}api/cart/edit`
  - Method: POST
  - Authentication: API key using `api_token`
  - Parameters: `key` (cart_id), `quantity`
  - Tests: Validates status code (200) and success message.

- **Remove Product from Cart**
  - Endpoint: `{{baseURL}}api/cart/remove`
  - Method: POST
  - Authentication: API key using `api_token`
  - Parameters: `key` (cart_id)
  - Tests: Validates status code (200), success message, and resets collection and environment variables.

## Environment Variables

- `ip`: IP address for the OpenCart server.
- `baseURL`: Base URL for API requests.
  
## Screenshots

- **Command Prompt Report**
  ![Command Prompt Report](https://github.com/MohammadShuvoAli/OpenCart_RestAPI_Postman/blob/main/Screenshot/Command_Prompt_Report.PNG)

- **HTML Report**
  ![HTML Report](https://github.com/MohammadShuvoAli/OpenCart_RestAPI_Postman/blob/main/Screenshot/Newman_Report.PNG)

- **Jenkins Integration**
  ![Jenkins Integration](https://github.com/MohammadShuvoAli/OpenCart_RestAPI_Postman/blob/main/Screenshot/Jenkins_Integration.PNG)
