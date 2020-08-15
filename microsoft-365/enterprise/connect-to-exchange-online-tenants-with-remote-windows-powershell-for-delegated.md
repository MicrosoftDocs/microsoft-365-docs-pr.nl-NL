---
title: Verbinding maken met Exchange Online-tenants met externe Windows PowerShell voor DAP partners
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: ae5f1a87-8b77-4f93-a1b8-56f800aeb283
description: 'Overzicht: externe Windows PowerShell gebruiken om verbinding te maken met Exchange Online met behulp van de DelegatedOrg-waarde.'
ms.openlocfilehash: 1351a6a6d19fac408b673796c1179bca0ede9c9f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689303"
---
# <a name="connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated-access-permissions-dap-partners"></a>Verbinding maken met Exchange Online-tenants met Remote Windows PowerShell voor gedelegeerde toegangsmachtigingen (DAP)

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

> [!IMPORTANT]
> De procedures in dit onderwerp zijn alleen bedoeld voor partners met een gedelegeerde toegangsrechten (DAP). Gebruik niet de procedures in dit onderwerp als u geen DAP partner bent. 
  
DAP partners zijn RSS-partners en Cloud solution providers. Vaak zijn ze netwerk-of telecommunicatie providers van andere bedrijven. Ze bundelt abonnementen in hun serviceaanbiedingen voor hun klanten. Ze hebben een partner pacht die automatisch beheer verleent aan de machtigingen van (AOBO) voor hun Microsoft 365 Customer tenancies, zodat ze al hun klant tenancies kunnen beheren en rapporteren.

DAP partners kunnen Exchange Online PowerShell gebruiken voor het beheren van de instellingen van klanten Exchange Online en Microsoft 365-rapporten van de opdrachtregel weergeven. U gebruikt Windows PowerShell op uw lokale computer om een externe PowerShell-sessie te maken voor Exchange Online. Het is eenvoudig om uw referenties in te voeren, maar u moet de vereiste verbindingsinstellingen opgeven en vervolgens de cmdlets van Exchange Online in uw lokale Windows PowerShell-sessie importeren, zodat u deze kunt gebruiken.

> [!NOTE]
> DAP partners kunnen de procedures in [verbinding maken met Exchange Online PowerShell met multi-factor Authentication met behulp van multi-factor Authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell) om verbinding te maken met de Tenant-organisaties van de klant in Exchange Online PowerShell. MFA en de Exchange Online Remote PowerShell-module werken niet met gedelegeerde verificatie.
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Geschatte tijdsduur: 5 minuten

