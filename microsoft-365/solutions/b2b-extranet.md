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
description: Leer hoe u een B2B-extranetsite of-team maakt met beheerde gastgebruikers van een partnerorganisatie.
ms.openlocfilehash: 83252241833f3dfe663cc70eae28a5df1214cce0
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949382"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a><span data-ttu-id="1401e-103">Een B2B-extranet maken met beheerde gasten</span><span class="sxs-lookup"><span data-stu-id="1401e-103">Create a B2B extranet with managed guests</span></span>

<span data-ttu-id="1401e-104">Met [Azure Active Directory-beheer van rechten](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) kunt u een B2B-extranet maken om samen te werken met een partnerorganisatie die gebruikmaakt van Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1401e-104">You can use [Azure Active Directory Entitlement Management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) to create a B2B extranet to collaborate with a partner organization that uses Azure Active Directory.</span></span> <span data-ttu-id="1401e-105">Hiermee kunnen gebruikers zichzelf registreren op de extranetsite of het team en toegang krijgen via een goedkeuringswerkstroom.</span><span class="sxs-lookup"><span data-stu-id="1401e-105">This allows users to self-enroll in the extranet site or team and receive access via an approval workflow.</span></span>

<span data-ttu-id="1401e-106">Met deze methode voor het delen van bronnen voor samenwerking kan de organisatie organisatie de gastgebruikers aan hun einde bijhouden en goedkeuren, waardoor de belasting van uw IT-afdeling wordt beperkt en de functies voor de samenwerking voor de samenwerking voor de samenwerking voor de samenwerking kunnen worden beheerd.</span><span class="sxs-lookup"><span data-stu-id="1401e-106">With this method of sharing resources for collaboration, the partner organization can help maintain and approve the guest users on their end, reducing the burden on your IT department and allowing those most familiar with the collaboration agreement to manage user access.</span></span>

<span data-ttu-id="1401e-107">In dit artikel worden de stappen beschreven voor het maken van een bron pakket (in dit geval een site of team) dat u kunt delen met een partnerorganisatie via een registratie model voor selfservice toegang.</span><span class="sxs-lookup"><span data-stu-id="1401e-107">This article walks through the steps to create a package of resources (in this case, a site or team) that you can share with a partner organization through a self-service access registration model.</span></span> 

