---
title: Veelgestelde vragen bij het in- en Microsoft 365 Defender
description: Antwoorden krijgen op de meestgestelde vragen over licenties, machtigingen, eerste instellingen en andere producten en services met betrekking tot het inschakelen van Microsoft 365 Defender
keywords: veelgestelde vragen, veelgestelde vragen, GCC, aan de slag, Microsoft 365 Defender, Microsoft 365 Defender, M365, beveiliging, gegevenslocatie, vereiste machtigingen, geschiktheid van licenties, instellingenpagina
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
ms.openlocfilehash: 1ba049e9fe608ba8bd559180c5a30060b10ee9e0
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53285983"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>Veelgestelde vragen bij het in- en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

Lees antwoorden op de meestgestelde vragen over het in- en [Microsoft 365 Defender,](microsoft-365-defender.md)inclusief vereiste licenties en machtigingen, het implementeren van ondersteuningsservices en eerste instellingen.

Lees In-Microsoft 365 Defender voor instructies over het in- en [Microsoft 365 Defender.](m365d-enable.md)

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>Ik heb geen Microsoft 365 E5 licentie. Kan ik nog steeds Microsoft 365 Defender?

Klanten met de volgende niet-E5-licenties kunnen Microsoft 365 Defender:

- Microsoft Defender voor Eindpunt
- Microsoft Defender for Identity
- Microsoft Cloud App Security
- Defender voor Office 365 (Plan 2)

Lees de licentievereisten voor een volledige lijst met [ondersteunde licenties.](prerequisites.md#licensing-requirements)

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>Moet ik iets installeren of implementeren om aan de slag te gaan met Microsoft 365 Defender?

Nee, Microsoft 365 Defender gegevens uit Microsoft 365 beveiligingsservices die u al hebt geïmplementeerd. Wanneer u deze in hebt ingeschakeld, gaan incident-, automatiserings- en zoekervaringen werken binnen het bereik van de geïmplementeerde producten. Als geen van deze producten correct wordt geïmplementeerd, worden Microsoft 365 Defender geen gegevens weergegeven en kan er geen actie worden ondernomen.

Als u uw Microsoft 365 Defender wilt optimaliseren,  raden we u aan alle ondersteunde beveiligingsproducten en [-services Microsoft 365 implementeren.](deploy-supported-services.md)

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Waar worden Microsoft 365 Defender gegevens verwerkt en opgeslagen?

Microsoft 365 Defender selecteert automatisch een optimale locatie voor het datacenter waar samengevoegde gegevens worden verwerkt en opgeslagen. Als u Microsoft Defender voor Eindpunt hebt, wordt dezelfde locatie geselecteerd die door Defender voor Eindpunt wordt gebruikt.

>[!NOTE]
>Microsoft Defender voor Eindpunt biedt automatisch voorzieningen in datacenters van de Europese Unie (EU) wanneer deze zijn ingeschakeld via Azure Defender. Microsoft 365 Defender wordt automatisch ingericht in hetzelfde EU-datacenter voor klanten die Microsoft Defender op deze manier voor Eindpunt hebben ingericht.

De locatie van het datacenter wordt weergegeven vóór en nadat de service is ingericht op de instellingenpagina voor Microsoft 365 Defender (**Instellingen > Microsoft 365 Defender).** Als u liever een andere datacenterlocatie gebruikt, selecteert u **Hulp nodig?** in het Microsoft 365 beveiligingscentrum om contact op te nemen met microsoft-ondersteuning.

## <a name="where-can-i-access-microsoft-365-defender"></a>Waar kan ik toegang tot Microsoft 365 Defender?

Microsoft 365 Defender is beschikbaar in Microsoft 365 beveiligingscentrum. Als u naar het beveiligingscentrum wilt gaan, bladert u naar de <https://security.microsoft.com> URL.

## <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>Welke machtigingen heb ik nodig om toegang te krijgen tot Microsoft 365 Defender in Microsoft 365 beveiligingscentrum?

Accounts die aan de volgende Azure Active Directory (Azure AD) zijn toegewezen, hebben toegang tot Microsoft 365 Defender functionaliteit en gegevens:

- Globale beheerder
- Beveiligingsbeheerder
- Beveiligingsoperator
- Algemene lezer
- Beveiligingslezer

> [!NOTE]
> Instellingen voor toegangsbeheer op basis van rollen in Microsoft Defender voor eindpunten zijn van invloed op de toegang tot gegevens. Lees voor meer informatie over [het beheren van toegang tot Microsoft 365 Defender.](m365d-permissions.md)

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>In welke tijdzone Microsoft 365 Defender standaard ingesteld?

Standaard worden Microsoft 365 Defender tijdgegevens weergegeven in de UTC-tijdzone. U kunt deze instelling wijzigen om uw lokale tijdzone te gebruiken. [Meer informatie over het instellen van de tijdzone](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>Hoe kom ik meer te weten over Microsoft 365 Defender nieuwe functies en ui-updates?

Microsoft verstrekt regelmatig informatie via de verschillende kanalen, waaronder:

- Het [berichtencentrum](../../admin/manage/message-center.md) in Microsoft 365-beheercentrum
- Blogposts in de [Microsoft 365 beveiligings- & compliance-tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

Krijg de nieuwste openbaar beschikbare ervaringen door [preview-functies in te stellen.](preview.md)

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Is Microsoft 365 Defender beschikbaar voor Amerikaanse Government Community Cloud (GCC) of GCC High?

Op dit moment is deze niet beschikbaar.

## <a name="related-topics"></a>Gerelateerde onderwerpen

- [Microsoft 365 Defender overzicht](microsoft-365-defender.md)
- [Schakel de Microsoft 365 Defender.](m365d-enable.md)
- [Licentievereisten en andere vereisten](prerequisites.md)
- [Ondersteunde services implementeren](deploy-supported-services.md)
- [Preview-functies inschakelen](preview.md)
