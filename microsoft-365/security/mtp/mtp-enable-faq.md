---
title: Veelgestelde vragen bij het inschakelen van Microsoft Threat Protection
description: Antwoorden krijgen op de meest gestelde vragen over licenties, machtigingen, initiële instellingen en andere producten en services met betrekking tot het inschakelen van Microsoft Threat Protection
keywords: veelgestelde vragen, FAQ, GCC, aan de slag, inschakelen MTP, Microsoft Threat Protection, M365, beveiliging, gegevens locatie, vereiste machtigingen, licentie geschiktheid, instellingen pagina
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
ms.openlocfilehash: 9dcfeb5616afc8953e862d6d1a542d694582b157
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/23/2020
ms.locfileid: "44845062"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-threat-protection"></a>Veelgestelde vragen bij het inschakelen van Microsoft Threat Protection

**Van toepassing op:**
- Microsoft Threat Protection

Lees antwoorden op de meest gestelde vragen over het inschakelen van [Microsoft Threat Protection](microsoft-threat-protection.md), inclusief vereiste licenties en machtigingen, het implementeren van ondersteuningsservices en de eerste instellingen.

[Lees Microsoft Threat Protection inschakelen](mtp-enable.md)voor instructies voor het inschakelen van de service.

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-threat-protection"></a>Ik heb geen Microsoft 365 E5 licentie. Kan ik nog steeds Microsoft Threat Protection gebruiken?

Klanten met de volgende niet-E5-licenties kunnen Microsoft Threat Protection gebruiken:

- Microsoft Defender Advanced Threat Protection
- Azure Advanced Threat Protection
- Microsoft Cloud App Security
- Geavanceerde bedreigingsbeveiliging van Office 365 (abonnement 2)
 
[Lees de licentievereisten](prerequisites.md#licensing-requirements)voor een volledige lijst met ondersteunde licenties.

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-threat-protection"></a>Moet ik iets installeren of implementeren om Microsoft Threat Protection te kunnen gebruiken?

Nee, Microsoft Threat Protection consolideert gegevens van Microsoft 365-beveiligingsservices die u al hebt geïmplementeerd. Zodra u het inschakelt, zullen incident-, automatiserings- en jachtervaringen gaan werken binnen het bereik van de geïmplementeerde producten. Als geen van deze producten correct is geïmplementeerd, geeft Microsoft Threat Protection geen gegevens weer en kan er geen actie worden ondernomen.

Om uw Microsoft Threat Protection-ervaringen te optimaliseren, raden we u aan *alle* ondersteunde [Microsoft 365-beveiligingsproducten en -services](deploy-supported-services.md)te implementeren.

## <a name="where-does-microsoft-threat-protection-process-and-store-my-data"></a>Waar verwerkt en slaat Microsoft Threat Protection mijn gegevens op?
Microsoft Threat Protection selecteert automatisch een optimale locatie voor het datacenter waar geconsolideerde gegevens worden verwerkt en opgeslagen. Als u Microsoft Defender ATP hebt, selecteert u dezelfde locatie die wordt gebruikt door Microsoft Defender ATP.

>[!NOTE]
>Microsoft Defender ATP-bepalingen in datacenters van de Europese Unie (EU) automatisch worden ingeschakeld via Azure Security Center. Microsoft Threat Protection voorziet automatisch in hetzelfde EU-datacenter voor klanten die Microsoft Defender ATP op deze manier hebben ingericht. 

De locatie van het datacenter wordt voor en na de service weergegeven op de instellingenpagina voor Microsoft Threat Protection **(Instellingen > Microsoft Threat Protection**). Als u liever een andere locatie van het datacenter gebruikt, selecteert u **Hulp nodig?**

## <a name="where-can-i-access-microsoft-threat-protection"></a>Waar heb ik toegang tot Microsoft Threat Protection?

Microsoft Threat Protection is beschikbaar in het Microsoft 365-beveiligingscentrum. Als u naar het beveiligingscentrum wilt gaan, bladert u naar de URL [https://security.microsoft.com](https://security.microsoft.com) .

##  <a name="what-permissions-do-i-need-to-access-microsoft-threat-protection-in-microsoft-365-security-center"></a>Welke machtigingen heb ik nodig om toegang te krijgen tot Microsoft Threat Protection in het Microsoft 365-beveiligingscentrum?

Accounts die de volgende Azure Active Directory(AD)-rollen hebben toegewezen, hebben toegang tot de functionaliteit en gegevens van Microsoft Threat Protection:

- Globale beheerder
- Beveiligingsbeheerder
- Beveiligingsoperator
- Global Reader
- Beveiligingslezer

>[!NOTE]
>Op rollen gebaseerde toegangscontrole-instellingen in Microsoft Defender ATP beïnvloeden de toegang tot gegevens. Lees voor meer informatie over [het beheren van de toegang tot Microsoft Threat Protection.](mtp-permissions.md)

## <a name="what-time-zone-does-microsoft-threat-protection-default-to"></a>Tot welke tijdzone wordt Microsoft Threat Protection standaard gebruikt?
Microsoft Threat Protection geeft standaard tijdsinformatie weer in de UTC-tijdzone. U deze instelling wijzigen om uw lokale tijdzone te gebruiken. [Meer informatie over het instellen van de tijdzone](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-threat-protection-feature-and-ui-updates"></a>Hoe kom ik meer te weten over de nieuwe Microsoft Threat Protection-functie en UI-updates?

Microsoft verstrekt regelmatig informatie via de verschillende kanalen, waaronder:

- Het [berichtencentrum](../../admin/manage/message-center.md) in het Microsoft 365-beheercentrum
- Blogposts in de [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

Ontvang de nieuwste openbaar beschikbare ervaringen door [preview-functies](preview.md)in te schakelen.

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Is Microsoft Threat Protection beschikbaar voor GCC of GCC High van de Amerikaanse overheid?
Op dit moment is het niet beschikbaar.

## <a name="related-topics"></a>Verwante onderwerpen

- [Overzicht van Microsoft Threat Protection](microsoft-threat-protection.md)
- [Schakel Microsoft Threat Protection in](mtp-enable.md).
- [Licentievereisten en andere voorwaarden](prerequisites.md)
- [Ondersteunde services implementeren](deploy-supported-services.md)
- [Voorbeeldfuncties inschakelen](preview.md)