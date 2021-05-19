---
title: Een DLP-beleid maken, testen en afstemmen
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.NewPolicyFromTemplate
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
ms.custom:
- seo-marvel-mar2020
ms.assetid: 59414438-99f5-488b-975c-5023f2254369
description: In dit artikel leert u hoe u een DLP-beleid kunt maken, testen en afstemmen op basis van uw organisatiebehoeften.
ms.openlocfilehash: e252c7328c59c246f739caf4b70acd44de010e42
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52532516"
---
# <a name="create-test-and-tune-a-dlp-policy"></a>Een DLP-beleid maken, testen en afstemmen

Preventie van gegevensverlies (DLP) helpt voorkomen dat gevoelige informatie onbedoeld of onbedoeld wordt gedeeld.

DLP onderzoekt e-mailberichten en bestanden op gevoelige informatie, zoals een creditcardnummer. Met DLP kunt u gevoelige informatie detecteren en actie ondernemen, zoals:

- De gebeurtenis voor controledoeleinden aanmelden
- Een waarschuwing weergeven voor de eindgebruiker die het e-mailbericht verstuurt of het bestand deelt
- Het delen van e-mail of bestanden actief blokkeren

## <a name="permissions"></a>Machtigingen

Leden van uw complianceteam die DLP-beleid gaan maken, hebben machtigingen nodig voor het Compliancecentrum. Standaard heeft uw tenantbeheerder toegang tot compliance officers en andere personen. Volg deze stappen:
  
1. Maak een groep in Microsoft 365 en voeg compliance officers toe aan deze groep.
    
2. Maak een rollengroep op de **pagina Machtigingen** van het Beveiligings &amp; compliancecentrum. 

3. Gebruik tijdens het maken van de rollengroep de sectie Rollen **kiezen** om de volgende rol toe te voegen aan de rollengroep: **DLP Compliance Management.**
    
4. Gebruik de **sectie Leden kiezen** om de groep Microsoft 365 die u eerder hebt gemaakt, toe te voegen aan de rollengroep.

Gebruik de **functie Alleen-weergeven DLP-compliancebeheer** om een rollengroep te maken met alleen-weergeven-bevoegdheden voor het DLP-beleid en DLP-rapporten.

Zie Gebruikers toegang geven tot het Office 365 [Compliance Center voor meer informatie.](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)
  
Deze machtigingen zijn vereist om een DLP-beleid te maken en toe te passen om beleid niet af te dwingen.

## <a name="how-sensitive-information-is-detected-by-dlp"></a>Hoe gevoelige informatie door DLP wordt gedetecteerd

Met DLP vindt u gevoelige informatie door regulier expressiepatroon (RegEx) te koppelen, in combinatie met andere indicatoren, zoals de nabijheid van bepaalde trefwoorden tot de overeenkomende patronen. Een VISA-creditcardnummer heeft bijvoorbeeld 16 cijfers. Maar deze cijfers kunnen op verschillende manieren worden geschreven, zoals 1111-1111-1111-1111-1111, 1111 1111 1111 1111 of 11111111111111111.

Een tekenreeks met 16 cijfers is niet per se een creditcardnummer, maar een ticketnummer van een helpdesksysteem of een serieel nummer van een stuk hardware. Als u het verschil wilt zien tussen een creditcardnummer en een onschadelijke tekenreeks met 16 cijfers, wordt een berekening uitgevoerd (checksum) om te bevestigen dat de getallen overeenkomen met een bekend patroon van de verschillende creditcardmerken.

Als DLP trefwoorden zoals 'VISA' of 'AMEX' vindt, bijna-datumwaarden die de vervaldatum van de creditcard kunnen zijn, gebruikt DLP deze gegevens ook om te bepalen of de tekenreeks een creditcardnummer is of niet.

Met andere woorden, DLP is slim genoeg om het verschil tussen deze twee tekenreeksen tekst in een e-mailbericht te herkennen:

