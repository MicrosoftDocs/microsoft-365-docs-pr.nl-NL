---
title: Meer informatie over het standaard preventiebeleid voor gegevensverlies in Microsoft Teams (preview)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Meer informatie over het standaardbeleid voor preventie van gegevensverlies in Microsoft Teams
ms.openlocfilehash: 0663c370373708009346d4f858729e17436f0f62
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/30/2021
ms.locfileid: "52162908"
---
# <a name="learn-about-the-default-data-loss-prevention-policy-in-microsoft-teams-preview"></a>Meer informatie over het standaard preventiebeleid voor gegevensverlies in Microsoft Teams (preview)

[De mogelijkheden voor preventie van](dlp-learn-about-dlp.md) gegevensverlies zijn uitgebreid met Microsoft Teams chat- en kanaalberichten, inclusief privékanaalberichten. Als onderdeel van deze release hebben we een standaard DLP-beleid gemaakt voor klanten die voor het eerst naar het Compliancecentrum gaan.

## <a name="applies-to"></a>Van toepassing op

Elke tenant die een licentie heeft met een of meer van de onderstaande licenties en actieve gebruikers Teams gebruiken
 
- ME5, 
- MA5, 
- E5/A5 Compliance, 
- IP+G, 
- OE5, 
- O365 Advanced Compliance 
- EMS E5


## <a name="what-does-the-default-policy-do"></a>Wat doet het standaardbeleid?

Het standaard DLP-beleid houdt alle creditcardnummers bij die intern en extern worden gedeeld met de organisatie. Dit beleid is standaard ingeschakeld voor alle gebruikers van de tenant. Het genereert geen beleidstips voor eindgebruikers, maar genereert wel een waarschuwingsgebeurtenis en activeert ook een e-mail met een lage ernst naar de beheerder (toegevoegd aan het beleid). Beheerder kan de activiteiten bekijken en de beleidsdetails bewerken door u aan te melden bij het Compliancecentrum.

Beheerders kunnen dit beleid bekijken in het [compliancecentrum](https://compliance.microsoft.com/compliancesettings) > pagina Preventiebeleid voor gegevensverlies.


> [!div class="mx-imgBorder"]
> ![standaard Teams DLP-beleid](../media/default-teams-dlp-policy.png)

## <a name="edit-or-delete-the-default-policy"></a>Het standaardbeleid bewerken of verwijderen

Als [u het standaardbeleid wilt bewerken voor betere prestaties](create-test-tune-dlp-policy.md#tune-a-dlp-policy)of om het te verwijderen, gebruikt u een account met **DLP Compliance Management-machtigingen.** Zie Machtigingen [voor meer informatie.](create-test-tune-dlp-policy.md#permissions)

