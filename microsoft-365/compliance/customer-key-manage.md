---
title: Klantcode beheren
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Nadat u Klantsleutel hebt ingesteld, leert u hoe u deze beheert door AKV-sleutels te herstellen, machtigingen te beheren en gegevensversleutelingsbeleid te maken en toe te wijzen.
ms.openlocfilehash: da806ec9dcf1327ec5fdd6b0a0c9e7f22c89584e
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345056"
---
# <a name="manage-customer-key"></a>Klantcode beheren

Nadat u Klantcode voor Office 365 hebt ingesteld, moet u een of meer beleidsregels voor gegevensversleuteling (DEP) maken en toewijzen. Nadat u de DEP's hebt toegewezen, kunt u uw sleutels beheren, zoals wordt beschreven in dit artikel. Meer informatie over Klantcode in de gerelateerde onderwerpen.

## <a name="create-a-dep-for-use-with-multiple-workloads-for-all-tenant-users"></a>Een DEP maken voor gebruik met meerdere werkbelastingen voor alle tenantgebruikers

Controleer voordat u begint of u de taken hebt voltooid die nodig zijn om Klant in te stellen. Zie Klantsleutel instellen voor [meer informatie.](customer-key-set-up.md) Als u de DEP wilt maken, hebt u de KEY VAULT-URL's nodig die u hebt verkregen tijdens de installatie. Zie De [URI voor elke Azure Key Vault-sleutel verkrijgen](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)voor meer informatie.

Als u een DEP met meerdere werkbelastingen wilt maken, gaat u als volgt te werk:
  
1. Op uw lokale computer maakt u via een werk- of schoolaccount met globale [beheerders- of](/powershell/exchange/connect-to-exchange-online-powershell) compliancebeheerdersmachtigingen in uw organisatie verbinding met Exchange Online PowerShell in Windows PowerShell venster.

2. Als u een DEP wilt maken, gebruikt u New-M365DataAtRestEncryptionPolicy cmdlet.

   ```powershell
   New-M365DataAtRestEncryptionPolicy -Name <PolicyName> -AzureKeyIDs <KeyVaultURI1, KeyVaultURI2> [-Description <String>]
   ```

   Waarbij:

   - *PolicyName* is de naam die u wilt gebruiken voor het beleid. Namen kunnen geen spaties bevatten. U kunt bijvoorbeeld Contoso_Global.

   - *KeyVaultURI1* is de URI voor de eerste sleutel in het beleid. Bijvoorbeeld <https://contosoWestUSvault1.vault.azure.net/keys/Key_01>.

   - *KeyVaultURI2* is de URI voor de tweede sleutel in het beleid. Bijvoorbeeld <https://contosoCentralUSvault1.vault.azure.net/keys/Key_02>. Scheid de twee URL's door een komma en een spatie.

   - *Beleidsbeschrijving* is een gebruiksvriendelijke beschrijving van het beleid om u te helpen onthouden waar het beleid voor is. U kunt spaties opnemen in de beschrijving. Bijvoorbeeld: 'Hoofdbeleid voor meerdere werkbelastingen voor alle gebruikers in de tenant'.

Voorbeeld:

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Contoso_Global" -AzureKeyIDs "https://contosoWestUSvault1.vault.azure.net/keys/Key_01","https://contosoCentralUSvault1.vault.azure.net/keys/Key_02" -Description "Policy for multiple workloads for all users in the tenant."
```

### <a name="assign-multi-workload-policy"></a>Beleid voor meerdere werkbelastingen toewijzen

Wijs de DEP toe met de Set-M365DataAtRestEncryptionPolicyAssignment cmdlet. Nadat u het beleid hebt toegewezen, Microsoft 365 de gegevens versleuteld met de sleutel die is geïdentificeerd in het DEP.

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy <PolicyName or ID>
```

 Waarbij *PolicyName* de naam van het beleid is. U kunt bijvoorbeeld Contoso_Global.

