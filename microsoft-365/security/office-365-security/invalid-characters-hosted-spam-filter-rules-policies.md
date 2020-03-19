---
title: Ongeldige tekens in uw spamfilterregels en het beleid voor spamfilters voorkomen
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 09/24/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Biedt hulp voor beheerders die ongeldige tekens in hun antispamconfiguratie hebben &amp; en problemen ondervinden wanneer ze het Security Compliance Center proberen te gebruiken.
ms.openlocfilehash: f1841eb86583a48acecde0770f030b626323fa8e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42810418"
---
# <a name="avoid-invalid-characters-in-your-spam-filter-rules-and-spam-filter-policy"></a><span data-ttu-id="9b3f3-103">Ongeldige tekens in uw spamfilterregels en het beleid voor spamfilters voorkomen</span><span class="sxs-lookup"><span data-stu-id="9b3f3-103">Avoid invalid characters in your spam filter rules and spam filter policy</span></span> 

<span data-ttu-id="9b3f3-104">Voorheen hebben Office 365-beheerders regels voor spamfilters en het spamfilterbeleid ingesteld en geconfigureerd met behulp van het Exchange-beheercentrum (EAC).</span><span class="sxs-lookup"><span data-stu-id="9b3f3-104">Previously, Office 365 administrators set up and configured spam filter rules and the spam filter policy by using the Exchange admin center (EAC).</span></span> <span data-ttu-id="9b3f3-105">U gebruikt nu &amp; het Security Compliance Center om uw antispamconfiguratie te beheren.</span><span class="sxs-lookup"><span data-stu-id="9b3f3-105">Now, you use the Security &amp; Compliance Center to manage the your anti-spam configuration.</span></span> <span data-ttu-id="9b3f3-106">De volgende tekens worden ondersteund in de EAC, maar &amp; worden niet ondersteund voor gebruik in het Security Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="9b3f3-106">The following characters were supported in the EAC but are not supported for use in the Security &amp; Compliance Center.</span></span>  

<span data-ttu-id="9b3f3-107">**Ongeldige tekens:**</span><span class="sxs-lookup"><span data-stu-id="9b3f3-107">**Invalid characters:**</span></span>
  
```\ % & * + / = ? { } | < > ( ) ; : , [ ] "```

<span data-ttu-id="9b3f3-108">Als uw spamfilterregels of uw spamfilterbeleid een van de ongeldige tekens bevatten, u een of meer van deze problemen tegenkomen:</span><span class="sxs-lookup"><span data-stu-id="9b3f3-108">If your spam filter rules or your spam filter policy contains any of the invalid characters, you might encounter any or all of these issues:</span></span>
- <span data-ttu-id="9b3f3-109">Het is mogelijk dat u het beleid &amp; of de regels niet vinden in het Security Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="9b3f3-109">You might be unable to find the policy or rules in the Security &amp; Compliance Center.</span></span>
- <span data-ttu-id="9b3f3-110">Mogelijk ontvangt u fouten wanneer u de regels of het beleid probeert te krijgen met Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9b3f3-110">You might receive errors when trying to get the rules or policy by using Windows PowerShell.</span></span>
- <span data-ttu-id="9b3f3-111">Mogelijk wordt het beleid of de instellingen niet uitgevoerd of uitgevoerd zoals verwacht.</span><span class="sxs-lookup"><span data-stu-id="9b3f3-111">You might find that the policy or settings do not run or perform as expected.</span></span>

## <a name="remove-the-invalid-characters-from-the-spam-filter-policy-and-rules"></a><span data-ttu-id="9b3f3-112">De ongeldige tekens verwijderen uit het beleid en de regels voor spamfilters</span><span class="sxs-lookup"><span data-stu-id="9b3f3-112">Remove the invalid characters from the spam filter policy and rules</span></span>

<span data-ttu-id="9b3f3-113">Zodra u het beleid en de regels hebt geïdentificeerd die ongeldige tekens bevatten, u de namen wijzigen met behulp van de Windows PowerShell-cmdlets.</span><span class="sxs-lookup"><span data-stu-id="9b3f3-113">Once you have identified the policy and rules that contain invalid characters, you can change the names by using the Windows PowerShell cmdlets.</span></span> 

1. <span data-ttu-id="9b3f3-114">[Maak verbinding met Exchange Online via Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="9b3f3-114">[Connect to Exchange Online Using Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>
    
2. <span data-ttu-id="9b3f3-115">Als u de naam van het spamfilterbeleid wilt wijzigen, voert u de cmdlet Set-HostedContentFilterPolicy als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="9b3f3-115">To change the name of the spam filter policy, run the Set-HostedContentFilterPolicy cmdlet as follows:</span></span>
    
    ```powershell
    Set-HostedContentFilterPolicy -Identity "Old policy name" -Name "New policy name"
    ```  

3. <span data-ttu-id="9b3f3-116">Als u de naam van een spamfilterregel wilt wijzigen, voert u de cmdlet Set-HostedContentFilterRule als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="9b3f3-116">To change the name of a spam filter rule, run the Set-HostedContentFilterRule cmdlet as follows:</span></span>
    
    ```powershell
    Set-HostedContentFilterRule -Identity "Old rule name" -Name "New rule name"
    ```  

  
 ## <a name="for-more-information"></a><span data-ttu-id="9b3f3-117">Voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="9b3f3-117">For more information</span></span>

[<span data-ttu-id="9b3f3-118">Bedreigingsbeheer in &amp; het Security Compliance Center</span><span class="sxs-lookup"><span data-stu-id="9b3f3-118">Threat management in the Security &amp; Compliance Center</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="9b3f3-119">Beleid voor set-hostedcontentfilter</span><span class="sxs-lookup"><span data-stu-id="9b3f3-119">Set-HostedContentFilterPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy)

[<span data-ttu-id="9b3f3-120">Regel van set-hostedcontentfilterregel</span><span class="sxs-lookup"><span data-stu-id="9b3f3-120">Set-HostedContentFilterRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule)
