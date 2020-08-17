---
title: Verbinding maken met alle Microsoft 365-services in één Windows PowerShell-venster
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/10/2020
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
description: 'Samenvatting: verbindt Windows PowerShell met alle Microsoft 365-services in één Windows PowerShell-venster.'
ms.openlocfilehash: d4e4bf6ec07ee4a0a5b2f8cb1c83ffacd221eaa0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689304"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window"></a>Verbinding maken met alle Microsoft 365-services in één Windows PowerShell-venster

Wanneer u PowerShell gebruikt om Microsoft 365 te beheren, is het mogelijk om maximaal vijf verschillende Windows PowerShell-sessies tegelijkertijd open te hebben die overeenkomen met het Microsoft 365-beheercentrum, SharePoint Online, Exchange Online, Skype voor Bedrijven Online, Microsoft Teams en het Beveiligings &amp;-compliancecentrum. Met vijf verschillende verbindingsmethoden in afzonderlijke Windows PowerShell-sessies kan het bureaublad er zo uitzien:
  
![Vijf Windows PowerShell-consoles die tegelijk worden uitgevoerd](../media/a1a852c2-89ea-4e8e-8d8b-dcdf596763d1.png)
  
Dit is niet optimaal voor het beheer van Microsoft 365, omdat u geen gegevens kunt uitwisselen tussen die vijf vensters voor servicebeheer. In dit onderwerp wordt beschreven hoe u één exemplaar van Windows PowerShell gebruikt van waaruit u Microsoft 365-accounts, Skype voor Bedrijven Online, Exchange Online, SharePoint Online, Microsoft Teams en het Beveiligings &amp;-compliancecentrum kunt beheren.

>[!Note]
>Dit artikel bevat momenteel alleen de opdrachten om verbinding te maken met de wereldwijde (+GCC) cloud. Aanvullende notities bevatten koppelingen naar artikelen met informatie over het maken van verbinding met de andere Microsoft 365-clouds.
>

## <a name="before-you-begin"></a>Voordat u begint

Voordat u Microsoft 365 vanuit één exemplaar van Windows PowerShell kunt beheren, moet u rekening houden met de volgende vereisten:
  
- Het werk- of schoolaccount van Microsoft 365 dat u voor deze procedures gebruikt, moet lid zijn van een Microsoft 365-beheerdersrol. Raadpleeg [Over beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide) voor meer informatie. Dit is een vereiste voor PowerShell voor Microsoft 365, niet per se voor alle andere Microsoft 365-services.
    
