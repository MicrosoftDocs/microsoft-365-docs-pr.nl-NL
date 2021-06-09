---
title: Microsoft 365 Overzicht van Defender, waarbij MDO, MDE, MDI en MCAS worden gecombineerd
description: Voordelen in Microsoft 365 Defender, waarbij Microsoft Defender voor Office 365 (MDO) en Microsoft Defender for Endpoint (MDE) worden gecombineerd met Microsoft Defender voor identiteit (MDI) en Microsoft Cloud App Security (MCAS). In dit artikel worden Microsoft 365 defender-ontwikkelingen voor beheerders beschreven.
keywords: beveiliging, malware, Microsoft 365, M365, beveiligingscentrum, monitor, rapport, identiteiten, gegevens, apparaten, apps
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.date: 04/21/2021
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: e88f23013a1a7d9fbeb6ae1d72592182eaaa7547
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841676"
---
# <a name="microsoft-365-defender-overview"></a>Microsoft 365 Overzicht van Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender voor Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)

> Wilt u Microsoft 365 Defender ervaren? U kunt het [evalueren in een testomgeving](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) of [uw pilotproject uitvoeren in een productieomgeving](m365d-pilot.md?ocid=cx-evalpilot).

**Microsoft 365 Defender** () combineert beveiliging, detectie, onderzoek en antwoord op [https://security.microsoft.com](https://security.microsoft.com) *e-mail,*  *samenwerking,* identiteit en *apparaatbedreigingen* in een centrale portal.

Microsoft 365 Defender brengt functionaliteit samen van bestaande Microsoft-beveiligingsportalen, zoals Microsoft Defender-beveiligingscentrum en het Office 365 Security & Compliance center. Het beveiligingscentrum benadrukt snelle toegang tot informatie, eenvoudigere indelingen en het samenbrengen van gerelateerde informatie voor eenvoudiger gebruik. Dit centrum bevat:

- **[Microsoft Defender voor Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)** Microsoft Defender voor Office 365 helpt organisaties hun bedrijf te beveiligen met een reeks preventie-, detectie-, onderzoeks- en zoekfuncties om e-mail en Office 365 beschermen.
- **[Microsoft Defender voor Eindpunt biedt](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)** preventieve beveiliging, detectie na inbreuk, geautomatiseerd onderzoek en antwoord voor apparaten in uw organisatie.
- **[Microsoft 365 Defender](microsoft-365-defender.md)** maakt deel uit van de XDR-oplossing *(Extended Detection and Response)* van Microsoft, die gebruik maakt van de Microsoft 365-beveiligingsportfolio om bedreigingsgegevens in domeinen automatisch te analyseren en een afbeelding te maken van een aanval op één dashboard.

Als u informatie nodig hebt over wat er is gewijzigd in het Office 365 Beveiligings- & Compliancecentrum of het Microsoft Defender-beveiligingscentrum, gaat u naar:

- [Defender voor Office 365 in Microsoft 365 Defender](microsoft-365-security-center-mdo.md)
- [Defender voor Eindpunt in Microsoft 365 Defender](microsoft-365-security-center-mde.md)

> [!NOTE]
> De Microsoft 365 beveiligingsportal gebruikt en dwingt bestaande toegang op basis van rollen af en verplaatst elk beveiligingsmodel naar de geïntegreerde portal. Elke geconvergeerde werkbelasting (zoals MDO of MDE) heeft een eigen toegang op basis van rollen. De rollen in de producten worden automatisch geconvergeerd naar Microsoft 365 beveiligingsportal. Rollen en machtigingen voor MCAS worden echter nog steeds verwerkt in MCAS.

## <a name="what-to-expect"></a>Wat u kunt verwachten

Alle beveiligingsinhoud die u gebruikt in het Office 365-beveiligings- en compliancecentrum (protection.office.com) en het Microsoft Defender-beveiligingscentrum (securitycenter.microsoft.com) vindt u nu in *het Microsoft 365 Defender.*

Microsoft 365 Defender helpt beveiligingsteams bij het onderzoeken en beantwoorden van aanvallen door signalen van verschillende werkbelastingen in te voeren in een set geïntegreerde ervaringen voor:

- Incidenten & waarschuwingen
- Opsporing
- Actiecentrum
- Dreigingsanalyse

Microsoft 365 Defender benadrukt *eenheid, helderheid* en gemeenschappelijke doelen terwijl Microsoft Defender voor Office 365 en Microsoft Defender voor Eindpunt wordt samengevoegd. De samenvoegbewerking is gebaseerd op de onderstaande prioriteiten en is gemaakt zonder dat dit ten koste gaat van de mogelijkheden die elke beveiligingssuite heeft toegevoegd aan de combinatie van:

- Veelgebruikte bouwstenen
- Veelgebruikte terminologie
- Algemene entiteiten
- Functiepariteit met andere werkbelastingen

> [!NOTE]
> Microsoft 365 Defender is toegankelijk zonder dat klanten migratiestappen hoeven te ondernemen of een nieuwe licentie moeten kopen. Deze nieuwe portal is bijvoorbeeld toegankelijk voor beheerders met een E3-abonnement, net zoals voor gebruikers met Microsoft Defender voor Office 365 Abonnement 1 en Abonnement 2. Klanten met Exchange Online Protection MDO-abonnement 1 zien echter alleen de beveiligingsfuncties die hun abonnementslicentie ondersteunt. Het nieuwe centrum heeft als doel de beveiliging te centraliseren.

## <a name="unified-investigations"></a>Geïntegreerde onderzoeken

Convergerende beveiligingscentra maken één plek voor het onderzoeken van beveiligingsincidenten in Microsoft 365. Een primair voorbeeld is **Incidenten** onder **Incidenten & waarschuwingen** over de snelle start van Microsoft 365 Defender.

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="De pagina Incidenten in Microsoft 365 Defender.":::

Als u een incidentnaam selecteert, wordt een pagina weergegeven met de waarde van convergerende beveiligingscentra.

:::image type="content" source="../../media/converged-incident-info-3.png" alt-text="Voorbeeld van de pagina Overzicht voor een incident in Microsoft 365 Defender":::

<!--
![Example of the Summary page for an incident in Microsoft 365 Defender](../../media/converged-incident-info-3.png)
--> 

Boven aan een pagina met incidenten ziet u de tabbladen **Samenvatting,** **Waarschuwingen,** **Apparaten,** **Gebruikers,** **Postvakken,** Onderzoeken **en** Bewijs. Selecteer deze tabbladen voor meer gedetailleerde informatie. Op het  tabblad Gebruikers worden bijvoorbeeld gegevens weergegeven voor gebruikers van geconvergeerde werkbelastingen (Microsoft Defender voor Eindpunt, Microsoft Defender voor identiteit en Microsoft Cloud App Security) en een reeks bronnen, zoals on-premises Active Directory Domain Services (AD DS), Azure Active Directory (Azure AD) en externe identiteitsproviders. Zie Gebruikers onderzoeken [voor meer informatie.](investigate-users.md)

Neem de tijd om de incidenten in uw omgeving te bekijken, in te zoomen op deze tabbladen en te oefenen met het opbouwen van inzicht in hoe u toegang hebt tot de informatie voor incidenten voor verschillende soorten bedreigingen.

Zie incidenten in Defender [Microsoft 365 voor meer informatie.](incidents-overview.md)

## <a name="improved-processes"></a>Verbeterde processen

Veelgebruikte besturingselementen en inhoud worden op dezelfde plaats weergegeven of worden gecondenseerd in één feed met gegevens, zodat u ze gemakkelijker kunt vinden. Bijvoorbeeld geïntegreerde instellingen.

### <a name="unified-settings"></a>Geïntegreerde instellingen

![klikte op 'Rollen' en opende Instellingen pagina met algemene instellingen, machtigingen, API's en regels. Open Machtigingen en vervolgens Rollen. Toont alle rollen](../../media/converged-add-role-9.png)

### <a name="permissions--roles"></a>Machtigingen & rollen

![Machtigingen & pagina Rollen met eindpunten & groepen, rollen en apparaatgroepen.](../../media/converged-roles-5.png)

 Toegang tot Microsoft 365 Defender is geconfigureerd met Azure Active Directory globale rollen of met aangepaste rollen. Zie Gebruikerstoegang toewijzen aan [Microsoft Defender-beveiligingscentrum.](/microsoft-365/security/defender-endpoint/assign-portal-access) Voor Defender voor Office 365, zie Machtigingen in het Microsoft 365 [compliancecentrum en Microsoft 365 Defender](../office-365-security/permissions-microsoft-365-compliance-security.md).

- Meer informatie over het beheren [van toegang tot](m365d-permissions.md) Microsoft 365 Defender
- Meer informatie over het maken [van aangepaste rollen](custom-roles.md) in Microsoft 365 Defender

> [!NOTE]
> Microsoft Defender voor Eindpunt in Microsoft 365 Defender ondersteunt het verlenen van toegang tot beheerde beveiligingsserviceproviders [op](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) dezelfde manier als toegang wordt verleend in het [Microsoft Defender-beveiligingscentrum.](./mssp-access.md)

### <a name="integrated-reports"></a>Geïntegreerde rapporten

Rapporten worden ook samengevoegd in Microsoft 365 Defender. Beheerders kunnen beginnen met een algemeen beveiligingsrapport en zich vertakken naar specifieke rapporten over eindpunten, e-mail & samenwerking. De koppelingen hier worden dynamisch gegenereerd op basis van de configuratie van de werkbelasting.

### <a name="quickly-view-your-microsoft-365-environment"></a>Snel uw Microsoft 365 weergeven

Op **de startpagina** ziet u veel van de veelgebruikte kaarten die beveiligingsteams nodig hebben. De samenstelling van kaarten en gegevens is afhankelijk van de gebruikersrol. Omdat Microsoft 365 beveiligingscentrum gebruikmaakt van toegangsbeheer op basis van rollen, zien verschillende rollen kaarten die meer betekenis hebben voor hun dagelijkse taken.  

Met deze in één oogopslag informatie kunt u op de hoogte blijven van de nieuwste activiteiten in uw organisatie. Microsoft 365 Defender brengt signalen uit verschillende bronnen samen om een holistisch beeld te geven van uw Microsoft 365 omgeving.

De kaarten vallen in deze categorieën:

- **Identiteiten:** controleer de identiteiten in uw organisatie en houd verdachte of riskante gedragingen bij. [Meer informatie over identiteitsbeveiliging.](/azure/active-directory/identity-protection/overview-identity-protection)
- **Gegevens:** help gebruikersactiviteiten bij te houden die kunnen leiden tot het vrijgeven van ongeautoriseerde gegevens.
- **Apparaten:** up-to-date informatie over waarschuwingen, activiteiten voor inbreuken en andere bedreigingen op uw apparaten.
- **Apps:** krijg inzicht in hoe cloud-apps worden gebruikt in uw organisatie. [Meer informatie over Cloud App Security apps die zijn gevonden.](/cloud-app-security/discovered-apps)

## <a name="threat-analytics-with-better-data-coverage"></a>Bedreigingsanalyse met betere gegevensdekking
Volg en reageer op nieuwe bedreigingen met de volgende Microsoft 365 geïntegreerde ervaring voor Defender Threat Analytics:

- Betere gegevensdekking tussen Microsoft Defender voor Eindpunt en Microsoft Defender voor Office 365, waardoor gecombineerd incidentbeheer, automatisch onderzoek, herstel en proactieve of reactieve bedreigingsjacht in het hele domein mogelijk zijn. 
- E-mailgerelateerde detecties en mitigaties van Microsoft Defender voor Office 365, naast de eindpuntgegevens die al beschikbaar zijn van Microsoft Defender voor Eindpunt.
- Een weergave van bedreigingsgerelateerde incidenten waarbij waarschuwingen worden samengevoegd tot end-to-end-aanvalsverhalen in Microsoft Defender voor Eindpunt en Microsoft Defender voor Office 365 om de werkwachtrij te verminderen en uw onderzoek te vereenvoudigen en te versnellen.
- Aanvalspogingen gedetecteerd en geblokkeerd door Microsoft 365 Defender-oplossingen. Er zijn ook gegevens die u kunt gebruiken om preventief te werken om het risico op verdere blootstelling te beperken en de tolerantie te vergroten. 
- Verbeterd ontwerp dat actie-informatie in de spotlight zet om snel gegevens te identificeren, zodat u zich snel kunt concentreren op, kunt onderzoeken en gebruikmaken van de rapporten.

## <a name="a-centralized-learning-hub"></a>Een gecentraliseerde leerhub

Microsoft 365 beveiligingscentrum bevat een leerhub die officiële richtlijnen opsneert van bronnen zoals de Microsoft-beveiligingsblog, de Microsoft-beveiligingscommunity op YouTube en de officiële documentatie op docs.microsoft.com.

In de leerhub staan E-mail & Collaboration (Microsoft Defender voor Office 365 of MDO) naast Endpoint (Microsoft Defender voor Eindpunt of MDE) en Microsoft 365 Defender leerbronnen.

De leerhub wordt geopend met leerpaden die zijn georganiseerd rond onderwerpen zoals 'How to Investigate Using Microsoft 365 Defender?' en 'Microsoft Defender voor Office 365 best practices'. Deze sectie wordt momenteel samengesteld door de beveiligingsproductgroep binnen Microsoft. Elk leerpad weerspiegelt een verwachte tijd die nodig is om door de concepten te gaan. Bijvoorbeeld: 'Stappen die u moet nemen wanneer een Microsoft Defender voor Office 365 gebruikersaccount is gecompromitteerd' kan acht minuten duren en is een waardevolle leerervaring.

Nadat u naar de inhoud hebt geklikt, kan het handig zijn om deze site een bladwijzer te geven en bladwijzers te ordenen in een map 'Beveiliging' of 'Kritiek'. Als u alle leerpaden wilt zien, klikt u op de koppeling Alle tonen in het hoofdvenster.

> [!NOTE]
> Er zijn handige **filters** aan de bovenkant van Microsoft 365 Defender-leerhub, zodat u kunt kiezen tussen producten (momenteel Microsoft 365 Defender, Microsoft Defender voor Eindpunt en Microsoft Defender voor Office 365). Het aantal leerbronnen voor elke sectie wordt vermeld, zodat leerlingen/studenten kunnen bijhouden hoeveel resources ze bij de hand hebben voor training en leren.
>
> Naast het productfilter worden actuele onderwerpen, typen resources (van video's tot webinars), niveaus van vertrouwdheid of ervaring met beveiligingsgebieden, beveiligingsrollen en productfuncties weergegeven.

> [!TIP]
> Er zijn veel andere leermogelijkheden in [Microsoft Learn.](/e/learn/) U vindt certificeringstraining zoals [Cursus MS-500T02-A: Implementatie van](/learn/certifications/courses/ms-500t02)Microsoft 365 Threat Protection .

## <a name="send-us-your-feedback"></a>Stuur ons uw feedback

We hebben uw feedback nodig. We zijn altijd op zoek naar verbetering, dus als er iets is dat u wilt zien, stuurt u ons uw feedback [Microsoft 365 Defender.](https://www.microsoft.com/videoplayer/embed/RE4K5Ci)

U kunt ook feedback geven in dit artikel. In de sectie 'Feedback' aan het einde onder 'Feedback verzenden en weergeven voor', zijn de opties *Dit product* of *Deze pagina.*

Gebruik de **knop Dit product** voor *productfeedback:*

1. Selecteer *Dit product* onderaan het artikel.
    1. Klik met de rechtermuisknop op de knop en 'Openen in een nieuw tabblad' als u deze aanwijzingen wilt blijven lezen.
2. Hiermee navigeert u naar **het UserVoice-forum.**
3. U hebt twee opties:
    1. Schuif omlaag naar het tekstvak Hoe kunnen we de naleving verbeteren of uw gebruikers beter beschermen *in Office 365?* en plakken in *Microsoft 365 Defender.* U kunt in de resultaten zoeken naar een idee zoals dat van u en het idee up-vote of de knop gebruiken voor **Een nieuw idee posten.**
    1. Als u zeker weet dat dit probleem al is gerapporteerd en het profiel wilt verhogen met een stem (of stemmen), gebruikt u het vak *Feedback* geven aan de rechterkant van UserVoice. Zoek naar *Microsoft 365 Defender,* **zoek het probleem en gebruik de stemknop om** de status te verhogen.

Gebruik *Deze pagina voor* feedback over het artikel zelf. Bedankt voor uw feedback. Uw stem helpt ons producten te verbeteren.

### <a name="explore-what-the-security-center-has-to-offer"></a>Ontdek wat het beveiligingscentrum te bieden heeft

Blijf de functies en mogelijkheden in defender Microsoft 365 verkennen:

- [Incidenten en waarschuwingen beheren](manage-incidents.md)
- [Nieuwe bedreigingen bijhouden en beantwoorden met bedreigingsanalyse](threat-analytics.md)
- [Het Actiecentrum](m365d-action-center.md)
- [Dreigingen in apparaten, e-mailberichten, apps en identiteiten opsporen](./advanced-hunting-query-emails-devices.md)
- [Aangepaste regels voor detectie](./custom-detection-rules.md)
- [Waarschuwingen voor E-mail en samenwerking](../../compliance/alert-policies.md#default-alert-policies)
- [Maak een phishing-aanvalssimulatie](../office-365-security/attack-simulation-training.md) [en maak een payload voor het trainen van uw teams](/microsoft-365/security/office-365-security/attack-simulation-training-payloads)
 
### <a name="related-information"></a>Gerelateerde informatie
- [Microsoft Defender voor Office 365 in Microsoft 365 Defender](microsoft-365-security-center-mdo.md)
- [Microsoft Defender voor Eindpunt in Microsoft 365 Defender](microsoft-365-security-center-mde.md)
- [Accounts omleiden van Microsoft Defender voor Eindpunt naar Microsoft 365 Defender](microsoft-365-security-mde-redirection.md)