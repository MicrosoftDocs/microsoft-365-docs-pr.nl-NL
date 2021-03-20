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
description: In dit artikel leert u hoe u algemene beheertaken kunt uitvoeren voor Microsoft 365-groepen in PowerShell.
ms.openlocfilehash: adf796ad2f2ee7a304c578cd42c700f2b44e7a5b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911048"
---
# <a name="manage-microsoft-365-groups-with-powershell"></a><span data-ttu-id="a924d-103">Microsoft 365-groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="a924d-103">Manage Microsoft 365 Groups with PowerShell</span></span>

<span data-ttu-id="a924d-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="a924d-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="a924d-105">In dit artikel vindt u de stappen voor het uitvoeren van algemene beheertaken voor groepen in Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a924d-105">This article provides the steps for doing common management tasks for Groups in Microsoft PowerShell.</span></span> <span data-ttu-id="a924d-106">Er worden ook de PowerShell-cmdlets voor groepen vermeld.</span><span class="sxs-lookup"><span data-stu-id="a924d-106">It also lists the PowerShell cmdlets for Groups.</span></span> <span data-ttu-id="a924d-107">Zie SharePoint Online-sites beheren met PowerShell voor meer informatie over het beheren van [SharePoint-sites.](/sharepoint/manage-team-and-communication-sites-in-powershell)</span><span class="sxs-lookup"><span data-stu-id="a924d-107">For info about managing SharePoint sites, see [Manage SharePoint Online sites using PowerShell](/sharepoint/manage-team-and-communication-sites-in-powershell).</span></span>

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a><span data-ttu-id="a924d-108">Koppeling maken naar de gebruiksrichtlijnen voor Microsoft 365 Groepen</span><span class="sxs-lookup"><span data-stu-id="a924d-108">Link to your Microsoft 365 Groups usage guidelines</span></span>
<span data-ttu-id="a924d-109"><a name="BK_LinkToGuideLines"> </a></span><span class="sxs-lookup"><span data-stu-id="a924d-109"><a name="BK_LinkToGuideLines"> </a></span></span>

<span data-ttu-id="a924d-110">Wanneer gebruikers een groep maken of [bewerken in Outlook,](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx)kunt u een koppeling naar de gebruiksrichtlijnen van uw organisatie laten zien.</span><span class="sxs-lookup"><span data-stu-id="a924d-110">When users [create or edit a group in Outlook](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx), you can show them a link to your organization's usage guidelines.</span></span> <span data-ttu-id="a924d-111">Als u bijvoorbeeld een specifiek voorvoegsel of achtervoegsel wilt toevoegen aan een groepsnaam.</span><span class="sxs-lookup"><span data-stu-id="a924d-111">For example, if you require a specific prefix or suffix to be added to a group name.</span></span>

<span data-ttu-id="a924d-112">Gebruik azure Active Directory (Azure AD) PowerShell om uw gebruikers te wijzen op de gebruiksrichtlijnen van uw organisatie voor Microsoft 365-groepen.</span><span class="sxs-lookup"><span data-stu-id="a924d-112">Use the Azure Active Directory (Azure AD) PowerShell to point your users to your organization's usage guidelines for Microsoft 365 groups.</span></span> <span data-ttu-id="a924d-113">Bekijk [Azure Active Directory-cmdlets](/azure/active-directory/enterprise-users/groups-settings-cmdlets) voor het configureren  van groepsinstellingen en volg de stappen in de instellingen maken op adreslijstniveau om de gebruiksrichtlijn hyperlink te definiëren.</span><span class="sxs-lookup"><span data-stu-id="a924d-113">Check out [Azure Active Directory cmdlets for configuring group settings](/azure/active-directory/enterprise-users/groups-settings-cmdlets) and follow the steps in the **Create settings at the directory level** to define the usage guideline hyperlink.</span></span> <span data-ttu-id="a924d-114">Wanneer u de AAD-cmdlet hebt uitgevoerd, zien gebruikers de koppeling naar uw richtlijnen wanneer ze een groep maken of bewerken in Outlook.</span><span class="sxs-lookup"><span data-stu-id="a924d-114">Once you run the AAD cmdlet, user's will see the link to your guidelines when they create or edit a group in Outlook.</span></span>

![Een nieuwe groep maken met koppeling gebruiksrichtlijnen](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)

