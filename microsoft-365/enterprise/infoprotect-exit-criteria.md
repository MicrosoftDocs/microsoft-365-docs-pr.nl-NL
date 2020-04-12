---
title: Uitgangscriteria voor de infrastructuur voor gegevensbeveiliging
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Bekijk de criteria voor op gegevensbeveiliging gebaseerde services en infrastructuur om ervoor te zorgen dat uw configuratie voldoet aan de vereisten van Microsoft 365 Enterprise.
ms.openlocfilehash: 28eff02ea870dcfca7e2e32580ed6a3a9e8a9484
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42806618"
---
# <a name="information-protection-infrastructure-exit-criteria"></a>Uitgangscriteria voor de infrastructuur voor gegevensbeveiliging

![Fase 6: gegevensbescherming](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Zorg ervoor dat de op gegevensbeveiliging gebaseerde infrastructuur aan de volgende vereiste criteria voldoet en dat u de optionele criteria hebt overwogen.

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a>Vereist: de beveiligings- en gegevensbeschermingsniveaus voor uw organisatie zijn gedefinieerd

U hebt de beveiligingsniveaus die uw organisatie nodig heeft gepland en vastgesteld. Deze niveaus bepalen een minimaal beveiligingsniveau en aanvullende niveaus voor steeds gevoeliger wordende gegevens en de bijbehorende gegevensbeveiliging.

U gebruikt minimaal drie beveiligingsniveaus:

- Basislijn
- Gevoelig
- Sterk gereglementeerd

Via [Stap 1](infoprotect-define-sec-infoprotect-levels.md) kunt u zo nodig aan deze vereisten voldoen. 

<a name="crit-infoprotect-step3"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a>Vereist: verbeterde beveiliging voor Microsoft 365 is geconfigureerd

U hebt de volgende instellingen voor [Office 365 verhoogde beveiliging](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security) geconfigureerd:

- Beleid voor bedreigingsbeheer in het Microsoft 365-beveiligingscentrum
- Aanvullende, tenant-brede Exchange Online-instellingen
- Tenant-breed deelbeleid in SharePoint Online-beheercentrum
- Instellingen in Azure Active Directory (Azure AD)

U hebt ook [Office 365 Advanced Threat Protection (ATP) voor bestanden in SharePoint, OneDrive en Microsoft Teams ingeschakeld](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).

Via [Stap 3](infoprotect-configure-increased-security-office-365.md) kunt u zo nodig aan deze vereisten voldoen. 

<a name="crit-infoprotect-step2"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a>Optioneel: classificatie wordt in uw gehele omgeving geconfigureerd

U hebt samen met uw juridische en compliance-teams een geschikt classificatie- en labelsysteem ontwikkeld voor het beheer van gegevens en het beveiligingsbeleid van uw organisatie. 

Dit beleid komt overeen met de configuratie en implementatie van:

- Gevoelige gegevenstypen
- Retentielabels
- Gevoeligheidslabels
- Azure Information Protection-labels

Via [Stap 2](infoprotect-configure-classification.md) kunt u zo nodig aan deze vereisten voldoen. 


<a name="crit-infoprotect-step4"></a>
## <a name="optional-windows-information-protection-is-deployed-across-your-environment"></a>Optioneel: Windows-gegevensbescherming wordt in uw volledige omgeving geïmplementeerd

Uw Windows 10 Enterprise-apparaten hebben een Intune-beleid geïmplementeerd en toegepast dat bepaalt:

- Welke apps moeten worden beveiligd.
- Het niveau van de beveiliging.
- Waar de beveiliging wordt uitgebreid.

Via [Stap 4](infoprotect-deploy-windows-information-protection.md) kunt u zo nodig aan deze vereisten voldoen. 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-office-365-data-loss-prevention-dlp-is-deployed"></a>Optioneel: Office 365-preventie van gegevensverlies (DLP) wordt geïmplementeerd

U hebt de set DLP-beleidsregels, met locaties en regels met voorwaarden en acties, die uw organisatie nodig heeft om klant- en andere soorten privégegevens te beschermen en te voldoen aan branche- en regionale voorschriften en vereisten, geanalyseerd, getest en vervolgens uitgerold.

Uw medewerkers voor compliance en beveiliging van gegevens gebruiken het Office 365-beveiligings- en compliance-dashboard om DLP-incidenten te bewaken.

Via [Stap 5](infoprotect-data-loss-prevention.md) kunt u zo nodig aan deze vereisten voldoen. 

<a name="crit-infoprotect-step6"></a>
## <a name="optional-email-encryption-is-configured"></a>Optioneel: e-mailversleuteling wordt geconfigureerd

U hebt voor uw organisatie de volgende e-mailversleuteling geconfigureerd:

|||
|:-------|:-----|
| **Versleutelingsmethode** | **Voor verzonden e-mail** |
| [Office 365-berichtversleuteling (OME)](https://docs.microsoft.com/Office365/SecurityCompliance/ome)  | Buiten uw organisatie met versleuteling |
| [IRM (Information Rights Management)](https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online) | Met zowel versleuteling als machtigingen |
| [S/MIME (Secure/Multipurpose Internet Mail Extensions)](https://docs.microsoft.com/Exchange/policy-and-compliance/smime) | Waarbij zowel versleuteling als digitale handtekeningen openbare sleutelcryptografie gebruiken |
|||

Via [Stap 6](infoprotect-email-encryption.md) kunt u zo nodig aan deze vereisten voldoen.

<a name="crit-infoprotect-step7"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a>Optioneel: configureer bevoegd toegangsbeheer in Office 365

U hebt de informatie in [Privileged Access Management (bevoegd toegangsbeheer) configureren in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) gebruikt om Privileged Access Management in te schakelen en een of meer beleidsregels voor geprivilegieerde toegang in uw organisatie te maken. U hebt deze beleidsregels geconfigureerd en just-in-time-toegang is ingeschakeld voor toegang tot gevoelige gegevens of kritieke configuratie-instellingen.

Via [Stap 7](infoprotect-configure-privileged-access-management.md) kunt u zo nodig aan deze vereisten voldoen. 

## <a name="results-and-next-steps"></a>Resultaten en volgende stappen

De infrastructuur voor informatiebescherming voor Microsoft 365 Enterprise gebruikt gedefinieerde beveiligingsniveaus, verhoogde beveiliging voor Office 365, classificatie met gevoelige gegevenstypen en labels, Windows-gegevensbescherming, preventie van gegevensverlies, e-mail versleuteling en beleid voor geprivilegieerde toegang.

Als u de volledige implementatie van Microsoft 365 Enterprise hebt gevolgd, bent u nu klaar om uw [workloads en scenario's](deploy-workloads.md) te laten profiteren van alle functies en configuraties van uw basisinfrastructuur.
