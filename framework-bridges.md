# MyORI SmartSecure NFC SDK - Framework Bridges

This document provides an overview of the framework bridges created for the MyORI SmartSecure NFC SDK, allowing integration with various cross-platform frameworks. The SDK is now organized into separate submodules for each framework integration.

## Available Bridges

### 1. Ionic/Capacitor Plugin

Submodule: `ssconsumer-sdk-ionic`

The Capacitor plugin allows integration with Ionic applications using Capacitor.

**Key Features:**
- TypeScript interface for Capacitor applications
- Native implementation for Android and iOS
- Event-based architecture for tag reading and error handling
- TypeScript definitions for improved developer experience

**Usage:**
```bash
npm install @myori/capacitor-nfc
npx cap sync
```

See the [Ionic Plugin README](/ssconsumer-sdk-ionic/README.md) for detailed documentation.

### 2. React Native Plugin

Submodule: `ssconsumer-sdk-react-native`

The React Native plugin allows integration with React Native applications.

**Key Features:**
- JavaScript/TypeScript interface for React Native applications
- Native implementation for Android and iOS
- Promise-based API for tag reading and error handling

**Usage:**
Refer to the [React Native Plugin README](/ssconsumer-sdk-react-native/README.md) for installation and usage instructions.

### 3. Flutter Plugin

Submodule: `ssconsumer-sdk-flutter`

The Flutter plugin allows integration with Flutter applications.

**Key Features:**
- Dart interface for Flutter applications
- Native implementation for Android and iOS
- Async/await support for tag reading operations

**Usage:**
Refer to the [Flutter Plugin README](/ssconsumer-sdk-flutter/README.md) for installation and usage instructions.

## Common Features

All framework bridges provide the following common functionality:

1. **NFC Tag Reading**: Read MyORI SmartSecure NFC tags
2. **NDEF Data Validation**: Ensure NDEF data is exactly 52 characters
3. **API Communication**: Send tag data to MyORI SmartSecure API
4. **Configuration**: Set API endpoint and key
5. **Error Handling**: Comprehensive error reporting

## API Data Format

When an NFC tag is read, all bridges send the following JSON data to the API:

```json
{
  "tag": "tag_id_value",
  "lbl": "first_28_characters_of_ndef_data",
  "enc": "remaining_characters_of_ndef_data",
  "device": "device_info"
}
```

## Platform Requirements

### Android
- Android 4.4 (API 19) or higher
- NFC-enabled device

### iOS
- iOS 13.0 or higher
- iPhone 7 or newer with NFC capabilities

## License

MIT