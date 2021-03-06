# Privacy Principles

## Lawful
Contact tracing apps must comply with all applicable laws, rules and regulations. Any data collection and use must have a lawful basis. 

## Voluntary
The use of contact tracing apps should be voluntary and not mandatory or compelled. 

## Informed Consent
A user must provide informed consent as a prerequisite for the installation and use of a contact tracing app. A user should be able to give their consent to each function of an app separately. This includes any third party libraries like Google's SafetyNet et al.

## Identity Control
Users make the determination to release of identifier such as Temporary Exposure Keys (TEK) and others. 

## Accountability
In order to ensure that organizations adhere to contact tracing privacy principles, there must be enforcement measures. For example, the following are three types of enforcement measures: Self-regulation by the information collectors or an appointed regulatory body; Private remedies that give civil causes of action for individuals whose information has been misused to sue violators; and Government enforcement that can include civil and criminal penalties levied by the government.

Relevant stakeholders should be fully involved and consulted in the development and deployment of an app, including data protection authorities, the privacy and security community, human rights and civil liberties organizations, government agencies, technology community, and public health professionals, including epidemiologists.

## Exposure Notification Server
Exposure Notification Server should have SSL certificate pinnings for secured communication between the server and EN apps. No privacy identifiers, such as IP address, should not be used, either directly or indirectly, in any communication between the server and EN apps. 

## Privacy Identifiers
No privacy identifiers, direct or indirect, should be used or saved in mobile apps, or EN Server. 


## Data Retention
Delete history exposure keys after 14 days. After 14 days, the exposure keys can no longer be matched to a device.

## Other Measures
* Data shall be as accurate as possible.
* All data is encrypted in transit and encrypted at rest in EN apps and server(s).
* No single person shall be able to both modify the source code and release the application to the public.
* All source code, models and technical documentation shall be publicly available, including all dependencies
* Privacy shall be as inclusive as possible, and this includes making the application work just as well for people with different abilities, wherever technically possible, and based on W3C/WAI standards
* Admin tool, used for configuration of backend-database, should not be deployed in production.

