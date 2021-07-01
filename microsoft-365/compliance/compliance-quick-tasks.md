---
title: Snelle taken om aan de slag te gaan met Microsoft 365-compliance
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- m365-security-compliance
- m365initiative-compliance
localization_priority: Normal
description: Meer informatie over taken die u helpen snel aan de slag te gaan met compliance in Microsoft 365.
ms.openlocfilehash: 61a057c3666faae51a012dd9db2d4c63ded0f77a
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227257"
---
# <a name="quick-tasks-for-getting-started-with-microsoft-365-compliance"></a>Snelle taken om aan de slag te gaan met Microsoft 365-compliance

Als u nieuw bent in het Microsoft 365 en u zich afvraagt waar u moet beginnen, bevat dit artikel richtlijnen over de basisbeginselen en geeft u prioriteit aan belangrijke compliancetaken. In dit artikel kunt u snel aan de slag met het beheren en bewaken van uw gegevens, het beschermen van informatie en het minimaliseren van insiderrisico's.

Dit artikel is ook handig als u wilt weten hoe u risico's het beste kunt beheren, uw gegevens kunt beschermen en voldoet aan de voorschriften en standaarden met een nieuw personeel op afstand. Werknemers werken nu op nieuwe manieren samen en verbinden zich met elkaar. Dit betekent dat uw bestaande complianceprocessen en -besturingselementen mogelijk moeten worden aangepast. Het identificeren en beheren van deze nieuwe compliancerisico's binnen uw organisatie is essentieel voor het beschermen van uw gegevens en het minimaliseren van bedreigingen en risico's.

Nadat u deze basis compliancetaken hebt voltooid, kunt u de compliancedekking in uw organisatie uitbreiden door extra Microsoft 365 complianceoplossingen te implementeren.

## <a name="task-1-configure-compliance-permissions"></a>Taak 1: Nalevingsmachtigingen configureren

Het is belangrijk om te beheren wie in uw organisatie toegang heeft tot de Microsoft 365-compliancecentrum inhoud te bekijken en beheertaken uit te voeren. Microsoft 365 bevat beheerrollen die specifiek zijn voor naleving en voor het gebruik van de hulpmiddelen die zijn opgenomen in de Microsoft 365-compliancecentrum.

Begin met het toewijzen van compliancemachtigingen aan de personen in uw organisatie, zodat ze deze taken kunnen uitvoeren en om te voorkomen dat onbevoegden toegang hebben tot gebieden buiten hun verantwoordelijkheid. U moet ervoor zorgen dat u de juiste personen  hebt toegewezen aan  de compliancegegevensbeheerder en de beheerdersrollen voor compliance voordat u complianceoplossingen gaat configureren en implementeren die zijn opgenomen in Microsoft 365. U moet ook gebruikers toewijzen aan de Azure Active Directory globale lezerrol om gegevens weer te geven in Compliance Manager.

Zie Machtigingen in het Beveiligings- & [Compliancecentrum voor stapsgewijse](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)richtlijnen voor het configureren van machtigingen en het toewijzen van personen aan beheerdersrollen.

## <a name="task-2-know-your-state-of-compliance"></a>Taak 2: Uw nalevingstoestand kennen

Het is moeilijk om te weten waar u naartoe moet als u niet weet waar u bent. Als u aan uw nalevingsbehoeften voldoet, moet u inzicht krijgen in uw huidige risiconiveau en welke updates mogelijk nodig zijn in deze steeds veranderende tijden. Of uw organisatie nu nieuw is met nalevingsvereisten of een diepgaande ervaring heeft met standaarden en voorschriften die van toepassing zijn op uw branche, het beste wat u kunt doen om de naleving te verbeteren, is om te begrijpen waar uw organisatie staat.

[Microsoft Compliance Manager](compliance-manager.md) kan u helpen de nalevingsstatus van uw organisatie te begrijpen en gebieden te markeren die mogelijk moeten worden verbeterd. Compliance Manager gebruikt een gecentraliseerde dashboard om een risicogebaseerd score te berekenen, waarmee u uw voortgang bij het uitvoeren van acties meet die de risico's rond gegevensbescherming en regelgeving helpen beperken. U kunt compliancebeheer ook gebruiken als hulpmiddel om al uw risicobeoordelingen bij te houden. Het biedt werkstroommogelijkheden waarmee u uw risicobeoordelingen efficiënt kunt voltooien via een gemeenschappelijk hulpmiddel.

