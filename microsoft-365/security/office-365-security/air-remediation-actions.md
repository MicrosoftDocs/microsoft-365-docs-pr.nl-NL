---
title: Herstelacties in geautomatiseerd onderzoek en respons van Office 365
keywords: AIR, autoIR, ATP, geautomatiseerd, onderzoek, reactie, sanering, bedreigingen, geavanceerd, bedreiging, bescherming
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Meer informatie over herstelacties in geautomatiseerde onderzoeks- en responsmogelijkheden in Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: 2efe0124304a9f9dcfdc92b548c850882ad507a0
ms.sourcegitcommit: 841c06a5d566d404c35d5e9c0c7de5088daab976
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/18/2020
ms.locfileid: "42836856"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a><span data-ttu-id="012b0-104">Herstelacties na een geautomatiseerd onderzoek in Office 365</span><span class="sxs-lookup"><span data-stu-id="012b0-104">Remediation actions following an automated investigation in Office 365</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="012b0-105">Saneringsacties</span><span class="sxs-lookup"><span data-stu-id="012b0-105">Remediation actions</span></span>

<span data-ttu-id="012b0-106">[Geautomatiseerde onderzoeks- en responsmogelijkheden](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR) in [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) Plan 2 bevatten bepaalde herstelacties.</span><span class="sxs-lookup"><span data-stu-id="012b0-106">[Automated investigation and response capabilities](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR) in [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) Plan 2 include certain remediation actions.</span></span> <span data-ttu-id="012b0-107">Wanneer een geautomatiseerd onderzoek wordt uitgevoerd of is voltooid, ziet u meestal een of meer herstelacties waarvoor goedkeuring vereist is door uw beveiligingsteam om door te gaan.</span><span class="sxs-lookup"><span data-stu-id="012b0-107">Whenever an automated investigation is running or has completed, you'll typically see one or more remediation actions that require approval by your security operations team to proceed.</span></span> 

<span data-ttu-id="012b0-108">In de volgende tabel wordt een overzicht gemaakt van de herstelacties die momenteel beschikbaar zijn in Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="012b0-108">The following table summarizes the remediation actions that are currently available in Office 365 ATP.</span></span> 

|<span data-ttu-id="012b0-109">Actie</span><span class="sxs-lookup"><span data-stu-id="012b0-109">Action</span></span> | <span data-ttu-id="012b0-110">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="012b0-110">Description</span></span> |
|-----|-----|
|<span data-ttu-id="012b0-111">URL blokkeren (tijd van klikken)</span><span class="sxs-lookup"><span data-stu-id="012b0-111">Block URL (time-of-click)</span></span> |<span data-ttu-id="012b0-112">Beschermt tegen e-mailberichten en documenten die kwaadaardige URL's bevatten.</span><span class="sxs-lookup"><span data-stu-id="012b0-112">Protects against email messages and documents that contain malicious URLs.</span></span> <span data-ttu-id="012b0-113">Dit maakt het blokkeren van schadelijke koppelingen en gerelateerde webpagina's via [veilige links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) mogelijk wanneer de gebruiker op een koppeling in een bestaand Office-bestand of in een ouder e-mailbericht klikt.</span><span class="sxs-lookup"><span data-stu-id="012b0-113">This enables the blocking of malicious links and any related webpages via [Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) when the user clicks a link in an existing Office file or in an older email message.</span></span> |
|<span data-ttu-id="012b0-114">E-mail voor soft delete</span><span class="sxs-lookup"><span data-stu-id="012b0-114">Soft delete email</span></span>  |<span data-ttu-id="012b0-115">Verwijder zachte e-mailberichten uit het postvak van een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="012b0-115">Soft delete specific email messages from a user's mailbox.</span></span> <br/><span data-ttu-id="012b0-116">Een bericht met zachte verwijderden wordt verplaatst naar de map Herstelbare items van een gebruiker en wordt behouden totdat de bewaartermijn voor verwijderde items is verstreken.</span><span class="sxs-lookup"><span data-stu-id="012b0-116">A soft-deleted message is moved to a user's Recoverable Items folder and is retained until the deleted item retention period expires.</span></span> |
|<span data-ttu-id="012b0-117">E-mailclusters voor soft delete</span><span class="sxs-lookup"><span data-stu-id="012b0-117">Soft delete email clusters</span></span>  |<span data-ttu-id="012b0-118">Soft verwijdert schadelijke e-mailberichten die overeenkomen met een query uit de mailboxen van alle gebruikers.</span><span class="sxs-lookup"><span data-stu-id="012b0-118">Soft delete malicious email messages matching a query from all users' mailboxes.</span></span> <br/><span data-ttu-id="012b0-119">Zachte verwijderde berichten worden verplaatst naar de map Herstelbare items van gebruikers en worden bewaard totdat de bewaartermijn voor verwijderde items is verstreken.</span><span class="sxs-lookup"><span data-stu-id="012b0-119">Soft-deleted messages are moved to users' Recoverable Items folder and are retained until the deleted item retention period expires.</span></span> |
|<span data-ttu-id="012b0-120">Externe e-mail doorsturen uitschakelen</span><span class="sxs-lookup"><span data-stu-id="012b0-120">Turn off external mail forwarding</span></span> |<span data-ttu-id="012b0-121">Hiermee verwijdert u een doorstuurregel uit het postvak van een specifieke eindgebruiker.</span><span class="sxs-lookup"><span data-stu-id="012b0-121">Removes a forwarding rule from a specific end user's mailbox.</span></span>|

> [!NOTE]
> <span data-ttu-id="012b0-122">In Office 365 ATP worden geen herstelacties automatisch uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="012b0-122">In Office 365 ATP, no remediation actions are taken automatically.</span></span> <span data-ttu-id="012b0-123">Herstelacties worden alleen uitgevoerd na goedkeuring door het beveiligingsteam van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="012b0-123">Remediation actions are taken only upon approval by your organization's security team.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="012b0-124">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="012b0-124">Next steps</span></span>

- [<span data-ttu-id="012b0-125">Lopende of voltooide herstelacties weergeven na een geautomatiseerd onderzoek in Office 365</span><span class="sxs-lookup"><span data-stu-id="012b0-125">View pending or completed remediation actions following an automated investigation in Office 365</span></span>](air-review-approve-pending-completed-actions.md)

- [<span data-ttu-id="012b0-126">Details en resultaten van een geautomatiseerd onderzoek in Office 365</span><span class="sxs-lookup"><span data-stu-id="012b0-126">Details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)