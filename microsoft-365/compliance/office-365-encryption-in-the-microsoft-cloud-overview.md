---
title: Versleuteling in de Microsoft-cloud
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
description: Lees in dit artikel een overzicht van de verschillende versleutelingsvormen die worden gebruikt om klantgegevens veilig te houden in de Microsoft-cloud.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4a351215b7773574d5932b936e30c5d5ca7aa116
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/26/2021
ms.locfileid: "52162378"
---
# <a name="encryption-in-the-microsoft-cloud"></a>Versleuteling in de Microsoft-cloud

Klantgegevens in de zakelijke cloudservices van Microsoft worden beschermd door verschillende technologieën en processen, waaronder verschillende vormen van versleuteling. (Klantgegevens in dit document bevatten Exchange Online-postvakinhoud, e-mail, agenda-items en de inhoud van e-mailbijlagen, en, indien van toepassing, Skype voor Bedrijven-inhoud), SharePoint Online-site-inhoud en de bestanden die zijn opgeslagen op sites en bestanden die zijn geüpload naar OneDrive voor Bedrijven of Skype voor Bedrijven.) Microsoft gebruikt meerdere versleutelingsmethoden, protocollen en cijfers in haar producten en services om een veilig pad te bieden voor klantgegevens om door onze cloudservices te reizen en om de vertrouwelijkheid te beschermen van klantgegevens die zijn opgeslagen in onze cloudservices. Microsoft gebruikt enkele van de sterkste, veiligste versleutelingsprotocollen die beschikbaar zijn om onbevoegde toegang tot klantgegevens tegen te gaan. Goed sleutelbeheer is ook een essentieel element van best practices voor versleuteling en Microsoft zorgt ervoor dat alle door Microsoft beheerde versleutelingssleutels correct worden beveiligd.