![Klik op Richtlijnen voor groepsgebruik om de richtlijnen voor Office 365-groepen van uw organisatie weer te geven](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)

## <a name="allow-users-to-send-as-the-microsoft-365-group"></a><span data-ttu-id="a924d-117">Gebruikers toestaan verzenden als de Microsoft 365-groep</span><span class="sxs-lookup"><span data-stu-id="a924d-117">Allow users to Send as the Microsoft 365 Group</span></span>
<span data-ttu-id="a924d-118"><a name="BK_LinkToGuideLines"> </a></span><span class="sxs-lookup"><span data-stu-id="a924d-118"><a name="BK_LinkToGuideLines"> </a></span></span>

<span data-ttu-id="a924d-119">Als u uw Microsoft 365-groepen wilt inschakelen voor Verzenden als, gebruikt u de [cmdlets Add-RecipientPermission](/powershell/module/exchange/add-recipientpermission) en [Get-RecipientPermission](/powershell/module/exchange/get-recipientpermission) om dit te configureren.</span><span class="sxs-lookup"><span data-stu-id="a924d-119">If you want to enable your Microsoft 365 groups to "Send As", use the [Add-RecipientPermission](/powershell/module/exchange/add-recipientpermission) and [Get-RecipientPermission](/powershell/module/exchange/get-recipientpermission) cmdlets to configure this.</span></span> <span data-ttu-id="a924d-120">Nadat u deze instelling hebt ingeschakeld, kunnen gebruikers van de Microsoft 365-groep Outlook of de webversie van Outlook gebruiken om e-mail te verzenden en te beantwoorden als de Microsoft 365-groep.</span><span class="sxs-lookup"><span data-stu-id="a924d-120">Once you enable this setting, Microsoft 365 group users can use Outlook or Outlook on the web to send and reply to email as the Microsoft 365 group.</span></span> <span data-ttu-id="a924d-121">Gebruikers kunnen naar de groep gaan, een nieuw e-mailbericht maken en het veld Verzenden als wijzigen in het e-mailadres van de groep.</span><span class="sxs-lookup"><span data-stu-id="a924d-121">Users can go to the group, create a new email, and change the "Send As" field to the group's email address.</span></span>

<span data-ttu-id="a924d-122">([U kunt dit ook doen in het Exchange-beheercentrum](/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group).)</span><span class="sxs-lookup"><span data-stu-id="a924d-122">([You can also do this in the Exchange Admin Center](/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group).)</span></span>

<span data-ttu-id="a924d-123">Gebruik het volgende script, vervangen door de alias van de groep die u wilt bijwerken en met de alias van de gebruiker aan wie u machtigingen *\<GroupAlias\>* *\<UserAlias\>* wilt verlenen.</span><span class="sxs-lookup"><span data-stu-id="a924d-123">Use the following script, replacing *\<GroupAlias\>* with the alias of the group that you want to update, and *\<UserAlias\>* with the alias of the user to whom you want to grant permissions.</span></span> <span data-ttu-id="a924d-124">[Maak verbinding met Exchange Online PowerShell om](/powershell/exchange/connect-to-exchange-online-powershell) dit script uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="a924d-124">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) to run this script.</span></span>

