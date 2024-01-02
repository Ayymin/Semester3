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

![[Pasted image 20240102172509.png|450]]
<mark class="hltr-orange">Sliding Window</mark>
Sliding window er en teknik, der administrerer dataoverførsel mellem en sender og en modtager. Det tillader afsenderen at sende flere datapakker, før der afventes en bekræftelse (acknowledgement) fra modtageren. Dette koncept muliggør en mere effektiv udnyttelse af netværksbåndbredde og forbedrer overførselshastigheden.

I det overstående eksempel, afsendes der datapakker: 0,1,2,3. Hvor vi så kan se at der kommer et acknowledgement på 0, 1. Derefter sendes 4 og 5, men der kommer ingen acknowledgement på 2. Derfor gensendes 2, samt de 4 rammer der kom efter. Det giver os en window size på 4. 



Emner:
Go Back N (GBN)
Selective Repeat (SR)
TCP
UDP

