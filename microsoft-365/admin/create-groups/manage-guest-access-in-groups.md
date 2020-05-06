---
title: Gasttoegang beheren in Microsoft 365-groepen
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
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
description: Meer informatie over het toevoegen van gasten aan een Microsoft 365-groep, het bekijken van gastgebruikers en het gebruik van PowerShell om de toegang van gasten te beheren.
ms.openlocfilehash: 1b315ac89936aaa69072959031733fef4e0a5c1a
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049189"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Gasttoegang beheren in Microsoft 365-groepen

Standaard is gasttoegang voor Microsoft 365-groepen ingeschakeld voor uw organisatie. Beheerders kunnen bepalen of gasten toegang moeten krijgen tot groepen voor hun hele organisatie of voor afzonderlijke groepen.

Wanneer de groep is ingeschakeld, kunnen groepsleden gastgebruikers uitnodigen voor een Microsoft 365-groep via Outlook on Web. Uitnodigingen worden ter goedkeuring naar de eigenaar van de groep gestuurd.

> [!Note]
> Yammer Enterprise-netwerken die zich in de native modus of de [EU Geo bevinden,](https://go.microsoft.com/fwlink/?linkid=2107357) bieden geen ondersteuning voor netwerkgasten.
> Microsoft 365 Connected Yammer-groepen bieden momenteel geen ondersteuning voor gasttoegang, maar u niet-verbonden externe groepen maken in uw Yammer-netwerk. Zie [Externe groepen maken en beheren in Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) voor instructies.

### <a name="edit-guest-information"></a>Gastgegevens bewerken

Na goedkeuring wordt de gastgebruiker toegevoegd aan de directory en de groep.

Gasttoegang in groepen wordt vaak gebruikt als onderdeel van een breder scenario dat SharePoint of Teams bevat. Deze services hebben hun eigen instellingen voor het delen van gasten. Zie voor volledige instructies voor het instellen van het delen van gasten in groepen, SharePoint en Teams:

- [Samenwerken met gasten op een site](../../solutions/collaborate-in-site.md)
- [Samenwerken met gasten in een team](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>Groepen gasttoegang beheren

Als u gasttoegang in groepen wilt in- of uitschakelen, u dit doen in het Microsoft 365-beheercentrum.

1. Ga in het beheercentrum naar de **instellingen** \> **instellingen** en selecteer **Microsoft 365-groepen**.
  
2. Kies op de pagina **Microsoft 365-groepen** of u mensen buiten de groepresources van uw organisatie toegang wilt geven of groepseigenaren mensen buiten uw organisatie aan groepen wilt laten toevoegen.

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>Gasten toevoegen aan een Microsoft 365-groep vanuit het beheercentrum

Als de gast al in uw directory aanwezig is, u deze toevoegen aan uw groepen vanuit het Microsoft 365-beheercentrum.
  
1. Ga in het beheercentrum naar de pagina **Groepen** > **groepen.**
  
2. Klik op de groep waaraan u de gast wilt toevoegen en selecteer **Alles weergeven en leden beheren** op het tabblad **Leden.** 
  
4. Selecteer **Leden toevoegen**en kies de naam van de gast die u wilt toevoegen.
    
5. Kies **Opslaan**.

Als u een gast rechtstreeks aan de directory wilt toevoegen, u [Azure Active Directory B2B-samenwerkingsgebruikers toevoegen aan de Azure-portal.](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator)

Als u een van de gegevens van een gast wilt bewerken, u [de profielgegevens van een gebruiker toevoegen of bijwerken met Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).
  
## <a name="block-guest-users-from-a-specific-group"></a>Gastgebruikers uit een specifieke groep blokkeren

Als u gasten toegang wilt geven tot de meeste groepen, maar een aantal hebt waar u gasttoegang wilt voorkomen, u gasttoegang voor afzonderlijke groepen blokkeren met Microsoft PowerShell.

U moet de preview-versie van [Azure Active Directory PowerShell voor Grafiek](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (modulenaam **AzureADPreview)** gebruiken om de instelling voor gasttoegang op groepsniveau te wijzigen:

- Als u nog nooit een versie van de Azure AD PowerShell-module hebt geïnstalleerd, raadpleegt u [De Azure AD-module installeren](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) en de instructies volgen om de openbare preview-release te installeren.

- Als u de versie met algemene beschikbaarheid van 2.0 van de Azure AD PowerShell-module (AzureAD) hebt geïnstalleerd, moet u deze verwijderen door deze uit te voeren `Uninstall-Module AzureAD` in uw PowerShell-sessie en vervolgens de preview-versie installeren door . `Install-Module AzureADPreview`

- Als u de preview-versie `Install-Module AzureADPreview` al hebt geïnstalleerd, voert u uit om te controleren of deze de nieuwste versie van deze module is.

> [!NOTE]
> U moet algemene beheerdersrechten hebben om deze opdrachten uit te voeren. 

Voer het volgende * / * script uit en wijzig de naam van de groep waar u gasttoegang wilt blokkeren.

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
    
![Schermafbeelding van het PowerShell-venster waarin wordt weergegeven dat de toegang tot gastgroepen is ingesteld op false.](../../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a>Gasttoegang toestaan of blokkeren op basis van hun domein

U gastgebruikers toestaan of blokkeren die een specifiek domein gebruiken. Als uw bedrijf (Contoso) bijvoorbeeld een partnerschap heeft met een ander bedrijf (Fabrikam), u Fabrikam toevoegen aan uw lijst Toestaan, zodat uw gebruikers deze gasten aan hun groepen kunnen toevoegen.

Zie [Uitnodigingen voor B2B-gebruikers van specifieke organisaties toestaan of blokkeren](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)voor meer informatie.

## <a name="add-guests-to-the-global-address-list"></a>Gasten toevoegen aan de wereldwijde adreslijst

Gasten zijn standaard niet zichtbaar in de Exchange Global Address List. Gebruik de onderstaande stappen om een gast zichtbaar te maken in de algemene adreslijst.

Zoek de ObjectID van de gastgebruiker door het uitvoeren van:

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

[AzureADUser instellen](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
