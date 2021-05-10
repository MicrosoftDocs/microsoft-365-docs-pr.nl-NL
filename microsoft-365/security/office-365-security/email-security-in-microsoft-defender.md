---
title: E-mailbeveiliging met Threat Explorer in Microsoft Defender voor Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Malware phishingpogingen bekijken en onderzoeken.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a2a6d3d10cfa21c0ad2da948bff130cb9336ebd8
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297621"
---
# <a name="email-security-with-threat-explorer-in-microsoft-defender-for-office-365"></a>E-mailbeveiliging met Threat Explorer in Microsoft Defender voor Office 365

In dit artikel:

- [Malware weergeven die is gedetecteerd in e-mail](#view-malware-detected-in-email)
- [Phishing-URL weergeven en op vonnisgegevens klikken](#view-phishing-url-and-click-verdict-data)
- [Geautomatiseerde onderzoeken en antwoorden starten](#start-automated-investigation-and-response)

> [!NOTE]
> Dit maakt deel uit van een reeks van drie artikelen over **Threat Explorer (Explorer),** **e-mailbeveiliging** **en** explorer- en **realtimedetecties** (zoals verschillen tussen de hulpprogramma's en machtigingen die nodig zijn om ze te kunnen gebruiken). De andere twee artikelen in deze reeks zijn [Bedreigingsjacht in Threat Explorer](threat-hunting-in-threat-explorer.md) en Threat Explorer en de basisbeginselen van [realtimedetecties.](real-time-detections.md) 

In dit artikel wordt uitgelegd hoe u malware- en phishingpogingen kunt bekijken en onderzoeken die worden gedetecteerd in e-mail door Microsoft 365 beveiligingsfuncties. 

**Van toepassing op**

- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

## <a name="view-malware-detected-in-email"></a>Malware weergeven die is gedetecteerd in e-mail

Als u malware wilt zien die is gedetecteerd in e-mail die is gesorteerd op Microsoft 365 technologie, gebruikt u de weergave E-mail [> Malware](threat-explorer-views.md#email--malware) van Explorer (of Realtime detecties). Malware is de standaardweergave, dus deze kan worden geselecteerd zodra u Verkenner opent.

1. Kies in & Beveiligingscentrum <https://protection.office.com> () **de** optie Threat Management \> **Explorer** (of **Realtime detecties).** (In dit voorbeeld wordt Verkenner gebruikt.) Als u zich in het geconvergeerde beveiligingscentrum Microsoft 365 ( https://security.microsoft.com/) schuif naar **E-mail & Explorer samenwerking**  >  .

   Vanaf hier begint u bij de weergave, kiest u een bepaald tijdsbestek om het te onderzoeken (indien nodig) en richt u de filters op de [verkenner.](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through)

2. Kies in **het** menu Beeld de optie **E-mail** \> **malware.**

   > [!div class="mx-imgBorder"]
   > ![Menu Weergeven voor Explorer](../../media/ExplorerViewEmailMalwareMenu.png)

3. Klik **op Afzender** en kies vervolgens **Basisdetectietechnologie.** \> 

   Uw detectietechnologieën zijn nu beschikbaar als filters voor het rapport.

   > [!div class="mx-imgBorder"]
   > ![Technologieën voor malwaredetectie](../../media/ExplorerEmailMalwareDetectionTech.png)

4. Kies een optie. Selecteer vervolgens de **knop Vernieuwen** om dat filter toe te passen.

   > [!div class="mx-imgBorder"]
   > ![Geselecteerde detectietechnologie](../../media/ExplorerEmailMalwareDetectionTechATP.png)

   Het rapport wordt vernieuwd om de resultaten weer te geven die malware heeft gedetecteerd in e-mail, met de technologieoptie die u hebt geselecteerd. Hier kunt u verdere analyse uitvoeren. 

## <a name="view-phishing-url-and-click-verdict-data"></a>Phishing-URL weergeven en op vonnisgegevens klikken

U kunt phishingpogingen via URL's in e-mail bekijken, inclusief een lijst met URL's die zijn toegestaan, geblokkeerd en overschrijven. Als u URL's wilt identificeren waar op is geklikt, [Safe koppelingen](safe-links.md) moeten worden geconfigureerd. Zorg ervoor dat u het beleid Safe [koppelingen](set-up-safe-links-policies.md) in te stellen voor time-of-click beveiliging en logboekregistratie van klik-uitspraken door Safe koppelingen.

Als u phish-URL's in berichten wilt bekijken en op URL's in phish-berichten wilt klikken, gebruikt u de weergave [ **E-mail**  >  **phish**](threat-explorer-views.md#email--phish) van Explorer of realtime detecties.

1. Kies in & Beveiligingscentrum <https://protection.office.com> () **de** optie Threat Management \> **Explorer** (of **Realtime detecties).** (In dit voorbeeld wordt Verkenner gebruikt.)

2. Kies in **het** menu Beeld de optie **E-mail** \> **phish**.

   > [!div class="mx-imgBorder"]
   > ![Menu Weergeven voor Explorer in phishing-context](../../media/ExplorerViewEmailPhishMenu.png)

3. Klik **op Afzender** en kies **URL's Klik** op \> **vonnis.**

4. Selecteer een of meer opties, zoals **Geblokkeerd** en Geblokkeerd,  en selecteer vervolgens de knop Vernieuwen op dezelfde regel als de opties om dat filter toe te passen. (Vernieuw het browservenster niet.)

   > [!div class="mx-imgBorder"]
   > ![URL's en klik op vonnissen](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

   Het rapport wordt vernieuwd om twee verschillende URL-tabellen weer te geven op het tabblad URL onder het rapport:

   - **Top-URL's** zijn de URL's in de berichten die u hebt gefilterd en de actie voor e-mailbezorging telt voor elke URL. In de phish-e-mailweergave bevat deze lijst meestal legitieme URL's. Aanvallers bevatten een combinatie van goede en slechte URL's in hun berichten om te proberen ze bezorgd te krijgen, maar ze maken de schadelijke koppelingen interessanter. De tabel met URL's wordt gesorteerd op totaal aantal e-mail, maar deze kolom is verborgen om de weergave te vereenvoudigen.

   - **De bovenste klikken** zijn de Safe url's met koppelingen die zijn geklikt, gesorteerd op het totale aantal klikken. Deze kolom wordt ook niet weergegeven, om de weergave te vereenvoudigen. Het totaal aantal per kolom geeft aan Safe aantal klikken op vonnissen voor elke geklikte URL. In de phish-e-mailweergave zijn dit meestal verdachte of schadelijke URL's. Maar de weergave kan URL's bevatten die geen bedreigingen zijn, maar in phish-berichten staan. URL-klikken op niet-uitpakte koppelingen worden hier niet weergegeven.

   De twee URL-tabellen bevatten de beste URL's in phishing-e-mailberichten op bezorgingsactie en locatie. In de tabellen worden URL-klikken weergegeven die ondanks een waarschuwing zijn geblokkeerd of bezocht, zodat u kunt zien welke mogelijke slechte koppelingen aan gebruikers zijn gepresenteerd en waar de gebruikers op hebben geklikt. Hier kunt u verdere analyse uitvoeren. Onder de grafiek ziet u bijvoorbeeld de bovenste URL's in e-mailberichten die zijn geblokkeerd in de omgeving van uw organisatie.

   > [!div class="mx-imgBorder"]
   > ![Explorer-URL's die zijn geblokkeerd](../../media/ExplorerPhishClickVerdictURLs.png)

   Selecteer een URL om meer gedetailleerde informatie weer te geven.

   > [!NOTE]
   > In het dialoogvenster URL-flyout wordt het filteren op e-mailberichten verwijderd om de volledige weergave van de blootstelling van de URL in uw omgeving weer te geven. Hiermee kunt u filteren op e-mailberichten waar u zich zorgen over maakt in Verkenner, specifieke URL's zoeken die potentiële bedreigingen zijn en vervolgens uw inzicht in de blootstelling aan URL's in uw omgeving uitbreiden (via het dialoogvenster URL-details) zonder URL-filters toe te voegen aan de Verkenner-weergave zelf.

### <a name="interpretation-of-click-verdicts"></a>Interpretatie van click-vonnissen

In de fly-outs E-mail of URL, TopKlikken en in onze filterervaringen ziet u verschillende waarden voor klikuitspraken:

- **Geen:** Kan de uitspraak voor de URL niet vastleggen. De gebruiker heeft mogelijk door de URL geklikt.
- **Toegestaan:** De gebruiker mocht naar de URL navigeren.
- **Geblokkeerd:** De gebruiker is geblokkeerd om naar de URL te navigeren.
- **Vonnis in behandeling:** De gebruiker heeft de pagina met detonatie in behandeling.
- **Geblokkeerde overschrijven:** De gebruiker is geblokkeerd om rechtstreeks naar de URL te navigeren. Maar de gebruiker overdroeed het blok om naar de URL te navigeren.
- **Vonnis in behandeling is omzeild:** De gebruiker kreeg de detonatiepagina te zien. Maar de gebruiker overdroeed het bericht om toegang te krijgen tot de URL.
- **Fout:** De gebruiker heeft de foutpagina te zien of er is een fout opgetreden bij het vastleggen van de uitspraak.
- **Fout:** Er is een onbekende uitzondering opgetreden tijdens het vastleggen van de uitspraak. De gebruiker heeft mogelijk door de URL geklikt.

## <a name="start-automated-investigation-and-response"></a>Geautomatiseerde onderzoeken en antwoorden starten

> [!NOTE]
> Geautomatiseerde onderzoeks- en antwoordmogelijkheden zijn beschikbaar in *Microsoft Defender voor Office 365 Plan 2* en Office 365 *E5.*

[Geautomatiseerde onderzoeken en antwoorden kunnen](automated-investigation-response-office.md) uw teamtijd en inspanning voor beveiligingsactiviteiten besparen bij het onderzoeken en verminderen van cyberaanvallen. Naast het configureren van waarschuwingen die een beveiligingss playbook kunnen activeren, kunt u een geautomatiseerd onderzoek en antwoordproces starten vanuit een weergave in Explorer. Zie Voorbeeld: Een beveiligingsbeheerder activeert een onderzoek [vanuit Verkenner voor meer informatie.](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)

## <a name="other-articles"></a>Andere artikelen

[E-mailberichten onderzoeken met de pagina E-mailentiteit](mdo-email-entity-page.md)
