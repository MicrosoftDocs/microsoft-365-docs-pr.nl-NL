---
title: Beveiligingslekken herstellen met bedreigings- en kwetsbaarheidsbeheer
description: Herstel beveiligingszwaktes die zijn ontdekt door beveiligingsaanbevelingen en maak zo nodig uitzonderingen in bedreigings- en kwetsbaarheidsbeheer.
keywords: Microsoft Defender voor herstel van endpoint-tvm, mdatp-tvm, bedreigings- en kwetsbaarheidsbeheer, bedreiging & kwetsbaarheidsbeheer, herstel van bedreiging & kwetsbaarheidsbeheer, tvm-herstel intune, tvm-herstel sccm
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: be24528c2337c5d2616eb1bf69906f60ae7b4375
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689363"
---
# <a name="remediate-vulnerabilities-with-threat-and-vulnerability-management"></a>Beveiligingslekken herstellen met bedreigings- en kwetsbaarheidsbeheer

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Bedreigings- en kwetsbaarheidsbeheer](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="request-remediation"></a>Herstelverzoeken

De mogelijkheid voor bedreigings- en kwetsbaarheidsbeheer in Microsoft Defender voor Eindpunt overbrugt de kloof tussen beveiligings- en IT-beheerders via de werkstroom voor herstelverzoeken. Beveiligingsbeheerders zoals u kunnen de IT-beheerder vragen om  een beveiligingsprobleem op te verhelpen van de pagina's met beveiligingsaanbevelingen naar Intune.

### <a name="enable-microsoft-intune-connection"></a>Microsoft Intune-verbinding inschakelen

Als u deze mogelijkheid wilt gebruiken, moet u uw Microsoft Intune-verbindingen inschakelen. Ga in het Microsoft Defender-beveiligingscentrum naar **Algemene** geavanceerde functies  >    >  **instellingen.** Schuif omlaag en zoek naar **Microsoft Intune-verbinding.** De schakelknop is standaard uitgeschakeld. Schakel uw **Microsoft Intune-verbinding** **in.**

**Opmerking:** Als de Intune-verbinding is ingeschakeld, krijgt u een optie om een Intune-beveiligingstaak te maken wanneer u een herstelaanvraag maakt. Deze optie wordt niet weergegeven als de verbinding niet is ingesteld.

Zie [Intune gebruiken om beveiligingslekken](https://docs.microsoft.com/intune/atp-manage-vulnerabilities) te verhelpen die zijn geïdentificeerd door Microsoft Defender voor Eindpunt voor meer informatie.

### <a name="remediation-request-steps"></a>Stappen voor herstelverzoeken

1. Ga naar het navigatiemenu bedreigings- en kwetsbaarheidsbeheer in het Microsoft Defender-beveiligingscentrum en selecteer [**Beveiligingsaanbevelingen.**](tvm-security-recommendation.md)

2. Selecteer een beveiligingsaanbeveling voor wie u herstel wilt aanvragen en selecteer vervolgens **Herstelopties.**

3. Vul het formulier in, inclusief waar u herstel voor aanvraagt, toepasselijke apparaatgroepen, prioriteit, einddatum en optionele notities.
    1. Als u de optie 'aandacht vereist' kiest, is het selecteren van een einddatum niet beschikbaar omdat er geen specifieke actie is.

4. Selecteer **Aanvraag indienen.** Als u een herstelaanvraag indient, wordt er een herstelactiviteitsitem gemaakt binnen bedreigings- en kwetsbaarheidsbeheer, dat kan worden gebruikt voor het bewaken van de herstel voortgang voor deze aanbeveling. Hiermee wordt geen herstel veroorzaakt of worden er geen wijzigingen toegepast op apparaten.

5. Informeer uw IT-beheerder over de nieuwe aanvraag en laat deze zich aanmelden bij Intune om de aanvraag goed te keuren of te weigeren en een pakketimplementatie te starten.

6. Ga naar de [**pagina Herstel om**](tvm-remediation.md) de status van uw herstelaanvraag weer te geven.

Als u wilt controleren hoe het ticket in Intune wordt aangegeven, raadpleegt u [Intune](https://docs.microsoft.com/intune/atp-manage-vulnerabilities) gebruiken om beveiligingslekken te verhelpen die zijn geïdentificeerd door Microsoft Defender voor Eindpunt voor meer informatie.

>[!NOTE]
>Als uw aanvraag betrekking heeft op het herstellen van meer dan 10.000 apparaten, kunnen we slechts 10.000 apparaten voor herstel naar Intune verzenden.

Nadat de zwakke punten van uw organisatie op het [](tvm-security-recommendation.md)gebied van cyberbeveiliging zijn geïdentificeerd en in kaart zijn gebracht aan actiebare beveiligingsaanbevelingen, begint u met het maken van beveiligingstaken. U kunt taken maken via de integratie met Microsoft Intune, waar hersteltickets worden gemaakt.

Verhoog de blootstelling van uw organisatie door beveiligingsproblemen en verhoog de beveiligingsconfiguratie door de beveiligingsaanbevelingen te corrigeren.

## <a name="view-your-remediation-activities"></a>Uw herstelactiviteiten weergeven

Wanneer u een herstelaanvraag vanaf de pagina Beveiligingsaanbevelingen indient, wordt een herstelactiviteit afgetrapt. Er wordt een beveiligingstaak gemaakt die kan worden  bijgemaakt op de pagina Herstel van bedreigings- en kwetsbaarheidsbeheer en er wordt een herstelticket gemaakt in Microsoft Intune.

Als u de optie 'aandacht vereist' kiest, is er geen voortgangsbalk, ticketstatus of einddatum omdat er geen werkelijke actie is die we kunnen controleren.

Wanneer u zich op de pagina Herstel hebt geplaatst, selecteert u de herstelactiviteit die u wilt weergeven. U kunt de herstelstappen volgen, de voortgang bijhouden, de gerelateerde aanbeveling bekijken, exporteren naar CSV of markeren als voltooid.
![Voorbeeld van de pagina Herstel, met een geselecteerde herstelactiviteit, en de flyout van die activiteit met de beschrijving, hulpprogramma's voor IT-service- en apparaatbeheer en de voortgang van de apparaatsanering.](images/remediation_flyouteolsw.png)

>[!NOTE]
> Er is een bewaarperiode van 180 dagen voor voltooide herstelactiviteiten. Als u de herstelpagina optimaal wilt laten functioneren, wordt de herstelactiviteit zes maanden na voltooiing verwijderd.

### <a name="completed-by-column"></a>Voltooid per kolom

Houd bij wie de herstelactiviteit heeft gesloten met de kolom Voltooid door op de pagina Herstel.

- **E-mailadres:** het e-mailadres van de persoon die de taak handmatig heeft voltooid
- **Systeembevestiging:** de taak is automatisch voltooid (alle apparaten zijn gesaneerd)
- **N/B:** Informatie is niet beschikbaar omdat we niet weten hoe deze oudere taak is voltooid

![Gemaakt door en voltooid door kolommen met twee rijen. Eén rij voor voltooid door heeft een voorbeeld van een e-mailbericht, in de andere rij staat systeembevestiging.](images/tvm-completed-by.png)

### <a name="top-remediation-activities-in-the-dashboard"></a>Belangrijkste herstelactiviteiten in het dashboard

Bekijk **de belangrijkste herstelactiviteiten** in het [dashboard bedreigings- en kwetsbaarheidsbeheer.](tvm-dashboard-insights.md) Selecteer een van de items om naar de pagina **Herstel te** gaan. U kunt de herstelactiviteit markeren als voltooid nadat het IT-beheerteam de taak heeft gesaneerd.

![Voorbeeld van de kaart Top herstelactiviteiten met een tabel met de belangrijkste activiteiten die zijn gegenereerd op basis van beveiligingsaanbevelingen.](images/tvm-remediation-activities-card.png)

## <a name="related-articles"></a>Verwante artikelen

- [Overzicht van bedreigings- en kwetsbaarheidsbeheer](next-gen-threat-and-vuln-mgt.md)
- [Dashboard](tvm-dashboard-insights.md)
- [Beveiligingsaanbevelingen](tvm-security-recommendation.md)