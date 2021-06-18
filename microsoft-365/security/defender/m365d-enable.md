---
title: Uw Microsoft 365 Defender in het Microsoft 365 beveiligingscentrum
description: Meer informatie over het inschakelen Microsoft 365 Defender en het integreren van uw beveiligingsincident en antwoord.
keywords: aan de slag, Microsoft 365 Defender, Microsoft 365 Defender, M365, beveiliging, gegevenslocatie, vereiste machtigingen, licentie geschiktheid, instellingenpagina
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 102666834562d0576920c746842582c2870b3738
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007607"
---
# <a name="turn-on-microsoft-365-defender"></a>Microsoft 365 Defender inschakelen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-365-defender.md) maakt het proces voor incidentrespons bij door belangrijke mogelijkheden te integreren in Microsoft Defender voor Eindpunt, Microsoft Defender voor Office 365, Microsoft Cloud App Security en Microsoft Defender voor identiteit. Deze geïntegreerde ervaring voegt krachtige functies toe die u kunt gebruiken in het Microsoft 365 beveiligingscentrum.

Microsoft 365 Defender wordt automatisch in gebruik wanneer in aanmerking komende klanten met de vereiste machtigingen naar Microsoft 365 beveiligingscentrum gaan. Lees dit artikel voor meer informatie over verschillende vereisten en hoe Microsoft 365 Defender is ingericht.

## <a name="check-license-eligibility-and-required-permissions"></a>Controleer de geschiktheid van licenties en vereiste machtigingen

Een licentie voor een Microsoft 365 beveiligingsproduct geeft u over het algemeen het recht om Microsoft 365 Defender gebruiken in Microsoft 365 beveiligingscentrum zonder extra licentiekosten. We raden u aan een licentie voor Microsoft 365 E5, E5-beveiliging, A5 of A5-beveiligingslicentie of een geldige combinatie van licenties te krijgen die toegang biedt tot alle ondersteunde services.

Lees de licentievereisten voor [gedetailleerde licentiegegevens.](prerequisites.md#licensing-requirements)

### <a name="check-your-role"></a>Uw rol controleren

U moet een globale **beheerder of** beveiligingsbeheerder **zijn** in Azure Active Directory om de Microsoft 365 Defender. [Uw rollen weergeven in Azure AD](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>Ondersteunde services

Microsoft 365 Defender statistische gegevens uit de verschillende ondersteunde services die u al hebt geïmplementeerd. Er worden gegevens centraal verwerkt en opgeslagen om nieuwe inzichten te identificeren en gecentraliseerde antwoordwerkstromen mogelijk te maken. Dit doet het zonder dat dit gevolgen heeft voor bestaande implementaties, instellingen of gegevens die zijn gekoppeld aan de geïntegreerde services.

Om de beste beveiliging te krijgen en Microsoft 365 Defender optimaliseren, raden we u aan alle van toepassing zijnde ondersteunde services in uw netwerk te implementeren. Lees voor meer informatie [over het implementeren van ondersteunde services.](deploy-supported-services.md)

## <a name="onboard-to-the-service"></a>Aan boord van de service
Onboarding naar Microsoft 365 Defender is eenvoudig. Selecteer in het navigatiemenu een item, zoals Incidenten & **waarschuwingen,** **Jagen,** **Actiecentrum** of Bedreigingsanalyse om het onboardingproces te starten.  

### <a name="data-center-location"></a>Locatie van datacenter

Microsoft 365 Defender gegevens worden opgeslagen en verwerkt op dezelfde locatie die [door Microsoft Defender voor Eindpunt wordt gebruikt.](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy) Als u geen Microsoft Defender voor Eindpunt hebt, wordt automatisch een nieuwe datacenterlocatie geselecteerd op basis van de locatie van actieve Microsoft 365 beveiligingsservices. De geselecteerde locatie van het datacenter wordt weergegeven in het scherm.

Selecteer **Hulp nodig?** in het Microsoft 365 beveiligingscentrum om contact op te nemen met microsoft-ondersteuning over het inrichten van Microsoft 365 Defender in een andere datacenterlocatie.

> [!NOTE]
> In het verleden is Microsoft Defender voor Eindpunt automatisch ingericht in datacenters van de Europese Unie (EU) wanneer deze zijn ingeschakeld via Azure Defender. Microsoft 365 Defender wordt automatisch ingericht in hetzelfde EU-datacenter voor klanten die Defender in het verleden op deze manier voor Eindpunt hebben ingericht.

### <a name="confirm-that-the-service-is-on"></a>Controleren of de service is aan

Wanneer de service is ingericht, wordt het volgende toegevoegd:

- [Incidentenbeheer](incidents-overview.md)
- [Waarschuwingenwachtrij](investigate-alerts.md)
- Een actiecentrum voor het beheren [van geautomatiseerd onderzoek en antwoord](m365d-autoir.md)
- [Geavanceerde mogelijkheden voor](advanced-hunting-overview.md) jagen
- Dreigingsanalyse

![Afbeelding van Microsoft 365 navigatiedeelvenster van het beveiligingscentrum met Microsoft 365 Defender functies Microsoft 365 beveiligingscentrum met ](../../media/overview-incident.png)
 *incidentenbeheer* en andere Microsoft 365 Defender mogelijkheden

### <a name="getting-microsoft-defender-for-identity-data"></a>Microsoft Defender voor identiteitsgegevens verkrijgen 
Als u de integratie met Microsoft Cloud App Security wilt inschakelen, moet u zich ten minste eenmaal aanmelden bij Microsoft Cloud App Security account.

## <a name="get-assistance"></a>Hulp krijgen

Als u antwoorden wilt krijgen op de meestgestelde vragen over het in Microsoft 365 Defender, leest u [de veelgestelde vragen.](m365d-enable-faq.md)

Microsoft-ondersteuningsmedewerkers kunnen helpen bij het inrichten of deprovisie van de service en gerelateerde resources op uw tenant. Voor hulp selecteert u **Hulp nodig?** in het Microsoft 365 beveiligingscentrum. Als u contact op kunt nemen met de ondersteuning, vermeldt u Microsoft 365 Defender.

## <a name="related-topics"></a>Verwante onderwerpen

- [Veelgestelde vragen](m365d-enable-faq.md)
- [Licentievereisten en andere vereisten](prerequisites.md)
- [Ondersteunde services implementeren](deploy-supported-services.md)
- [Microsoft 365 Defender overzicht](microsoft-365-defender.md)
- [Overzicht van Microsoft Defender voor eindpunt](../defender-endpoint/microsoft-defender-endpoint.md)
- [Overzicht van Defender voor Office 365](../office-365-security/defender-for-office-365.md)
- [Microsoft Cloud App Security overzicht](/cloud-app-security/what-is-cloud-app-security)
- [Overzicht van Microsoft Defender voor identiteit](/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender voor endpoint-gegevensopslag](../defender-endpoint/data-storage-privacy.md)
