---
title: Verbinding maken met Microsoft 365 met PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- O365ITProTrain
- Ent_Office_Other
ms.assetid: 5ebc0e21-b72d-46d8-96fa-00643b18eaec
description: Maak verbinding met uw Microsoft 365-Tenant met PowerShell voor Microsoft 365 voor het uitvoeren van Beheercentrum taken vanaf de opdrachtregel.
ms.openlocfilehash: d1e347a13ca5c587fa544ef80a8e289a8dec0a59
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689302"
---
# <a name="connect-to-microsoft-365-with-powershell"></a>Verbinding maken met Microsoft 365 met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Met PowerShell voor Microsoft 365 kunt u de instellingen van Microsoft 365 beheren vanaf de opdrachtregel. Verbinding maken met PowerShell is een eenvoudig proces waar u de vereiste software installeert en vervolgens verbinding maakt met uw Microsoft 365-organisatie. 

Er zijn twee versies van de PowerShell-module die u gebruikt om verbinding te maken met Microsoft 365 en gebruikersaccounts, groepen en licenties te beheren:

- Azure Active Directory PowerShell voor Graph (cmdlets bevatten **AzureAD** in hun naam)
- Microsoft Azure Active Directory-module voor Windows PowerShell (cmdlets bevatten **MSol** in hun naam) 

Vanaf de datum van dit artikel vervangt de module Azure Active Directory PowerShell voor Graph de functionaliteit in de cmdlets van de Microsoft Azure Active Directory-module voor Windows PowerShell-module voor de gebruikers-, groeps-en licentiebeheer functie niet volledig. In sommige gevallen moet u beide versies gebruiken. U kunt beide versies op dezelfde computer veilig installeren.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

U kunt de volgende versies van Windows gebruiken:
    
  - Windows 10, Windows 8.1, Windows 8, of Windows 7 Service Pack 1 (SP1) 
    
  - Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, of Windows Server 2008 R2 SP1

    > [!NOTE]
    > Voor de Azure Active Directory PowerShell-module voor Graph moet u PowerShell-versie 5.1 of hoger gebruiken. Voor de Microsoft Azure Active Directory-module voor Windows PowerShell-module moet u PowerShell-versie 5.1 of hoger tot PowerShell versie 6. PowerShell versie 7 kan niet worden gebruikt. Voor Windows 8,1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012 en Windows Server 2008 R2 SP1 kunt u het [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616)downloaden en installeren. 
    
    > [!NOTE]
    > Voor een 64-bits versie van Windows. Ondersteuning voor de 32-bits versie de Microsoft Azure Active Directory-module voor Windows PowerShell is stopgezet in oktober 2014.
    
