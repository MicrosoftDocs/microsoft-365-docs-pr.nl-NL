---
title: Een B2B-extranet maken met beheerde gasten
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom: ''
localization_priority: Normal
f1.keywords: NOCSH
description: Meer informatie over het maken van een B2B-extranetsite of -team met beheerde gasten van een partnerorganisatie.
ms.openlocfilehash: f9b8d9326f302233ed85c9d168fdf6f343dc6cbf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904754"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a><span data-ttu-id="e2b58-103">Een B2B-extranet maken met beheerde gasten</span><span class="sxs-lookup"><span data-stu-id="e2b58-103">Create a B2B extranet with managed guests</span></span>

<span data-ttu-id="e2b58-104">U kunt [Azure Active Directory Entitlement Management gebruiken](/azure/active-directory/governance/entitlement-management-overview) om een B2B-extranet te maken om samen te werken met een partnerorganisatie die Azure Active Directory gebruikt.</span><span class="sxs-lookup"><span data-stu-id="e2b58-104">You can use [Azure Active Directory Entitlement Management](/azure/active-directory/governance/entitlement-management-overview) to create a B2B extranet to collaborate with a partner organization that uses Azure Active Directory.</span></span> <span data-ttu-id="e2b58-105">Hierdoor kunnen gebruikers zich zelf registreren voor de extranetsite of het extranetteam en toegang krijgen via een goedkeuringswerkstroom.</span><span class="sxs-lookup"><span data-stu-id="e2b58-105">This allows users to self-enroll in the extranet site or team and receive access via an approval workflow.</span></span>

<span data-ttu-id="e2b58-106">Met deze methode voor het delen van resources voor samenwerking kan de partnerorganisatie helpen bij het onderhouden en goedkeuren van de gasten aan hun kant, waardoor de belasting voor uw IT-afdeling wordt verkleind en degenen die het meest vertrouwd zijn met de samenwerkingsovereenkomst, gebruikerstoegang kunnen beheren.</span><span class="sxs-lookup"><span data-stu-id="e2b58-106">With this method of sharing resources for collaboration, the partner organization can help maintain and approve the guests on their end, reducing the burden on your IT department and allowing those most familiar with the collaboration agreement to manage user access.</span></span>

<span data-ttu-id="e2b58-107">In dit artikel worden de stappen beschreven voor het maken van een pakket met resources (in dit geval een site of team) die u met een partnerorganisatie kunt delen via een registratiemodel voor selfservicetoegang.</span><span class="sxs-lookup"><span data-stu-id="e2b58-107">This article walks through the steps to create a package of resources (in this case, a site or team) that you can share with a partner organization through a self-service access registration model.</span></span> 

