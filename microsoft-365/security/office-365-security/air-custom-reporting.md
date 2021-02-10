---
title: Aangepaste rapportageoplossingen met automatisch onderzoek en reactie
keywords: SIEM, API, AIR, AutoIR, ATP, geautomatiseerd onderzoek, integratie, aangepast rapport
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Lees hoe u automatisch onderzoek en antwoorden kunt integreren met een aangepaste oplossing voor rapportages of rapporten van derden.
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a66a89a13182570259bcb8be4134c21d13e22391
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175809"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a>Aangepaste of externe rapportageoplossingen voor Microsoft Defender voor Office 365

Met [Microsoft Defender voor Office 365](office-365-atp.md)krijgt u gedetailleerde informatie over [geautomatiseerde onderzoeken.](air-view-investigation-results.md) Sommige organisaties gebruiken echter ook een aangepaste rapportageoplossing of rapportageoplossing van derden. Als uw organisatie informatie [](office-365-air.md) over geautomatiseerde onderzoeken wil integreren met een dergelijke oplossing, kunt u de Office 365 Management Activity-API gebruiken.

**Van toepassing op**
- [Microsoft Defender voor Office 365-abonnement 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Met [Microsoft Defender voor Office 365](office-365-atp.md)krijgt u gedetailleerde informatie over [geautomatiseerde onderzoeken.](air-view-investigation-results.md) Sommige organisaties gebruiken echter ook een aangepaste rapportageoplossing of rapportageoplossing van derden. Als uw organisatie informatie over geautomatiseerde onderzoeken wil integreren met een dergelijke oplossing, kunt u de Office 365 Management Activity-API gebruiken.

|Resource|Beschrijving|
|:---|:---|
|[Overzicht van Office 365-beheer-API's](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|De Office 365 Management Activity-API biedt informatie over diverse gebruikers-, beheerders-, systeem- en beleidsacties en -gebeurtenissen uit microsoft 365- en Azure Active Directory-activiteitslogboeken.|
|[Aan de slag met Beheer-API's van Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|De Office 365 Management-API gebruikt Azure AD om verificatieservices aan te bieden voor uw toepassing voor toegang tot Microsoft 365-gegevens. Volg de stappen in dit artikel om dit in te stellen.|
|[Office 365 Management Activity-API-referentie](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|U kunt de Office 365 Management Activity-API gebruiken om informatie over gebruikers-, beheerders-, systeem- en beleidsacties en -gebeurtenissen op te halen uit activiteitenlogboeken van Microsoft 365 en Azure AD. Lees dit artikel voor meer informatie over hoe dit werkt.|
|[Office 365 Management Activity-API-schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|Krijg een overzicht van het [algemene schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) en het Defender voor [Office 365-](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) en bedreigingsonderzoek en antwoordschema voor meer informatie over specifieke soorten gegevens die beschikbaar zijn via de Management Activity API van Office 365.|
|

## <a name="see-also"></a>Zie ook

- [Microsoft Defender voor Office 365](office-365-atp.md)
- [Automatisch onderzoek en antwoorden in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
