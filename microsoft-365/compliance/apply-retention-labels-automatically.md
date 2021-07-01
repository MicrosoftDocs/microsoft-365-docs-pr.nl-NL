---
title: Automatisch een retentielabel toepassen om inhoud te behouden of te verwijderen
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Retentielabels en beleidsregels voor automatisch labelen maken, zodat u automatisch labels kunt toepassen om te behouden wat u nodig hebt en te verwijderen wat u niet nodig hebt
ms.openlocfilehash: fa1d88271593f0278266004d4a170a807e1cbc32
ms.sourcegitcommit: 2266c2da090bc9a6dc1e01dea07f26901d20d57b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53222680"
---
# <a name="automatically-apply-a-retention-label-to-retain-or-delete-content"></a>Automatisch een retentielabel toepassen om inhoud te behouden of te verwijderen

>*[Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

> [!NOTE]
> Dit scenario wordt niet ondersteund voor [wettelijk verplichte records](records-management.md#records).

Een van de krachtigste functies van [retentielabels](retention.md) is de mogelijkheid om deze automatisch toe te passen op inhoud die aan bepaalde voorwaarden voldoet. In dit geval hoeven personen in uw organisatie de retentielabels niet toe te passen. Microsoft 365 doet het werk voor hen.
  
Het automatisch toepassen van retentielabels is een krachtige functie omdat:
  
- U uw gebruikers niet hoeft te trainen in al uw classificaties.
    
- U niet hoeft te vertrouwen op gebruikers om alle inhoud op de juiste manier te classificeren.
    
- Gebruikers hoeven niet langer meer op de hoogte te zijn van beleidsregels voor gegevensbeheer. Ze kunnen zich op hun werk concentreren.
    
U kunt retentielabels automatisch toepassen op inhoud wanneer deze inhoud gevoelige informatie, trefwoorden of doorzoekbare eigenschappen of een overeenkomst voor [trainbare classificaties](classifier-get-started-with.md) bevat.

> [!TIP]
> Gebruik de onlangs uitgebrachte doorzoekbare eigenschappen om [opnamen van een Teams-vergadering](#microsoft-teams-meeting-recordings) te herkennen.

De processen voor het automatisch toepassen van een bewaarlabel op basis van deze voorwaarden:

![Diagram met rollen en taken voor het automatisch toepassen van labels](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)

Gebruik de volgende instructies voor de twee beheerstappen.

> [!NOTE]
> Bij automatisch beleid wordt labelen aan servicezijde gebruikt met voorwaarden om automatisch bewaarlabels toe te passen. U kunt ook automatisch een bewaarlabel met een labelbeleid toepassen wanneer u het volgende doet: 
>
> - Een bewaarlabel toepassen op een document met een model voor het begrijpen van informatie in SharePoint Syntex
> - Een standaard retentielabel toepassen voor SharePoint en Outlook
>- Een retentielabel toepassen op e-mail met behulp van Outlook-regels
>
> Zie [Labels voor bewaarbeleid maken en toepassen in apps](create-apply-retention-labels.md) voor deze scenario's.

## <a name="before-you-begin"></a>Voordat u begint

De globale beheerder voor uw organisatie heeft volledige machtigingen om retentielabels en hun beleid te maken en te bewerken. Zie [Vereiste machtigingen om bewaarbeleid en bewaarlabels te maken en te beheren](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels) als u niet bent aangemeld als globale beheerder.

## <a name="how-to-auto-apply-a-retention-label"></a>Automatisch een retentielabel toepassen

Maak eerst uw retentielabel. Maak vervolgens een beleid om dat label automatisch toe te passen. Ga verder naar [Een automatisch beleid maken](#step-2-create-an-auto-apply-policy) als u het retentielabel al hebt gemaakt.

De navigatie-instructies zijn afhankelijk van of u al dan niet [recordbeheer](records-management.md) gebruikt. Er worden instructies gegeven voor beide scenario's.

### <a name="step-1-create-a-retention-label"></a>Stap 1: maak een retentielabel

1. Ga in het [Microsoft 365-compliancecentrum](https://compliance.microsoft.com/) naar een van de volgende locaties:
    
    - Als u recordbeheer gebruikt:
        - **Oplossingen** > **Recordbeheer** > **Bestandsplan** > **+ Een label maken** > **Retentielabel**
        
    - Als u geen recordbeheer gebruikt:
       - **Oplossingen** > **Informatiebeheer** > **Labels** > + **Een label maken**
    
    Ziet u de optie niet direct? Selecteer eerst **Alles weergeven**. 

2. Volg de aanwijzingen in de wizard. Als u recordbeheer gebruikt:
    
    - Zie [Bestandsplan gebruiken voor het beheren van retentielabels](file-plan-manager.md) voor meer informatie over de beschrijvingen van het bestandsplan
    
    - Schakel **Items markeren als records** of **Items markeren als wettelijke records** in als u het bewaarlabel wilt gebruiken om records te declareren. Zie het artikel [Retentielabels configureren om records te declareren](declare-records.md#configuring-retention-labels-to-declare-records) voor meer informatie.

3. Nadat u het label hebt gemaakt en de opties voor het publiceren van het label ziet, kunt u het label automatisch toepassen of gewoon opslaan: Selecteer **Dit label automatisch toepassen op een specifiek type inhoud** en selecteer vervolgens **Gereed** om de wizard Automatisch labelen te starten. U gaat daarna direct naar stap 2 in de volgende procedure.

Als u een bestaand label wilt bewerken, selecteert u het en selecteert u vervolgens de optie **Label bewerken** om de wizard Bewaarbeleid bewerken te starten. U kunt daarin de labelbeschrijvingen en eventuele [in aanmerking komende instellingen](#updating-retention-labels-and-their-policies) wijzigen vanaf stap 2.

### <a name="step-2-create-an-auto-apply-policy"></a>Stap 2: maak een beleid voor automatisch toepassen

Wanneer u een beleid voor automatisch toepassen maakt, selecteert u een bewaarlabel dat automatisch moet worden toegepast op inhoud op basis van de voorwaarden die u opgeeft.

1. Ga in het [Microsoft 365-compliancecentrum](https://compliance.microsoft.com/) naar een van de volgende locaties:
    
    - Als u recordbeheer gebruikt: **Informatiebeheer**:
        - **Oplossingen** > **Recordbeheer** > **Labelbeleid** > **Een label automatisch toepassen**
    
    - Als u geen recordbeheer gebruikt:
        - **Oplossingen** > **Informatiebeheer** > **Labelbeleid** > **Een label automatisch toepassen**
    
    Ziet u de optie niet direct? Selecteer eerst **Alles weergeven**. 

2. Volg de aanwijzingen in de wizard Automatisch labelen.
    
    Zie de sectie [Voorwaarden configureren voor het automatisch toepassen van retentielabels](#configuring-conditions-for-auto-apply-retention-labels) op deze pagina voor informatie over het configureren van de voorwaarden voor het automatisch toepassen van het retentielabel.
    
    Zie de sectie [Retentielabels en -locaties](retention.md#retention-label-policies-and-locations) voor meer informatie over de locaties die door retentielabels worden ondersteund.

U kunt een bestaand beleid voor automatisch toepassen bewerken door het te selecteren, zodat de wizard Bewaarbeleid bewerken wordt gestart. Vanaf stap 2 kunt u het geselecteerde retentielabel en alle [in aanmerking komende instellingen](#updating-retention-labels-and-their-policies) wijzigen.

Nadat inhoud is gelabeld met behulp van een beleid voor het automatisch toepassen van labels, kan het toegepaste label niet automatisch worden verwijderd of gewijzigd door de inhoud of het beleid te wijzigen of door een nieuw labelbeleid automatisch toe te passen. Zie [Slechts één bewaarlabel tegelijk](retention.md#only-one-retention-label-at-a-time) voor meer informatie.

### <a name="configuring-conditions-for-auto-apply-retention-labels"></a>Voorwaarden configureren voor het automatisch toepassen van retentielabels

U kunt retentielabels automatisch toepassen op inhoud wanneer deze inhoud het volgende bevat:

- [Specifieke typen gevoelige informatie](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)

- [Specifieke trefwoorden of doorzoekbare eigenschappen die overeenkomen met een query die u maakt](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [Een overeenkomst voor trainbare classificaties](#auto-apply-labels-to-content-by-using-trainable-classifiers)

#### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a>Automatisch labels toepassen op inhoud met specifieke typen gevoelige informatie

> [!WARNING]
> Deze configuratie kent momenteel een bekende beperking, waarbij voor alle e-mailberichten zonder label altijd het geselecteerde bewaarlabel wordt toegepast wanneer er een overeenkomst is met de door u gekozen typen gevoelige informatie. Zelfs als u bijvoorbeeld het beleid voor automatisch toepassen op specifieke gebruikers of andere locaties dan Exchange selecteert, wordt het label altijd toegepast op e-mailberichten zonder label wanneer er een overeenkomst is.

Wanneer u beleid maakt om automatisch retentielabels toe te passen op gevoelige informatie, ziet u dezelfde lijst met beleidssjablonen als bij het maken van een DLP-beleid (preventie van gegevensverlies). Elke sjabloon is vooraf geconfigureerd om te zoeken naar specifieke typen gevoelige informatie. In het volgende voorbeeld zijn de typen gevoelige informatie afkomstig uit de categorie **Privacy** en de sjabloon **PII-gegevens (persoonlijke gegevens)**:

![Beleidssjablonen met typen gevoelige informatie](../media/sensitive-info-configuration.png)

Zie [Entiteitsdefinities van typen gevoelige informatie](sensitive-information-type-entity-definitions.md) voor meer informatie over de typen gevoelige informatie. Momenteel worden [exacte gegevensovereenkomsten](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) en [fingerprinting van documenten](document-fingerprinting.md) niet ondersteund voor dit scenario.

Nadat u een beleidssjabloon hebt geselecteerd, kunt u alle typen gevoelige informatie toevoegen of verwijderen en kunt u de betrouwbaarheidswaarde en het aantal exemplaren wijzigen. In het vorige voorbeeld van een schermafbeelding zijn deze opties gewijzigd, zodat een retentielabel alleen automatisch wordt toegepast wanneer:
  
- Voor het gedetecteerde type gevoelige informatie is de nauwkeurigheid van de overeenkomst (of het [betrouwbaarheidsniveau](sensitive-information-type-learn-about.md#more-on-confidence-levels)) ten minste **Gemiddelde betrouwbaarheid** voor twee van de typen gevoelige informatie en **Hoge betrouwbaarheid** voor een type. Veel typen gevoelige informatie worden gedefinieerd met meerdere patronen, waarbij voor een patroon met een hogere nauwkeurigheid meer bewijs (zoals trefwoorden, datums of adressen) nodig is, terwijl voor een patroon met een lagere nauwkeurigheid minder bewijs nodig is. Hoe lager het betrouwbaarheidsniveau, hoe eerder de inhoud overeenkomt met de voorwaarde, maar met een grotere kans op fout-positieven.

- De inhoud bevat 1 tot 9 exemplaren van elk van deze drie typen gevoelige informatie. De standaardinstelling voor de waarde **tot** is **Elke**.

Zie voor meer informatie over deze opties de volgende richtlijnen in de DLP-documentatie [Regels afstemmen zodat deze eenvoudiger of moeilijker overeenkomen](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).

Overweeg het volgende wanneer u typen gevoelige informatie gebruikt om automatisch retentielabels toe te passen:

- Nieuwe en gewijzigde items kunnen automatisch worden gelabeld.

#### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a>Pas automatisch labels toe op inhoud met trefwoorden of doorzoekbare eigenschappen

U kunt automatisch labels toepassen op inhoud door een query te gebruiken die specifieke woorden, woordgroepen of waarden van doorzoekbare eigenschappen bevat. U kunt uw query verfijnen met behulp van zoekoperatoren zoals EN, OF en NIET.

![Queryeditor](../media/new-retention-query-editor.png)

Zie [Keyword Query Language-syntaxisverwijzing (KQL)](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) voor meer informatie over de querysyntaxis die KQL (Keyword Query Language) gebruikt.

Gebruik voor beleid voor het automatisch toepassen op basis van query'dezelfde zoekindex als voor het zoeken naar eDiscovery-inhoud om inhoud te identificeren. Raadpleeg [Trefwoordquery's en zoekvoorwaarden voor Inhoud zoeken](keyword-queries-and-search-conditions.md) voor meer informatie over de doorzoekbare eigenschappen die u kunt gebruiken.

Enkele dingen waarmee u rekening moet houden bij het gebruik van trefwoorden of doorzoekbare eigenschappen om automatisch labels voor bewaarbeleid toe te passen:

- Nieuwe, gewijzigde en bestaande items worden automatisch gelabeld voor SharePoint, OneDrive en Exchange.

- SharePoint ondersteunt geen verkende en aangepaste eigenschappen voor deze KQL-query's en u moet alleen vooraf gedefinieerde beheerde eigenschappen voor documenten gebruiken. U kunt echter toewijzingen op tenantniveau gebruiken met de vooraf gedefinieerde beheerde eigenschappen die standaard zijn ingeschakeld als verfijningen (RefinableDate00-19, RefinableString00-99, RefinableInt00-49, RefinableDecimals00-09 en RefinableDouble00-09). Zie [Overzicht van verkende en beheerde eigenschappen in SharePoint Server](/SharePoint/technical-reference/crawled-and-managed-properties-overview) voor meer informatie en zie [Een nieuwe beheerde eigenschap maken](/sharepoint/manage-search-schema#create-a-new-managed-property) voor instructies.

- Als u een aangepaste eigenschap aan een van de verfijningseigenschappen toewijst, moet u 24 uur wachten voordat u deze in uw KQL-query kunt gebruiken voor een retentielabel.

- Beheerde eigenschappen in SharePoint kunnen worden gewijzigd door aliassen te gebruiken, maar u moet deze niet gebruiken voor KQL-query's in uw etiketten. Geef altijd de feitelijke naam op van de beheerde eigenschap, bijvoorbeeld 'RefinableString01'.

- Gebruik dubbele aanhalingstekens (`" "`) als u wilt zoeken naar waarden die spaties of speciale tekens bevatten; bijvoorbeeld `subject:"Financial Statements"`.

- Gebruik de *Documentlink*-eigenschap in plaats van *pad* om een overeenkomst met een item te vinden op basis van de URL van het item. 

- Er wordt geen ondersteuning geboden voor zoekopdrachten met een voorafgaand jokerteken (zoals `*cat`) of waarbij er behalve het jokerteken achter de tekenreeks een ander jokerteken wordt (zoals `*cat*`). Zoekopdrachten met erachter een jokerteken (zoals `cat*`) worden wel ondersteund.

- Let op: gedeeltelijk geïndexeerde items kunnen ertoe leiden dat items niet worden gelabeld zoals u verwacht of dat items worden gelabeld waarvan u had verwacht dat ze zouden worden uitgesloten wanneer u de NOT-operator gebruikt. Zie [Gedeeltelijk geïndexeerde items in Inhoud zoeken](partially-indexed-items-in-content-search.md) voor meer informatie.


Voorbeelden van query's:

| Workload | Voorbeeld |
|:-----|:-----|
|Exchange   | `subject:"Financial Statements"` |
|Exchange   | `recipients:garthf@contoso.com` |
|SharePoint | `contenttype:document` |
|SharePoint | `site:https://contoso.sharepoint.com/sites/teams/procurement AND contenttype:document`|
|Exchange of SharePoint | `"customer information" OR "private"`|

Complexere voorbeelden:

Met de volgende query voor SharePoint worden Word-documenten of Excel-spreadsheets geïdentificeerd wanneer deze bestanden de trefwoorden **password**, **passwords** of **pw** bevatten:

```
(password OR passwords OR pw) AND (filetype:doc* OR filetype:xls*)
```

Met de volgende query voor Exchange wordt elk Word-document of PDF-document geïdentificeerd dat het woord **nda** of de frase **non disclosure agreement** bevat wanneer deze documenten aan een e-mailbericht zijn gekoppeld:

```
(nda OR "non disclosure agreement") AND (attachmentnames:.doc* OR attachmentnames:.pdf)
```

Met de volgende query voor SharePoint worden documenten geïdentificeerd die een creditcardnummer bevatten: 

```
sensitivetype:"credit card number"
```

De volgende query bevat enkele veelgebruikte trefwoorden om documenten of e-mailberichten met juridische inhoud te identificeren:

```
ACP OR (Attorney Client Privilege*) OR (AC Privilege)
```

De volgende query bevat veelgebruikte trefwoorden om documenten of e-mailberichten voor personeelszaken te identificeren: 

```
(resume AND staff AND employee AND salary AND recruitment AND candidate)
```

Houd er rekening mee dat in dit laatste voorbeeld de beproefde methode wordt gebruikt om altijd operatoren tussen trefwoorden op te nemen. Een spatie tussen trefwoorden (of twee expressies in de vorm eigenschap:waarde) is hetzelfde als het gebruik van AND. Door altijd operatoren toe te voegen, kunt u gemakkelijker zien dat met deze voorbeeldquery alleen inhoud wordt geïdentificeerd die al deze trefwoorden bevat in plaats van inhoud die een van de trefwoorden bevat. Gebruik OR in plaats van AND als u inhoud wilt identificeren die een van de trefwoorden bevat. Zoals u in dit voorbeeld ziet, kunt u de query gemakkelijker interpreteren wanneer u altijd de operatoren opgeeft. 

##### <a name="microsoft-teams-meeting-recordings"></a>Opnamen van Microsoft Teams-vergaderingen

> [!NOTE]
> De mogelijkheid om opnamen van Teams-vergaderingen te behouden en te verwijderen werkt niet voordat opnamen worden opgeslagen in OneDrive of SharePoint. Zie [OneDrive voor Bedrijven en SharePoint Online of Stream gebruiken om vergaderingen op te nemen](/MicrosoftTeams/tmr-meeting-recording-change) voor meer informatie.

Geef het volgende op voor de **Keyword Query Editor** als u wilt weten welke opnamen van een vergadering in Microsoft Teams in de OneDrive-accounts van gebruikers of in SharePoint zijn opgeslagen:

``` 
ProgID:Media AND ProgID:Meeting
```

Meestal worden opnamen van een vergadering opgeslagen in OneDrive. Maar voor kanaalvergaderingen worden ze opgeslagen in SharePoint.


#### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a>Labels automatisch toepassen op inhoud met trainbare classificaties

Wanneer u de optie voor een trainbare classificatie kiest, kunt u een van de ingebouwde classificaties of een aangepaste classificatie selecteren. De ingebouwde classificaties zijn **cv's**, **broncode**, **gerichte intimidatie**, **grofheid** en **bedreiging**:

![Trainbare classificaties kiezen](../media/retention-label-classifers.png)

> [!CAUTION]
> De ingebouwde classificatie **Grof taalgebruik** wordt afgeschaft omdat er veel fout-positieven worden geproduceerd. Gebruik deze ingebouwde classificatie niet en mocht u deze momenteel gebruiken, moet u deze niet voor uw bedrijfsprocessen gebruiken. U wordt aangeraden in plaats daarvan de ingebouwde classificaties **Gerichte intimidatie**, **Scheldwoorden** en **Bedreiging** te gebruiken.

Als u deze optie wilt gebruiken om automatisch een label toe te passen, moeten SharePoint-sites en -postvakken minimaal 10 MB aan gegevens bevatten.

Zie [Informatie over trainbare classificaties](classifier-learn-about.md) voor meer informatie over trainbare classificaties.

> [!TIP]
> Raadpleeg [Een classificatie opnieuw trainen voor de inhoudsverkenner](classifier-how-to-retrain-content-explorer.md) als u trainbare classificaties voor Exchange gebruikt.

Overweeg het volgende wanneer u trainbare classificaties gebruikt om automatisch retentielabels toe te passen:

- Nieuwe en gewijzigde items en bestaande items uit de afgelopen zes maanden kunnen automatisch worden gelabeld.

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a>Hoe lang het duurt voordat retentielabels van kracht worden

Wanneer u automatisch retentielabels toepast, kan het maximaal zeven dagen duren voordat de labels zijn toegepast op alle bestaande inhoud die aan de voorwaarden voldoet.
  
![Diagram van wanneer handmatig toegepaste labels van kracht worden](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)

Controleer de **Status** van het beleid voor het automatisch aanbrengen van labels door dit te selecteren op de pagina **Labelbeleid** in het compliancecentrum als de verwachte labels na zeven dagen niet worden weergegeven. Als u de status **Uit (Fout)** ziet en in de details voor de locaties een bericht wordt weergegeven dat het langer duurt dan verwacht om het beleid te implementeren (voor SharePoint) of dat moet worden geprobeerd om het beleid opnieuw te implementeren (voor OneDrive), kunt u de PowerShell-opdracht [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) uitvoeren om de beleidsdistributie opnieuw te proberen:

1. [Verbinding maken met Beveiligings- en compliancecentrum van Powershell](/powershell/exchange/connect-to-scc-powershell).

2. Voer de volgende opdracht uit:
    
    ``` PowerShell
    Set-RetentionCompliancePolicy -Identity <policy name> -RetryDistribution
   ```

## <a name="updating-retention-labels-and-their-policies"></a>Retentielabels en hun beleid bijwerken

Wanneer u een retentielabel of beleid voor het automatisch toepassen van labels bewerkt en het retentielabel al op inhoud is toegepast, worden de bijgewerkte instellingen automatisch toegepast op deze inhoud, naast de nieuw vastgestelde inhoud.

Sommige instellingen kunnen niet worden gewijzigd nadat het label of beleid is gemaakt en opgeslagen, waaronder:
- De naam van het retentielabel en bewaarbeleid, en de bewaarinstellingen met uitzondering van de retentieperiode. U kunt de retentieperiode echter niet wijzigen wanneer de retentieperiode is gebaseerd op het moment waarop een label aan items werd toegekend.
- De optie voor het markeren van items als een record.

### <a name="deleting-retention-labels"></a>Retentielabels verwijderen

U kunt retentielabels die momenteel niet zijn opgenomen in een retentielabelbeleid, die niet zijn geconfigureerd voor bewaren op basis van gebeurtenissen, of die items markeren als wettelijke records verwijderen.

Het verwijderen van retentielabels die u kunt verwijderen mislukt als ze op items zijn toegepast. U ziet dan een koppeling naar de inhoudsverkenner om de gelabelde items te identificeren.

Het kan echter maximaal twee dagen duren voordat de items met een label in de inhoudsverkenner worden weergegeven. In dit scenario wordt het retentielabel mogelijk verwijderd zonder dat u de koppeling naar de inhoudsverkenner ziet.

## <a name="locking-the-policy-to-prevent-changes"></a>Het beleid vergrendelen om wijzigingen te voorkomen

Zie [Behoudvergrendeling gebruiken om wijzigingen in bewaarbeleid en bewaarlabelbeleid te beperken](retention-preservation-lock.md) als u ervoor wilt zorgen dat niemand het beleid kan uitschakelen, verwijderen of verruimen.

## <a name="next-steps"></a>Volgende stappen

Zie [Retentielabels gebruiken voor het beheren van de levenscyclus van documenten die zijn opgeslagen in SharePoint](auto-apply-retention-labels-scenario.md) voor een voorbeeldscenario waarin automatisch een retentielabelbeleid wordt toegepast met beheerde eigenschappen in SharePoint en retentiebeleid op basis van gebeurtenissen om de retentieperiode te starten.