<span data-ttu-id="e2b58-108">Voordat u begint, maakt u de site of het team dat u wilt delen met de partnerorganisatie en stelt u deze in voor het delen van gasten.</span><span class="sxs-lookup"><span data-stu-id="e2b58-108">Before you begin, create the site or team that you want to share with the partner organization and enable it for guest sharing.</span></span> <span data-ttu-id="e2b58-109">Zie [Samenwerken met gasten op een site](collaborate-in-site.md) of Samenwerken met gasten in een [team](collaborate-as-team.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e2b58-109">See [Collaborate with guests in a site](collaborate-in-site.md) or [Collaborate with guests in a team](collaborate-as-team.md) for more information.</span></span> <span data-ttu-id="e2b58-110">We raden u [](create-secure-guest-sharing-environment.md) ook aan een beveiligde omgeving voor het delen van gasten te bekijken voor informatie over beveiligings- en compliancefuncties die u kunt gebruiken om uw beheerbeleid te behouden wanneer u samenwerkt met gasten.</span><span class="sxs-lookup"><span data-stu-id="e2b58-110">We also recommend that you review [Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) for information about security and compliance features that you can use to help maintain your governance policies when collaborating with guests.</span></span>

## <a name="license-requirements"></a><span data-ttu-id="e2b58-111">Licentievereisten</span><span class="sxs-lookup"><span data-stu-id="e2b58-111">License requirements</span></span>

<span data-ttu-id="e2b58-112">Voor het gebruik van deze functie is een Azure AD Premium P2-licentie vereist.</span><span class="sxs-lookup"><span data-stu-id="e2b58-112">Using this feature requires an Azure AD Premium P2 license.</span></span> 

<span data-ttu-id="e2b58-113">Gespecialiseerde clouds, zoals Azure Germany en Azure China 21Vianet, zijn momenteel niet beschikbaar voor gebruik.</span><span class="sxs-lookup"><span data-stu-id="e2b58-113">Specialized clouds, such as Azure Germany and Azure China 21Vianet, are not currently available for use.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="e2b58-114">Videodemonstratie</span><span class="sxs-lookup"><span data-stu-id="e2b58-114">Video demonstration</span></span>

<span data-ttu-id="e2b58-115">In deze video worden de procedures in dit artikel beschreven.</span><span class="sxs-lookup"><span data-stu-id="e2b58-115">This video demonstrates the procedures covered in this article.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a><span data-ttu-id="e2b58-116">De partnerorganisatie verbinden</span><span class="sxs-lookup"><span data-stu-id="e2b58-116">Connect the partner organization</span></span>

<span data-ttu-id="e2b58-117">Als u gasten van een partnerorganisatie wilt uitnodigen, moet u het domein van de partner toevoegen als verbonden organisatie in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e2b58-117">In order to invite guests from a partner organization, you need to add the partner's domain as a connected organization in Azure Active Directory.</span></span>

<span data-ttu-id="e2b58-118">Een verbonden organisatie toevoegen</span><span class="sxs-lookup"><span data-stu-id="e2b58-118">To add a connected organization</span></span>
1. <span data-ttu-id="e2b58-119">Klik [in Azure Active Directory](https://aad.portal.azure.com)op **Identiteitsbeheer.**</span><span class="sxs-lookup"><span data-stu-id="e2b58-119">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="e2b58-120">Klik **op Verbonden organisaties.**</span><span class="sxs-lookup"><span data-stu-id="e2b58-120">Click **Connected organizations**.</span></span>
4. <span data-ttu-id="e2b58-121">Klik **op Verbonden organisatie toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="e2b58-121">Click **Add connected organization**.</span></span>
5. <span data-ttu-id="e2b58-122">Typ een naam en beschrijving voor de organisatie en klik vervolgens **op Volgende: Directory + domein.**</span><span class="sxs-lookup"><span data-stu-id="e2b58-122">Type a name and description for the organization, and then click **Next: Directory + domain**.</span></span>
6. <span data-ttu-id="e2b58-123">Klik **op Adreslijst + domein toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="e2b58-123">Click **Add directory + domain**.</span></span>
7. <span data-ttu-id="e2b58-124">Typ het domein voor de organisatie die u wilt verbinden en klik vervolgens op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="e2b58-124">Type the domain for the organization that you want to connect, and then click **Add**.</span></span>
8. <span data-ttu-id="e2b58-125">Klik **op Verbinding** maken en klik vervolgens op **Volgende: Sponsors.**</span><span class="sxs-lookup"><span data-stu-id="e2b58-125">Click **Connect**, and then click **Next: Sponsors**.</span></span>
9. <span data-ttu-id="e2b58-126">Voeg personen toe van uw organisatie of de organisatie die u verbindt met wie u de toegang voor gasten wilt goedkeuren.</span><span class="sxs-lookup"><span data-stu-id="e2b58-126">Add people from your organization or the organization that you're connecting to who you want to approve access for guests.</span></span>
10. <span data-ttu-id="e2b58-127">Klik op **Volgendet: Controleren + Maken**.</span><span class="sxs-lookup"><span data-stu-id="e2b58-127">Click **Next: Review + Create**.</span></span>
11. <span data-ttu-id="e2b58-128">Controleer de instellingen die u hebt gekozen en klik vervolgens op **Maken.**</span><span class="sxs-lookup"><span data-stu-id="e2b58-128">Review the settings that you've chosen and then click **Create**.</span></span>

    ![Schermafbeelding van de pagina verbonden organisaties in Azure Active Directory](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a><span data-ttu-id="e2b58-130">De resources kiezen die u wilt delen</span><span class="sxs-lookup"><span data-stu-id="e2b58-130">Choose the resources to share</span></span>

<span data-ttu-id="e2b58-131">De eerste stap bij het selecteren van resources die u wilt delen met een partnerorganisatie, is het maken van een catalogus om deze te bevatten.</span><span class="sxs-lookup"><span data-stu-id="e2b58-131">The first step in selecting resources to share with a partner organization is to create a catalog to contain them.</span></span>

<span data-ttu-id="e2b58-132">Een catalogus maken</span><span class="sxs-lookup"><span data-stu-id="e2b58-132">To create a catalog</span></span>
1. <span data-ttu-id="e2b58-133">Klik [in Azure Active Directory](https://aad.portal.azure.com)op **Identiteitsbeheer.**</span><span class="sxs-lookup"><span data-stu-id="e2b58-133">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="e2b58-134">Klik **op Catalogi.**</span><span class="sxs-lookup"><span data-stu-id="e2b58-134">Click **Catalogs**.</span></span>
3. <span data-ttu-id="e2b58-135">Klik **op Nieuwe catalogus.**</span><span class="sxs-lookup"><span data-stu-id="e2b58-135">Click **New catalog**.</span></span>
4. <span data-ttu-id="e2b58-136">Typ een naam en beschrijving voor de catalogus en zorg ervoor dat **Ingeschakeld** en Ingeschakeld voor **externe gebruikers** beide zijn ingesteld op **Ja.**</span><span class="sxs-lookup"><span data-stu-id="e2b58-136">Type a name and description for the catalog and ensure that **Enabled** and **Enabled for external users** are both set to **Yes**.</span></span>
5. <span data-ttu-id="e2b58-137">Klik op **Maken**.</span><span class="sxs-lookup"><span data-stu-id="e2b58-137">Click **Create**.</span></span>

   ![Schermafbeelding van de cataloguspagina in Azure Active Directory Identity Governance](../media/identity-governance-catalogs.png)

<span data-ttu-id="e2b58-139">Nadat de catalogus is gemaakt, voegt u de SharePoint-site of -team toe die u wilt delen met de partnerorganisatie.</span><span class="sxs-lookup"><span data-stu-id="e2b58-139">Once the catalog has been created, you add the SharePoint site or team that you want to share with the partner organization.</span></span>

<span data-ttu-id="e2b58-140">Resources toevoegen aan een catalogus</span><span class="sxs-lookup"><span data-stu-id="e2b58-140">To add resources to a catalog</span></span>
1. <span data-ttu-id="e2b58-141">Klik in Azure AD Identity Governance op **Catalogi** en klik vervolgens op de catalogus waar u resources wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="e2b58-141">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to add resources.</span></span>
2. <span data-ttu-id="e2b58-142">Klik **op Resources** en klik vervolgens op Resources **toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="e2b58-142">Click **Resources** and then click **Add resources**.</span></span>
3. <span data-ttu-id="e2b58-143">Selecteer de teams of SharePoint-sites die u wilt opnemen in uw extranet en klik vervolgens op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="e2b58-143">Select the teams or SharePoint sites that you want to include in your extranet, and then click **Add**.</span></span>

   ![Schermafbeelding van de pagina catalogusresources in Azure Active Directory Identity Governance](../media/identity-governance-catalog-resource.png)

<span data-ttu-id="e2b58-145">Nadat u de resources hebt gedefinieerd die u wilt delen, is de volgende stap het maken van een access-pakket, waarin het type toegang wordt gedefinieerd dat partnergebruikers worden verleend en het goedkeuringsproces voor nieuwe partnergebruikers die toegang aanvragen.</span><span class="sxs-lookup"><span data-stu-id="e2b58-145">Once you've defined the resources that you want to share, the next step is to create an access package, which defines the type of access that partner users are granted and the approval process for new partner users requesting access.</span></span>

<span data-ttu-id="e2b58-146">Een toegangspakket maken</span><span class="sxs-lookup"><span data-stu-id="e2b58-146">To create an access package</span></span>
1. <span data-ttu-id="e2b58-147">Klik in Azure AD Identity Governance op **Catalogi** en klik vervolgens op de catalogus waar u een access-pakket wilt maken.</span><span class="sxs-lookup"><span data-stu-id="e2b58-147">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to create an access package.</span></span>
2. <span data-ttu-id="e2b58-148">Klik **op Access-pakketten** en klik vervolgens op **Nieuw toegangspakket.**</span><span class="sxs-lookup"><span data-stu-id="e2b58-148">Click **Access packages**, and then click **New access package**.</span></span>
3. <span data-ttu-id="e2b58-149">Typ een naam en beschrijving voor het access-pakket en klik vervolgens **op Volgende: Resourcerollen.**</span><span class="sxs-lookup"><span data-stu-id="e2b58-149">Type a name and description for the access package, and then click **Next: Resource roles**.</span></span>
4. <span data-ttu-id="e2b58-150">Kies de resources in de catalogus die u wilt gebruiken voor uw extranet.</span><span class="sxs-lookup"><span data-stu-id="e2b58-150">Choose the resources from the catalog that you want to use for your extranet.</span></span>
5. <span data-ttu-id="e2b58-151">Kies voor elke resource in **de** kolom Rol de gebruikersrol die u wilt verlenen aan de gasten die het extranet gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e2b58-151">For each resource, in the **Role** column, choose the user role you want to grant to the guests who use the extranet.</span></span>
6. <span data-ttu-id="e2b58-152">Klik **op Volgende: Aanvragen.**</span><span class="sxs-lookup"><span data-stu-id="e2b58-152">Click **Next: Requests**.</span></span>
7. <span data-ttu-id="e2b58-153">Kies **onder Gebruikers die toegang kunnen aanvragen** de optie Voor gebruikers die niet in uw **adreslijst staan.**</span><span class="sxs-lookup"><span data-stu-id="e2b58-153">Under **Users who can request access**, choose **For users not in your directory**.</span></span>
8. <span data-ttu-id="e2b58-154">Controleer of de **optie Specifieke verbonden organisaties** is geselecteerd en klik vervolgens op **Directories toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="e2b58-154">Ensure that the **Specific connected organizations** option is selected, and then click **Add directories**.</span></span>
9. <span data-ttu-id="e2b58-155">Kies de verbonden organisatie die u eerder hebt toevoegen en klik vervolgens op **Selecteren**</span><span class="sxs-lookup"><span data-stu-id="e2b58-155">Choose the connected organization that you add earlier, and then click **Select**</span></span>
10. <span data-ttu-id="e2b58-156">Kies **onder Goedkeuring** de optie **Ja** voor **Goedkeuring vereisen.**</span><span class="sxs-lookup"><span data-stu-id="e2b58-156">Under **Approval**, choose **Yes** for **Require approval**.</span></span>
11. <span data-ttu-id="e2b58-157">Kies **onder Eerste goedkeurder** een van de sponsors die u eerder hebt toegevoegd of kies een specifieke gebruiker.</span><span class="sxs-lookup"><span data-stu-id="e2b58-157">Under **First approver**, choose one of the sponsors that you added earlier or choose a specific user.</span></span>
12. <span data-ttu-id="e2b58-158">Klik **op Terugval toevoegen** en selecteer een fallback-goedkeurder.</span><span class="sxs-lookup"><span data-stu-id="e2b58-158">Click **Add fallback** and select a fallback approver.</span></span>
13. <span data-ttu-id="e2b58-159">Kies **onder Inschakelen** de optie **Ja.**</span><span class="sxs-lookup"><span data-stu-id="e2b58-159">Under **Enable**, choose **Yes**.</span></span>
14. <span data-ttu-id="e2b58-160">Klik **op Volgende: Levenscyclus.**</span><span class="sxs-lookup"><span data-stu-id="e2b58-160">Click **Next: Lifecycle**.</span></span>
15. <span data-ttu-id="e2b58-161">Kies de instellingen voor verloop en toegangsbeoordeling die u wilt gebruiken en klik vervolgens op **Volgende: Controleren + Maken.**</span><span class="sxs-lookup"><span data-stu-id="e2b58-161">Choose the expiration and access review settings that you want to use, and then click **Next: Review + Create**.</span></span>
16. <span data-ttu-id="e2b58-162">Controleer de instellingen en klik vervolgens op **Maken.**</span><span class="sxs-lookup"><span data-stu-id="e2b58-162">Review your settings, and then click **Create**.</span></span>

    ![Schermafbeelding van het scherm access packages in Azure Active Directory Identity Governance](../media/identity-governance-access-packages.png)

<span data-ttu-id="e2b58-164">Als u een partnerschap aan gaat met een grote organisatie, kunt u het toegangspakket verbergen.</span><span class="sxs-lookup"><span data-stu-id="e2b58-164">If you're partnering with a large organization, you may want to hide the access package.</span></span> <span data-ttu-id="e2b58-165">Als het pakket is verborgen, zien gebruikers in de partnerorganisatie het pakket niet in hun *My Access-portal.*</span><span class="sxs-lookup"><span data-stu-id="e2b58-165">If the package is hidden, then users in the partner organization will not see the package on their *My Access* portal.</span></span> <span data-ttu-id="e2b58-166">In plaats daarvan moeten ze een directe koppeling ontvangen om zich aan te melden voor het pakket.</span><span class="sxs-lookup"><span data-stu-id="e2b58-166">Instead, they must be sent a direct link to sign up for the package.</span></span> <span data-ttu-id="e2b58-167">Het verbergen van het toegangspakket kan het aantal ongepaste toegangsaanvragen verminderen en kan ook helpen om beschikbare toegangspakketten georganiseerd te houden in de portal van de partnerorganisatie.</span><span class="sxs-lookup"><span data-stu-id="e2b58-167">Hiding the access package can reduce the number of inappropriate access requests and can also help keep available access packages organized in the partner organization's portal.</span></span>

<span data-ttu-id="e2b58-168">Een toegangspakket instellen op verborgen</span><span class="sxs-lookup"><span data-stu-id="e2b58-168">To set an access package to hidden</span></span>
1. <span data-ttu-id="e2b58-169">Klik in Azure AD Identity Governance op **Access-pakketten** en klik vervolgens op uw toegangspakket.</span><span class="sxs-lookup"><span data-stu-id="e2b58-169">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="e2b58-170">Klik op **de pagina** Overzicht op **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="e2b58-170">On the **Overview** page, click **Edit**.</span></span>
3. <span data-ttu-id="e2b58-171">Kies **onder Eigenschappen** de optie **Ja** voor **verborgen** en klik vervolgens op **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="e2b58-171">Under **Properties**, choose **Yes** for **Hidden**, and then click **Save**.</span></span>

   ![Schermafbeelding van een scherm met eigenschappen van een bewerkingstoegangspakket](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a><span data-ttu-id="e2b58-173">Partnergebruikers uitnodigen</span><span class="sxs-lookup"><span data-stu-id="e2b58-173">Invite partner users</span></span>

<span data-ttu-id="e2b58-174">Als u het toegangspakket hebt ingesteld op verborgen, moet u een directe koppeling naar de partnerorganisatie verzenden, zodat deze toegang tot uw site of team kan aanvragen.</span><span class="sxs-lookup"><span data-stu-id="e2b58-174">If you set the access package to hidden, you need to send a direct link to the partner organization so that they can request access to your site or team.</span></span>

<span data-ttu-id="e2b58-175">De koppeling toegangsportal zoeken</span><span class="sxs-lookup"><span data-stu-id="e2b58-175">To find the access portal link</span></span>
1. <span data-ttu-id="e2b58-176">Klik in Azure AD Identity Governance op **Access-pakketten** en klik vervolgens op uw toegangspakket.</span><span class="sxs-lookup"><span data-stu-id="e2b58-176">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="e2b58-177">Klik op **de** pagina Overzicht op **Koppeling kopiëren naar klembord** voor de koppeling **Mijn Access-portal.**</span><span class="sxs-lookup"><span data-stu-id="e2b58-177">On the **Overview** page, click **Copy to clipboard** link for the **My Access portal link**.</span></span>

   ![Schermafbeelding van eigenschappen van access package met access portal link](../media/identity-governance-access-portal-link.png)

<span data-ttu-id="e2b58-179">Nadat u de koppeling hebt gekopieerd, kunt u deze delen met uw contactpersoon bij de partnerorganisatie en deze verzenden naar de gebruikers in hun samenwerkingsteam.</span><span class="sxs-lookup"><span data-stu-id="e2b58-179">Once you have copied the link, you can share it with your contact at the partner organization and they can send it to the users on their collaboration team.</span></span>

## <a name="see-also"></a><span data-ttu-id="e2b58-180">Zie ook</span><span class="sxs-lookup"><span data-stu-id="e2b58-180">See Also</span></span>

[<span data-ttu-id="e2b58-181">Een beveiligde omgeving voor het delen met gasten maken</span><span class="sxs-lookup"><span data-stu-id="e2b58-181">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)