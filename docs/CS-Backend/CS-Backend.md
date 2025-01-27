# C# Backend Project Overview

## Backend Definition
The Webstore Backend project is a server-side application designed to manage the core functionalities of an online store. It provides APIs for user authentication, product management, order processing, and other essential e-commerce operations. This backend interacts with databases, handles business logic, and ensures secure communication with clients.

**Backend Features:**

- User authentication and authorization using JWT tokens.
- Order creation and tracking.
- Integration with third-party services.
- Secure and scalable architecture.

## Architecture
The backend is developed using the following architecture and technologies:

**Architecture:**

- **Layered Architecture**: Separation of concerns with controllers, services, and repositories.
- **RESTful APIs**: Exposes endpoints for client applications to interact with the backend.
- **Containerization**: Dockerized setup for consistent deployment.

**Technologies:**

- **Programming Language**: C# (.NET 9). [Official Documentation](https://learn.microsoft.com/en-us/dotnet/)
- **Framework**: ASP.NET Core for building APIs. [ASP.NET Core Documentation](https://learn.microsoft.com/en-us/aspnet/core/)
- **Database**: PostgreSQL. [PostgreSQL Documentation](https://www.postgresql.org/docs/)
- **Authentication**: JWT tokens for secure user sessions. [JWT.io Documentation](https://jwt.io/introduction/)
- **Dependency Injection**: Built-in .NET Core DI framework. [Dependency Injection Documentation](https://learn.microsoft.com/en-us/dotnet/core/extensions/dependency-injection)
- **Configuration Management**: JSON configuration files and environment variables. [Configuration in .NET](https://learn.microsoft.com/en-us/aspnet/core/fundamentals/configuration/)
- **Containerization**: Docker and Docker Compose for deployment. [Docker Documentation](https://docs.docker.com/) | [Docker Compose Documentation](https://docs.docker.com/compose/)

## Use Cases

### User Registration

**Scenario**: A user can register on the application by providing necessary details such as email, username, and password.

**Flow**:

1. User provides registration details via a client application.
2. If valid, the backend creates a new user record in the database and encrypts the password for security.
3. The user receives a success message upon successful registration.
 
### User Login

**Scenario**: A user logs in.

**Flow**:

1. The user submits their login credentials via the frontend.
2. The backend validates the credentials against the database.
3. If valid, an authentication token is generated and returned to the frontend.
4. The frontend stores the token securely for subsequent requests.

**Scenario**: A user logs out.

**Flow**:

1. The user initiates a logout request via the frontend.
2. The frontend clears the locally stored authentication token.
3. A confirmation of the logout is returned to the frontend.

**Scenario**: A user stays logged in (handled via token).

**Flow**:

1. Upon login, the backend issues a token with an expiration period (e.g., a JWT).
2. The frontend includes the token in subsequent API requests for authentication.
3. The backend validates the token on each request to ensure it is still valid.
4. If the token is expired or invalid, the user is prompted to log in again.
  
### Cart Management

**Scenario**: A user adds a new product to the cart.

**Flow**:

1. The user selects a product and submits an "add to cart" request via the frontend.
2. The backend validates the product ID and checks availability.
3. The product is added to the user's cart in the database.
4. The updated cart data is returned to the frontend.

**Scenario**: A user removes a product from the cart.

**Flow**:

1. The user selects a product to remove and submits a "remove from cart" request.
2. The backend verifies the product exists in the user's cart.
3. The product is removed from the cart in the database.
4. The updated cart data is returned to the frontend.

**Scenario**: A user increases the quantity of a product in the cart.

**Flow**:

1. The user selects a product and submits an "increase quantity" request.
2. The backend verifies the product is in the cart and checks stock availability.
3. The quantity of the product in the cart is updated in the database.
4. The updated cart data is returned to the frontend.

**Scenario**: A user decreases the quantity of a product in the cart.

**Flow**:

1. The user selects a product and submits a "decrease quantity" request.
2. The backend verifies the product is in the cart and ensures the quantity doesn't drop below zero.
3. The quantity of the product in the cart is updated in the database.
4. The updated cart data is returned to the frontend.

**Scenario**: A user views the current state of the cart.

**Flow**:

1. The user submits a "view cart" request.
2. The backend retrieves all items in the user's cart from the database.
3. The cart data is returned to the frontend with product details, quantities, and total cost.

###  Order Processing

**Scenario**: A customer places an order.

**Flow**:

1. Customer submits the order via the API.
2. Backend verifies product availability and processes the order.
3. Order status is updated and confirmation sent to the user.

## Basics of Project Management

**Estimated Timeline:**

- **Phase 1: Requirements Gathering** (1-2 weeks): Define scope, features, and goals.
- **Phase 2: Development** (6-8 weeks): Implement core features and APIs.
- **Phase 3: Testing** (2 weeks): Perform unit, integration, and performance tests.
- **Phase 4: Deployment** (1 week): Deploy to production environment.

**Milestones:**

- Initial API setup and user authentication completed.
- Product management module operational.
- Full order processing workflow integrated.
- Deployment-ready Dockerized application.

## Code Structure

**High-Level Directory Layout:**

```
webstore-backend/
|-- Controllers/           # API controllers handling HTTP requests
|-- Services/              # Business logic implementation
|-- Models/                # Data models and DTOs
|-- Repositories/          # Database interaction layer
|-- Configuration/         # JSON files and environment settings
|-- Infrastructure/        # Dockerfile and deployment scripts
|-- Tests/                 # Unit and integration tests
|-- Webshop.csproj         # .NET project file
```

**Key Components:**

- **Controllers**: Handle API requests and responses.
- **Services**: Contain business logic, including user management, product catalog operations, and db operations.
- **Models**: Define data structures and facilitate data exchange between layers.
- **Data**: Contain the DbContext configuration.
- **Configuration**: Centralized application settings for different environments.

**Documentation Links for Frameworks and Libraries:**

- [C# Documentation](https://learn.microsoft.com/en-us/dotnet/)
- [ASP.NET Core Documentation](https://learn.microsoft.com/en-us/aspnet/core/)
- [Microsoft SQL Server Documentation](https://learn.microsoft.com/en-us/sql/)
- [PostgreSQL Documentation](https://www.postgresql.org/docs/)
- [JWT.io Documentation](https://jwt.io/introduction/)
- [Dependency Injection in .NET](https://learn.microsoft.com/en-us/dotnet/core/extensions/dependency-injection)
- [Configuration in .NET](https://learn.microsoft.com/en-us/aspnet/core/fundamentals/configuration/)
- [Docker Documentation](https://docs.docker.com/)
- [Docker Compose Documentation](https://docs.docker.com/compose/)
