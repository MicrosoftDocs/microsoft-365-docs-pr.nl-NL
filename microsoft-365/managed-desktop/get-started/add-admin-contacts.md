---
title: Contactpersonen voor beheer toevoegen en verifiëren in de beheerportal
description: Laat ons weten met wie we contact moeten opnemen voor elk focusgebied.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 18823db8ca8d4bfa82b8ab6265ee8a0902a13e79
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925890"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a><span data-ttu-id="d6630-104">Contactpersonen voor beheer toevoegen en verifiëren in de beheerportal</span><span class="sxs-lookup"><span data-stu-id="d6630-104">Add and verify admin contacts in the Admin portal</span></span>

<span data-ttu-id="d6630-105">Er zijn verschillende manieren waarop Microsoft Managed Desktop met klanten communiceert.</span><span class="sxs-lookup"><span data-stu-id="d6630-105">There are several ways that Microsoft Managed Desktop service communicates with customers.</span></span> <span data-ttu-id="d6630-106">Om de communicatie te stroomlijnen en ervoor te zorgen dat we contact hebben met de juiste personen, moet u een set beheerderscontacten verstrekken.</span><span class="sxs-lookup"><span data-stu-id="d6630-106">To streamline communication and ensure we’re checking with the right people, you need to provide a set of admin contacts.</span></span> <span data-ttu-id="d6630-107">Microsoft Managed Desktop IT Operations neemt contact op met deze personen voor hulp bij het oplossen van problemen met uw tenant.</span><span class="sxs-lookup"><span data-stu-id="d6630-107">Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d6630-108">Mogelijk hebt u deze contactpersonen al toegevoegd aan de beheerportal.</span><span class="sxs-lookup"><span data-stu-id="d6630-108">You might have already added these contacts in the Admin portal.</span></span> <span data-ttu-id="d6630-109">Als dat het geval is, kunt u nu even controleren of  de lijst met contactpersonen juist is, omdat Microsoft Managed Desktop moet kunnen bereiken als er een ernstig incident optreedt.</span><span class="sxs-lookup"><span data-stu-id="d6630-109">If so, take a moment now to double-check that the contact list is accurate, since Microsoft Managed Desktop **must** be able to reach them if a severe incident occurs.</span></span>

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="d6630-110">Azure Active Directory toegang voor Microsoft Managed Desktop-beheerportal</span><span class="sxs-lookup"><span data-stu-id="d6630-110">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="d6630-111">Microsoft Managed Desktop Beheerdersportal vereist dat personen die toegang hebben tot de portal een van deze Azure Active Directory (AD) rollen hebben:</span><span class="sxs-lookup"><span data-stu-id="d6630-111">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>
- <span data-ttu-id="d6630-112">Globale beheerder</span><span class="sxs-lookup"><span data-stu-id="d6630-112">Global Administrator</span></span>
- <span data-ttu-id="d6630-113">Intune-servicebeheerder</span><span class="sxs-lookup"><span data-stu-id="d6630-113">Intune Service Administrator</span></span>
- <span data-ttu-id="d6630-114">Algemene lezer</span><span class="sxs-lookup"><span data-stu-id="d6630-114">Global Reader</span></span>
- <span data-ttu-id="d6630-115">Serviceondersteuningsbeheerder</span><span class="sxs-lookup"><span data-stu-id="d6630-115">Service Support Administrator</span></span>

