# Opdracht Security evaluatie
Dit is een copy van https://github.com/T3hArco/RFIDPayments om op security te evalueren.

Gehost via Heroku: https://opdrachsecurityevalutatie.herokuapp.com/

## Uitgevoerde testen
 - DAST
     - Gebruikte tool: https://www.zaproxy.org/
     - Resultaten: <img src="https://cdn.discordapp.com/attachments/649230019817635854/1013015643827744788/unknown.png"/>
 - SCA
 - Penetration testing AKA ethical hacking
 - SAST
 - Evaluatiecriteria ivm wachtwoorden
     - Er zijn geen user logins. Er kan makkelijk gegevens van andere gebruikers uitgelezen worden. Een secure login systeem is een vereiste wanneer user interaction    mogelijk is bij deze applicatie.
 - Evaluatiecriteria ivm HTTPS
     - Webapplicatie heeft geen HTTPS redirect. Dit is op verschillende manier op te lossen. Voorbeeld: https://stackoverflow.com/questions/5106313/redirecting-from-http-to-https-with-php
