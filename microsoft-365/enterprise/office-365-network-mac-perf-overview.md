---
title: Aanbevelingen voor netwerkprestaties in het Microsoft 365-Beheercentrum (preview)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Overzicht van aanbevelingen voor netwerkprestaties in het Microsoft 365-Beheercentrum (preview)
ms.openlocfilehash: 03064f4919949659d7fb272c96b540c74ac3aca8
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695687"
---
# <a name="network-performance-recommendations-in-the-microsoft-365-admin-center-preview"></a>Aanbevelingen voor netwerkprestaties in het Microsoft 365-Beheercentrum (preview)

Het Microsoft 365-Beheercentrum bevat nu dynamische prestatiegegevens die zijn verzameld van uw Microsoft 365-Tenant en die alleen kunnen worden weergegeven door beheerders gebruikers in uw Tenant. de **aanbevelingen voor netwerk inzichten en prestaties** en de **netwerk beoordelingen** worden weergegeven in het Microsoft 365-Beheercentrum <https://portal.microsoft.com/adminportal/home#/networkperformance> . U vindt de pagina in het navigatiedeelvenster onder **status | Netwerkprestaties**.

![Pagina netwerkprestaties](../media/m365-mac-perf/m365-mac-perf-page-nav.png)

Wanneer u naar de pagina netwerkprestaties gaat, ziet u het deelvenster Overzicht met een overzicht van de algemene netwerkprestaties, een netwerkbeoordelings bereik voor de volledige Tenant en een lijst met actuele problemen. In het overzicht kunt u in-en uitzoomen om bepaalde metrische gegevens voor netwerkprestaties en-problemen weer te geven op locatie. Zie [het overzicht van netwerkprestaties in het Microsoft 365-Beheercentrum](#network-performance-overview-in-the-microsoft-365-admin-center)voor meer informatie.

## <a name="pre-requisites-for-connectivity-measurements-to-appear"></a>Vereisten voor het weergeven van connectiviteits waarden

Als u wilt dat de afmetingen van verbindingen worden weergegeven, moet u ten minste twee computers op elke Office-locatie hebben waarop de vereisten worden ondersteund. De Synchronisatieclient van OneDrive voor bedrijven-client versie 19,232 of hoger moet zijn geïnstalleerd op elke computer. Zie de opmerkingen bij de [OneDrive-release](https://support.office.com/article/onedrive-release-notes-845dcf18-f921-435e-bf28-4e24b95e5fc0)voor meer informatie.

Windows-locatie service moet zijn doorgestuurd op de computers. U kunt dit testen door de app **kaarten** uit te voeren en te zoeken. U kunt deze optie inschakelen op een enkele computer **Settings**met  ->  de**privacyinstellingen**van de instellingen  ->  **Location** waar de instelling ' apps mag toegang krijgen tot uw locatie ' moet zijn ingeschakeld. De Windows Location Service instemming kan worden geïmplementeerd op Pc's met behulp van MDM of Groepsbeleid met de instelling _LetAppsAccessLocation_.

De computers moeten Wi-Fi-netwerken hebben in plaats van een Ethernet-kabel. Machines met een Ethernet-kabel hebben geen nauwkeurige informatie over de locatie.

De maat monsters en de kantoorlocaties moeten 24 uur worden weergegeven nadat aan deze vereisten is voldaan.

## <a name="how-do-i-use-this-information"></a>Hoe gebruik ik deze informatie?

**Netwerk inzichten**, de bijbehorende prestatie aanbevelingen en netwerk beoordelingen zijn bedoeld voor het ontwerpen van netwerkverbindingen voor uw Office-locaties. Elk inzicht biedt u actuele informatie over de prestatie-eigenschappen voor een specifiek gemeenschappelijke probleem waarbij gebruikers toegang krijgen tot uw Tenant. **Aanbevelingen** voor de prestaties van elk netwerk voor inzicht in de vereisten voor het ontwerp van de netwerkarchitectuur kunt u een betere gebruikerservaring met de microsoft 365-netwerkconnectiviteit maken. De netwerk beoordeling laat zien hoe de gebruikerservaring invloed heeft op de gebruikerservaring, zodat de netwerkverbindingen van de verschillende gebruikerslocatie kunnen worden vergeleken.

**Netwerk beoordelingen** : een samenvatting van de gegevens van de netwerkprestaties in een momentopname van de status van uw bedrijfsnetwerk, aangeduid met een punten waarde uit 1-100. Netwerk beoordelingen zijn beperkt tot de gehele Tenant en voor elke geografische locatie van de gebruikers die verbinding maken met uw Tenant, zodat Microsoft 365-beheerders een eenvoudige manier is om een Gestalt van de netwerkstatus van de onderneming te begrijpt en snel een uitzoomen op een gedetailleerd overzicht van een wereldwijd kantoor.

Complexe ondernemingen met meerdere kantoorlocaties en niet-triviale netwerk perimeter architecturen kunnen met deze informatie profiteren van de voordelen van Microsoft 365 of voor het oplossen van problemen met de netwerkprestaties die zijn ontdekt bij gebruiks groei. Dit is doorgaans niet nodig voor kleine bedrijven die gebruikmaken van Microsoft 365, of ondernemingen die al eenvoudige en rechtstreekse netwerkconnectiviteit hebben. Voor bedrijven met meer dan 500 gebruikers en meerdere Office-locaties wordt naar verwachting geprofiteerd.

>[!IMPORTANT]
>Netwerk inzichten, prestatie aanbevelingen en beoordelingen in het Microsoft 365-Beheercentrum is momenteel in de preview-versie en is alleen beschikbaar voor Microsoft 365-tenants die zijn geregistreerd in het functie voorbeeldprogramma.

## <a name="enterprise-network-connectivity-challenges"></a>Netwerkconnectiviteitsproblemen voor ondernemingen

![Netwerk van klant naar Cloud](../media/m365-mac-perf/m365-mac-perf-first-last-mile.png)

Veel bedrijven hebben configuraties voor netwerkverbindingen die in de loop van de tijd zijn gekweekt en die hoofdzakelijk zijn ontworpen om toegang te krijgen tot de Internet site van werknemers waar de meeste websites niet vooraf bekend zijn en waarvan niet wordt vertrouwd. De heersende en de benodigde focus verlegt geen malware en verzorgt geen aanvallen van deze onbekende websites. Deze strategie voor de netwerkconfiguratie kan leiden tot degradatie van de prestaties van Microsoft 365 User en de gebruikerservaring.

## <a name="how-we-can-solve-these-challenges"></a>Hoe we deze uitdagingen kunnen oplossen

Ondernemingen kunnen de algemene gebruikerservaring verbeteren en hun omgeving beschermen aan de hand van de basis [principes van Office 365](https://aka.ms/pnc) en de functies voor netwerkprestaties van microsoft 365. In de meeste gevallen is het raadzaam om de latentie, de betrouwbaarheid van de dienst en de algehele prestaties van Microsoft 365 te verbeteren.

Microsoft vraagt soms om problemen met de netwerkprestaties met Microsoft 365 voor grote Enterprise-klanten en bevat vaak de basis oorzaak van de infrastructuur van de netwerk uitgang van de klant. Wanneer een veelvoorkomende hoofdoorzaak van een probleem met de netwerkverbinding van de klant wordt gevonden, willen we eenvoudige test metingen identificeren waarmee de basis oorzaak wordt aangegeven. Een test met een maateenheid die een specifiek probleem identificeert, is waardevol omdat u dezelfde afmeting op elke locatie kunt testen, aangeven of deze hoofdoorzaak op een willekeurige plaats aanwezig is en de beheerder als netwerk inzicht deelt.

Sommige netwerk inzichten geven slechts een probleem aan dat verder moet worden onderzocht. Een netwerk inzicht waarbij er voldoende tests zijn voor het weergeven van een specifieke herstelactie om de hoofdoorzaak te corrigeren, wordt weergegeven als **Aanbevolen actie**. Deze aanbevelingen op basis van Live metrische waarden die waarden weergeven die buiten een vooraf ingestelde drempel vallen, zijn veel waardevoler dan algemeen best practices adviseren, aangezien ze specifiek zijn voor uw omgeving, en zullen de daadwerkelijke verbetering aangeven wanneer de aanbevolen wijzigingen zijn aangebracht.

## <a name="network-performance-overview-in-the-microsoft-365-admin-center"></a>Netwerk prestatie-overzicht in het Microsoft 365-Beheercentrum

Microsoft beschikt over bestaande netwerk metingen van diverse bureaublad-en webclients van Office die de werking van Microsoft 365 ondersteunen. Deze metingen worden nu gebruikt voor het verschaffen van inzichten van de netwerkarchitectuur en een beoordeling van de netwerkprestaties die wordt weergegeven op de pagina **netwerkprestaties** in het microsoft 365-Beheercentrum.

Standaard wordt de plaats aangegeven waar de client apparatuur zich bevindt, de locatiegegevens die bij de netwerk metingen horen. De beoordeling van het netwerk op elke locatie wordt weergegeven met kleur en het relatieve aantal gebruikers op elke locatie wordt aangegeven met de grootte van de cirkel.

![Overzicht van netwerk inzichten](../media/m365-mac-perf/m365-mac-perf-overview-map.png)

Op de pagina Overview wordt ook de netwerkassessment voor de klant weergegeven als een gewogen gemiddelde voor alle kantoorlocaties.

![Netwerk beoordeling](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

## <a name="specific-office-location-network-performance-summary-and-insights"></a>Specifieke Office-locatie netwerk prestatie samenvatting en inzichten

Wanneer u een Office-locatie selecteert, wordt er een overzichtspagina weergegeven met details van de uittreding van het netwerk die is geïdentificeerd op basis van metingen voor die kantoorlocatie.

![Details netwerk inzichten op locatie](../media/m365-mac-perf/m365-mac-perf-locations-plan-overview.png)

Op de pagina Office-locatie overzicht ziet u ook de netwerk beoordeling van de vestiging, de netwerkbeoordelings geschiedenis, een vergelijking van de beoordeling van deze locatie en een lijst met specifieke inzichten en aanbevelingen die u kunt ondernemen om de prestaties van het netwerk en de betrouwbaarheid te verbeteren. Bij locaties met specifieke aanbevelingen kan ook een geschatte potentiële latentie verbetering worden opgenomen.

Voor vergelijkingen tussen klanten in dezelfde stad wordt uitgegaan van de verwachting dat alle klanten gelijke toegang hebben tot netwerkservice providers, telecommunicatie infrastructuur en nabijgelegen Microsoft-netwerk punten van aanwezigheid.

![Netwerk inzichten locaties](../media/m365-mac-perf/m365-mac-perf-locations.png)

Op het tabblad Details op de pagina Office-locatie ziet u de specifieke meetresultaten die zijn gebruikt voor inzichten, aanbevelingen en de netwerk beoordeling. Dit wordt geboden, zodat netwerk technici de aanbevelingen en de factoren in de desbetreffende omgeving kunnen valideren.

![Locatiespecifieke Details](../media/m365-mac-perf/m365-mac-perf-locations-plan-details-all.png)

Voor klanten die de nauwkeurigheid van locatiespecifieke metrische gegevens en aanbevelingen willen verbeteren, kunnen we specifiekere informatie invoeren. Dit kan de benaderingen verkorten die inherent zijn aan de beschikbare locatiegegevens voor netwerk metingen. Als u het adres van een bepaalde kantoorlocatie wilt <functionality not there yet> bewerken,

## <a name="import-undiscovered-office-locations"></a>Niet-ontdekte Office-locaties importeren

Op het tabblad prestaties van netwerk **locaties** wordt een lijst weergegeven met de Office-locaties die automatisch worden gedetecteerd via netwerktelemetry. Op deze Office-locaties zijn steden gevonden. U kunt handmatig specifiekere locaties toevoegen op deze steden als ze niet automatisch in de lijst worden weergegeven door ze te importeren uit een CSV-bestand. Als Office-locaties helemaal niet worden weergegeven, kunt u het probleem oplossen door de manier te wijzigen waarop de netwerk afmetingen niet worden weergegeven in plaats van dat u de locatie hier toevoegt. U kunt ook de waarde van het adres van bestaande Office-locaties bijwerken.

Op de locatie van het CSV-bestand aA is de **plaats van**de stad gelabeld en een handmatig toegevoegde locatie van **de locatie wordt**aangeduid

1. Klik in het venster belangrijkste _verbindingen met Microsoft 365_ op het tabblad **locaties** .
1. Klik op de knop **importeren** net boven de lijst met locaties. De flyout **Office-locaties importeren** wordt weergegeven.

   ![Foutbericht over importeren van CSV](../media/m365-mac-perf/m365-mac-perf-import.png)

1. Klik op de koppeling **huidige Office-locaties (. CSV) downloaden** om de lijst huidige locaties te exporteren naar een CSV-bestand en sla het op in de lokale harde schijf. U beschikt nu over een juist opgemaakte CSV waarmee u locaties kunt toevoegen. U kunt de geëxporteerde locaties sluiten. ze worden niet gedupliceerd wanneer u de bijgewerkte CSV-bestanden importeert. Als u het adres van een bestaande locatie wilt wijzigen, wordt dit bijgewerkt wanneer u het CSV-bestand importeert. U kunt het adres van een gevonden stad niet wijzigen.
1. Open het CSV-bestand en voeg uw locaties toe door de volgende velden in te vullen op een nieuwe regel voor elke locatie die u wilt toevoegen. Laat alle andere velden leeg; waarden die u invoert in andere velden, worden genegeerd.
   1. **Adres** (vereist): het fysieke adres van het kantoor
   1. **Breedtegraad** (optioneel): gevuld van Bing Maps lookup, indien leeg
   1. **Lengtegraad** (optioneel): gevuld met Bing Maps lookup, indien leeg
   1. **IP-adresbereiken voor IP-** adresbereiken 1-5 (optioneel): voor elk bereik voert u de naam van het circuit in gevolgd door een lijst met geldige IPv4-of IPv6-adressen die door een spatie zijn gescheiden. Deze waarden worden alleen gebruikt wanneer u SDWAN-integratie hebt ingeschakeld voor een bepaalde Office-locatie.
1. Wanneer u uw Office-locaties hebt toegevoegd en het bestand hebt opgeslagen, klikt u op de knop **Bladeren** naast het veld **voltooid uploaden** en selecteert u het opgeslagen CSV-bestand.
1. Het bestand wordt automatisch gevalideerd. Als er validatiefouten zijn, wordt het foutbericht weergegeven _in het importbestand. Controleer de fouten, corrigeer het importbestand en probeer het opnieuw._ Klik op de koppeling **Open foutgegevens** voor een lijst met specifieke veld validatiefouten.

   ![Foutbericht over importeren van CSV](../media/m365-mac-perf/m365-mac-perf-import-error.png)

1. Als het bestand geen fouten bevat, wordt het bericht weergegeven dat _het rapport klaar is. Er zijn x-locaties gevonden om bij te werken en toe te voegen op x locaties._ Klik op de knop **importeren** om het CSV-bestand te uploaden.

   ![CSV-bericht dat u wilt importeren](../media/m365-mac-perf/m365-mac-perf-import-ready.png)

## <a name="faq"></a>Veelgestelde vragen

### <a name="what-is-a-microsoft-365-service-front-door"></a>Wat is de front cover van de Microsoft 365-service?

De Microsoft 365-service front deur is een toegangspunt voor het globale netwerk van Microsoft waar Office-clients en-services hun netwerkverbinding beëindigen. Voor een optimale netwerkverbinding met Microsoft 365 wordt u aangeraden uw netwerkverbinding te beëindigen met de dichtstbijzijnde Microsoft 365-voor deur in uw stad of metro.

>[!NOTE]
>De Microsoft 365-service voor de voorgrond heeft geen directe relatie met het Azure-service-product voor de voor deur, dat beschikbaar is in de Azure Marketplace.

### <a name="what-is-an-optimal-microsoft-365-service-front-door"></a>Wat is een optimale front cover-service van Microsoft 365.

Een optimale front-service van Microsoft 365 is een service die het meest geschikt is voor uw netwerk uitgang, in het algemeen in het gebied plaats of metro. U kunt de [Microsoft 365 connectiviteitstest](office-365-network-mac-perf-onboarding-tool.md) gebruiken om de locatie te bepalen van uw in-microsoft 365-service en de front-deur voor optimale service. Als het hulpprogramma bepaalt dat de front-in-de voorgrond van uw gebruik optimaal is, maakt u optimaal verbinding met het wereldwijde netwerk van Microsoft.

### <a name="what-is-an-internet-egress-location"></a>Wat is een locatie voor uitgaand Internet?

De locatie voor het uittreden van Internet is de locatie waar uw netwerkverkeer uw Enterprise-netwerk verlaat en verbinding maakt met internet. Dit wordt ook herkend als de locatie waar u een NAT-apparaat (Network Address Translation) hebt en meestal waarbij u verbinding maakt met een internetprovider (ISP). Als u de locatie van uw locatie en de locatie van uw internetverbinding lang ziet, kan dit duiden op een aanzienlijke WAN-backhaul.

## <a name="related-topics"></a>Verwante onderwerpen

[Microsoft 365 Network Insights (preview)](office-365-network-mac-perf-insights.md)

[Microsoft 365-netwerk beoordeling (preview)](office-365-network-mac-perf-score.md)

[Microsoft 365 connectiviteitstest in het M365-Beheercentrum (preview)](office-365-network-mac-perf-onboarding-tool.md)

[Locatie Services voor Microsoft 365-netwerkconnectiviteit](office-365-network-mac-location-services.md)
