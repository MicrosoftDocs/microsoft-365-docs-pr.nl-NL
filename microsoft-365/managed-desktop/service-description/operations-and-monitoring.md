---
title: Microsoft Managed Desktop en monitoring
description: Wie doet wat voor verschillende wijzigingsprocessen
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 3e56066f0b4e63fc9b73bbecf5aaa3180ffd2e4f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920418"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Microsoft Managed Desktop en monitoring

<!-- Operations and monitoring: -->


## <a name="change-management"></a>Beheer wijzigen

In een serviceaanbieding wordt de verantwoordelijkheidsbalans voor zaken zoals hardwareonderhoud en beveiligingsupdates verplaatst naar de serviceprovider (Microsoft) in plaats van de klant (u). U moet er echter nog steeds voor zorgen dat niet-Microsoft en aangepaste software blijven werken zoals verwacht wanneer updates worden uitgerold.

Voor on-premises producten neemt uw organisatie alle verantwoordelijkheid voor het beheren van de wijziging op zich.

### <a name="balance-of-responsibility"></a>Verantwoordelijkheidsbalans

Verantwoordelijkheid | Microsoft Managed Desktop service | Microsoft 365 clientsoftware | On-premises clients en servers | niet-Microsoft en aangepaste software
----- | ----- | ----- | ----- | -----
Nieuwe functionaliteit bieden | Microsoft | Microsoft | Beide | Klant
Nieuwe functies testen voor kwaliteitsborging |  Microsoft | Microsoft | Beide | Klant
Communiceren over nieuwe functies | Beide | Beide | Beide | Klant
Aangepaste software integreren | Beide | Beide | Klant | Klant
Beveiligingsupdates toepassen | Microsoft | Microsoft | Klant | Klant
Systeemsoftware onderhouden | Microsoft | Microsoft | Klant | Klant
Pakket voor implementatie | Microsoft | Microsoft | Klant | Klant


### <a name="change-process-overview"></a>Overzicht van proces wijzigen

Hier volgt een overzicht van hoe het wijzigingsproces wordt gedeeld tussen Microsoft en klanten: 



<table>
<tr><th></th><th><p>De rol van Microsoft:</p></th><th><p>De rol van de klant:</p></th></tr>
<tr><td>Vóór een wijziging</td><td><ul><li>Stel verwachtingen in voor servicewijzigingen.</li><li>Informeer klanten vijf dagen van tevoren voor wijzigingen waarvoor beheerdersactie is vereist.</li><li>Voor wijzigingen in noodgevallen moet u een beperking toepassen vóór de melding.</li></ul></td><td><ul><li>Begrijp wat u kunt verwachten voor wijzigingen en communicatie.</li><li>Lees Microsoft Managed Desktop berichtencentrum regelmatig.</li><li>Interne processen voor wijzigingsbeheer controleren en bijwerken.</li><li>U kunt de naleving van de Microsoft Managed Desktop en controleren. </li><li>Bevestig en goed, indien vereist.</li></ul></td></tr><tr><td>Tijdens een wijziging</td><td><ul><li>Release en implementeer maandelijkse beveiligings- en niet-beveiligingsupdates voor Windows 10 en Office 365 clients.</li><li>Controleer gegevenssignalen en ondersteuningswachtrijen voor impact.</li></ul></td><td><ul><li>Controleer het Microsoft Managed Desktop berichtencentrum en controleer eventuele aanvullende informatie.</li><li>   Onderneemt alle vereiste acties, indien van toepassing, en test toepassingen.</li><li>Als een oplossingsscenario wordt ervaren, maakt u een ondersteuningsaanvraag.</li></ul></td></tr><tr><td>Na een wijziging</td><td><ul><li>Verzamel feedback van klanten om de implementatie van toekomstige wijzigingen te verbeteren.</li><li>Controleer gegevenssignalen en ondersteuningswachtrijen voor impact.</li></ul></td><td><ul><li>Werk samen met personen in uw organisatie om de wijziging aan te nemen.</li><li>   Controleer wijzigings- en acceptatiebeheerprocessen om de efficiëntie te verbeteren.</li><li>Geef algemene feedback en specifieke feedback in het feedbackprogramma van de beheerder.</li><li>Train gebruikers om app-specifieke feedback te geven met de Windows Feedback-hub en de knop Glimlach in Office apps.</li></ul></td></tr>
<table> 






### <a name="change-types"></a>Typen wijzigen

Er zijn verschillende typen wijzigingen die we regelmatig aan de service aanbrengen. Het communicatiekanaal voor deze wijzigingen en de acties waar u verantwoordelijk voor bent, variëren.

Niet alle wijzigingen hebben dezelfde invloed op uw gebruikers of vereisen actie. Sommige zijn gepland en sommige zijn niet gepland door hun aard (niet-beveiligingsupdates en beveiligingsupdates zijn meestal niet gepland). Afhankelijk van het type wijziging kan het communicatiekanaal variëren. In de volgende tabel ziet u de typen wijzigingen die u kunt verwachten voor de Microsoft Managed Desktop service.

