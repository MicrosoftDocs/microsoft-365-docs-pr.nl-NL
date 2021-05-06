---
title: BitLocker voor versleuteling
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
description: Meer informatie over Office 365 gebruik BitLocker versleuteling, waardoor de kans op gegevensdiefstal als gevolg van verloren of gestolen computers en schijven wordt verkleind.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cc329a053544ba6cf1753ae07caac642546cad11
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "52161453"
---
# <a name="bitlocker-and-distributed-key-manager-dkm-for-encryption"></a>BitLocker en Distributed Key Manager (DKM) voor versleuteling

Microsoft-servers gebruiken BitLocker om de schijfstations met klantgegevens op volumeniveau te versleutelen. BitLocker versleuteling is een functie voor gegevensbeveiliging die is ingebouwd in Windows. BitLocker is een van de technologieën die worden gebruikt om bedreigingen te beschermen voor het geval er sprake is van een fout in andere processen of besturingselementen (bijvoorbeeld toegangsbeheer of hergebruik van hardware) die ertoe kunnen leiden dat iemand fysieke toegang krijgt tot schijven met klantgegevens. In dit geval BitLocker risico op gegevensdiefstal of blootstelling als gevolg van verloren, gestolen of ongepast buiten bedrijf gesteld computers en schijven.

BitLocker wordt geïmplementeerd met AES(Advanced Encryption Standard) 256-bits versleuteling op schijven met klantgegevens in Exchange Online, SharePoint Online en Skype voor Bedrijven. Schijfsectoren worden versleuteld met een Full Volume Encryption Key (FVEK), die is versleuteld met de Volume Master Key (VMK), die op zijn beurt is gebonden aan de Trusted Platform Module (TPM) op de server. De VMK beschermt de FVEK rechtstreeks en daarom wordt het beschermen van de VMK kritiek. In de volgende afbeelding ziet u een voorbeeld van de BitLocker sleutelbeveiligingsketen voor een bepaalde server (in dit geval met een Exchange Online server).

In de volgende tabel wordt beschreven BitLocker sleutelbeveiligingsketen voor een bepaalde server (in dit geval een Exchange Online server).

| KEY PROTECTOR | GRANULARITEIT | HOE GEGENEREERD? | WAAR WORDT HET OPGESLAGEN? | BEVEILIGING |
|--------------------------------------------------------------------------------|-------------------------------------------------|----------------|-------------------------|--------------------------------------------------------------------------------------------------|
| AES 256-bits externe sleutel | Per Server | BitLocker API's | TPM of Secret Safe | Lockbox / Access Control |
|  |  |  | Postvakserverregister | TPM versleuteld |
| Numeriek wachtwoord van 48 cijfers | Per schijf | BitLocker API's | Active Directory | Lockbox / Access Control |
| X.509 Certificate as Data Recovery Agent (DRA) ook wel Public Key Protector genoemd | Omgeving (bijvoorbeeld Exchange Online multitenant) | Microsoft CA | Build-systeem | Niemand heeft het volledige wachtwoord voor de persoonlijke sleutel. Het wachtwoord staat onder fysieke beveiliging. |


BitLocker sleutelbeheer omvat het beheer van herstelsleutels die worden gebruikt voor het ontgrendelen/herstellen van versleutelde schijven in een Microsoft-datacenter. Microsoft 365 worden de hoofdsleutels opgeslagen in een beveiligd deel, alleen toegankelijk voor personen die zijn gescreend en goedgekeurd. De referenties voor de sleutels worden opgeslagen in een beveiligde opslagplaats voor toegangsbeheergegevens (wat we een 'geheim archief' noemen), waarvoor een hoog niveau van hoogte- en beheergoedkeuringen nodig is om toegang te krijgen met behulp van een just-in-time toegangsverheffingshulpmiddel.

BitLocker ondersteunt sleutels die in twee beheercategorieën vallen:

- BitLocker-beheerde sleutels, die over het algemeen van korte duur zijn en zijn gekoppeld aan de levensduur van een besturingssysteem-exemplaar dat is geïnstalleerd op een server of op een bepaalde schijf. Deze sleutels worden verwijderd en opnieuw ingesteld tijdens het opnieuw installeren van de server of tijdens het opmaken van de schijf.

- BitLocker herstelsleutels, die buiten de BitLocker worden beheerd, maar worden gebruikt voor schijfdecryptie. BitLocker gebruikt herstelsleutels voor het scenario waarin een besturingssysteem opnieuw wordt geïnstalleerd en er al versleutelde gegevensschijfjes bestaan. Herstelsleutels worden ook gebruikt door controle-sondes voor beheerde beschikbaarheid in Exchange Online waar een responder mogelijk een schijf moet ontgrendelen.

BitLocker beveiligde volumes worden versleuteld met een volledige volumeversleutelingssleutel, die op zijn beurt wordt versleuteld met een volumemodelsleutel. BitLocker maakt gebruik van FIPS-compatibele algoritmen om ervoor te zorgen dat versleutelingssleutels nooit worden opgeslagen of over de draad worden verzonden. De Microsoft 365 implementatie van klantgegevens-at-rest-protection wijkt niet af van de standaard implementatie BitLocker implementatie.
