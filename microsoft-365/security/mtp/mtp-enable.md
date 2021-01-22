---
title: Schakel Microsoft 365 Defender in in het Microsoft 365-beveiligingscentrum
description: Meer informatie over het inschakelen van Microsoft 365 Defender en het integreren van uw beveiligingsincident en -reactie.
keywords: aan de slag, schakel MTP, Microsoft Threat Protection, M365, beveiliging, gegevenslocatie, vereiste machtigingen, geschiktheid voor licenties, instellingenpagina
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
ms.openlocfilehash: 19f035a271626077911b05082a4aba6d67355cdb
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930220"
---
# <a name="turn-on-microsoft-365-defender"></a>Microsoft 365 Defender in te zetten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-threat-protection.md) defificeert uw incidentreactieproces door belangrijke mogelijkheden te integreren tussen Microsoft Defender voor eindpunt, Microsoft Defender voor Office 365, Microsoft Cloud App-beveiliging en Microsoft Defender voor identiteit. Deze geïntegreerde ervaring biedt krachtige functies die u kunt openen in het Microsoft 365-beveiligingscentrum.

Microsoft 365 Defender wordt automatisch in schakelt wanneer in aanmerking komende klanten met de vereiste machtigingen naar het Microsoft 365-beveiligingscentrum gaan. Lees dit artikel voor meer informatie over verschillende vereisten en hoe Microsoft 365 Defender wordt ingericht.

## <a name="check-license-eligibility-and-required-permissions"></a>Controleer of de licentie in aanmerking komt en de vereiste machtigingen

Een licentie voor een Microsoft 365-beveiligingsproduct biedt u in het algemeen een recht om Microsoft 365 Defender te gebruiken in het Microsoft 365-beveiligingscentrum zonder extra licentiekosten. We raden u aan een beveiligingslicentie voor Microsoft 365 E5, E5, A5 of A5 te verkrijgen of een geldige combinatie van licenties die toegang biedt tot alle ondersteunde services.

