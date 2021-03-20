---
title: Microsoft 365-apps voor ondernemingen
description: Microsoft 365-apps implementeren, hoe ze worden bijgewerkt en hoe instellingen worden beheerd
keywords: wijzigingsgeschiedenis
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: f8dd666c41863192d866693c6860a64064f846e6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904850"
---
# <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps voor ondernemingen

## <a name="initial-deployment"></a>Eerste implementatie

Microsoft Managed Desktop zorgt ervoor dat Microsoft 365 Apps voor ondernemingen (64-bits) zijn geïnstalleerd als onderdeel van de afbeelding op alle [programmaapparaten.](../service-description/device-list.md) Alle volgende toepassingen moeten aanwezig zijn op het apparaat wanneer deze worden geleverd:

- Word
- Excel
- PowerPoint
- Outlook
- Publisher
- Toegang
- Skype voor Bedrijven
- OneNote

Deze benadering minimaliseert de netwerkeffecten en zorgt ervoor dat gebruikers productief kunnen zijn zodra ze hun apparaat ontvangen. Vervolgens implementeren we meer beleidsregels voor beheerde apparaten om de toepassingen in te stellen voor gebruik.

> [!NOTE]
> Microsoft Teams wordt afzonderlijk van Microsoft 365 Apps voor ondernemingen geïmplementeerd en wordt niet opgenomen in de basisafbeelding. 

### <a name="available-deployment-to-users"></a>Beschikbare implementatie voor gebruikers

Als een gebruiker om welke reden dan ook geen Microsoft 365-apps op zijn apparaat heeft, kunt u een pakket gebruiken om het apparaat terug te keren naar de verwachte status. Voeg de gebruiker toe aan **de groep Modern Workplace-Office-Office365_Install** en de apps zijn beschikbaar in de bedrijfsportal.

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a>Microsoft 365 Apps voor ondernemingen (32-bits)

Microsoft Managed Desktop biedt geen ondersteuning voor de implementatie van de 32-bits versie van M365-apps voor bedrijven.

## <a name="updates-to-microsoft-365-apps"></a>Updates voor Microsoft 365-apps

