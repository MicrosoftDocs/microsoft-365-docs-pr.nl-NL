---
title: Voorwaardelijke toegang inschakelen om gebruikers, apparaten en gegevens beter te beveiligen
description: Schakel Voorwaardelijke toegang in om te voorkomen dat toepassingen worden uitgevoerd als een apparaat als risico wordt beschouwd en een toepassing niet compatibel is.
keywords: voorwaardelijke toegang, blokkeringstoepassingen, beveiligingsniveau, intune,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 21d17ee789a4757df10e99514f23cfc26b186405
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166195"
---
# <a name="enable-conditional-access-to-better-protect-users-devices-and-data"></a>Voorwaardelijke toegang inschakelen om gebruikers, apparaten en gegevens beter te beveiligen 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-abovefoldlink)

Voorwaardelijke toegang is een mogelijkheid waarmee u uw gebruikers en bedrijfsgegevens beter kunt beschermen door ervoor te zorgen dat alleen beveiligde apparaten toegang hebben tot toepassingen.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4byD1]

Met Voorwaardelijke toegang kunt u de toegang tot bedrijfsgegevens bepalen op basis van het risiconiveau van een apparaat. Hiermee kunt u vertrouwde gebruikers op vertrouwde apparaten houden met behulp van vertrouwde toepassingen.

U kunt beveiligingsvoorwaarden definiëren waaronder apparaten en toepassingen gegevens vanuit uw netwerk kunnen uitvoeren en openen door beleidsregels uit te voeren om te voorkomen dat toepassingen worden uitgevoerd totdat een apparaat weer compatibel is. 

De implementatie van Voorwaardelijke toegang in Defender voor Eindpunt is gebaseerd op Microsoft Intune (Intune) beleid voor apparaat compliance en Azure Active Directory (Azure AD) beleid voor voorwaardelijke toegang. 

Het compliancebeleid wordt gebruikt met Voorwaardelijke toegang om alleen apparaten die voldoen aan een of meer regels voor apparaat compliancebeleid toegang te geven tot toepassingen. 

## <a name="understand-the-conditional-access-flow"></a>De stroom Voorwaardelijke toegang begrijpen
Voorwaardelijke toegang wordt zo geïnstalleerd dat wanneer een bedreiging wordt gezien op een apparaat, de toegang tot gevoelige inhoud wordt geblokkeerd totdat de bedreiging wordt vereend. 

De stroom begint met apparaten met een laag, gemiddeld of hoog risico. Deze risicobepalingen worden vervolgens verzonden naar Intune. 

Afhankelijk van hoe u beleid configureert in Intune, kan Voorwaardelijke toegang zo worden ingesteld dat wanneer aan bepaalde voorwaarden wordt voldaan, het beleid wordt toegepast.

U kunt Intune bijvoorbeeld zo configureren dat Voorwaardelijke toegang wordt toegepast op apparaten met een hoog risico.

In Intune wordt een apparaat compliancebeleid gebruikt in combinatie met Azure AD Voorwaardelijke toegang om toegang tot toepassingen te blokkeren. Tegelijkertijd wordt een geautomatiseerd onderzoek en herstelproces gestart.

 Een gebruiker kan het apparaat nog steeds gebruiken terwijl het geautomatiseerde onderzoek en herstel plaatsvindt, maar de toegang tot ondernemingsgegevens wordt geblokkeerd totdat de bedreiging volledig is hersteld. 

Als u het risico op een apparaat wilt oplossen, moet u het apparaat terug naar een compatibele status. Een apparaat keert terug naar een compatibele status wanneer er geen risico op wordt gezien. 

Er zijn drie manieren om een risico aan te pakken:
1. Handmatige of geautomatiseerde herstelmaatregelen gebruiken.
2. Actieve waarschuwingen op het apparaat oplossen. Hierdoor wordt het risico van het apparaat verwijderd.
3. U kunt het apparaat verwijderen uit het actieve beleid en daarom wordt Voorwaardelijke toegang niet toegepast op het apparaat. 

Handmatig herstellen vereist een secops-beheerder om een waarschuwing te onderzoeken en het risico op het apparaat aan te pakken. De geautomatiseerde herstel wordt geconfigureerd via configuratie-instellingen in de volgende sectie [Voorwaardelijke toegang configureren.](configure-conditional-access.md)

Wanneer het risico wordt verwijderd via handmatige of geautomatiseerde herstel, keert het apparaat terug naar een compatibele status en wordt toegang tot toepassingen verleend.

In de volgende voorbeeldreeks van gebeurtenissen wordt Voorwaardelijke toegang in actie uitgelegd:

1. Een gebruiker opent een schadelijk bestand en Defender voor Eindpunt markeert het apparaat als hoog risico.
2. De beoordeling van het hoge risico wordt doorgegeven aan Intune. Tegelijkertijd wordt een geautomatiseerd onderzoek gestart om de geïdentificeerde bedreiging te herstellen. Er kan ook handmatig worden gesaneerd om de geïdentificeerde bedreiging te corrigeren.
3. Op basis van het beleid dat is gemaakt in Intune, wordt het apparaat gemarkeerd als niet compatibel. De beoordeling wordt vervolgens door het Beleid voor voorwaardelijke toegang in Intune naar Azure AD gecommuniceerd. In Azure AD wordt het bijbehorende beleid toegepast om toegang tot toepassingen te blokkeren.
4. Het handmatige of geautomatiseerde onderzoek en herstel is voltooid en de bedreiging wordt verwijderd. Defender voor Eindpunt ziet dat er geen risico's zijn op het apparaat en in Intune wordt beoordeeld of het apparaat compatibel is. Azure AD past het beleid toe dat toegang biedt tot toepassingen.
5. Gebruikers hebben nu toegang tot toepassingen.

 
## <a name="related-topic"></a>Verwant onderwerp
- [Voorwaardelijke toegang configureren in Microsoft Defender voor eindpunt](configure-conditional-access.md)
