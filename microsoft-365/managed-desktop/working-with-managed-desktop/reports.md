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
ms.openlocfilehash: bfd8305d23e0e6d761c629ee3048c6204f702d37
ms.sourcegitcommit: 98146c67a1d99db5510fa130340d3b7be8d81b21
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/07/2020
ms.locfileid: "49585326"
---
# <a name="work-with-reports"></a>Werken met rapporten

Microsoft Managed Desktop biedt diverse rapporten en dashboards die IT-beheerders in uw organisatie kunnen gebruiken om verschillende aspecten van de bevolking van apparaten te begrijpen.U vindt rapporten op twee locaties: in [Microsoft Endpoint Manager](https://endpoint.microsoft.com) en in het [Microsoft 365-Beheercentrum](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop). 

## <a name="reports-in-microsoft-endpoint-manager"></a>Rapporten in Microsoft Endpoint Manager

Met de Microsoft Endpoint Manager-console deelt u rapporten van diverse producten naar één locatie, zodat u problemen kunt controleren en onderzoeken met de configuratie en apparaten van Azure AD organisatie (Tenant). Het Microsoft-beheer bureaublad heeft een sectie onder **rapporten** in het hoofdmenu, waar u rapporten kunt vinden voor het beheer van het Microsoft-beheerapparaat van de apparaten die u hebt geregistreerd.

Daarnaast kunt u op verschillende locaties in Microsoft-eindpunten rapporten filteren op basis van andere productgroepen, zodat u alleen uw apparaten kunt opnemen of uitsluiten die door Microsoft worden beheerd. Voor deze rapporten is de volgende filterfunctie geïntegreerd:

- **Alle apparaten**
- **Apparaatcompatibiliteit**
- **Niet-compatibele apparaten**

> [!NOTE]
> Aangepaste Microsoft beheerde bureaublad rollen garanderen alleen toegang tot de Microsoft beheerde bureaublad rapporten. Zie [toegangsbeheer op basis van rollen met Microsoft intune](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control)voor informatie over toegang tot andere onderdelen van Microsoft Endpoint Manager, zoals **alle apparaten**. 

## <a name="reports-in-microsoft-365-admin-center"></a>Rapporten in het Beheercentrum van Microsoft 365

U vindt Microsoft Managed Desktop inzichten-rapporten door het [Microsoft 365-Beheercentrum](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)te openen en vervolgens te navigeren naar **rapporten** en door **Microsoft beheerde bureaublad** te selecteren. U kunt ook de directe koppeling naar deze rapporten volgen via het tabblad **Microsoft Managed Desktop** op de startpagina van [Microsoft Endpoint Manager](https://endpoint.microsoft.com). 

Dit rapport bevat de volgende informatie: 

- [Gebruiks inzichten](usage-insights.md) : in deze weergave worden gebruiksgegevens weergegeven voor uw door Microsoft beheerde bureaublad apparaten.
- [Betrouwbaarheid-inzichten](reliability-insights.md) : in deze weergave ziet u een overzicht van de status van uw beheerde apparatuur.
- [Batterij inzichten](battery-insights.md) : in deze weergave ziet u informatie over het energieverbruik van apps en de geprojecteerde acculevensduur voor apparaten in uw omgeving.
- [Windows beveiligingsupdate inzichten](security-update-insights.md) : in deze weergave ziet u informatie over de status van beveiligingsupdates voor uw door Microsoft beheerde bureaublad apparaten.

 ## <a name="inventory-data"></a>Inventarisatiegegevens

Naast de andere rapporten kunt u informatie exporteren over de apparaten die door Microsoft worden beheerd. In de weergave **apparaten** van het gebied **apparaten** van Microsoft Endpoint Manager gebruikt u het tabblad **Alles exporteren** om [een gedetailleerd inventarisatie rapport te downloaden](device-inventory-report.md).