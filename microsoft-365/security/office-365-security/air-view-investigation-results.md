---
title: De resultaten van een geautomatiseerd onderzoek in Office 365 weergeven
keywords: AIR, autoIR, ATP, geautomatiseerd, onderzoek, respons, sanering, bedreigingen, geavanceerd, bedreiging, bescherming
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
description: Tijdens en na een geautomatiseerd onderzoek in Office 365 u de resultaten en belangrijkste bevindingen bekijken.
ms.openlocfilehash: 104be669dcb6d22cba00974075418e2d14ed629c
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/21/2020
ms.locfileid: "42894226"
---
# <a name="details-and-results-of-an-automated-investigation-in-office-365"></a>Details en resultaten van een geautomatiseerd onderzoek in Office 365

Wanneer een [geautomatiseerd onderzoek](office-365-air.md) plaatsvindt in [Office 365 Advanced Threat Protection,](office-365-atp.md)zijn details over dat onderzoek beschikbaar tijdens en na het geautomatiseerde onderzoeksproces. Als u over de benodigde machtigingen beschikt, u deze gegevens bekijken in een weergave met onderzoeksdetails. De weergave onderzoeksdetails biedt u de up-to-date status en de mogelijkheid om alle lopende acties goed te keuren. 

## <a name="view-details-of-an-investigation"></a>Details van een onderzoek weergeven

