---
title: Automatiseer licenties en groepslidmaatschap voor uw microsoft 365 voor ondernemingstestomgeving
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
description: Configureer groepslicenties en dynamisch groepslidmaatschap in uw Microsoft 365 voor ondernemingstestomgeving.
ms.openlocfilehash: 26840e2884202a0fa9c4bb563f3d7c653482ef87
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905366"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="4504e-103">Automatiseer licenties en groepslidmaatschap voor uw microsoft 365 voor ondernemingstestomgeving</span><span class="sxs-lookup"><span data-stu-id="4504e-103">Automate licensing and group membership for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="4504e-104">*Deze testlaborator kan alleen worden gebruikt voor Microsoft 365 voor testomgevingen voor ondernemingen.*</span><span class="sxs-lookup"><span data-stu-id="4504e-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="4504e-105">Licenties op basis van groepen worden automatisch toegewezen of verwijderd voor een gebruikersaccount op basis van groepslidmaatschap.</span><span class="sxs-lookup"><span data-stu-id="4504e-105">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="4504e-106">Dynamische groepslidmaatschap voegt leden toe aan een groep op basis van eigenschappen van gebruikersaccounts, zoals **Afdeling** of **Land.**</span><span class="sxs-lookup"><span data-stu-id="4504e-106">Dynamic group membership adds or removes members to a group based on user account properties, such as **Department** or **Country**.</span></span> <span data-ttu-id="4504e-107">In dit artikel wordt beschreven hoe u groepsleden toevoegt en verwijdert in uw microsoft 365 voor ondernemingstestomgeving.</span><span class="sxs-lookup"><span data-stu-id="4504e-107">This article steps you through demonstrations of both adding and removing group members in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="4504e-108">Het instellen van lidmaatschap van automatische licenties en dynamische groepen in uw Microsoft 365-testomgeving voor ondernemingen omvat twee fasen:</span><span class="sxs-lookup"><span data-stu-id="4504e-108">Setting up auto-licensing and dynamic group membership in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="4504e-109">Fase 1: Uw Microsoft 365 voor ondernemingstestomgeving opbouwen</span><span class="sxs-lookup"><span data-stu-id="4504e-109">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="4504e-110">Fase 2: Dynamisch groepslidmaatschap en automatische licenties configureren en testen</span><span class="sxs-lookup"><span data-stu-id="4504e-110">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="4504e-112">Ga naar [Microsoft 365 for enterprise Test Lab Guide](../downloads/Microsoft365EnterpriseTLGStack.pdf)Stack voor een visuele kaart voor alle artikelen in de Microsoft 365 voor enterprise Test Lab Guide Stack.</span><span class="sxs-lookup"><span data-stu-id="4504e-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="4504e-113">Fase 1: Uw Microsoft 365 voor ondernemingstestomgeving opbouwen</span><span class="sxs-lookup"><span data-stu-id="4504e-113">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="4504e-114">Als u alleen geautomatiseerde licenties en groepslidmaatschap op een lichtgewicht manier wilt testen met de minimumvereisten, volgt u de instructies in De lichtgewicht [basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="4504e-114">If you want to only test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="4504e-115">Als u geautomatiseerde licenties en groepslidmaatschap in een gesimuleerde onderneming wilt testen, volgt u de instructies in [Pass-through-verificatie.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="4504e-115">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="4504e-116">Voor het testen van geautomatiseerde licenties en groepslidmaatschap is geen gesimuleerde testomgeving voor ondernemingen vereist, waaronder een gesimuleerd intranet dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS-forest (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="4504e-116">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="4504e-117">Het wordt hier als een optie aangeboden, zodat u geautomatiseerde licenties en groepslidmaatschap kunt testen en erop kunt experimenteren in een omgeving die een normale organisatie vertegenwoordigt.</span><span class="sxs-lookup"><span data-stu-id="4504e-117">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="4504e-118">Fase 2: Dynamisch groepslidmaatschap en automatische licenties configureren en testen</span><span class="sxs-lookup"><span data-stu-id="4504e-118">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="4504e-119">Maak eerst een nieuwe groep met de naam Verkoop en voeg  een dynamische  groepslidmaatschapsregel toe, zodat gebruikersaccounts met de afdeling Die is ingesteld op Verkoop, automatisch deelnemen aan de groep Verkoop.</span><span class="sxs-lookup"><span data-stu-id="4504e-119">First, create a new group named Sales, and add a dynamic group membership rule so that user accounts with the **Department** set to **Sales** automatically join the Sales group.</span></span>

