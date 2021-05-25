---
title: DNS-basisprincipes
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- MET150
- MOE150
- GEA150
- BSA160
ms.assetid: 854b6b2b-0255-4089-8019-b765cff70377
ROBOTS: NOINDEX
description: Met het domeinnaamsysteem worden computerhostnamen toegestuurd aan IP-adressen en als u inzicht hebt in DNS en de basisprincipes van domeinregistrars, kunt u domeinen beter beheren.
ms.openlocfilehash: 19fc444c056bbf3e1ea1f601d20a9b9cbd75bec8
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635424"
---
# <a name="dns-basics"></a>DNS-basisprincipes

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt. 
  
::: moniker range="o365-worldwide"

Domeinnamen, zoals contoso.com, worden beheerd met een wereldwijd systeem van domeinregistrars en databases. Het DNS (Domain Name System) biedt een koppeling tussen door mensen leesbare computerhostnamen en de IP-adressen die door netwerkapparatuur worden gebruikt. Als u de basisprincipes van DNS en domeinregistrars begrijpt, kunt u domeinen beter beheren.

## <a name="watch-domains--dns-an-overview"></a>Bekijken: Domeinen & DNS: een overzicht
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-germany"

Domeinnamen, zoals contoso.com, worden beheerd met een wereldwijd systeem van domeinregistrars en databases. Het DNS (Domain Name System) biedt een koppeling tussen door mensen leesbare computerhostnamen en de IP-adressen die door netwerkapparatuur worden gebruikt. Als u de basisprincipes van DNS en domeinregistrars begrijpt, kunt u domeinen beter beheren.

## <a name="watch-domains--dns-an-overview"></a>Bekijken: Domeinen & DNS: een overzicht
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-21vianet"

Domeinnamen, zoals contoso.com, worden beheerd met een wereldwijd systeem van domeinregistrars en databases. Het DNS (Domain Name System) biedt een koppeling tussen door mensen leesbare computerhostnamen en de IP-adressen die door netwerkapparatuur worden gebruikt. Beheerders die de basisprincipes van DNS en domeinregistrars begrijpen, zullen domeinen beter beheren.
  
::: moniker-end

## <a name="what-are-domain-names"></a>Wat zijn domeinnamen?

Domeinnamen worden gebruikt in URL’s en e-mailadressen en hebben verschillende niveaus. mail.contoso.com is bijvoorbeeld een domeinnaam met de volgende drie niveaus:
  
- **.com** is het domein op het hoogste niveau 
    
- **contoso** is het domein op het tweede niveau 
    
- **mail** is het domein op het derde niveau 
    
Waarom zou u een domein op het derde niveau gebruiken? Mogelijk wilt u verschillende domeinnamen voor marketingdoeleinden of een blog gebruiken. Bijvoorbeeld: blog.contoso.com. U voegt doorgaans een domein op het tweede niveau toe om te gebruiken met Microsoft, zoals contoso.com, maar als u wilt, kunt u ook domeinen op het derde niveau gebruiken.
  
Bekijk de [Servicebeschrijving voor Microsoft 365- en Office 365-platformen](/office365/servicedescriptions/office-365-platform-service-description/domains) voor meer informatie over wat u met domeinen kunt doen voor elk type aanbod.
  
## <a name="understand-dns-record-types"></a>Meer informatie over DNS-recordtypen

DNS-records die zijn opgeslagen bij een DNS-host voor uw domein worden gebruikt om verkeer van en naar uw domein te leiden. In de volgende tabel worden veelgebruikte DNS-records beschreven en hoe ze worden gebruikt.
  
