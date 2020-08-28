---
title: Contactpersonen voor beheer toevoegen en verifiëren in de beheerportal
description: Vertel ons wie u contact moet opnemen voor elk gebied van de focus.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8b287200b1c94ff350f7ba00cf0c4e6bc1b4a71f
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289259"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a><span data-ttu-id="31ef0-104">Contactpersonen voor beheer toevoegen en verifiëren in de beheerportal</span><span class="sxs-lookup"><span data-stu-id="31ef0-104">Add and verify admin contacts in the Admin portal</span></span>

<span data-ttu-id="31ef0-105">U kunt op verschillende manieren communiceren met klanten via Microsoft beheerde bureaublad service.</span><span class="sxs-lookup"><span data-stu-id="31ef0-105">There are several ways that Microsoft Managed Desktop service communicates with customers.</span></span> <span data-ttu-id="31ef0-106">Voor het stroomlijnen van de communicatie en zorg ervoor dat u de juiste personen controleert, moet u een reeks beheerders contacten opgeven.</span><span class="sxs-lookup"><span data-stu-id="31ef0-106">To streamline communication and ensure we’re checking with the right people, you need to provide a set of admin contacts.</span></span> <span data-ttu-id="31ef0-107">DOOR Microsoft beheerde bureaublad activiteiten wordt contact opgenomen met deze personen voor hulp bij het oplossen van problemen met de Tenant.</span><span class="sxs-lookup"><span data-stu-id="31ef0-107">Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="31ef0-108">U hebt deze contactpersonen al toegevoegd aan de beheerportal.</span><span class="sxs-lookup"><span data-stu-id="31ef0-108">You might have already added these contacts in the Admin portal.</span></span> <span data-ttu-id="31ef0-109">Als dit het geval is, kunt u nu even kijken of de lijst met contactpersonen nauwkeurig is, omdat Microsoft Managed Desktop de verbinding **moet** kunnen bereiken als er een ernstig incident plaatsvindt.</span><span class="sxs-lookup"><span data-stu-id="31ef0-109">If so, take a moment now to double-check that the contact list is accurate, since Microsoft Managed Desktop **must** be able to reach them if a severe incident occurs.</span></span>

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="31ef0-110">Azure Active Directory Access voor de beheerde portal voor Microsoft-bureaubladbeheer</span><span class="sxs-lookup"><span data-stu-id="31ef0-110">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="31ef0-111">De portal van de beheerde bureaublad beheerder van Microsoft wordt vereist dat personen die toegang hebben tot de portal een van deze Azure Active Directory (AD) rollen hebben.</span><span class="sxs-lookup"><span data-stu-id="31ef0-111">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>
- <span data-ttu-id="31ef0-112">Globale beheerder</span><span class="sxs-lookup"><span data-stu-id="31ef0-112">Global Administrator</span></span>
- <span data-ttu-id="31ef0-113">InTune-service beheerder</span><span class="sxs-lookup"><span data-stu-id="31ef0-113">Intune Service Administrator</span></span>
- <span data-ttu-id="31ef0-114">Algemene lezer</span><span class="sxs-lookup"><span data-stu-id="31ef0-114">Global Reader</span></span>
- <span data-ttu-id="31ef0-115">Service ondersteuningsbeheerder</span><span class="sxs-lookup"><span data-stu-id="31ef0-115">Service Support Administrator</span></span>

<span data-ttu-id="31ef0-116">De hoofdbeheerder moet de naam van de globale beheerder zijn om uw organisatie in te schrijven op Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="31ef0-116">The Global Administrator must be the one to enroll your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="31ef0-117">Alle vijf rollen hebben dezelfde toegang binnen de beheerportal om taken te initiëren en weer te geven.</span><span class="sxs-lookup"><span data-stu-id="31ef0-117">All five roles have the same access within the Admin portal to initiate and view tasks.</span></span> <span data-ttu-id="31ef0-118">Zie [machtigingen voor beheerdersrollen in azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)voor meer informatie over het toewijzen van deze rollen in azure AD.</span><span class="sxs-lookup"><span data-stu-id="31ef0-118">For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> 

