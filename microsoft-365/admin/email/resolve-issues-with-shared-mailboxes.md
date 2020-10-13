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
search.appverid:
- BCS160
- MET150
- MOE150
description: Probeer deze oplossingen als u problemen ondervindt met gedeelde postvakken.
ms.openlocfilehash: c889d3aa2fab8c2dce4cc2a8a00ef49a905363a1
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445505"
---
# <a name="resolve-issues-with-shared-mailboxes"></a><span data-ttu-id="cbdd8-103">Problemen met gedeelde postvakken oplossen</span><span class="sxs-lookup"><span data-stu-id="cbdd8-103">Resolve issues with shared mailboxes</span></span>

<span data-ttu-id="cbdd8-104">Als er foutberichten worden weergegeven wanneer u een gedeeld postvak maakt of gebruikt, kunt u deze oplossingen proberen.</span><span class="sxs-lookup"><span data-stu-id="cbdd8-104">If you see error messages when creating or using a shared mailbox, try these possible solutions.</span></span> 

## <a name="error-when-creating-shared-mailboxes"></a><span data-ttu-id="cbdd8-105">Fout bij het maken van gedeelde postvakken</span><span class="sxs-lookup"><span data-stu-id="cbdd8-105">Error when creating shared mailboxes</span></span>
<span data-ttu-id="cbdd8-106"><a name="bkmk_Fix"> </a></span><span class="sxs-lookup"><span data-stu-id="cbdd8-106"><a name="bkmk_Fix"> </a></span></span>

<span data-ttu-id="cbdd8-107">Als u het foutbericht **' SMTP: <gedeelde postvaknaam ' ziet, wordt dit \> al gebruikt door de proxyadressen of LegacyExchangeDN van ' \<name> '. Kies een ander proxyadres**, dat betekent dat u het gedeelde Postvak probeert een naam te geven die al in gebruik is.</span><span class="sxs-lookup"><span data-stu-id="cbdd8-107">If you see the error message, **The proxy address "smtp:<shared mailbox name\>" is already being used by the proxy addresses or LegacyExchangeDN of "\<name>". Please choose another proxy address**, it means you're trying to give the shared mailbox a name that's already in use.</span></span> <span data-ttu-id="cbdd8-108">Stel bijvoorbeeld dat u gedeelde postvakken wilt maken met de naam info@domein1 en info@domein2.</span><span class="sxs-lookup"><span data-stu-id="cbdd8-108">For example, let's say you want shared mailboxes named info@domain1 and info@domain2.</span></span> <span data-ttu-id="cbdd8-109">U kunt dit op twee manieren doen:</span><span class="sxs-lookup"><span data-stu-id="cbdd8-109">There are two ways to do this:</span></span>

  - <span data-ttu-id="cbdd8-110">Gebruik Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cbdd8-110">Use Windows PowerShell.</span></span> <span data-ttu-id="cbdd8-111">Bekijk dit blogbericht voor instructies: [gedeelde postvakken met dezelfde alias voor verschillende domeinen maken](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="cbdd8-111">See this blog post for instructions: [Create Shared Mailboxes with Same Alias at Different Domains](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span></span>
    
  - <span data-ttu-id="cbdd8-112">Naam het tweede gedeelde Postvak iets anders dan de fout.</span><span class="sxs-lookup"><span data-stu-id="cbdd8-112">Name the second shared mailbox something different from the start to get around the error.</span></span> <span data-ttu-id="cbdd8-113">Wijzig vervolgens in het Beheercentrum de naam van het gedeelde Postvak naar de gewenste waarde.</span><span class="sxs-lookup"><span data-stu-id="cbdd8-113">Then in the admin center, rename the shared mailbox to what you want it to be.</span></span>

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a><span data-ttu-id="cbdd8-114">Foutmelding over het niet verzenden van machtigingen bij gebruik van een gedeeld postvak</span><span class="sxs-lookup"><span data-stu-id="cbdd8-114">Error about not having send permissions when using a shared mailbox</span></span>

<span data-ttu-id="cbdd8-115">Als u een gedeeld postvak hebt gemaakt en daarna een bericht verzendt, kunt u dit als volgt doen:</span><span class="sxs-lookup"><span data-stu-id="cbdd8-115">If you created a shared mailbox and then try to send a message from it, you might get this:</span></span>

<span data-ttu-id="cbdd8-116">**Dit bericht kan niet worden verzonden. U bent niet gemachtigd om het bericht te verzenden namens de opgegeven gebruiker.**</span><span class="sxs-lookup"><span data-stu-id="cbdd8-116">**This message could not be sent. You do not have the permission to send the message on behalf of the specified user.**</span></span>

<span data-ttu-id="cbdd8-117">Dit bericht wordt weergegeven wanneer Microsoft 365 een replicatielatentie probleem ondervindt.</span><span class="sxs-lookup"><span data-stu-id="cbdd8-117">This message appears when Microsoft 365 is experiencing a replication latency issue.</span></span> <span data-ttu-id="cbdd8-118">De werkstroom moet binnen een uur plaatsvinden, wanneer de informatie over uw nieuwe gedeelde Postvak (of een extra gebruiker) wordt gerepliceerd over al uw gegevenscentra.</span><span class="sxs-lookup"><span data-stu-id="cbdd8-118">It should go away in an hour or so, when the information about your new shared mailbox (or added user) is replicated across all of our data centers.</span></span> <span data-ttu-id="cbdd8-119">Wacht een uur en probeer het nogmaals met een bericht te verzenden.</span><span class="sxs-lookup"><span data-stu-id="cbdd8-119">Wait an hour and then try again to send a message.</span></span>

## <a name="related-articles"></a><span data-ttu-id="cbdd8-120">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="cbdd8-120">Related articles</span></span>

[<span data-ttu-id="cbdd8-121">Meer over gedeelde postvakken</span><span class="sxs-lookup"><span data-stu-id="cbdd8-121">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="cbdd8-122">Een gedeeld postvak maken</span><span class="sxs-lookup"><span data-stu-id="cbdd8-122">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="cbdd8-123">Een gedeeld postvak configureren</span><span class="sxs-lookup"><span data-stu-id="cbdd8-123">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="cbdd8-124">Een gebruikerspostvak converteren naar een gedeeld postvak</span><span class="sxs-lookup"><span data-stu-id="cbdd8-124">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="cbdd8-125">Een licentie uit een gedeeld postvak verwijderen</span><span class="sxs-lookup"><span data-stu-id="cbdd8-125">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)


    

