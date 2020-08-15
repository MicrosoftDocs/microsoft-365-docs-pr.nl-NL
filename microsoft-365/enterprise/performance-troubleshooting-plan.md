---
title: Prestatieproblemen met het plannen van Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 5/10/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: e241e5d9-b1d8-4f1d-a5c8-4106b7325f8c
ms.collection:
- M365-security-compliance
- Ent_O365
description: Dit artikel kan u helpen bij het oplossen van problemen met de prestaties van Office 365 en zelfs enkele van de meest voorkomende problemen oplossen.
ms.openlocfilehash: 9287e2649a2eb126d723e7436a9178be93087bc0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689228"
---
# <a name="performance-troubleshooting-plan-for-office-365"></a>Prestatieproblemen met het plannen van Office 365

Wilt u weten welke stappen u moet uitvoeren om traag, vastlopen en de prestaties van de SharePoint Online, OneDrive voor bedrijven, Exchange Online of Skype voor bedrijven online, en de clientcomputer te identificeren en op te lossen? Voordat u de ondersteuning belt, kan dit artikel u helpen bij het oplossen van problemen met de prestaties van Office 365 en zelfs enkele veelvoorkomende problemen oplossen.
  
Dit artikel is eigenlijk een voorbeeld van een abonnement dat u kunt gebruiken om waardevolle informatie vast te leggen over uw prestatieprobleem terwijl dit gebeurt. In dit artikel worden ook enkele belangrijke punten besproken.

Als u geen ervaring hebt met de prestaties van het netwerk en een lang abonnement wilt voor het bewaken van de prestaties tussen uw clientcomputers en Office 365, kunt u de [prestaties van Office 365 optimaliseren en problemen oplossen: beheerders en IT-professionals](performance-tuning-using-baselines-and-history.md).
  
## <a name="sample-performance-troubleshooting-action-plan"></a>Voorbeeld van een probleem met de prestaties

Dit actieplan bestaat uit twee delen: een voorbereidingsfase en een logboekregistratie fase. Als u nu een prestatieprobleem hebt en u gegevens wilt verzamelen, kunt u meteen aan de slag met dit abonnement.
  
### <a name="prepare-the-client-computer"></a>De clientcomputer voorbereiden
  