## <a name="admin-contact-areas-of-focus"></a><span data-ttu-id="31ef0-119">Beheerders bereiken van focus</span><span class="sxs-lookup"><span data-stu-id="31ef0-119">Admin contact areas of focus</span></span>

<span data-ttu-id="31ef0-120">Contactpersonen beheerder moeten de beste persoon of groep zijn die vragen kan beantwoorden en besluiten te nemen voor verschillende gebieden van de focus.</span><span class="sxs-lookup"><span data-stu-id="31ef0-120">Admin contacts should be the best person or group that can answer questions and make decisions for different areas of focus.</span></span> <span data-ttu-id="31ef0-121">**Door Microsoft beheerde bureaublad activiteiten wordt contact opgenomen met deze beheerders contactpersonen voor vragen met ondersteuningsverzoeken die door de klant zijn ingediend.**</span><span class="sxs-lookup"><span data-stu-id="31ef0-121">**Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.**</span></span> <span data-ttu-id="31ef0-122">Deze beheerders contactpersonen ontvangen een melding voor updates van ondersteuningsaanvragen en nieuwe berichten.</span><span class="sxs-lookup"><span data-stu-id="31ef0-122">These Admin contacts will receive notifications for support request updates and new messages.</span></span> <span data-ttu-id="31ef0-123">Dit gebied omvat:</span><span class="sxs-lookup"><span data-stu-id="31ef0-123">These areas include:</span></span>

<span data-ttu-id="31ef0-124">Gebied met focus</span><span class="sxs-lookup"><span data-stu-id="31ef0-124">Area of focus</span></span> | <span data-ttu-id="31ef0-125">Voor vragen over</span><span class="sxs-lookup"><span data-stu-id="31ef0-125">For questions about</span></span>
--- | ---
<span data-ttu-id="31ef0-126">App-verpakking</span><span class="sxs-lookup"><span data-stu-id="31ef0-126">App packaging</span></span> | <span data-ttu-id="31ef0-127">App-verpakking oplossen</span><span class="sxs-lookup"><span data-stu-id="31ef0-127">Troubleshooting app packaging</span></span>
<span data-ttu-id="31ef0-128">Apparaten</span><span class="sxs-lookup"><span data-stu-id="31ef0-128">Devices</span></span> | <span data-ttu-id="31ef0-129">Apparaatstatusverklaring, probleemoplossing met door Microsoft beheerde bureaublad apparaten</span><span class="sxs-lookup"><span data-stu-id="31ef0-129">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="31ef0-130">Beveiliging</span><span class="sxs-lookup"><span data-stu-id="31ef0-130">Security</span></span> | <span data-ttu-id="31ef0-131">Beveiligingsproblemen met door Microsoft beheerde bureaublad apparaten oplossen</span><span class="sxs-lookup"><span data-stu-id="31ef0-131">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="31ef0-132">IT-helpdesk</span><span class="sxs-lookup"><span data-stu-id="31ef0-132">IT help desk</span></span> | <span data-ttu-id="31ef0-133">Wanneer onze ondersteuningsmedewerkers de afdeling ondersteunings gebieden van gebruikers buiten Microsoft beheerde bureaublad ondersteuning bevinden</span><span class="sxs-lookup"><span data-stu-id="31ef0-133">in cases where our Support staff hands over user tickets outside of Microsoft Managed Desktop support areas</span></span> 
<span data-ttu-id="31ef0-134">Overige</span><span class="sxs-lookup"><span data-stu-id="31ef0-134">Other</span></span> | <span data-ttu-id="31ef0-135">Voor problemen die niet worden bedekt door andere gebieden</span><span class="sxs-lookup"><span data-stu-id="31ef0-135">For issues not covered by other areas</span></span>

