---
title: Werken met rapporten
description: De verschillende rapporten die beschikbaar zijn in Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: b37ce09a0781aa83970502224ddbb3658ed07d69
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771883"
---
# <a name="work-with-reports"></a>Werken met rapporten

Microsoft Managed Desktop bevat verschillende rapporten en dashboards die IT-beheerders in uw organisatie kunnen gebruiken om verschillende aspecten van de populatie van apparaten te begrijpen. 

## <a name="reports-in-microsoft-endpoint-manager"></a>Rapporten in Microsoft Endpoint Manager

De Microsoft Endpoint Manager console brengt rapportage van verschillende producten samen op één locatie om u te helpen bij het controleren en onderzoeken van problemen met uw Azure AD-organisatie ("tenant")-configuratie en -apparaten. Microsoft Managed desktop heeft een sectie onder **Rapporten** in het hoofdmenu waar u rapporten kunt vinden die specifiek zijn voor het beheer Microsoft Managed Desktop van de apparaten die u hebt geregistreerd.

Deze rapporten omvatten:
- **Beheerde apparaten**  >  **Functie-updates:** in deze weergave ziet u de algehele status van functie-updates op uw Microsoft Managed Desktop apparaten.
- **Beheerde apparaten**  >  **Office updates:** in deze weergave ziet u de algehele status van Office updates op uw Microsoft Managed Desktop apparaten.

Bovendien kunt u op verschillende locaties in Microsoft Endpoint Manager rapporten van andere productgroepen filteren om uw apparaten die worden beheerd door Microsoft Managed Desktop. Deze rapporten hebben deze filterfunctie geïntegreerd:

- [Alle apparaten](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [Apparaat compliance](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [Niet-compatibele apparaten](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> Aangepaste Microsoft Managed Desktop garanderen alleen toegang tot de Microsoft Managed Desktop rapporten. Zie Op Microsoft Endpoint Manager rollen gebaseerd toegangsbeheer met [Microsoft Intune.](/mem/intune/fundamentals/role-based-access-control)  

## <a name="endpoint-analytics"></a>Eindpuntanalyse
Microsoft Managed Desktop is nu geïntegreerd met [Endpoint-analyse.](/mem/analytics/overview) Deze rapporten geven u inzichten om te meten hoe uw organisatie werkt en de kwaliteit van de ervaring die aan uw gebruikers wordt geleverd. Eindpuntanalyse staat in **het** menu Rapporten van [Microsoft Endpoint Manager.](https://endpoint.microsoft.com/) Als u een score wilt draaien om alleen apparaten op te nemen  die worden beheerd door Microsoft Managed Desktop naar een rapport gaan, selecteert u de vervolgkeuzekeuze en selecteert u Microsoft Managed Desktop **apparaten.**

Als Endpoint-analyse niet automatisch is geconfigureerd voor uw Azure AD-organisatie ("tenant") tijdens de inschrijving, kunt u dat zelf doen. Zie Onboard [in de Endpoint-analyseportal](/mem/analytics/enroll-intune#bkmk_onboard)voor meer informatie. U kunt al uw apparaten registreren of, als u alleen Microsoft Managed Desktop  apparaten wilt opnemen, de moderne apparaatgroepen op de werkplek selecteren voor Test, First, Fast en Broad. Voor deze rapporten zijn mogelijk verschillende machtigingen vereist. Zie Machtigingen om [ervoor te](/mem/analytics/overview#permissions) zorgen dat u rollen op de juiste manier hebt toegewezen voor meer informatie.

> [!NOTE]
> Als u de privacy van de privacy van gebruikers beter wilt respecteren, moeten er meer dan 10 Microsoft Managed Desktop zijn geregistreerd met Endpoint-analyse om dit filter te kunnen gebruiken.

 ## <a name="inventory-data"></a>Voorraadgegevens

Naast de andere rapporten kunt u informatie exporteren over de apparaten die worden beheerd door Microsoft Managed Desktop. Gebruik in **de** weergave Apparaten van **het** gebied Apparaten van Microsoft Endpoint Manager het tabblad Alles **exporteren** om een gedetailleerd [voorraadrapport te downloaden.](device-inventory-report.md)
