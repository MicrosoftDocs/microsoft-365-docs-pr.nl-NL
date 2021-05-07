---
title: Versleuteling in Azure
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: Meer informatie over versleuteling die beschikbaar is in Azure, zoals Azure Disk Encryption
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ee4eb2bec814d7e06d418518bb9be272f1bd5aaa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162118"
---
# <a name="encryption-in-azure"></a>Versleuteling in Azure

Technologische beveiligingen in Azure, zoals versleutelde communicatie en operationele processen, helpen uw gegevens veilig te houden. U hebt ook de flexibiliteit om extra versleutelingsfuncties te implementeren en uw eigen cryptografische sleutels te beheren. Ongeacht de configuratie van de klant, microsoft past versleuteling toe om klantgegevens in Azure te beveiligen. Microsoft stelt u ook in staat om uw gegevens die worden gehost in Azure te beheren via een reeks geavanceerde technologieën voor het versleutelen, beheren en beheren van cryptografische sleutels en het beheren en controleren van toegang tot gegevens. Daarnaast biedt Azure Storage uitgebreide set beveiligingsmogelijkheden waarmee ontwikkelaars samen veilige toepassingen kunnen bouwen.

Azure biedt veel mechanismen voor het beveiligen van gegevens wanneer deze van de ene locatie naar de andere worden verplaatst. Microsoft gebruikt TLS om gegevens te beveiligen wanneer deze tussen de cloudservices en klanten reizen. De datacenters van Microsoft onderhandelen over een TLS-verbinding met clientsystemen die verbinding maken met Azure-services. Perfect Forward Geheimhouding (PFS) beschermt verbindingen tussen clientsystemen van klanten en de cloudservices van Microsoft met unieke sleutels. Verbindingen gebruiken ook RSA-gebaseerde 2.048-bits versleutelingssleutellengten. Deze combinatie maakt het lastig voor iemand om gegevens die onderweg zijn te onderscheppen en te openen.

