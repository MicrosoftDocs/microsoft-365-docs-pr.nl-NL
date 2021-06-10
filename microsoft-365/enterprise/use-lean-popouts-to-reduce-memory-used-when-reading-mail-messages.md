---
title: Lean pop-outs gebruiken om het geheugen te verminderen dat wordt gebruikt bij het lezen van e-mailberichten
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a6d6ba01-2562-4c3d-a8f1-78748dd506cf
f1.keywords:
- NOCSH
description: Dit artikel bevat informatie over het gebruik van lean pop-outs om de downloadprestaties van berichten in Outlook op internet te verbeteren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0fec3e0267b7299e34de541a184cf92e99e260f1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925254"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a>Lean pop-outs gebruiken om het geheugen te verminderen dat wordt gebruikt bij het lezen van e-mailberichten

Dit artikel bevat informatie over het verbeteren van de downloadprestaties van berichten in Outlook op internet. Dit artikel maakt deel uit van de [netwerkplanning en prestatieafstemming voor Office 365](./network-planning-and-performance.md) project.
  
Als Office 365 globale beheerder kunt u Outlook op internet configureren om lean _pop-outs_ te leveren, een kleinere, minder geheugenintensieve versie van bepaalde e-mailberichten in Microsoft Edge of Internet Explorer. Wanneer lean pop-outs zijn geconfigureerd voor Outlook op internet, worden weergegeven onderdelen aan de server geladen die de prestaties optimaliseren.
  
> [!NOTE]
> Vanaf maart 2018 zijn lean pop-outs niet beschikbaar voor berichten waarin gebruiksrechtenbeperkingen worden opgegeven, zoals IRM (Information Rights Management).
  
Deze functies blijven werken in het hoofdvenster, maar zijn niet beschikbaar in lean pop-outs:
  
- Outlook invoegvoegingen
  
- Skype voor Bedrijven aanwezigheid
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a>Lean pop-outs configureren voor alle gebruikers binnen uw Office 365 organisatie
  
1. [Verbinding maken om Exchange Online Externe PowerShell te gebruiken.](/powershell/exchange/connect-to-exchange-online-powershell)
  
2. Voer de [cmdlet Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) uit met de parameter LeanPopoutEnabled als volgt:

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  Als u bijvoorbeeld lean pop-outs wilt inschakelen voor alle gebruikers in uw organisatie:
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  Lean-pop-outs uitschakelen voor alle gebruikers in uw organisatie:

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```