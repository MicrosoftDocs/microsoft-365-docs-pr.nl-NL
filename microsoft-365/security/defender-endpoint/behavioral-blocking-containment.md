---
title: Gedragsblokkering en -insluiting
description: Meer informatie over mogelijkheden voor het blokkeren en inperking van gedrag in Microsoft Defender voor Eindpunt
keywords: Microsoft Defender voor Eindpunt, EDR in blokmodus, passieve modus blokkeren
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 98ea631536bbfa9e1858f70ae3a0ea9de8743572
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029775"
---
# <a name="behavioral-blocking-and-containment"></a>Gedragsblokkering en -insluiting

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefversie.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a>Overzicht

Het huidige bedreigingslandschap wordt overlopen door bestandsloze [malware](/windows/security/threat-protection/intelligence/fileless-threats) en die buiten het land leeft, zeer polymorfe bedreigingen die sneller muteren dan traditionele oplossingen, en door mensen beheerde aanvallen die zich aanpassen aan wat tegenstanders vinden op gecompromitteerde apparaten. Traditionele beveiligingsoplossingen zijn niet voldoende om dergelijke aanvallen te stoppen. u hebt kunstmatige intelligentie (AI) en apparaatleren (ML) back-mogelijkheden nodig, zoals gedragsblokkering en insluiting, opgenomen in [Defender voor Eindpunt.](/windows/security)

Mogelijkheden voor het blokkeren en inperken van gedrag kunnen helpen bij het identificeren en stoppen van bedreigingen, op basis van hun gedrag en procesbomen, zelfs wanneer de bedreiging is gestart met de uitvoering. De volgende generatie beveiliging, EDR en Defender voor endpoint-onderdelen en -functies werken samen in de mogelijkheden voor het blokkeren en inperking van gedrag.

:::image type="content" source="images/mdatp-next-gen-EDR-behavblockcontain.png" alt-text="Gedragsblokkering en -insluiting":::

Functies voor het blokkeren en inperken van gedrag werken met meerdere onderdelen en functies van Defender voor Eindpunt om aanvallen onmiddellijk te stoppen en te voorkomen dat er aanvallen worden uitgevoerd.

- [Beveiliging van de volgende generatie](microsoft-defender-antivirus-in-windows-10.md) (inclusief Microsoft Defender Antivirus) kan bedreigingen detecteren door gedrag te analyseren en bedreigingen te stoppen die zijn gestart.

- [Eindpuntdetectie en -antwoord](overview-endpoint-detection-response.md) (EDR) ontvangt beveiligingssignalen in uw netwerk, apparaten en kernelgedrag. Wanneer er bedreigingen worden gedetecteerd, worden waarschuwingen gemaakt. Meerdere waarschuwingen van hetzelfde type worden samengevoegd tot incidenten, waardoor uw team voor beveiligingsbewerkingen gemakkelijker kan onderzoeken en reageren.

- [Defender for Endpoint](overview-endpoint-detection-response.md) heeft een breed scala aan optiek in identiteiten, e-mail, gegevens en apps, naast de netwerk-, eindpunt- en kernelgedragssignalen die via de EDR. Een onderdeel van [Microsoft 365 Defender](../defender/microsoft-365-defender.md), Defender voor Eindpunt verwerkt en correleert deze signalen, verhoogt detectiewaarschuwingen en verbindt gerelateerde waarschuwingen bij incidenten.

Met deze mogelijkheden kunnen meer bedreigingen worden voorkomen of geblokkeerd, zelfs als ze worden uitgevoerd. Wanneer verdacht gedrag wordt gedetecteerd, is de bedreiging opgenomen, worden waarschuwingen gemaakt en worden bedreigingen op hun sporen gestopt.

In de volgende afbeelding ziet u een voorbeeld van een waarschuwing die is geactiveerd door mogelijkheden voor het blokkeren en inperking van gedrag:

:::image type="content" source="images/blocked-behav-alert.png" alt-text="Voorbeeld van een waarschuwing door middel van blokkering en insluiting van gedrag":::

