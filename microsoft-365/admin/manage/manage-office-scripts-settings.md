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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid: MET150
description: Meer informatie over het beheren Office scripts voor gebruikers in uw organisatie.
ms.openlocfilehash: fea50838cf1089b73a6af5bbf86d490293831085
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "53392669"
---
# <a name="manage-office-scripts-settings"></a><span data-ttu-id="4a5b9-103">Instellingen voor Office-scripts beheren</span><span class="sxs-lookup"><span data-stu-id="4a5b9-103">Manage Office Scripts settings</span></span>

<span data-ttu-id="4a5b9-104">[Office scripts](/office/dev/scripts)kunnen gebruikers taken automatiseren door scripts op te nemen, te bewerken en uit te voeren in Excel web.</span><span class="sxs-lookup"><span data-stu-id="4a5b9-104">[Office Scripts](/office/dev/scripts)‎ allows users to automate tasks by recording, editing, and running scripts in ‎Excel‎ on the web.</span></span> <span data-ttu-id="4a5b9-105">Office Scripts werken met Power Automate en gebruikers voeren scripts uit op werkmappen met behulp van Excel onlineconnector (Business).</span><span class="sxs-lookup"><span data-stu-id="4a5b9-105">‎Office Scripts‎ works with Power Automate, and users run scripts on workbooks by using the ‎Excel‎ Online (Business) connector.</span></span> <span data-ttu-id="4a5b9-106">Microsoft 365 beheerders kunnen de Office scripts beheren vanaf de Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="4a5b9-106">Microsoft 365 admins can manage Office Scripts settings from the Microsoft 365 admin center.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4a5b9-107">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="4a5b9-107">Before you begin</span></span>