1. <span data-ttu-id="4504e-120">Meld u in een privé-exemplaar van uw internetbrowser aan bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com) met het globale beheerdersaccount van uw Microsoft 365 E5-testlaboratoriumabonnement.</span><span class="sxs-lookup"><span data-stu-id="4504e-120">In a private instance of your internet browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with the global administrator account of your Microsoft 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="4504e-121">Ga op een apart tabblad van uw browser naar de Azure-portal op [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="4504e-121">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="4504e-122">Voer in de Azure-portal **groepen** in het zoekvak in en selecteer vervolgens **Groepen.**</span><span class="sxs-lookup"><span data-stu-id="4504e-122">In the Azure portal, enter **groups** in the search box, and then select **Groups**.</span></span>
4. <span data-ttu-id="4504e-123">selecteer in **het deelvenster** Alle groepen de optie **Nieuwe groep**.</span><span class="sxs-lookup"><span data-stu-id="4504e-123">in the **All groups** pane, select **New group**.</span></span>
5. <span data-ttu-id="4504e-124">Selecteer **microsoft** **365** in groeptype .</span><span class="sxs-lookup"><span data-stu-id="4504e-124">In **Group type**, select **Microsoft 365**.</span></span>
6. <span data-ttu-id="4504e-125">Voer **in Groepsnaam** De **verkoop in.**</span><span class="sxs-lookup"><span data-stu-id="4504e-125">In **Group name**, enter **Sales**.</span></span>
7. <span data-ttu-id="4504e-126">Selecteer **dynamische gebruiker in het type** **Lidmaatschap.**</span><span class="sxs-lookup"><span data-stu-id="4504e-126">In **Membership type**, select **Dynamic user**.</span></span>
8. <span data-ttu-id="4504e-127">Selecteer **Dynamische gebruikersleden.**</span><span class="sxs-lookup"><span data-stu-id="4504e-127">Select **Dynamic user members**.</span></span>
9. <span data-ttu-id="4504e-128">In het **deelvenster Dynamische lidmaatschapsregels:**</span><span class="sxs-lookup"><span data-stu-id="4504e-128">In the **Dynamic membership rules** pane:</span></span> 
   - <span data-ttu-id="4504e-129">Selecteer de **eigenschap afdeling.**</span><span class="sxs-lookup"><span data-stu-id="4504e-129">Select the **department** property.</span></span>
   - <span data-ttu-id="4504e-130">Selecteer de **operator Gelijk** aan.</span><span class="sxs-lookup"><span data-stu-id="4504e-130">Select the **Equals** operator.</span></span>
   - <span data-ttu-id="4504e-131">Voer in **het** vak Waarde de tekst **Verkoop in.**</span><span class="sxs-lookup"><span data-stu-id="4504e-131">In the **Value** box, enter **Sales**.</span></span>
10. <span data-ttu-id="4504e-132">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="4504e-132">Select **Save**.</span></span>
11. <span data-ttu-id="4504e-133">Selecteer **Maken**. </span><span class="sxs-lookup"><span data-stu-id="4504e-133">Select **Create**.</span></span>

<span data-ttu-id="4504e-134">Configureer vervolgens de groep Verkoop, zodat leden automatisch de Microsoft 365 E5-licentie krijgen toegewezen.</span><span class="sxs-lookup"><span data-stu-id="4504e-134">Next, configure the Sales group so that members are automatically assigned the Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="4504e-135">Selecteer de **groep** Verkoop en selecteer **vervolgens Licenties**.</span><span class="sxs-lookup"><span data-stu-id="4504e-135">Select the **Sales** group, and then select **Licenses**.</span></span>
2. <span data-ttu-id="4504e-136">Selecteer microsoft **365 E5** in het deelvenster **Licentietoewijzingen** bijwerken en selecteer **opslaan.**</span><span class="sxs-lookup"><span data-stu-id="4504e-136">In the **Update license assignments** pane, select **Microsoft 365 E5**, and then select **Save**.</span></span>
3. <span data-ttu-id="4504e-137">Sluit in uw browser het tabblad Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="4504e-137">In your browser, close the Azure portal tab.</span></span>

<span data-ttu-id="4504e-138">Test vervolgens het dynamische groepslidmaatschap en automatische licenties voor het gebruikers 4-account:</span><span class="sxs-lookup"><span data-stu-id="4504e-138">Next, test dynamic group membership and automatic licensing on the User 4 account:</span></span>

1. <span data-ttu-id="4504e-139">Selecteer beheerder op het tabblad **Microsoft Office Home** in **uw** browser.</span><span class="sxs-lookup"><span data-stu-id="4504e-139">From the **Microsoft Office Home** tab in your browser, select **Admin**.</span></span>
2. <span data-ttu-id="4504e-140">Selecteer actieve gebruikers op het tabblad **Microsoft 365-beheercentrum.** </span><span class="sxs-lookup"><span data-stu-id="4504e-140">From the **Microsoft 365 admin center** tab, select **Active users**.</span></span>
3. <span data-ttu-id="4504e-141">Selecteer op **de pagina** Actieve gebruikers het account **Gebruiker 4.**</span><span class="sxs-lookup"><span data-stu-id="4504e-141">On the **Active users** page, select the **User 4** account.</span></span>
4. <span data-ttu-id="4504e-142">Selecteer in het deelvenster Gebruiker **4** de optie **Bewerken** voor **productlicenties.**</span><span class="sxs-lookup"><span data-stu-id="4504e-142">On the **User 4** pane, select **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="4504e-143">Schakel in **het deelvenster Productlicenties** de **Microsoft 365 E5-licentie** uit en selecteer **vervolgens Sluiten**  >  **opslaan.**</span><span class="sxs-lookup"><span data-stu-id="4504e-143">On the **Product licenses** pane, disable the **Microsoft 365 E5** license, and then select **Save** > **Close**.</span></span>
6. <span data-ttu-id="4504e-144">Controleer in de eigenschappen van het Gebruikers 4-account of er geen productlicenties zijn toegewezen en dat er geen groepslidmaatschap is.</span><span class="sxs-lookup"><span data-stu-id="4504e-144">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="4504e-145">Selecteer Bewerken voor  **contactgegevens.**</span><span class="sxs-lookup"><span data-stu-id="4504e-145">For **Contact information**, select **Edit**.</span></span>
8. <span data-ttu-id="4504e-146">Selecteer in **het deelvenster Contactgegevens** bewerken de optie **Contactgegevens**.</span><span class="sxs-lookup"><span data-stu-id="4504e-146">In the **Edit Contact information** pane, select **Contact information**.</span></span>
9. <span data-ttu-id="4504e-147">Voer in **het** vak Afdeling **verkoop in** en selecteer **vervolgens Sluiten**  >  **opslaan.**</span><span class="sxs-lookup"><span data-stu-id="4504e-147">In the **Department** box, enter **Sales**, and then select **Save** > **Close**.</span></span>
10. <span data-ttu-id="4504e-148">Wacht een paar minuten en selecteer  vervolgens regelmatig het pictogram Vernieuwen in de rechterbovenhoek van het deelvenster Gebruikers 4-account.</span><span class="sxs-lookup"><span data-stu-id="4504e-148">Wait a few minutes, and then periodically select the **Refresh** icon in the upper-right of the User 4 account pane.</span></span>

<span data-ttu-id="4504e-149">Op tijd ziet u het volgende:</span><span class="sxs-lookup"><span data-stu-id="4504e-149">In time, you should see the:</span></span>

- <span data-ttu-id="4504e-150">**De eigenschap Groepslidmaatschap** is bijgewerkt met de **groep** Verkoop.</span><span class="sxs-lookup"><span data-stu-id="4504e-150">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="4504e-151">**Eigenschap productlicenties** bijgewerkt met de **Microsoft 365 E5-licentie.**</span><span class="sxs-lookup"><span data-stu-id="4504e-151">**Product licenses** property updated with the **Microsoft 365 E5** license.</span></span>

<span data-ttu-id="4504e-152">Zie deze artikelen voor het implementeren van dynamisch groepslidmaatschap en automatische licenties in productie:</span><span class="sxs-lookup"><span data-stu-id="4504e-152">See these articles to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="4504e-153">Groepslicenties in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="4504e-153">Group-based licensing in Azure Active Directory</span></span>](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [<span data-ttu-id="4504e-154">Dynamische groepen in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="4504e-154">Dynamic groups in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a><span data-ttu-id="4504e-155">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="4504e-155">Next step</span></span>

<span data-ttu-id="4504e-156">Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="4504e-156">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="4504e-157">Zie ook</span><span class="sxs-lookup"><span data-stu-id="4504e-157">See also</span></span>

[<span data-ttu-id="4504e-158">Routekaart voor identiteit</span><span class="sxs-lookup"><span data-stu-id="4504e-158">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="4504e-159">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="4504e-159">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="4504e-160">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="4504e-160">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="4504e-161">Microsoft 365 enterprise-documentatie</span><span class="sxs-lookup"><span data-stu-id="4504e-161">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)