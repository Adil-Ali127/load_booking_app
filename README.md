# Loader Rickshaw — Flutter App

Flutter implementation of the Loader Rickshaw Figma design (navy `#1B2534` +
amber `#E29B3E` theme), covering the Shipper, Driver, and Admin flows.

## Getting started

```bash
flutter pub get
flutter run
```

The app opens on `/splash`, then flows: Login → OTP → Role Selection →
Shipper Home / Driver Home, and onward into each role's screens.

## Structure

```
lib/
  main.dart                 # MaterialApp + named routes
  theme/app_theme.dart      # Colors + ThemeData (navy/amber palette)
  widgets/common_widgets.dart  # AppCard, IconCircle, StatusPill, BigButton,
                                # AppInputField, AppBottomNav, AppTopBar,
                                # LoadCard, StatusTracker
  screens/
    splash_screen.dart
    login_screen.dart
    otp_screen.dart
    role_selection_screen.dart
    home_shipper_screen.dart
    post_load_screen.dart
    home_driver_screen.dart
    load_details_screen.dart
    active_booking_screen.dart
    chat_screen.dart
    rating_screen.dart
    profile_screen.dart
    wallet_screen.dart
    kyc_upload_screen.dart
    admin_dashboard_screen.dart   # desktop/web layout
```

## Notes

- All screens use mock/static data — no backend is wired up yet. Each
  `BigButton` / nav tap already navigates to the next screen in the flow so
  you can click through the whole prototype.
- Icons are simple emoji glyphs inside `IconCircle`, matching the Figma
  design — swap these for a real icon set (e.g. an SVG/icon package) when
  moving past the prototype stage.
- `AdminDashboardScreen` is a wide/desktop layout (sidebar + stat cards +
  table). Run it directly for the admin team with:
  ```bash
  flutter run -d chrome --dart-define=start_route=/admin-dashboard
  ```
  or temporarily change `initialRoute` in `main.dart` to `/admin-dashboard`.
  In a real project this would likely ship as its own Flutter Web build.
- This code has not been run through `flutter analyze` / `flutter run` in
  this environment (no Flutter SDK available here) — please run
  `flutter pub get` and `flutter analyze` locally after downloading to catch
  any small issues before building.
# load_booking_app
