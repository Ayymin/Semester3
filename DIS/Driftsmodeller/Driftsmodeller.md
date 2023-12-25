**Lektionens formål**: 
At opnå kendskab til forskellige driftsmodeller og arkitekturer ved  
design og implementering af IT-systemer
## <mark class="hltr-orange">Læsemateriale</mark>
![[DriftmodellerB_PP.pdf]]


## <mark class="hltr-green">De tre driftsmodeller
</mark>
#### <mark class="hltr-red">Central</mark>

![[chrome_9w0xktCisQ.png|325]]
**<mark class="hltr-pink">Redegørelse</mark>**
Den central driftsmodel er et simpelt koncept som tyder på en central processorkraft/mainframe, med flere nodes eller klienter som opretter forbindelser til denne ene mainframe. 
Klienterne er afhængige af denne store "kahuna", da det i virkeligheden er den eneste processorkraft som bruges til at udregne komplekse beregninger eller opfylde behov. 

**<mark class="hltr-pink">Fordele</mark>**
* Enklere infrastrukturer, da det er nemmere at sætte op end sine driftsmodel fættere (Decentral og Distribueret)
* Enklere sikkerhedsopsætning, mere strømlinet overvågning og sikkerhedsforanstaltninger. Dette gøre det også billigere. 
* Let integration til andre systemer, da man ofte har standarder protokoller til hvordan man skal tilføje et system til mainframen. 

**<mark class="hltr-pink">Ulemper</mark>**
* Single Point of Failure, hvis den centrale enhed svigter, lammer det hele systemet. 
* Høj afhængighed, da alle klienter regner med en central mainframe, hvilket kan skabe flaskehalse. 
* Højere mulighed for databrud, da alt data er koncentreret i et enkelt sted. Derfor skal anvendere af det centrale driftssystem lave store overvejelser når det kommer til sikkerhed. 
* Forøget svartid, skyldes af tryk på netværket. 

<mark class="hltr-pink">I praksis</mark>
Den centrale driftsmodel kan ses i forskellige sektorer, heriblandt finanssektoren. Banker gemmer på store mængder af data, heriblandt kundeoplysninger, transaktioner og andre former for kritiske oplysninger. Banker er notoriske for at bruge betydelige mængder af ressourcer når det kommer til sikkerhed. 
* Kryptering og to-faktor-autentificering og regelmæssige sikkerhedsgennemgange for at beskytte data. 
* Banker er også et godt eksempel på let integration med andre systemer, her kan man tænke på mobilepay. 



#### <mark class="hltr-yellow">Decentral</mark>

<mark class="hltr-orange">Redegørelse</mark>
Den decentrale driftsmodel bygger videre på den centrale driftsmodel, men adskiller sig ved at distribuere processorkraft og data over flere enheder, i stedet for at have alt samlet på en central enhed. Det skal dog pointeres at den stadig har kendetegn på det centrale, dog med processorkraft jævnt fordelt. 


#### <mark class="hltr-green">Distribueret</mark>
