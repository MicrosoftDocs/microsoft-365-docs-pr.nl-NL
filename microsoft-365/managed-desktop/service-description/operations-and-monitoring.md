---
title: Microsoft beheerde bureaublad bewerkingen en bewaking
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
ms.openlocfilehash: 01a43b35d272aaebce4c6866e3edfb04664b1801
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655721"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Microsoft beheerde bureaublad bewerkingen en bewaking

<!-- Operations and monitoring: -->


## <a name="change-management"></a>Wijzigingsbeheer

In een serviceaanbieding is het aandachtspunt voor zaken als hardware-onderhoud en beveiligingsupdates dienst verdienstt naar de service provider (Microsoft) in plaats van de klant. U dient echter nog steeds te zorgen dat de werking van een derde partij en aangepaste software blijft werken zoals verwacht wanneer updates worden uitgerold.

Voor on-premises producten is uw organisatie verantwoordelijk voor de verantwoordelijkheid voor het beheren van wijzigingen.

### <a name="balance-of-responsibility"></a>Verantwoordelijkheids bedrag

Verantwoordelijkheid | Microsoft beheerde bureaublad service | Microsoft 365-clientsoftware | On-premises clients en servers | derden en aangepaste software
----- | ----- | ----- | ----- | -----
Nieuwe functionaliteit maken | Microsoft | Microsoft | / | Klant
Nieuwe functies testen voor kwaliteitsbewaking |  Microsoft | Microsoft | / | Klant
Communiceren over nieuwe functies | / | / | / | Klant
Aangepaste software integreren | / | / | Klant | Klant
Beveiligingsupdates toepassen | Microsoft | Microsoft | Klant | Klant
Systeemsoftware onderhouden | Microsoft | Microsoft | Klant | Klant
Pakket voor implementatie | Microsoft | Microsoft | Klant | Klant


### <a name="change-process-overview"></a>Overzicht van processen wijzigen

Hier ziet u een overzicht van hoe het wijzigingsproces wordt gedeeld tussen Microsoft en klanten. 



<table>
<tr><th></th><th><p>De rol van Microsoft:</p></th><th><p>Rol van klant:</p></th></tr>
<tr><td>Vóór een wijziging</td><td><ul><li>Verwachtingen instellen voor Servicewijzigingen.</li><li>Klanten 5 dagen tevoren informeren over wijzigingen waarvoor beheerdersactie moeten ondernemen.</li><li>Voor wijzigingen in noodgevallen gelden een beperking voordat u op de hoogte wordt gesteld.</li></ul></td><td><ul><li>Begrijpen wat u kunt verwachten voor wijzigingen en communicatie.</li><li>Lees Microsoft Managed Desktop berichtencentrum regelmatig.</li><li>Interne processen voor wijzigingsbeheer controleren en bijwerken.</li><li>Meer informatie over de naleving van Microsoft beheerde bureaublad vereisten. </li><li>Erkennen en goedkeuren, indien nodig.</li></ul></td></tr><tr><td>Tijdens een wijziging</td><td><ul><li>Maandelijkse beveiligings-en niet-beveiligingsupdates voor Windows 10 en Office 365-clients vrijgeven en implementeren.</li><li>Gegevens signalen en ondersteunings wachtrijen voor invloed volgen.</li></ul></td><td><ul><li>Controleer het berichtencentrum van Microsoft Managed Desktop en Bekijk eventuele aanvullende informatie.</li><li>   Voer elke benodigde actie uit, indien van toepassing, en test toepassingen.</li><li>Maak een ondersteuningsverzoek als een scenario met een einde van een einde/herstel ervaring optrad.</li></ul></td></tr><tr><td>Na een wijziging</td><td><ul><li>Verzamel feedback van klanten om de implementatie van toekomstige wijzigingen te verbeteren.</li><li>Gegevens signalen en ondersteunings wachtrijen voor invloed volgen.</li></ul></td><td><ul><li>Werk samen met medewerkers in uw organisatie om de wijziging door te voeren.</li><li>   Bekijk wijzigingsbeheer processen voor verkoopkansen om efficiëntie te verkrijgen.</li><li>Algemene feedback en bepaalde feedback geven via het feedback programma voor beheerders.</li><li>Gebruikers trainen om app-specifieke feedback te geven met behulp van de Windows feedback-hub en de knop glimlach in Office-apps.</li></ul></td></tr>
<table> 






### <a name="change-types"></a>Typen wijzigen

Er zijn verschillende typen wijzigingen die regelmatig worden gemaakt in de service. Het communicatiekanaal voor deze wijzigingen en de acties waarvan klanten verantwoordelijk zijn.

Niet alle wijzigingen zijn van invloed op uw gebruikers of vereisen actie. Sommige worden gepland en sommige niet-gepland door hun aard (niet-beveiligingsupdates en beveiligingsupdates worden gewoonlijk niet gepland). Afhankelijk van het type wijziging kan het communicatiekanaal variëren. In de volgende tabel vindt u een overzicht van de typen wijzigingen die u kunt verwachten voor de Microsoft beheerde bureaublad service.

