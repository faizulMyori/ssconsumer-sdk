# MyORI SmartSecure NFC SDK - Framework Bridges

This document provides an overview of the framework bridges created for the MyORI SmartSecure NFC SDK, allowing integration with various cross-platform frameworks.

## Available Bridges

### 1. Ionic/Capacitor Plugin

Location: `/ionic/capacitor`

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

See the [Ionic Plugin README](/ionic/README.md) for detailed documentation.

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