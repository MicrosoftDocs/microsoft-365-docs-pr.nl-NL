---
title: Details en resultaten van een geautomatiseerd onderzoek
description: Bekijk de resultaten en belangrijkste bevindingen van geautomatiseerd onderzoek in Microsoft 365 Defender
keywords: geautomatiseerd, onderzoek, resultaten, analyseren, details, herstel, autoair
search.appverid: met150
ms.prod: m365-security
ms.technology: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.openlocfilehash: b26574c85e498209f8d0233495d3fe0e44733909
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245874"
---
# <a name="details-and-results-of-an-automated-investigation"></a>Details en resultaten van een geautomatiseerd onderzoek

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**
- Microsoft 365 Defender

Met Microsoft 365 Defender, wanneer [een](m365d-autoir.md) geautomatiseerd onderzoek wordt uitgevoerd, zijn details over dat onderzoek beschikbaar, zowel tijdens als na het geautomatiseerde onderzoeksproces. Als u de [benodigde machtigingen hebt,](m365d-action-center.md#required-permissions-for-action-center-tasks)kunt u deze details bekijken in een weergave met onderzoeksdetails. De weergave onderzoeksdetails biedt u de actuele status en de mogelijkheid om eventuele in behandeling zijnde acties goed te keuren. 

![Details van het onderzoek](../../media/mtp-air-investdetails.png)

## <a name="new-unified-investigation-page"></a>(NIEUW!) Geïntegreerde onderzoekspagina

De onderzoekspagina is onlangs bijgewerkt met informatie op uw apparaten, e-mail en samenwerkingsinhoud. De nieuwe, geïntegreerde onderzoekspagina definieert een gemeenschappelijke taal en biedt een geïntegreerde ervaring voor automatische onderzoeken in [Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) voor Eindpunt en Microsoft Defender [voor Office 365.](../office-365-security/defender-for-office-365.md) Als u toegang wilt tot de geïntegreerde onderzoekspagina, selecteert u de koppeling in de gele banner die u ziet op:
- Een onderzoekspagina in het Office 365 Beveiligings- & Compliancecentrum ( [https://protection.office.com](https://protection.office.com) )
- Een onderzoekspagina in de Microsoft Defender-beveiligingscentrum ( [https://securitycenter.windows.com](https://securitycenter.windows.com) )
- Elke incident- of actiecentrumervaring in het verbeterde Microsoft 365 beveiligingscentrum ( [https://security.microsoft.com](https://security.microsoft.com) )

## <a name="open-the-investigation-details-view"></a>De weergave onderzoeksdetails openen

U kunt de weergave onderzoeksdetails openen met behulp van een van de volgende methoden:
- [Een item selecteren in het actiecentrum](#select-an-item-in-the-action-center)
- [Een onderzoek selecteren op een pagina met details van incidenten](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a>Een item selecteren in het actiecentrum

Het verbeterde [Actiecentrum](m365d-action-center.md) () brengt herstelacties samen op uw [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) apparaten, e-mail & samenwerkingsinhoud en identiteiten. [](m365d-remediation-actions.md) In de lijst opgenomen acties zijn herstelacties die automatisch of handmatig zijn genomen. In het Actiecentrum kunt u acties bekijken die wachten op goedkeuring en acties die al zijn goedgekeurd of voltooid. U kunt ook naar meer details navigeren, zoals een onderzoekspagina.

> [!TIP]
> U moet bepaalde [machtigingen hebben om](m365d-action-center.md#required-permissions-for-action-center-tasks) acties goed te keuren, te weigeren of ongedaan te maken.

1. Ga naar [https://security.microsoft.com](https://security.microsoft.com) en meld u aan. 

2. Kies actiecentrum in het **navigatiedeelvenster.** 

3. Selecteer een item **op het** **tabblad** In behandeling of Geschiedenis. Het deelvenster Flyout wordt geopend.

4. Bekijk de informatie in het flyoutvenster en volg een van de volgende stappen:
   - Selecteer **Onderzoekspagina openen voor** meer informatie over het onderzoek.
   - Selecteer **Goedkeuren om** een actie in behandeling te starten.
   - Selecteer **Weigeren om** te voorkomen dat een actie in behandeling wordt ondernomen.
   - Selecteer **Ga op zoek om** naar Geavanceerd zoeken te [gaan.](advanced-hunting-overview.md)

### <a name="open-an-investigation-from-an-incident-details-page"></a>Een onderzoek openen vanaf een pagina met incidentgegevens

Gebruik een pagina met incidentdetails om gedetailleerde informatie over een incident weer te geven, inclusief waarschuwingen die zijn geactiveerde informatie over getroffen apparaten, gebruikersaccounts of postvakken.

![Details van incidenten](../../media/mtp-incidentdetails-tabs.png)

1. Ga naar [https://security.microsoft.com](https://security.microsoft.com) en meld u aan. 

2. Kies in het navigatiedeelvenster de optie **Incidenten & waarschuwingen**  >  **Incidenten**. 

3. Selecteer een item in de lijst en kies vervolgens **Incidentpagina openen.**

4. Selecteer het **tabblad Onderzoeken** en selecteer vervolgens een onderzoek in de lijst. Het deelvenster Flyout wordt geopend.

5. Selecteer **Onderzoekspagina openen.** 

## <a name="investigation-details"></a>Details van het onderzoek

Gebruik de weergave onderzoeksdetails om eerdere, huidige en in behandeling zijnde activiteiten met betrekking tot een onderzoek te bekijken. De weergave onderzoeksdetails lijkt op de volgende afbeelding:

![Details van het onderzoek](../../media/mtp-air-investdetails.png)

In de weergave Details van onderzoek kunt u informatie zien op de tabbladen **Onderzoek**,  **Waarschuwingen**, Apparaten , **Identiteiten**, **Belangrijke** bevindingen **,** Entiteiten , **Logboek** en Acties in behandeling , beschreven in de volgende tabel. 

> [!NOTE]
> De specifieke tabbladen die u op een pagina met onderzoeksdetails ziet, zijn afhankelijk van wat uw abonnement bevat. Als uw abonnement bijvoorbeeld geen Microsoft Defender bevat voor Office 365 abonnement 2, ziet u geen tabblad **Postvakken.**

| Tab | Omschrijving |
|:--------|:--------|
| **Onderzoeksgrafiek**   | Geeft een visuele weergave van het onderzoek. Hiermee worden entiteiten en lijsten weergegeven die zijn gevonden, samen met waarschuwingen en of er nog acties moeten worden goedgekeurd.<br/>U kunt een item in de grafiek selecteren om meer details weer te geven. Als u bijvoorbeeld het pictogram **Bewijs** selecteert, gaat u naar het tabblad Bewijs, waar u gedetecteerde entiteiten en hun vonnissen kunt zien.  |
| **Waarschuwingen**    | Hiermee worden waarschuwingen vermeld die aan het onderzoek zijn gekoppeld. Waarschuwingen kunnen afkomstig zijn van functies voor bedreigingsbeveiliging op het apparaat van een gebruiker, in Office apps, Cloud App Security en andere Microsoft 365 Defender-functies.|
| **Apparaten** | Hiermee worden apparaten vermeld die zijn opgenomen in het onderzoek, samen met het herstelniveau. (Herstelniveaus komen overeen met het [automatiseringsniveau voor apparaatgroepen](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups).) |
| **Postvakken** |Hiermee worden postvakken vermeld die worden beïnvloed door gedetecteerde bedreigingen.  |
| **Gebruikers**  | Hiermee worden gebruikersaccounts vermeld die worden beïnvloed door gedetecteerde bedreigingen. |
| **Bewijs** | Hier worden stukken bewijs vermeld die door waarschuwingen/onderzoeken worden opgesmeld. Bevat vonnissen *(Kwaadaardige,* *Verdachte* of *Geen gevonden bedreigingen)* en herstelstatus. |
| **Entiteiten**  | Bevat details over elke geanalyseerde entiteit, inclusief een uitspraak voor elk entiteitstype *(Schadelijk,* *Verdacht* of Geen *gevonden bedreigingen).*|
|**Logboek**    | Geeft een chronologische, gedetailleerde weergave van alle onderzoekacties die zijn ondernomen nadat een waarschuwing is geactiveerd.|
| **Acties in behandeling** | Hiermee worden items vermeld waarvoor goedkeuring is vereist. Ga naar het Actiecentrum [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () om acties in behandeling goed te keuren. |

## <a name="next-steps"></a>Volgende stappen

- [Herstelacties goedkeuren of weigeren na een geautomatiseerd onderzoek](m365d-autoir-actions.md)
- [Meer informatie over herstelacties](m365d-remediation-actions.md)
