# MY-STUDY-LIFE
Project Title: MY STUDY LIFE.               
Project Overview : My Study Life is an Android app designed to help students stay organized and on top of their academic responsibilities. It provides a centralized platform for managing classes, homework, and exams, with seamless cloud syncin
My study life was built using kotlin
# MY STUDY LIFE IMPLEMENTED 

A comprehensive Android application for managing study life with intelligent sensor-based quality tracking, cloud synchronization, and detailed analytics.

## 📱 Features

### Core Functionality
- **Class Management**: Add, view, and manage your classes with schedules
- **Homework Tracking**: Create and track homework assignments with due dates
- **Exam Management**: Schedule and track upcoming exams
- **Study Sessions**: Monitor study sessions with quality metrics

### Smart Sensor Integration
- **Accelerometer Monitoring**: Detects movement to assess focus levels
- **Light Sensor**: Monitors study environment lighting conditions
- **Proximity Sensor**: Tracks device usage patterns during study sessions
- **Real-time Quality Scoring**: Calculates study session quality based on sensor data

### Cloud & Analytics
- **Firebase Cloud Sync**: Backup and sync data across devices
- **Analytics Dashboard**: Visualize study patterns and performance trends
- **Historical Data**: Track progress over time with detailed charts
- **Settings Management**: Customize sensor sensitivity and sync preferences

## 🚀 Getting Started

### Prerequisites
- **Android Studio**: Arctic Fox (2020.3.1) or later
- **JDK**: Version 8 or higher
- **Android SDK**: API level 24 (Android 7.0) or higher
- **Device/Emulator**: Android device or emulator with sensor support

### Installation

1. **Clone the Repository**
   ```bash
   git clone <repository-url>
   cd MY-STUDY-LIFE
   ```

2. **Open in Android Studio**
   - Launch Android Studio
   - Select "Open an existing Android Studio project"
   - Navigate to the cloned directory and select it

3. **Configure Firebase (Required for Cloud Sync)**
   - Follow the detailed setup in [`FIREBASE_SETUP.md`](FIREBASE_SETUP.md)
   - Add your `google-services.json` file to the `app/` directory

4. **Build the Project**
   ```bash
   # Using Android Studio
   Build → Make Project (Ctrl+F9)

   # Or using command line
   ./gradlew build
   ```

5. **Run the Application**
   - Connect an Android device or start an emulator
   - Click the "Run" button (green play icon) in Android Studio
   - Or use: `Run → Run 'app'`

## 📋 Permissions Required

The app requires the following permissions for full functionality:

- **BODY_SENSORS**: Required for accelerometer, light, and proximity sensors
- **BODY_SENSORS_BACKGROUND**: For background sensor monitoring (Android 12+)
- **INTERNET**: For Firebase cloud synchronization
- **POST_NOTIFICATIONS**: For study session reminders

See [`SENSOR_PERMISSIONS_GUIDE.md`](SENSOR_PERMISSIONS_GUIDE.md) for detailed sensor permission information.

## 🏗️ Project Structure

```
app/src/main/java/com/divinemoses/mystudylife/
├── data/
│   ├── database/          # Room database entities and DAOs
│   ├── models/            # Data models (Class, Homework, Exam, etc.)
│   ├── repositories/      # Data access layer
│   └── services/          # Background services (CloudSyncService)
├── di/                    # Dependency injection modules (Hilt)
├── ui/
│   ├── activities/        # All app activities
│   ├── adapters/          # RecyclerView adapters
│   ├── fragments/         # UI fragments
│   └── viewmodels/        # ViewModels for MVVM architecture
├── utils/                 # Utility classes (Permissions, Sensors, etc.)
└── sensors/               # Sensor management classes
```

## 🛠️ Technologies Used

### Core Android
- **Language**: Kotlin
- **Architecture**: MVVM (Model-View-ViewModel)
- **UI**: Material Design 3, View Binding, Data Binding
- **Database**: Room Persistence Library
- **Dependency Injection**: Hilt (Dagger)

### Libraries & Frameworks
- **Networking**: Retrofit 2, OkHttp
- **Asynchronous**: Kotlin Coroutines, Flow
- **Charts**: MPAndroidChart v3.1.0
- **Background Tasks**: WorkManager
- **Firebase**: Firestore, Authentication
- **Permissions**: Accompanist Permissions

### Sensors & Hardware
- **Accelerometer**: Motion detection for focus tracking
- **Light Sensor**: Ambient light monitoring
- **Proximity Sensor**: Device usage detection

## 📊 App Architecture

The app follows Clean Architecture principles with MVVM:

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Activities    │    │   ViewModels    │    │  Repositories   │
│   Fragments     │◄──►│   LiveData      │◄──►│   Room DAOs     │
│   Adapters      │    │   StateFlow     │    │   Firebase      │
└─────────────────┘    └─────────────────┘    └─────────────────┘
         │                       │                       │
         ▼                       ▼                       ▼
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   UI Layer      │    │ Business Logic  │    │   Data Layer    │
│   (Material)    │    │   (Sensors)     │    │   (Local/Cloud) │
└─────────────────┘    └─────────────────┘    └─────────────────┘
```

## 🔧 Configuration

### Build Configuration
- **Compile SDK**: 34 (Android 14)
- **Target SDK**: 34 (Android 14)
- **Min SDK**: 24 (Android 7.0)
- **Kotlin Version**: 1.8.10

### Firebase Configuration
Required for cloud sync features. See [`FIREBASE_SETUP.md`](FIREBASE_SETUP.md) for complete setup instructions.

## 🧪 Testing

### Unit Tests
```bash
./gradlew test
```

### Instrumentation Tests
```bash
./gradlew connectedAndroidTest
```

## 📝 Usage Guide

### First Time Setup
1. **Grant Permissions**: Allow sensor permissions when prompted
2. **Configure Settings**: Adjust sensor sensitivity in Settings
3. **Add Classes**: Start by adding your class schedule
4. **Begin Studying**: Use the sensor dashboard to monitor study quality

### Key Features
- **Main Dashboard**: Overview of all your study activities
- **Add Activities**: Create new classes, homework, and exams
- **List Views**: Browse all your study items
- **Sensor Dashboard**: Real-time study quality monitoring
- **Analytics**: Historical performance and trend analysis
- **Settings**: Customize app behavior and preferences

## 🐛 Troubleshooting

### Common Issues

**App won't start or crashes**
- Ensure you have the latest Android Studio
- Check that all dependencies are downloaded
- Verify Firebase configuration if using cloud features

**Sensors not working**
- Check device sensor compatibility
- Grant BODY_SENSORS permission
- See [`SENSOR_PERMISSIONS_GUIDE.md`](SENSOR_PERMISSIONS_GUIDE.md)

**Firebase sync not working**
- Verify `google-services.json` is in the correct location
- Check internet connection
- Ensure Firebase project is properly configured

**Build errors**
- Clean and rebuild: `Build → Clean Project` then `Build → Rebuild Project`
- Invalidate caches: `File → Invalidate Caches / Restart`

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙋 Support

If you encounter any issues or have questions:
1. Check the troubleshooting section above
2. Review the documentation files in the project
3. Open an issue on the repository

## 📈 Future Enhancements

- [ ] Study streak tracking and gamification
- [ ] AI-powered study recommendations
- [ ] Integration with calendar apps
- [ ] Advanced analytics with machine learning
- [ ] Multi-device synchronization improvements
- [ ] Custom study timers and break reminders

---

**Happy Studying! 🎓**
