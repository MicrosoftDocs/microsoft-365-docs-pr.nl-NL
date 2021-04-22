---
title: Automatiseringsniveaus in geautomatiseerd onderzoek en herstel
description: Een overzicht krijgen van automatiseringsniveaus en hoe ze werken in Microsoft Defender voor Eindpunt
keywords: automated, investigation, level, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.date: 10/22/2020
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.custom: AIR
ms.openlocfilehash: 013e01e9f84cae01258afc6ba139b7b5ada5912f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934115"
---
# <a name="automation-levels-in-automated-investigation-and-remediation-capabilities"></a>Automatiseringsniveaus in geautomatiseerde onderzoeks- en herstelmogelijkheden

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Geautomatiseerde mogelijkheden voor onderzoek en herstel (AIR) in Microsoft Defender voor Eindpunt kunnen worden geconfigureerd op een van de verschillende automatiseringsniveaus. Uw automatiseringsniveau is van invloed op de vraag of herstelacties na AIR-onderzoeken automatisch of alleen na goedkeuring worden ondernomen.  
- *Volledige automatisering* (aanbevolen) betekent dat herstelacties automatisch worden ondernomen op artefacten die schadelijk zijn.
- *Semi-automatisering* betekent dat sommige herstelacties automatisch worden ondernomen, maar andere herstelacties wachten op goedkeuring voordat ze worden ondernomen. (Zie de tabel in [Automatiseringsniveaus](#levels-of-automation).)
- Alle herstelacties, in behandeling of voltooid, worden bijgespoord in het Actiecentrum ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ). 

> [!TIP]
> Voor de beste resultaten raden we u aan volledige automatisering te gebruiken wanneer u [AIR configureert.](configure-automated-investigations-remediation.md) Uit gegevens die het afgelopen jaar zijn verzameld en geanalyseerd, blijkt dat klanten die volledige automatisering gebruiken, 40% meer betrouwbaarheidsmonsters voor malware hebben verwijderd dan klanten die lagere automatiseringsniveaus gebruiken. Volledige automatisering kan u helpen uw resources voor beveiligingsbewerkingen vrij te maken, zodat u zich meer kunt richten op uw strategische initiatieven.

## <a name="levels-of-automation"></a>Automatiseringsniveaus

In de volgende tabel wordt elk automatiseringsniveau en de manier beschreven waarop het werkt.

|Automatiseringsniveau | Beschrijving|
|:---|:---|
|**Volledig: herstel bedreigingen automatisch** <br/>(ook wel volledige automatisering *genoemd)*| Met volledige automatisering worden herstelacties automatisch uitgevoerd. Alle herstelacties die worden ondernomen, kunnen worden weergegeven in het [Actiecentrum](auto-investigation-action-center.md) op het **tabblad** Geschiedenis. Indien nodig kan een herstelactie ongedaan worden gemaakt.<br/><br/>**_Volledige automatisering wordt_* aanbevolen en is standaard geselecteerd voor tenants die zijn gemaakt op of na 16 augustus 2020 met Microsoft Defender voor Eindpunt, zonder dat er apparaatgroepen zijn gedefinieerd.*  |
|**Semi - goedkeuring vereisen voor eventuele herstelmaatregelen** <br/>(ook wel *semi-automatisering genoemd)*| Met dit niveau van semi-automatisering is goedkeuring vereist voor *elke* herstelactie. Dergelijke acties in behandeling kunnen worden bekeken en goedgekeurd in het [Actiecentrum](auto-investigation-action-center.md)op **het tabblad** In behandeling.<br/><br/>*Dit niveau van semi-automatisering is standaard geselecteerd voor tenants die zijn gemaakt vóór 16 augustus 2020 met Microsoft Defender voor Eindpunt, zonder dat er apparaatgroepen zijn gedefinieerd.*|
|**Semi - goedkeuring vereisen voor herstel van kernmappen** <br/>(ook een type *semi-automatisering*)  | Met dit niveau van semi-automatisering is goedkeuring vereist voor herstelacties die nodig zijn voor bestanden of uitvoerbare bestanden die zich in hoofdmappen hebben. Hoofdmappen bevatten mappen voor besturingssysteem, zoals **windows** ( `\windows\*` ).<br/><br/>Herstelacties kunnen automatisch worden uitgevoerd op bestanden of uitvoerbare bestanden die zich in andere mappen (niet-kernmappen) verplaatsen. <br/><br/>Acties in behandeling voor bestanden of uitvoerbare bestanden in kernmappen kunnen worden bekeken en goedgekeurd in het [Actiecentrum](auto-investigation-action-center.md)op **het** tabblad In behandeling. <br/><br/>Acties die zijn uitgevoerd op bestanden of uitvoerbare bestanden in andere mappen, kunnen worden weergegeven in het [Actiecentrum](auto-investigation-action-center.md)op **het** tabblad Geschiedenis. |
|**Semi - goedkeuring vereisen voor herstel van niet-tijdelijke mappen** <br/>(ook een type *semi-automatisering*)| Met dit niveau van semi-automatisering is goedkeuring vereist voor herstelacties die nodig zijn voor bestanden of uitvoerbare bestanden die niet *in* tijdelijke mappen staan. <br/><br/>Tijdelijke mappen kunnen de volgende voorbeelden bevatten: <br/>- `\users\*\appdata\local\temp\*`<br/>- `\documents and settings\*\local settings\temp\*` <br/>- `\documents and settings\*\local settings\temporary\*`<br/>- `\windows\temp\*`<br/>- `\users\*\downloads\*`<br/>- `\program files\` <br/>- `\program files (x86)\*`<br/>- `\documents and settings\*\users\*`<br/><br/>Herstelacties kunnen automatisch worden uitgevoerd op bestanden of uitvoerbare bestanden in tijdelijke mappen. <br/><br/>Acties in behandeling voor bestanden of uitvoerbare bestanden die niet in tijdelijke mappen staan, kunnen worden bekeken en goedgekeurd in het [Actiecentrum](auto-investigation-action-center.md)op het tabblad In **behandeling.**<br/><br/>Acties die zijn uitgevoerd op bestanden of uitvoerbare bestanden in tijdelijke mappen, kunnen worden bekeken en goedgekeurd in het [Actiecentrum](auto-investigation-action-center.md)op **het** tabblad Geschiedenis.   |
|**Geen geautomatiseerde reactie** <br/>(ook wel geen automatisering *genoemd)* | Zonder automatisering wordt automatisch onderzoek niet uitgevoerd op de apparaten van uw organisatie. Hierdoor worden er geen herstelacties ondernomen of in behandeling als gevolg van geautomatiseerd onderzoek. Andere beveiligingsfuncties voor bedreigingen, zoals beveiliging tegen mogelijk ongewenste [toepassingen,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)kunnen echter van kracht zijn, afhankelijk van hoe uw antivirusprogramma en de volgende generatie beveiligingsfuncties zijn geconfigureerd.<br/><br/>***Het is *niet raadzaam de*** optie Geen automatisering te gebruiken, omdat de beveiliging van de apparaten van uw organisatie hierdoor wordt beperkt. [Overweeg uw automatiseringsniveau in te stellen op volledige automatisering (of ten minste semi-automatisering)](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups)*. |

## <a name="important-points-about-automation-levels"></a>Belangrijke punten over automatiseringsniveaus

- Volledige automatisering is betrouwbaar, efficiënt en veilig en wordt aanbevolen voor alle klanten. Volledige automatisering maakt uw kritieke beveiligingsbronnen vrij, zodat ze zich meer kunnen richten op uw strategische initiatieven.

- Nieuwe tenants (waaronder tenants die zijn gemaakt op of na 16 augustus 2020) met Microsoft Defender voor Eindpunt, zijn standaard ingesteld op volledige automatisering.

- Als uw beveiligingsteam apparaatgroepen met een automatiseringsniveau heeft gedefinieerd, worden deze instellingen niet gewijzigd door de nieuwe standaardinstellingen die worden uitgerold. 

- U kunt uw standaardautomatiseringsinstellingen behouden of wijzigen op basis van uw organisatiebehoeften. Als u uw instellingen wilt wijzigen, [stelt u het automatiseringsniveau in.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-automated-investigations-remediation#set-up-device-groups)

## <a name="next-steps"></a>Volgende stappen

- [Geautomatiseerde onderzoeks- en herstelmogelijkheden configureren in Microsoft Defender voor Eindpunt](configure-automated-investigations-remediation.md)

- [Ga naar het Actiecentrum](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
