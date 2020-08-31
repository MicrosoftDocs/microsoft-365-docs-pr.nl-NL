---
title: Beheren wie Microsoft 365-groepen kunnen maken
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: serdars
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
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Meer informatie over hoe u kunt bepalen welke gebruikers Microsoft 365-groepen kunnen maken.
ms.openlocfilehash: d6e6c6d9caff2ac7c13d03dad97b73906a509f46
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307857"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a>Beheren wie Microsoft 365-groepen kunnen maken

Standaard kunnen alle gebruikers Microsoft 365-groepen maken. Dit is de aanbevolen manier, omdat gebruikers kunnen samenwerken zonder dat ze daarvoor hulp hoeven te bieden.

Als u wilt dat u kunt instellen wie groepen kan maken, kunt u dat doen door de procedures in dit artikel te volgen. Wanneer u beperkt wie een groep kan maken, heeft dit invloed op alle services die afhankelijk zijn van groepen voor toegang, waaronder:

- Outlook
    
- SharePoint
    
- Yammer
    
- Microsoft Teams

- Microsoft Stream

- Planner
    
- PowerBI (klassiek)
    
- Project voor het web/routekaart
    
U kunt het maken van een Microsoft 365-groep beperken tot de leden van een bepaalde beveiligingsgroep. U kunt deze configureren met behulp van Windows PowerShell. In dit artikel wordt u stapsgewijs begeleid bij het uitvoeren van de benodigde stappen.
  
Met de stappen in dit artikel kunnen leden van bepaalde rollen geen groepen maken. Globale beheerders van Office 365 kunnen groepen maken op grond van een willekeurige manier, zoals het Beheercentrum van Microsoft 365, planner, teams, Exchange en SharePoint Online. Andere rollen kunnen groepen maken op grond van beperkte middelen die hieronder worden weergegeven.
        
  - Exchange-beheerder: Exchange-Beheercentrum, Azure AD
    
  - Ondersteuning voor partner niveau 1: Microsoft 365-Beheercentrum, Exchange-Beheercentrum, Azure AD
    
  - Ondersteuning voor partner niveau 2: Microsoft 365-Beheercentrum, Exchange-Beheercentrum, Azure AD
    
  - Directory schrijvers: Azure AD

  - SharePoint-beheerder: SharePoint-Beheercentrum, Azure AD
  
  - Service beheerder voor teams: Beheercentrum voor teams, Azure AD
  
  - Gebruikersbeheer beheerder: Microsoft 365-Beheercentrum, Yammer, Azure AD
     
Als u lid bent van een van deze rollen, kunt u Microsoft 365 groepen maken voor gebruikers met beperkte toegang, en vervolgens de gebruiker toewijzen als de eigenaar van de groep.

## <a name="licensing-requirements"></a>Licentievereisten

Voor het beheren van groepen moeten de volgende personen Azure AD Premium-licenties of Azure AD Basic Education-licenties aan hen toewijzen:

- De beheerder die de instellingen voor het maken van een groep configureert
- De leden van de beveiligingsgroep die groepen mogen maken
 
> [!NOTE]
> Zie [licenties toewijzen of verwijderen in de Azure Active Directory-Portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) voor meer informatie over het toewijzen van Azure-licenties.

De volgende personen hebben geen Azure AD Premium-of Azure AD-basisonderwijs-licenties toegewezen:

- Personen die lid zijn van Microsoft 365-groepen en geen andere groepen kunnen maken.

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-microsoft-365-groups"></a>Stap 1: een beveiligingsgroep maken voor gebruikers die Microsoft 365-groepen willen maken

U kunt slechts één beveiligingsgroep in uw organisatie gebruiken om te bepalen wie groepen kan maken. U kunt wel andere beveiligingsgroepen nesten als leden van deze groep.

Beheerders in de hierboven vermelde rollen hoeven geen lid te zijn van deze groep: ze behouden de mogelijkheid om groepen te maken.

> [!IMPORTANT]
> Zorg ervoor dat u een **beveiligingsgroep** gebruikt om te beperken wie groepen kan maken. Het gebruik van een Microsoft 365-groep wordt niet ondersteund. 
    