- "Kunt u mij een nieuwe laptop bestellen. Gebruik mijn VISA-nummer 1111-1111-1111-1111, verval 11-22 en stuur mij de geschatte leverdatum wanneer u deze hebt.'
- "Mijn serienummer van de laptop is 2222-2222-2222-2222 en is gekocht op 11-2010. Is mijn reisvisum trouwens al goedgekeurd?'

Zie [Entiteitsdefinities van het type](sensitive-information-type-entity-definitions.md) Gevoelige informatie waarin wordt uitgelegd hoe elk informatietype wordt gedetecteerd.

## <a name="where-to-start-with-data-loss-prevention"></a>Waar moet ik beginnen met preventie van gegevensverlies

Wanneer de risico's van gegevenslekken niet helemaal duidelijk zijn, is het moeilijk om uit te zoeken waar u precies moet beginnen met het implementeren van DLP. Gelukkig kunnen DLP-beleidsregels worden uitgevoerd in de 'testmodus', zodat u de effectiviteit en nauwkeurigheid kunt meten voordat u ze inschakelen.

DLP-beleid voor Exchange Online kan worden beheerd via het Exchange beheercentrum. Maar u kunt DLP-beleid configureren voor alle werkbelastingen via het Beveiligings- & Compliancecentrum, dus dat is wat ik ga gebruiken voor demonstraties in dit artikel. In het Beveiligings- & Compliancecentrum vindt u het DLP-beleid onder **Beleid voor** preventie van  >  **gegevensverlies.** Kies **Een beleid maken om** te beginnen.

Microsoft 365 bevat een reeks [DLP-beleidsjablonen](what-the-dlp-policy-templates-include.md) die u kunt gebruiken om beleid te maken. Stel dat u een Australisch bedrijf bent. U kunt de sjablonen filteren op Australië en financiële, medische en gezondheids- en privacyinstellingen kiezen.

![Optie om land of regio te kiezen](../media/DLP-create-test-tune-choose-country.png)

Voor deze demonstratie kies ik Australische pii-gegevens (Persoonlijk identificeerbare gegevens), waaronder de informatietypen Australisch belastingbestandsnummer (TFN) en het nummer van het rijbewijs.

![Optie om een beleidssjabloon te kiezen](../media/DLP-create-test-tune-choose-policy-template.png)

Geef uw nieuwe DLP-beleid een naam. De standaardnaam komt overeen met de DLP-beleidssjabloon, maar u moet zelf een beschrijvende naam kiezen, omdat er meerdere beleidsregels kunnen worden gemaakt op basis van dezelfde sjabloon.

![Optie om uw beleid een naam te geven](../media/DLP-create-test-tune-name-policy.png)

Kies de locaties op wie het beleid van toepassing is. DLP-beleid kan van toepassing zijn op Exchange Online, SharePoint Online en OneDrive voor Bedrijven. Ik laat dit beleid zo geconfigureerd dat dit van toepassing is op alle locaties.

![Optie om alle locaties te kiezen](../media/DLP-create-test-tune-choose-locations.png)

Accepteer bij **de eerste Instellingen** de standaardwaarden voor nu. U kunt DLP-beleid aanpassen, maar de standaardinstellingen zijn een prima plek om te beginnen.

![Opties voor het aanpassen van het type inhoud dat moet worden beschermd](../media/DLP-create-test-tune-default-customization-settings.png)

Nadat u op Volgende,** hebt geklikt, krijgt u een extra pagina Instellingen beleid met meer aanpassingsopties.  Voor een beleid dat u net aan het testen bent, kunt u hier beginnen met het aanbrengen van enkele aanpassingen.

