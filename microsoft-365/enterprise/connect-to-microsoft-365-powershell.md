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
description: Maak verbinding met je Microsoft 365-tenant via PowerShell voor Microsoft 365 om Beheercentrum-taken vanaf de opdrachtregel uit te voeren.
ms.openlocfilehash: 08005ba1cbdcbfec14585d22614129a9b33352b9
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445754"
---
# <a name="connect-to-microsoft-365-with-powershell"></a>Verbinding maken met Microsoft 365 met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Met PowerShell voor Microsoft 365 kun je de instellingen van Microsoft 365 beheren vanaf de opdrachtregel. Als je verbinding wilt maken met PowerShell, installeer je gewoon de vereiste software en maak je verbinding met je Microsoft 365-organisatie.

Er zijn twee versies van de PowerShell-module die je kunt gebruiken om verbinding te maken met Microsoft 365 en gebruikersaccounts, groepen en licenties te beheren:

- Azure Active Directory PowerShell voor Graph, waarvan de cmdlets *AzureAD* in de naam hebben
- Microsoft Azure Active Directory-module voor Windows PowerShell, waarvan cmdlets *MSol* in de naam hebben

Momenteel vervangt de module Azure Active Directory PowerShell voor Graph nog niet alle functionaliteit van de Microsoft Azure Active Directory-module voor Windows PowerShell voor het beheer van gebruikers, groepen en licenties. In sommige gevallen moet u beide versies gebruiken. U kunt beide versies op dezelfde computer veilig installeren.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?


**Besturingssysteem**

Je moet een 64-bits versie van Windows gebruiken. Ondersteuning voor de 32-bits versie van de Microsoft Azure Active Directory-module voor Windows PowerShell is in 2014 beëindigd.

U kunt de volgende versies van Windows gebruiken:
    
  - Windows 10, Windows 8.1, Windows 8, of Windows 7 Service Pack 1 (SP1) 
    
  - Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, of Windows Server 2008 R2 SP1

>[!Note]
>Voor Windows 8,1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012 en Windows Server 2008 R2 SP1 kunt u het [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616)downloaden en installeren.

**PowerShell**

- Voor de module Azure Active Directory PowerShell voor Graph moet je PowerShell versie 5.1 of hoger gebruiken.

- Voor de Microsoft Azure Active Directory-module voor Windows PowerShell moet je PowerShell versie 5.1 of hoger gebruiken, tot PowerShell versie 6. PowerShell versie 7 kan niet worden gebruikt.
       
>[!Note]
>Deze procedures zijn bedoeld voor gebruikers die lid zijn van een Microsoft 365-beheerdersrol. Raadpleeg [Over beheerdersrollen](../admin/add-users/about-admin-roles.md) voor meer informatie.


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a>Maak verbinding met de Windows PowerShell voor Graph-module van Microsoft Azure Active Directory.

Opdrachten in de module Azure Active Directory PowerShell voor Graph hebben *AzureAD* in de naam van de cmdlet. U kunt de module [ Azure Active Directory PowerShell voor Graph](/powershell/azure/active-directory/install-adv2) of [Azure PowerShell](/powershell/azure/install-az-ps) installeren.

Voer de volgende stappen uit om de module te installeren en verbinding te maken met je Microsoft 365-abonnement voor procedures waarvoor de nieuwe cmdlets in de module Azure Active Directory PowerShell voor Graph zijn vereist.

> [!Note]
> Zie [Module Azure Active Directory PowerShell voor Graph](/powershell/azure/active-directory/install-adv2) voor informatie over de ondersteuning voor verschillende versies van Microsoft Windows.

### <a name="step-1-install-the-required-software"></a>Stap 1:Installeer de vereiste software

Deze stappen hoef je maar één keer uit te voeren op je computer. Maar waarschijnlijk moet je de software regelmatig bijwerken.
  
1. Open een Windows PowerShell-opdrachtprompt met verhoogde bevoegdheid (voer Windows PowerShell uit als beheerder).
    
2. Voer de volgende opdracht uit:
    
    ```powershell
    Install-Module -Name AzureAD
    ```

  PowerShell Gallery (PSGallery) is niet geconfigureerd als vertrouwde opslagplaats voor **PowerShellGet**. De eerste keer dat u PSGallery gebruikt, ziet u het volgende bericht:

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Antwoord **Ja** of **Ja op alles** om door te gaan met de installatie.


### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a>Stap 2: Maak verbinding met Azure AD voor jouw Microsoft 365-abonnement

Als je verbinding wilt maken met Azure Active Directory (Azure AD) voor jouw Microsoft 365-abonnement met een accountnaam en wachtwoord of met meervoudige verificatie, voer je een van de volgende opdrachten uit vanaf een Windows PowerShell-opdrachtprompt. (Deze hoeft geen verhoogde bevoegdheid te hebben.)

| Office 365-cloud | Opdracht |
|:-------|:-----|
| Office 365 wereldwijd (+ GCC) | `Connect-AzureAD` |
| Office 365 beheerd door 21 Vianet | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| Office 365 Germany | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| Office 365 U.S. Government DoD en Office 365 U.S. Government GCC High | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

Typ de gebruikersnaam en het wachtwoord voor jouw werk- of schoolaccount van Microsoft 365 in het dialoogvenster **Aanmelden bij uw account** en selecteer vervolgens **OK**.

Als je meervoudige verificatie gebruikt, volg je de instructies om aanvullende verificatiegegevens op te geven, zoals een verificatiecode.

