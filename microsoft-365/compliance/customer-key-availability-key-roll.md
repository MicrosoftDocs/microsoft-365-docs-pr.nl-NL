---
title: Een klantsleutel of een beschikbaarheidssleutel rollen of draaien
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
description: Meer informatie over het rollen van de klantwortelsleutels die zijn opgeslagen in Azure Key Vault die worden gebruikt met de klantsleutel. Services zijn Exchange Online, Skype voor Bedrijven, SharePoint Online, OneDrive voor Bedrijven en Teams bestanden.
ms.openlocfilehash: 980d6b198b326cb75bb2b4ef4d2c980f605f23e5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162094"
---
# <a name="roll-or-rotate-a-customer-key-or-an-availability-key"></a>Een klantsleutel of een beschikbaarheidssleutel rollen of draaien

> [!CAUTION]
> Rol alleen een versleutelingssleutel die u gebruikt met klantsleutel wanneer uw beveiligings- of compliancevereisten voorschrijven dat u de sleutel moet rollen. Verwijder bovendien geen sleutels die zijn of zijn gekoppeld aan beleidsregels. Wanneer u de sleutels rolt, wordt inhoud versleuteld met de vorige toetsen. Hoewel actieve postvakken bijvoorbeeld regelmatig opnieuw worden versleuteld, kunnen inactieve, losgekoppelde en uitgeschakelde postvakken nog steeds worden versleuteld met de vorige sleutels. SharePoint Online voert back-up van inhoud uit voor herstel- en hersteldoeleinden, zodat er mogelijk nog steeds gearchiveerd inhoud is met oudere sleutels.

## <a name="about-rolling-the-availability-key"></a>Informatie over het rollen van de beschikbaarheidssleutel

Microsoft geeft klanten geen directe controle over de beschikbaarheidscode. U kunt bijvoorbeeld alleen de sleutels rollen (draaien) die u bezit in Azure Key Vault. Microsoft 365 de beschikbaarheidstoetsen op een intern gedefinieerd schema. Er is geen slaovereenkomst op serviceniveau (Customer Facing, Service Level Agreement) voor deze sleutelrolletjes. Microsoft 365 de beschikbaarheidssleutel draait met Microsoft 365 servicecode in een geautomatiseerd, niet-handmatig proces. Microsoft-beheerders kunnen het rollproces starten. De sleutel wordt gerold met behulp van geautomatiseerde mechanismen zonder directe toegang tot het sleutelopslag. Toegang tot het geheime winkel van de beschikbaarheidssleutel is niet ingericht voor Microsoft-beheerders. Het rollen van beschikbaarheidssleutels maakt gebruik van hetzelfde mechanisme dat wordt gebruikt om de sleutel in eerste instantie te genereren. Zie De beschikbaarheidssleutel voor meer informatie over [de beschikbaarheidscode.](customer-key-availability-key-understand.md)

> [!IMPORTANT]
> Exchange Online en Skype voor Bedrijven kunnen effectief worden gerold door klanten die een nieuwe DEP maken, omdat er een unieke beschikbaarheidssleutel wordt gegenereerd voor elke DEP die u maakt. Beschikbaarheidssleutels voor SharePoint Online-, OneDrive voor Bedrijven- en Teams-bestanden bestaan op forestniveau en worden gedeeld tussen DEP's en klanten, wat betekent dat rollen alleen plaatsvindt op een intern gedefinieerde planning van Microsoft. Als u het risico wilt beperken dat de beschikbaarheidssleutel niet telkens wordt gerold als er een nieuwe DEP wordt gemaakt, rollen SharePoint, OneDrive en Teams de tenant intermediate key (TIK), de sleutel die wordt omwikkeld door de hoofdsleutels en de beschikbaarheidssleutel van de klant, telkens als er een nieuwe DEP wordt gemaakt.

## <a name="request-a-new-version-of-each-existing-root-key-you-want-to-roll"></a>Een nieuwe versie aanvragen van elke bestaande hoofdsleutel die u wilt rollen

Wanneer u een sleutel rolt, vraagt u een nieuwe versie van een bestaande sleutel aan. Als u een nieuwe versie van een bestaande sleutel wilt aanvragen, gebruikt u dezelfde cmdlet, [Add-AzKeyVaultKey,](/powershell/module/az.keyvault/add-azkeyvaultkey)met dezelfde syntaxis die u hebt gebruikt om de sleutel te maken. Nadat u klaar bent met het rollen van een sleutel die is gekoppeld aan een dep (Data Encryption Policy), gebruikt u een andere cmdlet om ervoor te zorgen dat klantsleutel de nieuwe sleutel gaat gebruiken. Doe deze stap in elke Azure Key Vault (AKV).

