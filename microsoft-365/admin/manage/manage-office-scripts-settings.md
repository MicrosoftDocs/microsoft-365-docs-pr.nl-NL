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
description: Meer informatie over het beheren van de instellingen van Office-scripts voor gebruikers in uw organisatie.
ms.openlocfilehash: 12a80f277f6d17a8e7f5228f6948e70b7a93be11
ms.sourcegitcommit: 97ef8f846939c3d31bb0638edf07bb89463ace0b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/28/2020
ms.locfileid: "47300829"
---
# <a name="manage-office-scripts-settings"></a><span data-ttu-id="6dd27-103">Instellingen voor Office-scripts beheren</span><span class="sxs-lookup"><span data-stu-id="6dd27-103">Manage Office Scripts settings</span></span>

<span data-ttu-id="6dd27-104">Met Office-scripts kunnen gebruikers taken automatiseren door scripts op te nemen, te bewerken en uit te voeren in de webversie van Excel.</span><span class="sxs-lookup"><span data-stu-id="6dd27-104">Office Scripts‎ allows users to automate tasks by recording, editing, and running scripts in ‎Excel‎ on the web.</span></span> <span data-ttu-id="6dd27-105">Office-scripts werken met geautomatiseerde gebruikersfuncties en gebruikers uitvoeren scripts voor werkmappen met behulp van de Business-Connector (Business) van Excel online.</span><span class="sxs-lookup"><span data-stu-id="6dd27-105">‎Office Scripts‎ works with Power Automate, and users run scripts on workbooks by using the ‎Excel‎ Online (Business) connector.</span></span> <span data-ttu-id="6dd27-106">Microsoft 365-beheerders kunnen instellingen voor Office-scripts beheren via het Microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="6dd27-106">Microsoft 365 admins can manage Office Scripts settings from the Microsoft 365 admin center.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="6dd27-107">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="6dd27-107">Before you begin</span></span>

