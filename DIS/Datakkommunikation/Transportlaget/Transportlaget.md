**Lektionens formål**
At opnå kendskab til og forståelse for de tjenester transportlaget tilbyder

## <mark class="hltr-orange">Læsemateriale</mark>
![[Transportlaget_PP.pdf]]
## <mark class="hltr-green">Transportlaget</mark>
En transportlagsprotokol sørger for logisk kommunikation mellem applikationsprocesser, der kører på forskellige hosts. Transportlageret lever ikke data direkte til processen men til en socket.

#### <mark class="hltr-red">Socket</mark> 
En socket er et endepunkt i netværkskommunikation, identificeret af en ip-adresse og et portnummer. Det tillader dataudveksling mellem enheder og er afgørende for at etablere forbindelser og dirigere information på et netværk. 
<mark class="hltr-pink">Eksempel</mark>
* Lad os sige at du vil oprette forbindelse til en Minecraft-server, der kører på IP-adressen "192.0.2.100" og portnummeret "25565"
* Når man forsøger at oprette forbindelse, oprettes der en socket på sin computer. Den er forbundet til IP'en på computeren og en vilkårlig port, fx 12345.
* På Minecraft-serveren, der kører på IP'en "192.0.2.100" og portnummeret "25565", har serveren sin egen socket. Denne socket er tilknyttet serverens IP og portnummer. 

<mark class="hltr-pink">Multiplexing og demultiplexing</mark>
Efter at forbindelsen til modtageren oprettes samt socketsne, sendes der data til serveren. Hvis vi bygger videre på Minecraft eksemplet, så er det forskellige handlinger såsom blokplaceringer eller bevægelser som sendes. Multiplexing tillader klienten at kombinere disse forskellige datastrømme og sende dem samlet gennem den eksisterende forbindelse til serveren. 

Når det så når serveren, bruges Demultiplexing til at adskille og identificere de forskellige datatyper. Bevægelsesdata når til spillogikken, blokplaceringer til kortet og chatbeskeder til chatfunktionen. 

#### <mark class="hltr-yellow">Go Back N</mark>
Go Back N er en fejlkontrols protokol, der regner med at afsenderen sender flere datagrammer, mens den venter på bekræftelse fra modtageren for de tidligere afsendte rammer. Dette kaldes for pipelining.

![[GoBackN.png|450]]
<mark class="hltr-orange">Sliding Window</mark>
Sliding window er en teknik, der administrerer dataoverførsel mellem en sender og en modtager. Det tillader afsenderen at sende flere datapakker, før der afventes en bekræftelse (acknowledgement) fra modtageren. Dette koncept muliggør en mere effektiv udnyttelse af netværksbåndbredde og forbedrer overførselshastigheden.

I det overstående eksempel, afsendes der datapakker: 0,1,2,3. Hvor vi så kan se at der kommer et acknowledgement på 0, 1. Derefter sendes 4 og 5, men der kommer ingen acknowledgement på 2. Derfor gensendes 2, samt de 4 rammer der kom efter. Det giver os en window size på 4. 


<mark class="hltr-orange">Selective Repeat</mark>
I SR ville kun den specifikke tabte pakke blive genoverført, kontra GBN, hvor der vil gensendes den tabte pakke samt dem så der vil blive modtaget korrekt. 

Både SR og GBN eer designet til at sikre at data sendes og modtages pålideligt. Det sikrer også dataintegritet, så vi kan sikre os at dataet forbliver uforanderlige eller uforvanskede under overførsling. 


#### <mark class="hltr-green">TCP og UDP</mark>
![[TCP and UDP.png|325]]
<mark class="hltr-cyan">TCP</mark>
Transmission Control Protocol (TCP) er afgørende for at sikre, at al data modtages korrekt og i den rigtige rækkefølge. Uden TCP vil vi miste dataingretitet. Når to maskiner kommunikerer, etablerer TCP en forbindelse ved at udføre et "3 way handshake".
1. Den afsendende computer sender en SYN-besked til modtageren.
2. Modtageren svarer på med en SYN ACK.
3. Afsenderen sender en ACK til modtageren.
Efter denne håndtryksproces kan data leveres. TCP er også i stand til at genoverføre tabte datapakker for a sikre pålidelig overførsel. Dette kaldes for Retransmission.

<mark class="hltr-cyan">Retransmission</mark>
Når afsenderen sender en datarammer, registrerer den en time-out periode. Hvis den ikke modtager en acknowledgement fra modtageren inden for denne tidsgrænse, antager den, at rammen er gået tabt og sender pakken igen. 

<mark class="hltr-cyan">Anvendelser</mark>
TCP er gældende når pålidelig datatransmission er afgørende. 
Det er områder som filoverførsel, webbrowsing, e-mails og applikationer der kræver dataintegritet. 

<mark class="hltr-red">UDP</mark>
User Datagram Protocol (UDP) bruges også til at sende og modtage data. Forskellen er at UDP er connection-less og garanterer ikke datalevering. Det kan beskrives som "Fire and forget", hvor afsendere sender data til modtageren uden at forvente acknowledgement fra modtageren. Opgaven betragtes som fuldfør efter at dataet er blevet skudt. 

På trods af dette, kan UDPs tilgang beskrives som "Best effort". Protokollen gøre sit bedste for at levere dataene uden at garantere levering, ordentlig rækkefølge eller fejlfrihed. Det vil sige at der er tjeks, som vi kender fra TCP som for eksempel 3 Way Handshake eller acknowledgement til når datarammer bliver modtaget. 

<mark class="hltr-red">Anvendelser</mark>
Realtime applikationer fx Video og lydstreaming, online gaming. Generelt situationer, hvor øjeblikkelig respons er vi