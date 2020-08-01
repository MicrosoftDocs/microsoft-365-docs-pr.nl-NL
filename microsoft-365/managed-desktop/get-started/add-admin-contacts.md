---
title: Contactpersonen voor beheer toevoegen en verifiëren in de beheerportal
description: Vertel ons met wie we contact moeten opnemen voor elk aandachtsgebied.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d8a5775d90f592aa5f64dd5f379fb37278032d87
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529801"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a><span data-ttu-id="c32c0-104">Contactpersonen voor beheer toevoegen en verifiëren in de beheerportal</span><span class="sxs-lookup"><span data-stu-id="c32c0-104">Add and verify admin contacts in the Admin portal</span></span>

<span data-ttu-id="c32c0-105">Er zijn verschillende manieren waarop microsoft Managed Desktop-service met klanten communiceert.</span><span class="sxs-lookup"><span data-stu-id="c32c0-105">There are several ways that Microsoft Managed Desktop service communicates with customers.</span></span> <span data-ttu-id="c32c0-106">Om de communicatie te stroomlijnen en ervoor te zorgen dat we contact opnemen met de juiste mensen, moet u een set beheerderscontacten bieden.</span><span class="sxs-lookup"><span data-stu-id="c32c0-106">To streamline communication and ensure we’re checking with the right people, you need to provide a set of admin contacts.</span></span> <span data-ttu-id="c32c0-107">Microsoft Managed Desktop IT Operations neemt contact op met deze personen voor problemen met het oplossen van problemen met uw tenant.</span><span class="sxs-lookup"><span data-stu-id="c32c0-107">Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c32c0-108">Mogelijk hebt u deze contactpersonen al toegevoegd in de portal Beheerder.</span><span class="sxs-lookup"><span data-stu-id="c32c0-108">You might have already added these contacts in the Admin portal.</span></span> <span data-ttu-id="c32c0-109">Als dat het geval is, moet u nu even de tijd nemen om te controleren of de lijst met contactpersonen juist is, omdat Microsoft Managed Desktop deze **moet** kunnen bereiken als zich een ernstig incident voordoet.</span><span class="sxs-lookup"><span data-stu-id="c32c0-109">If so, take a moment now to double-check that the contact list is accurate, since Microsoft Managed Desktop **must** be able to reach them if a severe incident occurs.</span></span>

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="c32c0-110">Azure Active Directory-toegang voor microsoft Managed Desktop Admin-portal</span><span class="sxs-lookup"><span data-stu-id="c32c0-110">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="c32c0-111">Microsoft Managed Desktop Admin-portal vereist dat mensen die toegang hebben tot de portal een van deze Azure Active Directory (AD)-rollen hebben:</span><span class="sxs-lookup"><span data-stu-id="c32c0-111">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>
- <span data-ttu-id="c32c0-112">Globale beheerder</span><span class="sxs-lookup"><span data-stu-id="c32c0-112">Global Administrator</span></span>
- <span data-ttu-id="c32c0-113">Intune-servicebeheerder</span><span class="sxs-lookup"><span data-stu-id="c32c0-113">Intune Service Administrator</span></span>
- <span data-ttu-id="c32c0-114">Global Reader</span><span class="sxs-lookup"><span data-stu-id="c32c0-114">Global Reader</span></span>
- <span data-ttu-id="c32c0-115">Beheerder van serviceondersteuning</span><span class="sxs-lookup"><span data-stu-id="c32c0-115">Service Support Administrator</span></span>

<span data-ttu-id="c32c0-116">De globale beheerder moet degene zijn die uw organisatie moet inschrijven in Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="c32c0-116">The Global Administrator must be the one to enroll your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="c32c0-117">Alle vijf rollen hebben dezelfde toegang binnen de portal voor beheerders om taken te initiëren en weer te geven.</span><span class="sxs-lookup"><span data-stu-id="c32c0-117">All five roles have the same access within the Admin portal to initiate and view tasks.</span></span> <span data-ttu-id="c32c0-118">Zie [Machtigingen administratorrol in Azure Active Directory voor](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)meer informatie over het toewijzen van deze rollen in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c32c0-118">For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> 