Microsoft 365-apps zijn ingesteld op update op [het Monthly Enterprise-kanaal](/deployoffice/overview-update-channels#monthly-enterprise-channel-overview). Deze oefening biedt uw gebruikers elke maand nieuwe Office-functies, maar ze ontvangen slechts één update per maand volgens een voorspelbaar releaseschema. Updates worden uitgebracht op de tweede dinsdag van de maand. Deze updates kunnen functie-, beveiligings- en kwaliteitsupdates bevatten. Deze updates worden automatisch uitgevoerd en worden rechtstreeks uit het Office-CDN gehaald voor dat specifieke kanaal.

Microsoft Managed Desktop verspringen elke release om mogelijke problemen in uw omgeving te identificeren. We voltooien de implementatie 28 dagen na de release van de productgroep Microsoft 365 App. In Microsoft Managed Desktop worden updatereleases gepland voor verschillende groepen, zodat u als volgt tijd hebt voor validatie en testen: 

- Test: nul dagen
- Ten eerste: nul dagen
- Snel: 3 dagen
- Breed: 7 dagen

Microsoft Managed Desktop stelt een updatedeadline van zeven [dagen in](/deployoffice/configure-update-settings-microsoft-365-apps) voor apparaten. Zodra de update beschikbaar is, moet deze binnen zeven dagen zijn geïnstalleerd. Gebruikers krijgen [een](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) melding dat updates vereist zijn op verschillende locaties: de toepassing, in het systeemvak 12 uur vóór de deadline, en ze ontvangen een waarschuwing van 15 minuten vóór de deadline. Alle Microsoft 365-apps moeten zijn gesloten om de update te voltooien.

### <a name="pausing-or-rolling-back-an-update"></a>Een update onderbreken of terugrollen

Als u microsoft 365 App-update om welke reden dan ook wilt onderbreken of terugdraaien, dient u een ondersteuningsaanvraag voor beheerders in [via](../working-with-managed-desktop/admin-support.md) de Microsoft Managed Desktop-portal.

Tijdens een release controleert Microsoft Managed Desktop de foutpercentages van alle Microsoft 365-apps. Als we een aanzienlijk kwaliteitsverschil zien tussen de nieuwe release en de voorganger, kunnen we contact met u opnemen via de Microsoft Managed Desktop Admin-portal. Afhankelijk van de ernst wordt u gevraagd of u de release wilt onderbreken of dat we actie hebben ondernomen om een probleem te beperken. 

### <a name="delivery-optimization"></a>Leveringsoptimalisatie

Leveringsoptimalisatie is een peer-to-peer-distributietechnologie die beschikbaar is in Windows 10. Hiermee kunnen apparaten inhoud delen, zoals updates, die de apparaten via internet van Microsoft hebben gedownload. Als u de update gebruikt, kunt u de netwerkbandbreedte verminderen omdat een apparaat delen van de update van een ander apparaat op het lokale netwerk kan downloaden in plaats van de update volledig van Microsoft te moeten downloaden.

[Leveringsoptimalisatie](/deployoffice/delivery-optimization) is standaard ingeschakeld op apparaten met de Windows 10 Enterprise- of Windows 10 Education-edities. 

## <a name="settings-managed-by-microsoft-managed-desktop"></a>Instellingen beheerd door Microsoft Managed Desktop

Microsoft beheert sommige instellingen als onderdeel van de service. Microsoft Managed Desktop beheert geen basislijn voor Office-beveiliging, maar u kunt er zelf een instellen door de richtlijnen te volgen in de sectie Instellingen [die u beheert.](#settings-you-manage)

### <a name="update-settings"></a>Update-instellingen

Microsoft Managed Desktop onderhoudt alle [update-instellingen](/deployoffice/configure-update-settings-microsoft-365-apps) voor beheerde apparaten en u moet deze instellingen wijzigen.

### <a name="set-updates-to-occur-automatically"></a>Updates automatisch instellen

**Standaardwaarde**: Ingeschakeld

Dit beleid is geconfigureerd om ervoor te zorgen dat alle Office-apparaten up-to-date kunnen blijven vanuit de cloud. 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a>Een deadline instellen wanneer updates moeten worden toegepast

**Standaardwaarde**: 7 dagen

Het **UpdateDeadline-beleid** wordt gebruikt om de respijtperiode te configureren die gebruikers hebben voordat een update wordt afgedwongen op het apparaat. Dit deadlinebeleid activeert ook [meldingen aan](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) de gebruiker om hem of haar te informeren over de wijzigingen die op het apparaat zijn vereist.  

### <a name="defer-updates-on-a-device-for-a-period"></a>Updates op een apparaat een bepaalde periode uitstellen

Dit beleid is anders geconfigureerd voor elke updatebeheerapparaatgroep en is vereist voor Microsoft Managed Desktop om te voldoen aan de updatedoelen:  

- Test: nul dagen
- Ten eerste: nul dagen
- Snel 7 dagen
- Breed: 21 dagen

### <a name="update-notifications-settings"></a>Instellingen voor meldingen bijwerken

**Standaardwaarde:** Onwaar

De instelling Updatemeldingen verbergen is  ingesteld op Onwaar op Microsoft Managed Desktop-apparaten om gebruikers de beste update-ervaring te bieden door ze op de hoogte te stellen wanneer updates nodig zijn. [](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps)

### <a name="specify-a-location-to-look-for-updates"></a>Een locatie opgeven om te zoeken naar updates

**Standaardwaarde:** Monthly Enterprise-kanaal

Een combinatie van het **UpdatePath-** en **UpdateChannel-beleid** wordt zo nodig gebruikt om de updateplanning te bereiken. Dit beleid is ingesteld om ervoor te zorgen dat alle Office-apparaten rechtstreeks updates ontvangen van het CDN voor het Monthly Enterprise-kanaal.

### <a name="specify-the-target-version-of-microsoft-365-apps"></a>De doelversie van Microsoft 365-apps opgeven

Het beleid doelversie wordt soms gebruikt door Microsoft Managed Desktop om een specifieke versie van Office terug te draaien of vast te maken. 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a>De optie voor het in- of uitschakelen van automatische updates van Office verbergen

**Standaardwaarde**: Ingeschakeld

Deze instelling is vereist voor Microsoft Managed Desktop om te voldoen aan de updatedoelen voor Microsoft 365-toepassingen. 

### <a name="first-run-settings"></a>Instellingen voor het eerst uitvoeren 

Er zijn verschillende instellingen die van invloed zijn op het gedrag van de eerste keer dat Office wordt uitgevoerd.

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a>De licentievoorwaarden namens de eindgebruiker accepteren

**Standaardwaarde**: Uitgeschakeld

De eerste keer dat een gebruiker een Microsoft 365-app opent, wordt deze gevraagd de licentievoorwaarden te accepteren. Als u de licentievoorwaarden namens uw gebruikers wilt accepteren, moet u een serviceaanvraag indienen bij het Microsoft Managed Desktop Operations-team waarin u wordt gevraagd deze instelling in te stellen. 

### <a name="suppress-outlook-mobile-check-box"></a>Selectievakje Outlook Mobile onderdrukken

**Standaardwaarde**: Uitgeschakeld

De eerste keer dat een gebruiker Outlook opent, wordt hem of haar gevraagd Outlook Mobile te installeren. Als u niet wilt dat uw gebruikers dit selectievakje zien, kunt u een serviceaanvraag indienen bij het Microsoft Managed Desktop Operations-team met de vraag of deze instelling is ingeschakeld voor uw apparaten. 

## <a name="other-settings"></a>Andere instellingen

Er zijn andere Microsoft 365 App-instellingen die u desgewenst namens Microsoft Managed Desktop kunt configureren. 

### <a name="disable-personal-onedrive"></a>Persoonlijke OneDrive uitschakelen

**Standaardwaarde**: Uitgeschakeld

Sommige organisaties maken zich zorgen over gebruikers die toegang hebben tot zowel zakelijke als persoonlijke bestanden op hun apparaten. U kunt een serviceaanvraag indienen bij het Microsoft Managed Desktop Operations-team met de vraag of deze instelling moet worden ingeschakeld. 

## <a name="settings-you-manage"></a>Instellingen die u beheert

Er zijn nog veel andere beleidsregels die microsoft Managed Desktop nog niet als onderdeel van onze service heeft ingesteld. U kunt dit beleid configureren met Microsoft Intune, dat gebruikmaakt van de [Office Cloud Policy-service.](/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) Als u dit beleid wilt instellen, volgt u de volgende stappen:

1.  Meld u aan bij het Microsoft Endpoint Manager-beheercentrum.
2.  Selecteer **Apps > beleid voor Office-apps > Maken**
3.  Ga als **volgt te werk** op de pagina Beleidsconfiguratie maken:
    - Voer een naam in.
    - Geef een beschrijving op (optioneel).
    - Kies **in opdrachten** of dit beleid van toepassing is op alle gebruikers van Microsoft 365 Apps voor ondernemingen of alleen voor gebruikers die anoniem toegang hebben tot documenten met Office voor het web.
    - Selecteer de op AAD gebaseerde beveiligingsgroep die is toegewezen aan de beleidsconfiguratie. Elke beleidsconfiguratie kan slechts aan één groep worden toegewezen en aan elke groep kan slechts één beleidsconfiguratie worden toegewezen.
    - Configureer de beleidsinstellingen die moeten worden opgenomen in de beleidsconfiguratie. U kunt zoeken op de naam van de beleidsinstelling om de beleidsinstelling te zoeken die u wilt configureren. U kunt ook filteren op de toepassing, op de vraag of het beleid een aanbevolen beveiligingslijn is en of het beleid is geconfigureerd. De platformkolom geeft aan of het beleid wordt toegepast op Microsoft 365 Apps voor ondernemingen voor Windows-apparaten, Office voor het web of alles.
4.  Nadat u de selecties hebt gemaakt, kiest u **Maken.**

> [!NOTE]
> Office-configuratiebeleid biedt alleen ondersteuning voor implementatie op basis van gebruikers