---
title: Een B2B-extranet maken met beheerde gasten
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom: ''
localization_priority: Normal
f1.keywords: NOCSH
description: Meer informatie over het maken van een B2B extranet-site of -team met beheerde gastgebruikers van een partnerorganisatie.
ms.openlocfilehash: 4f8eb33ad9b41f552975d4158a61ec4cedcfa9cc
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46526980"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a><span data-ttu-id="08f0b-103">Een B2B-extranet maken met beheerde gasten</span><span class="sxs-lookup"><span data-stu-id="08f0b-103">Create a B2B extranet with managed guests</span></span>

<span data-ttu-id="08f0b-104">U [Azure Active Directory Entitlement Management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) gebruiken om een B2B-extranet te maken om samen te werken met een partnerorganisatie die Azure Active Directory gebruikt.</span><span class="sxs-lookup"><span data-stu-id="08f0b-104">You can use [Azure Active Directory Entitlement Management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) to create a B2B extranet to collaborate with a partner organization that uses Azure Active Directory.</span></span> <span data-ttu-id="08f0b-105">Hierdoor kunnen gebruikers zich zelf inschrijven voor de extranetsite of -team en toegang krijgen via een goedkeuringsworkflow.</span><span class="sxs-lookup"><span data-stu-id="08f0b-105">This allows users to self-enroll in the extranet site or team and receive access via an approval workflow.</span></span>

<span data-ttu-id="08f0b-106">Met deze methode voor het delen van resources voor samenwerking kan de partnerorganisatie helpen bij het onderhouden en goedkeuren van de gastgebruikers aan hun kant, waardoor de belasting voor uw IT-afdeling wordt verminderd en degenen die het meest bekend zijn met de samenwerkingsovereenkomst gebruikerstoegang kunnen beheren.</span><span class="sxs-lookup"><span data-stu-id="08f0b-106">With this method of sharing resources for collaboration, the partner organization can help maintain and approve the guest users on their end, reducing the burden on your IT department and allowing those most familiar with the collaboration agreement to manage user access.</span></span>

<span data-ttu-id="08f0b-107">In dit artikel worden de stappen doorlopen om een pakket resources te maken (in dit geval een site of team) die u delen met een partnerorganisatie via een registratiemodel voor selfservicetoegang.</span><span class="sxs-lookup"><span data-stu-id="08f0b-107">This article walks through the steps to create a package of resources (in this case, a site or team) that you can share with a partner organization through a self-service access registration model.</span></span> 

