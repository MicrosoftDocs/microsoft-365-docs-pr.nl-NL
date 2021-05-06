---
title: Microsoft 365-compliance-ondersteuning voor release-notes van dubbel-byte-tekenset (preview)
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Release-notes voor ondersteuning van dubbel-byte-tekensets.
ms.openlocfilehash: 1c2244c49a92aa2c00fad06caa8194cf7e32220e
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/22/2020
ms.locfileid: "52161543"
---
# <a name="support-for-double-byte-character-set-release-notes-preview"></a>Ondersteunding voor release-notes van dubbel-byte-tekenset (preview)

 Microsoft 365 Information Protection ondersteunt momenteel talen voor preview van dubbel-byte-tekensets voor:

- Chinees (vereenvoudigd)
- Chinees (traditioneel)
- Koreaans
- Japans

Deze ondersteuning is beschikbaar voor gevoelige informatietypen en sleutelwoordboeken. Deze wordt weerspiegeld in preventie van gegevensverlies, communicatiecompliance, Exchange Online, SharePoint Online, OneDrive voor Bedrijven en Teams-oplossingen.

## <a name="known-issues"></a>Bekende problemen

- Als een tekstbestand dat als bijlage is toegevoegd aan een e-mailbericht in UTF-8-formaat zonder bytevolgordemarkering (BOM), wordt het e-mailbericht niet gedetecteerd door het communicatie-compliancebeleid.

- Communicatie-compliancebeleid kan waarden niet detecteren als een zin is ingevoerd voor de beleidsvoorwaarde: 'Bericht bevat de volgende woorden'. Als de opgegeven tekst in het beleid als een woord is uitgeschreven, kan het gedetecteerd worden. Als het echter in het midden van een zin is geschreven, zal het niet gedetecteerd worden.

- Communicatie-compliancebeleid dat woordenboeken specificeert als letterbeeldinformatie, kan privé-chats en kanaalchats in Teams niet detecteren.

- De volgende voorwaarden worden in deze fase niet ondersteund door communicatie-compliance (er wordt aan een oplossing voor deze problemen gewerkt): 
  - 'Bericht bevat deze worden'
  - 'Bericht bevat geen van deze worden'
  - 'Bijlage bevat deze worden'
  - 'Bijlage bevat deze worden'

We raden in plaats daarvan aan een aangepast type gevoelige gegevens (SIT) met sleutelwoordenboek te maken, dat patronen in berichten en bijlagen kan detecteren. Gebruik deze aangepaste SIT als een voorwaarde voor communicatie-compliancebeleid.
