---
title: Microsoft 365-apps voor ondernemingen
description: Microsoft 365-apps implementeren, hoe deze worden bijgewerkt en hoe instellingen worden beheerd
keywords: wijzigingsgeschiedenis
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 26e62d6e59f1f90e35d9e18e6eed917a66876645
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453919"
---
# <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365-apps voor ondernemingen

## <a name="initial-deployment"></a>Eerste implementatie

Microsoft Managed Desktop zorgt ervoor dat Microsoft 365-apps voor ondernemingen (64 bits) als onderdeel van de afbeelding worden geïnstalleerd op alle [programmaapparaten.](../service-description/device-list.md) Alle volgende toepassingen moeten aanwezig zijn op het apparaat wanneer het wordt geleverd:

- Word
- Excel
- PowerPoint
- Outlook
- Publisher
- Toegang
- Skype voor Bedrijven
- OneNote

Deze methode minimaliseert de invloed op het netwerk en zorgt ervoor dat gebruikers productief kunnen zijn zodra ze hun apparaat ontvangen. Vervolgens implementeren we meer beleidsregels op beheerde apparaten om de toepassingen in te stellen voor gebruik.

> [!NOTE]
> Microsoft Teams wordt afzonderlijk van Microsoft 365 Apps voor ondernemingen geïmplementeerd en is niet opgenomen in de basisafbeelding. 

### <a name="available-deployment-to-users"></a>Beschikbare implementatie voor gebruikers

Als een gebruiker om welke reden dan ook geen Microsoft 365-apps op zijn apparaat heeft, kunt u een pakket gebruiken om het apparaat terug te keren naar de verwachte status. Voeg de gebruiker toe aan de **groep Modern Workplace-Office-Office365_Install** en de apps komen beschikbaar in de bedrijfsportal.

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a>Microsoft 365-apps voor ondernemingen (32-bits)

Microsoft Beheerd bureaublad biedt geen ondersteuning voor de implementatie van de 32-bits versie van M365-apps voor ondernemingen.

## <a name="updates-to-microsoft-365-apps"></a>Updates voor Microsoft 365-apps

Microsoft 365-apps zijn ingesteld voor update op [het Monthly Enterprise-kanaal.](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview) Deze oefening biedt uw gebruikers elke maand nieuwe Office-functies, maar ze ontvangen slechts één update per maand volgens een voorspelbaar releaseschema. Updates worden uitgebracht op de tweede dinsdag van de maand. deze updates kunnen functie-, beveiligings- en kwaliteitsupdates bevatten. Deze updates worden automatisch uitgevoerd en worden rechtstreeks vanuit het Office-CDN voor dat specifieke kanaal gehaald.

Microsoft Managed Desktop versprongen elke release om potentiële problemen in uw omgeving te identificeren. De implementatie is 28 dagen na de release van de Microsoft 365 App-productgroep voltooid. Met Microsoft Managed Desktop worden updatereleases voor verschillende groepen gepland, zodat u de validatie en tests als volgt kunt uitvoeren: 

- Test: nul dagen
- Eerste: nul dagen
- Snel: 3 dagen
- Ruim: 7 dagen

Microsoft Managed Desktop stelt een updatedeadline van zeven dagen [in](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) voor apparaten. Wanneer de update beschikbaar is, moet deze binnen zeven dagen worden geïnstalleerd. Gebruikers krijgen [een](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) melding dat updates op verschillende locaties zijn vereist: de toepassing, in het systeemvak 12 uur voor de deadline, en ze ontvangen een waarschuwing van 15 minuten vóór de deadline. Alle Microsoft 365-apps moeten worden gesloten om de update te voltooien.

### <a name="pausing-or-rolling-back-an-update"></a>Een update onderbreken of terugrollen

Als u de microsoft 365-app-update om welke reden dan ook wilt onderbreken of terugdraaien, kunt u een aanvraag voor ondersteuning voor beheerders indienen [via](../working-with-managed-desktop/admin-support.md) de portal voor Microsoft Managed Desktop.

