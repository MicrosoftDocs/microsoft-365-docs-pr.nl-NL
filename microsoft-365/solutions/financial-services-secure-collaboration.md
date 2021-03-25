---
title: Belangrijkste overwegingen op het gebied van compliance en beveiliging voor Amerikaanse banken en kapitaalmarkten
ms.author: bcarter
author: brendacarter
manager: laurawi
audience: ITPro
ms.topic: article
ms.collection:
- M365-security-compliance
ms.prod: microsoft-365-enterprise
ms.custom: seo-marvel-jun2020
localization_priority: Priority
description: Lees hoe financiële dienstverlening aan financiële compliance kan voldoen en effectief kan samenwerken met Microsoft 365 en Teams.
f1.keywords: NOCSH
ms.openlocfilehash: f7e32502994f89451d8016ed5664ebe3591dcc8d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51200339"
---
# <a name="key-compliance-and-security-considerations-for-us-banking-and-capital-markets"></a>Belangrijkste overwegingen op het gebied van compliance en beveiliging voor Amerikaanse banken en kapitaalmarkten

## <a name="introduction"></a>Inleiding
Financiële dienstverleners gaan verder dan de meeste commerciële bedrijven wat betreft de vraag naar strenge beveiligings-, compliance- en beheercontroles. De bescherming van gegevens, identiteiten, apparaten en toepassingen is niet alleen van cruciaal belang voor hun bedrijf, het is onderhevig aan compliancevereisten en richtlijnen van regelgevende instanties zoals de Amerikaanse Securities and Exchange Commission (SEC), de Financial Industry Regulatory Authority (FINRA), de Federal Financial Institutions Examination Council (FFIEC) en de Commodity Futures Trading Commission (CFTC). Daarnaast moeten financiële instellingen zich houden aan wetten zoals Dodd-Frank en de Sarbanes-Oxley Act uit 2002.

In het huidige klimaat van verhoogde waakzaamheid, interne risico's en inbreuken op openbare gegevens, eisen klanten ook een hoog beveiligingsniveau van hun financiële instellingen zodat ze hun persoonlijke gegevens en bankactiva aan hen kunnen toevertrouwen.

Historisch gezien had de behoefte aan uitgebreide controles een directe impact op de IT-systemen en platforms die financiële instellingen gebruiken om intern en extern samen te werken. Tegenwoordig hebben werknemers in de financiële dienstverlening een modern samenwerkingsplatform nodig dat gemakkelijk te gebruiken is. Maar bij financiële services is een flexibele samenwerking moeilijk tussen gebruikers, teams en afdelingen met beveiligings- en compliancecontroles die beleid afdwingen om gebruikers en IT-systemen te beschermen tegen bedreigingen.

In de financiële dienstverlening is zorgvuldige afweging vereist voor de configuratie en implementatie van samenwerkingstools en veiligheidscontroles, waaronder:
- Risicoanalyse voor algemene samenwerking binnen de organisatie en scenario's voor bedrijfsprocessen
- Vereisten voor informatiebescherming en gegevensbeheer
- Cyberbeveiliging en interne bedreigingen
- Wettelijke compliancevereisten
- Andere operationele risico's

**Microsoft 365 is een moderne cloudomgeving op de werkplek die is afgestemd op de hedendaagse uitdagingen waarmee financiële dienstverleners worden geconfronteerd. Veilige en flexibele samenwerking binnen de onderneming wordt gecombineerd met controles en handhaving van het beleid om te voldoen aan strikte regelgevingskaders.** In dit artikel wordt beschreven hoe u financiële services via het Microsoft 365-platform kunt overzetten naar een modern samenwerkingsplatform, waarbij gegevens en systemen beveiligd blijven conform de regelgeving:

* De productiviteit van organisaties en werknemers mogelijk maken met behulp van Microsoft 365 en Microsoft Teams
* Moderne samenwerking beveiligen met Microsoft 365 
* Gevoelige gegevens identificeren en verlies van gegevens voorkomen
* Het bedrijf beschermen
* Gegevens beheren en voldoen aan regelgeving door records effectief te beheren
* Ethische normen met informatiebarrières vaststellen
* Beschermen tegen data-exfiltratie en interne risico's

Als Microsoft-partner heeft Protiviti bijgedragen aan dit artikel door belangrijke feedback te geven.

De volgende downloadbare illustraties vullen dit artikel aan. Woodgrove Bank en Contoso worden gebruikt om aan te tonen hoe de in dit artikel beschreven mogelijkheden kunnen worden toegepast om te voldoen aan algemene regelgevingsvereisten voor financiële services. U kunt deze illustraties aan uw eigen wensen aanpassen. 

**Illustraties voor informatiebeveiliging en naleving in Microsoft 365**

| Item | Beschrijving |
|:-----|:-----|
|[![Modelposter: Microsoft 365-gegevensbescherming en nalevingsmogelijkheden](../media/solutions-architecture-center/m365-compliance-illustrations-thumb.png)](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf) <br/>Engels: [Downloaden als PDF](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf)\| [Downloaden als Visio  ](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.vsdx) <br/> Japans: [Downloaden als PDF](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.pdf)\| [Downloaden als Visio  ](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.vsdx)<br/> Laatst bijgewerkt: november 2020|Omvat: <ul><li>  Microsoft informatiebescherming en preventie van gegevensverlies</li><li>Bewaarbeleid en retentielabels </li><li>Informatiebelemmeringen</li><li>Communicatiecompliance</li><li>Insider-risico</li><li>Gegevens ingestie van derden</li>|


## <a name="empower-organizational-and-employee-productivity-by-using-microsoft-365-and-teams"></a>Versterk de productiviteit van organisaties en medewerkers door Microsoft 365 en Teams te gebruiken

Samenwerking vereist meestal verschillende vormen van communicatie, de mogelijkheid om documenten/gegevens op te slaan en te openen en de mogelijkheid om zo nodig andere toepassingen te integreren. Werknemers in de financiële dienstverlening moeten meestal samenwerken en communiceren met leden van andere afdelingen of teams en soms met externe entiteiten. Daarom kunt u beter geen systemen gebruiken die silo's maken of het delen van informatie bemoeilijken. In plaats daarvan kunt u beter platforms en toepassingen gebruiken waarmee medewerkers veilig kunnen communiceren, samenwerken en informatie kunnen delen volgens het bedrijfsbeleid.

Door medewerkers een modern samenwerkingsplatform in de cloud te bieden, kunnen ze tools kiezen en integreren waarmee ze productiever worden en flexibel kunnen werken. Door Teams te gebruiken in combinatie met veiligheidscontroles en beleid voor informatiebeheer die de organisatie beschermen, kunnen uw medewerkers effectief communiceren en samenwerken.

Teams biedt een samenwerkingshub voor de organisatie. Zo kunnen mensen samenwerken aan algemene initiatieven en projecten. Met Teams kunnen teamleden een-op-een en met meerdere partijen chatten, samenwerken aan documenten en bestanden opslaan en delen. Met Teams kunt u ook zakelijke onlinevergaderingen houden via geïntegreerde spraak en video. Teams kan ook worden aangepast met Microsoft-apps, zoals Microsoft Planner, Microsoft Dynamics 365, PowerApps, Power BI en externe line-of-business-toepassingen. Teams is bedoeld voor gebruik door zowel interne teamleden als gemachtigde externe gebruikers die kunnen deelnemen aan teamkanalen en chatgesprekken, toegang hebben tot opgeslagen bestanden en andere toepassingen kunnen gebruiken

Elk Microsoft-team wordt ondersteund door een Microsoft 365-groep. Deze groep wordt beschouwd als de lidmaatschapsservice voor diverse Office 365-services, waaronder Teams. Microsoft 365-groepen worden gebruikt om op een veilige manier onderscheid te maken tussen 'eigenaren' en 'leden' en om de toegang tot verschillende functies binnen Teams te beheren. Als Teams wordt gekoppeld aan de juiste beheerfuncties met regelmatig beheerde toegangscontroles, kunnen alleen leden en eigenaren de geautoriseerde kanalen en functionaliteit gebruiken.

Een veelvoorkomend scenario waarbij Teams financiële services ondersteunt, is bij het uitvoeren van interne projecten of programma's. Veel financiële instellingen, waaronder banken, vermogensbeheerders, kredietverenigingen en verzekeringsmaatschappijen, zijn bijvoorbeeld verplicht om antiwitwas- en andere complianceprogramma's te implementeren. Een multifunctioneel team bestaande uit IT, bedrijfstakken zoals retail- en vermogensbeheer en een eenheid voor financiële misdaadbestrijding, kan nodig zijn om gegevens met elkaar te delen en te communiceren over het programma of specifieke onderzoeken. Vroeger gebruikten deze programma's gedeelde netwerkschijven, maar dit voor diverse uitdagingen zorgen, waaronder:
* Er kan slechts één persoon tegelijk een document bewerken.
* Het beheren van beveiliging is tijdrovend omdat IT meestal moet worden ingeschakeld voor het toevoegen/verwijderen van personen.
* Gegevens blijven veel langer op gedeelde netwerkschijven staan dan nodig of gewenst is.

