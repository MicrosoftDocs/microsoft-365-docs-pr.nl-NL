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
description: Dit artikel bevat informatie over het gebruik van lean pop-outs om de downloadprestaties van berichten in de webversie van Outlook te verbeteren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0fec3e0267b7299e34de541a184cf92e99e260f1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925254"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a><span data-ttu-id="7fe2c-103">Lean pop-outs gebruiken om het geheugen te verminderen dat wordt gebruikt bij het lezen van e-mailberichten</span><span class="sxs-lookup"><span data-stu-id="7fe2c-103">Use lean popouts to reduce memory used when reading mail messages</span></span>

<span data-ttu-id="7fe2c-104">Dit artikel bevat informatie over het verbeteren van de prestaties van het downloaden van berichten in de webversie van Outlook.</span><span class="sxs-lookup"><span data-stu-id="7fe2c-104">This article contains information for improving message download performance in Outlook on the web.</span></span> <span data-ttu-id="7fe2c-105">Dit artikel maakt deel uit van [de netwerkplanning en prestatieafstemming voor Office 365-project.](./network-planning-and-performance.md)</span><span class="sxs-lookup"><span data-stu-id="7fe2c-105">This article is part of the [Network planning and performance tuning for Office 365](./network-planning-and-performance.md) project.</span></span>
  
<span data-ttu-id="7fe2c-106">Als globale beheerder van Office 365 kunt u de webversie van Outlook zo configureren dat er lean _pop-outs_ worden weergegeven, een kleinere, minder geheugenintensieve versie van bepaalde e-mailberichten in Microsoft Edge of Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="7fe2c-106">As an Office 365 global administrator, you can configure Outlook on the web to deliver _lean popouts_, a smaller, less memory-intensive version of certain email messages in Microsoft Edge or Internet Explorer.</span></span> <span data-ttu-id="7fe2c-107">Wanneer lean pop-outs zijn geconfigureerd voor de webversie van Outlook, worden weergegeven onderdelen aan de server geladen die de prestaties optimaliseren.</span><span class="sxs-lookup"><span data-stu-id="7fe2c-107">When lean popouts are configured for Outlook on the web, server-side rendered components are loaded that optimize performance.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7fe2c-108">Vanaf maart 2018 zijn lean pop-outs niet beschikbaar voor berichten waarin gebruiksrechtenbeperkingen worden opgegeven, zoals IRM (Information Rights Management).</span><span class="sxs-lookup"><span data-stu-id="7fe2c-108">As of March 2018, lean popouts are not available for messages that specify usage rights restrictions, such as Information Rights Management (IRM).</span></span>
  
<span data-ttu-id="7fe2c-109">Deze functies blijven werken in het hoofdvenster, maar zijn niet beschikbaar in lean pop-outs:</span><span class="sxs-lookup"><span data-stu-id="7fe2c-109">These features will continue to work in the main window but are not available in lean popouts:</span></span>
  
- <span data-ttu-id="7fe2c-110">Outlook-invoegvoegingen</span><span class="sxs-lookup"><span data-stu-id="7fe2c-110">Outlook add-ins</span></span>
  
- <span data-ttu-id="7fe2c-111">Aanwezigheid in Skype voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="7fe2c-111">Skype for Business presence</span></span>
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a><span data-ttu-id="7fe2c-112">Lean pop-outs configureren voor alle gebruikers binnen uw Office 365-organisatie</span><span class="sxs-lookup"><span data-stu-id="7fe2c-112">To configure lean popouts for all users within your Office 365 organization</span></span>
  
1. <span data-ttu-id="7fe2c-113">[Maak verbinding met Exchange Online met externe PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="7fe2c-113">[Connect to Exchange Online Using Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
  
2. <span data-ttu-id="7fe2c-114">Voer de [cmdlet Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) uit met de parameter LeanPopoutEnabled als volgt:</span><span class="sxs-lookup"><span data-stu-id="7fe2c-114">Run the [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) cmdlet with the LeanPopoutEnabled parameter as follows:</span></span>

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  <span data-ttu-id="7fe2c-115">Als u bijvoorbeeld lean pop-outs wilt inschakelen voor alle gebruikers in uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="7fe2c-115">For example, to enable lean popouts for all users in your organization:</span></span>
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  <span data-ttu-id="7fe2c-116">Lean-pop-outs uitschakelen voor alle gebruikers in uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="7fe2c-116">To disable lean popouts for all users in your organization:</span></span>

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```