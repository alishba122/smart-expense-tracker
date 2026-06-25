# Smart Expense Tracker (Android Native App)

A premium, highly interactive, and production-ready local-first financial companion built using **Kotlin**, **Jetpack Compose**, and the **Material Design 3 (M3)** design system. 

Designed with an eye-safe, immersive **Glassmorphic Obsidian/Pastel UI**, this application empowers you to manage your personal finances with confidence, providing offline reliability, interactive custom visualizations, real-time threshold notifications, and rich report categorizations.

---

## 🌟 Major Highlights & Architecture

### 1. Technology Stack
*   **Language:** Kotlin (100% native, optimized for Android 14+).
*   **UI Framework:** Jetpack Compose (using the modern Declarative model).
*   **Design System:** Material Theme 3 (with custom dynamic dark & light systems).
*   **Data Persistence:** Room SQLite Database (using the KSP Kotlin Symbol Processor).
*   **Reactive Flow:** Kotlin StateFlow and Coroutines for state-driven updates.
*   **Architecture Pattern:** Clean MVVM (Model-View-ViewModel) paired with the Repository Pattern.

### 2. High-Fidelity Features
*   **Secure Standing Authentication:** Standalone local system with user table storage. Includes registration, secure password hashing comparison, forgot-password verification, and mock single-click Google Sign-In identity integration.
*   **Glassmorphic Aesthetic:** Immersive translucent surfaces with delicate light-reflecting borders, soft shadows, and deep multi-colored ambient radial gradients.
*   **Intelligent Cash Flow Hub:** View current total balance, dynamic color-coded in/out indicators, and recent financial actions at a single glance.
*   **Custom Financial Visualizer:** A custom `Canvas` drawing engine displaying responsive donut chart analyses of category allocations (Food, Shopping, Health, Transport, etc.) without relying on heavy third-party plotting frameworks.
*   **Category & Income Management:** Full additions, edits, or deletions of income/expense records with contextual fields and custom Material symbol indicators.
*   **Interactive Search & Highlighting:** Real-time query matching across notes, descriptions, categories, or specific financial amounts.
*   **Multi-Period Reports:** Instantly filter details by Daily, Weekly, Monthly, or Yearly ranges with smart spend ratio indicators.
*   **Smart Notification Hub:** Interactive in-app alerts trigger automatically when expenditures exceed 50%, 80%, or 100% of the user's custom monthly budget limit.

---

## 📁 Repository Directory Structure

```text
/app/src/main/java/com/example/
│
├── data/
│   ├── model/
│   │   ├── User.kt                 # Secure user details and budget parameters
│   │   └── Transaction.kt          # Income & expense records database structures
│   │
│   ├── database/
│   │   ├── AppDatabase.kt          # Room SQLite Database holder and builder
│   │   ├── UserDao.kt              # Room Data Access Object for user table
│   │   └── TransactionDao.kt       # Room Data Access Object for transaction logs
│   │
│   └── repository/
│       ├── UserRepository.kt       # Abstracts authentication operations
│       └── TransactionRepository.kt# Abstracts database ledger modifications
│
├── ui/
│   ├── components/
│   │   └── GlassmorphicCard.kt     # Translucent cards, inputs, and gradients
│   │
│   ├── viewmodel/
│   │   ├── AuthViewModel.kt        # Directs user registration and auth status
│   │   ├── TrackerViewModel.kt     # Manages ledger states, search and notifications
│   │   └── ViewModelFactory.kt     # Safe dependency injector for VM initialization
│   │
│   ├── theme/
│   │   ├── Color.kt                # Primary, secondary, and glassmorphic colors
│   │   ├── Type.kt                 # Google Fonts paired Material Typography
│   │   └── Theme.kt                # Combines colors and styles for dark/light themes
│   │
│   └── screens/
│       ├── LoginScreen.kt          # Login, Registration, and Password Reset
│       ├── DashboardScreen.kt      # Balance display and custom canvas donut chart
│       ├── TransactionScreen.kt    # Add & Edit records with contextual details
│       ├── ReportsScreen.kt        # Multi-period filters and spend ratio progress
│       └── SettingsScreen.kt       # Theme switches, profile edits, and budget sliders
│
└── MainActivity.kt                 # App setup, back handling, and bottom-tabs flow
```

---

## 🚀 Step-by-Step Installation & Setup

Follow these simple steps to run the "Smart Expense Tracker" application on your local workstation:

### 📋 Prerequisites
1.  **Android Studio** (Koala | 2024.1.1 or newer recommended).
2.  **JDK 17** or newer configured in system variables.
3.  An Android Emulator or physical Android device running **Android 7.0 (API 24) or newer**.

### 🛠️ Setting Up the Code
1.  **Clone / Download the Repository:** Extract the project ZIP to a local folder.
2.  **Open in Android Studio:**
    *   Launch Android Studio, select **File > Open**, and select the project's root folder.
    *   Allow Gradle to sync automatically. The project utilizes a central Modern Version Catalog (`gradle/libs.versions.toml`) to load compatible libraries.
3.  **Configure Local Variables:**
    *   The project is pre-configured with the **Secrets Gradle Plugin** to read variables from `.env` or `.env.example`. Enter any desired security configurations here.
4.  **Run the Application:**
    *   Connect your Android emulator or physical device.
    *   Click the **Run (Green Play Button)** in the toolbar or use the keyboard shortcut `Shift + F10` (`Control + R` on macOS).
5.  **Run local Tests:**
    *   Execute standard unit and Robolectric tests via Android Studio's terminal:
        ```bash
        gradle :app:testDebugUnitTest
        ```

---

## 🎨 Creative Design & Aesthetics

The design of **Smart Expense Tracker** avoids generic layout defaults to provide an immersive luxury fintech experience:
*   **The Ambient Canvas:** A radial gradient blending dark slate, royal indigo, and pure black obsidian background spheres which moves subtly beneath layers of content.
*   **Layered Surfaces:** Custom Material 3 cards configured with thin translucent white borders (`Color.White.copy(0.15f)`) and light shadows to replicate premium sandblasted glass.
*   **High-Contrast Color Pairs:** Vibrant visual indicators for expenditures (Soft Pink/Red) versus savings (Soft Mint/Teal) ensuring immediate scannability.