|   | Mogelijk |   Niet-beveiligingsupdates |  Beveiliging
--- | --- | --- | ---
**Type wijziging** | Onderdeel updates<br>Nieuwe functies of toepassingen<br>Afgeschafte functies | Client-hotfixes voor problemen | Beveiligingspatches
**Kennisgeving vooraf** | 5 dagen kennisgeving voor wijzigingen waarvoor actie moet worden ondernomen |    Nee, deze zijn opgenomen in de maandelijkse versie   | Nee, deze zijn opgenomen in de maandelijkse versie 
**Communicatiekanaal** | -Berichtencentrum<br>-E-mail waarschuwing | -Berichtencentrum<br>-E-mail waarschuwing | -Berichtencentrum<br>-E-mail waarschuwing
**Actie van globale beheerder vereist** | Altijd |  Krijgen |    Krijgen 
**Type actie** | Instellingen wijzigen | Wijzigingen doorgeven aan gebruikers | Beheerdersinstellingen wijzigen     
**Vereist testen** | Bedrijfstoepassingen controleren, waaronder Remote Access Services |  Soms-de Fix testen tegen processen of aanpassingen |   Krijgen 
**Voorbeelden van wijzigingen** | -Functie-updates: IT-beheer Portal, eenvoudig ondersteuningsticket verzenden en controleren<br>Nieuwe functies of toepassingen: Semi-Annual release van een onderdelenupdate van Windows 10 | Hotfixes op basis van door de klant gerapporteerde fouten |  


## <a name="standard-operating-procedures"></a>Standaard exploitatiemethoden

De Microsoft-beheerbare bureaublad service wordt geïmplementeerd en beheerd door Microsoft in uw Microsoft-Cloud exemplaar, waar u andere beheeractiviteiten kunt verrichten. Microsoft is uitsluitend verantwoordelijk voor Microsoft Managed Desktop-specific setup, Configuration en Operation. 

Voor on-premises producten heeft uw organisatie de verantwoordelijkheid voor het beheren van de installatie, en het configureren van de configuratie en de operationele activiteiten.

Categorieën |    Microsoft zal u | Klant zal
--- | --- | ---
Netwerk (proxy, pakket inspectie, VPN)  | Adviseer en plan met klanten om Risico's te minimaliseren voor zakelijke gebruikers. | -Maak een ondersteuningsverzoek voor het aanvragen van informatie voor een geplande configuratiewijziging, waaronder configuratiedetails, Scope, tijdlijn en andere relevante informatie die Microsoft ter beoordeling moet nakijken.<br>-Alleen een wijziging toepassen als Microsoft de beheerde bureaublad voering heeft beoordeeld en is geadviseerd.
Service accounts |-De referenties implementeren, veilig opslaan en beheren.<br> -Geautoriseerde toegang of het gebruik van deze referenties communiceren met uw team van beveiligingsactiviteiten. | -Maak een ondersteuningsverzoek voor het aanvragen van informatie voor een geplande configuratiewijziging, waaronder configuratiedetails, Scope, tijdlijn en andere relevante informatie die Microsoft ter beoordeling moet nakijken.<br>-Alleen een wijziging toepassen als Microsoft de beheerde bureaublad voering heeft beoordeeld en is geadviseerd.<br>-Niet toewijzen van beleid, meervoudige verificatie, voorwaardelijke toegang of Toepassingsimplementatie aan de service accounts van Microsoft Managed Desktop.<br>-Het wachtwoord niet opnieuw instellen of de inloggegevens gebruiken.<br>-Open een ondersteuningsaanvraag voor SEV C voor Microsoft Managed Desktop Operations als verdachte activiteiten worden waargenomen in intune-of Azure-auditlogboeken, met betrekking tot deze serviceaccounts.
Apparaatgroepen | -Het lidmaatschap van apparaten in Microsoft Managed-bureaublad groepen implementeren en beheren.<br>-De door Microsoft beheerde bureaublad groepen gebruiken voor het beheren van de toewijzing en het vrijgeven van de configuratie en updates van apparaten. | -Maak een ondersteuningsverzoek voor het aanvragen van informatie voor een geplande configuratiewijziging, waaronder configuratiedetails, Scope, tijdlijn en andere relevante informatie die Microsoft ter beoordeling moet nakijken.<br>-Alleen een wijziging toepassen als Microsoft de beheerde bureaublad voering heeft beoordeeld en is geadviseerd.<br>-Wijzig het lidmaatschap van een door Microsoft beheerde bureaublad groep niet.<br>-Alleen de groepen gebruiken voor het toewijzen van bedrijfs certificaten voor services zoals VPN, Windows hello voor bedrijven of e-mail versleuteling, of de configuratie van het zakelijk Wi-Fi-profiel.<br>-Waar met comanagement is sprake van het expliciet uitsluiten van alle door Microsoft beheerde bureaublad groepen wanneer u de Configuration Manager-client implementeert.
Lijnen |  -Beleidsregels voor het Microsoft-beleid dat de configuratiestatus van apparatuur binnen de service beheerst implementeren en beheren.<br>-Met behulp van apparaatgroepen kunt u op basis van de groepen groepen een update implementeren, beleidsregels en Windows.<br> -U hoeft het doel van niet-door Microsoft beheerde bureaublad groepen expliciet uit te sluiten. | -Maak een ondersteuningsverzoek voor het aanvragen van informatie voor een geplande configuratiewijziging, waaronder configuratiedetails, Scope, tijdlijn en andere relevante informatie die Microsoft ter beoordeling moet nakijken.<br>-Alleen een wijziging toepassen als Microsoft de beheerde bureaublad voering heeft beoordeeld en is geadviseerd.<br>-Beleidsregels voor het Microsoft-beleid dat niet door Microsoft beheerde bureaubladservices worden beheerd, niet bewerken of toewijzen
Microsoft Defender Advanced Threat Protection   | Controleer en onderzoek apparatuur binnen het bereik van de Microsoft beheerde bureaublad service. | -Maak een ondersteuningsverzoek voor het aanvragen van informatie voor een geplande configuratiewijziging, waaronder configuratiedetails, Scope, tijdlijn en andere relevante informatie die Microsoft ter beoordeling moet nakijken.<br>-Alleen een wijziging toepassen wanneer door Microsoft beheerde bureaublad bewerkingen een beoordeling is uitgevoerd en is geadviseerd
Microsoft Store voor Bedrijven |  Configureer en onderhoud het Windows auto pilot-profiel voor de Microsoft beheerde bureaublad service. | -Maak een ondersteuningsverzoek voor het aanvragen van informatie voor een geplande configuratiewijziging, waaronder configuratiedetails, Scope, tijdlijn en andere relevante informatie die Microsoft ter beoordeling moet nakijken.<br>-Alleen een wijziging toepassen als Microsoft de beheerde bureaublad voering heeft beoordeeld en is geadviseerd.<br>-De configuratie van het Microsoft-Auto Pilot-Profiel van Microsoft beheerde bureaubladtoepassing niet wijzigen of toegewezen apparaten toevoegen/verwijderen.
Certificaat | | -Maak een ondersteuningsverzoek 60 dagen voordat een certificaat verloopt, zodat informatie wordt opgevraagd voor een geplande configuratiewijziging, waaronder configuratiedetails, Scope, tijdlijn en andere relevante informatie die Microsoft ter beoordeling moet nakijken.<br>-Alleen een wijziging toepassen als Microsoft de beheerde bureaublad voering heeft beoordeeld en is geadviseerd.<br>-Alle certificaten bijwerken die nodig zijn voor het configureren van certificaatprofielen, VPN-profielen en Wi-Fi profielen.




