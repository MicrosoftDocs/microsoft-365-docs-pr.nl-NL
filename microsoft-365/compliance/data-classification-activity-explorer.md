---
title: Aan de slag met de activiteitenverkenner
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Activiteitsverkenner rondt de functionaliteit van de functie gegevensclassificatie af door u te laten zien en filteren op de acties die gebruikers uitvoeren op uw gelabelde inhoud.
ms.openlocfilehash: 414ef4e5d9f6472180a5eaef391d3eba33463b02
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/30/2021
ms.locfileid: "52162883"
---
# <a name="get-started-with-activity-explorer"></a><span data-ttu-id="14320-103">Aan de slag met de activiteitenverkenner</span><span class="sxs-lookup"><span data-stu-id="14320-103">Get started with activity explorer</span></span>

<span data-ttu-id="14320-104">Het [overzicht van de gegevensclassificatie](data-classification-overview.md) [en](data-classification-content-explorer.md) de tabbladen van de inhoudsverkenner geven u inzicht in welke inhoud is gevonden en gelabeld en waar die inhoud zich vindt.</span><span class="sxs-lookup"><span data-stu-id="14320-104">The [data classification overview](data-classification-overview.md) and [content explorer](data-classification-content-explorer.md) tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="14320-105">Activiteitsverkenner rondt deze suite met functionaliteit af door u te laten controleren wat er met uw gelabelde inhoud wordt gedaan.</span><span class="sxs-lookup"><span data-stu-id="14320-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="14320-106">Activiteitsverkenner biedt een historische weergave van activiteiten op uw gelabelde inhoud.</span><span class="sxs-lookup"><span data-stu-id="14320-106">Activity explorer provides a historical view of activities on your labeled content.</span></span> <span data-ttu-id="14320-107">De activiteitsgegevens worden verzameld uit Microsoft 365 geïntegreerde auditlogboeken, getransformeerd en beschikbaar gesteld in de gebruikersinterface van Activity Explorer.</span><span class="sxs-lookup"><span data-stu-id="14320-107">The activity information is collected from the Microsoft 365 unified audit logs, transformed and made available in the Activity explorer UI.</span></span> 

![placeholder screenshot overview activity explorer](../media/data-classification-activity-explorer-1.png)

<span data-ttu-id="14320-109">Er zijn meer dan 30 verschillende filters beschikbaar voor gebruik, sommige zijn:</span><span class="sxs-lookup"><span data-stu-id="14320-109">There are over 30 different filters available for use, some are:</span></span>

- <span data-ttu-id="14320-110">datumbereik</span><span class="sxs-lookup"><span data-stu-id="14320-110">date range</span></span>
- <span data-ttu-id="14320-111">activiteitstype</span><span class="sxs-lookup"><span data-stu-id="14320-111">activity type</span></span>
- <span data-ttu-id="14320-112">locatie</span><span class="sxs-lookup"><span data-stu-id="14320-112">location</span></span>
- <span data-ttu-id="14320-113">gebruiker</span><span class="sxs-lookup"><span data-stu-id="14320-113">user</span></span>
- <span data-ttu-id="14320-114">gevoeligheidslabel</span><span class="sxs-lookup"><span data-stu-id="14320-114">sensitivity label</span></span>
- <span data-ttu-id="14320-115">bewaarlabel</span><span class="sxs-lookup"><span data-stu-id="14320-115">retention label</span></span>
- <span data-ttu-id="14320-116">bestandspad</span><span class="sxs-lookup"><span data-stu-id="14320-116">file path</span></span>
- <span data-ttu-id="14320-117">DLP-beleid</span><span class="sxs-lookup"><span data-stu-id="14320-117">DLP policy</span></span>



## <a name="prerequisites"></a><span data-ttu-id="14320-118">Vereisten</span><span class="sxs-lookup"><span data-stu-id="14320-118">Prerequisites</span></span>

<span data-ttu-id="14320-119">Aan elk account dat toegang krijgt tot en gebruikmaakt van gegevensclassificatie moet een licentie zijn toegewezen vanuit een van deze abonnementen:</span><span class="sxs-lookup"><span data-stu-id="14320-119">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="14320-120">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="14320-120">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="14320-121">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="14320-121">Office 365 (E5)</span></span>
- <span data-ttu-id="14320-122">Geavanceerde hulpprogramma's voor compliance (E5) invoegtoepassing</span><span class="sxs-lookup"><span data-stu-id="14320-122">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="14320-123">Geavanceerde bedreigingsinformatie (E5) invoegtoepassing</span><span class="sxs-lookup"><span data-stu-id="14320-123">Advanced Threat Intelligence (E5) add-on</span></span>
- <span data-ttu-id="14320-124">Microsoft 365 E5/A5 Info Protection & Governance</span><span class="sxs-lookup"><span data-stu-id="14320-124">Microsoft 365 E5/A5 Info Protection & Governance</span></span>
- <span data-ttu-id="14320-125">Microsoft 365 E5/A5 Compliance</span><span class="sxs-lookup"><span data-stu-id="14320-125">Microsoft 365 E5/A5 Compliance</span></span>