```PowerShell
$groupAlias = "<GroupAlias>"
$userAlias = "<UserAlias>"
$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

<span data-ttu-id="a924d-125">Wanneer de cmdlet is uitgevoerd, kunnen gebruikers naar de webversie van Outlook of Outlook gaan om deze als groep te verzenden door het groeps-e-mailadres toe te voegen aan het veld **Van.**</span><span class="sxs-lookup"><span data-stu-id="a924d-125">Once the cmdlet is executed, users can go to Outlook or Outlook on the web to send as the group, by adding the group email address to the **From** field.</span></span>

## <a name="create-classifications-for-microsoft-365-groups-in-your-organization"></a><span data-ttu-id="a924d-126">Classificaties maken voor Microsoft 365 Groepen in uw organisatie</span><span class="sxs-lookup"><span data-stu-id="a924d-126">Create classifications for Microsoft 365 Groups in your organization</span></span>

<span data-ttu-id="a924d-127">U kunt gevoeligheidslabels maken die de gebruikers in uw organisatie kunnen instellen wanneer ze een Microsoft 365-groep maken.</span><span class="sxs-lookup"><span data-stu-id="a924d-127">You can create sensitivity labels that the users in your organization can set when they create a Microsoft 365 Group.</span></span> <span data-ttu-id="a924d-128">Als u groepen wilt classificeren, raden we u aan gevoeligheidslabels te gebruiken in plaats van de vorige functie voor groepenclassificatie.</span><span class="sxs-lookup"><span data-stu-id="a924d-128">If you want to classify groups, we recommend using sensitivity labels instead of the previous groups classification feature.</span></span> <span data-ttu-id="a924d-129">Zie Gevoeligheidslabels gebruiken om inhoud in [Microsoft Teams, Microsoft 365-groepen en SharePoint-sites](../compliance/sensitivity-labels-teams-groups-sites.md)te beveiligen voor informatie over het gebruik van gevoeligheidslabels.</span><span class="sxs-lookup"><span data-stu-id="a924d-129">For information about using sensitivity labels, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a924d-130">Als u momenteel classificatielabels gebruikt, zijn deze niet meer beschikbaar voor gebruikers die groepen maken zodra gevoeligheidslabels zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="a924d-130">If you are currently using classification labels, they will no longer be available to users who create groups once sensitivity labels are enabled.</span></span>

<span data-ttu-id="a924d-131">U kunt de classificatiefunctie voor vorige groepen nog steeds gebruiken.</span><span class="sxs-lookup"><span data-stu-id="a924d-131">You can still use the previous groups classification feature.</span></span> <span data-ttu-id="a924d-132">U kunt classificaties maken die de gebruikers in uw organisatie kunnen instellen wanneer ze een Microsoft 365-groep maken.</span><span class="sxs-lookup"><span data-stu-id="a924d-132">You can create classifications that the users in your organization can set when they create an Microsoft 365 Group.</span></span> <span data-ttu-id="a924d-133">U kunt bijvoorbeeld toestaan dat gebruikers 'Standaard', 'Geheim' en 'Top Secret' instellen voor groepen die ze maken.</span><span class="sxs-lookup"><span data-stu-id="a924d-133">For example, you can allow users to set "Standard", "Secret", and "Top Secret" on groups they create.</span></span> <span data-ttu-id="a924d-134">Groepsclassificaties zijn niet standaard ingesteld en u moet deze maken zodat uw gebruikers deze kunnen instellen.</span><span class="sxs-lookup"><span data-stu-id="a924d-134">Group classifications aren't set by default and you need to create it in order for your users to set it.</span></span> <span data-ttu-id="a924d-135">Gebruik Azure Active Directory PowerShell om uw gebruikers te wijzen op de gebruiksrichtlijnen van uw organisatie voor Microsoft 365 Groepen.</span><span class="sxs-lookup"><span data-stu-id="a924d-135">Use Azure Active Directory PowerShell to point your users to your organization's usage guidelines for Microsoft 365 Groups.</span></span>

<span data-ttu-id="a924d-136">Bekijk [Azure Active Directory-cmdlets](/azure/active-directory/users-groups-roles/groups-settings-cmdlets) voor het configureren  van groepsinstellingen en volg de stappen in de instellingen maken op adreslijstniveau om de classificatie voor Microsoft 365 Groepen te definiëren.</span><span class="sxs-lookup"><span data-stu-id="a924d-136">Check out [Azure Active Directory cmdlets for configuring group settings](/azure/active-directory/users-groups-roles/groups-settings-cmdlets) and follow the steps in the **Create settings at the directory level** to define the classification for Microsoft 365 Groups.</span></span>

```powershell
$setting["ClassificationList"] = "Low Impact, Medium Impact, High Impact"
```

<span data-ttu-id="a924d-137">Als u een beschrijving wilt koppelen aan elke classificatie, kunt u het instellingenkenmerk  *Classificatiedescripties* gebruiken om te definiëren.</span><span class="sxs-lookup"><span data-stu-id="a924d-137">In order to associate a description to each classification you can use the settings attribute  *ClassificationDescriptions* to define.</span></span>

```powershell
$setting["ClassificationDescriptions"] ="Classification:Description,Classification:Description"
```

<span data-ttu-id="a924d-138">waarbij Classificatie overeenkomt met de tekenreeksen in de classificatielijst.</span><span class="sxs-lookup"><span data-stu-id="a924d-138">where Classification matches the strings in the ClassificationList.</span></span>

<span data-ttu-id="a924d-139">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="a924d-139">Example:</span></span>

```powershell
$setting["ClassificationDescriptions"] = "Low Impact: General communication, Medium Impact: Company internal data , High Impact: Data that has regulatory requirements"
```

<span data-ttu-id="a924d-140">Nadat u de bovenstaande Azure Active Directory-cmdlet hebt uitgevoerd om uw classificatie in te stellen, kunt u de cmdlet [Set-UnifiedGroup](/powershell/module/exchange/Set-UnifiedGroup) uitvoeren als u de classificatie voor een bepaalde groep wilt instellen.</span><span class="sxs-lookup"><span data-stu-id="a924d-140">After you run the above Azure Active Directory cmdlet to set your classification, run the [Set-UnifiedGroup](/powershell/module/exchange/Set-UnifiedGroup) cmdlet if you want to set the classification for a specific group.</span></span>

```powershell
Set-UnifiedGroup <LowImpactGroup@constoso.com> -Classification <LowImpact>
```

<span data-ttu-id="a924d-141">Of maak een nieuwe groep met een classificatie.</span><span class="sxs-lookup"><span data-stu-id="a924d-141">Or create a new group with a classification.</span></span>

```powershell
New-UnifiedGroup <HighImpactGroup@constoso.com> -Classification <HighImpact> -AccessType <Public>
```

<span data-ttu-id="a924d-142">Zie [Using PowerShell with Exchange Online](/powershell/exchange/exchange-online-powershell) (PowerShell gebruiken met Exchange Online) en [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor meer informatie over het gebruik van Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a924d-142">Check out [Using PowerShell with Exchange Online](/powershell/exchange/exchange-online-powershell) and [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for more details on using Exchange Online PowerShell.</span></span>

<span data-ttu-id="a924d-143">Wanneer deze instellingen zijn ingeschakeld, kan de groepseigenaar een classificatie kiezen in de vervolgkeuzelijst in de  webversie van Outlook en Outlook en deze opslaan op de groepspagina Bewerken.</span><span class="sxs-lookup"><span data-stu-id="a924d-143">Once these settings are enabled, the group owner will be able to choose a classification from the drop down menu in Outlook on the Web and Outlook, and save it from the **Edit** group page.</span></span>

![Microsoft 365-groepsclassificatie kiezen](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)

## <a name="hide-microsoft-365-groups-from-the-global-address-list"></a><span data-ttu-id="a924d-145">Microsoft 365 Groepen verbergen in de algemene adreslijst.</span><span class="sxs-lookup"><span data-stu-id="a924d-145">Hide Microsoft 365 Groups from the global address list.</span></span>
<span data-ttu-id="a924d-146"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="a924d-146"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="a924d-147">U kunt opgeven of een Microsoft 365-groep wordt weergegeven in de algemene adreslijst (GAL) en andere lijsten in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="a924d-147">You can specify whether a Microsoft 365 Group appears in the global address list (GAL) and other lists in your organization.</span></span> <span data-ttu-id="a924d-148">Als u bijvoorbeeld een juridische afdelingsgroep hebt die u niet wilt laten zien in de adreslijst, kunt u voorkomen dat deze groep wordt weergegeven in de adreslijst.</span><span class="sxs-lookup"><span data-stu-id="a924d-148">For example, if you have a legal department group that you don't want to show up in the address list, you can stop that group from appearing in the GAL.</span></span> <span data-ttu-id="a924d-149">Voer de Set-Unified Groep groep uit om de groep als dit te verbergen in de adreslijst:</span><span class="sxs-lookup"><span data-stu-id="a924d-149">Run the Set-Unified Group cmdlet to hide the group from the address list like this:</span></span>

```powershell
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-microsoft-365-groups"></a><span data-ttu-id="a924d-150">Alleen interne gebruikers toestaan een bericht te verzenden naar Microsoft 365-groepen</span><span class="sxs-lookup"><span data-stu-id="a924d-150">Allow only internal users to send message to Microsoft 365 Groups</span></span>
<span data-ttu-id="a924d-151"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="a924d-151"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="a924d-152">Als u niet wilt dat gebruikers van andere organisaties e-mailberichten verzenden naar een Microsoft 365-groep, kunt u de instellingen voor die groep wijzigen.</span><span class="sxs-lookup"><span data-stu-id="a924d-152">If you don't want users from other organizations to send emails to a Microsoft 365 Group, you can change the settings for that group.</span></span> <span data-ttu-id="a924d-153">Alleen interne gebruikers kunnen een e-mail naar uw groep verzenden.</span><span class="sxs-lookup"><span data-stu-id="a924d-153">It will allow only internal users to send an email to your group.</span></span> <span data-ttu-id="a924d-154">Als een externe gebruiker een bericht naar die groep probeert te verzenden, wordt dit geweigerd.</span><span class="sxs-lookup"><span data-stu-id="a924d-154">If an external user tries to send a message to that group, it will be rejected.</span></span>

