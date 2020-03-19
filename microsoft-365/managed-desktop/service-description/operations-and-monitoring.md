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
ms.openlocfilehash: 5aee7c835643fab94cc7e233ea005c3f3a1b921c
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42806081"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Microsoft Managed Desktop-bewerkingen en -bewaking

<!-- Operations and monitoring: -->


## <a name="change-management"></a>Wijzigingsbeheer

In een serviceaanbod verschuift de verantwoordelijkheidsbalans voor zaken als hardwareonderhoud en beveiligingsupdates naar de serviceprovider (Microsoft) in plaats van naar de klant (u). U moet er echter nog steeds voor zorgen dat software van derden en aangepaste software blijft functioneren zoals verwacht wanneer updates worden uitgerold.

Voor on-premises producten neemt uw organisatie alle verantwoordelijkheid voor het beheer van veranderingen op zich.

### <a name="balance-of-responsibility"></a>Verantwoordelijkheidsbalans

Verantwoordelijkheid | Microsoft Managed Desktop-service | Microsoft 365-clientsoftware | On-premises clients en servers | 3rd party en aangepaste software
----- | ----- | ----- | ----- | -----
Nieuwe functionaliteit bieden | Microsoft | Microsoft | Zowel | Klant
Test nieuwe functies voor kwaliteitsborging |  Microsoft | Microsoft | Zowel | Klant
Communiceren over nieuwe functies | Zowel | Zowel | Zowel | Klant
Aangepaste software integreren | Zowel | Zowel | Klant | Klant
Beveiligingsupdates toepassen | Microsoft | Microsoft | Klant | Klant
Systeemsoftware onderhouden | Microsoft | Microsoft | Klant | Klant
Pakket voor implementatie | Microsoft | Microsoft | Klant | Klant


### <a name="change-process-overview"></a>Overzicht van het proces wijzigen

Hier vindt u een overzicht van hoe het wijzigingsproces wordt gedeeld tussen Microsoft en klanten. 



<table>
<tr><th></th><th><p>De rol van Microsoft:</p></th><th><p>De rol van de klant:</p></th></tr>
<tr><td>Voordat een wijziging wordt gewijzigd</td><td><ul><li>Stel verwachtingen in voor servicewijzigingen.</li><li>Stel klanten 5 dagen van tevoren op de hoogte voor wijzigingen waarvoor beheerdersactie vereist is.</li><li>Voor noodwijzigingen moet u een beperking toepassen voordat u dit meldt.</li></ul></td><td><ul><li>Begrijp wat u verwachten voor wijzigingen en communicatie.</li><li>Lees het Microsoft Managed Desktop Message Center regelmatig.</li><li>Interne change management processen beoordelen en bijwerken.</li><li>Begrijp en controleer de naleving van de Microsoft Managed Desktop-vereisten. </li><li>Erkennen en goedkeuren, indien nodig.</li></ul></td></tr><tr><td>Tijdens een verandering</td><td><ul><li>Maandelijkse beveiligings- en niet-beveiligingsupdates voor Windows 10- en Office 365-clients vrijgeven en implementeren.</li><li>Monitor gegevenssignalen en steun wachtrijen voor impact.</li></ul></td><td><ul><li>Controleer het Microsoft Managed Desktop Message Center en bekijk alle aanvullende informatie.</li><li>   Neem alle vereiste actie, indien van toepassing, en test toepassingen.</li><li>Als er een break/fix-scenario wordt ervaren, maakt u een ondersteuningsaanvraag.</li></ul></td></tr><tr><td>Na een wijziging</td><td><ul><li>Verzamel feedback van klanten om de uitrol van toekomstige wijzigingen te verbeteren.</li><li>Monitor gegevenssignalen en steun wachtrijen voor impact.</li></ul></td><td><ul><li>Werk samen met mensen in uw organisatie om de verandering over te nemen.</li><li>   Bekijk veranderings- en adoptiebeheerprocessen op mogelijkheden om efficiëntie te behalen.</li><li>Geef algemene feedback en specifieke feedback in het hulpprogramma voor beheerdersfeedback.</li><li>Train gebruikers om app-specifieke feedback te geven met behulp van de Windows Feedback Hub en de Smile-knop in Office-apps.</li></ul></td></tr>
<table> 






### <a name="change-types"></a>Typen wijzigen

Er zijn verschillende soorten wijzigingen die regelmatig in de service worden aangebracht. Het communicatiekanaal voor deze wijzigingen en de acties waarvoor klanten verantwoordelijk zijn, varieert.

Niet alle wijzigingen hebben dezelfde impact op uw gebruikers of vereisen actie. Sommige zijn gepland en sommige ongepland door hun aard (niet-beveiligingsupdates en beveiligingsupdates zijn meestal niet gepland). Afhankelijk van het type wijziging kan het communicatiekanaal variëren. In de volgende tabel worden de typen wijzigingen weergegeven die u verwachten voor de Microsoft Managed Desktop-service.

