---
title: Herstelacties na geautomatiseerde onderzoeken controleren
description: Herstelacties na een geautomatiseerd onderzoek controleren en goedkeuren (of weigeren).
keywords: autoir, geautomatiseerd, onderzoek, detectie, herstel, actie, in behandeling, goedgekeurd
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.date: 01/29/2021
ms.technology: mde
ms.openlocfilehash: 410972bd823c3a3c4fda53cacc225014d83f3457
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844008"
---
# <a name="review-remediation-actions-following-an-automated-investigation"></a>Herstelacties na een geautomatiseerd onderzoek controleren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


## <a name="remediation-actions"></a>Herstelacties

Wanneer een [geautomatiseerd onderzoek wordt](automated-investigations.md) uitgevoerd, wordt een vonnis gegenereerd voor elk bewijs dat wordt onderzocht. Vonnissen kunnen *Schadelijk,* *Verdacht* of *Geen bedreigingen zijn gevonden.* 

Afhankelijk van

- het type bedreiging; 
- de resulterende uitspraak, en 
- hoe de apparaatgroepen van [uw](/microsoft-365/security/defender-endpoint/machine-groups) organisatie zijn geconfigureerd, 

Herstelacties kunnen automatisch of alleen plaatsvinden na goedkeuring door het beveiligingsteam van uw organisatie. 

Hier zijn enkele voorbeelden:

- **Voorbeeld 1:** De apparaatgroepen van Fabrikam zijn ingesteld op **Volledig: herstel** bedreigingen automatisch (de aanbevolen instelling). In dit geval worden herstelacties automatisch uitgevoerd voor artefacten die worden beschouwd als schadelijk na een geautomatiseerd onderzoek (zie Voltooide acties [controleren).](#review-completed-actions)

- **Voorbeeld 2**: De apparaten van Contoso zijn opgenomen in een apparaatgroep die is ingesteld voor Semi - goedkeuring vereisen voor **eventuele herstel.** In dit geval moet het beveiligingsteam van Contoso alle herstelacties na een geautomatiseerd onderzoek controleren en goedkeuren (zie Lopende acties [controleren).](#review-pending-actions)

- **Voorbeeld 3:** Tailspin Toys heeft hun apparaatgroepen ingesteld op **Geen geautomatiseerde reactie** (niet aanbevolen). In dit geval vindt er geen geautomatiseerd onderzoek plaats. Er worden geen herstelacties ondernomen of in behandeling en er worden geen acties geregistreerd in het [Actiecentrum](/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center) voor hun apparaten (zie [Apparaatgroepen beheren).](/microsoft-365/security/defender-endpoint/machine-groups#manage-device-groups)

Of dit nu automatisch of na goedkeuring wordt gedaan, een geautomatiseerd onderzoek kan leiden tot een of meer herstelacties:
- Een bestand in quarantaine plaatsen
- Een registersleutel verwijderen 
- Een proces om te laten gaan 
- Een service stoppen 
- Een stuurprogramma uitschakelen 
- Een geplande taak verwijderen

## <a name="review-pending-actions"></a>Acties in behandeling controleren

1. Ga naar het Microsoft 365 beveiligingscentrum ( [https://security.microsoft.com](https://security.microsoft.com) ) en meld u aan.
2. Kies actiecentrum in het **navigatiedeelvenster.** 
3. Bekijk de items op het tabblad **In** behandeling. 
4. Selecteer een actie om het flyoutvenster te openen.
5. Bekijk de gegevens in het deelvenster Flyout en volg een van de volgende stappen:
   - Selecteer **Onderzoekspagina openen voor** meer informatie over het onderzoek.
   - Selecteer **Goedkeuren om** een actie in behandeling te starten.
   - Selecteer **Weigeren om** te voorkomen dat een actie in behandeling wordt ondernomen.
   - Selecteer **Ga op zoek om** naar Geavanceerd zoeken te [gaan.](advanced-hunting-overview.md) 

## <a name="review-completed-actions"></a>Voltooide acties controleren

1. Ga naar het Microsoft 365 beveiligingscentrum ( [https://security.microsoft.com](https://security.microsoft.com) ) en meld u aan.
2. Kies actiecentrum in het **navigatiedeelvenster.** 
3. Bekijk de items op het **tabblad** Geschiedenis. 
4. Selecteer een item om meer informatie over die herstelactie weer te geven.
 
## <a name="undo-completed-actions"></a>Voltooide acties ongedaan maken

Als u hebt vastgesteld dat een apparaat of bestand geen bedreiging is, kunt u herstelacties ongedaan maken die zijn ondernomen, ongeacht of deze acties automatisch of handmatig zijn ondernomen. In het actiecentrum op het tabblad **Geschiedenis** kunt u een van de volgende acties ongedaan maken:  

| Actiebron | Ondersteunde acties |
|:---|:---|
| - Geautomatiseerd onderzoek <br/>- Microsoft Defender Antivirus <br/>- Handmatige antwoordacties | - Apparaat isoleren <br/>- Codeuitvoering beperken <br/>- Een bestand in quarantaine plaatsen <br/>- Een registersleutel verwijderen <br/>- Een service stoppen <br/>- Een stuurprogramma uitschakelen <br/>- Een geplande taak verwijderen |

### <a name="to-undo-multiple-actions-at-one-time"></a>Meerdere acties tegelijk ongedaan maken

1. Ga naar het Actiecentrum [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () en meld u aan.
2. Selecteer op **het** tabblad Geschiedenis de acties die u ongedaan wilt maken. Selecteer items met hetzelfde actietype. Er wordt een flyoutvenster geopend.
3. Selecteer ongedaan maken in het deelvenster Flyout.

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>Een bestand verwijderen uit quarantaine op meerdere apparaten 

1. Ga naar het Actiecentrum [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () en meld u aan.
2. Selecteer op **het** tabblad Geschiedenis een item met het bestand Actietype **Quarantaine**.
3. Selecteer in het deelvenster Flyout de optie **Toepassen op X meer exemplaren** van dit bestand en selecteer vervolgens **Ongedaan maken.**

## <a name="automation-levels-automated-investigation-results-and-resulting-actions"></a>Automatiseringsniveaus, geautomatiseerde onderzoeksresultaten en resulterende acties

Automatiseringsniveaus bepalen of bepaalde herstelacties automatisch of alleen na goedkeuring worden ondernomen. Soms moet uw beveiligingsteam meer stappen uitvoeren, afhankelijk van de resultaten van een geautomatiseerd onderzoek. In de volgende tabel worden automatiseringsniveaus, resultaten van geautomatiseerde onderzoeken en wat u in elk geval moet doen, samengevat. 

|Instelling apparaatgroep | Geautomatiseerde onderzoeksresultaten | Wat moet u doen? |
|:---|:---|:---|
|**Volledig: herstel bedreigingen automatisch** (de aanbevolen instelling) |Er wordt een uitspraak *van Kwaadwillend* bereikt voor een bewijs. <br/><br/>De juiste herstelacties worden automatisch ondernomen. |[Voltooide acties controleren](#review-completed-actions) |
|**Volledig: herstel bedreigingen automatisch** |Er wordt een vonnis *van Verdachte* bereikt voor een bewijs. <br/><br/>Herstelacties zijn in afwachting van goedkeuring om door te gaan. | [Acties in behandeling goedkeuren (of weigeren)](#review-pending-actions) |
|**Semi - goedkeuring vereisen voor eventuele herstelmaatregelen**  |Een uitspraak van *kwaadwillend* *of* verdacht wordt bereikt voor een bewijs. <br/><br/>Herstelacties zijn in afwachting van goedkeuring om door te gaan.  |[Acties in behandeling goedkeuren (of weigeren)](#review-pending-actions) |
|**Semi - goedkeuring vereisen voor herstel van kernmappen** |Er wordt een uitspraak *van Kwaadwillend* bereikt voor een bewijs. <br/><br/>Als het artefact een bestand is of uitvoerbaar is en zich in een adreslijst van het besturingssysteem, zoals de map Windows of de map Programma-bestanden, zijn herstelacties in behandeling. <br/><br/>Als het artefact niet *in een* besturingssysteemmap staat, worden herstelacties automatisch ondernomen. |1. [In behandeling zijnde acties goedkeuren (of weigeren)](#review-pending-actions)<br/><br/>2. [Voltooide acties controleren](#review-completed-actions) |
|**Semi - goedkeuring vereisen voor herstel van kernmappen** |Er wordt een vonnis *van Verdachte* bereikt voor een bewijs. <br/><br/>Herstelacties zijn in behandeling bij goedkeuring.  |[In behandeling zijnde acties goedkeuren (of afwijzen).](#review-pending-actions)|
|**Semi - goedkeuring vereisen voor herstel van niet-tijdelijke mappen** |Er wordt een uitspraak *van Kwaadwillend* bereikt voor een bewijs. <br/><br/>Als het artefact een bestand of uitvoerbaar bestand is dat zich niet in een tijdelijke map, zoals de downloadmap of de tijdelijke map van de gebruiker, in behandeling heeft, worden herstelacties in behandeling genomen. <br/><br/>Als het artefact een bestand is of dat kan worden uitgevoerd *in* een tijdelijke map, worden herstelacties automatisch uitgevoerd.  |1. [In behandeling zijnde acties goedkeuren (of weigeren)](#review-pending-actions)<br/><br/>2. [Voltooide acties controleren](#review-completed-actions)  |
|**Semi - goedkeuring vereisen voor herstel van niet-tijdelijke mappen** |Er wordt een vonnis *van Verdachte* bereikt voor een bewijs. <br/><br/>Herstelacties zijn in behandeling bij goedkeuring. |[Acties in behandeling goedkeuren (of weigeren)](#review-pending-actions)  | 
|Een van de **volledige** of **semi-automatiseringsniveaus** |Een uitspraak van *Geen gevonden bedreigingen* wordt bereikt voor een bewijs. <br/><br/>Er worden geen herstelacties ondernomen en er worden geen acties in behandeling genomen. |[Gegevens en resultaten van een geautomatiseerd onderzoek weergeven](/microsoft-365/security/defender-endpoint/auto-investigation-action-center) |
|**Geen geautomatiseerde reactie** (niet aanbevolen)|Er worden geen geautomatiseerde onderzoeken uitgevoerd, dus er worden geen vonnissen bereikt en er worden geen herstelacties ondernomen of wachten op goedkeuring. |[Overweeg om uw apparaatgroepen in te stellen of te wijzigen om **Volledige** of **Semi-automatisering te** gebruiken](/microsoft-365/security/defender-endpoint/machine-groups) |

In Microsoft Defender voor Eindpunt worden alle vonnissen bij gehouden in het [Actiecentrum.](auto-investigation-action-center.md#new-a-unified-action-center)

## <a name="next-steps"></a>Volgende stappen

- [Meer informatie over mogelijkheden voor live-antwoorden](live-response.md)
- [Proactief op bedreigingen zoeken met geavanceerde jacht](advanced-hunting-overview.md)
- [Actie ondernemen voor fout-positieven/-negatieven in Microsoft Defender voor Eindpunt](defender-endpoint-false-positives-negatives.md)

## <a name="see-also"></a>Zie ook

- [Overzicht van geautomatiseerde onderzoeken](automated-investigations.md)
