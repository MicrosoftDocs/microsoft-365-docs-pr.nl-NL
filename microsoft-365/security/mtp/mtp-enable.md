---
title: Microsoft 365 Defender inschakelen in het Microsoft 365 Beveiligingscentrum
description: Meer informatie over het inschakelen van Microsoft 365 Defender en het integreren van uw beveiligingsincident en-antwoord.
keywords: aan de slag, MTP, Microsoft Threat Protection, M365, beveiliging, gegevenslocatie, vereiste machtigingen, licentie komt, pagina instellingen weergeven
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
ms.openlocfilehash: c5b8cae9e4eabcb2b3c6a7eb76971784193a221d
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920500"
---
# <a name="turn-on-microsoft-365-defender"></a>Microsoft 365 Defender inschakelen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-threat-protection.md) verenigt uw incident-antwoord proces door de belangrijkste mogelijkheden van Microsoft Defender for endpoints te integreren, Microsoft Defender for Office 365, Microsoft Cloud app Security en Microsoft Defender for Identity. Deze geïntegreerde ervaring voegt krachtige functies toe die u kunt gebruiken in het Microsoft 365-Beveiligingscentrum.

Microsoft 365 Defender wordt automatisch ingeschakeld wanneer klanten in aanmerking komen met de vereiste machtigingen naar Microsoft 365 Beveiligingscentrum. In dit artikel vindt u meer informatie over diverse vereisten en hoe Microsoft 365 Defender wordt ingericht.

## <a name="check-license-eligibility-and-required-permissions"></a>Geschiktheid voor de licentie en de vereiste machtigingen controleren
Met een licentie voor een Microsoft 365-beveiligings product hebt u algemene informatie over het gebruik van Microsoft 365 Defender in Microsoft 365 Beveiligingscentrum zonder extra licentiekosten. U wordt aangeraden een Microsoft 365 E5-, E5-beveiligings licentie, A5, of A5-beveiligings licentie of een geldige combinatie van licenties te verkrijgen die toegang biedt tot alle ondersteunde services.

