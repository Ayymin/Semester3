**Lektionens formål**
At forstå applikationslagets opgaver og tjenester
## <mark class="hltr-orange">Læsemateriale</mark>
![[Applikationslaget_PP.pdf]]



## <mark class="hltr-green">Applikationsprotokoller</mark>
Protokolstakken eksisterer for at mindske design kompleksitet for de fleste netværk, ved at udarbejde en stak af lag.
Formål med hvert lag er at tilbyde visse services til laget ovenover og "skjuler" detaljer for disse lag.
Hvert lag giver data til det lag, der er lige nedenunder. 
![[chrome_4sFogxsoNP.png|424]]
Applikationslaget danner grundlag for at brugeren har adgang til information på netværket via programmer. Dette lag er brugergrænsefladen, eller brugerinterfacet til programmet, og derigennem til netværket. 

Applikationslaget udgør brugerens interface til netværket gennem programmer. Det tillader filoverførsel via FTP, håndterer e-mails gennem SMTP og faciliterer anmodninger og overførsel af websider via HTTP. 

#### <mark class="hltr-red">HTTP</mark>
![[Pasted image 20231229141219.png|475]]
<mark class="hltr-pink">Definition</mark>
HyperText Transfer Protocol er hjertet af Web, det driver world wide web.
Overfladsmæssigt fungerer det meget simpelt, en klient efterspørger et dokument og en server returner. Det skal understreges at HTTP er implementeret i to programmer. Et klient program og et server program. 

<mark class="hltr-pink">Funktion
</mark>
