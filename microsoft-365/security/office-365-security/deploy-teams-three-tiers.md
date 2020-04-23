---
title: Teams implementeren voor drie beveiligingslagen voor bestanden
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 1e8e3cfd-b878-4088-b941-9940363a5fae
description: Maak en configureer teams met Microsoft Teams voor verschillende niveaus gegevensbeveiliging voor bestanden.
ms.openlocfilehash: d8912900a02149d198222a4402e101b0dce53310
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637638"
---
# <a name="deploy-teams-for-three-tiers-of-protection-for-files"></a><span data-ttu-id="c3290-103">Teams implementeren voor drie beveiligingslagen voor bestanden</span><span class="sxs-lookup"><span data-stu-id="c3290-103">Deploy teams for three tiers of protection for files</span></span>

<span data-ttu-id="c3290-104">Gebruik de stappen in dit artikel om basislijnteams en gevoelige en zeer vertrouwelijke teams te ontwerpen en te implementeren.</span><span class="sxs-lookup"><span data-stu-id="c3290-104">Use the steps in this article to design and deploy baseline, sensitive, and highly confidential teams.</span></span> <span data-ttu-id="c3290-105">Zie [Bestanden beveiligen in Microsoft Teams](secure-files-in-teams.md) voor meer informatie over deze drie beveiligingslagen.</span><span class="sxs-lookup"><span data-stu-id="c3290-105">For more information about these three tiers of protection, see [Secure files in Microsoft Teams](secure-files-in-teams.md).</span></span>

## <a name="baseline-teams"></a><span data-ttu-id="c3290-106">Basislijnteams</span><span class="sxs-lookup"><span data-stu-id="c3290-106">Baseline teams</span></span>

<span data-ttu-id="c3290-107">Basislijnbeveiliging omvat zowel openbare teams als privéteams.</span><span class="sxs-lookup"><span data-stu-id="c3290-107">Baseline protection includes both public and private teams.</span></span> <span data-ttu-id="c3290-108">Openbare teams kunnen door iedereen in de organisatie worden gedetecteerd en geopend.</span><span class="sxs-lookup"><span data-stu-id="c3290-108">Public teams can be discovered and accessed by anybody in the organization.</span></span> <span data-ttu-id="c3290-109">Privéteams kunnen alleen worden gedetecteerd en geopend door leden van de Microsoft 365-groep die is gekoppeld aan het team.</span><span class="sxs-lookup"><span data-stu-id="c3290-109">Private sites can only be discovered and accessed by members of the Microsoft 365 group associated with the team.</span></span> <span data-ttu-id="c3290-110">Met beide typen teams kunnen leden de site delen met anderen.</span><span class="sxs-lookup"><span data-stu-id="c3290-110">Both of these types of teams allow members to share the site with others.</span></span>

### <a name="public"></a><span data-ttu-id="c3290-111">Openbaar</span><span class="sxs-lookup"><span data-stu-id="c3290-111">Public</span></span>

<span data-ttu-id="c3290-112">Volg de instructies in [dit artikel](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) om een basislijnteam met openbare toegang en machtigingen te maken.</span><span class="sxs-lookup"><span data-stu-id="c3290-112">Follow the instructions in [this article](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) to create a baseline Team with public access and permissions.</span></span>

<span data-ttu-id="c3290-113">Dit is de resulterende configuratie.</span><span class="sxs-lookup"><span data-stu-id="c3290-113">Here is your resulting configuration.</span></span>

![Basislijnbeveiliging voor een openbaar team.](../../media/baseline-public-team.png)

### <a name="private"></a><span data-ttu-id="c3290-115">Privé</span><span class="sxs-lookup"><span data-stu-id="c3290-115">Private</span></span>

<span data-ttu-id="c3290-116">Volg de instructies in [dit artikel](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) om een basislijnteam met persoonlijke toegang en machtigingen te maken.</span><span class="sxs-lookup"><span data-stu-id="c3290-116">Follow the instructions in [this article](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) to create a baseline Team with private access and permissions.</span></span>

<span data-ttu-id="c3290-117">Dit is de resulterende configuratie.</span><span class="sxs-lookup"><span data-stu-id="c3290-117">Here is your resulting configuration.</span></span>

![Basislijnbeveiliging voor een privéteam.](../../media/baseline-private-team.png)

## <a name="sensitive-teams"></a><span data-ttu-id="c3290-119">Gevoelige teams</span><span class="sxs-lookup"><span data-stu-id="c3290-119">Sensitive teams</span></span>

<span data-ttu-id="c3290-120">Voor een gevoelig team begint u met [het maken van een privéteam](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).</span><span class="sxs-lookup"><span data-stu-id="c3290-120">For a sensitive team, you start by [creating a private team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).</span></span>

<span data-ttu-id="c3290-121">Vervolgens configureert u de onderliggende SharePoint-site om het delen door teamleden te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="c3290-121">Next, you configure the underlying SharePoint site to prevent sharing by team members.</span></span>