- Ik heb nu beleidstips uitgeschakeld, wat een redelijke stap is om te doen als u alleen dingen uit test en nog niets wilt weergeven voor gebruikers. Met beleidstips worden waarschuwingen weergegeven voor gebruikers die op het punt staan een DLP-beleid te schenden. Een gebruiker met Outlook ziet bijvoorbeeld een waarschuwing dat het bestand dat hij of zij heeft bijgevoegd creditcardnummers bevat en dat zijn of haar e-mail wordt geweigerd. Het doel van beleidstips is om het niet-conforme gedrag te stoppen voordat het gebeurt.
- Ik heb ook het aantal exemplaren verlaagd van 10 naar 1, zodat met dit beleid wordt gedetecteerd dat Australische PII-gegevens worden gedeeld, niet alleen bulksgewijs delen van de gegevens.
- Ik heb ook een andere geadresseerde toegevoegd aan de e-mail van het incidentrapport.

![Aanvullende beleidsinstellingen](../media/DLP-create-test-tune-more-policy-settings.png)

Ten slotte heb ik dit beleid geconfigureerd om in eerste instantie in de testmodus uit te voeren. Er is ook een optie om beleidstips uit te schakelen in de testmodus. Dit biedt u de flexibiliteit om beleidstips in te stellen in het beleid, maar vervolgens te beslissen of u ze wilt laten zien of onderdrukken tijdens uw testen.

![Optie om beleid eerst uit te testen](../media/DLP-create-test-tune-test-mode.png)

Klik in het laatste revisiescherm op **Maken om** het beleid te voltooien.

## <a name="test-a-dlp-policy"></a>Een DLP-beleid testen

Het nieuwe DLP-beleid wordt binnen ongeveer 1 uur van kracht. U kunt zitten en wachten totdat deze wordt geactiveerd door normale gebruikersactiviteit, of u kunt proberen deze zelf te activeren. Eerder heb ik gekoppeld aan [entiteitsdefinities](sensitive-information-type-entity-definitions.md)van het type Gevoelige informatie, die u informatie geven over het activeren van DLP-overeenkomsten.

In het DLP-beleid dat ik voor dit artikel heb gemaakt, worden bijvoorbeeld Australische belastingbestandsnummers (TFN) gedetecteerd. Volgens de documentatie is de overeenkomst gebaseerd op de volgende criteria.

![Documentatie over Het belastingbestandsnummer van Australië](../media/DLP-create-test-tune-Australia-Tax-File-Number-doc.png)
 
Als u de TFN-detectie op een nogal botte manier wilt demonstreren, wordt er zonder problemen een e-mailbericht met de woorden 'Belastingbestandsnummer' en een tekenreeks met negen cijfers in de nabijheid door de E-mail gestuurd. De reden dat het DLP-beleid niet wordt triggerd, is dat de tekenreeks met negen cijfers de checksum moet passeren die aangeeft dat het een geldige TFN is en niet alleen een onschadelijke reeks getallen.

![Australië belastingbestandsnummer dat checksum niet passeert](../media/DLP-create-test-tune-email-test1.png)

Ter vergelijking: een e-mailbericht met de woorden 'Belastingbestandsnummer' en een geldige TFN die de checksum passeert, zal het beleid activeren. Voor de record hier is de TFN die ik gebruik, afkomstig van een website die geldige, maar niet echte TFN's genereert. Dergelijke sites zijn erg handig omdat een van de meest voorkomende fouten bij het testen van een DLP-beleid een ongeldig nummer gebruikt dat niet geldig is en niet door de checksum komt (en daarom het beleid niet activeert).

![Australië belastingbestandsnummer dat de checksum passeert](../media/DLP-create-test-tune-email-test2.png)

Het e-mailbericht van het incidentrapport bevat het type gevoelige informatie dat is gedetecteerd, hoeveel exemplaren zijn gedetecteerd en het betrouwbaarheidsniveau van de detectie.

![Incidentrapport met het gedetecteerde belastingbestandsnummer](../media/DLP-create-test-tune-email-incident-report.png)

Als u uw DLP-beleid in de testmodus laat staan en de e-mailberichten van het incidentrapport analyseert, kunt u de nauwkeurigheid van het DLP-beleid en de effectiviteit ervan zien wanneer het wordt afgedwongen. Naast de incidentenrapporten kunt u de [DLP-rapporten](view-the-dlp-reports.md) gebruiken om een samengevoegde weergave te zien van beleidswedstrijden in uw tenant.

