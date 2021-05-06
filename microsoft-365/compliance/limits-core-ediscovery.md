---
title: Limieten in hoofd-eDiscovery-zaak
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: In dit artikel worden de limieten beschreven in het hoofd-eDiscovery-geval in Microsoft 365.
ms.openlocfilehash: e18e1e6c1d9d7ecd78deaf267be72ccdc9d1ba5d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161764"
---
# <a name="limits-in-core-ediscovery"></a>Limieten in Core eDiscovery

In de volgende tabel worden de limieten voor kern-eDiscovery-zaken en -gegevens vermeld die zijn gekoppeld aan een kern-eDiscovery-zaak. Zie Overzicht van Core eDiscovery voor meer informatie over Core [eDiscovery.](./get-started-core-ediscovery.md)
    
  | Beschrijving van limiet | Limiet |
  |:-----|:-----|
  |Maximum aantal zaken voor een organisatie.  <br/> |Geen limiet  <br/> |
  |Maximum aantal case-holds voor een organisatie.  <br/> |10,000  <br/> |
  |Maximum aantal postvakken in één case hold. Deze limiet omvat het gecombineerde totaal van gebruikerspostvakken en de postvakken die zijn gekoppeld aan Microsoft 365 Groepen, Microsoft Teams en Yammer Groepen.  <br/> |1,000  <br/> |
  |Maximum aantal sites in één geval. Deze limiet omvat het gecombineerde totaal OneDrive voor Bedrijven sites, SharePoint sites en de sites die zijn gekoppeld aan Microsoft 365 Groepen, Microsoft Teams en Yammer Groepen.  <br/> |100  <br/> |
  |Het maximum aantal zaken dat wordt weergegeven op de basis-startpagina van eDiscovery en het maximum aantal items dat wordt weergegeven op de tabbladen Houdt, Zoekopdrachten en Exporteren in een zaak. <sup>1</sup> |1,000|
  |||

   > [!NOTE]
   > <sup>1</sup> Als u een lijst wilt weergeven met meer dan 1.000 gevallen, opgeslagen, gezocht of exporteert, kunt u de bijbehorende Office 365 Security & Compliance PowerShell-cmdlets gebruiken:
   > 
   > - [Get-ComplianceCase](/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](/powershell/module/exchange/get-compliancesearchaction)

Zie Limieten voor zoeken naar inhoud en Core [eDiscovery](limits-for-content-search.md)voor meer informatie over limieten voor het zoeken en exporteren van inhoud die zijn gekoppeld aan een core eDiscovery-zaak.