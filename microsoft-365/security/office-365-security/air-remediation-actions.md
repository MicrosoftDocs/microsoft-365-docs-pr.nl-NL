---
title: Herstelacties in automatisch onderzoek en reactie van Office 365
keywords: AIR, autoIR, ATP, geautomatiseerd, onderzoek, respons, sanering, bedreigingen, geavanceerd, bedreiging, bescherming
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
description: Meer informatie over herstelacties in geautomatiseerde onderzoeks- en reactiemogelijkheden in Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: 1dff52fe1bdab364e03bc42afc84c9b54696ccf5
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955531"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a><span data-ttu-id="a0dcd-104">Herstelacties na een geautomatiseerd onderzoek in Office 365</span><span class="sxs-lookup"><span data-stu-id="a0dcd-104">Remediation actions following an automated investigation in Office 365</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="a0dcd-105">Herstelacties</span><span class="sxs-lookup"><span data-stu-id="a0dcd-105">Remediation actions</span></span>

<span data-ttu-id="a0dcd-106">[Geautomatiseerde onderzoeks- en reactiemogelijkheden](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR) in [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) Plan 2 omvatten bepaalde herstelacties.</span><span class="sxs-lookup"><span data-stu-id="a0dcd-106">[Automated investigation and response capabilities](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR) in [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) Plan 2 include certain remediation actions.</span></span> <span data-ttu-id="a0dcd-107">Wanneer een geautomatiseerd onderzoek wordt uitgevoerd of is voltooid, ziet u doorgaans een of meer herstelacties waarvoor goedkeuring door uw beveiligingsteam nodig is om door te gaan.</span><span class="sxs-lookup"><span data-stu-id="a0dcd-107">Whenever an automated investigation is running or has completed, you'll typically see one or more remediation actions that require approval by your security operations team to proceed.</span></span> 

<span data-ttu-id="a0dcd-108">In de volgende tabel worden de herstelacties samengevat die momenteel beschikbaar zijn in Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="a0dcd-108">The following table summarizes the remediation actions that are currently available in Office 365 ATP.</span></span> 

|<span data-ttu-id="a0dcd-109">Actie</span><span class="sxs-lookup"><span data-stu-id="a0dcd-109">Action</span></span> | <span data-ttu-id="a0dcd-110">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="a0dcd-110">Description</span></span> |
|-----|-----|
|<span data-ttu-id="a0dcd-111">URL blokkeren (kliktijd)</span><span class="sxs-lookup"><span data-stu-id="a0dcd-111">Block URL (time-of-click)</span></span> |<span data-ttu-id="a0dcd-112">Beschermt tegen e-mailberichten en documenten die schadelijke URL's bevatten.</span><span class="sxs-lookup"><span data-stu-id="a0dcd-112">Protects against email messages and documents that contain malicious URLs.</span></span> <span data-ttu-id="a0dcd-113">Dit maakt het blokkeren van kwaadaardige links en gerelateerde webpagina's via [Veilige Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) mogelijk wanneer de gebruiker op een koppeling in een bestaand Office-bestand of in een ouder e-mailbericht klikt.</span><span class="sxs-lookup"><span data-stu-id="a0dcd-113">This enables the blocking of malicious links and any related webpages via [Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) when the user clicks a link in an existing Office file or in an older email message.</span></span> |
|<span data-ttu-id="a0dcd-114">E-mail met zachte verwijdering</span><span class="sxs-lookup"><span data-stu-id="a0dcd-114">Soft delete email</span></span>  |<span data-ttu-id="a0dcd-115">Soft verwijdert specifieke e-mailberichten uit het postvak van een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="a0dcd-115">Soft delete specific email messages from a user's mailbox.</span></span> <br/><span data-ttu-id="a0dcd-116">Een bericht met zachte berichten wordt verplaatst naar de map Herstelbare items van een gebruiker en wordt bewaard totdat de bewaartermijn voor verwijderde items is verstreken.</span><span class="sxs-lookup"><span data-stu-id="a0dcd-116">A soft-deleted message is moved to a user's Recoverable Items folder and is retained until the deleted item retention period expires.</span></span> |
|<span data-ttu-id="a0dcd-117">E-mailclusters voor het verwijderen van zachte verwijderen</span><span class="sxs-lookup"><span data-stu-id="a0dcd-117">Soft delete email clusters</span></span>  |<span data-ttu-id="a0dcd-118">Soft verwijdert schadelijke e-mailberichten die overeenkomen met een query uit de postvakken van alle gebruikers.</span><span class="sxs-lookup"><span data-stu-id="a0dcd-118">Soft delete malicious email messages matching a query from all users' mailboxes.</span></span> <br/><span data-ttu-id="a0dcd-119">Verwijderde berichten worden verplaatst naar de map Herstelbare items van gebruikers en worden bewaard totdat de bewaartermijn voor verwijderde items is verstreken.</span><span class="sxs-lookup"><span data-stu-id="a0dcd-119">Soft-deleted messages are moved to users' Recoverable Items folder and are retained until the deleted item retention period expires.</span></span> |
|<span data-ttu-id="a0dcd-120">Extern doorsturen van e-mail uitschakelen</span><span class="sxs-lookup"><span data-stu-id="a0dcd-120">Turn off external mail forwarding</span></span> |<span data-ttu-id="a0dcd-121">Hiermee verwijdert u een doorstuurregel uit het postvak van een specifieke eindgebruiker.</span><span class="sxs-lookup"><span data-stu-id="a0dcd-121">Removes a forwarding rule from a specific end user's mailbox.</span></span>|

> [!NOTE]
> <span data-ttu-id="a0dcd-122">In Office 365 ATP worden automatisch geen herstelacties uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="a0dcd-122">In Office 365 ATP, no remediation actions are taken automatically.</span></span> <span data-ttu-id="a0dcd-123">Herstelacties worden alleen uitgevoerd na goedkeuring door het beveiligingsteam van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="a0dcd-123">Remediation actions are taken only upon approval by your organization's security team.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="a0dcd-124">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="a0dcd-124">Next steps</span></span>

- [<span data-ttu-id="a0dcd-125">Inbehandeling of voltooide herstelacties weergeven na een geautomatiseerd onderzoek in Office 365</span><span class="sxs-lookup"><span data-stu-id="a0dcd-125">View pending or completed remediation actions following an automated investigation in Office 365</span></span>](air-review-approve-pending-completed-actions.md)

- [<span data-ttu-id="a0dcd-126">Details en resultaten van een geautomatiseerd onderzoek in Office 365</span><span class="sxs-lookup"><span data-stu-id="a0dcd-126">Details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)

## <a name="related-articles"></a><span data-ttu-id="a0dcd-127">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="a0dcd-127">Related articles</span></span>

- [<span data-ttu-id="a0dcd-128">Geautomatiseerd onderzoek in Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a0dcd-128">Automated investigation in Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="a0dcd-129">Microsoft-bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="a0dcd-129">Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)