<span data-ttu-id="08f0b-108">Voordat u begint, maakt u de site of het team dat u wilt delen met de partnerorganisatie en schakel u deze in voor het delen van gasten.</span><span class="sxs-lookup"><span data-stu-id="08f0b-108">Before you begin, create the site or team that you want to share with the partner organization and enable it for guest sharing.</span></span> <span data-ttu-id="08f0b-109">Zie [Samenwerken met gasten op een site](collaborate-in-site.md) of Samenwerken met gasten in een [team](collaborate-as-team.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="08f0b-109">See [Collaborate with guests in a site](collaborate-in-site.md) or [Collaborate with guests in a team](collaborate-as-team.md) for more information.</span></span> <span data-ttu-id="08f0b-110">We raden u ook aan een veilige omgeving voor [het delen van gasten](create-secure-guest-sharing-environment.md) te controleren op informatie over beveiligings- en nalevingsfuncties die u gebruiken om uw governancebeleid te behouden wanneer u samenwerkt met gasten.</span><span class="sxs-lookup"><span data-stu-id="08f0b-110">We also recommend that you review [Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) for information about security and compliance features that you can use to help maintain your governance policies when collaborating with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="08f0b-111">Videodemonstratie</span><span class="sxs-lookup"><span data-stu-id="08f0b-111">Video demonstration</span></span>

<span data-ttu-id="08f0b-112">Deze video toont de procedures die in dit artikel worden behandeld.</span><span class="sxs-lookup"><span data-stu-id="08f0b-112">This video demonstrates the procedures covered in this article.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a><span data-ttu-id="08f0b-113">De partnerorganisatie verbinden</span><span class="sxs-lookup"><span data-stu-id="08f0b-113">Connect the partner organization</span></span>

<span data-ttu-id="08f0b-114">Als u gasten van een partnerorganisatie wilt uitnodigen, moet u het domein van de partner toevoegen als een verbonden organisatie in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="08f0b-114">In order to invite guests from a partner organization, you need to add the partner's domain as a connected organization in Azure Active Directory.</span></span>

<span data-ttu-id="08f0b-115">Een verbonden organisatie toevoegen</span><span class="sxs-lookup"><span data-stu-id="08f0b-115">To add a connected organization</span></span>
1. <span data-ttu-id="08f0b-116">Klik in [Azure Active Directory](https://aad.portal.azure.com)op **Identiteitsbeheer**.</span><span class="sxs-lookup"><span data-stu-id="08f0b-116">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="08f0b-117">Klik **op Verbonden organisaties**.</span><span class="sxs-lookup"><span data-stu-id="08f0b-117">Click **Connected organizations**.</span></span>
4. <span data-ttu-id="08f0b-118">Klik **op Verbonden organisatie toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="08f0b-118">Click **Add connected organization**.</span></span>
5. <span data-ttu-id="08f0b-119">Typ een naam en beschrijving voor de organisatie en klik op **Volgende: Directory + domein**.</span><span class="sxs-lookup"><span data-stu-id="08f0b-119">Type a name and description for the organization, and then click **Next: Directory + domain**.</span></span>
6. <span data-ttu-id="08f0b-120">Klik **op Map + domein toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="08f0b-120">Click **Add directory + domain**.</span></span>
7. <span data-ttu-id="08f0b-121">Typ het domein voor de organisatie die u wilt verbinden en klik op **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="08f0b-121">Type the domain for the organization that you want to connect, and then click **Add**.</span></span>
8. <span data-ttu-id="08f0b-122">Klik **op Verbinden**en klik vervolgens op **Volgende: Sponsors**.</span><span class="sxs-lookup"><span data-stu-id="08f0b-122">Click **Connect**, and then click **Next: Sponsors**.</span></span>
9. <span data-ttu-id="08f0b-123">Voeg mensen uit uw organisatie of de organisatie toe waarmee u verbinding maakt met wie u toegang wilt goedkeuren voor gastgebruikers.</span><span class="sxs-lookup"><span data-stu-id="08f0b-123">Add people from your organization or the organization that you're connecting to who you want to approve access for guest users.</span></span>
10. <span data-ttu-id="08f0b-124">Klik **op Volgende: Controleren + Maken**.</span><span class="sxs-lookup"><span data-stu-id="08f0b-124">Click **Next: Review + Create**.</span></span>
11. <span data-ttu-id="08f0b-125">Bekijk de instellingen die u hebt gekozen en klik op **Maken**.</span><span class="sxs-lookup"><span data-stu-id="08f0b-125">Review the settings that you've chosen and then click **Create**.</span></span>

    ![Schermafbeelding van de pagina Verbonden organisaties in Azure Active Directory](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a><span data-ttu-id="08f0b-127">De resources kiezen die u wilt delen</span><span class="sxs-lookup"><span data-stu-id="08f0b-127">Choose the resources to share</span></span>

<span data-ttu-id="08f0b-128">De eerste stap bij het selecteren van resources die u wilt delen met een partnerorganisatie, is het maken van een catalogus die deze bevat.</span><span class="sxs-lookup"><span data-stu-id="08f0b-128">The first step in selecting resources to share with a partner organization is to create a catalog to contain them.</span></span>

<span data-ttu-id="08f0b-129">Een catalogus maken</span><span class="sxs-lookup"><span data-stu-id="08f0b-129">To create a catalog</span></span>
1. <span data-ttu-id="08f0b-130">Klik in [Azure Active Directory](https://aad.portal.azure.com)op **Identiteitsbeheer**.</span><span class="sxs-lookup"><span data-stu-id="08f0b-130">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="08f0b-131">Klik **op Catalogi**.</span><span class="sxs-lookup"><span data-stu-id="08f0b-131">Click **Catalogs**.</span></span>
3. <span data-ttu-id="08f0b-132">Klik op **Nieuwe catalogus**.</span><span class="sxs-lookup"><span data-stu-id="08f0b-132">Click **New catalog**.</span></span>
4. <span data-ttu-id="08f0b-133">Typ een naam en beschrijving voor de catalogus en zorg ervoor dat **Ingeschakeld** en **Ingeschakeld voor externe gebruikers** zijn ingesteld op **Ja.**</span><span class="sxs-lookup"><span data-stu-id="08f0b-133">Type a name and description for the catalog and ensure that **Enabled** and **Enabled for external users** are both set to **Yes**.</span></span>
5. <span data-ttu-id="08f0b-134">Klik op **Maken**.</span><span class="sxs-lookup"><span data-stu-id="08f0b-134">Click **Create**.</span></span>

   ![Schermafbeelding van de pagina catalogi in Azure Active Directory Identity Governance](../media/identity-governance-catalogs.png)

<span data-ttu-id="08f0b-136">Zodra de catalogus is gemaakt, voegt u de SharePoint-site of -team toe die u wilt delen met de partnerorganisatie.</span><span class="sxs-lookup"><span data-stu-id="08f0b-136">Once the catalog has been created, you add the SharePoint site or team that you want to share with the partner organization.</span></span>

<span data-ttu-id="08f0b-137">Resources toevoegen aan een catalogus</span><span class="sxs-lookup"><span data-stu-id="08f0b-137">To add resources to a catalog</span></span>
1. <span data-ttu-id="08f0b-138">Klik in Azure AD Identity Governance op **Catalogi**en klik vervolgens op de catalogus waar u resources wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="08f0b-138">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to add resources.</span></span>
2. <span data-ttu-id="08f0b-139">Klik **op Resources** en klik vervolgens op Resources **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="08f0b-139">Click **Resources** and then click **Add resources**.</span></span>
3. <span data-ttu-id="08f0b-140">Selecteer de teams of SharePoint-sites die u in uw extranet wilt opnemen en klik op **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="08f0b-140">Select the teams or SharePoint sites that you want to include in your extranet, and then click **Add**.</span></span>

   ![Schermafbeelding van de pagina catalogusresources in Azure Active Directory Identity Governance](../media/identity-governance-catalog-resource.png)

<span data-ttu-id="08f0b-142">Zodra u de resources hebt gedefinieerd die u wilt delen, is de volgende stap het maken van een toegangspakket, dat het type toegang definieert dat partnergebruikers krijgen en het goedkeuringsproces voor nieuwe partnergebruikers die toegang aanvragen.</span><span class="sxs-lookup"><span data-stu-id="08f0b-142">Once you've defined the resources that you want to share, the next step is to create an access package, which defines the type of access that partner users are granted and the approval process for new partner users requesting access.</span></span>

<span data-ttu-id="08f0b-143">Een toegangspakket maken</span><span class="sxs-lookup"><span data-stu-id="08f0b-143">To create an access package</span></span>
1. <span data-ttu-id="08f0b-144">Klik in Azure AD Identity Governance op **Catalogi**en klik vervolgens op de catalogus waar u een toegangspakket wilt maken.</span><span class="sxs-lookup"><span data-stu-id="08f0b-144">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to create an access package.</span></span>
2. <span data-ttu-id="08f0b-145">Klik op **Access-pakketten**en klik vervolgens op **Nieuw toegangspakket**.</span><span class="sxs-lookup"><span data-stu-id="08f0b-145">Click **Access packages**, and then click **New access package**.</span></span>
3. <span data-ttu-id="08f0b-146">Typ een naam en beschrijving voor het toegangspakket en klik op **Volgende: Resourcerollen**.</span><span class="sxs-lookup"><span data-stu-id="08f0b-146">Type a name and description for the access package, and then click **Next: Resource roles**.</span></span>
4. <span data-ttu-id="08f0b-147">Kies de bronnen uit de catalogus die u voor uw extranet wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="08f0b-147">Choose the resources from the catalog that you want to use for your extranet.</span></span>
5. <span data-ttu-id="08f0b-148">Kies voor elke resource in de kolom **Rol** de gebruikersrol die u wilt toekenn aan de gastgebruikers die het extranet gebruiken.</span><span class="sxs-lookup"><span data-stu-id="08f0b-148">For each resource, in the **Role** column, choose the user role you want to grant to the guest users who use the extranet.</span></span>
6. <span data-ttu-id="08f0b-149">Klik **op Volgende: aanvragen**.</span><span class="sxs-lookup"><span data-stu-id="08f0b-149">Click **Next: Requests**.</span></span>
7. <span data-ttu-id="08f0b-150">Kies **onder Gebruikers die toegang kunnen aanvragen**voor gebruikers die niet in uw map **staan.**</span><span class="sxs-lookup"><span data-stu-id="08f0b-150">Under **Users who can request access**, choose **For users not in your directory**.</span></span>
8. <span data-ttu-id="08f0b-151">Controleer of de optie **Specifieke verbonden organisaties** is geselecteerd en klik vervolgens op **Mappen toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="08f0b-151">Ensure that the **Specific connected organizations** option is selected, and then click **Add directories**.</span></span>
9. <span data-ttu-id="08f0b-152">Kies de verbonden organisatie die u eerder toevoegt en klik op **Selecteren**</span><span class="sxs-lookup"><span data-stu-id="08f0b-152">Choose the connected organization that you add earlier, and then click **Select**</span></span>
10. <span data-ttu-id="08f0b-153">Kies onder **Goedkeuring**de optie **Ja** voor **Goedkeuring vereisen**.</span><span class="sxs-lookup"><span data-stu-id="08f0b-153">Under **Approval**, choose **Yes** for **Require approval**.</span></span>
11. <span data-ttu-id="08f0b-154">Kies onder **Eerste goedkeurder**een van de sponsors die u eerder hebt toegevoegd of kies een specifieke gebruiker.</span><span class="sxs-lookup"><span data-stu-id="08f0b-154">Under **First approver**, choose one of the sponsors that you added earlier or choose a specific user.</span></span>
12. <span data-ttu-id="08f0b-155">Klik **op Fallback toevoegen** en selecteer een terugvalkeurder.</span><span class="sxs-lookup"><span data-stu-id="08f0b-155">Click **Add fallback** and select a fallback approver.</span></span>
13. <span data-ttu-id="08f0b-156">Kies onder **Inschakelen**de optie **Ja**.</span><span class="sxs-lookup"><span data-stu-id="08f0b-156">Under **Enable**, choose **Yes**.</span></span>
14. <span data-ttu-id="08f0b-157">Klik **op Volgende: Levenscyclus**.</span><span class="sxs-lookup"><span data-stu-id="08f0b-157">Click **Next: Lifecycle**.</span></span>
15. <span data-ttu-id="08f0b-158">Kies de instellingen voor verlopen en toegang tot de controle die u wilt gebruiken en klik op **Volgende: Controleren + Maken**.</span><span class="sxs-lookup"><span data-stu-id="08f0b-158">Choose the expiration and access review settings that you want to use, and then click **Next: Review + Create**.</span></span>
16. <span data-ttu-id="08f0b-159">Controleer uw instellingen en klik op **Maken**.</span><span class="sxs-lookup"><span data-stu-id="08f0b-159">Review your settings, and then click **Create**.</span></span>

    ![Schermafbeelding van het scherm toegangspakketten in Azure Active Directory Identity Governance](../media/identity-governance-access-packages.png)

<span data-ttu-id="08f0b-161">Als u samenwerkt met een grote organisatie, u het toegangspakket verbergen.</span><span class="sxs-lookup"><span data-stu-id="08f0b-161">If you're partnering with a large organization, you may want to hide the access package.</span></span> <span data-ttu-id="08f0b-162">Als het pakket is verborgen, zien gebruikers in de partnerorganisatie het pakket niet op hun *Mijn toegang-portal.*</span><span class="sxs-lookup"><span data-stu-id="08f0b-162">If the package is hidden, then users in the partner organization will not see the package on their *My Access* portal.</span></span> <span data-ttu-id="08f0b-163">In plaats daarvan moeten ze een directe link worden verzonden om zich aan te melden voor het pakket.</span><span class="sxs-lookup"><span data-stu-id="08f0b-163">Instead, they must be sent a direct link to sign up for the package.</span></span> <span data-ttu-id="08f0b-164">Het verbergen van het toegangspakket kan het aantal ongepaste toegangsaanvragen verminderen en kan ook helpen om beschikbare toegangspakketten georganiseerd te houden in het portaal van de partnerorganisatie.</span><span class="sxs-lookup"><span data-stu-id="08f0b-164">Hiding the access package can reduce the number of inappropriate access requests and can also help keep available access packages organized in the partner organization's portal.</span></span>

<span data-ttu-id="08f0b-165">Een toegangspakket instellen op verborgen</span><span class="sxs-lookup"><span data-stu-id="08f0b-165">To set an access package to hidden</span></span>
1. <span data-ttu-id="08f0b-166">Klik in Azure AD Identity Governance op **Access-pakketten**en klik vervolgens op uw toegangspakket.</span><span class="sxs-lookup"><span data-stu-id="08f0b-166">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="08f0b-167">Klik op de pagina **Overzicht** op **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="08f0b-167">On the **Overview** page, click **Edit**.</span></span>
3. <span data-ttu-id="08f0b-168">Kies onder **Eigenschappen**De optie **Ja** voor **Verborgen**en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="08f0b-168">Under **Properties**, choose **Yes** for **Hidden**, and then click **Save**.</span></span>

   ![Schermafbeelding van het scherm Eigenschappen van een toegangspakket bewerken](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a><span data-ttu-id="08f0b-170">Partnergebruikers uitnodigen</span><span class="sxs-lookup"><span data-stu-id="08f0b-170">Invite partner users</span></span>

<span data-ttu-id="08f0b-171">Als u het toegangspakket op verborgen stelt, moet u een directe koppeling naar de partnerorganisatie verzenden, zodat deze toegang tot uw site of team kan aanvragen.</span><span class="sxs-lookup"><span data-stu-id="08f0b-171">If you set the access package to hidden, you need to send a direct link to the partner organization so that they can request access to your site or team.</span></span>

<span data-ttu-id="08f0b-172">De koppeling naar de toegangsportalen zoeken</span><span class="sxs-lookup"><span data-stu-id="08f0b-172">To find the access portal link</span></span>
1. <span data-ttu-id="08f0b-173">Klik in Azure AD Identity Governance op **Access-pakketten**en klik vervolgens op uw toegangspakket.</span><span class="sxs-lookup"><span data-stu-id="08f0b-173">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="08f0b-174">Klik op de pagina **Overzicht** op **Kopiëren naar klembordkoppeling** voor de **koppeling Mijn toegang-portal**.</span><span class="sxs-lookup"><span data-stu-id="08f0b-174">On the **Overview** page, click **Copy to clipboard** link for the **My Access portal link**.</span></span>

   ![Schermafbeelding van de eigenschappen van toegangspakket met koppeling toegangsportport](../media/identity-governance-access-portal-link.png)

<span data-ttu-id="08f0b-176">Zodra u de koppeling hebt gekopieerd, u deze delen met uw contactpersoon bij de partnerorganisatie en deze naar de gebruikers van hun samenwerkingsteam sturen.</span><span class="sxs-lookup"><span data-stu-id="08f0b-176">Once you have copied the link, you can share it with your contact at the partner organization and they can send it to the users on their collaboration team.</span></span>

## <a name="see-also"></a><span data-ttu-id="08f0b-177">Zie ook</span><span class="sxs-lookup"><span data-stu-id="08f0b-177">See Also</span></span>

[<span data-ttu-id="08f0b-178">Een beveiligde omgeving voor het delen met gasten maken</span><span class="sxs-lookup"><span data-stu-id="08f0b-178">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

