---
title: Verbinding maken met alle Microsoft 365-services in een enkel PowerShell-venster
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 02/02/2021
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- Ent_Office_Other
- O365ITProTrain
- httpsfix
ms.assetid: 53d3eef6-4a16-4fb9-903c-816d5d98d7e8
description: 'Samenvatting: verbinding maken met alle Microsoft 365-services in een enkel PowerShell-venster.'
ms.openlocfilehash: 923e4bc39ae4391d4deaa2c232e19b9479c2efbe
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583122"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a>Verbinding maken met alle Microsoft 365-services in een enkel PowerShell-venster

Wanneer u PowerShell gebruikt om Microsoft 365 te beheren, kunt u meerdere PowerShell-sessies tegelijk openen. Mogelijk hebt u verschillende PowerShell-Vensters voor het beheren van gebruikersaccounts, SharePoint Online, Exchange Online, Skype voor Bedrijven Online, Microsoft Teams en het Beveiligings- &amp;en compliancecentrum.
  
Dit is niet optimaal voor het beheer van Microsoft 365, omdat u geen gegevens kunt uitwisselen tussen deze vensters voor servicebeheer. In dit artikel wordt beschreven hoe u één exemplaar van Windows PowerShell kunt gebruiken waarmee u Microsoft 365-accounts, Skype voor Bedrijven Online, Exchange Online, SharePoint Online, Microsoft Teams en het Beveiligings- &amp;en compliancecentrum kunt beheren.

>[!Note]
>Dit artikel bevat momenteel alleen de opdrachten om verbinding te maken met de wereldwijde (+GCC) cloud. Notities bevatten koppelingen naar artikelen over het maken van verbinding met de andere Microsoft 365-clouds.

## <a name="before-you-begin"></a>Voordat u begint

Voordat u Microsoft 365 vanuit één exemplaar van Windows PowerShell kunt beheren, moet u rekening houden met de volgende vereisten:
  
- Het werk- of schoolaccount van Microsoft 365 dat u gebruikt, moet lid zijn van een Microsoft 365-beheerdersrol. Raadpleeg [Over beheerdersrollen](../admin/add-users/about-admin-roles.md) voor meer informatie. Dit is een vereiste voor PowerShell voor Microsoft 365, niet per se voor alle andere Microsoft 365-services.
    
- U kunt de volgende 64-bits versies van Windows gebruiken:
    
  - Windows 10
    
  - Windows 8.1 of Windows 8
    
  - Windows Server 2019
    
  - Windows Server 2016
    
  - Windows Server 2012 R2 of Windows Server 2012
    
  - Windows 7 Service Pack 1 (SP1)*
    
  - Windows Server 2008 R2 SP1*
    
    \* U moet Microsoft .NET Framework 4.5 *x* installeren en vervolgens Windows Management Framework 3.0 of 4.0. Zie [Windows Management Framework](/powershell/scripting/windows-powershell/wmf/overview)voor meer informatie.
    
    U moet een 64-bits versie van Windows gebruiken vanwege de vereisten voor de module Skype voor Bedrijven Online en een van de Microsoft 365-modules.
    
