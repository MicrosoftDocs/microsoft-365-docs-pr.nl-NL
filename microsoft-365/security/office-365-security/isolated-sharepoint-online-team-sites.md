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
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 71250a04-fd2d-4c3c-a32b-b8a838b19a54
description: Meer informatie over geïsoleerde SharePoint Online-teamsites, zoals gebruik, vereisten en functies waarmee ze kunnen worden gebruikt.
ms.openlocfilehash: f88be4b16d7f3a65ba624f7bf4c490b0173883c8
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036702"
---
# <a name="isolated-sharepoint-online-team-sites"></a><span data-ttu-id="dc8cf-103">Geïsoleerde SharePoint Online-teamsites</span><span class="sxs-lookup"><span data-stu-id="dc8cf-103">Isolated SharePoint Online team sites</span></span>

 <span data-ttu-id="dc8cf-104">**Overzicht**: meer informatie over de toepassingen voor geïsoleerde SharePoint Online-teamsites.</span><span class="sxs-lookup"><span data-stu-id="dc8cf-104">**Summary:** Learn about the uses for isolated SharePoint Online team sites.</span></span>
  
<span data-ttu-id="dc8cf-105">Met SharePoint Online-teamsites kunt u snel een ruimte maken om samen te werken aan notities, documenten, artikelen, een agenda en andere bronnen in Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="dc8cf-105">SharePoint Online team sites are an easy way to quickly create a space for collaboration of notes, documents, articles, a calendar, and other resources in Microsoft Office 365.</span></span> <span data-ttu-id="dc8cf-106">SharePoint Online-teamsites zijn gebaseerd op een Microsoft 365-groep en beschikken over een vereenvoudigd beheermodel om een open samenwerking met een privéset groepsleden of de hele organisatie mogelijk te maken.</span><span class="sxs-lookup"><span data-stu-id="dc8cf-106">SharePoint Online team sites are based on an Microsoft 365 group and have a simplified administration model to allow open collaboration with a private set of group members or the entire organization.</span></span> <span data-ttu-id="dc8cf-107">Met een standaard SharePoint Online-teamsite kunnen leden van de Microsoft 365-groep andere gebruikers uitnodigen en instellingen voor machtigingen beheren.</span><span class="sxs-lookup"><span data-stu-id="dc8cf-107">A default SharePoint Online team site allows members of the Microsoft 365 group to invite other users and control permissions settings.</span></span>
  
<span data-ttu-id="dc8cf-108">In sommige gevallen wilt u echter voor samenwerking een SharePoint Online-teamsite maken waarbij de machtigingen van die site strak worden beheerd via het groepslidmaatschap en SharePoint Online-machtigingsniveaus die alleen worden beheerd door SharePoint-beheerders.</span><span class="sxs-lookup"><span data-stu-id="dc8cf-108">However, in some cases, you want to create a SharePoint Online team site for collaboration where the permissions of that site are more tightly controlled through group membership and SharePoint Online permission levels, which are only managed by SharePoint administrators.</span></span> <span data-ttu-id="dc8cf-109">Dit wordt een geïsoleerde site genoemd. De site is alleen beschikbaar voor de groep gebruikers die samenwerken, de inhoud van de site bekijken of de site beheren.</span><span class="sxs-lookup"><span data-stu-id="dc8cf-109">We call this an isolated site, which is isolated to the set of users that are either collaborating, viewing its contents, or administering the site.</span></span> <span data-ttu-id="dc8cf-110">Mogelijk hebt u een geïsoleerde site nodig voor het volgende:</span><span class="sxs-lookup"><span data-stu-id="dc8cf-110">You might need an isolated site for the following:</span></span>
  
- <span data-ttu-id="dc8cf-111">Een geheim project binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="dc8cf-111">A secret project within your organization.</span></span>
    
- <span data-ttu-id="dc8cf-112">De locatie voor zeer gevoelige of waardevolle intellectuele eigendommen van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="dc8cf-112">The location for highly-sensitive or valuable intellectual property for your organization.</span></span>
    
- <span data-ttu-id="dc8cf-113">De bronnen voor een juridische actie van uw organisatie of dat waarop het betrekking heeft.</span><span class="sxs-lookup"><span data-stu-id="dc8cf-113">The resources for a legal action taken by your organization or that to which it is being subjected.</span></span>
    
- <span data-ttu-id="dc8cf-114">Als u een abonnement op Microsoft 365 wilt delen tussen meerdere organisaties die elkaar overlappen maar voor het grootste deel als afzonderlijke bedrijfsentiteiten bestaan.</span><span class="sxs-lookup"><span data-stu-id="dc8cf-114">To share a Microsoft 365 subscription between multiple organizations that have some overlap, but for the most part exist as separate business entities.</span></span>
    
<span data-ttu-id="dc8cf-115">Hier volgen de vereisten voor een geïsoleerde site:</span><span class="sxs-lookup"><span data-stu-id="dc8cf-115">Here are the requirements of an isolated site:</span></span>
  
