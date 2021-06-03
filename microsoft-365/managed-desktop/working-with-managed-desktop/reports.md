---
title: Werken met rapporten
description: De verschillende rapporten die beschikbaar zijn in Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 28035a9f0a669c1daa7526d0b1fefac52a77c81a
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/03/2021
ms.locfileid: "52729966"
---
# <a name="work-with-reports"></a><span data-ttu-id="e3179-104">Werken met rapporten</span><span class="sxs-lookup"><span data-stu-id="e3179-104">Work with reports</span></span>

<span data-ttu-id="e3179-105">Microsoft Managed Desktop bevat verschillende rapporten en dashboards die IT-beheerders in uw organisatie kunnen gebruiken om verschillende aspecten van de populatie van apparaten te begrijpen.</span><span class="sxs-lookup"><span data-stu-id="e3179-105">Microsoft Managed Desktop provides several reports and dashboards that IT admins in your organization can use to understand various aspects of the population of devices.</span></span><span data-ttu-id="e3179-106">U vindt rapporten op twee locaties: [in](https://endpoint.microsoft.com) Microsoft Endpoint Manager en in het [Microsoft 365 beheercentrum.](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)</span><span class="sxs-lookup"><span data-stu-id="e3179-106"> You'll find reports in two locations: in [Microsoft Endpoint Manager](https://endpoint.microsoft.com) and in the [Microsoft 365 Admin Center](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop).</span></span> 

## <a name="reports-in-microsoft-endpoint-manager"></a><span data-ttu-id="e3179-107">Rapporten in Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="e3179-107">Reports in Microsoft Endpoint Manager</span></span>

<span data-ttu-id="e3179-108">De Microsoft Endpoint Manager console brengt rapportage van verschillende producten samen op één locatie om u te helpen bij het controleren en onderzoeken van problemen met uw Azure AD-organisatie ("tenant")-configuratie en -apparaten.</span><span class="sxs-lookup"><span data-stu-id="e3179-108">The Microsoft Endpoint Manager console brings together reporting from several products into a single location to help you monitor and investigate issues with your Azure AD organization ("tenant") configuration and devices.</span></span> <span data-ttu-id="e3179-109">Microsoft Managed desktop heeft een sectie onder **Rapporten** in het hoofdmenu waar u rapporten kunt vinden die specifiek zijn voor het beheer Microsoft Managed Desktop van de apparaten die u hebt geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="e3179-109">Microsoft Managed desktop has a section under **Reports** in the main menu where you can find reports specific to Microsoft Managed Desktop's management of the devices you’ve registered.</span></span>

<span data-ttu-id="e3179-110">Deze rapporten omvatten:</span><span class="sxs-lookup"><span data-stu-id="e3179-110">These reports include:</span></span>
- <span data-ttu-id="e3179-111">**Beheerde apparaten**  >  **Functie-updates:** in deze weergave ziet u de algehele status van functie-updates op uw Microsoft Managed Desktop apparaten.</span><span class="sxs-lookup"><span data-stu-id="e3179-111">**Managed devices** > **Feature updates**: This view shows the overall status of feature updates across your Microsoft Managed Desktop devices.</span></span>
- <span data-ttu-id="e3179-112">**Beheerde apparaten**  >  **Office updates:** in deze weergave ziet u de algehele status van Office updates op uw Microsoft Managed Desktop apparaten.</span><span class="sxs-lookup"><span data-stu-id="e3179-112">**Managed devices** > **Office updates**: This view shows the overall status of Office updates across your Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="e3179-113">Bovendien kunt u op verschillende locaties in Microsoft Endpoint Manager rapporten van andere productgroepen filteren om uw apparaten die worden beheerd door Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="e3179-113">Additionally, in several locations throughout Microsoft Endpoint Manager you can filter reports from other product groups to specifically include or exclude your devices that are managed by Microsoft Managed Desktop.</span></span> <span data-ttu-id="e3179-114">Deze rapporten hebben deze filterfunctie geïntegreerd:</span><span class="sxs-lookup"><span data-stu-id="e3179-114">These reports have integrated this filtering capability:</span></span>

- [<span data-ttu-id="e3179-115">Alle apparaten</span><span class="sxs-lookup"><span data-stu-id="e3179-115">All devices</span></span>](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [<span data-ttu-id="e3179-116">Apparaat compliance</span><span class="sxs-lookup"><span data-stu-id="e3179-116">Device compliance</span></span>](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [<span data-ttu-id="e3179-117">Niet-compatibele apparaten</span><span class="sxs-lookup"><span data-stu-id="e3179-117">Noncompliant devices</span></span>](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> <span data-ttu-id="e3179-118">Aangepaste Microsoft Managed Desktop garanderen alleen toegang tot de Microsoft Managed Desktop rapporten.</span><span class="sxs-lookup"><span data-stu-id="e3179-118">Custom Microsoft Managed Desktop roles guarantee access only to the Microsoft Managed Desktop reports.</span></span> <span data-ttu-id="e3179-119">Zie Op Microsoft Endpoint Manager rollen gebaseerd toegangsbeheer met [Microsoft Intune.](/mem/intune/fundamentals/role-based-access-control) </span><span class="sxs-lookup"><span data-stu-id="e3179-119">To access other parts of Microsoft Endpoint Manager, such as **All devices**, see [Role-based access control with Microsoft Intune](/mem/intune/fundamentals/role-based-access-control).</span></span> 


 ## <a name="inventory-data"></a><span data-ttu-id="e3179-120">Voorraadgegevens</span><span class="sxs-lookup"><span data-stu-id="e3179-120">Inventory data</span></span>

<span data-ttu-id="e3179-121">Naast de andere rapporten kunt u informatie exporteren over de apparaten die worden beheerd door Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="e3179-121">In addition to the other reports, you can export information about the devices managed by Microsoft Managed Desktop.</span></span> <span data-ttu-id="e3179-122">Gebruik in **de** weergave Apparaten van **het** gebied Apparaten van Microsoft Endpoint Manager het tabblad Alles **exporteren** om een gedetailleerd [voorraadrapport te downloaden.](device-inventory-report.md)</span><span class="sxs-lookup"><span data-stu-id="e3179-122">In the **Devices** view of the **Devices** area of Microsoft Endpoint Manager, use the **Export all** tab to [download a detailed inventory report](device-inventory-report.md).</span></span>