|   | Functionaliteit |   Niet-beveiligingsupdates |  Beveiliging
--- | --- | --- | ---
**Type wijziging** | - Functie-updates<br>- Nieuwe functies of toepassingen<br>- Afgeschafte functies | Client hotfixes voor problemen | Beveiligingsupdates
**Kennisgeving vooraf** | Kennisgeving van vijf dagen voor wijzigingen waarvoor actie moet worden ondernomen | Nee, dergelijke wijzigingen worden opgenomen in de maandelijkse release    | Nee, wijzigingen worden opgenomen in de maandelijkse release 
**Communicatiekanaal** | - Berichtencentrum<br>- E-mailwaarschuwing | - Berichtencentrum<br>- E-mailwaarschuwing | - Berichtencentrum<br>- E-mailwaarschuwing
**Vereist globale beheeractie** | Soms |  Zelden |    Zelden 
**Type actie** | Instellingen wijzigen | Wijzigingen communiceren aan gebruikers | Beheerdersinstellingen wijzigen     
**Vereist testen** | Zakelijke toepassingen controleren, inclusief services voor externe toegang |  Soms : de oplossing testen op processen of aanpassingen |   Zelden 
**Voorbeelden van verandering** | - Functie-updates: IT-beheerportal vereenvoudigde ondersteuningstickets indienen en controleren<br>- Nieuwe functies of toepassingen: Semi-Annual release van een Windows 10 onderdelenupdate | Hotfixes op basis van door de klant gerapporteerde fouten |  


## <a name="standard-operating-procedures"></a>Standaardbesturingssystemen

De Microsoft Managed Desktop service wordt geïmplementeerd en beheerd door Microsoft in uw Microsoft-cloud-exemplaar, waar u mogelijk andere beheeractiviteiten kunt uitvoeren. Microsoft is alleen verantwoordelijk voor Microsoft Managed Desktop-specifieke installatie, configuratie en bewerking. 

Voor on-premises producten neemt uw organisatie alle verantwoordelijkheid voor het beheren van installatie- en configuratie- en operationele activiteiten.

Categorieën |    Microsoft zal | Klant zal
--- | --- | ---
Netwerk (proxy, pakketcontrole, VPN)  | Adviseer en plan met klanten om het risico voor zakelijke gebruikers te minimaliseren. | - Maak een ondersteuningsaanvraag voor het aanvragen van informatie voor een geplande configuratiewijziging, inclusief configuratiedetails, bereik, tijdlijn en andere relevante details die Door Microsoft kunnen worden beoordeeld.<br>- Pas een wijziging alleen toe wanneer Microsoft Managed Desktop operations heeft beoordeeld en geadviseerd.
Serviceaccounts |- De referenties implementeren, veilig opslaan en beheren.<br> - Communiceer onbevoegde toegang of gebruik van deze referenties aan uw Team Beveiligingsbewerkingen. | - Maak een ondersteuningsaanvraag voor het aanvragen van informatie voor een geplande configuratiewijziging, inclusief configuratiedetails, bereik, tijdlijn en andere relevante details die Door Microsoft kunnen worden beoordeeld.<br>- Pas een wijziging alleen toe wanneer Microsoft Managed Desktop operations heeft beoordeeld en geadviseerd.<br>- Wijs geen beleid, meervoudige verificatie, voorwaardelijke toegang of toepassingsimplementatie toe aan de Microsoft Managed Desktop Serviceaccounts.<br>- Stel het wachtwoord niet opnieuw in of gebruik de referenties niet.<br>- Open een Sev C-ondersteuningsaanvraag voor Microsoft Managed Desktop Operations als verdachte activiteiten worden waargenomen in Intune- of Azure-auditlogboeken, die betrekking hebben op deze serviceaccounts.
Apparaatgroepen | - Implementeert en beheert het lidmaatschap van apparaten binnen Microsoft Managed Desktop groepen.<br>- Gebruik de Microsoft Managed Desktop groepen om de toewijzing en release van configuratie en updates voor apparaten te beheren. | - Maak een ondersteuningsaanvraag voor het aanvragen van informatie voor een geplande configuratiewijziging, inclusief configuratiedetails, bereik, tijdlijn en andere relevante details die Door Microsoft kunnen worden beoordeeld.<br>- Pas een wijziging alleen toe wanneer Microsoft Managed Desktop operations heeft beoordeeld en geadviseerd.<br>- Wijzig het lidmaatschap van een groep Microsoft Managed Desktop niet.<br>- Gebruik de groepen alleen om bedrijfscertificaten toe te wijzen voor services zoals VPN, Windows Hello voor Bedrijven of e-mailversleuteling, of Wi-Fi profielconfiguratie.<br>- Wanneer cobeheer bestaat, worden alle groepen Microsoft Managed Desktop bij de implementatie van de Configuration Manager-client expliciet uitgesloten.
Beleid |  - Implementeert en beheert Microsoft Managed Desktop beleidsregels die van toepassing zijn op de configuratietoestand van apparaten binnen de service.<br>- Updates implementeren, naar beleid of Windows, stapsgewijs met apparaatgroepen.<br> - Expliciet uitsluiten van niet-Microsoft Managed Desktop groepen. | - Maak een ondersteuningsaanvraag voor het aanvragen van informatie voor een geplande configuratiewijziging, inclusief configuratiedetails, bereik, tijdlijn en andere relevante details die Door Microsoft kunnen worden beoordeeld.<br>- Pas een wijziging alleen toe wanneer Microsoft Managed Desktop operations heeft beoordeeld en geadviseerd.<br>- Geen beleidsregels bewerken of toewijzen Microsoft Managed Desktop apparaten of gebruikers die niet worden beheerd door de Microsoft Managed Desktop service.
Microsoft Defender voor Eindpunt | Controleer en onderzoek apparaten binnen het bereik van de Microsoft Managed Desktop service. | - Maak een ondersteuningsaanvraag voor het aanvragen van informatie voor een geplande configuratiewijziging, inclusief configuratiedetails, bereik, tijdlijn en andere relevante details die Door Microsoft kunnen worden beoordeeld.<br>- Pas alleen een wijziging toe wanneer Microsoft Managed Desktop operations heeft beoordeeld en geadviseerd
Microsoft Store voor Bedrijven |  Configureer en onderhoud het Windows Autopilot-profiel voor de Microsoft Managed Desktop service. | - Maak een ondersteuningsaanvraag voor het aanvragen van informatie voor een geplande configuratiewijziging, inclusief configuratiedetails, bereik, tijdlijn en andere relevante details die Door Microsoft kunnen worden beoordeeld.<br>- Pas een wijziging alleen toe wanneer Microsoft Managed Desktop operations heeft beoordeeld en geadviseerd.<br>- Wijzig de configuratie van het autopilot-Microsoft Managed Desktop Windows niet of voeg toegewezen apparaten toe of verwijder deze.
Certificaten | | - Maak 60 dagen vóór het verlopen van een certificaat een ondersteuningsaanvraag en vraag informatie over een geplande configuratiewijziging, inclusief configuratiedetails, bereik, tijdlijn en andere relevante details die Door Microsoft moeten worden beoordeeld.<br>- Pas een wijziging alleen toe wanneer Microsoft Managed Desktop operations heeft beoordeeld en geadviseerd.<br>- Werk alle certificaten bij die nodig zijn om certificaatprofielen, VPN-profielen en Wi-Fi configureren.