### <a name="permissions"></a><span data-ttu-id="14320-126">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="14320-126">Permissions</span></span>

 <span data-ttu-id="14320-127">Als u toegang wilt krijgen tot het tabblad Activiteitsverkenner, moet aan een account expliciet lidmaatschap zijn toegewezen aan een van deze rollengroepen of expliciet aan de rol zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="14320-127">In order to get access to the activity explorer tab, an account must be explicitly assigned membership in any one of these role groups or explicitly granted the role.</span></span>

<!--
> [!IMPORTANT]
> Access to Activity explorer via the Security reader or Device Management role groups or other has been removed-->

<span data-ttu-id="14320-128">**Microsoft 365-rollengroepen**</span><span class="sxs-lookup"><span data-stu-id="14320-128">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="14320-129">Globale beheerder</span><span class="sxs-lookup"><span data-stu-id="14320-129">Global administrator</span></span>
- <span data-ttu-id="14320-130">Beheerder voor naleving</span><span class="sxs-lookup"><span data-stu-id="14320-130">Compliance administrator</span></span>
- <span data-ttu-id="14320-131">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="14320-131">Security administrator</span></span>
- <span data-ttu-id="14320-132">Beheerder van nalevingsgegevens</span><span class="sxs-lookup"><span data-stu-id="14320-132">Compliance data administrator</span></span>

<span data-ttu-id="14320-133">**Microsoft 365 rollen**</span><span class="sxs-lookup"><span data-stu-id="14320-133">**Microsoft 365 roles**</span></span>

- <span data-ttu-id="14320-134">Beheerder voor naleving</span><span class="sxs-lookup"><span data-stu-id="14320-134">Compliance administrator</span></span>
- <span data-ttu-id="14320-135">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="14320-135">Security administrator</span></span>

## <a name="activity-types"></a><span data-ttu-id="14320-136">Activiteitstypen</span><span class="sxs-lookup"><span data-stu-id="14320-136">Activity types</span></span>

<span data-ttu-id="14320-137">Activiteitsverkenner verzamelt activiteitsgegevens uit de auditlogboeken op meerdere bronnen van activiteiten.</span><span class="sxs-lookup"><span data-stu-id="14320-137">Activity explorer gathers activity information from the audit logs on multiple sources of activities.</span></span> <span data-ttu-id="14320-138">Zie [Labeling events available in Activity explorer (Labeling events available in Activity explorer)](data-classification-activity-explorer-available-events.md)voor meer informatie over de labelactiviteit die activiteit maakt voor Activiteitsverkenner.</span><span class="sxs-lookup"><span data-stu-id="14320-138">For more detailed information on what labeling activity makes it to Activity explorer, see [Labeling events available in Activity explorer](data-classification-activity-explorer-available-events.md).</span></span>

<span data-ttu-id="14320-139">**Activiteiten voor** gevoeligheidslabels en activiteiten voor het bewaren van etiketten van Office native toepassingen, azure information protection-invoegtoepassingen, SharePoint Online, Exchange Online (alleen gevoeligheidslabels) en OneDrive. </span><span class="sxs-lookup"><span data-stu-id="14320-139">**Sensitivity label activities** and **Retention labeling activities** from Office native applications, Azure Information Protection add-in, SharePoint Online, Exchange Online (sensitivity labels only) and OneDrive.</span></span> <span data-ttu-id="14320-140">Enkele voorbeelden zijn:</span><span class="sxs-lookup"><span data-stu-id="14320-140">Some examples are:</span></span>

- <span data-ttu-id="14320-141">label toegepast</span><span class="sxs-lookup"><span data-stu-id="14320-141">label applied</span></span>
- <span data-ttu-id="14320-142">label gewijzigd (bijgewerkt, gedegradeerd of verwijderd)</span><span class="sxs-lookup"><span data-stu-id="14320-142">label changed (upgraded, downgraded, or removed)</span></span>
- <span data-ttu-id="14320-143">automatische labelingsimulatie</span><span class="sxs-lookup"><span data-stu-id="14320-143">auto-labeling simulation</span></span>
- <span data-ttu-id="14320-144">bestand gelezen</span><span class="sxs-lookup"><span data-stu-id="14320-144">file read</span></span> 

<span data-ttu-id="14320-145">**AIP-scanner (Azure Information Protection) en AIP-clients**</span><span class="sxs-lookup"><span data-stu-id="14320-145">**Azure Information Protection (AIP) scanner and AIP clients**</span></span>

