# Flutter Clean Architecture Project

[Read this in Russian / Читать на русском](./README.ru.md)

An application built on the Flutter framework, developed using the principles of Clean Architecture and efficient state management with Riverpod.

The main goal of this project is to demonstrate the separation of business logic, UI, and data handling to create a scalable, testable, and maintainable codebase.

## Project Architecture

The code is structured using a feature-first approach, where each feature is divided into three independent layers:

1. **Domain (Business Logic Layer):**
   * A completely independent layer with pure Dart code and no dependencies on Flutter or third-party libraries.
   * Contains `Entities` (business objects), `Use Cases` (application logic scenarios), and `Repository Interfaces` (contracts for data).

2. **Data (Data Layer):**
   * Implements the contracts defined in the Domain layer.
   * Responsible for fetching data from external resources via `Data Sources` (Remote API / Local Database).
   * Contains `Models` (DTO objects for JSON serialization).

3. **Presentation (UI Layer):**
   * Responsible for rendering data to the user.
   * Uses `Riverpod` (Notifier/FutureProvider) for state management and isolating UI logic.
   * Contains widgets and pages.

## Tech Stack

* **Framework:** Flutter & Dart
* **State Management:** Riverpod (state management and DI)
* **Networking:** Dio / Http (network requests)
* **Local Database:** Isar / Hive / Shared Preferences (caching)
* **Code Generation:** Freezed / Json Serializable (if required)

## How to Run the Project

1. Clone the repository:
   ```bash
   git clone https://github.com
   ```
2. Navigate to the project directory:
   ```bash
   cd clean_architecture_flutter
   ```
3. Install dependencies:
   ```bash
   flutter pub get
   ```
4. (Optional) Run code generation if you use build_runner:
   ```bash
   flutter pub run build_runner build --delete-conflicting-outputs
   ```
5. Run the application:
   ```bash
   flutter run
   ```