Nadat je verbinding hebt gemaakt, kun je de cmdlets voor de [module Azure Active Directory PowerShell voor Graph](/powershell/module/azuread) gebruiken.

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Maak verbinding met de Microsoft Azure Active Directory-module voor Windows PowerShell

>[!Note]
>Cmdlets in de Microsoft Azure Active Directory-module voor Windows PowerShell hebben *MSol* in de naam.

PowerShell versie 7 biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell en cmdlets met *Msol* in de naam. Voor PowerShell versie 7 en hoger moet je de module Azure Active Directory PowerShell voor Graph gebruiken.

PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell en cmdlets met *Msol* in hun naam. Voer deze cmdlets uit vanuit Windows PowerShell.
    
### <a name="step-1-install-the-required-software"></a>Stap 1:Installeer de vereiste software

Deze stappen hoef je maar één keer uit te voeren op je computer. Maar waarschijnlijk moet je de software regelmatig bijwerken.
  
1.  Als je geen Windows 10 gebruikt, installeer je de 64-bits versie van de Microsoft Online Services-aanmeldhulp: [Microsoft Online Services-aanmeldhulp voor IT-professionals RTW](https://www.microsoft.com/Download/details.aspx?id=28177).
    
2. Installeer de Microsoft Azure Active Directory-module voor Windows PowerShell met deze stappen:
    
   1. Open een verhoogde Windows PowerShell-opdrachtprompt (Voer Windows PowerShell uit als beheerder).
   1.  Voer de **installatie-module MSOnline** uit.
   1. Als je wordt gevraagd om de NuGet-provider te installeren, typ je **Y** en druk je op Enter.
   1. Als je wordt gevraagd om de module van PSGallery te installeren, typ je **Y** en druk je op Enter.
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a>Stap 2: Maak verbinding met Azure AD voor jouw Microsoft 365-abonnement

Om verbinding te maken met Azure AD voor jouw Microsoft 365-abonnement met een accountnaam en wachtwoord of met meervoudige verificatie, voer je een van de volgende opdrachten uit vanaf een Windows PowerShell-opdrachtprompt. (Deze hoeft geen verhoogde bevoegdheid te hebben.)

| Office 365-cloud | Opdracht |
|:-------|:-----|
| Office 365 wereldwijd (+ GCC) | `Connect-MsolService` |
| Office 365 beheerd door 21 Vianet | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| Office 365 Germany | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| Office 365 U.S. Government DoD en Office 365 U.S. Government GCC High | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

Typ de gebruikersnaam en het wachtwoord voor jouw werk- of schoolaccount van Microsoft 365 in het dialoogvenster **Aanmelden bij uw account** en selecteer vervolgens **OK**.

Als je meervoudige verificatie gebruikt, volg je de instructies om aanvullende verificatiegegevens op te geven, zoals een verificatiecode.

### <a name="how-do-you-know-it-worked"></a>Hoe weet ik dat het werkt?

Als je geen foutmelding krijgt, ben je verbonden. Een snelle test is het uitvoeren van een Microsoft 365-cmdlet, bijvoorbeeld **Get-MsolUser**, en bekijk de resultaten.
  
Als er een foutbericht wordt weergegeven, controleer je de volgende problemen:
  
- **Een veelvoorkomend probleem is een onjuist wachtwoord**. Voer [stap 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) opnieuw uit en let goed op de gebruikersnaam en het wachtwoord die je invoert.
    
- **De Microsoft Azure Active Directory-module voor Windows PowerShell vereist dat Microsoft .NET Framework 3.5.* x* is ingeschakeld op de computer**. Op je computer is waarschijnlijk een nieuwere versie geïnstalleerd (bijvoorbeeld 4 of 4.5.* x*). Maar compatibiliteit met eerdere versies van .NET Framework kan worden ingeschakeld of uitgeschakeld. Zie de volgende artikelen voor meer informatie:
    
  - Zie voor Windows Server 2012 of Windows Server 2012 R2 [.NET Framework 3.5 inschakelen met behulp van de wizard Functies en onderdelen toevoegen](/previous-versions/windows/it-pro/windows-8.1-and-8/dn482071(v=win.10)).
    
  - Zie voor Windows 7 of Windows Server 2008 R2 [Je kunt de module Azure Active Directory voor Windows PowerShell niet openen](/troubleshoot/azure/active-directory/cant-open-aad-module-powershell).

  - Zie voor Windows 10, Windows 8.1 en Windows 8 [.NET Framework 3.5 installeren in Windows 10, Windows 8.1 en Windows 8](/dotnet/framework/install/dotnet-35-windows-10)

  
- **Uw versie van de module Microsoft Azure Active Directory voor Windows PowerShell is wellicht verouderd.** Als u dit wilt controleren, voert u de volgende opdracht uit in PowerShell voor Microsoft 365 of de Microsoft Azure Active Directory-module voor Windows PowerShell:
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    Als het geretourneerde versienummer lager is dan de waarde *1.0.8070.2*, verwijder je de Microsoft Azure Active Directory-module voor Windows PowerShell en installeer je deze vanuit [Stap 1](#step-1-install-the-required-software) hierboven.

- **Als je een verbindingsfoutbericht krijgt**, raadpleeg je [Foutbericht 'Connect-MsolService: Exception of type was thrown'](/office365/troubleshoot/active-directory/connect-msoservice-throw-exception).
    
- **Als je de foutmelding 'Get-Item: Cannot find path' krijgt**, voer je de volgende opdracht uit:


   ```powershell
     (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
   ```

## <a name="see-also"></a>Zie ook

- [Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
- [Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)
- [Verbinding maken met alle Microsoft 365-services in één Windows PowerShell-venster](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
