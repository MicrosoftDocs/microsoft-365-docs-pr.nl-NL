---
title: Azure AD Identity Protection voor uw Microsoft 365 voor bedrijfstestomgeving
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
description: Configureer Azure AD Identity Protection en analyseer de huidige accounts in uw Microsoft 365 voor bedrijfstestomgeving.
ms.openlocfilehash: 0cb0acf3faee13676573b04178bd6b4d3d36da4d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905342"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="e4634-103">Azure AD Identity Protection voor uw Microsoft 365 voor bedrijfstestomgeving</span><span class="sxs-lookup"><span data-stu-id="e4634-103">Azure AD Identity Protection for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="e4634-104">*Deze testlaborator kan alleen worden gebruikt Microsoft 365 voor bedrijfstestomgevingen.*</span><span class="sxs-lookup"><span data-stu-id="e4634-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="e4634-105">U kunt Azure Active Directory (Azure AD) Identity Protection gebruiken om mogelijke beveiligingsproblemen op te sporen die van invloed zijn op de identiteiten van uw organisatie, geautomatiseerde antwoorden configureren en incidenten onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="e4634-105">You can use Azure Active Directory (Azure AD) Identity Protection to detect potential vulnerabilities that affect your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="e4634-106">In dit artikel wordt beschreven hoe u Azure AD Identity Protection gebruikt om de analyse van uw testomgevingaccounts weer te geven.</span><span class="sxs-lookup"><span data-stu-id="e4634-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="e4634-107">Het instellen van Azure AD Identity Protection in uw Microsoft 365 voor ondernemingstestomgeving omvat twee fasen:</span><span class="sxs-lookup"><span data-stu-id="e4634-107">Setting up Azure AD Identity Protection in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="e4634-108">Fase 1: uw Microsoft 365 voor bedrijfstestomgeving</span><span class="sxs-lookup"><span data-stu-id="e4634-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="e4634-109">Fase 2: Azure AD Identity Protection gebruiken</span><span class="sxs-lookup"><span data-stu-id="e4634-109">Phase 2: Use Azure AD Identity Protection</span></span>](#phase-2-use-azure-ad-identity-protection)

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="e4634-111">Voor een visuele kaart van alle artikelen in de Microsoft 365 voor enterprise Test Lab Guide stack, gaat u naar Microsoft 365 voor [enterprise Test Lab Guide Stack.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="e4634-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="e4634-112">Fase 1: uw Microsoft 365 voor bedrijfstestomgeving</span><span class="sxs-lookup"><span data-stu-id="e4634-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="e4634-113">Als u Azure AD Identity Protection alleen op een lichtgewicht manier wilt testen met de minimumvereisten, volgt u de instructies in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="e4634-113">If you want to only test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="e4634-114">Als u Azure AD Identity Protection wilt testen in een gesimuleerde onderneming, volgt u de instructies in [Pass-through-verificatie.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="e4634-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e4634-115">Voor het testen van Azure AD Identity Protection is geen gesimuleerde bedrijfstestomgeving vereist, waaronder een gesimuleerd intranet dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS-forest (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="e4634-115">Testing Azure AD Identity Protection doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="e4634-116">Het is hier beschikbaar als een optie, zodat u Azure AD Identity Protection kunt testen en erop kunt experimenteren in een omgeving die een normale organisatie vertegenwoordigt.</span><span class="sxs-lookup"><span data-stu-id="e4634-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="e4634-117">Fase 2: Azure AD Identity Protection gebruiken</span><span class="sxs-lookup"><span data-stu-id="e4634-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="e4634-118">Open een privé-exemplaar van uw browser en meld u aan bij de Azure-portal bij met het globale beheerdersaccount van uw Microsoft 365 [https://portal.azure.com](https://portal.azure.com) voor ondernemingstestomgeving.</span><span class="sxs-lookup"><span data-stu-id="e4634-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="e4634-119">Typ in de Azure-portal **identiteitsbeveiliging** in het zoekvak en selecteer **vervolgens Azure AD Identity Protection**.</span><span class="sxs-lookup"><span data-stu-id="e4634-119">In the Azure portal, type **identity protection** in the search box, and then select **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="e4634-120">Selecteer in **het blad Identiteitsbeveiliging - Overzicht** elk rapport om te zien wat het rapport rapporteert.</span><span class="sxs-lookup"><span data-stu-id="e4634-120">In the **Identity Protection - Overview** blade, select each report to see what it's reporting.</span></span>
4. <span data-ttu-id="e4634-121">Selecteer **onder Aanmelden** de optie Gebruikers met risico **gedetecteerde waarschuwingen.**</span><span class="sxs-lookup"><span data-stu-id="e4634-121">Under **Notify**, select **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="e4634-122">Selecteer in **het deelvenster Gebruikers met risico gedetecteerde waarschuwingen** de optie **Medium**.</span><span class="sxs-lookup"><span data-stu-id="e4634-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="e4634-123">Als **e-mailberichten naar de volgende gebruikers worden verzonden,** **selecteert** u Opgenomen en controleert u of uw globale beheerdersaccount in de lijst met geselecteerde leden staat.</span><span class="sxs-lookup"><span data-stu-id="e4634-123">For **Emails are sent to the following users**, select **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="e4634-124">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="e4634-124">Select **Save**.</span></span>

<span data-ttu-id="e4634-125">Selecteer **onder** Beveiligen verschillende agenten om te zien hoe u deze configureert.</span><span class="sxs-lookup"><span data-stu-id="e4634-125">Under **Protect**, select various polices to see how to configure them.</span></span> <span data-ttu-id="e4634-126">Als u een beleid maakt en activeert, moet u ervoor zorgen dat de toegang niet voor alle gebruikers wordt geblokkeerd of dat u zich mogelijk niet kunt aanmelden.</span><span class="sxs-lookup"><span data-stu-id="e4634-126">If you create and activate a policy, make sure that it's not blocking access for all users, or you might not be able to sign in.</span></span> <span data-ttu-id="e4634-127">U kunt dit voorkomen door specifieke gebruikersaccounts uit te sluiten, zoals globale beheerders.</span><span class="sxs-lookup"><span data-stu-id="e4634-127">To prevent this, exclude specific user accounts, such as global admins.</span></span>

<span data-ttu-id="e4634-128">Zie Risicogebeurtenissen simuleren voor meer testen [en experimenteren.](/azure/active-directory/active-directory-identityprotection-playbook)</span><span class="sxs-lookup"><span data-stu-id="e4634-128">For further testing and experimentation, see [Simulating risk events](/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

## <a name="next-step"></a><span data-ttu-id="e4634-129">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="e4634-129">Next step</span></span>

<span data-ttu-id="e4634-130">Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="e4634-130">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="e4634-131">Zie ook</span><span class="sxs-lookup"><span data-stu-id="e4634-131">See also</span></span>

[<span data-ttu-id="e4634-132">Routekaart voor identiteit</span><span class="sxs-lookup"><span data-stu-id="e4634-132">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="e4634-133">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="e4634-133">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="e4634-134">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="e4634-134">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="e4634-135">Microsoft 365 enterprise-documentatie</span><span class="sxs-lookup"><span data-stu-id="e4634-135">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)