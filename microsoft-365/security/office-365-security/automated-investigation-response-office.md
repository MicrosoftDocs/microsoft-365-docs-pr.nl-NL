---
title: Automatisch onderzoek en antwoord werken in Microsoft Defender voor Office 365
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
ms.date: 11/05/2020
description: Nagaan hoe automatisch onderzoek en antwoord mogelijkheden werken in Microsoft Defender voor Office 365
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: 5ca9ea941d073c7b199678631a9063cfbeae8907
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/14/2021
ms.locfileid: "49864898"
---
# <a name="how-automated-investigation-and-response-works-in-microsoft-defender-for-office-365"></a>Automatisch onderzoek en antwoord werken in Microsoft Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Wanneer beveiligingswaarschuwingen worden geactiveerd, kunt u het beste uw beveiligingsteam raadplegen met deze waarschuwingen en de stappen ondernemen om uw organisatie te beveiligen. Soms kunnen beveiligingsactiviteiten teams overspoeld zijn door het volume van waarschuwingen dat wordt geactiveerd. Met geautomatiseerd onderzoek en antwoord mogelijkheden in Microsoft Defender voor Office 365 kunt u hulp krijgen.

AIR zorgt ervoor dat uw beveiligingsteam efficiënter en effectiever functioneert. De lucht mogelijkheden zijn geautomatiseerde onderzoek processen in antwoord naar bekende bedreigingen die vandaag zijn. Juiste herstelacties wachten op goedkeuring, zodat het team van uw beveiligingsactiviteiten kan reageren op gedetecteerde bedreigingen.

In dit artikel wordt beschreven hoe lucht met een aantal voorbeelden werkt. Wanneer u klaar bent om aan de slag te gaan met lucht, raadpleegt u [automatisch onderzoek en reageren op bedreigingen](office-365-air.md).

- [Voorbeeld 1: een door een gebruiker gemeld phishing-bericht opent een onderzoek Playbook](#example-a-user-reported-phish-message-launches-an-investigation-playbook)
- [Voorbeeld 2: een beveiligingsbeheerder activeert een onderzoek vanuit de Threat Explorer](#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)
- [Voorbeeld 3: een team van beveiligingsactiviteiten is lucht geïntegreerd met hun SIEM met behulp van de Office 365 Management Activity API](#example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api)

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>Voorbeeld: een door een gebruiker gemelde phishing-bericht opent een onderzoek Playbook

Stel dat een gebruiker in uw organisatie een e-mailbericht ontvangt waarvan de persoon een malafide e-mailbericht is. De gebruiker die is getraind voor het melden van dergelijke berichten, gebruikt de [invoegtoepassing bericht melden](enable-the-report-message-add-in.md) of de [invoegtoepassing](enable-the-report-phish-add-in.md) voor het melden van een e-mail naar Microsoft voor analyse. De opdracht verzenden wordt ook naar uw systeem verzonden en wordt weergegeven in Explorer in de weergave ingediende **items** (voorheen de door de **gebruiker gerapporteerde** weergave genoemd). Daarnaast wordt in het door de gebruiker gerapporteerde bericht nu een informatiesysteem geactiveerd waarmee onderzoek automatisch wordt gestart.

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
- Een controle wordt uitgevoerd via Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) en ([Microsoft Defender for Office 365](office-365-atp.md)) om te zien of er andere soortgelijke berichten door gebruikers worden gerapporteerd.
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

Een organisatie heeft bijvoorbeeld onlangs een manier voor het weergeven van het team van de gebruikers gemelde phishing-waarschuwingen die al door de lucht zijn verwerkt. Met hun oplossing worden relevante waarschuwingen geïntegreerd met de SIEM-server van de organisatie en de bewerkings systemen van de organisatie. Met deze oplossing wordt het aantal fouterende negatieven sterk beperkt, zodat het team van de beveiliging de tijd en de inspanning van concrete bedreigingen kan richten. Voor meer informatie over deze aangepaste oplossing raadpleegt u [tech Community Blog: Verbeter de effectiviteit van uw Soc met Microsoft Defender voor Office 365 en de O365-beheer API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).

## <a name="next-steps"></a>Volgende stappen

- [Aan de slag met lucht](office-365-air.md)

- [Ga naar het Microsoft 365-wegwijzer om te zien wat er is gepland en uitgebracht is binnenkort](https://www.microsoft.com/microsoft-365/roadmap?filters=)

- [Meer informatie over geautomatiseerde functies voor onderzoek en antwoorden in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
