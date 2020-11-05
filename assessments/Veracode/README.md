# Assessment Summary
The Veracode Application Security Platform used static analysis and software composition analysis to identify software security findings in the gaen-mobile application. Using
static analysis as well as software composition analysis helps reduce false negatives and
detect a broader range of security findings. Veracode Static Analysis models the application into an
intermediate representation, which is then analyzed for security flaws using a set of automated security
tests. Veracode Software Composition Analysis (SCA) helps you build an inventory of your
open-source components to identify vulnerabilities. Veracode leverages a continuous improvement
process and rapid updates to its SaaS-based scanning technology to ensure the lowest false-positive
rates in the industry. The end result is an accurate list of security findings for the classes of automated scans applied to the application.

# Scope
Version 1.0.8 and current develop branch (3 Nov 2020) - Entire codebase available within GitHub repository.

# Result
**Veracode discovered no vulnerabilities that impact the security of the gaen-mobile application.** 
Veracode found 0 vulnerabilities within gaen-mobile first-party application code. Veracode found vulnerable third-party packages used within gaen-mobile; however, Veracode confirmed that gaen-mobile does **NOT** use any of the insecure methods.