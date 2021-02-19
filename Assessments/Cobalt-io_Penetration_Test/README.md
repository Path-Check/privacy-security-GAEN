## Assessment Summary
A gray box penetration test of the PathCheck - GAEN-Mobile App mobile application was conducted in order to assess its risk posture and identify security issues that could negatively affect PathCheck's data, systems, or reputation. The scope of the assessment covered PathCheck gaen-mobile External iOS Beta version 1378 and PathCheck gaen-mobile Google Alpha Closed 1.0.3. The pentest was conducted by 2 pentester(s) between Sep 29, 2020 and Oct 13, 2020.

This penetration test was a manual assessment of the security of the application’s functionality, business logic, and vulnerabilities such as those catalogued in the OWASP Top 10. The assessment also included a review of security controls and requirements listed in the OWASP Mobile Application Security Verification Standard (MASVS). The pentesters leveraged tools to facilitate their work; however, the majority of the assessment involves manual analysis.

**Overall, the pentesters found that the application exhibits a good security posture during the assessment. The application is well built, with many security best practices in place. No major issues were discovered during the test because of this.** 

## Scope
Coverage

This penetration test was a manual assessment of the security of the app’s functionality, business logic, and vulnerabilities such as those cataloged in the OWASP Top 10. The assessment also included a review of security controls and requirements listed in the OWASP Mobile Application Security Verification Standard (MASVS). The researchers conduct manual analysis assisted by tools.

The mobile application did not authenticate users beyond the device where it was installed and did not send any personally identifiable information (PII) to the server. Therefore, testing related to security controls across roles and permissions did not apply. However, testing related to data security and privacy has been performed, including testing that data is stored securely on the device as well as handled security over the network.

The following is a brief summary of the main tests performed on the mobile application:

* Checks of native components and the source code
* Exported interface tests for Android applications
* Reverse engineering of the mobile application
* OWASP Mobile Top 10 testing

While the server was out of scope for testing, the following is a brief summary of the review performed on the API to make sure that user data was secure over the network:

* Authenticated endpoint testing for missing access control issues
* Input validation tests

Below is the summary of methodologies used to assess security at mentioned endpoints:
Inventory of API endpoints:

We inventoried the calls made by the app during all user activities. We then proceeded to analyze requests and responses to observe the underlying technology and any possible vulnerabilities. We observed that no PII is being sent to the server.
Manual and automated fuzzing of API endpoints:

We proceeded to reverse engineer the endpoints and perform modified calls using manual and automated methods. We attempted the following:

* Parameter manipulation (adding / modifying parameters to perform new functions, horizontal privilege escalation, etc.)
* Code injection (SQL injection attempts, Template injection, Cross Site Scripting attacks, etc.).
* Conducted testing of data storage for sensitive information disclosure.
* Tested the apps to ensure cryptographic best practices were adhered to.
* Performed analysis of local authentication mechanisms used by the applications.
* Tested network communication security controls such as certificate pinning, the use of TLS for application to API communication, and the security provider that is present on the mobile device. (this was deemed out of scope)
* Conducted an analysis of the different platform’s (iOS and Android) interaction with the application. These tests focused on the use of intents, IPC, broadcast receivers, services, URL schemes, file transfer mechanisms, etc.
* Worked to identify code quality and build setting deficiencies such as application signing, debug options, symbols that weren’t properly stripped, verbose logging, exception handling, and any issues stemming from the use of native libraries.
* Noted the effectiveness of code obfuscation techniques used to limit analysis efforts, and anti-reverse engineering mechanisms such as jailbreak or root detection.

Test Cases that successfully thwarted exploitation

During testing many positive controls were observed the be in place within the application. A brief overview of these includes:

* The JWT token used for verification was secured against common attacks like algorithm manipulation and brute force. The token signature was properly validated.
* The application does not store any sensitive data locally or send sensitive data to the server.
* The verification code is not reusable.
* The application does not expose any sensitive information in logs

Target description

* PathCheck gaen-mobile External iOS Beta version 1378 tested on non-jailbroken iOS 14.0.1, iPhone 11 Pro
* PathCheck gaen-mobile Google Alpha Closed 1.0.3 tested on Android v 10 Pixel 2

## Cobalt.io Testing Coverage

### Data Storage and Privacy

* Testing Whether Sensitive Data Is Sent To Third Parties
    > :heavy_check_mark:  No sensitive data is shared with third parties unless it is a necessary part of the architecture.
* Testing For Sensitive Data in Logs
    > :heavy_check_mark: No sensitive data is written to application logs.
