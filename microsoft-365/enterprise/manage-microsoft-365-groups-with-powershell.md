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
# <a name="manage-microsoft-365-groups-with-powershell"></a>Microsoft 365-groepen beheren met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

In dit artikel vindt u de stappen voor het uitvoeren van algemene beheertaken voor groepen in Microsoft PowerShell. Er worden ook de PowerShell-cmdlets voor groepen vermeld. Zie SharePoint Online-sites beheren met PowerShell voor meer informatie over het beheren van [SharePoint-sites.](/sharepoint/manage-team-and-communication-sites-in-powershell)

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a>Koppeling maken naar de gebruiksrichtlijnen voor Microsoft 365 Groepen
<a name="BK_LinkToGuideLines"> </a>

Wanneer gebruikers een groep maken of [bewerken in Outlook,](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx)kunt u een koppeling naar de gebruiksrichtlijnen van uw organisatie laten zien. Als u bijvoorbeeld een specifiek voorvoegsel of achtervoegsel wilt toevoegen aan een groepsnaam.

Gebruik azure Active Directory (Azure AD) PowerShell om uw gebruikers te wijzen op de gebruiksrichtlijnen van uw organisatie voor Microsoft 365-groepen. Bekijk [Azure Active Directory-cmdlets](/azure/active-directory/enterprise-users/groups-settings-cmdlets) voor het configureren  van groepsinstellingen en volg de stappen in de instellingen maken op adreslijstniveau om de gebruiksrichtlijn hyperlink te definiëren. Wanneer u de AAD-cmdlet hebt uitgevoerd, zien gebruikers de koppeling naar uw richtlijnen wanneer ze een groep maken of bewerken in Outlook.

![Een nieuwe groep maken met koppeling gebruiksrichtlijnen](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)

![Klik op Richtlijnen voor groepsgebruik om de richtlijnen voor Office 365-groepen van uw organisatie weer te geven](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)

## <a name="allow-users-to-send-as-the-microsoft-365-group"></a>Gebruikers toestaan verzenden als de Microsoft 365-groep
<a name="BK_LinkToGuideLines"> </a>

Als u uw Microsoft 365-groepen wilt inschakelen voor Verzenden als, gebruikt u de [cmdlets Add-RecipientPermission](/powershell/module/exchange/add-recipientpermission) en [Get-RecipientPermission](/powershell/module/exchange/get-recipientpermission) om dit te configureren. Nadat u deze instelling hebt ingeschakeld, kunnen gebruikers van de Microsoft 365-groep Outlook of de webversie van Outlook gebruiken om e-mail te verzenden en te beantwoorden als de Microsoft 365-groep. Gebruikers kunnen naar de groep gaan, een nieuw e-mailbericht maken en het veld Verzenden als wijzigen in het e-mailadres van de groep.

([U kunt dit ook doen in het Exchange-beheercentrum](/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group).)

Gebruik het volgende script, vervangen door de alias van de groep die u wilt bijwerken en met de alias van de gebruiker aan wie u machtigingen *\<GroupAlias\>* *\<UserAlias\>* wilt verlenen. [Maak verbinding met Exchange Online PowerShell om](/powershell/exchange/connect-to-exchange-online-powershell) dit script uit te voeren.