Bijvoorbeeld:

1. Meld u aan bij uw Azure-abonnement met Azure PowerShell. Zie Aanmelden met Azure PowerShell voor [instructies.](/powershell/azure/authenticate-azureps)

2. Voer de Add-AzKeyVaultKey cmdlet uit zoals wordt weergegeven in het volgende voorbeeld:

   ```powershell
   Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
   ```

   Aangezien in dit voorbeeld een sleutel met de naam **Contoso-O365EX-NA-VaultA1-Key001** bestaat in de **kluis Contoso-O365EX-NA-VaultA1,** wordt met de cmdlet een nieuwe versie van de sleutel gemaakt. Met deze bewerking blijven de vorige sleutelversies in de versiegeschiedenis voor de sleutel behouden. U hebt de vorige sleutelversie nodig om de gegevens te ontsleutelen die nog steeds worden versleuteld. Nadat u het rollen van een sleutel die is gekoppeld aan een DEP hebt voltooid, kunt u een extra cmdlet uitvoeren om ervoor te zorgen dat klantsleutel de nieuwe sleutel gaat gebruiken. In de volgende secties worden de cmdlets in meer detail beschreven.
  
## <a name="update-the-customer-key-for-exchange-online-and-skype-for-business"></a>De klantsleutel bijwerken voor Exchange Online en Skype voor Bedrijven

Wanneer u een van de Azure Key Vault-sleutels rolt die zijn gekoppeld aan een DEP die wordt gebruikt met Exchange Online en Skype voor Bedrijven, moet u de DEP bijwerken om naar de nieuwe sleutel te wijzen. Hiermee wordt de beschikbaarheidssleutel niet gedraaid.

Als u klantcode wilt instrueren om de nieuwe sleutel te gebruiken om postvakken te versleutelen, moet u Set-DataEncryptionPolicy cmdlet als volgt uitvoeren:

1. Voer de Set-DataEncryptionPolicy cmdlet uit in Azure PowerShell:
  
   ```powershell
   Set-DataEncryptionPolicy -Identity <DataEncryptionPolicyID> -Refresh
   ```

   Binnen 72 uur worden de actieve postvakken die aan deze DEP zijn gekoppeld, versleuteld met de nieuwe sleutel.

2. Als u de waarde wilt controleren voor de eigenschap DataEncryptionPolicyID voor het postvak, gebruikt u de stappen in Bepalen van de DEP die aan een [postvak is toegewezen.](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox) De waarde voor deze eigenschap wordt gewijzigd zodra de service de bijgewerkte sleutel heeft toegepast.
  
## <a name="update-the-customer-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>De klantsleutel bijwerken voor SharePoint Online OneDrive voor Bedrijven en Teams bestanden

SharePoint Online kunt u maar één toets tegelijk rollen. Als u beide sleutels in een sleutelkluis wilt rollen, wacht u totdat de eerste bewerking is voltooid. Microsoft raadt u aan uw bewerkingen te spreiden om dit probleem te voorkomen. Wanneer u een van de Azure Key Vault-sleutels rolt die zijn gekoppeld aan een DEP die wordt gebruikt met SharePoint Online en OneDrive voor Bedrijven, moet u de DEP bijwerken om naar de nieuwe sleutel te wijzen. Hiermee wordt de beschikbaarheidssleutel niet gedraaid.

1. Voer de Update-SPODataEncryptionPolicy als volgt uit:
  
   ```powershell
   Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
   ```

   Hoewel met deze cmdlet de sleutelrolbewerking voor SharePoint Online en OneDrive voor Bedrijven wordt gestart, wordt de actie niet onmiddellijk voltooid.

2. Als u de voortgang van de sleutelrolbewerking wilt zien, Get-SPODataEncryptionPolicy de cmdlet als volgt uit:

   ```powershell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
   ```

## <a name="related-articles"></a>Verwante artikelen

- [Serviceversleuteling met klantsleutel voor Office 365](customer-key-overview.md)

- [Klantsleutel instellen voor Office 365](customer-key-set-up.md)

- [Klantsleutel beheren voor Office 365](customer-key-manage.md)

- [Meer informatie over de beschikbaarheidssleutel](customer-key-availability-key-understand.md)