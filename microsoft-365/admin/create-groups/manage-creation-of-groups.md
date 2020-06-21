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
ms.openlocfilehash: b64e7ac96c5a0e38583d00f8a61bd47c5304cf45
ms.sourcegitcommit: 589f78fc0f39aff9109959ded48d146cc32fc3c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/16/2020
ms.locfileid: "44761672"
---
# <a name="manage-who-can-create-groups"></a>Beheren wie groepen kan maken

  
Omdat het zo eenvoudig is voor gebruikers om Microsoft 365-groepen te maken, wordt u niet overspoeld met verzoeken om ze te maken namens andere mensen. Afhankelijk van uw bedrijf wilt u wellicht zelf bepalen wie er groepen kunnen maken.
  
In dit artikel wordt uitgelegd hoe u de mogelijkheid uitschakelen om groepen te maken in alle Microsoft 365-services die groepen gebruiken, waaronder:
  
- Outlook
    
- SharePoint
    
- Yammer
    
- Microsoft Teams

- Microsoft Stream

- Planner
    
- PowerBI (PowerBI)

- Project voor het web en roadmap
    
U het maken van Microsoft 365-groepen beperken tot de leden van een bepaalde beveiligingsgroep. Als u dit wilt configureren, gebruikt u Windows PowerShell. Dit artikel leidt u door de benodigde stappen.
  
Met de stappen in dit artikel kunnen leden van bepaalde rollen er niet van worden weerhouden groepen te maken. Globale beheerders kunnen groepen maken op alle mogelijke manieren, zoals het Microsoft 365-beheercentrum, Planner, Teams, Exchange en SharePoint Online. Andere rollen kunnen groepen maken via beperkte middelen, hieronder vermeld.
        
  - Exchange-beheerder: Exchange-beheercentrum, Azure AD
    
  - Ondersteuning voor Partner Tier 1: Microsoft 365-beheercentrum, Exchange-beheercentrum, Azure AD
    
  - Partner Tier 2-ondersteuning: Microsoft 365-beheercentrum, Exchange-beheercentrum, Azure AD
    
  - Directory Writers: Azure AD

  - SharePoint-beheerder: SharePoint-beheercentrum, Azure AD
  
  - TeamsServicebeheerder: TeamsBeheercentrum, Azure AD
  
  - Beheerder gebruikersbeheer: Microsoft 365-beheercentrum, Yammer, Azure AD
     
Als u lid bent van een van deze rollen, u Microsoft 365-groepen maken voor beperkte gebruikers en de gebruiker vervolgens toewijzen als de eigenaar van de groep. Gebruikers met deze rol kunnen verbonden groepen maken in Yammer, ongeacht de PowerShell-instellingen die het maken ervan kunnen voorkomen.

## <a name="licensing-requirements"></a>Vergunningsvereisten

Als u wilt beheren wie groepen maakt, hebben de volgende personen Azure AD Premium-licenties of Azure AD Basic EDU-licenties nodig die aan hen zijn toegewezen:

- De beheerder die deze instellingen voor groepsvermaken configureert
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
  
4. Voltooi het instellen van de beveiligingsgroep en voeg mensen of andere beveiligingsgroepen toe die u groepen in uw organisatie wilt kunnen maken.
    
Zie [Een beveiligingsgroep maken, bewerken of verwijderen in het Microsoft 365-beheercentrum](../email/create-edit-or-delete-a-security-group.md)voor gedetailleerde instructies.
 
## <a name="step-2-run-powershell-commands"></a>Stap 2: PowerShell-opdrachten uitvoeren

U moet de voorbeeldversie van [Azure Active Directory PowerShell for Graph (AzureAD) (modulenaam](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) **AzureADPreview)** gebruiken om de instelling voor gasttoegang op groepsniveau te wijzigen:

- Als u nog geen versie van de Azure AD PowerShell-module eerder hebt geïnstalleerd, raadpleegt u [De Azure AD-module installeren](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) en de instructies volgen om de versie van de openbare preview te installeren.

- Als u de 2.0 algemene beschikbaarheidsversie van de Azure AD PowerShell-module (AzureAD) hebt geïnstalleerd, moet u deze verwijderen door deze uit te voeren `Uninstall-Module AzureAD` in uw PowerShell-sessie en vervolgens de preview-versie installeren door `Install-Module AzureADPreview` .

- Als u de preview-versie al hebt geïnstalleerd, moet u `Install-Module AzureADPreview` ervoor zorgen dat dit de nieuwste versie van deze module is.



Kopieer het script hieronder naar een teksteditor, zoals Kladblok of de [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).

Vervang *\<SecurityGroupName\>* de naam van de beveiligingsgroep die u hebt gemaakt. Bijvoorbeeld:

`$GroupName = "Group Creators"`

Sla het bestand op als GroupCreators.ps1. 

Navigeer in het PowerShell-venster naar de locatie waar u het bestand hebt opgeslagen (typ <FileLocation> 'CD').

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

Als u de beperking voor het maken van groepen wilt uitschakelen en alle gebruikers opnieuw toestaan groepen te maken, stelt u $GroupName in op '' en $AllowGroupCreation op 'True' en het script opnieuw uit te voeren.
    
## <a name="step-3-verify-that-it-works"></a>Stap 3: controleren of het werkt

Wijzigingen kunnen dertig minuten of langer duren om van kracht te worden. U de nieuwe instellingen als volgt controleren:

1. Meld u aan met een gebruikersaccount van iemand die NIET de mogelijkheid zou moeten hebben om groepen te maken. Dat wil zeggen dat ze geen lid zijn van de beveiligingsgroep die u hebt gemaakt of een beheerder.
    
2. Selecteer de tegel **Planner.** 
    
3. Selecteer in Planner **Nieuw plan** in de linkernavigatie om een plan te maken. 
  
4. U moet een bericht ontvangen dat het plannen en groepscreatie is uitgeschakeld.

Probeer dezelfde procedure opnieuw met een lid van de beveiligingsgroep.

> [!NOTE]
> Als leden van de beveiligingsgroep geen groepen kunnen maken, controleert u of ze niet worden geblokkeerd via hun [OWA-postvakbeleid](https://go.microsoft.com/fwlink/?linkid=852135).
    
## <a name="related-articles"></a>Verwante artikelen

[Getting started with Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[Selfservicegroepsbeheer instellen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[Beleid voor uitvoering instellen](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[Azure Active Directory-cmdlets voor het configureren van groepsinstellingen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