## <a name="device-wipe-with-factory-reset"></a>Apparaat wissen met fabrieksinstellingen

Het Microsoft Managed Desktop Operations-team kan indien nodig een fabrieks reset uitvoeren van apparaten die zijn geregistreerd voor de service. Het opnieuw instellen is handig als u een apparaat wilt geven aan een andere werknemer of als een werknemer uw bedrijf verlaat. 

Er zijn een paar vereisten:

- De globale beheerder moet een serviceaanvraag indienen.
- Neem de computernaam van het apparaat op in de aanvraag.
- Het gebruikersaccount moet zich in Azure AD hebben voordat we het apparaat opnieuw instellen.

Het team beheerde bureaubladbewerkingen doet het volgende:

- De naam van het apparaat zoeken in Intune
- De opdracht Fabrieksinstellingen naar het apparaat verzenden

>[!NOTE]
>Verwijder het gebruikersaccount niet uit Azure AD voordat het apparaat opnieuw wordt ingesteld. Als de gebruiker niet in Azure AD is, kan Intune de opdracht fabrieksinstellingen niet naar het apparaat verzenden. 

Het apparaat wordt opgestart in de 'out-of-box-ervaring' en alle vooraf geïnstalleerde toepassingen en instellingen worden opnieuw toegepast. De gebruiker van het apparaat moet de eerste installatiegegevens opnieuw verstrekken. 

Wanneer het apparaat opnieuw is ingesteld, kunt u het aan een andere persoon in uw organisatie geven. Geen van de gegevens van de vorige gebruiker of ondernemingsgegevens staat op het apparaat. De volgende gebruiker doormaakt hetzelfde proces als de vorige persoon met een nieuw Microsoft Managed Desktop apparaat.

BitLocker is een belangrijk onderdeel van gegevensbeveiliging in dit proces. Met BitLocker versleuteling op Microsoft Managed Desktop apparaten blijven de gegevens op het station veilig, zelfs nadat het apparaat in de fabriek is gereset. Alle gegevens die op het station stonden, zijn niet beschikbaar voor de volgende gebruiker van het apparaat. Zie BitLocker [overzicht voor meer informatie.](/windows/security/information-protection/bitlocker/bitlocker-overview)

Zie Een apparaat opnieuw [instellen in de fabriek voor meer informatie.](/intune/remote-actions/devices-wipe#factory-reset-a-device)