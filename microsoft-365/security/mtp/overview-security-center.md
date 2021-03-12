---
title: Overzicht van Microsoft 365-beveiligingscentrum
description: Voordelen in het Microsoft 365-beveiligingscentrum, waarbij Microsoft Defender voor Office 365 (MDO) en Microsoft Defender for Endpoint (MDE) worden gecombineerd met Microsoft Defender voor identiteit (MDI) en Microsoft Cloud App Security (MCAS). In dit artikel worden de ontwikkelingen in het Microsoft 365-beveiligingscentrum voor beheerders beschreven.
keywords: beveiliging, malware, Microsoft 365, M365, beveiligingscentrum, monitor, rapport, identiteiten, gegevens, apparaten, apps
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.date: 02/02/2021
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
ms.openlocfilehash: 7db9b9762830384370a4bedf220d7a52112ab1ea
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727209"
---
# <a name="the-unified-microsoft-365-security-center-overview"></a>Het overzicht van het geïntegreerde Microsoft 365-beveiligingscentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Van toepassing op:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft Defender voor Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)

> Wilt u Microsoft 365 Defender ervaren? U kunt [het project evalueren in een labomgeving](https://aka.ms/mtp-trial-lab) of uw [pilotproject uitvoeren in productie.](https://aka.ms/m365d-pilotplaybook)

Het verbeterde **Microsoft 365-beveiligingscentrum** () combineert beveiliging, detectie, onderzoek en antwoord op e-mail, [https://security.microsoft.com](https://security.microsoft.com) *samenwerking,* identiteit *en* *apparaatrisico's* in een centrale portal. 

Microsoft 365-beveiligingscentrum brengt functionaliteit samen van bestaande Microsoft-beveiligingsportalen, zoals Microsoft Defender-beveiligingscentrum en het Office 365-beveiligingscentrum & Compliancecentrum. Het beveiligingscentrum benadrukt snelle toegang tot informatie, eenvoudigere indelingen en het samenbrengen van gerelateerde informatie voor eenvoudiger gebruik. Dit centrum bevat:

- **[Microsoft Defender voor Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)** Microsoft Defender voor Office 365 helpt organisaties hun bedrijf te beveiligen met een reeks preventie-, detectie-, onderzoeks- en zoekfuncties om e-mail en Office 365-bronnen te beschermen.
- **[Microsoft Defender voor Eindpunt biedt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)** preventieve beveiliging, detectie na inbreuk, geautomatiseerd onderzoek en antwoord voor apparaten in uw organisatie.
- **[Microsoft 365 Defender](microsoft-threat-protection.md)** maakt deel uit van de XDR-oplossing *(Extended Detection and Response)* van Microsoft, die gebruik maakt van de Microsoft 365-beveiligingsportfolio om bedreigingsgegevens in domeinen automatisch te analyseren en een afbeelding te maken van een aanval op één dashboard.

Zie het volgende als u informatie nodig hebt over wat er is gewijzigd in het Office 365-beveiligingscentrum & compliancecentrum of het Microsoft Defender-beveiligingscentrum:

- [Defender voor Office 365 in het Microsoft 365-beveiligingscentrum](microsoft-365-security-center-mdo.md)
- [Defender voor Eindpunt in het Microsoft 365-beveiligingscentrum](microsoft-365-security-center-mde.md)

## <a name="what-to-expect"></a>Wat u kunt verwachten

Alle beveiligingsinhoud die u gebruikt in het Office 365-beveiligings- en compliancecentrum (protection.office.com) en het Microsoft Defender-beveiligingscentrum (securitycenter.microsoft.com) vindt u nu in het *Microsoft 365-beveiligingscentrum.*

Microsoft 365-beveiligingscentrum helpt beveiligingsteams bij het onderzoeken en beantwoorden van aanvallen door signalen van verschillende werkbelastingen in één geïntegreerde ervaring op te nemen:

- Incidenten & waarschuwingen
- Jagen
- Actiecentrum
- Dreigingsanalyse

Het Microsoft 365-beveiligingscentrum benadrukt *eenheid,* helderheid en gemeenschappelijke doelen terwijl Microsoft Defender voor Office 365 en Microsoft Defender voor Eindpunt worden samengevoegd. De samenvoegbewerking is gebaseerd op de onderstaande prioriteiten en is gemaakt zonder dat dit ten koste gaat van de mogelijkheden die elke beveiligingssuite aan de combinatie heeft toegevoegd:

- veelgebruikte bouwstenen
- algemene terminologie
- algemene entiteiten
- functiepariteit met andere werkbelastingen

## <a name="unified-investigations"></a>Geïntegreerde onderzoeken

Door beveiligingscentra te stroomlijnen, wordt één deelvenster gemaakt voor het onderzoeken van incidenten in een Microsoft 365-organisatie. Een primair voorbeeld is het **knooppunt Incidenten** bij de snelle start van het Microsoft 365-beveiligingscentrum.

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="De pagina Incidenten in MDO.":::

Als u bijvoorbeeld dubbelklikt op een  incidentnaam met hoge ernst, komt u op een pagina die het voordeel van convergerende centra aantoont.

![Incident in meerdere fases met escalatie van bevoegdheden op meerdere eindpunten, met 16 beïnvloede apparaten en 9 beïnvloede gebruikers.](../../media/converged-incident-info-3.png)

> [!TIP]
> Het tabblad **Geconvergeerde** gebruikers is een goede plek om uw vragen te starten. Op deze enkele pagina wordt informatie weergegeven voor gebruikers van geconvergeerde werkbelastingen (Microsoft Defender voor Eindpunt, Microsoft Defender voor identiteit en MCAS, als u deze gebruikt) en een reeks bronnen, zoals on-premises Active Directory, Azure Active Directory, gesynchroniseerde, lokale en externe gebruikers. Meer informatie over [de nieuwe gebruikerservaring.](investigate-users.md)

Incidentgegevens tonen specifieke gebruikers-/identiteitsgegevens en risicoapparaten, naast de betreffende postvakken. Het heeft ook betrekking op **onderzoeksgegevens en** verzamelde **gegevens**. Dit maakt het voor beheerders en beveiligingsbewerkingsteams gemakkelijker om van één waarschuwing met een hoog risico naar de getroffen gebruikers en postvakken te draaien. Als u naar **de tabbladen Incident** boven aan deze pagina kijkt, zijn er andere belangrijke beveiligingspivots beschikbaar vanaf deze ene locatie.

> [!IMPORTANT]
> Boven aan een pagina voor een specifiek incident ziet u de tabbladen **Samenvatting,** **Waarschuwingen,** **Apparaten,** **Gebruikers,** **Postvakken,** Onderzoeken **en** Bewijs.

Als **u Onderzoeken selecteert,** wordt een pagina geopend met een afbeelding van de analyse die wordt uitgevoerd en wordt een status (zoals goedkeuring in **behandeling)** weergegeven voor herstel. Neem de tijd om specifieke incidenten in uw omgeving te selecteren, in te zoomen op deze tabbladen en te oefenen met het opbouwen van een profiel voor verschillende soorten bedreigingen. Vertrouwdheid is van pas als er later een onderzoek wordt gestart.

## <a name="improved-processes"></a>Verbeterde processen

Veelgebruikte besturingselementen en inhoud worden op dezelfde plaats weergegeven of worden gecondenseerd in één feed met gegevens, zodat u ze gemakkelijker kunt vinden. Bijvoorbeeld geïntegreerde instellingen.

### <a name="unified-settings"></a>Geïntegreerde instellingen

![klik op 'Rollen' en opende de pagina Instellingen, met algemene instellingen, machtigingen, API's en regels. Open Machtigingen en vervolgens Rollen. Toont alle rollen](../../media/converged-add-role-9.png)

### <a name="permissions--roles"></a>Machtigingen & rollen

![Machtigingen & pagina Rollen met eindpunten & groepen, rollen en apparaatgroepen.](../../media/converged-roles-5.png)

 Access het Microsoft 365-beveiligingscentrum is geconfigureerd met globale azure Active Directory-rollen of met aangepaste rollen. Zie Gebruikerstoegang toewijzen aan [het Microsoft Defender-beveiligingscentrum](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/assign-portal-access)voor Defender voor Eindpunt. Zie Machtigingen in het [Microsoft 365-compliancecentrum en het Microsoft 365-beveiligingscentrum voor Defender voor Office 365.](../office-365-security/permissions-microsoft-365-compliance-security.md)

- Meer informatie over het beheren [van toegang tot Microsoft 365 Defender](mtp-permissions.md)
- Meer informatie over het maken [van aangepaste rollen](custom-roles.md) in het Microsoft 365-beveiligingscentrum

> [!NOTE]
> Microsoft Defender voor Eindpunt in het Microsoft 365-beveiligingscentrum ondersteunt het verlenen van toegang tot beheerde beveiligingsserviceproviders [(MSSP's)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) op dezelfde manier als toegang wordt verleend in het [Microsoft Defender-beveiligingscentrum.](https://docs.microsoft.com/microsoft-365/security/mtp/mssp-access)

### <a name="integrated-reports"></a>Geïntegreerde rapporten

Rapporten worden ook geïntegreerd in het Microsoft 365-beveiligingscentrum. Beheerders kunnen beginnen met een algemeen beveiligingsrapport en zich vertakken naar specifieke rapporten over eindpunten, e-mail & samenwerking. De koppelingen hier worden dynamisch gegenereerd op basis van de configuratie van de werkbelasting.

### <a name="quickly-view-your-microsoft-365-environment"></a>Snel uw Microsoft 365-omgeving weergeven

Op **de startpagina** ziet u veel van de veelgebruikte kaarten die beveiligingsteams nodig hebben. De samenstelling van kaarten en gegevens is afhankelijk van de gebruikersrol. Omdat het Microsoft 365-beveiligingscentrum gebruikmaakt van toegangsbeheer op basis van rollen, zien verschillende rollen kaarten die meer betekenis hebben voor hun dagelijkse taken.  

Met deze in één oogopslag informatie kunt u op de hoogte blijven van de nieuwste activiteiten in uw organisatie. Het Microsoft 365-beveiligingscentrum brengt signalen uit verschillende bronnen samen om een holistisch beeld te geven van uw Microsoft 365-omgeving.

De kaarten vallen in deze categorieën:

- **Identiteiten:** controleer de identiteiten in uw organisatie en houd verdachte of riskante gedragingen bij. [Meer informatie over identiteitsbeveiliging.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)
- **Gegevens:** help gebruikersactiviteiten bij te houden die kunnen leiden tot het vrijgeven van ongeautoriseerde gegevens.
- **Apparaten:** up-to-date informatie over waarschuwingen, activiteiten voor inbreuken en andere bedreigingen op uw apparaten.
- **Apps:** krijg inzicht in hoe cloud-apps worden gebruikt in uw organisatie. [Meer informatie over apps die door Cloud App Security zijn gevonden.](https://docs.microsoft.com/cloud-app-security/discovered-apps)

## <a name="threat-analytics-with-better-data-coverage"></a>Bedreigingsanalyse met betere gegevensdekking
Volg en reageer op nieuwe bedreigingen met de volgende geïntegreerde microsoft 365 Defender Threat Analytics-ervaring:

- Betere gegevensdekking tussen Microsoft Defender voor Eindpunt en Microsoft Defender voor Office 365, waardoor gecombineerd incidentbeheer, automatisch onderzoek, herstel en proactieve of reactieve bedreigingsjacht in het hele domein mogelijk zijn. 
- E-mailgerelateerde detecties en mitigaties van Microsoft Defender voor Office 365, naast de eindpuntgegevens die al beschikbaar zijn van Microsoft Defender voor Eindpunt.
- Een weergave van bedreigingsgerelateerde incidenten waarbij waarschuwingen worden samengevoegd tot end-to-end-aanvalsverhalen in Microsoft Defender voor Eindpunt en Microsoft Defender voor Office 365 om de werkwachtrij te verminderen en uw onderzoek te vereenvoudigen en te versnellen.
- Aanvalspogingen gedetecteerd en geblokkeerd door Microsoft 365 Defender-oplossingen. Er zijn ook gegevens die u kunt gebruiken om preventief te werken om het risico op verdere blootstelling te beperken en de tolerantie te vergroten. 
- Verbeterd ontwerp dat actie-informatie in de spotlight zet om snel gegevens te identificeren, zodat u zich snel kunt concentreren op, kunt onderzoeken en gebruikmaken van de rapporten.

## <a name="a-centralized-learning-hub"></a>Een gecentraliseerde leerhub

Het Microsoft 365-beveiligingscentrum bevat een leerhub die officiële richtlijnen bevat van bronnen zoals de Microsoft-beveiligingsblog, de Microsoft-beveiligingscommunity op YouTube en de officiële documentatie op docs.microsoft.com.

In de leerhub staan E-mail & Collaboration (Microsoft Defender voor Office 365 of MDO) naast eindpunten (Microsoft Defender voor Eindpunt of MDE) en leerbronnen van Microsoft 365 Defender.

De leerhub wordt geopend met leerpaden die zijn georganiseerd rond onderwerpen zoals 'How to Investigate Using Microsoft 365 Defender?' en 'Microsoft Defender voor Office 365 Best Practices'. Deze sectie wordt momenteel samengesteld door de beveiligingsproductgroep binnen Microsoft. Elk leerpad weerspiegelt een verwachte tijd die nodig is om door de concepten te gaan. Bijvoorbeeld: 'Stappen die moeten worden ondernomen wanneer een Microsoft Defender voor Office 365-gebruikersaccount is gehackt' worden in acht minuten geprojecteerd en zijn waardevolle informatie.

Nadat u naar de inhoud hebt geklikt, kan het handig zijn om deze site een bladwijzer te geven en bladwijzers te ordenen in een map 'Beveiliging' of 'Kritiek'. Als u alle leerpaden wilt zien, klikt u op de koppeling Alle tonen in het hoofdvenster.

> [!NOTE]
> Er zijn handige **filters** boven aan de leerhub van het Microsoft 365-beveiligingscentrum, zodat u kunt kiezen tussen producten (momenteel Microsoft 365 Defender, Microsoft Defender voor Eindpunt en Microsoft Defender voor Office 365). Het aantal leerbronnen voor elke sectie wordt vermeld, zodat leerlingen/studenten kunnen bijhouden hoeveel resources ze bij de hand hebben voor training en leren.
>
> Naast het productfilter worden actuele onderwerpen, typen resources (van video's tot webinars), niveaus van vertrouwdheid of ervaring met beveiligingsgebieden, beveiligingsrollen en productfuncties weergegeven.

## <a name="send-us-your-feedback"></a>Stuur ons uw feedback

We hebben uw feedback nodig. We zijn altijd op zoek naar verbetering, dus als er iets is dat u wilt zien, stuur ons dan uw [Microsoft 365 Defender-feedback.](https://www.microsoft.com/videoplayer/embed/RE4K5Ci)

U kunt ook feedback geven in dit artikel. In de sectie 'Feedback' aan het einde onder 'Feedback verzenden en weergeven voor', zijn de opties *Dit product* of *Deze pagina.*

Gebruik de **knop Dit product** voor *productfeedback:*

1. Selecteer *Dit product* onderaan het artikel.
    1. Klik met de rechtermuisknop op de knop en 'Openen in een nieuw tabblad' als u deze aanwijzingen wilt blijven lezen.
2. Hiermee navigeert u naar **het UserVoice-forum.**
3. U hebt twee opties:
    1. Schuif omlaag naar het tekstvak Hoe kunnen we de naleving verbeteren of uw gebruikers beter beschermen *in Office 365?* en plakken in *het Microsoft 365-beveiligingscentrum.* U kunt in de resultaten zoeken naar een idee zoals dat van u en het idee up-vote of de knop gebruiken voor **Een nieuw idee posten.**
    1. Als u zeker weet dat dit probleem al is gerapporteerd en het profiel wilt verhogen met een stem (of stemmen), gebruikt u het vak *Feedback* geven aan de rechterkant van UserVoice. Zoek naar *het Microsoft 365-beveiligingscentrum,* zoek het probleem en gebruik de **stemknop** om de status te verhogen.

Gebruik *Deze pagina voor* feedback over het artikel zelf. Bedankt voor uw feedback. Uw stem helpt ons producten te verbeteren.

### <a name="explore-what-the-security-center-has-to-offer"></a>Ontdek wat het beveiligingscentrum te bieden heeft

Blijf de functies en mogelijkheden in het Microsoft 365-beveiligingscentrum verkennen:

- [Incidenten en waarschuwingen beheren](manage-incidents.md)
- [Nieuwe bedreigingen bijhouden en beantwoorden met bedreigingsanalyse](threat-analytics.md)
- [Het Actiecentrum](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [Op bedreigingen zoeken op verschillende apparaten, e-mailberichten, apps en identiteiten](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-query-emails-devices)
- [Aangepaste detectieregels](https://docs.microsoft.com/microsoft-365/security/mtp/custom-detection-rules)
- [Waarschuwingen voor & e-mail](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies)
- [Maak een phishing-aanvalssimulatie](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training) [en maak een payload voor het trainen van uw teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training-payloads)
 
### <a name="related-information"></a>Gerelateerde informatie
- [Microsoft 365-beveiligingscentrum](overview-security-center.md)
- [Microsoft Defender voor Office 365 in het Microsoft 365-beveiligingscentrum](microsoft-365-security-center-mdo.md)
- [Microsoft Defender voor Eindpunt in het Microsoft 365-beveiligingscentrum](microsoft-365-security-center-mde.md)
- [Accounts omleiden van Microsoft Defender voor Eindpunt naar het Microsoft 365-beveiligingscentrum](microsoft-365-security-mde-redirection.md)