```PowerShell
$groupAlias = "<GroupAlias>"
$userAlias = "<UserAlias>"
$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

Wanneer de cmdlet is uitgevoerd, kunnen gebruikers naar de webversie van Outlook of Outlook gaan om deze als groep te verzenden door het groeps-e-mailadres toe te voegen aan het veld **Van.**

## <a name="create-classifications-for-microsoft-365-groups-in-your-organization"></a>Classificaties maken voor Microsoft 365 Groepen in uw organisatie

U kunt gevoeligheidslabels maken die de gebruikers in uw organisatie kunnen instellen wanneer ze een Microsoft 365-groep maken. Als u groepen wilt classificeren, raden we u aan gevoeligheidslabels te gebruiken in plaats van de vorige functie voor groepenclassificatie. Zie Gevoeligheidslabels gebruiken om inhoud in [Microsoft Teams, Microsoft 365-groepen en SharePoint-sites](../compliance/sensitivity-labels-teams-groups-sites.md)te beveiligen voor informatie over het gebruik van gevoeligheidslabels.

> [!IMPORTANT]
> Als u momenteel classificatielabels gebruikt, zijn deze niet meer beschikbaar voor gebruikers die groepen maken zodra gevoeligheidslabels zijn ingeschakeld.

U kunt de classificatiefunctie voor vorige groepen nog steeds gebruiken. U kunt classificaties maken die de gebruikers in uw organisatie kunnen instellen wanneer ze een Microsoft 365-groep maken. U kunt bijvoorbeeld toestaan dat gebruikers 'Standaard', 'Geheim' en 'Top Secret' instellen voor groepen die ze maken. Groepsclassificaties zijn niet standaard ingesteld en u moet deze maken zodat uw gebruikers deze kunnen instellen. Gebruik Azure Active Directory PowerShell om uw gebruikers te wijzen op de gebruiksrichtlijnen van uw organisatie voor Microsoft 365 Groepen.

Bekijk [Azure Active Directory-cmdlets](/azure/active-directory/users-groups-roles/groups-settings-cmdlets) voor het configureren  van groepsinstellingen en volg de stappen in de instellingen maken op adreslijstniveau om de classificatie voor Microsoft 365 Groepen te definiëren.

```powershell
$setting["ClassificationList"] = "Low Impact, Medium Impact, High Impact"
```

Als u een beschrijving wilt koppelen aan elke classificatie, kunt u het instellingenkenmerk  *Classificatiedescripties* gebruiken om te definiëren.

```powershell
$setting["ClassificationDescriptions"] ="Classification:Description,Classification:Description"
```

waarbij Classificatie overeenkomt met de tekenreeksen in de classificatielijst.

Voorbeeld:

```powershell
$setting["ClassificationDescriptions"] = "Low Impact: General communication, Medium Impact: Company internal data , High Impact: Data that has regulatory requirements"
```

Nadat u de bovenstaande Azure Active Directory-cmdlet hebt uitgevoerd om uw classificatie in te stellen, kunt u de cmdlet [Set-UnifiedGroup](/powershell/module/exchange/Set-UnifiedGroup) uitvoeren als u de classificatie voor een bepaalde groep wilt instellen.

```powershell
Set-UnifiedGroup <LowImpactGroup@constoso.com> -Classification <LowImpact>
```

Of maak een nieuwe groep met een classificatie.

```powershell
New-UnifiedGroup <HighImpactGroup@constoso.com> -Classification <HighImpact> -AccessType <Public>
```

Zie [Using PowerShell with Exchange Online](/powershell/exchange/exchange-online-powershell) (PowerShell gebruiken met Exchange Online) en [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor meer informatie over het gebruik van Exchange Online PowerShell.

Wanneer deze instellingen zijn ingeschakeld, kan de groepseigenaar een classificatie kiezen in de vervolgkeuzelijst in de  webversie van Outlook en Outlook en deze opslaan op de groepspagina Bewerken.

![Microsoft 365-groepsclassificatie kiezen](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)

## <a name="hide-microsoft-365-groups-from-the-global-address-list"></a>Microsoft 365 Groepen verbergen in de algemene adreslijst.
<a name="BKMK_CreateClassification"> </a>

U kunt opgeven of een Microsoft 365-groep wordt weergegeven in de algemene adreslijst (GAL) en andere lijsten in uw organisatie. Als u bijvoorbeeld een juridische afdelingsgroep hebt die u niet wilt laten zien in de adreslijst, kunt u voorkomen dat deze groep wordt weergegeven in de adreslijst. Voer de Set-Unified Groep groep uit om de groep als dit te verbergen in de adreslijst:

```powershell
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-microsoft-365-groups"></a>Alleen interne gebruikers toestaan een bericht te verzenden naar Microsoft 365-groepen
<a name="BKMK_CreateClassification"> </a>

Als u niet wilt dat gebruikers van andere organisaties e-mailberichten verzenden naar een Microsoft 365-groep, kunt u de instellingen voor die groep wijzigen. Alleen interne gebruikers kunnen een e-mail naar uw groep verzenden. Als een externe gebruiker een bericht naar die groep probeert te verzenden, wordt dit geweigerd.

Voer de Set-UnifiedGroup cmdlet uit om deze instelling bij te werken, zoals dit:

```powershell
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-microsoft-365-groups"></a>MailTips toevoegen aan Microsoft 365-groepen
<a name="BKMK_CreateClassification"> </a>

Wanneer een afzender een e-mail naar een Microsoft 365-groep probeert te verzenden, kan een MailTip aan hen worden weergegeven.

Voer de Set-Unified groep uit om een e-mailtip toe te voegen aan de groep:

```powershell
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

Naast MailTip kunt u ook MailTipTranslations instellen, waarmee extra talen voor de MailTip worden opgegeven. Stel dat u de Spaanse vertaling wilt gebruiken en voer vervolgens de volgende opdracht uit:

