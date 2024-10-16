# API Automation Project - Simple Books API with Postman & JavaScript

## Overview

This project automates API testing for the [Simple Books API](https://simple-books-api.glitch.me) using **Postman** and **JavaScript**. The API automation is implemented to validate book listings, order management, and client registration processes, leveraging Postman’s powerful scripting capabilities in conjunction with JavaScript for dynamic API test cases. This project ensures robust testing of all critical API endpoints through automated workflows.

---

## Table of Contents

- [Overview](#overview)
- [Technologies Used](#technologies-used)
- [API Endpoints Covered](#api-endpoints-covered)
- [Project Structure](#project-structure)
- [Setup Instructions](#setup-instructions)
- [Running the Tests](#running-the-tests)
- [Postman Reports](#postman-reports)
- [SEO Keywords](#seo-keywords)
- [Contributing](#contributing)
- [License](#license)

---

## Technologies Used

- **Postman**: API testing and automation platform.
- **JavaScript**: For scripting logic within Postman.
- **Newman**: Command-line tool to run Postman collections.
- **Postman Collection Runner**: To execute requests in bulk and validate API responses.
- **JSON**: For managing test data and response validation.
- **Environment Variables**: Used in Postman to handle dynamic data (like tokens, order IDs).

---

## API Endpoints Covered

### 1. API Status Check
- **Endpoint**: `GET /status`
- **Description**: Verifies the health status of the API.

### 2. Fetch Books List
- **Endpoint**: `GET /books`
- **Query Parameters**:
  - `type`: fiction or non-fiction (optional)
  - `limit`: number between 1 and 20 (optional)
- **Description**: Retrieves a list of books with optional filters.

### 3. Fetch Book Details
- **Endpoint**: `GET /books/:bookId`
- **Description**: Retrieves details of a specific book by its ID.

### 4. Submit New Book Order
- **Endpoint**: `POST /orders`
- **Description**: Submits a new order for a book.
- **Authentication**: Requires a Bearer token.
- **Request Body**:
  ```json
  {
    "bookId": 1,
    "customerName": "John"
  }
  ```

### 5. View All Orders
- **Endpoint**: `GET /orders`
- **Description**: Lists all orders placed by the API client.
- **Authentication**: Requires a Bearer token.

### 6. Get Order Details
- **Endpoint**: `GET /orders/:orderId`
- **Description**: Retrieves details for a specific order.
- **Authentication**: Requires a Bearer token.

### 7. Update Order
- **Endpoint**: `PATCH /orders/:orderId`
- **Description**: Updates the customer name of an existing order.
- **Authentication**: Requires a Bearer token.
- **Request Body**:
  ```json
  {
    "customerName": "John"
  }
  ```

### 8. Delete Order
- **Endpoint**: `DELETE /orders/:orderId`
- **Description**: Deletes an existing order.
- **Authentication**: Requires a Bearer token.

### 9. API Client Registration
- **Endpoint**: `POST /api-clients`
- **Description**: Registers a new API client to interact with the system.
- **Request Body**:
  ```json
  {
    "clientName": "Postman",
    "clientEmail": "example@example.com"
  }
  ```

---

## Project Structure

```plaintext
postman/
├── collections/
│   └── collections\SimpleBooksAPIWithPostmanJavaScript.postman_collection.json   # Postman collection file containing all API requests
├── scripts/
│   └── pre-request.js   # JavaScript for dynamic test data generation and token management
│   └── test-scripts.js  # JavaScript assertions for validating API responses
```

- **Collections**: The `SimpleBooksAPI` collection file contains all the API requests, grouped by endpoints (e.g., Books, Orders).
- **Environment**: The environment file includes variables like `base_url`, `token`, and dynamic data for managing API sessions.
- **Scripts**: JavaScript files define dynamic behaviors and test logic for validation purposes.

---

## Setup Instructions

### Prerequisites

1. **Postman**: Download and install [Postman](https://www.postman.com/downloads/).
2. **Newman**: Install [Newman](https://www.npmjs.com/package/newman) globally if you plan to run the collection via the command line:
    ```bash
    npm install -g newman
    ```

### Steps to Setup

1. **Clone the Repository**:
    ```bash
    git clone https://github.com/MohamedSci/SimpleBooksAPIWithPostmanJavaScript.git
    cd SimpleBooksAPIWithPostmanJavaScript
    ```

2. **Import Collection**:
    - Open Postman, click on **Import**, and choose the `collections\SimpleBooksAPIWithPostmanJavaScript.postman_collection.json` file from the `postman/collections/` directory.

3. **Set API Token**:
    - In the environment, replace the placeholder `{{token}}` with your actual Bearer token obtained via the `/api-clients` endpoint.

---

## Running the Tests

### Using Postman Collection Runner

1. Open Postman and navigate to the **Collection Runner**.
2. Select the **SimpleBooksAPI** collection.
3. Choose the **SimpleBooksAPI Environment**.
4. Click **Run** to execute all the requests and view the results in Postman.

### Using Newman

To run the collection via the command line using Newman, execute:

```bash
newman run collections\SimpleBooksAPIWithPostmanJavaScript.postman_collection.json -r json,cli --reporter-json-export result.json
```

---

## Postman Reports

Newman supports generating detailed HTML and JSON reports for the executed test cases. To generate an HTML report, run:

```bash
newman run collections\SimpleBooksAPIWithPostmanJavaScript.postman_collection.json -r json,html,cli --reporter-json-export result.json --reporter-html-export newman-report.html

```

This will generate a `newman-report.html` file containing the execution summary, request details, and pass/fail results for each test case.

---

## This Project About

- Postman API automation
- JavaScript API testing
- API testing with Postman
- Postman automation framework
- Simple Books API automation
- API automation tutorial
- REST API testing in Postman
- Newman Postman collection runner
- JavaScript dynamic API tests
- Automated API validation with Postman

---

## Contributing

We welcome contributions! To contribute to this project:

1. Fork the repository
2. Create a new feature branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m 'Add new feature'`)
4. Push the branch (`git push origin feature/your-feature`)
5. Open a Pull Request for review

---

## License

This project is licensed under the Apache 2.0 License. See the [LICENSE](LICENSE) file for more details.

---
## [Buy me a Coffee☕](<https://ko-fi.com/mohamedsaidibrahim>)

If you enjoy this content and want to support me, feel free to [buy me a coffee](<https://ko-fi.com/mohamedsaidibrahim>)

Happy testing with Postman and JavaScript! 🚀