Zie Aan de slag met Compliance Manager voor stapsgewijs richtlijnen om aan de slag te gaan met Compliance [Manager.](compliance-manager-setup.md)

> [!IMPORTANT]
> Beveiliging en compliance zijn nauw geïntegreerd voor de meeste organisaties. Het is belangrijk dat uw organisatie zich richt op basisgebieden voor beveiliging, bedreigingsbeveiliging en identiteits- en toegangsbeheer, zodat u een diepgaande benadering van beveiliging en compliance kunt bieden.
>
> Controleer uw [Microsoft 365 Secure Score](../security/defender/microsoft-secure-score.md) in het Microsoft 365 beveiligingscentrum en voltooi de taken die in de volgende artikelen worden beschreven:
>
> - [Routekaart voor beveiliging : topprioriteiten voor de eerste 30 dagen, 90 dagen en daarna](../security/office-365-security/security-roadmap.md)
> - [De 12 belangrijkste taken voor beveiligingsteams ter ondersteuning van thuis werken](../security/top-security-tasks-for-remote-work.md)

## <a name="task-3-enable-auditing-for-your-organization"></a>Taak 3: Controle voor uw organisatie inschakelen

Nu u de huidige status van uw organisatie hebt bepaald en wie compliancefuncties kan beheren, is de volgende stap ervoor te zorgen dat u de gegevens hebt om complianceonderzoeken uit te voeren en rapporten te genereren voor netwerk- en gebruikersactiviteiten in uw organisatie. Het inschakelen van auditing is ook een belangrijke voorwaarde voor complianceoplossingen die verder in dit artikel worden beschreven.

Insights in het auditlogboek zijn een waardevol hulpmiddel om uw compliancevereisten aan te passen aan oplossingen waarmee u compliancegebieden kunt beheren en controleren die moeten worden verbeterd. Auditlogboekregistratie moet zijn ingeschakeld voordat activiteiten worden opgenomen en voordat u in het auditlogboek kunt zoeken. Wanneer deze functie is ingeschakeld, wordt de activiteit van de gebruiker en beheerder van uw organisatie opgenomen in het auditlogboek en bewaard voor 90 dagen en maximaal één jaar, afhankelijk van de licentie die aan gebruikers is toegewezen.

Zie Zoeken in auditlogboek in- of uitschakelen voor stapsgewijs instructies voor het in- of [uitschakelen van controlelogboek.](turn-audit-log-search-on-or-off.md)

## <a name="task-4-create-policies-to-alert-you-about-potential-compliance-issues"></a>Taak 4: Beleid maken om u te waarschuwen voor mogelijke complianceproblemen

Microsoft biedt verschillende ingebouwde waarschuwingsbeleidsregels om misbruik van beheerdersmachtigingen, malwareactiviteit, potentiële externe en interne bedreigingen en risico's voor informatiebeheer te identificeren. Dit beleid is standaard ingeschakeld, maar mogelijk moet u aangepaste waarschuwingen configureren om nalevingsvereisten te beheren die specifiek zijn voor uw organisatie.

Gebruik hulpmiddelen voor waarschuwingsbeleid en waarschuwingsdashboards om aangepaste waarschuwingsbeleidsregels te maken en de waarschuwingen weer te geven die worden gegenereerd wanneer gebruikers activiteiten uitvoeren die voldoen aan de beleidsvoorwaarden. Enkele voorbeelden hiervan zijn het gebruik van waarschuwingsbeleid voor het bijhouden van activiteiten van gebruikers en beheerders die van invloed zijn op nalevingsvereisten, machtigingen en incidenten met gegevensverlies in uw organisatie.

Zie Waarschuwingsbeleid in het beveiligings- en compliancecentrum voor stapsgewijs richtlijnen voor het maken van aangepaste [waarschuwingsbeleid.](alert-policies.md)

