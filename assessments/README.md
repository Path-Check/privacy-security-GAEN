# Summary of Assessments

## Cobalt.io Penetration Test
The Cobalt.io penetration test suggested two security enhancements for PathCheck's GAEN-mobile application: SSL Pinning and Root Detection. 

* PathCheck contacted Google/Apple regarding SSL Pinning.  Google/Apple advised against SSL Pinning for the GAEN-mobile application stating, _Android and iOS does not trust non-standard CAs, even user or admin-added ones for TLS. Therefore, pining provides only protections against compromised CAs but a lot of risk of breakage due to rotation. We don't recommend you do it. In the event of a compromised CA Android and iOS will blacklist it remotely to protect all connections, yours included._  We are reviewing other solutions and will continue to evaluate the risk of a lack of SSL Pinning.

* The PathCheck team is currently collaborating internally and communicating with Google/Apple to implement security best practices when it comes to Root Detection.

The full report is available within the Cobalt.io Penetration Testing folder.

_Additional Write Ups of Assessments Coming Soon..._
