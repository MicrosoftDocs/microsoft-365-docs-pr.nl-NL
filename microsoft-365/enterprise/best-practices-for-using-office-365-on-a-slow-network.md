---
title: Aanbevolen procedures voor het gebruik van Office 365 op een traag netwerk
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/29/2016
audience: End User
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
search.appverid:
- MET150
- MET150
- MOP150
- MEW150
- BCS160
ms.assetid: fd16c8d2-4799-4c39-8fd7-045f06640166
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: In dit artikel wordt u begeleid bij de aanbevolen procedures die u kunt gebruiken voor het gebruik van Office 365 op een traag netwerk.
ms.openlocfilehash: a0a15191fa0240f24cecc5e595de9a259cacc9f9
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689360"
---
# <a name="best-practices-for-using-office-365-on-a-slow-network"></a>Aanbevolen procedures voor het gebruik van Office 365 op een traag netwerk

Zou het niet mooi zijn als uw Internet verbinding altijd snel en niet beschikbaar is? Misschien komt dat de dag. Ondertussen zijn er praktische dingen die u kunt doen om een balky-netwerk te omzeilen en nog steeds uw dagelijkse werk gedaan te krijgen. Hoewel Office 365 een cloudservice is, biedt Office ook tal van manieren waarop u offline kunt werken met uw inhoud en de wijzigingen vloeiend wilt houden. Daarnaast is het soms efficiënter om met inhoud offline te werken omdat toepassingen sneller werken en de gebruikersinterface meer tijd in bevindt. Dit is de optie: Office 365 biedt u de beste van beide werelden. U kunt dit als volgt doen. 
  
