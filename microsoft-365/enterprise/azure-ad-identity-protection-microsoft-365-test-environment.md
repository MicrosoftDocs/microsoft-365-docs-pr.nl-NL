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
ms.openlocfilehash: 162a6504fb7541874798f5e795bd2ecd590b5035
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487706"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="982b7-103">Azure AD-identiteitsbeveiliging voor uw Microsoft 365 voor Enterprise testomgeving</span><span class="sxs-lookup"><span data-stu-id="982b7-103">Azure AD Identity Protection for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="982b7-104">*Deze test lab-gids kan alleen worden gebruikt voor Microsoft 365 voor Enterprise test omgevingen.*</span><span class="sxs-lookup"><span data-stu-id="982b7-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="982b7-105">U kunt Azure Active Directory (Azure AD)-identiteitsbeveiliging gebruiken om potentiële beveiligingsproblemen op te sporen die van invloed zijn op de identiteiten van uw organisatie, automatische antwoorden configureren en gebeurtenissen onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="982b7-105">You can use Azure Active Directory (Azure AD) Identity Protection to detect potential vulnerabilities that affect your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="982b7-106">In dit artikel wordt uitgelegd hoe u Azure AD-identiteitsbeveiliging kunt gebruiken om de analyse van uw test omgevings accounts te bekijken.</span><span class="sxs-lookup"><span data-stu-id="982b7-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="982b7-107">Azure AD-identiteitsbeveiliging instellen voor de testomgeving Microsoft 365 voor Enterprise omvat twee fasen:</span><span class="sxs-lookup"><span data-stu-id="982b7-107">Setting up Azure AD Identity Protection in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="982b7-108">Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken</span><span class="sxs-lookup"><span data-stu-id="982b7-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="982b7-109">Fase 2: Azure AD-identiteitsbeveiliging gebruiken</span><span class="sxs-lookup"><span data-stu-id="982b7-109">Phase 2: Use Azure AD Identity Protection</span></span>](#phase-2-use-azure-ad-identity-protection)

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="982b7-111">Ga naar [Microsoft 365 for Enterprise test lab Guide](../downloads/Microsoft365EnterpriseTLGStack.pdf)van een visuele kaart voor alle artikelen in de stack microsoft 365 for Enterprise test lab Guide.</span><span class="sxs-lookup"><span data-stu-id="982b7-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="982b7-112">Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken</span><span class="sxs-lookup"><span data-stu-id="982b7-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="982b7-113">Als u de beveiliging van Azure AD op een lichte manier wilt testen aan de minimumvereisten, volgt u de instructies in de [basisconfiguratie](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="982b7-113">If you want to only test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="982b7-114">Als u Azure AD-identiteitsbeveiliging wilt testen in een gesimuleerde onderneming, volgt u de instructies in de [Pass Through-verificatie](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="982b7-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="982b7-115">Voor het testen van Azure Active Directory-identiteitsbeveiliging is de gesimuleerde Enterprise testomgeving niet vereist, waaronder een gesimuleerd intranet dat verbonden is met internet en adreslijstsynchronisatie van een Active Directory Domain Services (AD DS)-forest.</span><span class="sxs-lookup"><span data-stu-id="982b7-115">Testing Azure AD Identity Protection doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="982b7-116">U kunt dit als optie gebruiken, zodat u de beveiliging van Azure AD-identiteit kunt testen en een proef kunt uitvoeren in een omgeving die een typische organisatie voorstelt.</span><span class="sxs-lookup"><span data-stu-id="982b7-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="982b7-117">Fase 2: Azure AD-identiteitsbeveiliging gebruiken</span><span class="sxs-lookup"><span data-stu-id="982b7-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="982b7-118">Open een privé-exemplaar van uw browser en meld u aan bij de Azure-Portal [https://portal.azure.com](https://portal.azure.com) met het account van de globale beheerder van uw Microsoft 365 voor Enterprise-testomgeving.</span><span class="sxs-lookup"><span data-stu-id="982b7-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="982b7-119">Typ in het vak Zoeken van de Azure-Portal de optie **identiteitsbeveiliging** en selecteer **Azure AD-identiteitsbeveiliging**.</span><span class="sxs-lookup"><span data-stu-id="982b7-119">In the Azure portal, type **identity protection** in the search box, and then select **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="982b7-120">Selecteer in de blad **identiteitsbeveiliging-overzicht** de optie elk rapport om te zien wat er wordt gerapporteerd.</span><span class="sxs-lookup"><span data-stu-id="982b7-120">In the **Identity Protection - Overview** blade, select each report to see what it's reporting.</span></span>
4. <span data-ttu-id="982b7-121">Selecteer onder **waarschuwen** **gebruikers bij risico gedetecteerde meldingen**.</span><span class="sxs-lookup"><span data-stu-id="982b7-121">Under **Notify**, select **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="982b7-122">Selecteer in het deelvenster **gebruikers van risico gedetecteerde signalen** de optie **normaal**.</span><span class="sxs-lookup"><span data-stu-id="982b7-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="982b7-123">Voor **e-mailberichten worden de volgende gebruikers verstuurd**, selecteert u **inbegrepen** en controleert u of uw globale beheerdersaccount in de lijst met geselecteerde leden staat.</span><span class="sxs-lookup"><span data-stu-id="982b7-123">For **Emails are sent to the following users**, select **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="982b7-124">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="982b7-124">Select **Save**.</span></span>

<span data-ttu-id="982b7-125">Onder **beveiligen**selecteert u verschillende policies om te zien hoe ze ze kunnen configureren.</span><span class="sxs-lookup"><span data-stu-id="982b7-125">Under **Protect**, select various polices to see how to configure them.</span></span> <span data-ttu-id="982b7-126">Als u een beleid maakt en activeert, moet u ervoor zorgen dat u de toegang voor alle gebruikers niet blokkeert of dat u zich mogelijk niet kunt aanmelden.</span><span class="sxs-lookup"><span data-stu-id="982b7-126">If you create and activate a policy, make sure that it's not blocking access for all users, or you might not be able to sign in.</span></span> <span data-ttu-id="982b7-127">U kunt dit voorkomen door specifieke gebruikersaccounts, zoals globale beheerders, uit te sluiten.</span><span class="sxs-lookup"><span data-stu-id="982b7-127">To prevent this, exclude specific user accounts, such as global admins.</span></span>

<span data-ttu-id="982b7-128">Zie [risico gebeurtenissen simuleren](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)voor verdere testen en experimenteren.</span><span class="sxs-lookup"><span data-stu-id="982b7-128">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

## <a name="next-step"></a><span data-ttu-id="982b7-129">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="982b7-129">Next step</span></span>

<span data-ttu-id="982b7-130">Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="982b7-130">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="982b7-131">Zie ook</span><span class="sxs-lookup"><span data-stu-id="982b7-131">See also</span></span>

[<span data-ttu-id="982b7-132">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="982b7-132">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="982b7-133">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="982b7-133">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="982b7-134">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="982b7-134">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="982b7-135">Documentatie voor Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="982b7-135">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
