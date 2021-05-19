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
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
recommendations: false
description: Lees hoe u kunt bepalen welke gebruikers groepen Microsoft 365 maken.
ms.openlocfilehash: 19a106d255708f4b1df8f798219ea7ea778bbef3
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539177"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a>Beheren wie Microsoft 365-groepen kunnen maken

Standaard kunnen alle gebruikers Microsoft 365 maken. Dit is de aanbevolen methode, omdat gebruikers hiermee kunnen samenwerken zonder hulp van IT nodig te hebben.

Als uw bedrijf vereist dat u beperkt wie groepen kan maken, kunt u het maken van groepen beperken Microsoft 365 groep tot de leden van een bepaalde Microsoft 365 groep of beveiligingsgroep.

Als u zich zorgen maakt over gebruikers die teams of groepen maken die niet voldoen aan uw bedrijfsstandaarden, kunt u overwegen om gebruikers te verplichten een trainingscursus te volgen en ze vervolgens toe te voegen aan de groep toegestane gebruikers.

Wanneer u beperkt wie een groep kan maken, is dit van invloed op alle services die afhankelijk zijn van groepen voor toegang, waaronder:

- Outlook
- SharePoint
- Yammer
- Microsoft Teams
- Microsoft Stream
- Planner
- Power BI (klassiek)
- Project web / Roadmap

De stappen in dit artikel voorkomen niet dat leden van bepaalde rollen groepen kunnen maken. Office 365 Globale beheerders kunnen Groepen maken via het Microsoft 365 beheercentrum, Planner, Exchange en SharePoint Online. Andere rollen kunnen Groepen maken via beperkte middelen, hieronder weergegeven.

- Exchange Beheerder: Exchange beheercentrum, Azure AD
- Ondersteuning voor partnerniveau 1: Microsoft 365 beheercentrum, Exchange beheercentrum, Azure AD
- Ondersteuning voor partnerniveau 2: Microsoft 365 beheercentrum, Exchange beheercentrum, Azure AD
- Adreslijst schrijvers: Azure AD
- SharePoint Beheerder: SharePoint beheercentrum, Azure AD
- Teams Servicebeheerder: Teams beheercentrum, Azure AD
- Gebruikerbeheerder: Microsoft 365 beheercentrum, Azure AD

Als u lid bent van een van deze rollen, kunt u Microsoft 365 Groepen maken voor beperkte gebruikers en de gebruiker vervolgens toewijzen als eigenaar van de groep.

## <a name="licensing-requirements"></a>Licentievereisten

Als u wilt beheren wie groepen maakt, hebben de volgende personen Azure AD Premium of Azure AD Basic EDU-licenties die aan hen zijn toegewezen:

- De beheerder die deze instellingen voor het maken van groepen configureert
- De leden van de groep die groepen mogen maken

> [!NOTE]
> Zie [Licenties toewijzen of verwijderen in](/azure/active-directory/fundamentals/license-users-groups) de Azure Active Directory portal voor meer informatie over het toewijzen van Azure-licenties.

De volgende personen hebben geen Azure AD-Premium of Azure AD Basic EDU-licenties nodig die aan hen zijn toegewezen:

- Personen die lid zijn van Microsoft 365 groepen en die niet de mogelijkheid hebben om andere groepen te maken.

## <a name="step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups"></a>Stap 1: Een groep maken voor gebruikers die groepen Microsoft 365 maken

Slechts één groep in uw organisatie kan worden gebruikt om te bepalen wie groepen kan maken. Maar u kunt andere groepen nesten als leden van deze groep.

Beheerders in de bovenstaande rollen hoeven geen lid te zijn van deze groep: ze behouden hun mogelijkheid om groepen te maken.

