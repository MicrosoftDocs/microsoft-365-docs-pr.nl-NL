---
title: Details en resultaten van een geautomatiseerd onderzoek
description: Tijdens en na een geautomatiseerd onderzoek kunt u de resultaten en belangrijkste bevindingen bekijken
keywords: geautomatiseerd, onderzoek, resultaten, analyseren, details, herstel, autoair
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 02/02/2021
ms.openlocfilehash: c11d9cd1ce4c2ca49315ec62b51c23ef981555f4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059925"
---
# <a name="details-and-results-of-an-automated-investigation"></a>Details en resultaten van een geautomatiseerd onderzoek

**Van toepassing op:**
- Microsoft Defender for Endpoint

Wanneer een geautomatiseerd onderzoek wordt [](automated-investigations.md) uitgevoerd met Microsoft Defender for Endpoint, zijn details over dat onderzoek beschikbaar, zowel tijdens als na het geautomatiseerde onderzoeksproces. Als u de benodigde machtigingen hebt, kunt u deze details bekijken in een weergave met onderzoeksdetails. De weergave onderzoeksdetails biedt u de actuele status en de mogelijkheid om eventuele in behandeling zijnde acties goed te keuren. 

## <a name="new-unified-investigation-page"></a>(NIEUW!) Geïntegreerde onderzoekspagina

De onderzoekspagina is onlangs bijgewerkt met informatie op uw apparaten, e-mail en samenwerkingsinhoud. De nieuwe, geïntegreerde onderzoekspagina definieert een gemeenschappelijke taal en biedt een geïntegreerde ervaring voor automatische onderzoeken in [Microsoft Defender](microsoft-defender-advanced-threat-protection.md) voor Eindpunt en Microsoft Defender voor [Office 365.](/microsoft-365/security/defender-365-security/office-365-atp) 

> [!TIP]
> Zie (NIEUW!) voor meer informatie over wat er [verandert. Geïntegreerde onderzoekspagina](/microsoft-365/security/mtp/mtp-autoir-results).

## <a name="open-the-investigation-details-view"></a>De weergave onderzoeksdetails openen

U kunt de weergave onderzoeksdetails openen met behulp van een van de volgende methoden:
- [Een item selecteren in het actiecentrum](#select-an-item-in-the-action-center)
- [Een onderzoek selecteren op een pagina met details van incidenten](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a>Een item selecteren in het actiecentrum

Het verbeterde [Actiecentrum bevat](auto-investigation-action-center.md) [herstelacties](manage-auto-investigation.md#remediation-actions) op uw apparaten, e-mail en & samenwerkingsinhoud en identiteiten. In de lijst opgenomen acties zijn herstelacties die automatisch of handmatig zijn genomen. In het Actiecentrum kunt u acties bekijken die wachten op goedkeuring en acties die al zijn goedgekeurd of voltooid. U kunt ook naar meer details navigeren, zoals een onderzoekspagina.

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

1. Ga naar [https://security.microsoft.com](https://security.microsoft.com) en meld u aan. 
2. Kies in het navigatiedeelvenster de optie **Incidenten & waarschuwingen**  >  **Incidenten**. 
3. Selecteer een item in de lijst en kies vervolgens **Incidentpagina openen.**
4. Selecteer het **tabblad Onderzoeken** en selecteer vervolgens een onderzoek in de lijst. Het deelvenster Flyout wordt geopend.
5. Selecteer **Onderzoekspagina openen.** 

## <a name="investigation-details"></a>Details van het onderzoek

Gebruik de weergave onderzoeksdetails om eerdere, huidige en in behandeling zijnde activiteiten met betrekking tot een onderzoek te bekijken. De weergave onderzoeksdetails lijkt op de volgende afbeelding:

In de weergave Details van onderzoek kunt u informatie zien op de tabbladen **Onderzoek**,  **Waarschuwingen**, Apparaten , **Identiteiten**, **Belangrijke** bevindingen **,** Entiteiten , **Logboek** en Acties in behandeling , beschreven in de volgende tabel. 

> [!NOTE]
> De specifieke tabbladen die u op een pagina met onderzoeksdetails ziet, zijn afhankelijk van wat uw abonnement bevat. Als uw abonnement bijvoorbeeld geen Microsoft Defender voor Office 365-abonnement 2 bevat, ziet u geen tabblad **Postvakken.**

| Tab | Beschrijving |
|:--------|:--------|
| **Onderzoeksgrafiek**   | Geeft een visuele weergave van het onderzoek. Hiermee worden entiteiten en lijsten weergegeven die zijn gevonden, samen met waarschuwingen en of er nog acties moeten worden goedgekeurd.<br/>U kunt een item in de grafiek selecteren om meer details weer te geven. Als u bijvoorbeeld het pictogram **Bewijs** selecteert, gaat u naar het tabblad Bewijs, waar u gedetecteerde entiteiten en hun vonnissen kunt zien.  |
| **Waarschuwingen**    | Hiermee worden waarschuwingen vermeld die aan het onderzoek zijn gekoppeld. Waarschuwingen kunnen afkomstig zijn van functies voor bedreigingsbeveiliging op het apparaat van een gebruiker, in Office-apps, Cloud App-beveiliging en andere Microsoft 365 Defender-functies.|
| **Apparaten** | Hiermee worden apparaten vermeld die zijn opgenomen in het onderzoek, samen met het herstelniveau. (Herstelniveaus komen overeen met het [automatiseringsniveau voor apparaatgroepen](automation-levels.md).) |
| **Postvakken** |Hiermee worden postvakken vermeld die worden beïnvloed door gedetecteerde bedreigingen.  |
| **Gebruikers**  | Hiermee worden gebruikersaccounts vermeld die worden beïnvloed door gedetecteerde bedreigingen. |
| **Bewijs** | Hier worden stukken bewijs vermeld die door waarschuwingen/onderzoeken worden opgesmeld. Bevat vonnissen *(Kwaadaardige,* *Verdachte* of *Geen gevonden bedreigingen)* en herstelstatus. |
| **Entiteiten**  | Bevat details over elke geanalyseerde entiteit, inclusief een uitspraak voor elk entiteitstype *(Schadelijk,* *Verdacht* of Geen *gevonden bedreigingen).*|
|**Logboek**    | Geeft een chronologische, gedetailleerde weergave van alle onderzoekacties die zijn ondernomen nadat een waarschuwing is geactiveerd.|
| **Acties in behandeling** | Hiermee worden items vermeld waarvoor goedkeuring is vereist. Ga naar het Actiecentrum [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () om acties in behandeling goed te keuren. |

## <a name="see-also"></a>Zie ook

- [Herstelacties na een geautomatiseerd onderzoek controleren](manage-auto-investigation.md)
- [De wachtrij Microsoft Defender voor eindpuntincidenten weergeven en organiseren](view-incidents-queue.md)