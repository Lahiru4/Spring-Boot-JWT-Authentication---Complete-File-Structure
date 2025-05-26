# Spring Boot JWT Authentication - Complete File Structure

```
jwt-auth-app/
│
├── pom.xml
├── README.md
├── .gitignore
├── .env.example
│
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/
│   │   │       └── example/
│   │   │           ├── JwtAuthApplication.java
│   │   │           │
│   │   │           ├── config/
│   │   │           │   ├── SecurityConfig.java
│   │   │           │   ├── CorsConfig.java
│   │   │           │   └── AsyncConfig.java
│   │   │           │
│   │   │           ├── controller/
│   │   │           │   ├── AuthController.java
│   │   │           │   ├── TestController.java
│   │   │           │   └── UserController.java
│   │   │           │
│   │   │           ├── dto/
│   │   │           │   ├── AuthRequest.java
│   │   │           │   ├── AuthResponse.java
│   │   │           │   └── UserDto.java
│   │   │           │
│   │   │           ├── entity/
│   │   │           │   ├── User.java
│   │   │           │   ├── AuthProvider.java
│   │   │           │   ├── VerificationToken.java
│   │   │           │   └── RefreshToken.java
│   │   │           │
│   │   │           ├── repository/
│   │   │           │   ├── UserRepository.java
│   │   │           │   ├── VerificationTokenRepository.java
│   │   │           │   └── RefreshTokenRepository.java
│   │   │           │
│   │   │           ├── service/
│   │   │           │   ├── AuthService.java
│   │   │           │   ├── CustomUserDetailsService.java
│   │   │           │   ├── EmailService.java
│   │   │           │   ├── SmsService.java
│   │   │           │   ├── UserService.java
│   │   │           │   └── TokenCleanupService.java
│   │   │           │
│   │   │           ├── security/
│   │   │           │   ├── JwtUtil.java
│   │   │           │   ├── JwtAuthenticationFilter.java
│   │   │           │   ├── OAuth2AuthenticationSuccessHandler.java
│   │   │           │   ├── OAuth2AuthenticationFailureHandler.java
│   │   │           │   └── CustomAuthenticationEntryPoint.java
│   │   │           │
│   │   │           ├── exception/
│   │   │           │   ├── GlobalExceptionHandler.java
│   │   │           │   ├── CustomExceptions.java
│   │   │           │   ├── UserNotFoundException.java
│   │   │           │   ├── TokenExpiredException.java
│   │   │           │   └── InvalidTokenException.java
│   │   │           │
│   │   │           └── util/
│   │   │               ├── PhoneNumberValidator.java
│   │   │               ├── EmailValidator.java
│   │   │               ├── TokenGenerator.java
│   │   │               └── DateUtils.java
│   │   │
│   │   └── resources/
│   │       ├── application.properties
│   │       ├── application-dev.properties
│   │       ├── application-prod.properties
│   │       ├── application-test.properties
│   │       ├── static/
│   │       │   ├── css/
│   │       │   ├── js/
│   │       │   └── images/
│   │       └── templates/
│   │           ├── email/
│   │           │   ├── verification-email.html
│   │           │   ├── password-reset-email.html
│   │           │   └── welcome-email.html
│   │           └── sms/
│   │               └── verification-sms.txt
│   │
│   └── test/
│       └── java/
│           └── com/
│               └── example/
│                   ├── JwtAuthApplicationTests.java
│                   │
│                   ├── controller/
│                   │   ├── AuthControllerTest.java
│                   │   ├── TestControllerTest.java
│                   │   └── UserControllerTest.java
│                   │
│                   ├── service/
│                   │   ├── AuthServiceTest.java
│                   │   ├── EmailServiceTest.java
│                   │   ├── SmsServiceTest.java
│                   │   └── UserServiceTest.java
│                   │
│                   ├── security/
│                   │   ├── JwtUtilTest.java
│                   │   └── JwtAuthenticationFilterTest.java
│                   │
│                   ├── repository/
│                   │   ├── UserRepositoryTest.java
│                   │   └── VerificationTokenRepositoryTest.java
│                   │
│                   └── integration/
│                       ├── AuthIntegrationTest.java
│                       ├── OAuth2IntegrationTest.java
│                       └── SecurityIntegrationTest.java
│
├── docker/
│   ├── Dockerfile
│   ├── docker-compose.yml
│   ├── docker-compose.dev.yml
│   └── docker-compose.prod.yml
│
├── scripts/
│   ├── build.sh
│   ├── deploy.sh
│   ├── setup-database.sql
│   └── run-tests.sh
│
├── docs/
│   ├── API.md
│   ├── DEPLOYMENT.md
│   ├── SECURITY.md
│   ├── CONFIGURATION.md
│   └── postman/
│       └── JWT-Auth-Collection.json
│
└── .github/
    └── workflows/
        ├── ci.yml
        ├── build.yml
        └── deploy.yml
```

## **Detailed File Descriptions:**

### **Root Level Files:**
- `pom.xml` - Maven dependencies and build configuration
- `README.md` - Project documentation and setup instructions
- `.gitignore` - Git ignore patterns for Java/Spring Boot projects
- `.env.example` - Environment variable template

