---
title: Bewaarders importeren in een Advanced eDiscovery zaak
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Gebruik het importhulpmiddel dom snel meerdere bewaarders en bijbehorende gegevensbronnen toe te voegen aan een zaak in Advanced eDiscovery.
ms.openlocfilehash: 98ff3690fe7fd8c956fce436585014ef0db82a26
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/04/2021
ms.locfileid: "52161693"
---
# <a name="import-custodians-to-an-advanced-ediscovery-case"></a>Bewaarders importeren in een Advanced eDiscovery zaak

Voor Advanced eDiscovery gevallen waarbij veel bewaarders betrokken zijn, kunt u meerdere bewaarders tegelijk importeren met behulp van een CSV-bestand dat de informatie bevat die nodig is om ze toe te voegen aan een zaak.

## <a name="import-custodians"></a>Beheerders importeren

1. Open het Advanced eDiscovery en selecteer het tabblad **Gegevensbronnen.**

2. Klik **op Gegevensbron importeren**  >  **beheerders** toevoegen.

3. Klik op **de flyoutpagina Beheerders** importeren op Een lege sjabloon **downloaden** om een csv-bestand met bewaarsjabloon te downloaden.

   ![Een CSV-sjabloon downloaden van flyoutpagina importbezorgers](../media/ImportCustodians1.png)

