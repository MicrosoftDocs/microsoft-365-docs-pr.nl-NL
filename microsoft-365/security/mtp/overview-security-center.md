---
title: Overzicht van Microsoft 365-beveiligingscentrum
description: 'Voordelen in het Microsoft 365-beveiligingscentrum: de combinatie van Microsoft Defender voor Office 365 (MDO) en Microsoft Defender for Endpoint (MDE) met Microsoft Defender for Identity (MDI) en Microsoft Cloud App Security (MCAS). Dit artikel bevat een overzicht van de volgende ontwikkelingen in het Microsoft 365-beveiligingscentrum voor beheerders.'
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
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 89e72d703bd70647d6c2b00732315b8e5f015cc7
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167199"
---
# <a name="the-unified-microsoft-365-security-center-overview"></a>Overzicht van het geïntegreerde Microsoft 365-beveiligingscentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Van toepassing op:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft Defender voor Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)

> Wilt u ervaring met Microsoft 365 Defender? U kunt [het evalueren in een testomgeving](https://aka.ms/mtp-trial-lab) of uw [pilotproject in productie nemen.](https://aka.ms/m365d-pilotplaybook)

In het **verbeterde Microsoft 365-beveiligingscentrum** () worden beveiliging, detectie, onderzoek en antwoorden op e-mail, samenwerking, identiteit en apparaatrisico's gecombineerd in een [https://security.microsoft.com](https://security.microsoft.com) centrale portal.   

Het Microsoft 365-beveiligingscentrum brengt functionaliteit samen van bestaande Microsoft-beveiligingsportals, zoals het Microsoft Defender-beveiligingscentrum en het Office 365-& compliancecentrum. Het beveiligingscentrum legt de nadruk op snelle toegang tot informatie, eenvoudigere indelingen en het samenbrengen van gerelateerde informatie, voor eenvoudiger gebruik. Dit centrum bevat:

- **[Microsoft Defender voor Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)** Microsoft Defender voor Office 365 helpt organisaties bij het beveiligen van hun bedrijf met een reeks functies voor preventie, detectie, onderzoek en zoeken om e-mail en Office 365-bronnen te beschermen.
- **[Microsoft Defender for Endpoint levert](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)** preventieve beveiliging, detectie na inbreuken, geautomatiseerd onderzoek en antwoorden voor apparaten in uw organisatie.
- **[Microsoft 365 Defender](microsoft-threat-protection.md)** maakt deel uit van XDR-oplossing *(Extended Detection and Response)* van Microsoft, dat gebruik maakt van de Microsoft 365-beveiligingsportfolio voor het automatisch analyseren van bedreigingsgegevens in domeinen en een afbeelding van een aanval op één dashboard bouwen.

Als u informatie nodig hebt over wat er is gewijzigd vanuit het Office 365-&-compliancecentrum of het Microsoft Defender-beveiligingscentrum, gaat u naar:

- [Defender voor Office 365 in het Microsoft 365-beveiligingscentrum](microsoft-365-security-center-mdo.md)
- [Defender voor Eindpunt in het Microsoft 365-beveiligingscentrum](microsoft-365-security-center-mde.md)

## <a name="what-to-expect"></a>Wat u kunt verwachten

Alle beveiligingsinhoud die u gebruikt in het Office 365-beveiligings- en compliancecentrum (protection.office.com) en het Microsoft Defender-beveiligingscentrum (securitycenter.microsoft.com), vindt u nu in het *Microsoft 365-beveiligingscentrum.*

Het Microsoft 365-beveiligingscentrum helpt beveiligingsteams om aanvallen te onderzoeken en hierop te reageren door de signalen van verschillende werkbelastingen binnen te nemen in één geïntegreerde ervaring:

- Incidenten & waarschuwingen
- Op zoek naar
- Actiecentrum
- Dreigingsanalyse

In het Microsoft 365-beveiligingscentrum ligt de nadruk op *eenheid,* helderheid en gemeenschappelijke doelstellingen bij het samenvoegen van Microsoft Defender voor Office 365 en Microsoft Defender voor eindpunt. De samenvoeging is gebaseerd op de hierna genoemde prioriteiten en heeft geen ten koste van de mogelijkheden die elke beveiligingssuite aan de combinatie heeft aangebracht:

- algemene bouwstenen
- algemene terminologie
- algemene entiteiten
- functiepariteit met andere werkbelastingen

## <a name="unified-investigations"></a>Geïntegreerde onderzoeken

Bij het stroomlijnen van beveiligingscentra wordt één deelvenster gemaakt voor het onderzoeken van incidenten in een Microsoft 365-organisatie. Een primair voorbeeld is het **knooppunt Incidenten** op de werkbalk Snel starten van het Microsoft 365-beveiligingscentrum.

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="De pagina Incidenten in MDO.":::

Als u bijvoorbeeld dubbelklikt op een  incidentnaam met hoge ernst, komt u op een pagina waar het voordeel van convergerende centers wordt gedemonstreerd.

![Incident met meerdere fases waarbij sprake was van escalatie van bevoegdheden op meerdere eindpunten, waarbij 16 betrokken apparaten en 9 betrokken gebruikers werden weergegeven.](../../media/converged-incident-info-3.png)

> [!TIP]
> Het tabblad **Geconvergeerde** gebruikers is een goede plaats om uw vragen te starten. Op deze ene pagina worden gegevens weergegeven voor gebruikers van geconvergeerde werkbelastingen (Microsoft Defender voor eindpunt, Microsoft Defender for Identity en MCAS, als u deze gebruikt) en een reeks bronnen, zoals on-premises Active Directory, Azure Active Directory, gesynchroniseerde, lokale en externe gebruikers. Meer informatie over [de nieuwe gebruikerservaring.](investigate-users.md)

Incidentgegevens tonen specifieke gebruikers-/identiteitsgegevens en apparaten met een risico, naast de betreffende postvakken. Het heeft ook betrekking op **onderzoeksgegevens en** het verzamelen **van bewijs.** Hierdoor kunnen beheerders en beveiligingsteams eenvoudiger één waarschuwing met hoog risico gebruiken voor de betrokken gebruikers en postvakken. Als u naar **de tabbladen incident** boven aan deze pagina kijkt, zijn er andere belangrijke beveiligingspivots beschikbaar vanaf deze locatie.

> [!IMPORTANT]
> Boven aan een pagina voor een specifiek incident ziet u de tabbladen **Samenvatting,** **Waarschuwingen,** **Apparaten,** **Gebruikers,** Postvakken, Onderzoeken en Bewijs.  

Als **u Onderzoeken selecteert,** wordt een pagina geopend met een afbeelding van de analyse die wordt uitgevoerd en wordt een status (zoals goedkeuring in **behandeling)** weergegeven voor herstel. Neem de tijd om specifieke incidenten in uw omgeving te selecteren, in te zoomen op deze tabbladen en te oefenen met het maken van een profiel voor verschillende soorten bedreigingen. U kunt later bij nader onderzoek meer vertrouwd raken met het gebruik van vertrouwde informatie.

## <a name="improved-processes"></a>Verbeterde processen

Algemene besturingselementen en inhoud worden op dezelfde plaats weergegeven of zijn ingedekt in één gegevensfeed, zodat u deze gemakkelijker kunt vinden. Bijvoorbeeld geïntegreerde instellingen.

### <a name="unified-settings"></a>Geïntegreerde instellingen

![geklikt op Rollen en de pagina Instellingen geopend, die algemene instellingen, machtigingen, API's en regels bevat. Open Machtigingen en vervolgens Rollen. Toont alle rollen](../../media/converged-add-role-9.png)

### <a name="permissions--roles"></a>Machtigingen & rollen

![Machtigingen & pagina Rollen met de rollen van eindpunten & groepen, rollen en apparaatgroepen.](../../media/converged-roles-5.png)

 Toegang tot het Microsoft 365-beveiligingscentrum is geconfigureerd met globale azure Active Directory-rollen of met aangepaste rollen. Zie Gebruikerstoegang toewijzen aan het [Microsoft Defender-beveiligingscentrum](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/assign-portal-access)voor Defender voor eindpunt. Zie Machtigingen in het [Microsoft 365-compliancecentrum en het Microsoft 365-beveiligingscentrum voor Defender voor Office 365.](../office-365-security/permissions-microsoft-365-compliance-security.md)

- Meer informatie over het beheren [van de toegang tot Microsoft 365 Defender](mtp-permissions.md)
- Meer informatie over het maken [van aangepaste rollen](custom-roles.md) in het Microsoft 365-beveiligingscentrum

### <a name="integrated-reports"></a>Geïntegreerde rapporten

Rapporten worden ook geïntegreerd in het Microsoft 365-beveiligingscentrum. Beheerders kunnen beginnen met een algemeen beveiligingsrapport en zich vertakken in specifieke rapporten over eindpunten, e-mail & samenwerking. De koppelingen hier worden dynamisch gegenereerd op basis van de werkbelastingsconfiguratie.

### <a name="quickly-view-your-microsoft-365-environment"></a>Snel uw Microsoft 365-omgeving weergeven

Op **de startpagina** ziet u veel van de veelvoorkomende kaarten die beveiligingsteams nodig hebben. De samenstelling van kaarten en gegevens is afhankelijk van de gebruikersrol. Omdat het Microsoft 365-beveiligingscentrum toegangsbeheer op basis van rollen gebruikt, zien verschillende rollen kaarten die meer betekenis hebben voor hun dagelijkse werkzaamheden.  

Deze informatie in één oogopslag helpt u op de hoogte te blijven van de meest recente activiteiten in uw organisatie. Het Microsoft 365-beveiligingscentrum brengt signalen uit verschillende bronnen samen om een gebouwde weergave van uw Microsoft 365-omgeving te presenteren.

De kaarten vallen in deze categorieën:

- **Identiteiten:** houd de identiteiten in uw organisatie in de gaten en houd verdacht of riskant gedrag bij. [Meer informatie over identiteitsbeveiliging.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)
- **Gegevens:** helpt bij het bijhouden van gebruikersactiviteiten die kunnen leiden tot ongeautoriseerde openbaarmaking van gegevens.
- **Apparaten:** actuele informatie over waarschuwingen, inbreukactiviteiten en andere bedreigingen op uw apparaten.
- **Apps:** krijg inzicht in hoe cloud-apps worden gebruikt in uw organisatie. [Meer informatie over apps die door Cloud-app-beveiliging zijn gevonden.](https://docs.microsoft.com/cloud-app-security/discovered-apps)

## <a name="threat-analytics-with-better-data-coverage"></a>Bedreigingsanalyse met betere dekking van gegevens
Volg en reageer op nieuwe bedreigingen met de volgende geïntegreerde Microsoft 365 Defender Threat Analytics-ervaring:

- Betere gegevensdekking tussen Microsoft Defender voor Eindpunt en Microsoft Defender voor Office 365, waardoor gecombineerd beheer van incidenten, automatisch onderzoek, herstel en proactieve of reactief zoeken naar een heel domein mogelijk wordt. 
- Aan e-mail gerelateerde detecties en risicobeperking van Microsoft Defender voor Office 365, naast de eindpuntgegevens die al beschikbaar zijn van Microsoft Defender voor Eindpunt.
- Een weergave van risicogerelateerde incidenten die waarschuwingen samenvoegen in end-to-end-aanvalsverhalen over Microsoft Defender for Endpoint en Microsoft Defender voor Office 365 om de werkwachtrij te beperken en het onderzoek te vereenvoudigen en te versnellen.
- Aanvalspogingen gedetecteerd en geblokkeerd door Microsoft 365 Defender-oplossingen. Er zijn ook gegevens die u kunt gebruiken om voorzorgsacties aan te brengen die het risico op verdere blootstelling beperken en de tolerantie verhogen. 
- Verbeterd ontwerp dat actie-informatie onder de aandacht brengt om u te helpen snel gegevens te identificeren zodat u zich dringend kunt richten op, onderzoeken en gebruikmaken van de rapporten.

## <a name="a-centralized-learning-hub"></a>Een centrale leerhub

Het Microsoft 365-beveiligingscentrum bevat een leerhub die officiële richtlijnen optelt uit bronnen zoals de Microsoft-beveiligingsblog, de Microsoft-beveiligingscommunity op YouTube en de officiële documentatie op docs.microsoft.com.

In de leerhub worden richtlijnen voor samenwerking via e-mail & (Microsoft Defender voor Office 365 of MDO) naast eindpunten (Microsoft Defender voor eindpunt of MDE) en Microsoft 365 Defender-leerbronnen naast elkaar.

De onderwijshub wordt geopend met leerpaden rond onderwerpen zoals 'Hoe onderzoek doen met Microsoft 365 Defender?' en 'Best practices voor Microsoft Defender voor Office 365'. Dit gedeelte wordt momenteel samengesteld door de beveiligingsproductgroep binnen Microsoft. Elk leerpad weerspiegelt een geprojecteerde tijd die het kost om de concepten te door te nemen. Voorbeeld: 'Stappen die moeten worden ondernomen wanneer een Microsoft Defender voor Office 365-gebruikersaccount wordt gehackt', duurt naar project 8 minuten en is op dit moment zeer waardevol om te leren.

Nadat u naar de inhoud hebt geklikt, kan het handig zijn om een bladwijzer aan deze site toe te staan en bladwijzers te ordenen in de map Beveiliging of Kritiek. Als u alle leerpaden wilt zien, klikt u op de koppeling Alles tonen in het hoofdvenster.

> [!NOTE]
> Bovenaan de Microsoft 365-beveiligingscentrum-hub voor het leren zijn handige **filters** beschikbaar, zodat u kunt kiezen tussen producten (momenteel Microsoft 365 Defender, Microsoft Defender voor eindpunt en Microsoft Defender voor Office 365). U ziet dat het aantal leerbronnen voor elke sectie wordt weergegeven, zodat studenten kunnen bijhouden hoeveel trainings- en studiebronnen er beschikbaar zijn.
>
> Naast het productfilter worden de huidige onderwerpen, informatietypen (van video's tot webinars), het niveau van vertrouwdheid of ervaring met beveiligingsgebieden, beveiligingsrollen en productfuncties weergegeven.

## <a name="send-us-your-feedback"></a>Stuur ons uw feedback

We hebben uw feedback nodig. We zijn altijd op zoek naar verbetering, dus als u iets wilt zien, stuur ons dan [uw Microsoft 365 Defender-feedback.](https://www.microsoft.com/videoplayer/embed/RE4K5Ci)

U kunt ook feedback geven vanuit dit artikel. In de sectie Feedback aan het einde onder 'Verzenden en feedback bekijken voor', zijn de opties *Dit product* of *Deze pagina.*

Gebruik de **knop Dit product** voor *productfeedback:*

1. Selecteer *Dit product* onder aan het artikel.
    1. Klik met de rechtermuisknop op de knop en 'Open in een nieuw tabblad' als u deze aanwijzingen wilt lezen.
2. Hiermee navigeert u naar het **UserVoice-forum.**
3. U hebt twee opties:
    1. Schuif omlaag naar het tekstvak Hoe kunnen we de naleving verbeteren of uw gebruikers beter beschermen *in Office 365?* en plakken in *het Microsoft 365-beveiligingscentrum.* U kunt in de resultaten zoeken naar een idee zoals dat van u en dit up-voten, of de knop gebruiken om een **nieuw idee te posten.**
    1. Als u zeker weet dat dit probleem al is gerapporteerd en u het profiel wilt verhogen met een stem (of stemmen), gebruikt u het vak *Feedback* geven aan de rechterkant van UserVoice. Zoek naar *het Microsoft 365-beveiligingscentrum,* zoek het probleem en gebruik de stemknop om **de** status te verhogen.

Gebruik *Deze pagina voor* feedback over het artikel zelf. Bedankt voor uw feedback. Uw stem helpt ons producten te verbeteren.

### <a name="explore-what-the-security-center-has-to-offer"></a>Ontdek wat het beveiligingscentrum te bieden heeft

Blijf de functies en mogelijkheden verkennen in het Microsoft 365-beveiligingscentrum:

- [Incidenten en waarschuwingen beheren](manage-incidents.md)
- [Nieuwe bedreigingen volgen en hierop reageren met bedreigingsanalyse](threat-analytics.md)
- [Het Actiecentrum](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [Zoeken naar bedreigingen op apparaten, e-mailberichten, apps en identiteiten](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-query-emails-devices)
- [Aangepaste detectieregels](https://docs.microsoft.com/microsoft-365/security/mtp/custom-detection-rules)
- [Waarschuwingen voor & e-mail verzenden](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies)
- [Maak een phishing-aanvalsinerulatie](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training) [en maak een nettolading voor het trainen van uw teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training-payloads)
 
### <a name="related-information"></a>Gerelateerde informatie
- [Microsoft 365-beveiligingscentrum](overview-security-center.md)
- [Microsoft Defender voor Office 365 in het Microsoft 365-beveiligingscentrum](microsoft-365-security-center-mdo.md)
- [Microsoft Defender voor eindpunt in het Microsoft 365-beveiligingscentrum](microsoft-365-security-center-mde.md)
- [Accounts van Microsoft Defender voor eindpunt omleiden naar het Microsoft 365-beveiligingscentrum](microsoft-365-security-mde-redirection.md)
