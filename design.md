# LA Rail Proximity App - Design Document

## Overview

A React Native mobile app for Los Angeles rail transit that displays all LA Metro rail lines and stops on an interactive map powered by OpenStreetMap. Users can set custom pins, receive proximity notifications when approaching locations, maintain favorite locations, and view their location history.

## Screen List

1. **Map Screen** (Home)
   - Interactive OSM map with LA Metro rail lines and stops overlay
   - Current user location indicator
   - Tap to place pins on the map
   - Search bar to find locations
   - Floating action buttons for favorites, history, and settings

2. **Pin Detail Sheet**
   - Shows pin information (coordinates, address if available)
   - Set proximity notification distance (in miles/km)
   - Save as favorite option
   - Delete pin button
   - View on map button

3. **Favorites Screen**
   - List of all saved favorite locations
   - Each favorite shows: name, coordinates, notification distance
   - Tap to view on map
   - Swipe to delete
   - Edit favorite name and notification distance

4. **Location History Screen**
   - Chronological list of recently visited locations
   - Each entry shows: location, timestamp, distance from nearest rail stop
   - Tap to view on map
   - Clear history option

5. **Settings Screen**
   - Toggle notifications on/off
   - Notification sound selection
   - Distance unit preference (miles/km)
   - About and app info

## Primary Content and Functionality

### Map Screen (Primary Interface)
- **Rail Lines Overlay**: All LA Metro rail lines (A, B, C, D, E, K, L lines) rendered as colored polylines
- **Rail Stops Overlay**: All rail stops displayed as markers with line-specific colors
- **User Location**: Blue dot showing current GPS position (updates in real-time)
- **User Pins**: Custom pins placed by user (different color from rail stops)
- **Search Bar**: Search for addresses or locations via OSM geocoding
- **Floating Buttons**:
  - Favorites (star icon) → Opens favorites list
  - History (clock icon) → Opens location history
  - Settings (gear icon) → Opens settings

### Proximity Notifications
- When user approaches a pin within the set distance, a notification is triggered
- Background location tracking (using expo-location with background tasks)
- Notification includes: pin name, current distance, time triggered
- User can snooze or dismiss notifications

### Data Persistence
- Favorites stored in AsyncStorage (local device storage)
- Location history stored in AsyncStorage
- User preferences (units, notification settings) stored in AsyncStorage

## Key User Flows

### Flow 1: Set a Favorite Location with Notification
1. User opens app → Map Screen loads with current location
2. User taps on map to place a pin
3. Pin Detail Sheet opens
4. User enters a name for the pin
5. User sets notification distance (e.g., 0.5 miles)
6. User taps "Save as Favorite"
7. Pin is saved and appears on map

### Flow 2: Get Proximity Notification
1. User has set a favorite location with notification distance
2. User travels toward that location
3. When user enters the notification radius, a notification is sent
4. User can tap notification to view the location on map
5. Notification is logged in location history

### Flow 3: Search for a Location
1. User taps search bar on Map Screen
2. User types address or location name
3. Search results appear (from OSM geocoding)
4. User taps a result
5. Map centers on that location
6. User can place a pin there

### Flow 4: View Favorites
1. User taps Favorites button (star icon)
2. Favorites Screen opens showing all saved locations
3. User taps a favorite
4. Map centers on that location
5. User can edit or delete the favorite

### Flow 5: View Location History
1. User taps History button (clock icon)
2. Location History Screen opens
3. User sees list of recent locations visited
4. User taps a history entry
5. Map centers on that location

## Color Choices

### Brand Colors
- **Primary**: #0A7EA4 (LA Metro Blue) - Used for primary buttons, user location indicator
- **Rail Line Colors** (from LA Metro official colors):
  - **A Line (Blue)**: #0066CC
  - **B Line (Red)**: #E31C23
  - **C Line (Green)**: #339933
  - **D Line (Purple)**: #9933CC
  - **E Line (Gold)**: #FFCC00 (with black text for contrast)
  - **K Line (Silver)**: #CCCCCC
  - **L Line (Orange)**: #FF6600

### UI Colors
- **Background**: #FFFFFF (light mode) / #151718 (dark mode)
- **Surface**: #F5F5F5 (light mode) / #1E2022 (dark mode)
- **Text**: #11181C (light mode) / #ECEDEE (dark mode)
- **Muted Text**: #687076 (light mode) / #9BA1A6 (dark mode)
- **Border**: #E5E7EB (light mode) / #334155 (dark mode)
- **Success**: #22C55E (notification confirmed)
- **Error**: #EF4444 (error states)

### Map Markers
- **Rail Stops**: Line-specific color (from above)
- **User Location**: #0A7EA4 (blue dot with white outline)
- **User Pins**: #FF6B6B (coral red)
- **Favorite Pins**: #FFD700 (gold star)

## Layout Principles

- **Portrait Orientation**: All screens designed for portrait (9:16) with one-handed usage in mind
- **Safe Area Handling**: All content respects notch and home indicator areas
- **Tab Bar**: Bottom tab navigation for quick access to Map, Favorites, History, Settings
- **Floating Buttons**: Positioned in top-right corner for easy thumb reach
- **Bottom Sheets**: Used for pin details and search results (slide up from bottom)
- **Map Gestures**: Pinch to zoom, two-finger drag to rotate, tap to place pins

## Technical Implementation Notes

- **Map Library**: react-native-maps with OpenStreetMap tiles (UrlTile)
- **Location**: expo-location for GPS tracking and geofencing
- **Notifications**: expo-notifications for local notifications
- **Background Tasks**: expo-task-manager for background location updates
- **Data Storage**: AsyncStorage for local persistence
- **Geocoding**: OSM Nominatim API for address search