- <span data-ttu-id="dc8cf-116">Alleen beheerders van SharePoint Online kunnen sitebeheer uitvoeren, zoals groepslidmaatschap voor toegang tot de site en configuratie van aangepaste machtigingen.</span><span class="sxs-lookup"><span data-stu-id="dc8cf-116">Only SharePoint Online administrators can perform site administration, which includes group membership for access to the site and configuring custom permissions.</span></span>
    
- <span data-ttu-id="dc8cf-117">Leden van de site kunnen geen andere leden voor de teamsite uitnodigen.</span><span class="sxs-lookup"><span data-stu-id="dc8cf-117">Members of the site cannot invite other members to the team site.</span></span>
    
- <span data-ttu-id="dc8cf-118">Gebruikers die geen lid zijn van de geïsoleerde site, kunnen geen toegang tot de site aanvragen.</span><span class="sxs-lookup"><span data-stu-id="dc8cf-118">Users who are not members of the isolated site cannot request access to the site.</span></span> <span data-ttu-id="dc8cf-119">Zij krijgen het foutbericht 'Toegang geweigerd' te zien als ze toegang proberen te krijgen tot een URL die is gekoppeld aan de site.</span><span class="sxs-lookup"><span data-stu-id="dc8cf-119">They will receive an access denied web page when they attempt to access any URL associated with the site.</span></span>
    
<span data-ttu-id="dc8cf-120">Het nadeel van het gecentraliseerde toegangsbeheer en de aangepaste machtigingen door SharePoint Online-beheerders, is dat de site geïsoleerd blijft.</span><span class="sxs-lookup"><span data-stu-id="dc8cf-120">The tradeoff of requiring centralized access control and custom permissions by SharePoint Online administrators is that the site remains isolated over time.</span></span> <span data-ttu-id="dc8cf-121">Zo kunnen huidige leden geen andere personen uitnodigen (of dit nu opzettelijk of per ongeluk gebeurt) of aangepaste machtigingen configureren voor andere gebruikers in het Microsoft 365-abonnement die geen lid van de site zouden moeten zijn.</span><span class="sxs-lookup"><span data-stu-id="dc8cf-121">For example, current members cannot, either intentionally or accidentally, invite or configure custom permissions for other users within the Microsoft 365 subscription who should not be members of the site.</span></span>
  
<span data-ttu-id="dc8cf-122">Een geïsoleerde site kan worden gebruikt in combinatie met andere functies, zoals:</span><span class="sxs-lookup"><span data-stu-id="dc8cf-122">An isolated site can be used with other features, such as:</span></span>
  
- <span data-ttu-id="dc8cf-123">Information Rights Management om ervoor te zorgen dat de bronnen op de site versleuteld blijven, zelfs als ze lokaal worden gedownload en geüpload naar een andere site die voor de hele organisatie beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="dc8cf-123">Information Rights Management to ensure that the resources on the site remain encrypted, even if they are downloaded locally and uploaded to another site that is available to the entire organization.</span></span>
    
- <span data-ttu-id="dc8cf-124">Preventie van gegevensverlies om te voorkomen dat gebruikers de bronnen van de site, zoals bestanden, verzenden in een e-mail.</span><span class="sxs-lookup"><span data-stu-id="dc8cf-124">Data loss prevention to prevent users from sending the resources of the site, such as files, in email.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="dc8cf-125">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="dc8cf-125">Next steps</span></span>

<span data-ttu-id="dc8cf-126">Als u een geïsoleerde SharePoint Online-teamsite wilt uitproberen in een proefabonnement, raadpleegt u de stapsgewijze instructies in [de documentatie over een omgeving voor ontwikkelen/testen voor een SharePoint Online-teamsite](isolated-sharepoint-online-team-site-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="dc8cf-126">To try out an isolated SharePoint Online team site in a trial subscription, see the step-by-step instructions in [Isolated SharePoint Online team site dev/test environment](isolated-sharepoint-online-team-site-dev-test-environment.md).</span></span>
  
<span data-ttu-id="dc8cf-127">Als u klaar bent om een geïsoleerde SharePoint Online-teamsite in productie te implementeren, raadpleegt u de stapsgewijze overwegingen voor het ontwerpen in [Een geïsoleerde SharePoint Online-teamsite ontwerpen](design-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="dc8cf-127">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dc8cf-128">Zie ook</span><span class="sxs-lookup"><span data-stu-id="dc8cf-128">See Also</span></span>

[<span data-ttu-id="dc8cf-129">Een geïsoleerde SharePoint Online-teamsite ontwerpen</span><span class="sxs-lookup"><span data-stu-id="dc8cf-129">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)
  
[<span data-ttu-id="dc8cf-130">Een geïsoleerde SharePoint Online-teamsite beheren</span><span class="sxs-lookup"><span data-stu-id="dc8cf-130">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="dc8cf-131">Een geïsoleerde SharePoint Online-teamsite implementeren</span><span class="sxs-lookup"><span data-stu-id="dc8cf-131">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)