1. <span data-ttu-id="c3290-122">Klik op de werkbalk van het team op **Bestanden**.</span><span class="sxs-lookup"><span data-stu-id="c3290-122">In the tool bar for the team, click **Files**.</span></span>

2. <span data-ttu-id="c3290-123">Klik op het beletselteken en klik vervolgens op **Openen in SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="c3290-123">Click the ellipsis, and then click **Open in SharePoint**.</span></span>

3. <span data-ttu-id="c3290-124">Klik op de werkbalk van de onderliggende SharePoint-site op het pictogram Instellingen en vervolgens op **Sitemachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="c3290-124">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>

4. <span data-ttu-id="c3290-125">Klik in het deelvenster **Sitemachtigingen** onder **Instellingen voor delen** op **Instellingen voor delen wijzigen**.</span><span class="sxs-lookup"><span data-stu-id="c3290-125">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>

5. <span data-ttu-id="c3290-126">Kies onder **Machtigingen voor delen** de optie **Alleen site-eigenaren kunnen bestanden, mappen en de site delen** en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="c3290-126">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>

<span data-ttu-id="c3290-127">Dit is de resulterende configuratie.</span><span class="sxs-lookup"><span data-stu-id="c3290-127">Here is your resulting configuration.</span></span>

![Bescherming van gevoelige gegevens voor een team.](../../media/sensitive-team.png)

## <a name="highly-confidential-teams"></a><span data-ttu-id="c3290-129">Zeer vertrouwelijke teams</span><span class="sxs-lookup"><span data-stu-id="c3290-129">Highly confidential teams</span></span>

<span data-ttu-id="c3290-130">Voor een zeer vertrouwelijk team begint u met [het maken van een privéteam](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).</span><span class="sxs-lookup"><span data-stu-id="c3290-130">With a highly confidential team, you start by [creating a private team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).</span></span>

<span data-ttu-id="c3290-131">Vervolgens configureert u de onderliggende SharePoint-site om het delen door teamleden en het aanvragen van toegang door niet-leden van het team te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="c3290-131">Next, you configure the underlying SharePoint site to prevent sharing by team members and the requesting of access by non-members of the team.</span></span>

1. <span data-ttu-id="c3290-132">Klik op de werkbalk van het team op **Bestanden**.</span><span class="sxs-lookup"><span data-stu-id="c3290-132">In the tool bar for the team, click **Files**.</span></span>

2. <span data-ttu-id="c3290-133">Klik op het beletselteken en klik vervolgens op **Openen in SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="c3290-133">Click the ellipsis, and then click **Open in SharePoint**.</span></span>

3. <span data-ttu-id="c3290-134">Klik op de werkbalk van de onderliggende SharePoint-site op het pictogram Instellingen en vervolgens op **Sitemachtigingen**.</span><span class="sxs-lookup"><span data-stu-id="c3290-134">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>

4. <span data-ttu-id="c3290-135">Klik in het deelvenster **Sitemachtigingen** onder **Instellingen voor delen** op **Instellingen voor delen wijzigen**.</span><span class="sxs-lookup"><span data-stu-id="c3290-135">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>

5. <span data-ttu-id="c3290-136">Kies onder **Machtigingen voor delen**, **Alleen site-eigenaren kunnen bestanden, mappen en de site delen**.</span><span class="sxs-lookup"><span data-stu-id="c3290-136">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>

6. <span data-ttu-id="c3290-137">Schakel **Toegangsaanvragen toestaan** uit en klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="c3290-137">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="c3290-138">Dit is de resulterende configuratie.</span><span class="sxs-lookup"><span data-stu-id="c3290-138">Here is your resulting configuration.</span></span>

![Bescherming van zeer vertrouwelijke gegevens voor een team.](../../media/highly-confidential-team.png)

## <a name="next-step"></a><span data-ttu-id="c3290-140">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="c3290-140">Next step</span></span>

[<span data-ttu-id="c3290-141">Bestanden in teams beveiligen met retentielabels en DLP</span><span class="sxs-lookup"><span data-stu-id="c3290-141">Protect files in teams with retention labels and DLP</span></span>](deploy-teams-retention-DLP.md)

## <a name="see-also"></a><span data-ttu-id="c3290-142">Zie ook</span><span class="sxs-lookup"><span data-stu-id="c3290-142">See also</span></span>

[<span data-ttu-id="c3290-143">Bestanden beveiligen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c3290-143">Secure files in Microsoft Teams</span></span>](secure-files-in-teams.md)

<span data-ttu-id="c3290-144">[Cloud adoption and hybrid solutions](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions) (Overstappen op de cloud en hybride oplossingen)</span><span class="sxs-lookup"><span data-stu-id="c3290-144">[Cloud adoption and hybrid solutions](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)</span></span>
