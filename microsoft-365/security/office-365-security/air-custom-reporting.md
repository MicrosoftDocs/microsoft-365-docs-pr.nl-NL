---
title: Aangepaste rapportage oplossingen gebruiken met automatisch onderzoek en antwoord
keywords: SIEM, API, AIR, autoIR, ATP, automatisch onderzoek, integratie, aangepast rapport
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Leer hoe u een geautomatiseerd onderzoek en antwoord kunt integreren met een aangepaste oplossing of een rapportage oplossing van derden.
ms.date: 09/29/2020
ms.custom:
- air
ms.openlocfilehash: 08502516ae03dc7c6e7b58aa77939723e7532ef0
ms.sourcegitcommit: 6b1d0bea86ced26cae51695c0077adce8bcff3c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308918"
---
# <a name="use-the-management-activity-api-for-custom-or-third-party-reporting-solutions"></a>De API voor beheeractiviteiten gebruiken voor aangepaste oplossingen of oplossingen voor rapportage van derden

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Met [Microsoft Defender voor Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)kunt u [gedetailleerde informatie raadplegen over geautomatiseerde onderzoek](air-view-investigation-results.md). Sommige organisaties gebruiken echter ook een aangepaste oplossing of een rapportage oplossing van derden. Als uw organisatie informatie wil integreren over een geautomatiseerd onderzoek met een dergelijke oplossing, kunt u gebruikmaken van de API Office 365 Management Activity.

Gebruik de volgende bronnen om dit in te stellen:

****

|Materialen|Beschrijving|
|---|---|
|[Overzicht van Office 365 Management Api's](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|De Office 365 Management Activity API biedt informatie over diverse acties en gebeurtenissen van gebruikers, beheerders, systemen en beleid uit Microsoft 365 en Azure Active Directory-activiteitenlogboeken.|
|[Aan de slag met Api's van Office 365 Management](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|De Office 365-beheer-API maakt gebruik van Azure AD om authenticatie services te bieden voor de toepassing om toegang te krijgen tot gegevens van Microsoft 365. Voer de stappen in dit artikel uit om dit in te stellen.|
|[Naslag voor Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|U kunt de Office 365 Management Activity API gebruiken om informatie op te halen over acties en gebeurtenissen van gebruikers, beheerders, systemen en beleid uit Microsoft 365 en Azure AD-activiteitenlogboeken. Lees dit artikel voor meer informatie over hoe dit werkt.|
|[Office 365 Management Activity API-schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|Bekijk een overzicht van het [gemeenschappelijke schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) en het [schema Office 365 ATP-en risico onderzoek en antwoordschema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) voor informatie over specifieke soorten gegevens die beschikbaar zijn via de Office 365 Management Activity API.|
|

## <a name="see-also"></a>Zie ook

- [Microsoft Defender voor Office 365](office-365-atp.md)

- [Automatisch onderzoek en antwoord in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
