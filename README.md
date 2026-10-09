# 🍽️ MyRecipeApp

An Android app that lets users browse meal categories from [TheMealDB](https://www.themealdb.com/) public API, built with **Jetpack Compose** and **MVVM** architecture.

## 📱 Features
- Fetches meal categories from a REST API and displays them in a responsive 2-column grid
- Loads category images asynchronously with caching
- Handles loading, error, and success states cleanly through a single UI state object
- Material 3 theming with edge-to-edge display

## 🛠️ Tech Stack
| Area | Technology |
|---|---|
| Language | Kotlin |
| UI | Jetpack Compose, Material 3, `LazyVerticalGrid` |
| Architecture | MVVM (`ViewModel` + Compose state) |
| Async | Kotlin Coroutines (`viewModelScope`) |
| Networking | Retrofit, Gson converter |
| Image loading | Coil |
| Min SDK | 24 (Android 7.0) |

## 🏗️ Architecture
```
MainActivity
 └── RecipeScreen (Compose UI)
      └── MainViewModel  ──►  ApiService (Retrofit)  ──►  TheMealDB API
           └── RecipeState (loading / list / error)
```
The `ViewModel` exposes a single immutable `RecipeState`, and the UI reacts to it, showing a progress indicator while loading, an error message on failure, or the category grid on success.

## 🚀 Getting Started
1. Clone the repository
   ```bash
   git clone https://github.com/DilshanNish97/MyRecipeApp.git
   ```
2. Open it in Android Studio
3. Run it on an emulator or device (API 24+)

No API key is needed, since TheMealDB's free endpoint is used.

## 🔮 Planned Improvements
- Recipe detail screen with navigation
- Repository layer and dependency injection with Hilt
- Offline caching with Room
- Unit tests for the ViewModel
