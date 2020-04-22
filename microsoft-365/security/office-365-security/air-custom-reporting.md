---
title: Aangepaste rapportageoplossingen gebruiken met geautomatiseerd onderzoek en respons
keywords: AIR, autoIR, ATP, geautomatiseerd, onderzoek, respons, sanering, bedreigingen, geavanceerd, bedreiging, bescherming
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
description: Meer informatie over het integreren van geautomatiseerd onderzoek en respons met een aangepaste of externe rapportageoplossing.
ms.openlocfilehash: 4bd53de9a880fc774814588ed84dce2284535922
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634716"
---
# <a name="use-the-management-activity-api-for-custom-or-third-party-reporting-solutions"></a>Gebruik de API voor beheeractiviteit voor aangepaste of externe rapportageoplossingen

Met [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)krijgt u gedetailleerde informatie over [geautomatiseerde onderzoeken.](air-view-investigation-results.md) Sommige organisaties gebruiken echter ook een aangepaste of externe rapportageoplossing. Als uw organisatie informatie over geautomatiseerde onderzoeken met een dergelijke oplossing wil integreren, u de Office 365 Management Activity API gebruiken.

Gebruik de volgende bronnen om dit in te stellen:

|Resource  |Beschrijving  |
|---------|---------|
|[Overzicht van Office 365 Management API's](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)     |De Office 365 Management Activity API bevat informatie over verschillende gebruikers-, beheerders-, systeem- en beleidsacties en -gebeurtenissen uit Microsoft 365- en Azure Active Directory-activiteitslogboeken.         |
|[Aan de slag met Office 365 Management API's](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)     |De Office 365 Management API maakt gebruik van Azure AD om verificatieservices voor uw toepassing te bieden om toegang te krijgen tot Microsoft 365-gegevens. Volg de stappen in dit artikel om dit in te stellen.          |
|[Verwijzing naar api-activiteit voor Office 365-beheer](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)     |U de Office 365 Management Activity API gebruiken om informatie over gebruikers-, beheerders-, systeem- en beleidsacties en -gebeurtenissen op te halen uit microsoft 365- en Azure AD-activiteitslogboeken. Lees dit artikel voor meer informatie over hoe dit werkt.        |
|[Api-schema voor activiteitsbeheer office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)     |Krijg een overzicht van het [common-schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) en het [Office 365 ATP- en bedreigingsonderzoeks- en reactieschema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) voor meer informatie over specifieke soorten gegevens die beschikbaar zijn via de Office 365 Management Activity API.         |

## <a name="related-articles"></a>Verwante artikelen

- [Office 365 Advanced Threat Protection](office-365-atp.md)

- [Meer informatie over geautomatiseerd onderzoek en reactie in Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)