<span data-ttu-id="a924d-155">Voer de Set-UnifiedGroup cmdlet uit om deze instelling bij te werken, zoals dit:</span><span class="sxs-lookup"><span data-stu-id="a924d-155">Run the Set-UnifiedGroup cmdlet to update this setting, like this:</span></span>

```powershell
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-microsoft-365-groups"></a><span data-ttu-id="a924d-156">MailTips toevoegen aan Microsoft 365-groepen</span><span class="sxs-lookup"><span data-stu-id="a924d-156">Add MailTips to Microsoft 365 Groups</span></span>
<span data-ttu-id="a924d-157"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="a924d-157"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="a924d-158">Wanneer een afzender een e-mail naar een Microsoft 365-groep probeert te verzenden, kan een MailTip aan hen worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="a924d-158">Whenever a sender tries to send an email to a Microsoft 365 Group, a MailTip can be shown to them.</span></span>

<span data-ttu-id="a924d-159">Voer de Set-Unified groep uit om een e-mailtip toe te voegen aan de groep:</span><span class="sxs-lookup"><span data-stu-id="a924d-159">Run the Set-Unified Group cmdlet to add a mailTip to the group:</span></span>

```powershell
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

<span data-ttu-id="a924d-160">Naast MailTip kunt u ook MailTipTranslations instellen, waarmee extra talen voor de MailTip worden opgegeven.</span><span class="sxs-lookup"><span data-stu-id="a924d-160">Along with MailTip, you can also set MailTipTranslations, which specifies additional languages for the MailTip.</span></span> <span data-ttu-id="a924d-161">Stel dat u de Spaanse vertaling wilt gebruiken en voer vervolgens de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="a924d-161">Suppose you want to have the Spanish translation, then run the following command:</span></span>

