---
title: Azure AD-identiteitsbeveiliging voor uw Microsoft 365 voor Enterprise testomgeving
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Azure AD Identity Protection configureren en de huidige accounts in uw Microsoft 365 voor Enterprise testomgeving analyseren.
ms.openlocfilehash: bd1e7560e978b13d24e9e93a99a2567adca95c75
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694988"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="0a21e-103">Azure AD-identiteitsbeveiliging voor uw Microsoft 365 voor Enterprise testomgeving</span><span class="sxs-lookup"><span data-stu-id="0a21e-103">Azure AD Identity Protection for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="0a21e-104">*Deze test lab-gids kan alleen worden gebruikt voor Microsoft 365 voor Enterprise test omgevingen.*</span><span class="sxs-lookup"><span data-stu-id="0a21e-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="0a21e-105">Met identiteitsbeveiliging van Azure Active Directory (Azure AD) kunt u mogelijke problemen detecteren die van invloed zijn op de identiteiten van uw organisatie, automatische antwoorden configureren en incidenten onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="0a21e-105">Azure Active Directory (Azure AD) Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="0a21e-106">In dit artikel wordt uitgelegd hoe u Azure AD-identiteitsbeveiliging kunt gebruiken om de analyse van uw test omgevings accounts te bekijken.</span><span class="sxs-lookup"><span data-stu-id="0a21e-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="0a21e-107">Er zijn twee fasen om Azure AD-identiteitsbeveiliging in te stellen in uw Microsoft 365 voor Enterprise testomgeving:</span><span class="sxs-lookup"><span data-stu-id="0a21e-107">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 for enterprise test environment:</span></span>

1. <span data-ttu-id="0a21e-108">Maak de testomgeving Microsoft 365 for Enterprise.</span><span class="sxs-lookup"><span data-stu-id="0a21e-108">Create the Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="0a21e-109">Azure Active Directory-identiteitsbeveiliging gebruiken.</span><span class="sxs-lookup"><span data-stu-id="0a21e-109">Use Azure AD Identity Protection.</span></span>

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="0a21e-111">Klik op [Hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de stack van Microsoft 365 voor Enterprise-testlabrichtlijnen.</span><span class="sxs-lookup"><span data-stu-id="0a21e-111">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="0a21e-112">Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken</span><span class="sxs-lookup"><span data-stu-id="0a21e-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="0a21e-113">Als u alleen de bescherming van Azure AD-identiteit op een lichte manier wilt testen aan de minimumvereisten, volgt u de instructies in de [Lightweight Base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="0a21e-113">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="0a21e-114">Als u Azure AD-identiteitsbeveiliging wilt testen in een gesimuleerde onderneming, volgt u de instructies in de [Pass Through-verificatie](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="0a21e-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="0a21e-115">Voor Azure Active Directory-identiteitsbeveiliging is geen gesimuleerde Enterprise-testomgeving vereist, dat een gesimuleerd intranet bevat dat verbonden is met internet en adreslijstsynchronisatie van een Active Directory Domain Services (AD DS)-forest.</span><span class="sxs-lookup"><span data-stu-id="0a21e-115">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="0a21e-116">U kunt dit als optie gebruiken, zodat u de beveiliging van Azure AD-identiteit kunt testen en een proef kunt uitvoeren in een omgeving die een typische organisatie voorstelt.</span><span class="sxs-lookup"><span data-stu-id="0a21e-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="0a21e-117">Fase 2: Azure AD-identiteitsbeveiliging gebruiken</span><span class="sxs-lookup"><span data-stu-id="0a21e-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="0a21e-118">Open een privé-exemplaar van uw browser en meld u aan bij de Azure-Portal [https://portal.azure.com](https://portal.azure.com) met het account van de globale beheerder van uw Microsoft 365 voor Enterprise-testomgeving.</span><span class="sxs-lookup"><span data-stu-id="0a21e-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="0a21e-119">Typ in het vak Zoeken in de Azure-Portal de tekst **identiteitsbeveiliging** en klik vervolgens op **Azure AD Identity Protection**.</span><span class="sxs-lookup"><span data-stu-id="0a21e-119">In the Azure portal, type **identity protection** in the search box, and then click **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="0a21e-120">Klik in de blad **identiteitsbeveiliging-overzicht** op elk rapport om te zien wat ze rapporteren.</span><span class="sxs-lookup"><span data-stu-id="0a21e-120">In the **Identity Protection - Overview** blade, click on each of the reports to see what they are reporting.</span></span>
4. <span data-ttu-id="0a21e-121">Klik onder **waarschuwen**op **gebruikers met risico gedetecteerde meldingen**.</span><span class="sxs-lookup"><span data-stu-id="0a21e-121">Under **Notify**, click **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="0a21e-122">Selecteer in het deelvenster **gebruikers van risico gedetecteerde signalen** de optie **normaal**.</span><span class="sxs-lookup"><span data-stu-id="0a21e-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="0a21e-123">Voor **e-mailberichten worden de volgende gebruikers verzonden**: Klik op **opgenomen** en controleer of uw globale beheerdersaccount in de lijst met geselecteerde leden staat.</span><span class="sxs-lookup"><span data-stu-id="0a21e-123">For **Emails are sent to the following users**, click **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="0a21e-124">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="0a21e-124">Click **Save**.</span></span>

<span data-ttu-id="0a21e-125">Klik op de verschillende beleidsregels onder **beveiligen** om te zien hoe u deze kunt configureren.</span><span class="sxs-lookup"><span data-stu-id="0a21e-125">Click through the different policies under **Protect** to see how to configure them.</span></span> <span data-ttu-id="0a21e-126">Als u een beleid maakt en activeert, moet u ervoor zorgen dat de toegang niet te veel voorwaarden blokkeert, of dat u zich mogelijk niet kunt aanmelden, ook niet als globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="0a21e-126">If you create and activate a policy, make sure it is not blocking access for too wide a scope of conditions, or you might not be able to sign in, even as the global admin.</span></span>

<span data-ttu-id="0a21e-127">Zie [risico gebeurtenissen simuleren](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)voor verdere testen en experimenteren.</span><span class="sxs-lookup"><span data-stu-id="0a21e-127">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

## <a name="next-step"></a><span data-ttu-id="0a21e-128">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="0a21e-128">Next step</span></span>

<span data-ttu-id="0a21e-129">Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="0a21e-129">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="0a21e-130">Zie ook</span><span class="sxs-lookup"><span data-stu-id="0a21e-130">See also</span></span>

[<span data-ttu-id="0a21e-131">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="0a21e-131">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="0a21e-132">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="0a21e-132">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="0a21e-133">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="0a21e-133">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="0a21e-134">Documentatie voor Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="0a21e-134">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
