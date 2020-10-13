---
title: Automatisch onderzoek en antwoord (lucht) overzicht
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
keywords: geautomatiseerd incident antwoord, onderzoek, herstel, bedreigings bescherming
ms.date: 09/29/2020
description: Een overzicht van geautomatiseerde functies voor onderzoek en antwoorden in Microsoft Defender voor Office 365
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: d63ba8a6d3ffb653b30448a973e1cd862631d350
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/13/2020
ms.locfileid: "48447105"
---
# <a name="an-overview-of-automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Een overzicht van automatisch onderzoek en antwoord (lucht) in Microsoft Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Wanneer beveiligingswaarschuwingen worden geactiveerd, kunt u het beste uw beveiligingsteam raadplegen met deze waarschuwingen en de stappen ondernemen om uw organisatie te beveiligen. Soms kunnen beveiligingsactiviteiten teams overspoeld zijn door het volume van waarschuwingen dat wordt geactiveerd. Met geautomatiseerd onderzoek en antwoord mogelijkheden in Microsoft Defender voor Office 365 kunt u hulp krijgen. 

AIR zorgt ervoor dat uw beveiligingsteam efficiënter en effectiever functioneert. De lucht mogelijkheden zijn geautomatiseerde onderzoek processen in antwoord naar bekende bedreigingen die vandaag zijn. Juiste herstelacties wachten op goedkeuring, zodat het team van uw beveiligingsactiviteiten kan reageren op gedetecteerde bedreigingen. 

Dit artikel bevat een overzicht van lucht. Wanneer u klaar bent om aan de slag te gaan met lucht, raadpleegt u [automatisch onderzoek en reageren op bedreigingen](office-365-air.md).

## <a name="at-a-high-level"></a>Met een hoog niveau

