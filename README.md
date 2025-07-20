# Automation Java RestAssured

This project provides a framework for automating API testing using Java and RestAssured[1][2]. It includes examples for testing RESTful APIs, with support for assertions, logging, and end-to-end scenarios.

## Overview

RestAssured is a Java library that simplifies API automation by handling HTTP requests and validating responses[3][2]. This repository demonstrates its use for testing endpoints like those from Reqres.in or custom APIs[1]. Hamcrest Matchers are used for assertions, and TestNG Listeners capture logs[1].

## Features

- Automated API tests with dynamic data integration[1].
- Support for CRUD operations (GET, POST, PUT, DELETE)[4].
- Logging with Log4j and Lombok for simplified data handling[1].
- Integration with Maven for dependency management[5][6].
- BDD-style scripting for readability[4].

## Prerequisites

- Java JDK installed[7].
- Maven for project management[5][6].
- IDE like IntelliJ or Eclipse[4].

## Installation

1. Clone the repository:
   ```
   git clone https://github.com/your-repo/automation-java-restassured.git
   ```

2. Navigate to the project directory:
   ```
   cd automation-java-restassured
   ```

3. Install dependencies using Maven:
   ```
   mvn install
   ```


```

## Usage

### Basic Test Structure

Use the Given-When-Then syntax for tests[8][7]:

```java
import io.restassured.RestAssured;
import static io.restassured.RestAssured.given;
import static org.hamcrest.Matchers.equalTo;

public class ApiTest {
    public void testGetUser() {
        given()
            .when().get("https://reqres.in/api/users/2")
            .then()
            .statusCode(200)
            .body("data.id", equalTo(2));
    }
}
```

Run tests with Maven:
```
mvn test
```

### Configuration

Set up base URI and content type[2]:
```java
import io.restassured.builder.RequestSpecBuilder;
import io.restassured.specification.RequestSpecification;

public class ApiConfig {
    public static RequestSpecification getRequestSpec() {
        return new RequestSpecBuilder()
            .setBaseUri("https://api.example.com")
            .setContentType("application/json")
            .build();
    }
}
```

### Advanced Examples

- **GET Request**: Fetch data and assert status[9].
- **POST Request**: Send JSON body and validate creation[7][4].
- For authentication, use `.auth().basic("username", "password")`[7].

## Testing Endpoints

This framework tests fake APIs like Reqres.in for scenarios including user creation and updates[1].

## Contributing

Fork the repository and submit pull requests for improvements.

## License

This project is licensed under the MIT License.

[1] https://github.com/mfaisalkhatri/rest-assured-examples/blob/master/README.md
[2] https://dev.to/gadekar_sachin/api-automation-with-restassured-3c0a
[3] https://gitlab.com/automation_testing8471134/rest-assured-frameworks-project
[4] https://blog.joshsoftware.com/2024/07/17/rest-assured-framework-a-guide-to-using-cucumber-bdd-and-java-language/
[5] https://github.com/PacktPublishing/REST-API-Automation-testing-from-scratch--REST-Assured-java/blob/master/README.md
[6] https://github.com/adriangonciarz/rest-assured-example/blob/master/README.md
[7] https://blog.devgenius.io/rest-assured-for-api-automation-testing-beginners-guide-5c85aefd4980?gi=6b4551d31d1e
[8] https://www.guru99.com/rest-assured.html
[9] https://dev.to/leading-edje/testing-your-api-with-java-and-rest-assured-a15
[10] https://www.youtube.com/watch?v=kay86__5eTg