Gegevens kunnen tijdens het doorvoeren tussen een toepassing en Azure worden beveiligd met behulp van [clientversleuteling,](/azure/storage/storage-client-side-encryption)HTTPS of SMB 3.0. U kunt versleuteling inschakelen voor verkeer tussen uw eigen virtuele machines (VM's) en uw gebruikers. Met [Azure Virtual Networks](https://azure.microsoft.com/services/virtual-network/)kunt u het industriestandaard IPsec-protocol gebruiken om het verkeer tussen uw zakelijke VPN-gateway en Azure te versleutelen, evenals tussen de VM's in uw virtuele netwerk.

Voor gegevens in rust biedt Azure veel versleutelingsopties, zoals ondersteuning voor AES-256, zodat u de flexibiliteit hebt om het scenario voor gegevensopslag te kiezen dat het beste aan uw behoeften voldoet. Gegevens kunnen automatisch worden versleuteld wanneer ze worden geschreven naar Azure Storage met [Storage Service Encryption,](/azure/storage/storage-service-encryption)en besturingssysteem en gegevensschijfjes die door VM's worden gebruikt, kunnen worden versleuteld. Zie Beveiligingsaanbevelingen [voor Windows virtuele machines in Azure voor meer informatie.](/azure/security/azure-security-disk-encryption) Bovendien kan gedelegeerde toegang tot gegevensobjecten in Azure Storage worden verleend met [behulp van Gedeelde toegangshandtekeningen.](/azure/storage/storage-dotnet-shared-access-signature-part-1) Azure biedt ook versleuteling voor gegevens in rust met [Transparent Data Encryption voor Azure SQL Database en Data Warehouse.](/sql/relational-databases/security/encryption/transparent-data-encryption-azure-sql)

Zie Overzicht van Azure-versleuteling en [Azure](/azure/security/security-azure-encryption-overview) [Data Encryption-at-Rest](/azure/security/azure-security-encryption-atrest)voor meer informatie over versleuteling in Azure.

## <a name="azure-disk-encryption"></a>Azure Disk Encryption

Azure Disk Encryption kunt u uw Windows en Linux Infrastructure as a Service (IaaS) VM-schijven (IaaS) versleutelen. Azure Disk Encryption maakt gebruik van BitLocker functie van Windows en de DM-Crypt-functie van Linux om versleuteling op volumeniveau te bieden voor het besturingssysteem en de gegevensschijf. Het zorgt er ook voor dat alle gegevens op de VM-schijven in rust worden versleuteld in uw Azure-opslag. Azure Disk Encryption is geïntegreerd met Azure Key Vault om u te helpen bij het beheren, beheren en controleren van het gebruik van de versleutelingssleutels en -geheimen.

Zie Beveiligingsaanbevelingen [voor Windows virtuele machines in Azure voor meer informatie.](/azure/virtual-machines/windows/security-recommendations)

## <a name="azure-storage-service-encryption"></a>Azure Storage Serviceversleuteling

Met [Azure Storage serviceversleuteling](/azure/storage/storage-service-encryption)worden Azure Storage gegevens automatisch versleuteld voordat deze worden opgeslagen en worden gegevens ontsleuteld voordat ze worden opgehaald. De versleutelings-, ontsleutelings- en sleutelbeheerprocessen zijn volledig transparant voor gebruikers. Azure Storage Serviceversleuteling kan worden gebruikt voor [Azure Blob-Storage](https://azure.microsoft.com/services/storage/blobs/) [azure-bestanden.](https://azure.microsoft.com/services/storage/files/) U kunt ook door Microsoft beheerde versleutelingssleutels gebruiken Azure Storage serviceversleuteling of u kunt uw eigen versleutelingssleutels gebruiken. (Zie Voor informatie over het gebruik van uw eigen sleutels [Storage serviceversleuteling met behulp](/azure/storage/common/storage-service-encryption-customer-managed-keys)van door de klant beheerde sleutels in Azure Key Vault. Zie voor meer informatie over het gebruik van door Microsoft beheerde sleutels [Storage serviceversleuteling voor gegevens in Rest](/azure/storage/storage-service-encryption).) Daarnaast kunt u het gebruik van versleuteling automatiseren. U kunt bijvoorbeeld programmatisch Storage Serviceversleuteling in- of uitschakelen op een opslagaccount met behulp van de [REST-API van Azure Storage ResourceProvider,](/rest/api/storagerp/)de [clientbibliotheek van de Storage resourceprovider voor .NET,](/dotnet/api/overview/azure/storage) [Azure PowerShell of](/powershell/azureps-cmdlets-docs)de [Azure CLI.](/azure/storage/storage-azure-cli)

Sommige Microsoft 365 gebruiken Azure voor het opslaan van gegevens. Zo worden SharePoint online en OneDrive voor Bedrijven gegevens opgeslagen in Azure Blob-opslag en Microsoft Teams worden gegevens voor de chatservice opgeslagen in tabellen, blobs en wachtrijen. Daarnaast worden met de functie Compliancebeheer in het Microsoft 365 compliancecentrum door klanten ingevoerde gegevens opgeslagen die in versleutelde vorm worden opgeslagen in [Azure Cosmos DB](/azure/cosmos-db/database-encryption-at-rest), een Platform as a Service (PaaS), wereldwijd gedistribueerde database met meerdere modellen. Azure Storage Serviceversleuteling versleutelt gegevens die zijn opgeslagen in Azure Blob-opslag en in tabellen, en Azure Disk Encryption versleutelt gegevens in wachtrijen, evenals Windows- en IaaS-virtuele computerschijfjes om volumeversleuteling te bieden voor het besturingssysteem en de gegevensschijf. De oplossing zorgt ervoor dat alle gegevens op de virtuele computerschijf in rust worden versleuteld in uw Azure-opslag. [Versleuteling in Rust in Azure Cosmos DB](/azure/cosmos-db/database-encryption-at-rest) wordt geïmplementeerd met behulp van verschillende beveiligingstechnologieën, waaronder veilige opslagsystemen voor sleutels, versleutelde netwerken en cryptografische API's.

## <a name="azure-key-vault"></a>Azure Key Vault

Secure key management is niet alleen de kern van versleuteling best practices; het is ook essentieel voor het beveiligen van gegevens in de cloud. [Met Azure Key Vault](/azure/key-vault/key-vault-whatis) kunt u sleutels en kleine geheimen versleutelen, zoals wachtwoorden die gebruikmaken van sleutels die zijn opgeslagen in hardwarebeveiligingsmodules (HSM's). Azure Key Vault is de aanbevolen oplossing van Microsoft voor het beheren en beheren van toegang tot versleutelingssleutels die worden gebruikt door cloudservices. Machtigingen voor toegang tot sleutels kunnen worden toegewezen aan services of aan gebruikers met Azure Active Directory accounts. Azure Key Vault ontlast organisaties van de noodzaak om HSMs en sleutelbeheersoftware te configureren, te patchen en te onderhouden. Met Azure Key Vault ziet Microsoft nooit dat uw sleutels en toepassingen geen directe toegang tot deze sleutels hebben. u de controle houdt. U kunt ook sleutels importeren of genereren in HSMs. Organisaties die een abonnement hebben dat Azure Information Protection bevat, kunnen hun Azure Information Protection-tenant zo configureren dat ze een door de klant beheerde sleutel [Bring Your Own Key](/information-protection/plan-design/byok-price-restrictions) (BYOK) gebruiken en het gebruik ervan [aanmelden.](/information-protection/deploy-use/log-analyze-usage)