Wanneer waarschuwingen worden geactiveerd, wordt beveiligings playbooks naar kracht. Afhankelijk van de situatie kan een [proces voor automatisch onderzoek](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) beginnen. Tijdens en na een automatisch onderzoek worden [herstelacties](air-remediation-actions.md) aanbevolen. Er worden geen acties automatisch uitgevoerd in Microsoft Defender voor Office 365. Uw beveiligingsactiviteiten team reviseert en [keurt vervolgens elke herstelactie en keurt deze af](air-review-approve-pending-completed-actions.md). Wanneer alle acties na een onderzoek zijn goedgekeurd of afgekeurd, is het onderzoek voltooid. Al deze activiteiten worden bijgehouden en weergegeven in het Microsoft 365-Beveiligingscentrum ( [https://security.microsoft.com](https://security.microsoft.com) ). (Zie [Details van een onderzoek weergeven](air-view-investigation-results.md#view-details-of-an-investigation)voor meer informatie).

In de volgende secties vindt u meer informatie over waarschuwingen, beveiligings playbooks en voorbeelden van lucht in actie.

## <a name="alerts"></a>Waarschuwingen

[Waarschuwingen](../../compliance/alert-policies.md#viewing-alerts) vertegenwoordigen triggers voor bedrijfswerk stroom van beveiligings processen voor Incident Response. Prioriteit geven aan de juiste set waarschuwingen voor onderzoek, terwijl u er zeker van bent dat er geen bedreigingen zijn voor het ongedaan maken van problemen. Wanneer een onderzoek naar waarschuwingen handmatig wordt uitgevoerd, moeten beveiligingsbewerkingen teams de entiteiten (zoals inhoud, apparaten en gebruikers) die het risico van bedreigingen ondervinden, doorlopen en correleren. Het kan zeer lang duren voor taken en werkstromen en meerdere hulpprogramma's en systemen bestaan. Met lucht, onderzoek en reacties van beveiligingsgebeurtenissen zijn geautomatiseerde functies met waarschuwingen voor sleutelbeveiliging en risicobeheer automatisch antwoord playbooks. 

Op dit moment worden waarschuwingen die zijn gegenereerd op basis van de volgende soorten waarschuwings beleidsregels, automatisch onderzocht:  

- Er is een mogelijk schadelijke URL gevonden
- Door gebruiker gerapporteerde e-mail als phishing`*`
- E-mailberichten met malware verwijderd na levering`*`
- E-mailberichten met phishing-Url's verwijderd na levering`*`
- Verdachte e-mails voor het verzenden van patronen gedetecteerd
- Gebruiker beperkt geen e-mail verzenden
- Beheerder heeft het handmatig onderzoek van een e-mail geactiveerd`*`

> [!NOTE]
> De meldingen die zijn gemarkeerd met een sterretje ( `*` ), krijgen een *informatie over* de ernst van de informatie in het desbetreffende waarschuwings beleid binnen het Microsoft 365-Beveiligingscentrum, met meldingen per e-mail uitgeschakeld. U kunt e-mail meldingen inschakelen via [configuratie van waarschuwings beleid](../../compliance/alert-policies.md#alert-policy-settings). 

Als u waarschuwingen wilt bekijken, kiest u in het beveiligings & nalevings centrum **waarschuwingen**  >  **weergeven**. Selecteer een melding om de details ervan weer te geven en gebruik vervolgens de link **onderzoek weergeven** om naar het bijbehorende [onderzoek](air-view-investigation-results.md#investigation-graph)te gaan.  

> [!NOTE]
> Informatieve waarschuwingen zijn standaard verborgen in de weergave waarschuwingen. Als u ze wilt weergeven, wijzigt u de waarschuwingen filters, zodat informatieve meldingen worden opgenomen.

Als uw organisatie uw beveiligingswaarschuwingen beheert via een waarschuwings beheersysteem, servicebeheersysteem of beveiligings-en SIEM, kunt u via een e-mailbericht of via de [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)een melding naar dat systeem verzenden. De meldingen van onderzoek meldingen via e-mail of API bevatten koppelingen naar toegang tot waarschuwingen in het Microsoft 365 Beveiligingscentrum, zodat de toegewezen beveiligingsbeheerder snel naar het onderzoek kan navigeren.

![Waarschuwingen die zijn gekoppeld aan onderzoek](../../media/air-alerts-page-details.png) 

## <a name="security-playbooks"></a>Beveiligings playbooks

Beveiligings playbooks zijn een back-end beleid dat zich bevindt op de kern van automatisering in Microsoft Defender voor Office 365 en Microsoft Threat Protection. De beveiligings playbooks verstrekt in de lucht, gebaseerd op veelvoorkomende scenario's van realtime beveiligings scenario's en ontwikkeld op basis van feedback van beveiligingsactiviteiten teams. Een beveiligings Playbook wordt automatisch gestart wanneer bepaalde waarschuwingen binnen uw organisatie worden geactiveerd. Wanneer de signaal trigger wordt geactiveerd, wordt het bijbehorende Playbook uitgevoerd door het automatische onderzoek en het antwoord systeem. De vernieuwings stappen voor de beoordeling van de waarschuwing op basis van de Playbook, de gekoppelde metagegevens (waaronder e-mailberichten, gebruikers, onderwerpen, afzenders enzovoort). Op basis van de conclusies van het onderzoek Playbook, adviseert lucht een reeks acties te beheren die het beveiligingsteam van uw organisatie kan overnemen en de bedreiging van de bedreiging te beperken. 

De beveiligings playbooks die u met AIR ontvangt, is zo ontworpen dat de meest voorkomende bedreigingen met een e-mailadres worden geconfronteerd. De persoon maakt op basis van de invoer van beveiligingsactiviteiten en de teams-antwoord teams, waaronder mensen die Microsoft en onze klanten middelen helpen beschermen.

- Bericht met een door de gebruiker gemelde phishing
- URL: Klik op Verdict wijzigen
- Malware gedetecteerd na levering (malware ZAP)
- Phishing gevonden na levering van de geadresseerde (Phish ZAP)
- Door gebruiker gerapporteerde als gemanipuleerd 
- Handmatig e-mail onderzoek (geactiveerd door de beheerder van de gebruikers malware, phishing of alle e-mail weergave)

Meer playbooks-en Playbook-updates worden uitgebracht wanneer ze zijn voltooid. Ga naar het [Microsoft 365-wegwijzer](https://www.microsoft.com/microsoft-365/roadmap) om te zien wat er nog meer is gepland en binnenkort beschikbaar is.

### <a name="playbooks-include-investigation-and-recommendations"></a>Playbooks omvat onderzoek en aanbevelingen

In AIR bevat elke beveiligings Playbook: 

- een hoofdonderzoek van de entiteiten van een e-mailbericht (zoals bestanden, Url's, ontvangers, IP-adressen en meer).
- verdere jacht voor gelijkaardige e-mailberichten die zijn ontvangen van de organisatie 
- stappen voor het identificeren en correleren van andere potentiële bedreigingen en 
- Aanbevolen acties voor het herstel van bedreigingen.

Elke stap van hoog niveau bevat diverse substappen die worden uitgevoerd om een uitgebreide, gedetailleerde en volledige reactie te bieden aan bedreigingen.

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>Voorbeeld: een door een gebruiker gemelde phishing-bericht opent een onderzoek Playbook

Stel dat een gebruiker in uw organisatie een e-mailbericht ontvangt waarvan de persoon een malafide e-mailbericht is. De gebruiker die is getraind voor het melden van dergelijke berichten, gebruikt de [invoegtoepassing bericht melden](enable-the-report-message-add-in.md) om deze naar Microsoft te verzenden voor analyse. De opdracht verzenden wordt ook naar uw systeem verzonden en wordt weergegeven in Explorer in de weergave ingediende **items** (voorheen de door de **gebruiker gerapporteerde** weergave genoemd). Daarnaast wordt in het door de gebruiker gerapporteerde bericht nu een informatiesysteem geactiveerd waarmee onderzoek automatisch wordt gestart.

Tijdens de fase onderzoek worden verschillende aspecten van het e-mailbericht geëvalueerd. Dit zijn onder meer:

- Een bepaling van wat voor soort bedreiging het kan zijn;
- Wie heeft de persoon verzonden;
- De locatie waarvandaan de e-mail is verzonden (verzenden infrastructuur);
- Of andere e-mailberichten zijn bezorgd of geblokkeerd;
- Een beoordeling van onze analisten;
- Of het e-mailadres aan een bekende campagne is gekoppeld;
- en nog veel meer.

Wanneer het hoofdonderzoek is voltooid, biedt de Playbook een lijst met aanbevolen acties die u kunt uitvoeren met het oorspronkelijke e-mailbericht en de gekoppelde entiteiten.
  
Vervolgens worden diverse bedreigingen voor onderzoek en de jacht stappen uitgevoerd:

- Vergelijkbare e-mailberichten worden aangeduid via e-mail cluster zoekopdrachten.
- Het signaal wordt gedeeld met andere platforms, zoals [Microsoft Defender voor eindpunt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).
- U wordt bepaald of gebruikers op schadelijke koppelingen in verdachte e-mailberichten klikken.
- U kunt een controle uitvoeren via Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) en Office 365 Advanced Threat Protection ([ATP](office-365-atp.md)) om te zien of er andere soortgelijke berichten door gebruikers worden gerapporteerd.
- Als u wilt controleren of een gebruiker is aangetast. Met deze controle wordt geprofiteerd van signalen in Office 365, de beveiliging van de [Cloud-app van Microsoft](https://docs.microsoft.com/cloud-app-security)en [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), met betrekking tot afwijkingen van gebruikersactiviteiten.

Tijdens de jacht-fase worden Risico's en bedreigingen toegewezen aan diverse jacht stappen. 

Herstelfase is de laatste fase van de Playbook. Tijdens deze fase worden herstel stappen verricht, op basis van de activiteiten onderzoek en jacht. 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>Voorbeeld: een beveiligingsbeheerder activeert een onderzoek vanuit de bedreigings Verkenner

Naast geautomatiseerde onderzoeken die worden geactiveerd door een waarschuwing, kunnen het beveiligingsteam van uw organisatie een geautomatiseerd onderzoek uitvoeren via een weergave in de [bedreigings Verkenner](threat-explorer.md).  Dit onderzoek maakt ook een waarschuwing, zodat Microsoft Defender-incidenten en externe SIEM-hulpmiddelen kunnen zien dat dit onderzoek is geactiveerd. 

Stel dat u de **malware** -weergave in Verkenner gebruikt. Met de tabbladen onder de grafiek, selecteert u het tabblad **e-mail** . Als u een of meer items in de lijst selecteert, wordt de knop **+ acties** geactiveerd. 

![Verkenner met geselecteerde berichten](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

Via het menu **acties** kunt u het **onderzoek activeren**.

![Menu acties voor geselecteerde berichten](../../media/explorer-malwareview-selectedemails-actions.jpg)

Vergelijkbaar met playbooks die worden geactiveerd door een waarschuwing, zijn automatisch onderzoek die worden geactiveerd via een weergave in de Explorer een hoofdonderzoek, stappen voor het identificeren en correleren van bedreigingen en aanbevolen acties om deze bedreigingen te beperken.

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a>Voorbeeld: een team van beveiligingsactiviteiten integreert lucht met hun SIEM met behulp van de Office 365 Management Activity API

Met de functie lucht in Microsoft Defender voor Office 365 kunt u [rapporten opnemen & informatie](air-view-investigation-results.md) die teams voor beveiliging kunnen gebruiken om bedreigingen te bewaken en te verhelpen. U kunt ook lucht functies integreren met andere oplossingen. Voorbeelden hiervan zijn een beveiligings-en SIEM systeem, een aanvraag beheersysteem of een aangepaste rapportage oplossing. U kunt deze typen integraties uitvoeren met behulp van de [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference). 

Een organisatie heeft bijvoorbeeld onlangs een manier voor het weergeven van het team van de gebruikers gemelde phishing-waarschuwingen die al door de lucht zijn verwerkt. Met hun oplossing worden relevante waarschuwingen geïntegreerd met de SIEM-server van de organisatie en de bewerkings systemen van de organisatie. Met deze oplossing wordt het aantal fouterende negatieven sterk beperkt, zodat het team van de beveiliging de tijd en de inspanning van concrete bedreigingen kan richten. Voor meer informatie over deze aangepaste oplossing raadpleegt u [tech Community Blog: Verbeter de effectiviteit van uw Soc met Office 365 ATP en de O365-beheer API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).

## <a name="next-steps"></a>Volgende stappen

- [Aan de slag met lucht](office-365-air.md)

- [Ga naar het Microsoft 365-wegwijzer om te zien wat er is gepland en uitgebracht is binnenkort](https://www.microsoft.com/microsoft-365/roadmap?filters=)

- [Meer informatie over aanvullende functies voor automatisch onderzoek en antwoord in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir?view=o365-worldwide&preserve-view=true)
