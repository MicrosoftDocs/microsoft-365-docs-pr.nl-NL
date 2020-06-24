---
title: Microsoft Threat Protection inschakelen in het Microsoft 365-beveiligingscentrum
description: Meer informatie over het inschakelen van Microsoft Threat Protection en het integreren van uw beveiligingsincident en -reactie.
keywords: aan de slag, schakel MTP, Microsoft Threat Protection, M365, beveiliging, gegevenslocatie, vereiste machtigingen, licentiegeschiktheid, instellingenpagina in
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
ms.openlocfilehash: 0badae0d81b52b89c47f950b889109d4b9d35dda
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844590"
---
# <a name="turn-on-microsoft-threat-protection"></a>Microsoft Threat Protection inschakelen

**Van toepassing op:**
- Microsoft Threat Protection

[Microsoft Threat Protection](microsoft-threat-protection.md) verenigt uw incidentresponsproces door de belangrijkste mogelijkheden te integreren in Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security en Azure ATP. Deze uniforme ervaring voegt krachtige functies toe die u openen in het Microsoft 365-beveiligingscentrum.

Microsoft Threat Protection wordt automatisch ingeschakeld wanneer in aanmerking komende klanten met de vereiste machtigingen het Microsoft 365-beveiligingscentrum bezoeken. Lees dit artikel om inzicht te krijgen in verschillende vereisten en hoe Microsoft Threat Protection is ingericht.

## <a name="check-license-eligibility-and-required-permissions"></a>Controleer de geschiktheid van de licentie en vereiste machtigingen
Een licentie voor een Microsoft 365-beveiligingsproduct geeft u over het algemeen het recht om Microsoft Threat Protection te gebruiken in het Microsoft 365-beveiligingscentrum zonder extra licentiekosten. We raden u aan een Microsoft 365 E5-, E5-beveiligings-, A5- of A5-beveiligingslicentie of een geldige combinatie van licenties te krijgen die toegang biedt tot alle ondersteunde services.