## <a name="task-5-classify-and-protect-sensitive-data"></a>Taak 5: gevoelige gegevens classificeren en beveiligen

Om hun werk af te krijgen, werken personen in uw organisatie samen met anderen binnen de organisatie, maar ook met externe personen. Dit betekent dat de inhoud niet langer achter een firewall blijft. De inhoud kan overal worden gebruikt, op verschillende apparaten, apps en services. Wanneer de inhoud elders wordt gebruikt, wilt u dat dat gebeurt in een veilige, beschermde manier die voldoet aan het bedrijfs- en nalevingsbeleid van uw organisatie.

[Met gevoeligheidslabels](sensitivity-labels.md) kunt u de gegevens van uw organisatie classificeren en beveiligen, terwijl u ervoor zorgt dat de productiviteit van gebruikers en de mogelijkheid om samen te werken niet wordt gehinderd. Gebruik gevoeligheidslabels om versleuteling af te dwingen en gebruiksbeperkingen visuele markeringen toe te passen en informatie te beveiligen op platforms en apparaten, on-premises en in de cloud.

Zie Aan de slag met gevoeligheidslabels voor stapsgewijse richtlijnen voor het configureren en gebruiken van [gevoeligheidslabels.](get-started-with-sensitivity-labels.md) Zie voor informatie over gevoeligheidslabellicenties [Microsoft 365 richtlijnen voor beveiligings- & naleving.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)

## <a name="task-6-configure-a-retention-policy"></a>Taak 6: Een bewaarbeleid configureren

Met [een bewaarbeleid](retention.md) kunt u proactief bepalen of u inhoud wilt behouden, inhoud of beide wilt verwijderen. Vervolgens kunt u de inhoud behouden en verwijderen aan het einde van een opgegeven bewaarperiode. Deze acties kunnen nodig zijn om te voldoen aan branchevoorschriften en interne beleidsregels, en om uw risico's te beperken in geval van rechtszaken of een inbreuk op de beveiliging.

Wanneer inhoud is onderworpen aan een bewaarbeleid, kunnen personen de inhoud blijven bewerken en bewerken alsof er niets is gewijzigd. De inhoud blijft behouden op de oorspronkelijke locatie. Maar als iemand inhoud bewerkt of verwijdert die onderworpen is aan het bewaarbeleid, wordt een kopie van de oorspronkelijke inhoud opgeslagen op een veilige locatie waar deze wordt bewaard terwijl het bewaarbeleid voor die inhoud van kracht is.

U kunt snel een bewaarbeleid voeren voor meerdere locaties in uw Microsoft 365-omgeving, zoals Exchange-e-mail, SharePoint-sites, OneDrive-accounts en Microsoft 365-groepen. Er zijn geen limieten voor het aantal postvakken of sites dat dit beleid automatisch kan bevatten. Maar als u selectiever wilt worden, kunt u dit doen door een bewaarbeleid voor specifieke locaties te configureren en sites of gebruikers op te nemen of uit te sluiten.

Zie Bewaarbeleid maken en configureren voor stapsgewijs richtlijnen voor het configureren van een [bewaarbeleid.](create-retention-policies.md) Zie [Aan de slag met bewaarbeleid en retentielabels](get-started-with-retention.md) als het configureren van retentie in Microsoft 365 nieuw voor u is.

## <a name="task-7-configure-sensitive-information-and-offensive-language-policies"></a>Taak 7: Gevoelige informatie en aanstootgevend taalbeleid configureren

Het beschermen van gevoelige informatie en het opsporen en optreden bij incidenten met pesterijen op het werk is een belangrijk onderdeel van de naleving van interne beleidsregels en standaarden. [Communicatie-naleving](communication-compliance-feature-reference.md) in Microsoft 365 helpt deze risico's te minimaliseren door u te helpen snel herstelacties voor e-mail en communicatie Microsoft Teams detecteren, vastleggen en uitvoeren. Deze omvatten ongepaste communicatie met grof taalgebruik, bedreigingen en pesterijen en communicatie die gevoelige informatie binnen en buiten uw organisatie deelt.

