---
title: Hoe Exchange Online uw e-mailgeheimen kan beveiligen
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2019
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 989ba10c-f73f-4efb-ad1b-af3322e5f376
ms.collection:
- M365-security-compliance
description: Naast het Office 365 Trust Center met beveiligings-, privacy- en compliancegegevens voor Microsoft 365, wilt u misschien weten hoe Microsoft u helpt bij het beschermen van geheimen die u in de datacenters opgeslagen. We gebruiken de technologie Distributed Key Manager (DKM).
ms.openlocfilehash: 2f6e51b7fe9cd75cbd265c3135050a08130f34d8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161873"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a>Hoe Exchange Online uw e-mailgeheimen kan beveiligen

In dit artikel wordt beschreven hoe Microsoft uw e-mailgeheimen in de datacenters beveiligt.
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a>Hoe beveiligen we geheime gegevens die door u worden verstrekt?

Naast het Office 365 Trust Center met [beveiligings-, privacy-](./get-started-with-service-trust-portal.md)en compliancegegevens voor Office 365, wilt u misschien weten hoe Microsoft helpt bij het beschermen van geheimen die u in de datacenters opgeeft. We gebruiken de technologie Distributed Key Manager (DKM).
  
[Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) (DKM) is een clientfunctionaliteit die een set geheime sleutels gebruikt om gegevens te versleutelen en te ontsleutelen. Alleen leden van een specifieke beveiligingsgroep in Active Directory Domain Services hebben toegang tot deze sleutels om de gegevens te ontsleutelen die door DKM worden versleuteld. In Exchange Online maken alleen bepaalde serviceaccounts waaronder de Exchange processen worden uitgevoerd deel uit van die beveiligingsgroep. Als onderdeel van de standaardprocedure in het datacenter wordt geen mens referenties gegeven die deel uitmaken van deze beveiligingsgroep en heeft daarom geen mens toegang tot de sleutels die deze geheimen kunnen ontsleutelen.
  
Voor foutopsporing, probleemoplossing of controle moet een datacenterbeheerder verhoogde toegang aanvragen om tijdelijke referenties te verkrijgen die deel uitmaken van de beveiligingsgroep. Voor dit proces zijn meerdere juridische goedkeuringsniveaus vereist. Als toegang wordt verleend, worden alle activiteiten geregistreerd en gecontroleerd. Daarnaast wordt toegang alleen verleend voor een ingesteld tijdsinterval waarna deze automatisch verloopt.
  
Voor extra beveiliging omvat DKM-technologie geautomatiseerde sleutelrollen en archivering. Dit zorgt er ook voor dat u uw oudere inhoud kunt blijven openen zonder dat u voor onbepaalde tijd op dezelfde sleutel moet vertrouwen.
  
## <a name="where-does-exchange-online-make-use-of-dkm"></a>Waar wordt Exchange Online DKM gebruikt?

Microsoft gebruikt [Distributed Key Manager om](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) uw geheimen te versleutelen in Exchange Online datacenters. Bijvoorbeeld:
  
- Referenties voor e-mailaccounts voor verbonden accounts. Verbonden accounts zijn accounts van derden, zoals Hotmail, Gmail en Yahoo! e-mailaccounts.

- Klantcode. Als u [serviceversleuteling gebruikt met klantsleutel,](customer-key-overview.md)gebruikt u [Azure Key Vault](/azure/key-vault/key-vault-whatis) om uw geheimen te beschermen.

## <a name="related-topics"></a>Verwante onderwerpen

[Versleuteling in Office 365](encryption.md)
  
[Technische naslaginformatie over versleuteling](technical-reference-details-about-encryption.md)
  
[Servicecontrole in het Beveiligings &amp; compliancecentrum](./service-assurance.md)
