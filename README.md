#  API Automation Framework – Java | Rest Assured | TestNG

Welcome to the **APIFramework** – a scalable and robust automation testing framework built using **Java**, **Rest Assured**, and **TestNG**. This project is designed to test RESTful APIs efficiently with clean code architecture, modular utilities, and CI/CD readiness.

---

##  Highlights

-  Clean, scalable, and modular codebase
-  Supports **GET**, **POST**, **PUT**, **DELETE** methods
-  Centralized base configuration and request/response specs
-  Test execution using **TestNG**
-  Response validation using JSONPath & Hamcrest matchers
-  Token-based authentication support
-  Data-driven testing support
-  Custom utilities for response handling, reporting, logging
-  Ready for CI tools like Jenkins & GitHub Actions

---

## Tech Stack

| Tool/Library     | Purpose                            |
|------------------|------------------------------------|
| Java             | Core programming language          |
| Rest Assured     | API interaction and validation     |
| TestNG           | Test runner and reporting          |
| Maven            | Build & dependency management      |
| Log4j            | Logging                            |
| Jackson / GSON   | JSON serialization/deserialization |

---

## Project Structure

```
APIFramework/
├── src/
│   ├── main/java/
│   │   ├── base/         # Base classes (BaseTest, BaseRequest)
│   │   └── utils/        # Utility functions (config, data, token)
│   ├── test/java/
│   │   └── tests/        # Test classes (UserTests, AuthTests)
├── config.properties     # Base URI, tokens, env details
├── pom.xml               # Maven dependencies
├── testng.xml            # TestNG suite file
```

---

## Sample Test Case

```java
@Test
public void getUserDetails() {
    given()
        .baseUri(BASE_URL)
        .header("Authorization", "Bearer " + token)
    .when()
        .get("/users/123")
    .then()
        .statusCode(200)
        .body("data.id", equalTo(123))
        .body("data.email", containsString("@example.com"));
}
```

---

## How to Run

1. **Clone the repo**  
   `git clone https://github.com/kshit19/APIFramework.git`

2. **Import in IntelliJ or Eclipse** as a Maven project

3. **Update `config.properties`** with the base URL, tokens, and other test data

4. **Run tests**
   - From `testng.xml` file  
   - Or via Maven:  
     `mvn clean test`

---

## Reporting

You can integrate:
- **ExtentReports** – HTML report generation  
- **Allure** – advanced test reporting (optional)

---

## Author

**Kshitija**  
QA Automation Engineer  
India  
[LinkedIn](#) : https://www.linkedin.com/in/kshitija-lohar-094040271/

---

## Notes

- Designed for fast onboarding and API test automation
- Extendable for environment-based execution (dev/stage/prod)
- Feel free to fork or contribute!
