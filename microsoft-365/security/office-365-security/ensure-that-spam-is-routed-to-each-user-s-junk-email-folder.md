---
title: Ervoor zorgen dat spam wordt doorgestuurd naar de map Ongewenste e-mail van elke gebruiker
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 7/16/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Beheerders kunnen in Exchange Online Protection leren hoe ze spam kunnen doorsturen naar map ongewenste e-mail van gebruikers.
ms.openlocfilehash: 6d1fd625669e8b638a408b2db1993f45fa653ffb
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42806096"
---
# <a name="ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a><span data-ttu-id="05601-103">Ervoor zorgen dat spam wordt doorgestuurd naar de map Ongewenste e-mail van elke gebruiker</span><span class="sxs-lookup"><span data-stu-id="05601-103">Ensure that spam is routed to each user's Junk Email folder</span></span>

> [!IMPORTANT]
> <span data-ttu-id="05601-104">Dit onderwerp is alleen van toepassing op EOP-klanten (Exchange Online Protection) die postvakken on-premises hosten in een hybride implementatie.</span><span class="sxs-lookup"><span data-stu-id="05601-104">This topic only applies to Exchange Online Protection (EOP) customers who host mailboxes on-premises in a hybrid deployment.</span></span> <span data-ttu-id="05601-105">Exchange Online-klanten van wie de postvakken volledig zijn gehost in Office 365, hoeven deze opdrachten niet uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="05601-105">Exchange Online customers whose mailboxes are fully-hosted in Office 365 do not need to run these commands.</span></span>

<span data-ttu-id="05601-106">De standaard anti-spam actie voor EOP-klanten is om spamberichten te verplaatsen naar de map Ongewenste e-mail van de ontvangers.</span><span class="sxs-lookup"><span data-stu-id="05601-106">The default anti-spam action for EOP customers is to move spam messages to the recipients' Junk Email folder.</span></span> <span data-ttu-id="05601-107">Als u deze actie wilt uitvoeren met on-premises postvakken, moet u Exchange-mailstroomregels (ook wel transportregels genoemd) configureren op uw on-premises Edge- of Hub-servers om spamkoppen te detecteren die door EOP zijn toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="05601-107">In order for this action to work with on-premises mailboxes, you must configure Exchange mail flow rules (also known as transport rules) on your on-premises Edge or Hub servers to detect spam headers added by EOP.</span></span> <span data-ttu-id="05601-108">Deze regels voor e-mailstroom bepalen het spamvertrouwensniveau (SCL) dat wordt gebruikt door de eigenschap SclJunkThreshold van de cmdlet Set-OrganizationConfig om spam naar de map Ongewenste e-mail van elk postvak te verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="05601-108">These mail flow rules set the spam confidence level (SCL) used by the SclJunkThreshold property of the Set-OrganizationConfig cmdlet to move spam into the Junk Email folder of each mailbox.</span></span>

### <a name="to-add-mail-flow-rules-to-ensure-spam-is-moved-to-the-junk-email-folder-by-using-windows-powershell"></a><span data-ttu-id="05601-109">Regels voor e-mailstromen toevoegen om ervoor te zorgen dat spam wordt verplaatst naar de map Ongewenste e-mail met Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="05601-109">To add mail flow rules to ensure spam is moved to the Junk Email folder by using Windows PowerShell</span></span>

1. <span data-ttu-id="05601-110">Toegang tot de Exchange Management Shell voor uw on-premises Exchange-server.</span><span class="sxs-lookup"><span data-stu-id="05601-110">Access the Exchange Management Shell for your on-premises Exchange server.</span></span> <span data-ttu-id="05601-111">Zie De **Shell openen**voor meer informatie over het openen van de Exchange Management Shell in uw on-premises Exchange-organisatie.</span><span class="sxs-lookup"><span data-stu-id="05601-111">To learn how to open the Exchange Management Shell in your on-premises Exchange organization, see **Open the Shell**.</span></span>