Lees voor gedetailleerde licentie-informatie [de licentievereisten](prerequisites.md#licensing-requirements).

### <a name="check-your-role"></a>Controleer uw rol
U moet een **globale beheerder** of een **beveiligingsbeheerder** in Azure Active Directory zijn om Microsoft Threat Protection in te schakelen. [Uw rollen weergeven in Azure AD](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>Ondersteunde services
Microsoft Threat Protection verzamelt gegevens van de verschillende ondersteunde services die u al hebt geïmplementeerd. Het verwerkt en slaat gegevens centraal op om nieuwe inzichten te identificeren en gecentraliseerde responsworkflows mogelijk te maken. Dit gebeurt zonder dat dit gevolgen heeft voor bestaande implementaties, instellingen of gegevens die zijn gekoppeld aan de geïntegreerde services.

Om de beste bescherming te krijgen en Microsoft Threat Protection te optimaliseren, raden we u aan alle toepasselijke ondersteunde services in uw netwerk te implementeren. Lees voor meer informatie [over het implementeren van ondersteunde services.](deploy-supported-services.md)

## <a name="before-starting-the-service"></a>Voordat u met de service begint
Voordat u de service inschakelt, wordt in het Microsoft 365-beveiligingscentrum[(security.microsoft.com)](https://security.microsoft.com)de pagina Microsoft Threat Protection-instellingen weergegeven wanneer u **Incidenten,** **Actiecentrum**of **Hunting** selecteert in het navigatiedeelvenster. Deze navigatie-items worden niet weergegeven als u niet in aanmerking komt voor het gebruik van Microsoft Threat Protection.

![Afbeelding van de pagina Microsoft Threat Protection-instellingen die wordt weergegeven als Microsoft Threat Protection niet is ingeschakeld in ](../../media/mtp-enable/mtp-settings.png)
 *microsoft 365-beveiligingscentrum*

## <a name="starting-the-service"></a>De service starten
Als u Microsoft Threat Protection wilt inschakelen, selecteert u **Microsoft Threat Protection inschakelen** en past u de wijziging toe. U deze optie ook openen door **Instellingen** [(security.microsoft.com/settings)](https://security.microsoft.com/settings)in het navigatiedeelvenster te selecteren en **vervolgens Microsoft-bedreigingsbeveiliging te**selecteren.

>[!NOTE]
>Als u **Instellingen** niet ziet in het navigatiedeelvenster of geen toegang hebt tot de pagina, controleert u uw machtigingen en licenties.

### <a name="data-center-location"></a>Locatie datacenter
Microsoft Threat Protection slaat gegevens op en verwerkt deze op [dezelfde locatie die wordt gebruikt door Microsoft Defender ATP.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy) Als u geen Microsoft Defender ATP hebt, wordt automatisch een nieuwe locatie van het datacenter geselecteerd op basis van de locatie van actieve Microsoft 365-beveiligingsservices. De geselecteerde locatie van het datacenter wordt weergegeven in het scherm.

>[!NOTE]
>Selecteer **Hulp nodig?** In het Microsoft 365-beveiligingscentrum u contact opnemen met Microsoft-ondersteuning over het inrichten van Microsoft Threat Protection op een andere locatie van het datacenter. 

### <a name="confirm-that-the-service-is-on"></a>Controleer of de service is ingeschakeld
Zodra de service is ingericht, voegt zij eraan toe:

- [Incidentenbeheer](incidents-overview.md)
- Een actiecentrum voor het beheren van [geautomatiseerd onderzoek en respons](mtp-autoir.md)
- [Geavanceerde jachtmogelijkheden](advanced-hunting-overview.md)

![Afbeelding van het navigatiedeelvenster van het Microsoft 365-beveiligingscentrum met Microsoft Threat Protection is voorzien van ](../../media/mtp-enable/mtp-on.png)
 *Microsoft 365-beveiligingscentrum met incidentenbeheer en andere microsoft Threat Protection-mogelijkheden*

### <a name="getting-azure-atp-data"></a>Azure ATP-gegevens opvragen
Als u Azure ATP-gegevens wilt delen met Microsoft Threat Protection, moet u ervoor zorgen dat Microsoft Cloud App Security en Azure ATP-integratie zijn ingeschakeld. [Meer informatie over deze integratie](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a>Microsoft Threat Protection uitschakelen
Als u wilt stoppen met het gebruik van Microsoft Threat Protection, gaat u naar **Instellingen**  >  **Microsoft Threat Protection**  >  **Opt-in / Opt-out** in het Microsoft 365-beveiligingscentrum. Schakel **Microsoft-bedreigingsbeveiliging uitschakelen** en pas de wijzigingen toe.

De bijbehorende functies worden verwijderd uit het Microsoft 365-beveiligingscentrum.

## <a name="get-assistance"></a>Hulp krijgen

[Lees de veelgestelde](mtp-enable-faq.md)vragen voor antwoorden op de meest gestelde vragen over het inschakelen van Microsoft Threat Protection.

Microsoft-ondersteuningsmedewerkers kunnen helpen bij het inrichten of deprovisioneren van de service en gerelateerde bronnen op uw tenant. Selecteer Hulp **nodig in** het Microsoft 365-beveiligingscentrum voor hulp. Vermeld Microsoft Threat Protection wanneer u contact opneemt met ondersteuning.

## <a name="related-topics"></a>Verwante onderwerpen

- [Veelgestelde vragen](mtp-enable-faq.md)
- [Licentievereisten en andere voorwaarden](prerequisites.md)
- [Ondersteunde services implementeren](deploy-supported-services.md)
- [Overzicht van Microsoft Threat Protection](microsoft-threat-protection.md)
- [Microsoft Defender ATP-overzicht](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [AtP-overzicht van Office 365](../office-365-security/office-365-atp.md)
- [Overzicht van microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Azure ATP-overzicht](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender ATP-gegevensopslag](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)