- <span data-ttu-id="14320-146">toegepaste beveiliging</span><span class="sxs-lookup"><span data-stu-id="14320-146">protection applied</span></span>
- <span data-ttu-id="14320-147">beveiliging gewijzigd</span><span class="sxs-lookup"><span data-stu-id="14320-147">protection changed</span></span>
- <span data-ttu-id="14320-148">beveiliging verwijderd</span><span class="sxs-lookup"><span data-stu-id="14320-148">protection removed</span></span>
- <span data-ttu-id="14320-149">bestanden die zijn gevonden</span><span class="sxs-lookup"><span data-stu-id="14320-149">files discovered</span></span> 

<span data-ttu-id="14320-150">Activiteitenverkenner  verzamelt ook DLP-beleidsgebeurtenissen uit Exchange Online, SharePoint Online, OneDrive, Teams Chat en Kanaal (preview), on-premises SharePoint-mappen en -bibliotheken, on-premises bestandsaandelen en Windows 10-apparaten via **Endpoint Data Loss Prevention (DLP).**</span><span class="sxs-lookup"><span data-stu-id="14320-150">Activity explorer also gathers **DLP policy matches** events from Exchange Online, SharePoint Online, OneDrive, Teams Chat and Channel (preview), on-premises SharePoint folders and libraries, and on-premises file shares, and Windows 10 devices via **Endpoint data loss prevention (DLP)**.</span></span> <span data-ttu-id="14320-151">Enkele voorbeelden van gebeurtenissen Windows 10 apparaten zijn bestand:</span><span class="sxs-lookup"><span data-stu-id="14320-151">Some examples events from Windows 10 devices are file:</span></span>

- <span data-ttu-id="14320-152">verwijderingen</span><span class="sxs-lookup"><span data-stu-id="14320-152">deletions</span></span>
- <span data-ttu-id="14320-153">creaties</span><span class="sxs-lookup"><span data-stu-id="14320-153">creations</span></span>
- <span data-ttu-id="14320-154">gekopieerd naar klembord</span><span class="sxs-lookup"><span data-stu-id="14320-154">copied to clipboard</span></span>
- <span data-ttu-id="14320-155">gewijzigd</span><span class="sxs-lookup"><span data-stu-id="14320-155">modified</span></span>
- <span data-ttu-id="14320-156">gelezen</span><span class="sxs-lookup"><span data-stu-id="14320-156">read</span></span>
- <span data-ttu-id="14320-157">afgedrukt</span><span class="sxs-lookup"><span data-stu-id="14320-157">printed</span></span>
- <span data-ttu-id="14320-158">naam gewijzigd</span><span class="sxs-lookup"><span data-stu-id="14320-158">renamed</span></span>
- <span data-ttu-id="14320-159">gekopieerd naar netwerk delen</span><span class="sxs-lookup"><span data-stu-id="14320-159">copied to network share</span></span>
- <span data-ttu-id="14320-160">toegankelijk via niet-toegestaan app</span><span class="sxs-lookup"><span data-stu-id="14320-160">accessed by unallowed app</span></span> 

<span data-ttu-id="14320-161">De waarde van het begrijpen van de acties die worden ondernomen met uw gevoelige inhoud met [](dlp-learn-about-dlp.md) het label is dat u kunt zien of de besturingselementen die u al hebt gebruikt, zoals preventie van gegevensverlies, effectief zijn of niet.</span><span class="sxs-lookup"><span data-stu-id="14320-161">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention](dlp-learn-about-dlp.md) are effective or not.</span></span> <span data-ttu-id="14320-162">Zo niet, of als u iets onverwachts ontdekt, zoals een groot aantal items met een label en een downgrade, kunt u uw verschillende beleidsregels beheren en nieuwe acties ondernemen om ongewenst gedrag te `highly confidential` `general` beperken.</span><span class="sxs-lookup"><span data-stu-id="14320-162">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="14320-163">Activiteitsverkenner controleert momenteel geen bewaaractiviteiten voor Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="14320-163">Activity explorer doesn't currently monitor retention activities for Exchange Online.</span></span>

## <a name="see-also"></a><span data-ttu-id="14320-164">Zie ook</span><span class="sxs-lookup"><span data-stu-id="14320-164">See also</span></span>

- [<span data-ttu-id="14320-165">Meer informatie over vertrouwelijkheidslabels</span><span class="sxs-lookup"><span data-stu-id="14320-165">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="14320-166">Meer informatie over bewaarbeleid en retentielabels</span><span class="sxs-lookup"><span data-stu-id="14320-166">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="14320-167">Meer informatie over typen gevoelige informatie</span><span class="sxs-lookup"><span data-stu-id="14320-167">Learn about sensitive information types</span></span>](sensitive-information-type-learn-about.md)
- [<span data-ttu-id="14320-168">Meer informatie over gegevensclassificatie</span><span class="sxs-lookup"><span data-stu-id="14320-168">Learn about data classification</span></span>](data-classification-overview.md)