|**NS-record (naamserver)**|**Identificeert de naamservers die de 'gezaghebbende naamservers' voor een domein zijn. Wanneer u deze naamservers wijzigt voor uw domein, wijzigt u de locatie waar uw DNS-records worden beheerd en waar het DNS-systeem zoekt naar informatie over mailservers en dergelijke. Microsoft heeft eigen naamservers, maar u kunt ook besluiten om de naamservers te blijven gebruiken die al zijn ingesteld voor uw domein.**|
|:-----|:-----|
|A-record (adresrecord)  <br/> |Koppelt een domeinnaam aan een IP-adres.  <br/> |
|CNAME-record (alias of canoniek)  <br/> |Leidt het ene domein om naar een ander domein in het DNS-systeem. Wanneer een naamserver een domein opzoekt en ziet dat het domein een CNAME-record heeft, vervangt de server de eerste domeinnaam door de CNAME en wordt vervolgens de nieuwe naam opgezocht.  <br/> |
|MX-record (e-mailuitwisselaar)  <br/> |Verwijst naar de locatie waar uw e-mail naartoe moet worden gezonden. Deze record bevat ook een prioriteitsveld, zodat u e-mail naar verschillende servers kan verzenden in een bepaalde prioriteitsvolgorde.  <br/> |
|SPF-record (Sender Policy Framework)  <br/> |Een TXT-record die e-mailspoofing en phishing helpt voorkomen.  <br/> |
|SRV-record (service)  <br/> |Wordt gebruikt door Skype voor Bedrijven Online en Exchange Online om de gegevensstroom tussen Microsoft-services te coördineren. De SRV-records zijn bijvoorbeeld vereist om de aanwezigheid in Outlook Web App te zien en om Skype voor Bedrijven Online, Skype of andere chatprogramma's met personen in andere bedrijven te gebruiken.  <br/> |
|TTL (Time To Live)  <br/> |De hoeveelheid tijd die een naamserver een DNS-record bewaart voordat de server naar een bijgewerkte versie zoekt.  <br/> |
   
## <a name="how-does-dns-work"></a>Hoe werkt DNS?

Een deel van het instellen van uw domein voor een cloudservice zoals Microsoft 365 bestaat uit het wijzigen of toevoegen van [DNS-records](dns-basics.md) voor het domein. Deze wijzigingen zijn vereist vanwege de manier waarop het internet met DNS en domeinnamen omgaat zodat u weet waar u iets kunt vinden of naar toe sturen, bijvoorbeeld websites zoeken en e-mail verzenden. 
  
Internet is ingesteld voor gebruik met DNS (Domain Name System), waarmee bekende namen, zoals contoso.com, kunnen worden gebruikt om te zoeken naar specifieke internetlocaties die in feite, diep verborgen op internet, zijn gelabeld met moeilijk te onthouden getallen, ook wel IP-adressen (Internet Protocol) genoemd. Een IP-adres is bijvoorbeeld 70.42.241.42. Het is dus veel makkelijker om een domeinnaam te gebruiken om locaties, zoals e-mailhosts en websites, aan te duiden.
  
Dit is dus het korte antwoord: DNS-records laten het internet weten waar e-mail naartoe moet worden verzonden (zoals jan@contoso.com) of waar websites (zoals www.contoso.com) kunnen worden gevonden die uw domeinnaam gebruikt. Wanneer u de juiste informatie in de juiste DNS-records voor uw domein opneemt, wordt alles op de juiste manier gerouteerd door het DNS-systeem, zodat uw e-mail bijvoorbeeld binnenkomt in Microsoft 365 en niet op een andere locatie.
  
De DNS-records van een domein kunnen ook in andere situaties handig zijn. In Exchange wordt bijvoorbeeld een DNS-record gecontroleerd waarmee in Outlook automatisch een verbinding kan worden ingesteld met de juiste Exchange-server.
  
### <a name="dns-records-help-the-internet-send-email-to-the-right-place"></a>Met DNS-records wordt op internet e-mail naar de juiste plaats verzonden.

Zoals u hiervoor hebt gelezen, wordt met DNS in feite verkeer op internet geleid, waarbij beschrijvende domeinnamen worden toegewezen aan de moeilijk te onthouden IP-adressen. Eén DNS-record, de zogenaamde MX-record, is specifiek bedoeld voor het verzenden van e-mail naar de juiste host.
  
