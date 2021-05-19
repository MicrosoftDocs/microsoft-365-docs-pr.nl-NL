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
recommendations: false
description: Informatie over het voorkomen dat gasten worden toegevoegd aan een specifieke groep
ms.openlocfilehash: 1db2055f3e546c05905dbf4c854333387112f06e
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538925"
---
# <a name="prevent-guests-from-being-added-to-a-specific-microsoft-365-group-or-microsoft-teams-team"></a>Voorkomen dat gasten worden toegevoegd aan een specifieke Microsoft 365 of Microsoft Teams team

Als u gasttoegang wilt toestaan tot de meeste groepen en teams, maar u een aantal plaatsen wilt hebben waar u gasttoegang wilt voorkomen, kunt u gasttoegang voor afzonderlijke groepen en teams blokkeren. (Het blokkeren van gasttoegang tot een team wordt uitgevoerd door gasttoegang tot de gekoppelde groep te blokkeren.) Hiermee voorkomt u dat nieuwe gasten worden toegevoegd, maar worden gasten die al lid zijn van de groep of het team, niet verwijderd.

Als u gevoeligheidslabels in uw organisatie gebruikt, raden we u aan deze te gebruiken om gasttoegang per groep te bepalen. Voor informatie over hoe u dit doet, gebruikt u gevoeligheidslabels om inhoud [in Microsoft Teams, Microsoft 365 groepen](../compliance/sensitivity-labels-teams-groups-sites.md)en SharePoint beschermen. Dit is de aanbevolen methode.

## <a name="change-group-settings-using-microsoft-powershell"></a>Groepsinstellingen wijzigen met Microsoft PowerShell

U kunt ook de toevoeging van nieuwe gasten aan afzonderlijke groepen voorkomen met Behulp van PowerShell. (Vergeet niet dat de gekoppelde site van het team SharePoint heeft afzonderlijke besturingselementen voor het [delen van gasten](/sharepoint/change-external-sharing-site).)

U moet de preview-versie van [Azure Active Directory PowerShell voor Graph](/powershell/azure/active-directory/install-adv2) (modulenaam **AzureADPreview)** gebruiken om de instelling voor gasttoegang op groepsniveau te wijzigen:

- Zie De [Azure AD-module](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) installeren als u nog geen versie van de Azure AD PowerShell-module hebt geïnstalleerd en volg de instructies voor het installeren van de openbare preview-release.

- Als u de 2.0 algemene beschikbaarheidsversie van de Azure AD PowerShell-module (AzureAD) hebt geïnstalleerd, moet u deze verwijderen door deze uit te laten lopen in uw PowerShell-sessie en vervolgens de preview-versie te installeren door het uitvoeren `Uninstall-Module AzureAD` `Install-Module AzureADPreview` van .

- Als u de preview-versie al hebt geïnstalleerd, moet u ervoor zorgen dat deze de `Install-Module AzureADPreview` nieuwste versie van deze module is.

> [!NOTE]
> U moet globale beheerdersrechten hebben om deze opdrachten uit te voeren. 

Voer het volgende script uit en ga naar de naam van de groep waarin */<GroupName/>* u gasttoegang wilt blokkeren.

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

De verificatie ziet er als volgende uit:
    
![Schermafbeelding van het PowerShell-venster waarin wordt weergegeven dat de toegang tot gastgroep is ingesteld op onwaar.](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a>Gasttoegang toestaan of blokkeren op basis van hun domein

U kunt gasten die een specifiek domein gebruiken, toestaan of blokkeren. Als uw bedrijf (Contoso) bijvoorbeeld een partnerschap heeft met een ander bedrijf (Fabrikam), kunt u Fabrikam toevoegen aan uw lijst Toestaan, zodat uw gebruikers deze gasten aan hun groepen kunnen toevoegen.

Zie Uitnodigingen toestaan of blokkeren voor [B2B-gebruikers van specifieke organisaties voor meer informatie.](/azure/active-directory/b2b/allow-deny-list)

## <a name="add-guests-to-the-global-address-list"></a>Gasten toevoegen aan de algemene adreslijst

Gasten zijn standaard niet zichtbaar in de Exchange algemene adreslijst. Gebruik de onderstaande stappen om een gast zichtbaar te maken in de algemene adreslijst.

Zoek de object-id van de gast door het volgende uit te lopen:

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

Voer vervolgens het volgende uit met de juiste waarden voor ObjectID, GivenName, Achternaam, Weergavenaam en Telefoonnummer.

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-topics"></a>Verwante onderwerpen

[Planning van samenwerkingsbeheer stap voor stap](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Uw samenwerkingsbeheerplan maken](collaboration-governance-first.md)

[Groepslidmaatschap beheren in het Microsoft 365 beheercentrum](../admin/create-groups/add-or-remove-members-from-groups.md)
  
[Azure Active Directory toegangsbeoordelingen](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](/powershell/module/azuread/set-azureaduser)