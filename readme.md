# Game Rental Backend

Welcome to the Game Rental Backend repository! This backend application is designed to facilitate game rentals for both gamers and sellers. Below, you'll find information on the features, APIs, and data storage used in this project.

## Application Details

- *Backend Technologies*: Node, Express, MongoDB
- *Frontend*: No frontend implementation (backend only)
- *End-Users*: Gamers, Sellers

## Postman Collection

- *For testing the APIs, you can use the [![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/29328925-abfed150-26c1-466e-a048-05cafe9ec458?action=collection%2Ffork&source=rip_markdown&collection-url=entityId%3D29328925-abfed150-26c1-466e-a048-05cafe9ec458%26entityType%3Dcollection%26workspaceId%3Ded4f1f64-4b2b-445c-8f64-35a46a7b3a73) provided.

1. [Download Postman](https://www.postman.com/downloads/) if you haven't already.
## Application Features

### Common Functionalities

#### Login

- *Method*: POST
- *Request Data*: { "username": "abc", "password": "abc@123" }
- *Response Data (Success)*: { "userId": 12, "message": "Login Successful" }
- *Response Data (Failure)*: { "status": 400, "message": "Invalid Login Credentials" }

#### Register

- *Method*: POST
- *Request Data*: { "username": "", "email": "", "password": "", "firstName": "", "lastName": "", "contactNumber": "", "userType": "" }
- *Response Data (Success)*: { "userId": "", "username": "", "email": "", "password": "", "firstName": "", "lastName": "", "contactNumber": "", "userType": "" }
- *Response Data (Failure)*: { "status": 400, "message": "Please provide email" }

#### Homepage API

- *Method*: GET
- *Request Data*: None
- *Response Data*: Array of products with minimal details

#### Product Details

- *Method*: GET
- *Request Data*: { "productID": 123 }
- *Response Data (Success)*: Product details object
- *Response Data (Failure)*: { "status": 404, "message": "Product Not Found" }

#### Save/Remove from Wishlist

- *Method*: PUT
- *Request Data*: { "userID": 1, "productID": 123 }
- *Response Data (Success)*: Array of wishlist products
- *Response Data (Failure)*: { "status": 404, "message": "Error Message" }

#### Add/Remove from Cart

- *Method*: PUT
- *Request Data*: { "userID": 1, "productID": 123, "count": 2, "bookingStartDate": "2024-01-01", "bookingEndDate": "2024-01-07" }
- *Response Data (Success)*: Array of cart products
- *Response Data (Failure)*: { "status": 400, "message": "Only 4 units available" }

#### Place Order

- *Method*: POST
- *Request Data*: { "userID": 1 }
- *Response Data (Success)*: Array of ordered products
- *Response Data (Failure)*: { "status": 404, "message": "Error Message" }

#### View User Details

- *Method*: GET
- *Request Data*: { "username": "qaifi" }
- *Response Data (Success)*: User details object
- *Response Data (Failure)*: { "status": 404, "message": "Error Message" }

#### Update User Details

- *Method*: PUT
- *Request Data*: { "userID": 1, "firstName": "John", "lastName": "Doe", "email": "john.doe@example.com", "contactNumber": "1234567890", "userType": "Gamer" }
- *Response Data (Success)*: Updated user details object
- *Response Data (Failure)*: { "status": 404, "message": "Error Message" }

### Seller Functionalities

#### Create Product

- *Method*: POST
- *Request Data*: { "title": "Game Title", "thumbnailURL": "url", "sellerUsername": "seller", "unitsAvailable": 10, "productType": "game", "productImages": [], "rentalPricePerWeek": 50, "rentalPricePerMonth": 150 }
- *Response Data (Success)*: Created product details
- *Response Data (Failure)*: { "status": 400, "message": "Error Message" }

#### Update Product

- *Method*: PUT
- *Request Data*: { "productID": 123, "title": "Updated Title", "thumbnailURL": "updated_url", "sellerUsername": "seller", "unitsAvailable": 8, "productType": "game", "productImages": [], "rentalPricePerWeek": 60, "rentalPricePerMonth": 180 }
- *Response Data (Success)*: Updated product details
- *Response Data (Failure)*: { "status": 400, "message": "Error Message" }

## Data Storage

- Create a new FREE cluster on MongoDB Cloud (Atlas).
- Set the cluster URL in the DATABASE_URL constant in the database.js file.

Feel free to explore and contribute to this backend application for a seamless gaming experience!