<span data-ttu-id="31ef0-136">**Degene die u voor deze contactpersonen kiest, moet de kennis en bevoegdheid hebben om beslissingen te kunnen nemen voor de Microsoft-beheerde bureaubladomgeving.**</span><span class="sxs-lookup"><span data-stu-id="31ef0-136">**Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment.**</span></span> <span data-ttu-id="31ef0-137">Wanneer u de beheerde bureaubladomgeving van Microsoft ophaalt, wordt u gevraagd contactpersonen voor uw lokale helpdesk en beveiliging toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="31ef0-137">When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="31ef0-138">Beheerders contactpersonen zijn vereist wanneer u [een ondersteuningsaanvraag indient](../service-description/support.md).</span><span class="sxs-lookup"><span data-stu-id="31ef0-138">Admin contacts are required when you [submit a Support request](../service-description/support.md).</span></span> <span data-ttu-id="31ef0-139">U moet een beheerders contact hebben voor het focus gebied van het ondersteuningsverzoek.</span><span class="sxs-lookup"><span data-stu-id="31ef0-139">You’ll need to have an admin contact for the focus area of the Support request.</span></span> 

<span data-ttu-id="31ef0-140">**Beheerders contactpersonen toevoegen**</span><span class="sxs-lookup"><span data-stu-id="31ef0-140">**To add admin contacts**</span></span>

1.  <span data-ttu-id="31ef0-141">Meld u aan bij de [Portal van Microsoft beheerde bureaubladbeheer](https://aka.ms/mwaasportal).</span><span class="sxs-lookup"><span data-stu-id="31ef0-141">Sign in to [Microsoft Managed Desktop admin portal](https://aka.ms/mwaasportal).</span></span> 

2.  <span data-ttu-id="31ef0-142">Selecteer onder **ondersteuning**de optie **beheerder contactpersonen**.</span><span class="sxs-lookup"><span data-stu-id="31ef0-142">Under **Support**, select **Admin contacts**.</span></span> 

    ![Ondersteunings menu, contactpersonen van beheerder, bijna bovenaan geselecteerd](../../media/admincontacts.png)

3. <span data-ttu-id="31ef0-144">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="31ef0-144">Select **Add**.</span></span>

    ![Beheerportal, knop toevoegen links van exporteren en vernieuwen](../../media/adminadd.png)

4.  <span data-ttu-id="31ef0-146">Selecteer een **gebied met de focus** en voer de gegevens voor de contactpersoon in.</span><span class="sxs-lookup"><span data-stu-id="31ef0-146">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![de lijst met de focus gebieden, zoals andere, apps en beveiliging](../../media/areaoffocus.png)

5. <span data-ttu-id="31ef0-148">Herhaal dit voor elk gebied van de focus.</span><span class="sxs-lookup"><span data-stu-id="31ef0-148">Repeat for each area of focus.</span></span> 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="31ef0-149">Stappen om aan de slag te gaan met Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="31ef0-149">Steps to get started with Microsoft Managed Desktop</span></span>

1. <span data-ttu-id="31ef0-150">Beheerders contactpersonen toevoegen en controleren in de beheerportal (dit onderwerp)</span><span class="sxs-lookup"><span data-stu-id="31ef0-150">Add and verify admin contacts in the Admin portal (this topic)</span></span>
2. [<span data-ttu-id="31ef0-151">Voorwaardelijke toegang aanpassen</span><span class="sxs-lookup"><span data-stu-id="31ef0-151">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="31ef0-152">Licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="31ef0-152">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="31ef0-153">InTune-bedrijfsportal installeren op apparaten</span><span class="sxs-lookup"><span data-stu-id="31ef0-153">Install Intune Company Portal on on devices</span></span>](company-portal.md)
5. [<span data-ttu-id="31ef0-154">Enterprise State Roaming inschakelen</span><span class="sxs-lookup"><span data-stu-id="31ef0-154">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="31ef0-155">Microsoft Managed Desktop-apparaten instellen</span><span class="sxs-lookup"><span data-stu-id="31ef0-155">Set up Microsoft Managed Desktop devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="31ef0-156">Uw gebruikers voorbereiden om apparaten te gebruiken</span><span class="sxs-lookup"><span data-stu-id="31ef0-156">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="31ef0-157">Apps implementeren op apparaten</span><span class="sxs-lookup"><span data-stu-id="31ef0-157">Deploy apps to devices</span></span>](deploy-apps.md)