Tijdens een release houdt Microsoft Managed Desktop de fouttarieven van alle Microsoft 365-apps in de gaten. Als we een aanzienlijk verschil zien in kwaliteit tussen de nieuwe release en de voorafgaande versie, kunnen we contact met u opnemen via de portal voor beheerde bureaubladbeheerder van Microsoft. Afhankelijk van de ernst wordt u gevraagd of u de release wilt onderbreken of dat er actie is ondernomen om het probleem te beperken. 

### <a name="delivery-optimization"></a>Verzendingsoptimalisatie

Delivery Optimization is een peer-to-peer distributietechnologie die beschikbaar is in Windows 10. Hiermee kunnen apparaten inhoud delen, zoals updates, die de apparaten via internet van Microsoft hebben gedownload. Als u dit gebruikt, kunt u de netwerkbandbreedte verminderen omdat een apparaat delen van de update kan downloaden van een ander apparaat op het lokale netwerk in plaats van de update volledig bij Microsoft te moeten downloaden.

[Leveringsoptimalisatie](https://docs.microsoft.com/deployoffice/delivery-optimization) is standaard ingeschakeld op apparaten met de edities Windows 10 Enterprise of Windows 10 Education. 

## <a name="settings-managed-by-microsoft-managed-desktop"></a>Instellingen die worden beheerd door het beheerde bureaublad van Microsoft

Microsoft beheert bepaalde instellingen als onderdeel van de service. Microsoft Beheerd bureaublad beheert geen basislijn voor Office-beveiliging, maar u kunt er zelf een instellen door de richtlijnen te volgen in de sectie Instellingen [die u](#settings-you-manage) beheert.

### <a name="update-settings"></a>Instellingen bijwerken

Microsoft Managed Desktop behoudt alle [update-instellingen](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) voor beheerde apparaten en u moet deze instellingen wijzigen.

### <a name="set-updates-to-occur-automatically"></a>Instellen dat updates automatisch worden uitgevoerd

**Standaardwaarde:** ingeschakeld

Dit beleid is geconfigureerd om ervoor te zorgen dat alle Office-apparaten up-to-date blijven vanuit de cloud. 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a>Een deadline instellen wanneer updates moeten worden toegepast

**Standaardwaarde:** 7 dagen

Het **beleid UpdateDeadline** wordt gebruikt om de respijtperiode te configureren die gebruikers hebben voordat een update wordt afgedwongen op het apparaat. Dit deadlinebeleid activeert de [gebruiker ook](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) om de gebruiker te informeren over de vereiste wijzigingen op het apparaat.  

### <a name="defer-updates-on-a-device-for-a-period"></a>Updates op een apparaat een bepaalde periode uitstellen

Dit beleid is anders geconfigureerd voor elke apparaatgroep voor updatebeheer en is vereist om het beheerde bureaublad van Microsoft te laten voldoen aan de updatedoelen:  

- Test: nul dagen
- Eerste: nul dagen
- Zeven dagen snel
- Ruim: 21 dagen

### <a name="update-notifications-settings"></a>Instellingen voor meldingen bijwerken

**Standaardwaarde:** Onwaar

De instelling 'updatemeldingen verbergen'  is ingesteld op Onwaar op Microsoft Managed [](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) Desktop-apparaten voor de beste update-ervaring voor gebruikers door hen te laten weten wanneer updates vereist zijn.

### <a name="specify-a-location-to-look-for-updates"></a>Een locatie opgeven om te zoeken naar updates

**Standaardwaarde:** Monthly Enterprise-kanaal

Een combinatie van het **UpdatePath-** en **UpdateChannel-beleid** wordt zo nodig gebruikt om de updateplanning te bereiken. Dit beleid is ingesteld om ervoor te zorgen dat alle Office-apparaten updates rechtstreeks ontvangen van het CDN voor het Monthly Enterprise-kanaal.

### <a name="specify-the-target-version-of-microsoft-365-apps"></a>De doelversie van Microsoft 365-apps opgeven

Het beleid doelversie wordt soms gebruikt door beheerd bureaublad van Microsoft om een specifieke versie van Office terug te draaien of vast te maken. 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a>De optie voor het in- of uitschakelen van automatische updates van Office verbergen

**Standaardwaarde:** ingeschakeld

Deze instelling is vereist om Beheerd bureaublad van Microsoft te laten voldoen aan de updatedoelen voor Microsoft 365-toepassingen. 

### <a name="first-run-settings"></a>First run settings 

Er zijn verschillende instellingen die van invloed zijn op het gedrag als Office voor het eerst wordt uitgevoerd.

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a>De licentievoorwaarden namens de eindgebruiker accepteren

**Standaardwaarde:** uitgeschakeld

De eerste keer dat een gebruiker een Microsoft 365-app opent, wordt hem of haar gevraagd de licentievoorwaarden te accepteren. Als u de licentievoorwaarden namens uw gebruikers wilt accepteren, moet u een serviceaanvraag indienen bij het team van Microsoft Managed Desktop Operations waarin u vraagt of deze instelling is ingeschakeld. 

### <a name="suppress-outlook-mobile-check-box"></a>Selectievakje Outlook Mobile onderdrukken

**Standaardwaarde:** uitgeschakeld

De eerste keer dat een gebruiker Outlook opent, wordt hem of haar gevraagd Outlook Mobile te installeren. Als u niet wilt dat uw gebruikers dit selectievakje zien, kunt u een serviceaanvraag indienen bij het team van Microsoft Managed Desktop Operations waarin u vraagt of deze instelling is ingeschakeld voor uw apparaten. 

## <a name="other-settings"></a>Overige instellingen

Er zijn andere microsoft 365 App-instellingen die desgewenst namens u kunnen worden geconfigureerd door Microsoft Managed Desktop. 

### <a name="disable-personal-onedrive"></a>Persoonlijke OneDrive uitschakelen

**Standaardwaarde:** uitgeschakeld

Sommige organisaties maken zich zorgen over het gebruik van bedrijfsbestanden en persoonlijke bestanden op hun apparaten. U kunt een serviceaanvraag indienen bij het team van Microsoft Managed Desktop Operations waarin u wordt gevraagd of deze instelling is ingeschakeld. 

## <a name="settings-you-manage"></a>Instellingen die u beheert

Er zijn nog veel andere beleidsregels die nog niet zijn ingesteld als onderdeel van onze service. U kunt dit beleid configureren met behulp van Microsoft Intune, dat gebruikmaakt van de [Cloudbeleidsservice van Office.](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) Als u dit beleid wilt instellen, gaat u als volgt te werk:

1.  Meld u aan bij het beheercentrum van Microsoft Eindpuntenbeheer.
2.  Apps **en > voor Office-apps selecteren > maken**
3.  Ga als **volgt te werk op** de pagina Beleidsconfiguratie maken:
    - Voer een naam in.
    - Geef een beschrijving op (optioneel).
    - Kies **in toewijzingen** of dit beleid van toepassing is op alle gebruikers van Microsoft 365 Apps voor ondernemingen of alleen op gebruikers die anoniem documenten openen met de web app van Office.
    - Selecteer de op AAD gebaseerde beveiligingsgroep die is toegewezen aan de beleidsconfiguratie. Elke beleidsconfiguratie kan slechts aan één groep worden toegewezen en aan elke groep kan slechts één beleidsconfiguratie worden toegewezen.
    - Configureer de beleidsinstellingen die moeten worden opgenomen in de beleidsconfiguratie. U kunt zoeken op de naam van de beleidsinstelling om de beleidsinstelling te vinden die u wilt configureren. U kunt ook filteren op de toepassing, of het beleid een aanbevolen beveiligingsbasislijn is en of het beleid is geconfigureerd. De platformkolom geeft aan of het beleid wordt toegepast op Microsoft 365 Apps voor Ondernemingen voor Windows-apparaten, Office voor het web of alles.
4.  Nadat u uw selecties hebt gemaakt, kiest u **Maken.**

> [!NOTE]
> Office-configuratiebeleid biedt alleen ondersteuning voor implementatie op basis van gebruikers