```powershell
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-the-display-name-of-the-microsoft-365-group"></a><span data-ttu-id="a924d-162">De weergavenaam van de Microsoft 365-groep wijzigen</span><span class="sxs-lookup"><span data-stu-id="a924d-162">Change the display name of the Microsoft 365 Group</span></span>

<span data-ttu-id="a924d-163">De weergavenaam geeft de naam van de Microsoft 365-groep aan.</span><span class="sxs-lookup"><span data-stu-id="a924d-163">The display name specifies the name of the Microsoft 365 Group.</span></span> <span data-ttu-id="a924d-164">U kunt deze naam zien in uw Exchange-beheercentrum of Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="a924d-164">You can see this name in your exchange admin center or Microsoft 365 admin center.</span></span> <span data-ttu-id="a924d-165">U kunt de weergavenaam van de groep bewerken of een weergavenaam toewijzen aan een bestaande Microsoft 365-groep door de opdracht Set-UnifiedGroup uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="a924d-165">You can edit the display name of the group or assign a display name to an existing Microsoft 365 Group by running the Set-UnifiedGroup command:</span></span>

```powershell
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-microsoft-365-groups-for-outlook-to-public-or-private"></a><span data-ttu-id="a924d-166">De standaardinstelling van Microsoft 365 Groepen voor Outlook wijzigen in Openbaar of Privé</span><span class="sxs-lookup"><span data-stu-id="a924d-166">Change the default setting of Microsoft 365 Groups for Outlook to Public or Private</span></span>
<span data-ttu-id="a924d-167"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="a924d-167"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="a924d-168">Microsoft 365 Groepen in Outlook worden standaard als Privé gemaakt.</span><span class="sxs-lookup"><span data-stu-id="a924d-168">Microsoft 365 Groups in Outlook are created as Private by default.</span></span> <span data-ttu-id="a924d-169">Als uw organisatie wil dat Microsoft 365 Groepen standaard worden gemaakt als Openbaar (of terug naar Privé), gebruikt u deze syntaxis van de PowerShell-cmdlet:</span><span class="sxs-lookup"><span data-stu-id="a924d-169">If your organization wants Microsoft 365 Groups to be created as Public by default (or back to Private), use this PowerShell cmdlet syntax:</span></span>

 `Set-OrganizationConfig -DefaultGroupAccessType Public`

