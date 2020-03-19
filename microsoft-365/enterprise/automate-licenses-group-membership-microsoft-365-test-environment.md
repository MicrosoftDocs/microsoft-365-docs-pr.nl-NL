---
title: Licentie- en groepslidmaatschap voor uw Microsoft 365 Enterprise-testomgeving automatiseren
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Groepsgebaseerde licenties en dynamisch groepslidmaatschap configureren in uw Microsoft 365 Enterprise-testomgeving.
ms.openlocfilehash: 266ae8cb133eccf74ea75382b400ca8241782ec5
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806816"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="cae8b-103">Licentie- en groepslidmaatschap voor uw Microsoft 365 Enterprise-testomgeving automatiseren</span><span class="sxs-lookup"><span data-stu-id="cae8b-103">Automate licensing and group membership for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="cae8b-104">*Deze Test Lab Guide kan alleen worden gebruikt voor Microsoft 365 Enterprise-testomgevingen.*</span><span class="sxs-lookup"><span data-stu-id="cae8b-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="cae8b-105">Groepslicenties worden automatisch toegeschreven of verwijderd licenties voor een gebruikersaccount op basis van groepslidmaatschap.</span><span class="sxs-lookup"><span data-stu-id="cae8b-105">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="cae8b-106">Dynamisch groepslidmaatschap voegt leden toe of verwijdert leden aan een groep op basis van de eigenschappen van gebruikersaccounts, zoals Afdeling of Land.</span><span class="sxs-lookup"><span data-stu-id="cae8b-106">Dynamic group membership adds or removes members to a group based on user account properties, such as Department or Country.</span></span> <span data-ttu-id="cae8b-107">In dit artikel wordt een demonstratie van beide in uw Microsoft 365 Enterprise-testomgeving gegeven.</span><span class="sxs-lookup"><span data-stu-id="cae8b-107">This article steps you through a demonstration of both in your Microsoft 365 Enterprise test environment.</span></span>

<span data-ttu-id="cae8b-108">Er zijn twee fasen voor het instellen van automatisch licentie- en dynamisch groepslidmaatschap in uw Microsoft 365 Enterprise-testomgeving:</span><span class="sxs-lookup"><span data-stu-id="cae8b-108">There are two phases to setting up auto-licensing and dynamic group membership in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="cae8b-109">Maak de Microsoft 365 Enterprise-testomgeving.</span><span class="sxs-lookup"><span data-stu-id="cae8b-109">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="cae8b-110">Dynamisch groepslidmaatschap en automatische licenties configureren en testen.</span><span class="sxs-lookup"><span data-stu-id="cae8b-110">Configure and test dynamic group membership and automatic licensing.</span></span>