- U kunt de volgende 64-bits versies van Windows gebruiken:
    
  - Windows 10
    
  - Windows 8.1 of Windows 8
    
  - Windows Server 2019
    
  - Windows Server 2016
    
  - Windows Server 2012 R2 of Windows Server 2012
    
  - Windows 7 Service Pack 1 (SP1)*
    
  - Windows Server 2008 R2 SP1*
    
    \* U moet Microsoft .NET Framework 4.5 installeren.*x* en vervolgens Windows Management Framework 3.0 of Windows Management Framework 4.0. Zie [.NET Framework installeren](https://go.microsoft.com/fwlink/p/?LinkId=257868) en [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) of [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344) voor meer informatie.
    
    U moet een 64-bits versie van Windows gebruiken vanwege de vereisten voor de module Skype voor Bedrijven Online en een van de Microsoft 365-modules.
    
- U moet de modules installeren die vereist zijn voor Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype voor Bedrijven Online en Teams:
    
   - [Azure Active Directory V2](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
   - [SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251)
   - [Skype voor Bedrijven Online, Windows PowerShell-module](https://go.microsoft.com/fwlink/p/?LinkId=532439)
   - [Exchange Online PowerShell V2](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)
   - [Overzicht van Teams PowerShell](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  Windows PowerShell moet worden geconfigureerd voor het uitvoeren van ondertekende scripts voor Skype voor Bedrijven Online en Het Beveiligings &amp;-compliancecentrum. U doet dit door de volgende opdracht uit te voeren in een verhoogde Windows PowerShell-sessie (een Windows PowerShell-venster dat u opent door **Als administrator uitvoeren** te selecteren).
    
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

3. Voer deze opdracht uit om verbinding te maken met Azure AD met de Azure Active Directory PowerShell voor Graph-module.
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   Als u de Microsoft Azure Active Directory-module voor Windows PowerShell-module gebruikt, voert u deze opdracht uit.
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell-module en cmdlets met **Msol** in hun naam. Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.

4. Voer deze opdrachten uit om verbinding te maken met SharePoint Online. Geef de naam van de organisatie op voor uw domein. Voor bijvoorbeeld 'litwareinc.onmicrosoft.com' is de waarde van de organisatienaam 'litwareinc'.
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCredential
   ```

5. Voer deze opdrachten uit om verbinding te maken met Skype voor Bedrijven Online. Een waarschuwing over het verhogen van de `WSMan NetworkDelayms`-waarde wordt verwacht de eerste keer dat u verbinding maakt; deze moet worden genegeerd.
     
   ```powershell
   Import-Module SkypeOnlineConnector
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. Voer deze opdracht uit om verbinding te maken met Exchange Online.
    
   ```powershell
   Connect-ExchangeOnline -Credential $credential -ShowProgress $true
   ```

   > [!Note]
   > Als u verbinding wilt maken met Exchange Online voor Microsoft 365-clouds anders dan wereldwijd, gebruikt u de **ExchangeEnvironmentName**-parameter. Zie [Connect-ExchangeOnline](https://docs.microsoft.com/powershell/module/exchange/powershell-v2-module/connect-exchangeonline?view=exchange-ps) voor meer informatie.

7. Voer deze opdrachten uit om verbinding te maken met Teams PowerShell.
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > Zie [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) om verbinding te maken met andere Microsoft Teams-clouds dan wereldwijd.

8. Voer deze opdrachten uit om verbinding te maken met het Beveiligings &amp;-compliancecentrum.
    
   ```powershell
   $SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
   Import-PSSession $SccSession -Prefix cc
   ```

   > [!Note]
   > Zie [Verbinding maken met Beveiligings- en compliancecentrum PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) om verbinding te maken met het Security &amp; compliancecentrum voor Microsoft 365-clouds anders dan wereldwijd.

Hier vindt u alle opdrachten in één blok wanneer u de Azure Active Directory PowerShell voor Graph-module gebruikt. Geef de naam op van uw domeinhost en voer ze allemaal tegelijk uit.
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
$SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
Import-PSSession $SccSession -Prefix cc
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

Als alternatief zijn hier alle opdrachten in één blok bij gebruik van de Microsoft Azure Active Directory-module voor Windows PowerShell-module. Geef de naam op van uw domeinhost en voer ze allemaal tegelijk uit.
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-MsolService -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
$SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
Import-PSSession $SccSession -Prefix cc
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

Wanneer u klaar bent om het Windows PowerShell-venster te sluiten, voert u deze opdracht uit om de actieve sessies naar Skype voor Bedrijven Online, SharePoint Online, het Security &amp;-nalevingscentrum en Teams te verwijderen:
  
```powershell
Remove-PSSession $sfboSession ; Remove-PSSession $SccSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="connection-steps-when-using-multi-factor-authentication"></a>Verbindingsstappen wanneer u meervoudige verificatie gebruikt

Hier vindt u alle opdrachten in één blok om verbinding te maken met Azure AD, SharePoint Online, Skype voor Bedrijven, Exchange Online en Teams met behulp van meervoudige verificatie in één venster met de Azure Active Directory PowerShell voor Graph-module. Geef de UPN-naam (User Principal Name) op van een gebruikersaccount en de naam van uw domeinhost en voer ze vervolgens allemaal tegelijk uit.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

Als alternatief zijn hier alle opdrachten bij gebruik van de Microsoft Azure Active Directory-module voor Windows PowerShell-module.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

Zie voor het Beveiligings &amp;-compliancecentrum [Verbinding maken met Beveiligings- en compliancecentrum PowerShell met behulp van meervoudige verificatie](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps) om verbinding te maken met behulp van meervoudige verificatie:

## <a name="see-also"></a>Zie ook

- [Verbinding maken met Microsoft 365 met PowerShell](connect-to-microsoft-365-powershell.md)
- [SharePoint Online beheren met PowerShell](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [Windows PowerShell gebruiken om rapporten te maken in Microsoft 365](use-windows-powershell-to-create-reports-in-microsoft-365.md)