* Testing for Sensitive Data Disclosure Through the User Interface
    > :heavy_check_mark: No sensitive data, such as passwords or pins, is exposed through the user interface.
* Testing Whether Sensitive Data Is Exposed via IPC Mechanisms
    > :heavy_check_mark: No sensitive data is exposed via IPC mechanisms.
* Testing for Sensitive Information in Auto-Generated Screenshots
    > :heavy_check_mark: The app removes sensitive data from views when backgrounded.
* Testing the Device-Access-Security Policy
    > :heavy_check_mark: The app enforces a minimum device-access-security policy, such as requiring the user to set a device passcode.
* Testing user education
    > :heavy_check_mark: The app educates the user about the types of personally identifiable information processed, as well as security best practices the user should follow in using the app. 
* Testing for Sensitive Data in Memory
    > :heavy_check_mark: The app does not hold sensitive data in memory longer than necessary, and memory is cleared explicitly after use.
* Testing For Sensitive Data in Local Data Storage
    > :heavy_check_mark: No sensitive data should be stored outside of the app container or system credential storage facilities.

    > :heavy_check_mark: System credential storage facilities are used appropriately to store sensitive data, such as PII, user credentials or cryptographic keys.
* Testing for Sensitive Data in Backups
    > :heavy_check_mark: No sensitive data is included in backups generated by the mobile operating system.

### Resiliency Against Reverse Engineering

* Testing Simple Emulator Detection
    > :heavy_check_mark: Impede Dynamic Analysis and Tampering - The app detects, and responds to, being run in an emulator.
* Impede comprehensive and analysis
    > :heavy_check_mark: Impede Dynamic Analysis and Tampering - The app implements multiple mechanisms in each defense category (8.1 to 8.6). Note that resiliency scales with the amount, diversity of the originality of the mechanisms used.

    > :heavy_check_mark: Impede Dynamic Analysis and Tampering - The detection mechanisms trigger responses of different types, including delayed and stealthy responses. 

    > :heavy_check_mark: Impede Comprehension - If the goal of obfuscation is to protect sensitive computations, an obfuscation scheme is used that is both appropriate for the particular task and robust against manual and automated de-obfuscation methods, considering currently published research. The effectiveness of the obfuscation scheme must be verified through manual testing. Note that hardware-based isolation features are preferred over obfuscation whenever possible. 
* Testing Run-Time Integrity Checks
    > :heavy_check_mark: Impede Dynamic Analysis and Tampering - The app detects, and responds to, tampering the code and data in its own memory space. 
* Testing Simple Obfuscation
    > :heavy_check_mark: Impede Dynamic Analysis and Tampering - Obfuscation is applied to programmatic defenses, which in turn impede de-obfuscation via dynamic analysis. 
* Testing Detection of Reverse Engineering Tools
    > :heavy_check_mark: Impede Dynamic Analysis and Tampering - The app detects, and responds to, the presence of widely used reverse engineering tools and frameworks on the device. 
* Testing Device Binding
    > :heavy_check_mark: Device Binding - The app implements a 'device binding' functionality using a device fingerprint derived from multiple properties unique to the device. 
* Testing Jailbreak Detection, Testing Root Detection
    > :heavy_check_mark: Impede Dynamic Analysis and Tampering - The app detects, and responds to, the presence of a rooted or jailbroken device either by alerting the user or terminating the app. 
* Testing File Integrity Checks
    > :heavy_check_mark: Impede Dynamic Analysis and Tampering - The app detects, and responds to, tampering with executable files and critical data within its own sandbox. 
* Testing Obfuscation
    > :heavy_check_mark: Impede Comprehension - All executable files and libraries belonging to the app are either encrypted on the file level and/or important code and data segments inside the executables are encrypted or packed. Trivial static analysis does not reveal important code or data. 
* Testing Debugging Defenses
    > :heavy_check_mark: Impede Dynamic Analysis and Tampering - The app prevents debugging and/or detects, and responds to, a debugger being attached. All available debugging protocols must be covered. 

### Network Communication

* Testing Endpoint Identify Verification
    > :heavy_check_mark: The app verifies the X.509 certificate of the remote endpoint when the secure channel is established. Only certificates signed by a trusted CA are accepted. 
* Verifying that Critical Operations Use Secure Communication Channels
    > :heavy_check_mark: The app doesn't rely on a single insecure communication channel (email or SMS) for critical operations, such as enrollments and account recovery. 
* Verifying the TLS Settings
    > :heavy_check_mark: The TLS settings are in line with current best practices, or as close as possible if the mobile operating system does not support the recommended standards. 