Teams biedt een samenwerkingsruimte waarin gevoelige klantgegevens veilig kunnen worden opgeslagen en teamleden gevoelige onderwerpen kunnen bespreken. Meerdere leden van het team kunnen één document tegelijk bewerken of hieraan samenwerken. De eigenaar van het programma of de coördinator kan worden geconfigureerd als de teameigenaar en kan vervolgens leden toevoegen en verwijderen.

Een ander algemeen scenario is het gebruik van Teams als 'virtuele gegevensruimte' om veilig samen te werken, waaronder het opslaan en beheren van documenten. Teamleden en syndicaten binnen investeringsbankieren, vermogensbeheer of private-equityfirma's kunnen veilig samenwerken aan een deal of investering. Multifunctionele teams zijn vaak betrokken bij het plannen en uitvoeren van dergelijke deals en de mogelijkheid om veilig gegevens te delen en gesprekken te voeren, is een kernvereiste. Het delen van gerelateerde documenten met externe investeerders is ook een essentiële vereiste. Teams bieden een veilige en volledig controleerbare locatie voor het centraal opslaan, beschermen en delen van investeringsgegevens.

![Een groep kantoormedewerkers in een vergadering bespreekt afbeeldingen op een groot scherm](../media/m365cO19-ent-dell-latitude13-5951.jpg)
 
### <a name="teams-improve-collaboration-and-reduce-compliance-risk"></a>Teams: betere samenwerking en minder compliancerisico

Microsoft 365 biedt andere algemene beleidsmogelijkheden voor Teams door het gebruik van Microsoft 365-groepen als onderliggende lidmaatschapsservice. Met dit beleid kunt u de samenwerking verbeteren en aan de compliancevereisten voldoen.

Het **naamgevingsbeleid voor Microsoft 365-groepen** zorgt ervoor dat Microsoft 365-groepen, ofwel teams, een naam krijgen volgens het bedrijfsbeleid. Namen kunnen problematisch zijn als ze niet geschikt zijn. Het is bijvoorbeeld mogelijk dat werknemers niet weten voor welke teams ze moeten werken of met welke teams ze informatie kunnen delen als namen niet op de juiste manier worden toegepast. Groepsnaamgevingsbeleid (inclusief ondersteuning voor op voorvoegsel/achtervoegsel gebaseerde beleidsregels en aangepaste geblokkeerde woorden) kan een goede 'hygiëne' afdwingen en het gebruik van specifieke woorden, zoals gereserveerde woorden of ongepaste terminologie, voorkomen.
  
Het **beleid voor het verlopen van Microsoft 365-groepen** helpt ervoor te zorgen dat Microsoft 365-groepen, ofwel teams, niet langer worden bewaard dan de organisatie wil of nodig heeft. Met deze functie voorkomt u twee belangrijke problemen met informatiebeheer:

* Wildgroei van teams die niet nodig zijn of niet worden gebruikt.
* Het bewaren van gegevens die niet meer nodig zijn of worden gebruikt door de organisatie (met uitzondering van juridische bewaarplicht/bewaring).

Beheerders kunnen een verloopperiode opgeven voor Microsoft 365-groepen, bijvoorbeeld 90, 180 of 365 dagen. Als een service die wordt ondersteund door een Microsoft 365-groep, inactief is gedurende de vervalperiode, worden groepseigenaren op de hoogte gesteld. Als er geen actie wordt ondernomen, worden de Microsoft 365-groep en alle bijbehorende services, inclusief Teams, verwijderd.
  
Het bewaren van gegevens die zijn opgeslagen in Teams en andere groepsservices, kan risico's vormen voor financiële dienstverleners. Het verloopbeleid van Microsoft 365-groepen wordt aanbevolen om te voorkomen dat gegevens worden bewaard die niet meer nodig zijn. In combinatie met ingebouwde bewaarlabels en -beleid helpt Microsoft 365 ervoor te zorgen dat organisaties alleen de gegevens bewaren die nodig zijn om te voldoen aan het bedrijfsbeleid en wettelijke complianceverplichtingen.

#### <a name="teams-integrate-custom-requirements-with-ease"></a>Teams: eenvoudig aangepaste vereisten integreren

Met Teams kunt u standaard zelf teams maken. Veel gereguleerde organisaties willen echter controleren en begrijpen welke samenwerkingskanalen momenteel door hun werknemers worden gebruikt, welke kanalen mogelijk gevoelige gegevens bevatten en het eigendom van organisatiekanalen zijn. Om deze beheercontroles te vergemakkelijken, kan de organisatie in Microsoft 365 het zelf maken van teams uitschakelen. Door gebruik te maken van automatiseringstools voor bedrijfsprocessen, zoals Microsoft Power Apps en Power Automate, kunnen organisaties eenvoudige formulieren en goedkeuringsprocessen maken en implementeren voor werknemers, zodat ze kunnen aanvragen om een nieuw team te maken. Na goedkeuring kan het team automatisch worden ingericht en een koppeling naar de aanvrager worden gestuurd. Op deze manier kunnen organisaties hun compliancecontroles en aangepaste vereisten ontwerpen en integreren in het teamcreatieproces.
 
### <a name="acceptable-digital-communication-channels"></a>Acceptabele digitale communicatiekanalen

