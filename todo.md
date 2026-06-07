# LA Rail Proximity App - TODO

## Phase 1: Core Map and Rail Data Integration
- [x] Integrate react-native-maps with OpenStreetMap tiles
- [x] Load and parse LA Metro GTFS GeoJSON data (metro_lines.json, metro_stops.json)
- [x] Render all rail lines as colored polylines on map
- [x] Render all rail stops as markers with line-specific colors
- [x] Implement map gestures (pinch zoom, pan, tap to place pins)
- [x] Display current user location with blue dot indicator
- [x] Center map on user location on app launch

## Phase 2: Pin Management and Search
- [x] Implement tap-to-place-pin functionality
- [x] Create Pin Detail Sheet component
- [x] Allow users to name and save pins
- [ ] Implement OSM Nominatim geocoding for location search
- [ ] Create search bar UI on map screen
- [ ] Display search results and allow selection
- [x] Persist pins to AsyncStorage

## Phase 3: Proximity Notifications
- [ ] Set up expo-location for background geolocation tracking
- [ ] Implement geofencing logic (distance calculation)
- [ ] Configure expo-notifications for local notifications
- [ ] Trigger notifications when user enters pin radius
- [ ] Allow users to set custom notification distances
- [ ] Implement notification dismissal and snooze

## Phase 4: Favorites Management
- [x] Create Favorites Screen UI
- [x] Display all saved favorite locations
- [ ] Allow editing favorite names and notification distances
- [ ] Allow deleting favorites (swipe gesture)
- [ ] Tap favorite to center map on location
- [x] Persist favorites to AsyncStorage
- [x] Add favorite star icon to tab bar

## Phase 5: Location History
- [ ] Track user location updates periodically
- [ ] Store location history entries with timestamps
- [x] Create Location History Screen UI
- [x] Display history entries in chronological order
- [ ] Calculate distance from each history entry to nearest rail stop
- [ ] Tap history entry to view on map
- [x] Clear history button
- [x] Add history clock icon to tab bar

## Phase 6: Settings and Preferences
- [x] Create Settings Screen UI
- [x] Toggle notifications on/off
- [x] Distance unit preference (miles/km)
- [x] Notification sound selection
- [x] About and app info section
- [x] Persist settings to AsyncStorage
- [x] Add settings gear icon to tab bar

## Phase 7: UI/UX Polish and Testing
- [ ] Create custom app logo and branding
- [ ] Update app.config.ts with app name and branding
- [ ] Implement dark mode support
- [ ] Test all user flows end-to-end
- [ ] Test on physical Android device via Expo Go
- [ ] Optimize map performance with large GeoJSON datasets
- [ ] Handle edge cases (no GPS signal, offline mode)

## Phase 8: Build and Delivery
- [ ] Generate APK build
- [ ] Test APK on Android device
- [ ] Create checkpoint before publishing
- [ ] Deliver to user with instructions
