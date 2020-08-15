---
title: Gebruik Lean popouts om geheugen te verminderen voor het lezen van e-mailberichten
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
description: Dit artikel bevat informatie over het gebruik van Lean popouts voor het verbeteren van de prestaties van het downloaden van berichten in de webversie van Outlook.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7bf53464ac6b2783fbbfc335fd4ff73dbe4435fb
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689438"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a><span data-ttu-id="d9ced-103">Gebruik Lean popouts om geheugen te verminderen voor het lezen van e-mailberichten</span><span class="sxs-lookup"><span data-stu-id="d9ced-103">Use lean popouts to reduce memory used when reading mail messages</span></span>

<span data-ttu-id="d9ced-104">Dit artikel bevat informatie over het verbeteren van de downloadprestaties van berichten in de webversie van Outlook.</span><span class="sxs-lookup"><span data-stu-id="d9ced-104">This article contains information for improving message download performance in Outlook on the web.</span></span> <span data-ttu-id="d9ced-105">Dit artikel maakt deel uit van het project [netwerk planning en prestaties optimaliseren voor Office 365](https://aka.ms/tune) .</span><span class="sxs-lookup"><span data-stu-id="d9ced-105">This article is part of the [Network planning and performance tuning for Office 365](https://aka.ms/tune) project.</span></span>
  
<span data-ttu-id="d9ced-106">Als globale beheerder van Office 365 kunt u de webversie van Outlook configureren voor het leveren van _Lean popouts_, een kleinere en minder geheugenintensief versie van bepaalde e-mailberichten in Microsoft Edge of Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="d9ced-106">As an Office 365 global administrator, you can configure Outlook on the web to deliver _lean popouts_, a smaller, less memory-intensive version of certain email messages in Microsoft Edge or Internet Explorer.</span></span> <span data-ttu-id="d9ced-107">Wanneer Lean popouts is geconfigureerd voor de webversie van Outlook, worden op de server gegenereerde onderdelen geladen die de prestaties optimaliseren.</span><span class="sxs-lookup"><span data-stu-id="d9ced-107">When lean popouts are configured for Outlook on the web, server-side rendered components are loaded that optimize performance.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d9ced-108">Met ingang van maart 2018 zijn Lean popouts niet beschikbaar voor berichten waarin beperkingen gelden voor gebruiksrechten, zoals Information Rights Management (IRM).</span><span class="sxs-lookup"><span data-stu-id="d9ced-108">As of March 2018, lean popouts are not available for messages that specify usage rights restrictions, such as Information Rights Management (IRM).</span></span>
  
<span data-ttu-id="d9ced-109">Deze functies werken nog steeds in het hoofdvenster, maar zijn niet beschikbaar in Lean popouts:</span><span class="sxs-lookup"><span data-stu-id="d9ced-109">These features will continue to work in the main window but are not available in lean popouts:</span></span>
  
- <span data-ttu-id="d9ced-110">Outlook-invoegtoepassingen</span><span class="sxs-lookup"><span data-stu-id="d9ced-110">Outlook add-ins</span></span>
  
- <span data-ttu-id="d9ced-111">Aanwezigheidsgegevens voor Skype voor bedrijven</span><span class="sxs-lookup"><span data-stu-id="d9ced-111">Skype for Business presence</span></span>
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a><span data-ttu-id="d9ced-112">De kanbanschemagroepen van de popouts configureren voor alle gebruikers binnen uw Office 365-organisatie</span><span class="sxs-lookup"><span data-stu-id="d9ced-112">To configure lean popouts for all users within your Office 365 organization</span></span>
  
1. <span data-ttu-id="d9ced-113">[Maak verbinding met Exchange Online via externe PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx ).</span><span class="sxs-lookup"><span data-stu-id="d9ced-113">[Connect to Exchange Online Using Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx ).</span></span>
  
2. <span data-ttu-id="d9ced-114">Voer de cmdlet [set-OrganizationConfig](https://technet.microsoft.com/library/aa997443%28v=exchg.160%29.aspx) uit met de parameter LeanPopoutEnabled als volgt:</span><span class="sxs-lookup"><span data-stu-id="d9ced-114">Run the [Set-OrganizationConfig](https://technet.microsoft.com/library/aa997443%28v=exchg.160%29.aspx) cmdlet with the LeanPopoutEnabled parameter as follows:</span></span>

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  <span data-ttu-id="d9ced-115">Als u bijvoorbeeld de popouts voor alle gebruikers in uw organisatie wilt inschakelen:</span><span class="sxs-lookup"><span data-stu-id="d9ced-115">For example, to enable lean popouts for all users in your organization:</span></span>
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  <span data-ttu-id="d9ced-116">U schakelt de popouts voor alle gebruikers in uw organisatie als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="d9ced-116">To disable lean popouts for all users in your organization:</span></span>

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```
