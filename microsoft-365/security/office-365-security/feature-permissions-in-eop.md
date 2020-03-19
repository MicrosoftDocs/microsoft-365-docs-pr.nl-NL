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
description: De machtigingen die nodig zijn om taken uit te voeren om Microsoft Exchange Online Protection (EOP) te beheren, zijn afhankelijk van de functie die u beheert.
ms.openlocfilehash: 2129df7faaa977d59f8af8082291520d33bc9cc7
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42806624"
---
# <a name="feature-permissions-in-eop"></a>Functiemachtigingen in EOP

De machtigingen die nodig zijn om taken uit te voeren om Exchange Online Protection (EOP) te beheren, zijn afhankelijk van de functie die u beheert.

Als u EOP wilt instellen, moet u een Globale Beheerder van Office 365 of een Exchange Company Administrator (de rolgroep Organisatiebeheer) zijn.

## <a name="exchange-online-protection-permissions"></a>Machtigingen voor exchange online-beveiliging

Zie de volgende tabel om te weten te komen welke machtigingen u nodig hebt om EOP-functies te beheren. Als een functie meer dan een rolgroep opnoemt, moet u slechts een van de rolgroepen hebben toegewezen om de functie te gebruiken.

|**Functie**|**Vereiste machtigingen**|
|:-----|:-----|
|Anti-malware|Organisatiebeheer <br/><br/> Hygiënemanagement|
|Anti-spam|Organisatiebeheer <br/><br/> Hygiënemanagement|
|Regels voor e-mailstroom|Organisatiebeheer <br/><br/> Beheer van records|
|Domeinen|Organisatiebeheer <br/><br/> Alleen-view organisatiebeheer|
|Advanced Threat Protection (ATP)|Organisatiebeheer <br/><br/> Hygiënemanagement|
|Office 365-connectors|Organisatiebeheer|
|Berichttracering|Organisatiebeheer <br/><br/> Alleen-view organisatiebeheer|
|Organisatieconfiguratie|Organisatiebeheer|
|Quarantaine|Organisatiebeheer <br/><br/> Alleen-view organisatiebeheer <br/><br/> Hygiënemanagement|
|Gebruikers, contactpersonen en rolgroepen|Organisatiebeheer <br/><br/> Alleen-view organisatiebeheer <br/><br/> Hygiënemanagement|
|Distributiegroepen en beveiligingsgroepen|Organisatiebeheer <br/><br/> Alleen-view organisatiebeheer <br/><br/> Hygiënemanagement|
|Rapporten weergeven|Organisatiebeheer: toegang tot e-mailbeveiligingsrapporten. <br/><br/> Ontvangers die alleen voor weergave zijn: toegang tot e-mailbeveiligingsrapporten.  <br/><br/> Compliance Management: Toegang tot e-mailbeveiligingsrapporten en DLP-rapporten (Data Loss Prevention) (als uw abonnement DLP-mogelijkheden heeft).|
