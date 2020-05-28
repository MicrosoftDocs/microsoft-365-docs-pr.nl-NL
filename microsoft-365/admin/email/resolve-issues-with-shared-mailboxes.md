---
title: Problemen met gedeelde postvakken oplossen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
ms.openlocfilehash: 5d6de9ac66b11f0e50b259cdca0b1bb50b8326ee
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400014"
---
# <a name="resolve-issues-with-shared-mailboxes"></a><span data-ttu-id="0c582-103">Problemen met gedeelde postvakken oplossen</span><span class="sxs-lookup"><span data-stu-id="0c582-103">Resolve issues with shared mailboxes</span></span>

<span data-ttu-id="0c582-104">Als u foutmeldingen ziet bij het maken of gebruiken van een gedeeld postvak, probeert u deze mogelijke oplossingen.</span><span class="sxs-lookup"><span data-stu-id="0c582-104">If you see error messages when creating or using a shared mailbox, try these possible solutions.</span></span> 

## <a name="error-when-creating-shared-mailboxes"></a><span data-ttu-id="0c582-105">Fout bij het maken van gedeelde postvakken</span><span class="sxs-lookup"><span data-stu-id="0c582-105">Error when creating shared mailboxes</span></span>
<span data-ttu-id="0c582-106"><a name="bkmk_Fix"> </a></span><span class="sxs-lookup"><span data-stu-id="0c582-106"><a name="bkmk_Fix"> </a></span></span>

<span data-ttu-id="0c582-107">Als u het foutbericht ziet, **wordt het proxyadres 'smtp:<gedeelde postvaknaam' \> al gebruikt door de proxyadressen of LegacyExchangeDN van \<name> " ". Kies een ander proxyadres,** dit betekent dat u het gedeelde postvak een naam probeert te geven die al in gebruik is.</span><span class="sxs-lookup"><span data-stu-id="0c582-107">If you see the error message, **The proxy address "smtp:<shared mailbox name\>" is already being used by the proxy addresses or LegacyExchangeDN of "\<name>". Please choose another proxy address**, it means you're trying to give the shared mailbox a name that's already in use.</span></span> <span data-ttu-id="0c582-108">Stel bijvoorbeeld dat u gedeelde postvakken wilt maken met de naam info@domein1 en info@domein2.</span><span class="sxs-lookup"><span data-stu-id="0c582-108">For example, let's say you want shared mailboxes named info@domain1 and info@domain2.</span></span> <span data-ttu-id="0c582-109">U kunt dit op twee manieren doen:</span><span class="sxs-lookup"><span data-stu-id="0c582-109">There are two ways to do this:</span></span>

  - <span data-ttu-id="0c582-110">Gebruik Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c582-110">Use Windows PowerShell.</span></span> <span data-ttu-id="0c582-111">Zie dit blogbericht voor instructies: [Gedeelde postvakken maken met dezelfde alias bij verschillende domeinen](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="0c582-111">See this blog post for instructions: [Create Shared Mailboxes with Same Alias at Different Domains](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span></span>
    
  - <span data-ttu-id="0c582-112">Geef het tweede gedeelde postvak iets anders dan het begin om de fout te omzeilen.</span><span class="sxs-lookup"><span data-stu-id="0c582-112">Name the second shared mailbox something different from the start to get around the error.</span></span> <span data-ttu-id="0c582-113">Wijzig vervolgens in het beheercentrum de naam van het gedeelde postvak naar wat u wilt dat het is.</span><span class="sxs-lookup"><span data-stu-id="0c582-113">Then in the admin center, rename the shared mailbox to what you want it to be.</span></span>

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a><span data-ttu-id="0c582-114">Fout over het niet verzenden van machtigingen bij het gebruik van een gedeeld postvak</span><span class="sxs-lookup"><span data-stu-id="0c582-114">Error about not having send permissions when using a shared mailbox</span></span>

<span data-ttu-id="0c582-115">Als u een gedeeld postvak hebt gemaakt en vervolgens probeert er een bericht van te verzenden, krijgt u mogelijk het gewenste bericht:</span><span class="sxs-lookup"><span data-stu-id="0c582-115">If you created a shared mailbox and then try to send a message from it, you might get this:</span></span>

<span data-ttu-id="0c582-116">**Dit bericht kan niet worden verzonden. U hebt geen toestemming om het bericht namens de opgegeven gebruiker te verzenden.**</span><span class="sxs-lookup"><span data-stu-id="0c582-116">**This message could not be sent. You do not have the permission to send the message on behalf of the specified user.**</span></span>

<span data-ttu-id="0c582-117">Dit bericht wordt weergegeven wanneer Microsoft 365 een replicatielatentieprobleem ondervindt.</span><span class="sxs-lookup"><span data-stu-id="0c582-117">This message appears when Microsoft 365 is experiencing a replication latency issue.</span></span> <span data-ttu-id="0c582-118">Het moet verdwijnen in een uur of zo, wanneer de informatie over uw nieuwe gedeelde postvak (of toegevoegde gebruiker) wordt gerepliceerd in al onze datacenters.</span><span class="sxs-lookup"><span data-stu-id="0c582-118">It should go away in an hour or so, when the information about your new shared mailbox (or added user) is replicated across all of our data centers.</span></span> <span data-ttu-id="0c582-119">Wacht een uur en probeer dan opnieuw om een bericht te verzenden.</span><span class="sxs-lookup"><span data-stu-id="0c582-119">Wait an hour and then try again to send a message.</span></span>

## <a name="related-articles"></a><span data-ttu-id="0c582-120">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="0c582-120">Related articles</span></span>

[<span data-ttu-id="0c582-121">Meer over gedeelde postvakken</span><span class="sxs-lookup"><span data-stu-id="0c582-121">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="0c582-122">Een gedeeld postvak maken</span><span class="sxs-lookup"><span data-stu-id="0c582-122">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="0c582-123">Een gedeeld postvak configureren</span><span class="sxs-lookup"><span data-stu-id="0c582-123">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="0c582-124">Een gebruikerspostvak converteren naar een gedeeld postvak</span><span class="sxs-lookup"><span data-stu-id="0c582-124">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="0c582-125">Een licentie uit een gedeeld postvak verwijderen</span><span class="sxs-lookup"><span data-stu-id="0c582-125">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)


    

