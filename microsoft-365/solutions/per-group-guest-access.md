---
title: Voorkomen dat gasten worden toegevoegd aan een specifieke groep
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Meer informatie over hoe u ervoor kunt zorgen dat gasten niet aan een specifieke groep worden toegevoegd
ms.openlocfilehash: 8bee26bf5ec323536ca1ac6f25ce96927634cee7
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/11/2020
ms.locfileid: "49660046"
---
# <a name="prevent-guests-from-being-added-to-a-specific-microsoft-365-group-or-microsoft-teams-team"></a>Voorkomen dat gasten worden toegevoegd aan een specifieke Microsoft 365-groep of een Microsoft teams-team

Als u gasttoegang wilt verlenen tot de meeste groepen en teams, maar wel een deel van de toegang tot gasttoegang wilt blokkeren, kunt u gasttoegang voor afzonderlijke groepen en teams blokkeren. (Het blokkeren van toegang tot een team is ongedaan gemaakt door gasttoegang tot de bijbehorende groep te blokkeren). Hiermee voorkomt u dat nieuwe gasten worden toegevoegd, maar geen gasten die al deel uitmaken van de groep of het team.

Als u de palletlabels in uw organisatie gebruikt, raden we u aan ze te gebruiken voor het beheren van gasttoegang per groep. Voor informatie over hoe u dit doet, [kunt u de vertrouwelijkheids labels gebruiken om inhoud te beschermen in Microsoft teams, Microsoft 365-groepen en SharePoint-sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites). Dit is de aanbevolen aanpak.

## <a name="change-group-settings-using-microsoft-powershell"></a>Groepsinstellingen wijzigen met Microsoft PowerShell

U kunt er ook voor zorgen dat nieuwe gasten worden toegevoegd aan individuele groepen met behulp van PowerShell. Houd er rekening mee dat de gekoppelde SharePoint-site van het team [afzonderlijke besturingselementen](https://docs.microsoft.com/sharepoint/change-external-sharing-site)voor het delen van gasten bevat.

U moet de preview-versie van [Azure Active Directory PowerShell voor Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) gebruiken om de instelling voor gasttoegang op het groepeerniveau te wijzigen:

- Als u nog geen versie van de Azure AD PowerShell-module hebt geïnstalleerd, raadpleegt u [de module van Azure AD installeren](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) en volgt u de instructies voor het installeren van de openbare preview-versie.

- Als u de algemene beschikbaarheid van 2,0 van de versie van de Azure AD PowerShell-module (AzureAD) hebt geïnstalleerd, moet u deze verwijderen door `Uninstall-Module AzureAD` in uw PowerShell-sessie te worden uitgevoerd, en de preview-versie vervolgens te installeren `Install-Module AzureADPreview` .

- Als u de preview-versie al hebt geïnstalleerd, controleert u `Install-Module AzureADPreview` of deze de nieuwste versie van deze module is.

> [!NOTE]
> U moet over globale beheerdersrechten beschikken om deze opdrachten uit te voeren. 

Voer het volgende script uit en wijzig */<GroupName/>* de naam van de groep waarin u gasttoegang wilt blokkeren.

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

Als u uw instellingen wilt controleren, voert u deze opdracht uit:

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

De verificatie ziet er als volgt uit:
    
![Schermafbeelding van het PowerShell-venster waarin wordt aangegeven dat toegang tot gast groepen is ingesteld op ONWAAR.](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a>Gasttoegang op basis van hun domein toestaan of blokkeren

U kunt gast personen die een specifiek domein gebruiken toestaan of blokkeren. Als uw bedrijf (Contoso) bijvoorbeeld een partnership heeft met een ander bedrijf (fabrikam), kunt u fabrikam toevoegen aan uw lijst toestaan, zodat uw gebruikers deze gasten kunnen toevoegen aan hun groepen.

Zie [uitnodigingen voor B2B-gebruikers in specifieke organisaties toestaan of blokkeren](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)voor meer informatie.

## <a name="add-guests-to-the-global-address-list"></a>Gasten toevoegen aan de algemene adreslijst

Gasten worden standaard niet weergegeven in de algemene adreslijst van Exchange. Volg de onderstaande stappen om een gast zichtbaar te maken in de algemene adreslijst.

Ga als volgt te werk om de ObjectID van de gast te zoeken:

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

Voer vervolgens de volgende opdracht uit om de juiste waarden te gebruiken voor ObjectID, OpgegevenNaam, achternaam, weergavenaam en TelephoneNumber.

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-topics"></a>Verwante onderwerpen

[Stapsgewijze planning voor samenwerking](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Uw plan voor samenwerking maken](collaboration-governance-first.md)

[Groepslidmaatschap beheren in het Microsoft 365-Beheercentrum](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups)
  
[Azure Active Directory Access-beoordelingen](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