FINRA [benadrukt dat de digitale communicatie van gereguleerde bedrijven voldoet aan de archiveringsvereisten van Exchange Act-regels 17a-3 en 17a-4, evenals FINRA-regelserie 4510 ](https://www.finra.org/rules-guidance/key-topics/books-records). FINRA brengt een jaarverslag uit met belangrijke conclusies, bevindingen en effectieve praktijken op basis waarvan organisaties compliance en risicobeheer kunnen verbeteren. In het [rapport over onderzoeksresultaten en bevindingen uit 2019](https://www.finra.org/rules-guidance/guidance/reports/2019-report-exam-findings-and-observations) identificeerde FINRA digitale communicatie als een belangrijk gebied waar bedrijven uitdagingen tegenkomen die voldoen aan de vereisten voor toezicht en archivering.

Als een organisatie haar werknemers toestaat een specifieke toepassing te gebruiken, zoals een app-berichtenservice of samenwerkingsplatform, moet het bedrijf bedrijfsgegevens archiveren en toezicht houden op de activiteiten en communicatie van deze medewerkers in die toepassing. Organisaties zijn verantwoordelijk voor het uitvoeren van due diligence om te voldoen aan de FINRA-regels en effectenwetgeving en voor het opvolgen van mogelijke schendingen van die regels met betrekking tot het gebruik van dergelijke apps door werknemers.
  
De volgende effectieve praktijken worden onder andere door FINRA aanbevolen:
* Een uitgebreid beheerprogramma opzetten voor digitale communicatiekanalen. De beslissingen van de organisatie beheren over welke digitale communicatiekanalen zijn toegestaan en complianceprocessen voor elk digitaal kanaal definiëren. Het snel veranderende landschap van digitale communicatiekanalen nauwlettend volgen en zorgen dat complianceprocessen up-to-date zijn.
* Toegestane digitale kanalen duidelijk definiëren en controleren. Zowel goedgekeurde als verboden digitale kanalen definiëren. Het gebruik van verboden digitale kanalen of verboden functies binnen digitale kanalen blokkeren of beperken, die de organisatie belemmeren om te voldoen aan archiefbeheer en toezichtvereisten.
* Training geven voor digitale communicatie. Verplichte trainingsprogramma's implementeren voordat u geregistreerde vertegenwoordigers toegang geeft tot goedgekeurde digitale kanalen. Met training kunt u de verwachtingen van een organisatie voor zakelijke en persoonlijke digitale communicatie verduidelijken en IT-medewerkers beter begeleiden bij het gebruik van toegestane functies van elk kanaal.

FINRA's conclusies en bevindingen voor digitale communicatie houden rechtstreeks verband met het vermogen van een organisatie om te voldoen aan [SEC-regel 17a-4](https://www.law.cornell.edu/cfr/text/17/240.17a-4) voor het bewaren van alle zakelijke communicatie, FINRA-regels [3110](https://www.finra.org/rules-guidance/rulebooks/finra-rules/3110) en [3120](https://www.finra.org/rules-guidance/rulebooks/finra-rules/3120) voor toezicht op en controle van communicatie en regelserie [4510](https://www.finra.org/rules-guidance/rulebooks/finra-rules/4510) voor het bijhouden van gegevens. De Commodity Futures Trading Commission (CFTC) kondigt gelijksoortige vereisten aan onder 17 CFR 131. Deze regelgeving wordt later in dit artikel uitgebreid besproken.

***Teams biedt, samen met de uitgebreide suite beveiligings- en compliancefuncties van Microsoft 365, een digitaal communicatiekanaal voor financiële dienstverleners voor een effectieve bedrijfsvoering en om te voldoen aan regelgeving.*** In de rest van dit artikel wordt beschreven hoe Microsoft 365 ingebouwde mogelijkheden voor recordbeheer, informatiebeveiliging, informatiebarrières en toezichtcontrole Teams een robuuste toolset biedt om te helpen aan deze wettelijke verplichtingen te voldoen.

## <a name="protect-modern-collaboration-with-microsoft-365"></a>Moderne samenwerking beveiligen met Microsoft 365

### <a name="secure-user-identities-and-control-access"></a>Gebruikersidentiteiten beveiligen en toegang beheren

***Het beveiligen van de toegang tot klantgegevens, financiële documenten en toepassingen begint met het sterk beveiligen van gebruikersidentiteiten.*** Hiervoor hebt u een veilig platform voor de onderneming nodig om identiteiten op te slaan en te beheren, zodat u over een vertrouwde verificatiemethode beschikt en de toegang tot deze toepassingen dynamisch kunt beheren.

Tijdens het werk kunnen medewerkers steeds wisselen van toepassing, locatie en apparaat. De toegang tot gegevens moet bij elke stap worden geverifieerd. Het verificatieproces moet ondersteuning bieden voor een sterk protocol en meerdere verificatiefactoren (zoals eenmalige sms-toegangscode, verificatie-app en certificaat) om ervoor te zorgen dat de identiteit niet wordt aangetast. Het afdwingen van op risico gebaseerd toegangsbeleid is van cruciaal belang voor het beschermen van financiële gegevens en toepassingen tegen interne bedreigingen, onopzettelijke gegevenslekken en gegevensexfiltratie.

Microsoft 365 biedt een veilig identiteitsplatform in [Azure Active Directory (Azure AD)](/azure/active-directory/), waarin de id's centraal worden opgeslagen en veilig worden beheerd. Azure AD vormt samen met een groot aantal gerelateerde Microsoft 365-beveiligingsservices, de basis om werknemers de toegang te bieden die ze nodig hebben om veilig te werken en tegelijk de organisatie te beschermen tegen bedreigingen.

[Azure AD Multi-Factor Authentication (MFA)](/azure/active-directory/fundamentals/concept-fundamentals-mfa-get-started) is ingebouwd in het platform en biedt een extra verificatiemiddel voor het bevestigen van de gebruikersidentiteit bij het verkrijgen van toegang tot gevoelige financiële gegevens en toepassingen. Azure MFA vereist ten minste twee vormen van verificatie, zoals een wachtwoord plus een bekend mobiel apparaat. Er worden verschillende opties voor tweestapsverificatie ondersteund, waaronder:

- De Microsoft Authenticator-app
- Een eenmalige toegangscode via sms
- Een telefoontje waarbij een gebruiker een pincode moet invoeren

Als het wachtwoord wordt aangetast, heeft een potentiële hacker de telefoon van de gebruiker nog steeds nodig om toegang te krijgen tot organisatiegegevens. Bovendien gebruikt Microsoft 365 moderne verificatie als een belangrijk protocol, dat dezelfde sterke en rijke verificatie-ervaring van webbrowsers biedt voor de samenwerkingstools die werknemers dagelijks gebruiken, waaronder Microsoft Outlook en de andere Microsoft Office-toepassingen.

#### <a name="passwordless"></a>Zonder wachtwoord

Wachtwoorden zijn de zwakste schakel in een beveiligingsketen. Ze kunnen het storingspunt zijn als er geen aanvullende verificatie is. Microsoft ondersteunt een groot aantal verificatieopties om aan de behoeften van financiële instellingen tegemoet te komen.

MFA is handiger voor gebruikers via methoden *zonder wachtwoord*. Hoewel niet alle MFA zonder wachtwoord werkt, maken technologieën zonder wachtwoord gebruik van meervoudige verificatie. Microsoft, Google en andere toonaangevende bedrijven hebben standaarden ontwikkeld om een eenvoudigere, sterkere verificatie-ervaring mogelijk te maken op het web en mobiele apparaten in de groep Fast IDentity Online (FIDO). Met de onlangs ontwikkelde FIDO2-standaard kunnen gebruikers eenvoudig en veilig verifiëren zonder dat een wachtwoord nodig is om phishing te elimineren.

De volgende Microsoft MFA-methoden zonder wachtwoord zijn onder andere beschikbaar:
* [Microsoft Authenticator](/azure/active-directory/user-help/user-help-auth-app-overview): vanwege de flexibiliteit, het gebruiksgemak en lage kosten raden we u aan de mobiele Microsoft Authenticator-app te gebruiken. Microsoft Authenticator ondersteunt biometrie, pushmeldingen en een eenmalige wachtwoordcode voor elke app die is verbonden met Azure AD. De app is beschikbaar in de Apple App Store en Android App Store.
*  [Windows Hello](/windows/security/identity-protection/hello-for-business/hello-overview): voor een ingebouwde ervaring op de pc raden we u aan Windows Hello te gebruiken. Hierbij wordt gebruikgemaakt van biometrische informatie (zoals gezicht of vingerafdruk) waarmee u automatisch kunt aanmelden.  
* [FIDO2-beveiligingssleutels](/windows/security/identity-protection/hello-for-business/microsoft-compatible-security-key) zijn nu verkrijgbaar bij verschillende Microsoft-partners: Yubico, Feitian Technologies en HID Global in een USB-badge met NFC of biometrische sleutel.

[Voorwaardelijke toegang voor Azure AD](/azure/active-directory/conditional-access/) is een krachtige oplossing voor het automatiseren van beslissingen voor toegangsbeheer en het afdwingen van organisatiebeleid om bedrijfsmiddelen te beveiligen. Een klassiek voorbeeld is een financiële planner die toegang wil krijgen tot een toepassing met gevoelige klantgegevens. Hij of zij moet automatisch meervoudige verificatie uitvoeren om specifiek toegang te krijgen tot deze toepassing vanaf een apparaat dat door het bedrijf wordt beheerd. Met voorwaardelijke toegang voor Azure worden de signalen van de toegangsaanvraag van een gebruiker samengevoegd, zoals de eigenschappen van de gebruiker, het apparaat, de locatie en het netwerk en de toepassing waartoe de gebruiker toegang probeert te krijgen. Er worden dynamisch pogingen voor toegang tot de toepassing beoordeeld op basis van het geconfigureerde beleid. Bij een verhoogd risico voor gebruikers of apparaten of als er niet aan andere voorwaarden wordt voldaan, kan Azure AD automatisch beleidsregels afdwingen, zoals het vereisen van MFA en het veilig opnieuw instellen van het wachtwoord of het beperken of blokkeren van de toegang. Dit helpt ervoor te zorgen dat gevoelige bedrijfsmiddelen worden beschermd in dynamisch veranderende omgevingen.
 
Azure AD en de bijbehorende beveiligingsservices van Microsoft 365 vormen de basis waarop een modern samenwerkingsplatform in de cloud kan worden geïmplementeerd voor financiële instellingen, zodat de toegang tot gegevens en toepassingen kan worden beveiligd en de regelgeving kan worden nageleefd. Deze tools bieden de volgende belangrijke mogelijkheden:

* Centraal opslaan en veilig beheren van gebruikersidentiteiten.
* Gebruik van een krachtig verificatieprotocol, inclusief meervoudige verificatie, om gebruikers te verifiëren voor toegangsaanvragen en een consistente en krachtige verificatie-ervaring te bieden voor alle toepassingen.
* Dynamisch valideren van beleid voor alle toegangsaanvragen, waarbij meerdere signalen worden opgenomen in het besluitvormingsproces van het beleid, waaronder identiteit, lidmaatschap van gebruikers/groepen, toepassing, apparaat, netwerk, locatie en realtime risicoscore.
* Gedetailleerd beleid valideren op basis van gebruikersgedrag en bestandseigenschappen en dynamisch aanvullende beveiligingsmaatregelen afdwingen wanneer dat nodig is.
* 'Schaduw-IT' in de organisatie identificeren en InfoSec-teams toestaan om cloudtoepassingen te accepteren of te blokkeren.
* De toegang tot Microsoft- en niet-Microsoft-cloudtoepassingen bewaken en beheren.
* Proactief beschermen tegen phishing- en ransomwareaanvallen via e-mail.

#### <a name="azure-ad-identity-protection"></a>Azure AD Identity Protection
Hoewel voorwaardelijke toegang resources beschermt tegen verdachte aanvragen, gaat identiteitsbeveiliging veel verder door het inschakelen van continue risicodetectie en het aanpakken van verdachte gebruikersaccounts. Identity Protection houdt u continu op de hoogte van verdacht gebruikers- en aanmeldingsgedrag in uw omgeving. Via automatische antwoorden voorkomt u proactief misbruik van gecompromitteerde identiteiten.
 
Identity Protection is een tool waarmee organisaties drie belangrijke taken kunnen uitvoeren:

* Detectie en herstel van op identiteit gebaseerde risico's automatiseren.
* Risico's onderzoeken met behulp van gegevens in de portal.
* Risicodetectiegegevens exporteren naar externe hulpprogramma's voor verdere analyse.

Identity Protection gebruikt kennis die Microsoft heeft opgedaan vanuit haar positie in organisaties met Azure AD, in de consumentenruimte met Microsoft-accounts en in gaming met Xbox om uw gebruikers te beschermen. Microsoft analyseert 65 biljoen signalen per dag om klanten te identificeren en te beschermen tegen bedreigingen. De signalen die worden gegenereerd door en worden ingevoerd in Identity Protection, kunnen verder worden ingevoerd in tools zoals voorwaardelijke toegang om toegangsbeslissingen te nemen. Ze kunnen ook worden teruggekoppeld naar een SIEM-tool (Security Information and Event Management) voor verder onderzoek op basis van het door uw organisatie afgedwongen beleid.

Identity Protection helpt organisaties automatisch te beschermen tegen inbreuk op identiteiten door gebruik te maken van cloudintelligentie met geavanceerde detectie op basis van heuristische functies, gebruikers- en entiteitsgedragsanalyse (UEBA) en machine learning (ML) in het hele Microsoft-ecosysteem.

![Vijf IT-medewerkers kijken toe terwijl een collega een presentatie geeft](../media/win17-15021-00-n9.jpg)
 
## <a name="identify-sensitive-data-and-prevent-data-loss"></a>Gevoelige gegevens identificeren en verlies van gegevens voorkomen
Met Microsoft 365 kunnen alle organisaties gevoelige gegevens binnen de organisatie identificeren door een combinatie van krachtige mogelijkheden, waaronder:

* **Microsoft Information Protection (MIP)** voor classificatie op basis van gebruikers en automatische classificatie van gevoelige gegevens.
* **Office 365 DLP (preventie van gegevensverlies)** voor automatische identificatie van gevoelige gegevens met behulp van gevoelige gegevenstypen (met andere woorden, reguliere expressies) en trefwoorden en het afdwingen van beleid.

Met **[Microsoft Information Protection (MIP)](../compliance/information-protection.md)** kunnen organisaties documenten en e-mails intelligent classificeren met behulp van gevoeligheidslabels. Gevoeligheidslabels kunnen door gebruikers handmatig worden toegepast op documenten in Microsoft Office-toepassingen en e-mailberichten in Outlook. Met de labels kunnen automatisch documentmarkeringen, bescherming via versleuteling en het afdwingen van rechtenbeheer worden toegepast. U kunt ook automatisch gevoeligheidslabels toepassen door beleid in te stellen waarvoor trefwoorden en gevoelige gegevenstypen worden gebruikt, zoals creditcardnummers, burgerservicenummers en identiteitsnummers, om automatisch gevoelige gegevens te zoeken en te classificeren.

Daarnaast biedt Microsoft 'trainbare classificaties' die machine learning-modellen gebruiken om gevoelige gegevens te identificeren op basis van de inhoud, en niet alleen door te zoeken op patroonovereenkomsten of de elementen in de inhoud. Een classificatie leert hoe een inhoudstype moet worden geïdentificeerd door te kijken naar een groot aantal voorbeelden van de inhoud die moet worden geclassificeerd. U kunt een classificatie trainen door voorbeelden van de inhoud van een bepaalde categorie toe te voegen. Nadat het model van deze voorbeelden heeft geleerd, wordt het getest door een combinatie van overeenkomende en niet-overeenkomende voorbeelden in te voeren. De classificatie voorspelt of een bepaald voorbeeld al dan niet in de categorie. Een persoon bevestigt vervolgens de resultaten, waarbij de positieve waarden, negatieve waarden, fout-positieven en fout-negatieven worden gesorteerd om nauwkeurigere voorspellingen te krijgen. Wanneer de getrainde classificatie wordt gepubliceerd, wordt de inhoud van Microsoft SharePoint Online, Exchange Online en OneDrive voor Bedrijven verwerkt en wordt deze automatisch geclassificeerd.

Wanneer u gevoeligheidslabels toepast op documenten en e-mailberichten, worden metagegevens ingesloten waarmee de gekozen gevoeligheid binnen het object wordt geïdentificeerd. Vervolgens wordt de gevoeligheid met de gegevens meeverplaatst. Zelfs als een gelabeld document wordt opgeslagen op de desktop van een gebruiker of in een on-premises systeem, is het nog steeds beveiligd. Met deze functionaliteit kunnen andere Microsoft 365-oplossingen, zoals Microsoft Cloud App Security of edge-apparaten voor netwerken, gevoelige gegevens identificeren en automatisch beveiligingscontroles afdwingen. Gevoeligheidslabels hebben het extra voordeel dat medewerkers worden geïnformeerd over welke gegevens binnen een organisatie als gevoelig worden beschouwd en hoe ze met de gegevens moeten omgaan wanneer ze deze ontvangen.

**[Office 365 DLP (preventie van gegevensverlies)](../compliance/data-loss-prevention-policies.md?view=o365-worldwide)** identificeert automatisch documenten, e-mails en gesprekken die gevoelige gegevens bevatten door ze te scannen op gevoelige gegevens en vervolgens beleid af te dwingen voor deze objecten. Beleidsregels worden afgedwongen voor documenten in SharePoint en OneDrive voor Bedrijven. Ze worden ook afgedwongen wanneer gebruikers e-mail verzenden en bij chats en kanaalgesprekken in Teams. Het beleid kan worden geconfigureerd op het zoeken naar trefwoorden, gevoelige gegevenstypen, retentielabels en of gegevens binnen de organisatie of extern worden gedeeld. Met controles kunnen organisaties het DLP-beleid aanpassen om fout-positieven te beperken. Wanneer gevoelige gegevens worden gevonden, kunnen er in Microsoft 365-toepassingen aanpasbare beleidstips worden weergegeven voor gebruikers om hen te laten weten dat hun inhoud gevoelige gegevens bevat, waarna er herstelbewerkingen worden voorgesteld. Met beleid kunt u ook voorkomen dat gebruikers documenten openen of delen of e-mailberichten verzenden die bepaalde typen gevoelige gegevens bevatten. Microsoft 365 biedt ondersteuning voor meer dan 100 ingebouwde gevoelige gegevenstypen. Organisaties kunnen aangepaste gevoelige gegevenstypen configureren om te voldoen aan hun beleid.

Het implementeren van MIP-en DLP-beleid voor organisaties vergt een zorgvuldige planning en een trainingsprogramma voor gebruikers, zodat medewerkers inzicht hebben in het schema voor de gegevensclassificaties van de organisatie en weten welke typen gegevens als gevoelig worden beschouwd. Door werknemers tools en educatieve programma's te bieden waarmee ze gevoelige gegevens kunnen identificeren en begrijpen hoe ze ermee om moeten gaan, maken ze deel uit van de oplossing voor het beperken van informatiebeveiligingsrisico's.

De signalen die worden gegenereerd door en worden ingevoerd in Identity Protection, kunnen ook worden ingevoerd in tools zoals voorwaardelijke toegang om toegangsbeslissingen te nemen of in een tool voor beveiligingsinformatie en gebeurtenisbeheer (SIEM) voor onderzoek op basis van het door de organisatie afgedwongen beleid.

Identity Protection helpt organisaties automatisch te beschermen tegen inbreuk op identiteiten door gebruik te maken van cloudintelligentie met geavanceerde detectie op basis van heuristische functies, gebruikers- en entiteitsgedragsanalyse en machine learning in het hele Microsoft-ecosysteem.

![Een IT-medewerker staat afgebeeld voor een groot aantal monitoren](../media/clo1718-portrait-006.jpg)

## <a name="defend-the-fortress"></a>Het bedrijf beschermen

Microsoft heeft onlangs de Microsoft 365 Defender-oplossing gelanceerd, die is ontworpen om de moderne organisatie te beschermen tegen het zich steeds verder ontwikkelende bedreigingslandschap. Door gebruik te maken van Intelligent Security Graph, biedt de Threat Protection-oplossing uitgebreide, geïntegreerde beveiliging tegen meerdere aanvalsvectoren.

### <a name="the-intelligent-security-graph"></a>[Intelligent Security Graph](https://www.microsoft.com/security/business/intelligence) 
Beveiligingsservices van Microsoft 365 worden mogelijk gemaakt door Intelligent Security Graph. Om cyberbedreigingen te bestrijden, gebruikt Intelligent Security Graph geavanceerde analyses om bedreigingsinformatie en beveiligingssignalen van Microsoft en haar partners te koppelen. Microsoft biedt wereldwijd op grote schaal services aan en verzamelt biljoenen beveiligingssignalen voor alle beschermingslagen. Machine learning-modellen beoordelen deze informatie en de signaal- en dreigingsinzichten worden doorgestuurd naar al onze producten en services. Hierdoor kunnen we snel bedreigingen detecteren en hierop reageren en bruikbare waarschuwingen en informatie naar klanten sturen voor herstelacties. Onze machine learning-modellen worden continu getraind en bijgewerkt met nieuwe inzichten, waardoor we veiligere producten kunnen maken en proactievere beveiliging kunnen bieden.

[Microsoft Defender voor Office 365](../security/office-365-security/defender-for-office-365.md?view=o365-worldwide) biedt een geïntegreerde Microsoft 365-service waarmee organisaties worden beschermd tegen schadelijke koppelingen en malware die binnenkomen via e-mail en Office-documenten. Een van de meest voorkomende aanvalsvectoren die momenteel van invloed zijn op gebruikers, is een phishingaanval via e-mail. Deze aanvallen kunnen worden gericht op specifieke gebruikers en kunnen zeer overtuigend zijn, met een oproep tot actie waarin de gebruiker wordt gevraagd om op een schadelijke koppeling te klikken of een bijlage met malware te openen. Wanneer een computer is geïnfecteerd, kan de kwaadwillende gebruiker de referenties van de gebruiker stelen en ze vervolgens lateraal in de organisatie verplaatsen of kan e-mails en gegevens exfiltreren om te zoeken naar gevoelige informatie. Defender voor Office 365 biedt ondersteuning voor veilige bijlagen en koppelingen door documenten en koppelingen bij het klikken te evalueren op mogelijke schadelijke bedoelingen en de toegang te blokkeren. E-mailbijlagen worden geopend in een beveiligde sandbox voordat ze worden bezorgd in het postvak van een gebruiker. Ook worden koppelingen in Office-documenten geëvalueerd op schadelijke URL's. Defender voor Office 365 biedt bovendien bescherming voor koppelingen en bestanden in SharePoint Online, OneDrive voor Bedrijven en Teams. Als er een schadelijk bestand wordt gevonden, wordt dit automatisch door Defender voor Office 365 vergrendeld om mogelijke schade te beperken.

[Microsoft Defender voor Eindpunt](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) is een compleet eindpuntbeveiligingsplatform voor preventieve bescherming, detectie van inbreuken, geautomatiseerde onderzoeken en herstelmaatregelen. Defender voor Eindpunt biedt ingebouwde functionaliteit voor ontdekking en bescherming van gevoelige gegevens voor zakelijke eindpunten.

Met [Microsoft Cloud App Security (MCAS)](/cloud-app-security/what-is-cloud-app-security) kunnen organisaties beleid op gedetailleerd niveau afdwingen en gedragsproblemen vaststellen op basis van afzonderlijke gebruikersprofielen die automatisch zijn gedefinieerd via machine learning. MCAS-beleid kan voortborduren op Azure-beleid voor voorwaardelijke toegang om gevoelige bedrijfsmiddelen te beschermen door aanvullende signalen te evalueren op gebruikersgedrag en eigenschappen van de documenten waartoe toegang wordt verkregen. Na verloop van tijd leert MCAS wat typisch gedrag is voor elke medewerker met betrekking tot de gegevens waartoe ze toegang hebben en de toepassingen die ze gebruiken. Op basis van aangeleerde gedragspatronen kan beleid vervolgens automatisch beveiligingscontroles afdwingen als een medewerker niet volgens dit gedragsprofiel handelt. Als een medewerker bijvoorbeeld van maandag tot en met vrijdag van 9.00 tot 17.00 uur toegang heeft tot een boekhoudtoepassing, maar plotseling deze toepassing vaak opent op een zondagavond, kan MCAS dynamisch beleid afdwingen waarmee de gebruiker zich opnieuw moet verifiëren. Hierdoor wordt ervoor gezorgd dat de inloggegevens van de gebruiker niet worden aangetast. MCAS helpt ook bij de identificatie van 'schaduw-IT' in de organisatie. Hierdoor kunnen informatiebeveiligingsteams controleren of medewerkers goedgekeurde tools gebruiken wanneer ze werken met gevoelige gegevens. Ten slotte kan MCAS gevoelige gegevens overal in de cloud beschermen, zelfs buiten het Microsoft 365-platform. Hiermee kunnen organisaties specifieke externe cloud-apps goedkeuren (of weigeren) en de toegang en het gebruik beheren.
 
[Microsoft Defender for Identity](/azure-advanced-threat-protection/what-is-atp) is een cloudbeveiligingsoplossing die gebruikmaakt van uw on-premises Active Directory-signalen om geavanceerde bedreigingen, gecompromitteerde identiteiten en kwaadwillende acties van binnenuit die zijn gericht op uw organisatie, te identificeren, te detecteren en te onderzoeken. Met AATP kunnen SecOp-analisten en beveiligingsprofessionals geavanceerde aanvallen in hybride omgevingen detecteren voor het volgende:
* Gebruikers, entiteitsgedrag en activiteiten bewaken met analyses op basis van machine learning.
* Gebruikersidentiteiten en -referenties beveiligen die zijn opgeslagen in Active Directory.
* Verdachte gebruikersactiviteiten en geavanceerde aanvallen in de hele kill chain identificeren en onderzoeken.
* Heldere incidentinformatie verstrekken op een eenvoudige tijdlijn voor snelle sortering.

![De kantoormedewerkers komen samen in een kleine vergaderruimte. Een ervan geeft een presentatie.](../media/clo1717-corporate-office-021.jpg)
 
## <a name="govern-data-and-manage-records"></a>Gegevens en records beheren

Financiële instellingen moeten hun records en informatie bewaren overeenkomstig hun wettelijke, juridische en zakelijke verplichtingen zoals aangegeven in hun zakelijke bewaarschema. De [SEC schrijft bijvoorbeeld een bewaartermijn](https://www.sec.gov/rules/interp/34-47806.htm) van drie tot zes jaar voor, gebaseerd op recordtype, met onmiddellijke toegankelijkheid voor de eerste twee jaar. Organisaties lopen risico's op het gebied van naleving van wet- en regelgeving als gegevens niet lang genoeg worden bewaard (te vroeg worden verwijderd) en beheren nu ook regelgeving voor het verwijderen van informatie die niet meer is vereist. Effectieve strategieën voor recordbeheer zijn vooral gericht op een praktische en consistente aanpak, zodat informatie op de juiste manier wordt verwijderd en de kosten en risico's voor de organisatie tot een minimum worden beperkt.
 
Bovendien stellen mandaten van de regelgeving van het New York State Department of Financial Services dat betrokken entiteiten beleidsregels en procedures moeten handhaven voor het verwijderen van niet-openbare informatie. Volgens 23 NYCRR 500, Sectie 500.13, Beperkingen op het bewaren van gegevens moet "Als onderdeel van het cyberveiligheidsprogramma, elke betrokken entiteit beleid en procedures hebben voor de veilige verwijdering op periodieke basis van alle niet-openbare informatie die is aangegeven in sectie 500.01(g)(2)-(3) van dit deel, die niet meer nodig is voor bedrijfsactiviteiten of voor andere wettelijke zakelijke doeleinden van de betrokken entiteit, behalve wanneer dergelijke informatie anderszins wettelijk verplicht moet worden bewaard."
 
Financiële instellingen beheren grote hoeveelheden gegevens. En sommige bewaarperioden worden geactiveerd door gebeurtenissen, zoals het verlopen van een contract of een medewerker die de organisatie verlaat. In deze gevallen kan het lastig zijn om een bewaarbeleid voor records toe te passen. Methoden voor het nauwkeurig toewijzen van bewaarperioden voor alle organisatiedocumenten kunnen variëren. Sommigen passen het bewaarbeleid breed toe of maken gebruik van automatische classificatie en machine learning-technieken. Anderen gebruiken een methode waarvoor een gedetailleerder proces nodig is en waarbij een unieke bewaartermijn wordt toegekend aan afzonderlijke documenten.

***Microsoft 365 biedt flexibele functionaliteit voor het definiëren van retentielabels en bewaarbeleid om de vereisten voor recordbeheer intelligent te implementeren.*** Een recordmanager definieert een retentielabel, dat een 'recordtype' aanduidt in een traditioneel bewaarschema. Het retentielabel bevat instellingen waarmee deze details worden gedefinieerd:

- Hoelang een record wordt bewaard
- Wat er gebeurt wanneer de bewaarperiode is verlopen (het document verwijderen, een verwijderingsbeoordeling starten of geen actie ondernemen)
-  Waardoor de bewaarperiode wordt geactiveerd (aanmaakdatum, datum laatst gewijzigd, datum gelabeld of een gebeurtenis) en het document of de e-mail als record wordt gemarkeerd (wat betekent dat het niet kan worden bewerkt of verwijderd)

De retentielabels worden vervolgens gepubliceerd naar SharePoint- en OneDrive-sites, Exchange-postvakken en Microsoft 365-groepen. Gebruikers kunnen de retentielabels handmatig toepassen op documenten en e-mails. Recordbeheerders kunnen intelligentie gebruiken om de labels automatisch toe te passen. Intelligente functionaliteit kan worden gebaseerd op [meer dan 90 ingebouwde typen gevoelige informatie](../compliance/content-search.md?view=o365-worldwide) (zoals het ABA Outing-nummer, het Amerikaanse bankrekeningnummer of Amerikaanse burgerservicenummer). Deze functionaliteit kan ook worden aangepast op basis van trefwoorden of gevoelige gegevens in documenten of e-mailberichten, zoals creditcardnummers of andere persoonsgegevens die zijn gebaseerd op SharePoint-metagegevens. Voor gegevens die niet gemakkelijk kunnen worden geïdentificeerd door handmatige of geautomatiseerde patroonvergelijking, kunnen trainbare classificaties worden gebruikt om documenten intelligent te classificeren op basis van technieken voor machine learning.
 
De **Securities and Exchange Commission (SEC)** vereist dat brokerdealers en andere gereguleerde financiële instellingen alle zakelijke communicatie bewaren. Deze vereisten zijn van toepassing op veel typen communicatie en gegevens, waaronder e-mailberichten, documenten, chatberichten en faxberichten en meer. **SEC-regel 17a-4** definieert de criteria waaraan deze organisaties moeten voldoen om records op te slaan in een elektronisch gegevensopslagsysteem. In 2003 bracht de SEC een release uit waarin deze vereisten werden toegelicht. Deze bevat de volgende criteria:

* Gegevens die door een elektronisch opslagsysteem worden bewaard, moeten niet-herschrijfbaar en niet-uitwisbaar zijn. Dit wordt een WORM-vereiste genoemd (één keer schrijven, veel lezen).
* Het opslagsysteem moet gegevens langer kunnen opslaan dan de door de regel vereiste bewaartermijn, in geval van een dagvaarding of een ander gerechtelijk bevel.
* Een organisatie zou de vereiste in paragraaf (f) (2) (ii) (A) van de regel niet overtreden als ze een elektronisch opslagsysteem zou gebruiken dat het overschrijven, wissen of anderszins wijzigen van een record tijdens de vereiste bewaarperiode voorkomt door het gebruik van geïntegreerde hardware- en softwarecontrolecodes.
* Elektronische opslagsystemen die slechts het risico dat een record wordt overschreven of gewist, 'verkleinen', bijvoorbeeld door te vertrouwen op toegangscontrole, voldoen niet aan de vereisten van de regel.

Om financiële instellingen te helpen voldoen aan de vereisten van SEC-regel 17a-4, biedt Microsoft 365 een combinatie van mogelijkheden met betrekking tot het bewaren van gegevens, het configureren van beleid en het opslaan van gegevens binnen de service. Dit zijn onder andere:

* **Bewaring van gegevens (Regel 17a-4(a), (b)(4))** - retentielabels en bewaarbeleid zijn flexibel om te kunnen voldoen aan de behoeften van de organisatie en kunnen automatisch of handmatig worden toegepast op verschillende typen gegevens, documenten en informatie. Er wordt een groot aantal gegevenstypen en communicaties ondersteund, waaronder documenten in SharePoint en OneDrive voor Bedrijven, gegevens in Exchange Online-postvakken en gegevens in Teams.  
* **Niet-herschrijfbare, niet-wisbare indeling (Regel 17a-4 (f) (2) (II))** - met de functie Behoudvergrendeling voor bewaarbeleidsregels kunnen recordmanagers en -beheerders het bewaarbeleid zo configureren dat het beperkend is, zodat het niet meer kan worden gewijzigd. Hierdoor kan niemand het bewaarbeleid op welke manier dan ook verwijderen, uitschakelen of wijzigen. Dit betekent dat zodra Behoudvergrendeling is ingeschakeld, deze functie niet kan worden uitgeschakeld en dat er geen methode is waarmee gegevens waarop het bewaarbeleid is toegepast, kunnen worden overschreven, gewijzigd of verwijderd tijdens de bewaarperiode. Bovendien kan de bewaarperiode niet worden ingekort. De bewaarperiode kan echter wel worden verlengd wanneer er sprake is van wettelijke vereisten om de gegevens te blijven bewaren.<br/><br/>Wanneer een Behoudvergrendeling wordt toegepast op een bewaarbeleid, zijn de volgende acties beperkt:

  - De bewaarperiode van het beleid kan alleen worden verlengd. Deze kan niet worden ingekort.
  - Gebruikers kunnen worden toegevoegd aan het beleid, maar bestaande gebruikers die in het beleid zijn geconfigureerd, kunnen niet worden verwijderd.
   - Het bewaarbeleid kan niet worden verwijderd door een beheerder in de organisatie.
 
  Behoudvergrendeling zorgt ervoor dat geen enkele gebruiker, zelfs geen beheerders met de hoogste niveaus van bevoegde toegang, de instellingen kunnen wijzigen of de opgeslagen gegevens kunnen wijzigen, overschrijven of verwijderen, waardoor de archivering in Office 365 in overeenstemming wordt gebracht met de richtlijnen in de SEC 2003-release.

* **Kwaliteit, nauwkeurigheid en verificatie van opslag/serialisatie en indexering van gegevens (Regel 17a-4(f)(2) (ii)(B) en (C))** - Office 365-workloads bevatten elk functies voor het automatisch verifiëren van de kwaliteit en nauwkeurigheid van het proces voor het vastleggen van gegevens op opslagmedia. Bovendien worden gegevens opgeslagen met metagegevens en tijdstempels om te zorgen voor voldoende indexering, zodat gegevens effectief kunnen worden opgezocht en opgehaald.
 
* **Afzonderlijke opslag voor dubbele kopieën (Regel 17a-4(f)(3(III))** - in de Office 365-cloudservice worden dubbele kopieën van gegevens opgeslagen als een kernaspect van de hoge beschikbaarheid. Dit wordt bereikt door redundantie te implementeren op alle niveaus van de service, inclusief het fysieke niveau op alle servers, op serverniveau in het datacenter en op serviceniveau voor geografisch verspreide datacenters.

* **Downloadbare en toegankelijke gegevens (Regel 17a-4(f)(2)(ii)(D))** - Office 365 staat over het algemeen toe dat gegevens die zijn gelabeld voor bewaring, worden gezocht, geopend en gedownload. Bovendien kan er worden gezocht naar gegevens in Exchange Online-archieven met behulp van ingebouwde eDiscovery-functies. De gegevens kunnen vervolgens zo nodig worden gedownload in standaardindelingen, waaronder EDRML en PST.
 
* **Auditvereisten (Regel 17a-4(f)(3)(v))** - Office 365 biedt auditregistratie voor elke beheerders- en gebruikersactie waarbij gegevensobjecten worden gewijzigd, bewaarbeleid wordt geconfigureerd of gewijzigd, eDiscovery-zoekopdrachten worden uitgevoerd of toegangsrechten worden gewijzigd. Office 365 houdt een uitgebreid audittraject bij, inclusief gegevens over wie een actie heeft uitgevoerd, wanneer deze is uitgevoerd, details over de actie en de uitgevoerde opdrachten. Het auditlogboek kan vervolgens worden uitgevoerd en zo nodig worden opgenomen als onderdeel van officiële auditprocessen.

Ten slotte vereist Regel 17a-4 dat organisaties records bewaren voor veel typen transacties, zodat ze onmiddellijk toegankelijk zijn gedurende twee jaar. Records moeten daarna drie tot zes jaar worden bewaard zonder onmiddellijke toegang. Dubbele records moeten ook gedurende deze periode worden bewaard op een externe locatie. Met Office 365-functies voor recordbeheer kunnen records zo worden bewaard dat ze niet kunnen worden gewijzigd of verwijderd, maar wel gemakkelijk toegankelijk zijn voor een periode die wordt bepaald door de recordmanager. Deze perioden kunnen dagen, maanden of jaren beslaan, afhankelijk van de verplichtingen op het gebied van naleving van de regelgeving voor de organisatie.
 
Op verzoek zal Microsoft, indien vereist door een organisatie, een attestverklaring van compliance overleggen die voldoet aan SEC 17a-4.

Bovendien helpen deze mogelijkheden Microsoft 365 ook om te voldoen aan de opslagvereisten voor [CFTC-regel 1.31(c)-(d)](https://www.cftc.gov/sites/default/files/opa/press99/opa4266-99-attch.htm) van de **U.S. Commodity Futures Trading Commission** en [FINRA-regel serie 4510](https://www.finra.org/rules-guidance/rulebooks/finra-rules/4511) van de **Financial Industry Regulatory Authority**. Gezamenlijk vormen deze regels wereldwijd de meest prescriptieve richtlijn voor financiële instellingen om records te bewaren.

Meer informatie over de manier waarop Microsoft 365 voldoet aan de vereisten voor SEC-regel 17a-4 en andere regelgeving zijn beschikbaar bij [Assessment of Office 365 Exchange Online SEC 17a-4(f)/CFTC 1.31(c)-(d) door Cohasset Associates](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers).

## <a name="establish-ethical-walls-with-information-barriers"></a>Ethische normen met informatiebarrières vaststellen

Financiële instellingen kunnen worden onderworpen aan regels die voorkomen dat medewerkers in bepaalde functies informatie uitwisselen of samenwerken met andere functies. FINRA heeft bijvoorbeeld de regels 2241(b)(2)(G), 2242(b)(2) (D), (b)(2)(H)(ii) en (b)(2)(H)(iii) gepubliceerd waarvoor leden het volgende moeten:

"(G) informatieblokkades of andere institutionele waarborgen op te zetten die redelijkerwijs zijn ontworpen om ervoor te zorgen dat onderzoeksanalisten worden geïsoleerd van de toetsing, druk of het toezicht door personen die zich bezighouden met activiteiten op het gebied van investeringsbankservices of andere personen, met inbegrip van verkoop- en handelspersoneel, die vooringenomen kunnen zijn in hun oordeel of toezicht;" en "(H) informatieblokkades of andere institutionele waarborgen vaststellen die redelijkerwijs zijn ontworpen om ervoor te zorgen dat analisten voor schuldonderzoek worden geïsoleerd van de toetsing, druk of het toezicht door personen die zich bezighouden met: (i) investeringsbankdiensten; (ii) belangrijke handel of verkoop en handelsactiviteiten, en (iii) andere personen die vooringenomen kunnen zijn in hun oordeel of toezicht; "

Uiteindelijk vereisen deze regels dat organisaties beleid opstellen en informatiebarrières implementeren tussen functies die zijn betrokken bij bankservices, verkoop of handel door informatie uit te wisselen en te communiceren met analisten.

Met [Informatieblokkades ](../compliance/information-barriers.md?view=o365-worldwide) kunt u ethische muren creëren binnen uw Office 365-omgeving, waardoor compliancebeheerders of andere geautoriseerde beheerders beleidsregels kunnen definiëren die communicatie tussen groepen gebruikers in Teams toestaan of voorkomen. Met Informatieblokkades wordt gecontroleerd op specifieke acties om niet-geautoriseerde communicatie te voorkomen. Met Informatieblokkades kan ook de communicatie worden beperkt in scenario's waarin interne teams samenwerken aan fusies/overnames of vertrouwelijke deals of werken met gevoelige interne informatie die sterk moet worden beperkt.

Informatieblokkades in Microsoft 365 ondersteunt gesprekken en bestanden in Teams. Hiermee kunnen de volgende typen communicatieactiviteiten worden voorkomen om te voldoen aan de FINRA-regelgeving:

* Een gebruiker zoeken
* Een lid toevoegen aan een team of blijven deelnemen in een team met een ander lid
* Een chatsessie starten of voortzetten
* Een groepschat starten of voortzetten
* Iemand uitnodigen om deel te nemen aan een vergadering
* Een scherm delen
* Een gesprek starten

## <a name="implement-supervisory-control"></a>Toezichtscontrole implementeren

Financiële instellingen moeten doorgaans een toezichthoudende functie binnen hun organisatie tot stand brengen en onderhouden om de activiteiten van medewerkers te bewaken en compliance met toepasselijke effectenwetgeving te realiseren. FINRA heeft met name de volgende toezichtsvereisten ingesteld:
 
* [FINRA-regel 3110 (toezicht)](https://www.finra.org/rules-guidance/rulebooks/finra-rules/3110) vereist dat bedrijven over schriftelijke toezichtprocedures (WSP's) beschikken om toezicht te houden op de activiteiten van hun medewerkers en de typen bedrijven waarmee ze werken. Naast andere vereisten, moeten procedures het volgende omvatten:
   - Toezicht op het toezichtspersoneel
   - Beoordeling van investeringsbankieren, effectenactiviteiten, interne communicatie en interne onderzoeken van een bedrijf
   - Beoordeling van transacties voor handel met voorkennis
   - Beoordeling van correspondentie en klachten

   Procedures moeten de personen beschrijven die verantwoordelijk zijn voor beoordelingen, samen met de toezichtactiviteiten die elke persoon uitvoert, de beoordelingsfrequentie en de typen documentatie of communicatie die worden beoordeeld.
 
* [FINRA-regel 3120 (controlesysteem voor toezicht)](https://www.finra.org/rules-guidance/rulebooks/finra-rules/3120) vereist dat bedrijven beschikken over een systeem van controlebeleid en procedures voor toezicht (SCP's) waarmee hun schriftelijke toezichtprocedures worden gevalideerd, zoals gedefinieerd door Regel 3110. Bedrijven moeten niet alleen WSP's hebben, maar ook beleidsregels waarmee deze procedures jaarlijks worden getest om te valideren dat de toepasselijke effectenwetgeving en -regelgeving worden nageleefd. Op risico gebaseerde methoden en steekproeven kunnen worden gebruikt om de omvang van de tests te definiëren. Deze regel vereist onder andere dat bedrijven een jaarverslag verstrekken aan hoger management met een overzicht van de testresultaten en belangrijke uitzonderingen of gewijzigde procedures als gevolg van de testresultaten.

![Een kantoormedewerker bekijkt een grafiek en tabellen op een scherm, terwijl anderen op de achtergrond vergaderen.](../media/wco18-desk-work-002.jpg)
 
### <a name="communication-compliance"></a>Communicatiecompliance

Met Communicatiecompliance in Microsoft 365 kunnen organisaties vooraf beleidsregels configureren om de communicatie van medewerkers vast te leggen voor bewaking en beoordeling door geautoriseerde supervisors. Beleid inzake communicatiecompliance kan interne/externe e-mail en bijlagen, communicatie via Teams-chat -kanalen en chatcommunicatie en bijlagen via Skype voor Bedrijven Online omvatten. Daarnaast kan communicatiecompliance betrekking hebben op communicatie en gegevens van externe services (zoals Bloomberg, Thomson Reuters, LinkedIn, Twitter, Facebook, Box en Dropbox).
Door de uitgebreide aard van de communicatie die binnen een organisatie kan worden vastgelegd en beoordeeld, en de uitgebreide voorwaarden waarmee beleid kan worden geconfigureerd, kan communicatiebeleid financiële instellingen helpen bij het voldoen aan FINRA-regel 3110. Beleid kan worden geconfigureerd om communicatie voor personen of groepen te beoordelen.  Aangewezen supervisors kunnen worden toegewezen op een afzonderlijk of een groepsniveau. Er kunnen uitgebreide voorwaarden worden geconfigureerd om communicatie vast te leggen op basis van inkomende of uitgaande berichten, domeinen, retentielabels, trefwoorden of zinnen, trefwoordwoordenboeken, gevoelige gegevenstypen, bijlagen, berichtgrootte of bijlagegrootte. Reviewers krijgen een dashboard waarin ze gemarkeerde communicatie kunnen beoordelen, kunnen reageren op communicatie die mogelijk het beleid schendt en gemarkeerde items als opgelost kunnen markeren. Ze kunnen ook de resultaten bekijken van beoordelingen en items die eerder zijn afgesloten.
  
Communicatiecompliance biedt rapporten waarmee activiteiten voor beleidsbeoordeling kunnen worden gecontroleerd op basis van het beleid en de beoordelaar. Rapporten zijn beschikbaar om te controleren of het beleid werkt zoals is gedefinieerd door het schriftelijke toezichtbeleid van de organisatie. Ze kunnen ook worden gebruikt om de communicatie te identificeren die moet worden beoordeeld en de communicatie die niet compatibel is met het bedrijfsbeleid. Ten slotte worden alle activiteiten met betrekking tot het configureren van beleid en het beoordelen van communicatie gecontroleerd in het geïntegreerde Office 365 auditlogboek. Hierdoor helpt Communicatiecompliance in Microsoft 365 financiële instellingen ook om te voldoen aan FINRA-regel 3120.

Naast het naleven van de FINRA-regels, kunnen organisaties met Communicatiecompliance communicatie controleren op compliance van andere wettelijke vereisten, bedrijfsbeleid en ethische standaarden. Communicatiecompliance biedt ingebouwde classificaties voor bedreiging, intimidatie en scheldwoorden die helpen bij het beperken van fout-positieven tijdens de beoordeling van communicatie, waardoor beoordelaars tijd besparen tijdens het onderzoeks- en herstelproces. Daarnaast kunnen organisaties hiermee risico's verminderen door communicatie te bewaken wanneer ze gevoelige veranderingen ondergaan, zoals fusies en overnames of veranderingen in het leiderschap.

![Een IT-medewerker kijkt aandachtig naar een scherm.](../media/msc16-slalom-004.jpg)
 
## <a name="protect-against-data-exfiltration-and-insider-risk"></a>Beschermen tegen data-exfiltratie en interne risico's

Een veelvoorkomende bedreiging voor ondernemingen is de exfiltratie van gegevens of het extraheren van gegevens van een organisatie. Dit risico kan een grote zorg zijn voor financiële instellingen vanwege de gevoelige aard van de informatie die dagelijks toegankelijk is. Met het toenemende aantal beschikbare communicatiekanalen en de wildgroei van tools voor het verplaatsen van gegevens, zijn doorgaans geavanceerde mogelijkheden nodig om de risico's van gegevenslekken, beleidsschendingen en interne risico's te beperken.

### <a name="insider-risk-management"></a>Intern risicobeheer

Als medewerkers beschikken over online samenwerkingstools die overal toegankelijk zijn, brengt dit risico's met zich mee voor de organisatie. Medewerkers kunnen gegevens per ongeluk of opzettelijk lekken naar aanvallers of concurrenten.  Ze kunnen ook gegevens exfiltreren voor persoonlijk gebruik of gegevens meenemen naar een toekomstige werkgever. Deze scenario's vormen ernstige risico's voor financiële instellingen wat betreft beveiliging en compliance. Het identificeren van deze risico's wanneer ze zich voordoen en het snel beperken hiervan, vereist zowel intelligente tools voor gegevensverzameling als samenwerking tussen verschillende afdelingen, zoals juridisch, human resources en gegevensbeveiliging.

Microsoft 365 heeft onlangs een oplossing voor intern risicobeheer gelanceerd die signalen correleert tussen Microsoft 365-services en gebruikmaakt van machine learning-modellen om gebruikersgedrag te analyseren op verborgen patronen en tekenen van interne risico's. Met deze tool kunnen beveiligingsmedewerkers, interne onderzoekers en HR samenwerken, zodat ze gemakkelijk zaken kunnen oplossen op basis van vooraf vastgestelde werkstromen.  

Met intern risicobeheer in Microsoft 365 kunnen bijvoorbeeld signalen van de Windows 10-desktop van een gebruiker, zoals het kopiëren van bestanden naar een USB-station of het sturen van een e-mail naar een persoonlijk e-mailaccount, worden gecorreleerd met activiteiten van onlineservices, zoals Office 365-e-mail, SharePoint Online, Microsoft Teams of OneDrive voor Bedrijven om patronen voor gegevensexfiltratie te identificeren. Deze activiteiten kunnen ook worden gecorreleerd met medewerkers die een organisatie verlaten, wat een veelvoorkomend gegevensexfiltratiepatroon is. Er kunnen meerdere activiteiten en gedragspatronen in de loop van de tijd worden bewaakt. Wanneer veelvoorkomende patronen zichtbaar worden, kunnen er waarschuwingen worden gegenereerd, waardoor onderzoekers zich beter kunnen richten op belangrijke activiteiten om een beleidsschending met een hoge mate van vertrouwelijkheid te verifiëren. Met intern risicobeheer kunnen gegevens van onderzoekers pseudo-anoniem worden gemaakt, zodat aan de regelgeving voor gegevensprivacy kan worden voldaan, terwijl ze toch belangrijke activiteiten kunnen ontdekken waarmee ze een onderzoek efficiënt kunnen uitvoeren. Hiermee kunnen onderzoekers de gegevens van belangrijke activiteiten inpakken en veilig verzenden naar de afdeling HR en de juridische afdeling volgens de algemene escalatiewerkstromen voor het melden van zaken voor herstelactie.

Met intern risicobeheer in Microsoft 365 kunnen organisaties beter interne risico's bewaken en onderzoeken, terwijl organisaties nog steeds kunnen voldoen aan de regelgeving voor gegevensprivacy en de vastgelegde escalatiepaden kan volgen wanneer actie op een hoger niveau is vereist. Voor meer info over intern risicobeheer in Microsoft 365, zie [ Moderne risicopunten en werkstroom in intern risicobeheer in Microsoft 365](../compliance/insider-risk-management.md?view=o365-worldwide).

![Een medewerker in een callcenter op een werkplek typt en kijkt naar een scherm.](../media/clo17-call-center-006.jpg)
 
### <a name="tenant-restrictions"></a>Tenantbeperkingen
Organisaties die te maken hebben met gevoelige gegevens en beveiliging heel belangrijk vinden, willen meestal de online resources beheren waartoe gebruikers toegang hebben. Tegelijkertijd willen ze veilige samenwerking mogelijk maken via onlineservices zoals Office 365. Hierdoor valt het niet mee om de Office 365-omgevingen te beheren waartoe gebruikers toegang hebben, omdat niet-zakelijke Office 365-omgevingen kunnen worden gebruikt om kwaadwillig of onbedoeld gegevens van bedrijfsapparaten te exfiltreren. Normaal gesproken beperken organisaties de domeinen of IP-adressen waartoe gebruikers toegang hebben vanaf bedrijfsapparaten. Maar dit werkt niet in een cloudomgeving, waarin gebruikers legitiem toegang moeten hebben tot Office 365-services.

Microsoft 365 biedt tenant[beperkingen](/azure/active-directory/manage-apps/tenant-restrictions), waarmee dit probleem kan worden opgelost. U kunt tenantbeperkingen configureren om de toegang van medewerkers tot externe Office 365 Enterprise-tenants met frauduleuze identiteiten (identiteiten die geen deel uitmaken van uw zakelijke adresboek) te beperken. Tegenwoordig zijn tenantbeperkingen van toepassing op de hele tenant, waardoor toegang wordt verleend aan alleen de tenants die voorkomen op de lijst die u configureert. Microsoft blijft aan deze oplossing werken om de controle te verfijnen en de bescherming te verbeteren.

![AFBEELDING](../media/clo1717-corporate-office-001.jpg)
 
## <a name="conclusion"></a>Conclusie

Microsoft 365 en Teams bieden een geïntegreerde en allesomvattende oplossing voor financiële instellingen, die eenvoudige maar krachtige functionaliteit voor samenwerking en communicatie in de cloud mogelijk maakt binnen de onderneming. Door gebruik te maken van beveiligings- en compliance-technologieën van Microsoft 365, kunnen instellingen veiliger en volgens de regelgeving werken met robuuste beveiligingscontroles om gegevens, identiteiten, apparaten en toepassingen te beschermen tegen verschillende operationele risico's, waaronder cyberbeveiliging en interne risico's. Microsoft 365 biedt een fundamenteel veilig platform waarop financiële dienstverleners meer kunnen bereiken terwijl ze hun bedrijf, medewerkers en klanten beschermen.