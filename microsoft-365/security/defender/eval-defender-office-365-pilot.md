---
title: Test Microsoft Defender voor Office 365, gebruik de evaluatie in uw productieomgeving, bevorder de evaluatie om in productie te leven, leer hoe u Defender evalueert
description: Stappen om uw evaluatie te testen met groepen actieve en bestaande gebruikers om de functies van Microsoft Defender goed te testen voor Office 365.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 05/25/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: how-to
ms.technology: m365d
ms.openlocfilehash: 86f8dcc7b5e06605042f609ede4027510663cc65
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457863"
---
# <a name="pilot-microsoft-defender-for-office-365"></a>Test Microsoft Defender voor Office 365
**Van toepassing op:**
- Microsoft 365 Defender

Dit artikel is [stap 3 van 3](eval-defender-office-365-overview.md) in het proces van het instellen van de evaluatieomgeving voor Microsoft Defender voor Office 365. Zie het [overzichtsartikel](eval-defender-office-365-overview.md)voor meer informatie over dit proces.

Gebruik de volgende stappen om de pilot voor Microsoft Defender in te stellen en te configureren Office 365.

![Stappen voor het maken van de pilot voor Microsoft Defender voor Office 365](../../media/defender/m365-defender-office-pilot.png)

- [Stap 1: Pilotgroepen maken](#step-1-create-pilot-groups)
- [Stap 2: Beveiliging configureren](#step-2-configure-protection)
- [Stap 3: Mogelijkheden uitproberen: vertrouwd raken met simulatie, monitoring en metrische gegevens](#step-3-try-out-capabilities--get-familiar-with-simulation-monitoring-and-metrics)

Wanneer u Microsoft Defender evalueert voor Office 365, kunt u ervoor kiezen om specifieke gebruikers te piloten voordat u beleidsregels in- en afdwingt voor uw hele organisatie. Het maken van distributiegroepen kan helpen bij het beheren van de implementatieprocessen. Maak bijvoorbeeld groepen zoals Defender voor *Office 365-gebruikers -* Standaardbeveiliging, Defender voor *Office 365-gebruikers - Strikte* beveiliging, Defender voor *Office 365-gebruikers - Aangepaste* beveiliging of Defender voor *Office 365-gebruikers - Uitzonderingen.*

Het is misschien niet duidelijk waarom 'Standaard' en 'Strikt' de termen zijn die hiervoor worden gebruikt, maar dat wordt duidelijk wanneer u meer informatie over Defender voor Office 365 beveiligingsinstellingen. Naamgevingsgroepen 'aangepast' en 'uitzonderingen' spreken voor zich, en  hoewel de meeste van uw gebruikers onder standaard en *strikte,* aangepaste en uitzonderingsgroepen vallen, worden waardevolle gegevens voor u verzameld over het beheren van risico's.

## <a name="step-1-create-pilot-groups"></a>Stap 1: Pilotgroepen maken

Distributiegroepen kunnen rechtstreeks worden gemaakt en gedefinieerd in Exchange Online of worden gesynchroniseerd vanuit on-premises Active Directory.

1. Aanmelding bij Exchange(EAC) met behulp van een account dat is toegewezen als beheerder van geadresseerde of gedelegeerde machtigingen voor groepsbeheer.
2. Vouw geadresseerden uit in het navigatiemenu *en* selecteer *Groepen.*

:::image type="content" source="../../media/mdo-eval/1_mdo-eval-pilot.png" alt-text="Exchange beheercentrum in het navigatiemenu (snel starten) met een pijl die naar Groepen wijst. Klik op Groepen.":::

3. Selecteer in het dashboard Groepen de optie 'Een groep toevoegen'.

:::image type="content" source="../../media/mdo-eval/2_mdo-eval-pilot-add-group.png" alt-text="Groepen toevoegen in het deelvenster Groepen.":::

4. Voor groeptype selecteert u *Verdeling* en klikt u op Volgende.

:::image type="content" source="../../media/mdo-eval/3-mdo-eval-pilot-group-type.png" alt-text="Kies hier een type distributiegroep.":::

5. Geef de groep een naam en beschrijving en klik vervolgens op Volgende.

:::image type="content" source="../../media/mdo-eval/4_mdo-eval-pilot-set-up-basics.png" alt-text="De groep een naam geven en beschrijven.":::

## <a name="step-2-configure-protection"></a>Stap 2: Beveiliging configureren

Sommige mogelijkheden in Defender voor Office 365 zijn standaard geconfigureerd en ingeschakeld, maar beveiligingsbewerkingen willen mogelijk het beveiligingsniveau van de standaardinstelling verhogen.

Sommige mogelijkheden zijn *nog niet* geconfigureerd. U hebt drie opties voor het configureren van beveiliging:

- **Automatisch vooraf ingestelde beveiligingsbeleid** toewijzen: [vooraf](../office-365-security/preset-security-policies.md) ingestelde beveiligingsbeleidsregels worden geleverd als een methode om snel een uniform beveiligingsniveau toe te wijzen voor alle mogelijkheden. U kunt kiezen uit **_standaard_*_ of _*_strikt_**. Een goede benadering is om te beginnen met vooraf ingestelde beveiligingsbeleidsregels en vervolgens het beleid aan te passen terwijl u meer informatie krijgt over de mogelijkheden en uw eigen unieke bedreigingsomgeving. Het voordeel hiervan is dat u groepen gebruikers zo snel mogelijk beschermt, met de mogelijkheid om de beveiliging daarna aan te passen. (Deze methode wordt aanbevolen.)
- **Basislijnbeveiliging handmatig** configureren: als u de omgeving zelf  wilt configureren, kunt u snel een basislijn van beveiliging bereiken door de richtlijnen in Beschermen [tegen bedreigingen te volgen.](../office-365-security/protect-against-threats.md) Met deze methode krijgt u meer informatie over de instellingen die u kunt configureren. En natuurlijk kunt u het beleid later verder afstemmen.
- **Aangepaste *beveiligingsbeleid* configureren:** u kunt ook aangepaste beveiligingsbeleidsregels maken en toewijzen als onderdeel van uw evaluatie. Voordat u beleid gaat aanpassen, is het belangrijk om te weten welke prioriteit deze beveiligingsbeleidsregels worden toegepast en afgedwongen. Beveiligingsops moeten een aantal beleidsregels maken, zelfs als de vooraf ingestelde beleidsinstelling is toegepast, in het bijzonder om beveiligingsbeleid te definiëren voor Safe Koppelingen en Safe Bijlagen.

> [!IMPORTANT]
> **Als u aangepaste** beveiligingsbeleidsregels moet configureren, moet  u  hier de waarden bekijken die de definities Standaard en Strikt beveiliging bevatten: Aanbevolen instellingen voor EOP en Microsoft Defender voor Office 365 *[beveiliging.](../office-365-security/recommended-settings-for-eop-and-office365.md)* Standaardwaarden, zoals weergegeven voordat een configuratie plaatsvindt, worden ook weergegeven. Bewaar een spreadsheet van waar uw aangepaste build van afwijkt.

### <a name="assign-preset-security-policies"></a>Vooraf ingestelde beveiligingsbeleidsregels toewijzen

Het wordt aangeraden om  te beginnen met het aanbevolen basislijnbeleid bij de evaluatie van MDO en deze vervolgens zo nodig te verfijnen in de loop van de evaluatieperiode.

U kunt aanbevolen EOP en Defender snel inschakelen Office 365 beveiligingsbeleid en deze toewijzen aan specifieke testgebruikers of gedefinieerde groepen als onderdeel van uw evaluatie. Vooraf ingestelde beleidsregels bieden een **standaardbeveiligingssjabloon** voor basislijn of een agressievere strikte beschermingssjabloon die onafhankelijk van elkaar kan worden toegewezen of gecombineerd. 

Hier is het [beveiligingsbeleid vooraf ingesteld in EOP en Microsoft Defender voor Office 365](../office-365-security/preset-security-policies.md) waarin de stappen worden beschreven.

1. Meld u aan bij uw Microsoft 365 tenant. Gebruik een account met toegang tot de Microsoft 365 Defender portal, toegevoegd aan de rol organisatiebeheer in Office 365 of beveiligingsbeheerder in Microsoft 365.
2. Selecteer in het navigatiemenu de optie *& regels onder* E-mail & Samenwerking.

:::image type="content" source="../../media/mdo-eval/5_mdo-eval-pilot-policies.png" alt-text="Klik onder & samenwerking in het navigatievenster op Beleidsregels & regels.":::

3. Klik op het & beleidsregels op *Bedreigingsbeleid.*

:::image type="content" source="../../media/mdo-eval/6-mdo-eval-pilot-threat-policies.png" alt-text="a":::

4. Vouw in Microsoft 365 Defender portal Bedreigingsbeheer uit in het navigatiemenu en selecteer vervolgens Beleid in het submenu.
5. Klik op het dashboard Beleid op *Vooraf ingestelde beveiligingsbeleidsregels.*

:::image type="content" source="../../media/mdo-eval/7-mdo-eval-pilot-template-policies.png" alt-text="Klik op de tegel Vooraf ingestelde beveiligingsbeleid.":::

6. Klik *op Bewerken* om het standaardbeleid en/of strikt beleid te configureren en toe te wijzen. :::image type="content" source="../../media/mdo-eval/8-mdo-eval-pilot-preset.png" alt-text="Klik in het deelvenster Vooraf ingestelde beveiligingsbeleidsregels op Bewerken.":::
7. Voeg zo nodig voorwaarden toe om basislijn ***EOP** _ beveiligingen toe te passen op specifieke testgebruikers of groepen gebruikers en selecteer _Next* om door te gaan.
    - Een Defender voor Office 365-voorwaarde voor testevaluaties kan bijvoorbeeld worden  toegepast als de geadresseerden lid zijn van een gedefinieerde groep Defender voor *Office 365 Standard Protection* en vervolgens worden beheerd door alleen accounts toe te voegen aan of account uit de groep te verwijderen.
 :::image type="content" source="../../media/mdo-eval/9-mdo-eval-pilot-eop-protections.png" alt-text="Voeg de voorwaarden toe die nodig zijn om het EOP-beveiligingsniveau toe te passen op uw testgroep.":::

8. Voeg zo nodig voorwaarden toe om basislijn ***MDO** _ beveiliging toe te passen op specifieke testgebruikers of groepen gebruikers. Klik _Next* om door te gaan.
    - Een voorwaarde voor Defender voor Office 365 voor testevaluaties kan bijvoorbeeld worden  toegepast als de geadresseerden lid zijn van een gedefinieerde Defender voor *Office 365 Standard Protection-groep* en vervolgens worden beheerd door alleen accounts toe te voegen of te verwijderen via de groep.
  :::image type="content" source="../../media/mdo-eval/10-mdo-eval-pilot-mdo-protections.png" alt-text="Voeg de voorwaarden toe die nodig zijn om het beveiligingsniveau van Defender Office 365 toe te passen op uw testgroep.":::

9. Controleer en bevestig uw wijzigingen voor het toewijzen van vooraf ingestelde beveiligingsbeleidsregels.
10. Vooraf ingestelde beveiligingsbeleidsregels kunnen worden beheerd (opnieuw geconfigureerd, opnieuw toegepast, uitgeschakeld, enzovoort) door terug te keren naar de Microsoft 365 Defender-portal > Policies &-regels > Bedreigingsbeleid > en op de tegel Vooraf ingestelde beveiligingsbeleid te klikken. 

### <a name="configure-custom-protection-policies"></a>Aangepast beveiligingsbeleid configureren

De vooraf gedefinieerde *standaard-* of *strikte* Defender-Office 365 bieden uw testgebruikers de aanbevolen basislijnbeveiliging. U kunt echter ook aangepaste beveiligingsbeleidsregels maken en toewijzen als onderdeel van uw evaluatie.

Het is belangrijk *om* op de hoogte te zijn van de prioriteit die deze beveiligingsbeleidsregels krijgen wanneer ze worden toegepast en afgedwongen, zoals Order en prioriteit van e-mailbeveiliging [- Office 365](../office-365-security/how-policies-and-protections-are-combined.md) wordt uitgelegd.

De onderstaande tabel bevat verwijzingen en aanvullende richtlijnen voor het configureren en toewijzen van aangepast beveiligingsbeleid:

|Beleid   |Omschrijving  |Verwijzing  |
|:---------:|---------|---------|
|Verbindingsfilters     |    Identificeer goede of slechte bron-e-mailservers door hun IP-adressen.     |     [Het standaardbeleid voor verbindingsfilter configureren in EOP](../office-365-security/configure-the-connection-filter-policy.md)    |
|Anti-malware    |    Bescherm gebruikers tegen e-mail malware, inclusief welke acties moeten worden ondernomen en wie moet melden als malware wordt gedetecteerd.     |    [Anti-malwarebeleid configureren in EOP](../office-365-security/configure-anti-malware-policies.md)     |
|Anti-spoofing     |  Bescherm gebruikers tegen spoofingpogingen met behulp van spoof intelligence en spoof intelligence insights.   |     [Spoof intelligence configureren in Defender voor Office 365](../office-365-security/learn-about-spoof-intelligence.md)    |
|Antispam     |    Bescherm gebruikers tegen e-mailspam, inclusief welke acties moeten worden ondernomen als spam wordt gedetecteerd.     |    [Antispambeleid configureren in Defender voor Office 365](../office-365-security/configure-your-spam-filter-policies.md)     |
|Anti-phishing     |   Gebruikers beschermen tegen phishingaanvallen en veiligheidstips voor verdachte berichten configureren      |     [Anti-phishingbeleid configureren in Defender voor Office 365](../office-365-security/configure-mdo-anti-phishing-policies.md)    |
|Veilige bijlagen     |    Bescherm gebruikers tegen schadelijke inhoud in e-mailbijlagen en bestanden in SharePoint, OneDrive en Teams.     |    [Beleid voor veilige bijlagen instellen in Defender voor Office 365](../office-365-security/set-up-safe-attachments-policies.md)     |
|Veilige koppelingen     |     Bescherm gebruikers tegen het openen en delen van schadelijke koppelingen in e-mailberichten of Office bureaublad-apps.    |    [Beleid voor veilige koppelingen instellen in Defender voor Office 365](../office-365-security/set-up-safe-links-policies.md)     |

## <a name="step-3-try-out-capabilities--get-familiar-with-simulation-monitoring-and-metrics"></a>Stap 3: Mogelijkheden uitproberen: vertrouwd raken met simulatie, monitoring en metrische gegevens

Nu uw pilot is ingesteld en geconfigureerd, is het handig om vertrouwd te raken met de rapportage-, monitoring- en aanvalssimulatieprogramma's die uniek zijn voor Microsoft Defender voor Microsoft 365.

|Mogelijkheid  |Beschrijving  |Meer informatie  |
|---------|---------|---------|
|Bedreigingsverkenner     | Threat Explorer is een krachtig hulpprogramma in realtime waarmee Beveiligingsbewerkingsteams bedreigingen kunnen onderzoeken en beantwoorden en informatie kunnen weergeven over vermoedelijke malware en phish in e-mail en bestanden in Office 365, evenals andere beveiligingsrisico's en risico's voor uw organisatie.        | [Weergaven in Threat Explorer en realtime detecties ](../office-365-security/threat-explorer-views.md)       | 
|Aanvalssimulator     | U kunt Training voor aanvalssimulatie gebruiken in de Microsoft Defender 365-portal om realistische aanvalsscenario's in uw organisatie uit te voeren waarmee u kwetsbare gebruikers kunt identificeren en vinden voordat een echte aanval van invloed is op uw omgeving.        |  [Attack Simulator in Microsoft Defender voor Office 365](../office-365-security/attack-simulator.md)       |
|Rapportendashboard     | Klik in het linkernavigatiemenu op Rapporten en vouw de kop E-mail & samenwerking uit. In de samenwerkingsrapporten voor e-mail & worden beveiligingstrends gedetecteerd, waarvan sommige u in staat stellen actie te ondernemen (via knoppen zoals 'Ga naar inzendingen') en andere met trends, zoals Overzicht van de status mailflow, Top Malware, Spoofdetecties, Gecompromitteerde gebruikers, E-maillatentie, Safe Koppelingen en Safe-bijlagenrapporten. Deze metrische gegevens worden automatisch gegenereerd.  |    [Rapporten weergeven](../office-365-security/view-email-security-reports.md)     |

## <a name="next-steps"></a>Volgende stappen


[Microsoft Defender voor Eindpunt evalueren](eval-defender-endpoint-overview.md)

Ga terug naar het overzicht voor [Microsoft Defender evalueren voor Office 365](eval-defender-office-365-overview.md)

Ga terug naar het overzicht voor [Evalueren en Microsoft 365 Defender](eval-overview.md)