DNS-records zijn vergelijkbaar met een database met informatie over uw domein. De records en de bijbehorende waarden worden bewaard in een zonebestand dat een lijst bevat met elke record voor uw domein en wat de waarde is. Domeinregistrars en andere DNS-hostingbedrijven bieden een gebruikersinterface op hun websites, zodat u de records in het zonebestand van uw domein kunt bewerken. Dit is de plaats waar u de MX-record voor uw domein bijwerkt om e-mailberichten naar Microsoft 365 te verzenden.
  
 *Wanneer u uw e-mailadres overzet naar Microsoft 365 door de MX-record van uw domein in de volgende stap bij te werken, komt alle e-mail die naar dat domein wordt verzonden binnen in Microsoft 365.*  Als andere personen uw domein voor e-mail gebruiken, moet u voor elke persoon Microsoft 365-postvakken instellen. 
  
Klinkt dit ingewikkeld? Dat is het soms ook, maar we begeleiden u stapsgewijs bij het instellen van het Microsoft-domein.
  
### <a name="dns-tells-the-internet-where-to-look-for-websites-too"></a>Via DNS wordt ook aangegeven waar op internet naar websites moet worden gezocht.

Wanneer u een websiteadres typt, bijvoorbeeld www.contoso.com, wordt eerst met een van de DNS-servers gezocht naar iets dat een NS-record (naamserver) voor (in dit geval) contoso.com wordt genoemd. Met de NS-record wordt aangegeven waar moet worden gezocht naar het zonebestand met alle andere DNS-recordwaarden voor dat domein. Er zijn veel DNS-servers die allemaal met elkaar zijn verbonden. De servers werken samen om alle geregistreerde domeinnamen (die uniek moeten zijn) bij te houden en waar de zonebestanden van het domein zich bevinden.
  
::: moniker range="o365-worldwide"

Stel dat de NS-record voor contoso.com 'godaddy.com' is. Nu weet het internet dat op GoDaddy.com moet worden gezocht naar het zonebestand met alle DNS-records voor contoso.com. De DNS-records bevatten de MX-record waarin is opgegeven waar u e-mailberichten naartoe moet sturen voor contoso.com en andere records. Als de MX-record een waarde heeft waarin vermeld wordt (in technische termen) 'e-mail verzenden naar Microsoft 365', worden daar alle e-mails gericht aan een contoso.com-e-mailadres (zoals jan@contoso.com) naartoe gestuurd. Vervolgens wordt het e-mailbericht bezorgd, zolang er een postvak met de naam Jan op die locatie aanwezig is.

::: moniker-end

::: moniker range="o365-germany"

Stel dat de NS-record voor contoso.com 'godaddy.com' is. Nu weet het internet dat op GoDaddy.com moet worden gezocht naar het zonebestand met alle DNS-records voor contoso.com. De DNS-records bevatten de MX-record waarin is opgegeven waar u e-mailberichten naartoe moet sturen voor contoso.com en andere records. Als de MX-record een waarde heeft waarin vermeld wordt (in technische termen) 'e-mail verzenden naar Microsoft 365', worden daar alle e-mails gericht aan een contoso.com-e-mailadres (zoals jan@contoso.com) naartoe gestuurd. Vervolgens wordt het e-mailbericht bezorgd, zolang er een postvak met de naam Jan op die locatie aanwezig is.

::: moniker-end

::: moniker range="o365-21vianet"

Stel dat de NS-record voor contoso.com 'hichina.com' is. Nu weet het internet dat op hichina.com moet worden gezocht naar het zonebestand met alle DNS-records voor contoso.com. De DNS-records bevatten de MX-record waarin is opgegeven waar u e-mailberichten naartoe moet sturen voor contoso.com en andere records. Als de MX-record een waarde heeft waarin vermeld wordt (in technische termen) 'e-mail verzenden naar Microsoft 365', worden daar alle e-mails gericht aan een contoso.com-e-mailadres (zoals jan@contoso.com) naartoe gestuurd. Vervolgens wordt het e-mailbericht bezorgd, zolang er een postvak met de naam Jan op die locatie aanwezig is.

::: moniker-end

De werkelijke waarden die u voor Microsoft 365 moet invoeren, worden weergegeven in de stappen die u moet volgen als u uw domein instelt. Als u de instelling handmatig uitvoert, kopieert en plakt u de waarden in de juiste DNS-records (MX-record, CNAME-records, enzovoort) op uw DNS-host. Dit kan uw domeinregistrar of iets anders zijn.
  
