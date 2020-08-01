# Introduction

This document makes heavy use of the OWASP (Open Web Application Security Project) project.  It is best read in conjuction with the OWASP deliverables that explain acronyms, reference test procedures, and provide a glossary. Also, some of the principles have been modified to get GAEN recommendations.

## Security Principles

### OWASP Principles
The following principles have been derived from [OWASP principles applicable to mobile applications](https://owasp.org/www-project-mobile-security-testing-guide/), and applicable to the EN apps and related Notification Server:

* MSTG-ARCH-1 All app components are identified and known to be needed.
* MSTG-ARCH-2 A high-level architecture for the mobile app and all connected EN server components has been defined and security has been addressed in that architecture
* MSTG-ARCH-3 All app components are defined in terms of the business functions and/or security functions they provide.
* MSTG-ARCH-4 A threat model for the mobile app and the associated remote services has been produced that identifies potential threats and countermeasures.
* MSTG-ARCH-5 Encryption of Temporary Exposure Keys (TEK) and related key management should follow standards / refernce architecture recommended by [GAEN Cryptographic Specification](https://covid19-static.cdn-apple.com/applications/covid19/current/static/contact-tracing/pdf/ExposureNotification-CryptographySpecificationv1.2.pdf?1).
* MSTG-ARCH-6 Security is addressed within all parts of the software development lifecycle.
* MSTG-CRYPTO-1 The app does not rely on symmetric cryptography with hardcoded keys as a sole method of encryption.
* MSTG-CRYPTO-2 The app uses proven implementations of cryptographic primitives.
* MSTG-CRYPTO-3 The app uses cryptographic primitives that are appropriate for the particular use-case, configured with parameters that adhere to industry best practices.
* MSTG-CRYPTO-4 The app does not use cryptographic protocols or algorithms that are widely considered deprecated for security purposes.
* MSTG-CRYPTO-6 EN apps must use SSL certificate pinning to verify that they are securely communicating with the correct EN server.

* MSTG-NETWORK-1 Data is encrypted on the network using Transport Level Security (TLS). The secure channel is used consistently throughout the app.
* MSTG-NETWORK-2 The TLS settings are in line with current best practices, or as close as possible if the mobile operating system does not support the recommended standards.
* MSTG-NETWORK-3 The app verifies the X.509 certificate of the remote endpoint when the secure channel is established. Only certificates signed by a trusted Certificate Authority (CA) are accepted.
* MSTG-NETWORK-4 The app only depends on up-to-date connectivity and security libraries.

* MSTG-PLATFORM-1 The app only requests the minimum set of permissions necessary
* MSTG-PLATFORM-2 All inputs from external sources and the user are validated and if necessary sanitized. This includes data received via the User Interface (UI), Inter-Process Communication (IPC) mechanisms such as intents, custom Uniform Resource Locators (URLs), and network sources.
* MSTG-PLATFORM-3 The app does not export sensitive functionality via custom URL schemes, unless these mechanisms are properly protected.
* MSTG-PLATFORM-4 JavaScript is disabled in WebViews unless explicitly required.
* MSTG-PLATFORM-5 WebViews are configured to allow only the minimum set of protocol handlers required (ideally, only https is supported). Potentially dangerous handlers, such as file, tel and app-id, are disabled.
* MSTG-PLATFORM-8 Object deserialization, if any, is implemented using safe serialization Application Programming Interfaces (APIs).
* MSTG-CODE-1 The app is signed and provisioned with a valid certificate, of which the private key is properly protected.
* MSTG-CODE-2 The app has been built in release mode, with settings appropriate for a release build (e.g. non-debuggable).
* MSTG-CODE-3 Debugging symbols have been removed from native binaries.
* MSTG-CODE-4 Debugging code and developer assistance code (e.g. test code, backdoors, hidden settings) have been removed. The app does not log verbose errors or debugging messages.
* MSTG-CODE-5 All third party components used by the mobile app, such as libraries and frameworks, are identified, and checked for known vulnerabilities.
* MSTG-CODE-6 The app catches and handles possible exceptions.
* MSTG-CODE-7 Error handling logic in security controls denies access by default.
* MSTG-CODE-8 In unmanaged code, memory is allocated, freed and used securely.
* MSTG-CODE-9 Free security features offered by the toolchain, such as byte-code minification, stack protection, Position Independent Executable (PIE) support and automatic reference counting, are activated.
* MSTG-STORAGE-1: System credential storage facilities need to be used to store sensitive data, such as Personally Identifiable Information (PII), user credentials or cryptographic keys. [![PASS](../images/pass.png?raw=true)](../dynamic_testing/MSTSG_STORAGE.md)
* MSTG-STORAGE-2: No sensitive data should be stored outside of the app container or system credential storage facilities.  [![PASS](../images/pass.png?raw=true)](../dynamic_testing/MSTSG_STORAGE.md)
* MSTG-STORAGE-3: No sensitive data is written to application logs.  [![PASS](../images/pass.png?raw=true)](../dynamic_testing/MSTSG_STORAGE.md)
* MSTG-STORAGE-4: No sensitive data is shared with third parties unless it is a necessary part of the architecture.  [![PASS](../images/pass.png?raw=true)](../dynamic_testing/MSTSG_STORAGE.md)
* MSTG-STORAGE-5: The keyboard cache is disabled on text inputs that process sensitive data.  [![PASS](../images/pass.png?raw=true)](../dynamic_testing/MSTSG_STORAGE.md)
* MSTG-STORAGE-6: No sensitive data is exposed via IPC mechanisms.  [![PASS](../images/pass.png?raw=true)](../dynamic_testing/MSTSG_STORAGE.md)
* MSTG-STORAGE-7: No sensitive data, such as passwords or pins, is exposed through the user interface.  [![PASS](../images/pass.png?raw=true)](../dynamic_testing/MSTSG_STORAGE.md)
* MSTG-STORAGE-8: No sensitive data is included in backups generated by the mobile operating system.  [![PASS](../images/pass.png?raw=true)](../dynamic_testing/MSTSG_STORAGE.md)
* MSTG-STORAGE-9: The app removes sensitive data from views when moved to the background.  [![PASS](../images/pass.png?raw=true)](../dynamic_testing/MSTSG_STORAGE.md)
* MSTG-STORAGE-10 The app does not hold sensitive data in memory longer than necessary, and memory is cleared explicitly after use.


