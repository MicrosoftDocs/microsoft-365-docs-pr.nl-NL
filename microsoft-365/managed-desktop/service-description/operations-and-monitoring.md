---
title: Microsoft Managed Desktop-bewerkingen en -bewaking
description: ''
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
ms.openlocfilehash: 0ed10b7088e38cbf5a2d9196508eae5cdc522a74
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529443"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Microsoft Managed Desktop-bewerkingen en -bewaking

<!-- Operations and monitoring: -->


## <a name="change-management"></a>Wijzigingsbeheer

In een serviceaanbod verschuift de balans van verantwoordelijkheid voor zaken als hardwareonderhoud en beveiligingsupdates naar de serviceprovider (Microsoft) in plaats van naar de klant (u). U moet er echter nog steeds voor zorgen dat software van derden en aangepaste software blijft functioneren zoals verwacht wanneer updates worden uitgerold.

Voor on-premises producten neemt uw organisatie alle verantwoordelijkheid voor het beheer van veranderingen.

### <a name="balance-of-responsibility"></a>Evenwicht van verantwoordelijkheid

Verantwoordelijkheid | Microsoft Managed Desktop-service | Microsoft 365-clientsoftware | On-premises clients en servers | 3rd party en custom software
----- | ----- | ----- | ----- | -----
Nieuwe functionaliteit bieden | Microsoft | Microsoft | Zowel | Klant
Test nieuwe functies voor kwaliteitsborging |  Microsoft | Microsoft | Zowel | Klant
Communiceren over nieuwe functies | Zowel | Zowel | Zowel | Klant
Aangepaste software integreren | Zowel | Zowel | Klant | Klant
Beveiligingsupdates toepassen | Microsoft | Microsoft | Klant | Klant
Systeemsoftware onderhouden | Microsoft | Microsoft | Klant | Klant
Pakket voor implementatie | Microsoft | Microsoft | Klant | Klant


### <a name="change-process-overview"></a>Procesoverzicht wijzigen

Hier vindt u een overzicht van de manier waarop het wijzigingsproces wordt gedeeld tussen Microsoft en klanten. 



<table>
<tr><th></th><th><p>De rol van Microsoft:</p></th><th><p>De rol van de klant:</p></th></tr>
<tr><td>Vóór een wijziging</td><td><ul><li>Stel verwachtingen in voor servicewijzigingen.</li><li>Stel klanten 5 dagen van tevoren in kennis van wijzigingen waarvoor beheerdersactie vereist is.</li><li>Voor noodwijzigingen moet u een mitigatie toepassen voordat u dit meldt.</li></ul></td><td><ul><li>Begrijp wat u verwachten voor wijzigingen en communicatie.</li><li>Lees microsoft Managed Desktop Message Center regelmatig.</li><li>Interne processen voor veranderingsbeheer controleren en bijwerken.</li><li>Begrijp en controleer of er aan de vereisten voor Microsoft Managed Desktop is voldaan. </li><li>Erken en goed te keuren, indien nodig.</li></ul></td></tr><tr><td>Tijdens een verandering</td><td><ul><li>Maandelijkse beveiligings- en niet-beveiligingsupdates voor Windows 10- en Office 365-clients vrijgeven en implementeren.</li><li>Controleer gegevenssignalen en ondersteun wachtrijen voor impact.</li></ul></td><td><ul><li>Controleer het Microsoft Managed Desktop Message Center en bekijk eventuele aanvullende informatie.</li><li>   Onderneem eventuele vereiste maatregelen, indien van toepassing, en test toepassingen.</li><li>Als er een scenario voor onderbreking/oplossing wordt ervaren, maakt u een ondersteuningsverzoek.</li></ul></td></tr><tr><td>Na een wijziging</td><td><ul><li>Verzamel feedback van klanten om de uitrol van toekomstige wijzigingen te verbeteren.</li><li>Controleer gegevenssignalen en ondersteun wachtrijen voor impact.</li></ul></td><td><ul><li>Werk samen met mensen in uw organisatie om de wijziging over te nemen.</li><li>   Bekijk veranderingen- en adoptiebeheerprocessen voor mogelijkheden om efficiëntie te behalen.</li><li>Geef algemene feedback en specifieke feedback in de admin feedback tool.</li><li>Train gebruikers om app-specifieke feedback te geven met de Windows Feedback Hub en de Smile-knop in Office-apps.</li></ul></td></tr>
<table> 






### <a name="change-types"></a>Typen wijzigen

Er zijn verschillende soorten wijzigingen die worden aangebracht in de service op een regelmatige basis. Het communicatiekanaal voor deze wijzigingen en de acties waar klanten verantwoordelijk voor zijn, varieert.

