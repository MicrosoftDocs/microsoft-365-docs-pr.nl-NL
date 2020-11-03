---
title: Microsoft 365-groepen beheren met PowerShell
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BSA160
- BCS160
ms.assetid: aeb669aa-1770-4537-9de2-a82ac11b0540
description: In dit artikel vindt u informatie over het uitvoeren van algemene beheertaken voor Microsoft 365-groepen in PowerShell.
ms.openlocfilehash: 1cad2aa39a6b106cbb4dbfbafa995899b2442ed1
ms.sourcegitcommit: 9d1351ea6d9942550b52132817f9f9693ddef2fd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/02/2020
ms.locfileid: "48830613"
---
# <a name="manage-microsoft-365-groups-with-powershell"></a><span data-ttu-id="7b815-103">Microsoft 365-groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b815-103">Manage Microsoft 365 Groups with PowerShell</span></span>

<span data-ttu-id="7b815-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="7b815-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="7b815-105">In dit artikel vindt u de stappen voor het uitvoeren van veelvoorkomende beheertaken voor groepen in Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7b815-105">This article provides the steps for doing common management tasks for Groups in Microsoft PowerShell.</span></span> <span data-ttu-id="7b815-106">De PowerShell-cmdlets voor groepen worden ook weergegeven.</span><span class="sxs-lookup"><span data-stu-id="7b815-106">It also lists the PowerShell cmdlets for Groups.</span></span> <span data-ttu-id="7b815-107">Zie [SharePoint Online-sites beheren met PowerShell](https://docs.microsoft.com/sharepoint/manage-team-and-communication-sites-in-powershell)voor informatie over het beheren van SharePoint-sites.</span><span class="sxs-lookup"><span data-stu-id="7b815-107">For info about managing SharePoint sites, see [Manage SharePoint Online sites using PowerShell](https://docs.microsoft.com/sharepoint/manage-team-and-communication-sites-in-powershell).</span></span>

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a><span data-ttu-id="7b815-108">Koppeling naar richtlijnen voor het gebruik van Microsoft 365 groepen</span><span class="sxs-lookup"><span data-stu-id="7b815-108">Link to your Microsoft 365 Groups usage guidelines</span></span>
<span data-ttu-id="7b815-109"><a name="BK_LinkToGuideLines"> </a></span><span class="sxs-lookup"><span data-stu-id="7b815-109"><a name="BK_LinkToGuideLines"> </a></span></span>

<span data-ttu-id="7b815-110">Wanneer gebruikers [een groep in Outlook maken of bewerken](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx), kunt u een koppeling naar de gebruiks richtlijnen van uw organisatie weergeven.</span><span class="sxs-lookup"><span data-stu-id="7b815-110">When users [create or edit a group in Outlook](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx), you can show them a link to your organization's usage guidelines.</span></span> <span data-ttu-id="7b815-111">Als u bijvoorbeeld een specifiek voorvoegsel of achtervoegsel wilt toevoegen aan de naam van een groep.</span><span class="sxs-lookup"><span data-stu-id="7b815-111">For example, if you require a specific prefix or suffix to be added to a group name.</span></span>

<span data-ttu-id="7b815-112">Gebruik de PowerShell van Azure Active Directory (Azure AD) om uw gebruikers te laten verwijzen naar de richtlijnen voor het gebruik van uw organisatie voor Microsoft 365 groepen.</span><span class="sxs-lookup"><span data-stu-id="7b815-112">Use the Azure Active Directory (Azure AD) PowerShell to point your users to your organization's usage guidelines for Microsoft 365 groups.</span></span> <span data-ttu-id="7b815-113">Ga naar [Azure Active Directory-cmdlets voor het configureren van de groepsinstellingen](https://go.microsoft.com/fwlink/?LinkID=827484) en volg de stappen in het venster **instellingen maken op het niveau** van de gebruikers richtlijn.</span><span class="sxs-lookup"><span data-stu-id="7b815-113">Check out [Azure Active Directory cmdlets for configuring group settings](https://go.microsoft.com/fwlink/?LinkID=827484) and follow the steps in the **Create settings at the directory level** to define the usage guideline hyperlink.</span></span> <span data-ttu-id="7b815-114">Wanneer u de AAD-cmdlet uitvoert, ziet gebruikers de koppeling naar uw richtlijnen wanneer ze een groep in Outlook maken of bewerken.</span><span class="sxs-lookup"><span data-stu-id="7b815-114">Once you run the AAD cmdlet, user's will see the link to your guidelines when they create or edit a group in Outlook.</span></span>

