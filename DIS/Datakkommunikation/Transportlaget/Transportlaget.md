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
Efter at forb

Emner:
Multiplexing/Demultiplexing
Go Back N (GBN)
Selective Repeat (SR)
TCP
UDP