- U kunt de volgende versies van Windows gebruiken:
    
  - Windows 10

  - Windows 8,1

  - Windows Server 2016

  - Windows Server 2012 of Windows Server 2012 R2

  - Windows 7 Service Pack 1 (SP1)<sup>*</sup>

  - Windows Server 2008 R2 SP1<sup>*</sup>

    <sup>*</sup> Voor oudere versies van Windows moet u Microsoft.NET Framework 4,5 of hoger installeren en vervolgens een bijgewerkte versie van Windows Management Framework: 3,0, 4,0 of 5,1 (maar één). Zie voor meer informatie [het artikel .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868), [windows Management Framework 3,0](https://go.microsoft.com/fwlink/p/?LinkId=272757), [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/p/?LinkId=391344)en [Windows Management Framework 5,1](https://aka.ms/wmf5download)installeren.

- Windows PowerShell moet zijn geconfigureerd voor het uitvoeren van scripts, en dit is standaard niet. Wanneer u verbinding probeert te maken, wordt het volgende foutbericht weergegeven:

  `Files cannot be loaded because running scripts is disabled on this system. Provide a valid certificate with which to sign the files.`

  Als u wilt dat alle PowerShell-scripts die u downloadt via internet, zijn ondertekend door een vertrouwde uitgever, voert u de volgende opdracht uit in het venster van Windows PowerShell (een Windows PowerShell-venster dat u opent door **als administrator uitvoeren**te selecteren).

    ```
    Set-ExecutionPolicy RemoteSigned
    ```

  U hoeft deze instelling maar één keer op uw computer te configureren, niet telkens wanneer u verbinding maakt.

- Zie [Toetsenbordsneltoetsen in het Exchange-Beheercentrum](https://go.microsoft.com/fwlink/p/?LinkId=534017)voor informatie over toetscombinaties die van toepassing kunnen zijn op de procedures in dit onderwerp.

## <a name="connect-to-exchange-online-for-customer-organizations"></a>Verbinding maken met Exchange Online voor klanten organisaties

1. Open Windows PowerShell op uw lokale computer en voer de volgende opdracht uit.
    
    ```
    $UserCredential = Get-Credential
    ```

    Voer in het dialoogvenster **referentie aanvraag voor Windows PowerShell** uw gebruikersnaam en wachtwoord voor de beheerder van de gebruikersnaam in en klik op **OK**.
    
2. Vervang de _\<customer tenant domain name\>_ naam van het Tenant domein waarmee u verbinding wilt maken en voer de volgende opdracht uit:
    
    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid?DelegatedOrg=<customer tenant domain name> -Credential $UserCredential -Authentication Basic -AllowRedirection
    ```

    Met de sleutel stap in deze opdracht geeft u aan welke klant toegang heeft voor de rapportagegegevens. U doet dit in de parameter  _ConnectionURI_ , waarbij u de FQDN van de oorspronkelijke domeinnaam opgeeft als de waarde voor `?DelegatedOrg=` . Met deze waarde wordt het juiste Exchange Online PowerShell-eindpunt aangegeven waarmee verbinding moet worden gemaakt. Externe PowerShell moet in de context van een specifieke klant verbinding maken met Microsoft 365-rapportage wanneer een rapport wordt uitgevoerd. Nadat u verbinding hebt gemaakt met Exchange Online PowerShell, worden alle volgende opdrachten uitgevoerd in de context van de klant, zodat u toegang hebt tot alle beschikbare rapporten voor de klant.
    
3. Voer de volgende opdracht uit.
    
    ```
    Import-PSSession $Session
    ```

> [!NOTE]
> U kunt maximaal drie gelijktijdige sessies uitvoeren onder één account. Zorg ervoor dat u de externe PowerShell-sessie verbreekt wanneer u klaar bent. Als u het venster van Windows PowerShell sluit zonder de sessie te beëindigen, kunt u alle externe PowerShell-sessies gebruiken die beschikbaar zijn voor u, en moet u wachten tot de sessies zijn verlopen. Voer de volgende opdracht uit om de externe PowerShell-sessie te verbreken:

```
Remove-PSSession $Session
```
  
## <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Na stap 3 worden de cmdlets van Exchange Online in uw lokale Windows PowerShell-sessie geïmporteerd, zoals bijgehouden door een voortgangsbalk. Als u geen fouten ontvangt, is er verbinding met internet. Een snelle test is het uitvoeren van een cmdlet van Exchange Online (bijvoorbeeld **Get-Mailbox**) en de resultaten te zien.
  
Als u fouten ontvangt, controleert u de volgende vereisten:
  
- Een veelvoorkomend probleem is een onjuist wachtwoord. Voer de drie stappen opnieuw uit en Let op de aandacht voor de gebruikersnaam en het wachtwoord die u in stap 1 invoert.
    
- Het account dat u gebruikt om verbinding te maken met Exchange Online, moet zijn ingeschakeld voor Remote PowerShell. Zie [toegang tot Exchange Online PowerShell in-of uitschakelen](https://go.microsoft.com/fwlink/p/?LinkId=534018)voor meer informatie.
    
- TCP-poort 80 verkeer moet worden geopend tussen uw lokale computer en Exchange Online. Het is waarschijnlijk geopend, maar het is een goed idee om u ervan te bedenken of uw organisatie een beperkt toegangsbeleid voor Internet heeft.
    
## <a name="call-the-cmdlet-directly-with-invoke-command"></a>Bel de cmdlet rechtstreeks met de opdracht invoke

Het importeren van een externe PowerShell-sessie (stap 3) kan een langdurige procedure zijn, omdat deze _alle_ cmdlets van Exchange Online overbrengt. Dit kan een probleem met de verwerking van batches zijn (bijvoorbeeld wanneer u rapporten uitvoert of bulk wijzigingen aanbrengt voor verschillende tenants). Als alternatief voor het gebruik van **import-PSSession**kunt u cmdlets bellen die u rechtstreeks wilt gebruiken met de **opdracht invoke**. Als u bijvoorbeeld de cmdlet **Get-Milbox** wilt bellen, vervangt u deze syntaxis voor de `Import-PSSession $Session` opdracht in stap 3:
  
```
Invoke-Command -Session $Session -ScriptBlock {Get-Mailbox}
```

## <a name="more-reporting-cmdlets"></a>Meer cmdlets voor rapporten

De cmdlets die u in dit onderwerp gebruikt, zijn Windows PowerShell-cmdlets. Zie de volgende onderwerpen voor meer informatie over deze cmdlets:
  
- [Get-Credential](https://go.microsoft.com/fwlink/p/?LinkId=389618)
    
- [New-PSSession](https://go.microsoft.com/fwlink/p/?LinkId=389621)
    
- [Import-PSSession](https://go.microsoft.com/fwlink/p/?LinkId=389619)
    
- [Remove-PSSession](https://go.microsoft.com/fwlink/p/?LinkId=389620)
    
- [Set-ExecutionPolicy](https://go.microsoft.com/fwlink/p/?LinkId=389623)
    

