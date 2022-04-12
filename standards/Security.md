# Security

** Requires fleshing out standard authentication information here **

## Transport Security

All service URLs must be HTTPS (that is, all inbound calls MUST be HTTPS).
Services that deal with Web Hooks MUST accept HTTPS.

We recommend that services that allow client defined Web Hook **Callback URLs SHOULD NOT transmit data over HTTP**. This is because information can be inadvertently exposed via client, network, server logs and other mechanisms.

## OWASP

The OWASP Project have a [cheatsheet on REST security](https://cheatsheetseries.owasp.org/cheatsheets/REST_Security_Cheat_Sheet.html).

There is also a short [testing methodology for testing REST security](https://cheatsheetseries.owasp.org/cheatsheets/REST_Assessment_Cheat_Sheet.html).