## <a name="device-wipe-with-factory-reset"></a>Apparaat wissen met fabrieksinstellingen

Het team van Microsoft beheerde bureaublad activiteiten kan het opnieuw instellen van apparaten die in de service zijn geregistreerd, indien nodig. Dit is handig als u een apparaat aan een andere werknemer wilt geven of als een werknemer uw bedrijf verlaat. 

Er zijn een paar vereisten:

- Uw globale beheerder moet een serviceaanvraag indienen.
- Neem de computernaam van het apparaat op in de aanvraag.
- Het gebruikersaccount moet zich in azure AD bevinden voordat het apparaat opnieuw wordt ingesteld.

Beheerde bureaublad bewerkingen team gaat het volgende doen:

- De naam van het apparaat opzoeken in intune
- De opdracht voor de fabrieksinstellingen naar het apparaat verzenden

>[!NOTE]
>Verwijder het gebruikersaccount van Azure AD niet voordat het apparaat opnieuw wordt ingesteld. Als de gebruiker zich niet in azure AD bevindt, kan intune de opdracht Factory Reset niet naar het apparaat verzenden. 

Het apparaat wordt gestart in de ' out-of-Box Experience ' en alle vooraf geïnstalleerde toepassingen en instellingen worden opnieuw toegepast. De gebruiker van het apparaat moet eerst de installatiegegevens opgeven. 

Wanneer het apparaat opnieuw is ingesteld, kunt u het aan een andere persoon in uw organisatie geven. Geen van de gegevens van de vorige gebruiker of de bedrijfsgegevens op het apparaat. De volgende gebruiker gaat verder met het proces dat de vorige persoon heeft uitgevoerd met een nieuw Microsoft-beheerd bureaublad.

BitLocker is een belangrijk onderdeel van gegevensbeveiliging in dit proces. Met BitLocker-versleuteling op Microsoft beheerde bureaublad apparaten blijven de gegevens op het station veilig, zelfs als de fabriek opnieuw is ingesteld. Alle gegevens die zich op het station bevonden, zijn niet beschikbaar voor de volgende gebruiker van het apparaat. Zie [overzicht van BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)voor meer informatie.

Zie [een apparaat opnieuw instellen](https://docs.microsoft.com/intune/remote-actions/devices-wipe#factory-reset-a-device)voor meer informatie. 