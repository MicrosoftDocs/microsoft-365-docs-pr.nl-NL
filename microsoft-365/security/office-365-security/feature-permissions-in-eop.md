---
title: Functiemachtigingen in EOP
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 1/30/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: De machtigingen die nodig zijn om taken uit te voeren voor het beheer van Microsoft Exchange Online Protection (EOP) zijn afhankelijk van de functie die u beheert.
ms.openlocfilehash: 146bf34f157eb30e680ad9e0c3e53501d6e7b425
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638116"
---
# <a name="feature-permissions-in-eop"></a>Functiemachtigingen in EOP

De machtigingen die nodig zijn om taken uit te voeren voor het beheer van Exchange Online Protection (EOP) zijn afhankelijk van de functie die u beheert.

Als u EOP wilt instellen, moet u een globale beheerder of een Exchange Company Administrator (de rolgroep Organisatiebeheer) zijn.

## <a name="exchange-online-protection-permissions"></a>Machtigingen voor Exchange Online Protection

Zie de volgende tabel voor meer informatie over de machtigingen die u nodig hebt om EOP-functies te beheren. Als een functie meer dan een rolgroep opnoemt, moet u slechts een van de rolgroepen hebben toegewezen om de functie te gebruiken.

|**Functie**|**Vereiste machtigingen**|
|:-----|:-----|
|Anti-malware|Organisatiebeheer <br/><br/> Hygiënebeheer|
|Anti-spam|Organisatiebeheer <br/><br/> Hygiënebeheer|
|Regels voor e-mailstromen|Organisatiebeheer <br/><br/> Records beheer|
|Domeinen|Organisatiebeheer <br/><br/> Alleen-weergaveorganisatiebeheer|
|Geavanceerde bedreigingsbeveiliging (ATP)|Organisatiebeheer <br/><br/> Hygiënebeheer|
|Microsoft 365-connectors|Organisatiebeheer|
|Berichttracering|Organisatiebeheer <br/><br/> Alleen-weergaveorganisatiebeheer|
|Organisatieconfiguratie|Organisatiebeheer|
|Quarantaine|Organisatiebeheer <br/><br/> Alleen-weergaveorganisatiebeheer <br/><br/> Hygiënebeheer|
|Gebruikers, contactpersonen en rolgroepen|Organisatiebeheer <br/><br/> Alleen-weergaveorganisatiebeheer <br/><br/> Hygiënebeheer|
|Distributiegroepen en beveiligingsgroepen|Organisatiebeheer <br/><br/> Alleen-weergaveorganisatiebeheer <br/><br/> Hygiënebeheer|
|Rapporten weergeven|Organisatiebeheer: toegang tot rapporten over e-mailbeveiliging. <br/><br/> Alleen-weergeven ontvangers: toegang tot rapporten over e-mailbeveiliging.  <br/><br/> Compliance Management: Toegang tot e-mailbeveiligingsrapporten en DLP-rapporten (Data Loss Prevention) (als uw abonnement dlp-mogelijkheden heeft).|