[Lees de licentievereisten](prerequisites.md#licensing-requirements)voor uitgebreide licentiegegevens.

### <a name="check-your-role"></a>Uw rol controleren
U moet een **globale beheerder** of een **beveiligingsbeheerder** in azure Active Directory zijn om Microsoft 365 Defender in te schakelen. [Uw rollen weergeven in azure AD](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>Ondersteunde services
Microsoft 365 Defender voegt gegevens samen van de verschillende ondersteunde services die u al hebt geïmplementeerd. De gegevens worden centraal verwerkt en opgeslagen om nieuwe inzichten te identificeren en mogelijk gecentraliseerde antwoord werkstromen te maken. Dit gebeurt zonder dat dit invloed heeft op bestaande installaties, instellingen of gegevens die zijn gekoppeld aan de geïntegreerde services.

Om de beste beveiliging te bieden en Microsoft 365 Defender te optimaliseren, wordt u aangeraden alle toepasselijke ondersteunde services op uw netwerk te implementeren. Lees voor meer informatie [over het implementeren van ondersteunde services](deploy-supported-services.md).

## <a name="before-starting-the-service"></a>Voordat u de service start
Voordat u de service inschakelt, ziet u in het micro [soft 365-beveiligings](https://security.microsoft.com)centrum de pagina met instellingen voor microsoft 365 Defender wanneer u **incidenten** , **Onderhoudscentrum** of **jacht** selecteert in het navigatiedeelvenster. Deze navigatie-items worden niet weergegeven als u niet in aanmerking komt voor het gebruik van Microsoft 365 Defender.

![Afbeelding van de pagina met instellingen voor Microsoft 365 Defender, die wordt weergegeven als Microsoft 365 Defender niet is ingeschakeld voor de ](../../media/mtp-enable/mtp-settings.png)
 *instellingen van microsoft 365 Defender in microsoft 365 Beveiligingscentrum*

## <a name="starting-the-service"></a>De service starten
Als u Microsoft 365 Defender wilt inschakelen, selecteert u **Microsoft 365 Defender inschakelen** en voegt u de wijziging toe. U kunt deze optie ook openen door **instellingen** ( [Security.Microsoft.com/Settings](https://security.microsoft.com/settings)) te selecteren in het navigatiedeelvenster en vervolgens **Microsoft 365 Defender** te selecteren.

>[!NOTE]
>Als u **instellingen** niet ziet in het navigatiedeelvenster of de pagina niet kunt openen, controleert u de machtigingen en licenties.

### <a name="data-center-location"></a>Locatie van het Data Center
In Microsoft 365 Defender worden gegevens opgeslagen en verwerkt op [dezelfde locatie die wordt gebruikt door Microsoft Defender voor eindpunt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy). Als u Microsoft Defender voor eindpunten niet hebt, wordt een nieuwe locatie voor het datacenter automatisch geselecteerd op basis van de locatie van de actieve Microsoft 365-beveiligingsservices. De geselecteerde locatie van het datacenter wordt in het scherm weergegeven. 

Selecteer **hulp nodig?** in het microsoft 365-Beveiligingscentrum kunt u contact opnemen met Microsoft ondersteuning voor het inrichten van microsoft 365 Defender op een andere locatie van het datacenter. 

>[!NOTE]
>Microsoft Defender voor eindpunten in de Europese Unie (EU)-datacenters worden automatisch aangerekend wanneer Azure Defender wordt ingeschakeld. Microsoft 365 Defender voorziet automatisch in hetzelfde EU-datacenter voor klanten die de einddatum van de einddatum van eindpunten op deze manier hebben ingericht. 

### <a name="confirm-that-the-service-is-on"></a>Ga na of de service is ingeschakeld
Wanneer de service is ingericht, wordt het volgende toegevoegd:

- [Beheer van incidenten](incidents-overview.md)
- Een Actiecentrum voor het beheren van [geautomatiseerde onderzoek en reacties](mtp-autoir.md)
- [Geavanceerde](advanced-hunting-overview.md) functies voor de jacht

![Afbeelding van het navigatiedeelvenster van Microsoft 365-Beveiligingscentrum met Microsoft 365 Defender-functies ](../../media/mtp-enable/mtp-on.png)
 *microsoft 365 Beveiligingscentrum met incidentenbeheer en andere microsoft 365-mogelijkheden*

### <a name="getting-microsoft-defender-for-identity-data"></a>Microsoft Defender voor identiteitsgegevens verkrijgen
Als u Microsoft Defender wilt delen voor identiteitsgegevens met Microsoft 365 Defender, moet u ervoor zorgen dat Microsoft Cloud app Security en Microsoft Defender voor identiteits integratie is ingeschakeld. [Meer informatie over deze integratie](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-365-defender"></a>Microsoft 365 Defender uitschakelen
Als u wilt stoppen met het gebruik van Microsoft 365 Defender, gaat u naar **instellingen**  >  **Microsoft 365**  >  **voor afmelden/** uitbellen in het Microsoft 365-Beveiligingscentrum. Schakel **Microsoft 365 Defender in of uit** en pas de wijzigingen toe.

De bijbehorende functies worden verwijderd uit het Microsoft 365-Beveiligingscentrum.

## <a name="get-assistance"></a>Ondersteuning vragen

Voor antwoorden op de meest gestelde vragen over het inschakelen van Microsoft 365 Defender [raadpleegt u de veelgestelde vragen](mtp-enable-faq.md).

Ondersteuningspersoneel van Microsoft kan u helpen bij het inrichten van of het inrichten van de service en verwante bronnen voor uw Tenant. Als u hulp nodig hebt, selecteert u **hulp nodig?** in het microsoft 365-Beveiligingscentrum. Vermeld Microsoft 365 Defender wanneer u contact opneemt met de ondersteuning.

## <a name="related-topics"></a>Verwante onderwerpen

- [Veelgestelde vragen](mtp-enable-faq.md)
- [Licentievereisten en andere vereisten](prerequisites.md)
- [Ondersteunde services implementeren](deploy-supported-services.md)
- [Overzicht van Microsoft 365 Defender](microsoft-threat-protection.md)
- [Overzicht van Microsoft Defender voor eindpunt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Overzicht van Defender voor Office 365](../office-365-security/office-365-atp.md)
- [Overzicht van de beveiliging van Microsoft Cloud-app](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Overzicht van Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Gegevensopslag voor Microsoft Defender voor eindpunten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
