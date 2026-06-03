# Ledger - Flutter Finance App
**Creator@KhaingNyeinThant**

Web (HTML/JS/CSS) မှ Flutter သို့ ပြောင်းထားသော Personal Finance App ။

---

## Features
- 💼 ဝင်ငွေ / ထွက်ငွေ / လွှဲငွေ မှတ်တမ်းသွင်းနိုင်
- 🏦 အကောင့်များ စီမံခန့်ခွဲနိုင် (Cash, PayApp, Card, Custom)
- 📋 အကြွေး / ငွေချေး tracking
- 📊 Bar chart နှင့် Trend chart (ဂရပ်)
- 📥📤 JSON Backup / Restore
- 🌓 Dark / Light Theme
- 👁️ Balance hide/show
- 🛠️ Category စီမံနိုင်
- 🇲🇲 Burmese UI

---

## Setup Instructions

### 1. Flutter SDK Install
```bash
# Flutter SDK download: https://flutter.dev/docs/get-started/install
flutter --version   # 3.x.x လိုအပ်
```

### 2. Fonts ထည့်ရန်
`assets/fonts/` folder ထဲတွင် Noto Sans Myanmar font ထည့်ပါ:
- [Download Noto Sans Myanmar](https://fonts.google.com/noto/specimen/Noto+Sans+Myanmar)
- `NotoSansMyanmar-Regular.ttf`
- `NotoSansMyanmar-Bold.ttf`

```bash
mkdir -p assets/fonts
# font files ကို assets/fonts/ ထဲသို့ ထည့်ပါ
```

### 3. Dependencies Install
```bash
cd ledger_flutter
flutter pub get
```

### 4. Run
```bash
# Android device/emulator
flutter run

# Release APK build
flutter build apk --release
# Output: build/app/outputs/flutter-apk/app-release.apk

# Release AAB (Play Store)
flutter build appbundle --release
```

---

## Project Structure
```
lib/
├── main.dart                    # Entry point + MainShell + Bottom Nav
├── models/
│   └── models.dart              # Account, Transaction, CategoryItem, AppSettings
├── providers/
│   └── app_provider.dart        # State management (ChangeNotifier)
├── screens/
│   ├── home_screen.dart         # ပင်မစာမျက်နှာ
│   ├── accounts_screen.dart     # အကောင့်စီမံ
│   ├── debt_screen.dart         # အကြွေးစာမျက်နှာ
│   ├── charts_screen.dart       # ဂရပ်
│   ├── add_transaction_screen.dart  # မှတ်တမ်းသွင်း/ပြင်
│   └── settings_sheet.dart      # Settings + Category Manager
├── widgets/
│   ├── tx_list_widget.dart      # Transaction list (reusable)
│   └── tx_detail_sheet.dart     # Transaction detail bottom sheet
└── utils/
    ├── app_theme.dart           # Theme + Colors
    ├── database_helper.dart     # SQLite (sqflite)
    └── formatters.dart          # Number + Date formatting
```

---

## Dependencies (pubspec.yaml)
| Package | ရည်ရွယ်ချက် |
|---------|------------|
| `sqflite` | Local database (IndexedDB အစား) |
| `shared_preferences` | Settings သိမ်း |
| `intl` | Number formatting |
| `fl_chart` | Bar charts |
| `share_plus` | Backup file share |
| `file_picker` | JSON import |
| `path_provider` | File paths |
| `google_fonts` | (Optional) |
| `provider` | State management |

---

## Notes
- Data သည် device ပေါ်တွင် SQLite မှာ သိမ်းဆည်းသည်
- Backup `.json` format သည် original web app နှင့် compatible
- Android min SDK 21+ လိုအပ်