|   | Functionaliteit |   Niet-beveiligingsupdates |  Beveiliging
--- | --- | --- | ---
**Type wijziging** | - Functie-updates<br>- Nieuwe functies of toepassingen<br>- Afgeschafte functies | Clienthotfixes voor problemen | Beveiligingspatches
**Vooraankondiging** | 5 dagen van tevoren voor wijzigingen die actie vereisen |    Nee, deze zijn opgenomen in de maandelijkse release   | Nee, deze zijn opgenomen in de maandelijkse release 
**Communicatiekanaal** | - Berichtencentrum<br>- E-mailwaarschuwing | - Berichtencentrum<br>- E-mailwaarschuwing | - Berichtencentrum<br>- E-mailwaarschuwing
**Vereist stappen actie voor tenantbeheerders** | Soms |  Zelden |    Zelden 
**Type actie** | Instellingen wijzigen | Wijzigingen communiceren met gebruikers | Beheerdersinstellingen wijzigen     
**Vereist testen** | Zakelijke toepassingen controleren, inclusief services voor externe toegang |  Soms - het testen van de oplossing tegen processen of aanpassingen |   Zelden 
**Voorbeelden van verandering** | - Functie-updates: IT-beheerportal vereenvoudigde ondersteuning voor het indienen en beoordelen van ondersteuningstickets<br>- Nieuwe functies of toepassingen: Semi-jaarlijkse release van een Windows 10-functie-update | Hotfixes op basis van door klanten gerapporteerde bugs |  


## <a name="standard-operating-procedures"></a>Standaardwerkprocedures

De Microsoft Managed Desktop-service wordt geïmplementeerd en beheerd door Microsoft in uw Microsoft-cloudexemplaar, waar u andere administratieve activiteiten uitvoeren. Microsoft is als enige verantwoordelijk voor microsoft Managed Desktop-specifieke installatie, configuratie en bewerking. 

Voor on-premises producten neemt uw organisatie alle verantwoordelijkheid op zich voor het beheer van de installatie en configuratie- en operationele activiteiten.

Categorieën |    Microsoft zal | Klant zal
--- | --- | ---
Netwerk (proxy, pakketinspectie, VPN)  | Adviseren en plannen met klanten om risico's voor zakelijke gebruikers te minimaliseren. | - Maak een ondersteuningsverzoek met informatie om informatie voor een geplande configuratiewijziging, inclusief configuratiegegevens, scope, tijdlijn en andere relevante details die Microsoft kan bekijken.<br>- Pas een wijziging alleen toe nadat Microsoft Managed Desktop Operations is beoordeeld en geadviseerd.
Serviceaccounts |- Implementeren, veilig opslaan en beheren van de referenties.<br> - Communiceer ongeautoriseerde toegang of gebruik van deze referenties naar uw Security Operations-team. | - Maak een ondersteuningsverzoek met informatie om informatie voor een geplande configuratiewijziging, inclusief configuratiegegevens, scope, tijdlijn en andere relevante details die Microsoft kan bekijken.<br>- Pas een wijziging alleen toe nadat Microsoft Managed Desktop Operations is beoordeeld en geadviseerd.<br>- Geen beleid, meervoudige verificatie, voorwaardelijke toegang of toepassingsimplementatie toewijzen aan de Microsoft Managed Desktop Service Accounts.<br>- Stel het wachtwoord niet opnieuw in of gebruik de referenties.<br>- Open een Sev C-ondersteuningsverzoek voor Microsoft Managed Desktop Operations als verdachte activiteit wordt waargenomen in Intune- of Azure-controlelogboeken, gerelateerd aan deze serviceaccounts.
Apparaatgroepen | - Implementeren en beheren van het lidmaatschap van apparaten binnen Microsoft Managed Desktop-groepen.<br>- Gebruik de Microsoft Managed Desktop-groepen om de toewijzing en release van configuratie en updates voor apparaten te beheren. | - Maak een ondersteuningsverzoek met informatie om informatie voor een geplande configuratiewijziging, inclusief configuratiegegevens, scope, tijdlijn en andere relevante details die Microsoft kan bekijken.<br>- Pas een wijziging alleen toe nadat Microsoft Managed Desktop Operations is beoordeeld en geadviseerd.<br>- Wijzig het lidmaatschap van een Microsoft Managed Desktop-groep niet.<br>- Gebruik de groepen alleen om bedrijfscertificaten toe te wijzen voor services zoals VPN, Windows Hello for Business of e-mailversleuteling of bedrijfsconfiguratie van wifi-profielen.<br>- Wanneer er co-management bestaat, sluit u bij het implementeren van de Configuration Manager-client expliciet alle Microsoft Managed Desktop-groepen uit.
Beleid |  - Implementeer en beheer het Microsoft Managed Desktop-beleid dat de configuratiestatus van apparaten binnen de service regelt.<br>- Updates implementeren in het beleid of Windows, stapsgewijs met apparaatgroepen.<br> - Sluit targeting niet-Microsoft Managed Desktop-groepen expliciet uit. | - Maak een ondersteuningsverzoek met informatie om informatie voor een geplande configuratiewijziging, inclusief configuratiegegevens, scope, tijdlijn en andere relevante details die Microsoft kan bekijken.<br>- Pas een wijziging alleen toe nadat Microsoft Managed Desktop Operations is beoordeeld en geadviseerd.<br>- Microsoft Managed Desktop-beleid niet bewerken of toewijzen aan apparaten of gebruikers die niet worden beheerd door de Microsoft Managed Desktop-service.
Geavanceerde bescherming voor geavanceerde bedreigingen van Microsoft Defender   | Apparaten bewaken en onderzoeken binnen het bereik van de Microsoft Managed Desktop-service. | - Maak een ondersteuningsverzoek met informatie om informatie voor een geplande configuratiewijziging, inclusief configuratiegegevens, scope, tijdlijn en andere relevante details die Microsoft kan bekijken.<br>- Pas een wijziging alleen toe nadat Microsoft Managed Desktop Operations heeft beoordeeld en geadviseerd
Microsoft Store voor Bedrijven |  Configureer en onderhoud het Windows Autopilot-profiel voor de Microsoft Managed Desktop-service. | - Maak een ondersteuningsverzoek met informatie om informatie voor een geplande configuratiewijziging, inclusief configuratiegegevens, scope, tijdlijn en andere relevante details die Microsoft kan bekijken.<br>- Pas een wijziging alleen toe nadat Microsoft Managed Desktop Operations is beoordeeld en geadviseerd.<br>- Wijzig de configuratie van het Microsoft Managed Desktop Windows Autopilot-profiel niet of voeg/verwijder toegewezen apparaten niet.
Certificaten | | - Maak 60 dagen voor het verlopen van een certificaat een ondersteuningsverzoek, waarbij informatie wordt opgevraagd voor een geplande configuratiewijziging, inclusief configuratiegegevens, scope, tijdlijn en andere relevante gegevens die Microsoft kan controleren.<br>- Pas een wijziging alleen toe nadat Microsoft Managed Desktop Operations is beoordeeld en geadviseerd.<br>- Werk alle certificaten bij die nodig zijn om certificaatprofielen, VPN-profielen en Wi-Fi-profielen te configureren.




