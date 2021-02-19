# Software Component Usage
This is a review of the [package.json](https://github.com/Path-Check/gaen-mobile/blob/develop/package.json) on the GAEN Mobile Github as of Feb 4, 2021.

```json
"dependencies": {
    "@bugsnag/react-native": "^7.3.4",
    "@react-native-community/async-storage": "^1.12.1",
    "@react-native-community/datetimepicker": "^3.0.8",
    "@react-native-community/masked-view": "^0.1.10",
    "@react-native-community/netinfo": "^5.9.4",
    "@react-native-community/push-notification-ios": "^1.4.0",
    "@react-native-community/segmented-control": "^2.1.2",
    "@react-navigation/bottom-tabs": "^5.5.2",
    "@react-navigation/native": "^5.7.3",
    "@react-navigation/stack": "5.1.1",
    "array-flat-polyfill": "^1.0.1",
    "dayjs": "^1.8.24",
    "i18next": "^19.3.3",
    "node-fetch": "^2.6.1",
    "prop-types": "^15.7.2",
    "react": "16.13.1",
    "react-i18next": "^11.4.0",
    "react-native": "0.63.4",
    "react-native-config": "^1.2.1",
    "react-native-flash-message": "^0.1.16",
    "react-native-gesture-handler": "^1.9.0",
    "react-native-keyboard-aware-scroll-view": "^0.9.3",
    "react-native-matomo-sdk": "^0.4.0",
    "react-native-permissions": "^2.2.2",
    "react-native-safe-area-context": "^3.1.9",
    "react-native-screens": "^2.16.1",
    "react-native-simple-crypto": "^0.2.15",
    "react-native-splash-screen": "^3.2.0",
    "react-native-static-safe-area-insets": "^2.1.1",
    "react-native-svg": "^12.0.3",
    "react-native-webview": "^11.2.0",
    "reanimated-bottom-sheet": "^1.0.0-alpha.19",
    "regression": "^2.0.1",
    "ts.data.json": "^1.5.0"
  }
  ```
  ## Dependency Justifications
  * BugSnag - used for bug and error tracking within the GAEN mobile code and catching crashes and other hidden issues breaking the app
  * React Native Community:

     

    * DateTimePicker - for selecting various dates in the application

    

    * NetInfo - Used for managing components/code for when certain network events fire.

    * PushNotificationiOS - used for sending native push notifications to iOS devices from the app

    * Segmented Control - Possible we aren’t using
  * React Navigation
    * Bottom Tabs - Used for basic navigation between screens in the app.

    * Native - Used for leveraging OS level  navigation between screens in the app.

    * Stack - Managing multiple activities going on within the app
  * Array Flat Polyfill - Brought in to add “array flattening” functionality for Javascript

* DayJS - Parsing and date manipulation

* i18Next - Used for Translations



* PropTypes - Core functionality for checking types of property variables

* React i18Next - Used for translations

* React Native - Core functionality for the entire app framework

* React Native Config - Core functionality for the entire app framework

* React Native Flash Message - Functionality for toasts and other “in app” popup messaging

 

* React Native Keyboard Aware Scroll - Used for auto scrolling input screens when the current input leaves the view

* Matomo SDK - Used for Analytics

* Permissions - Provides access to the OS permissions (enabling EN, Notifications, etc.)

* Safe Area Context - Used for keeping the UI within the correct areas of a device

* Screens - Core functionality for allowing multiple screens

* Simple Crypto - Used for hashing to package the keys before sending up to the server

* Splash Screen - Used for a UI element on initial app load splash screen

* Static Safe Area Insets - Companion package to Safe Area Context

* SVG - Used for displaying and manipulating SVGs used on the mobile app UIs

* Webview - Currently being used for Tableau analytics on some GAEN apps



* TS Data JSON - Used for deserializing JSON responses

### Packages Under Review
* Async Storage - Key/Value storage system for React Native. Being used for app specific data. Stores data right in app “local storage”.  ⚠️ This package is deprecated - planning replacement with another localstorage library.
* MaskedView - ⚠️ Shows an opaque view that is hidden from the user but still rendered. 
* NodeFetch - ⚠️ Core functionality for retrieving data. Reviewing requirement.
* React Native Gesture Handling - ⚠️ Only used in a jest config. Currently Reviewing.
* Reanimated Bottom Sheet - ⚠️ Currently Under Review
* Regression - ⚠️ Currently Under Review
