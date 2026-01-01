# 🚗 Car Rental System — OOP (Java)

[![Build Status](https://img.shields.io/github/actions/workflow/status/hansaPiyumal/Car-rental-system-OOP-/ci.yml?branch=main&label=build&style=for-the-badge)](https://github.com/hansaPiyumal/Car-rental-system-OOP-/actions)
[![Issues](https://img.shields.io/github/issues/hansaPiyumal/Car-rental-system-OOP-?style=for-the-badge)](https://github.com/hansaPiyumal/Car-rental-system-OOP-/issues)
[![License](https://img.shields.io/github/license/hansaPiyumal/Car-rental-system-OOP-?style=for-the-badge)](https://github.com/hansaPiyumal/Car-rental-system-OOP-/blob/main/LICENSE)
[![Stars](https://img.shields.io/github/stars/hansaPiyumal/Car-rental-system-OOP-?style=for-the-badge)](https://github.com/hansaPiyumal/Car-rental-system-OOP-/stargazers)
[![Last Commit](https://img.shields.io/github/last-commit/hansaPiyumal/Car-rental-system-OOP-?style=for-the-badge)](https://github.com/hansaPiyumal/Car-rental-system-OOP-/commits)

A clean, object-oriented Java backend project modeling a car rental system. This repository focuses on OOP principles (encapsulation, inheritance, polymorphism, SOLID design), domain modeling (cars, customers, reservations), and easy extensibility.

---

## ✨ Highlights

- Clear domain model: Car, Customer, Rental/Reservation, Pricing
- OOP-first design — easy to extend and test
- Simple persistence layer (plug-in for file/DB)
- Unit-test friendly structure
- Starter README to help contributors get up and running

---

## 🧭 Features (example)

- Manage fleet: add, update, list cars
- Customer management: registration and lookup
- Rental bookings: create, cancel, return
- Availability checks and basic pricing rules
- Invoice generation (text/console)
- Well-separated layers: model, service, repository, CLI/REST adapter

> Note: Exact implemented features depend on project code — this README provides a complete guide for a typical OOP car rental backend.

---

## 🛠 Tech Stack

- Java 8+ (recommended: 11+)
- Build: Maven or Gradle (project uses whichever you prefer)
- Testing: JUnit
- (Optional) REST: Spring Boot (if present)
- (Optional) DB: H2 / MySQL or file-based persistence

---

## 🚀 Quick Start

Prerequisites
- Java 8 or later installed (JAVA_HOME set)
- Maven (or Gradle) installed if you use the CLI build steps
- Git

Clone
```bash
git clone https://github.com/hansaPiyumal/Car-rental-system-OOP-.git
cd Car-rental-system-OOP-
```

Build (Maven)
```bash
mvn clean package
```

Run (if project produces an executable jar)
```bash
java -jar target/*.jar
```

Run in your IDE
- Import as a Maven/Gradle project
- Locate and run the main class (e.g., `com.yourpackage.Main` or `App`)

If the repo provides a REST API (Spring Boot), run and visit:
- http://localhost:8080/ (or configured port)
- Example endpoints:
  - GET /cars
  - POST /rentals
  - GET /customers/{id}

Example curl (if REST present)
```bash
# List cars
curl -s http://localhost:8080/cars | jq

# Create a rental
curl -X POST http://localhost:8080/rentals \
  -H "Content-Type: application/json" \
  -d '{"carId":123,"customerId":456,"from":"2026-01-10","to":"2026-01-15"}'
```

---

## 🗂 Suggested Project Structure

A typical layout for this kind of project:

```
src/
├─ main/
│  ├─ java/
│  │  ├─ com.example.rental/
│  │  │  ├─ model/        # Car, Customer, Rental, Invoice, enums
│  │  │  ├─ repository/   # interfaces + file/db implementations
│  │  │  ├─ service/      # business logic
│  │  │  ├─ api/          # REST controllers or CLI adapters
│  │  │  └─ App.java       # Main class (if applicable)
│  └─ resources/
└─ test/
   └─ java/               # unit tests (JUnit)
```

---

## ✅ Contributing

Contributions are welcome! Suggested workflow:

1. Fork the repository
2. Create a feature branch: `git checkout -b feat/my-feature`
3. Implement changes with tests
4. Run tests locally: `mvn test`
5. Open a pull request describing changes

Please follow the existing code style and add unit tests for new behavior.

---

## 🧪 Testing

Run unit tests with:
```bash
mvn test
```

If using Gradle:
```bash
./gradlew test
```

---

## 📘 Design Notes & Tips

- Keep services small and focused — one responsibility per class.
- Use interfaces for repositories to make switching persistence implementations trivial.
- Favor immutability for value objects (e.g., Money, Date ranges).
- Add validation early (dates, availability) in the service layer.
- Write unit tests for business rules (pricing, availability, overlap detection).

---

## 📝 License

This project can be distributed under the MIT License. If you want to add a license file, create a `LICENSE` with your chosen terms.

---

## 💬 Contact & Support

If you have questions, feature requests, or want a code review, open an issue in this repository and tag @hansaPiyumal.

---

Thank you for checking out this Car Rental System — happy coding! 🚘🎉
