---
title: Azure AD-identiteitsbeveiliging voor uw Microsoft 365 Enterprise-testomgeving
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
description: Configureer Azure AD-identiteitsbeveiliging en analyseer de huidige accounts in uw Microsoft 365 Enterprise-testomgeving.
ms.openlocfilehash: 3f3740e42c7ec909f44a3c761dfc743359b3f030
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42806079"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="cfec5-103">Azure AD-identiteitsbeveiliging voor uw Microsoft 365 Enterprise-testomgeving</span><span class="sxs-lookup"><span data-stu-id="cfec5-103">Azure AD Identity Protection for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="cfec5-104">*Deze Test Lab Guide kan alleen worden gebruikt voor Microsoft 365 Enterprise-testomgevingen.*</span><span class="sxs-lookup"><span data-stu-id="cfec5-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="cfec5-105">Met Azure Active Directory (Azure AD) Identity Protection u mogelijke kwetsbaarheden detecteren die de identiteit van uw organisatie beïnvloeden, geautomatiseerde antwoorden configureren en incidenten onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="cfec5-105">Azure Active Directory (Azure AD) Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="cfec5-106">In dit artikel wordt beschreven hoe u Azure AD-identiteitsbeveiliging gebruiken om de analyse van uw testomgevingsaccounts weer te geven.</span><span class="sxs-lookup"><span data-stu-id="cfec5-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="cfec5-107">Er zijn twee fasen om Azure AD-identiteitsbeveiliging in te stellen in uw Microsoft 365 Enterprise-testomgeving:</span><span class="sxs-lookup"><span data-stu-id="cfec5-107">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="cfec5-108">Maak de Microsoft 365 Enterprise-testomgeving.</span><span class="sxs-lookup"><span data-stu-id="cfec5-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="cfec5-109">Gebruik Azure AD-identiteitsbeveiliging.</span><span class="sxs-lookup"><span data-stu-id="cfec5-109">Use Azure AD Identity Protection.</span></span>

![Test Lab-hulplijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="cfec5-111">Klik [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de Microsoft 365 Enterprise Test Lab Guide stack.</span><span class="sxs-lookup"><span data-stu-id="cfec5-111">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="cfec5-112">Fase 1: Uw Microsoft 365 Enterprise-testomgeving uitbouwen</span><span class="sxs-lookup"><span data-stu-id="cfec5-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="cfec5-113">Als u Azure AD Identity Protection alleen op een lichtgewicht manier wilt testen met de minimumvereisten, volgt u de instructies in [lichtgewicht basisconfiguratie](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="cfec5-113">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="cfec5-114">Als u Azure AD-identiteitsbeveiliging wilt testen in een gesimuleerde onderneming, volgt u de instructies in [Pass-through-verificatie](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="cfec5-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="cfec5-115">Het testen van Azure AD-identiteitsbeveiliging vereist niet de gesimuleerde bedrijfstestomgeving, die een gesimuleerd intranet bevat dat is verbonden met internet- en adreslijstsynchronisatie voor een AD DS-forest (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="cfec5-115">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="cfec5-116">Het wordt hier als optie geleverd, zodat u Azure AD-identiteitsbescherming testen en ermee experimenteren in een omgeving die een typische organisatie vertegenwoordigt.</span><span class="sxs-lookup"><span data-stu-id="cfec5-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="cfec5-117">Fase 2: Azure AD-identiteitsbeveiliging gebruiken</span><span class="sxs-lookup"><span data-stu-id="cfec5-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="cfec5-118">Open een privé-exemplaar van uw browser en [https://portal.azure.com](https://portal.azure.com) meld u aan bij de Azure-portal met het globale beheerdersaccount van uw Microsoft 365 Enterprise-testomgeving.</span><span class="sxs-lookup"><span data-stu-id="cfec5-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="cfec5-119">Typ in de Azure-portal **identiteitsbeveiliging** in het zoekvak en klik op **Azure AD-identiteitsbeveiliging**.</span><span class="sxs-lookup"><span data-stu-id="cfec5-119">In the Azure portal, type **identity protection** in the search box, and then click **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="cfec5-120">Klik in het **blade voor identiteitsbescherming - op** elk van de rapporten om te zien wat ze rapporteren.</span><span class="sxs-lookup"><span data-stu-id="cfec5-120">In the **Identity Protection - Overview** blade, click on each of the reports to see what they are reporting.</span></span>
4. <span data-ttu-id="cfec5-121">Klik onder **Aanmelden**op **Gebruikers met risico gedetecteerde waarschuwingen**.</span><span class="sxs-lookup"><span data-stu-id="cfec5-121">Under **Notify**, click **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="cfec5-122">Selecteer **Users at risk detected alerts** **Medium**.</span><span class="sxs-lookup"><span data-stu-id="cfec5-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="cfec5-123">Als **e-mails naar de volgende gebruikers worden verzonden,** klikt u op **Opgenomen** en controleert u of uw globale beheerdersaccount zich in de lijst met geselecteerde leden bevindt.</span><span class="sxs-lookup"><span data-stu-id="cfec5-123">For **Emails are sent to the following users**, click **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="cfec5-124">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="cfec5-124">Click **Save**.</span></span>

<span data-ttu-id="cfec5-125">Klik door het verschillende beleid onder **Beveiligen** om te zien hoe u ze configureert.</span><span class="sxs-lookup"><span data-stu-id="cfec5-125">Click through the different policies under **Protect** to see how to configure them.</span></span> <span data-ttu-id="cfec5-126">Als u een beleid maakt en activeert, moet u ervoor zorgen dat het de toegang niet blokkeert voor een te breed scala aan voorwaarden, of als u zich mogelijk niet aanmelden, zelfs niet als globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="cfec5-126">If you create and activate a policy, make sure it is not blocking access for too wide a scope of conditions, or you might not be able to sign in, even as the global admin.</span></span>

<span data-ttu-id="cfec5-127">Zie [Risicogebeurtenissen simuleren](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)voor verder onderzoek en experimenten.</span><span class="sxs-lookup"><span data-stu-id="cfec5-127">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

<span data-ttu-id="cfec5-128">Zie de stap [Beveiligen tegen het compromitteren van referenties](identity-secure-user-sign-ins.md#identity-ident-prot) in de identiteitsfase voor informatie en koppelingen om Azure AD-identiteitsbeveiliging in productie te implementeren.</span><span class="sxs-lookup"><span data-stu-id="cfec5-128">See the [Protect against credential compromise](identity-secure-user-sign-ins.md#identity-ident-prot) step in the Identity phase for information and links to deploy Azure AD Identity Protection in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="cfec5-129">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="cfec5-129">Next step</span></span>

<span data-ttu-id="cfec5-130">Ontdek extra [identiteitsfuncties](m365-enterprise-test-lab-guides.md#identity) en -mogelijkheden in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="cfec5-130">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="cfec5-131">Zie ook</span><span class="sxs-lookup"><span data-stu-id="cfec5-131">See also</span></span>

[<span data-ttu-id="cfec5-132">Fase 2: Identiteit</span><span class="sxs-lookup"><span data-stu-id="cfec5-132">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="cfec5-133">Microsoft 365 Enterprise Test Lab-handleidingen</span><span class="sxs-lookup"><span data-stu-id="cfec5-133">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="cfec5-134">Microsoft 365 Enterprise-implementatie</span><span class="sxs-lookup"><span data-stu-id="cfec5-134">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="cfec5-135">Microsoft 365 Enterprise-documentatie</span><span class="sxs-lookup"><span data-stu-id="cfec5-135">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
