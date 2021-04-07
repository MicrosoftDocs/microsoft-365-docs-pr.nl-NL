---
title: Stapsgewijs beveiligingsstack voor bedreigingen in Microsoft Defender voor Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/05/2021
ms.reviewer: gigarrub
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
description: Volg het pad van een binnenkomend bericht door de filtertack voor bedreigingen in Microsoft Defender voor Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0760bd7a67f175e4af114324ccc729355ad5f593
ms.sourcegitcommit: 4e05f19c00e172b65f637f19ca461db5b21dff4e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/06/2021
ms.locfileid: "51601374"
---
# <a name="step-by-step-threat-protection-in-microsoft-defender-for-office-365"></a>Stapsgewijs bedreigingsbeveiliging in Microsoft Defender voor Office 365

De beveiligings- of filtertack van Microsoft Defender voor Office 365 kan worden onderverdeeld in vier fasen, zoals in dit artikel. In het algemeen gaat inkomende e-mail door al deze fasen vóór de bezorging, maar het werkelijke pad dat e-mail neemt, is afhankelijk van de Defender voor Office 365-configuratie van een organisatie.

> [!TIP]
> Blijf op de hoogte tot het einde van dit artikel voor een *geïntegreerde* afbeelding van alle 4 fasen van Defender voor Office 365-beveiliging!

## <a name="phase-1---edge-protection"></a>Fase 1 - Edge Protection

Helaas zijn Edge-blokken die ooit kritiek *waren,* nu relatief eenvoudig voor slechte spelers om te overwinnen. Na een tijd wordt hier minder verkeer geblokkeerd, maar blijft het een belangrijk onderdeel van de stapel.  

Edge-blokken zijn ontworpen om automatisch te zijn. In het geval van onwaar positief worden afzenders op de hoogte gesteld en wordt hen verteld hoe ze hun probleem kunnen oplossen. Connectors van vertrouwde partners met een beperkte reputatie kunnen ervoor zorgen dat ze beschikbaar zijn of tijdelijke overschrijven kunnen worden gebruikt bij het onboarden van nieuwe eindpunten.

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase1.png" alt-text="Fase 1 van filteren in Defender voor Office 365 is Edge Protection.":::

1. **Netwerkbeperking beschermt** Office 365-infrastructuur en klanten tegen DOS-aanvallen (Denial of Service) door het aantal berichten te beperken dat door een specifieke set infrastructuur kan worden verzonden.

2. **IP-reputatie en beperking blokkeren** berichten die worden verzonden van bekende slecht verbonden IP-adressen. Als met een specifiek IP-adres veel berichten in een korte periode worden verzonden, worden deze beperkt.

3. **Domeinreputatie** blokkeert alle berichten die worden verzonden vanuit een bekend slecht domein.

4. **Op adreslijst gebaseerde randfilterblokken** proberen de adreslijstgegevens van een organisatie te verzamelen via SMTP.

