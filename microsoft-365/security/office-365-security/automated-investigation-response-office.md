---
title: Geautomatiseerd onderzoek en antwoord (AIR) in Office 365
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
ms.collection: M365-security-compliance
description: Krijg een overzicht van geautomatiseerde onderzoeks- en reactiemogelijkheden in Office 365 Advanced Threat Protection Plan 2.
ms.custom: air
ms.openlocfilehash: 420143a6a2888900cdc128b22f7b0bcb05adad27
ms.sourcegitcommit: 2859c82b30ae9cbd3a3e4bcdebd65f18444f1a9e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/18/2020
ms.locfileid: "42826401"
---
# <a name="automated-investigation-and-response-air-in-office-365"></a>Geautomatiseerd onderzoek en antwoord (AIR) in Office 365

Als beveiligingswaarschuwingen worden geactiveerd, is het aan uw beveiligingsteam om deze waarschuwingen te bekijken en stappen te ondernemen om uw organisatie te beschermen. Soms kunnen beveiligingsteams zich overweldigd voelen door het aantal waarschuwingen dat wordt geactiveerd. Automatische air-mogelijkheden (Investigation and Response) in Office 365 kunnen u helpen. AIR stelt uw beveiligingsteam in staat om efficiënter en effectiever te werken. Air-mogelijkheden omvatten geautomatiseerde onderzoeksprocessen in reactie op bekende bedreigingen die vandaag de dag bestaan. De juiste herstelacties wachten op goedkeuring, zodat uw beveiligingsteam kan reageren op gedetecteerde bedreigingen. 

Dit artikel geeft een overzicht van AIR. Zie Automatisch onderzoeken en reageren op [bedreigingen in Office 365](office-365-air.md)wanneer u klaar bent om aan de slag te gaan met AIR.

## <a name="at-a-high-level"></a>Op een hoog niveau

