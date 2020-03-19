---
title: Het antispambeleid configureren
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 6/9/2015
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 31279431-828d-48bd-b979-20b6de15fa4a
ms.collection:
- M365-security-compliance
description: Spamfiltering wordt automatisch in het hele bedrijf ingeschakeld via het standaard antispambeleid (verbindingsfilter, spamfilter en uitgaande spam). Als beheerder u het standaard antispambeleid weergeven en bewerken, maar niet verwijderen, zodat ze zo zijn afgestemd op de behoeften van uw organisatie. Voor een grotere granulariteit u ook aangepaste beleidsregels maken en deze toepassen op bepaalde gebruikers, groepen of domeinen in uw organisatie. Standaard hebben aangepaste beleidsregels voorrang op het standaardbeleid, maar u de prioriteit van uw beleid wijzigen.
ms.openlocfilehash: 2ee5833bf476123a84411a7ad645b9f8c5d0b2b8
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42810947"
---
# <a name="configure-the-anti-spam-policies"></a><span data-ttu-id="766d5-106">Het antispambeleid configureren</span><span class="sxs-lookup"><span data-stu-id="766d5-106">Configure the anti-spam policies</span></span>

<span data-ttu-id="766d5-107">Spamfiltering wordt automatisch in het hele bedrijf ingeschakeld via het standaard antispambeleid (verbindingsfilter, spamfilter en uitgaande spam).</span><span class="sxs-lookup"><span data-stu-id="766d5-107">Spam filtering is automatically enabled company-wide through the default anti-spam policies (connection filter, spam filter, and outbound spam).</span></span> <span data-ttu-id="766d5-108">Als beheerder u het standaard antispambeleid weergeven en bewerken, maar niet verwijderen, zodat ze zo zijn afgestemd op de behoeften van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="766d5-108">As an administrator, you can view and edit, but not delete, the default anti-spam policies so that they are tailored to best meet the needs of your organization.</span></span> <span data-ttu-id="766d5-109">Voor een grotere granulariteit u ook aangepaste beleidsregels maken en deze toepassen op bepaalde gebruikers, groepen of domeinen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="766d5-109">For greater granularity, you can also create custom policies and apply them to specified users, groups, or domains in your organization.</span></span> <span data-ttu-id="766d5-110">Standaard hebben aangepaste beleidsregels voorrang op het standaardbeleid, maar u de prioriteit van uw beleid wijzigen.</span><span class="sxs-lookup"><span data-stu-id="766d5-110">By default, custom policies take precedence over the default policy, but you can change the priority of your policies.</span></span> 
  
<span data-ttu-id="766d5-111">Zie de volgende onderwerpen voor meer informatie over het configureren van uw antispambeleid:</span><span class="sxs-lookup"><span data-stu-id="766d5-111">For more about configuring your anti-spam policies, see the following topics:</span></span>
  
[<span data-ttu-id="766d5-112">Het beleid van het verbindingsfilter configureren</span><span class="sxs-lookup"><span data-stu-id="766d5-112">Configure the connection filter policy</span></span>](configure-the-connection-filter-policy.md)
  
[<span data-ttu-id="766d5-113">Uw spamfilterbeleid configureren</span><span class="sxs-lookup"><span data-stu-id="766d5-113">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
> [!IMPORTANT]
> <span data-ttu-id="766d5-114">Voor zelfstandige eop-klanten: de EOP-inhoudsfilters sturen standaard door spam gedetecteerde berichten naar de map Ongewenste e-mail van elke ontvanger.</span><span class="sxs-lookup"><span data-stu-id="766d5-114">For EOP standalone customers: By default, the EOP content filters send spam-detected messages to each recipients' Junk Email folder.</span></span> <span data-ttu-id="766d5-115">Om er echter voor te zorgen dat de **mapactie Berichten verplaatsen naar ongewenste e-mail** werkt met on-premises postvakken, moet u twee Exchange-regels voor e-mailstromen (ook wel transportregels genoemd) configureren op uw on-premises servers om spamkoppen van EOP te detecteren.</span><span class="sxs-lookup"><span data-stu-id="766d5-115">However, in order to ensure that the **Move message to Junk Email folder** action will work with on-premises mailboxes, you must configure two Exchange mail flow rules (also known as transport rules) on your on-premises servers to detect spam headers added by EOP.</span></span> <span data-ttu-id="766d5-116">Zie Zorgen [dat spam wordt doorgestuurd naar de map Ongewenste e-mail](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)van elke gebruiker.</span><span class="sxs-lookup"><span data-stu-id="766d5-116">For details, see [Ensure that spam is routed to each user's Junk Email folder](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> 
  
[<span data-ttu-id="766d5-117">Het uitgaande spambeleid configureren</span><span class="sxs-lookup"><span data-stu-id="766d5-117">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  