![Lab-handleidingen testen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="cae8b-112">Klik [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de Microsoft 365 Enterprise Test Lab Guide stack.</span><span class="sxs-lookup"><span data-stu-id="cae8b-112">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="cae8b-113">Fase 1: Uw Microsoft 365 Enterprise-testomgeving uitbouwen</span><span class="sxs-lookup"><span data-stu-id="cae8b-113">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="cae8b-114">Als u alleen geautomatiseerde licenties en groepslidmaatschap op een lichtgewicht manier wilt testen met de minimale vereisten, volgt u de instructies in [lichtgewicht basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="cae8b-114">If you just want to test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="cae8b-115">Als u geautomatiseerde licenties en groepslidmaatschap in een gesimuleerde onderneming wilt testen, volgt u de instructies in [pass-through-verificatie.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="cae8b-115">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="cae8b-116">Voor het testen van geautomatiseerde licenties en groepslidmaatschap is geen gesimuleerde bedrijfstestomgeving vereist, waaronder een gesimuleerd intranet dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS-forest (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="cae8b-116">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="cae8b-117">Het wordt hier als optie verstrekt, zodat u geautomatiseerde licenties en groepslidmaatschap testen en ermee experimenteren in een omgeving die een typische organisatie vertegenwoordigt.</span><span class="sxs-lookup"><span data-stu-id="cae8b-117">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="cae8b-118">Fase 2: Dynamisch groepslidmaatschap en automatische licenties configureren en testen</span><span class="sxs-lookup"><span data-stu-id="cae8b-118">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="cae8b-119">Eerst maakt u een nieuwe verkoopgroep en voegt u een dynamische groepslidmaatschapsregel toe, zodat gebruikersaccounts met de afdeling die is ingesteld op Verkoop automatisch worden toegevoegd aan de groep Verkoop.</span><span class="sxs-lookup"><span data-stu-id="cae8b-119">First, you create a new Sales group and add a dynamic group membership rule so that user accounts with the Department set to Sales are automatically added to the Sales group.</span></span>

1. <span data-ttu-id="cae8b-120">Meld u met een privé-exemplaar van uw internetbrowser [https://portal.office.com](https://portal.office.com) aan bij de Office 365-portal met het globale beheerdersaccount van uw Microsoft 365 E5-testlababonnement.</span><span class="sxs-lookup"><span data-stu-id="cae8b-120">Using a private instance of your Internet browser, sign in to the Office 365 portal at [https://portal.office.com](https://portal.office.com) with the global administrator account of your Microsoft 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="cae8b-121">Ga op een apart tabblad van uw [https://portal.azure.com](https://portal.azure.com)browser naar de Azure-portal op .</span><span class="sxs-lookup"><span data-stu-id="cae8b-121">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="cae8b-122">Typ in de Azure-portal **groepen** in het zoekvak en klik op **Groepen**.</span><span class="sxs-lookup"><span data-stu-id="cae8b-122">In the Azure portal, type **groups** in the search box, and then click **Groups**.</span></span>
4. <span data-ttu-id="cae8b-123">Klik in het deelvenster **Alle groepen** op **Nieuwe groep**.</span><span class="sxs-lookup"><span data-stu-id="cae8b-123">in the **All groups** pane, click **New group**.</span></span>
5. <span data-ttu-id="cae8b-124">Selecteer **Office 365**in **Groepstype**.</span><span class="sxs-lookup"><span data-stu-id="cae8b-124">In **Group type**, select **Office 365**.</span></span>
6. <span data-ttu-id="cae8b-125">Typ **Verkoop**in **groepsnaam**.</span><span class="sxs-lookup"><span data-stu-id="cae8b-125">In **Group name**, type **Sales**.</span></span>
7. <span data-ttu-id="cae8b-126">Selecteer **Dynamische gebruiker**in **lidmaatschapstype**.</span><span class="sxs-lookup"><span data-stu-id="cae8b-126">In **Membership type**, select **Dynamic user**.</span></span>
8. <span data-ttu-id="cae8b-127">Klik **op Dynamische gebruikersleden**.</span><span class="sxs-lookup"><span data-stu-id="cae8b-127">Click **Dynamic user members**.</span></span>
9. <span data-ttu-id="cae8b-128">Ga als volgt te werk in het deelvenster **Regels voor lidmaatschap van Dynamic:**</span><span class="sxs-lookup"><span data-stu-id="cae8b-128">In the **Dynamic membership rules** pane:</span></span> 
   - <span data-ttu-id="cae8b-129">Selecteer de eigenschap van de **afdeling.**</span><span class="sxs-lookup"><span data-stu-id="cae8b-129">Select the **department** property.</span></span>
   - <span data-ttu-id="cae8b-130">Selecteer de **operator Gelijken.**</span><span class="sxs-lookup"><span data-stu-id="cae8b-130">Select the **Equals** operator.</span></span>
   - <span data-ttu-id="cae8b-131">Typ **Verkoop** in **waarde**.</span><span class="sxs-lookup"><span data-stu-id="cae8b-131">Type **Sales** in **Value**.</span></span>
10. <span data-ttu-id="cae8b-132">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="cae8b-132">Click **Save**.</span></span>
11. <span data-ttu-id="cae8b-133">Klik **op Maken**.</span><span class="sxs-lookup"><span data-stu-id="cae8b-133">Click **Create**.</span></span>

<span data-ttu-id="cae8b-134">Vervolgens configureert u de groep Verkoop, zodat leden automatisch de Microsoft 365 E5-licentie toegewezen krijgen.</span><span class="sxs-lookup"><span data-stu-id="cae8b-134">Next, you configure the Sales group so that members are automatically assigned the Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="cae8b-135">Klik op de groep **Verkoop** en klik vervolgens op **Licenties**.</span><span class="sxs-lookup"><span data-stu-id="cae8b-135">Click the **Sales** group, and then click **Licenses**.</span></span>
2. <span data-ttu-id="cae8b-136">Selecteer **Microsoft 365 E5**in het deelvenster **Licentietoewijzingen** bijwerken en klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="cae8b-136">In the **Update license assignments** pane, select **Microsoft 365 E5**, and then click **Save**.</span></span>
3. <span data-ttu-id="cae8b-137">Sluit het tabblad Azure-portal in uw browser.</span><span class="sxs-lookup"><span data-stu-id="cae8b-137">Close the Azure portal tab in your browser.</span></span>

<span data-ttu-id="cae8b-138">Vervolgens test u dynamisch groepslidmaatschap en automatische licenties op het account Gebruiker 4.</span><span class="sxs-lookup"><span data-stu-id="cae8b-138">Next, you test dynamic group membership and automatic licensing on the User 4 account.</span></span> 

1. <span data-ttu-id="cae8b-139">Klik op het tabblad **Microsoft Office Start** in uw browser op **Beheerder**.</span><span class="sxs-lookup"><span data-stu-id="cae8b-139">From the **Microsoft Office Home** tab in your browser, click **Admin**.</span></span>
2. <span data-ttu-id="cae8b-140">Klik op het tabblad **Microsoft 365-beheercentrum** op **Actieve gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="cae8b-140">From the **Microsoft 365 admin center** tab, click **Active users**.</span></span>
3. <span data-ttu-id="cae8b-141">Klik op de pagina **Actieve gebruikers** op het account **Gebruiker 4.**</span><span class="sxs-lookup"><span data-stu-id="cae8b-141">On the **Active users** page, click the **User 4** account.</span></span>
4. <span data-ttu-id="cae8b-142">Klik **in** het deelvenster Gebruiker 4 op **Bewerken** voor **productlicenties**.</span><span class="sxs-lookup"><span data-stu-id="cae8b-142">On the **User 4** pane, click **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="cae8b-143">Schakel in het deelvenster **Productlicenties** de **Microsoft 365 E5-licentie** uit en klik op **> sluiten opslaan**.</span><span class="sxs-lookup"><span data-stu-id="cae8b-143">On the **Product licenses** pane, disable the **Microsoft 365 E5** license, and then click **Save > Close**.</span></span>
6. <span data-ttu-id="cae8b-144">Controleer in de eigenschappen van het account Gebruiker 4 of er geen productlicenties zijn toegewezen en dat er geen groepslidmaatschappen zijn.</span><span class="sxs-lookup"><span data-stu-id="cae8b-144">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="cae8b-145">Klik **op Bewerken** voor **contactgegevens**.</span><span class="sxs-lookup"><span data-stu-id="cae8b-145">Click **Edit** for **Contact information**.</span></span>
8. <span data-ttu-id="cae8b-146">Klik in het deelvenster **Contactgegevens bewerken** op **Contactgegevens**.</span><span class="sxs-lookup"><span data-stu-id="cae8b-146">In the **Edit Contact information** pane, click **Contact information**.</span></span>
9. <span data-ttu-id="cae8b-147">Typ **verkoop** in **Sales**het veld Afdeling en klik op **> sluiten opslaan**.</span><span class="sxs-lookup"><span data-stu-id="cae8b-147">In the **Department** field, type **Sales**, and then click **Save > Close**.</span></span>
10. <span data-ttu-id="cae8b-148">Wacht een paar minuten en klik vervolgens regelmatig op het vernieuwingspictogram rechtsboven in het accountvenster Gebruiker 4.</span><span class="sxs-lookup"><span data-stu-id="cae8b-148">Wait a few minutes, and then periodically click the refresh icon in the upper-right of the User 4 account pane.</span></span> 

<span data-ttu-id="cae8b-149">Na verloop van tijd zou je de:</span><span class="sxs-lookup"><span data-stu-id="cae8b-149">In time you should see the:</span></span>

- <span data-ttu-id="cae8b-150">**Groepslidmaatschappen,** bijgewerkt met de **groep Verkoop.**</span><span class="sxs-lookup"><span data-stu-id="cae8b-150">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="cae8b-151">**Eigenschap productlicenties** bijgewerkt met de **Microsoft 365 E5-licentie.**</span><span class="sxs-lookup"><span data-stu-id="cae8b-151">**Product licenses** property updated with the **Microsoft 365 E5** license.</span></span>

<span data-ttu-id="cae8b-152">Bekijk deze stappen in de identiteitsfase voor informatie en koppelingen voor het implementeren van dynamisch groepslidmaatschap en automatische licenties in productie:</span><span class="sxs-lookup"><span data-stu-id="cae8b-152">See these steps in the Identity phase for information and links to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="cae8b-153">Automatische licenties instellen</span><span class="sxs-lookup"><span data-stu-id="cae8b-153">Set up automatic licensing</span></span>](identity-use-group-management.md#identity-group-license)
- [<span data-ttu-id="cae8b-154">Dynamisch groepslidmaatschap instellen</span><span class="sxs-lookup"><span data-stu-id="cae8b-154">Set up dynamic group membership</span></span>](identity-use-group-management.md#identity-dyn-groups)

## <a name="next-step"></a><span data-ttu-id="cae8b-155">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="cae8b-155">Next step</span></span>

<span data-ttu-id="cae8b-156">Ontdek extra [identiteitsfuncties](m365-enterprise-test-lab-guides.md#identity) en -mogelijkheden in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="cae8b-156">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="cae8b-157">Zie ook</span><span class="sxs-lookup"><span data-stu-id="cae8b-157">See also</span></span>

[<span data-ttu-id="cae8b-158">Fase 2: Identiteit</span><span class="sxs-lookup"><span data-stu-id="cae8b-158">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="cae8b-159">Microsoft 365 Enterprise Test Lab-handleidingen</span><span class="sxs-lookup"><span data-stu-id="cae8b-159">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="cae8b-160">Microsoft 365 Enterprise-implementatie</span><span class="sxs-lookup"><span data-stu-id="cae8b-160">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="cae8b-161">Microsoft 365 Enterprise-documentatie</span><span class="sxs-lookup"><span data-stu-id="cae8b-161">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