Als waarschuwingen worden geactiveerd, worden beveiligingsplaybooks van kracht. Afhankelijk van de situatie kan een [geautomatiseerd onderzoeksproces](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) beginnen. Tijdens en na een geautomatiseerd onderzoek worden [herstelacties](air-remediation-actions.md) aanbevolen. Er worden niet automatisch acties uitgevoerd in Office 365 Advanced Threat Protection. Uw beveiligingsteam controleert en [keurt vervolgens elke herstelactie goed of weigert](air-review-approve-pending-completed-actions.md)deze , en wanneer dit is gedaan, wordt elk onderzoek voltooid. Al deze activiteiten worden bijgehouden en zichtbaar in het Office 365 Security & Compliance Center (zie [Details van een onderzoek weergeven).](air-view-investigation-results.md#view-details-of-an-investigation)

In de volgende secties vindt u meer informatie over waarschuwingen, beveiligingsplaybooks en voorbeelden van AIR in actie.

## <a name="alerts"></a>Waarschuwingen

[Waarschuwingen](../../compliance/alert-policies.md#viewing-alerts) vertegenwoordigen triggers voor beveiligingswerkstromen voor beveiligingsbewerkingen voor incidentrespons. Het prioriteren van de juiste set waarschuwingen voor onderzoek, terwijl ervoor zorgen dat bedreigingen niet worden aangepakt, is een uitdaging. Wanneer onderzoeken naar waarschuwingen handmatig worden uitgevoerd, moeten security operations-teams entiteiten (zoals inhoud, apparaten en gebruikers) op jagen en correleren die risico lopen op bedreigingen. Dergelijke taken en workflows kunnen zeer tijdrovend zijn en meerdere tools en systemen omvatten. Met AIR worden onderzoek en respons voor Office 365-beveiligingsgebeurtenissen geautomatiseerd door dat belangrijke waarschuwingen voor beveiligings- en bedreigingsbeheer automatisch playbooks voor beveiligingsreacties activeren. 

Momenteel voor AIR worden waarschuwingen die worden gegenereerd uit de volgende soorten waarschuwingsbeleid automatisch onderzocht:  

- Er is een mogelijk kwaadaardige URL-klik gedetecteerd
- E-mail gerapporteerd door gebruiker als phish*
- E-mailberichten met malware verwijderd na levering*
- E-mailberichten met phish-URL's die na levering zijn verwijderd*
- Verdachte e-mailverzendpatronen gedetecteerd #
- Gebruiker beperkt van het verzenden van e-mail #

> [!NOTE]
> Aan de waarschuwingen met een sterretje (*) wordt een *informatieve* ernst toegewezen in het desbetreffende waarschuwingsbeleid binnen het Security & Compliance Center, waarbij e-mailmeldingen zijn uitgeschakeld. E-mailmeldingen kunnen worden ingeschakeld via [de configuratie van het waarschuwingsbeleid.](../../compliance/alert-policies.md#alert-policy-settings) Waarschuwingen die zijn gemarkeerd met een hash (#) zijn algemeen beschikbare waarschuwingen die zijn gekoppeld aan openbare preview-playbooks.

Als u waarschuwingen wilt weergeven, kiest u in het Beveiligings- & Compliance Center de optie **Waarschuwingen** > **weergeven.** Selecteer een waarschuwing om de details te bekijken en gebruik vanaf daar de koppeling **Onderzoek bekijken** om naar het desbetreffende [onderzoek](air-view-investigation-results.md#investigation-graph)te gaan.  

> [!NOTE]
> Informatieve waarschuwingen worden standaard verborgen in de waarschuwingsweergave. Als u ze wilt zien, wijzigt u het waarschuwingsfilter om informatieve waarschuwingen op te nemen.

Als uw organisatie uw beveiligingswaarschuwingen beheert via een waarschuwingsbeheersysteem, servicebeheersysteem of SIEM-systeem (Security Information and Event Management), u Office 365-waarschuwingen naar dat systeem verzenden via een e-mailmelding of via de [Office 365 Management Activity API.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference) De meldingen van waarschuwingen voor onderzoek via e-mail of API bevatten koppelingen om toegang te krijgen tot de waarschuwingen in het Security & Compliance Center, zodat de toegewezen beveiligingsbeheerder snel naar het onderzoek kan navigeren.

![Waarschuwingen die verband houden met onderzoeken](../../media/air-alerts-page-details.png) 

## <a name="security-playbooks"></a>Beveiligingsplaybooks

Playbooks voor beveiliging zijn back-endbeleid dat centraal staat in de automatisering van Office Advanced Threat Protection en Microsoft Threat Protection. De beveiligingsplaybooks in AIR zijn gebaseerd op veelvoorkomende echte beveiligingsscenario's en zijn ontwikkeld op basis van feedback van Security Operations-teams. Een beveiligingsplaybook wordt automatisch gestart wanneer specifieke waarschuwingen binnen uw organisatie worden geactiveerd. Zodra de waarschuwing wordt geactiveerd, wordt het bijbehorende draaiboek uitgevoerd door het Air-systeem (Automated Investigation and Response). Het onderzoek wordt uitgevoerd door analyse van de waarschuwing op basis van het draaiboek van die specifieke waarschuwing, kijkend naar alle bijbehorende metagegevens (inclusief e-mailberichten, gebruikers, onderwerpen, afzenders, enz.). Op basis van de bevindingen van het onderzoeksplaybook beveelt AIR een reeks acties aan die het beveiligingsteam van uw organisatie kan ondernemen om de dreiging te beheersen en te beperken. 

De beveiligingsplaybooks die je met AIR krijgt, zijn ontworpen om de meest voorkomende bedreigingen aan te pakken die organisaties vandaag de dag tegenkomen met e-mail. Ze zijn gebaseerd op input van Security Operations- en Incident Response-teams, inclusief degenen die microsoft en de activa van onze klanten helpen verdedigen.

### <a name="security-playbooks-are-rolling-out-in-phases"></a>Beveiligingsplaybooks worden gefaseerd uitgerold

Als onderdeel van AIR worden veiligheidsplaybooks gefaseerd uitgerold. Fase 1 is nu algemeen beschikbaar en bevat verschillende playbooks die aanbevelingen bevatten voor acties die beveiligingsbeheerders kunnen controleren en goedkeuren:
- Door de gebruiker gerapporteerdphishbericht
- URL klik vonnis wijzigen
- Malware gedetecteerd na levering (Malware ZAP)
- Phish gedetecteerd post-delivery ZAP (Phish ZAP)

Fase 1 bevat ook ondersteuning voor door de beheerder geactiveerde e-mailonderzoeken (met Behulp van [Threat Explorer).](threat-explorer.md)

Fase 2 is nu vooruitgang met de volgende playbooks in **openbare preview,** met aanbevelingen voor acties en het helpen van beveiligingsbeheerders bij het onderzoeken van problemen:
- Gebruiker gerapporteerd als gecompromitteerd (openbare preview)

Verdere playbooks zullen worden vrijgegeven als ze zijn voltooid. Bezoek de [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) om te zien wat er nog meer is gepland en binnenkort.

### <a name="playbooks-include-investigation-and-recommendations"></a>Playbooks bevatten onderzoek en aanbevelingen

In AIR bevat elk beveiligingsdraaiboek: 
- een root-onderzoek van de entiteiten van een e-mail (bestanden, URL's, ontvangers, IP-adressen, enz.),
- verder op zoek naar soortgelijke e-mails ontvangen door de organisatie 
- stappen die zijn genomen om andere potentiële bedreigingen te identificeren en te correleren, en 
- aanbevolen acties voor het herstellen van bedreigingen.

Elke stap op hoog niveau bevat een aantal substappen die worden uitgevoerd om een diep, gedetailleerd en uitputtend antwoord op bedreigingen te bieden.

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>Voorbeeld: Een door de gebruiker gerapporteerd phish-bericht lanceert een onderzoeksplaybook

Wanneer een gebruiker in uw organisatie een e-mailbericht indient en rapporteert aan Microsoft met behulp van de [invoegtoepassing Rapportbericht voor Outlook of Outlook Web App,](enable-the-report-message-add-in.md)wordt het rapport ook naar uw systeem verzonden en is het zichtbaar in Explorer in de weergave Door gebruikers gerapporteerde weergave. Dit door de gebruiker gerapporteerde bericht activeert nu een systeemgebaseerde informatieve waarschuwing, die automatisch het onderzoeksplaybook start.

Tijdens de wortelonderzoeksfase worden verschillende aspecten van de e-mail beoordeeld. Deze omvatten:
- Een bepaling over wat voor soort bedreiging het zou kunnen zijn;
- Wie heeft het verzonden;
- Waar de e-mail is verzonden vanuit (verzendende infrastructuur);
- Of andere exemplaren van de e-mail zijn bezorgd of geblokkeerd;
- Een beoordeling van onze analisten;
- Of de e-mail is gekoppeld aan bekende campagnes;
- en meer.

Nadat het hoofdonderzoek is voltooid, bevat het draaiboek een lijst met aanbevolen acties die u moet uitvoeren op de oorspronkelijke e-mail en entiteiten die eraan zijn gekoppeld.
  
Vervolgens worden verschillende dreigingsonderzoeken en jachtstappen uitgevoerd:

- Vergelijkbare e-mailberichten worden geïdentificeerd via zoekopdrachten in het e-mailcluster.
- Het signaal wordt gedeeld met andere platforms, zoals [Microsoft Defender ATP.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- Een bepaling wordt gemaakt over de vraag of gebruikers hebben geklikt via een kwaadaardige links in verdachte e-mailberichten.
- Er wordt gecontroleerd in Office 365 Exchange Online Protection[(EOP)](exchange-online-protection-eop.md)en Office 365 Advanced Threat Protection[(ATP)](office-365-atp.md)om te zien of er andere soortgelijke berichten zijn gerapporteerd door gebruikers.
- Een controle wordt gedaan om te zien of een gebruiker is gecompromitteerd. Met deze controle worden signalen in Office 365, [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)en Azure Active [Directory](https://docs.microsoft.com/azure/active-directory)gecontroleerd, waarbij eventuele gerelateerde afwijkingen van gebruikersactiviteiten worden aangetast. 

Tijdens de jachtfase worden risico's en bedreigingen toegewezen aan verschillende jachtstappen. 

Herstel is de laatste fase van het draaiboek. In deze fase worden saneringsmaatregelen genomen op basis van de onderzoeks- en jachtfasen. 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>Voorbeeld: een beveiligingsbeheerder activeert een onderzoek vanuit Threat Explorer

Naast automatische onderzoeken die worden geactiveerd door een waarschuwing, kan het beveiligingsteam van uw organisatie een automatisch onderzoek starten vanuit een weergave in [Threat Explorer.](threat-explorer.md)

Stel dat u gegevens in Explorer over door gebruikers gerapporteerde berichten bekijkt. U een item selecteren in de lijst met resultaten en vervolgens in het actiemenu op **Onderzoek** klikken (ervan uitgaande dat u over de juiste herstelmachtigingen beschikt).

![Door de gebruiker gerapporteerde berichten in Explorer met knop Onderzoeken](../../media/Explorer-UserReported-Investigate.png)

Stel dat u gegevens over gedetecteerde e-mailberichten bekijkt die malware bevatten en dat er verschillende e-mailberichten zijn gedetecteerd die malware bevatten. U het tabblad **E-mail** selecteren, een of meer e-mailberichten selecteren en vervolgens in het menu **Acties** de optie **Onderzoeken selecteren**. 

![Een onderzoek starten naar malware in Explorer](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

Net als bij playbooks die worden geactiveerd door een waarschuwing, bevatten automatische onderzoeken die vanuit een weergave in Explorer worden geactiveerd een root-onderzoek, stappen om bedreigingen te identificeren en te correleren en aanbevolen acties om deze bedreigingen te beperken.

## <a name="next-steps"></a>Volgende stappen

- [Aan de slag met AIR in Office 365](office-365-air.md)

- [Bezoek de Microsoft 365 Roadmap om te zien wat er binnenkort komt en uitrol](https://www.microsoft.com/microsoft-365/roadmap?filters=)