Met een vooraf *gedefinieerde* beleidssjabloon Aanstootgevende taal en beleid tegen pesten kunt u interne en externe communicatie scannen op beleidsafgetalen, zodat deze kunnen worden onderzocht door aangewezen revisoren. Revisoren kunnen gescande e-mail, Microsoft Teams, Yammer of communicatie van derden in uw organisatie onderzoeken en passende herstelacties uitvoeren om ervoor te zorgen dat ze voldoen aan de standaarden van uw organisatie.

Met de  vooraf gedefinieerde sjabloon Voor gevoelige informatiebeleid kunt u snel een beleid maken voor het scannen van e-mail en Microsoft Teams-communicatie met gedefinieerde gevoelige informatietypen of trefwoorden om ervoor te zorgen dat belangrijke gegevens niet worden gedeeld met personen die geen toegang mogen hebben. Deze activiteiten kunnen ongeautoriseerde communicatie over vertrouwelijke projecten of branchespecifieke regels voor handel met voorkennis of andere collusieactiviteiten omvatten.

Zie [Plan](communication-compliance-plan.md) voor communicatie compliance en Aan de slag met communicatie compliance voor stapsgewijs richtlijnen voor het plannen en configureren van [communicatie compliance.](communication-compliance-configure.md) Zie voor informatie over communicatie [compliancelicenties Microsoft 365 richtlijnen voor beveiligings- & naleving.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-compliance)

## <a name="task-8-see-whats-happening-with-your-sensitive-items"></a>Taak 8: bekijk wat er gebeurt met uw gevoelige items

Gevoeligheidslabels, gevoelige informatietypen, bewaarlabels en beleidsregels en trainbare classificaties kunnen worden gebruikt om gevoelige items in Exchange, SharePoint en OneDrive te classificeren en labelen, zoals u in de vorige taken hebt gezien. De laatste stap in uw snelle taakreis is om te zien welke items zijn gelabeld en welke acties uw gebruikers uitvoeren op deze gevoelige items. [inhoudsverkenner](data-classification-content-explorer.md) [en activiteitenverkenner](data-classification-activity-explorer.md) bieden deze zichtbaarheid.

### <a name="content-explorer"></a>Inhoudsverkenner
 Met Inhoudsverkenner kunt u in de eigen indeling alle items bekijken die zijn geclassificeerd als een vertrouwelijk informatietype of die behoren tot een bepaalde classificatie door een trainbare classificatie, evenals alle items met een gevoeligheids- of bewaarlabel.

Zie Uw gegevens [kennen -](data-classification-overview.md)overzicht van gegevensclassificatie en Aan de slag met inhoudsverkenner voor stapsgewijse richtlijnen voor het gebruik [van inhoudsverkenner.](data-classification-content-explorer.md)

### <a name="activity-explorer"></a>Activiteitenverkenner
Met Activity Explorer kunt u controleren wat er wordt gedaan met uw geclassificeerde en gelabelde gevoelige items in:
- SharePoint
- Exchange
- OneDrive

Er zijn meer dan 30 verschillende filters beschikbaar voor gebruik, sommige zijn:

- datumbereik
- activiteitstype
- locatie
- gebruiker
- gevoeligheidslabel
- bewaarlabel
- bestandspad
- DLP-beleid

Zie Aan de slag met [activiteitenverkenner](data-classification-activity-explorer.md)voor stapsgewijse richtlijnen voor het gebruik van activiteitenverkenner.

## <a name="next-steps"></a>Volgende stappen

Nu u de basisbeginselen voor compliancebeheer voor uw organisatie hebt geconfigureerd, kunt u de volgende complianceoplossingen in Microsoft 365 gebruiken om gevoelige informatie te beschermen en aanvullende insiderrisico's op te sporen en op te treden.

### <a name="configure-retention-labels"></a>Bewaarlabels configureren

