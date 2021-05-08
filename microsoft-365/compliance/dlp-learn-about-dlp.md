---
title: Meer informatie over preventie van gegevensverlies
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Lees hoe u uw gevoelige informatie kunt beveiligen met Microsoft 365 beleid en hulpprogramma's voor preventie van gegevensverlies en een rondleiding kunt volgen door de DLP-levenscyclus.
ms.openlocfilehash: 88cf913f62d28c89bce7054473eb577217de9489
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244610"
---
# <a name="learn-about-data-loss-prevention"></a>Meer informatie over preventie van gegevensverlies

Organisaties hebben gevoelige informatie onder hun controle, zoals financiële gegevens, eigendomsgegevens, creditcardnummers, gezondheidsrecords of sociale-zekerheidsnummers. Om deze gevoelige gegevens te beschermen en risico's te beperken, hebben ze een manier nodig om te voorkomen dat hun gebruikers deze op ongepaste wijze delen met personen die deze gegevens niet mogen hebben. Deze praktijk heet preventie van gegevensverlies (DLP).

In Microsoft 365 implementeert u preventie van gegevensverlies door DLP-beleid te definiëren en toe te passen. Met een DLP-beleid kunt u gevoelige items op verschillende gebieden identificeren, controleren en automatisch beveiligen:

- Microsoft 365 services zoals Teams, Exchange, SharePoint en OneDrive
- Office toepassingen zoals Word, Excel en PowerPoint
- Windows 10 eindpunten
- niet-Microsoft-cloud-apps
- on-premises bestandsaandelen en on-premises SharePoint.

Microsoft 365 detecteert gevoelige items met behulp van diepgaande inhoudsanalyse, niet alleen door een eenvoudige tekstscan. Inhoud wordt geanalyseerd op primaire gegevens die overeenkomen met trefwoorden, door de evaluatie van reguliere expressies, door interne functievalidatie en door secundaire gegevensmatchen die zich in de nabijheid van de primaire gegevensmatch bevinden. Daarnaast gebruikt DLP ook algoritmen voor machine learning en andere methoden om inhoud te detecteren die overeenkomt met uw DLP-beleid.
  
## <a name="dlp-is-part-of-the-larger-microsoft-365-compliance-offering"></a>DLP maakt deel uit van het grotere Microsoft 365 Compliance-aanbod

Microsoft 365 DLP is slechts een van de Microsoft 365 compliancehulpmiddelen die u gebruikt om uw gevoelige items te beschermen, waar ze ook wonen of reizen. U moet de andere hulpprogramma's in de Microsoft 365 compliancehulpprogramma's begrijpen, hoe ze met elkaar verwisseld zijn en beter samenwerken.  Zie de [Microsoft 365 voor meer](protect-information.md) informatie over het informatiebeveiligingsproces.

## <a name="protective-actions-of-dlp-policies"></a>Beschermende acties van DLP-beleid

Microsoft 365 DLP-beleid is hoe u de activiteiten controleert die gebruikers in rust uitvoeren op gevoelige items, gevoelige items die onderweg zijn of gevoelige items die worden gebruikt en beschermende acties ondernemen. Als een gebruiker bijvoorbeeld probeert een verboden actie uit te voeren, zoals het kopiëren van een gevoelig item naar een niet-goedgekeurde locatie of het delen van medische informatie in een e-mail of andere voorwaarden die in een beleid zijn vastgelegd, kan DLP:

- een pop-upbeleidstip tonen aan de gebruiker die hem of haar waarschuwt dat hij of zij mogelijk een gevoelig item ongepast probeert te delen
- het delen te blokkeren en via een beleidstip de gebruiker toe te staan het blok te overschrijven en de rechtvaardiging van de gebruikers vast te leggen
- het delen blokkeren zonder de optie overschrijven
- voor gegevens in rust kunnen gevoelige items worden vergrendeld en naar een veilige quarantainelocatie worden verplaatst
- voor Teams chat, worden de gevoelige gegevens niet weergegeven

Alle DLP-gecontroleerde activiteiten worden standaard opgenomen in [het Microsoft 365 auditlogboek](search-the-audit-log-in-security-and-compliance.md) en worden doorgeleid naar [Activiteitsverkenner.](data-classification-activity-explorer.md) Wanneer een gebruiker een actie uitvoert die voldoet aan de criteria van een DLP-beleid en u waarschuwingen hebt geconfigureerd, geeft DLP waarschuwingen in het [DLP-dashboard voor waarschuwingsbeheer.](dlp-configure-view-alerts-policies.md)

## <a name="dlp-lifecycle"></a>DLP-levenscyclus

Een DLP-implementatie volgt meestal deze belangrijke fasen.

