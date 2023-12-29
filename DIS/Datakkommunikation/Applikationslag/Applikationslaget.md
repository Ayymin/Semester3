**Lektionens formål**
At forstå applikationslagets opgaver og tjenester
## <mark class="hltr-orange">Læsemateriale</mark>
![[Applikationslaget_PP.pdf]]

![[DNS_PP.pdf]]

## <mark class="hltr-green">Applikationsprotokoller</mark>
Protokolstakken eksisterer for at mindske design kompleksitet for de fleste netværk, ved at udarbejde en stak af lag.
Formål med hvert lag er at tilbyde visse services til laget ovenover og "skjuler" detaljer for disse lag.
Hvert lag giver data til det lag, der er lige nedenunder. 
![[Applikationslag ISO.png|424]]
Applikationslaget danner grundlag for at brugeren har adgang til information på netværket via programmer. Dette lag er brugergrænsefladen, eller brugerinterfacet til programmet, og derigennem til netværket. 

Applikationslaget udgør brugerens interface til netværket gennem programmer. Det tillader filoverførsel via FTP, håndterer e-mails gennem SMTP og faciliterer anmodninger og overførsel af websider via HTTP. 

#### <mark class="hltr-red">HTTP</mark>
![[HTTP visuel.png|400]]
<mark class="hltr-pink">Definition</mark>
HyperText Transfer Protocol er hjertet af Web, det driver world Wide web.
Overfladsmæssigt fungerer det ret simpelt, en klient efterspørger  dokument, billeder, eller andre former for ressourcer og en server returner. Det skal understreges at HTTP er implementeret i to programmer. Et klient program og et server program. 

<mark class="hltr-pink">Cookies
</mark>
HTTP server er stateless, det vil sige at der ikkke gemmes noget data på HTTP'en. Enhver interaktion der sendes fran en klient til en server, betragtes som en separat og uafhængig handling. For at imødegå HTTPs stateless-natur, blev cookies udviklet som et modsvar. 

Cookies fungerer som et kunstigt "sessions lag" oven på HTTP, der skaber en sammenhæng mellem forskellige anmodninger fra den samme bruger. Via dette opbevares der midlertidige data. 

<mark class="hltr-pink">Cookies komponenter</mark>
Cookies består af 4 komponenter:
* En cookie fil der er på brugerens end system og håndteres af brugerens browser
* En back-end database på Web sitet
* En cookie header line i HTTP request beskeden
* En cookie header line i HTTP response beskeden. 


#### <mark class="hltr-yellow">SMTP</mark>
![[SMTP visuel.png|325]]
<mark class="hltr-orange">Definition</mark>
Simple Mail Transfer Protocol bruges til at sende og videresende mails mellem mailservere. Den håndtere transmissionen af e-mails fra afsendende til modtagende mailservere. 

<mark class="hltr-orange">Funktion</mark>
SMTP er designet specifikt til at videresende e-mails fra afsendende mailservere til modtagende mailservere. Når en bruger sender en e-mail gennem en mailklient, bruger klienten SMTP til at sende e-mailen til afsenderens mailserver. Denne mailserver videresender derefter e-mailen til modtagerens mailserver gennem internet. 

<mark class="hltr-orange">SMTP komponenter</mark>
* Mailklient: Brugt til at skrive og sende e-mails
* Mailserver: Ansvarlig for at sende, modtage og videresende e-mails.
* SMTTP-kommandoer-og-svar: Serie af instruktioner og svar, som mailservere bruger til at overføre e-mails.
* Overskrifter og beskedtekst: E-mailens opbygning med metadata i overskrifter 

#### <mark class="hltr-green">DNS</mark>
![[DNS simplified.png|350]]
<mark class="hltr-cyan">Definition</mark>
DNS er en protokol, der fungerer som internettets "telefonbog", der oversætter menneskeligt læsbare domænenavne til numeriske IP-adresser, som computere bruger til at identificere hinanden på nettet.

<mark class="hltr-cyan">Funktion</mark>
Når en bruger indtaster et domænenavn som f.eks. "youtube.com" i deres browser, udfører enheden en DNS-forespørgsel for at finde den tilsvarende Ip-adresse til det angivne domænenavn. DNS-serveren oversætter derefter domænenavnet til IP-adressen, så browseren kan etablere forbindelse til den specifikke server, der hoster den efterspurgte hjemmeside. Denne proces kaldes "Resolution"

<mark class="hltr-cyan">DNS processen</mark>
![[DNS forespørgsel.png|475]]
* Local DNS-cache: Først kigges der i den enkelte enheds DNS-cache, for at se om den har gemt IP-adressen for den efterspurgte domæne. 
* Root-DNS server: Næste skridt hvis den ikke findes lokalt. Dise servere indeholder oplysninger om de autoritative DNS-servere for topdomænerne, fx .com