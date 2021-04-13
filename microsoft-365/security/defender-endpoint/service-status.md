---
title: De service status van Microsoft Defender voor eindpunt controleren
description: Controleer de service health van Microsoft Defender voor eindpunten, kijk of er problemen zijn met de service en bekijk eerdere problemen die zijn opgelost.
keywords: dashboard, service, problemen, servicestatus, huidige status, statusgeschiedenis, overzicht van de gevolgen, voorlopige oorzaak, oplossing, resolutietijd, verwachte resolutietijd
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1b4545daace5df1a1a9c6e827f7d8f1b522a690c
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687623"
---
# <a name="check-the-microsoft-defender-for-endpoint-service-health"></a><span data-ttu-id="64395-104">De service status van Microsoft Defender voor eindpunt controleren</span><span class="sxs-lookup"><span data-stu-id="64395-104">Check the Microsoft Defender for Endpoint service health</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="64395-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="64395-105">**Applies to:**</span></span>
- [<span data-ttu-id="64395-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="64395-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)



><span data-ttu-id="64395-107">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="64395-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="64395-108">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="64395-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-servicestatus-abovefoldlink)

<span data-ttu-id="64395-109">**Servicestatus** bevat informatie over de huidige status van de Defender voor Eindpunt-service.</span><span class="sxs-lookup"><span data-stu-id="64395-109">**Service health** provides information on the current status of the Defender for Endpoint service.</span></span> <span data-ttu-id="64395-110">U kunt controleren of de service-status gezond is of dat er actuele problemen zijn.</span><span class="sxs-lookup"><span data-stu-id="64395-110">You'll be able to verify that the service health is healthy or if there are current issues.</span></span> <span data-ttu-id="64395-111">Als er problemen zijn, ziet u informatie, zoals wanneer het probleem is gedetecteerd, wat de voorlopige hoofdoorzaak is en de verwachte oplossingstijd.</span><span class="sxs-lookup"><span data-stu-id="64395-111">If there are issues, you'll see information such as when the issue was detected, what the preliminary root cause is, and the expected resolution time.</span></span>

<span data-ttu-id="64395-112">U ziet ook informatie over historische problemen die zijn opgelost en details, zoals de datum en tijd waarop het probleem is opgelost.</span><span class="sxs-lookup"><span data-stu-id="64395-112">You'll also see information on historical issues that have been resolved and details such as the date and time when the issue was resolved.</span></span> <span data-ttu-id="64395-113">Als er geen problemen zijn met de service, ziet u een gezonde status.</span><span class="sxs-lookup"><span data-stu-id="64395-113">When there are no issues on the service, you'll see a healthy status.</span></span>

<span data-ttu-id="64395-114">U kunt details over de servicetoestand weergeven door op de tegel te klikken in het **dashboard** Beveiligingsbewerkingen of het **menu Service** status te selecteren in het navigatiedeelvenster.</span><span class="sxs-lookup"><span data-stu-id="64395-114">You can view details on the service health by clicking the tile from the **Security operations dashboard** or selecting the **Service health** menu from the navigation pane.</span></span>

<span data-ttu-id="64395-115">De **pagina Service-statusdetails** heeft de volgende tabbladen:</span><span class="sxs-lookup"><span data-stu-id="64395-115">The **Service health** details page has the following tabs:</span></span>

- <span data-ttu-id="64395-116">**Huidige status**</span><span class="sxs-lookup"><span data-stu-id="64395-116">**Current status**</span></span>
- <span data-ttu-id="64395-117">**Statusgeschiedenis**</span><span class="sxs-lookup"><span data-stu-id="64395-117">**Status history**</span></span>

