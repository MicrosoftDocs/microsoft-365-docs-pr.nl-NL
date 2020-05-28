---
title: Beheren wie groepen kan maken
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
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
- BCS160
- MSP160
- MST160
- MET150
- MOE150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Meer informatie over hoe u bepalen welke gebruikers Microsoft 365-groepen kunnen maken.
ms.openlocfilehash: f3de4ac0856f1281151e6d1c686d90559a5e8544
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387991"
---
# <a name="manage-who-can-create-groups"></a>Beheren wie groepen kan maken

  
Omdat het voor gebruikers zo gemakkelijk is om Microsoft 365-groepen te maken, wordt u niet overspoeld met verzoeken om ze namens andere mensen te maken. Afhankelijk van uw bedrijf wilt u wellicht zelf bepalen wie er groepen kunnen maken.
  
In dit artikel wordt uitgelegd hoe u de mogelijkheid voor het maken van groepen in alle Microsoft 365-services die groepen gebruiken, uitschakelen, waaronder:
  
- Outlook
    
- SharePoint
    
- Yammer
    
- Microsoft Teams

- Microsoft Stream
    
- StaffHub (StaffHub)
    
- Planner
    
- PowerBI (PowerBI)

- Routekaart
    
U het maken van Microsoft 365-groepen beperken tot de leden van een bepaalde beveiligingsgroep. Om dit te configureren, gebruikt u Windows PowerShell. Dit artikel leidt u door de nodige stappen.
  
De stappen in dit artikel verhinderen niet dat leden van bepaalde rollen groepen maken. Globale beheerders kunnen groepen op alle manieren maken, zoals het Microsoft 365-beheercentrum, Planner, Teams, Exchange en SharePoint Online. Andere rollen kunnen groepen maken via beperkte middelen, hieronder vermeld.
        
  - Exchange Administrator: Exchange Admin center, Azure AD
    
  - Ondersteuning voor Partnerniveau 1: Microsoft 365-beheercentrum, Exchange-beheercentrum, Azure AD
    
  - Ondersteuning voor Partnertier 2: Microsoft 365-beheercentrum, Exchange-beheercentrum, Azure AD
    
  - Directory Writers: Azure AD

  - SharePoint-beheerder: SharePoint-beheercentrum, Azure AD
  
  - Teams Service Administrator: Teams Admin center, Azure AD
  
  - Beheerder van het beheer van gebruiker: Microsoft 365-beheercentrum, Yammer, Azure AD
     
Als u lid bent van een van deze rollen, u Microsoft 365-groepen maken voor beperkte gebruikers en de gebruiker vervolgens toewijzen als eigenaar van de groep. Gebruikers die deze rol hebben, kunnen verbonden groepen maken in Yammer, ongeacht de PowerShell-instellingen die het maken kunnen verhinderen.

## <a name="licensing-requirements"></a>Licentievereisten

Om te beheren wie groepen maakt, hebben de volgende personen Azure AD Premium-licenties of Azure AD Basic EDU-licenties nodig die aan hen zijn toegewezen:

- De beheerder die deze instellingen voor het maken van groepen configureert
- De leden van de beveiligingsgroep die groepen mogen maken

> [!NOTE]
> Zie [Licenties toewijzen of verwijderen in de Azure Active Directory-portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) voor meer informatie over het toewijzen van Azure-licenties.

De volgende personen hebben geen Azure AD Premium- of Azure AD Basic EDU-licenties nodig die aan hen zijn toegewezen:

- Mensen die lid zijn van Microsoft 365-groepen en die niet de mogelijkheid hebben om andere groepen te maken.

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-microsoft-365-groups"></a>Stap 1: Een beveiligingsgroep maken voor gebruikers die Microsoft 365-groepen moeten maken

Er kan slechts één beveiligingsgroep in uw organisatie worden gebruikt om te bepalen wie groepen kan maken. U kunt wel andere beveiligingsgroepen nesten als leden van deze groep. Voorbeeld: de groep met de naam Groep maken toestaan is de aangewezen beveiligingsgroep en de groepen met de naam Microsoft Planner-gebruikers en Exchange Online-gebruikers zijn lid van die groep.

Beheerders in de bovenstaande rollen hoeven geen lid te zijn van deze groep: ze behouden hun mogelijkheid om groepen te maken.