<span data-ttu-id="1401e-108">Voordat u begint, maakt u de site of het team dat u wilt delen met de partnerorganisatie en schakelt u de site in voor het delen van gasten.</span><span class="sxs-lookup"><span data-stu-id="1401e-108">Before you begin, create the site or team that you want to share with the partner organization and enable it for guest sharing.</span></span> <span data-ttu-id="1401e-109">Zie [samenwerken met gasten in een site](collaborate-in-site.md) of [samenwerken met gasten in een team](collaborate-as-team.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1401e-109">See [Collaborate with guests in a site](collaborate-in-site.md) or [Collaborate with guests in a team](collaborate-as-team.md) for more information.</span></span> <span data-ttu-id="1401e-110">U wordt ook aangeraden [een beveiligde omgeving voor het delen van gasten](create-secure-guest-sharing-environment.md) te bekijken voor informatie over beveiligings-en compliance-functies die u kunt gebruiken om uw beheerbeleidsregels te beschermen bij het samenwerken aan gasten.</span><span class="sxs-lookup"><span data-stu-id="1401e-110">We also recommend that you review [Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) for information about security and compliance features that you can use to help maintain your governance policies when collaborating with guests.</span></span>

## <a name="license-requirements"></a><span data-ttu-id="1401e-111">Licentievereisten</span><span class="sxs-lookup"><span data-stu-id="1401e-111">License requirements</span></span>

<span data-ttu-id="1401e-112">Voor het gebruik van deze functie is een Azure AD Premium-licentie vereist.</span><span class="sxs-lookup"><span data-stu-id="1401e-112">Using this feature requires an Azure AD Premium P2 license.</span></span> 

<span data-ttu-id="1401e-113">Gespecialiseerde wolken, zoals Azure Duitsland en Azure China 21Vianet, zijn momenteel niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="1401e-113">Specialized clouds, such as Azure Germany and Azure China 21Vianet, are not currently available for use.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="1401e-114">Videodemonstratie</span><span class="sxs-lookup"><span data-stu-id="1401e-114">Video demonstration</span></span>

<span data-ttu-id="1401e-115">In deze video ziet u de procedures in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="1401e-115">This video demonstrates the procedures covered in this article.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a><span data-ttu-id="1401e-116">De partnerorganisatie verbinden</span><span class="sxs-lookup"><span data-stu-id="1401e-116">Connect the partner organization</span></span>

<span data-ttu-id="1401e-117">Om gasten van een partnerorganisatie uit te nodigen, moet u het domein van de partner toevoegen als een verbonden organisatie in azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1401e-117">In order to invite guests from a partner organization, you need to add the partner's domain as a connected organization in Azure Active Directory.</span></span>

<span data-ttu-id="1401e-118">Een verbonden organisatie toevoegen</span><span class="sxs-lookup"><span data-stu-id="1401e-118">To add a connected organization</span></span>
1. <span data-ttu-id="1401e-119">Klik in [Azure Active Directory](https://aad.portal.azure.com)op **Identity governance**.</span><span class="sxs-lookup"><span data-stu-id="1401e-119">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="1401e-120">Klik op **verbonden organisaties**.</span><span class="sxs-lookup"><span data-stu-id="1401e-120">Click **Connected organizations**.</span></span>
4. <span data-ttu-id="1401e-121">Klik op **verbonden organisatie toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="1401e-121">Click **Add connected organization**.</span></span>
5. <span data-ttu-id="1401e-122">Voer een naam en beschrijving voor de organisatie in en klik op **volgende: adreslijst + domein**.</span><span class="sxs-lookup"><span data-stu-id="1401e-122">Type a name and description for the organization, and then click **Next: Directory + domain**.</span></span>
6. <span data-ttu-id="1401e-123">Klik op **adreslijst + domein toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="1401e-123">Click **Add directory + domain**.</span></span>
7. <span data-ttu-id="1401e-124">Typ het domein voor de organisatie waarmee u verbinding wilt maken en klik op **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="1401e-124">Type the domain for the organization that you want to connect, and then click **Add**.</span></span>
8. <span data-ttu-id="1401e-125">Klik op **verbinden**en klik vervolgens op **volgende: sponsors**.</span><span class="sxs-lookup"><span data-stu-id="1401e-125">Click **Connect**, and then click **Next: Sponsors**.</span></span>
9. <span data-ttu-id="1401e-126">Voeg mensen uit uw organisatie of organisatie toe die u wilt gebruiken voor de toegang tot gastgebruikers.</span><span class="sxs-lookup"><span data-stu-id="1401e-126">Add people from your organization or the organization that you're connecting to who you want to approve access for guest users.</span></span>
10. <span data-ttu-id="1401e-127">Klik op **volgende: bekijken + maken**.</span><span class="sxs-lookup"><span data-stu-id="1401e-127">Click **Next: Review + Create**.</span></span>
11. <span data-ttu-id="1401e-128">Controleer de instellingen die u hebt gekozen en klik vervolgens op **maken**.</span><span class="sxs-lookup"><span data-stu-id="1401e-128">Review the settings that you've chosen and then click **Create**.</span></span>

    ![Schermafbeelding van de pagina verbonden organisaties in azure Active Directory](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a><span data-ttu-id="1401e-130">Kies de resources die u wilt delen</span><span class="sxs-lookup"><span data-stu-id="1401e-130">Choose the resources to share</span></span>

<span data-ttu-id="1401e-131">De eerste stap bij het selecteren van resources om te delen met een partnerorganisatie is het maken van een catalogus om deze te bevatten.</span><span class="sxs-lookup"><span data-stu-id="1401e-131">The first step in selecting resources to share with a partner organization is to create a catalog to contain them.</span></span>

<span data-ttu-id="1401e-132">Een catalogus maken</span><span class="sxs-lookup"><span data-stu-id="1401e-132">To create a catalog</span></span>
1. <span data-ttu-id="1401e-133">Klik in [Azure Active Directory](https://aad.portal.azure.com)op **Identity governance**.</span><span class="sxs-lookup"><span data-stu-id="1401e-133">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="1401e-134">Klik op **catalogussen**.</span><span class="sxs-lookup"><span data-stu-id="1401e-134">Click **Catalogs**.</span></span>
3. <span data-ttu-id="1401e-135">Klik op **nieuwe catalogus**.</span><span class="sxs-lookup"><span data-stu-id="1401e-135">Click **New catalog**.</span></span>
4. <span data-ttu-id="1401e-136">Typ een naam en beschrijving voor de catalogus en zorg ervoor dat **ingeschakeld** en **ingeschakeld voor externe gebruikers** zijn ingesteld op **Ja**.</span><span class="sxs-lookup"><span data-stu-id="1401e-136">Type a name and description for the catalog and ensure that **Enabled** and **Enabled for external users** are both set to **Yes**.</span></span>
5. <span data-ttu-id="1401e-137">Klik op **Maken**.</span><span class="sxs-lookup"><span data-stu-id="1401e-137">Click **Create**.</span></span>

   ![Schermafbeelding van de pagina catalogussen in azure Active Directory Identity governance](../media/identity-governance-catalogs.png)

<span data-ttu-id="1401e-139">Nadat de catalogus is gemaakt, voegt u de SharePoint-site of het team toe dat u wilt delen met de partnerorganisatie.</span><span class="sxs-lookup"><span data-stu-id="1401e-139">Once the catalog has been created, you add the SharePoint site or team that you want to share with the partner organization.</span></span>

<span data-ttu-id="1401e-140">Resources aan een catalogus toevoegen</span><span class="sxs-lookup"><span data-stu-id="1401e-140">To add resources to a catalog</span></span>
1. <span data-ttu-id="1401e-141">Klik in azure AD Identity governance op **catalogi**en klik vervolgens op de catalogus waaraan u resources wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="1401e-141">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to add resources.</span></span>
2. <span data-ttu-id="1401e-142">Klik op **resources** en klik vervolgens op **resources toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="1401e-142">Click **Resources** and then click **Add resources**.</span></span>
3. <span data-ttu-id="1401e-143">Selecteer de teams of SharePoint-sites die u wilt opnemen in uw extranet en klik op **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="1401e-143">Select the teams or SharePoint sites that you want to include in your extranet, and then click **Add**.</span></span>

   ![Schermafbeelding van de pagina met catalogus resources in azure Active Directory Identity governance](../media/identity-governance-catalog-resource.png)

<span data-ttu-id="1401e-145">Wanneer u de bronnen hebt gedefinieerd die u wilt delen, moet u een toegangs pakket maken, waarmee het type toegang dat partner gebruikers worden verleend en het goedkeuringsproces voor nieuwe partner gebruikers die toegang vraagt, wordt gedefinieerd.</span><span class="sxs-lookup"><span data-stu-id="1401e-145">Once you've defined the resources that you want to share, the next step is to create an access package, which defines the type of access that partner users are granted and the approval process for new partner users requesting access.</span></span>

<span data-ttu-id="1401e-146">Een toegangs pakket maken</span><span class="sxs-lookup"><span data-stu-id="1401e-146">To create an access package</span></span>
1. <span data-ttu-id="1401e-147">Klik in azure AD Identity governance op **catalogi**en klik vervolgens op de catalogus waarop u een toegangs pakket wilt maken.</span><span class="sxs-lookup"><span data-stu-id="1401e-147">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to create an access package.</span></span>
2. <span data-ttu-id="1401e-148">Klik op **toegangs pakketten**en klik vervolgens op **nieuw toegangs pakket**.</span><span class="sxs-lookup"><span data-stu-id="1401e-148">Click **Access packages**, and then click **New access package**.</span></span>
3. <span data-ttu-id="1401e-149">Typ een naam en beschrijving voor het toegangs pakket en klik vervolgens op **volgende: resource rollen**.</span><span class="sxs-lookup"><span data-stu-id="1401e-149">Type a name and description for the access package, and then click **Next: Resource roles**.</span></span>
4. <span data-ttu-id="1401e-150">Kies de resources in de catalogus die u wilt gebruiken voor uw extranet.</span><span class="sxs-lookup"><span data-stu-id="1401e-150">Choose the resources from the catalog that you want to use for your extranet.</span></span>
5. <span data-ttu-id="1401e-151">Kies voor elke **resource de gebruikersrol** die u wilt verlenen aan de gastgebruikers die het extranet gebruiken.</span><span class="sxs-lookup"><span data-stu-id="1401e-151">For each resource, in the **Role** column, choose the user role you want to grant to the guest users who use the extranet.</span></span>
6. <span data-ttu-id="1401e-152">Klik op **volgende: aanvragen**.</span><span class="sxs-lookup"><span data-stu-id="1401e-152">Click **Next: Requests**.</span></span>
7. <span data-ttu-id="1401e-153">Kies onder **gebruikers die toegang kunnen aanvragen** **voor gebruikers die niet in uw adreslijst**staan.</span><span class="sxs-lookup"><span data-stu-id="1401e-153">Under **Users who can request access**, choose **For users not in your directory**.</span></span>
8. <span data-ttu-id="1401e-154">Zorg ervoor dat de optie **specifieke verbonden organisaties** is geselecteerd en klik vervolgens op **mappen toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="1401e-154">Ensure that the **Specific connected organizations** option is selected, and then click **Add directories**.</span></span>
9. <span data-ttu-id="1401e-155">Kies de verbonden organisatie die u eerder toevoegt en klik vervolgens op **selecteren**</span><span class="sxs-lookup"><span data-stu-id="1401e-155">Choose the connected organization that you add earlier, and then click **Select**</span></span>
10. <span data-ttu-id="1401e-156">Kies onder **goedkeuring**de optie **Ja** voor **Goedkeuring vereisen**.</span><span class="sxs-lookup"><span data-stu-id="1401e-156">Under **Approval**, choose **Yes** for **Require approval**.</span></span>
11. <span data-ttu-id="1401e-157">Kies onder **First beoordelaar**een van de sponsors die u eerder hebt toegevoegd of kies een specifieke gebruiker.</span><span class="sxs-lookup"><span data-stu-id="1401e-157">Under **First approver**, choose one of the sponsors that you added earlier or choose a specific user.</span></span>
12. <span data-ttu-id="1401e-158">Klik op **terugval toevoegen** en selecteer een terugval beoordelaar.</span><span class="sxs-lookup"><span data-stu-id="1401e-158">Click **Add fallback** and select a fallback approver.</span></span>
13. <span data-ttu-id="1401e-159">Kies onder **inschakelen**de optie **Ja**.</span><span class="sxs-lookup"><span data-stu-id="1401e-159">Under **Enable**, choose **Yes**.</span></span>
14. <span data-ttu-id="1401e-160">Klik op **volgende: levenscyclus**.</span><span class="sxs-lookup"><span data-stu-id="1401e-160">Click **Next: Lifecycle**.</span></span>
15. <span data-ttu-id="1401e-161">Kies de instellingen voor het verloop en toegangscontrole die u wilt gebruiken en klik op **volgende: controleren + maken**.</span><span class="sxs-lookup"><span data-stu-id="1401e-161">Choose the expiration and access review settings that you want to use, and then click **Next: Review + Create**.</span></span>
16. <span data-ttu-id="1401e-162">Controleer de instellingen en klik vervolgens op **maken**.</span><span class="sxs-lookup"><span data-stu-id="1401e-162">Review your settings, and then click **Create**.</span></span>

    ![Schermafbeelding van het scherm met toegangs pakketten in azure Active Directory Identity governance](../media/identity-governance-access-packages.png)

<span data-ttu-id="1401e-164">Als u een partner maakt met een grote organisatie, wilt u mogelijk het toegangs pakket verbergen.</span><span class="sxs-lookup"><span data-stu-id="1401e-164">If you're partnering with a large organization, you may want to hide the access package.</span></span> <span data-ttu-id="1401e-165">Als het pakket verborgen is, wordt het pakket niet in de partnerorganisatie weergegeven op de portal van *Mijn toegang* .</span><span class="sxs-lookup"><span data-stu-id="1401e-165">If the package is hidden, then users in the partner organization will not see the package on their *My Access* portal.</span></span> <span data-ttu-id="1401e-166">In plaats daarvan moet de persoon een directe koppeling sturen om zich voor het pakket te registreren.</span><span class="sxs-lookup"><span data-stu-id="1401e-166">Instead, they must be sent a direct link to sign up for the package.</span></span> <span data-ttu-id="1401e-167">Als u het toegangs pakket verbergt, kan het aantal ongepaste toegangsaanvragen verminderd en worden de beschikbare toegangs pakketten in de portal van de partnerorganisatie ook bijgehouden.</span><span class="sxs-lookup"><span data-stu-id="1401e-167">Hiding the access package can reduce the number of inappropriate access requests and can also help keep available access packages organized in the partner organization's portal.</span></span>

<span data-ttu-id="1401e-168">Een toegangs pakket instellen op verborgen</span><span class="sxs-lookup"><span data-stu-id="1401e-168">To set an access package to hidden</span></span>
1. <span data-ttu-id="1401e-169">Klik in azure AD Identity governance op **toegangs pakketten**en klik vervolgens op uw toegangs pakket.</span><span class="sxs-lookup"><span data-stu-id="1401e-169">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="1401e-170">Klik op de pagina **overzicht** op **bewerken**.</span><span class="sxs-lookup"><span data-stu-id="1401e-170">On the **Overview** page, click **Edit**.</span></span>
3. <span data-ttu-id="1401e-171">Kies onder **Eigenschappen**de optie **Ja** voor **verborgen**en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1401e-171">Under **Properties**, choose **Yes** for **Hidden**, and then click **Save**.</span></span>

   ![Schermafbeelding van het scherm Eigenschappen van het Access-pakket bewerken](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a><span data-ttu-id="1401e-173">Gebruikers van partners uitnodigen</span><span class="sxs-lookup"><span data-stu-id="1401e-173">Invite partner users</span></span>

<span data-ttu-id="1401e-174">Als u het toegangs pakket instelt op verborgen, moet u een rechtstreekse koppeling naar de partnerorganisatie verzenden, zodat ze toegang tot uw site of team kunnen aanvragen.</span><span class="sxs-lookup"><span data-stu-id="1401e-174">If you set the access package to hidden, you need to send a direct link to the partner organization so that they can request access to your site or team.</span></span>

<span data-ttu-id="1401e-175">De koppeling naar een Access-Portal zoeken</span><span class="sxs-lookup"><span data-stu-id="1401e-175">To find the access portal link</span></span>
1. <span data-ttu-id="1401e-176">Klik in azure AD Identity governance op **toegangs pakketten**en klik vervolgens op uw toegangs pakket.</span><span class="sxs-lookup"><span data-stu-id="1401e-176">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="1401e-177">Klik op de pagina **overzicht** op **naar Klembord kopiëren om** de **koppeling naar de portal voor mijn toegang**.</span><span class="sxs-lookup"><span data-stu-id="1401e-177">On the **Overview** page, click **Copy to clipboard** link for the **My Access portal link**.</span></span>

   ![Schermafbeelding van eigenschappen van het Access-pakket met de koppeling naar de portal van Access](../media/identity-governance-access-portal-link.png)

<span data-ttu-id="1401e-179">Wanneer u de koppeling hebt gekopieerd, kunt u deze delen met uw contactpersoon in de partnerorganisatie en ze kunnen het verzenden naar de gebruikers in het samenwerkingsteam.</span><span class="sxs-lookup"><span data-stu-id="1401e-179">Once you have copied the link, you can share it with your contact at the partner organization and they can send it to the users on their collaboration team.</span></span>

## <a name="see-also"></a><span data-ttu-id="1401e-180">Zie ook</span><span class="sxs-lookup"><span data-stu-id="1401e-180">See Also</span></span>

[<span data-ttu-id="1401e-181">Een beveiligde omgeving voor het delen met gasten maken</span><span class="sxs-lookup"><span data-stu-id="1401e-181">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)
