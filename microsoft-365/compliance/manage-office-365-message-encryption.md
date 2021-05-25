---
title: Office 365-berichtversleuteling beheren
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 5/8/2019
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Wanneer u klaar bent met het instellen van Office 365-berichtversleuteling (OME), leert u hoe u uw implementatie op verschillende manieren kunt aanpassen.
ms.openlocfilehash: a2b3dde44ea541deb41eeb9d55d5ed745fa6c719
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2021
ms.locfileid: "52650982"
---
# <a name="manage-office-365-message-encryption"></a>Office 365-berichtversleuteling beheren

Wanneer u klaar bent met het instellen van Office 365-berichtversleuteling (OME), kunt u de configuratie van uw implementatie op verschillende manieren aanpassen. U kunt bijvoorbeeld configureren of u een een  keer pascodes wilt inschakelen, de knop Versleutelen wilt weergeven in Outlook op internet en meer. In de taken in dit artikel wordt beschreven hoe.

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a>Beheren of geadresseerden van Google, Yahoo en Microsoft-account deze accounts kunnen gebruiken om zich aan te melden bij de Office 365-berichtversleuteling portal

Wanneer u de nieuwe functies Office 365-berichtversleuteling, kunnen gebruikers in uw organisatie berichten verzenden naar geadresseerden buiten uw organisatie. Als de ontvanger een *sociale* id gebruikt, zoals een Google-account, Yahoo-account of Microsoft-account, kan de ontvanger zich aanmelden bij de OME-portal met een sociale id. Als u wilt, kunt u ervoor kiezen om geadresseerden niet toe te staan zich aan te melden bij de OME-portal.
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a>Beheren of geadresseerden sociale IDs kunnen gebruiken om zich aan te melden bij de OME-portal
  