Niet alle wijzigingen hebben dezelfde impact op uw gebruikers of vereisen actie. Sommige zijn gepland en sommige ongepland door hun aard (niet-beveiligingsupdates en beveiligingsupdates zijn meestal niet gepland). Afhankelijk van het type wijziging kan het communicatiekanaal variëren. In de volgende tabel worden de typen wijzigingen weergegeven die u verwachten voor de Microsoft Managed Desktop-service.

|   | Functionaliteit |   Niet-beveiligingsupdates |  Beveiliging
--- | --- | --- | ---
**Type wijziging** | - Functie-updates<br>- Nieuwe functies of toepassingen<br>- Afgeschafte kenmerken | Hotfixes voor clients voor problemen | Beveiligingspatches
**Voorafgaande kennisgeving** | 5 dagen van tevoren voor wijzigingen die actie vereisen |    Nee, deze zijn opgenomen in de maandelijkse release   | Nee, deze zijn opgenomen in de maandelijkse release 
**Communicatiekanaal** | - Berichtencentrum<br>- E-mailwaarschuwing | - Berichtencentrum<br>- E-mailwaarschuwing | - Berichtencentrum<br>- E-mailwaarschuwing
**Vereist wereldwijde beheeractie** | Soms |  Zelden |    Zelden 
**Type actie** | Instellingen wijzigen | Wijzigingen doorgeven aan gebruikers | Beheerdersinstellingen wijzigen     
**Vereist testen** | Zakelijke toepassingen controleren, inclusief services voor externe toegang |  Soms - het testen van de oplossing tegen processen of aanpassingen |   Zelden 
**Voorbeelden van verandering** | - Functie-updates: IT Admin Portal vereenvoudigd ondersteuning ticket indiening en beoordeling<br>- Nieuwe functies of toepassingen: halfjaarlijkse release van een Windows 10-functie-update | Hotfixes op basis van gemelde bugs door klanten |  


## <a name="standard-operating-procedures"></a>Standaardwerkprocedures

De Microsoft Managed Desktop-service wordt geïmplementeerd en beheerd door Microsoft in uw Microsoft-cloudinstantie, waar u andere administratieve activiteiten uitvoeren. Microsoft is als enige verantwoordelijk voor microsoft Managed Desktop-specifieke installatie, configuratie en werking. 

Voor on-premises producten neemt uw organisatie alle verantwoordelijkheid op zich voor het beheer van de installatie en configuratie en operationele activiteiten.

Categorieën |    Microsoft zal | Klant zal
--- | --- | ---
Netwerk (proxy, pakketinspectie, VPN)  | Adviseren en plannen met klanten om risico's voor zakelijke gebruikers te minimaliseren. | - Maak een ondersteuningsverzoek waarin om informatie wordt gevraagd voor een geplande configuratiewijziging, inclusief configuratiedetails, bereik, tijdlijn en andere relevante details die Microsoft kan controleren.<br>- Pas een wijziging toe nadat Microsoft Managed Desktop Operations heeft beoordeeld en geadviseerd.
Serviceaccounts |- Implementeer, bewaar veilig de referenties en beheer deze.<br> - Communiceer ongeautoriseerde toegang of het gebruik van deze referenties naar uw Security Operations-team. | - Maak een ondersteuningsverzoek waarin om informatie wordt gevraagd voor een geplande configuratiewijziging, inclusief configuratiedetails, bereik, tijdlijn en andere relevante details die Microsoft kan controleren.<br>- Pas een wijziging toe nadat Microsoft Managed Desktop Operations heeft beoordeeld en geadviseerd.<br>- Geen beleid, meervoudige verificatie, voorwaardelijke toegang of toepassingsimplementatie toewijzen aan de Microsoft Managed Desktop Service Accounts.<br>- Het wachtwoord niet opnieuw instellen of de referenties gebruiken.<br>- Open een Sev C-ondersteuningsverzoek voor Microsoft Managed Desktop Operations als verdachte activiteit wordt waargenomen in Intune- of Azure-controlelogboeken die verband houden met deze serviceaccounts.
Apparaatgroepen | - Implementeren en beheren van het lidmaatschap van apparaten binnen Microsoft Managed Desktop-groepen.<br>- Gebruik de Microsoft Managed Desktop-groepen om de toewijzing en release van configuratie en updates voor apparaten te beheren. | - Maak een ondersteuningsverzoek waarin om informatie wordt gevraagd voor een geplande configuratiewijziging, inclusief configuratiedetails, bereik, tijdlijn en andere relevante details die Microsoft kan controleren.<br>- Pas een wijziging toe nadat Microsoft Managed Desktop Operations heeft beoordeeld en geadviseerd.<br>- Wijzig het lidmaatschap van een Microsoft Managed Desktop-groep niet.<br>- Gebruik de groepen alleen om bedrijfscertificaten toe te wijzen voor services zoals VPN, Windows Hello for Business of e-mailversleuteling of configuratie van het zakelijke Wi-Fi-profiel.<br>- Wanneer co-management bestaat, worden alle Microsoft Managed Desktop-groepen expliciet uitgesloten bij het implementeren van de Client Configuration Manager.
Beleid |  - Implementeer en beheer het Microsoft Managed Desktop-beleid dat de configuratiestatus van apparaten binnen de service regelt.<br>- Implementeer updates, naar beleid of Windows, stapsgewijs met apparaatgroepen.<br> - Het expliciet uitsluiten van targeting niet-Microsoft Managed Desktop-groepen. | - Maak een ondersteuningsverzoek waarin om informatie wordt gevraagd voor een geplande configuratiewijziging, inclusief configuratiedetails, bereik, tijdlijn en andere relevante details die Microsoft kan controleren.<br>- Pas een wijziging toe nadat Microsoft Managed Desktop Operations heeft beoordeeld en geadviseerd.<br>- Microsoft Managed Desktop-beleid niet bewerken of toewijzen aan apparaten of gebruikers die niet worden beheerd door de Microsoft Managed Desktop-service.
Microsoft Defender Advanced Threat Protection   | Apparaten controleren en onderzoeken binnen het bereik van de Microsoft Managed Desktop-service. | - Maak een ondersteuningsverzoek waarin om informatie wordt gevraagd voor een geplande configuratiewijziging, inclusief configuratiedetails, bereik, tijdlijn en andere relevante details die Microsoft kan controleren.<br>- Pas een wijziging toepassen nadat Microsoft Managed Desktop Operations heeft beoordeeld en geadviseerd
Microsoft Store voor Bedrijven |  Het Windows Autopilot-profiel configureren en onderhouden voor de Microsoft Managed Desktop-service. | - Maak een ondersteuningsverzoek waarin om informatie wordt gevraagd voor een geplande configuratiewijziging, inclusief configuratiedetails, bereik, tijdlijn en andere relevante details die Microsoft kan controleren.<br>- Pas een wijziging toe nadat Microsoft Managed Desktop Operations heeft beoordeeld en geadviseerd.<br>- Wijzig de configuratie van het Microsoft Managed Desktop Windows Autopilot-profiel niet of voeg/verwijder toegewezen apparaten toe.
Certificaten | | - Maak 60 dagen voor het verstrijken van een certificaat een ondersteuningsverzoek en vraag informatie op voor een geplande configuratiewijziging, inclusief configuratiegegevens, bereik, tijdlijn en andere relevante details die Microsoft kan controleren.<br>- Pas een wijziging toe nadat Microsoft Managed Desktop Operations heeft beoordeeld en geadviseerd.<br>- Werk alle certificaten bij die nodig zijn om certificaatprofielen, VPN-profielen en Wi-Fi-profielen te configureren.




