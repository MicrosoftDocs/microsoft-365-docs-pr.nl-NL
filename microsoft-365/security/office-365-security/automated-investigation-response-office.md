---
title: Hoe automatisch onderzoek en antwoorden werken in Microsoft Defender voor Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
keywords: automated incident response, investigation, remediation, threat protection
ms.date: 01/29/2021
description: Bekijk hoe geautomatiseerde onderzoeks- en antwoordmogelijkheden werken in Microsoft Defender voor Office 365
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 97cc2f6bcb066ff2d6f64254add3a57eb27b8828
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142547"
---
# <a name="how-automated-investigation-and-response-works-in-microsoft-defender-for-office-365"></a>Hoe automatisch onderzoek en antwoorden werken in Microsoft Defender voor Office 365

Wanneer beveiligingswaarschuwingen worden geactiveerd, is het aan uw team voor beveiligingsactiviteiten om naar deze waarschuwingen te kijken en stappen te ondernemen om uw organisatie te beschermen. Soms kunnen teams met beveiligingsbewerkingen overstelpt worden door het aantal waarschuwingen dat wordt geactiveerd. Mogelijkheden voor automatisch onderzoek en reactie (AIR) in Microsoft Defender voor Office 365 kunnen u helpen.

Met AIR kan uw team voor beveiligingsactiviteiten efficiënter en efficiënter werken. AIR-mogelijkheden omvatten geautomatiseerde onderzoeksprocessen in reactie op bekende bedreigingen die op dit moment bestaan. Juiste herstelacties wachten op goedkeuring, zodat het team met beveiligingsbewerkingen kan reageren op gedetecteerde bedreigingen.

In dit artikel wordt beschreven hoe AIR werkt aan de hand van verschillende voorbeelden. Wanneer u klaar bent om aan de slag te gaan met AIR, bekijkt u Automatisch onderzoeken en [reageren op bedreigingen.](office-365-air.md)