## <a name="tune-a-dlp-policy"></a>Een DLP-beleid afstemmen

Wanneer u uw beleid analyseert, wilt u mogelijk enkele wijzigingen aanbrengen in de manier waarop het beleid wordt gedragen. Als een eenvoudig voorbeeld kunt u vaststellen dat één TFN in e-mail geen probleem is (ik denk dat dit nog steeds het geval is, maar laten we ervoor zorgen dat het wordt gedemonstreerd), maar twee of meer exemplaren is een probleem. Meerdere exemplaren kunnen een riskant scenario zijn, zoals een werknemer die een CSV-export uit de HR-database naar een externe partij e-mailt, bijvoorbeeld een externe boekhoudservice. Zeker iets wat u liever wilt detecteren en blokkeren.

In het beveiligingscentrum & kunt u een bestaand beleid bewerken om het gedrag aan te passen.

![Optie voor het bewerken van beleid](../media/DLP-create-test-tune-edit-policy.png)
 
U kunt de locatie-instellingen zo aanpassen dat het beleid alleen wordt toegepast op specifieke werkbelastingen of op specifieke sites en accounts.

![Opties voor het kiezen van specifieke locaties](../media/DLP-create-test-tune-edit-locations.png)

U kunt ook de beleidsinstellingen aanpassen en de regels aanpassen aan uw behoeften.

![Optie voor het bewerken van regel](../media/DLP-create-test-tune-edit-rule.png)

Wanneer u een regel binnen een DLP-beleid bewerkt, kunt u het volgende wijzigen:

- De voorwaarden, waaronder het type en het aantal exemplaren van gevoelige gegevens die de regel activeren.
- De acties die worden ondernomen, zoals het beperken van de toegang tot de inhoud.
- Gebruikersmeldingen, die beleidstips zijn die worden weergegeven aan de gebruiker in hun e-mailclient of webbrowser.
- Gebruiker overschrijven bepaalt of gebruikers er toch voor kunnen kiezen om door te gaan met hun e-mail of het delen van bestanden.
- Incidentrapporten, om beheerders op de hoogte te stellen.

![Opties voor het bewerken van onderdelen van een regel](../media/DLP-create-test-tune-editing-options.png)

Voor deze demonstratie heb ik gebruikersmeldingen toegevoegd aan het beleid (wees voorzichtig om dit te doen zonder voldoende training voor gebruikersbekendheid) en heb ik gebruikers toegestaan het beleid te overschrijven met een zakelijke rechtvaardiging of door het als een onwaar positief te markeren. U kunt ook de tekst van de e-mail- en beleidstip aanpassen als u aanvullende informatie over het beleid van uw organisatie wilt opnemen of gebruikers kunt vragen contact op te nemen met de ondersteuning als ze vragen hebben.

![Opties voor gebruikersmeldingen en overschrijven](../media/DLP-create-test-tune-user-notifications.png)

Het beleid bevat twee regels voor het verwerken van hoog volume en laag volume, dus zorg ervoor dat u beide bewerkingen bewerkt met de acties die u wilt. Dit is een gelegenheid om zaken anders te behandelen, afhankelijk van hun kenmerken. U kunt bijvoorbeeld overschrijven toestaan voor schendingen van laag volume, maar geen overschrijvingen toestaan voor schendingen van hoog volume.

![Eén regel voor hoog volume en één regel voor laag volume](../media/DLP-create-test-tune-two-rules.png)

Als u de toegang tot inhoud die in strijd is met het beleid, daadwerkelijk wilt blokkeren of beperken, moet u een actie op de regel configureren om dit te doen.

![Optie om de toegang tot inhoud te beperken](../media/DLP-create-test-tune-restrict-access-action.png)

Na het opslaan van deze wijzigingen in de beleidsinstellingen, moet ik ook terugkeren naar de pagina met hoofdinstellingen voor het beleid en de optie inschakelen om beleidstips weer te geven aan gebruikers terwijl het beleid in de testmodus staat. Dit is een effectieve manier om DLP-beleid in te voeren voor uw eindgebruikers en gebruikers bewust te maken van de training, zonder dat u te veel onwaar positieven riskeert die van invloed zijn op hun productiviteit.