![Een nieuwe groep maken met de koppeling voor gebruiks richtlijnen](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)

![Klik op richtlijnen voor het gebruik van groepen om de richtlijnen voor Office 365-groepen te zien](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)

## <a name="allow-users-to-send-as-the-microsoft-365-group"></a><span data-ttu-id="7b815-117">Gebruikers toestaan te verzenden als de Microsoft 365-groep</span><span class="sxs-lookup"><span data-stu-id="7b815-117">Allow users to Send as the Microsoft 365 Group</span></span>
<span data-ttu-id="7b815-118"><a name="BK_LinkToGuideLines"> </a></span><span class="sxs-lookup"><span data-stu-id="7b815-118"><a name="BK_LinkToGuideLines"> </a></span></span>

<span data-ttu-id="7b815-119">Als u uw Microsoft 365-groepen wilt inschakelen voor ' verzenden als ', gebruikt u de cmdlets [add-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/add-recipientpermission) en [Get-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/get-recipientpermission) om dit te configureren.</span><span class="sxs-lookup"><span data-stu-id="7b815-119">If you want to enable your Microsoft 365 groups to "Send As", use the [Add-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/add-recipientpermission) and [Get-RecipientPermission](https://docs.microsoft.com/powershell/module/exchange/get-recipientpermission) cmdlets to configure this.</span></span> <span data-ttu-id="7b815-120">Als u deze instelling inschakelt, kunnen gebruikers van Microsoft 365-groepen de webversie van Outlook of de webversie van Outlook gebruiken om e-mail te verzenden en te beantwoorden als de groep Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7b815-120">Once you enable this setting, Microsoft 365 group users can use Outlook or Outlook on the web to send and reply to email as the Microsoft 365 group.</span></span> <span data-ttu-id="7b815-121">Gebruikers kunnen naar de groep gaan, een nieuw e-mailbericht maken en het veld ' verzenden als ' wijzigen in het e-mailadres van de groep.</span><span class="sxs-lookup"><span data-stu-id="7b815-121">Users can go to the group, create a new email, and change the "Send As" field to the group's email address.</span></span>

<span data-ttu-id="7b815-122">([U kunt dit ook doen in het Exchange-Beheercentrum](https://docs.microsoft.com/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group).)</span><span class="sxs-lookup"><span data-stu-id="7b815-122">([You can also do this in the Exchange Admin Center](https://docs.microsoft.com/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group).)</span></span>

<span data-ttu-id="7b815-123">Gebruik het volgende script, vervangen *\<GroupAlias\>* door de alias van de groep die u wilt bijwerken en *\<UserAlias\>* met de alias van de gebruiker aan wie u machtigingen wilt toekennen.</span><span class="sxs-lookup"><span data-stu-id="7b815-123">Use the following script, replacing *\<GroupAlias\>* with the alias of the group that you want to update, and *\<UserAlias\>* with the alias of the user to whom you want to grant permissions.</span></span> <span data-ttu-id="7b815-124">[Maak verbinding met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) om dit script uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="7b815-124">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) to run this script.</span></span>

```PowerShell
$groupAlias = "<GroupAlias>"
$userAlias = "<UserAlias>"
$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

<span data-ttu-id="7b815-125">Nadat de cmdlet is uitgevoerd, kunnen gebruikers naar Outlook of de webversie van Outlook gaan om als groep e-mail te verzenden door het e-mailadres van de groep toe te voegen aan het veld **van** .</span><span class="sxs-lookup"><span data-stu-id="7b815-125">Once the cmdlet is executed, users can go to Outlook or Outlook on the web to send as the group, by adding the group email address to the **From** field.</span></span>

## <a name="create-classifications-for-microsoft-365-groups-in-your-organization"></a><span data-ttu-id="7b815-126">Classificaties maken voor Microsoft 365-groepen in uw organisatie</span><span class="sxs-lookup"><span data-stu-id="7b815-126">Create classifications for Microsoft 365 Groups in your organization</span></span>

<span data-ttu-id="7b815-127">U kunt met de gebruikers in uw organisatie tekstlabels labels maken die door gebruikers in uw organisatie worden ingesteld wanneer ze een Microsoft 365-groep maken.</span><span class="sxs-lookup"><span data-stu-id="7b815-127">You can create sensitivity labels that the users in your organization can set when they create a Microsoft 365 Group.</span></span> <span data-ttu-id="7b815-128">Als u groepen wilt classificeren, raden we u aan om beschikbare palletlabels te gebruiken in plaats van de eerdere classificatiefunctie voor groepen.</span><span class="sxs-lookup"><span data-stu-id="7b815-128">If you want to classify groups, we recommend using sensitivity labels instead of the previous groups classification feature.</span></span> <span data-ttu-id="7b815-129">Zie voor meer informatie over het gebruik van tekstlabels labels [gebruiken om de inhoud in Microsoft teams, Microsoft 365-groepen en SharePoint-sites te beveiligen](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="7b815-129">For information about using sensitivity labels, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7b815-130">Als u momenteel classificatie labels gebruikt, zijn deze niet langer beschikbaar voor gebruikers die groepen maken wanneer de functie gevoelige labels zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="7b815-130">If you are currently using classification labels, they will no longer be available to users who create groups once sensitivity labels are enabled.</span></span>

<span data-ttu-id="7b815-131">U kunt nog steeds de eerdere classificatiefunctie voor groepen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="7b815-131">You can still use the previous groups classification feature.</span></span> <span data-ttu-id="7b815-132">U kunt classificaties maken die gebruikers in uw organisatie kunnen instellen wanneer ze een Microsoft 365-groep maken.</span><span class="sxs-lookup"><span data-stu-id="7b815-132">You can create classifications that the users in your organization can set when they create an Microsoft 365 Group.</span></span> <span data-ttu-id="7b815-133">U kunt bijvoorbeeld instellen dat gebruikers ' standaard ', ' Secret ' en ' beste geheim ' kunnen instellen voor groepen die ze maken.</span><span class="sxs-lookup"><span data-stu-id="7b815-133">For example, you can allow users to set "Standard", "Secret", and "Top Secret" on groups they create.</span></span> <span data-ttu-id="7b815-134">Groeps classificaties worden niet standaard ingesteld en u moet deze maken om de gebruikers in te stellen.</span><span class="sxs-lookup"><span data-stu-id="7b815-134">Group classifications aren't set by default and you need to create it in order for your users to set it.</span></span> <span data-ttu-id="7b815-135">Gebruik Azure Active Directory PowerShell om uw gebruikers te laten verwijzen naar de gebruiks richtlijnen van uw organisatie voor Microsoft 365 groepen.</span><span class="sxs-lookup"><span data-stu-id="7b815-135">Use Azure Active Directory PowerShell to point your users to your organization's usage guidelines for Microsoft 365 Groups.</span></span>

<span data-ttu-id="7b815-136">Ga naar [Azure Active Directory-cmdlets voor het configureren van de groepsinstellingen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets) en volg de stappen in het venster **instellingen voor maken** om de classificatie voor Microsoft 365-groepen te definiëren.</span><span class="sxs-lookup"><span data-stu-id="7b815-136">Check out [Azure Active Directory cmdlets for configuring group settings](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets) and follow the steps in the **Create settings at the directory level** to define the classification for Microsoft 365 Groups.</span></span>

```powershell
$setting["ClassificationList"] = "Low Impact, Medium Impact, High Impact"
```

<span data-ttu-id="7b815-137">Als u een beschrijving aan elke classificatie wilt koppelen, kunt u het kenmerk  *ClassificationDescriptions* van de instellingen gebruiken om te definiëren.</span><span class="sxs-lookup"><span data-stu-id="7b815-137">In order to associate a description to each classification you can use the settings attribute  *ClassificationDescriptions* to define.</span></span>

```powershell
$setting["ClassificationDescriptions"] ="Classification:Description,Classification:Description"
```

<span data-ttu-id="7b815-138">waarbij classificatie overeenkomt met de tekenreeksen in de ClassificationList.</span><span class="sxs-lookup"><span data-stu-id="7b815-138">where Classification matches the strings in the ClassificationList.</span></span>

<span data-ttu-id="7b815-139">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="7b815-139">Example:</span></span>

```powershell
$setting["ClassificationDescriptions"] = "Low Impact: General communication, Medium Impact: Company internal data , High Impact: Data that has regulatory requirements"
```

<span data-ttu-id="7b815-140">Nadat u de bovenstaande Azure Active Directory-cmdlet hebt uitgevoerd om uw classificatie in te stellen, voert u de cmdlet [set-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/Set-UnifiedGroup) uit als u de classificatie voor een bepaalde groep wilt instellen.</span><span class="sxs-lookup"><span data-stu-id="7b815-140">After you run the above Azure Active Directory cmdlet to set your classification, run the [Set-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/Set-UnifiedGroup) cmdlet if you want to set the classification for a specific group.</span></span>

```powershell
Set-UnifiedGroup <LowImpactGroup@constoso.com> -Classification <LowImpact>
```

<span data-ttu-id="7b815-141">U maakt een nieuwe groep met een classificatie.</span><span class="sxs-lookup"><span data-stu-id="7b815-141">Or create a new group with a classification.</span></span>

```powershell
New-UnifiedGroup <HighImpactGroup@constoso.com> -Classification <HighImpact> -AccessType <Public>
```

<span data-ttu-id="7b815-142">Zie [Using PowerShell with Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) (PowerShell gebruiken met Exchange Online) en [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor meer informatie over het gebruik van Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7b815-142">Check out [Using PowerShell with Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) and [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) for more details on using Exchange Online PowerShell.</span></span>

<span data-ttu-id="7b815-143">Nadat deze instellingen zijn ingeschakeld, kunnen de groepseigenaar een classificatie kiezen in de vervolgkeuzelijst in de webversie van Outlook en Outlook, en deze opslaan via de paginagroep **bewerken** .</span><span class="sxs-lookup"><span data-stu-id="7b815-143">Once these settings are enabled, the group owner will be able to choose a classification from the drop down menu in Outlook on the Web and Outlook, and save it from the **Edit** group page.</span></span>

![Kies Microsoft 365-groeps classificatie](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)

## <a name="hide-microsoft-365-groups-from-the-global-address-list"></a><span data-ttu-id="7b815-145">Microsoft 365 groepen verbergen in de algemene adreslijst.</span><span class="sxs-lookup"><span data-stu-id="7b815-145">Hide Microsoft 365 Groups from the global address list.</span></span>
<span data-ttu-id="7b815-146"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="7b815-146"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="7b815-147">U kunt opgeven of een Microsoft 365-groep moet worden weergegeven in de algemene adreslijst (GAL) en in de andere lijsten van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="7b815-147">You can specify whether a Microsoft 365 Group appears in the global address list (GAL) and other lists in your organization.</span></span> <span data-ttu-id="7b815-148">Als u bijvoorbeeld een juridische afdeling hebt die u niet wilt weergeven in de adreslijst, kunt u ervoor zorgen dat de groep niet meer wordt weergegeven in de algemene adreslijst.</span><span class="sxs-lookup"><span data-stu-id="7b815-148">For example, if you have a legal department group that you don't want to show up in the address list, you can stop that group from appearing in the GAL.</span></span> <span data-ttu-id="7b815-149">Voer de Set-Unified groep-cmdlet uit om de groep te verbergen in de adreslijst, zoals hier:</span><span class="sxs-lookup"><span data-stu-id="7b815-149">Run the Set-Unified Group cmdlet to hide the group from the address list like this:</span></span>

```powershell
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-microsoft-365-groups"></a><span data-ttu-id="7b815-150">Instellen dat alleen interne gebruikers berichten mogen verzenden naar Microsoft 365-groepen</span><span class="sxs-lookup"><span data-stu-id="7b815-150">Allow only internal users to send message to Microsoft 365 Groups</span></span>
<span data-ttu-id="7b815-151"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="7b815-151"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="7b815-152">Als u niet wilt dat gebruikers van andere organisaties een e-mailbericht verzenden naar een Microsoft 365-groep, kunt u de instellingen voor die groep wijzigen.</span><span class="sxs-lookup"><span data-stu-id="7b815-152">If you don't want users from other organizations to send emails to a Microsoft 365 Group, you can change the settings for that group.</span></span> <span data-ttu-id="7b815-153">Met deze optie kunnen alleen interne gebruikers een e-mailbericht sturen naar uw groep.</span><span class="sxs-lookup"><span data-stu-id="7b815-153">It will allow only internal users to send an email to your group.</span></span> <span data-ttu-id="7b815-154">Als een externe gebruiker een bericht naar die groep probeert te sturen, wordt dit genegeerd.</span><span class="sxs-lookup"><span data-stu-id="7b815-154">If an external user tries to send a message to that group, it will be rejected.</span></span>

<span data-ttu-id="7b815-155">Voer de Set-UnifiedGroup cmdlet uit om deze instelling bij te werken, zoals hier:</span><span class="sxs-lookup"><span data-stu-id="7b815-155">Run the Set-UnifiedGroup cmdlet to update this setting, like this:</span></span>

```powershell
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-microsoft-365-groups"></a><span data-ttu-id="7b815-156">MailTips toevoegen aan Microsoft 365-groepen</span><span class="sxs-lookup"><span data-stu-id="7b815-156">Add MailTips to Microsoft 365 Groups</span></span>
<span data-ttu-id="7b815-157"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="7b815-157"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="7b815-158">Wanneer een afzender een e-mailbericht naar een Microsoft 365-groep wil verzenden, kan er een MailTip worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="7b815-158">Whenever a sender tries to send an email to a Microsoft 365 Group, a MailTip can be shown to them.</span></span>

<span data-ttu-id="7b815-159">Voer de cmdlet Set-Unified Group uit om een mailTip aan de groep toe te voegen:</span><span class="sxs-lookup"><span data-stu-id="7b815-159">Run the Set-Unified Group cmdlet to add a mailTip to the group:</span></span>

```powershell
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

<span data-ttu-id="7b815-160">Met MailTip kunt u ook MailTipTranslations instellen, wat extra talen voor de MailTip opgeven.</span><span class="sxs-lookup"><span data-stu-id="7b815-160">Along with MailTip, you can also set MailTipTranslations, which specifies additional languages for the MailTip.</span></span> <span data-ttu-id="7b815-161">Stel dat u de Spaanse vertaling wilt gebruiken, en voer de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="7b815-161">Suppose you want to have the Spanish translation, then run the following command:</span></span>

```powershell
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-the-display-name-of-the-microsoft-365-group"></a><span data-ttu-id="7b815-162">De weergavenaam van de Microsoft 365-groep wijzigen</span><span class="sxs-lookup"><span data-stu-id="7b815-162">Change the display name of the Microsoft 365 Group</span></span>

<span data-ttu-id="7b815-163">De weergavenaam geeft de naam van de Microsoft 365-groep aan.</span><span class="sxs-lookup"><span data-stu-id="7b815-163">The display name specifies the name of the Microsoft 365 Group.</span></span> <span data-ttu-id="7b815-164">U kunt deze naam zien in uw Exchange Admin Center of het Microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="7b815-164">You can see this name in your exchange admin center or Microsoft 365 admin center.</span></span> <span data-ttu-id="7b815-165">U kunt de weergavenaam van de groep wijzigen of een weergavenaam toewijzen aan een bestaande groep Microsoft 365 door de opdracht Set-UnifiedGroup uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="7b815-165">You can edit the display name of the group or assign a display name to an existing Microsoft 365 Group by running the Set-UnifiedGroup command:</span></span>

```powershell
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-microsoft-365-groups-for-outlook-to-public-or-private"></a><span data-ttu-id="7b815-166">De standaardinstelling voor Microsoft 365 groepen voor Outlook wijzigen van openbaar naar persoonlijk</span><span class="sxs-lookup"><span data-stu-id="7b815-166">Change the default setting of Microsoft 365 Groups for Outlook to Public or Private</span></span>
<span data-ttu-id="7b815-167"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="7b815-167"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="7b815-168">Microsoft 365-groepen in Outlook worden standaard als privé gemaakt.</span><span class="sxs-lookup"><span data-stu-id="7b815-168">Microsoft 365 Groups in Outlook are created as Private by default.</span></span> <span data-ttu-id="7b815-169">Als uw organisatie Microsoft 365-groepen wil maken als standaard publiek (of terug naar privé), gebruikt u deze syntaxis voor de PowerShell-cmdlet:</span><span class="sxs-lookup"><span data-stu-id="7b815-169">If your organization wants Microsoft 365 Groups to be created as Public by default (or back to Private), use this PowerShell cmdlet syntax:</span></span>

 `Set-OrganizationConfig -DefaultGroupAccessType Public`

<span data-ttu-id="7b815-170">Als privé-instelling:</span><span class="sxs-lookup"><span data-stu-id="7b815-170">To set to Private:</span></span>

 `Set-OrganizationConfig -DefaultGroupAccessType Private`

<span data-ttu-id="7b815-171">Ga als volgt te werk om de instelling te controleren:</span><span class="sxs-lookup"><span data-stu-id="7b815-171">To verify the setting:</span></span>

 `Get-OrganizationConfig | ft DefaultGroupAccessType`

<span data-ttu-id="7b815-172">Zie [set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) en [Get-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/get-organizationconfig)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="7b815-172">To learn more, see [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) and [Get-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/get-organizationconfig).</span></span>

## <a name="microsoft-365-groups-cmdlets"></a><span data-ttu-id="7b815-173">Cmdlets voor Microsoft 365-groepen</span><span class="sxs-lookup"><span data-stu-id="7b815-173">Microsoft 365 Groups cmdlets</span></span>

<span data-ttu-id="7b815-174">De volgende cmdlets kunnen worden gebruikt met Microsoft 365 groepen.</span><span class="sxs-lookup"><span data-stu-id="7b815-174">The following cmdlets can be used with Microsoft 365 Groups.</span></span>

|<span data-ttu-id="7b815-175">**Naam van cmdlet**</span><span class="sxs-lookup"><span data-stu-id="7b815-175">**Cmdlet name**</span></span>|<span data-ttu-id="7b815-176">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="7b815-176">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="7b815-177">Get-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="7b815-177">Get-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616182) <br/> |<span data-ttu-id="7b815-178">Gebruik deze cmdlet om bestaande Microsoft 365-groepen te zoeken en om eigenschappen van het groepsobject te bekijken.</span><span class="sxs-lookup"><span data-stu-id="7b815-178">Use this cmdlet to look up existing Microsoft 365 Groups, and to view properties of the group object</span></span>  <br/> |
|[<span data-ttu-id="7b815-179">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="7b815-179">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189) <br/> |<span data-ttu-id="7b815-180">De eigenschappen van een bepaalde Microsoft 365-groep bijwerken</span><span class="sxs-lookup"><span data-stu-id="7b815-180">Update the properties of a specific Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="7b815-181">New-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="7b815-181">New-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616183) <br/> |<span data-ttu-id="7b815-182">Maak een nieuwe groep Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7b815-182">Create a new Microsoft 365 Group.</span></span> <span data-ttu-id="7b815-183">Deze cmdlet biedt een minimale set parameters.</span><span class="sxs-lookup"><span data-stu-id="7b815-183">This cmdlet provides a minimal set of parameters.</span></span> <span data-ttu-id="7b815-184">Als u waarden wilt instellen voor uitgebreide eigenschappen, gebruikt u Set-UnifiedGroup nadat u de nieuwe groep hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="7b815-184">To set values for extended properties, use Set-UnifiedGroup after creating the new group</span></span>  <br/> |
|[<span data-ttu-id="7b815-185">Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="7b815-185">Remove-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616186) <br/> |<span data-ttu-id="7b815-186">Een bestaande Microsoft 365-groep verwijderen</span><span class="sxs-lookup"><span data-stu-id="7b815-186">Delete an existing Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="7b815-187">Get-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="7b815-187">Get-UnifiedGroupLinks</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616194) <br/> |<span data-ttu-id="7b815-188">Gegevens voor lidmaatschap en eigenaar ophalen voor een Microsoft 365-groep</span><span class="sxs-lookup"><span data-stu-id="7b815-188">Retrieve membership and owner information for a Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="7b815-189">Add-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="7b815-189">Add-UnifiedGroupLinks</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616191) <br/> |<span data-ttu-id="7b815-190">Leden, eigenaren en abonnees toevoegen aan een bestaande Microsoft 365-groep</span><span class="sxs-lookup"><span data-stu-id="7b815-190">Add members, owners, and subscribers to an existing Microsoft 365 Group</span></span> <br/> |
|[<span data-ttu-id="7b815-191">Remove-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="7b815-191">Remove-UnifiedGroupLinks</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616195) <br/> |<span data-ttu-id="7b815-192">Leden en eigenaren verwijderen uit een bestaande Microsoft 365-groep</span><span class="sxs-lookup"><span data-stu-id="7b815-192">Remove owners and members from an existing Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="7b815-193">Get-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="7b815-193">Get-UserPhoto</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=536510) <br/> |<span data-ttu-id="7b815-194">Wordt gebruikt om informatie weer te geven over de foto van een gebruiker die is gekoppeld aan een account.</span><span class="sxs-lookup"><span data-stu-id="7b815-194">Used to view information about the user photo associated with an account.</span></span> <span data-ttu-id="7b815-195">Foto's van gebruikers worden opgeslagen in Active Directory</span><span class="sxs-lookup"><span data-stu-id="7b815-195">User photos are stored in Active Directory</span></span>  <br/> |
|[<span data-ttu-id="7b815-196">Set-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="7b815-196">Set-UserPhoto</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=536511) <br/> |<span data-ttu-id="7b815-197">Wordt gebruikt om een gebruikers foto aan een account te koppelen.</span><span class="sxs-lookup"><span data-stu-id="7b815-197">Used to associate a user photo with an account.</span></span> <span data-ttu-id="7b815-198">Foto's van gebruikers worden opgeslagen in Active Directory</span><span class="sxs-lookup"><span data-stu-id="7b815-198">User photos are stored in Active Directory</span></span>  <br/> |
|[<span data-ttu-id="7b815-199">Remove-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="7b815-199">Remove-UserPhoto</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=536512) <br/> |<span data-ttu-id="7b815-200">De foto voor een Microsoft 365-groep verwijderen</span><span class="sxs-lookup"><span data-stu-id="7b815-200">Remove the photo for an Microsoft 365 Group</span></span>  <br/> |

## <a name="related-topics"></a><span data-ttu-id="7b815-201">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="7b815-201">Related topics</span></span>

[<span data-ttu-id="7b815-202">Distributielijsten upgraden naar Microsoft 365-groepen</span><span class="sxs-lookup"><span data-stu-id="7b815-202">Upgrade distribution lists to Microsoft 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists)

<span data-ttu-id="7b815-203">[Beheren wie Microsoft 365-groepen kunnen](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups) maken</span><span class="sxs-lookup"><span data-stu-id="7b815-203">[Manage who can create Microsoft 365 Groups](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups)</span></span>

[<span data-ttu-id="7b815-204">Gasttoegang tot Microsoft 365-groepen beheren</span><span class="sxs-lookup"><span data-stu-id="7b815-204">Manage guest access to Microsoft 365 Groups</span></span>](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[<span data-ttu-id="7b815-205">Dynamisch groepslidmaatschap wijzigen in</span><span class="sxs-lookup"><span data-stu-id="7b815-205">Change static group membership to dynamic in</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)
