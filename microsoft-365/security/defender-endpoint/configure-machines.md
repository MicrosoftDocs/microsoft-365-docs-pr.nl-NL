---
title: Controleer of uw apparaten correct zijn geconfigureerd
description: Configureer apparaten op de juiste manier om de algehele tolerantie tegen bedreigingen te verbeteren en uw mogelijkheden voor het detecteren en beantwoorden van aanvallen te verbeteren.
keywords: onboard, Intune management, MDATP, WDATP, Microsoft Defender, Windows Defender, advanced threat protection, attack surface reduction, ASR, security baseline
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e7b00ceafc2761f42c316f434a27acf7c551e7cf
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163361"
---
# <a name="ensure-your-devices-are-configured-properly"></a>Controleer of uw apparaten correct zijn geconfigureerd

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

Met goed geconfigureerde apparaten kunt u de algehele tolerantie tegen bedreigingen vergroten en uw vermogen verbeteren om aanvallen te detecteren en te beantwoorden. Beveiligingsconfiguratiebeheer zorgt ervoor dat uw apparaten:

- Onboard to Microsoft Defender for Endpoint
- Voldoen aan of overschrijden van de beveiligingslijnconfiguratie van Defender for Endpoint
- Strategische risicobeperking op het oppervlak van de aanval toepassen

Klik **in het** navigatiemenu op Configuratiebeheer om de pagina Apparaatconfiguratiebeheer te openen.

![Pagina Beveiligingsconfiguratiebeheer](images/secconmgmt_main.png)<br>
*Pagina Apparaatconfiguratiebeheer*

U kunt de configuratiestatus op organisatieniveau bijhouden en snel actie ondernemen als reactie op slechte onboarding-dekking, complianceproblemen en slecht geoptimaliseerde risico's voor aanvalsoppervlak via directe, diepe koppelingen naar pagina's voor apparaatbeheer in het Microsoft Intune- en Microsoft 365-beveiligingscentrum.

Daarbij profiteert u van:
- Uitgebreide zichtbaarheid van de gebeurtenissen op uw apparaten
- Krachtige bedreigingsinformatie en krachtige leertechnologieën voor apparaten voor het verwerken van onbewerkte gebeurtenissen en het identificeren van de inbreukactiviteit en bedreigingsindicatoren
- Een volledige stapel beveiligingsfuncties die zijn geconfigureerd om de installatie van schadelijke implantaten, het kapen van systeembestanden en -processen, gegevens exfiltratie en andere bedreigingsactiviteiten efficiënt te stoppen
- Geoptimaliseerde risico's voor aanvallen op het oppervlak, het maximaliseren van strategische verdediging tegen bedreigingsactiviteit en het minimaliseren van de invloed op de productiviteit

## <a name="enroll-devices-to-intune-management"></a>Apparaten registreren voor Intune-beheer

Apparaatconfiguratiebeheer werkt nauw samen met Intune-apparaatbeheer om de inventaris van de apparaten in uw organisatie en de basislijnbeveiligingsconfiguratie vast te stellen. U kunt configuratieproblemen bijhouden en beheren op Door Intune beheerde Windows 10-apparaten.

Voordat u ervoor kunt zorgen dat uw apparaten correct zijn geconfigureerd, moet u deze registreren bij Intune-beheer. Intune-registratie is robuust en heeft verschillende inschrijvingsopties voor Windows 10-apparaten. Voor meer informatie over intune-registratieopties leest u over het instellen van [registratie voor Windows-apparaten.](https://docs.microsoft.com/intune/windows-enroll)

>[!NOTE]
>Als u Windows-apparaten wilt registreren bij Intune, moeten beheerders al licenties zijn toegewezen. [Lees meer over het toewijzen van licenties voor apparaatinschrijving.](https://docs.microsoft.com/intune/licenses-assign)

>[!TIP] 
>Als u apparaatbeheer wilt optimaliseren via Intune, verbindt u [Intune met Defender voor Eindpunt.](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune)

## <a name="obtain-required-permissions"></a>Vereiste machtigingen verkrijgen
Standaard kunnen alleen gebruikers die de globale beheerder of de rol van Intune-servicebeheerder in Azure AD hebben toegewezen, de apparaatconfiguratieprofielen beheren en toewijzen die nodig zijn voor onboarding-apparaten en de beveiligingslijn implementeren.

Als u andere rollen hebt toegewezen, moet u ervoor zorgen dat u de benodigde machtigingen hebt:

- Volledige machtigingen voor apparaatconfiguraties
- Volledige machtigingen voor beveiligingslijnlijnen
- Leesmachtigingen voor apparaat compliancebeleid
- Leesmachtigingen voor de organisatie

![Vereiste machtigingen voor intune](images/secconmgmt_intune_permissions.png)<br>
*Apparaatconfiguratiemachtigingen voor Intune*

>[!TIP] 
>Lees meer over het maken van aangepaste [](https://docs.microsoft.com/intune/create-custom-role#to-create-a-custom-role)rollen voor meer informatie over het toewijzen van machtigingen aan Intune.

## <a name="in-this-section"></a>In deze sectie
Onderwerp | Beschrijving
:---|:---
[Apparaten in gebruik nemen bij Defender voor Eindpunt](configure-machines-onboarding.md)| Volg de onboarding-status van door Intune beheerde apparaten en onboard meer apparaten via Intune. 
[Naleving van de beveiligingslijn defender voor eindpunt verhogen](configure-machines-security-baseline.md) | Houd de naleving van de basislijn en niet-naleving bij. Implementeer de beveiligingslijn naar meer door Intune beheerde apparaten.
[Asr-regelimplementatie en -detecties optimaliseren](configure-machines-asr.md) | Controleer de implementatie van regels en pas detecties aan met behulp van hulpmiddelen voor effectanalyse in het Microsoft 365-beveiligingscentrum.

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
