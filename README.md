# Flutter Clean Architecture Project

Приложение на фреймворке **Flutter**, разработанное с применением принципов **Clean Architecture (Чистой архитектуры)** и эффективного управления состоянием с помощью **Riverpod**.

Основная цель проекта — продемонстрировать разделение бизнес-логики, UI и работы с данными для создания масштабируемого, тестируемого и поддерживаемого кода.

## Архитектура проекта

Код структурирован по фичам (feature-first approach), где каждая фича делится на три независимых слоя:

1. **Domain (Слой бизнес-логики):**
   * Абсолютно независимый слой (чистый Dart без зависимостей от Flutter/сторонних библиотек).
   * Содержит `Entities` (бизнес-объекты), `Use Cases` (сценарии использования) и `Repository Interfaces` (контракты для данных).

2. **Data (Слой данных):**
   * Реализует контракты из слоя Domain.
   * Отвечает за получение данных из внешних источников via `Data Sources` (удаленный API/локальная БД).
   * Содержит `Models` (DTO-объекты для маппинга JSON).

3. **Presentation (Слой интерфейса):**
   * Отвечает за отображение данных пользователю.
   * Использует `Riverpod` (Notifier/FutureProvider) для управления состоянием и изоляции логики UI.
   * Содержит виджеты и страницы.

## Стек технологий

* **Framework:** Flutter & Dart
* **State Management:** Riverpod (управление состоянием и DI)
* **Networking:** Dio / Http (работа с сетью)
* **Local Database:** Isar / Hive / Shared Preferences (кэширование)
* **Code Generation:** Freezed / Json Serializable (при необходимости)

## Как запустить проект

1. Клонируйте репозиторий:
   ```bash
   git clone https://github.com
   ```
2. Перейдите в папку проекта:
   ```bash
   cd clean_architecture_flutter
   ```
3. Установите зависимости:
   ```bash
   flutter pub get
   ```
4. (Опционально) Запустите генерацию кода, если используете build_runner:
   ```bash
   flutter pub run build_runner build --delete-conflicting-outputs
   ```
5. Запустите приложение:
   ```bash
   flutter run
   ```