<span data-ttu-id="a924d-170">Instellen op Privé:</span><span class="sxs-lookup"><span data-stu-id="a924d-170">To set to Private:</span></span>

 `Set-OrganizationConfig -DefaultGroupAccessType Private`

<span data-ttu-id="a924d-171">De instelling controleren:</span><span class="sxs-lookup"><span data-stu-id="a924d-171">To verify the setting:</span></span>

 `Get-OrganizationConfig | ft DefaultGroupAccessType`

<span data-ttu-id="a924d-172">Zie [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) en [Get-OrganizationConfig](/powershell/module/exchange/get-organizationconfig)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a924d-172">To learn more, see [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) and [Get-OrganizationConfig](/powershell/module/exchange/get-organizationconfig).</span></span>

## <a name="microsoft-365-groups-cmdlets"></a><span data-ttu-id="a924d-173">Microsoft 365 Groups-cmdlets</span><span class="sxs-lookup"><span data-stu-id="a924d-173">Microsoft 365 Groups cmdlets</span></span>

<span data-ttu-id="a924d-174">De volgende cmdlets kunnen worden gebruikt met Microsoft 365 Groepen.</span><span class="sxs-lookup"><span data-stu-id="a924d-174">The following cmdlets can be used with Microsoft 365 Groups.</span></span>