1. [Verbinding maken om Exchange Online Externe PowerShell te gebruiken.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Voer de Set-OMEConfiguration cmdlet uit met de parameter SocialIdSignIn als volgt:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   Als u bijvoorbeeld sociale-1D's wilt uitschakelen:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   Ga als volgende te werk om sociale--eds in te stellen:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a>Het gebruik van een een tijdspascodes voor de Office 365-berichtversleuteling beheren

Als de geadresseerde van een bericht dat door OME is versleuteld, geen Outlook gebruikt, ongeacht het account dat door de geadresseerde wordt gebruikt, ontvangt de geadresseerde een koppeling voor een beperkte webweergave waarmee hij of zij het bericht kan lezen. Deze koppeling bevat een een time pass-code. Als beheerder kunt u bepalen of geadresseerden een eentijdspascodes kunnen gebruiken om zich aan te melden bij de OME-portal.
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a>Beheren of OME een eentijdspascodes genereert
  
1. Gebruik een werk- of schoolaccount met globale beheerdersmachtigingen in uw organisatie en start een Windows PowerShell en maak verbinding met Exchange Online. Zie [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor instructies.

2. Voer de Set-OMEConfiguration cmdlet uit met de OTPEnabled-parameter:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -OTPEnabled <$true|$false>
   ```

   Als u bijvoorbeeld een een-time passcodes wilt uitschakelen:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   Een een time pass codes inschakelen:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a>De weergave van de knop Versleutelen beheren in Outlook web

Als beheerder kunt u beheren of u deze knop wilt weergeven voor eindgebruikers.
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a>Beheren of de knop Versleutelen wordt weergegeven in Outlook web
  
1. Gebruik een werk- of schoolaccount met globale beheerdersmachtigingen in uw organisatie en start een Windows PowerShell en maak verbinding met Exchange Online. Zie [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor instructies.

2. Voer de Set-IRMConfiguration cmdlet uit met de parameter -SimplifiedClientAccessEnabled:

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   Als u bijvoorbeeld de knop **Versleutelen wilt** uitschakelen:

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   De knop **Versleutelen inschakelen:**

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a>Ontsleuteling van e-mailberichten aan de servicezijde inschakelen voor gebruikers van de iOS-e-mailapp

De iOS-e-mailapp kan geen berichten ontsleutelen die zijn beveiligd met Office 365-berichtversleuteling. Als beheerder Microsoft 365 kunt u ontsleuteling aan de servicezijde toepassen voor berichten die worden bezorgd in de e-mailapp van iOS. Wanneer u ervoor kiest om de ontsleuteling aan de servicezijde te gebruiken, stuurt de service een ontsleutelde kopie van het bericht naar het iOS-apparaat. Het clientapparaat slaat een ontsleutelde kopie van het bericht op. Het bericht behoudt ook informatie over gebruiksrechten, ook al past de e-mail-app voor iOS geen gebruiksrechten aan de client toe op de gebruiker. De gebruiker kan het bericht kopiëren of afdrukken, zelfs als hij of zij niet de oorspronkelijke rechten heeft om dit te doen. Als de gebruiker echter een actie probeert uit te voeren die vereist is voor de e-mailserver van Microsoft 365, zoals het doorsturen van het bericht, staat de server de actie niet toe als de gebruiker oorspronkelijk niet het gebruiksrecht had om dit te doen. Eindgebruikers kunnen echter de gebruiksbeperking 'Niet doorsturen' gebruiken door het bericht door te sturen vanuit een ander account in de e-mail-app van iOS. Ongeacht of u de ontsleuteling van e-mail aan de servicezijde hebt ingesteld, bijlagen voor versleutelde en rechten beveiligde e-mail kunnen niet worden bekeken in de e-mailapp van iOS.
  
Als u ervoor kiest om niet toe te staan dat ontsleutelde berichten worden verzonden naar gebruikers van de e-mailapp van iOS, ontvangen gebruikers een bericht waarin staat dat ze niet de rechten hebben om het bericht te bekijken. Standaard is het ontsleutelen van e-mailberichten aan de servicezijde niet ingeschakeld.
  
Zie Versleutelde berichten weergeven op uw iPhone of iPad voor meer informatie en voor een weergave van de [clientervaring.](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a>Beheren of gebruikers van de iOS-e-mailapp berichten kunnen bekijken die zijn beveiligd met Office 365-berichtversleuteling
  
1. Gebruik een werk- of schoolaccount met globale beheerdersmachtigingen in uw organisatie en start een Windows PowerShell en maak verbinding met Exchange Online. Zie [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor instructies.

2. Voer de Set-ActiveSyncOrganizations cmdlet uit met de parameter AllowRMSSupportForUnenlightenedApps:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   Als u de service bijvoorbeeld zo wilt configureren dat berichten worden ontsleuteld voordat ze worden verzonden naar niet-gelichte apps, zoals de e-mail-app voor iOS:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   Of als u de service zo wilt configureren dat er geen ontsleutelde berichten worden verzonden naar niet-gelichte apps:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> Afzonderlijke postvakbeleidsregels (OWA/ActiveSync) overschrijven deze instellingen (dat wil zeggen als -IRMEnabled is ingesteld op Onwaar binnen het betreffende OWA-postvakbeleid of ActiveSync-postvakbeleid, dan zijn deze configuraties niet van toepassing).

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a>Ontsleuteling van e-mailbijlagen aan de servicezijde inschakelen voor e-mail clients in webbrowser

Normaal gesproken worden bijlagen automatisch versleuteld wanneer Office 365 berichtversleuteling gebruikt. Als beheerder kunt u ontsleuteling aan de service toepassen voor e-mailbijlagen die gebruikers downloaden vanuit een webbrowser.
  
Wanneer u de ontsleuteling aan de servicezijde gebruikt, verzendt de service een ontsleutelde kopie van het bestand naar het apparaat. Het bericht is nog steeds versleuteld. De e-mailbijlage bewaart ook informatie over gebruiksrechten, ook al wordt in de browser geen gebruiksrechten aan de client op de gebruiker toegepast. De gebruiker kan de e-mailbijlage kopiëren of afdrukken, zelfs als hij of zij niet de oorspronkelijke rechten heeft om dit te doen. Als de gebruiker echter een actie probeert uit te voeren die vereist is voor de e-mailserver van Microsoft 365, zoals het doorsturen van de bijlage, staat de server de actie niet toe als de gebruiker oorspronkelijk niet het gebruiksrecht had om dit te doen.
  
Ongeacht of u het ontsleutelen van bijlagen aan de servicezijde hebt ingesteld, gebruikers kunnen geen bijlagen weergeven voor versleutelde en rechten beveiligde e-mail in de e-mail-app voor iOS.
  
Als u ervoor kiest om ontsleutelde e-mailbijlagen niet toe te staan, wat de standaardinstelling is, ontvangen gebruikers een bericht waarin staat dat ze niet de rechten hebben om de bijlage te bekijken.
  
Zie Versleutelen-alleen-optie voor e-mailberichten voor meer Microsoft 365 voor e-mails en e-mailbijlagen met de optie Encrypt-Only [e-mail.](/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a>Beheren of e-mailbijlagen worden ontsleuteld bij downloaden vanuit een webbrowser
  
1. Gebruik een werk- of schoolaccount met globale beheerdersmachtigingen in uw organisatie en start een Windows PowerShell en maak verbinding met Exchange Online. Zie [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor instructies.

2. Voer de Set-IRMConfiguration cmdlet uit met de parameter DecryptAttachmentForEncryptOnly:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly <$true|$false>
   ```

   Als u bijvoorbeeld de service wilt configureren voor het ontsleutelen van e-mailbijlagen wanneer een gebruiker deze downloadt vanuit een webbrowser:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
   ```

   U kunt de service zo configureren dat versleutelde e-mailbijlagen worden verlaten zoals ze zijn bij het downloaden:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail"></a>Controleer of alle externe geadresseerden de OME Portal gebruiken om versleutelde e-mail te lezen

U kunt aangepaste huisstijlsjablonen gebruiken om geadresseerden te dwingen een wrapper-e-mail te ontvangen, zodat ze versleutelde e-mail moeten lezen in de OME Portal in plaats van Outlook of Outlook op het web. U kunt dit doen als u meer controle wilt over de manier waarop geadresseerden de e-mail gebruiken die ze ontvangen. Als externe geadresseerden bijvoorbeeld e-mail weergeven in de webportal, kunt u een vervaldatum instellen voor de e-mail en kunt u de e-mail intrekken. Deze functies worden alleen ondersteund via de OME Portal. U kunt de optie Versleutelen en de optie Niet doorsturen gebruiken bij het maken van de regels voor de e-mailstroom.

### <a name="use-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email"></a>Een aangepaste sjabloon gebruiken om alle externe geadresseerden te dwingen de OME-portal te gebruiken en voor versleutelde e-mail

1. Gebruik een werk- of schoolaccount met globale beheerdersmachtigingen in uw organisatie en start een Windows PowerShell en maak verbinding met Exchange Online. Zie [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor instructies.

2. Voer de New-TransportRule cmdlet uit:

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    waarbij:

   - `mail flow rule name` is de naam die u wilt gebruiken voor de nieuwe regel voor de e-mailstroom.

   - `option name` is of `Encrypt` `Do Not Forward` .

   - `template name` is bijvoorbeeld de naam die u de aangepaste huisstijlsjabloon hebt `OME Configuration` gegeven.

   Alle externe e-mail versleutelen met de sjabloon 'OME-configuratie' en de optie Encrypt-Only toepassen:

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

   Alle externe e-mail versleutelen met de sjabloon OME-configuratie en de optie Niet doorsturen toepassen:

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a>Het uiterlijk van e-mailberichten en de OME-portal aanpassen

Zie Het merk van uw organisatie toevoegen aan uw versleutelde berichten voor meer informatie over hoe u OME voor uw organisatie [kunt aanpassen.](add-your-organization-brand-to-encrypted-messages.md)
  
## <a name="disable-the-new-capabilities-for-ome"></a>De nieuwe mogelijkheden voor OME uitschakelen

We hopen dat het er niet bij komt, maar als het nodig is, is het uitschakelen van de nieuwe mogelijkheden voor OME heel eenvoudig. Eerst moet u alle e-mailstroomregels verwijderen die u hebt gemaakt met de nieuwe OME-mogelijkheden. Zie Regels voor e-mailstroom beheren voor informatie over het verwijderen van regels voor [e-mailstroom.](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules) Voltooi vervolgens deze stappen in Exchange Online PowerShell.
  
### <a name="to-disable-the-new-capabilities-for-ome"></a>De nieuwe mogelijkheden voor OME uitschakelen
  
1. Als u een werk- of schoolaccount gebruikt met globale beheerdersmachtigingen in uw organisatie, start u een Windows PowerShell en maakt u verbinding met Exchange Online. Zie [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor instructies.

2. Als u de  knop Versleutelen hebt ingeschakeld in Outlook web, schakelt u deze uit door de Set-IRMConfiguration-cmdlet met de parameter SimplifiedClientAccessEnabled uit te schakelen. Anders slaat u deze stap over.

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. Schakel de nieuwe mogelijkheden voor OME uit door de Set-IRMConfiguration met de parameter AzureRMSLicensingEnabled uit te stellen op onwaar:

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
