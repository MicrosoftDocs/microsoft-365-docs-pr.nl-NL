---
title: Geïsoleerde SharePoint Online-teamsites
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: overview
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 71250a04-fd2d-4c3c-a32b-b8a838b19a54
description: Meer informatie over geïsoleerde SharePoint Online-teamsites, zoals gebruik, vereisten en functies waarmee ze kunnen worden gebruikt.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 056c6f2a463d38dd27b26d484995280dddedf436
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286583"
---
# <a name="isolated-sharepoint-online-team-sites"></a><span data-ttu-id="6f516-103">Geïsoleerde SharePoint Online-teamsites</span><span class="sxs-lookup"><span data-stu-id="6f516-103">Isolated SharePoint Online team sites</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6f516-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="6f516-104">**Applies to**</span></span>
- [<span data-ttu-id="6f516-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="6f516-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="6f516-106">Abonnement 1 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="6f516-106">Microsoft Defender for Office 365 plan 1</span></span>](office-365-atp.md)
- <span data-ttu-id="6f516-107">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="6f516-107">SharePoint Online</span></span> 

 <span data-ttu-id="6f516-108">**Overzicht**: meer informatie over de toepassingen voor geïsoleerde SharePoint Online-teamsites.</span><span class="sxs-lookup"><span data-stu-id="6f516-108">**Summary:** Learn about the uses for isolated SharePoint Online team sites.</span></span>

<span data-ttu-id="6f516-109">Met SharePoint Online-teamsites kunt u snel en gemakkelijk een ruimte creëren om samen te werken.</span><span class="sxs-lookup"><span data-stu-id="6f516-109">SharePoint Online team sites are an easy way to quickly create a space for collaboration.</span></span> <span data-ttu-id="6f516-110">Gebruikers kunnen samenwerken aan notities, documenten, artikelen, een agenda en andere informatiebronnen in Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="6f516-110">Users can work together on notes, documents, articles, a calendar, and other resources in Microsoft Office 365.</span></span> <span data-ttu-id="6f516-111">SharePoint Online-teamsites zijn gebaseerd op een Microsoft 365-groep en beschikken over een vereenvoudigd beheermodel om een open samenwerking met een privéset groepsleden of de hele organisatie mogelijk te maken.</span><span class="sxs-lookup"><span data-stu-id="6f516-111">SharePoint Online team sites are based on a Microsoft 365 group and have a simplified administration model to allow open collaboration with a private set of group members or the entire organization.</span></span> <span data-ttu-id="6f516-112">Met een standaard SharePoint Online-teamsite kunnen leden van de Microsoft 365-groep andere gebruikers uitnodigen en instellingen voor machtigingen beheren.</span><span class="sxs-lookup"><span data-stu-id="6f516-112">A default SharePoint Online team site allows members of the Microsoft 365 group to invite other users and control permissions settings.</span></span>

<span data-ttu-id="6f516-113">Soms hebt u echter toegang tot een site nodig waarvoor groepslidmaatschap en SharePoint Online-machtigingsniveaus die worden beheerd door SharePoint-beheerders, nodig zijn.</span><span class="sxs-lookup"><span data-stu-id="6f516-113">However, you'll sometimes need site access to be controlled by group memberships, and SharePoint Online permission levels managed by SharePoint administrators.</span></span> <span data-ttu-id="6f516-114">Dit wordt een geïsoleerde site genoemd. De site is alleen beschikbaar voor de groep gebruikers die samenwerken, de inhoud van de site bekijken of de site beheren.</span><span class="sxs-lookup"><span data-stu-id="6f516-114">We call this an isolated site, which is isolated to the set of users that are either collaborating, viewing its contents, or administering the site.</span></span> <span data-ttu-id="6f516-115">Mogelijk hebt u een geïsoleerde site nodig voor het volgende:</span><span class="sxs-lookup"><span data-stu-id="6f516-115">You might need an isolated site for the following:</span></span>

- <span data-ttu-id="6f516-116">Een geheim project binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="6f516-116">A secret project within your organization.</span></span>

- <span data-ttu-id="6f516-117">De locatie voor zeer gevoelige of waardevolle intellectuele eigendommen van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="6f516-117">The location for highly-sensitive or valuable intellectual property for your organization.</span></span>

- <span data-ttu-id="6f516-118">De bronnen voor een juridische actie van uw organisatie of dat waarop het betrekking heeft.</span><span class="sxs-lookup"><span data-stu-id="6f516-118">The resources for a legal action taken by your organization or that to which it is being subjected.</span></span>

- <span data-ttu-id="6f516-119">Als u een abonnement op Microsoft 365 wilt delen tussen meerdere organisaties die elkaar overlappen maar voor het grootste deel als afzonderlijke bedrijfsentiteiten bestaan.</span><span class="sxs-lookup"><span data-stu-id="6f516-119">To share a Microsoft 365 subscription between multiple organizations that have some overlap, but for the most part exist as separate business entities.</span></span>