```powershell
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-the-display-name-of-the-microsoft-365-group"></a>De weergavenaam van de Microsoft 365-groep wijzigen

De weergavenaam geeft de naam van de Microsoft 365-groep aan. U kunt deze naam zien in uw Exchange-beheercentrum of Microsoft 365-beheercentrum. U kunt de weergavenaam van de groep bewerken of een weergavenaam toewijzen aan een bestaande Microsoft 365-groep door de opdracht Set-UnifiedGroup uitvoeren:

```powershell
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-microsoft-365-groups-for-outlook-to-public-or-private"></a>De standaardinstelling van Microsoft 365 Groepen voor Outlook wijzigen in Openbaar of Privé
<a name="BKMK_CreateClassification"> </a>

Microsoft 365 Groepen in Outlook worden standaard als Privé gemaakt. Als uw organisatie wil dat Microsoft 365 Groepen standaard worden gemaakt als Openbaar (of terug naar Privé), gebruikt u deze syntaxis van de PowerShell-cmdlet:

 `Set-OrganizationConfig -DefaultGroupAccessType Public`

Instellen op Privé:

 `Set-OrganizationConfig -DefaultGroupAccessType Private`

De instelling controleren:

 `Get-OrganizationConfig | ft DefaultGroupAccessType`

Zie [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) en [Get-OrganizationConfig](/powershell/module/exchange/get-organizationconfig)voor meer informatie.

## <a name="microsoft-365-groups-cmdlets"></a>Microsoft 365 Groups-cmdlets

De volgende cmdlets kunnen worden gebruikt met Microsoft 365 Groepen.

|**Cmdletnaam**|**Beschrijving**|
|:-----|:-----|
|[Get-UnifiedGroup](/powershell/module/exchange/get-unifiedgroup) <br/> |Gebruik deze cmdlet om bestaande Microsoft 365-groepen op te zoeken en om eigenschappen van het groepsobject weer te geven  <br/> |
|[Set-UnifiedGroup](/powershell/module/exchange/set-unifiedgroup) <br/> |De eigenschappen van een specifieke Microsoft 365-groep bijwerken  <br/> |
|[New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) <br/> |Een nieuwe Microsoft 365-groep maken. Deze cmdlet biedt een minimale set parameters. Als u waarden wilt instellen voor uitgebreide eigenschappen, gebruikt u Set-UnifiedGroup na het maken van de nieuwe groep  <br/> |
|[Remove-UnifiedGroup](/powershell/module/exchange/remove-unifiedgroup) <br/> |Een bestaande Microsoft 365-groep verwijderen  <br/> |
|[Get-UnifiedGroupLinks](/powershell/module/exchange/get-unifiedgrouplinks) <br/> |Lidmaatschaps- en eigenaargegevens ophalen voor een Microsoft 365-groep  <br/> |
|[Add-UnifiedGroupLinks](/powershell/module/exchange/add-unifiedgrouplinks) <br/> |Leden, eigenaren en abonnees toevoegen aan een bestaande Microsoft 365-groep <br/> |
|[Remove-UnifiedGroupLinks](/powershell/module/exchange/remove-unifiedgrouplinks) <br/> |Eigenaren en leden verwijderen uit een bestaande Microsoft 365-groep  <br/> |
|[Get-UserPhoto](/powershell/module/exchange/get-userphoto) <br/> |Wordt gebruikt om informatie weer te geven over de gebruikersfoto die is gekoppeld aan een account. Gebruikersfoto's worden opgeslagen in Active Directory  <br/> |
|[Set-UserPhoto](/powershell/module/exchange/set-userphoto) <br/> |Wordt gebruikt om een gebruikersfoto te koppelen aan een account. Gebruikersfoto's worden opgeslagen in Active Directory  <br/> |
|[Remove-UserPhoto](/powershell/module/exchange/remove-userphoto) <br/> |De foto voor een Microsoft 365-groep verwijderen  <br/> |

## <a name="related-topics"></a>Verwante onderwerpen

[Distributielijsten upgraden naar Microsoft 365 Groepen](/office365/admin/manage/upgrade-distribution-lists)

[Beheren wie Microsoft 365-groepen kunnen maken](/office365/admin/create-groups/manage-creation-of-groups)

[Gasttoegang tot Microsoft 365-groepen beheren](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[Statisch groepslidmaatschap wijzigen in dynamisch in](/azure/active-directory/users-groups-roles/groups-change-type)