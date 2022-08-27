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
     - Meerdere tools wijn toegevoegd aan deze github repo die eigen rapporten opstellen.
 - Penetration testing AKA ethical hacking
     - Security headers wensen toegevoegd te worden: https://web.dev/security-headers/
     - De Database is niet meer actief en kan niet grondig getest worden.
 - SAST
     - Gebruikte tools: https://semgrep.dev/ & https://www.sonarqube.org/
     - Geen nieuwe problemen gevonden tegenover eerder vermelde problemen.
 - Evaluatiecriteria ivm wachtwoorden
     - De gebruikte hash: sha1 is niet geen secure algoritme en dienst vervangen te worden
     - Er worden hardcodes credentials gebruikt in de applicatie die onderschept kunnen worden.
 - Evaluatiecriteria ivm HTTPS
     - Webapplicatie heeft geen HTTPS redirect. Dit is op verschillende manier op te lossen. Voorbeeld: https://stackoverflow.com/questions/5106313/redirecting-from-http-to-https-with-php
 - API
     - Voornamelijk gebruikt van GET requests. Sommige van deze requests kunnen omgezet worden naar POST requests die in het algemeen veiliger zijn. 