## <a name="admin-contact-areas-of-focus"></a><span data-ttu-id="c32c0-119">Aandachtsgebieden voor contactpersonen voor beheerders</span><span class="sxs-lookup"><span data-stu-id="c32c0-119">Admin contact areas of focus</span></span>

<span data-ttu-id="c32c0-120">Admin contacten moeten de beste persoon of groep die vragen kan beantwoorden en beslissingen te nemen voor verschillende gebieden van focus.</span><span class="sxs-lookup"><span data-stu-id="c32c0-120">Admin contacts should be the best person or group that can answer questions and make decisions for different areas of focus.</span></span> <span data-ttu-id="c32c0-121">**Microsoft Managed Desktop Operations neemt contact op met deze beheerderscontactpersonen voor vragen over ondersteuningsverzoeken die door de klant zijn ingediend.**</span><span class="sxs-lookup"><span data-stu-id="c32c0-121">**Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.**</span></span> <span data-ttu-id="c32c0-122">Deze beheerderscontactpersonen ontvangen meldingen voor updates voor ondersteuningsverzoeken en nieuwe berichten.</span><span class="sxs-lookup"><span data-stu-id="c32c0-122">These Admin contacts will receive notifications for support request updates and new messages.</span></span> <span data-ttu-id="c32c0-123">Deze gebieden omvatten:</span><span class="sxs-lookup"><span data-stu-id="c32c0-123">These areas include:</span></span>

<span data-ttu-id="c32c0-124">Aandachtsgebied</span><span class="sxs-lookup"><span data-stu-id="c32c0-124">Area of focus</span></span> | <span data-ttu-id="c32c0-125">Voor vragen over</span><span class="sxs-lookup"><span data-stu-id="c32c0-125">For questions about</span></span>
--- | ---
<span data-ttu-id="c32c0-126">App-verpakking</span><span class="sxs-lookup"><span data-stu-id="c32c0-126">App packaging</span></span> | <span data-ttu-id="c32c0-127">Problemen met app-verpakking oplossen</span><span class="sxs-lookup"><span data-stu-id="c32c0-127">Troubleshooting app packaging</span></span>
<span data-ttu-id="c32c0-128">Apparaten</span><span class="sxs-lookup"><span data-stu-id="c32c0-128">Devices</span></span> | <span data-ttu-id="c32c0-129">Apparaatstatus, probleemoplossing met Microsoft Managed Desktop-apparaten</span><span class="sxs-lookup"><span data-stu-id="c32c0-129">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="c32c0-130">Beveiliging</span><span class="sxs-lookup"><span data-stu-id="c32c0-130">Security</span></span> | <span data-ttu-id="c32c0-131">Problemen met beveiliging oplossen met Microsoft Managed Desktop-apparaten</span><span class="sxs-lookup"><span data-stu-id="c32c0-131">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="c32c0-132">IT-helpdesk</span><span class="sxs-lookup"><span data-stu-id="c32c0-132">IT help desk</span></span> | <span data-ttu-id="c32c0-133">in gevallen waarin ons ondersteuningspersoneel tickets voor eindgebruikers overhandigt buiten microsoft Managed Desktop-ondersteuningsgebieden</span><span class="sxs-lookup"><span data-stu-id="c32c0-133">in cases where our Support staff hands over end-user tickets outside of Microsoft Managed Desktop support areas</span></span> 
<span data-ttu-id="c32c0-134">Overige</span><span class="sxs-lookup"><span data-stu-id="c32c0-134">Other</span></span> | <span data-ttu-id="c32c0-135">Voor kwesties die niet onder andere gebieden vallen</span><span class="sxs-lookup"><span data-stu-id="c32c0-135">For issues not covered by other areas</span></span>

