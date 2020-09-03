---
title: Enterprise Access-besturingselementen voor Microsoft 365 Yammer
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Dit artikel bevat een beknopt overzicht van de besturingselementen voor Enterprise-toegangsbeheer in de productieomgeving.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b7e1ceae1b7ddda4c2eac96cd581a612768f1461
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332662"
---
# <a name="yammer-enterprise-access-controls"></a>Enterprise Access-besturingselementen voor Yammer 

Fysiek en logisch toegankelijke voor de Yammer-productieomgeving is beperkt tot een klein aantal personen (infrastructuur en bewerkingen). Net als met andere Microsoft 365-technici hebben Yammer-ingenieurs geen toegang tot klantgegevens. U moet een verzoek indienen op basis van een goedkeuringssysteem voor een goedkeuringsproces dat is gekoppeld aan de lockbox met een beperkt aantal goedkeurders. Goedkeurders verifieert de aanvraag (bijvoorbeeld de persoon controleert of de aanvraag legitiem is op basis van behoefte, zakelijk geval, tijd, etc.) en keurt de aanvraag goed of weigert. Als de aanvraag is goedgekeurd, wordt JIT-toegang verleend voor een gedefinieerde en beperkte tijd. Wanneer de toegangs periode is verstreken, wordt de toegang automatisch verloopt.

Net als bij andere Microsoft 365-Services, maakt alle toegang tot de Yammer-productieomgeving gebruik van meervoudige verificatie. Alle toegang-en opdrachtgeschiedenis wordt gekenmerkd aan een gebruiker, die regelmatig is aangemeld en gecontroleerd door het Yammer-beveiligingsteam.

Zie [Help voor Yammer-beheerders](https://docs.microsoft.com/yammer/yammer-landing-page)voor meer informatie over Yammer-beheer en-beheer.