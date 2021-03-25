---
title: Ga naar het Actiecentrum om herstelacties te zien
description: Het actiecentrum gebruiken om details en resultaten weer te geven na een geautomatiseerd onderzoek
keywords: actie, centreren, autoir, geautomatiseerd, onderzoek, antwoord, herstel
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.date: 01/28/2021
ms.technology: mde
ms.openlocfilehash: af9e9315088a8dd5da9740b33135551d28664ed7
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186111"
---
# <a name="visit-the-action-center-to-see-remediation-actions"></a>Ga naar het Actiecentrum om herstelacties te zien

Tijdens en na een geautomatiseerd onderzoek worden herstelacties voor bedreigingsdetecties geïdentificeerd. Afhankelijk van de specifieke bedreiging en de configuratie van [Microsoft Defender voor](https://docs.microsoft.com/windows/security/threat-protection) Eindpunt voor uw organisatie, worden sommige herstelacties automatisch genomen en moeten andere worden goedgekeurd. Als u deel uitmaakt van het beveiligingsteam van uw organisatie, kunt u in behandeling zijnde en voltooide herstelacties bekijken [in](manage-auto-investigation.md#remediation-actions) het **Actiecentrum.** 


**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="new-a-unified-action-center"></a>(NIEUW!) Een geïntegreerd actiecentrum


We zijn blij om een nieuw, geïntegreerd actiecentrum aan te kondigen ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) )!

:::image type="content" source="images/mde-action-center-unified.png" alt-text="Actiecentrum in microsoft 365-beveiligingscentrum":::

In de volgende tabel wordt het nieuwe, geïntegreerde actiecentrum vergeleken met het vorige Actiecentrum.

|Het nieuwe, geïntegreerde actiecentrum  |Het vorige actiecentrum  |
|---------|---------|
|Lijsten in behandeling en voltooide acties voor apparaten en e-mail op één locatie <br/>([Microsoft Defender voor Eindpunt](microsoft-defender-endpoint.md) plus Microsoft Defender voor Office [365](https://docs.microsoft.com/microsoft-365/security/defender-365-security/office-365-atp))|Lijsten in behandeling en voltooide acties voor apparaten <br/> ([Alleen Microsoft Defender voor eindpunt)](microsoft-defender-endpoint.md)   |
|Bevindt zich op:<br/>[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)         |Bevindt zich op:<br/>[https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)     |
| Kies actiecentrum in het Microsoft **365-beveiligingscentrum.** <p>:::image type="content" source="images/action-center-nav-new.png" alt-text="Navigeren naar het Actiecentrum in het Microsoft 365-beveiligingscentrum"::: | Kies in het Microsoft Defender-beveiligingscentrum de optie **Geautomatiseerde onderzoeken**  >  **Actiecentrum**. <p>:::image type="content" source="images/action-center-nav-old.png" alt-text="Navigeren naar het Actiecentrum vanuit het Microsoft Defender-beveiligingscentrum":::  |

Het geïntegreerde actiecentrum brengt herstelacties samen in Defender voor Eindpunt en Defender voor Office 365. Het definieert een gemeenschappelijke taal voor alle herstelacties en biedt een geïntegreerde onderzoekservaring. 

U kunt het geïntegreerde actiecentrum gebruiken als u de juiste machtigingen en een of meer van de volgende abonnementen hebt:
- [Defender voor Eindpunt](microsoft-defender-endpoint.md)
- [Defender voor Office 365](https://docs.microsoft.com/microsoft-365/security/defender-365-security/office-365-atp)
- [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) 

> [!TIP]
> Zie Vereisten voor meer [informatie.](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites)

## <a name="using-the-action-center"></a>Het actiecentrum gebruiken

Ga als eerste naar het geïntegreerde Actiecentrum in het verbeterde Microsoft 365-beveiligingscentrum:
1. Ga naar het Microsoft 365-beveiligingscentrum [https://security.microsoft.com](https://security.microsoft.com) () en meld u aan.
2. Selecteer actiecentrum in het **navigatiedeelvenster.** 

Wanneer u het Actiecentrum bezoekt, ziet u twee tabbladen: **Acties in behandeling** en **Geschiedenis.** De volgende tabel bevat een overzicht van wat u op elk tabblad ziet:

|Tab  |Beschrijving  |
|---------|---------|
|**In behandeling**     | Hiermee wordt een lijst weergegeven met acties die aandacht vereisen. U kunt acties één voor één goedkeuren of weigeren of meerdere acties selecteren als ze hetzelfde type actie hebben (zoals **Quarantainebestand).** <br/>**TIP:** Controleer en keur in behandeling zijnde acties zo snel mogelijk goed [(of weiger)](manage-auto-investigation.md) zodat uw geautomatiseerde onderzoeken tijdig kunnen worden voltooid. |
|**Geschiedenis**     | Fungeert als een auditlogboek voor acties die zijn uitgevoerd, zoals: <br/>- Herstelacties die zijn ondernomen als gevolg van geautomatiseerde onderzoeken <br>- Herstelacties die zijn goedgekeurd door uw beveiligingsteam  <br/>- Opdrachten die zijn uitgevoerd en herstelacties die zijn toegepast tijdens livereactiesessies  <br/>- Herstelacties die zijn ondernomen door functies voor bedreigingsbeveiliging in Microsoft Defender Antivirus  <p>Biedt een manier om bepaalde acties ongedaan te maken (zie [Voltooide acties ongedaan maken).](manage-auto-investigation.md#undo-completed-actions)       |

U kunt gegevens aanpassen, sorteren, filteren en exporteren in het Actiecentrum.

:::image type="content" source="images/new-action-center-columnsfilters.png" alt-text="Kolommen en filters in het actiecentrum":::

- Selecteer een kolomkoppen om items in oplopende of aflopende volgorde te sorteren.
- Gebruik het tijdsperiodefilter om gegevens voor de afgelopen dag, week, 30 dagen of 6 maanden weer te geven.
- Kies de kolommen die u wilt weergeven.
- Geef op hoeveel items u wilt opnemen op elke pagina met gegevens.
- Gebruik filters om alleen de items te bekijken die u wilt zien.
- Selecteer **Exporteren om** resultaten te exporteren naar een CSV-bestand. 

## <a name="next-steps"></a>Volgende stappen

- [Herstelacties weergeven en goedkeuren](manage-auto-investigation.md)
- [Zie de interactieve handleiding: Bedreigingen onderzoeken en corrigeren met Microsoft Defender voor Eindpunt](https://aka.ms/MDATP-IR-Interactive-Guide)
 
## <a name="see-also"></a>Zie ook

- [False positives/negatives in Microsoft Defender for Endpoint adresseert](defender-endpoint-false-positives-negatives.md)