> [!TIP]
> Wilt u zien hoe traag (of snelle) de netwerkverbinding is? Probeer de [ OOKLA-snelheids test ](https://www.speedtest.net/) of de app voor het testen van de [netwerksnelheid](https://www.windowsphone.com/store/app/network-speed-test/9b9ae06b-2961-41ef-987d-b09567cffe70). 

## <a name="why-is-my-network-so-slow"></a>Waarom is mijn netwerk zo traag?

Hoewel u geen controle hebt over de prestaties van het netwerk, is het handig als u weet wat er achter de schermen gebeurt. Het internet is enorm ingewikkeld, maar er zijn een paar concepten die u kunnen helpen de situatie veel beter te begrijpen. Als u de best practices in dit artikel volgt, kunt u problemen met de prestaties verhelpen en minder frustraties.
  
**Belangrijke factoren die van invloed zijn op de prestaties van het netwerk**

![Netwerk Prestatiefactoren](../media/62a94322-3f1a-4d2d-bbdc-2aa0722d2d96.png)
  
 **Bandbreedte en latentie** De twee belangrijkste maateenheden van netwerkprestaties zijn bandbreedte en latentie: 
  
- Bandbreedte is de snelheid van doorvoer in bits per seconde. Groter is beter. Bandbreedte zoals een waterleiding. Hoe groter de sluis, hoe meer water u kunt plaatsen.

- Latentie is de tijd die nodig is om inhoud van een server of service naar uw apparaat te halen en wordt gemeten in milliseconden. Sneller is een betere ervaring. Latentie kan worden veroorzaakt door een aantal factoren, waaronder lage bandbreedte, een verspreide verbinding of een verzendtijd.

 **Veelvoorkomende problemen** Naast de bandbreedte en latentie, hebben andere problemen invloed op de netwerkprestaties en zijn vaak niet te laat. Netwerkprestaties kunnen schommelen op basis van de tijd van de dag of uw fysieke locatie. Het netwerk kan worden verstopt als bepaalde gebeurtenissen plaatsvinden, wat de toepassing van het internet is, zoals een natuurlijke ramp of een grote openbare gebeurtenis. De grootte en complexiteit van de pagina die wordt geladen, en het aantal en de grootte van de overgebrachte bestanden zijn direct van invloed op de prestaties. Een WiFi-verbinding kan tijdelijk worden afgebroken: u kunt bijvoorbeeld een grote vergadering met duizend tallies navragen door iedereen tegelijk te Tweet. 
  
 **Aandachtspunten voor een satelliet netwerk** Een satelliet netwerk is nuttig wanneer een terrestrisch netwerk niet haalbaar is, zoals het land dat of het land of een opleverings schip of een extern wetenschappelijk gebied. Deze netwerken zijn afhankelijk van de beweringen in een geosynchrone baan 22.000 kilometers van de vergeleken. Een overdracht bevat echter wel een vertraging over 90.000 kilometers, zodat een satelliet netwerk een vertraging heeft (500 MS of meer) dan een terrestrisch netwerk (20 tot 50ms). Onder de voorwaarden bedacht u deze latentie mogelijk niet, maar voor het downloaden van grote bestanden, streaming Video's en het spelen van games gaat u waarschijnlijk. Een ander probleem is "regen vervagen", waarbij met zware weer, zoals thunderstorms en Blizzards, het versturen van de satelliet tijdelijk kan worden onderbroken.
  
## <a name="are-you-sure-its-the-network"></a>Weet u zeker dat het netwerk is?

Wanneer u prestatieproblemen ondervindt, controleert u eerst of het apparaat niet de hoofdoorzaak is van het probleem. Er zijn twee dingen die u kunt doen om grote verbeteringen aan te brengen:
  
- Controleer of het apparaat goed werkt en of zich geen malware op uw computer bevindt.

- Koop meer geheugen, indien mogelijk. Het toevoegen van geheugen is de eenvoudigste en vaakste manier om de prestaties van uw apparaat te verbeteren. Dit is vooral handig als u werkt met grote bestanden en Video's.

Zie [ Windows prestatie en onderhoud ](https://windows.microsoft.com/windows/performance-maintenance-help#performance-maintenance-help) en [Tips voor het verbeteren van de prestaties van uw computer in Windows 10](https://support.microsoft.com/en-za/help/4002019/windows-10-improve-pc-performance)voor meer informatie.

## <a name="best-practices-for-using-your-browser"></a>Aanbevolen procedures voor het gebruik van uw browser

Uw browser is de gateway naar Office 365, zodat de invloed kan zijn op de prestaties, vooral met de tijd die het duurt om een pagina te laden en hoe vaak u de reis rondt naar de Office 365-service.
  
 **Browsers in het algemeen**
  
Hier volgen enkele suggesties voor browsers in het algemeen:
  
- Schakel browser invoegtoepassingen uit die mogelijk van invloed zijn op de prestaties of die u niet echt nodig hebt.

- Verhoog de cachegrootte voor uw tijdelijke internetbestanden.

- Als u zich hebt aangemeld bij uw werk-of schoolaccount, moet u het browservenster voor de hele dag geopend houden. U kunt andere tabbladen en vensters openen zonder u aan te melden. Als u zich wilt aanmelden bij een ander account, gebruikt u de functie private Browse. 

- Houd de pagina's eenmaal geopend en open ze met behulp van tabs. U kunt eenvoudig tussen tabbladen navigeren en de pagina later op de dag gebruiken. Vernieuw een pagina alleen als u de meest recente gegevens op de pagina hebt.

- Als het te lang duurt voor een pagina wordt geopend, stopt u met het downloaden van de pagina (druk op ESC) en vernieuwt u de pagina (druk op F5). 

-  Beperk indien mogelijk rond Reiss naar Office 365. In plaats van een lijst of bibliotheek te gebruiken, kunt u bijvoorbeeld zoeken naar bestanden in een grote bibliotheek en filteren in een lijst om direct naar de gewenste resultaten te gaan. U kunt nu weergaven maken waarmee de laadtijd van pagina's wordt geminimaliseerd. Zie [grote lijsten en bibliotheken beheren in Office 365](https://support.office.com/article/b4038448-ec0e-49b7-b853-679d3d8fb784#BKMK_PAGES)voor meer informatie.

- Als de prestaties van de video slecht zijn, kunt u de video mogelijk downloaden en deze op uw apparaat bekijken. Mogelijk is er een downloadkoppeling beschikbaar, of u kunt met de rechtermuisknop op de koppeling naar de video klikken en **doel opslaan als**selecteren.

 **Specifiek voor browsers**
  
Hier volgen enkele suggesties voor uw specifieke browser:
  
- **Internet Explorer** Voer een upgrade uit naar Internet Explorer versie 11 of hoger voor aanzienlijke prestatieverbeteringen ten opzichte van eerdere versies. Zie [Troubleshooting Guide voor Internet Explorer](https://support.microsoft.com/help/2437121/troubleshooting-guide-for-internet-explorer-when-you-access-office-365)voor meer informatie.

- **Firefox** Zie voor meer informatie [Firefox traag of niet meer werken](https://support.mozilla.org/products/firefox/fix-problems/slowness-or-hanging).

- **Safari** Zie [Apple Safari](https://www.apple.com/safari/)voor meer informatie.

- **Chrome** Voor meer informatie raadpleegt u de [Help van Chrome](https://support.google.com/chrome/?hl=en).
  
## <a name="best-practices-for-using-outlook-and-outlook-web-app"></a>Aanbevolen procedures voor het gebruik van Outlook en Outlook Web app

Het lezen, schrijven en organiseren van e-mailberichten is een groot deel van de dag van iedereen. Outlook en Outlook Web app (OWA) bieden offline ondersteuning. Het gebruik van een e-mail-app op uw smartphone is een handige alternatief. Gebruik de volgende opties die het beste aansluiten op uw behoeften:
  
- Voer een upgrade uit naar de nieuwste versie van Outlook voor belangrijke prestatieverbeteringen ten opzichte van eerdere versies. 

-  Met Outlook Web App kunt u offline berichten, contactpersonen en agenda-items maken die worden geüpload wanneer OWA verbinding kan maken met Office 365. Zie [Outlook Web app offline gebruiken](https://support.office.com/article/3214839c-0604-4162-8a97-6856b4c27b36)voor meer informatie over het instellen en gebruiken van OWA in de offlinemodus.

- In Outlook kunt u werken in de cachemodus, zodat automatisch verbinding maakt wanneer dit mogelijk is. U kunt in Outlook uw gehele postvak of slechts een gedeelte hiervan downloaden. Zie [Exchange-modus met cache inschakelen](https://support.office.com/article/7885af08-9a60-4ec3-850a-e221c1ed0c1c) en [offline werken in Outlook](https://support.office.com/article/f3a1251c-6dd5-4208-aef9-7c8c9522d633)voor meer informatie.

- Outlook biedt ook een offlinemodus. Als u dit wilt gebruiken, moet u eerst de cachemodus instellen zodat gegevens van uw account naar uw computer worden gekopieerd. In de offlinemodus probeert Outlook verbinding te maken met behulp van de instellingen voor verzenden en ontvangen, of wanneer u deze handmatig instelt voor online werken. Zie [offline werken om te voorkomen dat dataverbinding kostprijzen kost](https://support.office.com/article/827fe51f-5609-4062-82b4-3578057f9282), [Wijzig instellingen voor verzenden en ontvangen wanneer u offline werkt](https://support.office.com/article/f681ec10-cb14-40cb-8709-1909a13c304a)en [schakelt van offline werken naar online](https://support.office.com/article/2460e4a8-16c7-47fc-b204-b1549275aac9).

- Als u een smartphone hebt, kunt u deze gebruiken om uw e-mail en agenda te sortering via het netwerk van uw telefoonprovider.

> [!NOTE]
> Hier volgen enkele richtlijnen voor het gebruik van Outlook of OWA. Als schijfruimte geen probleem op uw apparaat is, heeft Outlook een volledige reeks functies en geschikt voor u mogelijk. Als u een probleem op uw apparaat kunt oplossen, kunt u het beste OWA gebruiken met een subset van functies, maar het is ook geschikt voor de online situatie. U kunt natuurlijk natuurlijk ook gebruiken omdat ze samen samenwerken.
  
## <a name="best-practices-for-using-onedrive-for-business"></a>Aanbevolen procedures voor het gebruik van OneDrive voor bedrijven

OneDrive voor bedrijven is zo ontworpen dat ze online en offline werken met uw bestanden. Wanneer u deze hebt ingesteld, wordt de synchronisatie van de wijzigingen automatisch en op een willekeurige plaats automatisch uitgevoerd wanneer u deze maakt. Als het netwerk traag is, kunt u werken met de offline versie van de bestanden.
  
De synchronisatie-app voor OneDrive voor bedrijven is uitgerust met een SharePoint Online-en Office 365-Bedrijfs abonnement, of u kunt de synchronisatie-app voor OneDrive voor bedrijven gratis [downloaden](https://support.microsoft.com/kb/2903984) . Deze app is ook sneller dan met de opdracht **openen in Verkenner** of **uploaden** . Zie [uw computer instellen op het synchroniseren van OneDrive voor bedrijven-bestanden in Office 365](https://support.office.com/article/23e1f12b-d896-4cb1-a238-f91d19827a16)voor meer informatie.
  
Hier volgen enkele aanvullende richtlijnen voor het gebruik van de synchronisatie-app voor OneDrive voor bedrijven:
  
- Als u een grote bibliotheek voor het eerst synchroniseert, start de synchronisatie dan buiten kantooruren, bijvoorbeeld 's nachts.

- Met de functie voor [het synchroniseren van een bibliotheek met de app van OneDrive voor bedrijven](https://support.office.com/article/a7e41f1f-3a98-4ca7-9443-f10250688330) kunt u de synchronisatie van een bibliotheek tijdelijk stopzetten. Gebruik deze functie echter voor korte perioden, zoals een paar uur per keer, om te voorkomen dat grote aantallen updates in de wachtrij worden omgezet en om het risico op samenvoegings conflicten te minimaliseren als meerdere personen aan hetzelfde document werken.
  
## <a name="best-practices-for-using-onenote"></a>Aanbevolen procedures voor het gebruik van OneNote

Elke SharePoint-Team site heeft een ingebouwd OneNote-notitieblok en u kunt eenvoudig uw eigen notitieblok maken. OneNote is een fantastische manier om de tijd te verzamelen waarop u elke dag informatie nodig hebt om taken uit te voeren. Zo wordt in veel teams OneNote als een verzamelings punt gebruikt voor wekelijkse vergaderingen, projectnotities, ideeën, plannen en statusrapporten. Met behulp van pagina's, secties en tabbladen kunt u op een handige manier deze verschillende informatie ordenen.
  
Het mooie van OneNote is dat u toegang hebt tot de inhoud van vrijwel elk apparaat, of een desktop, een laptop, een tablet of een smartphone. U hoeft zich geen zorgen te maken over het opslaan of synchroniseren omdat OneNote het voor u doet.
  
Zie [Microsoft OneNote](https://office.microsoft.com/onenote)voor meer informatie.

## <a name="best-practices-for-using-skype-for-business-and-lync-online"></a>Aanbevolen procedures voor het gebruik van Skype voor bedrijven en Lync online

Hier volgen algemene richtlijnen voor het gebruik van Skype voor bedrijven of Lync online wanneer uw netwerk traag is:

- Gebruik expresberichten wanneer u dat wel doet omdat dit geschikt is voor een traag netwerk.

- Maak geen telefoongesprekken via een VPN-verbinding (Virtual Private Network) of een RAS-verbinding (Remote Access service).

- Zorg ervoor dat uw audioapparaat is goedgekeurd. Zie voor meer informatie [telefoons en apparaten die zijn gekwalificeerd voor Microsoft Lync](https://docs.microsoft.com/skypeforbusiness/lync-cert/ip-phones).

- Wanneer u PowerPoint in een onlinepresentatie gebruikt, kunt u de grootte en complexiteit van de dia's verkleinen. Zie [Tips voor het verbeteren van de prestaties van uw presentatie](https://support.office.com/article/34c82835-5f23-4bf0-98cc-72235bbd2949)voor meer informatie.

- De prestaties van het netwerk zijn zeer afhankelijk van de prestaties van het netwerk. Vermijd het gebruik van video als uw netwerk traag is.

Zie [slechte audio-of videokwaliteit in Lync online](https://support.microsoft.com/kb/2386655)of problemen met de [verbinding oplossen in Skype voor bedrijven](https://support.office.com/article/troubleshoot-connection-issues-in-skype-for-business-ca302828-783f-425c-bbe2-356348583771)voor meer informatie.
  
## <a name="best-practices-for-using-sharepoint-lists"></a>Aanbevolen procedures voor het gebruik van SharePoint-lijsten

Werken met lijstgegevens offline om de gevolgen van een traag netwerk te beperken, is een uitstekende manier om de gevolgen van een traag netwerk te beperken. U kunt de meeste lijsten lezen en schrijven in Microsoft Access 2019 en Microsoft Access 2016 door deze te koppelen. U kunt ook een lijst exporteren naar een Excel-tabel, waarmee een eenrichtings gegevensverbinding wordt gemaakt tussen de Excel-tabel en de lijst. Meer informatie over het [offline werken met tabellen die aan SharePoint-lijsten zijn gekoppeld](https://support.office.com/article/work-offline-with-tables-that-are-linked-to-sharepoint-lists-5d66594a-6176-4a25-a198-320f13ccf41e).
  
Zie voor meer informatie de sectie ' meer informatie over het beheren van grote lijsten ' in [grote lijsten en bibliotheken beheren in Office 365](https://support.office.com/article/b4038448-ec0e-49b7-b853-679d3d8fb784).
  
## <a name="best-practices-for-customizing-web-pages"></a>Aanbevolen procedures voor het aanpassen van webpagina's

Wanneer u een webpagina aanpast, is het mogelijk dat u de pagina niet goed kunt presteren. Een aantal factoren kan een impact hebben, zoals de complexiteit en de grootte van de pagina, het aantal webonderdelen dat wordt toegevoegd, het aantal items in de lijst of bibliotheek dat in eerste instantie wordt weergegeven en de manier waarop u de pagina codeert.
  
Zie [prestaties van SharePoint Online afstemmen](tune-sharepoint-online-performance.md)voor meer informatie.
  
## <a name="best-practices-for-using-project-online"></a>Aanbevolen procedures voor het gebruik van project online

De volgende richtlijnen kunnen helpen om de prestaties van het netwerk te verbeteren.
  
- Project online en SharePoint Online hebben synchronisatie nodig, wat veel tijd in beslag kan zijn. Als uw projectteams een lage omzet hebben, schakelt u project site synchroniseren uit om de prestaties van project publicatie en project detail pagina's te verbeteren. Beperk Active Directory-synchronisatie met groepen bronnen die het systeem echt moeten gebruiken, en Controleer eventuele problemen met de machtiging na de synchronisatie van grote groepen.

- Als uw organisatie gebruikmaakt van projectsites, kunt u deze op aanvraag maken in plaats van automatisch te gebruiken. Hiermee versnelt u de eerste publicatie en vermijdt u het maken van overbodige sites en inhoud.

- Met project detail pagina's (PDP) kan een herberekening van het hele project worden geactiveerd en de werkstroomacties worden uitgevoerd, zowel de werking van de werkstroom. Om te voorkomen dat twee update processen tegelijkertijd worden geactiveerd op dezelfde PDP, moet u voorkomen dat u de agendavelden (begindatum, einddatum, status datum en huidige datum) en de niet-geplande velden (projectnaam, beschrijving en eigenaar) bijwerkt.

- Verminder het aantal webonderdelen en aangepaste velden die worden weergegeven op elke PDP. Maak een gespecialiseerde PDP met de enige velden die moeten worden bijgewerkt om de belasting te verbeteren en tijd te besparen.

- Wanneer u OData gebruikt voor rapporten, Beperk u de hoeveelheid gegevens die u opvraagt gedurende runtime, door Server filtering te gebruiken.

Zie [prestaties van project online optimaliseren](https://support.office.com/article/12ba0ebd-c616-42e5-b9b6-cad570e8409c)voor meer informatie.
  
## <a name="whats-the-best-way-to-report-problems"></a>Hoe kan ik het beste problemen rapporteren?

Microsoft verbetert de algehele prestaties van Office 365 voortdurend door de bewaking van het netwerk, de bandbreedte en latentie te verbeteren, de laadtijd van pagina's te verbeteren en de pagina's opnieuw te ontwerpen voor het gebruik van minimale Download strategie, het toevoegen van een hardware aan datacenters en het toevoegen van meer datacenters. Zie de [servicestatus van Office 365 controleren](view-service-health.md)voor meer informatie over het controleren van uw huidige status en rapportage problemen.
  
## <a name="see-also"></a>Zie ook

[Network planning and performance tuning for Office 365](network-planning-and-performance.md)
  
[Methoden voor netwerkverbindingen in Office 365](microsoft-365-network-connectivity-principles.md)
  
[Office 365-eindpunten beheren](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Veelgestelde vragen over Office 365-eindpunten](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
 
