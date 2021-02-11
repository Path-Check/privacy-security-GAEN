# Glossary

This overview provides a description for all acronyms and special terms which are used in the Path Check GAEN repositories. If you encounter any missing terms, please [let us know](https://github.com/Path-Check/privacy-security-GAEN/issues/new?labels=documentation%2C+bug) or [create a pull request](https://github.com/Path-Check/privacy-security-GAEN/pulls).

| Term, acronym... | Description |
| --- | --- |
| AEM | Acronym for "[Associated Encrypted Metadata](https://covid19-static.cdn-apple.com/applications/covid19/current/static/contact-tracing/pdf/ExposureNotification-BluetoothSpecificationv1.2.pdf)". A privacy preserving encrypted metadata that shall be used to carry protocol versioning and transmit (Tx) power for better distance approximation. The Associated Encrypted Metadata changes about every 15 minutes, at the same cadence as the Rolling Proximity Identifier, to prevent wireless tracking of the device.  |
| AES | Acronym for "[Advanced Encryption Standard](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard)", used in the [Exposure Notification Framework](https://covid19-static.cdn-apple.com/applications/covid19/current/static/contact-tracing/pdf/ExposureNotification-CryptographySpecificationv1.2.pdf) |
| API | An [Application Programming Interface](https://en.wikipedia.org/wiki/Application_programming_interface) (API) is a computing interface which defines interactions between multiple software intermediaries. |
| APNs | Acronym for "[Apple Push Notification service](https://en.wikipedia.org/wiki/Apple_Push_Notification_service)", a platform notification service created by Apple Inc. |
| BLE, BTLE | [Bluetooth Low Energy](https://en.wikipedia.org/wiki/Bluetooth_Low_Energy) is a wireless personal area network technology. It is used in all GAEN apps. |
| CDN | Acronym for [Content Delivery Network](https://en.wikipedia.org/wiki/Content_delivery_network). |
| COVID-19 | [Coronavirus disease 2019](https://en.wikipedia.org/wiki/Coronavirus_disease_2019) is an infectious disease caused by severe acute respiratory syndrome coronavirus 2 (SARS-CoV-2). |
| CTR | Acronym for "[Counter (Mode)](https://en.wikipedia.org/wiki/Block_cipher_mode_of_operation#CTR)", a mode of operation in cryptography, also used in the [Exposure Notification Framework](https://covid19-static.cdn-apple.com/applications/covid19/current/static/contact-tracing/pdf/ExposureNotification-CryptographySpecificationv1.2.pdf) |
| Diagnosis Key(s) | The subset of Temporary Exposure Keys uploaded when the device owner is diagnosed as positive for the coronavirus. See also the [Exposure Notification Bluetooth Specification](https://covid19-static.cdn-apple.com/applications/covid19/current/static/contact-tracing/pdf/ExposureNotification-BluetoothSpecificationv1.2.pdf) |
| DP-3T | [Decentralized Privacy-Preserving Proximity Tracing](https://github.com/DP-3T/documents), another approach to an exposure notification app, mainly driven by institutions from Switzerland. |
| FAQ | Frequently Asked Questions |
| FCM | Acronym for "[Firebase Cloud Messaging](https://en.wikipedia.org/wiki/Firebase_Cloud_Messaging)", a cross-platform cloud solution for messages and notifications. |
| GUID | Acronym for "[Globally Unique Identifier](https://en.wikipedia.org/wiki/Universally_unique_identifier)". |
| PEPP-PT | [Pan-European Privacy-Preserving Proximity Tracing](https://www.pepp-pt.org/), formerly endorsed approach to a COVID-19 exposure notification app for Germany. |
| QR Code | Acronym for [Quick Response Code](https://en.wikipedia.org/wiki/QR_code), a two-dimensional/matrix barcode, sometimes handed out by the test center after a test was conducted.  |
| Registration Token | Used to a) link the mobile phone with the data from the QR Code and b) generate a TAN which is needed to finally perform the upload of the diagnosis keys to the Exposure Notification Server.  |
| REST | Acronym for "[Representational State Transfer](https://en.wikipedia.org/wiki/Representational_state_transfer)". |
| Risk score | Several parameters are used to calculate a risk score, i.e. the likelihood that a user has been exposed to the coronavirus. |
| RPI | Acronym for "[Rolling Proximity Identifier](https://covid19-static.cdn-apple.com/applications/covid19/current/static/contact-tracing/pdf/ExposureNotification-BluetoothSpecificationv1.2.pdf)". A privacy preserving identifier derived from the Temporary Exposure Key and sent in the broadcast of the Bluetooth payload. The identifier changes about every 15 minutes to prevent wireless tracking of the device. |
| SARS-CoV-2 | [Severe acute respiratory syndrome coronavirus 2](https://en.wikipedia.org/wiki/Severe_acute_respiratory_syndrome_coronavirus_2) (SARS-CoV-2) is the strain of coronavirus that causes coronavirus disease 2019 (COVID-19), a respiratory illness. It is colloquially known as coronavirus. |
| TAN | Acronym for "[Transaction Authentication Number](https://en.wikipedia.org/wiki/Transaction_authentication_number)". Needed to ensure that a device is allowed to do the upload of the diagnosis keys. TANs are not visible to users. See our [solution architecture document](solution_architecture.md) for details. |
| TAM | Acronym for "[Technical Architecture Modeling](http://www.fmc-modeling.org/fmc-and-tam)", a modeling language mainly used at SAP to describe software architectures.
| TCN | The [TCN Coalition](https://tcn-coalition.org/) is a global community of people to support exposure notification apps during the COVID-19 pandemic. |
| TEK | Acronym for "[Temporary Exposure Key](https://covid19-static.cdn-apple.com/applications/covid19/current/static/contact-tracing/pdf/ExposureNotification-BluetoothSpecificationv1.2.pdf)". A key that’s generated every 24 hours for privacy consideration. |
