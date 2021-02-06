---
title: Beheren wie Microsoft 365-groepen kan maken
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
description: Lees hoe u kunt bepalen welke gebruikers Microsoft 365-groepen kunnen maken.
ms.openlocfilehash: 3fa430e44c272e5ababbfb0e4befba707c72c1ba
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122382"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a>Beheren wie Microsoft 365-groepen kan maken

Standaard kunnen alle gebruikers Microsoft 365-groepen maken. Dit is de aanbevolen aanpak, omdat gebruikers hierdoor kunnen gaan samenwerken zonder dat de IT-ondersteuning hiervoor nodig is.

Als uw bedrijf vereist dat u beperkt wie groepen kan maken, kunt u dit doen door de procedures in dit artikel te volgen. Wanneer u beperkt wie een groep kan maken, is dit van invloed op alle services die afhankelijk zijn van groepen voor toegang, waaronder:

- Outlook
- SharePoint
- Yammer
- Microsoft Teams
- Microsoft Stream
- Planner
- Power BI (klassiek)
- Project voor het web / Roadmap

U kunt het maken van Microsoft 365-groepen beperken tot de leden van een bepaalde Microsoft 365-groep of beveiligingsgroep. U kunt dit configureren met Windows PowerShell. In dit artikel worden de benodigde stappen beschreven.

Met de stappen in dit artikel wordt niet voorkomen dat leden met bepaalde rollen groepen kunnen maken. Globale beheerders van Office 365 kunnen groepen maken op elke manier, zoals het Microsoft 365-beheercentrum, Planner, Teams, Exchange en SharePoint Online. Andere rollen kunnen groepen maken via beperkte middelen, zoals hieronder wordt vermeld.

- Exchange-beheerder: Exchange-beheercentrum, Azure AD
- Ondersteuning voor partnerlaag 1: Microsoft 365-beheercentrum, Exchange-beheercentrum, Azure AD
- Ondersteuning voor partnerlaag 2: Microsoft 365-beheercentrum, Exchange-beheercentrum, Azure AD
- Schrijvers van adreslijst: Azure AD
- SharePoint-beheerder: SharePoint-beheercentrum, Azure AD
- Teams-servicebeheerder: Teams-beheercentrum, Azure AD
- Beheerder gebruikersbeheer: Microsoft 365-beheercentrum, Yammer, Azure AD

Als u lid bent van een van deze rollen, kunt u Microsoft 365-groepen maken voor beperkte gebruikers en de gebruiker vervolgens toewijzen als de eigenaar van de groep.

## <a name="licensing-requirements"></a>Licentievereisten

Om te beheren wie groepen maakt, moeten de volgende personen Azure AD Premium-licenties of Azure AD Basic EDU-licenties aan hen toegewezen hebben:

- De beheerder die deze instellingen voor het maken van groepen configureert
- De leden van de groep die groepen mogen maken

> [!NOTE]
> Zie [Licenties toewijzen of verwijderen in de Azure Active Directory-portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) voor meer informatie over het toewijzen van Azure-licenties.

De volgende personen hebben geen Azure AD Premium- of Azure AD Basic EDU-licenties nodig die aan hen zijn toegewezen:

- Personen die lid zijn van Microsoft 365-groepen en die niet in staat zijn om andere groepen te maken.

## <a name="step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups"></a>Stap 1: Een groep maken voor gebruikers die Microsoft 365-groepen moeten maken

Slechts één groep in uw organisatie kan worden gebruikt om te bepalen wie groepen kan maken. Maar u kunt andere groepen nesten als leden van deze groep.

Beheerders in de bovenstaande rollen hoeven geen lid te zijn van deze groep: ze behouden hun mogelijkheid om groepen te maken.

1. Ga in het beheercentrum naar de [pagina Groepen.](https://admin.microsoft.com/adminportal/home#/groups)

2. Klik op **Groep toevoegen.**

3. Kies het 3D-groepstype. Onthoud de naam van de groep goed. Deze hebt u later nodig.

4. Rond het instellen van de groep af en voeg personen of andere groepen toe die u in uw organisatie wilt kunnen maken.

Zie Een beveiligingsgroep maken, bewerken of verwijderen in het [Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group)voor gedetailleerde instructies.

## <a name="step-2-run-powershell-commands"></a>Stap 2: PowerShell-opdrachten uitvoeren

U moet de preview-versie van [Azure Active Directory PowerShell for Graph (AzureAD) (modulenaam](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) **AzureADPreview)** gebruiken om de instelling voor gasttoegang op groepsniveau te wijzigen:

- Als u nog geen versie van de Azure AD PowerShell-module hebt geïnstalleerd, gaat u naar De [Azure AD-module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) installeren en volgt u de instructies om de openbare preview-versie te installeren.

- Als u de 2.0 algemene beschikbaarheidsversie van de Azure AD PowerShell-module (AzureAD) hebt geïnstalleerd, moet u deze verwijderen door deze uit te zetten in uw PowerShell-sessie en vervolgens de preview-versie te installeren. `Uninstall-Module AzureAD` `Install-Module AzureADPreview`

- Als u de preview-versie al hebt geïnstalleerd, moet u ervoor zorgen dat dit de nieuwste versie `Install-Module AzureADPreview` van deze module is.

Kopieer het onderstaande script naar een teksteditor, zoals Kladblok of [de Windows PowerShell ISE.](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise)

Vervang *\<GroupName\>* door de naam van de groep die u hebt gemaakt. Bijvoorbeeld:

`$GroupName = "Group Creators"`

Sla het bestand op als GroupCreators.ps1.

Navigeer in het PowerShell-venster naar de locatie waar u het bestand hebt opgeslagen (typ <FileLocation> 'CD').

Voer het script uit door te typen:

`.\GroupCreators.ps1`

en [meld u aan met uw beheerdersaccount](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) wanneer hier om wordt gevraagd.

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

![This is what your settings will look like when you're done.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

Als u in de toekomst wilt wijzigen welke groep wordt gebruikt, kunt u het script opnieuw uitvoeren met de naam van de nieuwe groep.

Als u de beperking voor het maken van groepen wilt uitschakelen en weer wilt toestaan dat alle gebruikers groepen maken, stelt u $GroupName in op '' en $AllowGroupCreation op 'Waar' en voeren u het script opnieuw uit.

## <a name="step-3-verify-that-it-works"></a>Stap 3: controleren of het werkt

Het kan dertig minuten of meer duren voordat de wijzigingen van kracht worden. U kunt de nieuwe instellingen als volgt controleren:

1. Meld u aan bij Microsoft 365 met een gebruikersaccount van iemand die NIET in staat mag zijn om groepen te maken. Dat wil zeggen dat ze geen lid zijn van de groep die u hebt gemaakt of van een beheerder.

2. Selecteer de **Planner-tegel.**

3. Selecteer in Planner **Nieuw plan** in het linkernavigatievenster om een plan te maken.

4. Er wordt een bericht weergegeven dat plannen en het maken van groepen zijn uitgeschakeld.

Probeer dezelfde procedure opnieuw met een lid van de groep.

> [!NOTE]
> Als leden van de groep geen groepen kunnen maken, controleert u of deze niet worden geblokkeerd door hun [OWA-postvakbeleid.](https://go.microsoft.com/fwlink/?linkid=852135)

## <a name="related-topics"></a>Verwante onderwerpen

[Planning van samenwerkingsbeheer stap voor stap](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Uw samenwerkingsbeheerplan maken](collaboration-governance-first.md)

[Getting started with Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[Selfservice voor groepsbeheer instellen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[Azure Active Directory-cmdlets voor het configureren van groepsinstellingen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
