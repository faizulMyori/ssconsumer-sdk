# MyORI SmartSecure NFC SDK

This SDK provides NFC functionality for Android and iOS applications to interact with MyORI SmartSecure NFC tags. When an NFC tag is tapped, the SDK will process the data and send it to the MyORI API.

## Features

- Easy integration with Android and iOS applications
- Handles NFC tag reading and data extraction
- Secure communication with MyORI SmartSecure API
- Callback mechanisms for successful/failed NFC operations
- Comprehensive error handling
- Validation of NDEF data format

## Framework Bridges

This repository now includes bridges for integrating the MyORI SmartSecure NFC SDK with various cross-platform frameworks:

- [Ionic/Capacitor Plugin](/ionic) - For Ionic applications using Capacitor

See the [Framework Bridges](/framework-bridges.md) document for a detailed overview of all available bridges.

## Project Structure

```
ssconsumer-sdk/
├── android/                 # Android SDK files
│   ├── src/                 # Source code
│   ├── example/             # Example Android application
│   └── build.gradle         # Android build configuration
├── ios/                     # iOS SDK files
│   ├── Sources/             # Source code
│   ├── Example/             # Example iOS application
│   └── Package.swift        # Swift Package Manager configuration
├── ionic/                   # Ionic/Capacitor plugin
│   └── capacitor/           # Capacitor plugin implementation
└── docs/                    # Documentation
    ├── android-integration.md  # Android integration guide
    └── ios-integration.md      # iOS integration guide
```

## Getting Started

Please refer to the platform-specific integration guides in the `docs` directory for detailed instructions on how to integrate the SDK into your native application.

For cross-platform frameworks, choose the appropriate framework bridge for your application:

### Ionic/Capacitor

```bash
npm install @myori/capacitor-nfc
npx cap sync
```

See the [Ionic Plugin README](/ionic/README.md) for detailed documentation.

## NDEF Data Format Requirements

When working with NFC tags, the SDK requires that the NDEF data must be exactly 52 characters in length. If the data is more or less than 52 characters, the API request will fail with an error message.

The SDK will automatically split the NDEF data into two parts for the API request:
- `lbl`: The first 28 characters of the NDEF data
- `enc`: The remaining characters (after the first 28) of the NDEF data

This format is required by the MyORI SmartSecure API.

## License

This SDK is proprietary and confidential. Unauthorized copying, transferring or reproduction of the contents of this repository, via any medium is strictly prohibited.

## Support

For any questions or support requests, please contact [support@myorismartssecure.com](mailto:support@myorismartssecure.com).