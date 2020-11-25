![](RackMultipart20201125-4-cadnvf_html_5ebd433fc02f9ab9.png)

# PathCheck: Security Practices for Developers

19 November 2020

# Table of Contents

[PathCheck: Security Practices for Developers 1](#_Toc56688686)

[Introduction 1](#_Toc56688687)

[How to report a security issue 1](#_Toc56688688)

[Security in our development process 2](#_Toc56688689)

[Security best practices 2](#_Toc56688690)

[Other Coding Guidelines 3](#_Toc56688691)

# Introduction

The [Privacy Principles](https://github.com/Path-Check/privacy-security-GAEN/blob/master/principles/1_Privacy.md) page outlines the privacy intentions of the PathCheck Foundation&#39;s GAEN Exposure Notification Apps.

The [Privacy &amp; Security Repo for GAEN - Exposure Notification Apps](https://github.com/Path-Check/privacy-security-GAEN) page provides information about how to contribute to the PathCheck Foundation&#39;s GAEN Exposure Notification Apps and provides links to other security related documentation.

This document is intended to outline common security practices that developers contributing code should be aware of and adhere to.

# How to report a security issue

We encourage you to responsibly report issues via email to security@pathcheck.org.

Assist us by providing as much detail as you can about your environment, the GAEN-mobile application version, plugins used (if relevant), and any other relevant information.

A response from a team member acknowledging receipt of your email, will typically be within 24 hrs. If you do not receive a response, please know we are not ignoring you – it is quite possible your email did not make it through a spam filter.

We appreciate your patience in understanding that some bugs will take time to correct and the process may involve a review of the codebase for similar problems. Coordinating across time zones and work schedules can be time-consuming so your input and effort in this matter is warmly received. It is also crucial we can trust you not to disclose the vulnerability to anyone until a few days after the release of the stable GAEN-mobile application, and after the advisory is issued.

As a thank you, your name will be credited in the Changelog.

# Security in our development process

Core developers are all committed to achieving the highest standard of security. All PathCheck code should adhere to the security checklist. All commits to the PathCheck GitHub repository are reviewed by at least two core developers.

Regular external security reviews do take place, and some of these have contributed a few security suggestions. The GAEN-mobile application undergoes rigorous security testing supported by industry leaders including Cobalt.io, best-of-breed tools including Veracode and WhiteSource, the Bugcrowd crowdsourced cybersecurity platform, opensource testing solutions including the Mobile Security Framework, certified penetration testing experts, along with numerous volunteers continually reviewing and testing the GAEN-mobile application.

Feature requests are regularly reviewed and any efforts introducing significant features, require design documents and review by experienced security professionals.

The PathCheck Foundation also uses an ever-expanding comprehensive set of automated tests and automated web tests running after each code change on servers as part of its continuous integration and software quality assurance. Security testing includes ongoing Binary Static Code Analysis, Software Composition Analysis, Dynamic Application Security Testing, and Timeboxed Integral Penetration-testing to thoroughly assess the application&#39;s security and locate any vulnerabilities that could impact the confidentiality, integrity, or availability of the GAEN-mobile ecosystem. This complements our software development practices such as code reviews. Information about security assessments can be found at [https://github.com/Path-Check/privacy-security-GAEN/tree/master/assessments](https://github.com/Path-Check/privacy-security-GAEN/tree/master/assessments).

The PathCheck Foundation has a policy and processes for identifying, prioritizing, and remediating or mitigating risks that may be introduced by the use of third-party software or services. Any feature that introduces a new dependency on a third-party must be identified and a risk assessment must be performed.

We also maintain a list of requests for security improvements.

For any security issue identified, PathCheck works swiftly to remediate the issue and, when provided, PathCheck follows Google and Apple&#39;s remediation guidance. We hope PathCheck is not vulnerable to any critical security bugs and we are committed to ensuring that this remains the case. Thank you for your support!

# Security best practices

This guide contains a list of methods to combat certain vulnerabilities. Follow all of them when working on your plugin or contribution.

All code contributors should be familiar with the OWASP Top 10, which is a standard awareness document for developers and web application security. It represents a broad consensus about the most critical security risks to web applications.

To learn **more about security in web applications** read this article: [Top 10 Security from The Open Web Application Security Project (OWASP)](https://www.owasp.org/index.php/Top_10_2013-Table_of_Contents).

The PathCheck Foundation&#39;s [OWASP Principles and Responsibilities Guide](https://github.com/Path-Check/privacy-security-GAEN/blob/master/principles/OWASP-Principles-Responsibility-Sheet.md) shows which controls are the responsibility of PathCheck and its developers, which are the responsibility of Google and Apple (GAEN), and which are the responsibility of each HA/Jurisdiction.

OWASP also publishes its [Mobile Application Security Verification Standard](https://github.com/OWASP/owasp-masvs) and other information from its [Mobile Security Project](https://owasp.org/www-project-mobile-security/).

The document at [https://github.com/Path-Check/privacy-security-GAEN/blob/master/principles/2\_security.md](https://github.com/Path-Check/privacy-security-GAEN/blob/master/principles/2_security.md) provides a detailed list of principles substantially derived from OWASP materials.

# Other Coding Guidelines

Here are some additional coding guidelines that will help make your code more secure:

 * Do not write overly complex code. Consider using tool to generate a [cyclomatic complexity](https://en.wikipedia.org/wiki/Cyclomatic_complexity) metric (CCM) of your code. If the CCM is 12 or greater consider refactoring your code to make it simpler. This is especially important for open source project such as the PathCheck gaen-mobile application because of the variety of volunteers working on the project over time.

 * Do not hard-code secrets, API keys, or passwords into the code. iOS apps should store secrets and credentials in the KeyChain. Android versions should use the Android Keystore system. If you have a key or token that can be disclosed without compromising security, that may be hard-coded, but the name and nearby comments should clearly indicate that it is a public token and that disclosure does not impact the security of the application. In addition, since many security analysis tools may still identify it as a hard-coded secret, it may be worthwhile to obfuscate the value.

 * Use native TLS libraries on the OS. Some third party libraries have vulnerabilities such as HeartBleed, which can be exploited for man-in-the-middle attacks.

 * Use secure communication channels. All app communication must be encrypted.

 * Store data securely. Data should not be stored in files in plaintext at any point. No sensitive data should be stored outside of the app container or system credential storage facilities.

 * Do not enable inter-app communication.

 * Only declare permissions that the app actually needs and uses in the app.

 * Do write unit test cases for your code.

![](RackMultipart20201125-4-cadnvf_html_353a77aa6a08bd29.gif)



PathCheck Foundation &amp; Tuik Security Group LLC