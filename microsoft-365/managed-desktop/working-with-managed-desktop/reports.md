---
title: Werken met rapporten
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a80616b58298ba544b9eab1d19ffb77f0e6825d4
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921348"
---
# <a name="work-with-reports"></a>Werken met rapporten

Microsoft Managed Desktop biedt verschillende rapporten en dashboards die IT-beheerders in uw organisatie kunnen gebruiken om inzicht te krijgen in de verschillende aspecten van de populatie van apparaten.U vindt rapporten op twee locaties: in [Microsoft Endpoint Manager](https://endpoint.microsoft.com) en in het [Microsoft 365-beheercentrum.](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop) 

## <a name="reports-in-microsoft-endpoint-manager"></a>Rapporten in Microsoft Endpoint Manager

De Microsoft Endpoint Manager-console brengt rapportages van verschillende producten samen op één locatie om problemen met de configuratie en apparaten van uw Azure AD-organisatie ('tenant') te controleren en te onderzoeken. Het beheerde bureaublad van Microsoft bevat een sectie onder Rapporten **in** het hoofdmenu waar u rapporten kunt vinden die specifiek zijn voor het beheer van microsoft Beheerd bureaublad van de apparaten die u hebt geregistreerd.

Deze rapporten omvatten:
- **Beheerde apparaten**  >  **Functie-updates:** in deze weergave ziet u de algehele status van functie-updates op uw microsoft Beheerde bureaublad-apparaten.
- **Beheerde apparaten**  >  **Office-updates:** in deze weergave ziet u de algehele status van Office-updates op uw Microsoft Managed Desktop-apparaten.

Bovendien kunt u op verschillende locaties in Microsoft Endpoint Manager rapporten uit andere productgroepen filteren om uw apparaten die worden beheerd door het beheerde bureaublad van Microsoft, specifiek op te nemen of uit te sluiten. Deze rapporten hebben deze filtermogelijkheden geïntegreerd:

- [Alle apparaten](https://docs.microsoft.com/mem/intune/remote-actions/device-management#get-to-your-devices)
- [Apparaat compliance](https://docs.microsoft.com/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [Niet-compatibele apparaten](https://docs.microsoft.com/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> Aangepaste rollen in het beheerde bureaublad van Microsoft garanderen alleen toegang tot de rapporten van Microsoft Beheerd bureaublad. Zie Toegangsbeheer op basis van rollen met Microsoft Intune voor toegang tot andere onderdelen [van Microsoft Eindpuntbeheer, zoals Alle apparaten.](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control) 

## <a name="reports-in-microsoft-365-admin-center"></a>Rapporten in het Microsoft 365-beheercentrum

U kunt inzichten in Microsoft Managed Desktop insights vinden door het Microsoft  [365-beheercentrum](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)te openen, naar Rapporten te gaan en **Microsoft Managed Desktop te selecteren.** U kunt ook de directe koppeling naar deze rapporten volgen op het tabblad **Microsoft Beheerd bureaublad** op de startpagina van Microsoft [Endpoint Manager.](https://endpoint.microsoft.com) 

Deze rapporten omvatten: 

- [Gebruiksinzichten:](usage-insights.md) deze weergave bevat gebruiksgegevens voor uw door Microsoft beheerde bureaubladapparaten.
- [Betrouwbaarheidsinzichten:](reliability-insights.md) deze weergave bevat een overzicht van de status van uw beheerde apparaten.
- [Batterijinzichten:](battery-insights.md) in deze weergave ziet u informatie over het energieverbruik van apps en de verwachte levensduur van de batterij voor apparaten in uw omgeving.
- [Inzichten in Windows-beveiligingsupdates:](security-update-insights.md) deze weergave toont informatie over de status van beveiligingsupdates voor uw beheerde bureaubladapparaten van Microsoft.

 ## <a name="inventory-data"></a>Voorraadgegevens

Naast de andere rapporten kunt u ook informatie exporteren over de apparaten die worden beheerd met het beheerde bureaublad van Microsoft. In de **weergave Apparaten** van het **gebied Apparaten** van Microsoft Endpoint Manager gebruikt u het tabblad Alles exporteren om een gedetailleerd  [voorraadrapport te downloaden.](device-inventory-report.md)
