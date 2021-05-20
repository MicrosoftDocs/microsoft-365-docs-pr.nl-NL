---
title: Veelgestelde vragen bij het inschakelen van Microsoft 365 Defender
description: Krijg antwoord op de meest gestelde vragen over licenties, machtigingen, initiële instellingen en andere producten en services met betrekking tot het inschakelen van Microsoft 365 Defender
keywords: veelgestelde vragen, VEELGESTELDE VRAGEN, GCC, aan de slag, Microsoft 365 Defender inschakelen, Microsoft 365 Defender, M365, beveiliging, gegevenslocatie, vereiste machtigingen, geschiktheid voor licenties, instellingenpagina
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
ms.openlocfilehash: 008e3cc6ee65597a032aa932b74a64ac591927f2
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572763"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>Veelgestelde vragen bij het inschakelen van Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

Lees antwoorden op de meest gestelde vragen over het inschakelen [van Microsoft 365 Defender,](microsoft-365-defender.md)inclusief vereiste licenties en machtigingen, het implementeren van ondersteuningsservices en initiële instellingen.

[Lees Microsoft 365 Defender inschakelen](m365d-enable.md)voor instructies over het inschakelen van de service.

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>Ik heb geen Microsoft 365 E5 rijbewijs. Kan ik Microsoft 365 Defender nog gebruiken?

Klanten met de volgende niet-E5-licenties kunnen Microsoft 365 Defender gebruiken:

- Microsoft Defender voor Eindpunt
- Microsoft Defender for Identity
- Microsoft Cloud App Security
- Verdediger voor Office 365 (Plan 2)
 
[Lees de licentievereisten](prerequisites.md#licensing-requirements)voor een volledige lijst met ondersteunde licenties.

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>Moet ik iets installeren of implementeren om Microsoft 365 Defender te kunnen gebruiken?

Nee, Microsoft 365 Defender consolideert gegevens van Microsoft 365 beveiligingsservices die u al hebt geïmplementeerd. Zodra u het inschakelt, beginnen incident-, automatiserings- en jachtervaringen te werken binnen het bereik van de geïmplementeerde producten. Als geen van deze producten correct is geïmplementeerd, geeft Microsoft 365 Defender geen gegevens weer en kan deze geen actie ondernemen.

Om uw Microsoft 365 Defender-ervaringen te optimaliseren, raden we u aan *alle* ondersteunde [Microsoft 365 beveiligingsproducten en -services](deploy-supported-services.md)te implementeren.

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Waar verwerkt en bewaart Microsoft 365 Defender mijn gegevens?
Microsoft 365 Defender selecteert automatisch een optimale locatie voor het datacenter waar geconsolideerde gegevens worden verwerkt en opgeslagen. Als u Microsoft Defender voor Eindpunt hebt, wordt dezelfde locatie geselecteerd die door Defender voor Eindpunt wordt gebruikt.

>[!NOTE]
>Microsoft Defender for Endpoint voorziet automatisch in datacenters van de Europese Unie (EU) wanneer deze zijn ingeschakeld via Azure Defender. Microsoft 365 Defender wordt automatisch in hetzelfde EU-datacenter ingericht voor klanten die Microsoft Defender op deze manier hebben ingericht voor Endpoint. 

De locatie van het datacenter wordt weergegeven voor en nadat de service is ingericht op de instellingenpagina voor Microsoft 365 Defender (**Instellingen > Microsoft 365 Defender**). Als u liever een andere datacenterlocatie gebruikt, selecteert u **Hulp nodig?** in het beveiligingscentrum Microsoft 365 om contact op te nemen met Microsoft-ondersteuning.

## <a name="where-can-i-access-microsoft-365-defender"></a>Waar kan ik Microsoft 365 Defender bereiken?

Microsoft 365 Defender is beschikbaar in Microsoft 365 beveiligingscentrum. Als u naar het beveiligingscentrum wilt gaan, bladert u naar de URL [https://security.microsoft.com](https://security.microsoft.com) .

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>Welke machtigingen heb ik nodig om toegang te krijgen tot Microsoft 365 Defender in Microsoft 365 beveiligingscentrum?

Accounts waaraan de volgende azure AD-rollen (Azure Active Directory) zijn toegewezen, hebben toegang tot Microsoft 365 Defender-functionaliteit en -gegevens:

- Globale beheerder
- Beveiligingsbeheerder
- Beveiligingsoperator
- Algemene lezer
- Beveiligingslezer

>[!NOTE]
>Op rollen gebaseerde instellingen voor toegangsbeheer in Microsoft Defender voor eindpunt hebben invloed op de toegang tot gegevens. Lees meer over [het beheren van de toegang tot Microsoft 365 Defender](m365d-permissions.md).

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>In welke tijdzone wordt Microsoft 365 Defender standaard ingesteld?
Standaard geeft Microsoft 365 Defender tijdgegevens weer in de tijdzone UTC. U kunt deze instelling wijzigen om uw lokale tijdzone te gebruiken. [Meer informatie over het instellen van de tijdzone](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>Hoe kan ik meer te weten komen over nieuwe Microsoft 365 Defender-functie en UI-updates?

Microsoft verstrekt regelmatig informatie via de verschillende kanalen, waaronder:

- Het [berichtencentrum](../../admin/manage/message-center.md) in Microsoft 365-beheercentrum
- Blogposts in de [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

Krijg de nieuwste openbaar beschikbare ervaringen door [preview-functies](preview.md)in te schakelen .

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Is Microsoft 365 Defender beschikbaar voor Amerikaanse Government Community Cloud (GCC) of GCC High?
Op dit moment is het niet beschikbaar.

## <a name="related-topics"></a>Verwante onderwerpen

- [Microsoft 365 Defender overzicht](microsoft-365-defender.md)
- [Schakel Microsoft 365 Defender in.](m365d-enable.md)
- [Licentievereisten en andere vereisten](prerequisites.md)
- [Ondersteunde services implementeren](deploy-supported-services.md)
- [Preview-functies inschakelen](preview.md)