![Optie voor het tonen van beleidstips in de testmodus](../media/DLP-create-test-tune-show-policy-tips.png)

Aan de serverzijde (of in de cloud, indien u wilt), wordt de wijziging mogelijk niet onmiddellijk doorgevoerd vanwege verschillende verwerkingsintervallen. Als u een DLP-beleid wijzigt waarmee nieuwe beleidstips voor een gebruiker worden weergegeven, ziet de gebruiker de wijzigingen mogelijk niet onmiddellijk in de Outlook-client, die elke 24 uur op beleidswijzigingen controleert. Als u het testen wilt versnellen, kunt u deze registerfix gebruiken om het laatste downloadtijdstempel van de [PolicyNudges-toets te verwijderen.](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451) Outlook downloadt de meest recente beleidsgegevens wanneer u deze de volgende keer opnieuw start en begint met het opstellen van een e-mailbericht.

Als u beleidstips hebt ingeschakeld, ziet de gebruiker de tips in Outlook en kan deze fout-positieven aan u rapporteren wanneer ze optreden.

![Beleidstip met optie om onwaar positief te melden](../media/DLP-create-test-tune-policy-tip-in-outlook.png)

## <a name="investigate-false-positives"></a>Onwaar positieven onderzoeken

DLP-beleidsjablonen zijn niet direct perfect. Waarschijnlijk vindt u enkele onwaar positieven in uw omgeving. Daarom is het zo belangrijk om uw weg te vinden naar een DLP-implementatie, waarbij u de tijd neemt om uw beleid op de juiste manier te testen en af te stemmen.

Hier is een voorbeeld van een onwaar positief. Deze e-mail is vrij onschadelijk. De gebruiker geeft zijn mobiele telefoonnummer aan iemand op, inclusief zijn of haar e-mailhandtekening.

![E-mail met fout-positieve informatie](../media/DLP-create-test-tune-false-positive-email.png)
 
Maar de gebruiker ziet een beleidstip met de waarschuwing dat het e-mailbericht gevoelige informatie bevat, met name een Australisch rijbewijsnummer.

![Optie voor het rapporteren van onwaar positief in beleidstip](../media/DLP-create-test-tune-policy-tip-closeup.png)

De gebruiker kan de fout-positief melden en de beheerder kan nakijken waarom deze heeft plaatsgevonden. In de e-mail van het incidentrapport wordt de e-mail gemarkeerd als een onwaar positief.

![Incidentrapport met onwaar positief](../media/DLP-create-test-tune-false-positive-incident-report.png)

Dit rijbewijs is een goed voorbeeld om in te graven. De reden dat deze fout-positief is opgetreden, is dat het type 'Australische rijbewijs' wordt geactiveerd door een 9-cijferige tekenreeks (zelfs een tekenreeks die deel uitmaakt van een tekenreeks met 10 cijfers), binnen 300 tekens in de nabijheid van de trefwoorden 'sydney nsw' (niet hoofdtekengevoelig). Het wordt dus geactiveerd door het telefoonnummer en de e-mailhandtekening, alleen omdat de gebruiker zich toevallig in Sydney heeft.


Een van de opties is om het australische rijbewijsgegevenstype uit het beleid te verwijderen. Het is daar omdat het deel uitmaakt van de DLP-beleidssjabloon, maar we worden niet gedwongen deze te gebruiken. Als u alleen geïnteresseerd bent in Belastingbestandsnummers en niet in rijbewijzen, kunt u deze gewoon verwijderen. U kunt de regel bijvoorbeeld verwijderen uit de regel met een laag volume in het beleid, maar deze in de regel voor hoog volume laten staan, zodat lijsten met meerdere stuurprogramma's nog steeds worden gedetecteerd.
 