* Testing Custom Certificate Stores and SSL Pinning
    > :heavy_check_mark: The app either uses its own certificate store, or pins the endpoint certificate or public key, and subsequently does not establish connections with endpoints that offer a different certificate or key, even if signed by a trusted CA. 
* Testing for Unencrypted Sensitive Data on the Network
    > :heavy_check_mark: Data is encrypted on the network using TLS. The secure channel is used consistently throughout the app.
* Verifying the Security Provider
    > :heavy_check_mark: The app only depends on up-to-date connectivity and security libraries.

### Code Quality and Build Settings

* Verifying usage of Free Security Features
    > :heavy_check_mark: Free security features offered by the toolchain, such as byte-code minification, stack protection, PIE support and automatic reference counting, are activated. 
* Testing If the App is Debuggable
    > :heavy_check_mark: The app has been built in release mode, with settings appropriate for a release build (e.g. non-debuggable).
* Testing for Weaknesses in Third Party Libraries
    > :heavy_check_mark: All third party components used by the mobile app, such as libraries and frameworks, are identified, and checked for known vulnerabilities. 
* Testing for Debugging Code and Verbose Error Logging
    > :heavy_check_mark: Debugging code has been removed, and the app does not log verbose errors or debugging messages.
* Testing Exception Handling
    > :heavy_check_mark: The app catches and handles possible exceptions.
* Testing for Memory Management Bugs
    > :heavy_check_mark: In unmanaged code, memory is allocated, freed and used securely.
* Testing Error Handling in Security Controls
    > :heavy_check_mark: Error handling logic in security controls denies access by default.
* Testing for Debugging Symbols
    > :heavy_check_mark: Debugging symbols have been removed from native binaries.
* Verifying That the App is Properly Signed
    > :heavy_check_mark: The app is signed and provisioned with a valid certificate, of which the private key is properly protected.

### Cryptography

* Testing for Insecure and/or Deprecated Cryptographic Algorithms
    > :heavy_check_mark: The app does not use cryptographic protocols or algorithms that are widely considered depreciated for security purposes.
* Verifying the Configuration of Cryptographic Standard Algorithms
    > :heavy_check_mark: The app uses cryptographic primitives that are appropriate for the particular use-case, configured with parameters that adhere to industry best practices. 
* Verifying Key Management
    > :heavy_check_mark: The app doesn't re-use the same cryptographic key for multiple purposes.

    > :heavy_check_mark: The app does not rely on symmetric cryptography with hardcoded keys as a sole method of encryption
* Testing for Custom Implementations of Cryptography
    > :heavy_check_mark: The app uses proven implementations of cryptographic primitives.
* Testing Random Number Generation
    > :heavy_check_mark: All random values are generated using a sufficiently secure random number generator.

### Platform Interaction

* Testing Input Validation and Sanitization
    > :heavy_check_mark: All inputs from external sources and the user are validated and if necessary sanitized. This includes data received via the UI, IPC mechanisms such as intents, custom URLs, and network sources. 
* Testing Object (De-)Serialization
    > :heavy_check_mark: Object deserialization, if any, is implemented using safe serialization APIs.
* Testing For Sensitive Functionality Exposure Through IPC
    > :heavy_check_mark: The app does not export sensitive functionality through IPC facilities, unless these mechanisms are properly protected.
* Testing Custom URL Schemes
    > :heavy_check_mark: The app does not export sensitive functionality via custom URL schemes, unless these mechanisms are properly protected.
* Testing App Permissions
    > :heavy_check_mark: The app only requests the minimum set of permissions necessary.

### Authentication and Session Management

* Verifying that Users Are Properly Authenticated
    > :heavy_check_mark: If the app provides users access to a remote service, some form of authentication, such as username/password authentication, is performed at the remote endpoint. 
* Testing Stateless Authentication
    > :heavy_check_mark: If stateless token-based authentication is used, the server provides a token that has been signed using a secure algorithm.
* Testing the Session Timeout
    > :heavy_check_mark: Sessions are invalidated at the remote endpoint after a predefined period of inactivity and access tokens expire.

### Architecture, design and threat modelling

* Components
    > :heavy_check_mark: All app components are identified and known to be needed.
* Architecture
    > :heavy_check_mark: Security controls are never enforced only on the client side, but on the respective remote endpoints.

    > :heavy_check_mark: A high-level architecture for the mobile app and all connected remote services has been defined and security has been addressed in that architecture. 

    > :heavy_check_mark: Data considered sensitive in the context of the mobile app is clearly identified.
