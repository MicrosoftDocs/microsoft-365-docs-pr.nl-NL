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
ms.openlocfilehash: e509ae63225362613962cd0c366c51239f3d4493
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917680"
---
# <a name="work-with-reports"></a>Werken met rapporten

Microsoft Managed Desktop bevat verschillende rapporten en dashboards die IT-beheerders in uw organisatie kunnen gebruiken om verschillende aspecten van de populatie van apparaten te begrijpen.U vindt rapporten op twee locaties: in [Microsoft Endpoint Manager](https://endpoint.microsoft.com) en in het [Microsoft 365-beheercentrum.](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop) 

## <a name="reports-in-microsoft-endpoint-manager"></a>Rapporten in Microsoft Endpoint Manager

De Microsoft Endpoint Manager-console brengt rapportages van verschillende producten samen op één locatie om u te helpen bij het controleren en onderzoeken van problemen met uw Azure AD-organisatie ("tenant")-configuratie en -apparaten. Microsoft Managed Desktop bevat een sectie onder **Rapporten** in het hoofdmenu waar u rapporten kunt vinden die specifiek zijn voor het beheer van de apparaten die u hebt geregistreerd door Microsoft Managed Desktop.

Deze rapporten omvatten:
- **Beheerde apparaten**  >  **Functie-updates:** in deze weergave ziet u de algehele status van functie-updates op uw beheerde bureaubladapparaten van Microsoft.
- **Beheerde apparaten**  >  **Office-updates:** in deze weergave ziet u de algehele status van Office-updates op uw Beheerde bureaublad-apparaten van Microsoft.

Bovendien kunt u op verschillende locaties in Microsoft Endpoint Manager rapporten uit andere productgroepen filteren om specifiek uw apparaten op te nemen of uit te sluiten die worden beheerd door Microsoft Managed Desktop. Deze rapporten hebben deze filterfunctie geïntegreerd:

- [Alle apparaten](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [Apparaat compliance](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [Niet-compatibele apparaten](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> Aangepaste Microsoft Managed Desktop-rollen garanderen alleen toegang tot de Microsoft Managed Desktop-rapporten. Zie Toegangsbeheer op basis van rollen met [Microsoft Intune](/mem/intune/fundamentals/role-based-access-control)voor toegang tot andere onderdelen van Microsoft Endpoint Manager, zoals Alle apparaten. 

## <a name="reports-in-microsoft-365-admin-center"></a>Rapporten in microsoft 365-beheercentrum

U kunt microsoft Managed Desktop Insights-rapporten vinden door het [Microsoft 365-beheercentrum](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)te openen en vervolgens naar Rapporten te navigeren en Microsoft Beheerd bureaublad **te selecteren.**  U kunt ook de directe koppeling naar deze rapporten volgen op het tabblad Beheerd bureaublad van **Microsoft** op de startpagina [van Microsoft Endpoint Manager.](https://endpoint.microsoft.com) 

Deze rapporten omvatten: 

- [Gebruiksinzichten:](usage-insights.md) deze weergave bevat gebruiksgegevens voor uw beheerde bureaubladapparaten van Microsoft.
- [Betrouwbaarheidsinzichten:](reliability-insights.md) in deze weergave krijgt u een overzicht van de status van uw beheerde apparaten.
- [Batterijinzichten:](battery-insights.md) in deze weergave ziet u informatie over het energieverbruik van apps en de verwachte levensduur van de batterij voor apparaten in uw omgeving.
- [Inzichten in Windows-beveiligingsupdates:](security-update-insights.md) in deze weergave ziet u informatie over de status van beveiligingsupdates voor uw Microsoft Managed Desktop-apparaten.

 ## <a name="inventory-data"></a>Voorraadgegevens

Naast de andere rapporten kunt u informatie exporteren over de apparaten die worden beheerd door Microsoft Managed Desktop. Gebruik in **de** weergave Apparaten **van het** gebied Apparaten van Microsoft Endpoint Manager het tabblad Alles **exporteren** om een [gedetailleerd voorraadrapport te downloaden.](device-inventory-report.md)