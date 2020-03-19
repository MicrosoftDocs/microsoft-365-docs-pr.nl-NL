---
title: Toegang tot gasten beheren in Office 365-groepen
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.date: 12/18/2019
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Meer informatie over het toevoegen van gasten aan een Office 365-groep, gastgebruikers weergeven en PowerShell gebruiken om de toegang van gasten te beheren.
ms.openlocfilehash: 3314746e4d12c318eaae8fbfa34c2ed0b4d31aed
ms.sourcegitcommit: dcea75af89f5f80ec6670346ee176407e043de54
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/12/2020
ms.locfileid: "42806900"
---
# <a name="manage-guest-access-in-office-365-groups"></a>Toegang tot gasten beheren in Office 365-groepen

Standaard is gasttoegang voor Office 365-groepen ingeschakeld voor uw organisatie. Beheerders kunnen bepalen of gasten toegang moeten krijgen tot groepen voor hun hele organisatie of voor afzonderlijke groepen.

Wanneer deze is ingeschakeld, kunnen groepsleden gastgebruikers uitnodigen voor een Office 365-groep via Outlook on Web. Uitnodigingen worden ter goedkeuring naar de eigenaar van de groep gestuurd.

> [!Note]
> Yammer Enterprise-netwerken die zich in de native modus of de [EU Geo bevinden,](https://go.microsoft.com/fwlink/?linkid=2107357) ondersteunen geen netwerkgasten.
> Office 365 Verbonden Yammer-groepen ondersteunen momenteel geen gasttoegang, maar u niet-verbonden, externe groepen maken in uw Yammer-netwerk. Zie [Externe groepen maken en beheren in Yammer](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a.aspx) voor instructies.

### <a name="edit-guest-information"></a>Gastgegevens bewerken

Eenmaal goedgekeurd, wordt de gastgebruiker toegevoegd aan de map en de groep.

Gasttoegang in groepen wordt vaak gebruikt als onderdeel van een breder scenario dat SharePoint of Teams omvat. Deze services hebben hun eigen instellingen voor het delen van gasten. Zie voor volledige instructies voor het instellen van delen van gasten tussen groepen, SharePoint en Teams:

- [Samenwerken met gasten op een site](../../solutions/collaborate-in-site.md)
- [Samenwerken met gasten in een team](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>Toegang tot groepen gasten beheren

Als u gasttoegang in groepen wilt in- of uitschakelen, u dit doen in het Microsoft 365-beheercentrum.

1. Ga in het beheercentrum naar de pagina **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">beheer & invoeginstellingen.</a>

2. Selecteer **Office 365-groepen**.
  
3. Kies op de pagina **Office 365-groepen** of je mensen buiten je organisatie toegang wilt geven tot groepsbronnen of dat groepseigenaren mensen buiten je organisatie aan groepen toevoegen.

## <a name="add-guests-to-an-office-365-group-from-the-admin-center"></a>Gasten toevoegen aan een Office 365-groep vanuit het beheercentrum

Als de gast al in uw map staat, u deze toevoegen aan uw groepen vanuit het Microsoft 365-beheercentrum.
  
1. Ga in het beheercentrum naar de pagina > **Groepengroepen.** **Groups**
  
2. Selecteer de groep waaraan u de gast wilt toevoegen en selecteer **Alle weergave en beheer leden** op het tabblad **Leden.** 
  
4. Selecteer **Leden toevoegen**en kies de naam van de gast die u wilt toevoegen.
    
5. Kies **Opslaan**.

Als u een gast rechtstreeks aan de map wilt toevoegen, u [Azure Active Directory B2B-gebruikers toevoegen in de Azure-portal.](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator)

Als u de gegevens van een gast wilt bewerken, u [de profielgegevens van een gebruiker toevoegen of bijwerken met Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)
  
## <a name="block-guest-users-from-a-specific-group"></a>Gastgebruikers blokkeren uit een specifieke groep

Als u gasttoegang tot de meeste groepen wilt toestaan, maar er een aantal wilt hebben waar u toegang tot gasten wilt voorkomen, u de toegang van gasten voor afzonderlijke groepen blokkeren met Microsoft PowerShell.

U moet de voorbeeldversie van [Azure Active Directory PowerShell voor Grafiek (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (modulenaam **AzureADPreview)** gebruiken om de instelling voor gasttoegang op groepsniveau te wijzigen:

- Zie [De Azure AD-module installeren](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) en de instructies volgen om de openbare preview-versie te installeren als u nog geen versie van de Azure AD PowerShell-module hebt geïnstalleerd.

- Als u de versie voor algemene beschikbaarheid van de Azure AD PowerShell-module (AzureAD) `Uninstall-Module AzureAD` hebt geïnstalleerd, moet u deze verwijderen `Install-Module AzureADPreview`door in uw PowerShell-sessie uit te voeren en vervolgens de preview-versie installeren door .

- Als u de preview-versie `Install-Module AzureADPreview` al hebt geïnstalleerd, voert u uit om te controleren of dit de nieuwste versie van deze module is.

> [!NOTE]
> U moet algemene beheerdersrechten hebben om deze opdrachten uit te voeren. 

Voer het volgende * / * script uit en wijzig de naam van de groep waar u de toegang van gasten wilt blokkeren.

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

Voer de opdracht uit om uw instellingen te verifiëren:

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

De verificatie ziet er als volgt uit:
    
![Schermafbeelding van het PowerShell-venster waarop wordt weergegeven dat de toegang tot de gastgroep is ingesteld op false.](../../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a>Toegang tot gasten toestaan of blokkeren op basis van hun domein

U gastgebruikers die een specifiek domein gebruiken toestaan of blokkeren. Als uw bedrijf (Contoso) bijvoorbeeld een partnerschap heeft met een ander bedrijf (Fabrikam), u Fabrikam toevoegen aan uw lijst Toestaan, zodat uw gebruikers deze gasten aan hun groepen kunnen toevoegen.

Zie [Uitnodigingen voor B2B-gebruikers van specifieke organisaties toestaan of blokkeren](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)voor meer informatie.

## <a name="add-guests-to-the-global-address-list"></a>Gasten toevoegen aan de algemene adreslijst

Gasten zijn standaard niet zichtbaar in de exchange Global Address List. Gebruik de onderstaande stappen om een gast zichtbaar te maken in de algemene adreslijst.

Zoek de ObjectID van de gastgebruiker door uit te voeren:

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

Voer vervolgens het volgende uit met de juiste waarden voor ObjectID, GivenName, Achternaam, DisplayName en Telefoonnummer.

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-articles"></a>Verwante artikelen

[Groepslidmaatschap beheren in het Microsoft 365-beheercentrum](add-or-remove-members-from-groups.md)
  
[Azure Active Directory-toegangsbeoordelingen](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
