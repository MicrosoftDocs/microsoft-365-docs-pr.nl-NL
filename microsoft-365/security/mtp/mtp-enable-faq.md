---
title: Veelgestelde vragen over het in- en uitschakelen van Microsoft 365 Defender
description: Antwoorden krijgen op de meest gestelde vragen over licenties, machtigingen, aanvankelijke instellingen en andere producten en services met betrekking tot het inschakelen van Microsoft 365 Defender
keywords: veelgestelde vragen, veelgestelde vragen, GCC, aan de slag, MTP inschakelen, Microsoft Threat Protection, M365, beveiliging, gegevenslocatie, vereiste machtigingen, geschiktheid voor licenties, instellingenpagina
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 2cb9aed070959644e3660188835386118d5f4d9b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930184"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>Veelgestelde vragen over het in- en uitschakelen van Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

Lees antwoorden op de meest gestelde vragen over het inleveren van [Microsoft 365 Defender,](microsoft-threat-protection.md)inclusief vereiste licenties en machtigingen, het implementeren van ondersteuningsservices en de eerste instellingen.

Lees Microsoft 365 Defender in turn on the [service (Microsoft 365 Defender in)](mtp-enable.md)voor instructies over het in- en in- en uit- van de service.

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>Ik heb geen Microsoft 365 E5-licentie. Kan ik Microsoft 365 Defender toch gebruiken?

Klanten met de volgende niet-E5-licenties kunnen Microsoft 365 Defender gebruiken:

- Microsoft Defender for Endpoint
- Microsoft Defender for Identity
- Microsoft Cloud App Security
- Defender voor Office 365 (abonnement 2)
 
Lees de licentievereisten voor een volledige lijst [met ondersteunde licenties.](prerequisites.md#licensing-requirements)

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>Moet ik iets installeren of implementeren om aan de slag te gaan met Microsoft 365 Defender?

Nee, Microsoft 365 Defender voegt gegevens samen uit Microsoft 365-beveiligingsservices die u al hebt geïmplementeerd. Wanneer u deze hebt ingeschakeld, zullen incidentele, automatiserings- en zoekervaringen binnen het bereik van de geïmplementeerde producten gaan werken. Als geen van deze producten correct zijn geïmplementeerd, wordt er door Microsoft 365 Defender geen gegevens weergegeven en kan er geen actie worden ondernomen.

Om uw ervaringen met Microsoft 365 Defender te optimaliseren, wordt u aangeraden alle *ondersteunde* beveiligingsproducten en -services van [Microsoft 365 te implementeren.](deploy-supported-services.md)

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Waar worden mijn gegevens verwerkt en opgeslagen door Microsoft 365 Defender?
Microsoft 365 Defender selecteert automatisch een optimale locatie voor het datacenter waar samengevoegde gegevens worden verwerkt en opgeslagen. Als u Microsoft Defender voor eindpunt hebt, wordt dezelfde locatie geselecteerd die ook door Defender voor het eindpunt wordt gebruikt.

>[!NOTE]
>Microsoft Defender voor eindpunt richt automatisch voorzieningen in datacenters van de Europese Unie (EU) indien ingeschakeld via Azure Defender. Microsoft 365 Defender wordt automatisch ingericht in hetzelfde EU-datacenter voor klanten die Op deze manier Microsoft Defender voor het eindpunt hebben ingericht. 

De locatie van het datacenter wordt weergegeven voor en nadat de service is ingericht op de instellingenpagina voor Microsoft 365 Defender (instellingen **> Microsoft 365 Defender).** Als u liever een andere locatie in het datacenter gebruikt, selecteert u Hulp **nodig?** In het Microsoft 365-beveiligingscentrum kunt u contact opnemen met de ondersteuning van Microsoft.

## <a name="where-can-i-access-microsoft-365-defender"></a>Waar kan ik Microsoft 365 Defender openen?

Microsoft 365 Defender is beschikbaar in het Microsoft 365-beveiligingscentrum. Blader naar de URL om naar het beveiligingscentrum te [https://security.microsoft.com](https://security.microsoft.com) gaan.

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>Welke machtigingen heb ik nodig voor toegang tot Microsoft 365 Defender in het Microsoft 365-beveiligingscentrum?

Accounts die zijn toegewezen aan de volgende Azure Active Directory (AD)-rollen, hebben toegang tot functionaliteit en gegevens van Microsoft 365 Defender:

- Globale beheerder
- Beveiligingsbeheerder
- Beveiligingsoperator
- Algemene lezer
- Beveiligingslezer

>[!NOTE]
>Instellingen voor toegangsbeheer op basis van rollen in Microsoft Defender for Endpoint zijn van invloed op toegang tot gegevens. Lees meer over het beheren [van de toegang tot Microsoft 365 Defender.](mtp-permissions.md)

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>In welke tijdzone is Microsoft 365 Defender standaard ingesteld?
Standaard geeft Microsoft 365 Defender tijdgegevens weer in de UTC-tijdzone. U kunt deze instelling wijzigen om uw lokale tijdzone te gebruiken. [Meer informatie over het instellen van de tijdzone](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>Hoe kom ik meer te weten over nieuwe Microsoft 365 Defender-functies en ui-updates?

Microsoft verstrekt regelmatig informatie via de verschillende kanalen, waaronder:

- Het [berichtencentrum](../../admin/manage/message-center.md) in het Microsoft 365-beheercentrum
- Blogposts in de Technische community voor naleving van [Microsoft 365 & beveiliging](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

Haal de nieuwste openbaar beschikbare ervaringen op door preview-functies [in te stellen.](preview.md)

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Is Microsoft 365 Defender beschikbaar voor US Government Community Cloud (GCC) of GCC High?
Deze is momenteel niet beschikbaar.

## <a name="related-topics"></a>Verwante onderwerpen

- [Overzicht van Microsoft 365 Defender](microsoft-threat-protection.md)
- [Schakel Microsoft 365 Defender in.](mtp-enable.md)
- [Licentievereisten en andere vereisten](prerequisites.md)
- [Ondersteunde services implementeren](deploy-supported-services.md)
- [Preview-functies inschakelen](preview.md)
