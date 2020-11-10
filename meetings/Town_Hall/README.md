# PathCheck Town Hall 

## Town Hall 10/29/2020
### Recording:
https://drive.google.com/file/d/1czSTMGrs3a6zpGbaCGrFr4wp202A3QR7/view

### Agenda
* Overview
* Introductions (Panelists)
* Goals of Privacy and Security
* Next Steps / Future

### Timestamps:
**(0:00)** Overview and Introductions

**(6:30)** What is GAEN-mobile and how does it work?
  * GAEN-mobile is a COVID19 contract tracing app to help alert users who may have been exposed to the virus. It works by sending and storing randomized unique values via Bluetooth. Each user gets a random code, and the random codes of others around them; if a user is diagnosed with the virus, users that have the code stored will be alerted.


**(12:03)** How does this app's data compare to other's on my phone?
 * GAEN-mobile only uses the functions and features necessary to perform contact tracing. Utilizing anonymous bluetooth tokens to be shared and stored in comparison to other apps using location, camera, contacts, etc. in order to function. 


**(16:55)** How do you measure adoption?
  * Jurisdictions can optionally allow for users to submit additional data such as positive tests or symptoms, however these are always specifically allowed by the user. Using this data we can measure how often, and how effectively the app is working.

**(21:15)** How does Security/Privacy controls impact development/QA testing? 
  * Because no data is shared unless the user defines it, development and QA testing becomes difficult as feedback is only received if the user specifically shares it.

**(23:25)** Can contact tracing slow the spread of COVID? How can effectiveness be tracked provided the privacy focus of the application?
  * Yes, through contact tracing users can find out earlier about possible exposures and seek treatment and quarantine appropriately to control the spread of the virus. Effectiveness can be tracked through users sharing usage data and feedback to show a decline in cases. 

**(28:00)** How reliable is the tracking technology? Is GPS still in use? _[Answer: No]_
  * GPS is not in use in GAEN-mobile. The application will not run if GPS is enabled on the application. GAEN-mobile utilizes random unique tokens shared locally from users.

**(30:49)** Why move from GPS to Bluetooth? How reliable, secure, and accurate are GPS and Bluetooth contact tracing? Are their trade offs?
  * Bluetooth offers more privacy and security by default than GPS by only sharing unique randomized bluetooth tokens with other users of the application rather than sharing location data. GPS would allow for better location tracking and notifications, with the trade off that there would be much less security. GPS also doesn't account for elevation differences that bluetooth exposure notifications handle well. 
  
**(36:04)** Has Google/Apple GAEN been changing over time? 
  * Yes, the original algorithm GAEN uses has remained consistent; however, they have pushed many quality-of-life patches and maintenance updates.

**(38:01)** Can gaen-mobile be used to track an individual's location? _[Answer: No]_
  * No, GAEN-mobile uses unique randomized bluetooth tokens that are shared when two users are within exposure proximity to one-another. The app monitors relative position to others using the app with no specific location data attached. 

**(45:51)** What is being done to protect the security and privacy of users?
  * Penetration testing, binary static code analyses, agent and non-agent based software composition analyses, and dynamic code analyses have all been conducted to ensure the privacy and security of the application and it's users.
  
**(47:45)** What are the results of the penetration test?
  * There were no security vulnerabilities detected within the application. There were 2 security enhancements that were detected: SSL Pinning and Root Detection. PathCheck communicated the findings with Apple/Google and they gave the specific recommendation to not implement SSL Pinning remedies as it hurts the reliability of the application. Root detection is a security enhancement that is in the works internally within PathCheck. 
   
**(50:16)** What are the results of the static code analysis and software composition analysis? 
  * The static code analyses and software composition analyses found no vulnerabilities present within the application. The scans flagged a few libraries in use that have vulnerabilities present, however PathCheck confirmed the areas of the library that are vulnerable are not in use in the GAEN-mobile application. 

**(53:07)** What is a DPIA and what were the results?
  * A Data Protection Impact Assessment (DPIA) is the 'best in class' standard for minimizing data protection risks. We expect to complete the assessment very soon.
  
**(55:31)** What data leaves the device and does it need approval?
  * Unique random bluetooth tokens, product analytics (only some app versions), and user submitted forms. All data that leaves the device and application is specifically defined and allowed by the user.

**(58:58)** Are IP addresses stored by the notification / verification server for submissions?
  * No, verification servers do not store IP addresses. Verification servers and their protocols are also independent of PathCheck's GAEN-mobile application.
  
**(01:01:01)** Why does every state have it's own server vs having a central one? Is this because of privacy or security?
 * The intention of this was to have each health authority can control the data and privacy/security requirements they use in their implementation of the GAEN-mobile application. Google/Apple are implementing a centralized token server in order to allow for exposure notifications across state/health authority borders. 
  
**(01:05:01)** Is there a risk to using a centralized notification server?
 * No, they centralized key server would only serve the purpose of sharing the unique random bluetooth tokens across health authority borders and holds no authentication or personal data. 
  
**(01:07:01)** How long is the data stored on the notification server?
 * The random unique bluetooth tokens are stored on the notification server for 14 days, and none of the data is user identifiable.
  
**(01:08:28)** Is there any other usage planned for the technology? Are their other advancements planned within the technology? Reverse contact tracking?
  * The Google/Apple exposure notification server requires each state or health authority that uses their API to commit to taking down the app following the COVID19 pandemic. QR code scanning is another possible advancement that could be coming to the Google/Apple exposure notification server, that will also entail specific security constraints in order to access (i.e. Open-source code bases) which PathCheck happily complies with.