2. <span data-ttu-id="05601-112">Voer de volgende opdracht uit om door inhoud gefilterde spamberichten door te sturen naar de map Ongewenste e-mail:</span><span class="sxs-lookup"><span data-stu-id="05601-112">Run the following command to route content-filtered spam messages to the Junk Email folder:</span></span>

   ```Powershell
   New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
   ```

   <span data-ttu-id="05601-113">Waar _NameForRule_ de naam is voor de nieuwe regel, bijvoorbeeld JunkContentFilteredMail.</span><span class="sxs-lookup"><span data-stu-id="05601-113">Where _NameForRule_ is the name for the new rule, for example, JunkContentFilteredMail.</span></span>

3. <span data-ttu-id="05601-114">Voer de volgende opdracht uit om berichten die als spam zijn gemarkeerd, te routeren voordat u het inhoudsfilter naar de map Ongewenste e-mail bereikt:</span><span class="sxs-lookup"><span data-stu-id="05601-114">Run the following command to route messages marked as spam prior to reaching the content filter to the Junk Email folder:</span></span>

   ```Powershell
   New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
   ```

   <span data-ttu-id="05601-115">Waar _NameForRule_ de naam is voor de nieuwe regel, bijvoorbeeld JunkMailBeforeReachingContentFilter.</span><span class="sxs-lookup"><span data-stu-id="05601-115">Where _NameForRule_ is the name for the new rule, for example, JunkMailBeforeReachingContentFilter.</span></span>

4. <span data-ttu-id="05601-116">Voer de volgende opdracht uit om ervoor te zorgen dat berichten van afzenders in een bloklijst in het beleid voor spamfilters, zoals de lijst **met afzenderblokken,** worden doorgestuurd naar de map Ongewenste e-mail:</span><span class="sxs-lookup"><span data-stu-id="05601-116">Run the following command to ensure that messages from senders in a block list in the spam filter policy, such as the **Sender block** list, are routed to the Junk Email folder:</span></span>

   ```Powershell
   New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
   ```

   <span data-ttu-id="05601-117">Waar _NameForRule_ de naam is voor de nieuwe regel, bijvoorbeeld JunkMailInSenderBlockList.</span><span class="sxs-lookup"><span data-stu-id="05601-117">Where _NameForRule_ is the name for the new rule, for example, JunkMailInSenderBlockList.</span></span>

<span data-ttu-id="05601-118">Als u het mapbericht Verplaatsen naar **ongewenste e-mail** niet wilt gebruiken, u een andere actie kiezen in uw inhoudsfilterbeleid in het Exchange-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="05601-118">If you do not want to use the **Move message to Junk Email folder** action, you can choose another action in your content filter policies in the Exchange admin center.</span></span> <span data-ttu-id="05601-119">Zie [Beleid voor spamfilters configureren](configure-your-spam-filter-policies.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="05601-119">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="05601-120">Zie [Kopteksten voor antispamberichten](anti-spam-message-headers.md)voor meer informatie over deze velden in de koptekst van het bericht.</span><span class="sxs-lookup"><span data-stu-id="05601-120">For more information about these fields in the message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

> [!TIP]
> <span data-ttu-id="05601-121">Als u het actie bericht verplaatsen naar **ongewenste e-mail** niet wilt gebruiken, u een andere actie kiezen in uw inhoudsfilterbeleid in het Exchange-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="05601-121">If you don't want to use the **Move message to Junk Email folder** action, you can choose another action in your content filter policies in the Exchange admin center.</span></span> <span data-ttu-id="05601-122">Zie [Beleid voor spamfilters configureren](configure-your-spam-filter-policies.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="05601-122">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="05601-123">Zie [Kopteksten voor antispamberichten](anti-spam-message-headers.md)voor meer informatie over deze velden in de koptekst van het bericht.</span><span class="sxs-lookup"><span data-stu-id="05601-123">For more information about these fields in the message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="05601-124">Zie ook</span><span class="sxs-lookup"><span data-stu-id="05601-124">See also</span></span>

[<span data-ttu-id="05601-125">Nieuwe transportregel</span><span class="sxs-lookup"><span data-stu-id="05601-125">New-TransportRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule)