Een andere optie is het aantal exemplaren te verhogen, zodat een laag aantal rijbewijzen alleen wordt gedetecteerd wanneer er meerdere exemplaren zijn.

![Optie om het aantal exemplaren te bewerken](../media/DLP-create-test-tune-edit-instance-count.png)

Naast het wijzigen van het aantal exemplaren, kunt u ook de nauwkeurigheid van de overeenkomst (of betrouwbaarheidsniveau) aanpassen. Als uw gevoelige informatietype meerdere patronen heeft, kunt u de nauwkeurigheid van de overeenkomst in de regel aanpassen, zodat de regel alleen overeenkomt met specifieke patronen. Als u bijvoorbeeld wilt helpen bij het verminderen van fout-positieven, kunt u de nauwkeurigheid van de regel zo instellen dat deze alleen overeenkomt met het patroon met het hoogste betrouwbaarheidsniveau. Zie Vertrouwensniveau gebruiken om uw regels af te stemmen voor meer informatie over [betrouwbaarheidsniveaus.](data-loss-prevention-policies.md#match-accuracy)

Als u nog wat geavanceerder wilt worden, kunt u elk type gevoelige informatie aanpassen. U kunt bijvoorbeeld 'Sydney [](sensitive-information-type-entity-definitions.md#australia-drivers-license-number)NSW' verwijderen uit de lijst met trefwoorden voor het australische rijbewijsnummer, om de fout-positieve fout die hierboven is geactiveerd, te verwijderen. Zie Een [ingebouwd](customize-a-built-in-sensitive-information-type.md)type gevoelige informatie aanpassen voor meer informatie over hoe u dit doet met XML en PowerShell.

## <a name="turn-on-a-dlp-policy"></a>Een DLP-beleid in-

Als u blij bent dat uw DLP-beleid op een nauwkeurige en effectieve manier gevoelige informatietypen detecteert en dat uw eindgebruikers klaar zijn om te werken met het beleid dat van kracht is, kunt u het beleid inschakelen.

![Optie om beleid in te zetten](../media/DLP-create-test-tune-turn-on-policy.png)
 
Als u wilt zien wanneer het beleid van kracht wordt, Verbinding maken naar [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) en voer de [cmdlet Get-DlpCompliancePolicy uit](/powershell/module/exchange/get-dlpcompliancepolicy) om de Distributiestatus te zien.

![Cmdlet uitvoeren in PowerShell](../media/DLP-create-test-tune-PowerShell.png)

Nadat u het DLP-beleid hebt in gebruik genomen, moet u zelf enkele laatste tests uitvoeren om ervoor te zorgen dat de verwachte beleidsacties worden uitgevoerd. Als u dingen zoals creditcardgegevens probeert te testen, zijn er websites online met informatie over het genereren van voorbeeldtegoeden of andere persoonlijke gegevens die checksums doorgeven en uw beleid activeren.

Beleidsregels waarmee gebruikers worden overschrijven, presenteren deze optie aan de gebruiker als onderdeel van de beleidstip.

![Beleidstip waarmee gebruikers kunnen worden overschrijven](../media/DLP-create-test-tune-override-option.png)

Beleidsregels die inhoud beperken, geven de gebruiker een waarschuwing als onderdeel van de beleidstip en voorkomen dat ze de e-mail verzenden.

![Beleidstip dat inhoud is beperkt](../media/DLP-create-test-tune-restrict-warning.png)

## <a name="summary"></a>Samenvatting

Preventiebeleid voor gegevensverlies is handig voor organisaties van alle typen. Het testen van sommige DLP-beleidsregels is een oefening met een laag risico vanwege de controle die u hebt over zaken als beleidstips, overschrijven van eindgebruikers en incidentenrapporten. U kunt een aantal DLP-beleidsregels stilletjes testen om te zien welk type schendingen er al plaatsvinden in uw organisatie. Vervolgens kunt u beleid maken met lage onwaar positieve tarieven, uw gebruikers informeren over wat wel en niet is toegestaan en vervolgens uw DLP-beleid aan de organisatie uitrollen.