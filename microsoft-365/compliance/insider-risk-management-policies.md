---
title: Beleidsregels voor intern risicobeheer
description: Meer informatie over beleidsregels voor intern risicobeheer in Microsoft 365
keywords: Microsoft 365, intern risicobeheer, risicobeheer, naleving
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: f64fcf4908f119e261b07bbc4feaed2151e30187
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226429"
---
# <a name="insider-risk-management-policies"></a>Beleidsregels voor intern risicobeheer

Met beleidsregels voor intern risicobeheer wordt bepaald welke gebruikers binnen het bereik zijn en welke typen risico-indicatoren zijn geconfigureerd voor waarschuwingen. U kunt snel een beleid maken dat van toepassing is op alle gebruikers in uw organisatie of afzonderlijke gebruikers of groepen definiëren voor beheer in een beleid. Beleid biedt ondersteuning voor inhoudsprioriteiten voor het richten van beleidsvoorwaarden op meerdere of specifieke Microsoft Teams, SharePoint-sites, typen gegevensgevoeligheid en gegevenslabels. Met behulp van sjablonen kunt u specifieke risico-indicatoren selecteren en drempelwaarden voor gebeurtenissen aanpassen voor beleidsindicatoren, waardoor u effectief risicoscores en het niveau en de frequentie van waarschuwingen aanpast. Bovendien helpen risicoscore-boosters en afwijkingsdetecties gebruikersactiviteit te identificeren die van groter belang of ongebruikelijker is. Met beleidsvensters kunt u de periode definiëren waarmee het beleid wordt toegepast op waarschuwingsactiviteiten en wordt de duur van het beleid bepaald wanneer het is geactiveerd.

