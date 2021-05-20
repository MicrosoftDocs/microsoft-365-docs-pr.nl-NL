---
title: Instellingen voor Office-scripts beheren
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Meer informatie over het beheren van Office scriptsinstellingen voor gebruikers in uw organisatie.
ms.openlocfilehash: e0cb52c4a8f48ff2310c83ffce61e08a0236ed59
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572307"
---
# <a name="manage-office-scripts-settings"></a><span data-ttu-id="585f5-103">Instellingen voor Office-scripts beheren</span><span class="sxs-lookup"><span data-stu-id="585f5-103">Manage Office Scripts settings</span></span>

<span data-ttu-id="585f5-104">[met Office Scripts](/office/dev/scripts)kunnen gebruikers taken automatiseren door scripts op te nemen, te bewerken en uit te voeren in Excel op het web.</span><span class="sxs-lookup"><span data-stu-id="585f5-104">[Office Scripts](/office/dev/scripts)‎ allows users to automate tasks by recording, editing, and running scripts in ‎Excel‎ on the web.</span></span> <span data-ttu-id="585f5-105">Office Scripts werken met Power Automate en gebruikers voeren scripts uit op werkmappen met behulp van de connector Excel Online (Business).</span><span class="sxs-lookup"><span data-stu-id="585f5-105">‎Office Scripts‎ works with Power Automate, and users run scripts on workbooks by using the ‎Excel‎ Online (Business) connector.</span></span> <span data-ttu-id="585f5-106">Microsoft 365 beheerders kunnen Office scripts beheren vanuit het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="585f5-106">Microsoft 365 admins can manage Office Scripts settings from the Microsoft 365 admin center.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="585f5-107">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="585f5-107">Before you begin</span></span>

- <span data-ttu-id="585f5-108">Als u Office scripts wilt beheren, moet u een globale beheerder zijn. Zie [Beheerdersrollen voor](../add-users/about-admin-roles.md)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="585f5-108">To manage Office Scripts settings, you must be a Global admin. For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="585f5-109">Zorg ervoor dat gebruikers in uw organisatie een geldige licentie hebben voor een Microsoft 365 of Office 365 commercieel of EDU-abonnement dat toegang bevat tot Office bureaublad-apps, zoals een van de volgende abonnementen:</span><span class="sxs-lookup"><span data-stu-id="585f5-109">Ensure users in your organization have a valid license for a Microsoft 365 or Office 365 commercial or EDU plan that includes access to Office desktop apps, such as one of the following plans:</span></span>

    - <span data-ttu-id="585f5-110">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="585f5-110">Microsoft 365 Business Standard</span></span>
    - <span data-ttu-id="585f5-111">Microsoft 365-apps voor bedrijven</span><span class="sxs-lookup"><span data-stu-id="585f5-111">Microsoft 365 Apps for business</span></span>
    - <span data-ttu-id="585f5-112">Microsoft 365-apps voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="585f5-112">Microsoft 365 Apps for enterprise</span></span>
    - <span data-ttu-id="585f5-113">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="585f5-113">Office 365 E3</span></span>
    - <span data-ttu-id="585f5-114">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="585f5-114">Office 365 E5</span></span>
    - <span data-ttu-id="585f5-115">Office 365 A3</span><span class="sxs-lookup"><span data-stu-id="585f5-115">Office 365 A3</span></span>
    - <span data-ttu-id="585f5-116">Office 365 A5</span><span class="sxs-lookup"><span data-stu-id="585f5-116">Office 365 A5</span></span>

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a><span data-ttu-id="585f5-117">De beschikbaarheid van Office scripts beheren en scripts delen</span><span class="sxs-lookup"><span data-stu-id="585f5-117">Manage availability of Office Scripts and sharing of scripts</span></span>

1. <span data-ttu-id="585f5-118">Ga in het Microsoft 365-beheercentrum naar het tabblad **Instellingen** \> **Organisatie-instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services.</a></span><span class="sxs-lookup"><span data-stu-id="585f5-118">In the Microsoft 365 admin center, go to the **Settings** \> **Org settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> tab.</span></span>

