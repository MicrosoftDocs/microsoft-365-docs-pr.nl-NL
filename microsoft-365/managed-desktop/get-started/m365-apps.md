---
title: Microsoft 365-apps voor ondernemingen
description: Hoe implementeert u Microsoft 365-apps, hoe ze worden bijgewerkt en hoe instellingen worden beheerd
keywords: wijzigingsgeschiedenis
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 7b1178312178865face58748a37228f60643d5fc
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287973"
---
# <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365-apps voor ondernemingen

## <a name="initial-deployment"></a>Eerste implementatie

Microsoft Managed Desktop zorgt ervoor dat Microsoft 365-apps voor ondernemingen (64-bits) worden geïnstalleerd als onderdeel van de afbeelding op alle [programmaapparaten.](../service-description/device-list.md) Alle volgende toepassingen moeten aanwezig zijn op het apparaat wanneer deze worden geleverd:

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
> Microsoft Teams wordt afzonderlijk van de Microsoft 365-apps voor ondernemingen geïmplementeerd en wordt niet opgenomen in de basisafbeelding. 

### <a name="available-deployment-to-users"></a>Beschikbare implementatie voor gebruikers

Als een gebruiker om Microsoft 365-apps reden geen toegang heeft tot het apparaat, kunt u een pakket gebruiken om het apparaat terug te geven naar de verwachte status. Voeg de gebruiker toe aan de **groep Modern Workplace-Office-Office365_Install** en de apps zijn beschikbaar in de Bedrijfsportal.

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a>Microsoft 365-apps voor ondernemingen (32-bits)

Microsoft Managed Desktop biedt geen ondersteuning voor de implementatie van de 32-bits versie van M365-apps voor ondernemingen.

## <a name="updates-to-microsoft-365-apps"></a>Updates voor Microsoft 365-apps