<span data-ttu-id="c32c0-136">**Wie u ook kiest voor deze contactpersonen, moet de kennis en autoriteit hebben om beslissingen te nemen voor uw Microsoft Managed Desktop-omgeving.**</span><span class="sxs-lookup"><span data-stu-id="c32c0-136">**Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment.**</span></span> <span data-ttu-id="c32c0-137">Wanneer u aan boord bent van uw Microsoft Managed Desktop-omgeving, wordt u gevraagd contactpersonen toe te voegen voor uw lokale helpdesk en beveiliging.</span><span class="sxs-lookup"><span data-stu-id="c32c0-137">When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="c32c0-138">Beheerderscontacten zijn vereist wanneer u [een ondersteuningsverzoek indient.](../service-description/support.md)</span><span class="sxs-lookup"><span data-stu-id="c32c0-138">Admin contacts are required when you [submit a Support request](../service-description/support.md).</span></span> <span data-ttu-id="c32c0-139">U moet een beheerderscontact hebben voor het focusgebied van het ondersteuningsverzoek.</span><span class="sxs-lookup"><span data-stu-id="c32c0-139">You’ll need to have an admin contact for the focus area of the Support request.</span></span> 

<span data-ttu-id="c32c0-140">**Beheerderscontactpersonen toevoegen**</span><span class="sxs-lookup"><span data-stu-id="c32c0-140">**To add admin contacts**</span></span>

1.  <span data-ttu-id="c32c0-141">Meld u aan bij [microsoft Managed Desktop-beheerportal](https://aka.ms/mwaasportal).</span><span class="sxs-lookup"><span data-stu-id="c32c0-141">Sign in to [Microsoft Managed Desktop admin portal](https://aka.ms/mwaasportal).</span></span> 

2.  <span data-ttu-id="c32c0-142">Selecteer onder **Ondersteuning**de optie **Beheerderscontactpersonen**.</span><span class="sxs-lookup"><span data-stu-id="c32c0-142">Under **Support**, select **Admin contacts**.</span></span> 

    ![Ondersteuningsmenu, Beheerderscontacten in de buurt van de bovenbovenhoek geselecteerd](../../media/admincontacts.png)

3. <span data-ttu-id="c32c0-144">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="c32c0-144">Select **Add**.</span></span>

    ![Admin portal, Knop Toevoegen, links van Exporteren en Vernieuwen](../../media/adminadd.png)

4.  <span data-ttu-id="c32c0-146">Selecteer een **scherpsgebied** en voer de informatie voor de contactpersoon in.</span><span class="sxs-lookup"><span data-stu-id="c32c0-146">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![de lijst met aandachtsgebieden, zoals Andere, Apps en Beveiliging](../../media/areaoffocus.png)

5. <span data-ttu-id="c32c0-148">Herhaal dit voor elk scherpstelgebied.</span><span class="sxs-lookup"><span data-stu-id="c32c0-148">Repeat for each area of focus.</span></span> 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="c32c0-149">Stappen om aan de slag te gaan met Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="c32c0-149">Steps to get started with Microsoft Managed Desktop</span></span>

1. <span data-ttu-id="c32c0-150">Beheerderscontacten toevoegen en verifiëren in de beheerportal (dit onderwerp)</span><span class="sxs-lookup"><span data-stu-id="c32c0-150">Add and verify admin contacts in the Admin portal (this topic)</span></span>
2. [<span data-ttu-id="c32c0-151">Voorwaardelijke toegang aanpassen</span><span class="sxs-lookup"><span data-stu-id="c32c0-151">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="c32c0-152">Licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="c32c0-152">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="c32c0-153">InTune-bedrijfsportal installeren op apparaten</span><span class="sxs-lookup"><span data-stu-id="c32c0-153">Install Intune Company Portal on on devices</span></span>](company-portal.md)
5. [<span data-ttu-id="c32c0-154">Enterprise State Roaming inschakelen</span><span class="sxs-lookup"><span data-stu-id="c32c0-154">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="c32c0-155">Microsoft Managed Desktop-apparaten instellen</span><span class="sxs-lookup"><span data-stu-id="c32c0-155">Set up Microsoft Managed Desktop devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="c32c0-156">Uw gebruikers voorbereiden om apparaten te gebruiken</span><span class="sxs-lookup"><span data-stu-id="c32c0-156">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="c32c0-157">Apps implementeren op apparaten</span><span class="sxs-lookup"><span data-stu-id="c32c0-157">Deploy apps to devices</span></span>](deploy-apps.md)
