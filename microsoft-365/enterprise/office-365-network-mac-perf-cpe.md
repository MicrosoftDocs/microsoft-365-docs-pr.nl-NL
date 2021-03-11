---
title: Goed geïnformeerde netwerkroutering in Microsoft 365
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
description: Goed geïnformeerde netwerkroutering in Microsoft 365
ms.openlocfilehash: 5275f8ea55afaf621555b440e7fae4a6d11cad91
ms.sourcegitcommit: 6e4ddf35aaf747599f476f9988bcef02cacce1b6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/11/2021
ms.locfileid: "50717585"
---
# <a name="microsoft-365-informed-network-routing-preview"></a>Microsoft 365 geïnformeerde netwerkroutering (preview)

Goed geïnformeerde netwerkroutering is een functie waarmee verschillende Microsoft 365-toepassingen worden geïntegreerd met door derden gedefinieerde netwerkoplossingen (SD-WAN) om de netwerkverbinding met service-eindpunten van Microsoft te optimaliseren en te verbeteren. Geoptimaliseerde SD-WAN-connectiviteit kan resulteren in betere gebruikerservaringen en prestaties.

>[!IMPORTANT]
>Routering via een netwerk met microsoft 365-informatie is momenteel in preview-status. Zie Voor meer informatie over deze preview, inclusief richtlijnen voor het ontvangen van hulp, de openbare preview-versie van [het Microsoft 365-netwerk routeren.](https://go.microsoft.com/fwlink/?linkid=2151565)

## <a name="overview"></a>Overzicht

Goed geïnformeerde netwerkroutering biedt een bi directioneel kanaal voor het delen van gegevens tussen Microsoft en uw SD-WAN-oplossing. Voor elk kantoorlocatie en internetcircuit dat u configureert, deelt Microsoft periodiek feedback met de SD-WAN-oplossing over de kwaliteit van geselecteerde Microsoft 365-toepassingservaringen voor netwerkverkeer dat is gekoppeld aan elk specifiek internetcircuit. Op basis van deze feedback kan de SD-WAN-oplossing vervolgens slimme herstelacties uitvoeren door Microsoft 365-toepassingsverkeer te routeren via alternatieve beschikbare koppelingen. 

De kwaliteit van de service gaat voortdurend verloren in het pad van een bepaald internetcircuit, zoals een grotere latentie of hoog pakketverlies. Deze degradaties zijn mogelijk schadelijke gebruikerservaringen voor toepassingen zoals Exchange Online, SharePoint, OneDrive en Microsoft Teams. Veelvoorkomende symptomen zijn traag zoeken naar Exchange-inhoud, hoge overdrachtstijden bij interactie met Documentbibliotheken van SharePoint of OneDrive, of slechte gespreks- of vergaderingskwaliteit in Microsoft Teams.

Met het feedback- en herstelmechanisme in routering die is geïnformeerd over een netwerk, wordt gezocht naar het dynamisch detecteren van dergelijke problemen in realtime en wordt de geïmplementeerde SD-WAN-oplossing geïnformeerd om automatische herstelacties uit te voeren.

Het kanaal voor gegevensdeling wordt ook regelmatig gebruikt om op netwerkniveau optiekgegevens van de SD-WAN-oplossing te ontvangen, inclusief configuratiegegevens en gebruiksstatistieken die zijn gekoppeld aan het apparaat en gekoppelde circuits. Er worden geen persoonlijke gegevens verzameld of opgeslagen. Alle verzamelde gegevens worden samengevoegd naar kantoorlocaties en verbonden internetcircuits. Met deze informatie kan Microsoft gerapporteerde problemen met uw gebruik van Microsoft 365-services en -toepassingen efficiënter en effectiever oplossen.

>[!NOTE]
>Routering via een geïnformeerd Microsoft 365-netwerk ondersteunt tenants in de commerciële cloud van WW, maar niet de GCC Moderate, GCC High, DoD, Germany of China clouds.

## <a name="requirements"></a>Vereisten

### <a name="integrated-sd-wan-solutions"></a>Geïntegreerde SD-WAN-oplossingen

Microsoft werkt samen met verschillende partners om integratie met routering met goed geïnformeerde microsoft 365-netwerken mogelijk te maken. De volgende oplossingen zijn momenteel ingeschakeld:

| Device Maker | Naam van oplossing | Minimale versie |
| --- | --- | --- |
| Cisco | [IOS XE SD-WAN](https://go.microsoft.com/fwlink/?linkid=2151460) | 20.4/17.4 |

### <a name="network-topology"></a>Netwerktopologie

Een goed geïnformeerde netwerkroutering identificeert momenteel verkeer dat is gekoppeld aan een specifieke kantoorlocatie en een bepaald internetcircuit op basis van het openbare IP-adres dat wordt gebruikt om netwerkverkeer naar Microsoft te verzenden. 

In het geval dat er niet ten minste één netwerkcircuit is dat directe internettoegang biedt op een vertakkingslocatie, levert routering met informatie over het netwerk mogelijk geen belangrijke waarde op.

### <a name="application-usage"></a>Toepassingsgebruik

Gegevens over de toepassingservaring (weergegeven door de metrische netwerkkwaliteit) worden verzameld via het gebruik van specifieke Microsoft-clienttoepassingen. Exchange-metrische gegevens geven het gebruik van de Outlook-client en een deel van het gebruik van Outlook Web App weer. SharePoint- en OneDrive-meetwaarden geven het gebruik van tenantspecifieke SharePoint-eindpunten weer, ongeacht de clienttoepassing. De metrische gegevens in Teams geven het gebruik van de Teams-bureaubladclient weer. Ander toepassingsverkeer wordt niet overwogen bij het evalueren van de status van een netwerkcircuit.

## <a name="enabling-informed-network-routing"></a>Goed geïnformeerde netwerkroutering inschakelen

Voor het inschakelen van goed geïnformeerde netwerkroutering zijn meerdere stappen vereist, waarvan sommige moeten worden uitgevoerd binnen de configuratie-interface van uw SD-WAN-oplossing. Raadpleeg uw leverancier van SD-WAN-oplossingen voor hulp bij het inschakelen van routering via een netwerk binnen de SD-WAN-oplossing voordat u doorgaat met de configuratie in het Microsoft 365-beheercentrum.

Wanneer u klaar bent om geïnformeerde netwerkroutering in teschakelen in het Microsoft 365-beheercentrum, controleert u of u de benodigde machtigingen voor globale beheerders hebt.

>[!IMPORTANT]
>Als u de benodigde machtigingen voor toepassingen op tenantniveau wilt verlenen voor de geselecteerde SD-WAN-oplossing voor toegang tot het kanaal voor goed geïnformeerde netwerkroutering, moet u als globale beheerder de volgende stappen uitvoeren.


### <a name="step-1-open-sd-wan-solution-configuration-options"></a>Stap 1: Configuratieopties voor SD-WAN-oplossing openen

Selecteer in [het Microsoft 365-beheercentrum](https://admin.microsoft.com/) **> netwerkconnectiviteit** in het navigatiedeelvenster aan de linkerkant.

Deze sectie van het beheercentrum bevat statistieken over geaggregeerde netwerkconnectiviteit voor uw organisatie en richtlijnen voor het verbeteren van uw connectiviteit. Zie [Netwerkconnectiviteit in het Microsoft 365-beheercentrum (preview)](office-365-network-mac-perf-overview.md) voor meer informatie over deze functies die beschikbaar zijn in het beheercentrum.

Selecteer **Instellingen > SD-WAN-oplossing om** het configuratiedeelvenster voor goed geïnformeerde netwerkroutering te openen. De andere opties die worden weergegeven onder **Instellingen,** zijn van toepassing op de algemene richtlijnen voor netwerkconnectiviteit in het beheercentrum en zijn niet vereist om goed geïnformeerde netwerkroutering in te stellen.

Selecteer uw **SD-WAN-oplossing (Preview)** toevoegen in het configuratiedeelvenster.

### <a name="step-2-select-your-sd-wan-solution-and-data-storage-location"></a>Stap 2: Uw SD-WAN-oplossing en gegevensopslaglocatie selecteren

Selecteer in de vervolgkeuzelijst de SD-WAN-oplossing die u hebt geïmplementeerd en de locatie waar u de gegevens die zijn gekoppeld aan routering met een goede netwerkinformatie wilt opslaan. Zie de [sectie gegevensopslag](#data-storage) voor meer informatie.

Selecteer **Volgende**.

### <a name="step-3-accept-terms-for-sharing-of-data"></a>Stap 3: Voorwaarden accepteren voor het delen van gegevens

Lees en bevestig zorgvuldig de voorwaarden die zijn gekoppeld aan het delen van gegevens tussen Microsoft en uw geselecteerde SD-WAN-oplossing en schakel het aangegeven selectievakje in.

Selecteer **Volgende**.

### <a name="step-4-grant-permissions-to-the-sd-wan-solution"></a>Stap 4: Machtigingen verlenen aan de SD-WAN-oplossing

Met deze stap start u een aanvraag voor het verlenen van machtigingen met Azure Active Directory (Azure AD). U wordt gevraagd machtigingen op tenantniveau te verlenen waarmee uw geselecteerde SD-WAN-oplossing toegang heeft tot de gegevensopslag op een goed geïnformeerde netwerkroutering en de service statusinformatie die is gekoppeld aan uw tenant. Voor deze actie zijn globale beheerdersrolmachtigingen vereist.

Selecteer de **koppeling Machtiging geven voor deze toepassing** en volg de Azure AD-aanvragen.

Wanneer u de machtigingen hebt voltooid, selecteert u **Volgende.**

### <a name="step-5-confirm-your-configuration-settings"></a>Stap 5: De configuratie-instellingen bevestigen

De laatste stap bij het inschakelen van routering via een netwerk voor uw tenant is een bevestigingspagina met de instellingen die u hebt opgegeven. 

Goed geïnformeerde netwerkroutering is nu ingeschakeld voor uw tenant.

Selecteer **Klaar en** sluit het configuratiedeelvenster van de SD-WAN-oplossing.

## <a name="configuring-network-informed-routing"></a>Routering met informatie over het netwerk configureren

U voert een groot deel van de configuratie uit voor goed geïnformeerde netwerkroutering binnen uw SD-WAN-oplossing, zoals het configureren van hoe uw verkeer in de normale omstandigheden moet worden gerouteerd en de alternatieve paden die moeten worden gebruikt als er problemen worden gedetecteerd. Neem contact op met uw SD-WAN-oplossingsprovider voor meer informatie over deze configuratiestappen.

Elke kantoorlocatie moet worden geconfigureerd in het Microsoft 365-beheercentrum, zodat een goed geïnformeerde netwerkroutering het verkeer kan identificeren dat is gekoppeld aan de netwerkcircuits die verbinding bieden met deze locaties.

Office-locaties kunnen automatisch worden gedetecteerd als onderdeel van de door Microsoft lopende verzameling netwerk telemetrie. Hierdoor zijn sommige locaties mogelijk vooraf ingevuld in het beheercentrum voor uw tenant. 

Als deze locaties correct zijn, hoeft u alleen de functie voor geïnformeerde netwerkroutering in teschakelen voor elke gewenste locatie en de internetcircuits en de openbare IP-adressen te configureren. 

Als de automatisch gedetecteerde locaties niet nauwkeurig zijn of als er geen locaties in uw tenant vooraf zijn ingevuld, moet u locaties handmatig toevoegen of bewerken om een nauwkeurige topologie van uw organisatie weer te geven.

### <a name="updating-locations"></a>Locaties bijwerken

Locaties voor uw tenant vindt u op het **tabblad** Locaties. Locaties kunnen rechtstreeks in de lijst worden bewerkt of bijgewerkt met een CSV-bestand.

Zorg ervoor dat elke kantoorlocatie waar u geïnformeerde netwerkroutering wilt inschakelen in deze lijst staat.

>[!NOTE]
>De kolommen in de **lijst Locaties** voor verzamelde voorbeelden en andere proefgerelateerde gegevens hebben geen verband met de functie voor goed geïnformeerde netwerkroutering.

### <a name="enabling-a-location-for-informed-network-routing"></a>Een locatie inschakelen voor goed geïnformeerde netwerkroutering

1. Selecteer Bewerken **in**  het menu Snelle acties in de lijst Locaties om het configuratievenster voor de locatie te openen.

2. Selecteer **Routering via een microsoft 365-netwerk met informatie op deze locatie.**

3. Voeg alle netwerkcircuits met internetconnectiviteit toe aan deze kantoorlocatie in de sectie Met IP-adresbereiken voor dit **kantoor.** Controleer of elk circuit is gekoppeld aan de unieke openbare IP-adressubnetten die uw netwerkverkeer vertegenwoordigen.

4. Selecteer **Opslaan** om de wijzigingen op te slaan.

## <a name="disabling-network-informed-routing"></a>Routering met goed geïnformeerd netwerk uitschakelen

De functie voor goed geïnformeerde netwerkroutering kan voor de hele tenant worden uitgeschakeld door de instellingen van uw SD-WAN-oplossing opnieuw in te passen. Hoewel hiermee de verwerking van gegevens in Microsoft 365 wordt gestopt, moet u ook routering met informatie over het netwerk uitschakelen in het beheercentrum.

### <a name="step-1-open-sd-wan-solution-configuration-options"></a>Stap 1: Configuratieopties voor SD-WAN-oplossing openen

Selecteer in [het Microsoft 365-beheercentrum](https://admin.microsoft.com/) > **netwerkconnectiviteit** in het navigatiedeelvenster aan de linkerkant.

Selecteer **Instellingen > SD-WAN-oplossing om** het configuratiedeelvenster voor goed geïnformeerde netwerkroutering te openen.

In het configuratiedeelvenster wordt een overzicht weergegeven van uw momenteel geconfigureerde SD-WAN-oplossing.

### <a name="step-2-reset-your-configuration"></a>Stap 2: De configuratie opnieuw instellen

Selecteer in het configuratiedeelvenster **De instellingen van uw SD-WAN-oplossing opnieuw instellen.**

Uw instellingen zijn nu opnieuw ingesteld en goed geïnformeerde netwerkroutering is uitgeschakeld. U kunt het netwerk op elk moment opnieuw inschakelen door de stappen in Goed geïnformeerde netwerkroutering [in te stellen.](#enabling-informed-network-routing)

## <a name="data-storage"></a>Gegevensopslag

Gegevens die worden uitgewisseld tussen Microsoft en de SD-WAN-oplossingsprovider worden opgeslagen in de gegevensopslaglocatie die is geselecteerd tijdens de eerste inschakelen van routering met informatie over het netwerk. De opties voor gegevensopslaglocatie vertegenwoordigen geografische gebieden met Microsoft Azure-regio's waarin de gegevens worden opgeslagen.

>[!NOTE]
>Tijdens de Preview-fase is de enige beschikbare opslaglocatie **Noord-Amerika.** Er komen extra locaties voor gegevensopslag beschikbaar voordat een goed geïnformeerde netwerkroutering algemeen beschikbaar komt.

Gegevens blijven op deze locatie tot 30 dagen bewaard. Wanneer deze is uitgeschakeld, worden alle resterende gegevens verwijderd binnen dit bewaarvenster van 30 dagen.

## <a name="related-topics"></a>Verwante onderwerpen

[Netwerkconnectiviteit in het Microsoft 365-beheercentrum (preview)](office-365-network-mac-perf-overview.md)

[Microsoft 365 Network Connectivity Location Services (preview)](office-365-network-mac-location-services.md)
