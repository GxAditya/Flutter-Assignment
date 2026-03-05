# Task Management App

A cross-platform task management and habit tracking application built with Flutter. This project demonstrates core mobile development concepts including user authentication, local data persistence, external API integration, and notification management.

---

## Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Running the App](#running-the-app)
- [Architecture](#architecture)
- [External API Integration](#external-api-integration)
- [User Stories](#user-stories)
- [License](#license)

---

## Features

**Authentication**
- User registration with name, email, and password
- Login with email and password
- Session persistence across app restarts via local storage
- Form validation with inline error feedback

**Task Management**
- View a list of to-do tasks on the home screen dashboard
- Swipe-to-complete gesture to mark tasks as done
- Navigate to a detail view for each task with description and metadata
- Visual separation of pending and completed tasks

**Settings and Profile**
- View personal information (name, email) loaded from local storage
- Edit profile placeholder for future implementation
- Categorized settings menu accessible from a navigation drawer

**Notifications**
- Toggle notifications on or off
- Select specific habits and times of day for reminders
- Send test browser notifications (web platform)
- Notification preferences persisted locally

**External API Integration**
- Fetches NASA's Astronomy Picture of the Day (APOD) via REST API
- Displays the image, title, date, copyright, and explanation
- Handles loading states and error feedback

**Data Persistence**
- User credentials stored locally using SharedPreferences
- User profile and activity logs saved and retrieved across sessions
- Notification settings persisted between app launches

---

## Tech Stack

| Component         | Technology                        |
|-------------------|-----------------------------------|
| Framework         | Flutter 3.6+                      |
| Language          | Dart                              |
| UI Toolkit        | Material Design 3 (Material You)  |
| Local Storage     | shared_preferences ^2.5.2         |
| HTTP Client       | http ^1.3.0                       |
| Platforms         | Android, iOS, Web                 |

---

## Project Structure

```
app/coursera_app/
  lib/
    main.dart              # Application entry point and theme configuration
    login_page.dart        # Login screen with form validation
    register_page.dart     # Registration screen with local data persistence
    home_page.dart         # Main dashboard with task lists and navigation drawer
    detail_page.dart       # Task detail view
    settings_page.dart     # Personal information and profile settings
    notifications_page.dart  # Notification preferences and test notifications
    planet.dart            # NASA APOD API integration and display
    local_storage.dart     # Utility class for local data read/write operations
  test/
    widget_test.dart       # Widget tests
  android/                 # Android platform configuration
  ios/                     # iOS platform configuration
  web/                     # Web platform configuration
  pubspec.yaml             # Dependencies and project metadata

UserStories/
  user_stories.md          # Detailed user stories and acceptance criteria
```

---

## Getting Started

### Prerequisites

- Flutter SDK 3.6.0 or higher
- Dart SDK (bundled with Flutter)
- Android Studio, Xcode, or a compatible IDE with Flutter support
- A physical device or emulator/simulator for testing

### Installation

1. Clone the repository:

   ```bash
   git clone <repository-url>
   cd Flutter-Assignment/app/coursera_app
   ```

2. Install dependencies:

   ```bash
   flutter pub get
   ```

### Running the App

Run on a connected device or emulator:

```bash
flutter run
```

Run specifically for web:

```bash
flutter run -d chrome
```

Run on Android:

```bash
flutter run -d android
```

Run on iOS (macOS only):

```bash
flutter run -d ios
```

---

## Architecture

The application follows a simple page-based architecture using Flutter's built-in navigation (`MaterialPageRoute`) and state management (`setState`). Each screen is implemented as a separate Dart file under the `lib/` directory.

- **Navigation**: Push/pop routing via `Navigator` with a `Drawer` widget for the main menu.
- **State Management**: Local widget state via `StatefulWidget` and `setState`.
- **Persistence**: All local data operations are centralized in `local_storage.dart` using `SharedPreferences`.
- **Theming**: Centralized Material 3 theme defined in `main.dart` with a custom color scheme seed.

---

## External API Integration

The app integrates with NASA's Astronomy Picture of the Day (APOD) API to demonstrate external data fetching.

- **Endpoint**: `https://api.nasa.gov/planetary/apod`
- **Library**: `http` package for making GET requests
- **Data Model**: `ApodData` class with JSON deserialization via a factory constructor
- **Error Handling**: Loading indicators during fetch, error messages on failure, and null-safe rendering

Note: The API key in `planet.dart` should be replaced with a valid NASA API key. You can obtain a free key at [https://api.nasa.gov](https://api.nasa.gov).

---

## User Stories

Detailed user stories with acceptance criteria are documented in `UserStories/user_stories.md`. The stories cover the following areas:

- Login and Registration
- Home Screen Dashboard
- Task Detail Screen
- Persistent Data Integration
- External API Integration
- Settings Menu and Settings Screen
- Notifications

---

## License

This project is developed as a course assignment.
