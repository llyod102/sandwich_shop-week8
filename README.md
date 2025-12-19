# Sandwich Shop App

A Flutter mobile application for ordering customizable sandwiches with cart management, checkout, order history, and user profile features.

## Features

### 🥪 Order Screen
- Select from multiple sandwich types (Veggie Delight, Chicken Teriyaki, Italian B.M.T., etc.)
- Choose sandwich size (6-inch or Footlong)
- Adjust quantity (up to 5 sandwiches)
- Real-time price calculation
- Add items to cart with instant cart summary updates

### 🛒 Cart Management
- View all items in cart with individual prices
- Modify quantities with +/- buttons
- Remove individual items with delete button
- Automatic price recalculation
- Empty cart message when no items present
- User feedback via snackbars for all cart actions

### 💳 Checkout Flow
- Order summary with itemized list
- Total price display
- Simulated payment processing (2 seconds)
- Automatic order saving to history
- Cart clearing after successful checkout

### 📦 Order History
- View all past orders with order IDs
- Order date/time stamps
- Item count and total price for each order
- Persistent storage using SQLite
- Empty state message when no orders exist

### 👤 Profile Screen
- Save user name and preferred location
- Welcome message displayed on order screen
- Persistent profile data using SharedPreferences

### ⚙️ Settings
- Adjustable font size (12px - 32px)
- Live preview of font changes
- Global font size applied across all screens
- Persistent font size preference

## Technical Stack

- **Framework**: Flutter 3.35.7
- **State Management**: Provider
- **Database**: SQLite (sqflite)
- **Local Storage**: SharedPreferences
- **Testing**: Integration tests with flutter_test

## Project Structure

```
lib/
├── main.dart                      # App entry point
├── models/
│   ├── cart.dart                  # Cart state management
│   ├── sandwich.dart              # Sandwich data model
│   └── saved_order.dart           # Order history model
├── repositories/
│   └── pricing_repository.dart   # Price calculation logic
├── services/
│   └── database_service.dart     # SQLite database operations
├── views/
│   ├── app_styles.dart           # Global styling and font size
│   ├── cart_screen.dart          # Cart management UI
│   ├── checkout_screen.dart      # Checkout flow
│   ├── order_history_screen.dart # Order history display
│   ├── order_screen.dart         # Main ordering interface
│   ├── profile_screen.dart       # User profile
│   └── settings_screen.dart      # App settings
└── widgets/
    └── common_widgets.dart       # Reusable UI components

integration_test/
└── app_test.dart                 # End-to-end integration tests
```

## Building

### Android Release Build
```bash
flutter build apk --release
```
Output: `build/app/outputs/flutter-apk/app-release.apk` (81.4MB)

### iOS Release Build
```bash
flutter build ios --release
```

### Web Build
```bash
flutter build web --release
```

## Running Tests

### Integration Tests
```bash
flutter test integration_test/app_test.dart
```

The integration test suite covers:
- Adding sandwiches to cart
- Changing sandwich types
- Modifying quantities
- Complete checkout flow
- Profile management
- Cart modifications (add, remove, update)
- Order history verification
- Settings adjustments
- Size switching (6-inch/footlong)

## Requirements

- Flutter SDK 3.0+
- Dart 2.17+
- Android SDK (for Android builds)
- Xcode (for iOS builds)

## Getting Started

1. Install Flutter dependencies:
```bash
flutter pub get
```

2. Run the app:
```bash
flutter run
```

3. Run tests:
```bash
flutter test
```

## App Flow

1. **Order Screen** (Home) - Select and customize sandwiches
2. **Cart Screen** - Review and modify cart contents
3. **Checkout Screen** - Complete purchase with simulated payment
4. **Order History** - View past orders
5. **Profile Screen** - Update user information
6. **Settings Screen** - Adjust app preferences

## Database Schema

### Orders Table
- `id` (INTEGER PRIMARY KEY)
- `orderId` (TEXT) - Unique order identifier
- `timestamp` (TEXT) - Order date/time
- `totalPrice` (REAL) - Order total
- `itemCount` (INTEGER) - Number of items

## Notes

- Kotlin version 1.8.22 (upgrade to 2.1.0+ recommended)
- Material Icons tree-shaking enabled (99.8% size reduction)
- Release APK size: 81.4MB

## License

This project is a Flutter demonstration application for educational purposes.