<span data-ttu-id="d6630-116">De globale beheerder moet degene zijn die uw organisatie inschrijft voor Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="d6630-116">The Global Administrator must be the one to enroll your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="d6630-117">Alle vijf rollen hebben dezelfde toegang binnen de beheerportal om taken te starten en weer te geven.</span><span class="sxs-lookup"><span data-stu-id="d6630-117">All five roles have the same access within the Admin portal to initiate and view tasks.</span></span> <span data-ttu-id="d6630-118">Zie Beheerdersrolmachtigingen in Azure Active Directory voor meer informatie over het toewijzen van [deze rollen in](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d6630-118">For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> 

## <a name="admin-contact-areas-of-focus"></a><span data-ttu-id="d6630-119">Contactgebieden van beheerder met focus</span><span class="sxs-lookup"><span data-stu-id="d6630-119">Admin contact areas of focus</span></span>

<span data-ttu-id="d6630-120">Beheerderscontacten moeten de beste persoon of groep zijn die vragen kan beantwoorden en beslissingen kunnen nemen voor verschillende aandachtsgebieden.</span><span class="sxs-lookup"><span data-stu-id="d6630-120">Admin contacts should be the best person or group that can answer questions and make decisions for different areas of focus.</span></span> <span data-ttu-id="d6630-121">**Microsoft Managed Desktop Operations neemt contact op met deze beheerderscontacten voor vragen over ondersteuningsaanvragen die door de klant zijn ingediend.**</span><span class="sxs-lookup"><span data-stu-id="d6630-121">**Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.**</span></span> <span data-ttu-id="d6630-122">Deze beheerderscontacten ontvangen meldingen voor ondersteuningsverzoekupdates en nieuwe berichten.</span><span class="sxs-lookup"><span data-stu-id="d6630-122">These Admin contacts will receive notifications for support request updates and new messages.</span></span> <span data-ttu-id="d6630-123">Deze gebieden zijn:</span><span class="sxs-lookup"><span data-stu-id="d6630-123">These areas include:</span></span>

<span data-ttu-id="d6630-124">Focusgebied</span><span class="sxs-lookup"><span data-stu-id="d6630-124">Area of focus</span></span> | <span data-ttu-id="d6630-125">Voor vragen over</span><span class="sxs-lookup"><span data-stu-id="d6630-125">For questions about</span></span>
--- | ---
<span data-ttu-id="d6630-126">App-verpakking</span><span class="sxs-lookup"><span data-stu-id="d6630-126">App packaging</span></span> | <span data-ttu-id="d6630-127">App-verpakking oplossen</span><span class="sxs-lookup"><span data-stu-id="d6630-127">Troubleshooting app packaging</span></span>
<span data-ttu-id="d6630-128">Apparaten</span><span class="sxs-lookup"><span data-stu-id="d6630-128">Devices</span></span> | <span data-ttu-id="d6630-129">Apparaattoestand, probleemoplossing met Microsoft Managed Desktop apparaten</span><span class="sxs-lookup"><span data-stu-id="d6630-129">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="d6630-130">Beveiliging</span><span class="sxs-lookup"><span data-stu-id="d6630-130">Security</span></span> | <span data-ttu-id="d6630-131">Beveiligingsproblemen met Microsoft Managed Desktop oplossen</span><span class="sxs-lookup"><span data-stu-id="d6630-131">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="d6630-132">IT-helpdesk</span><span class="sxs-lookup"><span data-stu-id="d6630-132">IT help desk</span></span> | <span data-ttu-id="d6630-133">in gevallen waarin ons ondersteuningspersoneel gebruikerstickets overhandt buiten Microsoft Managed Desktop ondersteuningsgebieden</span><span class="sxs-lookup"><span data-stu-id="d6630-133">in cases where our Support staff hands over user tickets outside of Microsoft Managed Desktop support areas</span></span> 
<span data-ttu-id="d6630-134">Overige</span><span class="sxs-lookup"><span data-stu-id="d6630-134">Other</span></span> | <span data-ttu-id="d6630-135">Voor problemen die niet onder andere gebieden vallen</span><span class="sxs-lookup"><span data-stu-id="d6630-135">For issues not covered by other areas</span></span>

<span data-ttu-id="d6630-136">**Wie u ook kiest voor deze contactpersonen, moet de kennis en bevoegdheid hebben om beslissingen te nemen voor uw Microsoft Managed Desktop omgeving.**</span><span class="sxs-lookup"><span data-stu-id="d6630-136">**Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment.**</span></span> <span data-ttu-id="d6630-137">Wanneer u uw Microsoft Managed Desktop invoegt, wordt u gevraagd contactpersonen toe te voegen voor uw lokale helpdesk en beveiliging.</span><span class="sxs-lookup"><span data-stu-id="d6630-137">When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="d6630-138">Beheerderscontacten zijn vereist wanneer u [een ondersteuningsaanvraag indient.](../service-description/support.md)</span><span class="sxs-lookup"><span data-stu-id="d6630-138">Admin contacts are required when you [submit a Support request](../service-description/support.md).</span></span> <span data-ttu-id="d6630-139">U moet een beheerdercontactcontact hebben voor het focusgebied van de ondersteuningsaanvraag.</span><span class="sxs-lookup"><span data-stu-id="d6630-139">You’ll need to have an admin contact for the focus area of the Support request.</span></span> 

<span data-ttu-id="d6630-140">**Beheerderscontacten toevoegen**</span><span class="sxs-lookup"><span data-stu-id="d6630-140">**To add admin contacts**</span></span>

1.  <span data-ttu-id="d6630-141">Meld u aan [bij Microsoft Managed Desktop beheerportal.](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="d6630-141">Sign in to [Microsoft Managed Desktop admin portal](https://aka.ms/mwaasportal).</span></span> 

2.  <span data-ttu-id="d6630-142">Selecteer **onder Ondersteuning** de optie Contactpersonen **beheren.**</span><span class="sxs-lookup"><span data-stu-id="d6630-142">Under **Support**, select **Admin contacts**.</span></span> 

    ![Ondersteuningsmenu, Contactpersonen beheren in de buurt van de bovenste geselecteerde](../../media/admincontacts.png)

3. <span data-ttu-id="d6630-144">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="d6630-144">Select **Add**.</span></span>

    ![Beheerportal, knop Toevoegen, links van Exporteren en vernieuwen](../../media/adminadd.png)

4.  <span data-ttu-id="d6630-146">Selecteer een **gebied met focus** en voer de gegevens voor de contactpersoon in.</span><span class="sxs-lookup"><span data-stu-id="d6630-146">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![de lijst met focusgebieden, zoals Overige, Apps en Beveiliging](../../media/areaoffocus.png)

5. <span data-ttu-id="d6630-148">Herhaal dit voor elk focusgebied.</span><span class="sxs-lookup"><span data-stu-id="d6630-148">Repeat for each area of focus.</span></span> 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="d6630-149">Stappen om aan de slag te gaan met Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="d6630-149">Steps to get started with Microsoft Managed Desktop</span></span>

1. <span data-ttu-id="d6630-150">Beheerderscontacten toevoegen en verifiëren in de beheerportal (dit onderwerp)</span><span class="sxs-lookup"><span data-stu-id="d6630-150">Add and verify admin contacts in the Admin portal (this topic)</span></span>
2. [<span data-ttu-id="d6630-151">Voorwaardelijke toegang aanpassen</span><span class="sxs-lookup"><span data-stu-id="d6630-151">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="d6630-152">Licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="d6630-152">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="d6630-153">InTune-bedrijfsportal installeren op apparaten</span><span class="sxs-lookup"><span data-stu-id="d6630-153">Install Intune Company Portal on on devices</span></span>](company-portal.md)
5. [<span data-ttu-id="d6630-154">Enterprise State Roaming inschakelen</span><span class="sxs-lookup"><span data-stu-id="d6630-154">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="d6630-155">Microsoft Managed Desktop-apparaten instellen</span><span class="sxs-lookup"><span data-stu-id="d6630-155">Set up Microsoft Managed Desktop devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="d6630-156">Uw gebruikers voorbereiden om apparaten te gebruiken</span><span class="sxs-lookup"><span data-stu-id="d6630-156">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="d6630-157">Apps implementeren op apparaten</span><span class="sxs-lookup"><span data-stu-id="d6630-157">Deploy apps to devices</span></span>](deploy-apps.md)