Klantgegevens die zijn opgeslagen in de zakelijke cloudservices van Microsoft, worden beveiligd met behulp van een of meer vormen van versleuteling. (Validatie van ons cryptobeleid en de handhaving ervan wordt onafhankelijk gecontroleerd door meerdere externe auditors en rapporten van deze audits zijn beschikbaar op de [Service Trust Portal](https://aka.ms/stp).)

Microsoft biedt servicetechnologieën die klantgegevens in rust en onderweg versleutelen. Voor klantgegevens in rust gebruikt Microsoft Azure [bijvoorbeeld BitLocker](/windows/device-security/bitlocker/bitlocker-overview) en [DM-Crypt,](https://en.wikipedia.org/wiki/Dm-crypt)en Microsoft 365 gebruikt BitLocker, Azure Storage [Service Encryption,](/azure/) [Distributed Key Manager](./exchange-online-secures-email-secrets.md) (DKM) en Microsoft 365-serviceversleuteling. Voor klantgegevens die onderweg zijn, maken Azure, Office 365, Microsoft Commercial Support, Microsoft Dynamics 365, Microsoft Power BI en Visual Studio Team Services gebruik van branchestandaard beveiligde transportprotocollen, zoals IPsec (Internet Protocol Security) en Transport Layer Security (TLS), tussen Microsoft-datacenters en tussen gebruikersapparaten en Microsoft-datacenters.

Naast het basisniveau van cryptografische beveiliging die door Microsoft wordt geleverd, bevatten onze cloudservices ook cryptografieopties die u kunt beheren. U kunt bijvoorbeeld versleuteling inschakelen voor verkeer tussen hun Virtuele Azure-machines (VM's) en hun gebruikers. Met [Azure Virtual Networks](https://azure.microsoft.com/services/virtual-network/)kunt u het industriestandaard IPsec-protocol gebruiken om het verkeer tussen uw zakelijke VPN-gateway en Azure te versleutelen. U kunt ook verkeer versleutelen tussen de VM's in uw virtuele netwerk. Bovendien kunt [u met Office 365-berichtversleuteling nieuwe functies](set-up-new-message-encryption-capabilities.md) versleutelde e-mail naar iedereen verzenden.

In navolging van de operationele beveiligingsstandaard openbare sleutelinfrastructuur, een onderdeel van het [Microsoft-beveiligingsbeleid,](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5868ecc8-50b7-4f91-b43f-640e2b99e86e&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ%20and%20White%20Papers)gebruikt Microsoft de cryptografische mogelijkheden die zijn opgenomen in het Windows-besturingssysteem voor certificaten en verificatiemechanismen. Deze mechanismen omvatten het gebruik van cryptografische modules die voldoen aan de FiPS-norm [(Federal Information Processing Standards)](https://csrc.nist.gov/publications/PubsFIPS.html) 140-2 van de Amerikaanse overheid. U kunt zoeken naar de relevante NIST-certificaatnummers voor Microsoft met behulp van de CMVP van het [cryptografische modulevalidatieprogramma.](https://csrc.nist.gov/projects/cryptographic-module-validation-program/validated-modules/search)

> [OPMERKING] Als u het Microsoft-beveiligingsbeleid als resource wilt gebruiken, moet u zich aanmelden met uw werk- of schoolaccount. Als u nog geen abonnement hebt, kunt [u zich registreren voor een gratis proefabonnement.](https://servicetrust.microsoft.com/Home/TrialSubscriptions)

FIPS 140-2 is een standaard die speciaal is ontworpen voor het valideren van productmodules die cryptografie implementeren in plaats van de producten die deze gebruiken. Cryptografische modules die binnen een service worden geïmplementeerd, kunnen worden gecertificeerd als voldoen aan de vereisten voor hash-sterkte, sleutelbeheer en meer. De cryptografische modules en cijfers die worden gebruikt om de vertrouwelijkheid, integriteit of beschikbaarheid van gegevens in de cloudservices van Microsoft te beschermen, voldoen aan de FIPS 140-2-standaard.

Microsoft certificeert de onderliggende cryptografische modules die in onze cloudservices worden gebruikt bij elke nieuwe release van het Windows besturingssysteem:

- Azure en Azure U.S. Government
- Dynamics 365 en Dynamics 365 Amerikaanse overheid
- Office 365, Office 365 U.S. Government en Office 365 U.S. Government Defense

Versleuteling van klantgegevens in rust wordt geleverd door meerdere servicetechnologieën, waaronder BitLocker, DKM, Azure Storage Service Encryption en serviceversleuteling in Exchange Online, Skype voor Bedrijven, OneDrive voor Bedrijven en SharePoint Online. Office 365 serviceversleuteling bevat een optie voor het gebruik van door de klant beheerde versleutelingssleutels die zijn opgeslagen in Azure Key Vault. Deze door de klant [](./customer-key-overview.md)beheerde sleuteloptie, genaamd Klantsleutel, is beschikbaar voor Exchange Online, SharePoint Online, Skype voor Bedrijven en OneDrive voor Bedrijven.

Voor klantgegevens die onderweg zijn, Office 365 standaard veilige sessies met TLS met clientapparaten om klantgegevens te beveiligen. U kunt bijvoorbeeld Office 365 beveiligde sessies met Skype voor Bedrijven, Outlook en Outlook op internet, mobiele clients en webbrowsers.

(Alle op de klant gerichte servers onderhandelen standaard over TLS 1.2.)

## <a name="related-links"></a>Gerelateerde koppelingen

- [Versleuteling in Azure](office-365-azure-encryption.md)
- [BitLocker en Distributed Key Manager (DKM) voor versleuteling](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)
- [Office 365 Serviceversleuteling](office-365-service-encryption.md)
- [Office 365 Versleuteling voor Skype voor Bedrijven, OneDrive voor Bedrijven, SharePoint Online en Exchange Online](https://docs.microsoft.com/compliance/assurance/assurance-encryption-for-microsoft-365-services) 
- [Versleuteling voor gegevens in transit](/compliance/assurance/assurance-encryption-in-transit)
- [Door klanten beheerde versleutelingsfuncties](office-365-customer-managed-encryption-features.md)
- [Versleutelingsrisico's en -beveiligingen](office-365-encryption-risks-and-protections.md)
- [Versleuteling in Microsoft Dynamics 365](office-365-encryption-in-microsoft-dynamics-365.md)