4. Voeg de bewaargegevens toe aan het CSV-bestand en sla deze op uw lokale computer op. Zie de [sectie Bewaarder CSV-bestand](#custodian-csv-file) voor informatie over de vereiste eigenschappen in het CSV-bestand.

5. Nadat u het CSV-bestand met de bewaargegevens hebt  voorbereid, gaat u terug naar het tabblad Gegevensbronnen en klikt u nogmaals op **Gegevensbron**  >   importeren.

6. Klik op **de flyoutpagina** Beheerders importeren op **Bladeren** en upload het CSV-bestand dat de bewaargegevens bevat.

   Nadat het CSV-bestand is geüpload, wordt een taak **genaamd BulkAddCustodian** gemaakt en weergegeven op het **tabblad** Taken. De taak valideert de bewaarders en de bijbehorende gegevensbronnen en voegt deze toe aan de pagina **Gegevensbronnen** van de zaak.

## <a name="custodian-csv-file"></a>Bewaarder CSV-bestand

Nadat u de csv-bewaarsjabloon hebt gedownload, kunt u beheerders en de gegevensbron in elke rij toevoegen. Zorg ervoor dat u de kolomnamen in de veldnamenrij niet wijzigt. Gebruik de kolommen werkbelastingtype en werkbelastinglocatie om andere gegevensbronnen aan een beheerder te koppelen.

| Kolomnaam|Beschrijving|
|:------- |:------------------------------------------------------------|
|**Bewaarder contactEmail**     |Het UPN-e-mailadres van de bewaarder. U kunt bijvoorbeeld sarad@contoso.onmicrosoft.com.           |
|**Exchange Ingeschakeld** | WAAR/ONWAAR-waarde die al dan niet het postvak van de bewaarder moet bevatten.      |
|**OneDrive Ingeschakeld** | WAAR/ONWAAR-waarde die al dan niet het account van de bewaarder OneDrive voor Bedrijven opgenomen. |
|**Is OnHold**        | WAAR/ONWAAR om aan te geven of de bewaargegevensbronnen in de wacht moeten worden gezet. <sup>1</sup>     |
|**Werkbelasting1 Type**         |Tekenreekswaarde die het type gegevensbron aangeeft dat moet worden geassocieerd met de bewaarder. Mogelijke waarden zijn: <br/>- ExchangeMailbox<br/> - SharePointSite<br/>- TeamsMailbox<br/>- TeamsSite<br/> - YammerMailbox<br/>- YammerSite |
|**Werkbelasting1 Locatie**     | Afhankelijk van het type werkbelasting is dit de locatie van de gegevensbron. Bijvoorbeeld het e-mailadres voor een postvak Exchange of de URL voor een SharePoint site. |
|||

> [!NOTE]
> <sup>1</sup> U kunt maximaal 1.000 postvakken en 100 sites in de wacht zetten met behulp van het bewaarproces en het CSV-bestand. U kunt dit proces gebruiken om meer dan 1.000 bewaarders toe te voegen aan een zaak, maar de bewaarlimieten zijn nog steeds van toepassing. Zie Limieten [in](limits-ediscovery20.md#hold-limits)Advanced eDiscovery.

Hier is een voorbeeld van een CSV-bestand met bewaargegevens:<br/><br/>

|Bewaarder contactEmail      | Exchange Ingeschakeld | OneDrive Ingeschakeld | Is OnHold | Werkbelasting1 Type | Werkbelasting1 Locatie             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|robinc@onmicrosoft.contoso.com | WAAR             | WAAR             | WAAR      | SharePointSite | https://contoso.sharepoint.com |
|pillarp@onmicrosoft.contoso.com | WAAR             | WAAR             | WAAR      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a>Bewaar- en gegevensbronvalidatie

Nadat u het bewaarder CSV-bestand hebt geüpload, Advanced eDiscovery u de volgende dingen:

1. Valideert de bewaarders en hun gegevensbronnen.

2. Indexeert alle gegevensbronnen voor elke bewaarder en plaatst deze in de wacht (als de eigenschap **Is OnHold** in het CSV-bestand is ingesteld op WAAR).

### <a name="custodian-validation"></a>Bewaardervalidatie

Momenteel ondersteunen we alleen importbezorgers die zijn opgenomen in de Azure Active Directory van uw organisatie (Azure AD).

Met het hulpprogramma voor het importeren van bewaarders worden bewaarders gevonden en gevalideerd met behulp van de UPN-waarde in de kolom **Bewaarder contactEmail** in het CSV-bestand. Bewaarders die worden gevalideerd, worden automatisch toegevoegd aan de zaak en worden weergegeven op het tabblad **Gegevensbronnen** van de zaak. Als een voogd niet kan worden gevalideerd, worden deze weergegeven in het foutenlogboek voor de BulkAddCustodian-taak die wordt weergegeven op het tabblad Taken in de zaak.  Niet-gevalideerde bewaarders worden niet toegevoegd aan de zaak of worden vermeld op het **tabblad Gegevensbronnen.**

### <a name="data-source-validation"></a>Gegevensbronvalidatie

Nadat bewaarders zijn gevalideerd en aan de zaak zijn toegevoegd, worden elk primair postvak en OneDrive account toegevoegd dat is gekoppeld aan een bewaarder.

Als een van de andere gegevensbronnen (zoals SharePoint-sites, Microsoft Teams, Microsoft 365 Groepen of Yammer-groepen) die zijn gekoppeld aan een bewaarder niet kan worden gevonden, worden geen  van deze gegevens toegewezen aan de bewaarder en  wordt de waarde Niet gevalideerd weergegeven in de kolom **Status** naast de bewaarder op het tabblad Gegevensbronnen.

Gevalideerde gegevensbronnen voor een bewaarder toevoegen:

1. Selecteer op **het tabblad** Gegevensbronnen een bewaarder die gegevensbronnen bevat die niet zijn gevalideerd.

2. Schuif op de pagina bewaarder flyout naar de sectie **Bewaarlocaties** om zowel gevalideerde als niet-gevalideerde gegevensbronnen weer te geven die zijn gekoppeld aan bewaarder.

3. Klik **boven** aan de flyoutpagina op Bewerken om ongeldige gegevensbronnen te verwijderen of nieuwe gegevens toe te voegen.

4. Nadat u niet-gevalideerde gegevensbronnen hebt verwijderd of een nieuwe hebt toevoegen, wordt de waarde **Actief** weergegeven in **de kolom Status** voor de bewaarder op het tabblad **Gegevensbronnen.** Als u bronnen wilt toevoegen die eerder ongeldig leken, volgt u de onderstaande herstelstappen om ze handmatig toe te voegen aan een bewaarder.

### <a name="remediating-invalid-data-sources"></a>Ongeldige gegevensbronnen herstellen

Handmatig een gegevensbron toevoegen en koppelen die eerder ongeldig was:

1. Selecteer op **het tabblad Gegevensbronnen** een beheerder om handmatig een gegevensbron toe te voegen en te koppelen die eerder ongeldig was.

2. Klik **boven** aan de flyoutpagina op Bewerken om postvakken, sites, Teams of Yammer aan de beheerder te koppelen. Doe dit door te klikken op **Bewerken** naast het juiste gegevenslocatietype.

3. Klik **op Volgende** om de pagina Instellingen voor **wachtstand weer** te geven en de instelling voor de ingedrukt houden te configureren voor de gegevensbronnen die u hebt toegevoegd.

4. Klik **op Volgende** om de pagina **Revisiebeheerders weer te** geven en klik vervolgens op Verzenden **om** uw wijzigingen op te slaan.
