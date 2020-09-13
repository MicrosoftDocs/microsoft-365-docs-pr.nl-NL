---
title: Microsoft 365-apps voor ondernemingen
description: Microsoft 365-Apps implementeren, hoe deze worden bijgewerkt en hoe instellingen worden beheerd
keywords: wijzigingsoverzicht
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 767489ba9f9ac63bc1a2d8b4999b6634335b1aef
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547744"
---
# <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365-apps voor ondernemingen

## <a name="initial-deployment"></a>Eerste implementatie

Microsoft Managed Desktop zorgt ervoor dat Microsoft 365-apps voor Enterprise (64-bits) zijn geïnstalleerd als onderdeel van de afbeelding op alle [programma apparaten](../service-description/device-list.md). U kunt alle volgende toepassingen op het apparaat presenteren wanneer het wordt uitgebracht:

- Word
- Excel
- PowerPoint
- Outlook
- Publisher
- Access
- Skype voor Bedrijven
- OneNote

Met deze aanpak wordt de invloed van het netwerk geminimaliseerd en wordt gegarandeerd dat gebruikers productief kunnen zijn zodra ze hun apparaat ontvangen. We implementeren vervolgens extra beleidsregels voor beheerde apparaten om de toepassingen te configureren voor gebruik.

> [!NOTE]
> Microsoft teams is apart geïmplementeerd via Microsoft 365-apps voor Enterprise en is niet opgenomen in de basisafbeelding. 

### <a name="available-deployment-to-users"></a>Beschikbare implementatie voor gebruikers

Als een gebruiker om welke reden dan ook geen Microsoft 365-apps op hun apparaat heeft, kunt u een pakket gebruiken om de verwachte status van het apparaat te herstellen. Voeg de gebruiker toe aan de **moderne werkplek-Office-Office365_Install** groep en de apps komen voor hen beschikbaar in de bedrijfs portal.

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a>Microsoft 365-apps voor Enterprise (32-bits)

Microsoft Managed Desktop biedt geen ondersteuning voor de implementatie van de 32-bits versie van M365-apps voor Enterprise.

## <a name="updates-to-microsoft-365-apps"></a>Updates voor Microsoft 365-apps

Microsoft 365-apps zijn ingesteld op bijwerken op het [maandelijkse Enterprise-kanaal](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview). Deze oefening biedt gebruikers een maand lang nieuwe Office-functies, maar ontvangt per maand slechts één update per maand op een voorspelbare release planning. Updates worden uitgebracht op de tweede dinsdag van de maand; deze updates kunnen functies, beveiliging en kwaliteitsupdates bevatten. Deze updates worden automatisch uitgevoerd en worden direct opgehaald uit het Office CDN voor dat specifieke kanaal.

Microsoft Managed Desktop spreidt elke release om potentiële problemen in uw omgeving te identificeren. We voltooien de implementatie 28 dagen na de release van de productgroep Microsoft 365-app. Microsoft Managed Desktop plant updates voor verschillende groepen om te kunnen valideren en testen als volgt: 

- Test: 0 dagen
- Eerste: 0 dagen
- Snel: zeven dagen
- Algemeen: 21 dagen

Door Microsoft beheerde bureaublad sets wordt een [Update deadline](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) van zeven dagen voor apparaten ingesteld. Zodra de update beschikbaar is, moet deze binnen zeven dagen zijn geïnstalleerd. Gebruikers ontvangen een [melding](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) dat er updates zijn vereist op diverse locaties: de toepassing, in het systeemvak, 12 uur vóór de deadline, en ontvangt een waarschuwing van 15 minuten vóór de deadline. Alle Microsoft 365-apps moeten worden gesloten om de update te voltooien.

### <a name="pausing-or-rolling-back-an-update"></a>Een update onderbreken of herstellen

Als u de Microsoft 365-App-Update om welke reden dan ook moet onderbreken of opnieuw moet aanbrengen, dient u een [beheerders aanvraag voor beheerders](../working-with-managed-desktop/admin-support.md) via de Microsoft beheerde bureaublad Portal.