::: moniker range="o365-worldwide"

Waarom kan het zonebestand van uw domein zich ergens buiten uw domeinregistrar bevinden? Omdat het mogelijk is dat u uw domeinnaam registreert bij een domeinregistrar, zoals GoDaddy, terwijl uw DNS-records ergens anders worden beheerd, in een apart DNS-hostingbedrijf of een webhostingbedrijf. Die gegevens worden in de NS-records voor uw domeinopslagplaats opgeslagen, zodat alle DNS-servers weten waar ze moeten zoeken.

::: moniker-end

::: moniker range="o365-germany"

Waarom kan het zonebestand van uw domein zich ergens buiten uw domeinregistrar bevinden? Omdat het mogelijk is dat u uw domeinnaam registreert bij een domeinregistrar, zoals GoDaddy, terwijl uw DNS-records ergens anders worden beheerd, in een apart DNS-hostingbedrijf of een webhostingbedrijf. Die gegevens worden in de NS-records voor uw domeinopslagplaats opgeslagen, zodat alle DNS-servers weten waar ze moeten zoeken.

::: moniker-end

::: moniker range="o365-21vianet"

Waarom kan het zonebestand van uw domein zich ergens buiten uw domeinregistrar bevinden? Het is ook mogelijk dat u uw domeinnaam registreert bij een domeinregistrar, zoals HiChina, terwijl uw DNS-records ergens anders worden beheerd, in een afzonderlijk DNS-hostingbedrijf of een webhostingbedrijf. Die gegevens worden in de NS-records voor uw domeinopslagplaats opgeslagen, zodat alle DNS-servers weten waar ze moeten zoeken.

::: moniker-end

::: moniker range="o365-worldwide"
## <a name="why-add-a-domain-in-microsoft-365"></a>Waarom zou ik een domein toevoegen in Microsoft 365?


Als u een aangepast domein, zoals fourthcoffee.com, toevoegt aan Microsoft 365, kunt u kortere, meer vertrouwde e-mailadressen en gebruikers-id's met de service gebruiken. U [krijgt een domein toegewezen](../setup/domains-faq.yml) wanneer u zich aanmeldt voor een Microsoft 365-account, maar dit bevat onmicrosoft.com. Veel mensen voegen liever het domein van hun organisatie of bedrijf toe als ze Microsoft 365 voor e-mail willen gaan gebruiken. 
  
> [!NOTE]
> Als u alleen Microsoft-apps wilt downloaden en gebruiken, zoals Outlook of Word, hoeft u geen domein toe te voegen: [Installeer Office op uw pc of Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658). 
  
U kunt uw domeinnaam in Microsoft 365 gebruiken voor uw e-mailadres, het adres van uw openbare website en uw chatadres.
  
- **E-mail:** Met uw domeinnaam kunt u uw e-mailadres aanpassen, zodat u een korter en gemakkelijker te onthouden adres kunt gebruiken dan [het eerste onmicrosoft.com-e-mailadres](../setup/domains-faq.yml) dat bij uw account wordt geleverd. Dus in plaats van jan@contoso.onmicrosoft.com kan het e-mailadres (dat ook het werkaccount is dat u gebruikt voor het aanmelden bij Microsoft 365) jan@contoso.com zijn. 
    
- **Website:** Als u een Microsoft 365-abonnement hebt dat een openbare SharePoint Online-website omvat (niet meer te koop), heeft deze openbare site in eerste instantie een adres zoals contoso-public.sharepoint.com. Als u een website voor uw bedrijf instelt, kunt u een aangepaste domeinnaam gebruiken om het websiteadres te wijzigen in bijvoorbeeld www.contoso.com. 
    
- **Chatten:** Uw adres van Skype voor Bedrijven Online kan ook zo worden aangepast dat uw domeinnaam wordt gebruikt, zodat mensen in uw organisatie contact met elkaar kunnen hebben via Skype voor Bedrijven Online met een korter, eenvoudiger te onthouden adres (zoals jan@contoso.com). 
    
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-add-a-domain-in-microsoft-365"></a>Waarom zou ik een domein toevoegen in Microsoft 365?