Lees de licentievereisten voor [meer informatie over licenties.](prerequisites.md#licensing-requirements)

### <a name="check-your-role"></a>Controleer uw rol

U moet een globale beheerder **of** beveiligingsbeheerder **in** Azure Active Directory zijn om Microsoft 365 Defender in te zetten. [Uw rollen weergeven in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>Ondersteunde services

Microsoft 365 Defender verzamelt gegevens uit de verschillende ondersteunde services die u al hebt geïmplementeerd. Gegevens worden centraal verwerkt en opgeslagen om nieuwe inzichten te identificeren en gecentraliseerde antwoordwerkstromen mogelijk te maken. Dit gebeurt zonder dat dit van invloed is op bestaande implementaties, instellingen of gegevens die zijn gekoppeld aan de geïntegreerde services.

Voor de beste bescherming en optimaliseren van Microsoft 365 Defender, raden we u aan alle toepasselijke ondersteunde services op uw netwerk te implementeren. Lees meer over het [implementeren van ondersteunde services.](deploy-supported-services.md)

## <a name="before-starting-the-service"></a>Voordat u de service start

Voordat u de service in dienst gaat, wordt in het Microsoft 365-beveiligingscentrum [(security.microsoft.com)](https://security.microsoft.com)de pagina met  Microsoft 365 Defender-instellingen weergegeven wanneer u **Incidenten,** Actiecentrum of Zoeken selecteert in het navigatiedeelvenster. Deze navigatie-items worden niet weergegeven als u niet in aanmerking komt voor het gebruik van Microsoft 365 Defender.

![Afbeelding van de pagina met microsoft 365 Defender-instellingen die wordt weergegeven als Microsoft 365 Defender geen Microsoft 365 Defender-instellingen heeft ingeschakeld in het ](../../media/mtp-enable/mtp-settings.png)
 *Microsoft 365-beveiligingscentrum*

## <a name="starting-the-service"></a>De service starten

Als u Microsoft 365 Defender wilt in turnen, selecteert u **Microsoft 365 Defender** in te zetten en de wijziging toe te passen. U kunt deze optie ook openen door **Instellingen** [(security.microsoft.com/settings)](https://security.microsoft.com/settings)te selecteren in het navigatiedeelvenster en vervolgens **Microsoft 365 Defender te selecteren.**

> [!NOTE]
> Als u Instellingen niet ziet in **het** navigatiedeelvenster of als u de pagina niet kunt openen, controleert u uw machtigingen en licenties.

### <a name="data-center-location"></a>Locatie van datacenter

Microsoft 365 Defender zal gegevens opslaan en verwerken op dezelfde locatie die door [Microsoft Defender voor Eindpunt wordt gebruikt.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy) Als u microsoft Defender voor eindpunt niet hebt, wordt automatisch een nieuwe locatie van het datacenter geselecteerd op basis van de locatie van actieve beveiligingsservices van Microsoft 365. De geselecteerde locatie van het datacenter wordt weergegeven op het scherm.

Selecteer **Hulp nodig?** In het Microsoft 365-beveiligingscentrum kunt u contact opnemen met Microsoft Ondersteuning over de inrichting van Microsoft 365 Defender op een andere locatie in het datacenter.

> [!NOTE]
> Microsoft Defender voor eindpunt richt automatisch voorzieningen in datacenters van de Europese Unie (EU) indien ingeschakeld via Azure Defender. Microsoft 365 Defender wordt automatisch ingericht in hetzelfde EU-datacenter voor klanten die Defender voor eindpunt op deze manier hebben ingericht.

### <a name="confirm-that-the-service-is-on"></a>Controleer of de service is

Nadat de service is ingericht, wordt het volgende toegevoegd:

- [Incidentenbeheer](incidents-overview.md)
- Een actiecentrum voor het beheren [van automatisch onderzoek en antwoorden](mtp-autoir.md)
- [Geavanceerde mogelijkheden voor](advanced-hunting-overview.md) zoeken

![Afbeelding van navigatiedeelvenster van het Microsoft 365-beveiligingscentrum met Microsoft 365 Defender-functies Microsoft 365-beveiligingscentrum met beheer van incidenten en andere mogelijkheden van ](../../media/mtp-enable/mtp-on.png)
 *Microsoft 365 Defender*

### <a name="getting-microsoft-defender-for-identity-data"></a>Microsoft Defender voor identiteitsgegevens verkrijgen

Als u Microsoft Defender voor identiteitsgegevens wilt delen met Microsoft 365 Defender, moet Microsoft Cloud App Security en Microsoft Defender voor identiteitsintegratie zijn ingeschakeld. [Meer informatie over deze integratie.](https://docs.microsoft.com/cloud-app-security/mdi-integration)

## <a name="get-assistance"></a>Ondersteuning krijgen

Lees de veelgestelde vragen voor antwoorden op de meest gestelde vragen over het in- en uitschakelen [van](mtp-enable-faq.md)Microsoft 365 Defender.

Microsoft-ondersteuningsmedewerkers kunnen u helpen bij het inrichten of de inrichting van de service en gerelateerde resources in uw tenant. Selecteer Hulp nodig in **het** Microsoft 365-beveiligingscentrum voor hulp. Als u contact op kunt nemen met ondersteuning, vermeldt u Microsoft 365 Defender.

## <a name="related-topics"></a>Verwante onderwerpen

- [Veelgestelde vragen](mtp-enable-faq.md)
- [Licentievereisten en andere vereisten](prerequisites.md)
- [Ondersteunde services implementeren](deploy-supported-services.md)
- [Overzicht van Microsoft 365 Defender](microsoft-threat-protection.md)
- [Overzicht van Microsoft Defender voor eindpunt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Overzicht van Defender voor Office 365](../office-365-security/office-365-atp.md)
- [Overzicht van beveiliging van Microsoft Cloud-apps](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Overzicht van Microsoft Defender voor identiteit](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Gegevensopslag met Microsoft Defender voor eindpunt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
