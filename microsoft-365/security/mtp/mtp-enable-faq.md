---
title: Veelgestelde vragen wanneer u Microsoft 365 Defender inschakelt
description: Hier vindt u antwoorden op de meest gestelde vragen over licenties, machtigingen, initiële instellingen en andere producten en services met betrekking tot het inschakelen van Microsoft 365 Defender
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
ms.openlocfilehash: bfb58cb043f2bc641245814c41e389ddcdbfdefa
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842414"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>Veelgestelde vragen wanneer u Microsoft 365 Defender inschakelt

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

Lees de antwoorden op de meest gestelde vragen over het inschakelen van [Microsoft 365 Defender](microsoft-threat-protection.md), waaronder vereiste licenties en machtigingen, het implementeren van ondersteuningsservices en de eerste instellingen.

[Zie Microsoft 365 Defender inschakelen](mtp-enable.md)voor instructies over het inschakelen van de service.

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>Ik heb geen Microsoft 365 E5-licentie. Kan ik nog steeds Microsoft 365 Defender gebruiken?

Voor klanten met de volgende niet-E5-licenties kan Microsoft 365 Defender worden gebruikt:

- Microsoft Defender voor eindpunt
- Microsoft Defender voor identiteit
- Microsoft Cloud App Security
- Defender voor Office 365 (abonnement 2)
 
Voor een volledige lijst met ondersteunde licenties [raadpleegt u de licentievereisten](prerequisites.md#licensing-requirements).

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>Moet ik alles installeren of implementeren om te beginnen met Microsoft 365 Defender?

Nee, Microsoft 365 Defender bevat gegevens van Microsoft 365-beveiligingsservices die u al hebt geïmplementeerd. Wanneer u de functie hebt ingeschakeld, kunnen incident-, automatiserings-en jacht-ervaringen werken binnen het bereik van de gedistribueerde producten. Als geen van deze producten op de juiste manier is geïmplementeerd, worden geen gegevens in Microsoft 365 Defender weergegeven en kan geen actie ondernemen.

Voor het optimaliseren van uw Microsoft 365-ervaring voor Microsoft kunt u het beste *alle* ondersteunde [beveiligingsproducten en-services van Microsoft 365](deploy-supported-services.md)implementeren.

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Waar kan ik mijn gegevens in Microsoft 365 Defender verwerken en opslaan?
Microsoft 365 Defender selecteert automatisch een optimale locatie voor het datacenter waar geconsolideerde gegevens worden verwerkt en opgeslagen. Als u Microsoft Defender voor eindpunten hebt, wordt de gebruikte locatie voor eindpunten van Defender geselecteerd.

>[!NOTE]
>Microsoft Defender voor eindpunten in de Europese Unie (EU)-datacenters worden automatisch aangerekend wanneer Azure Defender * wordt ingeschakeld. Microsoft 365 Defender wordt automatisch ingericht in hetzelfde EU-datacenter voor klanten die Microsoft Defender voor eindpunten op deze manier hebben ingericht. 

De locatie van het datacenter wordt weergegeven vóór en nadat de service is ingericht op de pagina instellingen voor Microsoft 365 Defender (de **instellingen > Microsoft 365 Defender** ). Als u liever een andere locatie voor het datacenter wilt gebruiken, selecteert u **hulp nodig?** in het microsoft 365-Beveiligingscentrum voor contact opnemen met Microsoft ondersteuning.

## <a name="where-can-i-access-microsoft-365-defender"></a>Waar kan ik Microsoft 365 Defender openen?

Microsoft 365 Defender is beschikbaar in het Beveiligingscentrum van Microsoft 365. Blader naar de URL om naar het Beveiligingscentrum te gaan [https://security.microsoft.com](https://security.microsoft.com) .

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>Welke machtigingen heb ik nodig voor het openen van Microsoft 365 Defender in Microsoft 365 Beveiligingscentrum?

Accounts die zijn toegewezen aan de volgende Azure Active Directory (AD) rollen, hebben toegang tot de functies en gegevens van Microsoft 365 Defender:

- Globale beheerder
- Beveiligingsbeheerder
- Beveiligings operator
- Algemene lezer
- Beveiligings lezer

>[!NOTE]
>Instellingen voor toegangsbeheer op basis van rollen in Microsoft Defender voor eindpunten hebben invloed op toegang tot gegevens. Lees voor meer informatie over [het beheren van de toegang tot Microsoft 365 Defender](mtp-permissions.md).

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>Op welke tijdzone is standaard Microsoft 365 Defender standaard?
In Microsoft 365 Defender worden tijdgegevens standaard weergegeven in de UTC-tijdzone. U kunt deze instelling wijzigen om uw lokale tijdzone te gebruiken. [Meer informatie over het instellen van de tijdzone](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>Hoe kan ik meer informatie vinden over de nieuwe functies en UI-updates voor Microsoft 365 Defender?

Microsoft biedt regelmatig informatie over de verschillende kanalen, waaronder:

- Het [berichtencentrum](../../admin/manage/message-center.md) in het microsoft 365-Beheercentrum
- Blogposts in de [Microsoft 365-beveiligings & compliance tech Community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

U krijgt de nieuwste, algemeen beschikbare [functies door Voorbeeldfuncties](preview.md)in te schakelen.

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Is Microsoft 365 Defender beschikbaar voor US Government Community Cloud (GCC) of GCC High?
Dit is momenteel niet beschikbaar.

## <a name="related-topics"></a>Verwante onderwerpen

- [Overzicht van Microsoft 365 Defender](microsoft-threat-protection.md)
- [Schakel Microsoft 365 Defender in](mtp-enable.md).
- [Licentievereisten en andere vereisten](prerequisites.md)
- [Ondersteunde services implementeren](deploy-supported-services.md)
- [Preview-functies inschakelen](preview.md)