- <span data-ttu-id="6dd27-108">Voor het beheren van instellingen voor Office-scripts moet u een globale beheerder zijn. Zie voor meer informatie [beheerdersrollen](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="6dd27-108">To manage Office Scripts settings, you must be a Global admin. For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="6dd27-109">Zorg ervoor dat gebruikers in uw organisatie een geldige licentie hebben voor een commercieel of onderwijs abonnement voor Microsoft 365 of Office 365 dat toegang heeft tot Office-bureaubladtoepassingen, zoals een van de volgende abonnementen:</span><span class="sxs-lookup"><span data-stu-id="6dd27-109">Ensure users in your organization have a valid license for a Microsoft 365 or Office 365 commercial or EDU plan that includes access to Office desktop apps, such as one of the following plans:</span></span>

    - <span data-ttu-id="6dd27-110">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="6dd27-110">Microsoft 365 Business Standard</span></span>
    - <span data-ttu-id="6dd27-111">Microsoft 365-apps voor bedrijven</span><span class="sxs-lookup"><span data-stu-id="6dd27-111">Microsoft 365 Apps for business</span></span>
    - <span data-ttu-id="6dd27-112">Microsoft 365-apps voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="6dd27-112">Microsoft 365 Apps for enterprise</span></span>
    - <span data-ttu-id="6dd27-113">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="6dd27-113">Office 365 E3</span></span>
    - <span data-ttu-id="6dd27-114">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="6dd27-114">Office 365 E5</span></span>
    - <span data-ttu-id="6dd27-115">Office 365 a3</span><span class="sxs-lookup"><span data-stu-id="6dd27-115">Office 365 A3</span></span>
    - <span data-ttu-id="6dd27-116">Office 365 A5</span><span class="sxs-lookup"><span data-stu-id="6dd27-116">Office 365 A5</span></span>

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a><span data-ttu-id="6dd27-117">De beschikbaarheid van Office-scripts en het delen van scripts beheren</span><span class="sxs-lookup"><span data-stu-id="6dd27-117">Manage availability of Office Scripts and sharing of scripts</span></span>

1. <span data-ttu-id="6dd27-118">Ga in het Microsoft 365-Beheercentrum naar **het** \> tabblad Services van de organisatie- **instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> .</span><span class="sxs-lookup"><span data-stu-id="6dd27-118">In the Microsoft 365 admin center, go to the **Settings** \> **Org settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> tab.</span></span>

2. <span data-ttu-id="6dd27-119">Selecteer **Office-scripts**.</span><span class="sxs-lookup"><span data-stu-id="6dd27-119">Select **Office Scripts**.</span></span>

3. <span data-ttu-id="6dd27-120">Office-scripts is standaard ingeschakeld en iedereen in uw organisatie kan de functie openen en gebruiken en scripts delen.</span><span class="sxs-lookup"><span data-stu-id="6dd27-120">Office Scripts is turned on by default, and everyone in your organization can access and use the feature and share scripts.</span></span> <span data-ttu-id="6dd27-121">Als u Office-scripts voor uw organisatie wilt uitschakelen, schakelt u het selectievakje **gebruikers hun taken laten automatiseren in Excel op het web** uit.</span><span class="sxs-lookup"><span data-stu-id="6dd27-121">To turn off Office Scripts for your organization, clear the **Let users automate their tasks in Excel on the web** check box.</span></span>

4. <span data-ttu-id="6dd27-122">Als u Office-scripts eerder voor uw organisatie hebt uitgeschakeld en u deze weer wilt inschakelen, selecteert u **gebruikers toestaan hun taken te laten automatiseren in de webversie van Excel**en geeft u vervolgens de personen die de functie kunnen openen en gebruiken:</span><span class="sxs-lookup"><span data-stu-id="6dd27-122">If you previously turned off Office Scripts for your organization and you want to turn it back on, select **Let users automate their tasks in Excel on the web**, and then specify who can access and use the feature:</span></span>

    - <span data-ttu-id="6dd27-123">Als u alle gebruikers in uw organisatie in staat wilt stellen Office-scripts te openen en gebruiken, laat u **iedereen** (de standaardinstelling) geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="6dd27-123">To allow all users in your organization to access and use Office Scripts, leave **Everyone** (the default) selected.</span></span> 

    - <span data-ttu-id="6dd27-124">Als u wilt dat alleen leden van een bepaalde groep Office-scripts kunnen openen en gebruiken, selecteert u **specifieke groep**en voert u de naam of e-mail alias van de groep in om deze toe te voegen aan de lijst toestaan.</span><span class="sxs-lookup"><span data-stu-id="6dd27-124">To allow only members of a specific group to access and use Office Scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="6dd27-125">U kunt slechts één groep toevoegen aan de toegestane lijst en moet een van de volgende typen zijn:</span><span class="sxs-lookup"><span data-stu-id="6dd27-125">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="6dd27-126">Microsoft 365-groep</span><span class="sxs-lookup"><span data-stu-id="6dd27-126">Microsoft 365 group</span></span>
        - <span data-ttu-id="6dd27-127">Distributiegroep</span><span class="sxs-lookup"><span data-stu-id="6dd27-127">Distribution group</span></span>
        - <span data-ttu-id="6dd27-128">Beveiligingsgroep</span><span class="sxs-lookup"><span data-stu-id="6dd27-128">Security group</span></span>
        - <span data-ttu-id="6dd27-129">Beveiligingsgroep met e-mail</span><span class="sxs-lookup"><span data-stu-id="6dd27-129">Mail-enabled security group</span></span>
    
        <span data-ttu-id="6dd27-130">Zie [Groepen vergelijken](../create-groups/compare-groups.md)voor meer informatie over de verschillende soorten groepen.</span><span class="sxs-lookup"><span data-stu-id="6dd27-130">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

5. <span data-ttu-id="6dd27-131">Als u wilt dat gebruikers toegang hebben tot Office-scripts waarmee hun scripts met andere personen in uw organisatie kunnen worden gedeeld, schakelt u **gebruikers met toegang tot Office-scripts toestaan hun scripts met andere personen in de organisatie**te delen.</span><span class="sxs-lookup"><span data-stu-id="6dd27-131">To allow users with access to Office Scripts to share their scripts with others in your organization, select **Let users with access to Office Scripts share their scripts with others in the organization**.</span></span> <span data-ttu-id="6dd27-132">Het delen van scripts buiten een organisatie is niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="6dd27-132">Sharing scripts outside of an organization is not allowed.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="6dd27-133">Als u het delen van scripts later uitschakelt voor uw organisatie, kunnen gebruikers eerder eerder gedeelde scripts uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="6dd27-133">If you later turn off script sharing for your organization, users will still be able to run previously-shared scripts.</span></span>
 
6. <span data-ttu-id="6dd27-134">Opgeven welke gebruikers toegang hebben tot Office-scripts hun scripts kunnen delen:</span><span class="sxs-lookup"><span data-stu-id="6dd27-134">Specify which users with access to Office Scripts can share their scripts:</span></span>
    
    - <span data-ttu-id="6dd27-135">Als u wilt dat alle gebruikers met toegang tot Office-scripts hun scripts kunnen delen, laat u **iedereen** (de standaardinstelling) geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="6dd27-135">To allow all users with access to Office Scripts to share their scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="6dd27-136">Als u wilt dat alleen leden van een bepaalde groep toegang hebben tot Office-scripts om hun scripts te delen, selecteert u **specifieke groep**en voert u de naam of het e-mail alias van de groep in om deze toe te voegen aan de lijst toestaan.</span><span class="sxs-lookup"><span data-stu-id="6dd27-136">To allow only members of a specific group with access to Office Scripts to share their scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="6dd27-137">U kunt slechts één groep toevoegen aan de toegestane lijst en moet een van de volgende typen zijn:</span><span class="sxs-lookup"><span data-stu-id="6dd27-137">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="6dd27-138">Microsoft 365-groep</span><span class="sxs-lookup"><span data-stu-id="6dd27-138">Microsoft 365 group</span></span>
        - <span data-ttu-id="6dd27-139">Distributiegroep</span><span class="sxs-lookup"><span data-stu-id="6dd27-139">Distribution group</span></span>
        - <span data-ttu-id="6dd27-140">Beveiligingsgroep</span><span class="sxs-lookup"><span data-stu-id="6dd27-140">Security group</span></span>
        - <span data-ttu-id="6dd27-141">Beveiligingsgroep met e-mail</span><span class="sxs-lookup"><span data-stu-id="6dd27-141">Mail-enabled security group</span></span>
    
        <span data-ttu-id="6dd27-142">Zie [Groepen vergelijken](../create-groups/compare-groups.md)voor meer informatie over de verschillende soorten groepen.</span><span class="sxs-lookup"><span data-stu-id="6dd27-142">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

7. <span data-ttu-id="6dd27-143">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6dd27-143">Select **Save**.</span></span>

    <span data-ttu-id="6dd27-144">Het kan tot 48 uur duren voordat wijzigingen in de instellingen van het Office-script worden doorgevoerd.</span><span class="sxs-lookup"><span data-stu-id="6dd27-144">It can take up to 48 hours for changes to Office Script settings to take effect.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6dd27-145">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="6dd27-145">Next steps</span></span>

<span data-ttu-id="6dd27-146">Aangezien Office-scripts met automatisering werken, is het raadzaam om uw bestaande DLP-beleidsregels (preventie van gegevensverlies) te controleren om ervoor te zorgen dat de gegevens van uw organisatie worden beveiligd wanneer gebruikers Office-scripts gebruiken.</span><span class="sxs-lookup"><span data-stu-id="6dd27-146">Because Office Scripts works with Power Automate, we recommend that you review your existing data loss prevention (DLP) policies to ensure your organization's data remains protected while users use ‎Office Scripts‎.</span></span> <span data-ttu-id="6dd27-147">Zie [DLP-beleid (preventie van gegevensverlies)](/power-automate/prevent-data-loss)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="6dd27-147">For more information, see [Data loss prevention (DLP) policies](/power-automate/prevent-data-loss).</span></span>

## <a name="related-content"></a><span data-ttu-id="6dd27-148">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="6dd27-148">Related content</span></span>

<span data-ttu-id="6dd27-149">[Technische documentatie voor Office-scripts](/office/dev/scripts/) (koppelings pagina) </span><span class="sxs-lookup"><span data-stu-id="6dd27-149">[Office Scripts technical documentation](/office/dev/scripts/) (link page)</span></span>\
<span data-ttu-id="6dd27-150">[Inleiding tot Office-scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (artikel) </span><span class="sxs-lookup"><span data-stu-id="6dd27-150">[Introduction to Office Scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (article)</span></span>\
<span data-ttu-id="6dd27-151">[Office-scripts delen in Excel voor het web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (artikel) </span><span class="sxs-lookup"><span data-stu-id="6dd27-151">[Sharing Office Scripts in Excel for the Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (article)</span></span>\
<span data-ttu-id="6dd27-152">[Office-scripts opnemen, bewerken en maken in de webversie van Excel](/office/dev/scripts/tutorials/excel-tutorial) (artikel)</span><span class="sxs-lookup"><span data-stu-id="6dd27-152">[Record, edit, and create Office Scripts in Excel on the web](/office/dev/scripts/tutorials/excel-tutorial) (article)</span></span>