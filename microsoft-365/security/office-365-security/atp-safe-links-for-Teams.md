---
title: Veilige verbindingen voor werknemers voor teams, safelinks, veilige koppelingen, schadelijke koppelingen blokkeren, Office 365 ATP, veilige koppelingen voor teams, stop gebruikers op beschadigde koppelingen, schadelijke koppelingen
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 02/28/2020
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Teams heeft nu toegang tot veilige koppelingen op het moment van de klikken. Als u een abonnement hebt op Office 365, kunt u gebruikmaken van deze veiligheidsfunctie, ongeacht of u chatsessies van 1 tot en met 1 gebruikt, tussen groepen of in kanalen en tabbladen.
ms.openlocfilehash: 362fb37b352a77aea07b899b707dbf4ac3d440d5
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198749"
---
<!--06/21/2019-->

# <a name="safe-links-in-teams"></a><span data-ttu-id="16773-104">Veilige koppelingen in teams</span><span class="sxs-lookup"><span data-stu-id="16773-104">Safe Links in Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!IMPORTANT]
> <span data-ttu-id="16773-105">Deze functie is beschikbaar in de **openbare preview** voor klanten in het Microsoft teams-hulpprogramma voor Microsoft teams-technologie (tik) op 28 februari 2020.</span><span class="sxs-lookup"><span data-stu-id="16773-105">This feature is in **Public Preview** for customers in the Microsoft Teams Technology Adoption Program (TAP) as of Feb 28, 2020.</span></span> <span data-ttu-id="16773-106">Deze opmerking wordt van het artikel verwijderd wanneer veilige koppelingen voor teams meer beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="16773-106">This note will be removed from the article when Safe Links for Teams is more widely available.</span></span>

<span data-ttu-id="16773-107">Microsoft teams, een Microsoft-Cloud toepassing voor het beheren van uw werk, maakt al gebruik van veilige bijlagen (voor Office 365), maar deze functie heeft nu toegang tot veilige koppelingen op het moment van de klikken.</span><span class="sxs-lookup"><span data-stu-id="16773-107">Microsoft Teams, a Microsoft cloud-based application for managing your work, already uses Safe Attachments (for Office 365), but it will now have access to Safe Links at the time of your click.</span></span> <span data-ttu-id="16773-108">Als u een abonnement hebt op Office 365 ATP, kunt u gebruikmaken van deze veiligheidsmaatregel, ongeacht of u chat gesprekken, groepsgesprekken, kanalen of tabbladen gebruikt.</span><span class="sxs-lookup"><span data-stu-id="16773-108">Whether you're using Chats, Group Chats, Channels, or Tabs, if you have a subscription to Office 365 ATP, you will have the ability to enable and use this safety measure.</span></span> <span data-ttu-id="16773-109">Zie voor meer informatie over licentievereisten [Microsoft 365 Licensing Services Licensing-instructies](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="16773-109">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="16773-110">Dit werkt als volgt:</span><span class="sxs-lookup"><span data-stu-id="16773-110">Here's how it works:</span></span>

1. <span data-ttu-id="16773-111">Wanneer u de toepassing teams start, controleert Microsoft 365 of de gebruiker lid is van een organisatie met Office 365 ATP, en dat de gebruiker deel uitmaakt van een actief beleid voor veilige koppelingen met de bescherming ingeschakeld voor Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="16773-111">When you start the Teams application, Microsoft 365 will check to make sure the user belongs to an organization that has Office 365 ATP, and that the user is part of an active safe links policy with its protection enabled for Microsoft Teams.</span></span>

2. <span data-ttu-id="16773-112">Als de bovenstaande voorwaarden waar zijn, worden Url's gevalideerd wanneer u klikt op het moment van klikken in chats, groepsgesprekken, kanalen en de tabbladen van die gebruiker.</span><span class="sxs-lookup"><span data-stu-id="16773-112">If the above are true, then URLs will be validated at the time of click in Chats, Group Chats, Channels, and in Tabs for that user.</span></span>

## <a name="what-will-users-experience"></a><span data-ttu-id="16773-113">Wat werken gebruikers?</span><span class="sxs-lookup"><span data-stu-id="16773-113">What will users experience?</span></span>