1. Ga [https://protection.office.com](https://protection.office.com) naar en meld je aan. Dit brengt u naar het Security & Compliance Center.

2. Voer een van de volgende handelingen uit:

    - Ga naar **Threat Management** > **Dashboard**. Dit brengt u naar het [beveiligingsdashboard.](security-dashboard.md) Uw AIR-widgets worden boven aan het [beveiligingsdashboard](security-dashboard.md)weergegeven. Selecteer een widget, zoals **overzicht Onderzoeken**.

    - Ga naar **Threat Management** > **Investigations**. 

    Beide methoden brengen je naar een lijst van onderzoeken.

    ![Hoofdonderzoekspagina voor AIR](../../media/air-maininvestigationpage.png) 

3. Selecteer in de lijst met onderzoeken een item in de kolom **ID.** Dit opent de pagina met onderzoeksdetails, te beginnen met de onderzoeksgrafiek in beeld.

    ![AIR-onderzoeksgrafiekpagina](../../media/air-investigationgraphpage.png)

   Gebruik de verschillende tabbladen om meer te weten te komen over het onderzoek.

## <a name="view-details-about-an-alert-related-to-an-investigation"></a>Details weergeven over een waarschuwing met betrekking tot een onderzoek

Bepaalde soorten waarschuwingen leiden tot geautomatiseerd onderzoek in Office 365. Zie [Waarschuwingen](automated-investigation-response-office.md#alerts)voor meer informatie. Gebruik de volgende procedure om details over een waarschuwing te bekijken die is gekoppeld aan een geautomatiseerd onderzoek.

1. Ga [https://protection.office.com](https://protection.office.com) naar en meld je aan. Dit brengt u naar het Security & Compliance Center.

2. Ga naar **Threat Management** > **Investigations**.

3. Selecteer in de lijst met onderzoeken een item in de kolom **ID.** 

4. Als details van een onderzoek zijn geopend, selecteert u het tabblad **Waarschuwingen.** Alle waarschuwingen die het onderzoek hebben geactiveerd, worden hier vermeld.

5. Selecteer een item in de lijst. Er wordt een flyout geopend, met details over de waarschuwing en koppelingen naar aanvullende informatie en acties.

6. Controleer de informatie over de flyout en onderneem, afhankelijk van de specifieke waarschuwing, een actie, zoals **Oplossen,** **Onderdrukken**of **Gebruikers op de hoogte stellen**. 

    - **Oplossen** is gelijk aan het sluiten van een waarschuwing
    
    - **Onderdrukken** zorgt ervoor dat een beleid gedurende een bepaalde periode geen waarschuwingen activeert
    
    - **Gebruikers op de hoogte** stellen start een e-mail met de e-mailadressen van gebruikers die al zijn ingevoerd en stelt uw beveiligingsteam in staat om een bericht aan die gebruikers te typen. (Dit is vergelijkbaar met het verzenden van een bericht naar ontvangers met Behulp van [Threat Explorer](threat-explorer.md).)  

## <a name="how-to-use-the-various-tabs"></a>De verschillende tabbladen gebruiken

De volgende secties lopen u door de verschillende tabbladen op de geautomatiseerde onderzoeken pagina en hoe u de informatie gebruiken.

### <a name="automated-investigations-page"></a>Pagina Geautomatiseerde onderzoeken

De pagina met geautomatiseerde onderzoeken toont de onderzoeken van uw organisatie en hun huidige status.

![Hoofdonderzoekspagina voor AIR](../../media/air-maininvestigationpage.png) 
  
U kunt:
- Navigeer rechtstreeks naar een onderzoek (selecteer een **onderzoeks-id).**
- Filters toepassen. Kies **uit Onderzoekstype,** **Tijdbereik,** **Status**of een combinatie hiervan.
- Exporteer de gegevens naar een CSV-bestand.

De onderzoeksstatus geeft de voortgang van de analyse en acties aan. Naarmate het onderzoek wordt uitgevoerd, verandert de status om aan te geven of er bedreigingen zijn gevonden en of acties zijn goedgekeurd. 

|Status  |Wat het betekent  |
|---------|---------|
|Starten | Het onderzoek staat in de wachtrij om binnenkort te beginnen |
|Met | Het onderzoek is gestart en voert zijn analyse uit |
|Geen bedreigingen gevonden | Het onderzoek heeft zijn analyse afgerond en er zijn geen bedreigingen |
|Beëindigd per systeem | Het onderzoek werd niet gesloten en verliep na 7 dagen |
|Actie in behandeling | Het onderzoek vond bedreigingen met acties aanbevolen.  Het onderzoek wordt voortgezet nadat het de eerste bedreigingen en aanbevolen acties heeft gevonden, dus u moet het logboek controleren voordat u acties goedkeurt om te zien of analysers nog aan de gang zijn. |
|Gevonden bedreigingen | Het onderzoek vond bedreigingen, maar de bedreigingen hebben geen acties beschikbaar binnen AIR.  Dit zijn acties van gebruikers waarbij er nog geen air-actie in de richting is. |
|Gesaneerd | Het onderzoek werd afgerond en volledig gesaneerd (alle acties werden goedgekeurd) |
|Gedeeltelijk gesaneerd | Het onderzoek werd afgerond en een aantal van de aanbevolen acties werd |
|Beëindigd door gebruiker | Een beheerder heeft het onderzoek beëindigd |
|Mislukt | Er is een fout opgetreden tijdens het onderzoek waardoor zij geen conclusie kon trekken over bedreigingen |
|In de wachtrij door throttling | Het onderzoek wacht op analyse vanwege systeemverwerkingsbeperkingen (om de prestaties van de service te beschermen) |
|Beëindigd door beperking | Het onderzoek kon niet tijdig worden afgerond vanwege de omvang van het onderzoek en de beperkingen voor de verwerking van het systeem. U het onderzoek opnieuw activeren door de e-mail in Explorer te selecteren en de actie Onderzoeken te selecteren. |

### <a name="investigation-graph"></a>Onderzoeksgrafiek

Wanneer u een specifiek onderzoek opent, ziet u de pagina met de onderzoeksgrafiek. Op deze pagina worden alle verschillende entiteiten weergegeven: e-mailberichten, gebruikers (en hun activiteiten) en apparaten die automatisch zijn onderzocht als onderdeel van de waarschuwing die is geactiveerd.

![AIR-onderzoeksgrafiekpagina](../../media/air-investigationgraphpage.png)

U kunt:
- Krijg een visueel overzicht van het huidige onderzoek.
- Bekijk een samenvatting van de duur van het onderzoek.
- Selecteer een knooppunt in de visualisatie om details voor dat knooppunt weer te geven.
- Selecteer een tabblad bovenom details voor dat tabblad weer te geven.

### <a name="alert-investigation"></a>Waarschuwingsonderzoek

Op het tabblad **Waarschuwingen** voor een onderzoek ziet u waarschuwingen die relevant zijn voor het onderzoek. Details omvatten de waarschuwing die het onderzoek heeft geactiveerd en andere gecorreleerde waarschuwingen, zoals risicovolle aanmelding, DLP-beleidsschendingen, enz., die zijn gecorreleerd aan het onderzoek. Op deze pagina kan een beveiligingsanalist ook aanvullende details over afzonderlijke waarschuwingen bekijken.

![PAGINA AIR-waarschuwingen](../../media/air-investigationalertspage.png)

U kunt:
- Krijg een visueel overzicht van de huidige triggering alert en eventuele bijbehorende waarschuwingen.
- Selecteer een waarschuwing in de lijst om een fly-outpagina te openen met volledige waarschuwingsgegevens.

### <a name="email-investigation"></a>E-mailonderzoek

Op het tabblad **E-mail** voor een onderzoek ziet u de oorspronkelijke e-mails en de clusters van vergelijkbare e-mails die als onderdeel van het onderzoek zijn geïdentificeerd. 

Gezien de enorme hoeveelheid e-mail die gebruikers in een organisatie verzenden en ontvangen, plus de aard van e-mailcommunicatie en -aanvallen met meerdere gebruikers, 
- e-mailberichten clusteren op basis van vergelijkbare kenmerken van een berichtkoptekst, hoofdtekst, URL en bijlagen; 
- het scheiden van kwaadaardige e-mail van de goede e-mail; En 
- actie ondernemen tegen schadelijke e-mailberichten 

kan veel tijd in beslag nemen. AIR automatiseert dit proces nu, waardoor het beveiligingsteam van uw organisatie tijd en moeite bespaart. 

Tijdens de e-mailanalysestap kunnen twee verschillende typen e-mailclusters worden geïdentificeerd: gelijkenisclusters en indicatorclusters. 
- Vergelijkbare clusters zijn e-mailberichten die worden geïdentificeerd door te jagen op e-mails met vergelijkbare afzender- en inhoudskenmerken. Deze clusters worden beoordeeld op schadelijke inhoud op basis van de oorspronkelijke detectiebevindingen. E-mailclusters die voldoende schadelijke e-maildetecties bevatten, worden als kwaadaardig beschouwd.
- Indicatorclusters zijn e-mailberichten die worden geïdentificeerd door te jagen op dezelfde indicatorentiteit (bestandshash of URL) van de oorspronkelijke e-mail. Wanneer de oorspronkelijke bestands-/URL-entiteit als kwaadaardig wordt geïdentificeerd, past AIR het indicatorvonnis toe op het hele cluster van e-mailberichten dat die entiteit bevat. Een bestand geïdentificeerd als malware betekent dat het cluster van e-mailberichten met dat bestand worden behandeld als malware e-mailberichten.

Het doel van clustering is om te jagen en andere gerelateerde e-mailberichten te vinden die door dezelfde afzender worden verzonden als onderdeel van een aanval of een campagne.  In sommige gevallen kan legitieme e-mail een onderzoek ingang brengen (bijvoorbeeld een gebruiker meldt een marketinge-mail).  In deze scenario's moet de e-mailclustering identificeren dat e-mailclusters niet kwaadaardig zijn - wanneer dit op de juiste manier wordt aangegeven, wordt **geen** bedreiging aangegeven en wordt het verwijderen van e-mail niet aanbevolen.

Het tabblad **E-mail** toont ook e-mailitems met betrekking tot het onderzoek, zoals de door de gebruiker gerapporteerde e-mailgegevens, de oorspronkelijke e-mail die is gerapporteerd, het e-mailbericht(en) zapped als gevolg van malware / phish, enz.

Het aantal e-mail dat op het tabblad e-mail wordt geïdentificeerd, vertegenwoordigt momenteel de som van alle e-mailberichten die op het tabblad **E-mail worden** weergegeven. Omdat e-mailberichten aanwezig zijn in meerdere clusters, is het werkelijke totale aantal geïdentificeerde e-mailberichten (en beïnvloed door herstelacties) het aantal unieke e-mailberichten dat aanwezig is in alle clusters en de e-mailberichten van de oorspronkelijke geadresseerden. 

Zowel Explorer als AIR tellen e-mailberichten per ontvanger, omdat de beveiligingsvonnissen, acties en leveringslocaties per ontvanger verschillen. Dus een originele e-mail verzonden naar drie gebruikers tellen als een totaal van drie e-mailberichten in plaats van een e-mail. Houd er rekening mee dat er gevallen kunnen zijn waarin een e-mail twee of meer keer wordt geteld, omdat de e-mail meerdere acties kan hebben en er meerdere kopieën van de e-mail kunnen zijn zodra alle acties plaatsvinden. Een malware-e-mail die bij levering wordt gedetecteerd, kan bijvoorbeeld leiden tot zowel een geblokkeerde (in quarantaine geplaatste) e-mail en een vervangen e-mail (bedreigingsbestand dat wordt vervangen door een waarschuwingsbestand en vervolgens wordt bezorgd in het postvak van de gebruiker). Aangezien er letterlijk twee kopieën van de e-mail in het systeem zijn, kunnen beide worden meegeteld in clustertellingen. 

E-mailtellingen worden berekend op het moment van het onderzoek en sommige tellingen worden opnieuw berekend wanneer u flyouts van onderzoek opent (op basis van een onderliggende query). De e-mailtellingen die worden weergegeven voor de e-mailclusters op het e-mailtabblad en de e-mailhoeveelheidswaarde die wordt weergegeven op clusterflyout, worden berekend op het moment van het onderzoek en worden niet gewijzigd. Het aantal e-maildat onder aan het e-mailtabblad van de flyout van het e-mailcluster wordt weergegeven en het aantal e-mailberichten dat in Explorer wordt weergegeven, weerspiegelen e-mailberichten die zijn ontvangen na de eerste analyse van het onderzoek. Zo zou een e-mailcluster met een originele hoeveelheid van 10 e-mailberichten een totaal van 15 e-mailtonen wanneer er nog vijf e-mailberichten binnenkomen tussen de onderzoeksanalysefase en wanneer de beheerder het onderzoek bekijkt.  Ook oude onderzoeken kunnen beginnen met grotere tellingen dan Explorer query's laten zien, omdat ATP P2 verloopt gegevens na 7 dagen voor proeven en 30 dagen voor betaalde licenties.  Het weergeven van zowel het aantal historische als de huidige tellingen in verschillende weergaven wordt gedaan om de e-mailimpact op het moment van het onderzoek en de huidige impact aan te geven tot het moment dat de hersteling wordt uitgevoerd.

Denk bijvoorbeeld aan het volgende scenario. Het eerste cluster van drie e-mailberichten werd beschouwd als phish. Een andere cluster van soortgelijke berichten met hetzelfde IP-en onderwerp werd gevonden en beschouwd als kwaadaardig, zoals sommige van hen werden geïdentificeerd als phish tijdens de eerste detectie. 

![AIR-pagina voor e-mailonderzoek](../../media/air-investigationemailpage.png)

U kunt:
- Krijg een visueel overzicht van de huidige clusteringresultaten en bedreigingen die worden gevonden.
- Klik op een clusterentiteit of een bedreigingslijst om een fly-outpagina te openen met de volledige waarschuwingsgegevens.
- Onderzoek het e-mailcluster verder door boven aan het tabblad 'E-mailclusterdetails' te klikken op de koppeling 'Openen in Explorer'

![AIR-onderzoek e-mail met flyout details](../../media/air-investigationemailpageflyoutdetails.png)

> [!NOTE]
> In de context van e-mail ziet u mogelijk een volumeanomaliebedreiging als onderdeel van het onderzoek. Een volumeafwijking duidt op een piek in vergelijkbare e-mailberichten rond de gebeurtenistijd van het onderzoek in vergelijking met eerdere termijnen. Deze piek in e-mailverkeer met vergelijkbare kenmerken (bijvoorbeeld onderwerp- en afzenderdomein, gelijkenis met het lichaam en afzender-IP) is typerend voor het begin van e-mailcampagnes of -aanvallen. Echter, bulk, spam, en legitieme e-mailcampagnes delen vaak deze kenmerken. Volumeafwijkingen vormen een potentiële bedreiging en kunnen daarom minder ernstig zijn in vergelijking met malware of phish-bedreigingen die worden geïdentificeerd met behulp van antivirusengines, ontploffing of kwaadwillige reputatie.

### <a name="user-investigation"></a>Gebruikersonderzoek

Op het tabblad **Gebruikers** ziet u alle gebruikers die zijn geïdentificeerd als onderdeel van het onderzoek. Gebruikersaccounts worden in het onderzoek weergegeven wanneer er een gebeurtenis of aanwijzing is dat deze gebruikersaccounts kunnen worden beïnvloed of gecompromitteerd.

In de volgende afbeelding heeft AIR bijvoorbeeld indicatoren van compromissen en afwijkingen geïdentificeerd op basis van een nieuwe inboxregel die is gemaakt. Aanvullende details (bewijs) van het onderzoek zijn beschikbaar via gedetailleerde weergaven op dit tabblad. Indicatoren van compromissen en afwijkingen kunnen ook anomaliedetecties van [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)bevatten.

![PAGINA gebruikers van AIR-onderzoek](../../media/air-investigationuserspage.png)

U kunt:
- Krijg een visueel overzicht van de geïdentificeerde gebruikersresultaten en -risico's.
- Selecteer een gebruiker om een fly-outpagina te openen met de volledige waarschuwingsgegevens.

### <a name="machine-investigation"></a>Machineonderzoek

Op het tabblad **Machines** ziet u alle machines die zijn geïdentificeerd als onderdeel van het onderzoek. 

![AIR-onderzoeksmachinepagina](../../media/air-investigationmachinepage.png)

Als onderdeel van sommige playbooks correleert AIR e-mailbedreigingen naar apparaten (bijvoorbeeld Zapped-malware). Een onderzoek geeft bijvoorbeeld een kwaadaardige bestandshash door aan [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection
) om dit te onderzoeken. Dit maakt geautomatiseerd onderzoek van relevante machines voor uw gebruikers mogelijk, om ervoor te zorgen dat bedreigingen zowel in de cloud als in uw eindpunten worden aangepakt. 

U kunt:
- Krijg een visueel overzicht van de huidige machines en bedreigingen gevonden.
- Selecteer een machine om een weergave te openen die wordt gebruikt voor de gerelateerde [Microsoft Defender ATP-onderzoeken](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) in het Microsoft Defender Security Center.

### <a name="entity-investigation"></a>Entiteitsonderzoek

Op het tabblad **Entiteiten** ziet u de entiteiten die zijn geïdentificeerd en geanalyseerd als onderdeel van het onderzoek. 

Hier ziet u de onderzochte entiteiten en details van de typen entiteiten, zoals e-mailberichten, clusters, IP-adressen, gebruikers en meer. U ook zien hoeveel entiteiten zijn geanalyseerd en welke bedreigingen aan elk van deze entiteiten zijn gekoppeld. 

![PAGINA AIR-onderzoeksentiteiten](../../media/air-investigationentitiespage.png)

U kunt:
- Krijg een visueel overzicht van de gevonden onderzoeksentiteiten en bedreigingen.
- Selecteer een entiteit om een fly-outpagina te openen die de gerelateerde entiteitsgegevens weergeeft.

![Air-onderzoeksentiteiten details](../../media/air-investigationsentitiespagedetails.png)

### <a name="playbook-log"></a>Logboeklogboek

Op het tabblad **Logboek** ziet u alle stappen in de draaimap die tijdens het onderzoek zijn opgetreden. Het logboek bevat een volledige inventaris van alle analyseapparaten en acties die zijn voltooid door de mogelijkheden voor automatisch onderzoek van Office 365 als onderdeel van AIR. Het geeft een duidelijk beeld van alle genomen stappen, inclusief de actie zelf, een beschrijving en de duur van de werkelijke van begin tot eind. 

![AIR-logboekpagina voor onderzoek](../../media/air-investigationlogpage.png)

U kunt:
- Bekijk een visueel overzicht van de stappen die zijn genomen.
- Exporteer de resultaten naar een CSV-bestand.
- Filter de weergave.

|Analyzer | Beschrijving |
|-----|-----|
|DLP overtredingen onderzoek |Eventuele overtredingen onderzoeken die zijn gedetecteerd door [Office 365 Data Loss Prevention](../../compliance/data-loss-prevention-policies.md) (DLP) |
|Extractie van e-mailindicatoren |Indicatoren uit de koptekst, het hoofd en de inhoud van een e-mailbericht voor onderzoek extraheren |
|Reputatie van bestandshash |Afwijkingen detecteren op basis van bestandshashes voor gebruikers en machines in uw organisatie |
|Identificatie van e-mailcluster |Analyse van e-mailcluster op basis van koptekst, hoofdtekst, inhoud en URL's |
|Volumeanalyse van het e-mailcluster |E-mailclusteranalyse op basis van uitgaande volumepatronen van e-mailstroom |
|Onderzoek naar de delegatie van e-mail |Toegang tot e-maildelegatieonderzoeken voor gebruikerspostvakken in verband met dit onderzoek |
|Onderzoek naar regels voor het doorsturen van e-mail |Alle regels voor het doorsturen van e-mail onderzoeken voor postvakken van gebruikers die verband houden met dit onderzoek |
|Gemiste malware gedetecteerd |Gemiste malware detecteren die in uw organisatie in het postvak van de gebruiker wordt geleverd |
|On-demand ontploffing |On-demand ontploffing geactiveerd voor e-mailberichten, bijlagen en URL's |
|Uitgaand e-mailanomalieonderzoek |Afwijkingen detecteren op basis van historische verzendpatronen voor e-mailstromen voor gebruikers in uw organisatie |
|Uitgaand malware- en spamanomalieonderzoek |Detecteer intra-org en uitgaande malware, phish of spam afkomstig van gebruikers in uw organisatie |
|Onderzoek naar afzenderdomein |On-demand controle van de domeinreputatie van de [Microsoft Intelligent Security Graph](https://www.microsoft.com/security/operations/intelligence) en externe threat intelligence bronnen |
|IP-onderzoek afzender | On-demand controle van ip-reputatie van de [Microsoft Intelligent Security Graph](https://www.microsoft.com/security/operations/intelligence) en externe threat intelligence bronnen |
|ONDERZOEK NAAR URL-klikken | Clicks onderzoeken van gebruikers die zijn beschermd door Veilige Koppelingen van [Office 365 ATP](atp-safe-links.md) in uw organisatie |
|URL reputatie onderzoek |On-demand controle op de reputatie van de URL van de [Microsoft Intelligent Security Graph](https://www.microsoft.com/security/operations/intelligence) en externe threat intelligence bronnen |
|Onderzoek naar gebruikersactiviteiten |Afwijkingen van gebruikersactiviteiten analyseren in [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) |
|Door de gebruiker gerapporteerde e-mails indicatoren extractie |Indicatoren uit de header, body en inhoud van [door de gebruiker gerapporteerde e-mail](enable-the-report-message-add-in.md) voor onderzoek extraheren |

### <a name="recommended-actions"></a>Aanbevolen acties

Op het tabblad **Acties** ziet u alle playbook-acties die worden aanbevolen voor herstel nadat het onderzoek is voltooid. 

Acties leggen de stappen vast die Microsoft aanhet einde van een onderzoek aanbeveelt. U hier herstelacties uitvoeren door een of meer acties te selecteren. Als u op **Goedkeuren klikt,** kan de herstelprocedure beginnen. (Er zijn passende machtigingen nodig - de rol 'Zoeken en verwijderen' is vereist om acties uit te voeren vanuit Explorer en AIR). Een beveiligingslezer kan bijvoorbeeld acties bekijken, maar deze niet goedkeuren. Opmerking: Je hoeft niet elke actie goed te keuren. Als u het niet eens bent met de aanbevolen actie of als uw organisatie bepaalde soorten acties niet kiest, u ervoor kiezen om de acties af te **wijzen** of ze gewoon te negeren en geen actie te ondernemen. Door alle acties goed te keuren en/of af te wijzen, kan het onderzoek volledig worden afgesloten (status wordt gesaneerd), terwijl sommige acties onvolledig blijven, waardoor de onderzoeksstatus verandert in een gedeeltelijk gesaneerd toestand.

![Actiepagina AIR-onderzoeken](../../media/air-investigationactionspage.png)

U kunt:
- Krijg een visueel overzicht van de acties die aan de playbook worden aanbevolen.
- Selecteer één actie of meerdere acties.
- Aanbevolen acties goedkeuren of afwijzen met opmerkingen.
- Exporteer de resultaten naar een CSV-bestand.
- Filter de weergave.

## <a name="next-steps"></a>Volgende stappen

- [In behandeling zijnde acties controleren en goedkeuren](https://review.docs.microsoft.com/microsoft-365/security/office-365-security/air-review-approve-pending-completed-actions)

- [Meer informatie over geautomatiseerd onderzoek en reactie in Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
