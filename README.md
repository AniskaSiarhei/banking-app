# Banking App REST API

This project implements a RESTful API for managing bank accounts. It allows users to perform basic banking operations such as creating accounts, retrieving account details, making deposits and withdrawals, and deleting accounts.

## Key Features

•   **RESTful API Design:** Utilizes standard HTTP methods (GET, POST, PUT, DELETE) for performing operations on bank accounts.
•   **Data Transfer Objects (DTOs):** Uses DTOs to encapsulate data transfer between layers.
•   **JPA with Hibernate:** Employs Spring Data JPA with Hibernate for database interaction.
•   **MySQL Database:** Uses MySQL as the underlying data storage.
•   **Custom Exceptions:** Implements custom exceptions for better error handling and specific error responses.
•   **Global Exception Handling:** Provides a centralized mechanism to handle exceptions and return standardized error messages.

## Technologies Used

•   **Java 17**
•   **Spring Boot 3.1.1**
•   **Spring Web**
•   **Spring Data JPA**
•   **MySQL**
•   **Lombok**

API Endpoints

•  POST /api/accounts: Creates a new bank account.
  •  Request Body: AccountDto (JSON) - {"accountHolderName": "John Doe", "balance": 100.0}
  •  Response: 201 Created with AccountDto in the body (JSON)
•  GET /api/accounts/{id}: Retrieves an existing bank account by its ID.
  •  Response: 200 OK with AccountDto in the body (JSON).
•  PUT /api/accounts/{id}/deposit: Deposits an amount into an existing bank account.
  •  Request Body: {"amount": 50.0} (JSON)
  •  Response: 200 OK with the updated AccountDto in the body (JSON)
•  PUT /api/accounts/{id}/withdraw: Withdraws an amount from an existing bank account.
  •  Request Body: {"amount": 20.0} (JSON)
  •  Response: 200 OK with the updated AccountDto in the body (JSON)
•  GET /api/accounts: Retrieves all bank accounts.
  •  Response: 200 OK with a list of AccountDto in the body (JSON)
•  DELETE /api/accounts/{id}: Deletes a bank account by its ID.
  •  Response: 200 OK with a message "The account is deleted successfully".

  ▌Exception Handling

The application uses @RestControllerAdvice to globally handle exceptions.
•  AccountException: This custom exception is thrown when an account is not found, an attempt to withdraw with insufficient funds happens. Returns a 404 Not Found response.
•  Exception: Handles any generic exceptions and returns a 500 Internal Server Error response.