<span data-ttu-id="6f516-120">Hier volgen de vereisten voor een geïsoleerde site:</span><span class="sxs-lookup"><span data-stu-id="6f516-120">Here are the requirements of an isolated site:</span></span>

- <span data-ttu-id="6f516-121">Alleen beheerders van SharePoint Online kunnen sitebeheer uitvoeren, zoals groepslidmaatschap voor toegang tot de site en configuratie van aangepaste machtigingen.</span><span class="sxs-lookup"><span data-stu-id="6f516-121">Only SharePoint Online administrators can perform site administration, which includes group membership for access to the site and configuring custom permissions.</span></span>

- <span data-ttu-id="6f516-122">Leden van de site kunnen geen andere leden voor de teamsite uitnodigen.</span><span class="sxs-lookup"><span data-stu-id="6f516-122">Members of the site cannot invite other members to the team site.</span></span>

- <span data-ttu-id="6f516-123">Gebruikers die geen lid zijn van de geïsoleerde site, kunnen geen toegang tot de site aanvragen.</span><span class="sxs-lookup"><span data-stu-id="6f516-123">Users who are not members of the isolated site cannot request access to the site.</span></span> <span data-ttu-id="6f516-124">Zij krijgen het foutbericht 'Toegang geweigerd' te zien als ze toegang proberen te krijgen tot een URL die is gekoppeld aan de site.</span><span class="sxs-lookup"><span data-stu-id="6f516-124">They will receive an access denied web page when they attempt to access any URL associated with the site.</span></span>

<span data-ttu-id="6f516-125">Het nadeel van het gecentraliseerde toegangsbeheer en de aangepaste machtigingen door SharePoint Online-beheerders, is dat de site geïsoleerd blijft.</span><span class="sxs-lookup"><span data-stu-id="6f516-125">The tradeoff of requiring centralized access control and custom permissions by SharePoint Online administrators is that the site remains isolated over time.</span></span> <span data-ttu-id="6f516-126">Zo kunnen huidige leden geen andere personen uitnodigen (of dit nu opzettelijk of per ongeluk gebeurt) of aangepaste machtigingen configureren voor andere gebruikers in het Microsoft 365-abonnement die geen lid van de site zouden moeten zijn.</span><span class="sxs-lookup"><span data-stu-id="6f516-126">For example, current members cannot, either intentionally or accidentally, invite or configure custom permissions for other users within the Microsoft 365 subscription who should not be members of the site.</span></span>

<span data-ttu-id="6f516-127">Een geïsoleerde site kan worden gebruikt in combinatie met andere functies, zoals:</span><span class="sxs-lookup"><span data-stu-id="6f516-127">An isolated site can be used with other features, such as:</span></span>

- <span data-ttu-id="6f516-128">Information Rights Management om ervoor te zorgen dat de bronnen op de site versleuteld blijven, zelfs als ze lokaal worden gedownload en geüpload naar een andere site die voor de hele organisatie beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="6f516-128">Information Rights Management to ensure that the resources on the site remain encrypted, even if they are downloaded locally and uploaded to another site that is available to the entire organization.</span></span>

- <span data-ttu-id="6f516-129">Preventie van gegevensverlies om te voorkomen dat gebruikers de bronnen van de site, zoals bestanden, verzenden in een e-mail.</span><span class="sxs-lookup"><span data-stu-id="6f516-129">Data loss prevention to prevent users from sending the resources of the site, such as files, in email.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6f516-130">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="6f516-130">Next steps</span></span>

<span data-ttu-id="6f516-131">Als u een geïsoleerde SharePoint Online-teamsite wilt uitproberen in een proefabonnement, raadpleegt u de stapsgewijze instructies in [de documentatie over een omgeving voor ontwikkelen/testen voor een SharePoint Online-teamsite](isolated-sharepoint-online-team-site-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="6f516-131">To try out an isolated SharePoint Online team site in a trial subscription, see the step-by-step instructions in [Isolated SharePoint Online team site dev/test environment](isolated-sharepoint-online-team-site-dev-test-environment.md).</span></span>

<span data-ttu-id="6f516-132">Als u klaar bent om een geïsoleerde SharePoint Online-teamsite in productie te implementeren, raadpleegt u de stapsgewijze overwegingen voor het ontwerpen in [Een geïsoleerde SharePoint Online-teamsite ontwerpen](design-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="6f516-132">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="6f516-133">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="6f516-133">Related topics</span></span>

[<span data-ttu-id="6f516-134">Een geïsoleerde SharePoint Online-teamsite ontwerpen</span><span class="sxs-lookup"><span data-stu-id="6f516-134">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="6f516-135">Een geïsoleerde SharePoint Online-teamsite beheren</span><span class="sxs-lookup"><span data-stu-id="6f516-135">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="6f516-136">Een geïsoleerde SharePoint Online-teamsite implementeren</span><span class="sxs-lookup"><span data-stu-id="6f516-136">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)
