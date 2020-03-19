---
title: 'Stap 7: Privileged Access Management configureren voor Office 365'
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: Beheer van bevoegde toegang voor Office 365 begrijpen en configureren.
ms.openlocfilehash: f29b1e0934a4b9a6d4e3347584f39423d446ed58
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42808416"
---
# <a name="step-7-configure-privileged-access-management-for-office-365"></a>Stap 7: Privileged Access Management configureren voor Office 365

*Deze stap is optioneel en geldt alleen voor de E5- en Advanced Compliance-versies van Microsoft 365 Enterprise*

![Fase 6: Informatiebescherming](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Privileged access management is ingeschakeld door beleid te configureren dat just-in-time toegang opgeeft voor taakgebaseerde activiteiten in uw Office 365-tenant. Het kan uw organisatie beschermen tegen inbreuken die bestaande bevoegde beheerdersaccounts kunnen gebruiken met permanente toegang tot gevoelige gegevens of toegang tot kritieke configuratie-instellingen. U bijvoorbeeld een beleid voor beheer van privileged access configureren waarvoor expliciete goedkeuring vereist is voor toegang tot en wijziging van de instellingen van het organalaatpostvak in uw Office 365-tenant.

In deze stap schakelt u privileged access management in uw Office 365-tenant in en configureert u beleid voor bevoegde toegang dat extra beveiliging biedt voor taakgebaseerde toegang tot Office 365-gegevens en configuratie-instellingen voor uw organisatie. Er zijn drie basisstappen om aan de slag te gaan met bevoorrechte toegang in uw Office 365-organisatie:
- De groep van een goedkeurder maken
- Bevoorrechte toegang inschakelen
- Goedkeuringsbeleid maken

Een geconfigureerd, geprivilegieerd toegangsbeheer stelt uw organisatie in staat om te werken met nul permanente bevoegdheden en biedt een laag van verdediging tegen kwetsbaarheden die ontstaan als gevolg van dergelijke permanente administratieve toegang. Voor bevoorrechte toegang zijn goedkeuringen vereist voor het uitvoeren van een taak waarvoor een bijbehorend goedkeuringsbeleid is gedefinieerd. Gebruikers die taken moeten uitvoeren die zijn opgenomen in het goedkeuringsbeleid, moeten toegangsgoedkeuring aanvragen en krijgen om machtigingen te hebben die nodig zijn om taken uit te voeren die in het beleid zijn gedefinieerd.

Zie Het onderwerp Privileged Access Management [configureren in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) als u office 365-toegangsbeheer wilt inschakelen.

Zie het onderwerp [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) voor meer informatie.


|||
|:-------|:-----|
|![Lab-handleidingen testen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  Zie de Test Lab Guide voor [privileged access management](privileged-access-microsoft-365-enterprise-dev-test-environment.md)voor deze configuratie in een testlabomgeving. |
|||

Zie als tussencontrole de [exitcriteria](infoprotect-exit-criteria.md#crit-infoprotect-step7) die overeenkomen met deze stap.

## <a name="next-step"></a>Volgende stap

[Criteria voor het verlaten van informatiebeschermingsinfrastructuur](infoprotect-exit-criteria.md)
