# LA Rail Proximity

LA Rail Proximity is a simpl;e, lightweight, native Android "destination alarm" built specifically for the Los Angeles rail system. Whether you’re taking a nap on the A Line, zoning out to music on the Expo Line, or deep in a book on the D Line, this app ensures you wake up and get off at the right stop every time.
Key Features:
•
LA Metro Optimized: A color-coded, interactive map featuring all current lines (A, B, C, D, E, and K), including the new Regional Connector stations.
•
Custom Proximity Alerts: Set your own alarm radius—from 100 meters to 5 kilometers—and receive a high-priority notification as you approach your target.
•
Works in Your Pocket: Optimized for background location tracking, the app continues to monitor your trip even when your screen is off or you’re using other apps.
•
Search Anything: Need to go beyond the rails? Search for any street address or landmark to set a custom proximity alarm anywhere in the city.
•
Quick Access: Save your most frequent commutes to your Favorites and see your full recent search history at a glance.
Relax and enjoy the ride. We’ll let you know when you’re there.

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
1. Download the apk file
2. run
3. open the app
4. search your location
5. Select the distance from your location
6. you'll get a notification when you're close!

## Assets
- Transit data (`metro_lines.json`, `metro_stops.json`) is located in `android/app/src/main/assets/`.
- Raw images are backed up in `android/app/src/main/assets/images/`.