## <a name="current-status"></a><span data-ttu-id="64395-118">Huidige status</span><span class="sxs-lookup"><span data-stu-id="64395-118">Current status</span></span>
<span data-ttu-id="64395-119">Op **het tabblad Huidige status** wordt de huidige status van de Defender voor Eindpunt-service weergegeven.</span><span class="sxs-lookup"><span data-stu-id="64395-119">The **Current status** tab shows the current state of the Defender for Endpoint service.</span></span> <span data-ttu-id="64395-120">Wanneer de service soepel wordt uitgevoerd, wordt een gezonde servicetoestand weergegeven.</span><span class="sxs-lookup"><span data-stu-id="64395-120">When the service is running smoothly a healthy service health is shown.</span></span> <span data-ttu-id="64395-121">Als er problemen zijn, worden de volgende servicedetails weergegeven om u beter inzicht te geven in het probleem:</span><span class="sxs-lookup"><span data-stu-id="64395-121">If there are issues seen, the following service details are shown to help you gain better insight about the issue:</span></span>

- <span data-ttu-id="64395-122">Datum en tijd voor wanneer het probleem is gedetecteerd</span><span class="sxs-lookup"><span data-stu-id="64395-122">Date and time for when the issue was detected</span></span>
- <span data-ttu-id="64395-123">Een korte beschrijving van het probleem</span><span class="sxs-lookup"><span data-stu-id="64395-123">A short description of the issue</span></span>
- <span data-ttu-id="64395-124">Tijd bijwerken</span><span class="sxs-lookup"><span data-stu-id="64395-124">Update time</span></span>
- <span data-ttu-id="64395-125">Overzicht van de gevolgen</span><span class="sxs-lookup"><span data-stu-id="64395-125">Summary of impact</span></span>
- <span data-ttu-id="64395-126">Voorlopige hoofdoorzaak</span><span class="sxs-lookup"><span data-stu-id="64395-126">Preliminary root cause</span></span>
- <span data-ttu-id="64395-127">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="64395-127">Next steps</span></span>
- <span data-ttu-id="64395-128">Verwachte resolutietijd</span><span class="sxs-lookup"><span data-stu-id="64395-128">Expected resolution time</span></span>

<span data-ttu-id="64395-129">Updates over de voortgang van een probleem worden weergegeven op de pagina wanneer het probleem wordt opgelost.</span><span class="sxs-lookup"><span data-stu-id="64395-129">Updates on the progress of an issue are reflected on the page as the issue gets resolved.</span></span> <span data-ttu-id="64395-130">U ziet updates over informatie, zoals een bijgewerkte geschatte resolutietijd of volgende stappen.</span><span class="sxs-lookup"><span data-stu-id="64395-130">You'll see updates on information such as an updated estimate resolution time or next steps.</span></span>

<span data-ttu-id="64395-131">Wanneer een probleem is opgelost, wordt het opgenomen op het **tabblad Statusgeschiedenis.**</span><span class="sxs-lookup"><span data-stu-id="64395-131">When an issue is resolved, it gets recorded in the **Status history** tab.</span></span>

## <a name="status-history"></a><span data-ttu-id="64395-132">Statusgeschiedenis</span><span class="sxs-lookup"><span data-stu-id="64395-132">Status history</span></span>
<span data-ttu-id="64395-133">Het **tabblad Statusgeschiedenis** geeft alle historische problemen weer die zijn gezien en opgelost.</span><span class="sxs-lookup"><span data-stu-id="64395-133">The **Status history** tab reflects all the historical issues that were seen and resolved.</span></span> <span data-ttu-id="64395-134">U ziet details van de opgeloste problemen, samen met de andere gegevens die zijn opgenomen terwijl deze werden opgelost.</span><span class="sxs-lookup"><span data-stu-id="64395-134">You'll see details of the resolved issues along with the other information that were included while it was being resolved.</span></span>

### <a name="related-topic"></a><span data-ttu-id="64395-135">Verwant onderwerp</span><span class="sxs-lookup"><span data-stu-id="64395-135">Related topic</span></span>
- [<span data-ttu-id="64395-136">Het dashboard Beveiligingsbewerkingen weergeven</span><span class="sxs-lookup"><span data-stu-id="64395-136">View the Security operations dashboard</span></span>](security-operations-dashboard.md)
