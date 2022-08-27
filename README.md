# Opdracht Security evaluatie
Dit is een copy van https://github.com/T3hArco/RFIDPayments om op security te evalueren.

Gehost via Heroku: https://opdrachsecurityevalutatie.herokuapp.com/

## Uitgevoerde testen
 - DAST
     - Gebruikte tool: https://www.zaproxy.org/
     - <img src="https://cdn.discordapp.com/attachments/649230019817635854/1013015643827744788/unknown.png"/>
     - Webapplicatie is niet beschermd tegen ClickJacking. Dit opgelost worden met het toevoegen van een header.
     - Meerdere cookies kunnen uitgelezen worden met JavaScript. Hier moeten ook stappen voor genomen worden om hierop te beveiligen.
 - SCA
     - Dependabot alerts: 0
     - Gebruikte tool: https://app.snyk.io/
     - Webapplicatie is door het gebruikt van HTTP paramter flows zeer gevoelig aan Cross-Site Scripting (XSS) deze wensen vervangen te worden. (High severity issue)
     - Een insecure/outdated hash is ingebruik in de webapplicatie en dient vervangen te worden. (Medium severity issue)
     - In mysqli staan hardcoded credentials die uitgelezen kunnen worden door iemand met slechte bedoelingen. Deze dienen ergens op een veilige plek opgeslaan te    worden. (Medium severity issue)
 - Penetration testing AKA ethical hacking
 - SAST
 - Evaluatiecriteria ivm wachtwoorden
     - De gebruikte hash: sha1 is niet geen secure algoritme en dienst vervangen te worden
     - Er worden hardcodes credentials gebruikt in de applicatie die onderschept kunnen worden.
 - Evaluatiecriteria ivm HTTPS
     - Webapplicatie heeft geen HTTPS redirect. Dit is op verschillende manier op te lossen. Voorbeeld: https://stackoverflow.com/questions/5106313/redirecting-from-http-to-https-with-php
