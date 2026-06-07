# LA Rail Proximity

A pure native Android application built with **Kotlin** and **Jetpack Compose**.

## Project Overview
This project provides real-time alerts and proximity information for the Los Angeles transit system.

## Tech Stack
- **Language:** Kotlin
- **UI Framework:** Jetpack Compose
- **Architecture:** MVVM (recommended)
- **Minimum SDK:** 24
- **Target SDK:** 34

## Project Structure
- `android/app/src/main/java/com/app/larailproximityapp/`: Main Kotlin source code.
- `android/app/src/main/java/com/app/larailproximityapp/ui/theme/`: Jetpack Compose theme definitions.
- `android/app/src/main/assets/`: Raw data files (e.g., transit JSON).
- `android/app/src/main/res/`: Android resources (drawables, mipmaps, strings).

## Getting Started
1. Open the `android/` directory in Android Studio.
2. Sync Project with Gradle Files.
3. Run the `app` module on an emulator or physical device.

## Assets
- Transit data (`metro_lines.json`, `metro_stops.json`) is located in `android/app/src/main/assets/`.
- Raw images are backed up in `android/app/src/main/assets/images/`.