Voorbeeld:

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "Contoso_Global"
```

## <a name="create-a-dep-for-use-with-exchange-online-mailboxes"></a>Een DEP maken voor gebruik met Exchange Online postvakken

Controleer voordat u begint of u de taken hebt voltooid die nodig zijn om Azure Key Vault in te stellen. Zie Klantsleutel instellen voor [meer informatie.](customer-key-set-up.md) U voltooit deze stappen door op afstand verbinding te maken met Exchange Online met Windows PowerShell.

Een DEP is gekoppeld aan een set sleutels die zijn opgeslagen in Azure Key Vault. U wijst een DEP toe aan een postvak in Microsoft 365. Microsoft 365 gebruikt vervolgens de sleutels die zijn geïdentificeerd in het beleid om het postvak te versleutelen. Als u de DEP wilt maken, hebt u de KEY VAULT-URL's nodig die u hebt verkregen tijdens de installatie. Zie De [URI voor elke Azure Key Vault-sleutel verkrijgen](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)voor meer informatie.

Vergeet niet! Wanneer u een DEP maakt, geeft u twee sleutels op in twee verschillende Azure Key Vaults. Maak deze sleutels in twee afzonderlijke Azure-regio's om te zorgen voor geo-redundantie.

Als u een DEP wilt maken voor gebruik met een postvak, gaat u als volgt te werk:
  
1. Op uw lokale computer maakt u via een werk- of schoolaccount met globale beheerders- Exchange Online beheerdersmachtigingen in uw organisatie verbinding met Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in een Windows PowerShell venster.

2. Als u een DEP wilt maken, gebruikt u New-DataEncryptionPolicy cmdlet door de volgende opdracht te typen.

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   Waarbij:

   - *PolicyName* is de naam die u wilt gebruiken voor het beleid. Namen kunnen geen spaties bevatten. U kunt bijvoorbeeld USA_mailboxes.

   - *Beleidsbeschrijving* is een gebruiksvriendelijke beschrijving van het beleid om u te helpen onthouden waar het beleid voor is. U kunt spaties opnemen in de beschrijving. Bijvoorbeeld :'Hoofdsleutel voor postvakken in de VS en de regio's'.

   - *KeyVaultURI1* is de URI voor de eerste sleutel in het beleid. Bijvoorbeeld <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.

   - *KeyVaultURI2* is de URI voor de tweede sleutel in het beleid. Bijvoorbeeld <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>. Scheid de twee URL's door een komma en een spatie.

   Voorbeeld:
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault02.vault.azure.net/keys/USA_key_01, https://contoso_CentralUSvault02.vault.azure.net/keys/USA_Key_02
   ```

Zie [New-DataEncryptionPolicy voor](/powershell/module/exchange/new-data-encryptionpolicy)gedetailleerde syntaxis- en parametergegevens.

### <a name="assign-a-dep-to-a-mailbox"></a>Een DEP toewijzen aan een postvak

Wijs de DEP toe aan een postvak met de Set-Mailbox cmdlet. Nadat u het beleid hebt toegewezen, Microsoft 365 het postvak versleutelen met de sleutel die is geïdentificeerd in het DEP.
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

Waarbij *MailboxIdParameter* een gebruikerspostvak aangeeft. Zie [Postvak instellen](/powershell/module/exchange/set-mailbox)voor meer Set-Mailbox cmdlet.

In hybride omgevingen kunt u een DEP toewijzen aan de on-premises postvakgegevens die worden gesynchroniseerd met uw Exchange Online tenant. Als u een DEP wilt toewijzen aan deze gesynchroniseerde postvakgegevens, gebruikt u de Set-MailUser cmdlet. Zie [on-premises](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)postvakken met Outlook voor iOS en Android met hybride moderne verificatie voor meer informatie over postvakgegevens in de hybride omgeving.

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

Waar *MailUserIdParameter* een e-mailgebruiker (ook wel een gebruiker met e-mail genoemd) aangeeft. Zie [Set-MailUser](/powershell/module/exchange/set-mailuser)voor meer Set-MailUser cmdlet.

## <a name="create-a-dep-for-use-with-sharepoint-online-onedrive-for-business-and-teams-files"></a>Een DEP maken voor gebruik met SharePoint Online OneDrive voor Bedrijven en Teams bestanden

Controleer voordat u begint of u de taken hebt voltooid die nodig zijn om Azure Key Vault in te stellen. Zie Klantsleutel instellen voor [meer informatie.](customer-key-set-up.md)
  
Als u klantcode wilt instellen voor SharePoint Online-, OneDrive voor Bedrijven- en Teams-bestanden, kunt u deze stappen voltooien door op afstand verbinding te maken met SharePoint Online met Windows PowerShell.
  