2. <span data-ttu-id="585f5-119">Selecteer **Office scripts**.</span><span class="sxs-lookup"><span data-stu-id="585f5-119">Select **Office Scripts**.</span></span>

3. <span data-ttu-id="585f5-120">Office Scripts zijn standaard ingeschakeld en iedereen in uw organisatie heeft toegang tot en kan de functie gebruiken en scripts delen.</span><span class="sxs-lookup"><span data-stu-id="585f5-120">Office Scripts is turned on by default, and everyone in your organization can access and use the feature and share scripts.</span></span> <span data-ttu-id="585f5-121">Als u Office scripts voor uw organisatie wilt uitschakelen, schakelt u het selectievakje **Gebruikers hun taken automatiseren in webversie van Excel** uit.</span><span class="sxs-lookup"><span data-stu-id="585f5-121">To turn off Office Scripts for your organization, clear the **Let users automate their tasks in Excel on the web** check box.</span></span>

4. <span data-ttu-id="585f5-122">Als u eerder Office scripts voor uw organisatie hebt uitgeschakeld en u deze weer wilt inschakelen, selecteert u **Gebruikers hun taken laten automatiseren in webversie van Excel** en geeft u vervolgens op wie toegang heeft tot de functie en deze kan gebruiken:</span><span class="sxs-lookup"><span data-stu-id="585f5-122">If you previously turned off Office Scripts for your organization and you want to turn it back on, select **Let users automate their tasks in Excel on the web**, and then specify who can access and use the feature:</span></span>

    - <span data-ttu-id="585f5-123">Als u wilt dat alle gebruikers in uw organisatie toegang hebben tot en Office scripts gebruiken, laat u **Iedereen** (de standaardinstelling) geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="585f5-123">To allow all users in your organization to access and use Office Scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="585f5-124">Als u alleen leden van een specifieke groep toegang wilt geven tot en Office scripts wilt gebruiken, selecteert u **Specifieke groep** en voert u vervolgens de naam of e-mailalias van de groep in om deze toe te voegen aan de lijst met toegestane groepen.</span><span class="sxs-lookup"><span data-stu-id="585f5-124">To allow only members of a specific group to access and use Office Scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="585f5-125">U kunt slechts één groep toevoegen aan de lijst met toegestane groepen en dit moet een van de volgende typen zijn:</span><span class="sxs-lookup"><span data-stu-id="585f5-125">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="585f5-126">Microsoft 365 groep</span><span class="sxs-lookup"><span data-stu-id="585f5-126">Microsoft 365 group</span></span>
        - <span data-ttu-id="585f5-127">Distributiegroep</span><span class="sxs-lookup"><span data-stu-id="585f5-127">Distribution group</span></span>
        - <span data-ttu-id="585f5-128">Beveiligingsgroep</span><span class="sxs-lookup"><span data-stu-id="585f5-128">Security group</span></span>
        - <span data-ttu-id="585f5-129">Beveiligingsgroep met e-mail</span><span class="sxs-lookup"><span data-stu-id="585f5-129">Mail-enabled security group</span></span>
    
        <span data-ttu-id="585f5-130">Zie Groepen vergelijken voor meer informatie over de verschillende typen [groepen.](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="585f5-130">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

5. <span data-ttu-id="585f5-131">Als u gebruikers met toegang tot Office scripts hun scripts wilt laten delen met anderen in uw organisatie, selecteert u **Gebruikers met toegang tot Office scripts hun scripts delen met anderen in de organisatie**.</span><span class="sxs-lookup"><span data-stu-id="585f5-131">To allow users with access to Office Scripts to share their scripts with others in your organization, select **Let users with access to Office Scripts share their scripts with others in the organization**.</span></span> <span data-ttu-id="585f5-132">Het delen van scripts buiten een organisatie is niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="585f5-132">Sharing scripts outside of an organization is not allowed.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="585f5-133">Als u later het delen van scripts voor uw organisatie uitschakelt, kunnen gebruikers nog steeds eerder gedeelde scripts uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="585f5-133">If you later turn off script sharing for your organization, users will still be able to run previously-shared scripts.</span></span>
 
6. <span data-ttu-id="585f5-134">Geef op welke gebruikers met toegang tot Office scripts hun scripts kunnen delen:</span><span class="sxs-lookup"><span data-stu-id="585f5-134">Specify which users with access to Office Scripts can share their scripts:</span></span>
    
    - <span data-ttu-id="585f5-135">Als u wilt dat alle gebruikers met toegang tot Office scripts hun scripts kunnen delen, laat u **Iedereen** (de standaardinstelling) geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="585f5-135">To allow all users with access to Office Scripts to share their scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="585f5-136">Als u alleen leden van een specifieke groep met toegang tot Office scripts wilt toestaan hun scripts te delen, selecteert u **Specifieke groep** en voert u vervolgens de naam of e-mailalias van de groep in om deze toe te voegen aan de lijst met toegestane scripts.</span><span class="sxs-lookup"><span data-stu-id="585f5-136">To allow only members of a specific group with access to Office Scripts to share their scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="585f5-137">U kunt slechts één groep toevoegen aan de lijst met toegestane groepen en dit moet een van de volgende typen zijn:</span><span class="sxs-lookup"><span data-stu-id="585f5-137">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="585f5-138">Microsoft 365 groep</span><span class="sxs-lookup"><span data-stu-id="585f5-138">Microsoft 365 group</span></span>
        - <span data-ttu-id="585f5-139">Distributiegroep</span><span class="sxs-lookup"><span data-stu-id="585f5-139">Distribution group</span></span>
        - <span data-ttu-id="585f5-140">Beveiligingsgroep</span><span class="sxs-lookup"><span data-stu-id="585f5-140">Security group</span></span>
        - <span data-ttu-id="585f5-141">Beveiligingsgroep met e-mail</span><span class="sxs-lookup"><span data-stu-id="585f5-141">Mail-enabled security group</span></span>
    
        <span data-ttu-id="585f5-142">Zie Groepen vergelijken voor meer informatie over de verschillende typen [groepen.](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="585f5-142">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

7. <span data-ttu-id="585f5-143">Als u wilt dat gebruikers hun Office scripts binnen Power Automate stromen kunnen uitvoeren, selecteert u **Gebruikers met toegang tot Office scripts hun scripts laten uitvoeren met Power Automate**.</span><span class="sxs-lookup"><span data-stu-id="585f5-143">To allow users to run their Office Scripts inside Power Automate flows, select **Let users with access to Office Scripts run their scripts with Power Automate**.</span></span> <span data-ttu-id="585f5-144">Hierdoor kunnen gebruikers stroomstappen toevoegen met de **scriptoptie** [Excel Online (Business) Connector.](/connectors/excelonlinebusiness)</span><span class="sxs-lookup"><span data-stu-id="585f5-144">This allows users to add flow steps with the [Excel Online (Business) Connector's](/connectors/excelonlinebusiness) **Run script** option.</span></span>

    - <span data-ttu-id="585f5-145">Als u wilt dat alle gebruikers met toegang tot Office scripts hun scripts in stromen kunnen gebruiken, laat u **Iedereen** (de standaardinstelling) geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="585f5-145">To allow all users with access to Office Scripts to use their scripts in flows, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="585f5-146">Als u alleen leden van een specifieke groep met toegang tot Office scripts wilt toestaan hun scripts in stromen te gebruiken, selecteert u **Specifieke groep** en voert u vervolgens de naam of e-mailalias van de groep in om deze toe te voegen aan de lijst met toegestane scripts.</span><span class="sxs-lookup"><span data-stu-id="585f5-146">To allow only members of a specific group with access to Office Scripts to use their scripts in flows, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="585f5-147">U kunt slechts één groep toevoegen aan de lijst met toegestane groepen en dit moet een van de volgende typen zijn:</span><span class="sxs-lookup"><span data-stu-id="585f5-147">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="585f5-148">Microsoft 365 groep</span><span class="sxs-lookup"><span data-stu-id="585f5-148">Microsoft 365 group</span></span>
        - <span data-ttu-id="585f5-149">Distributiegroep</span><span class="sxs-lookup"><span data-stu-id="585f5-149">Distribution group</span></span>
        - <span data-ttu-id="585f5-150">Beveiligingsgroep</span><span class="sxs-lookup"><span data-stu-id="585f5-150">Security group</span></span>
        - <span data-ttu-id="585f5-151">Beveiligingsgroep met e-mail</span><span class="sxs-lookup"><span data-stu-id="585f5-151">Mail-enabled security group</span></span>

        <span data-ttu-id="585f5-152">Zie Groepen vergelijken voor meer informatie over de verschillende typen [groepen.](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="585f5-152">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

    - <span data-ttu-id="585f5-153">Zie Office scripts uitvoeren met Power Automate voor meer informatie over het gebruik [van Office scripts met Power Automate.](/office/dev/scripts/develop/power-automate-integration)</span><span class="sxs-lookup"><span data-stu-id="585f5-153">To learn more about using Office Scripts with Power Automate, see [Run Office Scripts with Power Automate](/office/dev/scripts/develop/power-automate-integration).</span></span>

8. <span data-ttu-id="585f5-154">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="585f5-154">Select **Save**.</span></span>

    <span data-ttu-id="585f5-155">Het kan tot 48 uur duren voordat wijzigingen in Office scripts-instellingen van kracht worden.</span><span class="sxs-lookup"><span data-stu-id="585f5-155">It can take up to 48 hours for changes to Office Scripts settings to take effect.</span></span>

## <a name="next-steps"></a><span data-ttu-id="585f5-156">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="585f5-156">Next steps</span></span>

<span data-ttu-id="585f5-157">Omdat Office Scripts met Power Automate werkt, raden we u aan uw bestaande DLP-beleid (Data Loss Prevention) te bekijken om ervoor te zorgen dat de gegevens van uw organisatie beschermd blijven terwijl gebruikers Office scripts gebruiken.</span><span class="sxs-lookup"><span data-stu-id="585f5-157">Because Office Scripts works with Power Automate, we recommend that you review your existing data loss prevention (DLP) policies to ensure your organization's data remains protected while users use ‎Office Scripts‎.</span></span> <span data-ttu-id="585f5-158">Zie beleid voor [het voorkomen van gegevensverlies (DLP)](/power-automate/prevent-data-loss)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="585f5-158">For more information, see [Data loss prevention (DLP) policies](/power-automate/prevent-data-loss).</span></span>

## <a name="related-content"></a><span data-ttu-id="585f5-159">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="585f5-159">Related content</span></span>

<span data-ttu-id="585f5-160">[Office Scripts technische documentatie](/office/dev/scripts/) (linkpagina)</span><span class="sxs-lookup"><span data-stu-id="585f5-160">[Office Scripts technical documentation](/office/dev/scripts/) (link page)</span></span>\
<span data-ttu-id="585f5-161">[Inleiding tot Office scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (artikel)</span><span class="sxs-lookup"><span data-stu-id="585f5-161">[Introduction to Office Scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (article)</span></span>\
<span data-ttu-id="585f5-162">[Office scripts delen in Excel voor het web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (artikel)</span><span class="sxs-lookup"><span data-stu-id="585f5-162">[Sharing Office Scripts in Excel for the Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (article)</span></span>\
<span data-ttu-id="585f5-163">[Office scripts opnemen, bewerken en maken in webversie van Excel](/office/dev/scripts/tutorials/excel-tutorial) (artikel)</span><span class="sxs-lookup"><span data-stu-id="585f5-163">[Record, edit, and create Office Scripts in Excel on the web](/office/dev/scripts/tutorials/excel-tutorial) (article)</span></span>
