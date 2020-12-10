---
title: Microsoft 365 bedacht netwerkroutering
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 1/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 bedacht netwerkroutering
ms.openlocfilehash: 40b4345ca80c5e90a07583b83b82368d4a35535a
ms.sourcegitcommit: 039205fdaaa2a233ff7e95cd91bace474b84b68c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611434"
---
# <a name="microsoft-365-informed-network-routing-preview"></a>Microsoft 365 gefundeerde netwerkroutering (preview)

Gefundeerde netwerkroutering is een functie waarmee diverse Microsoft 365-toepassingen worden geïntegreerd met software van de door software gedefinieerde netwerkclient (SD-WAN) om de netwerkverbinding met Microsoft-service-eindpunten te optimaliseren en te verbeteren. Geoptimaliseerde SD-WAN-verbinding kan leiden tot betere gebruikerservaringen en prestaties.

>[!IMPORTANT]
>Microsoft 365 gefundeerde netwerkroutering wordt momenteel geopend in de preview-status. Zie [Microsoft 365 met de openbare preview-versie van netwerkroutering](https://go.microsoft.com/fwlink/?linkid=2151565)voor meer informatie over deze preview-versie.

## <a name="overview"></a>Overzicht

Gefundeerde netwerkroutering biedt een bi-directioneel kanaal voor het delen van gegevens tussen Microsoft en uw SD-WAN-oplossing. Voor elke Office-locatie en Internet circuit die u configureert, deelt Microsoft periodiek de feedback met de SD-WAN-oplossing op de kwaliteit van de geselecteerde Microsoft 365-toepassings ervaringen voor netwerkverkeer dat is gekoppeld aan elk specifiek Internet circuit. Door deze feedback te gebruiken, kan de SD-WAN-oplossing vervolgens slim herstelacties uitvoeren door Microsoft 365-toepassings verkeer te routeren via alternatieve beschikbare koppelingen. 

Kwaliteitsbeoordeling van de service in het pad van een bepaald Internet circuit, zoals een langere latentie of een hoog pakketverlies, is moeilijk te detecteren. Deze degrading kan nadelig zijn voor gebruikerservaring voor toepassingen zoals Exchange Online, SharePoint, OneDrive en Microsoft teams. Veelvoorkomende problemen zijn van invloed op de trage zoekfunctie van Exchange-inhoud, hoge overdrachts tijden wanneer u werkt met SharePoint-of OneDrive-documentbibliotheken of een slechte oproep of vergaderings kwaliteit in Microsoft teams.

Het feedback-en herstel mechanisme in netwerk gerichte routerings gerichte routering zoekt naar dynamische detectie van dergelijke problemen in vrijwel realtime en informeert de geïmplementeerde SD-oplossing voor het automatisch herstellen van acties.

Het kanaal voor het delen van gegevens wordt ook gebruikt om periodiek gegevens op netwerkniveau te ontvangen van de SD-WAN-oplossing, waaronder configuratiegegevens en gebruiksstatistieken die zijn gekoppeld aan het apparaat en gekoppelde circuits. Er worden geen persoonlijke gegevens verzameld of opgeslagen. Alle verzamelde gegevens worden geaggregeerd naar Office-locaties en verbonden Internet circuits. Met deze informatie kunnen Microsoft efficiënt en effectief gerapporteerde problemen met uw gebruik van Microsoft 365-Services en-toepassingen helpen oplossen.

>[!NOTE]
>Microsoft 365 gefundeerde netwerkroutering ondersteunt tenants in de commerciële cloud van de Cloud, maar niet de GCC op GCC hoog, DoD, Duitsland of China.

## <a name="requirements"></a>Vereisten

### <a name="integrated-sd-wan-solutions"></a>Geïntegreerde SD-WAN-oplossingen

Microsoft werkt samen met diverse partners om integratie met Microsoft 365 gefundeerde netwerkroutering te activeren. Momenteel zijn de volgende oplossingen beschikbaar:

| Device maker | Naam oplossing | Minimum versie |
| --- | --- | --- |
| Verwijzen | [IOS XE SD-WAN](https://go.microsoft.com/fwlink/?linkid=2151460) | 20.4/17.4 |

### <a name="network-topology"></a>Netwerktopologie

Gefundeerde netwerkroutering identificeert momenteel verkeer dat is gekoppeld aan een specifieke kantoorlocatie en Internet circuit op basis van het openbare IP-adres dat wordt gebruikt voor het verzenden van netwerkverkeer naar Microsoft. 

In het geval waarbij er niet minimaal één netwerkcircuit beschikbaar is om rechtstreeks Internet toegang te bieden op een vertakkings locatie, kan het netwerk met een gefundeerde routering mogelijk geen significante waarde leveren.

### <a name="application-usage"></a>Toepassingsgebruik

Data-ervarings gegevens worden verzameld via Microsoft Outlook op apparaten met Windows, teams, SharePoint en OneDrive. U wordt niet gekeken naar de status van een netwerkcircuit wanneer u de status van een netwerkcircuit evalueert.

## <a name="enabling-informed-network-routing"></a>Gefundeerde netwerkroutering inschakelen

Voor het inschakelen van de gefundeerde netwerkroutering zijn meerdere stappen nodig, wat moet plaatsvinden binnen de configuratie-interface van uw SD-WAN-oplossing. Neem contact op met de SD-oplossing leverancier voor instructies over het inschakelen van het proces voor het inschakelen van netwerk gerichte routering binnen de SD-WAN-oplossing voordat u verdergaat met de configuratie in het Microsoft 365-Beheercentrum.

Wanneer u klaar bent om in het Microsoft 365-Beheercentrum gefundeerde netwerkroutering te activeren, moet u beschikken over de benodigde machtigingen voor een globale beheerder.

>[!IMPORTANT]
>U moet de volgende stappen uitvoeren als globale beheerder als u de machtigingen voor de benodigde toepassingen voor de tenantniveau wilt gebruiken voor de geselecteerde SD-WAN-oplossing voor het gefundeerde kanaal voor het delen van gegevens.


### <a name="step-1-open-sd-wan-solution-configuration-options"></a>Stap 1: Open de configuratieopties voor de SD-WAN-oplossing

Selecteer in het [Microsoft 365-Beheercentrum](https://admin.microsoft.com/) **status > netwerkverbinding** in het navigatiedeelvenster aan de linkerkant.

Dit gedeelte van het Beheercentrum biedt een geaggregeerde metrische netwerk verbindings metriek voor uw organisatie en richtlijnen voor het verbeteren van de connectiviteit. Zie [netwerkverbinding in het Microsoft 365-Beheercentrum (preview)](office-365-network-mac-perf-overview.md) voor meer informatie over de functies die beschikbaar zijn in het Beheercentrum.

Selecteer **instellingen > SD-WAN-oplossing** om het bedachte configuratie deelvenster netwerkroutering te openen. De andere opties die worden weergegeven onder **instellingen** zijn van toepassing op de algemene richtlijnen voor netwerkverbindingen in het Beheercentrum en zijn niet verplicht om geïnformeerde netwerkroutering in te schakelen.

Selecteer in het deelvenster configuratie **de optie uw SD-WAN-oplossing toevoegen (preview)**.

### <a name="step-2-select-your-sd-wan-solution-and-data-storage-location"></a>Stap 2: Selecteer de SD-WAN-oplossing en de opslaglocatie van de gegevens

Selecteer in de vervolgkeuzelijsten de SD-WAN-oplossing die u hebt geïmplementeerd en de locatie waar u de gegevens die zijn gekoppeld aan het netwerk, zijn gerouteerde routering wilt opslaan. Zie de sectie [gegevensopslag](#data-storage) voor aanvullende informatie.

Selecteer **Volgende**.

### <a name="step-3-accept-terms-for-sharing-of-data"></a>Stap 3: voorwaarden voor het delen van gegevens accepteren

Lees de meegeleverde voorwaarden die zijn gekoppeld aan gegevens delen tussen Microsoft en de geselecteerde SD-WAN-oplossing aandachtig door en selecteer het aangegeven selectievakje.

Selecteer **Volgende**.

### <a name="step-4-grant-permissions-to-the-sd-wan-solution"></a>Stap 4: machtigingen toewijzen aan de SD-WAN-oplossing

Met deze stap wordt een aanvraag voor machtigingen verlening gestart met Azure Active Directory (Azure AD). U wordt gevraagd om machtigingen op tenantniveau te verlenen waarmee de door u geselecteerde SD-WAN-oplossing toegang kan worden verleend tot de begeleide netwerk routeringsgegevens opslag en de informatie over de servicestatus die is gekoppeld aan uw Tenant. Voor deze actie zijn globale machtigingen voor rollen beheerders vereist.

Selecteer de koppeling **machtigingen verlenen aan deze toepassing** en volg de verzoeken van Azure AD.

Wanneer u klaar bent met de machtiging, selecteert u **volgende**.

### <a name="step-5-confirm-your-configuration-settings"></a>Stap 5: uw configuratie-instellingen bevestigen

De laatste stap voor het inschakelen van netwerk met routering voor uw Tenant is een bevestigingspagina waarop de instellingen worden weergegeven die u hebt opgegeven. 

Gefundeerde netwerkroutering is nu ingeschakeld voor uw Tenant.

Selecteer **gereed** en sluit vervolgens het configuratievenster van de SD-WAN-oplossing.

## <a name="configuring-network-informed-routing"></a>Netwerk met Routering gefundeerd configureren

U voert veel van de configuratie uit voor het doorsturen van netwerkroutering binnen uw SD-WAN-oplossing, zoals het configureren van het verkeer onder normale omstandigheden, en de alternatieve paden die moeten worden gebruikt als er problemen worden gedetecteerd. Neem contact op met uw SD-WAN-oplossing voor informatie over deze configuratiestappen.

Elke Office-locatie moet worden geconfigureerd in het Microsoft 365-Beheercentrum, zodat de gefundeerde netwerkroutering op de juiste manier kan worden geïdentificeerd aan de netwerk circuits die verbinding maken met deze locaties.

Office-locaties kunnen automatisch worden gedetecteerd als onderdeel van Microsoft continue verzameling van netwerktelemetry. Daarom kunnen sommige locaties vooraf worden ingevuld in het Beheercentrum voor uw Tenant. 

Als deze locaties kloppen, moet u de gefundeerde functie voor netwerkroutering inschakelen voor elke gewenste locatie en de Internet circuits en hun openbare IP-adressen configureren. 

Als de automatische locaties niet kloppen of als uw Tenant geen locaties heeft ingevuld, moet u locaties handmatig toevoegen of bewerken om de juiste topologie van uw organisatie weer te geven.

### <a name="updating-locations"></a>Locaties bijwerken

Locaties voor de Tenant vindt u op het tabblad **locaties** . Locaties kunnen rechtstreeks in de lijst worden bewerkt of bijgewerkt met een CSV-bestand.

Zorg ervoor dat elke kantoorlocatie waarop u gefundeerde netwerkroutering beschikbaar wilt maken in deze lijst staat.

>[!NOTE]
>De kolommen in de lijst met **locaties** voor steekproeven die zijn verzameld en andere informatie over de beoordeling, zijn niet gekoppeld aan de beschikbare functie voor netwerkroutering.

### <a name="enabling-a-location-for-informed-network-routing"></a>Een locatie voor de gefundeerde netwerkroutering inschakelen

1. Selecteer in de lijst **locaties** de optie **bewerken** in het menu snelle acties om het deelvenster locatie configuratie te openen.

2. Selecteer **op deze locatie Microsoft 365 met de gefundeerde netwerkroutering**.

3. Voeg alle netwerk circuits toe die verbinding bieden met de Internet locatie in de sectie IP-adresbereiken voor het **aflossen van deze Office-locatie** . Zorg ervoor dat elk circuit gekoppeld is aan de unieke subnetten met unieke IP-adressen voor uw netwerkverkeer.

4. Selecteer **Opslaan** om uw wijzigingen op te slaan.

## <a name="disabling-network-informed-routing"></a>Netwerk met gefundeerde routering uitschakelen

De gefundeerde functie voor netwerkroutering is mogelijk uitgeschakeld voor de volledige Tenant door de instellingen voor de SD-WAN-oplossing opnieuw in te stellen. Wanneer u alle gegevensverwerking binnen Microsoft 365 stopt, moet u ook netwerkverkeer op de hoogte stellen binnen het Beheercentrum.

### <a name="step-1-open-sd-wan-solution-configuration-options"></a>Stap 1: Open de configuratieopties voor de SD-WAN-oplossing

Selecteer in het [Microsoft 365-Beheercentrum](https://admin.microsoft.com/) **status > netwerkverbinding** in het navigatiedeelvenster aan de linkerkant.

Selecteer **instellingen > SD-WAN-oplossing** om het bedachte configuratie deelvenster netwerkroutering te openen.

In het configuratievenster ziet u een overzicht van de momenteel geconfigureerde SD-WAN-oplossing.

### <a name="step-2-reset-your-configuration"></a>Stap 2: de configuratie opnieuw instellen

Selecteer in het deelvenster configuratie de optie **de instellingen van uw SD-WAN-oplossing opnieuw instellen**.

Uw instellingen zijn nu opnieuw ingesteld en de gefundeerde netwerkroutering is uitgeschakeld. U kunt de optie op elk gewenst moment weer inschakelen door de stappen te volgen in genodigde [netwerkroutering inschakelen](#enabling-informed-network-routing).

## <a name="data-storage"></a>Gegevensopslag

Uitwisseling van gegevens tussen Microsoft en de SD-WAN solution provider wordt opgeslagen op de opslaglocatie voor gegevens die is geselecteerd tijdens de eerste activering van een netwerk gerichte routering. De opties voor gegevensopslag locatie vertegenwoordigen geografische gebieden met Microsoft Azure-gebieden waar de gegevens zijn opgeslagen.

>[!NOTE]
>Tijdens de preview-fase is de enige beschikbare opslaglocatie voor gegevensopslag **Noord-Amerika**. Extra opslaglocaties voor gegevens worden beschikbaar vóór de algemene beschikbaarheid van netwerkroutering.

Gegevens blijven gedurende 30 dagen op deze locatie bewaard. Indien uitgeschakeld, worden alle overige gegevens verwijderd binnen dit Bewaar venster van 30 dagen.

## <a name="related-topics"></a>Verwante onderwerpen

[Netwerkverbinding in het Microsoft 365-Beheercentrum (preview)](office-365-network-mac-perf-overview.md)

[Locatie Services voor Microsoft 365-netwerkconnectiviteit](office-365-network-mac-location-services.md)
