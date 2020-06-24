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
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Meer informatie over het toevoegen van gasten aan een Microsoft 365-groep, het bekijken van gastgebruikers en het gebruik van PowerShell om de toegang van gasten te beheren.
ms.openlocfilehash: 0322bd269f1c5637627461d136b40f6af4fc9540
ms.sourcegitcommit: 4512f54ba80d869d4c04e8f9bd897d1878280852
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/23/2020
ms.locfileid: "44854244"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Gasttoegang beheren in Microsoft 365-groepen

Standaard is gasttoegang voor Microsoft 365-groepen ingeschakeld voor uw organisatie. Beheerders kunnen bepalen of ze gasten toegang willen geven tot groepen voor hun hele organisatie of voor afzonderlijke groepen.

Wanneer deze is ingeschakeld, kunnen groepsleden gastgebruikers uitnodigen voor een Microsoft 365-groep via Outlook on Web. Uitnodigingen worden ter goedkeuring naar de eigenaar van de groep gestuurd.

Na goedkeuring wordt de gastgebruiker toegevoegd aan de map en de groep.

> [!Note]
> Yammer Enterprise-netwerken in native mode of de [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357) ondersteunen geen netwerkgasten.
> Microsoft 365 Connected Yammer-groepen bieden momenteel geen ondersteuning voor gasttoegang, maar u niet-verbonden, externe groepen in uw Yammer-netwerk maken. Zie [Externe groepen maken en beheren in Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) voor instructies.

Gasttoegang in groepen wordt vaak gebruikt als onderdeel van een breder scenario dat SharePoint of Teams omvat. Deze services hebben hun eigen instellingen voor het delen van gasten. Zie voor volledige instructies voor het instellen van het delen van gasten tussen groepen, SharePoint en Teams:

- [Samenwerken met gasten op een site](../../solutions/collaborate-in-site.md)
- [Samenwerken met gasten in een team](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>Toegang tot groepen beheren

Als u gasttoegang in groepen wilt in- of uitschakelen, u dit doen in het Microsoft 365-beheercentrum.

1. Ga in het beheercentrum naar **Alle** instellingen instellingen die \> **Settings** \> **orginstellingen weergeven** en selecteer op het tabblad **Services** **Microsoft 365-groepen**.
  
2. Kies op de pagina **Microsoft 365-groepen** of u mensen buiten uw organisatie groepsbronnen wilt laten openen of dat groepseigenaren mensen buiten uw organisatie aan groepen wilt toevoegen.

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>Gasten toevoegen aan een Microsoft 365-groep vanuit het beheercentrum

Als de gast al in uw map bestaat, u deze toevoegen aan uw groepen vanuit het Microsoft 365-beheercentrum.
  
1. Ga in het beheercentrum **Groups**naar de pagina  >  **Groepen groepen.**
  
2. Klik op de groep waaraan u de gast wilt toevoegen en selecteer **Alle leden weergeven en beheren** op het tabblad **Leden.** 
  
4. Selecteer **Leden toevoegen**en kies de naam van de gast die u wilt toevoegen.
    
5. Kies **Opslaan**.

Als u een gast rechtstreeks aan de map wilt toevoegen, u [Azure Active Directory B2B-samenwerkingsgebruikers toevoegen in de Azure-portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).

Als u een van de gegevens van een gast wilt bewerken, u [de profielgegevens](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)van een gebruiker toevoegen of bijwerken met Azure Active Directory.
  
## <a name="block-guest-users-from-a-specific-group"></a>Gastgebruikers blokkeren uit een specifieke groep

Als u gasttoegang tot de meeste groepen wilt toestaan, maar een aantal wilt hebben waar u gasttoegang wilt voorkomen, u de toegang van gasten voor afzonderlijke groepen blokkeren met Microsoft PowerShell.

U moet de voorbeeldversie van [Azure Active Directory PowerShell voor Grafiek](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (modulenaam **AzureADPreview)** gebruiken om de instelling voor gasttoegang op groepsniveau te wijzigen:

- Als u nog geen versie van de Azure AD PowerShell-module eerder hebt geïnstalleerd, raadpleegt u [De Azure AD-module installeren](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) en de instructies volgen om de versie van de openbare preview te installeren.

- Als u de 2.0 algemene beschikbaarheidsversie van de Azure AD PowerShell-module (AzureAD) hebt geïnstalleerd, moet u deze verwijderen door deze uit te voeren `Uninstall-Module AzureAD` in uw PowerShell-sessie en vervolgens de preview-versie installeren door `Install-Module AzureADPreview` .

- Als u de preview-versie al hebt geïnstalleerd, moet u `Install-Module AzureADPreview` ervoor zorgen dat dit de nieuwste versie van deze module is.

> [!NOTE]
> U moet algemene beheerdersrechten hebben om deze opdrachten uit te voeren. 

Voer het volgende script uit en wijzig */<GroupName/>* de naam van de groep waar u gasttoegang wilt blokkeren.

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

Voer deze opdracht uit om uw instellingen te verifiëren:

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

De verificatie ziet er als volgt uit:
    
![Schermafbeelding van het PowerShell-venster waaruit blijkt dat de toegang tot de gastgroep is ingesteld op false.](../../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a>Toegang van gasten toestaan of blokkeren op basis van hun domein

U gastgebruikers die een specifiek domein gebruiken toestaan of blokkeren. Als uw bedrijf (Contoso) bijvoorbeeld een partnerschap heeft met een ander bedrijf (Fabrikam), u Fabrikam toevoegen aan uw lijst Toestaan, zodat uw gebruikers deze gasten aan hun groepen kunnen toevoegen.

Zie [Uitnodigingen voor B2B-gebruikers van specifieke organisaties toestaan of blokkeren voor](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)meer informatie.

## <a name="add-guests-to-the-global-address-list"></a>Gasten toevoegen aan de algemene adreslijst

Gasten zijn standaard niet zichtbaar in de algemene adreslijst van Exchange. Gebruik de onderstaande stappen om een gast zichtbaar te maken in de algemene adreslijst.

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

[AzureADUser instellen](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
