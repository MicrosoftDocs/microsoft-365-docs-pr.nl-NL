---
title: Problemen met gedeelde postvakken oplossen
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: Er kunnen fouten optreden bij het instellen van gedeelde postvakken. Probeer deze oplossingen als u problemen hebt met gedeelde postvakken.
ms.openlocfilehash: 89cdfbe29ab035b1eb6c3a0183629eef59d67477
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706128"
---
# <a name="resolve-issues-with-shared-mailboxes"></a><span data-ttu-id="95303-104">Problemen met gedeelde postvakken oplossen</span><span class="sxs-lookup"><span data-stu-id="95303-104">Resolve issues with shared mailboxes</span></span>

<span data-ttu-id="95303-105">Als u foutberichten ziet bij het maken of gebruiken van een gedeeld postvak, probeert u deze mogelijke oplossingen.</span><span class="sxs-lookup"><span data-stu-id="95303-105">If you see error messages when creating or using a shared mailbox, try these possible solutions.</span></span> 

## <a name="error-when-creating-shared-mailboxes"></a><span data-ttu-id="95303-106">Fout bij het maken van gedeelde postvakken</span><span class="sxs-lookup"><span data-stu-id="95303-106">Error when creating shared mailboxes</span></span>
<span data-ttu-id="95303-107"><a name="bkmk_Fix"> </a></span><span class="sxs-lookup"><span data-stu-id="95303-107"><a name="bkmk_Fix"> </a></span></span>

<span data-ttu-id="95303-108">Als u het foutbericht ziet, wordt het proxyadres 'smtp:<naam van gedeeld postvak' al gebruikt door de **\> proxyadressen of LegacyExchangeDN of ' \<name> '. Kies een ander proxyadres.** Dit betekent dat u probeert het gedeelde postvak een naam te geven die al in gebruik is.</span><span class="sxs-lookup"><span data-stu-id="95303-108">If you see the error message, **The proxy address "smtp:<shared mailbox name\>" is already being used by the proxy addresses or LegacyExchangeDN of "\<name>". Please choose another proxy address**, it means you're trying to give the shared mailbox a name that's already in use.</span></span> <span data-ttu-id="95303-109">Stel bijvoorbeeld dat u gedeelde postvakken wilt maken met de naam info@domein1 en info@domein2.</span><span class="sxs-lookup"><span data-stu-id="95303-109">For example, let's say you want shared mailboxes named info@domain1 and info@domain2.</span></span> <span data-ttu-id="95303-110">U kunt dit op twee manieren doen:</span><span class="sxs-lookup"><span data-stu-id="95303-110">There are two ways to do this:</span></span>

  - <span data-ttu-id="95303-111">Gebruik Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="95303-111">Use Windows PowerShell.</span></span> <span data-ttu-id="95303-112">Zie dit blogbericht voor instructies: [Gedeelde postvakken maken met dezelfde alias bij verschillende domeinen](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="95303-112">See this blog post for instructions: [Create Shared Mailboxes with Same Alias at Different Domains](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span></span>
    
  - <span data-ttu-id="95303-113">Noem het tweede gedeelde postvak een andere naam dan het begin om de fout te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="95303-113">Name the second shared mailbox something different from the start to get around the error.</span></span> <span data-ttu-id="95303-114">Wijzig vervolgens in het beheercentrum de naam van het gedeelde postvak in wat u wilt.</span><span class="sxs-lookup"><span data-stu-id="95303-114">Then in the admin center, rename the shared mailbox to what you want it to be.</span></span>

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a><span data-ttu-id="95303-115">Fout over het niet hebben van machtigingen voor verzenden bij het gebruik van een gedeeld postvak</span><span class="sxs-lookup"><span data-stu-id="95303-115">Error about not having send permissions when using a shared mailbox</span></span>

<span data-ttu-id="95303-116">Als u een gedeeld postvak hebt gemaakt en er vervolgens een bericht van probeert te verzenden, krijgt u mogelijk het volgende:</span><span class="sxs-lookup"><span data-stu-id="95303-116">If you created a shared mailbox and then try to send a message from it, you might get this:</span></span>

<span data-ttu-id="95303-117">**Dit bericht kan niet worden verzonden. U hebt niet de machtiging om het bericht namens de opgegeven gebruiker te verzenden.**</span><span class="sxs-lookup"><span data-stu-id="95303-117">**This message could not be sent. You do not have the permission to send the message on behalf of the specified user.**</span></span>

<span data-ttu-id="95303-118">Dit bericht wordt weergegeven wanneer Microsoft 365 een replicatielatentieprobleem ondervindt.</span><span class="sxs-lookup"><span data-stu-id="95303-118">This message appears when Microsoft 365 is experiencing a replication latency issue.</span></span> <span data-ttu-id="95303-119">De gegevens over uw nieuwe gedeelde postvak (of toegevoegde gebruiker) worden over een uur of zo gerepliceerd in al onze datacenters.</span><span class="sxs-lookup"><span data-stu-id="95303-119">It should go away in an hour or so, when the information about your new shared mailbox (or added user) is replicated across all of our data centers.</span></span> <span data-ttu-id="95303-120">Wacht een uur en probeer het opnieuw om een bericht te verzenden.</span><span class="sxs-lookup"><span data-stu-id="95303-120">Wait an hour and then try again to send a message.</span></span>

## <a name="related-content"></a><span data-ttu-id="95303-121">Verwante inhoud</span><span class="sxs-lookup"><span data-stu-id="95303-121">Related content</span></span>

<span data-ttu-id="95303-122">[Info over gedeelde postvakken](about-shared-mailboxes.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="95303-122">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>\
<span data-ttu-id="95303-123">[Een gedeeld postvak](create-a-shared-mailbox.md) maken (artikel)</span><span class="sxs-lookup"><span data-stu-id="95303-123">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="95303-124">[Een gedeeld postvak configureren](configure-a-shared-mailbox.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="95303-124">[Configure a shared mailbox](configure-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="95303-125">[Het postvak van een gebruiker converteren naar een gedeeld postvak](convert-user-mailbox-to-shared-mailbox.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="95303-125">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="95303-126">[Een licentie uit een gedeeld postvak verwijderen](remove-license-from-shared-mailbox.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="95303-126">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>


    