## <a name="components-of-behavioral-blocking-and-containment"></a>Onderdelen van het blokkeren en inperking van gedrag

- **On-client, policy-driven [attack surface reduction rules](attack-surface-reduction.md)** Vooraf gedefinieerde veelvoorkomende aanvalsgedrag kan niet worden uitgevoerd volgens de surface reduction-regels voor uw aanval. Wanneer dergelijke gedragingen worden uitgevoerd, kunnen ze in Microsoft 365 Defender worden gezien <https://security.microsoft.com> als informatiewaarschuwingen. Surface-beperkingsregels voor aanvallen zijn standaard niet ingeschakeld. u configureert uw beleid in de [Microsoft 365 Defender.](microsoft-defender-security-center.md)

- **[Clientgedragsblokkering](client-behavioral-blocking.md)** Bedreigingen op eindpunten worden gedetecteerd via machine learning en worden vervolgens automatisch geblokkeerd en gesaneerd. (Clientgedragsblokkering is standaard ingeschakeld.)

- **[Het blokkeren van feedbackluss](feedback-loop-blocking.md)** (ook wel snelle beveiliging genoemd) Detecties van bedreigingen worden waargenomen via gedragsinformatie. Bedreigingen worden gestopt en worden niet uitgevoerd op andere eindpunten. (Het blokkeren van feedbacklussen is standaard ingeschakeld.)

- **[Eindpuntdetectie en -antwoord (EDR) in de blokmodus](edr-in-block-mode.md)** Schadelijke artefacten of gedragingen die worden waargenomen via bescherming na inbreuk, worden geblokkeerd en opgenomen. EDR in de blokmodus werkt zelfs als Microsoft Defender Antivirus niet de primaire antivirusoplossing is. (EDR in de blokmodus is standaard niet ingeschakeld; u zet deze in Microsoft 365 Defender.)

