---
title: Aangepaste rapportage oplossingen gebruiken met automatisch onderzoek en antwoord
keywords: AIR, autoIR, ATP, automatisch, onderzoek, antwoord, herstel, bedreiging, Geavanceerd, bedreiging, bescherming
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
ms.openlocfilehash: 2ff0ef995fc8418c3d57895f00ea96f05b0aaa97
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195603"
---
# <a name="use-the-management-activity-api-for-custom-or-third-party-reporting-solutions"></a>De API voor beheeractiviteiten gebruiken voor aangepaste oplossingen of oplossingen voor rapportage van derden

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Met [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)kunt u [gedetailleerde informatie raadplegen over geautomatiseerde onderzoeken](air-view-investigation-results.md). Sommige organisaties gebruiken echter ook een aangepaste oplossing of een rapportage oplossing van derden. Als uw organisatie informatie wil integreren over een geautomatiseerd onderzoek met een dergelijke oplossing, kunt u gebruikmaken van de API Office 365 Management Activity.

Gebruik de volgende bronnen om dit in te stellen:

****

|Materialen|Beschrijving|
|---|---|
|[Overzicht van Office 365 Management Api's](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|De Office 365 Management Activity API biedt informatie over diverse acties en gebeurtenissen van gebruikers, beheerders, systemen en beleid uit Microsoft 365 en Azure Active Directory-activiteitenlogboeken.|
|[Aan de slag met Api's van Office 365 Management](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|De Office 365-beheer-API maakt gebruik van Azure AD om authenticatie services te bieden voor de toepassing om toegang te krijgen tot gegevens van Microsoft 365. Voer de stappen in dit artikel uit om dit in te stellen.|
|[Naslag voor Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|U kunt de Office 365 Management Activity API gebruiken om informatie op te halen over acties en gebeurtenissen van gebruikers, beheerders, systemen en beleid uit Microsoft 365 en Azure AD-activiteitenlogboeken. Lees dit artikel voor meer informatie over hoe dit werkt.|
|[Office 365 Management Activity API-schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|Bekijk een overzicht van het [gemeenschappelijke schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) en het [schema Office 365 ATP-en risico onderzoek en antwoordschema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) voor informatie over specifieke soorten gegevens die beschikbaar zijn via de Office 365 Management Activity API.|
|

## <a name="related-articles"></a>Verwante artikelen

- [Office 365 Advanced Threat Protection](office-365-atp.md)

- [Meer informatie over het geautomatiseerde onderzoek en antwoord in Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