- [Voorbeeld 1: Met een door de gebruiker gemeld phish-bericht wordt een playbook voor onderzoek gestart](#example-a-user-reported-phish-message-launches-an-investigation-playbook)
- [Voorbeeld 2: Een beveiligingsbeheerder activeert een onderzoek vanuit Bedreigingsverkenner](#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)
- [Voorbeeld 3: Een team voor beveiligingsbewerkingen integreert AIR met hun SIEM met behulp van de Office 365 Management Activity-API](#example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api)

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>Voorbeeld: Een door de gebruiker gerapporteerde phish-bericht start een playbook voor onderzoek

Stel dat een gebruiker in uw organisatie een e-mailbericht ontvangt dat hij of zij een poging tot phishing lijkt te doen. De gebruiker die is opgeleid voor het rapporteren van dergelijke berichten, gebruikt de [invoegapp](enable-the-report-message-add-in.md) Bericht rapporteren of de [invoegapp Phishing melden](enable-the-report-phish-add-in.md) om deze naar Microsoft te verzenden voor analyse. De inzending wordt ook naar uw systeem  verzonden en is zichtbaar in Verkenner in de weergave Voorzendingen (voorheen de weergave door de gebruiker **gerapporteerd).** Bovendien activeert het door de gebruiker gerapporteerde bericht nu een op het systeem gebaseerde informatiemelding, waarmee automatisch het playbook voor onderzoek wordt gestart.

Tijdens de hoofdonderzoeksfase worden verschillende aspecten van de e-mail geëvalueerd. Dit zijn onder andere de volgende aspecten:

- Een beslissing over welk type bedreiging het zou kunnen zijn;
- Wie heeft het verzonden;
- Vanaf welke plaats de e-mail is verzonden (infrastructuur voor verzenden);
- Of andere exemplaren van het e-mailbericht zijn bezorgd of geblokkeerd;
- Een beoordeling van onze analisten;
- Of het e-mailbericht is gekoppeld aan bekende campagnes:
- en meer.

Nadat het hoofdonderzoek is voltooid, bevat de playbook een lijst met aanbevolen acties die kunnen worden ondernomen voor het oorspronkelijke e-mailbericht en de entiteiten die ermee zijn verbonden.

Vervolgens worden verschillende bedreigingsonderzoeken en zoekstappen uitgevoerd:

- Vergelijkbare e-mailberichten worden geïdentificeerd via zoekopdrachten in e-mailclusters.
- Het signaal wordt gedeeld met andere platforms, zoals [Microsoft Defender voor Eindpunt.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- Er wordt een beslissing genomen over het al dan niet klikken op schadelijke koppelingen in verdachte e-mailberichten.
- Er wordt een controle uitgevoerd in Exchange Online Protection[(EOP)](exchange-online-protection-overview.md)en (Microsoft Defender voor[Office 365)](office-365-atp.md)om te zien of er andere soortgelijke berichten zijn gerapporteerd door gebruikers.
- Er wordt een controle uitgevoerd om te zien of een gebruiker is gehackt. Deze controle maakt gebruik van signalen in Office 365, [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)en Azure Active [Directory,](https://docs.microsoft.com/azure/active-directory)die een verband houden met gerelateerde activiteitsactiviteit van gebruikers.

Tijdens de zoekfase worden risico's en bedreigingen toegewezen aan diverse zoekstappen.

Herstel is de laatste fase van het playbook. Tijdens deze fase worden herstelstappen ondernomen op basis van het onderzoek en de zoekfasen.

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>Voorbeeld: een beveiligingsbeheerder activeert een onderzoek vanuit Bedreigingsverkenner

Naast automatische onderzoeken die worden geactiveerd door een waarschuwing, kan het team voor beveiligingsbewerkingen van uw organisatie een geautomatiseerd onderzoek activeren vanuit een weergave in [Bedreigingsverkenner.](threat-explorer.md)  Voor dit onderzoek wordt ook een waarschuwing gemaakt, zodat Microsoft Defender-incidenten en externe SIEM-hulpprogramma's kunnen zien dat dit onderzoek is geactiveerd.

Stel dat u de weergave **Malware** in Verkenner gebruikt. Met de tabbladen onder de grafiek selecteert u het **tabblad E-mail.** Als u een of meer items in de lijst selecteert, wordt de **knop +** Acties geactiveerd.

![Verkenner met geselecteerde berichten](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

Via **het** menu Acties kunt u Onderzoek **activeren selecteren.**

![Menu Acties voor geselecteerde berichten](../../media/explorer-malwareview-selectedemails-actions.jpg)

Net zoals playbooks die zijn geactiveerd door een waarschuwing, omvatten automatische onderzoeken die worden geactiveerd vanuit een weergave in Verkenner een hoofdonderzoek, stappen om bedreigingen te identificeren en te correleren en aanbevolen acties om deze bedreigingen te beperken.

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a>Voorbeeld: een team voor beveiligingsbewerkingen integreert AIR met hun SIEM met behulp van de Office 365 Management Activity API

AIR-mogelijkheden in Microsoft Defender voor Office 365 bevatten rapporten met & [details](air-view-investigation-results.md) die teams voor beveiligingsbewerkingen kunnen gebruiken om bedreigingen te bewaken en aan te pakken. Maar u kunt AIR-mogelijkheden ook integreren met andere oplossingen. Voorbeelden hiervan zijn een SIEM-systeem (Security Information and Event Management), een case management system of een aangepaste rapportageoplossing. Deze soorten integraties kunnen worden uitgevoerd met behulp van de Management Activity API van [Office 365.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)

Onlangs heeft een organisatie bijvoorbeeld een manier ingesteld voor hun team voor beveiligingsbewerkingen om door gebruikers gerapporteerde phish-waarschuwingen te bekijken die al door AIR zijn verwerkt. De oplossing integreert relevante waarschuwingen met de SIEM-server van de organisatie en het case management-systeem. Met de oplossing wordt het aantal fout-positieven aanzienlijk beperkt, zodat het team voor beveiligingsbewerkingen de tijd en inspanning kan richten op echte bedreigingen. Zie het blog van de Tech Community voor meer informatie over deze aangepaste oplossing: Verbeter de effectiviteit van uw SOC met Microsoft Defender voor Office 365 en de [O365 Management-API.](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)

## <a name="next-steps"></a>Volgende stappen

- [Aan de slag met AIR](office-365-air.md)
- [Acties in behandeling of voltooide herstelacties weergeven](air-review-approve-pending-completed-actions.md)