1. Ga in het Beheercentrum naar de [pagina groepen](https://admin.microsoft.com/adminportal/home#/groups).

2. Klik op **een groep toevoegen**.

3. Kies **beveiliging** als groepstype. Onthoud de naam van de groep goed. Deze hebt u later nodig.
  
4. Voltooi het instellen van de beveiligingsgroep en voeg personen of andere beveiligingsgroepen toe die groepen in uw organisatie moeten kunnen maken.
    
Zie [een beveiligingsgroep maken, bewerken of verwijderen in het Microsoft 365-Beheercentrum](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group)voor gedetailleerde instructies.
 
## <a name="step-2-run-powershell-commands"></a>Stap 2: PowerShell-opdrachten uitvoeren

U moet de preview-versie van [Azure Active Directory PowerShell voor Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (modulenaam **AzureADPreview**) gebruiken om de instelling voor gasttoegang op het groepeerniveau te wijzigen:

- Als u nog geen versie van de Azure AD PowerShell-module hebt geïnstalleerd, raadpleegt u [de module van Azure AD installeren](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) en volgt u de instructies voor het installeren van de openbare preview-versie.

- Als u de algemene beschikbaarheid van 2,0 van de versie van de Azure AD PowerShell-module (AzureAD) hebt geïnstalleerd, moet u deze verwijderen door `Uninstall-Module AzureAD` in uw PowerShell-sessie te worden uitgevoerd, en de preview-versie vervolgens te installeren `Install-Module AzureADPreview` .

- Als u de preview-versie al hebt geïnstalleerd, controleert u `Install-Module AzureADPreview` of deze de nieuwste versie van deze module is.

Kopieer het volgende script naar een teksteditor, zoals Kladblok of de [Windows PowerShell-ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).

Vervang door *\<SecurityGroupName\>* de naam van de beveiligingsgroep die u hebt gemaakt. Bijvoorbeeld:

`$GroupName = "Group Creators"`

Sla het bestand op als GroupCreators.ps1. 

Ga in het PowerShell-venster naar de locatie waar u het bestand hebt opgeslagen (type CD <FileLocation> ).

Voer het script uit door het volgende te typen:

`.\GroupCreators.ps1`

en [Meld u aan met uw beheerdersaccount](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) wanneer hierom wordt gevraagd.

```PowerShell
$GroupName = "<SecurityGroupName>"
$AllowGroupCreation = "False"

Connect-AzureAD

$settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
if(!$settingsObjectID)
{
      $template = Get-AzureADDirectorySettingTemplate | Where-object {$_.displayname -eq "group.unified"}
    $settingsCopy = $template.CreateDirectorySetting()
    New-AzureADDirectorySetting -DirectorySetting $settingsCopy
    $settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
}

$settingsCopy = Get-AzureADDirectorySetting -Id $settingsObjectID
$settingsCopy["EnableGroupCreation"] = $AllowGroupCreation

if($GroupName)
{
    $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -SearchString $GroupName).objectid
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

In de laatste regel van het script worden de bijgewerkte instellingen weergegeven:

![This is what your settings will look like when you're done.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

Als u in de toekomst de gebruikte beveiligingsgroep wilt wijzigen, kunt u het script opnieuw uitvoeren met de naam van de nieuwe beveiligingsgroep.

Als u de beperking voor het maken van een groep wilt uitschakelen en alle gebruikers de mogelijkheid wilt bieden om groepen te maken, stelt u $GroupName in op ' ' en ' $AllowGroupCreation ' en voert u het script opnieuw uit.
    
## <a name="step-3-verify-that-it-works"></a>Stap 3: controleren of het werkt

Het kan dertig minuten of langer duren voordat de wijzigingen zijn doorgevoerd. U kunt de nieuwe instellingen als volgt controleren:

1. Meld u aan bij Microsoft 365 met een gebruikersaccount van iemand die de mogelijkheid om groepen te maken niet heeft. Dat wil zeggen dat ze geen lid zijn van de beveiligingsgroep die u hebt gemaakt of van een beheerder.
    
2. Selecteer de tegel **planner** . 
    
3. Selecteer **nieuw plan** in het linker navigatieniveau in Planner om een plan te maken. 
  
4. U moet een bericht weergeven dat het maken van een abonnement en het maken van groepen is uitgeschakeld.

Probeer opnieuw dezelfde procedure met een lid van de beveiligingsgroep.

> [!NOTE]
> Als leden van de beveiligingsgroep geen groepen kunnen maken, controleert u of ze niet worden geblokkeerd via het [OWA-postvak beleid](https://go.microsoft.com/fwlink/?linkid=852135).
    
## <a name="related-articles"></a>Verwante artikelen

[Getting started with Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[Selfservice voor groepsbeheer instellen in azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[Azure Active Directory-cmdlets voor het configureren van instellingen voor groepen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