U koppelt een DEP aan een set sleutels die zijn opgeslagen in Azure Key Vault. U kunt een DEP toepassen op al uw gegevens op één geografische locatie, ook wel een geo genoemd. Als u de functie multi-geo van Office 365 gebruikt, kunt u één DEP per geo maken met de mogelijkheid om verschillende toetsen per geo te gebruiken. Als u geen multi-geo gebruikt, kunt u één DEP in uw organisatie maken voor gebruik met SharePoint Online, OneDrive voor Bedrijven en Teams bestanden. Microsoft 365 gebruikt de sleutels die zijn geïdentificeerd in de DEP om uw gegevens in die geo te versleutelen. Als u de DEP wilt maken, hebt u de KEY VAULT-URL's nodig die u hebt verkregen tijdens de installatie. Zie De [URI voor elke Azure Key Vault-sleutel verkrijgen](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)voor meer informatie.
  
Vergeet niet! Wanneer u een DEP maakt, geeft u twee sleutels op in twee verschillende Azure Key Vaults. Maak deze sleutels in twee afzonderlijke Azure-regio's om te zorgen voor geo-redundantie.
  
Als u een DEP wilt maken, moet u op afstand verbinding maken met SharePoint Online met behulp van Windows PowerShell.
  
1. Gebruik op uw lokale computer een werk- of schoolaccount met globale beheerdersmachtigingen in uw organisatie en Verbinding maken om SharePoint [Online PowerShell.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps)

2. Voer in Microsoft Office SharePoint Online Management Shell de Register-SPODataEncryptionPolicy als volgt uit:

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <adminSiteCollectionURL> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   Voorbeeld:
  
   ```powershell
   Register-SPODataEncryptionPolicy -Identity https://contoso.sharepoint.com -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a’
   ```

   Wanneer u het DEP registreert, wordt versleuteling gestart op de gegevens in de geo. Versleuteling kan enige tijd duren. Zie [Register-SPODataEncryptionPolicy](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps)voor meer informatie over het gebruik van deze parameter.

### <a name="view-the-deps-youve-created-for-exchange-online-mailboxes"></a>De DEP's weergeven die u hebt gemaakt voor Exchange Online postvakken

Als u een lijst wilt weergeven met alle DEP's die u voor postvakken hebt gemaakt, gebruikt u Get-DataEncryptionPolicy PowerShell-cmdlet.