Deze procedures zijn bedoeld voor gebruikers die lid zijn van een Microsoft 365-beheerdersrol. Raadpleeg [Over beheerdersrollen](https://go.microsoft.com/fwlink/p/?LinkId=532367) voor meer informatie.


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a>Maak verbinding met de Windows PowerShell voor Graph-module van Microsoft Azure Active Directory.

Opdrachten in de module Azure Active Directory PowerShell voor Graph hebben **AzureAD** in de naam van de cmdlet. U kunt de module [ Azure Active Directory PowerShell voor Graph](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory) of [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-3.6.1) installeren.

Voer de volgende stappen uit om de module te installeren en verbinding te maken met uw Microsoft 365-abonnement voor procedures waarvoor de nieuwe cmdlets in de module Azure Active Directory PowerShell voor Graph zijn vereist.

>[!Note]
>Zie [Azure Active Directory PowerShell voor Graph module](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory) voor informatie over de ondersteuning voor verschillende versies van Microsoft Windows.
>

### <a name="step-1-install-required-software"></a>Stap 1: vereiste software installeren

Deze stappen zijn eenmalig vereist op uw computer, niet telkens wanneer u verbinding maakt. Het is echter waarschijnlijk dat u regelmatig nieuwere versies van de software moet installeren.
  
1. Open een verhoogde Windows PowerShell-opdrachtprompt (Voer Windows PowerShell uit als beheerder).
    
2. Voer deze opdracht uit op de **Beheerder: Windows PowerShell**-opdrachtprompt op beheerdersniveau:
    
  ```powershell
  Install-Module -Name AzureAD
  ```

Als u wordt gevraagd een module te installeren vanuit een niet-vertrouwde opslagplaats, typt u **Y** en drukt u op ENTER.

### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a>Stap 2: verbinding maken met Azure AD voor uw abonnement op Microsoft 365

Als u verbinding wilt maken met Azure AD voor uw abonnement op Microsoft 365 met een accountnaam en wachtwoord of met multi-factor Authentication (MFA), voert u een van de volgende opdrachten uit vanui een Windows PowerShell-opdrachtprompt (deze hoeft niet verhoogd te zijn).

| Office 365-cloud | Opdracht |
|:-------|:-----|
| Office 365 wereldwijd (+ GCC) | `Connect-AzureAD` |
| Office 365 beheerd door 21 Vianet | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| Office 365 Germany | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| Office 365 U.S. Government DoD en Office 365 U.S. Government GCC High | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

Typ de gebruikersnaam en het wachtwoord voor uw Microsoft 365-werk-of schoolaccount in het dialoogvenster **aanmelden bij uw account** en klik vervolgens op **OK**.

Als u MFA gebruikt, volg de instructies in het extra dialoogvenster om aanvullende verificatiegegevens op te geven, zoals een verificatiecode.

Nadat u verbinding hebt gemaakt, kunt u de cmdlets voor de [module Azure Active Directory PowerShell voor Graph](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory)gebruiken.
  

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Maak verbinding met de Microsoft Azure Active Directory-module voor Windows PowerShell

Opdrachten in de module Microsoft Azure Active Directory voor Windows PowerShell hebben**MSol** in hun cmdlet-naam.

PowerShell versie 7 biedt geen ondersteuning voor de module Microsoft Azure Active Directory voor Windows PowerShell-module en cmdlets met **Msol** in hun naam. Voor PowerShell versie 7 en hoger, moet u de module Azure Active Directory PowerShell voor Graph gebruiken.

PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell-module en cmdlets met **Msol** in hun naam. Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell. 
    
### <a name="step-1-install-required-software"></a>Stap 1: vereiste software installeren

Deze stappen zijn eenmalig vereist op uw computer, niet telkens wanneer u verbinding maakt. Het is echter waarschijnlijk dat u regelmatig nieuwere versies van de software moet installeren.
  
1.  Als u geen Windows 10 gebruikt, installeer de 64-bits versie van de Microsoft Online Services-aanmeldhulp: [Microsoft Online Services-aanmeldhulp voor IT-professionals RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).
    
2. Installeer de module Microsoft Azure Active Directory voor Windows PowerShell met deze stappen:
    
  - Open een verhoogde Windows PowerShell-opdrachtprompt (Voer Windows PowerShell uit als beheerder).
  - Voer de **installatie-module MSOnline** uit.
  - Als u wordt gevraagd om de NuGet provider te installeren, typt u **Y** en drukt u op ENTER.
  - Als u wordt gevraagd om de module van PSGallery te installeren, typt u **Y** en drukt u op ENTER.
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a>Stap 2: verbinding maken met Azure AD voor uw abonnement op Microsoft 365

Als u verbinding wilt maken met Azure AD voor uw abonnement op Microsoft 365 met een accountnaam en wachtwoord of met multi-factor Authentication (MFA), voert u een van de volgende opdrachten uit vanui een Windows PowerShell-opdrachtprompt (deze hoeft niet verhoogd te zijn).

| Office 365-cloud | Opdracht |
|:-------|:-----|
| Office 365 wereldwijd (+ GCC) | `Connect-MsolService` |
| Office 365 beheerd door 21 Vianet | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| Office 365 Germany | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| Office 365 U.S. Government DoD en Office 365 U.S. Government GCC High | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

Typ de gebruikersnaam en het wachtwoord voor uw Microsoft 365-werk-of schoolaccount in het dialoogvenster **aanmelden bij uw account** en klik vervolgens op **OK**.

Als u MFA gebruikt, volg de instructies in het extra dialoogvenster om aanvullende verificatiegegevens op te geven, zoals een verificatiecode.

### <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als er geen fouten worden ontvangen, bent u succesvol verbonden. Een snelle test is het uitvoeren van een Microsoft 365-cmdlet, bijvoorbeeld **Get-MsolUser** - en bekijk de resultaten.
  
Als er fouten worden ontvangen, controleert u de volgende vereisten:
  
- **Een veelvoorkomend probleem is een onjuist wachtwoord**. Voer stap 2 nogmaals uit. en let goed op de gebruikersnaam en het wachtwoord dat u invoert.
    
- **De module Microsoft Azure Active Directory voor Windows PowerShell vereist dat Microsoft .NET Framework 3.5.* x *-functie is ingeschakeld op uw computer**. De kans is groot dat er een nieuwere versie van op uw computer is geïnstalleerd (bijvoorbeeld 4 of 4.5.* x*), maar terugwaartse compatibiliteit met oudere versies van .NET Framework kan worden ingeschakeld of uitgeschakeld. Zie de volgende onderwerpen voor meer informatie:
    
  - Zie voor Windows Server 2012 of Windows Server 2012 R2 [.NET Framework 3,5 inschakelen met behulp van de wizard functies en onderdelen toevoegen](https://go.microsoft.com/fwlink/p/?LinkId=532368)
    
  - Zie voor Windows 7 of Windows Server 2008 R2 [U kunt de Azure Active Directory-module voor Windows PowerShell niet openen](https://go.microsoft.com/fwlink/p/?LinkId=532370)

  - Zie voor Windows 10, Windows 8,1 en Windows 8 [.NET Framework 3.5 installeren in Windows 10, Windows 8,1 en Windows 8](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10)

  
- **Uw versie van de module Microsoft Azure Active Directory voor Windows PowerShell is wellicht verouderd.** Als u dit wilt controleren, voert u de volgende opdracht uit in PowerShell voor Microsoft 365 of de Microsoft Azure Active Directory-module voor Windows PowerShell:
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    Als het geretourneerde versienummer lager is dan de waarde 1.0.8070.2, verwijdert u de Microsoft Azure Active Directory-module voor Windows PowerShell en installeert u deze uit stap 1 hierboven.

- **Als er een verbindingsfout wordt ontvangen, raadpleegt u dit onderwerp:** ['verbinden-MsolService: uitzondering van type is opgetreden'](https://go.microsoft.com/fwlink/p/?LinkId=532377).
    
- **Als u het foutbericht Get-item: kan pad niet vinden ontvangt, gebruikt u de volgende opdracht:** 

```powershell
  (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
```

## <a name="see-also"></a>Zie ook

- [Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
- [Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)
- [Verbinding maken met alle Microsoft 365-services in één Windows PowerShell-venster](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