In een uitgebrachte Microsoft-Desktop wordt de fout tarieven van alle Microsoft 365-apps gecontroleerd. Als we een aanzienlijk verschil van kwaliteit aangeven tussen de nieuwe release en de voorafgaande taak, kunnen we contact met u opnemen via de portal van de beheerde bureaublad beheerder van Microsoft. Afhankelijk van de ernst, vragen wij u of u de release wilt onderbreken of wilt u op de hoogte blijven van een probleem. 

### <a name="delivery-optimization"></a>Delivery Optimization

Delivery Optimization is een peer-to-peer-distributie technologie beschikbaar in Windows 10. Apparaten kunnen inhoud, zoals updates, delen die de apparaten van Microsoft via internet hebben gedownload. Dit kan de bandbreedte van het netwerk beperken omdat een apparaat gedeelten van de update kan downloaden van een ander apparaat in het lokale netwerk, zodat u de update niet volledig van Microsoft hoeft te downloaden.

[Delivery Optimization](https://docs.microsoft.com/deployoffice/delivery-optimization) is standaard ingeschakeld op apparaten met de edities Windows 10 Enterprise of Windows 10 education. 

## <a name="settings-managed-by-microsoft-managed-desktop"></a>Instellingen die worden beheerd door Microsoft Managed Desktop

Microsoft beheert bepaalde instellingen als onderdeel van de service. Microsoft Managed Desktop beheert geen beveiligings basislijn van Office, maar u kunt er zelf een instellen door de instructies te volgen in de sectie [instellingen die u beheert](#settings-you-manage) .

### <a name="update-settings"></a>Instellingen bijwerken

Microsoft Managed Desktop onderhoudt alle [Update-instellingen](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) voor beheerde apparaten en u moet deze instellingen wijzigen.

### <a name="set-updates-to-occur-automatically"></a>Automatisch aanstellen van updates

**Standaardwaarde**: ingeschakeld

Dit beleid is zodanig geconfigureerd dat alle Office-apparaten up-to-date worden gehouden in de Cloud. 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a>Een deadline instellen wanneer updates moeten worden toegepast

**Standaardwaarde**: 7 dagen

Het **UpdateDeadline** -beleid wordt gebruikt voor het configureren van de respijtperiode die gebruikers hebben voordat een update wordt afgedwongen op het apparaat. Met dit deadline beleid worden ook [meldingen](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) aan de gebruiker ondergebracht om deze te informeren over de wijzigingen die op hun apparaat zijn vereist.  

### <a name="defer-updates-on-a-device-for-a-period"></a>Updates op een apparaat uitstellen voor een punt

Dit beleid is voor elke groep updatebeheer apparaat anders geconfigureerd en is vereist voor Microsoft Managed Desktop voor de update doelen:  

- Test: 0 dagen
- Eerste: 0 dagen
- Snel 7 dagen
- Algemeen: 21 dagen

### <a name="update-notifications-settings"></a>Instellingen voor meldingen bijwerken

**Standaardwaarde**: onwaar

De instelling meldingen voor update verbergen is ingesteld op **Onwaar** op Microsoft Managed Desktop-apparaten om de beste update ervaring voor gebruikers te bieden door hen op de [hoogte](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) te stellen wanneer er updates zijn vereist.

### <a name="specify-a-location-to-look-for-updates"></a>Een locatie opgeven waarnaar u wilt zoeken naar updates

**Standaardwaarde**: Monthly Enterprise-kanaal

Een combinatie van het **UpdatePath** -en **UpdateChannel** -beleid wordt zo nodig gebruikt om de updateplanning te bereiken. Dit beleid is ingesteld om ervoor te zorgen dat alle Office-apparaten updates rechtstreeks uit het CDN ontvangen voor het maandelijkse Enterprise-kanaal.

### <a name="specify-the-target-version-of-microsoft-365-apps"></a>De doelversie van Microsoft 365-apps opgeven

Het doelversie beleid wordt soms door Microsoft beheerd bureaublad gebruikt om een bepaalde versie van Office terug te draaien of vast te maken. 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a>De optie voor het in-of uitschakelen van Office automatische updates verbergen

**Standaardwaarde**: ingeschakeld

Deze instelling is vereist voor Microsoft Managed Desktop om te voldoen aan de update doelen voor Microsoft 365-toepassingen. 

### <a name="first-run-settings"></a>Instellingen voor First Run 

Er zijn verschillende instellingen die van invloed zijn op het gedrag wanneer Office voor het eerst wordt uitgevoerd.

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a>De licentievoorwaarden namens de eindgebruiker accepteren

**Standaardwaarde**: uitgeschakeld

Wanneer een gebruiker een Microsoft 365-app voor de eerste keer opent, wordt u gevraagd de gebruiksrechtovereenkomst te accepteren. Als u de licentievoorwaarden voor uw gebruikers wilt accepteren, dient u een serviceaanvraag te indienen bij het Microsoft-beheer team van het bureaublad dat u vraagt om deze instelling in te schakelen. 

### <a name="suppress-outlook-mobile-check-box"></a>Selectievakje Outlook Mobile onderdrukken

**Standaardwaarde**: uitgeschakeld

De eerste keer dat een gebruiker Outlook opent, wordt u gevraagd Outlook Mobile te installeren. Als u niet wilt dat gebruikers dit selectievakje zien, dient u een serviceaanvraag te indienen bij het Microsoft-beheerde bureaublad operationeel en vragen om deze instelling voor uw apparaten te kunnen inschakelen. 

## <a name="other-settings"></a>Andere instellingen

Er zijn andere Microsoft 365-app-instellingen die door Microsoft worden beheerd om namens u te configureren. 

### <a name="disable-personal-onedrive"></a>Persoonlijke OneDrive uitschakelen

**Standaardwaarde**: uitgeschakeld

Sommige organisaties zorgen voor gebruikers die toegang hebben tot zowel zakelijke als persoonlijke bestanden op hun eigen apparaat. U kunt een serviceaanvraag indienen bij het Microsoft-beheerbare bureaublad bewerkings team waarin u wordt gevraagd om deze instelling in te schakelen. 

## <a name="settings-you-manage"></a>Instellingen die u beheert

Er zijn veel andere beleidsregels die door Microsoft worden beheerd de bureaubladversie nog niet is ingesteld als onderdeel van onze service. U kunt deze configureren met behulp van Microsoft intune, dat gebruikmaakt van de service [Cloud beleid van Office](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) . Ga hiervoor als volgt te werk:

1.  Meld u aan bij het Beheercentrum van Microsoft Endpoint Manager.
2.  Selecteer **Apps > beleid voor Office-Apps > maken**
3.  Voer de volgende handelingen uit op de pagina **beleidsconfiguratie maken** :
    - Voer een naam in.
    - Voer een beschrijving in (optioneel).
    - Kies in **toewijzingen**of dit beleid van toepassing is op alle gebruikers van microsoft 365-apps voor ondernemingen of alleen voor gebruikers die anoniem toegang hebben tot documenten via Office voor het web.
    - Selecteer de beveiligingsgroep op basis van AAD die is toegewezen aan de beleidsconfiguratie. U kunt alle beleidsconfiguraties slechts toewijzen aan één groep, en elke groep kan slechts één beleidsconfiguratie worden toegewezen.
    - Configureer de beleidsinstellingen die moeten worden opgenomen in de beleidsconfiguratie. U kunt op de naam van de beleidsinstelling zoeken naar de beleidsinstelling die u wilt configureren. U kunt ook filteren op de toepassing, of het beleid een aanbevolen beveiligings basislijn is en of het beleid is geconfigureerd. De kolom platform geeft aan of het beleid wordt toegepast op Microsoft 365-apps voor Enterprise voor Windows-apparaten, Office voor het web of alle.
4.  Nadat u uw selecties hebt gemaakt, kiest u **maken**.

> [!NOTE]
> Office-configuratie beleidsregels ondersteunen alleen op gebruikers gebaseerde implementatie