5. **Backscatterdetectie voorkomt** dat een organisatie wordt aangevallen via ongeldige niet-bezorgingsrapporten (NDR's).

6. **Verbeterde filtering voor verbindingslijnen** behoudt verificatiegegevens, zelfs wanneer het verkeer door een ander apparaat loopt voordat het Office 365 bereikt. Dit verbetert de nauwkeurigheid van het filteren van stapels, waaronder heuristische clustering, anti-spoofing en anti-phishing machine learning-modellen, zelfs in complexe of hybride routeringsscenario's.

## <a name="phase-2---sender-intelligence"></a>Fase 2 - Sender Intelligence

Functies in afzenderinformatie zijn essentieel voor het opsporen van spam, bulksgewijs, imitatie en ongeautoriseerde spoofberichten, en zijn ook belangrijk voor phish-detectie. De meeste van deze functies kunnen afzonderlijk worden geconfigureerd.

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase2.png" alt-text="Fase 2 van filteren in MDO is Sender intelligence.":::

1. **Triggers voor het opsporen** van accountcompromitteerden en waarschuwingen worden verhoogd wanneer een account afwijkende gedragingen heeft, in overeenstemming met compromissen. In sommige gevallen is het gebruikersaccount geblokkeerd en kan het geen e-mailberichten meer verzenden totdat het probleem is opgelost door het beveiligingsteam van een organisatie.

2. **E-mailverificatie** omvat geconfigureerde methoden van klanten en methoden die zijn ingesteld in de cloud, om ervoor te zorgen dat afzenders geautoriseerde, authentieke e-mailers zijn. Deze methoden zijn niet bestand tegen spoofing.
    - **SPF** kan e-mails weigeren op basis van DNS TXT-records waarin IP-adressen en servers worden vermeld die namens de organisatie e-mail mogen verzenden.
    - **DKIM biedt** een versleutelde handtekening die de afzender verifieert.
    - **Met DMARC** kunnen beheerders SPF en DKIM markeren zoals vereist in hun domein en wordt de uitlijning tussen de resultaten van deze twee technologieën afgedwongen.
    - **ARC** is niet geconfigureerd voor klanten, maar bouwt voort op DMARC om te werken met doorsturen in adressenlijsten, terwijl u een verificatieketen opneemt.

3. **Spoof intelligence** is geschikt voor het filteren van personen die mogen 'spoofen' (dat wil zeggen die e-mail verzenden namens een ander account, of doorsturen voor een adressenlijst) van kwaadaardige spoofers die een organisatie- of bekend extern domein imiteren. Het scheidt legitieme 'namens' e-mail van afzenders die spoofing gebruiken om spam- en phishingberichten te verzenden. 

    **Spoofintelligentie binnen de** organisatie detecteert en blokkeert spoofpogingen vanuit een domein binnen de organisatie.

4. **Spoofintelligentie met meerdere** domeinen detecteert en blokkeert spoofpogingen vanuit een domein buiten de organisatie.

5. **Met bulkfilters** kunnen beheerders een bulksgewijs betrouwbaarheidsniveau (BCL) configureren dat aangeeft of het bericht is verzonden van een bulksgewijs verzonden afzender. Beheerders kunnen de schuifregelaar Bulksgewijs in het antispambeleid gebruiken om te bepalen welk niveau van bulkmail moet worden behandeld als spam.

6. **Postvakinformatie** leert van standaardgedrag van e-mail van gebruikers. Het maakt gebruik van de communicatiegrafiek van een gebruiker om te detecteren wanneer een afzender alleen lijkt te zijn iemand met wie de gebruiker meestal communiceert, maar daadwerkelijk schadelijk is. Met deze methode wordt imitatie gedetecteerd.

7. **Nabootsing van** postvakkenintelligentie schakelt verbeterde imitatieresultaten in of uit op basis van de afzonderlijke afzenderkaart van elke gebruiker. Wanneer deze functie is ingeschakeld, kunt u nabootsing identificeren.

8. **Met gebruikersomitatie** kan een beheerder een lijst maken met doelen met een hoge waarde die waarschijnlijk worden nagebootst. Als een e-mailbericht binnenkomt waarbij de afzender alleen dezelfde naam en hetzelfde adres lijkt te hebben als het beveiligde account met hoge waarde, wordt de e-mail gemarkeerd of gelabeld. (Bijvoorbeeld *trα cye@contoso.com* voor *tracye@contoso.com).*

9. **Domein-imitatie** detecteert domeinen die lijken op het domein van de ontvanger en die lijken op een intern domein. Deze imitatie wordt bijvoorbeeld *tracye@liw α re.com* voor *tracye@litware.com.*

## <a name="phase-3---content-filtering"></a>Fase 3 - Inhoudsfilters

In deze fase begint de filtertack met het verwerken van de specifieke inhoud van de e-mail, inclusief de hyperlinks en bijlagen.

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase3.png" alt-text="Fase 3 van filteren in MDO is Inhoudsfiltering.":::

1. **Met transportregels** (ook wel e-mailstroomregels of Exchange-transportregels genoemd) kan een beheerder een groot aantal acties uitvoeren wanneer aan een even groot aantal voorwaarden voor een bericht wordt voldaan. Alle berichten die door uw organisatie stromen, worden geëvalueerd op basis van de ingeschakelde regels voor e-mailstroom/transportregels.

2. **Microsoft Defender Antivirus** en twee *antivirusprogramma's* van derden worden gebruikt om alle bekende malware in bijlagen te detecteren.

3. De antivirusprogramma's (AV)-engines worden ook gebruikt om  alle bijlagen waar te typen, zodat typeblokkering alle bijlagen van typen kan blokkeren die door de beheerder zijn opgegeven.

4. Wanneer Microsoft Defender voor Office 365 een schadelijke bijlage detecteert, worden de hash van het bestand en een hash van de actieve inhoud toegevoegd aan de EOP-reputatie (Exchange Online Protection). **Als u de reputatie van** bijlagen blokkeert, wordt dat bestand geblokkeerd in alle Office 365- en eindpunten via MSAV-cloudgesprekken.

5. **Heuristische clustering** kan bepalen dat een bestand verdacht is op basis van bezorgings heuristische gegevens. Wanneer een verdachte bijlage wordt gevonden, wordt de hele campagne onderbroken en is het bestand sandboxed. Als het bestand schadelijk blijkt te zijn, wordt de hele campagne geblokkeerd.

6. **Machine learning-modellen** werken op de koptekst, hoofdinhoud en URL's van een bericht om phishingpogingen te detecteren.

7. Microsoft gebruikt een bepaling van de reputatie van URL sandboxing en URL-reputatie van feeds van derden in **URL-reputatie** blokkeren , om een bericht te blokkeren met een bekende kwaadaardige URL.

8. **Inhouds heuristische berichten** kunnen verdachte berichten detecteren op basis van structuur en woordfrequentie in de berichtstructuur, met behulp van machine learning-modellen.

9. **Safe Attachments** sandboxes every attachment for Defender for Office 365 customers, using dynamic analysis to detect never-before seen threats.

10. **Met gekoppelde** inhoudsdetonatie wordt elke URL die aan een bestand in een e-mailbericht wordt gekoppeld, behandeld als een bijlage, waarin het bestand asynchron wordt sandboxing op het moment van de bezorging.

11. **URL-detonatie** vindt plaats wanneer upstream anti-phishingtechnologie een bericht of URL verdacht vindt. URL-detonatie sandboxes de URL's in het bericht op het moment van levering.

## <a name="phase-4---post-delivery-protection"></a>Fase 4 - Bescherming na aflevering

De laatste fase vindt plaats na de bezorging van e-mail of bestanden, met e-mail in verschillende postvakken en bestanden en koppelingen die worden weergegeven in clients zoals Microsoft Teams.

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase4.png" alt-text="Fase 4 van filteren in Defender voor Office 365 is bescherming na aflevering.":::

1. **Veilige koppelingen** is de time-of-click-beveiliging van MDO. Elke URL in elk bericht wordt omwikkeld om te wijzen naar Microsoft Safe Links-servers. Wanneer op een URL wordt geklikt, wordt deze gecontroleerd op de meest recente reputatie, voordat de gebruiker wordt omgeleid naar de doelsite. De URL is asynchrone sandboxed om de reputatie bij te werken.

2. **Phish Zero-Hour Automatisch verwijderen (ZAP)** detecteert en neutraliseert met terugwerkende kracht kwaadaardige phishingberichten die al zijn bezorgd in Exchange Online-postvakken.

3. **Malware ZAP** detecteert en neutraliseert schadelijke malwareberichten die al zijn bezorgd in Exchange Online-postvakken en neutraliseert deze met terugwerkende kracht.

4. **Spam ZAP** detecteert en neutraliseert schadelijke spamberichten die al zijn bezorgd in Exchange Online-postvakken.

5. **Met campagneweergaven** kunnen beheerders het grote geheel van een aanval zien, sneller en vollediger dan elk team zonder automatisering. Microsoft maakt gebruik van de enorme hoeveelheden anti-phishing-, antispam- en anti-malwaregegevens in de hele service om campagnes te identificeren. Beheerders kunnen deze vervolgens van begin tot eind onderzoeken, inclusief doelen, effecten en stromen, die ook beschikbaar zijn in een downloadbare campagne.

6. **Met de invoegvoegingen** rapportbericht kunnen personen eenvoudig onwaar-positieven (goede e-mail, per ongeluk gemarkeerd als *slecht)* of onwaar negatieven (slechte e-mail die als goed is *gemarkeerd)* aan Microsoft rapporteren voor verdere analyse.

7. **Veilige koppelingen voor Office-clients** bieden dezelfde time-of-clickbeveiliging voor Veilige koppelingen, inheems binnen Office-clients zoals Word, PowerPoint en Excel.

8. **Beveiliging voor OneDrive, SharePoint** en Teams biedt dezelfde beveiliging tegen veilige bijlagen tegen schadelijke bestanden, inheems, binnen OneDrive, SharePoint en Microsoft Teams.

9. Wanneer een URL die naar een bestand  wijst, is geselecteerd na de bezorging, wordt met gekoppelde inhoudsdetonatie een waarschuwingspagina weergegeven totdat de sandboxing van het bestand is voltooid en de URL veilig is.


## <a name="the-filtering-stack-diagram"></a>Het filtertackdiagram

Het uiteindelijke diagram (zoals met alle onderdelen van het diagram) kan worden gewijzigd naarmate het product groeit *en zich ontwikkelt.* Bladwijzer voor deze pagina en gebruik de **feedbackoptie** die u onderaan vindt als u na updates wilt vragen. Voor uw records is dit de stapel met alle fasen in volgorde:

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase5.png" alt-text="Alle fasen van filteren in MDO in volgorde, 1 tot en met 4.":::

## <a name="more-information"></a>Meer informatie

Moet u Microsoft Defender voor Office 365 ***nu** instellen _? Gebruik deze stapel, _now*, met deze stapsgewijs om [uw](protect-against-threats.md) organisatie te gaan beveiligen.

*Speciale dank van MSFTTracyP en het docs-schrijfteam aan Giulian Garruba voor deze inhoud.*