Verwacht meer op het gebied van het blokkeren en inperking van gedrag, omdat Microsoft de functies en mogelijkheden voor bedreigingsbeveiliging blijft verbeteren. Als u wilt zien wat er nu wordt gepland en uitgerold, gaat u [naar Microsoft 365 routekaart.](https://www.microsoft.com/microsoft-365/roadmap)

## <a name="examples-of-behavioral-blocking-and-containment-in-action"></a>Voorbeelden van gedrag blokkeren en inperking in actie

De mogelijkheden voor het blokkeren en inperking van gedrag hebben technieken voor aanvallers geblokkeerd, zoals de volgende:

- Referentiesdumping van LSASS
- Kruisprocesinjectie
- Uitholling van proces
- Bypass gebruikersaccountbeheer
- Geknoei met antivirusprogramma's (zoals het uitschakelen of het toevoegen van de malware als uitsluiting)
- Contact opnemen met Command and Control (C&C) om payloads te downloaden
- Munten delven
- Wijziging van opstartrecord
- Pass-the-hash-aanvallen
- Installatie van hoofdcertificaat
- Poging tot misbruik voor verschillende beveiligingslekken

Hieronder vindt u twee praktijkvoorbeelden van het blokkeren en inperking van gedrag in actie.

### <a name="example-1-credential-theft-attack-against-100-organizations"></a>Voorbeeld 1: Diefstal van referenties tegen 100 organisaties

Zoals wordt beschreven in In hot pursuit of ongrijpbare bedreigingen: door [AI-gestuurde](https://www.microsoft.com/security/blog/2019/10/08/in-hot-pursuit-of-elusive-threats-ai-driven-behavior-based-blocking-stops-attacks-in-their-tracks)blokkering op basis van gedrag worden aanvallen in hun sporen gestopt, werd een aanval op referentiesdiefstal tegen 100 organisaties over de hele wereld gestopt door de mogelijkheden voor het blokkeren en inperken van gedrag. E-mailberichten met een lokmiddel zijn verzonden naar de beoogde organisaties. Als een geadresseerde de bijlage heeft geopend, kon een gerelateerd extern document code uitvoeren op het apparaat van de gebruiker en Lokibot-malware laden, waardoor referenties werden gestolen, gestolen gegevens werden geëfiltreerd en werd gewacht op verdere instructies van een command-and-control-server.

Op gedrag gebaseerde apparaatlerende modellen in Defender voor Eindpunt zijn op twee punten in de aanvalsketen vastgelegd en gestopt:

- De eerste beveiligingslaag heeft het gedrag van de exploit gedetecteerd. Leerclassifiers voor apparaten in de cloud hebben de bedreiging correct geïdentificeerd als en hebben het clientapparaat onmiddellijk geïnstrueerd de aanval te blokkeren.
- De tweede beveiligingslaag, waarmee de gevallen van de aanval voorbij de eerste laag werden gestopt, procesverholding werd gedetecteerd, dat proces werd gestopt en de bijbehorende bestanden (zoals Lokibot) werden verwijderd.

Terwijl de aanval werd gedetecteerd en gestopt, werden waarschuwingen, zoals een 'eerste toegangsmelding', geactiveerd en verschenen in de [Microsoft 365 Defender-portal](microsoft-defender-security-center.md) (voorheen de Microsoft Defender-beveiligingscentrum):

:::image type="content" source="images/behavblockcontain-initialaccessalert.png" alt-text="Eerste toegangsmelding in de Microsoft 365 Defender portal":::

In dit voorbeeld ziet u hoe op gedrag gebaseerde leermodellen voor apparaten in de cloud nieuwe beveiligingslagen tegen aanvallen toevoegen, zelfs nadat ze zijn gestart met uitvoeren.

### <a name="example-2-ntlm-relay---juicy-potato-malware-variant"></a>Voorbeeld 2: NTLM-relay - Malwarevariant van de 2e versie van De aardappel

Zoals in het recente blogbericht wordt beschreven, heeft Defender voor Eindpunt in januari 2020 een activiteit voor escalatie van bevoegdheden gedetecteerd op een apparaat in een [organisatie.](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection) Er is een waarschuwing met de naam 'Mogelijke escalatie van bevoegdheden met NTLM-relay' geactiveerd.

:::image type="content" source="images/NTLMalertjuicypotato.png" alt-text="NTLM-waarschuwing voor malware met de naam Juicy Potato":::

De bedreiging bleek malware te zijn. het was een nieuwe, niet-gezien-vóór variant van een berucht hackingprogramma genaamd Juicy Potato, dat door aanvallers wordt gebruikt om privilege escalatie op een apparaat te krijgen.

Minuten nadat de waarschuwing is geactiveerd, is het bestand geanalyseerd en bevestigd dat het schadelijk is. Het proces is gestopt en geblokkeerd, zoals wordt weergegeven in de volgende afbeelding:

:::image type="content" source="images/Artifactblockedjuicypotato.png" alt-text="Artefact geblokkeerd":::

Enkele minuten nadat het artefact was geblokkeerd, werden meerdere exemplaren van hetzelfde bestand geblokkeerd op hetzelfde apparaat, waardoor extra aanvallers of andere malware niet op het apparaat konden worden geïmplementeerd.

In dit voorbeeld ziet u dat met mogelijkheden voor het blokkeren en inperking van gedrag, bedreigingen automatisch worden gedetecteerd, opgenomen en geblokkeerd.

## <a name="next-steps"></a>Volgende stappen

- [Meer informatie over Defender voor Eindpunt](overview-endpoint-detection-response.md)

- [De surface reduction-regels voor aanvallen configureren](attack-surface-reduction.md)

- [De EDR in de blokmodus inschakelen](edr-in-block-mode.md)

- [Recente wereldwijde bedreigingsactiviteit bekijken](https://www.microsoft.com/wdsi/threats)

- [Een overzicht van Microsoft 365 Defender](../defender/microsoft-365-defender.md)