- <span data-ttu-id="4a5b9-108">Als u de Office scripts wilt beheren, moet u een globale beheerder zijn. Zie Over beheerdersrollen [voor meer informatie.](../add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="4a5b9-108">To manage Office Scripts settings, you must be a Global admin. For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="4a5b9-109">Zorg ervoor dat gebruikers in uw organisatie een geldige licentie hebben voor een Microsoft 365- of Office 365-commercieel of EDU-abonnement met toegang tot Office-bureaublad-apps, zoals een van de volgende abonnementen:</span><span class="sxs-lookup"><span data-stu-id="4a5b9-109">Ensure users in your organization have a valid license for a Microsoft 365 or Office 365 commercial or EDU plan that includes access to Office desktop apps, such as one of the following plans:</span></span>

    - <span data-ttu-id="4a5b9-110">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="4a5b9-110">Microsoft 365 Business Standard</span></span>
    - <span data-ttu-id="4a5b9-111">Microsoft 365-apps voor bedrijven</span><span class="sxs-lookup"><span data-stu-id="4a5b9-111">Microsoft 365 Apps for business</span></span>
    - <span data-ttu-id="4a5b9-112">Microsoft 365-apps voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="4a5b9-112">Microsoft 365 Apps for enterprise</span></span>
    - <span data-ttu-id="4a5b9-113">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="4a5b9-113">Office 365 E3</span></span>
    - <span data-ttu-id="4a5b9-114">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="4a5b9-114">Office 365 E5</span></span>
    - <span data-ttu-id="4a5b9-115">Office 365 A3</span><span class="sxs-lookup"><span data-stu-id="4a5b9-115">Office 365 A3</span></span>
    - <span data-ttu-id="4a5b9-116">Office 365 A5</span><span class="sxs-lookup"><span data-stu-id="4a5b9-116">Office 365 A5</span></span>

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a><span data-ttu-id="4a5b9-117">Beschikbaarheid van scripts Office en delen van scripts beheren</span><span class="sxs-lookup"><span data-stu-id="4a5b9-117">Manage availability of Office Scripts and sharing of scripts</span></span>

1. <span data-ttu-id="4a5b9-118">Ga in Microsoft 365-beheercentrum naar het tabblad **Instellingen** \> **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">services.</a></span><span class="sxs-lookup"><span data-stu-id="4a5b9-118">In the Microsoft 365 admin center, go to the **Settings** \> **Org settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> tab.</span></span>

2. <span data-ttu-id="4a5b9-119">Selecteer **Office scripts.**</span><span class="sxs-lookup"><span data-stu-id="4a5b9-119">Select **Office Scripts**.</span></span>

3. <span data-ttu-id="4a5b9-120">Office Scripts zijn standaard ingeschakeld en iedereen in uw organisatie kan de functie openen en gebruiken en scripts delen.</span><span class="sxs-lookup"><span data-stu-id="4a5b9-120">Office Scripts is turned on by default, and everyone in your organization can access and use the feature and share scripts.</span></span> <span data-ttu-id="4a5b9-121">Als u Office scripts voor uw organisatie wilt uitschakelen, schakelt u het selectievakje Gebruikers hun taken laten automatiseren **in** webversie van Excel uit.</span><span class="sxs-lookup"><span data-stu-id="4a5b9-121">To turn off Office Scripts for your organization, clear the **Let users automate their tasks in Excel on the web** check box.</span></span>

4. <span data-ttu-id="4a5b9-122">Als u eerder Office Scripts voor uw organisatie hebt uitgeschakeld en u deze opnieuw wilt in schakelen, selecteert u Gebruikers hun taken laten automatiseren **in webversie van Excel** en geeft u vervolgens op wie de functie kan openen en gebruiken:</span><span class="sxs-lookup"><span data-stu-id="4a5b9-122">If you previously turned off Office Scripts for your organization and you want to turn it back on, select **Let users automate their tasks in Excel on the web**, and then specify who can access and use the feature:</span></span>

    - <span data-ttu-id="4a5b9-123">Als u wilt dat alle gebruikers in uw organisatie toegang hebben tot en Office scripts gebruiken, laat u **Iedereen** (de standaardinstelling) geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="4a5b9-123">To allow all users in your organization to access and use Office Scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="4a5b9-124">Als u wilt dat alleen leden van een specifieke groep Office Scripts kunnen openen en gebruiken, selecteert u Specifieke groep **en** voert u vervolgens de naam of e-mailalias van de groep in om deze toe te voegen aan de lijst toestaan.</span><span class="sxs-lookup"><span data-stu-id="4a5b9-124">To allow only members of a specific group to access and use Office Scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="4a5b9-125">U mag slechts één groep toevoegen aan de lijst toestaan en dit moet een van de volgende typen zijn:</span><span class="sxs-lookup"><span data-stu-id="4a5b9-125">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="4a5b9-126">Microsoft 365 groep</span><span class="sxs-lookup"><span data-stu-id="4a5b9-126">Microsoft 365 group</span></span>
        - <span data-ttu-id="4a5b9-127">Distributiegroep</span><span class="sxs-lookup"><span data-stu-id="4a5b9-127">Distribution group</span></span>
        - <span data-ttu-id="4a5b9-128">Beveiligingsgroep</span><span class="sxs-lookup"><span data-stu-id="4a5b9-128">Security group</span></span>
        - <span data-ttu-id="4a5b9-129">Beveiligingsgroep met e-mail</span><span class="sxs-lookup"><span data-stu-id="4a5b9-129">Mail-enabled security group</span></span>
    
        <span data-ttu-id="4a5b9-130">Zie Groepen vergelijken voor meer informatie over de verschillende typen [groepen.](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="4a5b9-130">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

5. <span data-ttu-id="4a5b9-131">Als u gebruikers met toegang tot Office Scripts wilt toestaan hun scripts te delen met anderen in uw organisatie, selecteert u Gebruikers met toegang tot Office Scripts toestaan hun scripts te delen met anderen in de **organisatie.**</span><span class="sxs-lookup"><span data-stu-id="4a5b9-131">To allow users with access to Office Scripts to share their scripts with others in your organization, select **Let users with access to Office Scripts share their scripts with others in the organization**.</span></span> <span data-ttu-id="4a5b9-132">Scripts delen buiten een organisatie is niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="4a5b9-132">Sharing scripts outside of an organization is not allowed.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="4a5b9-133">Als u later het delen van scripts voor uw organisatie uit zet, kunnen gebruikers nog steeds eerder gedeelde scripts uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="4a5b9-133">If you later turn off script sharing for your organization, users will still be able to run previously-shared scripts.</span></span>
 
6. <span data-ttu-id="4a5b9-134">Geef op welke gebruikers met toegang tot Office scripts hun scripts kunnen delen:</span><span class="sxs-lookup"><span data-stu-id="4a5b9-134">Specify which users with access to Office Scripts can share their scripts:</span></span>
    
    - <span data-ttu-id="4a5b9-135">Als u wilt dat alle gebruikers met toegang Office scripts om hun scripts te delen, laat u **Iedereen** (de standaardinstelling) geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="4a5b9-135">To allow all users with access to Office Scripts to share their scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="4a5b9-136">Als u wilt dat alleen leden van een specifieke groep met toegang tot Office Scripts hun scripts kunnen delen, selecteert u Specifieke groep **en** voert u vervolgens de naam of e-mailalias van de groep in om deze toe te voegen aan de lijst toestaan.</span><span class="sxs-lookup"><span data-stu-id="4a5b9-136">To allow only members of a specific group with access to Office Scripts to share their scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="4a5b9-137">U mag slechts één groep toevoegen aan de lijst toestaan en dit moet een van de volgende typen zijn:</span><span class="sxs-lookup"><span data-stu-id="4a5b9-137">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="4a5b9-138">Microsoft 365 groep</span><span class="sxs-lookup"><span data-stu-id="4a5b9-138">Microsoft 365 group</span></span>
        - <span data-ttu-id="4a5b9-139">Distributiegroep</span><span class="sxs-lookup"><span data-stu-id="4a5b9-139">Distribution group</span></span>
        - <span data-ttu-id="4a5b9-140">Beveiligingsgroep</span><span class="sxs-lookup"><span data-stu-id="4a5b9-140">Security group</span></span>
        - <span data-ttu-id="4a5b9-141">Beveiligingsgroep met e-mail</span><span class="sxs-lookup"><span data-stu-id="4a5b9-141">Mail-enabled security group</span></span>
    
        <span data-ttu-id="4a5b9-142">Zie Groepen vergelijken voor meer informatie over de verschillende typen [groepen.](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="4a5b9-142">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

7. <span data-ttu-id="4a5b9-143">Als u wilt dat gebruikers hun Office scripts kunnen uitvoeren in Power Automate stromen, selecteert u Gebruikers met toegang tot Office Scripts hun scripts laten uitvoeren **met Power Automate.**</span><span class="sxs-lookup"><span data-stu-id="4a5b9-143">To allow users to run their Office Scripts inside Power Automate flows, select **Let users with access to Office Scripts run their scripts with Power Automate**.</span></span> <span data-ttu-id="4a5b9-144">Hierdoor kunnen gebruikers stroomstappen toevoegen met de optie uitvoeren [van Excel onlineconnector (Business)](/connectors/excelonlinebusiness) **Connector.**</span><span class="sxs-lookup"><span data-stu-id="4a5b9-144">This allows users to add flow steps with the [Excel Online (Business) Connector's](/connectors/excelonlinebusiness) **Run script** option.</span></span>

    - <span data-ttu-id="4a5b9-145">Als u alle gebruikers met toegang tot Office scripts wilt toestaan om hun scripts in stromen te gebruiken, laat u **Iedereen** (de standaardinstelling) geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="4a5b9-145">To allow all users with access to Office Scripts to use their scripts in flows, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="4a5b9-146">Als u wilt dat alleen leden van een specifieke groep met toegang tot Office Scripts hun scripts kunnen gebruiken in stromen, selecteert u Specifieke groep **en** voert u vervolgens de naam of e-mailalias van de groep in om deze toe te voegen aan de lijst toestaan.</span><span class="sxs-lookup"><span data-stu-id="4a5b9-146">To allow only members of a specific group with access to Office Scripts to use their scripts in flows, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="4a5b9-147">U mag slechts één groep toevoegen aan de lijst toestaan en dit moet een van de volgende typen zijn:</span><span class="sxs-lookup"><span data-stu-id="4a5b9-147">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="4a5b9-148">Microsoft 365 groep</span><span class="sxs-lookup"><span data-stu-id="4a5b9-148">Microsoft 365 group</span></span>
        - <span data-ttu-id="4a5b9-149">Distributiegroep</span><span class="sxs-lookup"><span data-stu-id="4a5b9-149">Distribution group</span></span>
        - <span data-ttu-id="4a5b9-150">Beveiligingsgroep</span><span class="sxs-lookup"><span data-stu-id="4a5b9-150">Security group</span></span>
        - <span data-ttu-id="4a5b9-151">Beveiligingsgroep met e-mail</span><span class="sxs-lookup"><span data-stu-id="4a5b9-151">Mail-enabled security group</span></span>

        <span data-ttu-id="4a5b9-152">Zie Groepen vergelijken voor meer informatie over de verschillende typen [groepen.](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="4a5b9-152">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

    - <span data-ttu-id="4a5b9-153">Zie Office scripts uitvoeren met Power Automate voor meer informatie over het gebruik van Office [scripts met Power Automate](/office/dev/scripts/develop/power-automate-integration)scripts.</span><span class="sxs-lookup"><span data-stu-id="4a5b9-153">To learn more about using Office Scripts with Power Automate, see [Run Office Scripts with Power Automate](/office/dev/scripts/develop/power-automate-integration).</span></span>

8. <span data-ttu-id="4a5b9-154">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="4a5b9-154">Select **Save**.</span></span>

    <span data-ttu-id="4a5b9-155">Het kan tot 48 uur duren voordat wijzigingen in de Office scripts worden doorgevoerd.</span><span class="sxs-lookup"><span data-stu-id="4a5b9-155">It can take up to 48 hours for changes to Office Scripts settings to take effect.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4a5b9-156">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="4a5b9-156">Next steps</span></span>

<span data-ttu-id="4a5b9-157">Omdat Office Scripts werkt met Power Automate, raden we u aan uw bestaande DLP-beleid (Data Loss Prevention) te bekijken om ervoor te zorgen dat de gegevens van uw organisatie beveiligd blijven terwijl gebruikers scripts Office gebruiken.</span><span class="sxs-lookup"><span data-stu-id="4a5b9-157">Because Office Scripts works with Power Automate, we recommend that you review your existing data loss prevention (DLP) policies to ensure your organization's data remains protected while users use ‎Office Scripts‎.</span></span> <span data-ttu-id="4a5b9-158">Zie [DLP-beleid (Data Loss Prevention) voor meer informatie.](/power-automate/prevent-data-loss)</span><span class="sxs-lookup"><span data-stu-id="4a5b9-158">For more information, see [Data loss prevention (DLP) policies](/power-automate/prevent-data-loss).</span></span>

## <a name="related-content"></a><span data-ttu-id="4a5b9-159">Verwante inhoud</span><span class="sxs-lookup"><span data-stu-id="4a5b9-159">Related content</span></span>

<span data-ttu-id="4a5b9-160">[Office Scripts technische documentatie](/office/dev/scripts/) (koppelingspagina)</span><span class="sxs-lookup"><span data-stu-id="4a5b9-160">[Office Scripts technical documentation](/office/dev/scripts/) (link page)</span></span>\
<span data-ttu-id="4a5b9-161">[Inleiding tot Office scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (artikel)</span><span class="sxs-lookup"><span data-stu-id="4a5b9-161">[Introduction to Office Scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (article)</span></span>\
<span data-ttu-id="4a5b9-162">[Scripts Office delen in Excel web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (artikel)</span><span class="sxs-lookup"><span data-stu-id="4a5b9-162">[Sharing Office Scripts in Excel for the Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (article)</span></span>\
<span data-ttu-id="4a5b9-163">[Scripts opnemen, bewerken](/office/dev/scripts/tutorials/excel-tutorial) en Office maken in webversie van Excel (artikel)</span><span class="sxs-lookup"><span data-stu-id="4a5b9-163">[Record, edit, and create Office Scripts in Excel on the web](/office/dev/scripts/tutorials/excel-tutorial) (article)</span></span>