### **Main Source Code (`src/main/java/com/example/`):**

#### **Core Application:**
- `JwtAuthApplication.java` - Main Spring Boot application class

#### **Configuration (`config/`):**
- `SecurityConfig.java` - Spring Security configuration
- `CorsConfig.java` - CORS configuration for cross-origin requests
- `AsyncConfig.java` - Async processing configuration

#### **Controllers (`controller/`):**
- `AuthController.java` - Authentication endpoints (login, register, verify)
- `TestController.java` - Protected test endpoints
- `UserController.java` - User management endpoints

#### **Data Transfer Objects (`dto/`):**
- `AuthRequest.java` - Request DTOs for authentication
- `AuthResponse.java` - Response DTOs for authentication
- `UserDto.java` - User data transfer objects

#### **Entities (`entity/`):**
- `User.java` - User entity with JPA annotations
- `AuthProvider.java` - Enum for authentication providers
- `VerificationToken.java` - Email/SMS verification tokens
- `RefreshToken.java` - JWT refresh token entity

#### **Repositories (`repository/`):**
- `UserRepository.java` - User data access layer
- `VerificationTokenRepository.java` - Token data access layer
- `RefreshTokenRepository.java` - Refresh token data access layer

#### **Services (`service/`):**
- `AuthService.java` - Core authentication business logic
- `CustomUserDetailsService.java` - Spring Security user details service
- `EmailService.java` - Email sending service
- `SmsService.java` - SMS sending service
- `UserService.java` - User management service
- `TokenCleanupService.java` - Expired token cleanup service

#### **Security (`security/`):**
- `JwtUtil.java` - JWT token generation and validation
- `JwtAuthenticationFilter.java` - JWT authentication filter
- `OAuth2AuthenticationSuccessHandler.java` - OAuth2 success handler
- `OAuth2AuthenticationFailureHandler.java` - OAuth2 failure handler
- `CustomAuthenticationEntryPoint.java` - Custom authentication entry point

#### **Exception Handling (`exception/`):**
- `GlobalExceptionHandler.java` - Global exception handler
- `CustomExceptions.java` - Custom exception classes
- `UserNotFoundException.java` - User not found exception
- `TokenExpiredException.java` - Token expiration exception
- `InvalidTokenException.java` - Invalid token exception

#### **Utilities (`util/`):**
- `PhoneNumberValidator.java` - Phone number validation utilities
- `EmailValidator.java` - Email validation utilities
- `TokenGenerator.java` - Token generation utilities
- `DateUtils.java` - Date/time utility functions

### **Resources (`src/main/resources/`):**

#### **Configuration Files:**
- `application.properties` - Main configuration
- `application-dev.properties` - Development environment config
- `application-prod.properties` - Production environment config
- `application-test.properties` - Test environment config

#### **Templates (`templates/`):**
- `email/verification-email.html` - Email verification template
- `email/password-reset-email.html` - Password reset email template
- `email/welcome-email.html` - Welcome email template
- `sms/verification-sms.txt` - SMS verification template

### **Test Code (`src/test/java/com/example/`):**

#### **Unit Tests:**
- `controller/` - Controller layer tests
- `service/` - Service layer tests
- `security/` - Security component tests
- `repository/` - Repository layer tests

#### **Integration Tests:**
- `integration/` - End-to-end integration tests

### **Additional Project Files:**

#### **Docker (`docker/`):**
- `Dockerfile` - Application container definition
- `docker-compose.yml` - Multi-container setup
- `docker-compose.dev.yml` - Development containers
- `docker-compose.prod.yml` - Production containers

#### **Scripts (`scripts/`):**
- `build.sh` - Build automation script
- `deploy.sh` - Deployment script
- `setup-database.sql` - Database initialization
- `run-tests.sh` - Test execution script

#### **Documentation (`docs/`):**
- `API.md` - API documentation
- `DEPLOYMENT.md` - Deployment guide
- `SECURITY.md` - Security guidelines
- `CONFIGURATION.md` - Configuration guide
- `postman/` - Postman collection for API testing

#### **CI/CD (`.github/workflows/`):**
- `ci.yml` - Continuous integration workflow
- `build.yml` - Build workflow
- `deploy.yml` - Deployment workflow

## **Package Structure Benefits:**

1. **Separation of Concerns** - Each package has a specific responsibility
2. **Maintainability** - Easy to locate and modify specific functionality
3. **Testability** - Clear structure for unit and integration tests
4. **Scalability** - Easy to add new features without restructuring
5. **Standard Spring Boot Convention** - Follows Spring Boot best practices

## **Key Features of This Structure:**

- **Layered Architecture** - Clear separation between web, service, and data layers
- **Configuration Management** - Environment-specific configurations
- **Comprehensive Testing** - Unit and integration test structure
- **Docker Support** - Containerization ready
- **CI/CD Ready** - GitHub Actions workflows included
- **Documentation** - Comprehensive documentation structure
- **Security First** - Dedicated security package with proper separation

This structure provides a solid foundation for a production-ready Spring Boot application with JWT authentication and multiple sign-up options.