|<span data-ttu-id="a924d-175">**Cmdletnaam**</span><span class="sxs-lookup"><span data-stu-id="a924d-175">**Cmdlet name**</span></span>|<span data-ttu-id="a924d-176">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="a924d-176">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="a924d-177">Get-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="a924d-177">Get-UnifiedGroup</span></span>](/powershell/module/exchange/get-unifiedgroup) <br/> |<span data-ttu-id="a924d-178">Gebruik deze cmdlet om bestaande Microsoft 365-groepen op te zoeken en om eigenschappen van het groepsobject weer te geven</span><span class="sxs-lookup"><span data-stu-id="a924d-178">Use this cmdlet to look up existing Microsoft 365 Groups, and to view properties of the group object</span></span>  <br/> |
|[<span data-ttu-id="a924d-179">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="a924d-179">Set-UnifiedGroup</span></span>](/powershell/module/exchange/set-unifiedgroup) <br/> |<span data-ttu-id="a924d-180">De eigenschappen van een specifieke Microsoft 365-groep bijwerken</span><span class="sxs-lookup"><span data-stu-id="a924d-180">Update the properties of a specific Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="a924d-181">New-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="a924d-181">New-UnifiedGroup</span></span>](/powershell/module/exchange/new-unifiedgroup) <br/> |<span data-ttu-id="a924d-182">Een nieuwe Microsoft 365-groep maken.</span><span class="sxs-lookup"><span data-stu-id="a924d-182">Create a new Microsoft 365 Group.</span></span> <span data-ttu-id="a924d-183">Deze cmdlet biedt een minimale set parameters.</span><span class="sxs-lookup"><span data-stu-id="a924d-183">This cmdlet provides a minimal set of parameters.</span></span> <span data-ttu-id="a924d-184">Als u waarden wilt instellen voor uitgebreide eigenschappen, gebruikt u Set-UnifiedGroup na het maken van de nieuwe groep</span><span class="sxs-lookup"><span data-stu-id="a924d-184">To set values for extended properties, use Set-UnifiedGroup after creating the new group</span></span>  <br/> |
|[<span data-ttu-id="a924d-185">Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="a924d-185">Remove-UnifiedGroup</span></span>](/powershell/module/exchange/remove-unifiedgroup) <br/> |<span data-ttu-id="a924d-186">Een bestaande Microsoft 365-groep verwijderen</span><span class="sxs-lookup"><span data-stu-id="a924d-186">Delete an existing Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="a924d-187">Get-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="a924d-187">Get-UnifiedGroupLinks</span></span>](/powershell/module/exchange/get-unifiedgrouplinks) <br/> |<span data-ttu-id="a924d-188">Lidmaatschaps- en eigenaargegevens ophalen voor een Microsoft 365-groep</span><span class="sxs-lookup"><span data-stu-id="a924d-188">Retrieve membership and owner information for a Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="a924d-189">Add-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="a924d-189">Add-UnifiedGroupLinks</span></span>](/powershell/module/exchange/add-unifiedgrouplinks) <br/> |<span data-ttu-id="a924d-190">Leden, eigenaren en abonnees toevoegen aan een bestaande Microsoft 365-groep</span><span class="sxs-lookup"><span data-stu-id="a924d-190">Add members, owners, and subscribers to an existing Microsoft 365 Group</span></span> <br/> |
|[<span data-ttu-id="a924d-191">Remove-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="a924d-191">Remove-UnifiedGroupLinks</span></span>](/powershell/module/exchange/remove-unifiedgrouplinks) <br/> |<span data-ttu-id="a924d-192">Eigenaren en leden verwijderen uit een bestaande Microsoft 365-groep</span><span class="sxs-lookup"><span data-stu-id="a924d-192">Remove owners and members from an existing Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="a924d-193">Get-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="a924d-193">Get-UserPhoto</span></span>](/powershell/module/exchange/get-userphoto) <br/> |<span data-ttu-id="a924d-194">Wordt gebruikt om informatie weer te geven over de gebruikersfoto die is gekoppeld aan een account.</span><span class="sxs-lookup"><span data-stu-id="a924d-194">Used to view information about the user photo associated with an account.</span></span> <span data-ttu-id="a924d-195">Gebruikersfoto's worden opgeslagen in Active Directory</span><span class="sxs-lookup"><span data-stu-id="a924d-195">User photos are stored in Active Directory</span></span>  <br/> |
|[<span data-ttu-id="a924d-196">Set-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="a924d-196">Set-UserPhoto</span></span>](/powershell/module/exchange/set-userphoto) <br/> |<span data-ttu-id="a924d-197">Wordt gebruikt om een gebruikersfoto te koppelen aan een account.</span><span class="sxs-lookup"><span data-stu-id="a924d-197">Used to associate a user photo with an account.</span></span> <span data-ttu-id="a924d-198">Gebruikersfoto's worden opgeslagen in Active Directory</span><span class="sxs-lookup"><span data-stu-id="a924d-198">User photos are stored in Active Directory</span></span>  <br/> |
|[<span data-ttu-id="a924d-199">Remove-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="a924d-199">Remove-UserPhoto</span></span>](/powershell/module/exchange/remove-userphoto) <br/> |<span data-ttu-id="a924d-200">De foto voor een Microsoft 365-groep verwijderen</span><span class="sxs-lookup"><span data-stu-id="a924d-200">Remove the photo for an Microsoft 365 Group</span></span>  <br/> |

## <a name="related-topics"></a><span data-ttu-id="a924d-201">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="a924d-201">Related topics</span></span>

[<span data-ttu-id="a924d-202">Distributielijsten upgraden naar Microsoft 365 Groepen</span><span class="sxs-lookup"><span data-stu-id="a924d-202">Upgrade distribution lists to Microsoft 365 Groups</span></span>](/office365/admin/manage/upgrade-distribution-lists)

[<span data-ttu-id="a924d-203">Beheren wie Microsoft 365-groepen kunnen maken</span><span class="sxs-lookup"><span data-stu-id="a924d-203">Manage who can create Microsoft 365 Groups</span></span>](/office365/admin/create-groups/manage-creation-of-groups)

[<span data-ttu-id="a924d-204">Gasttoegang tot Microsoft 365-groepen beheren</span><span class="sxs-lookup"><span data-stu-id="a924d-204">Manage guest access to Microsoft 365 Groups</span></span>](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[<span data-ttu-id="a924d-205">Statisch groepslidmaatschap wijzigen in dynamisch in</span><span class="sxs-lookup"><span data-stu-id="a924d-205">Change static group membership to dynamic in</span></span>](/azure/active-directory/users-groups-roles/groups-change-type)