Bekijk de video [Configuratiebeleid voor intern risicobeheer](https://www.youtube.com/watch?v=kudK5ajZTUo) voor een overzicht van hoe beleidsregels die zijn gemaakt met ingebouwde beleidssjablonen, u kunnen helpen snel actie te ondernemen tegen potentiële risico's.

## <a name="policy-dashboard"></a>Beleidsdashboard

Met het **Beleidsdashboard** kunt u snel de beleidsregels in uw organisatie en de status van het beleid zien, gebruikers handmatig toevoegen aan beleidsregels en de status bekijken van waarschuwingen die aan elk beleid zijn gekoppeld.

- **Beleidsnaam**: de naam die is toegewezen aan het beleid in de beleidswizard.
- **Status**: de integriteitsstatus van elk beleid. Hiermee wordt het aantal beleidswaarschuwingen en aanbevelingen of de status *In orde* weergegeven voor beleid zonder problemen.  U kunt op het beleid klikken om de statusdetails voor eventuele waarschuwingen of aanbevelingen te bekijken.
- **Actieve waarschuwingen**: het aantal actieve waarschuwingen voor elk beleid.
- **Bevestigd waarschuwingen**: het totale aantal waarschuwingen dat het resultaat is van het beleid in de afgelopen 365 dagen.
- **Acties ondernomen op waarschuwingen**: het totale aantal waarschuwingen dat de afgelopen 365 dagen is bevestigd of afgewezen.
- **Effectiviteit van beleidswaarschuwingen**: het percentage dat wordt bepaald door het totale aantal bevestigde waarschuwingen gedeeld door het totaal aantal acties die zijn ondernomen op waarschuwingen (het totaal aantal waarschuwingen dat in het afgelopen jaar is bevestigd of is afgewezen).

![Dashboard voor beleid voor intern risicobeheer](../media/insider-risk-policy-dashboard.png)

## <a name="policy-recommendations-from-analytics-preview"></a>Beleidsaanbevelingen van analyse (preview)

Met risicoanalyses voor insiders kunt u een evaluatie uitvoeren van potentiële interne risico's in uw organisatie zonder dat u een intern risicobeleid configureert. Aan de hand van deze evaluatie kan uw organisatie potentiële gebieden met een hoger gebruikersrisico identificeren en bepalen welk type en bereik van het beleid voor intern risicobeheer u wilt configureren.

Zie voor meer informatie over interne risicoanalyses en beleidsaanbevelingen, [Instellingen voor intern risicobeheer: Analyse (preview)](insider-risk-management-settings.md#analytics-preview).

## <a name="policy-templates"></a>Beleidssjablonen

Sjablonen voor intern risicobeheer zijn vooraf gedefinieerde beleidsvoorwaarden waarmee de typen risico-indicatoren en het risicoscoremodel worden gedefinieerd dat door het beleid wordt gebruikt. Aan elk beleid moet een sjabloon zijn toegewezen in de wizard Beleid maken voordat het beleid wordt gemaakt. Intern risicobeheer ondersteunt maximaal vijf beleidsregels voor elke beleidssjabloon. Wanneer u een nieuw intern risicobeleid maakt met de beleidswizard, kiest u een van de volgende beleidssjablonen:

### <a name="data-theft-by-departing-users"></a>Gegevensdiefstal door vertrekkende gebruikers

Wanneer gebruikers uw organisatie verlaten, zijn er specifieke risico-indicatoren die doorgaans worden geassocieerd met gegevensdiefstal door vertrekkende gebruikers. Dit beleidssjabloon gebruikt exfiltratie-indicatoren voor een risicoscore en is gericht op detectie en waarschuwingen in dit risicogebied. Gegevensdiefstal door vertrekkende gebruikers kan bestaan uit het downloaden van bestanden van SharePoint Online, het afdrukken van bestanden en het kopiëren van gegevens naar persoonlijke berichten- en opslagdiensten in de cloud kort voor hun ontslag- of einddatum. Door gebruik te maken van de Microsoft 365 HR-connector of de optie om automatisch te controleren op verwijdering van gebruikersaccounts in Azure Active Directory voor uw organisatie, begint deze sjabloon te scoren voor risico-indicatoren met betrekking tot deze activiteiten en hoe deze correleren met de arbeidsstatus van de gebruiker.

> [!IMPORTANT]
> Wanneer u deze sjabloon gebruikt, kunt u een Microsoft 365 HR-connector configureren om periodiek informatie over de opzeg- en beëindigingsdatum te importeren voor gebruikers in uw organisatie. Zie het artikel [Gegevens importeren met de HR-connector](import-hr-data.md) voor stapsgewijze richtlijnen voor het configureren van de Microsoft 365 HR-connector voor uw organisatie. Als u ervoor kiest de HR-connector niet te gebruiken, selecteert u de optie Gebruikersaccount uit Azure AD verwijderd bij het configureren van triggergebeurtenissen in de beleidswizard.

### <a name="general-data-leaks"></a>Algemene gegevenslekken

Het beschermen van gegevens en het voorkomen van gegevenslekken is een constante uitdaging voor de meeste organisaties, met name door de snelle toename van nieuwe gegevens die worden gemaakt door gebruikers, apparaten en services. Gebruikers hebben de mogelijkheden om informatie te maken, op te slaan en te delen tussen services en apparaten, zodat het beheren van gegevenslekken complexer en moeilijker wordt. Datalekken kunnen het per ongeluk te veel delen van informatie buiten uw organisatie of gegevensdiefstal met kwaadwillende bedoelingen omvatten. Met een toegewezen beleid voor preventie van gegevensverlies (DLP) of de ingebouwde triggergebeurtenis, begint deze sjabloon met het scoren van realtime detecties van verdachte SharePoint Online-gegevensdownloads, het delen van bestanden en mappen, het afdrukken van bestanden en het kopiëren van gegevens naar persoonlijke cloudberichten en -opslagservices.

Wanneer u een sjabloon *Gegevenslekken* gebruikt, kunt u een DLP-beleid toewijzen om indicatoren in het intern risicobeleid te activeren voor waarschuwingen met hoge prioriteit in uw organisatie. Wanneer een waarschuwing met een hoge urgentie wordt gegenereerd door een DLP-beleidsregel die wordt toegevoegd aan het Office 365-controlelogboek, wordt de DLP-waarschuwing met hoge prioriteit die met deze sjabloon is gemaakt automatisch onderzocht. Als de waarschuwing een gebruiker binnen het bereik bevat die is gedefinieerd in het intern beleid risicobeheer, wordt de waarschuwing verwerkt door het intern beleid risicobeheer als een nieuwe waarschuwing en worden de ernst van het interne risico en een risicoscore toegewezen. Met dit beleid kunt u deze waarschuwing evalueren in samenhang met andere activiteiten die in de case zijn opgenomen. Als u geen DLP-beleid kiest, moet u de ingebouwde triggeringsgebeurtenis selecteren.

#### <a name="data-leaks-policy-guidelines"></a>Beleidsrichtlijnen voor gegevenslekken

Houd rekening met de volgende richtlijnen bij het maken of wijzigen van DLP-beleidsregels voor gebruik met beleidsregels voor intern risicobeheer:

- Geef prioriteit aan data-exfiltratiegebeurtenissen en wees selectief bij het toewijzen van instellingen voor **incidentrapporten** aan *Hoog* bij het configureren van regels in uw DLP-beleid. Het e-mailen van gevoelige documenten naar een bekende concurrent zou bijvoorbeeld een exfiltratiegebeurtenis op *hoog* waarschuwingsniveau moeten zijn. Door het *hoge* niveau in de instellingen voor **incidentrapporten** in andere DLP-beleidsregels te veel toe te wijzen, kan de ruis in de werkstroom voor waarschuwingen voor intern risicobeheer toenemen en kan het voor uw gegevensonderzoekers en analisten moeilijker worden om deze waarschuwingen goed te evalueren. Door bijvoorbeeld *hoge* waarschuwingsniveaus toe te wijzen voor toegang tot weigeringactiviteiten in DLP-beleidsregels, wordt het uitdagender om echt risicovol gebruikersgedrag en -activiteiten te evalueren.
- Zorg ervoor dat u de gebruikers in het DLP- en beleid voor intern risicobeheer begrijpt en op de juiste manier configureert. Alleen gebruikers die met de sjabloon **Gegevenslekken** zijn gedefinieerd als in-scope voor intern risicobeheerbeleid, worden met hoge prioriteit verwerkt. Bovendien zullen alleen gebruikers die in een regel voor een zeer ernstige DLP-waarschuwing zijn gedefinieerd als binnen het bereik vallend, door het beheer van intern risicobeleid ter overweging worden onderzocht. Het is belangrijk dat u niet onbewust gebruikers die binnen het bereik vallen in zowel uw DLP- als intern risicobeleid op een tegenstrijdige manier configureert.

     Als uw DLP-beleidsregels bijvoorbeeld alleen betrekking hebben op gebruikers in het verkoopteam en het interne risicobeleid dat is gemaakt op basis van de **Gegevenslekken**-sjabloon heeft alle gebruikers gedefinieerd als binnen het bereik vallend, zal het interne risicobeleid alleen daadwerkelijk zeer ernstige DLP-waarschuwingen verwerken voor de gebruikers van het verkoopteam. Het intern risicobeleid ontvangt geen DLP-waarschuwingen met hoge prioriteit voor gebruikers die niet zijn gedefinieerd in de DLP-regels in dit voorbeeld. Omgekeerd, als uw beleid voor intern risicobeheer dat is gemaakt op basis van **Gegevenslekken**-sjablonen is bedoeld voor gebruikers van het verkoopteam en het toegewezen DLP-beleid voor alle gebruikers geldt, verwerkt het beleid voor intern risicobeheer alleen zeer ernstige DLP-waarschuwingen voor leden van het verkoopteam. Met het beleid voor intern risicobeheer worden DLP-waarschuwingen met hoge prioriteit genegeerd voor alle gebruikers die geen deel uitmaken van het verkoopteam.

- Zorg ervoor dat de regelinstelling **Incidentrapporten** in het DLP-beleid dat wordt gebruikt voor deze sjabloon voor intern risicobeheer is geconfigureerd voor waarschuwingen met een *hoog* prioriteitsniveau. Bij het *hoge* urgentieniveau worden de triggerende gebeurtenissen en waarschuwingen voor intern risicobeheer niet gegenereerd op basis van regels in DLP-beleid waarbij het veld **Incidentrapporten** is ingesteld op *Laag* of *Gemiddeld*.

    ![Instelling voor DLP-beleidswaarschuwingen](../media/insider-risk-DLP-policy-high-severity.png)

     > [!NOTE]
     > Wanneer u een nieuw DLP-beleid maakt met behulp van de ingebouwde sjablonen, moet u de optie **Geavanceerde DLP-regels maken of aanpassen** selecteren om de instelling **Incidentrapporten** te configureren voor het *hoge* urgentieniveau.

Aan elk intern risicobeheerbeleid dat is gemaakt op basis van de sjabloon **Datalekken**, kan slechts één DLP-beleid worden toegewezen. Overweeg om een speciaal DLP-beleid te maken waarin de verschillende activiteiten worden gecombineerd die u wilt detecteren en gebruiken om gebeurtenissen te activeren voor intern risicobeleid dat gebruik maakt van de sjabloon **Gegevenslekken**.

Zie het artikel [DLP-beleid maken, testen en afstemmen](create-test-tune-dlp-policy.md) voor stapsgewijze instructies voor het configureren van DLP-beleid voor uw organisatie.

### <a name="data-leaks-by-priority-users-preview"></a>Gegevenslekken door prioriteitsgebruikers (voorbeeld)

Het beschermen van gegevens en het voorkomen van gegevenslekken voor gebruikers in uw organisatie kan afhankelijk zijn van hun positie, toegangsniveau tot gevoelige informatie of risicogeschiedenis. Datalekken kunnen het per ongeluk te veel delen van zeer gevoelige informatie buiten uw organisatie of gegevensdiefstal met kwaadwillende bedoelingen omvatten. Met een toegewezen Beleid voor preventie van gegevensverlies (DLP) begint deze sjabloon met het scoren van realtime detecties van verdachte activiteit. Dit resulteert in een verhoogde kans op insider-risicowaarschuwingen en -waarschuwingen met hogere prioriteitsniveaus. Prioriteitsgebruikers worden gedefinieerd in [gebruikersgroepen met prioriteit](insider-risk-management-settings.md#priority-user-groups-preview) die zijn geconfigureerd in het gebied met instellingen voor intern risicobeheer.

Net als bij de sjabloon **Algemene datalekken**, moet u een DLP-beleid toewijzen om indicatoren in het intern risicobeleid te activeren voor waarschuwingen met een hoge prioriteit in uw organisatie. Volg de richtlijnen voor het beleid voor gegevenslekken hierboven wanneer u een beleid maakt met deze sjabloon. Daarnaast moet u prioriteitsgebruikersgroepen toewijzen die zijn gemaakt in **Insider-risicobeheer** > **Instellingen** > **Gebruikersgroepen prioriteit** aan het beleid.

### <a name="data-leaks-by-disgruntled-users-preview"></a>Gegevenslekken door ontevreden gebruikers (voorbeeld)

Wanneer gebruikers stressfactoren op het werk ervaren, kunnen ze ontevreden raken, wat de kans op interne risico's kan vergroten. Deze sjabloon begint met het scoren van gebruikersactiviteit wanneer een indicator wordt geïdentificeerd die verband houdt met ontevredenheid. Voorbeelden zijn onder meer meldingen over prestatieverbeteringen, beoordelingen van slechte prestaties of wijzigingen in de status op functieniveau. Datalekken voor ontevreden gebruikers kunnen het downloaden van bestanden van SharePoint Online en het kopiëren van gegevens naar persoonlijke cloudberichten en opslagdiensten in de buurt van stressfactoren op het werk omvatten.

Wanneer u deze sjabloon gebruikt, moet u ook een Microsoft 365 HR-connector configureren om periodiek notificaties voor prestatieverbeteringen, slechte prestatiebeoordelingsstatus of wijzigingsinformatie op taakniveau te importeren voor gebruikers in uw organisatie. Zie het artikel [Gegevens importeren met de HR-connector](import-hr-data.md) voor stapsgewijze richtlijnen voor het configureren van de Microsoft 365 HR-connector voor uw organisatie.

### <a name="general-security-policy-violations-preview"></a>Algemene schendingen van het beveiligingsbeleid (voorbeeld)

In veel organisaties hebben gebruikers toestemming om software te installeren op hun apparaten of om apparaatinstellingen aan te passen zodat ze taken kunnen uitvoeren. Gebruikers kunnen per ongeluk of met kwaadwillende bedoelingen malware installeren of belangrijke beveiligingsfuncties uitschakelen die helpen bij het beveiligen van informatie op hun apparaat of op uw netwerkbronnen. Deze beleidssjabloon maakt gebruik van beveiligingswaarschuwingen van Microsoft Defender voor Eindpunt om deze activiteiten te scoren en focusdetectie en waarschuwingen op dit risicogebied te richten. Gebruik deze sjabloon om inzicht te geven in schendingen van het beveiligingsbeleid in scenario's waarin gebruikers mogelijk een geschiedenis van schendingen van het beveiligingsbeleid hebben die een indicatie kunnen zijn van een risico van binnenuit.

U moet Microsoft Defender voor Eindpunt in uw organisatie hebben geconfigureerd en Defender voor Eindpunt inschakelen voor integratie van intern risicobeheer in het Defender-beveiligingscentrum om waarschuwingen voor beveiligingsovertredingen te importeren. Zie voor meer informatie over het configureren van Defender voor Eindpunt voor integratie met intern risicobeheer [Geavanceerde functies in Defender voor Eindpunt configureren](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="security-policy-violations-by-departing-users-preview"></a>Schendingen van beveiligingsbeleid door vertrekkende werknemers (voorbeeld)

Vertrekkende gebruikers, of ze op een positieve of negatieve manier vertrekken, kunnen een groter risico vormen voor schendingen van het beveiligingsbeleid. Om te helpen beschermen tegen onbedoelde of kwaadwillende beveiligingsschendingen voor vertrekkende gebruikers, gebruikt deze beleidssjabloon Defender voor Eindpunt-waarschuwingen om inzicht te geven in beveiligingsgerelateerde activiteiten. Deze activiteiten omvatten het installeren van malware of andere mogelijk schadelijke toepassingen door de gebruiker en het uitschakelen van beveiligingsfuncties op hun apparaten. Door gebruik te maken van de [Microsoft 365 HR-connector](import-hr-data.md) of de optie om automatisch te controleren op verwijdering van gebruikersaccounts in Azure Active Directory voor uw organisatie, begint deze sjabloon te scoren voor risico-indicatoren met betrekking tot deze beveiligingsactiviteiten en hoe deze correleren met de arbeidsstatus van de gebruiker.

U moet Microsoft Defender voor Eindpunt in uw organisatie hebben geconfigureerd en Defender voor Eindpunt inschakelen voor integratie van intern risicobeheer in het Defender-beveiligingscentrum om waarschuwingen voor beveiligingsovertredingen te importeren. Zie voor meer informatie over het configureren van Defender voor Eindpunt voor integratie met intern risicobeheer [Geavanceerde functies in Defender voor Eindpunt configureren](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="security-policy-violations-by-priority-users-preview"></a>Schendingen van het beveiligingsbeleid door prioriteitsgebruikers (voorbeeld)

Beveiliging tegen beveiligingsovertredingen voor gebruikers in uw organisatie kan afhankelijk zijn van hun positie, het toegangsniveau tot gevoelige informatie of hun risicogeschiedenis. Omdat beveiligingsschendingen door gebruikers met prioriteit een aanzienlijke impact kunnen hebben op de kritieke gebieden van uw organisatie, begint deze beleidssjabloon te scoren op deze indicatoren en gebruikt het waarschuwingen van Microsoft Defender voor Eindpunt om inzicht te geven in beveiligingsgerelateerde activiteiten voor deze gebruikers. Dit kunnen activiteiten zijn van gebruikers met prioriteit die malware of andere mogelijk schadelijke toepassingen installeren en beveiligingsfuncties op hun apparaten uitschakelen. Gebruikers met prioriteit worden gedefinieerd in gebruikersgroepen met prioriteit die zijn geconfigureerd in het gebied voor risicobeheer voor insiders.

U moet Microsoft Defender voor Eindpunt in uw organisatie hebben geconfigureerd en Defender voor Eindpunt inschakelen voor integratie van intern risicobeheer in het Defender-beveiligingscentrum om waarschuwingen voor beveiligingsovertredingen te importeren. Zie voor meer informatie over het configureren van Defender voor Eindpunt voor integratie met intern risicobeheer [Geavanceerde functies in Defender voor Eindpunt configureren](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center). Daarnaast moet u prioriteitsgebruikersgroepen toewijzen die zijn gemaakt in **Insider-risicobeheer** > **Instellingen** > **Gebruikersgroepen prioriteit** aan het beleid.

### <a name="security-policy-violations-by-disgruntled-users-preview"></a>Schendingen van beveiligingsbeleid door ontevreden gebruikers (voorbeeld)

Gebruikers die stressfactoren op het werk ervaren, lopen mogelijk een groter risico op onbedoelde of kwaadwillende schendingen van het beveiligingsbeleid. Voorbeelden van stressfactoren zijn dat de gebruiker op een prestatieverbeteringsplan wordt geplaatst, een slechte prestatiebeoordelingstatus heeft of wordt gedegradeerd uit zijn huidige positie. Met deze beleidssjabloon wordt de risicoscore gestart op basis van deze indicatoren en activiteiten die aan deze gebeurtenissen voor deze gebruikers zijn gekoppeld.

Wanneer u deze sjabloon gebruikt, moet u ook een Microsoft 365 HR-connector configureren om periodiek notificaties voor prestatieverbeteringen, slechte prestatiebeoordelingsstatus of wijzigingsinformatie op taakniveau te importeren voor gebruikers in uw organisatie. Zie het artikel [Gegevens importeren met de HR-connector](import-hr-data.md) voor stapsgewijze richtlijnen voor het configureren van de Microsoft 365 HR-connector voor uw organisatie.

U moet ook Microsoft Defender voor Eindpunten configureren in uw organisatie en Defender voor Eindpunt inschakelen voor integratie met intern risicobeheer in het Defender-beveiligingscentrum om waarschuwingen over beveiligingsovertreding te importeren. Zie voor meer informatie over het configureren van Defender voor Eindpunt voor integratie met intern risicobeheer [Geavanceerde functies in Defender voor Eindpunt configureren](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="policy-template-prerequisites-and-triggering-events"></a>Vereisten voor beleidssjablonen en het activeren van gebeurtenissen

Afhankelijk van het sjabloon dat u kiest voor een intern beleid voor risicobeheer, variëren de triggergebeurtenissen en beleidsvereisten. Triggergebeurtenissen zijn voorwaarden die bepalen of een gebruiker actief is voor intern beleid risicobeheer. Als een gebruiker wordt toegevoegd aan een intern beleid risicobeheer maar geen triggergebeurtenis heeft, wordt de gebruikersactiviteit niet geëvalueerd door het beleid, tenzij deze handmatig wordt toegevoegd aan het dashboard Gebruikers. Beleidsvereisten zijn vereiste items, zodat het beleid de signalen of activiteiten ontvangt die nodig zijn om het risico te evalueren.

De volgende tabel bevat de triggergebeurtenissen en vereisten voor het beleid dat is gemaakt op basis van elke beleidssjabloon voor intern risicobeheer:

| **Beleidssjabloon** | **Gebeurtenissen activeren voor beleid** | **Vereisten** |
| :------------------ | :--------------------------------- | :---------------- |
| Gegevensdiefstal door vertrekkende gebruikers | Indicator voor het stopzetten of beëindigen van een HR-connector | (optioneel) Microsoft 365 HR-connector geconfigureerd voor beëindigings- en ontslagdatumindicatoren of Azure Active Directory-integratie ingeschakeld |
| Algemene gegevenslekken | Activiteit in het beleid voor het lekken van gegevens, waardoor een waarschuwing met hoge prioriteit wordt gemaakt | (optioneel) DLP-beleid geconfigureerd voor waarschuwingen met hoge urgentie of ingebouwde gegevensextrusie triggergebeurtenis |
| Gegevenslekken per gebruiker met prioriteit | Gegevenslekbeleidsactiviteit die een waarschuwing met *hoge ernst* of ingebouwde gebeurtenisactiveringen voor exfiltratie creëert | (optioneel) DLP-beleid geconfigureerd voor waarschuwingen met hoge prioriteit <br><br> Gebruikersgroepen met prioriteit die zijn geconfigureerd in intern risico-instellingen |
| Gegevenslekken door ontevreden gebruikers | Prestatieverbetering, slechte prestaties of wijzigingsindicatoren op taakniveau via de HR-connector | Microsoft 365 HR-connector geconfigureerd voor ontevredenheidsindicatoren |
| Algemene schendingen beveiligingsbeleid | Defensieve omzeiling van beveiligingsmaatregelen of ongewenste software gedetecteerd door Microsoft Defender voor Eindpunt | Actief abonnement op Microsoft Defender voor Eindpunt <br><br> Integratie van Microsoft Defender voor Eindpunt met het Microsoft 365-compliancecentrum geconfigureerd |
| Schendingen van beveiligingsbeleid door vertrekkende gebruikers | Indicatoren voor ontslag- of beëindigingsdatum van HR-connector of verwijdering van Azure Active Directory-account | (optioneel) Microsoft 365 HR-connector geconfigureerd voor beëindigings- en ontslagdatumindicatoren <br><br> Actief abonnement op Microsoft Defender voor Eindpunt <br><br> Integratie van Microsoft Defender voor Eindpunt met het Microsoft 365-compliancecentrum geconfigureerd |
| Schendingen van beveiligingsbeleid door gebruikers met een prioriteit | Defensieve omzeiling van beveiligingsmaatregelen of ongewenste software gedetecteerd door Microsoft Defender voor Eindpunt | Actief abonnement op Microsoft Defender voor Eindpunt <br><br> Integratie van Microsoft Defender voor Eindpunt met het Microsoft 365-compliancecentrum geconfigureerd <br><br> Gebruikersgroepen met prioriteit die zijn geconfigureerd in intern risico-instellingen |
| Schendingen van het beveiligingsbeleid door een ontevreden gebruiker | Prestatieverbetering, slechte prestaties of wijzigingsindicatoren op taakniveau via de HR-connector | Microsoft 365 HR-connector geconfigureerd voor ontevredenheidsindicatoren <br><br> Actief abonnement op Microsoft Defender voor Eindpunt <br><br> Integratie van Microsoft Defender voor Eindpunt met het Microsoft 365-compliancecentrum geconfigureerd |

## <a name="prioritize-content-in-policies"></a>Prioriteit geven aan inhoud in beleid

Beleid voor intern risicobeheer biedt ondersteuning voor het opgeven van een hogere prioriteit voor inhoud, afhankelijk van waar deze is opgeslagen of hoe deze wordt geclassificeerd. Als inhoud wordt opgegeven als een prioriteit, wordt de risicoscore voor een gekoppelde activiteit verhoogd, waardoor de kans op een hoge prioriteitswaarschuwing toeneemt. Sommige activiteiten genereren echter helemaal geen waarschuwing, tenzij de gerelateerde inhoud ingebouwde of aangepaste gevoelige informatietypen bevat of is opgegeven als prioriteit in het beleid.

Uw organisatie heeft bijvoorbeeld een speciale SharePoint-site voor een zeer vertrouwelijk project. Gegevenslekken met informatie op deze SharePoint-site kunnen het project in gevaar brengen en een grote invloed hebben op het succes ervan. Door prioriteit te geven aan deze SharePoint-site in een beleid voor het lekken van gegevens, worden de risicoscores voor in aanmerking komende activiteiten automatisch verhoogd. Met deze prioriteit wordt de kans vergroot dat deze activiteiten een intern risicowaarschuwing genereren en wordt het urgentieniveau voor de waarschuwing verhoogd.

Wanneer u een intern risicobeheerbeleid maakt in de beleidswizard, kunt u kiezen uit de volgende prioriteiten:

- **SharePoint-sites**: elke activiteit die is gekoppeld aan alle bestandstypen in gedefinieerde SharePoint-sites, krijgt een hogere risicoscore. 
- **Gevoelige informatietypen**: elke activiteit die verband houdt met inhoud die [gevoelige informatietypes](sensitive-information-type-entity-definitions.md) bevat, krijgt een hogere risicoscore.
- **Gevoeligheidslabels**: elke activiteit die is gekoppeld aan inhoud waarop specifieke [gevoeligheidslabels](sensitivity-labels.md) zijn toegepast, krijgt een hogere risicoscore.

## <a name="sequence-detection-preview"></a>Detecties van reeksen (voorbeeld)

Risicovolle activiteiten kunnen plaatsvinden als niet op zichzelf staande gebeurtenissen. Deze risico's maken vaak deel uit van een grotere reeks gebeurtenissen. Een reeks is een groep van twee of meer gebruikersactiviteiten die na elkaar zijn uitgevoerd, wat op verhoogde risico's kan duiden. Het identificeren van deze verwante activiteiten is een belangrijk onderdeel bij het evalueren van het algehele risico. Wanneer sequentie is ingeschakeld voor gegevensdiefstal of beleidsregels voor gegevenslekken, worden inzichten uit sequentiegegevensactiviteiten weergegeven op het tabblad **Gebruikersactiviteit** in een intern risicobeheercase. De volgende beleidssjablonen ondersteunen sequentiedetectie:

- Gegevensdiefstal door vertrekkende gebruikers
- Algemene gegevenslekken
- Gegevenslekken per gebruiker met prioriteit
- Gegevenslekken door ontevreden gebruikers

Deze interne beleidsregels voor risicobeheer kunnen gebruikmaken van specifieke indicatoren en de volgorde waarin ze voorkomen om elke stap in een reeks risico's te detecteren. Bestandsnamen worden gebruikt bij het toewijzen van activiteiten in een reeks. Deze risico's zijn ingedeeld in vier hoofdcategorieën van activiteit:

- **Verzameling**: deze categorie signaleringen richt zich op downloadactiviteiten door gebruikers van het beleid binnen het bereik. Een voorbeeldactiviteit in deze categorie is het downloaden van bestanden van SharePoint-sites.
- **Exfiltratie**: deze categoriesignalen zijn gericht op deel- of extractieactiviteiten naar interne en externe bronnen door beleidsgebruikers die binnen het bereik vallen. Een voorbeeldactiviteit in deze categorie is het verzenden van e-mailberichten met bijlagen van uw organisatie naar externe geadresseerden.
- **Verduistering**: deze categoriesignalen zijn gericht op het maskeren van risicovolle activiteiten door beleidsgebruikers die binnen het bereik vallen. Een voorbeeldactiviteit in deze categorie is het wijzigen van de naam van bestanden op een apparaat.
- **Opschonen**: deze categoriesignalen zijn gericht op verwijderingsactiviteiten door beleidsgebruikers die binnen het bereik vallen. Een voorbeeldactiviteit in deze categorie is het verwijderen van bestanden van een apparaat.

> [!NOTE]
> Reeksdetectie maakt gebruik van indicatoren die zijn ingeschakeld in de algemene instellingen voor intern risicobeheer en indicatoren die zijn geselecteerd in een beleid. Als de juiste indicatoren niet zijn geselecteerd, werkt de reeksdetectie niet.

U kunt afzonderlijke drempelwaarden aanpassen voor elk type reeksdetectie wanneer dit in het beleid is geconfigureerd. Met deze drempelwaarden worden waarschuwingen aangepast op basis van het aantal bestanden dat aan de reeks is gekoppeld.

Voor meer informatie over het beheer van reeksdetectie in de weergave **Gebruikersactiviteit**, zie [Gevallen van insiderrisicobeheer: gebruikersactiviteit](insider-risk-management-cases.md#user-activity).

## <a name="cumulative-exfiltration-detection-preview"></a>Cumulatieve exfiltratiedetectie (voorbeeld)

Insider-risicoindicatoren helpen ongebruikelijke niveaus van risicoactiviteiten te identificeren wanneer ze dagelijks worden geëvalueerd voor gebruikers binnen het insider-risicobeleid. Cumulatieve exfiltratiedetectie maakt gebruik van machine learning-modellen om u te helpen bepalen wanneer exfiltratieactiviteiten van gebruikers de organisatiegemiddelden overschrijden, gemeten in de tijd en over meerdere typen exfiltratieactiviteiten. Analisten en onderzoekers op het gebied van risicobeheer van insiders kunnen cumulatieve inzichten op het gebied van exfiltratiedetectie gebruiken om exfiltratieactiviteiten te identificeren die doorgaans geen waarschuwingen genereren, maar hoger zijn dan wat typisch is voor hun organisatie. Enkele voorbeelden kunnen zijn dat vertrekkende gebruikers langzaam gegevens exfiltreren over een reeks van dagen, of wanneer gebruikers herhaaldelijk gegevens delen via meerdere kanalen, meer dan normaal voor het delen van gegevens voor uw organisatie.

De detectie van cumulatieve exfiltratie is standaard ingeschakeld wanneer u de volgende beleidssjablonen gebruikt:

- Gegevensdiefstal door vertrekkende gebruikers
- Algemene gegevenslekken
- Gegevenslekken per gebruiker met prioriteit
- Gegevenslekken door ontevreden gebruikers

> [!NOTE]
> Cumulatieve exfiltratiedetectie maakt gebruik van exfiltratie-indicatoren die zijn ingeschakeld in de algemene instellingen voor insiderrisicobeheer en exfiltratie-indicatoren die zijn geselecteerd in een beleid. Als zodanig wordt cumulatieve exfiltratiedetectie alleen geëvalueerd voor de noodzakelijke geselecteerde exfiltratie-indicatoren.

Wanneer cumulatieve exfiltratiedetectie is ingeschakeld voor datadiefstal- of datalekbeleid, worden inzichten van cumulatieve exfiltratieactiviteiten weergegeven op het tabblad **Gebruikersactiviteit** binnen een insider-risicobeheercase.

Zie [Insider-risicobeheercases: gebruikersactiviteiten](insider-risk-management-cases.md#user-activity) voor meer informatie over het beheer van gebruikersactiviteiten.

## <a name="policy-health-preview"></a>Beleidsstatus (voorbeeld)

De status van het beleid geeft u inzicht in mogelijke problemen met uw insider-beleid voor risicobeheer. De kolom Status op het tabblad Beleid kan u waarschuwen voor beleidskwesties die ertoe kunnen leiden dat gebruikersactiviteit niet wordt gerapporteerd of waarom het aantal activiteitsmeldingen ongebruikelijk is. De status van het beleid kan ook bevestigen dat het beleid in orde is en geen aandacht of configuratiewijzigingen vereist.

Als er problemen zijn met een beleid, geeft de status van het beleid waarschuwingen en aanbevelingen weer om u te helpen actie te ondernemen om beleidsproblemen op te lossen. Deze meldingen kunnen u helpen de volgende problemen op te lossen:

- Beleidsregels met onvolledige configuratie. Deze problemen kunnen bestaan uit ontbrekende gebruikers of groepen in het beleid of andere onvolledige beleidsconfiguratiestappen.
- Beleid met configuratieproblemen voor indicatoren. Indicatoren zijn een belangrijk onderdeel van elk beleid. Als indicatoren niet zijn geconfigureerd of als er te weinig indicatoren zijn geselecteerd, worden risicovolle activiteiten mogelijk niet zoals verwacht geëvalueerd door het beleid.
- Beleidstriggers werken niet of de vereisten voor beleids triggers zijn niet correct geconfigureerd. Beleidsfunctionaliteit kan afhankelijk zijn van andere services of configuratievereisten om activerende gebeurtenissen effectief te detecteren om risicoscore-toewijzing aan gebruikers in het beleid te activeren. Deze afhankelijkheden kunnen problemen omvatten met de configuratie van connectors, het delen van waarschuwingen voor Microsoft Defender voor Eindpunt of beleidsinstellingen voor preventie van gegevensverlies.
- Volumelimieten naderen of worden overschreden. Insider-beleid voor risicobeheer maakt gebruik van een groot aantal Microsoft 365-services en -eindpunten om risicoactiviteitssignalen samen te stellen. Afhankelijk van het aantal gebruikers in uw beleid kunnen volumelimieten de identificatie en rapportage van risicoactiviteiten vertragen. Meer informatie over deze limieten kunt u lezen in de sectie Beleidssjabloonlimieten van dit artikel.

Als u snel de statusstatus van een beleid wilt bekijken, navigeert u naar het tabblad Beleid en de kolom Status. Hier ziet u de volgende statusopties voor de beleidsstatus voor elk beleid:

- In orde: er zijn geen problemen geïdentificeerd met het beleid.
- Aanbevelingen: er zijn enkele problemen met het beleid waardoor het beleid mogelijk niet werkt zoals verwacht.
- Waarschuwingen: er zijn problemen met het beleid waardoor risicovolle activiteiten niet kunnen worden geidentificeerd.

Voor meer informatie over aanbevelingen of waarschuwingen selecteert u een beleid op het tabblad **Beleid** om de kaart met beleidsdetails te openen. Meer informatie over de aanbevelingen en waarschuwingen, waaronder richtlijnen voor het oplossen van deze problemen, wordt weergegeven in de sectie Meldingen van de detailkaart.

![Beleidsstatus voor intern risicobeheer](../media/insider-risk-policy-health.png)

In de volgende tabel vindt u meer informatie over aanbevelingen en waarschuwingsmeldingen en acties die u kunt uitvoeren om potentiële problemen op te lossen.

|**Meldingsberichten**|**Beleidssjablonen**|**Oorzaken / Probeer deze actie om op te lossen**|
|:------------------------|:-------------------|:---------------------------|
| Beleid kent geen risicoscores toe aan activiteit. | Alle beleidssjablonen | Mogelijk wilt u het bereik van uw beleid herzien en de configuratie van gebeurtenissen zo activeren dat het beleid risicoscores kan toewijzen aan activiteiten <br><br> 1. Controleer de gebruikers die zijn geselecteerd voor het beleid. Als er slechts weinig gebruikers zijn geselecteerd, kunt u extra gebruikers selecteren. <br> 2. Als u een HR-connector gebruikt, controleert u of uw HR-connector de juiste gegevens verstuurt. <br> 3. Als u DLP-beleid gebruikt als triggeringsgebeurtenis, controleert u de configuratie van uw DLP-beleid om te controleren of dit is geconfigureerd voor gebruik in dit beleid. <br> 4. Voor beveiligingsovertredingsbeleid bekijkt u de meldingsstatus van Microsoft Defender voor eindpunt die is geselecteerd in Insider-risico-instellingen > intelligente detecties. Controleer of het waarschuwingsfilter niet te beperkend is ingesteld. |
| Het beleid heeft geen waarschuwingen gegenereerd. | Alle beleidssjablonen | Mogelijk wilt u uw beleidsconfiguratie bekijken, zodat u de score van de activiteit analyseert die voor u belangrijk is. <br><br> 1. Controleer of u indicatoren hebt geselecteerd die u als score wilt gebruiken. Hoe meer indicatoren zijn geselecteerd, hoe meer activiteiten risicoscores krijgen toegewezen. <br> 2. Controleer de aanpassingen van de drempelwaarde voor beleid. Als de geselecteerde drempelwaarden niet in overeenstemming zijn met de risicotolerantie van uw organisatie, past u de selecties aan zodat waarschuwingen worden gemaakt op basis van de drempelwaarden van uw voorkeur. <br> 3. Controleer de gebruikers en groepen die zijn geselecteerd voor het beleid. Controleer of u alle toepasselijke gebruikers en groepen hebt geselecteerd. <br> 4. Bevestig bij beveiligingsovertredingsbeleid dat u de triagestatus hebt geselecteerd die u wilt gebruiken voor waarschuwingen van Microsoft Defender voor Eindpunt onder Intelligente detecties in instellingen.|
| Er zijn geen gebruikers of groepen in dit beleid opgenomen. | Alle beleidssjablonen | Gebruikers of groepen worden niet toegewezen aan het beleid. <br><br> Bewerk uw beleid en selecteer gebruikers of groepen voor het beleid. |
| Er zijn geen indicatoren geselecteerd voor dit beleid. | Alle beleidssjablonen | Er zijn geen indicatoren geselecteerd voor dit beleid. <br><br> Bewerk uw beleid en selecteer de juiste beleidsindicatoren voor het beleid. |
| Er zijn geen gebruikersgroepen met prioriteit opgenomen in dit beleid. | - Gegevenslekken per gebruiker met prioriteit <br> - Schendingen van beveiligingsbeleid door gebruikers met een prioriteit | Gebruikers of groepen worden niet toegewezen aan het beleid. <br><br> Configureer prioritaire gebruikersgroepen in Insider-instellingen voor risicobeheer en wijs prioritaire gebruikersgroepen toe aan het beleid. |
| Er is geen triggergebeurtenis geselecteerd voor dit beleid. | Alle beleidssjablonen | Er is geen triggeringgebeurtenis geconfigureerd voor het beleid <br><br> Risicoscores worden pas aan gebruikersactiviteiten toegewezen wanneer u het beleid bewerkt en een triggeringgebeurtenis selecteert. |
| HR-connector is niet geconfigureerd of werkt niet zoals verwacht. | - Gegevensdiefstal door vertrekkende gebruikers <br> - Schendingen van beveiligingsbeleid door gebruiker die het bedrijf verlaat <br> - Gegevenslekken door ontevreden gebruikers <br> - Schendingen van het beveiligingsbeleid door een ontevreden gebruiker | Er is een probleem met de HR-connector. <br><br> 1. Als u een HR-connector gebruikt, controleert u of uw HR-connector de juiste gegevens verstuurt. <br><br> OF <br><br> 2. Selecteer het Azure AD-account dat is verwijderd voor het activeren van de gebeurtenis. |
| Er zijn geen apparaten geïmplementeerd | - Gegevensdiefstal door vertrekkende gebruikers <br> - Algemene gegevenslekken <br> - Gegevenslekken door ontevreden gebruikers <br> - Gegevenslekken per gebruiker met prioriteit | Apparaatindicatoren zijn geselecteerd, maar er zijn geen apparaten geïmplementeerd voor Microsoft 365 <br><br> Controleer of apparaten zijn geïmplementeerd en voldoen aan de eisen. |
| De HR-connector heeft onlangs geen gegevens geïmporteerd. | - Gegevensdiefstal door vertrekkende gebruikers <br> - Schendingen van beveiligingsbeleid door gebruiker die het bedrijf verlaat <br> - Gegevenslekken door ontevreden gebruikers <br> - Schendingen van het beveiligingsbeleid door een ontevreden gebruiker | De HR-connector heeft in meer dan zeven dagen geen gegevens geïmporteerd. <br><br> Controleer of uw HR-connector juist is geconfigureerd en of het gegevens verzendt. |
| De status van uw HR-connector kan momenteel niet worden gecontroleerd. Probeer het later opnieuw | - Gegevensdiefstal door vertrekkende gebruikers <br> - Schendingen van beveiligingsbeleid door gebruiker die het bedrijf verlaat <br> - Gegevenslekken door ontevreden gebruikers <br> - Schendingen van het beveiligingsbeleid door een ontevreden gebruiker | De insider-oplossing voor risicobeheer kan de status van uw HR-connector niet controleren. <br><br> Controleer of uw HR-connector juist is geconfigureerd en gegevens verstuurt, of kom terug en controleer de status van het beleid.  |
| DLP-beleid is niet geselecteerd als de triggergebeurtenis. | - Algemene gegevenslekken <br> - Gegevenslekken per gebruiker met prioriteit | Een DLP-beleid is niet geselecteerd als een triggeringgebeurtenis of het geselecteerde DLP-beleid is verwijderd. <br><br> Bewerk het beleid en selecteer een actief DLP-beleid of 'Gebruiker voert een exfiltratieactiviteit uit' als de activerende gebeurtenis in de beleidsconfiguratie. |
| Het DLP-beleid dat in dit beleid wordt gebruikt, is uitgeschakeld. | - Algemene gegevenslekken <br> - Gegevenslekken per gebruiker met prioriteit | Het DLP-beleid dat in dit beleid wordt gebruikt, is uitgeschakeld. <br><br> 1. Schakel het DLP-beleid in dat aan dit beleid is toegewezen. <br><br> OF <br><br> Bewerk dit beleid en selecteer een nieuw DLP-beleid of 'Gebruiker voert een exfiltratieactiviteit uit' als de activerende gebeurtenis in de beleidsconfiguratie. |
| DLP-beleid voldoet niet aan vereisten. | - Algemene gegevenslekken <br> - Gegevenslekken per gebruiker met prioriteit | DLP-beleid dat wordt gebruikt als triggering-gebeurtenissen, moeten zo worden geconfigureerd dat waarschuwingen met hoge prioriteit worden gegenereerd. <br><br>  1. Bewerk uw DLP-beleid om toepasselijke waarschuwingen toe te wijzen *met hoge prioriteit*. <br><br> OF <br><br> 2. Bewerk dit beleid en selecteer *Gebruiker voert een exfiltratie-activiteit uit* als de triggeringgebeurtenis. |
| Uw organisatie heeft geen abonnement op Microsoft Defender voor Eindpunt. | - Algemene schendingen beveiligingsbeleid <br> - Schendingen van beveiligingsbeleid door vertrekkende gebruikers <br> - Schendingen van het beveiligingsbeleid door een ontevreden gebruiker <br> - Schendingen van beveiligingsbeleid door gebruikers met een prioriteit | Er is geen actief abonnement op Microsoft Defender voor Eindpunt gedetecteerd voor uw organisatie. <br><br> Totdat een Microsoft Defender for Endpoint-abonnement is toegevoegd, wijst dit beleid geen risicoscores toe aan gebruikersactiviteit. |
| Microsoft Defender voor Eindpunt-waarschuwingen worden niet gedeeld met het compliancecentrum. | - Algemene schendingen beveiligingsbeleid <br> - Schendingen van beveiligingsbeleid door vertrekkende gebruikers <br> - Schendingen van het beveiligingsbeleid door een ontevreden gebruiker <br> - Schendingen van beveiligingsbeleid door gebruikers met een prioriteit | Microsoft Defender voor Eindpunt-waarschuwingen worden niet gedeeld met het compliancecentrum. <br><br> Het delen van waarschuwingen van Microsoft Defender voor Eindpunt configureren. |
| U nadert de maximale limiet van gebruikers die actief worden gescoord voor deze beleidssjabloon. | Alle beleidssjablonen | Elke beleidssjabloon heeft een maximum aantal gebruikers binnen het bereik. Zie de sectiedetails voor limieten voor sjablonen. <br><br> Controleer de gebruikers op het tabblad Gebruikers en verwijder alle gebruikers die niet langer hoeven te worden beoordeeld. |

## <a name="policy-template-limits"></a>Limieten voor beleidssjablonen

Beleidssjablonen voor Insider-risicobeheer gebruiken limieten voor het beheren van het volume en de snelheid van verwerking voor risicoactiviteiten van gebruikers binnen het bereik en hoe dit proces is geïntegreerd met de ondersteuning van Microsoft 365-services. Elke beleidssjabloon heeft een maximum aantal gebruikers waaraan actief risicoscores kunnen worden toegewezen voor het beleid dat het kan ondersteunen en die risicoactiviteiten effectief kunnen verwerken en rapporteren. Gebruikers binnen het bereik zijn gebruikers die gebeurtenissen activeren voor het beleid.

De limiet voor elk beleid wordt berekend op basis van het totale aantal unieke gebruikers dat risicoscores per type beleidssjabloon ontvangt. Als het aantal gebruikers voor een type beleidssjabloon de gebruikerslimiet benadert of overschrijdt, worden de prestaties van het beleid verminderd. Als u het huidige aantal gebruikers voor een beleid wilt weergeven, gaat u naar het tabblad Beleid en de kolom Gebruikers in bereik. U kunt maximaal vijf beleidsregels hebben voor een beleidssjabloon. Deze maximumlimieten gelden voor alle gebruikers in alle beleidsregels die een bepaalde beleidssjabloon gebruiken.

Gebruik de volgende tabel om het maximum aantal gebruikers in het bereik te bepalen dat voor elke beleidssjabloon wordt ondersteund:

|**Beleidssjabloon**|**Huidig maximum aantal gebruikers binnen het bereik**|
|:------------------|:--------------------------------|
| Algemene gegevenslekken | 15.000 |
| Gegevenslekken door ontevreden gebruikers | 7.500 |
| Gegevenslekken per gebruiker met prioriteit | 1000 |
| Gegevensdiefstal door vertrekkende gebruikers | 20.000 |
| Algemene schendingen beveiligingsbeleid | 1000 |
| Schendingen van beveiligingsbeleid door gebruikers met een prioriteit | 1000 |
| Schendingen van beveiligingsbeleid door vertrekkende gebruikers | 15.000 |
| Schendingen van het beveiligingsbeleid door een ontevreden gebruiker | 7.500 |

## <a name="create-a-new-policy"></a>Een nieuw beleid maken

Als u een nieuw intern risicobeheerbeleid wilt maken, gebruikt u de beleidswizard in **Insider-** -oplossing in het Compliancecentrum van Microsoft 365.

Voltooi de volgende stappen om een nieuw beleid te maken:

1. Ga in het [Compliancecentrum van Microsoft 365](https://compliance.microsoft.com)naar **Intern risicobeheer** en selecteer het tabblad **Beleid**.
2. Selecteer **Beleid maken** om de wizard Beleid te openen.
3. Kies op de pagina **Beleidssjabloon** een beleidscategorie en selecteer vervolgens de sjabloon voor het nieuwe beleid. Deze sjablonen bestaan uit voorwaarden en indicatoren waarmee de risicoactiviteiten worden gedefinieerd die u wilt detecteren en onderzoeken. Bekijk de vereisten voor de sjabloon, triggering van gebeurtenissen en gedetecteerde activiteiten om te controleren of deze beleidssjabloon aan uw wensen voldoet.

    > [!IMPORTANT]
    > Sommige beleidssjablonen hebben vereisten die moeten worden geconfigureerd voor het genereren van relevante waarschuwingen voor het beleid. Zie **stap 4** hierboven als u de toepasselijke beleidsvereisten niet hebt geconfigureerd.

4. Selecteer **Volgende** om door te gaan.
5. Vul op de pagina **Naam en beschrijving** de volgende velden in:
    - **Naam (vereist)**: geef een gebruiksvriendelijke naam voor het beleid op. Deze naam kan niet worden gewijzigd nadat het beleid is gemaakt.
    - **Beschrijving (optioneel)**: voer een optionele beschrijving in voor het beleid.

6. Selecteer **Volgende** om door te gaan.
7. Selecteer op de pagina **Gebruikers en groepen** de optie **Alle gebruikers en groepen opnemen** of **Neem specifieke gebruikers en groepen op** om te bepalen welke gebruikers of groepen in het beleid zijn opgenomen, of als u een sjabloon op basis van prioriteit voor gebruikers hebt gekozen; selecteer **Gebruikersgroepen met prioriteit toevoegen of bewerken**. Als u **Alle gebruikers en groepen opnemen** selecteert, wordt gezocht naar activeringsgebeurtenissen voor alle gebruikers en groepen in uw organisatie om te beginnen met het toewijzen van risicoscores voor het beleid. Als u **Specifieke gebruikers en groepen opnemen** selecteert, kunt u definiëren welke gebruikers en groepen moeten worden toegewezen aan het beleid.
8. Selecteer **Volgende** om door te gaan.
9. Op de pagina **Te prioriteren inhoud** kunt u (indien nodig) de bronnen toewijzen die prioriteit moeten krijgen, waardoor de kans op het genereren van een waarschuwing met een hoge ernst voor deze bronnen toeneemt. Selecteer een van de volgende opties:

    - **Ja, ik wil SharePoint-sites, gevoeligheidslabels en/of gevoelige gegevenstypen als prioriteitsinhoud aanwijzen**. Als u deze optie selecteert, kunnen deze kanalen worden geconfigureerd op detailpagina's in de wizard.
    - **Ik wil nu geen prioriteitsinhoud opgeven (u kunt dit doen nadat het beleid is gemaakt)**. Als u deze optie selecteert, worden de pagina's met kanaaldetails in de wizard overgeslagen.

10. Selecteer **Volgende** om door te gaan.

11. Als u in de vorige stap **Ik wil SharePoint-sites, gevoeligheidslabels en/of gevoelige informatietypen als prioriteitsinhoud** hebt geselecteerd, ziet u de detailpagina's voor *SharePoint-sites*, *Gevoelige informatietypen* en *Gevoeligheidslabels*. Gebruik deze detailpagina's om de SharePoint, typen gevoelige informatie en gevoeligheidslabels te definiëren die in het beleid prioriteit moeten krijgen.

    - **SharePoint-sites**: selecteer **SharePoint-site toevoegen** en selecteer de SharePoint-sites waartoe u toegang hebt en die u prioriteit wilt geven. Bijvoorbeeld *'group1@contoso.sharepoint.com/sites/group1'*.
    - **Type gevoelige informatie**: selecteer **Type gevoelige informatie toevoegen** en selecteer de gevoeligheidstypen die u prioriteit wilt geven. Bijvoorbeeld *'Amerikaans bankrekeningnummer'* *'Creditcardnummer'*.
    - **Gevoeligheidslabels**: selecteer **Een gevoeligheidslabel toevoegen** en selecteer de labels aan wie u een prioriteit wilt toevoegen. Bijvoorbeeld *'Vertrouwelijk'* en *'Geheim'*.

12. Selecteer **Volgende** om door te gaan.
13. Op de pagina **Indicatoren en activeringsgebeurtenissen** ziet u de [indicatoren](insider-risk-management-settings.md#indicators) die u hebt gedefinieerd als beschikbaar op de pagina **Indicatoren** voor **Insider-risico-instellingen** > . Als u aan het begin van de wizard een sjabloon voor *gegevenslekken* hebt geselecteerd, moet u een **DLP-beleid** selecteren in de vervolgkeuzelijst DLP-beleid om triggeringindicatoren voor het beleid in te schakelen of de ingebouwde activeringsgebeurtenis selecteren.

    > [!IMPORTANT]
    > Als indicatoren op deze pagina niet kunnen worden geselecteerd, selecteert u de indicatoren die u voor alle beleidsregels wilt inschakelen. U kunt de knop **Indicatoren inschakelen** in de wizard gebruiken of indicatoren selecteren op de pagina **Intern risicobeheer** > **Instellingen** > **Beleidsindicatoren**.

    Selecteer de indicatoren die u wilt toepassen op het beleid. Als u liever geen gebruik wilt maken van de standaardinstellingen voor drempelwaarden voor deze indicatoren, schakelt u de optie **Standaard drempelwaarden gebruiken die door Microsoft worden aanbevolen** uit en voert u de drempelwaarden in voor elke geselecteerde indicator.

    - Als u ten minste één *Office*- of *apparaat*-indicator hebt geselecteerd, selecteert u de **risicoscore-boosters** die van toepassing zijn. Risicoscore-boosters zijn alleen van toepassing op geselecteerde indicatoren.
    - Als u een beleidssjabloon voor *gegevensdiefstal* of *gegevenslekken* hebt geselecteerd, selecteert u een of meer **sequentiedetectie**-methoden en een **cumulatieve exfiltratiedetectie**-methode om op het beleid toe te passen.

14. Selecteer **Volgende** om door te gaan.
15. Selecteer op de pagina **Indicatordrempels** de optie om standaardindicatordrempels te gebruiken of om aangepaste drempels voor individuele indicatoren op te geven. Kies voor elke indicator het juiste niveau om het gewenste niveau van activiteitswaarschuwingen te genereren.
16. Selecteer **Volgende** om door te gaan.
17. Bekijk op de pagina **Controleren** de instellingen die u voor het beleid heeft gekozen en eventuele suggesties of waarschuwingen voor uw selecties. Selecteer **Bewerken** om een van de beleidswaarden te wijzigen of selecteer **Verzenden** om het beleid te maken en te activeren.

## <a name="update-a-policy"></a>Een beleid bijwerken

Als u een bestaand intern risicobeheerbeleid wilt bijwerken, gebruikt u de beleidswizard van de **Intern risicobeheer**-oplossing in het Compliancecentrum van Microsoft 365.

Voltooi de volgende stappen om een bestaand beleid te beheren:

1. Ga in het [Compliancecentrum van Microsoft 365](https://compliance.microsoft.com)naar **Intern risicobeheer** en selecteer het tabblad **Beleid**.
2. Selecteer op het beleidsdashboard het beleid dat u wilt beheren.
3. Selecteer op de pagina beleidsdetails de optie **Beleid bewerken**
4. In de wizard Beleid kunt u het volgende niet bewerken:
    - **Beleidssjabloon**: de sjabloon die wordt gebruikt voor het definiëren van de typen risico-indicatoren die door het beleid worden gecontroleerd.
    - **Naam**: de gebruiksvriendelijke naam voor het beleid
5. Werk op de pagina **Naam en beschrijving** de beschrijving van het beleid bij in het veld **Beschrijving**.
6. Selecteer **Volgende** om door te gaan.
7. Selecteer op de pagina **Gebruikers en groepen** de optie **Alle gebruikers en groepen opnemen** of **Neem specifieke gebruikers en groepen op** om te bepalen welke gebruikers of groepen in het beleid zijn opgenomen, of als u een sjabloon op basis van prioriteit voor gebruikers hebt gekozen; selecteer **Gebruikersgroepen met prioriteit toevoegen of bewerken**. Als u **Alle gebruikers en groepen opnemen** selecteert, wordt gezocht naar activeringsgebeurtenissen voor alle gebruikers en groepen in uw organisatie om te beginnen met het toewijzen van risicoscores voor het beleid. Als u **Specifieke gebruikers en groepen opnemen** selecteert, kunt u definiëren welke gebruikers en groepen moeten worden toegewezen aan het beleid.
8. Selecteer **Volgende** om door te gaan.
9. Op de pagina **Te prioriteren inhoud** kunt u (indien nodig) de bronnen toewijzen die prioriteit moeten krijgen, waardoor de kans op het genereren van een waarschuwing met een hoge ernst voor deze bronnen toeneemt. Selecteer een van de volgende opties:

    - **Ja, ik wil SharePoint-sites, gevoeligheidslabels en/of gevoelige gegevenstypen als prioriteitsinhoud aanwijzen**. Als u deze optie selecteert, kunnen deze kanalen worden geconfigureerd op detailpagina's in de wizard.
    - **Ik wil nu geen prioriteitsinhoud opgeven (u kunt dit doen nadat het beleid is gemaakt)**. Als u deze optie selecteert, worden de pagina's met kanaaldetails in de wizard overgeslagen.

10. Selecteer **Volgende** om door te gaan.

11. Als u in de vorige stap **Ik wil SharePoint-sites, gevoeligheidslabels en/of gevoelige informatietypen als prioriteitsinhoud** hebt geselecteerd, ziet u de detailpagina's voor *SharePoint-sites*, *Gevoelige informatietypen* en *Gevoeligheidslabels*. Gebruik deze detailpagina's om de SharePoint, typen gevoelige informatie en gevoeligheidslabels te definiëren die in het beleid prioriteit moeten krijgen.

    - **SharePoint-sites**: selecteer **SharePoint-site toevoegen** en selecteer de SharePoint-sites waartoe u toegang hebt en die u prioriteit wilt geven. Bijvoorbeeld *'group1@contoso.sharepoint.com/sites/group1'*.
    - **Type gevoelige informatie**: selecteer **Type gevoelige informatie toevoegen** en selecteer de gevoeligheidstypen die u prioriteit wilt geven. Bijvoorbeeld *'Amerikaans bankrekeningnummer'* *'Creditcardnummer'*.
    - **Gevoeligheidslabels**: selecteer **Een gevoeligheidslabel toevoegen** en selecteer de labels aan wie u een prioriteit wilt toevoegen. Bijvoorbeeld *'Vertrouwelijk'* en *'Geheim'*.

12. Selecteer **Volgende** om door te gaan.
13. Op de pagina **Indicatoren en activeringsgebeurtenissen** ziet u de [indicatoren](insider-risk-management-settings.md#indicators) die u hebt gedefinieerd als beschikbaar op de pagina **Indicatoren** voor **Insider-risico-instellingen** > . Als u aan het begin van de wizard een sjabloon voor *gegevenslekken* hebt geselecteerd, moet u een **DLP-beleid** selecteren in de vervolgkeuzelijst DLP-beleid om triggeringindicatoren voor het beleid in te schakelen of de ingebouwde activeringsgebeurtenis selecteren.

    > [!IMPORTANT]
    > Als indicatoren op deze pagina niet kunnen worden geselecteerd, selecteert u de indicatoren die u voor alle beleidsregels wilt inschakelen. U kunt de knop **Indicatoren inschakelen** in de wizard gebruiken of indicatoren selecteren op de pagina **Intern risicobeheer** > **Instellingen** > **Beleidsindicatoren**.

    Selecteer de indicatoren die u wilt toepassen op het beleid. Als u liever geen gebruik wilt maken van de standaardinstellingen voor drempelwaarden voor deze indicatoren, schakelt u de optie **Standaard drempelwaarden gebruiken die door Microsoft worden aanbevolen** uit en voert u de drempelwaarden in voor elke geselecteerde indicator.

    - Als u ten minste één *Office*- of *apparaat*-indicator hebt geselecteerd, selecteert u de **risicoscore-boosters** die van toepassing zijn. Risicoscore-boosters zijn alleen van toepassing op geselecteerde indicatoren.
    - Als u een beleidssjabloon voor *gegevensdiefstal* of *gegevenslekken* hebt geselecteerd, selecteert u een of meer **sequentiedetectie**-methoden en een **cumulatieve exfiltratiedetectie**-methode om op het beleid toe te passen.

14. Selecteer **Volgende** om door te gaan.
15. Selecteer op de pagina **Indicatordrempels** de optie om standaardindicatordrempels te gebruiken of om aangepaste drempels voor individuele indicatoren op te geven. Kies voor elke indicator het juiste niveau om het gewenste niveau van activiteitswaarschuwingen te genereren.
16. Selecteer **Volgende** om door te gaan.
17. Bekijk op de pagina **Controleren** de instellingen die u voor het beleid heeft gekozen en eventuele suggesties of waarschuwingen voor uw selecties. Selecteer **Bewerken** om een van de beleidswaarden te wijzigen of selecteer **Verzenden** om het beleid te maken en te activeren.

## <a name="copy-a-policy"></a>Een beleid kopiëren

Mogelijk moet u een nieuw beleid maken dat lijkt op een bestaand beleid, maar dat slechts een paar configuratiewijzigingen nodig heeft. In plaats van een nieuw beleid te maken, kunt u een bestaand beleid kopiëren en vervolgens de gebieden wijzigen die moeten worden bijgewerkt in het nieuwe beleid.

Voltooi de volgende stappen om een bestaand beleid te kopiëren:

1. Ga in het Compliancecentrum van Microsoft 365 naar Intern risicobeheer en selecteer het tabblad Beleid.
2. Selecteer op het beleidsdashboard het beleid dat u wilt kopiëren.
3. Selecteer Kopiëren op de pagina Beleidsdetails.
4. Geef het nieuwe beleid een naam in de beleidswizard en werk de beleidsconfiguratie indien nodig bij.

## <a name="immediately-start-scoring-user-activity"></a>Begin onmiddellijk met het scoren van gebruikersactiviteit

Er kunnen scenario's zijn waarin u onmiddellijk risicoscores moet gaan toewijzen aan gebruikers met een intern risicobeleid buiten de workflow voor intern risicobeheer die gebeurtenissen triggert. Gebruik **Een scoreactiviteit starten voor gebruikers** op het tabblad **Beleid** om handmatig een gebruiker (of gebruikers) toe te voegen aan een of meer insiderrisicobeleid voor een bepaalde tijd, om onmiddellijk risicoscores toe te wijzen aan hun activiteit en om de vereiste voor een gebruiker om een trigger-indicator te hebben (zoals een DLP-beleidsovereenkomst), te omzeilen. U kunt ook een reden toevoegen voor het toevoegen van de gebruiker aan het beleid, dat wordt weergegeven op de tijdlijn voor activiteiten van de gebruiker. Gebruikers die handmatig aan beleid zijn toegevoegd, worden weergegeven in het dashboard **Gebruikers** en waarschuwingen worden gemaakt als de activiteit voldoet aan de drempelwaarden voor beleidswaarschuwingen.

Enkele scenario's waarin u mogelijk direct wilt beginnen met het scoren van gebruikersactiviteiten:

- Wanneer er gebruikers zijn geïdentificeerd die mogelijk een risico vormen, en u wilt direct beginnen met het toewijzen van risicoscores aan hun activiteiten voor een of meer van uw beleidsregels
- Wanneer er zich een incident heeft voorgedaan waardoor u mogelijk direct wilt beginnen met het toewijzen van risicoscores voor de activiteiten van betrokken gebruikers voor een of meer van uw beleidsregels
- Wanneer u uw HR-connector nog niet hebt geconfigureerd, maar u wilt beginnen met het toewijzen van risicoscores aan gebruikersactiviteiten voor HR-gebeurtenissen door een CSV-bestand te uploaden voor de gebruikers

> [!NOTE]
> Het kan enkele uren duren voordat nieuwe handmatig toegevoegde gebruikers worden weergegeven op het dashboard **Gebruikers**. Het kan tot 24 uur duren voordat de activiteiten van de afgelopen 90 dagen voor deze gebruikers worden weergegeven. Om activiteiten voor handmatig toegevoegde gebruikers te bekijken, navigeert u naar het tabblad **Gebruikers** en selecteert u de gebruiker op het **Gebruikers**-dashboard en opent u het tabblad **Gebruikersactiviteit** in het detailvenster.

Voer de volgende stappen uit om handmatig scoreactiviteit voor gebruikers te starten in een of meer beleidsregels voor intern risicobeheer:

1. Ga in het [Compliancecentrum van Microsoft 365](https://compliance.microsoft.com)naar **Intern risicobeheer** en selecteer het tabblad **Beleid**.
2. Selecteer op het beleidsdashboard het beleid of de beleidsregels waar u gebruikers aan wilt toevoegen.
3. Selecteer **Scoreactiviteit starten voor gebruikers**.
4. Voeg in het veld **Reden** in het deelvenster **Gebruikers aan meerdere beleidsregels toevoegen** een reden toe voor het toevoegen van de gebruikers.
5. Definieer in het veld **Dit duurt (kies een waarde tussen 5 en 30 dagen)** het aantal dagen om de activiteit van de gebruiker te scoren voor het beleid waaraan ze zijn toegevoegd
6. Om in uw Active Directory naar gebruikers te zoeken, gebruikt u het veld **Gebruiker zoeken om toe te voegen aan beleidsregels**. Typ de naam van de gebruiker die u aan het beleid wilt toevoegen. Selecteer de gebruikersnaam en herhaal deze optie om meerdere gebruikers aan het beleid toe te wijzen. De lijst met gebruikers die u hebt geselecteerd, wordt weergegeven in de sectie Gebruikers van het deelvenster Gebruikers toevoegen aan meerdere beleidsregels.
7. Als u een lijst met gebruikers wilt importeren die u aan het beleid wilt toevoegen, selecteert u **Importeren** om een csv-bestand (met door komma's gescheiden waarden) te importeren. Het bestand moet de volgende indeling hebben en u moet de User Principal-namen in het bestand opnoemen:

    ```csv
    user principal name
    user1@domain.com
    user2@domain.com
    ```

8. Selecteer het beleid Gebruikers toevoegen aan beleid om de wijzigingen te accepteren en gebruikers aan het beleid toe te voegen of selecteer Annuleren om de wijzigingen te negeren en het dialoogvenster te sluiten.

## <a name="stop-scoring-users-in-a-policy"></a>Stop met het scoren van gebruikers in een beleid

Zie het artikel [Intern risicobeheergebruikers: gebruikers verwijderen uit toewijzing binnen het bereik aan beleid](insider-risk-management-users.md#remove-users-from-in-scope-assignment-to-policies) om te stoppen met het scoren van gebruikers in een beleid.

## <a name="delete-a-policy"></a>Een beleid verwijderen

> [!NOTE]
> Als u een beleid verwijdert, worden actieve of gearchiveerde waarschuwingen die op basis van het beleid zijn gegenereerd, niet verwijderd.

Als u een bestaand beleid voor intern risicobeheer wilt verwijderen, moet u de volgende stappen voltooien:

1. Ga in het [Compliancecentrum van Microsoft 365](https://compliance.microsoft.com)naar **Intern risicobeheer** en selecteer het tabblad **Beleid**.
2. Selecteer op het beleidsdashboard het beleid dat u wilt verwijderen.
3. Selecteer **Verwijderen** op de dashboardwerkbalk.
4. Selecteer in dialoogvenster **Verwijderen** de optie **Ja** om het beleid te verwijderen of selecteer **Annuleren** om het dialoogvenster te sluiten.