> [!IMPORTANT]
> Zorg ervoor dat u een **beveiligingsgroep** gebruikt om te beperken wie groepen kan maken. Als u een Microsoft 365-groep probeert te gebruiken, kunnen leden geen groep maken vanuit SharePoint omdat deze controleert op een beveiligingsgroep. 
    
1. Ga in het beheercentrum **Groups** naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groepen groepen.</a>

2. Klik op **Een groep toevoegen**.

3. Kies **Beveiliging** als groepstype. Onthoud de naam van de groep goed. Deze hebt u later nodig.
  
4. Voltooi het instellen van de beveiligingsgroep en voeg personen of andere beveiligingsgroepen toe die u wilt kunnen maken groepen in uw organisatie.
    
Zie [Een beveiligingsgroep maken, bewerken of verwijderen in het Microsoft 365-beheercentrum](../email/create-edit-or-delete-a-security-group.md)voor gedetailleerde instructies.
 
## <a name="step-2-run-powershell-commands"></a>Stap 2: PowerShell-opdrachten uitvoeren

U moet de preview-versie van [Azure Active Directory PowerShell voor Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (modulenaam **AzureADPreview)** gebruiken om de instelling voor gasttoegang op groepsniveau te wijzigen:

- Als u nog nooit een versie van de Azure AD PowerShell-module hebt geïnstalleerd, raadpleegt u [De Azure AD-module installeren](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) en de instructies volgen om de openbare preview-release te installeren.

- Als u de versie met algemene beschikbaarheid van 2.0 van de Azure AD PowerShell-module (AzureAD) hebt geïnstalleerd, moet u deze verwijderen door deze uit te voeren `Uninstall-Module AzureAD` in uw PowerShell-sessie en vervolgens de preview-versie installeren door . `Install-Module AzureADPreview`

- Als u de preview-versie al hebt geïnstalleerd, voert u uit `Install-Module AzureADPreview` om te controleren of deze de nieuwste versie van deze module is.



Kopieer het script hieronder naar een teksteditor, zoals Kladblok of de [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).

Vervang *\<SecurityGroupName\>* de naam van de beveiligingsgroep die u hebt gemaakt. Bijvoorbeeld:

`$GroupName = "Group Creators"`

Sla het bestand op als GroupCreators.ps1. 

Navigeer in het PowerShell-venster naar de locatie waar u het bestand hebt opgeslagen (typ <FileLocation> 'CD").

Voer het script uit door te typen:

`.\GroupCreators.ps1`

en [meld u aan met uw beheerdersaccount](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) wanneer daarom wordt gevraagd.

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
    $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -Filter "DisplayName eq '$GroupName'").objectId
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

De laatste regel van het script geeft de bijgewerkte instellingen weer:

![This is what your settings will look like when you're done.](../../media/952cd982-5139-4080-9add-24bafca0830c.png)

Als u in de toekomst wilt wijzigen welke beveiligingsgroep wordt gebruikt, u het script opnieuw uitvoeren met de naam van de nieuwe beveiligingsgroep.

Als u de groepsinstellingsbeperking wilt uitschakelen en alle gebruikers opnieuw groepen wilt toestaan, stelt u $GroupName in op '' en $AllowGroupCreation op 'Waar' en voert u het script opnieuw uit.
    
## <a name="step-4-verify-that-it-works"></a>Stap 4: Controleren of het werkt

Het kan dertig minuten of langer duren voordat wijzigingen worden doorgevoerd. U de nieuwe instellingen als volgt verifiëren:

1. Meld u aan met een gebruikersaccount van iemand die NIET de mogelijkheid zou moeten hebben om groepen te maken. Dat wil zeggen, ze zijn geen lid van de beveiligingsgroep die u hebt gemaakt of een beheerder.
    
2. Selecteer de tegel **Planner.** 
    
3. Selecteer In Planner **Nieuw plan** in de linkernavigatie om een plan te maken. 
  
4. U moet een bericht ontvangen dat het maken van plannen en het maken van groepen is uitgeschakeld.

Probeer dezelfde procedure opnieuw met een lid van de beveiligingsgroep.

> [!NOTE]
> Als leden van de beveiligingsgroep geen groepen kunnen maken, controleert u of ze niet worden geblokkeerd via hun [OWA-postvakbeleid](https://go.microsoft.com/fwlink/?linkid=852135).
    
## <a name="related-articles"></a>Verwante artikelen

[Getting started with Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[Zelfservicegroepsbeheer instellen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[Uitvoeringsbeleid instellen](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[Azure Active Directory-cmdlets voor het configureren van groepsinstellingen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