Microsoft 365-apps zijn ingesteld op bijwerken op [het Monthly Enterprise-kanaal](/deployoffice/overview-update-channels#monthly-enterprise-channel-overview). Deze oefening biedt uw gebruikers elke Office nieuwe functies, maar ze ontvangen slechts één update per maand volgens een voorspelbaar releaseschema. Updates worden uitgebracht op de tweede dinsdag van de maand. Deze updates kunnen functie-, beveiligings- en kwaliteitsupdates bevatten. Deze updates worden automatisch uitgevoerd en worden rechtstreeks uit de Office CDN voor dat specifieke kanaal gehaald.

Microsoft Managed Desktop elke release om mogelijke problemen in uw omgeving te identificeren. We voltooien de implementatie 28 dagen na de release van de Microsoft 365 App-productgroep. Microsoft Managed Desktop geplande updatereleases voor verschillende groepen, zodat er tijd beschikbaar is voor validatie en testen als volgt: 

- Test: nul dagen
- Ten eerste: nul dagen
- Snel: 3 dagen
- Breed: 7 dagen

Microsoft Managed Desktop stelt een updatedeadline van [zeven dagen in](/deployoffice/configure-update-settings-microsoft-365-apps) voor apparaten. Zodra de update beschikbaar is, moet deze binnen zeven dagen zijn geïnstalleerd. Gebruikers krijgen [een](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) melding dat updates vereist zijn op verschillende locaties: de toepassing, in het systeemvak 12 uur vóór de deadline, en ze ontvangen een waarschuwing van 15 minuten vóór de deadline. Alle Microsoft 365-apps moeten worden gesloten om de update te voltooien.

### <a name="pausing-or-rolling-back-an-update"></a>Een update onderbreken of terugrollen

Als u de app-update om Microsoft 365 reden wilt onderbreken of terugdraaien, dient u een ondersteuningsaanvraag voor beheerders in [via](../working-with-managed-desktop/admin-support.md) de Microsoft Managed Desktop portal.

Tijdens een release worden Microsoft Managed Desktop de foutpercentages van alle Microsoft 365-apps. Als we een aanzienlijk kwaliteitsverschil zien tussen de nieuwe release en de voorganger, kunnen we contact met u opnemen via de Microsoft Managed Desktop Admin portal. Afhankelijk van de ernst wordt u gevraagd of u de release wilt onderbreken of dat we actie hebben ondernomen om een probleem te beperken. 

### <a name="delivery-optimization"></a>Leveringsoptimalisatie

Delivery Optimization is een peer-to-peer distributietechnologie die beschikbaar is in Windows 10. Hiermee kunnen apparaten inhoud delen, zoals updates, die de apparaten via internet van Microsoft hebben gedownload. Als u de update gebruikt, kunt u de netwerkbandbreedte verminderen omdat een apparaat delen van de update van een ander apparaat op het lokale netwerk kan downloaden in plaats van de update volledig van Microsoft te moeten downloaden.

[Leveringsoptimalisatie](/deployoffice/delivery-optimization) is standaard ingeschakeld op apparaten met de Windows 10 Enterprise of Windows 10 Education versies. 

## <a name="settings-managed-by-microsoft-managed-desktop"></a>Instellingen beheerd door Microsoft Managed Desktop

Microsoft beheert sommige instellingen als onderdeel van de service. Microsoft Managed Desktop beheert geen basislijn voor Office beveiliging, maar u kunt er zelf een instellen door de richtlijnen te volgen in de sectie Instellingen u [beheert.](#settings-you-manage)

### <a name="update-settings"></a>Update-instellingen

Microsoft Managed Desktop alle [update-instellingen voor](/deployoffice/configure-update-settings-microsoft-365-apps) beheerde apparaten behouden en u moet deze instellingen wijzigen.

### <a name="set-updates-to-occur-automatically"></a>Updates automatisch instellen

**Standaardwaarde**: Ingeschakeld

Dit beleid is geconfigureerd om ervoor te zorgen dat Office apparaten up-to-date kunnen blijven vanuit de cloud. 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a>Een deadline instellen wanneer updates moeten worden toegepast

**Standaardwaarde**: 7 dagen

Het **UpdateDeadline-beleid** wordt gebruikt om de respijtperiode te configureren die gebruikers hebben voordat een update wordt afgedwongen op het apparaat. Dit deadlinebeleid activeert ook [meldingen aan](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) de gebruiker om hem of haar te informeren over de wijzigingen die op het apparaat zijn vereist.  

### <a name="defer-updates-on-a-device-for-a-period"></a>Updates op een apparaat een bepaalde periode uitstellen

Dit beleid is anders geconfigureerd voor elke updatebeheerapparaatgroep en is vereist om Microsoft Managed Desktop de updatedoelen te kunnen bereiken:  

- Test: nul dagen
- Ten eerste: nul dagen
- Snel 7 dagen
- Breed: 21 dagen

### <a name="update-notifications-settings"></a>Instellingen voor meldingen bijwerken

**Standaardwaarde:** Onwaar

De instelling Updatemeldingen verbergen is  ingesteld op Onwaar op Microsoft Managed Desktop apparaten om [](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) gebruikers de beste update-ervaring te bieden door hen te informeren wanneer updates vereist zijn.

### <a name="specify-a-location-to-look-for-updates"></a>Een locatie opgeven om te zoeken naar updates

**Standaardwaarde:** Monthly Enterprise-kanaal

Een combinatie van het **UpdatePath-** en **UpdateChannel-beleid** wordt zo nodig gebruikt om de updateplanning te bereiken. Dit beleid is ingesteld om ervoor te zorgen dat Office apparaten rechtstreeks updates ontvangen van de CDN voor het Monthly Enterprise-kanaal.

### <a name="specify-the-target-version-of-microsoft-365-apps"></a>Geef de doelversie van Microsoft 365-apps

Het beleid doelversie wordt soms gebruikt door Microsoft Managed Desktop om een specifieke versie van de Office. 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a>De optie voor het in- of uitschakelen van automatische Office verbergen

**Standaardwaarde**: Ingeschakeld

Deze instelling is vereist om Microsoft Managed Desktop te voldoen aan de updatedoelen voor Microsoft 365 toepassingen. 

### <a name="first-run-settings"></a>Instellingen voor het eerst uitvoeren 

Er zijn verschillende instellingen die van invloed zijn op het gedrag dat de eerste keer Office wordt uitgevoerd.

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a>De licentievoorwaarden namens de eindgebruiker accepteren

**Standaardwaarde**: Uitgeschakeld

De eerste keer dat een gebruiker een Microsoft 365 app opent, wordt hij of zij gevraagd de licentievoorwaarden te accepteren. Als u de licentievoorwaarden namens uw gebruikers wilt accepteren, moet u een serviceaanvraag indienen bij het Microsoft Managed Desktop Operations-team waarin u wordt gevraagd deze instelling in te stellen. 

### <a name="suppress-outlook-mobile-check-box"></a>Selectievakje Outlook mobiel onderdrukken

**Standaardwaarde**: Uitgeschakeld

De eerste keer dat een gebruiker een Outlook wordt hem of haar gevraagd om een Outlook installeren. Als u niet wilt dat uw gebruikers dit selectievakje zien, kunt u een serviceaanvraag indienen bij het Microsoft Managed Desktop Operations-team met de vraag of deze instelling is ingeschakeld voor uw apparaten. 

## <a name="other-settings"></a>Andere instellingen

Er zijn andere Microsoft 365 app-instellingen die Microsoft Managed Desktop u desgewenst namens u kunt configureren. 

### <a name="disable-personal-onedrive"></a>Persoonlijke OneDrive

**Standaardwaarde**: Uitgeschakeld

Sommige organisaties maken zich zorgen over gebruikers die toegang hebben tot zowel zakelijke als persoonlijke bestanden op hun apparaten. U kunt een serviceaanvraag indienen bij het Microsoft Managed Desktop Operations-team waarin wordt gevraagd of deze instelling moet worden ingeschakeld. 

## <a name="settings-you-manage"></a>Instellingen beheren

Er zijn veel andere beleidsregels Microsoft Managed Desktop nog niet als onderdeel van onze service is ingesteld. U kunt dit beleid configureren met Microsoft Intune, die gebruikmaakt van Office cloudbeleidsservice. [](/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) Als u dit beleid wilt instellen, volgt u de volgende stappen:

1. Meld u aan bij het Microsoft Endpoint Manager beheercentrum.
2. Selecteer **Apps > beleid voor Office apps > Maken**
3. Ga als **volgt te werk** op de pagina Beleidsconfiguratie maken:
    - Voer een naam in.
    - Geef een beschrijving op (optioneel).
    - Kies **in opdrachten** of dit beleid van toepassing is op alle gebruikers van Microsoft 365-apps voor ondernemingen of alleen op gebruikers die anoniem documenten openen met webversie van Office.
    - Selecteer de op AAD gebaseerde beveiligingsgroep die is toegewezen aan de beleidsconfiguratie. Elke beleidsconfiguratie kan slechts aan één groep worden toegewezen en aan elke groep kan slechts één beleidsconfiguratie worden toegewezen.
    - Configureer de beleidsinstellingen die moeten worden opgenomen in de beleidsconfiguratie. U kunt zoeken op de naam van de beleidsinstelling om de beleidsinstelling te zoeken die u wilt configureren. U kunt ook filteren op de toepassing, op de vraag of het beleid een aanbevolen beveiligingslijn is en of het beleid is geconfigureerd. De platformkolom geeft aan of het beleid wordt toegepast op Microsoft 365-apps voor ondernemingen voor Windows apparaten, webversie van Office of alle apparaten.
4. Nadat u de selecties hebt gemaakt, kiest u **Maken.**

> [!NOTE]
> Office Configuratiebeleid biedt alleen ondersteuning voor implementatie op basis van gebruikers
