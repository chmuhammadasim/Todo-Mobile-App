# To-Do App

## Overview

The To-Do App is a Flutter-based application designed to help users manage their tasks efficiently. It allows users to create tasks with scheduled notifications, toggle between light and dark themes, and view their tasks in a list. The app ensures that notifications for tasks are sent even if the app is inactive or closed.

## Features

- **Add Tasks**: Users can enter tasks and set a due date and time.
- **Scheduled Notifications**: Notifications are scheduled and sent even if the app is not running.
- **Theming**: Users can switch between light and dark themes.
- **Task Management**: View a list of tasks, and delete them when completed.

## Screenshots

![App Screenshot](link-to-screenshot)

## Installation

To set up the project on your local machine, follow these instructions:

### Prerequisites

Ensure you have the following installed:

- [Flutter SDK](https://flutter.dev/docs/get-started/install)
- [Dart SDK](https://dart.dev/get-dart)
- [Android Studio](https://developer.android.com/studio) or [Visual Studio Code](https://code.visualstudio.com/) with Flutter and Dart plugins

### Clone the Repository

Clone the repository to your local machine:
```bash
git clone https://github.com/yourusername/todoapp.git
cd todoapp
```

### Install Dependencies

Navigate to the project directory and install the required dependencies:
```bash
flutter pub get
```

### Run the App

To run the app on an emulator or a connected device, use:
```bash
flutter run
```

## Configuration

### Notifications

#### Android

1. **Permissions and Services**: Update your `AndroidManifest.xml` file to include the necessary permissions and services:
   ```xml
   <uses-permission android:name="android.permission.RECEIVE_BOOT_COMPLETED"/>
   <application
     android:label="To-Do App"
     android:icon="@mipmap/ic_launcher">
     <receiver android:name="me.carda.notifications.notifications.NotificationReceiver" android:exported="true"/>
     <service android:name="me.carda.notifications.services.NotificationService" android:exported="true"/>
   </application>
   ```

2. **Notification Channel**: Ensure you have set up a notification channel in your code.

#### iOS

1. **Request Permissions**: Request notification permissions in your iOS app. Update `Info.plist` to include:
   ```xml
   <key>UIBackgroundModes</key>
   <array>
     <string>fetch</string>
     <string>remote-notification</string>
   </array>
   ```

2. **Local Notifications**: Make sure to configure local notifications for iOS as required.

## Code Structure

### `main.dart`

- **Entry Point**: Sets up the application, initializes notifications, and handles theme switching.

### `TodoListScreen`

- **UI for Tasks**: Displays the list of tasks, allows users to add new tasks, and manage existing ones.
- **Notification Handling**: Schedules notifications for tasks based on user input.

### `TodoItem`

- **Model Class**: Represents a task with a title and due date/time.

## Dependencies

- [flutter_local_notifications](https://pub.dev/packages/flutter_local_notifications): Handles local notifications.
- [intl](https://pub.dev/packages/intl): Provides internationalization and localization support for formatting dates and times.
- [timezone](https://pub.dev/packages/timezone): Manages timezones for scheduling notifications.

## Usage

1. **Adding a Task**: Enter the task title and select a due date and time. The task will be added to the list and a notification will be scheduled.
2. **Deleting a Task**: Swipe to delete tasks from the list.
3. **Toggling Themes**: Use the app bar button to switch between light and dark themes.

## Contributing

We welcome contributions to improve the app. To contribute:

1. **Fork the Repository**: Create your own copy of the project.
2. **Create a Branch**: Work on a new feature or bug fix in a separate branch.
3. **Submit a Pull Request**: Submit a pull request with a description of your changes.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact

For any questions, issues, or suggestions, please open an issue on the GitHub repository or contact me at [muhammadasimchattha@gmail.com](mailto:muhammadasimchattha@gmail.com).
