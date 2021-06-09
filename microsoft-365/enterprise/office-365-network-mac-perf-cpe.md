---
title: Microsoft 365 weloverwogen netwerkroutering
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/10/2021
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 weloverwogen netwerkroutering
ms.openlocfilehash: 5275f8ea55afaf621555b440e7fae4a6d11cad91
ms.sourcegitcommit: 6e4ddf35aaf747599f476f9988bcef02cacce1b6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/11/2021
ms.locfileid: "50717585"
---
# <a name="microsoft-365-informed-network-routing-preview"></a>Microsoft 365 weloverwogen netwerkroutering (voorbeeld)

Informed Network Routing is een functie waarmee verschillende Microsoft 365-toepassingen worden geïntegreerd met SD-WAN-oplossingen (Software Defined Network) van derden om uw netwerkconnectiviteit met Microsoft-service-eindpunten te optimaliseren en te verbeteren. Geoptimaliseerde SD-WAN-connectiviteit kan leiden tot verbeterde gebruikerservaringen en prestaties.

>[!IMPORTANT]
>Microsoft 365 netwerkroutering is momenteel in de preview-status. Zie voor meer informatie over dit voorbeeld, inclusief richtlijnen voor het ontvangen van hulp, [Microsoft 365 weloverwogen netwerkroutering Openbare preview.](https://go.microsoft.com/fwlink/?linkid=2151565)

## <a name="overview"></a>Overzicht

Informed Network Routing biedt een bi-directioneel kanaal voor het delen van gegevens tussen Microsoft en uw SD-WAN-oplossing. Voor elk kantoorlocatie- en internetcircuit dat u configureert, deelt Microsoft regelmatig feedback met de SD-WAN-oplossing over de kwaliteit van geselecteerde Microsoft 365-toepassingen voor netwerkverkeer dat is gekoppeld aan elk specifiek internetcircuit. Met behulp van deze feedback kan de SD-WAN-oplossing vervolgens slimme herstelacties uitvoeren door het Microsoft 365 door alternatieve beschikbare koppelingen te routeren. 

De kwaliteit van servicedegradaties in het pad van een bepaald internetcircuit, zoals een verhoogde latentie of een hoog pakketverlies, is moeilijk op continue basis te detecteren. Deze verslechteringen kunnen schadelijk zijn voor gebruikerservaringen voor toepassingen zoals Exchange Online, SharePoint, OneDrive en Microsoft Teams. Veelvoorkomende symptomen zijn traag zoeken naar Exchange inhoud, hoge overdrachtstijden bij de interactie met SharePoint of OneDrive documentbibliotheken, of slechte gespreks- of vergaderingskwaliteit in Microsoft Teams.

Het feedback- en herstelmechanisme binnen routering met netwerkgegevens probeert dergelijke problemen in realtime dynamisch te detecteren en informeert de geïmplementeerde SD-WAN-oplossing om automatische herstelacties uit te voeren.

Het kanaal voor het delen van gegevens wordt ook gebruikt om periodiek optische gegevens op netwerkniveau te ontvangen van de SD-WAN-oplossing, inclusief configuratiegegevens en gebruiksstatistieken die zijn gekoppeld aan het apparaat en gekoppelde circuits. Er worden geen persoonlijke gegevens verzameld of opgeslagen. Alle verzamelde gegevens worden samengevoegd naar kantoorlocaties en verbonden internetcircuits. Deze informatie kan Microsoft helpen om gerapporteerde problemen efficiënter en effectiever op te lossen met uw gebruik van Microsoft 365 services en toepassingen.

>[!NOTE]
>Microsoft 365 informed network routing ondersteunt tenants in WW Commercial cloud, maar niet de GCC Moderate, GCC High, DoD, Germany of China clouds.

## <a name="requirements"></a>Vereisten

### <a name="integrated-sd-wan-solutions"></a>Geïntegreerde SD-WAN-oplossingen

Microsoft werkt samen met verschillende partners om integratie met Microsoft 365 netwerkroutering mogelijk te maken. Momenteel ingeschakelde oplossingen zijn onder andere:

| Apparaatmaker | Naam van oplossing | Minimale versie |
| --- | --- | --- |
| Cisco | [IOS XE SD-WAN](https://go.microsoft.com/fwlink/?linkid=2151460) | 20.4/17.4 |

### <a name="network-topology"></a>Netwerktopologie

Netwerkroutering met kennis van zaken identificeert momenteel het verkeer dat is gekoppeld aan een specifieke kantoorlocatie en internetcircuit op basis van het openbare IP-adres dat wordt gebruikt om netwerkverkeer naar Microsoft te verzenden. 

In het geval dat er niet ten minste één netwerkcircuit is dat directe internettoegang biedt op een vestigingslocatie, kan routering met netwerkgegevens geen significante waarde bieden.

### <a name="application-usage"></a>Toepassingsgebruik

Toepassingservaringsgegevens (die worden weergegeven in de metrische netwerkkwaliteit) worden verzameld via het gebruik van specifieke Microsoft-clienttoepassingen. Exchange metrische gegevens geven het gebruik van de Outlook client en sommige Outlook Web App aan. SharePoint en OneDrive geven het gebruik van de tenantspecifieke SharePoint eindpunten aan, ongeacht de clienttoepassing. Teams geeft het gebruik van de Teams desktopclient aan. Ander toepassingsverkeer wordt niet overwogen bij het evalueren van de status van een netwerkcircuit.

## <a name="enabling-informed-network-routing"></a>Weloverwogen netwerkroutering inschakelen

Voor het inschakelen van routering via een geïnformeerd netwerk zijn meerdere stappen vereist, waarvan sommige moeten worden uitgevoerd binnen de configuratie-interface van uw SD-WAN-oplossing. Raadpleeg uw leverancier van SD-WAN-oplossingen voor instructies over het starten van het proces voor het inschakelen van routering op basis van netwerkgegevens binnen de SD-WAN-oplossing voordat u verder gaat met de configuratie in het Microsoft 365 beheercentrum.

Nadat u klaar bent om routering van een geïnformeerd netwerk in te Microsoft 365 het beheercentrum, controleert u of u over de benodigde globale beheerdersmachtigingen bent.

>[!IMPORTANT]
>Als u toestemming wilt geven voor de vereiste machtigingen voor toepassingen op tenantniveau voor de geselecteerde SD-WAN-oplossing om toegang te krijgen tot het kanaal voor het routeren van gegevens op basis van een netwerk, moet u de volgende stappen uitvoeren als globale beheerder.


### <a name="step-1-open-sd-wan-solution-configuration-options"></a>Stap 1: Configuratieopties voor SD-WAN-oplossing openen

Selecteer in [Microsoft 365 beheercentrum](https://admin.microsoft.com/)de optie **> Netwerkconnectiviteit** in het linkernavigatiedeelvenster.

In dit gedeelte van het beheercentrum vindt u statistische netwerkconnectiviteitsgegevens voor uw organisatie en richtlijnen voor het verbeteren van uw connectiviteit. Zie [Netwerkconnectiviteit in het Microsoft 365 -beheercentrum (preview)](office-365-network-mac-perf-overview.md) voor meer informatie over deze functies die beschikbaar zijn in het beheercentrum.

Selecteer **Instellingen > SD-WAN-oplossing om** het configuratievenster voor netwerkroutering met informatie te openen. De andere opties  die onder Instellingen worden weergegeven, zijn van toepassing op de algemene richtlijnen voor netwerkconnectiviteit in het beheercentrum en zijn niet vereist voor het inschakelen van netwerkroutering met kennis van informatie.

Selecteer in het configuratiedeelvenster **De SD-WAN-oplossing toevoegen (Preview).**

### <a name="step-2-select-your-sd-wan-solution-and-data-storage-location"></a>Stap 2: Selecteer uw SD-WAN-oplossing en locatie voor gegevensopslag

Selecteer in de vervolgkeuzevakken de SD-WAN-oplossing die u hebt geïmplementeerd en de locatie waar u de gegevens wilt laten opslaan die aan routering met netwerkinformatie zijn gekoppeld. Zie de [sectie Gegevensopslag](#data-storage) voor meer informatie.

Selecteer **Volgende**.

### <a name="step-3-accept-terms-for-sharing-of-data"></a>Stap 3: Voorwaarden voor het delen van gegevens accepteren

Lees de opgegeven voorwaarden voor het delen van gegevens tussen Microsoft en de geselecteerde SD-WAN-oplossing zorgvuldig en bevestig deze en schakel het aangegeven selectievakje in.

Selecteer **Volgende**.

### <a name="step-4-grant-permissions-to-the-sd-wan-solution"></a>Stap 4: Machtigingen verlenen voor de SD-WAN-oplossing

Met deze stap wordt een machtigingsaanvraag gestart met Azure Active Directory (Azure AD). U wordt gevraagd om machtigingen op tenantniveau toe te staan waarmee uw geselecteerde SD-WAN-oplossing toegang heeft tot de gegevensopslag van de weloverwogen netwerkroutering en de service-statusgegevens die aan uw tenant zijn gekoppeld. Voor deze actie zijn globale beheerdersrolmachtigingen vereist.

Selecteer de **koppeling Machtiging geven voor deze toepassing** en volg de Azure AD-aanvragen.

Nadat u de machtigingen hebt verleend, selecteert u **Volgende.**

### <a name="step-5-confirm-your-configuration-settings"></a>Stap 5: Uw configuratie-instellingen bevestigen

De laatste stap in het inschakelen van netwerkroutering voor uw tenant is een bevestigingspagina met de instellingen die u hebt opgegeven. 

Netwerkroutering met informatie is nu ingeschakeld voor uw tenant.

Selecteer **Klaar** en sluit het configuratiedeelvenster van de SD-WAN-oplossing.

## <a name="configuring-network-informed-routing"></a>Routering met informatie over netwerken configureren

U voert een groot deel van de configuratie uit voor een weloverwogen netwerkroutering binnen uw SD-WAN-oplossing, zoals het configureren van de manier waarop uw verkeer moet worden gerouteerd onder normale omstandigheden en de alternatieve paden die moeten worden gebruikt als er problemen worden gedetecteerd. Raadpleeg uw SD-WAN-oplossingsprovider voor meer informatie over deze configuratiestappen.

Elke kantoorlocatie moet worden geconfigureerd in het Microsoft 365-beheercentrum, zodat met een goed geïnformeerde netwerkroutering het verkeer kan worden gevonden dat is gekoppeld aan de netwerkcircuits die verbinding bieden met deze locaties.

Office locaties kunnen automatisch worden gedetecteerd als onderdeel van de lopende verzameling netwerk-telemetrie van Microsoft. Hierdoor zijn sommige locaties mogelijk vooraf ingevuld in het beheercentrum voor uw tenant. 

Als deze locaties nauwkeurig zijn, moet u alleen de functie voor het routeren van het netwerk met kennis van informatie voor elke gewenste locatie inschakelen en de internetcircuits en hun openbare IP-adressen configureren. 

Als de automatisch gedetecteerde locaties niet nauwkeurig zijn of er geen locaties zijn die vooraf zijn ingevuld in uw tenant, moet u locaties handmatig toevoegen of bewerken om een nauwkeurige topologie van uw organisatie weer te geven.

### <a name="updating-locations"></a>Locaties bijwerken

Locaties voor uw tenant vindt u op het **tabblad** Locaties. Locaties kunnen rechtstreeks in de lijst worden bewerkt of worden bijgewerkt met een CSV-bestand.

Zorg ervoor dat elke kantoorlocatie waar u netwerkroutering met kennis van zaken wilt inschakelen, aanwezig is in deze lijst.

>[!NOTE]
>De kolommen in de lijst **Locaties** voor verzamelde steekproeven en andere beoordelingsgerelateerde informatie zijn niet gerelateerd aan de functie voor netwerkroutering met informatie.

### <a name="enabling-a-location-for-informed-network-routing"></a>Een locatie inschakelen voor netwerkroutering met kennis van informatie

1. Selecteer bewerken in **de** lijst Locaties **in** het menu Snelle acties om het configuratievenster voor de locatie te openen.

2. Selecteer **Gebruik Microsoft 365 netwerkroutering op deze locatie**.

3. Voeg alle netwerkcircuits toe die internetconnectiviteit bieden aan deze office-locatie in de ip-adresbereiken van **Egress op deze office-locatiesectie.** Controleer of elk circuit is gekoppeld aan de unieke openbare IP-adressubnetten die uw netwerkverkeer vertegenwoordigen.

4. Selecteer **Opslaan** om de wijzigingen op te slaan.

## <a name="disabling-network-informed-routing"></a>Routering met netwerkgegevens uitschakelen

De routeringsfunctie voor geïnformeerde netwerken kan voor de hele tenant worden uitgeschakeld door de instellingen voor de SD-WAN-oplossing opnieuw in te passen. Hoewel hiermee de verwerking van gegevens binnen de Microsoft 365 wordt gestopt, moet u ook routering met netwerkinformatie uitschakelen in het beheercentrum.

### <a name="step-1-open-sd-wan-solution-configuration-options"></a>Stap 1: Configuratieopties voor SD-WAN-oplossing openen

Selecteer in [Microsoft 365 beheercentrum](https://admin.microsoft.com/) **Health > Netwerkconnectiviteit** in het linkernavigatiedeelvenster.

Selecteer **Instellingen > SD-WAN-oplossing om** het configuratievenster voor netwerkroutering met informatie te openen.

In het configuratiedeelvenster ziet u een overzicht van de momenteel geconfigureerde SD-WAN-oplossing.

### <a name="step-2-reset-your-configuration"></a>Stap 2: Uw configuratie opnieuw instellen

Selecteer in het configuratiedeelvenster **De instellingen voor de SD-WAN-oplossing opnieuw instellen.**

Uw instellingen zijn nu opnieuw ingesteld en netwerkroutering met informatie is uitgeschakeld. U kunt de functie op elk moment opnieuw inschakelen door de stappen te volgen in [Het routeren van een netwerk met informatie inschakelen.](#enabling-informed-network-routing)

## <a name="data-storage"></a>Gegevensopslag

Gegevens die tussen Microsoft en de SD-WAN-oplossingsprovider worden uitgewisseld, worden opgeslagen op de locatie voor gegevensopslag die is geselecteerd tijdens de eerste enablement van routering met netwerkinformatie. De opties voor gegevensopslag vertegenwoordigen geografische gebieden met Microsoft Azure regio's waar de gegevens zijn opgeslagen.

>[!NOTE]
>Tijdens de preview-fase is de enige beschikbare locatie voor gegevensopslag **Noord-Amerika.** Er komen extra locaties voor gegevensopslag beschikbaar vóór de algemene beschikbaarheid van netwerkroutering met kennis van informatie.

Gegevens worden maximaal 30 dagen op deze locatie bewaard. Wanneer deze is uitgeschakeld, worden alle resterende gegevens verwijderd in dit bewaarvenster van 30 dagen.

## <a name="related-topics"></a>Verwante onderwerpen

[Netwerkconnectiviteit in het Microsoft 365 beheercentrum (voorbeeld)](office-365-network-mac-perf-overview.md)

[Microsoft 365 Network Connectivity Location Services (preview)](office-365-network-mac-location-services.md)
