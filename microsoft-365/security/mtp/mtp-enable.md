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
ms.openlocfilehash: fa970b28939ad43bf6a2717e603013277bc9130f
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42811336"
---
# <a name="turn-on-microsoft-threat-protection"></a>Microsoft-bedreigingsbeveiliging inschakelen

**Van toepassing op:**
- Microsoft-bedreigingsbeveiliging

Microsoft Threat Protection maakt uw incidentresponsproces los door belangrijke mogelijkheden te integreren in Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security en Azure ATP. Deze uniforme ervaring voegt krachtige functies toe die u openen in het Microsoft 365-beveiligingscentrum.

Om de beste bescherming te krijgen en Microsoft Threat Protection te optimaliseren, raden we u aan alle toepasselijke ondersteunde services in uw netwerk te implementeren. Lees voor meer informatie [over het implementeren van ondersteunde services](deploy-supported-services.md).

## <a name="check-license-eligibility-and-required-permissions"></a>Controleer de geschiktheid en vereiste machtigingen voor licenties
Een Microsoft 365 E5-, E5-beveiligings- of A5-licentie of een geldige combinatie van licenties biedt toegang tot ondersteunde services en geeft u het recht om Microsoft Threat Protection te gebruiken in microsoft 365-beveiligingscentrum.

Lees voor gedetailleerde licentiegegevens [de licentievereisten](prerequisites.md#licensing-requirements).

### <a name="check-your-role"></a>Controleer uw rol
U moet een **globale beheerder** of een **beveiligingsbeheerder** in Azure Active Directory zijn om Microsoft Threat Protection in te schakelen. [Uw rollen weergeven in Azure AD](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="start-using-the-service"></a>De service gebruiken
Microsoft Threat Protection verzamelt gegevens van de verschillende geïntegreerde services. Het zal gegevens centraal verwerken en opslaan om nieuwe inzichten te identificeren en gecentraliseerde responsworkflows mogelijk te maken.

Voordat u de service inschakelt, toont het Microsoft 365-beveiligingscentrum[(security.microsoft.com)](https://security.microsoft.com)de welkomstpagina voor Microsoft Threat Protection wanneer u **Incidenten,** **actiecentrum**of **Jacht** selecteert in het navigatiedeelvenster. Deze navigatieopties worden niet weergegeven als u niet in aanmerking komt voor het gebruik van Microsoft Threat Protection.

![Afbeelding van de welkomstpagina van Microsoft Threat Protection weergegeven](../../media/mtp-welcome.png)
als Microsoft Threat Protection niet is ingeschakeld op*de welkomstpagina van Microsoft Threat Protection in microsoft 365-beveiligingscentrum*

Als u Microsoft Threat Protection wilt inschakelen, voltooit u het proces eenvoudig vanaf de welkomstpagina. U Microsoft Threat Protection ook inschakelen door toegang te krijgen tot **Instellingen** [(security.microsoft.com/settings)](https://security.microsoft.com/settings)in het navigatiedeelvenster en **Microsoft Threat Protection**te selecteren.

>[!NOTE]
>Als u **Instellingen** niet in het navigatiedeelvenster ziet of geen toegang hebt tot de pagina, controleert u uw machtigingen en licenties.

### <a name="select-data-center-location"></a>Datacenterlocatie selecteren
Als Microsoft Defender ATP is ingericht voor uw organisatie, worden gegevens opgeslagen en verwerkt op dezelfde datacenterlocatie die u hebt geselecteerd voor [uw Microsoft Defender ATP-gegevens.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy) Als u geen Microsoft Defender ATP hebt, wordt u gevraagd om een nieuwe datacenterlocatie te kiezen die specifiek voor Microsoft Threat Protection is bedoeld. 

U moet toestemming geven voordat gegevens worden gedeeld tussen services en samengevoegd.

### <a name="confirm-that-the-service-is-on"></a>Controleer of de service is ingeschakeld
Zodra de service is ingericht, voegt het:

- [Incidentenbeheer](incidents-overview.md)
- Een actiecentrum voor het beheren van [geautomatiseerd onderzoek en respons](mtp-autoir.md)
- [Geavanceerde jachtmogelijkheden](advanced-hunting-overview.md)

![Afbeelding van microsoft 365 security center navigatievenster met Microsoft Threat Protection functies](../../media/mtp-on.png)
Microsoft*365 security center met incidenten beheer en andere Microsoft Threat Protection mogelijkheden*

### <a name="getting-azure-atp-data"></a>Azure ATP-gegevens verkrijgen
Als u Azure ATP-gegevens wilt delen met Microsoft Threat Protection, moet u ervoor zorgen dat Microsoft Cloud App Security en Azure ATP-integratie zijn ingeschakeld. [Meer informatie over deze integratie](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a>Microsoft-bedreigingsbeveiliging uitschakelen
Ga naar **Instellingen** > **voor Microsoft Threat Protection** > **Opt-in / Opt-out** in het Microsoft 365-beveiligingscentrum om te stoppen met het gebruik van Microsoft Threat Protection. Schakel de optie **Microsoft Bedreigingsbeveiliging inschakelen** uit en sla de wijzigingen op.

De bijbehorende functies worden verwijderd uit het Microsoft 365-beveiligingscentrum.

## <a name="get-assistance"></a>Hulp krijgen

Microsoft-ondersteuningsmedewerkers kunnen helpen bij het inrichten of deprovisioneren van de service en gerelateerde resources op uw tenant. Selecteer Hulp nodig in het Microsoft 365-beveiligingscentrum voor **hulp?** Vermeld bij het contact met de ondersteuning Microsoft Threat Protection.

## <a name="related-topics"></a>Verwante onderwerpen

- [Overzicht van Microsoft Threat Protection](microsoft-threat-protection.md)
- [Licentievereisten en andere vereisten](prerequisites.md)
- [Ondersteunde services implementeren](deploy-supported-services.md)
- [Microsoft Defender ATP-overzicht](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Office 365 ATP-overzicht](../office-365-security/office-365-atp.md)
- [Overzicht van Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Azure ATP-overzicht](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender ATP-gegevensopslag](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