## <a name="device-wipe-with-factory-reset"></a>Apparaatwissen met fabrieksreset

Het Microsoft Managed Desktop Operations Team kan indien nodig een fabrieksreset uitvoeren van apparaten die zijn ingeschreven bij de service. Dit is handig als u een apparaat aan een andere werknemer moet geven of als een werknemer uw bedrijf verlaat. 

Er zijn een paar eisen:

- De tenantbeheerder van de klant moet een serviceaanvraag indienen
- We hebben de computernaam voor het apparaat nodig.
- Gebruikersaccount moet zich in Azure AD bevinden voordat we de reset doen

Managed Desktop Operations Team zal:

- De naam van het apparaat opzoeken in Intune
- De opdracht fabrieksreset naar het apparaat verzenden

>[!NOTE]
>Verwijder het gebruikersaccount niet uit Azure AD voordat de fabrieksopnieuw wordt ingesteld. Als de gebruiker zich niet in Azure AD bevindt, kan Intune de opdracht fabrieksreset niet naar het apparaat verzenden. 

Het apparaat wordt opgestart in OOBE en alle vooraf geïnstalleerde toepassingen en instellingen worden opnieuw toegepast. De gebruiker van het apparaat moet opnieuw informatie verstrekken. 

Wanneer het apparaat is gereset, u het aan een andere persoon in uw organisatie geven. Geen van de gegevens van de vorige gebruiker of bedrijfsgegevens staat op het apparaat. De volgende gebruiker gaat door hetzelfde proces als de vorige persoon deed met een nieuw Microsoft Managed Desktop-apparaat.

BitLocker is een belangrijk onderdeel van de beveiliging van gegevens in dit proces. Met BitLocker-versleuteling op Microsoft Managed Desktop-apparaten blijven gegevens op het station veilig, zelfs nadat de fabrieksreset op het apparaat is toegepast. Alle gegevens die zich op het station hebben staan, zijn niet beschikbaar voor de volgende gebruiker van het apparaat. Zie [BitLocker-overzicht](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)voor meer informatie.

Zie [Een apparaat opnieuw instellen](https://docs.microsoft.com/intune/remote-actions/devices-wipe#factory-reset-a-device)voor meer informatie. 
