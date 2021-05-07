---
title: Klantcode beheren
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Nadat u Klantsleutel hebt ingesteld, leert u hoe u deze beheert door AKV-sleutels te herstellen en machtigingen en uw gegevensversleutelingsbeleid te beheren.
ms.openlocfilehash: 284a8ff24fef2f7e8b807477c99e20aaf593552e
ms.sourcegitcommit: 94fa3e57fa6505551d84ae7b458150dceff30db7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/26/2021
ms.locfileid: "52162484"
---
# <a name="manage-customer-key"></a>Klantcode beheren

Nadat u Klantcode voor Office 365 hebt ingesteld, kunt u uw sleutels beheren, zoals in dit artikel wordt beschreven. Meer informatie over Klantcode in de gerelateerde onderwerpen.

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

Er zijn verschillende cmdlets beschikbaar waarmee u machtigingen voor sleutelkluisen kunt bekijken en zo nodig kunt verwijderen. Mogelijk moet u machtigingen verwijderen, bijvoorbeeld wanneer een werknemer het team verlaat. Voor elk van deze taken gebruikt u Azure PowerShell. Zie Overzicht van [Azure PowerShell.](/powershell/azure/)

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

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a>Beleid voor gegevensversleuteling (DEP's) beheren met klantcode

Klantsleutel verwerkt DEP's anders tussen de verschillende services. U kunt bijvoorbeeld een ander aantal DEP's voor de verschillende services maken.

**Exchange Online en Skype voor Bedrijven:** U kunt maximaal 50 DEP's maken. Zie Een [dep (Data Encryption Policy) maken voor](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)gebruik met Exchange Online en Skype voor Bedrijven voor instructies.

**SharePoint Online, OneDrive voor Bedrijven en Teams bestanden:** Een DEP is van toepassing op gegevens op één geografische locatie, ook wel een _geo genoemd._ Als u de functie multi-geo van Office 365 gebruikt, kunt u één DEP per geo maken. Als u geen multi-geo gebruikt, kunt u één DEP maken. Normaal gesproken maakt u de DEP wanneer u Klantcode in stelt. Zie Een [dep (Data Encryption Policy) maken](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)voor elke SharePoint Online en OneDrive voor Bedrijven geo voor instructies.

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a>Bekijk de DEP's die u hebt gemaakt voor Exchange Online en Skype voor Bedrijven

Als u een lijst wilt weergeven met alle DEP's die u hebt gemaakt voor Exchange Online en Skype voor Bedrijven met de powershell-cmdlet Get-DataEncryptionPolicy PowerShell, moet u deze stappen voltooien.

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

Gebruik de stappen in deze sectie om ervoor te zorgen dat versleuteling wordt voltooid, ongeacht of u zojuist een klantsleutel hebt gerold, een nieuw dep hebt toegewezen of een postvak hebt gemigreerd.

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a>Versleuteling controleren voor Exchange Online en Skype voor Bedrijven

Het versleutelen van een postvak kan enige tijd duren. U wordt aangeraden 72 uur te wachten voordat u versleuteling probeert te valideren nadat u een DEP hebt gewijzigd of de eerste keer dat u een DEP aan een postvak toewijst.
  
Gebruik de Get-MailboxStatistics cmdlet om te bepalen of een postvak is versleuteld.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

De eigenschap IsEncrypted retourneert een waarde van **waar** als het postvak is versleuteld en een waarde van **onwaar** als het postvak niet is versleuteld.

De tijd om postvak te voltooien is afhankelijk van de grootte van het postvak. Als klantcode het postvak na 72 uur vanaf het moment dat u een nieuwe DEP toewijst, nog niet volledig heeft versleuteld, neem dan contact op met microsoft-ondersteuning voor hulp. De New-MoveRequest cmdlet is niet meer beschikbaar voor lokale postvakverhuisbewegingen. Raadpleeg deze [aankondiging voor](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) meer informatie.

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Versleuteling controleren voor SharePoint Online OneDrive voor Bedrijven en Teams bestanden

Controleer de status van versleuteling door de Get-SPODataEncryptionPolicy als volgt uit te laten:

```powershell
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

## <a name="roll-back-from-customer-key-to-microsoft-managed-keys"></a>Terugdraaien van klantsleutel naar beheerde sleutels van Microsoft

Voor Klantsleutel op tenantniveau moet u contact op nemen met Microsoft met een verzoek om 'offboarding' van klantsleutel. De aanvraag wordt afgehandeld door het on-call engineering-team.

Voor Klantsleutel op toepassingsniveau doet u dit door een DEP uit postvakken te verwijderen met behulp van de PowerShell-cmdlet Set-mailbox en de instelling voor `DataEncryptionPolicy` `$NULL` . Als u deze cmdlet uitdeelt, wordt de momenteel toegewezen DEP verwijderd en wordt het postvak opnieuw versleuteld met behulp van de DEP die is gekoppeld aan standaard beheerde microsoft-sleutels. U kunt de DEP die door beheerde sleutels van Microsoft wordt gebruikt, niet lossteken. Als u de beheerde sleutels van Microsoft niet wilt gebruiken, kunt u een andere klantcodedep aan het postvak toewijzen.

Als u de DEP uit een postvak wilt verwijderen met de Set-Mailbox PowerShell-cmdlet, moet u deze stappen voltooien.

1. Als u een werk- of schoolaccount gebruikt met globale beheerdersmachtigingen in uw organisatie, maakt u [verbinding met Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Voer de Set-Mailbox cmdlet uit.

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a>Uw sleutels intrekken en het proces voor het gegevensre purgepad starten

U kunt de intrekking van alle hoofdsleutels, inclusief de beschikbaarheidssleutel, bepalen. Customer Key biedt controle over het planningsaspect van de wettelijke vereisten voor u. Als u besluit uw sleutels in te trekken om uw gegevens te verwijderen en de service te verlaten, wordt de beschikbaarheidssleutel verwijderd zodra het gegevens verwijderen is voltooid. U kunt geen gegevens verwijderen voor een tenantbeleid.

Microsoft 365 controleert en valideert het pad voor het verwijderen van gegevens. Zie het SSAE 18 SOC 2-rapport dat beschikbaar is op de Service Trust Portal voor meer [informatie.](https://servicetrust.microsoft.com/) Daarnaast raadt Microsoft de volgende documenten aan:

- [Handleiding risicobeoordeling en compliance voor financiële instellingen in de Microsoft Cloud](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [O365 Exit Planning Considerations](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

Het pad voor het verwijderen van gegevens verschilt enigszins tussen de verschillende services.

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