<span data-ttu-id="16773-114">Alle beveiligde gebruikers hebben deze ervaring met gevaarlijke Url's:</span><span class="sxs-lookup"><span data-stu-id="16773-114">All protected users will have this experience with hazardous URLs:</span></span>

- <span data-ttu-id="16773-115">Als u op de koppeling hebt geklikt vanuit een teams-gesprek, groepsgesprek of kanalen, wordt een pagina weergegeven in de standaardbrowser.</span><span class="sxs-lookup"><span data-stu-id="16773-115">If the link was clicked from a Teams conversation, group chat, or from channels, a page will render in the default browser.</span></span> <span data-ttu-id="16773-116">Als u de koppeling hebt geklikt van het tabblad vastgemaakt, wordt de pagina weergegeven in de GEBRUIKERSINTERFACE van teams op dat tabblad en wordt de optie voor openen in browser uitgeschakeld vanwege beveiligingsredenen.</span><span class="sxs-lookup"><span data-stu-id="16773-116">If the link was clicked from a pinned tab, the page will appear in the Teams GUI within that tab, and the option to open in browser will be disabled for security purposes.</span></span>

- <span data-ttu-id="16773-117">Deze gebruiker wordt geblokkeerd en gaat verder met de site van de URL.</span><span class="sxs-lookup"><span data-stu-id="16773-117">This user will be blocked from proceeding to the URL's site.</span></span>

<span data-ttu-id="16773-118">Als de gebruiker die de koppeling heeft verzonden, niet is beveiligd door Office 365 ATP, kan hij of zij op de URL van zijn of haar machine klikken en de probleem site oplossen.</span><span class="sxs-lookup"><span data-stu-id="16773-118">If the user who sent the link isn't protected by Office 365 ATP, he or she is free to click the URL on his or her machine and resolve the problem site.</span></span> <span data-ttu-id="16773-119">Dit maakt het twee belangrijke punten van de beheerder op de hoogte van de naam van de beveiligde gebruikers.</span><span class="sxs-lookup"><span data-stu-id="16773-119">This makes it doubly important for administrators to be aware of who their protected users are and should be.</span></span>

![Een pagina met veilige koppelingen voor teams die een kwaadaardige koppeling rapporteren en de transit voor de pagina blokkeren.](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

<span data-ttu-id="16773-121">Als u op de knop *terug* op deze pagina in teams klikt, wordt deze gesloten, of kan een lege pagina worden gebruikt die gebruikers kunnen sluiten.</span><span class="sxs-lookup"><span data-stu-id="16773-121">Clicking the *Go Back* button on this page in Teams will close it out (or may result in a blank page users  can close out).</span></span> <span data-ttu-id="16773-122">Als u echter op de koppeling klikt, krijgt u een nieuwe beoordeling van de reputatie van de site zodat deze pagina opnieuw wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="16773-122">However, clicking on the link again will result in reassessment of the reputation of the site so that this page reappears.</span></span>

> [!NOTE]
> <span data-ttu-id="16773-123">Sommige Microsoft 365-beheerders zullen het bericht **toch doorgaan** op de pagina met blokkeren activeren.</span><span class="sxs-lookup"><span data-stu-id="16773-123">Some Microsoft 365 admins will enable the **Continue Anyway** message on the blocking page.</span></span> <span data-ttu-id="16773-124">Als u echter met veilige koppelingen de reputatie van een site aftreft en deze niet ziet, dan moet u verder klikken.</span><span class="sxs-lookup"><span data-stu-id="16773-124">However, if Safe Links measures the reputation of a site and finds it lacking, no further click-through should be undertaken.</span></span> <span data-ttu-id="16773-125">Gebruikers wordt niet aangeraden veiligheidsmaatregelen over te slaan.</span><span class="sxs-lookup"><span data-stu-id="16773-125">It is not recommended that users bypass safety measures.</span></span> <span data-ttu-id="16773-126">Weeg dit in uw overwegingen voordat u toch doorgaan inschakelt.</span><span class="sxs-lookup"><span data-stu-id="16773-126">Please weigh this into your considerations before enabling Continue Anyway.</span></span>