Als u een aangepast domein, zoals fourthcoffee.com, toevoegt aan Microsoft 365, kunt u kortere, meer vertrouwde e-mailadressen en gebruikers-id's met de service gebruiken. U [krijgt een domein toegewezen](../setup/domains-faq.yml) wanneer u zich aanmeldt voor een Microsoft 365-account, maar dit bevat onmicrosoft.com. Veel mensen voegen liever het domein van hun organisatie of bedrijf toe als ze Microsoft 365 voor e-mail willen gaan gebruiken. 
  
> [!NOTE]
> Als u alleen Microsoft 365-apps wilt downloaden en gebruiken, zoals Outlook of Word, hoeft u geen domein toe te voegen: [Installeer Office op uw pc of Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658). 
  
U kunt uw domeinnaam in Microsoft 365 gebruiken voor uw e-mailadres, het adres van uw openbare website en uw chatadres.
  
- **E-mail:** Met uw domeinnaam kunt u uw e-mailadres aanpassen, zodat u een korter en gemakkelijker te onthouden adres kunt gebruiken dan [het eerste onmicrosoft.com-e-mailadres](../setup/domains-faq.yml) dat bij uw account wordt geleverd. Dus in plaats van jan@contoso.onmicrosoft.com kan het e-mailadres (dat ook het werkaccount is dat u gebruikt voor het aanmelden bij Microsoft 365) jan@contoso.com zijn. 
    
- **Website:** Als u een abonnement hebt dat een openbare SharePoint Online-website omvat (niet meer te koop), heeft deze openbare site in eerste instantie een adres zoals contoso-public.sharepoint.com. Als u een website voor uw bedrijf instelt, kunt u een aangepaste domeinnaam gebruiken om het websiteadres te wijzigen in bijvoorbeeld www.contoso.com. 
    
- **Chatten:** Uw adres van Skype voor Bedrijven Online kan ook zo worden aangepast dat uw domeinnaam wordt gebruikt, zodat mensen in uw organisatie contact met elkaar kunnen hebben via Skype voor Bedrijven Online met een korter, eenvoudiger te onthouden adres (zoals jan@contoso.com). 
    
::: moniker-end

## <a name="the-dns-records-required-for-microsoft-365"></a>De benodigde DNS-records voor Microsoft 365

Er zijn een aantal DNS-records vereist om Microsoft 365 te laten werken met uw domein. Naast het instellen van de MX-record van uw domein, zodat e-mail naar Microsoft 365 wordt verzonden, zijn er ook records ter ondersteuning van andere taken, bijvoorbeeld om ervoor te zorgen dat Outlook automatisch verbinding kan maken met de juiste Exchange-server, voor de configuratie van chatberichten en om ongewenste e-mail te voorkomen.
  
U kunt [zoeken naar een lijst met waarden](information-for-dns-records.md) om uw domein in te stellen. .Deze zijn opgenomen in het Microsoft 365-beheercentrum. 
  
Als u een implementatie plant, wilt u mogelijk een lijst bekijken met alle vereiste DNS-records voor Microsoft 365, de functie ervan en voorbeeldwaarden. Bekijk [Externe DNS-records voor Microsoft 365](../../enterprise/external-domain-name-system-records.md).
  
## <a name="next-steps"></a>Volgende stappen

Raadpleeg het volgende: 
  
- Weet u niet zeker waar uw domein is geregistreerd? [Hulp krijgen bij het vinden van uw domeinregistrar.](find-your-domain-registrar.md)
- Kijk [waarom u de stappen van de wizard moet voltooien](../setup/add-domain.md) voordat u uw domein kunt gebruiken met Microsoft 365.

## <a name="related-content"></a>Verwante inhoud

[Veelgestelde vragen over domeinen](../setup/domains-faq.yml) (artikel)\
[Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](find-and-fix-issues.md) (artikel)\
[Domeinen beheren](index.yml) (koppelingspagina)