- U moet de modules installeren die vereist zijn voor Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype voor Bedrijven Online en Teams:
    
  - [Azure Active Directory V2](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  - [SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251)
  - [Skype voor Bedrijven Online, Windows PowerShell-module](/microsoftteams/teams-powershell-overview)
  - [Exchange Online PowerShell V2](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
  - [Overzicht van PowerShell voor Teams](/microsoftteams/teams-powershell-overview)
    
-  Windows PowerShell moet worden geconfigureerd voor het uitvoeren van ondertekende scripts voor Skype voor Bedrijven Online en het Beveiligings- &amp; en compliancecentrum. Voer de volgende opdracht uit in een Windows PowerShell-sessie met een verhoogde bevoegdheid (een Windows PowerShell-sessie die u **Als beheerder uitvoert**).
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="connection-steps-when-using-just-a-password"></a>Verbindingsstappen als u alleen een wachtwoord gebruikt

Hier volgen de stappen voor het maken van verbinding met alle services in één PowerShell-venster wanneer u alleen een wachtwoord gebruikt voor aanmelding.
  
1. Open Windows PowerShell.
    
2. Voer deze opdracht uit en voer de referenties voor uw werk- of schoolaccount van Microsoft 365 in.
    
   ```powershell
   $credential = Get-Credential
   ```

3. Voer deze opdracht uit om verbinding te maken met Azure AD met behulp van de Azure Active Directory PowerShell voor Graph-module.
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   Als u de Microsoft Azure Active Directory-module voor Windows PowerShell gebruikt, voert u de volgende opdracht uit.
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell en cmdlets met *Msol* in hun naam. Voer deze cmdlets uit vanuit Windows PowerShell.

4. Voer deze opdrachten uit om verbinding te maken met SharePoint Online. Geef de naam van de organisatie op voor uw domein. Voor 'litwareinc\.onmicrosoft.com' is de waarde van de organisatienaam bijvoorbeeld 'litwareinc'.
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $Credential
   ```

5. Voer deze opdrachten uit om verbinding te maken met Exchange Online.
    
   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -ShowProgress $true
   ```

   > [!Note]
   > Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) om verbinding te maken met andere Exchange Online voor Microsoft 365-clouds dan wereldwijd.

6. Voer deze opdrachten uit om verbinding te maken met het Beveiligings- en compliancecentrum.
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > Zie [Verbinding maken Beveiligings- en compliancecentrum Powershell](/powershell/exchange/connect-to-scc-powershell)om verbinding maken met andere Beveiligings-&amp; en compliancecentrum voor Microsoft 365-clouds dan wereldwijd.

7. Voer deze opdrachten uit om verbinding te maken met Teams PowerShell (en Skype voor Bedrijven Online).
    
   ```powershell
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > Skype voor Bedrijven Online-connector maakt momenteel deel uit van de nieuwste Teams PowerShell-module. Als u de meest recente openbare versie van Teams PowerShell gebruikt, hoeft u de Skype voor Bedrijven Online-connector niet te installeren.
  
   > [!Note]
   > Zie [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams) om verbinding te maken met andere Microsoft Teams-clouds dan *Worldwide*.
  


### <a name="azure-active-directory-powershell-for-graph-module"></a>Azure Active Directory PowerShell voor Graph-module

Dit zijn de opdrachten voor alle services in één blok als u de Azure Active Directory PowerShell voor Graph-module gebruikt. Geef de naam op van uw domeinhost en de UPN voor het aanmelden en voer ze allemaal tegelijk uit.
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName -Message "Type the account's password."
#Azure Active Directory
Connect-AzureAD -Credential $credential
#SharePoint Online
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams and Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a>Microsoft Azure Active Directory-module voor Windows PowerShell

Dit zijn de opdrachten voor alle services in één blok als u de Microsoft Azure Active Directory-module voor Windows PowerShell gebruikt. Geef de naam op van uw domeinhost en de UPN voor het aanmelden en voer ze allemaal tegelijk uit.
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName -Message "Type the account's password."
#Azure Active Directory
Connect-MsolService -Credential $credential
#SharePoint Online
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams and Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

## <a name="connection-steps-when-using-multi-factor-authentication"></a>Verbindingsstappen als u meervoudige verificatie gebruikt

### <a name="azure-active-directory-powershell-for-graph-module"></a>Azure Active Directory PowerShell voor Graph-module

Dit zijn de opdrachten in één blok voor alle services om verbinding te maken met meerdere Microsoft 365-services met meervoudige verificatie als u de Azure Active Directory PowerShell voor Graph-module gebruikt.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams and Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a>Microsoft Azure Active Directory-module voor Windows PowerShell

Dit zijn de opdrachten in één blok voor alle services om verbinding te maken met meerdere Microsoft 365-services met meervoudige verificatie als u de Microsoft Azure Active Directory-module voor Windows PowerShell gebruikt.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams and Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a>Powershell-venster sluiten

Om het Windows PowerShell-venster te sluiten, voert u deze opdracht uit om de actieve sessies naar Skype voor Bedrijven Online, SharePoint Online en Teams te verwijderen:
  
```powershell
Remove-PSSession $sfboSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="see-also"></a>Zie ook

- [Verbinding maken met Microsoft 365 met PowerShell](connect-to-microsoft-365-powershell.md)
- [SharePoint Online beheren met PowerShell](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