1. Als u een werk- of schoolaccount gebruikt met globale beheerdersmachtigingen in uw organisatie, maakt u [verbinding met Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Als u alle DEP's in uw organisatie wilt retourneren, Get-DataEncryptionPolicy de cmdlet zonder parameters.

   ```powershell
   Get-DataEncryptionPolicy
   ```

   Zie [Get-DataEncryptionPolicy (Get-DataEncryptionPolicy)](/powershell/module/exchange/get-dataencryptionpolicy)voor meer informatie over Get-DataEncryptionPolicy cmdlet.

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a>Een DEP toewijzen voordat u een postvak migreert naar de cloud

Wanneer u de DEP toewijst, Microsoft 365 de inhoud van het postvak versleutelt met behulp van de toegewezen DEP tijdens de migratie. Dit proces is efficiënter dan het migreren van het postvak, het toewijzen van de DEP en het wachten op versleuteling, wat uren of mogelijk dagen kan duren.

Als u een DEP wilt toewijzen aan een postvak voordat u deze migreert naar Office 365, voer u de Set-MailUser cmdlet uit in Exchange Online PowerShell:

1. Als u een werk- of schoolaccount gebruikt met globale beheerdersmachtigingen in uw organisatie, maakt u [verbinding met Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Voer de Set-MailUser cmdlet uit.

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   Waar *GeneralMailboxOrMailUserIdParameter* een postvak aangeeft en *DataEncryptionPolicyIdParameter* de id van de DEP is. Zie [Set-MailUser](/powershell/module/exchange/set-mailuser)voor meer Set-MailUser cmdlet.

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>Bepalen welke DEP is toegewezen aan een postvak

Als u de DEP wilt bepalen die aan een postvak is toegewezen, gebruikt u Get-MailboxStatistics cmdlet. De cmdlet retourneert een unieke id (GUID).
  
1. Als u een werk- of schoolaccount gebruikt met globale beheerdersmachtigingen in uw organisatie, maakt u [verbinding met Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   Waar *GeneralMailboxOrMailUserIdParameter* een postvak aangeeft en DataEncryptionPolicyID de GUID van de DEP retourneert. Zie [Get-MailboxStatistics (Get-MailboxStatistics)](/powershell/module/exchange/get-mailboxstatistics)voor meer informatie over Get-MailboxStatistics cmdlet.
  
2. Voer de Get-DataEncryptionPolicy cmdlet uit om de vriendelijke naam te weten te komen van de DEP waaraan het postvak is toegewezen.
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   Waarbij *GUID* de GUID is die wordt geretourneerd door de Get-MailboxStatistics cmdlet in de vorige stap.

## <a name="verify-that-customer-key-has-finished-encryption"></a>Controleren of de klantsleutel is voltooid met versleuteling

Gebruik de stappen in deze sectie om ervoor te zorgen dat versleuteling wordt voltooid, ongeacht of u een klantsleutel hebt gerold, een nieuw dep hebt toegewezen of een postvak hebt gemigreerd.

### <a name="verify-encryption-completes-for-exchange-online-mailboxes"></a>Versleuteling controleren voor Exchange Online postvakken

Het versleutelen van een postvak kan enige tijd duren. Voor de eerste keer versleuteling moet het postvak ook volledig van de ene database naar de andere worden verplaatst voordat de service het postvak kan versleutelen.
  
Gebruik de Get-MailboxStatistics cmdlet om te bepalen of een postvak is versleuteld.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

De eigenschap IsEncrypted retourneert een waarde van waar als  het postvak is versleuteld en een waarde van onwaar als het postvak niet is versleuteld.  De tijd waarop postvak wordt verplaatst, is afhankelijk van het aantal postvakken waaraan u voor het eerst een DEP toewijst en de grootte van de postvakken. Als de postvakken niet zijn versleuteld na een week vanaf het moment dat u de DEP hebt toegewezen, neem dan contact op met Microsoft.

De New-MoveRequest cmdlet is niet meer beschikbaar voor lokale postvakverhuisbewegingen. Raadpleeg deze [aankondiging voor](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) meer informatie.

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Versleuteling controleren voor SharePoint Online OneDrive voor Bedrijven en Teams bestanden

Controleer de status van versleuteling door de Get-SPODataEncryptionPolicy als volgt uit te laten:

```PowerShell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

De uitvoer van deze cmdlet omvat:
  
- De URI van de primaire sleutel.

- De URI van de secundaire sleutel.

- De versleutelingsstatus voor de geo. Mogelijke staten zijn:

  - **Niet-geregistreerd:** Klantsleutelversleuteling is nog niet toegepast.

  - **Registreren:** Klantsleutelversleuteling is toegepast en uw bestanden worden momenteel versleuteld. Als de sleutel voor de geo wordt geregistreerd, wordt ook informatie weergegeven over het percentage sites in de geo dat is voltooid, zodat u de voortgang van versleuteling kunt volgen.

  - **Geregistreerd:** Klantsleutelversleuteling is toegepast en alle bestanden op alle sites zijn versleuteld.

  - **Rollend:** Er wordt een sleutelrol uitgevoerd. Als de sleutel voor het geo wordt gerold, wordt ook informatie weergegeven over het percentage sites dat de sleutelrolbewerking heeft voltooid, zodat u de voortgang kunt volgen.

## <a name="get-details-about-deps-you-use-with-multiple-workloads"></a>Meer informatie over DEP's die u met meerdere werkbelastingen gebruikt

Als u meer informatie wilt over alle DEP's die u hebt gemaakt voor gebruik met meerdere werkbelastingen, gaat u als volgende stappen te werk:

1. Op uw lokale computer maakt u via een werk- of schoolaccount met globale [beheerders- of](/powershell/exchange/connect-to-exchange-online-powershell) compliancebeheerdersmachtigingen in uw organisatie verbinding met Exchange Online PowerShell in Windows PowerShell venster.

   - Voer deze opdracht uit als u de lijst met alle DEP's met meerdere werkbelastingen in de organisatie wilt retourneren.

     ```powershell
        Get-M365DataAtRestEncryptionPolicy
     ```

   - Voer deze opdracht uit als u details over een specifiek dep wilt retourneren. Dit voorbeeld retourneert gedetailleerde informatie voor het DEP met de naam 'Contoso_Global'.

     ```powershell
        Get-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global"
     ```

## <a name="get-multi-workload-dep-assignment-information"></a>Informatie over DEP-toewijzing met meerdere werkbelastingen

Als u wilt weten welke DEP momenteel aan uw tenant is toegewezen, volgt u deze stappen. 

1. Op uw lokale computer maakt u via een werk- of schoolaccount met globale [beheerders- of](/powershell/exchange/connect-to-exchange-online-powershell) compliancebeheerdersmachtigingen in uw organisatie verbinding met Exchange Online PowerShell in Windows PowerShell venster.

2. Typ deze opdracht.

   ```powershell
      Get-M365DataAtRestEncryptionPolicyAssignment
   ```

## <a name="disable-a-multi-workload-dep"></a>Een DEP met meerdere werkbelastingen uitschakelen

Voordat u een DEP met meerdere werkbelastingen uit schakelt, moet u de DEP van werkbelastingen in uw tenant verwijderen. Als u een DEP wilt uitschakelen die wordt gebruikt met meerdere werkbelastingen, moet u de volgende stappen uitvoeren:

1. Op uw lokale computer maakt u via een werk- of schoolaccount met globale [beheerders- of](/powershell/exchange/connect-to-exchange-online-powershell) compliancebeheerdersmachtigingen in uw organisatie verbinding met Exchange Online PowerShell in Windows PowerShell venster.

2. Voer de Set-M365DataAtRestEncryptionPolicy cmdlet uit.
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Enabled $false
   ```

Waarbij *PolicyName* de naam of unieke id van het beleid is. U kunt bijvoorbeeld Contoso_Global.

Voorbeeld:

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Enabled $false
```

## <a name="restore-azure-key-vault-keys"></a>Azure Key Vault-sleutels herstellen

Voordat u herstelt, gebruikt u de herstelmogelijkheden van soft delete. Alle sleutels die worden gebruikt met klantsleutel zijn vereist om soft delete in te stellen. Soft delete werkt als een prullenbak en maakt herstel tot 90 dagen mogelijk zonder dat u het hoeft te herstellen. Herstellen is alleen vereist in extreme of ongebruikelijke omstandigheden, bijvoorbeeld als de sleutel- of sleutelkluis verloren gaat. Als u een sleutel moet herstellen voor gebruik met klantsleutel, Azure PowerShell u de cmdlet Restore-AzureKeyVaultKey als volgt:
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

Bijvoorbeeld:
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

Als de sleutelkluis al een sleutel met dezelfde naam bevat, mislukt de herstelbewerking. Restore-AzKeyVaultKey herstelt alle sleutelversies en alle metagegevens voor de sleutel, inclusief de sleutelnaam.
  
## <a name="manage-key-vault-permissions"></a>Machtigingen voor sleutelkluis beheren

Er zijn verschillende cmdlets beschikbaar waarmee u machtigingen voor sleutelkluisen kunt bekijken en zo nodig kunt verwijderen. Mogelijk moet u machtigingen verwijderen, bijvoorbeeld wanneer een werknemer het team verlaat. Voor elk van deze taken gebruikt u Azure PowerShell. Zie Overzicht van Azure PowerShell [Azure PowerShell.](/powershell/azure/)

Als u machtigingen voor de sleutelkluis wilt weergeven, Get-AzKeyVault cmdlet.

```powershell
Get-AzKeyVault -VaultName <vault name>
```

Bijvoorbeeld:

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

Als u de machtigingen van een beheerder wilt verwijderen, moet u Remove-AzKeyVaultAccessPolicy cmdlet uitvoeren:
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

Bijvoorbeeld:

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="roll-back-from-customer-key-to-microsoft-managed-keys"></a>Terugdraaien van klantsleutel naar beheerde sleutels van Microsoft

Als u wilt terugkeren naar door Microsoft beheerde sleutels, kunt u dit doen. Wanneer u offboard bent, worden uw gegevens opnieuw versleuteld met behulp van standaardversleuteling die door elke afzonderlijke werkbelasting wordt ondersteund. Zo ondersteunt Exchange Online standaardversleuteling met behulp van door Microsoft beheerde sleutels.

> [!IMPORTANT]
> Offboarding is niet hetzelfde als een gegevens purge. Met een gegevens purge worden de gegevens van uw organisatie definitief verwijderd uit Microsoft 365, offboarding niet. U kunt geen gegevens verwijderen voor een beleid voor meerdere werkbelastingen.

Als u besluit klantsleutel niet meer te gebruiken voor het toewijzen van DEP's met meerdere werkbelastingen, moet u contact op nemen met de Ondersteuning van Microsoft met een verzoek om 'offboard' van klantsleutel. Vraag het ondersteuningsteam om een serviceaanvraag in te Microsoft 365 klantsleutelteam. Contact op met m365-ck@service.microsoft.com als u vragen hebt.

Als u afzonderlijke postvakken niet meer wilt versleutelen met DEP's op postvakniveau, kunt u DEP's op postvakniveau uit al uw postvakken verwijderen.

Als u postvakDEP's wilt verwijderen, gebruikt u Set-Mailbox PowerShell-cmdlet.

1. Als u een werk- of schoolaccount gebruikt met globale beheerdersmachtigingen in uw organisatie, maakt u [verbinding met Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Voer de Set-Mailbox cmdlet uit.

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

Als u deze cmdlet uitdeelt, wordt de momenteel toegewezen DEP verwijderd en wordt het postvak opnieuw versleuteld met behulp van de DEP die is gekoppeld aan standaard door Microsoft beheerde sleutels. U kunt de DEP die door beheerde sleutels van Microsoft wordt gebruikt, niet lossteken. Als u de door Microsoft beheerde sleutels niet wilt gebruiken, kunt u een andere klantcodedep aan het postvak toewijzen.

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a>Uw sleutels intrekken en het proces voor het gegevensre purgepad starten

U kunt de intrekking van alle hoofdsleutels, inclusief de beschikbaarheidssleutel, bepalen. Customer Key biedt controle over het planningsaspect van de wettelijke vereisten voor u. Als u besluit uw sleutels in te trekken om uw gegevens te verwijderen en de service te verlaten, wordt de beschikbaarheidssleutel verwijderd zodra het gegevens verwijderen is voltooid. Dit wordt ondersteund voor klantcode-DEP's die zijn toegewezen aan afzonderlijke postvakken.

Microsoft 365 controleert en valideert het pad voor het verwijderen van gegevens. Zie het SSAE 18 SOC 2-rapport dat beschikbaar is op de Service Trust Portal voor meer [informatie.](https://servicetrust.microsoft.com/) Daarnaast raadt Microsoft de volgende documenten aan:

- [Handleiding risicobeoordeling en compliance voor financiële instellingen in de Microsoft Cloud](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [O365 Exit Planning Considerations](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

Het zuiveren van DEP met meerdere werkbelastingen wordt niet ondersteund voor Microsoft 365 Klantcode. De DEP met meerdere werkbelastingen wordt gebruikt om gegevens te versleutelen voor meerdere werkbelastingen voor alle tenantgebruikers. Als u een dergelijke DEP wilt verwijderen, worden gegevens uit meerdere werkbelastingen ontoegankelijk. Als u besluit om de services Microsoft 365 afsluiten, kunt u het pad van tenantverhaling volgen volgens het gedocumenteerde proces. Zie [hoe u een tenant verwijdert in Azure Active Directoy.](/azure/active-directory/enterprise-users/directory-delete-howto)

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a>Uw klantsleutels intrekken en de beschikbaarheidscode voor Exchange Online en Skype voor Bedrijven

Wanneer u het pad voor het verwijderen van gegevens start voor Exchange Online en Skype voor Bedrijven, stelt u een permanente aanvraag voor het verwijderen van gegevens in op een DEP. Hierdoor worden versleutelde gegevens definitief verwijderd in de postvakken waaraan die DEP is toegewezen.

Aangezien u de PowerShell-cmdlet slechts met één DEP tegelijk kunt uitvoeren, kunt u overwegen om één DEP opnieuw toe te staan aan al uw postvakken voordat u het pad voor gegevensre purge start.

> [!WARNING]
> Gebruik het pad voor het verwijderen van gegevens niet om een subset van uw postvakken te verwijderen. Dit proces is alleen bedoeld voor klanten die de service verlaten.

Als u het pad voor het verwijderen van gegevens wilt starten, gaat u als volgende stappen te werk:

1. Verwijder wrap- en uitpakken-machtigingen voor 'O365 Exchange Online' uit Azure Key Vaults.

2. Gebruik een werk- of schoolaccount met globale beheerdersbevoegdheden in uw organisatie en maak [verbinding met Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

3. Voer voor elke DEP die postvakken bevat die u wilt verwijderen de cmdlet [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) als volgt uit.

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   Als de opdracht mislukt, moet u ervoor zorgen dat u de machtigingen Exchange Online beide sleutels in Azure Key Vault hebt verwijderd, zoals eerder in deze taak is opgegeven.Wanneer u de permanentdatapurgeRequested-schakelknop hebt ingesteld met de Set-DataEncryptionPolicy-cmdlet, kunt u deze DEP niet meer toewijzen aan postvakken.

4. Neem contact op met de ondersteuning van Microsoft en vraag de eDocument data purge aan.

    Op uw verzoek stuurt Microsoft u een juridisch document om het verwijderen van gegevens te bevestigen en te machtigen. De persoon in uw organisatie die zich heeft aangemeld als een goedkeurder in de FastTrack-aanbieding tijdens onboarding, moet dit document ondertekenen. Normaal gesproken is dit een leidinggevende of een andere aangewezen persoon in uw bedrijf die wettelijk gemachtigd is om het papierwerk namens uw organisatie te ondertekenen.

5. Nadat uw vertegenwoordiger het juridische document heeft ondertekend, retourneerd u het document naar Microsoft (meestal via een eDoc-handtekening).

    Nadat Microsoft het juridische document heeft ontvangen, worden cmdlets uitgevoerd om de gegevensreinerering te activeren die eerst het beleid verwijdert, de postvakken markeert voor permanente verwijdering en vervolgens de beschikbaarheidssleutel verwijdert. Wanneer het proces voor het verwijderen van gegevens is voltooid, zijn de gegevens verwijderd, zijn ze niet toegankelijk voor Exchange Online en kunnen ze niet worden hersteld.

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Uw klantsleutels en de beschikbaarheidscode intrekken voor SharePoint Online OneDrive voor Bedrijven en Teams bestanden

Als u het pad voor het verwijderen van gegevens voor SharePoint Online, OneDrive voor Bedrijven en Teams wilt starten, gaat u als volgende stappen te werk:

1. Azure Key Vault-toegang intrekken. Alle key vault admins moeten ermee akkoord gaan om de toegang in te trekken.

   U verwijdert de Azure Key Vault niet voor SharePoint Online. Sleutelkluizen kunnen worden gedeeld tussen verschillende SharePoint onlinetententen en DEP's.

2. Neem contact op met Microsoft om de beschikbaarheidscode te verwijderen.

    Wanneer u contact op wilt nemen met Microsoft om de beschikbaarheidscode te verwijderen, sturen we u een juridisch document. De persoon in uw organisatie die zich heeft aangemeld als een goedkeurder in de FastTrack-aanbieding tijdens onboarding, moet dit document ondertekenen. Normaal gesproken is dit een leidinggevende of een andere aangewezen persoon in uw bedrijf die wettelijk gemachtigd is om het papierwerk namens uw organisatie te ondertekenen.

3. Nadat uw vertegenwoordiger het juridische document heeft ondertekend, retourneert u het document naar Microsoft (meestal via een eDoc-handtekening).

   Zodra Microsoft het juridische document heeft ontvangen, worden cmdlets uitgevoerd om de gegevens te verwijderen waarmee de tenantsleutel, sitesleutel en alle afzonderlijke sleutels per document worden verwijderd, waardoor de sleutelhiërarchie onherroepelijk wordt gebroken. Nadat de cmdlets voor het verwijderen van gegevens zijn voltooid, zijn uw gegevens verwijderd.

## <a name="related-articles"></a>Verwante artikelen

- [Serviceversleuteling met klantsleutel](customer-key-overview.md)

- [Meer informatie over de beschikbaarheidssleutel](customer-key-availability-key-understand.md)

- [Klantsleutel instellen](customer-key-set-up.md)

- [Een klantsleutel of een beschikbaarheidssleutel rollen of draaien](customer-key-availability-key-roll.md)

- [Klanten-lockbox](customer-lockbox-requests.md)

- [Serviceversleuteling](office-365-service-encryption.md)