1. Ga in het beheercentrum naar de pagina [Groepen.](https://admin.microsoft.com/adminportal/home#/groups)

2. Klik op **Een groep toevoegen.**

3. Kies het groeptype dat u wilt. Onthoud de naam van de groep goed. Deze hebt u later nodig.

4. Sluit het instellen van de groep af, voeg personen of andere groepen toe die u groepen in uw organisatie wilt kunnen maken.

Zie Een beveiligingsgroep maken, bewerken of verwijderen in het Microsoft 365 [voor gedetailleerde instructies.](../admin/email/create-edit-or-delete-a-security-group.md)

## <a name="step-2-run-powershell-commands"></a>Stap 2: PowerShell-opdrachten uitvoeren

U moet de preview-versie van [Azure Active Directory PowerShell voor Graph (AzureAD)](/powershell/azure/active-directory/install-adv2) (modulenaam **AzureADPreview)** gebruiken om de instelling voor gasttoegang op groepsniveau te wijzigen:

- Zie De [Azure AD-module](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) installeren als u nog geen versie van de Azure AD PowerShell-module hebt geïnstalleerd en volg de instructies voor het installeren van de openbare preview-release.

- Als u de 2.0 algemene beschikbaarheidsversie van de Azure AD PowerShell-module (AzureAD) hebt geïnstalleerd, moet u deze verwijderen door deze uit te laten lopen in uw PowerShell-sessie en vervolgens de preview-versie te installeren door het uitvoeren `Uninstall-Module AzureAD` `Install-Module AzureADPreview` van .

- Als u de preview-versie al hebt geïnstalleerd, moet u ervoor zorgen dat deze de `Install-Module AzureADPreview` nieuwste versie van deze module is.

Kopieer het script hieronder naar een teksteditor, zoals Kladblok of de [Windows PowerShell ISE.](/powershell/scripting/components/ise/introducing-the-windows-powershell-ise)

Vervang *\<GroupName\>* door de naam van de groep die u hebt gemaakt. Bijvoorbeeld:

`$GroupName = "Group Creators"`

Sla het bestand op als GroupCreators.ps1.

Ga in het PowerShell-venster naar de locatie waar u het bestand hebt opgeslagen (typ <FileLocation> 'CD').

Voer het script uit door te typen:

`.\GroupCreators.ps1`

en [meld u aan met uw beheerdersaccount](../enterprise/connect-to-microsoft-365-powershell.md#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) wanneer u daarom wordt gevraagd.

```PowerShell
$GroupName = "<GroupName>"
$AllowGroupCreation = $False

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

Op de laatste regel van het script worden de bijgewerkte instellingen weergegeven:

![Schermafbeelding van powershell-scriptuitvoer.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

Als u in de toekomst wilt wijzigen welke groep wordt gebruikt, kunt u het script opnieuw uitvoeren met de naam van de nieuwe groep.

Als u de beperking voor het maken van groepen wilt uitschakelen en alle gebruikers opnieuw groepen wilt toestaan, stelt u $GroupName in op '' en $AllowGroupCreation op 'Waar' en het script opnieuw uitvoeren.

## <a name="step-3-verify-that-it-works"></a>Stap 3: controleren of het werkt

Wijzigingen kunnen dertig minuten of meer duren. U kunt de nieuwe instellingen als volgt controleren:

1. Meld u aan bij Microsoft 365 met een gebruikersaccount van iemand die niet de mogelijkheid zou moeten hebben om groepen te maken. Dat wil zeggen dat ze geen lid zijn van de groep die u hebt gemaakt of een beheerder.

2. Selecteer de **tegel Planner.**

3. Selecteer nieuw plan in **de** linkernavigatie om een plan te maken in Planner.

4. U krijgt een bericht dat het plannen en maken van groepen is uitgeschakeld.

Probeer dezelfde procedure opnieuw met een lid van de groep.

> [!NOTE]
> Als leden van de groep geen groepen kunnen maken, controleert u of ze niet worden geblokkeerd via hun [OWA-postvakbeleid.](/powershell/module/exchange/set-owamailboxpolicy)

## <a name="related-topics"></a>Verwante onderwerpen

[Planning van samenwerkingsbeheer stap voor stap](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Uw samenwerkingsbeheerplan maken](collaboration-governance-first.md)

[Getting started with Office 365 PowerShell](../enterprise/getting-started-with-microsoft-365-powershell.md)

[Selfservicegroepsbeheer instellen in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-self-service-management)

[Set-ExecutionPolicy](/powershell/module/microsoft.powershell.security/set-executionpolicy)

[Azure Active Directory cmdlets voor het configureren van groepsinstellingen](/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