- [Plannen voor DLP](#plan-for-dlp)
- [Voorbereiden op DLP](#prepare-for-dlp)
- [Uw beleid implementeren in productie](#deploy-your-policies-in-production)


<!--ADD DIAGRAM OF THE DLP LIFECYCLE WORK ON WITH MAS-->

### <a name="plan-for-dlp"></a>Plannen voor DLP

Microsoft 365 DLP-monitoring en -beveiliging zijn inheems in de toepassingen die gebruikers elke dag gebruiken. Dit helpt om de gevoelige items van uw organisatie te beschermen tegen riskante activiteiten, zelfs als uw gebruikers niet zijn gewend aan preventie van gegevensverlies. Als uw organisatie en uw gebruikers nieuw zijn op het gebied van preventie van gegevensverlies, kan het nodig zijn om DLP aan te passen aan uw bedrijfsprocessen en is er een cultuurverschuiving voor uw gebruikers. Maar met de juiste planning, testen en afstemmen beschermt uw DLP-beleid uw gevoelige items en minimaliseert u eventuele verstoringen van bedrijfsprocessen.

**Technologieplanning voor DLP**

Houd er rekening mee dat DLP als technologie uw gegevens in rust kan bewaken en beveiligen, gegevens in gebruik en gegevens die in beweging zijn op Microsoft 365-services, Windows 10-apparaten, on-premises bestandsaandelen en on-premises SharePoint. Er zijn plannings implicaties voor de verschillende locaties, het type gegevens dat u wilt bewaken en beveiligen en de acties die moeten worden ondernomen wanneer een beleidsmatch plaatsvindt.  

**Planning van bedrijfsprocessen voor DLP**

DLP-beleid kan verboden activiteiten blokkeren, zoals ongepast delen van gevoelige informatie via e-mail. Terwijl u uw DLP-beleid plant, moet u de bedrijfsprocessen identificeren die uw gevoelige items raken. De eigenaren van bedrijfsprocessen kunnen u helpen bij het identificeren van het juiste gebruikersgedrag dat moet worden toegestaan en ongepast gebruikersgedrag dat moet worden beschermd. U moet uw beleid plannen en implementeren in de [](data-classification-activity-explorer.md) testmodus, en eerst de impact ervan evalueren via activiteitsverkenner, voordat u ze in meer beperkende modi kunt toepassen.

**Organisatiecultuurplanning voor DLP**

Een succesvolle DLP-implementatie is net zo afhankelijk van het trainen en wennen van uw gebruikers aan preventie van gegevensverlies als aan goed geplande en afgestemde beleidsregels. Aangezien uw gebruikers nauw betrokken zijn, moet u ook training voor hen plannen. U kunt beleidstips strategisch gebruiken om uw gebruikers bewust te maken voordat u de beleidshandhaving verandert van testmodus in meer beperkende modi.

<!--For more information on planning for DLP, including suggestions for deployment based on your needs and resources, see [Planning for Microsoft 365 data loss prevention](dlp-plan-for-dlp.md).-->

### <a name="prepare-for-dlp"></a>Voorbereiden op DLP

U kunt DLP-beleid toepassen op gegevens in rust, gegevens in gebruik en gegevens in beweging op locaties, zoals:

- Exchange Online e-mail
- SharePoint Onlinesites
- OneDrive accounts
- Teams chat- en kanaalberichten
- Microsoft Cloud App Security
- Windows 10 apparaten
- On-premises opslagplaatsen

Elk heeft verschillende vereisten. Gevoelige items op sommige locaties, zoals Exchange online, kunnen onder de paraplu van DLP worden gebracht door gewoon een beleid te configureren dat op hen van toepassing is. Voor andere bestanden, zoals on-premises bestandsitories, is een implementatie van AIP-scanner (Azure Information Protection) vereist. U moet uw omgeving voorbereiden, conceptbeleid coderen en deze grondig testen voordat u eventuele blokkeringsacties activeert.

### <a name="deploy-your-policies-in-production"></a>Uw beleid implementeren in productie

#### <a name="design-your-policies"></a>Uw beleid ontwerpen

Begin met het definiëren van uw beheerdoelstellingen en hoe deze van toepassing zijn op elke respectievelijke werkbelasting. Een beleid opstellen dat uw doelstellingen belichaamt. U kunt beginnen met één werkbelasting tegelijk of met alle werkbelastingen. Er is nog geen effect.

#### <a name="implement-policy-in-test-mode"></a>Beleid implementeren in testmodus

Evalueer de impact van de besturingselementen door deze te implementeren met een DLP-beleid in de testmodus. Het is ok om het beleid toe te passen op alle werkbelastingen in de testmodus, zodat u de volledige breedte van de resultaten kunt krijgen, maar u kunt beginnen met één werkbelasting als dat nodig is.

#### <a name="monitor-outcomes-and-fine-tune-the-policy"></a>Resultaten controleren en het beleid verder afstemmen

Houd in de testmodus de resultaten van het beleid in de gaten en pas het aan zodat het voldoet aan uw beheerdoelstellingen, terwijl u ervoor zorgt dat u geen nadelige of onbedoelde invloed hebt op geldige gebruikerswerkstromen en productiviteit. Hier zijn enkele voorbeelden van dingen die u kunt afstemmen:

- het aanpassen van de locaties en personen/plaatsen die binnen of buiten het bereik vallen
- de voorwaarden en uitzonderingen afstemmen die worden gebruikt om te bepalen of een item en wat er mee wordt gedaan, overeenkomt met het beleid
- de definitie van gevoelige informatie/s
- de acties
- het niveau van beperkingen
- nieuwe besturingselementen toevoegen
- nieuwe personen toevoegen
- nieuwe, beperkte apps toevoegen
- nieuwe sites met beperkingen toevoegen

#### <a name="enable-the-control-and-tune-your-policies"></a>Het besturingselement inschakelen en uw beleid afstemmen

Wanneer het beleid aan al uw doelstellingen voldoet, zet u het in. Blijf de resultaten van de beleidstoepassing controleren en zo nodig afstemmen. Over het algemeen worden beleidsregels ongeveer een uur na het in- en uit <!--See, KOPPELING NAAR-onderwerp voor SLA's voor locatiespecifieke details, >

## <a name="dlp-policy-configuration-overview"></a>Overzicht van DLP-beleidsconfiguratie

U hebt flexibiliteit in de manier waarop u uw DLP-beleid maakt en configureert. U kunt beginnen met een vooraf gedefinieerde sjabloon en met slechts een paar klikken een beleid maken of u kunt uw eigen sjabloon van begin af aan ontwerpen. Welke u ook kiest, voor alle DLP-beleidsregels is dezelfde informatie van u vereist.

1. **Kies wat u wilt controleren:** Microsoft 365 bevat veel vooraf gedefinieerde beleidssjablonen om u te helpen aan de slag te gaan of u kunt een aangepast beleid maken.
    - Een vooraf gedefinieerde beleidssjabloon: Financiële gegevens, medische en gezondheidsgegevens, Privacygegevens voor verschillende landen en regio's.
    - Een aangepast beleid dat gebruikmaakt van de beschikbare gevoelige informatietypen, bewaarlabels en gevoeligheidslabels.
2. **Kies waar u wilt controleren:** u kiest een of meer locaties waarop U DLP wilt controleren voor gevoelige informatie. U kunt het volgende controleren:
    
locatie | opnemen/uitsluiten door|
|---------|---------|
|Exchange e-mail| distributiegroepen|
|SharePoint sites |sites |
|OneDrive accounts |accounts of distributiegroepen |
|Teams chat- en kanaalberichten |accounts |
|Windows 10 apparaten |gebruiker of groep |
|Microsoft Cloud App Security |exemplaar |
|On-premises opslagplaatsen| archiefbestandspad|

3. **Kies de voorwaarden die moeten worden aangepast** om een beleid toe te passen op een item. U kunt vooraf geconfigureerde voorwaarden accepteren of aangepaste voorwaarden definiëren. Enkele voorbeelden zijn:

- item bevat een opgegeven soort gevoelige informatie die in een bepaalde context wordt gebruikt. Er worden bijvoorbeeld 95 sociale-zekerheidsnummers per e-mail verzonden naar geadresseerde buiten uw organisatie.
- item heeft een opgegeven gevoeligheidslabel
- item met gevoelige informatie wordt intern of extern gedeeld

4. **Kies de actie die moet worden ondernomen wanneer** aan de beleidsvoorwaarden wordt voldaan: de acties zijn afhankelijk van de locatie waar de activiteit wordt plaatsvinden.  Enkele voorbeelden zijn:

- SharePoint/Exchange/OneDrive: Blokkeren dat personen buiten uw organisatie toegang hebben tot de inhoud. Laat de gebruiker een tip zien en stuur hem of haar een e-mailmelding dat hij of zij een actie onderneemt die is verboden door het DLP-beleid.
- Teams Chatten en kanaal: blokkeren dat gevoelige informatie wordt gedeeld in de chat of het kanaal
- Windows 10 Apparaten: Het kopiëren van een gevoelig item naar een verwijderbaar USB-apparaat controleren of beperken 
- Office Apps: Laat een pop-up zien waarin de gebruiker wordt op de hoogte gebracht dat hij of zij risicovol gedrag heeft en blokkeert of blokkeert, maar overschrijven toestaat.
- On-premises bestandsaandelen: verplaats het bestand van waar het is opgeslagen naar een quarantainemap

> [!NOTE]
> De voorwaarden en de acties die moeten worden ondernomen, worden gedefinieerd in een object dat een regel wordt genoemd.

<!--## Create a DLP policy

All DLP policies are created and maintained in the Microsoft 365 Compliance center. See, INSERT LINK TO ARTICLE THAT WILL START WALKING THEM THROUGH THE POLICY CREATION PROCEDURES for more information.-->

Nadat u een DLP-beleid hebt in het Compliancecentrum, wordt het opgeslagen in een centrale beleidsopslag en vervolgens gesynchroniseerd met de verschillende inhoudsbronnen, waaronder:
  
- Exchange Online, en van daar naar Outlook op het web en Outlook.
- OneDrive voor Bedrijven sites.
- SharePoint Onlinesites.
- Office bureaubladprogramma's (Excel, PowerPoint en Word).
- Microsoft Teams kanalen en chatberichten.
    
Nadat het beleid is gesynchroniseerd met de juiste locaties, wordt gestart met het evalueren van inhoud en het afdwingen van acties.

## <a name="viewing-policy-application-results"></a>Resultaten van beleidstoepassing weergeven

DLP rapporteert een grote hoeveelheid informatie in Microsoft 365 monitoring, beleidswedstrijden en acties en gebruikersactiviteiten. U moet deze informatie gebruiken en erop reageren om uw beleid af te stemmen en acties op gevoelige items af te stemmen. De telemetrie gaat eerst naar [het Microsoft 365 auditlogboeken](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log-in-the-compliance-center) van het compliancecentrum, wordt verwerkt en maakt zijn weg naar verschillende rapportagehulpmiddelen. Elk rapportagehulpmiddel heeft een ander doel.  

### <a name="dlp-alerts-dashboard"></a>DLP-waarschuwingendashboard

Wanneer DLP een actie onderneemt voor een gevoelig item, kunt u hiervan op de hoogte worden gesteld via een configureerbare waarschuwing. In plaats van dat deze waarschuwingen zich in een postvak opstapelen om door te sissen, stelt het Compliancecentrum deze beschikbaar in het [DLP Alerts Management Dashboard.](dlp-configure-view-alerts-policies.md) Gebruik het DLP-waarschuwingendashboard om waarschuwingen te configureren, te controleren, te triagen en de resolutie van DLP-waarschuwingen bij te houden. Hier volgen een voorbeeld van waarschuwingen die worden gegenereerd door beleidswedstrijden en activiteiten van Windows 10 apparaten.

> [!div class="mx-imgBorder"]
> ![Waarschuwingsgegevens](../media/Alert-info-1.png)

U kunt ook details van de bijbehorende gebeurtenis weergeven met uitgebreide metagegevens in hetzelfde dashboard

> [!div class="mx-imgBorder"]
> ![gebeurtenisgegevens](../media/Event-info-1.png)

### <a name="reports"></a>Rapporten

De [DLP-rapporten](view-the-dlp-reports.md#view-the-reports-for-data-loss-prevention) laten algemene trends zien in de tijd en geven specifieke inzichten in:

- **DLP-beleid komt overeen** met de tijd en filtert op datumbereik, locatie, beleid of actie
- **DLP-incident matches** toont ook overeenkomsten in de tijd, maar draait op de items in plaats van de beleidsregels.
- **DLP false positives and overrides shows** the count of false positives and, if configured, user-overrides along with the user justification.

### <a name="dlp-activity-explorer"></a>DLP Activity Explorer

Op het tabblad Activiteitsverkenner op de pagina DLP is het filter *Activiteit* vooraf ingesteld op *DLPRuleMatch.* Gebruik dit hulpprogramma om activiteiten te bekijken die betrekking hebben op inhoud die gevoelige informatie bevat of waarvoor labels zijn toegepast, zoals welke etiketten zijn gewijzigd, bestanden zijn gewijzigd en overeenkomen met een regel.

![schermafbeelding van de DLPRuleMatch-activiteitenverkenner met een bereik ](../media/dlp-activity-explorer.png)

Zie Aan de slag [met activiteitenverkenner](data-classification-activity-explorer.md) voor meer informatie

Zie voor meer informatie Microsoft 365 DLP:

- [Meer informatie over Microsoft 365 Eindpunt-DLP](endpoint-dlp-learn-about.md)
- [Meer informatie over het standaard preventiebeleid voor gegevensverlies in Microsoft Teams (preview)](dlp-teams-default-policy.md)
- [Meer informatie over de on-premises scanner voor Microsoft 365 preventie van gegevensverlies (preview)](dlp-on-premises-scanner-learn.md)
- [Meer informatie over de Microsoft-compliance-extensie (preview)](dlp-chrome-learn-about.md)
- [Meer informatie over het Waarschuwingen-dashboard voor preventie van gegevensverlies](dlp-alerts-dashboard-learn.md)

Zie Informatiebeveiliging implementeren voor privacyregels voor gegevens met [](../solutions/information-protection-deploy.md) Microsoft 365 (aka.ms/m365dataprivacy).