- Zoek een clientcomputer die het prestatieprobleem kan reproduceren. Deze computer wordt in de cursus voor probleemoplossing gebruikt.
- Noteer de stappen die het prestatieprobleem veroorzaken, zodat u klaar bent wanneer u gaat testen.
- Installatie hulpprogramma's voor het verzamelen en opnemen van informatie:
  - Installeer [Netmon 3,4](https://www.microsoft.com/download/details.aspx?id=4865) (of een soortgelijk hulpprogramma voor het maken van netwerktraces).
  - Installeer de gratis Basic Edition van [HTTPWatch](https://www.httpwatch.com/download/) (of een soortgelijk hulpprogramma voor het maken van netwerktraces).
  - Gebruik een scherm recorder of voer Probleemstappenbeschrijving (PSR.exe) uit, die deel uitmaakt van Windows Vista en hoger, om een overzicht te houden van de stappen die u tijdens het testen uitvoert.

### <a name="log-the-performance-issue"></a>Het prestatieprobleem registreren
  
- Sluit alle overbodige Internet browsers.
- Start de stappenbeschrijving of een andere scherm recorder.
- Start uw netmon-opname (of hulpprogramma voor netwerktracering).
- Wis de DNS-cache op de clientcomputer vanaf de opdrachtregel door ipconfig/flushdns te typen.
- Start een nieuwe browsersessie en schakel HTTPWatch in.
- Optioneel: als u Exchange Online wilt testen, voert u het hulpprogramma Exchange client Performance Analyzer uit vanaf de beheerconsole van Office 365.
- Reproduceer de exacte stappen die het prestatieprobleem veroorzaken.
- Stop de tracering van netmon of andere hulpmiddelen.
- Voer via de opdrachtregel een tracerings route uit naar uw Office 365-abonnement door de volgende opdracht in te voeren en op ENTER te drukken:

  ``` cmd
  tracert <subscriptionname>.onmicrosoft.com
  ```

- Stop de stappenbeschrijving en sla de video op. Zorg ervoor dat u de datum en tijd van de opname opneemt en of dit een goede of onjuiste werking toont.
- Sla de bestanden van de tracering op. Zorg er ook voor dat u de datum en tijd van de opname opneemt en of dit een goede of onjuiste werking toont.

Als u niet bekend bent met het uitvoeren van de hulpmiddelen uit dit artikel, kunt u zich niet zorgen maken omdat deze stappen volgende worden beschreven. Als u gewend bent dit soort netwerk opnamen te doen, kunt u overstappen op [het verzamelen van basislijnen](performance-tuning-using-baselines-and-history.md#how-to-collect-baselines), zodat de logboeken worden gefilterd en gelezen.
  
### <a name="flush-the-dns-cache-first"></a>De DNS-cache eerst wissen

Waarom? Door de DNS-cache te delegeren, kunt u uw tests met een schone lei starten. Als u de cache uitschakelt, wordt de inhoud van de DNS-resolver opnieuw ingesteld op de meest recente vermeldingen. Als u een flush opslaat, worden de bestandsvermeldingen niet verwijderd. Als u de bestandsvermeldingen van de HOST uitvoerig gebruikt, kopieert u deze naar een bestand in een andere adreslijst en leegt u vervolgens het HOSTbestand.
  
#### <a name="flush-your-dns-resolver-cache"></a>Uw DNS-resolver cache leegmaken
  
1. Open de opdrachtprompt ( **Start** \> **Run** \> **cmd** of **Windows-toets** \> **cmd**).
2. Typ de volgende opdracht en druk op ENTER:

    ``` cmd
    ipconfig /flushdns
    ```

## <a name="netmon"></a>Netmon

Het Microsoft-programma voor netwerk bewaking ([netmon](https://www.microsoft.com/download/details.aspx?id=4865)) analyseert pakketten, dit is verkeer, dat wordt doorgestuurd tussen computers in netwerken. Met netmon voor het traceren van verkeer met Office 365 kunt u pakket koppen vastleggen, weergeven en lezen, tussenliggende apparaten identificeren, belangrijke instellingen controleren op de netwerkhardware, zoeken naar genegeerde pakketten en de stroom van verkeer tussen computers in uw bedrijfsnetwerk en Office 365 volgen. Aangezien de daadwerkelijke hoofdtekst van het verkeer versleuteld is, dat wil zeggen dat de bestanden worden verzonden via SSL/TLS, kunt u 443 deze niet lezen. In plaats daarvan krijgt u een niet-gefilterde tracering van het pad dat het pakket afneemt, wat helpt u bij het opsporen van het probleem gedrag.
  
Zorg dat u op dit moment geen filter toepast. Voer in plaats daarvan de stappen uit om het probleem te demonstreren voordat u de tracering stopt en opslaat.
  
Wanneer u Netmon 3,4 hebt geïnstalleerd, opent u het hulpprogramma en voert u de volgende stappen uit:
  
### <a name="take-a-netmon-trace-and-reproduce-the-issue"></a>Een netmon-trace maken en het probleem reproduceren
  
1. Start netmon 3,4.
De **Start** pagina bevat drie deelvensters: **recente opnamen**, **Selecteer netwerken**en aan de slag **met Microsoft Network Monitor 3,4. Kennisgeving**. Het deelvenster netwerken selecteren biedt u ook een lijst met de standaard netwerken waaruit u kunt vastleggen. Zorg ervoor dat netwerkkaarten hier zijn geselecteerd.

2. Klik boven aan de **Start** pagina op **nieuwe opname** . Hiermee wordt een nieuw tabblad toegevoegd naast het tabblad **Start** pagina met de naam **opname 1**.
![De gebruikersinterface van Netmon met de nieuwe knoppen vastleggen, starten en stoppen gemarkeerd.](../media/d4527d84-62ec-4301-82d5-e0166ff71f20.PNG)

3. Als u een eenvoudige opname wilt maken, klikt u op de werkbalk op **Start** .

4. Reproduceer de stappen die tot een prestatieprobleem leiden.

5. Klik **Stop** op \> **bestand** \> **Opslaan als**beëindigen. Zorg dat u de datum en tijd met de tijdzone verduidelijkt en vermeldt of u de juiste of goede prestaties ziet.

## <a name="httpwatch"></a>HTTPWatch

[HTTPWatch](https://www.httpwatch.com/download/) wordt in rekening gebracht en een gratis editie. De gratis Basic Edition behandelt alles wat u nodig hebt voor deze test. HTTPWatch bewaakt netwerkverkeer en de laadtijd van pagina's direct vanuit het browservenster. HTTPWatch is een invoegtoepassing voor Internet Explorer waarmee de prestaties grafisch worden beschreven. De analyse kan worden opgeslagen en weergegeven in HTTPWatch Studio.
  
> [!NOTE]
> Als u een andere browser gebruikt, zoals Firefox, Google Chrome of als u HTTPWatch niet kunt installeren in Internet Explorer, opent u een nieuw browservenster en drukt u op F12 op het toetsenbord. De pop-upvenster voor ontwikkelaars wordt onder in de browser weergegeven. Als u Opera gebruikt, drukt u op CTRL + SHIFT + I voor webcontrole, klikt u op het tabblad **netwerk** en voert u de test hieronder uit. De gegevens zijn iets anders, maar de laadtijden worden nog steeds weergegeven in milliseconden. > HTTPWatch is ook zeer handig bij problemen met de laadtijd van pagina's in SharePoint Online.
  
### <a name="run-httpwatch-and-reproduce-the-issue"></a>HTTPWatch uitvoeren en het probleem reproduceren
  
HTTPWatch is een browser invoegtoepassing, dus als u het hulpmiddel in de browser wilt gebruiken, is het enigszins verschillend voor elke versie van Internet Explorer. Meestal vindt u HTTPWatch onder de Opdrachtenbalk in de browser Internet Explorer. Als u de invoegtoepassing voor HTTPWatch niet ziet in uw browservenster, controleert u de versie van uw browser door te klikken op **Help** \> **voor**, of in latere versies van Internet Explorer, klikt u op het tandwiel pictogram en **over Internet Explorer**. Als u de **opdrachten** balk wilt starten, klikt u met de rechtermuisknop op de menubalk in Internet Explorer en klikt u op **Opdrachtenbalk**.

In het verleden is HTTPWatch gekoppeld aan de opdrachten en de Explorer-balken, dus nadat u de installatie hebt voltooid, kunt u het pictogram van de **hulpmiddelen**voor het opnieuw opstarten en de werkbalken voor het pictogram weergeven. Houd er rekening mee dat u werkbalken kunt aanpassen en opties kunt toevoegen.

![De opdrachtbalk van Internet Explorer met het pictogram HTTPWatch weergegeven.](../media/198590b0-d7b1-4bff-a6ad-e4ec3a1e83df.png)
  
1. Start HTTPWatch in een browservenster van Internet Explorer. Het wordt weergegeven in de browser onder aan dat venster. Klik op **opnemen**.

2. Reproduceer de stappen die het resultaat zijn van het prestatieprobleem. Klik op de knop **stoppen** in HTTPWatch.

3. De HTTPWatch **Opslaan** of **per e-mail verzenden**. Vergeet niet het bestand een naam te geven zodat het datum-en tijdgegevens bevat en geef aan of uw controle een demonstratie van goede of onjuiste prestaties bevat.

![HTTPWatch met het tabblad netwerk voor het laden van de startpagina van Office 365.](../media/021a2c64-d581-49fd-adf4-4c364f589d75.PNG)

Deze schermafbeelding is afkomstig uit de professionele versie van HTTPWatch. U kunt traceringen openen die zijn gemaakt in de basisversie op een computer met een professionele versie en deze daar lezen. Voor de tracering via die methode zijn er mogelijk extra gegevens beschikbaar.

## <a name="problem-steps-recorder"></a>Probleemstappenbeschrijving

Met behulp van stappenbeschrijving of PSR.exe kunt u problemen vastleggen wanneer ze zich voordoen. Dit is een zeer handige functie en heel gemakkelijk te voeren.
  
### <a name="run-problem-steps-recorder-psrexe-to-record-your-work"></a>Probleemstappenbeschrijving (PSR.exe) uitvoeren om uw werk vast te leggen
  
1. Gebruik **Start** \> **Run** \> type **PSR.exe** \> **OK**, of klik op het **Windows-sleutel** \> type **PSR.exe** \> en druk vervolgens op ENTER.

2. Wanneer het venster van Small PSR.exe wordt weergegeven, klikt u op **opname starten** en reproduceert u de stappen die het prestatieprobleem veroorzaken. U kunt zo nodig opmerkingen toevoegen door op **Opmerking toevoegen**te klikken.

3. Klik op **opname stoppen** wanneer u de stappen hebt voltooid. Als het prestatieprobleem een paginaweergave is, moet u wachten tot de pagina wordt weergegeven voordat u de opname stopt.

4. Klik op **Opslaan**.

![Een schermafbeelding van de stappenbeschrijving of PSR.exe.](../media/8542b0aa-a3ff-4718-8dc4-43f5521c6c34.PNG)
  
De datum en tijd worden vastgelegd. Op die manier kunt u uw in de HTTPWatch-tracering en-in de loop van de tijd en helpt u nauwkeurig te kunnen oplossen. De datum en tijd in de naam van de record kunnen Voorst delen van de URL en de gedeeltelijke weergave van de beheersite worden weergegeven.
  
## <a name="read-your-traces"></a>Uw traces lezen

Het is niet mogelijk om alles te leren over het oplossen van netwerk-en prestatieproblemen die iemand anders moet weten via een artikel. Als u tevreden bent over de prestaties, maakt u kennis met de werking van uw netwerk en gewoonlijk. Maar het is mogelijk om een lijst met veelvoorkomende problemen af te ronden en de manier weer te geven waarop u de meest voorkomende problemen eenvoudiger kunt verhelpen.
  
Als u vaardigheden wilt zoeken voor uw Office 365-sites, kunt u geen betere docenten maken dan vaak tracerings pagina's maken en de ervaring beter lezen. Wanneer u bijvoorbeeld een kans hebt, laadt u een Office 365-service en traceert u het proces. U kunt de tracering voor DNS-verkeer filteren of de centreren zoeken voor de naam van de service waarnaar u op zoek bent. Scan de tracering om een idee te krijgen van de stappen die zich voordoen wanneer de service wordt geladen. Dit helpt u verder te leren hoe de belasting van de pagina eruit moet zien, en in het geval van probleemoplossing, met name rond de prestaties, kunt u een groot aantal zaken vergelijken.
  
Netmon gebruikt Microsoft IntelliSense in het veldweergave filter. Een IntelliSense-of intelligentere programmacode wordt gebruikt om te typen in een punt en alle beschikbare opties worden weergegeven in een selectievakje voor vervolgkeuzelijsten. Als u bijvoorbeeld zorgen voor de schaal van het TCP-venster, kunt u op dit manier de manier waarop u een filter kunt vinden (bijvoorbeeld  `.protocol.tcp.window < 100` ).
  
![Schermafbeelding van Netmon waarin wordt weergegeven dat het veld filter filter wordt gebruikt voor IntelliSense.](../media/75a56c11-9a60-47ee-a100-aabdfb1ba10f.PNG)
  
Netmon-traces kunnen veel verkeer bevatten. Als u deze niet kunt lezen, wordt waarschijnlijk overspoeld dat u de eerste keer opspoort. Het eerste wat u moet doen, is het signaal van de achtergrond geluiden in de tracering scheidt. U hebt getest op Office 365 en dat is het verkeer dat u wilt bekijken. Als u gebruikt om te navigeren door traces, hebt u deze lijst mogelijk niet nodig.
  
Verkeer tussen uw client en Office 365 wordt via TLS getransporteerd, wat betekent dat de hoofdtekst van het verkeer versleutelt en niet leesbaar is in een algemene netmon-tracering. De prestatieanalyse hoeft niet de specifieke gegevens van de informatie in het pakket te weten. Dat is echter zeer geïnteresseerd in pakketheaders en de gegevens die ze bevatten.
  
### <a name="tips-to-get-a-good-trace"></a>Tips om een goede tracering te voorkomen
  
- U weet de waarde van het IPv4-of IPv6-adres van de clientcomputer. U kunt dit achterhalen via de opdracht **prompt en vervolgens op ENTER te drukken** . Als u op de hoogte bent van dit adres, kunt u in één oogopslag zien of het verkeer van de tracering direct de clientcomputer omvat. Als er sprake is van een bekende proxy, pingt u deze en haalt u ook het bijbehorende IP-adres op.

- Flush de DNS resolver cache en, indien mogelijk, sluit alle browsers, behalve de versie waarin u de tests uitvoert. Als het u niet lukt om dit te doen als ondersteuning een dergelijk hulpprogramma op basis van een browser gebruikt om het bureaublad van de clientcomputer te zien, moet u de tracering voorbereiden.

- Ga in een bezet tracering naar de Office 365-service die u gebruikt. Als u uw verkeer niet al dan niet al eerder hebt gezien, dan is dit een handige stap bij het scheiden van het prestatieprobleem van andere netwerk geluiden. U kunt dit op een aantal manieren doen. U kunt voor de test direct voor de test gebruikmaken van _ping_ of _PSPING_ op de URL van de bepaalde service ( `ping outlook.office365.com` of `psping -4 microsoft-my.sharepoint.com:443` bijvoorbeeld). U kunt deze ping-of PsPing in een netmon-trace met de naam van het proces ook gemakkelijk vinden. U krijgt een plaats waar u kunt zoeken.

Als u de tracering van Netmon alleen op het moment van het probleem gebruikt, klopt dat ook. Als u het wilt laten overkomen, gebruikt u een filter zoals `ContainsBin(FrameData, ASCII, "office")` of `ContainsBin(FrameData, ASCII, "outlook")` . U kunt het framenummer opnemen in het traceringsbestand. U kunt ook het deelvenster _kader samenvatting_ helemaal naar rechts schuiven en de kolom GESPREKS-id opzoeken. Er is een cijfer aangegeven voor de ID van deze specifieke conversatie die u later kunt opnemen en bekijken. Zorg dat u dit filter verwijdert voordat u andere filters toepast.

> [!TIP]
> Netmon biedt veel handige ingebouwde filters. Gebruik de knop **filter laden** boven aan het deelvenster _weergave_ filter.
  
![Zoek uw IP-adres met behulp van PSPing vanaf de opdrachtregel op de clientcomputer.](../media/4c43ac67-e28e-4536-842d-7add7aa28847.PNG)
  
![Netmon-tracering van de client met dezelfde PSPing-opdracht via het filter TCP. Flags. SYN = = 1.](../media/0ae7ef7d-e003-4d01-a006-dc49bd1fcef2.PNG)
  
Raak vertrouwd met uw verkeer en leer hoe u de informatie kunt vinden die u nodig hebt. Als u bijvoorbeeld wilt weten welk pakket in de tracering de eerste verwijzing naar de Office 365-service die u gebruikt (zoals ' Outlook ').

Met Office 365 Outlook online als voorbeeld, begint het verkeer met een van de volgende items:
  
- DNS-standaard query en DNS-antwoord voor outlook.office365.com met overeenkomstige QueryIDs. Het is belangrijk dat u zich aanmeldt voor het aanvullen van de tijd en waar ter wereld de DNS-records van Office 365 de aanvraag voor de naamomzetting verzenden. In het ideale geval, in plaats van Midden overal ter wereld.

- Een HTTP GET-aanvraag met het statusrapport permanent verplaatst (301)

- RWS verkeer, waaronder RWS Connect-aanvragen, en antwoorden verbinden. (Dit is externe Winsock die een verbinding maakt.)

- Een TCP SYN en TCP SYN/ACK-gesprek. Veel van de instellingen in dit gesprek zijn van invloed op de prestaties.

- Vervolgens een reeks TLS: TLS-verkeer, waarin de TLS-Handshake en de TLS-certificaat uitwisseling plaatsvinden. (Onthoud dat de gegevens worden versleuteld via SSL/TLS.)

Alle onderdelen van het verkeer zijn belangrijk en verbonden, maar kleine delen van de tracering bieden vooral belangrijke informatie over het oplossen van de prestaties, zodat we de focus op die gebieden richten. Omdat we voldoende Office 365-prestaties voor de prestaties van Microsoft hebben gedaan om een top tien lijst met veelvoorkomende problemen op te stellen, richten we ons op deze problemen en hoe u deze kunt gebruiken.
  
Als u deze niet allemaal klaar hebt geïnstalleerd, kunt u in de onderstaande matrix diverse hulpmiddelen gebruiken. Waar mogelijk. Koppelingen worden geleverd met de installatiepunten. De lijst bevat veelgebruikte hulpprogramma's voor het traceren van netwerken, zoals [netmon](https://www.microsoft.com/download/details.aspx?id=4865) en [wireshark](https://www.wireshark.org/), maar u kunt ook gebruikmaken van een programma waarmee u vertrouwd bent, en waarbij u niet gewend bent om netwerkverkeer te filteren. Let op het volgende wanneer u gaat testen:
  
- *Sluit uw browsers en test met maar één browser*  als deze wordt gebruikt, wordt het totale verkeer dat u hebt vastgelegd, verminderd. De tracering minder bezet is.
- *De DNS-resolver cache op de clientcomputer leegmaken*  : Hiermee krijgt u een schone pastel wanneer u begint met het maken van uw opname voor een duidelijkere tracering.

## <a name="common-issues"></a>Veelvoorkomende problemen

Enkele veelvoorkomende problemen die kunnen optreden en hoe u ze vindt in uw netwerk spoor.

### <a name="tcp-windows-scaling"></a>Schaalbaarheid van TCP-vensters

Gevonden in de SYN-SYN/ACK. Oude of verouderde hardware maakt geen gebruik van schaalbaarheid van TCP-vensters.  Zonder de juiste schaalinstellingen voor TCP-vensters wordt de standaard 16-bits buffer in TCP-headers in milliseconden gevuld.  Het is niet mogelijk om verkeer door te sturen totdat de klant een bevestiging ontvangt dat de oorspronkelijke gegevens zijn ontvangen en vertraging veroorzaken.

#### <a name="tools"></a>Hulpprogramma's

- Netmon
- Wireshark

#### <a name="what-to-look-for"></a>Waarnaar moet worden gezocht

Zoek naar het SYN-SYN/ACK-verkeer in uw netwerk spoor.  In netmon gebruikt u een filter like  `tcp.flags.syn == 1` . Dit filter is hetzelfde in wireshark.  

![Filter in netmon of wireshark voor SYN-pakketten voor beide hulpprogramma's: TCP. Flags. SYN = = 1.](../media/4b9a12a1-c915-43c8-ac2f-a679d0435a29.PNG)

U ziet dat voor elke SYN er een nummer voor de bronpoort (SrcPort) komt dat overeenkomt met de bestemmingspoort (DstPort) van de gerelateerde bevestiging (SYN/ACK).

Als u de waarde van de schaalbaarheid van de vensters wilt zien die wordt gebruikt door uw netwerkverbinding, vouwt u eerst de SYN uit en vervolgens de desbetreffende SYN/ACK.  

![Afbeelding van het vergelijken van SrcPort met DstPort in een spoor om de tijdsdelta te bepalen.](../media/6a4ca573-0253-4fbd-93e8-92821ee1c351.png)  

### <a name="tcp-idle-time-settings"></a>Instellingen voor niet-actieve tijd TCP

Historisch, de meeste perimeternetwerken zijn geconfigureerd voor tijdelijke verbindingen, wat betekent dat onbezete verbindingen meestal worden beëindigd. Niet-actieve TCP-sessies kunnen door proxy's en firewalls worden beëindigd op meer dan 100 tot 300 seconden. Dit is problematisch voor Outlook online omdat er langdurige verbindingen worden gemaakt en gebruikt, ongeacht of deze actief zijn of niet.  

Wanneer verbindingen worden beëindigd door proxy-of firewall apparaten, wordt de client niet op de hoogte gesteld en wordt u geprobeerd Outlook online te gebruiken, maar een clientcomputer probeert herhaaldelijk de verbinding te maken voordat een nieuwe verbinding wordt gemaakt. U ziet mogelijk vastlopen van het product, prompts of vertragingen bij het laden van pagina's.

#### <a name="tools"></a>Hulpprogramma's

- Netmon
- Wireshark

#### <a name="what-to-look-for"></a>Waarnaar moet worden gezocht

Kijk in netmon naar het veld Time offset voor een retour reis. Een afronding is de tijd tussen de klant die een aanvraag verzendt naar de server en een antwoord ontvangt. Controleer de client en het uitgangspunt (ex). Client-- \> proxy) of de client naar Office 365 (client- \> Office 365). U kunt dit in veel typen pakketten zien.

Voorbeeld: het filter in netmon kan er als volgt uitzien  `.Protocol.IPv4.Address == 10.102.14.112 AND .Protocol.IPv4.Address == 10.201.114.12` , of, in wireshark,  `ip.addr == 10.102.14.112 &amp;&amp; ip.addr == 10.201.114.12` .  

> [!TIP]
> Weet u niet of het IP-adres van de tracering deel uitmaakt van uw DNS-server? Kijk op de opdrachtregel. Klik op **Start** \> **Run** \> en typ **cmd**, of druk op de **Windows-toets** \> en typ **cmd**. Typ bij de prompt  `nslookup <the IP address from the network trace>` . Als u wilt testen, gebruikt u Nslookup voor het IP-adres van uw eigen computer. Zie [Office 365-url's en IP-](https://technet.microsoft.com/library/hh373144.aspx)adresbereiken > u een lijst met IP-bereiken van Microsoft wilt weergeven.

Als er sprake is van een probleem, krijgt u een langere tijds afstand te zien, in dit geval (Outlook online), met name in TLS: TLS-pakketten waarin het doorgeven van toepassingsgegevens wordt weergegeven (bijvoorbeeld in netmon kunt u toepassingen gegevenspakketten vinden via  `.Protocol.TLS AND Description == "TLS:TLS Rec Layer-1 SSL Application Data"` ). U ziet nu een soepele voortgang tijdens de sessie. Als u tijdens het vernieuwen van Outlook online vertragingen ziet, is dit mogelijk het gevolg van een hoge weergave van de opnieuw ingestelde reset berichten.

### <a name="latencyround-trip-time"></a>Latentie/retourtijd

Latentie is een maateenheid waarmee u een lot kunt wijzigen, afhankelijk van talrijke variabelen, zoals het upgraden van verouderings apparaten, het toevoegen van een groot aantal gebruikers aan een netwerk en het percentage van de totale bandbreedte die wordt gebruikt door andere taken op een netwerkverbinding.

Op de pagina [netwerk planning en prestaties optimaliseren voor office 365](network-planning-and-performance.md) zijn bandbreedte berekenen voor Office 365 beschikbaar.  

Wilt u de snelheid van de verbinding of de bandbreedte van de provider van de verbinding waarderen? Probeer deze site (of sites zoals de site): [Speed Test officiële site](https://www.speedtest.net/)of zoek een zoekmachine naar uw favoriete zoekprogramma voor **de wachtwoordzin.**

#### <a name="tools"></a>Hulpprogramma's

- Sporen
- PsPing
- Netmon
- Wireshark

#### <a name="what-to-look-for"></a>Waarnaar moet worden gezocht

Als u de latentie van een spoor wilt bijhouden, moet u het IP-adres van de client en het IP-adres van de DNS-server in Office 365 vastleggen. Dit is bedoeld om het filteren van tracering te vereenvoudigen. Als u verbinding maakt via een proxy, hebt u het IP-adres van de client en het IP-adres van de client en het IP-adres van Office 365 nodig om het werk eenvoudiger te maken.  

Bij een ping-aanvraag die naar outlook.office365.com is verzonden, krijgt u de naam van het datacenter dat de aanvraag ontvangt, ook  *als ping geen verbinding kan maken*  om de opeenvolgende ICMP-pakketten van het handelsmerk te verzenden. Als u PsPing (een gratis tool voor downloaden) gebruikt, en specifiek de poort (443) en wellicht IPv4 (-4), krijgt u een gemiddelde retourtijd voor verzonden pakketten. Dit is geschikt voor andere Url's in Office 365-Services, zoals `psping -4 yourSite.sharepoint.com:443` . U kunt in werkelijkheid een aantal pings opgeven om een groter voorbeeld voor uw gemiddelde te bereiken, probeer dan iets te doen `psping -4 -n 20 yourSite-my.sharepoint.com:443` .  

> [!NOTE]
> PsPing verzendt geen ICMP-pakketten. Met de opdracht pingeert u TCP-pakketten via een specifieke poort, zodat u elke bewuste versie kunt gebruiken. In Office 365, dat gebruikmaakt van SSL/TLS, probeert u poort: 443 toe te voegen aan uw PsPing.

![Schermafbeelding met een ping met een onderverdeling van outlook.office365.com en een PSPing met de 443 op dezelfde manier, maar het rapporteren van een gemiddelde RETOURwaarde van 6,5 ms.](../media/c64339f2-2c96-45b8-b168-c2a060430266.PNG)

Als u de pagina met de traagste uitvoering van Office 365 hebt geladen tijdens het uitvoeren van een netwerktracering, moet u een netmon-of wireshark-tracering filteren `DNS` . Dit is een van de IPs waarnaar we op zoek zijn.  

Dit zijn de stappen die u moet uitvoeren om uw netmon te filteren om het IP-adres te achterhalen (en de DNS-latentie te bekijken). In dit voorbeeld wordt outlook.office365.com gebruikt, maar de URL van een SharePoint Online-Tenant kan ook worden gebruikt (bijvoorbeeld hithere.sharepoint.com).  

1. Ping de URL `ping outlook.office365.com` en noteer de naam en het IP-adres van de DNS-server waarop de opdracht ping is verzonden.
2. Netwerktracering Hiermee opent u de pagina of de actie die het prestatieprobleem oplevert, of als u een hoge latentie ziet op de ping, zichzelf.
3. Open de tracering in netmon en filter for DNS (dit filter werkt ook in wireshark, maar is afhankelijk van het hoofdlettergebruik `-- dns` ). Aangezien u de naam van de DNS-server weet van uw ping, kunt u ook sneller filteren in netmon, zoals dit: `DNS AND ContainsBin(FrameData, ASCII, "namnorthwest")` , wat er als volgt uitziet in wireshark DNS en frame bevat ' namnorthwest '.<br/>Open het antwoordpakket en klik in het venster met het **frame Details** van Netmon op **DNS** om meer informatie weer te geven. In de DNS-gegevens wordt het IP-adres van de DNS-server weergeven, waarbij de aanvraag is gevonden in Office 365. U hebt dit IP-adres nodig voor de volgende stap (het PsPing-hulpprogramma). Verwijder het filter, klik met de rechtermuisknop op het DNS-antwoord in Netmon (**kader samenvatting** \> **vindt u discussie** \> **-DNS**) om de DNS-query en het antwoord naast elkaar te bekijken.
4. In netmon ziet u ook de kolom Time offset tussen de DNS-aanvraag en het antwoord. In de volgende stap is het [PsPing](https://technet.microsoft.com/sysinternals/jj729731.aspx) -hulpprogramma eenvoudig te installeren en te gebruiken, beide omdat ICMP vaak wordt geblokkeerd op firewalls en omdat PsPing op een elegante manier de latentie in milliseconden registreert. PsPing voltooit een TCP-verbinding met een adres en poort (in onze zaak open poort 443).
5. Installeer PsPing.
6. Open een opdrachtprompt (Start \> \> type cmd of Windows-toets \> type cmd) en wijzig de adreslijst in de directory waarin u PsPing hebt geïnstalleerd om de opdracht PsPing uit te voeren. In mijn voorbeelden ziet u de map ' perf ' in de hoofdmap van C. U kunt hetzelfde doen voor snelle toegang.
7. Typ de opdracht zodat u de PsPing kunt aanwijzen met het IP-adres van de Office 365-DNS-server via uw eerder netmon-tracering, waaronder het poortnummer, zoals `psping -n 20 132.245.24.82:445` . U krijgt een steekproef van 20 pings en gemiddelde de latentie wanneer PsPing stopt.

Als u Office 365 via een proxyserver gaat, zijn de stappen iets anders. U verstuurt eerst de PsPing naar uw proxyserver voor een gemiddelde latentie waarde in milliseconden om te worden gecommuniceerd, en vervolgens uit te voeren en vervolgens PsPing uit te voeren op de proxy of op een computer met een rechtstreekse Internet verbinding om de ontbrekende waarde te verkrijgen (de ene naar Office 365 en deze terug).  

Als u ervoor kiest om PsPing uit te voeren vanuit de proxy, hebt u twee milliseconde-waarden: client computer naar proxyserver of uitgangspunt en proxyserver naar Office 365. En u bent klaar. Ook waarden opnemen.  

Als u PsPing uitvoert op een andere clientcomputer die een directe verbinding met internet heeft, dat wil zeggen, zonder proxy, hebt u twee milliseconde-waarden: clientcomputer met een proxyserver of een uitgangspunt, en de clientcomputer naar Office 365. In dit geval trekt u de waarde van clientcomputer naar proxyserver of uitgangspunt af van de waarde van clientcomputer naar Office 365, en hebt u de RTT-nummers van de clientcomputer naar de proxyserver of het uitgangspunt en van de proxyserver of het uitgangspunt naar Office 365.

Als u echter een clientcomputer kunt vinden op de beïnvloede locatie die rechtstreeks verbonden is of de proxy omzeilt, kunt u ervoor kiezen om te zien of het probleem zich hierin voordoet, en hoe u het probleem later kunt testen.

De latentie, zoals gezien in een netmon-tracering, kan deze extra milliseconden optellen wanneer ze genoeg zijn in een bepaalde sessie.  

![Algemene latentie in netmon, met de kolom netmon standaardtijd Delta, toegevoegd aan het frame overzicht.](../media/7ad17380-8527-4bc2-9b9b-6310cf19ba6b.PNG)

> [!NOTE]
> Uw IP-adres kan afwijken van de IPs die hier worden weergegeven, bijvoorbeeld: uw ping kan iets retourneren zoals 157.56.0.0/16 of een vergelijkbaar bereik. Zie [url's en IP-](https://technet.microsoft.com/library/hh373144.aspx)adresbereiken voor Office 365 voor een lijst met bereiken die worden gebruikt door Office 365.

Vergeet niet alle knooppunten uit te vouwen (er is een knop bovenaan) als u bijvoorbeeld wilt zoeken naar 132,245.

### <a name="proxy-authentication"></a>Proxy verificatie

Dit is alleen van toepassing als u een proxyserver gebruikt. Zo niet, dan kunt u deze stappen overslaan. Bij een juiste werking van de proxyverificatie moet u zich op de juiste tijd in milliseconden plaatsen. Tijdens piek gebruiks perioden zijn de prestaties van de piek gebruiksperiode niet te zien.  

Als proxy-verificatie is ingeschakeld, moet u de volgende keer dat u een nieuwe TCP-verbinding met Office 365 maakt voor informatie, moet u een verificatieproces achter de schermen passeren. Bijvoorbeeld, wanneer u overstapt van agenda naar E-mail in Outlook online, wordt u geverifieerd. In SharePoint Online, als op een pagina media of gegevens van meerdere sites en locaties worden weergegeven, wordt u geverifieerd voor elke andere TCP-verbinding die nodig is om de gegevens weer te geven.  

In Outlook online ondervindt u mogelijk vertragingen wanneer u schakelt tussen de agenda en uw postvak, of op langzame pagina wordt geladen in SharePoint Online. Er zijn echter andere problemen die hier niet worden vermeld.

Proxyverificatie is een instelling op de proxyserver voor de uitgang. Als dit wordt veroorzaakt door een prestatieprobleem met Office 365, moet u uw netwerkteam raadplegen.  

#### <a name="tools"></a>Hulpprogramma's

- Netmon
- Wireshark

#### <a name="what-to-look-for"></a>Waarnaar moet worden gezocht

Er gebeurt een proxy verificatie wanneer een nieuwe TCP-sessie moet worden uitgevoerd, vaak om bestanden of informatie van de server aan te vragen of informatie te verstrekken. U kunt bijvoorbeeld proxyverificatie zien rond HTTP GET-of HTTP POST-aanvragen. Als u wilt dat de frames worden weergegeven waar u aanvragen in uw Trace verifieert, voegt u de kolom ' NTLMSSP Summary ' toe aan netmon en filter  `.property.NTLMSSPSummary` . Als u wilt zien hoe lang de authenticatie duurt, voegt u de kolom time Delta toe.

Een kolom toevoegen aan netmon:

1. Klik met de rechtermuisknop op een kolom, bijvoorbeeld **Description**.
2. Klik op **kolommen kiezen**.
3. Ga naar _NTLMSSP Summary_ en _time Delta_ in de lijst en klik op **add**.
4. Beweeg de nieuwe kolommen naar de juiste plaats of achter de kolom _Beschrijving_ , zodat u ze naast elkaar kunt lezen.
5. Klik op **OK**.

Ook als u de kolom niet toevoegt, werkt het netmon-filter. Het probleem is nu veel eenvoudiger als u kunt zien welke verificatiefase u gebruikt.

Wanneer u op zoek bent naar exemplaren van proxy verificatie, moet u de bestudeering van alle frames met een NTLM-uitdaging of een verificatiebericht presteren. Klik zo nodig met de rechtermuisknop op het specifieke gedeelte van het verkeer en zoek de TCP-conversaties \> . Let op de tijds Delta waarden in deze gesprekken.

![Netmon-spoor met proxyverificatie, gefilterd op gesprek.](../media/b640f176-0a52-4bbb-972e-60fb3d6aece2.PNG)

Een vertraging van de vier seconden in de proxyverificatie zoals gezien in wireshark. De kolom **time Delta van vorige weergegeven frame** werd gemaakt door met de rechtermuisknop te klikken op het veld met dezelfde naam in de frame Details en vervolgens toevoegen als kolom te selecteren.  <br/> ![In wireshark kan de kolom time Delta van vorige weergegeven frame worden gemaakt door met de rechtermuisknop op het veld met dezelfde naam in de frame details te klikken en toevoegen als kolom te selecteren.](../media/f5b7bde4-8067-4ee0-bc7f-e9062ce1ba6f.PNG)

### <a name="dns-performance"></a>DNS-prestaties

Naamresolutie werkt het best en het snelst wanneer het zo dicht mogelijk plaatsvindt bij het land waar u het product van de klant onderneemt.

Als de DNS-naamresolutie in het buitenland plaatsvindt, kan dit seconden toevoegen aan het laden van pagina's. In het ideale geval is de naamomzetting onder 100 MS. Zo niet, dan moet u verder onderzoek doen.

> [!TIP]
> Weet u niet hoe client connectiviteit werkt in Office 365? Bekijk de documentatie voor de client connectiviteit [hier](https://technet.microsoft.com/library/dn741250.aspx).

#### <a name="tools"></a>Hulpprogramma's

- Netmon
- Wireshark
- PsPing

#### <a name="what-to-look-for"></a>Waarnaar moet worden gezocht

Het analyseren van de prestaties van DNS is meestal een andere taak voor een netwerktracering. PsPing is echter ook handig bij een beslissing in, of uit een mogelijke oorzaak.

DNS-verkeer is gebaseerd op TCP-en UDP-aanvragen en-antwoorden worden duidelijk gemarkeerd met een ID die helpt bij het vergelijken van een specifieke aanvraag met een specifiek antwoord. Als u bijvoorbeeld een netwerknaam of URL op een webpagina gebruikt, ziet u DNS-verkeer. Dit is een regel van de duim, met uitzondering van het overbrengen van zones, via UDP.

In zowel netmon als wireshark is het meest eenvoudige filter waarmee u eenvoudig kunt werken met DNS-verkeer `dns` . Zorg ervoor dat u kleine letters gebruikt wanneer u het filter opgeeft. Vergeet niet om uw DNS-resolver cache leeg te maken voordat u het probleem op de clientcomputer opnieuw maakt. Als u bijvoorbeeld een langzame SharePoint Online-pagina laadt voor de startpagina, moet u alle browsers sluiten, een nieuwe browser openen, de start tracering afbreken, uw DNS-resolver cache leegmaken en naar de SharePoint Online-site bladeren. Wanneer de hele pagina wordt opgelost, stopt u de tracering en slaat u deze op.

![Een eenvoudig filter voor DNS in netmon is DNS.](../media/1bebc118-ca13-45f3-803f-ab73e7af401d.png)

U wilt het tijdstip waarnaar u wilt kijken. Het kan handig zijn om de kolom **time Delta** toe te voegen aan netmon, zodat u deze stappen kunt uitvoeren:

1. Klik met de rechtermuisknop op een kolom, bijvoorbeeld **Description**.
2. Klik op **kolommen kiezen**.
3. Zoek _tijds Delta_ in de lijst en klik op **toevoegen**.
4. Beweeg de nieuwe kolom naar de kolom Beschrijving voor of achter de kolom _Beschrijving_ , zodat u ze naast elkaar kunt lezen.
5. Klik op **OK**.

Als u een belangrijke query vindt, kunt u deze isoleren door met de rechtermuisknop op de query te klikken in het venster Details van frame en vervolgens te kiezen voor **gesprekken** \> **DNS**. Zoals u ziet, gaat u naar het deelvenster netwerk gesprekken en gaat u naar de specifieke conversatie in het logboek van UDP-verkeer.

![Een netmon-tracering van Outlook online die wordt gefilterd door DNS, en het gebruik van gesprekken zoeken en DNS gebruiken om de resultaten te verfijnen.](../media/763cf20e-7b48-4a37-9449-c9978cfe118b.PNG)

In wireshark kunt u een kolom voor DNS-tijd maken. Neem uw trace (of open een spoor) in wireshark en filter op een `dns` of meer handige,  `dns.time` . Klik op een willekeurige DNS-query en Breid in het deelvenster met details de  `Domain Name System (response)` Details uit. U ziet een veld voor tijd (bijvoorbeeld `[Time: 0.001111100 seconds]` . Klik met de rechtermuisknop op deze tijd en selecteer **toepassen als kolom**. Hiermee krijgt u een kolom **tijd** waarmee u de tracering sneller kunt sorteren. Klik op de nieuwe kolom om op de aflopende waarden te sorteren, zodat u kunt zien welke DNS-oproepen het langst voor u zijn.

[Een Browse van SharePoint Online in wireshark gefilterd op DNS. time (in kleine letters), waarbij het tijdstip van de gegevens in een kolom is gemaakt en oplopend wordt gesorteerd.](../media/1439dcc2-12ff-4ee2-9ef3-1484cf79c384.PNG)

Als u meer controle wilt doen over de DNS-oplossingstijd, probeert u een PsPing met de DNS-poort die door TCP wordt gebruikt (bijvoorbeeld  `psping <IP address of DNS server>:53` ). Krijgt u nog steeds een prestatieprobleem? Als dit het geval is, is het probleem waarschijnlijk een groter netwerkprobleem dan een probleem met de specifieke DNS-toepassing die u nog moet oplossen. Ook op de hoogte van een ping naar outlook.office365.com krijgt u het volgende te zien waar de DNS-naamomzetting voor Outlook online wordt uitgevoerd (bijvoorbeeld outlook-namnorthwest.office365.com).

Als het probleem er zo uitziet als DNS specifiek is, moet u contact opnemen met uw IT-afdeling voor de DNS-configuraties en DNS-doorstuurservers om dit probleem verder te onderzoeken.

### <a name="proxy-scalability"></a>Schaalbaarheid van de proxy

Services zoals Outlook online in Office 365 verlenen clients meerdere verbindingen voor de lange termijn. Elke gebruiker mag daarom meerdere verbindingen gebruiken die langer mee moeten gaan.  

#### <a name="tools"></a>Hulpprogramma's

Wiskundig  

#### <a name="what-to-look-for"></a>Waarnaar moet worden gezocht

Er is geen specifiek netwerk spoor of hulpprogramma voor probleemoplossing. In plaats daarvan wordt er rekening gehouden met beperkingen en andere variabelen voor de bandbreedte.  

### <a name="tcp-max-segment-size"></a>Maximale segment grootte TCP

Gevonden in de SYN-SYN/ACK.  Voer de volgende handelingen uit om de prestaties van het netwerk te controleren die u hebt genomen om ervoor te zorgen dat TCP-pakketten zodanig zijn geconfigureerd dat ze de maximale hoeveelheid gegevens kunnen meenemen.

Het doel is een MSS van 1460 bytes voor de overdracht van gegevens. Als u zich achter een proxy bevindt, of als u een NAT gebruikt, moet u deze test uitvoeren van client naar proxy/afleiden/NAT, en van proxy/uitgang/NAT naar Office 365 voor de beste resultaten. Dit zijn verschillende TCP-sessies.

#### <a name="tools"></a>Hulpprogramma's

Netmon

#### <a name="what-to-look-for"></a>Waarnaar moet worden gezocht

Maximale segment grootte TCP (MSS) is een andere parameter van de ThreeD Handshake in uw netwerktracering, wat betekent dat u de gegevens kunt vinden die u nodig hebt in het SYN-SYN/ACK-pakket. MSS is echt heel gemakkelijk te zien.

Open de prestatie netwerktracering die u hebt en zoek de verbinding waarop u bent of die het prestatieprobleem vertoont.

> [!NOTE]
> Als u op zoek bent naar een tracering en het verkeer moet vinden dat relevant is voor uw gesprek, kunt u filteren op het IP-adres van de client of het IP-adres of het IP-adres van de proxyserver of uitgangspunt. Ga rechtstreeks naar de URL die u wilt testen voor het IP-adres van Office 365 in de tracering en filtreer de URL.

Bekijkt u de beschikbaarheid van de tweede hand? Gebruik filters om uzelf te berichten. Voer in netmon een zoekopdracht uit op basis van de URL, bijvoorbeeld `Containsbin(framedata, ascii, "sphybridExample")` het framenummer.

In wireshark gebruikt u bijvoorbeeld iets  `frame contains "sphybridExample"` . Als u merkt dat u het externe Winsock-verkeer (RWS) hebt gevonden (het bericht kan worden weergegeven als [PSH, ACK] in wireshark), moet u nadenken dat RWS Connects worden weergegeven na vóór de juiste SYN-SYN/Ack's, zoals eerder is beschreven.

U kunt op dit moment het framenummer opnemen, het filter weghalen, op **alle verkeer** in het venster netwerk conversaties in netmon klikken om de dichtstbijzijnde SYN te zien.

Als u op het moment van de tracering geen gegevens van het IP-adres hebt ontvangen, kunt u deze als volgt weergeven in de tracering (een gedeelte van het voor `sphybridExample-my.sharepoint.com` beeld).

Zoek de verbinding in de trace waarin u geïnteresseerd bent. U kunt dit doen door de trace te scannen, te filteren op IP-adressen of door specifieke gespreks-Id's te selecteren met het venster Netwerk gesprekken in Netmon. Als u het SYN-pakket hebt gevonden, vouwt u TCP (in netmon) of Transmission Control Protocol (in wireshark) uit in het deelvenster frame Details. Vouw TCP options en Maxsegmentsize uit. Zoek het bijbehorende SYN-ACK-frame en vouw TCP options en Maxsegmentsize uit. De kleinste van de twee waarden is de maximale segment grootte. In deze afbeelding maak ik gebruik van de ingebouwde kolom in netmon genaamd TCP Troubleshoot.  

![Netwerk spoor gefilterd in netmon met behulp van de ingebouwde kolommen.](../media/e073df13-71f8-497a-83b4-bb9f70bd9833.PNG)

De ingebouwde kolom bevindt zich boven aan het deelvenster **Details van frame** . (Als u wilt teruggaan naar de normale weergave, klikt u nogmaals op **kolommen** en vervolgens op **tijd zone**.)

![Waar vind ik de vervolgkeuzelijst kolommen voor de optie problemen met TCP oplossen (boven aan het frame-overzicht).](../media/64fd4baa-a872-4f07-b959-752d7d37fd62.PNG)

Dit is een gefilterde tracering in wireshark. Er is een filter specifiek voor de MSS-waarde ( `tcp.options.mss` ). De frames van een SYN, SYN/ACK, ACK-hand Shake zijn onder aan de details van het frame (dus frame 47 ACK, koppelingen naar de 46 SYN/ACK, koppelingen naar 43 SYN) om dit type werk makkelijker te maken.

![Spoor gefilterd in wireshark door TCP. options. MSS voor maximale segment grootte (MSS).](../media/51e278db-801b-48bc-9b68-87cf92f03fd6.PNG)

Als u **selectieve bevestiging** (volgend onderwerp in deze matrix) wilt controleren, sluit u het traceren niet.

### <a name="selective-acknowledgment"></a>Selectieve bevestiging

Gevonden in de SYN-SYN/ACK. Moet worden gerapporteerd als toegestaan in zowel SYN als SYN/ACK. Met behulp van selectieve bevestiging kunt u gegevens soepel opnieuw verzenden wanneer een pakket of pakketten verloren gaan. Apparaten kunnen deze functie uitschakelen, wat tot prestatieproblemen kan leiden.

Als u zich achter een proxy bevindt, of als u een NAT gebruikt, moet u deze test uitvoeren van client naar proxy/afleiden/NAT, en van proxy/uitgang/NAT naar Office 365 voor de beste resultaten. Dit zijn verschillende TCP-sessies.

#### <a name="tools"></a>Hulpprogramma's

Netmon

#### <a name="what-to-look-for"></a>Waarnaar moet worden gezocht

Selected acknowledgment (zakken) is een andere parameter in de SYN-SYN/ACK-handshake. U kunt de tracering voor SYN-SYN/ACK op tal van manieren filteren.

Zoek de verbinding in de trace waarin u geïnteresseerd bent door de trace te scannen, te filteren op IP-adressen of door op een gespreks-ID te klikken via het venster Network Conversations in Netmon. Als u het SYN-pakket hebt gevonden, vouwt u TCP in netmon of Transmission Control Protocol in wireshark in de sectie Details van frame. Vouw TCP options en vervolgens een zakken uit. Zoek het bijbehorende SYN-ACK-frame en vouw TCP options en het veld zakken uit. Maak de zakken van een bepaalde zak toegestaan in zowel SYN als SYN/ACK. Dit zijn de waarden voor zakken zoals weergegeven in zowel netmon als wireshark.

![Selectieve bevestiging (zakken) in netmon als gevolg van TCP. Flags. SYN = = 1.](../media/216f556f-5031-4ed2-b066-a0d9b3251fa2.PNG)

![ZAKKEN zoals gezien in wireshark met het filter TCP. Flags. SYN = = 1.](../media/0a6e26e5-43dc-403b-adc9-3349a55f4e4b.PNG)

### <a name="dns-geolocation"></a>DNS-geolocatie

Waar in de wereld Office 365 uw DNS-oproep probeert op te lossen, invloed hebben op uw verbindingssnelheid.

Als u in Outlook online de eerste DNS-zoekopdracht hebt voltooid, wordt de locatie van die DNS gebruikt om verbinding te maken met uw dichtstbijzijnde datacenter. U wordt verbonden met een CERTIFICERINGs server van Outlook online waarop het backbone-netwerk wordt gebruikt om verbinding te maken met het datacenter (dC) waar de gegevens zijn opgeslagen. Dit gaat sneller.

Wanneer u SharePoint Online gebruikt, wordt een gebruiker in het buitenland doorgestuurd naar het actieve datacenter: dat is de dC waarvan de locatie gebruikmaakt van de startpagina van de SPO-Tenant (zodat een dC in de Verenigde Staten kan een dC in de Verenigde Staten voor de gebruiker als de gebruiker wordt uitgevoerd).

Lync Online bevat in meerdere Dc's tegelijkertijd actieve knooppunten. Wanneer aanvragen voor Lync online-exemplaren worden verzonden, bepaalt Microsoft de locatie van de wereld waar de aanvraag vandaan komt en retourneert deze IP-adressen uit de dichtstbijzijnde regionale dC waar Lync online actief is.

> [!TIP]
> Wilt u meer weten over hoe clients verbinding maken met Office 365? Bekijk het artikel over de [client verbinding](https://technet.microsoft.com/library/dn741250.aspx) (en de bijbehorende handige afbeeldingen).

#### <a name="tools"></a>Hulpprogramma's

- Sporen
- PsPing

#### <a name="what-to-look-for"></a>Waarnaar moet worden gezocht

Aanvragen voor de naamomzetting van de DNS-servers van de client naar de DNS-servers van Microsoft behoren meestal tot het IP-adres van een Regional datacenter (dC). Wat betekent dit voor u? Als u in de Verenigde Staten een aanvraag doet voor de Bangalore, India, maar u in de Verenigde Staten een aanvraag voor Outlook online doet, kunnen de DNS-servers van Microsoft de IP-adressen aan databases in de Verenigde Staten--een regionaal datacenter leveren. Als u e-mail nodig hebt in Outlook, worden deze gegevens over het snelle backbone-netwerk van Microsoft tussen de datacenters verzonden.

DNS werkt snel wanneer de naamomzetting op de locatie van de gebruiker is voltooid. Als u in Europa bent, gaat u naar een Microsoft DNS in Europa en (IDEA) transactie met een datacenter in Europa. De prestaties van een client in Europe gaan naar DNS en een datacenter in Amerika gaat langzamer.

Voer het hulpprogramma ping uit voor outlook.office365.com om te bepalen waar de wereld uw DNS-aanvraag naar wordt verzonden. In Europa ziet u een antwoord van iets als outlook-emeawest.office365.com. In het Amerikaans-Amerika verwachten iets als outlook-namnorthwest.office365.com.

Open de opdrachtprompt op de clientcomputer (via Start \> \> opdracht cmd of Windows \> -toets cmd). Typ ping outlook.office365.com en druk op ENTER. Vergeet niet dat u-4 wilt opgeven voor ping via IPv4. Het kan zijn dat u geen antwoord hebt ontvangen van de ICMP-pakketten, maar u moet wel de naam zien van de DNS waarnaar de aanvraag is doorgestuurd. Als u de latentie nummers voor deze verbinding wilt weergeven, voert u PsPing naar het IP-adres van de server die het resultaat is van ping.  

![Ping van outlook.office365.com met de resolutie in Outlook-namnorthwest.](../media/06c944d5-6159-43ec-aa31-757770695e8b.PNG)

![PSPing naar het IP-adres geretourneerd door de ping naar outlook.office365.com met een latentie van gemiddeld 28 milliseconden.](../media/f2b25a75-1a87-4479-b8a7-fa4375683507.PNG)

### <a name="office-365-application-troubleshooting"></a>Problemen met Office 365-toepassing oplossen

#### <a name="tools"></a>Hulpprogramma's

- Netmon
- HTTPWatch
- F12-console in de browser

We bieden geen hulpmiddelen die worden gebruikt in toepassingsspecifieke probleemoplossing in dit netwerkspecifieke artikel. U vindt dan bronnen die u [op deze pagina](https://support.office.com/article/Network-planning-and-performance-tuning-for-Office-365-e5f1228c-da3c-4654-bf16-d163daee8848) *kunt* gebruiken.

## <a name="related-topics"></a>Verwante onderwerpen

[Office 365-eindpunten beheren](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Veelgestelde vragen over Office 365-eindpunten](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
