---
title: Veelgestelde vragen over het inschakelen van Microsoft Threat Protection
description: Hier vindt u antwoorden op de meest gestelde vragen over licenties, machtigingen, initiële instellingen en andere producten en services met betrekking tot het inschakelen van Microsoft Threat Protection
keywords: Veelgestelde vragen, veelgestelde vragen, GCC, aan de slag, MTP inschakelen, Microsoft Threat Protection, M365, beveiliging, gegevenslocatie, vereiste machtigingen, licentie komt, pagina instellingen
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 6b0d8d9be0cc84e61a3228f79fc14f1bfc9f8a83
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198837"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-threat-protection"></a>Veelgestelde vragen over het inschakelen van Microsoft Threat Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft Threat Protection

Lees de antwoorden op de meest gestelde vragen over het inschakelen van [Microsoft Threat Protection](microsoft-threat-protection.md), waaronder vereiste licenties en machtigingen, het implementeren van ondersteuningsservices en de eerste instellingen.

[Zie Microsoft Threat Protection inschakelen](mtp-enable.md)voor instructies over het inschakelen van de service.

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-threat-protection"></a>Ik heb geen Microsoft 365 E5-licentie. Kan ik nog steeds Microsoft Threat Protection gebruiken?

Klanten met de volgende non-E5-licenties kunnen Microsoft Threat Protection gebruiken:

- Microsoft Defender Advanced Threat Protection
- Azure Advanced Threat Protection
- Microsoft Cloud App Security
- Office 365 Advanced Threat Protection (abonnement 2)
 
Voor een volledige lijst met ondersteunde licenties [raadpleegt u de licentievereisten](prerequisites.md#licensing-requirements).

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-threat-protection"></a>Moet ik alles installeren of implementeren om Microsoft Threat Protection te kunnen gebruiken?

Nee, Microsoft Threat Protection kan gegevens van Microsoft 365-beveiligingsservices die u al hebt geïmplementeerd, samenvoegen. Wanneer u de functie hebt ingeschakeld, kunnen incident-, automatiserings-en jacht-ervaringen werken binnen het bereik van de gedistribueerde producten. Als geen van deze producten op de juiste manier is geïmplementeerd, worden geen gegevens in Microsoft Threat Protection weergegeven en kan geen actie ondernemen.

Om uw ervaringen met Microsoft Threat Protection te optimaliseren, wordt u aangeraden *alle* ondersteunde [Microsoft 365-beveiligingsproducten en-services](deploy-supported-services.md)te implementeren.

## <a name="where-does-microsoft-threat-protection-process-and-store-my-data"></a>Waar kan ik Microsoft Threat Protection processen en mijn gegevens opslaan?
Microsoft Threat Protection selecteert automatisch een optimale locatie voor het datacenter waar geconsolideerde gegevens worden verwerkt en opgeslagen. Als u Microsoft Defender ATP hebt, wordt de locatie geselecteerd die wordt gebruikt in Microsoft Defender ATP.

>[!NOTE]
>In Microsoft Defender ATP worden automatisch de voorzieningen van de Europese Unie (EU)-datacenters automatisch ingericht wanneer ze zijn ingeschakeld via Azure Beveiligingscentrum. Microsoft Threat Protection wordt automatisch ingericht in hetzelfde EU-datacenter voor klanten die op deze manier Microsoft Defender ATP hebben ingericht. 

De locatie van het datacenter wordt weergegeven vóór en na het inrichten van de service op de pagina instellingen voor Microsoft Threat Protection (**instellingen > Microsoft Threat Protection**). Als u liever een andere locatie voor het datacenter wilt gebruiken, selecteert u **hulp nodig?** in het microsoft 365-Beveiligingscentrum voor contact opnemen met Microsoft ondersteuning.

## <a name="where-can-i-access-microsoft-threat-protection"></a>Waar kan ik Microsoft Threat Protection openen?

Microsoft Threat Protection is beschikbaar in het Beveiligingscentrum van Microsoft 365. Blader naar de URL om naar het Beveiligingscentrum te gaan [https://security.microsoft.com](https://security.microsoft.com) .

##  <a name="what-permissions-do-i-need-to-access-microsoft-threat-protection-in-microsoft-365-security-center"></a>Welke machtigingen heb ik nodig voor het openen van Microsoft Threat Protection in Microsoft 365 Beveiligingscentrum?

Accounts die zijn toegewezen aan de volgende Azure Active Directory (AD) rollen hebben toegang tot de functies en gegevens van Microsoft Threat Protection.

- Globale beheerder
- Beveiligingsbeheerder
- Beveiligings operator
- Algemene lezer
- Beveiligings lezer

>[!NOTE]
>De instellingen voor toegangsbeheer op basis van rollen in Microsoft Defender ATP beïnvloeden de toegang tot gegevens. Lees voor meer informatie over [het beheren van de toegang tot Microsoft Threat Protection](mtp-permissions.md).

## <a name="what-time-zone-does-microsoft-threat-protection-default-to"></a>Voor welke tijdzone is Microsoft Threat Protection standaard?
Standaard worden in Microsoft Bedreigingsbeveiliging tijds informatie weergegeven in de UTC-tijdzone. U kunt deze instelling wijzigen om uw lokale tijdzone te gebruiken. [Meer informatie over het instellen van de tijdzone](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-threat-protection-feature-and-ui-updates"></a>Hoe kan ik meer te weten komen over de nieuwe functies en UI-updates voor Microsoft Threat Protection?

Microsoft biedt regelmatig informatie over de verschillende kanalen, waaronder:

- Het [berichtencentrum](../../admin/manage/message-center.md) in het microsoft 365-Beheercentrum
- Blogposts in de [Microsoft 365-beveiligings & compliance tech Community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

U krijgt de nieuwste, algemeen beschikbare [functies door Voorbeeldfuncties](preview.md)in te schakelen.

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Is Microsoft Threat Protection beschikbaar voor US Government Community Cloud (GCC) of GCC High?
Dit is momenteel niet beschikbaar.

## <a name="related-topics"></a>Verwante onderwerpen

- [Overzicht van Microsoft Threat Protection](microsoft-threat-protection.md)
- [Schakel Microsoft Threat Protection in](mtp-enable.md).
- [Licentievereisten en andere vereisten](prerequisites.md)
- [Ondersteunde services implementeren](deploy-supported-services.md)
- [Voorbeeldfuncties inschakelen](preview.md)