Hoewel bewaarbeleid op containerniveau van toepassing is op locaties zoals SharePoint-sites [](retention.md#retention-labels) en Exchange-postvakken, kunnen bewaarlabels specifiekere targeting toepassen voor uw bewaar- en verwijderingsbeleid. Bijvoorbeeld op het niveau van het document of e-mailbericht dat eindgebruikers handmatig kunnen toepassen naast automatische toepassing door beheerders. U kunt ook een bewaarlabel toepassen op een documentbibliotheek, map of documentset in SharePoint, zodat alle documenten die op die locatie zijn opgeslagen, het standaard bewaarlabel overnemen.

Bovendien ondersteunen bewaarlabels [het beheer van records om](records-management.md) inhoud als record te markeren. Wanneer dit gebeurt, worden op het etiket extra beperkingen opgelegd aan de inhoud die mogelijk nodig is om uw organisatie te helpen voldoen aan wettelijke vereisten.

Zie de volgende richtlijnen voor stapsgewijs richtlijnen voor het maken en publiceren van bewaarlabels:
- [Retentielabels maken en deze toepassen in apps](create-apply-retention-labels.md)
- [Een retentielabel automatisch toepassen op inhoud](apply-retention-labels-automatically.md)

Zie Aan de slag met recordbeheer om aan de slag te gaan met [recordsbeheer.](get-started-with-records-management.md)

### <a name="identify-and-define-sensitive-information-types"></a>Gevoelige informatietypen identificeren en definiëren

Definieer gevoelige informatietypen op basis van het patroon in gegevens in de gegevens van uw organisatie. Gebruik [ingebouwde typen gevoelige informatie om](./sensitive-information-type-entity-definitions.md) creditcardnummers, bankrekeningnummers, paspoortnummers en meer te identificeren en te beveiligen. Of maak uw eigen [specifieke gegevenstypen voor](create-a-custom-sensitive-information-type.md) aangepaste gevoeligheid voor uw organisatie.

Zie Een aangepast type gevoelige informatie maken in het beveiligings- & compliancecentrum voor stapsgewijse richtlijnen voor het definiëren [van aangepaste gevoelige informatietypen.](./create-a-custom-sensitive-information-type.md)

### <a name="prevent-data-loss"></a>Verlies van gegevens voorkomen

[Met DLP-beleid (Data Loss Prevention)](dlp-learn-about-dlp.md) kunt u gevoelige informatie identificeren, controleren en automatisch beveiligen in uw Microsoft 365 organisatie. Gebruik DLP-beleid om gevoelige items in verschillende Microsoft-services te identificeren, het onbedoeld delen van gevoelige items te voorkomen en gebruikers te helpen te leren hoe ze compatibel kunnen blijven zonder hun werkstroom te onderbreken.

Voor stapsgewijs richtlijnen voor het configureren van DLP-beleid, maakt, test en stemt u [een DLP-beleid af.](create-test-tune-dlp-policy.md) Zie voor informatie over licentiegegevens voor gegevensverliesbeheer Microsoft 365 richtlijnen voor [beveiligings- & naleving.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#office-365-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business)

### <a name="detect-and-act-on-insider-risks"></a>Insiderrisico's detecteren en handelen

Werknemers hebben steeds meer toegang tot het maken, beheren en delen van gegevens in een breed spectrum van platforms en services. In de meeste gevallen beschikken organisaties over beperkte resources en hulpmiddelen om risico's in de hele organisatie te identificeren en te beperken, terwijl ze ook voldoen aan nalevingsvereisten en privacystandaarden voor werknemers. Deze risico's kunnen gegevensdiefstal zijn door vertrekkende werknemers en gegevenslekken van informatie buiten uw organisatie door onbedoelde oversharing of schadelijke bedoelingen.

[Insider risk management](insider-risk-management-policies.md) in Microsoft 365 gebruikt de volledige breedte van service- en externe indicatoren om u te helpen snel risicovolle gebruikersactiviteiten te identificeren, te triagen en te handelen. Met behulp van logboeken van Microsoft 365 en Microsoft Graph kunt u met insiderrisicobeheer specifieke beleidsregels definiëren om risico-indicatoren te identificeren en actie te ondernemen om deze risico's te beperken.

Zie [Plan voor](insider-risk-management-plan.md) insider risk management en Aan de slag met insider risk management voor stapsgewijs richtlijnen voor het plannen en configureren van beleid voor [insiderrisicobeheer.](insider-risk-management-configure.md) Zie voor informatie over [insider-risicobeheerlicenties Microsoft 365 richtlijnen voor beveiligings- & naleving.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#insider-risk-management)