## <a name="device-wipe-with-factory-reset"></a>Apparaat wissen met fabrieksreset

Het Microsoft Managed Desktop Operations Team kan een fabrieksreset uitvoeren van apparaten die zijn ingeschreven voor de service wanneer dat nodig is. Dit is handig als u een apparaat aan een andere werknemer moet geven of als een werknemer uw bedrijf verlaat. 

Er zijn een paar eisen:

- Uw globale beheerder moet een serviceaanvraag indienen.
- Neem de computernaam van het apparaat op in het verzoek.
- Het gebruikersaccount moet zich in Azure AD bevinden voordat we het apparaat opnieuw instellen.

Managed Desktop Operations-team gaat als volgt te werk:

- Zoek de naam van het apparaat op in Intune
- De opdracht fabrieksreset naar het apparaat verzenden

>[!NOTE]
>Verwijder het gebruikersaccount niet uit Azure AD voordat het apparaat opnieuw wordt ingesteld. Als de gebruiker zich niet in Azure AD bevindt, kan Intune de opdracht fabrieksreset niet naar het apparaat verzenden. 

Het apparaat start op in de 'out-of-box-ervaring' en alle vooraf geïnstalleerde toepassingen en instellingen worden opnieuw toegepast. De gebruiker van het apparaat moet opnieuw eerste installatiegegevens verstrekken. 

Wanneer het apparaat is gereset, u het aan een andere persoon in uw organisatie geven. Geen van de gegevens of bedrijfsgegevens van de vorige gebruiker wordt op het apparaat weergegeven. De volgende gebruiker zal gaan door hetzelfde proces dat de vorige persoon deed met een nieuwe Microsoft Managed Desktop-apparaat.

BitLocker is een belangrijk onderdeel van gegevensbeveiliging in dit proces. Met BitLocker-versleuteling op Microsoft Managed Desktop-apparaten blijven de gegevens op het station veilig, zelfs nadat het apparaat is gereset. Gegevens die op het station stond, zijn niet beschikbaar voor de volgende gebruiker van het apparaat. Zie [BitLocker-overzicht](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)voor meer informatie.

Zie [Een apparaat opnieuw instellen](https://docs.microsoft.com/intune/remote-actions/devices-wipe#factory-reset-a-device)in de fabriek voor meer informatie. 