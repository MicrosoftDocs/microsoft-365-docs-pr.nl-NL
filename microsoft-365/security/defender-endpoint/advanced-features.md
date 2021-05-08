---
title: Geavanceerde functies configureren in Microsoft Defender voor Eindpunt
description: Schakel geavanceerde functies in, zoals blokbestand in Microsoft Defender voor Eindpunt.
keywords: geavanceerde functies, instellingen, blokbestand, geautomatiseerd onderzoek, automatisch oplossen, skype, microsoft defender voor identiteit, office 365, azure information protection, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 87305f28975b8997afce211ffa4de3711d26be6b
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246366"
---
# <a name="configure-advanced-features-in-defender-for-endpoint"></a>Geavanceerde functies configureren in Defender voor Eindpunt

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedfeats-abovefoldlink)

Afhankelijk van de Microsoft-beveiligingsproducten die u gebruikt, zijn er mogelijk enkele geavanceerde functies beschikbaar voor u om Defender voor Eindpunt te integreren.

## <a name="enable-advanced-features"></a>Geavanceerde functies inschakelen

1. Selecteer in het navigatiedeelvenster **Voorkeuren instellen**  >  **Geavanceerde functies.**
2. Selecteer de geavanceerde functie die u wilt configureren en schakel de instelling in tussen **Aan** en **Uit.**
3. Klik **op Voorkeuren opslaan.**

Gebruik de volgende geavanceerde functies om beter te worden beschermd tegen potentieel schadelijke bestanden en om beter inzicht te krijgen tijdens beveiligingsonderzoeken.

## <a name="automated-investigation"></a>Geautomatiseerd onderzoek

Schakel deze functie in om te profiteren van de geautomatiseerde onderzoeks- en herstelfuncties van de service. Zie Geautomatiseerd onderzoek [voor meer informatie.](automated-investigations.md)

## <a name="live-response"></a>Live-antwoord

Schakel deze functie in, zodat gebruikers met de juiste machtigingen een livereactiesessie op apparaten kunnen starten.

Zie Rollen maken en beheren voor meer informatie over [roltoewijzingen.](user-roles.md)

## <a name="live-response-for-servers"></a>Livereactie voor servers
Schakel deze functie in, zodat gebruikers met de juiste machtigingen een livereactiesessie op servers kunnen starten.

Zie Rollen maken en beheren voor meer informatie over [roltoewijzingen.](user-roles.md)


## <a name="live-response-unsigned-script-execution"></a>Uitvoering van niet-ondertekende scripts met livereactie

Als u deze functie inschakelen, kunt u niet-ondertekende scripts uitvoeren in een livereactiesessie.

## <a name="always-remediate-pua"></a>PuA altijd herstellen
Potentieel ongewenste toepassingen (PUA) zijn een categorie software waarmee uw computer traag kan worden uitgevoerd, onverwachte advertenties kan weergeven of in het slechtste geval andere software kan installeren die onverwacht of ongewenst kan zijn. 

Schakel deze functie in, zodat mogelijk ongewenste toepassingen (PUA) worden gesaneerd op alle apparaten in uw tenant, zelfs als PUA-beveiliging niet is geconfigureerd op de apparaten. Dit helpt gebruikers te beschermen tegen het onbedoeld installeren van ongewenste toepassingen op hun apparaat. Wanneer deze is uitgeschakeld, is herstel afhankelijk van de apparaatconfiguratie. 


## <a name="restrict-correlation-to-within-scoped-device-groups"></a>Correlatie beperken tot binnen bereik van apparaatgroepen
Deze configuratie kan worden gebruikt voor scenario's waarin lokale soc-bewerkingen de correlaties van waarschuwingen alleen willen beperken tot apparaatgroepen die ze kunnen openen. Door deze instelling in te stellen, wordt een incident dat bestaat uit waarschuwingen die verschillende apparaatgroepen zijn, niet langer als één incident beschouwd. De lokale soc kan dan actie ondernemen op het incident omdat ze toegang hebben tot een van de betrokken apparaatgroepen. Globale SOC ziet echter verschillende incidenten per apparaatgroep in plaats van één incident. U wordt niet aangeraden deze instelling in te stellen, tenzij dit de voordelen van incidentcorrelatie in de hele organisatie opweegt
>[!NOTE]
>Het wijzigen van deze instelling heeft alleen gevolgen voor toekomstige waarschuwingscorrelatie.

## <a name="enable-edr-in-block-mode"></a>De EDR in de blokmodus inschakelen
Eindpuntdetectie en -antwoord (EDR) in de blokmodus biedt bescherming tegen schadelijke artefacten, zelfs wanneer Microsoft Defender Antivirus actief is in de passieve modus. Wanneer deze functie is ingeschakeld, EDR in de blokmodus schadelijke artefacten of gedragingen die op een apparaat worden gedetecteerd, geblokkeerd. EDR in de blokmodus werkt achter de schermen om schadelijke artefacten te corrigeren die na een inbreuk worden gedetecteerd.


## <a name="autoresolve-remediated-alerts"></a>Autoresolve remediated alerts

Voor tenants die zijn gemaakt op of na Windows 10, versie 1809, is de mogelijkheid voor automatisch onderzoek en herstel standaard geconfigureerd om waarschuwingen op te lossen waarbij de status van het geautomatiseerde analyseresultaat 'Geen bedreigingen gevonden' of 'Herstel' is.  Als u waarschuwingen niet automatisch wilt laten oplossen, moet u de functie handmatig uitschakelen.

> [!TIP]
> Voor tenants die vóór die versie zijn gemaakt, moet u deze functie handmatig inschakelen vanaf de [pagina Geavanceerde functies.](https://securitycenter.windows.com/preferences2/integration)

> [!NOTE]
>
> - Het resultaat van de actie voor automatisch oplossen kan van invloed zijn op de berekening van het apparaatrisiconiveau, die is gebaseerd op de actieve waarschuwingen die op een apparaat zijn gevonden.
> - Als een beveiligingsanalist de status van een waarschuwing handmatig in stelt op 'Aan de gang' of 'Opgelost', wordt de functie voor automatisch oplossen niet overschreven.

## <a name="allow-or-block-file"></a>Bestand toestaan of blokkeren

Blokkeren is alleen beschikbaar als uw organisatie aan deze vereisten voldoet:

- Gebruikt Microsoft Defender Antivirus als de actieve antimalwareoplossing en,
- De cloudbeveiligingsfunctie is ingeschakeld

Met deze functie kunt u potentieel schadelijke bestanden in uw netwerk blokkeren. Als u een bestand blokkeert, wordt dit niet gelezen, geschreven of uitgevoerd op apparaten in uw organisatie.

Bestanden **toestaan of blokkeren** in- of in- of uit te stellen:

1. Selecteer in het navigatiedeelvenster **Instellingen** Geavanceerde functies Bestand toestaan  >    >  **of blokkeren.**

1. Schakel de instelling in tussen **Aan** en **Uit.**

    ![Afbeelding van geavanceerde instellingen voor blokbestandsfunctie](images/atp-preferences-setup.png)

1. Selecteer **Voorkeuren opslaan** onder aan de pagina.

Nadat u deze functie hebt ingeslagen, kunt u bestanden [blokkeren](respond-file-alerts.md#allow-or-block-file) via het tabblad **Indicator** toevoegen op de profielpagina van een bestand.

## <a name="custom-network-indicators"></a>Aangepaste netwerkindicatoren

Met deze functie kunt u indicatoren maken voor IP-adressen, domeinen of URL's, die bepalen of deze worden toegestaan of geblokkeerd op basis van uw aangepaste indicatorlijst.

Als u deze functie wilt gebruiken, moeten apparaten worden uitgevoerd Windows 10 versie 1709 of hoger. Ze moeten ook netwerkbeveiliging hebben in de blokmodus en versie 4.18.1906.3 of hoger van het antimalware-platform [zie KB 4052623](https://go.microsoft.com/fwlink/?linkid=2099834).

Zie Indicatoren beheren voor meer [informatie.](manage-indicators.md)

> [!NOTE]
> Netwerkbeveiliging maakt gebruik van reputatieservices die aanvragen verwerken op locaties die zich mogelijk buiten de locatie bevinden die u hebt geselecteerd voor uw Defender voor eindpuntgegevens.

## <a name="tamper-protection"></a>Beveiliging van tamper
Tijdens sommige soorten cyberaanvallen proberen slechte spelers beveiligingsfuncties, zoals antivirusbeveiliging, uit te schakelen op uw machines. Slechte spelers willen uw beveiligingsfuncties uitschakelen om gemakkelijker toegang te krijgen tot uw gegevens, om malware te installeren of om op een andere manier uw gegevens, identiteit en apparaten te misbruiken.

Met tamperbeveiliging worden Microsoft Defender Antivirus en voorkomt u dat uw beveiligingsinstellingen worden gewijzigd via apps en methoden.

Deze functie is beschikbaar als uw organisatie gebruikmaakt van Microsoft Defender Antivirus cloudbeveiliging is ingeschakeld. Zie Technologieën van de volgende generatie gebruiken in Microsoft Defender Antivirus beveiliging in de cloud voor [meer informatie.](cloud-protection-microsoft-defender-antivirus.md)

Houd de beveiliging van de tamper ingeschakeld om ongewenste wijzigingen in uw beveiligingsoplossing en de essentiële functies te voorkomen.


## <a name="show-user-details"></a>Gebruikersgegevens tonen

Schakel deze functie in, zodat u de gebruikersgegevens kunt zien die zijn opgeslagen in Azure Active Directory. Details zijn onder andere de afbeelding, naam, titel en afdelingsgegevens van een gebruiker bij het onderzoeken van entiteiten van gebruikersaccounts. U kunt gebruikersaccountgegevens vinden in de volgende weergaven:

- Dashboard beveiligingsbewerkingen
- Waarschuwingswachtrij
- Pagina Apparaatdetails

Zie Een gebruikersaccount [onderzoeken voor meer informatie.](investigate-user.md)


## <a name="skype-for-business-integration"></a>Skype voor Bedrijven integratie

Als u de Skype voor Bedrijven inschakelen, kunt u communiceren met gebruikers via Skype voor Bedrijven, e-mail of telefoon. Dit kan handig zijn als u wilt communiceren met de gebruiker en risico's wilt beperken.

> [!NOTE]
> Wanneer een apparaat wordt geïsoleerd van het netwerk, is er een pop-up waar u ervoor kunt kiezen om Outlook- en Skype-communicatie in te stellen, zodat communicatie met de gebruiker kan worden gedaan terwijl deze verbinding met het netwerk is verbroken. Deze instelling is van toepassing op Skype en Outlook communicatie wanneer apparaten in de isolatiemodus staan.

## <a name="microsoft-defender-for-identity-integration"></a>Microsoft Defender voor identiteitsintegratie

Met de integratie met Microsoft Defender voor identiteit kunt u rechtstreeks naar een ander beveiligingsproduct van Microsoft Identity draaien. Microsoft Defender voor identiteit vergroot een onderzoek met aanvullende inzichten over een verdacht gekromd account en gerelateerde bronnen. Door deze functie in te stellen, verrijkt u de apparaatgebaseerde onderzoeksfunctie door vanuit een identificeerpunt over het netwerk te draaien.

> [!NOTE]
> U moet over de juiste licentie beschikken om deze functie in te stellen.

## <a name="office-365-threat-intelligence-connection"></a>Office 365 Threat Intelligence-verbinding

Deze functie is alleen beschikbaar als u een actieve Office 365 E5 of de threat intelligence-invoeging hebt. Zie de productpagina Office 365 Enterprise E5 voor meer informatie.

Wanneer u deze functie in gebruik neemt, kunt u gegevens van Microsoft Defender voor Office 365 opnemen in Microsoft Defender-beveiligingscentrum om een uitgebreid beveiligingsonderzoek uit te voeren op Office 365 postvakken en Windows apparaten.

> [!NOTE]
> U moet over de juiste licentie beschikken om deze functie in te stellen.

Als u contextuele apparaatintegratie wilt ontvangen in Office 365 Threat Intelligence, moet u de instellingen van Defender voor Eindpunt inschakelen in het dashboard & Compliance. Zie Bedreigingsonderzoek [en -antwoord voor meer informatie.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-ti)

## <a name="microsoft-threat-experts---targeted-attack-notifications"></a>Microsoft Threat Experts - Meldingen van gerichte aanvallen

Van de twee Microsoft Threat Expert-onderdelen is een gerichte aanvalsmelding algemeen beschikbaar. Experts-on-demand-mogelijkheden zijn nog steeds beschikbaar in de preview-versie. U kunt de mogelijkheid van experts op aanvraag alleen gebruiken als u een preview-aanvraag hebt ingediend en uw toepassing is goedgekeurd. U kunt gerichte aanvalsmeldingen ontvangen van Microsoft Threat Experts via het dashboard waarschuwingen van de Defender for Endpoint-portal en via e-mail als u deze configureert.

> [!NOTE]
> De Microsoft Threat Experts in Defender voor Eindpunt is beschikbaar met een E5-licentie voor [Enterprise Mobility + Security.](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
## <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security

Als u deze instelling inschakelen, worden defender-voor-eindpunt-signalen Microsoft Cloud App Security om meer inzicht te krijgen in het gebruik van cloudtoepassing. Doorgestuurde gegevens worden opgeslagen en verwerkt op dezelfde locatie als uw Cloud App Security gegevens.

> [!NOTE]
> Deze functie is beschikbaar met een E5-licentie voor [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) op apparaten met Windows 10, versie 1709 (os build 16299.1085 met [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, versie 1803 (os build 17134.704 met [KB4493464),](https://support.microsoft.com/help/4493464)Windows 10, versie 1809 (os build 17763.379 met [KB4489899),](https://support.microsoft.com/help/4489899)of later Windows 10 versies.

## <a name="microsoft-secure-score"></a>Microsoft Secure Score

Doorgestuurde Microsoft Defender voor Eindpunt-signalen naar Microsoft Secure Score in het Microsoft 365 beveiligingscentrum. Door deze functie in te stellen, krijgt Microsoft Secure Score inzicht in de beveiligingsstatus van het apparaat. Doorgestuurde gegevens worden opgeslagen en verwerkt op dezelfde locatie als uw Microsoft Secure Score-gegevens.


### <a name="enable-the-microsoft-defender-for-endpoint-integration-from-the-microsoft-defender-for-identity-portal"></a>De integratie van Microsoft Defender voor eindpunten inschakelen vanuit de Microsoft Defender voor identiteitsportal

Als u contextuele apparaatintegratie wilt ontvangen in Microsoft Defender voor identiteit, moet u de functie ook inschakelen in de Microsoft Defender for Identity-portal.

1. Meld u aan bij de [Microsoft Defender for Identity-portal](https://portal.atp.azure.com/) met een rol voor globale beheerder of beveiligingsbeheerder.

2. Klik **op Uw exemplaar maken.**

3. Schakel de instelling Integratie in op **Aan** en klik op **Opslaan.**

Nadat u de integratiestappen voor beide portals hebt doorlopen, kunt u relevante waarschuwingen zien op de pagina apparaatdetails of gebruikersgegevens.

## <a name="web-content-filtering"></a>Filteren van webinhoud
Blokkeer de toegang tot websites die ongewenste inhoud bevatten en volg webactiviteit in alle domeinen. Als u de categorieën met webinhoud wilt opgeven die u wilt blokkeren, maakt u een [filterbeleid voor webinhoud.](https://security.microsoft.com/preferences2/web_content_filtering_policy) Zorg ervoor dat u netwerkbeveiliging hebt in de blokmodus bij het implementeren van de [beveiligingslijn van Microsoft Defender voor Eindpunt.](https://devicemanagement.microsoft.com/#blade/Microsoft_Intune_Workflows/SecurityBaselineSummaryMenu/overview/templateType/2)


## <a name="share-endpoint-alerts-with-microsoft-compliance-center"></a>Eindpuntwaarschuwingen delen met Microsoft Compliance Center
Doorgestuurde beveiligingswaarschuwingen voor eindpunten en hun triagestatus naar Microsoft Compliance Center, zodat u het beleid voor insiderrisicobeheer kunt verbeteren met waarschuwingen en interne risico's kunt corrigeren voordat deze schade veroorzaken. Doorgestuurde gegevens worden verwerkt en opgeslagen op dezelfde locatie als uw Office 365 gegevens.

Nadat u [](/microsoft-365/compliance/insider-risk-management-settings#indicators) de indicatoren voor beveiligingsbeleidsovertreding hebt geconfigureerd in de instellingen voor insiderrisicobeheer, worden defender voor eindpuntwaarschuwingen gedeeld met insiderrisicobeheer voor toepasselijke gebruikers.



## <a name="microsoft-intune-connection"></a>Microsoft Intune verbinding

Defender for Endpoint kan worden geïntegreerd [met](https://docs.microsoft.com/intune/what-is-intune) Microsoft Intune om voorwaardelijke toegang op basis van [apparaatrisico's in te stellen.](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune) Wanneer u [deze functie in gebruikt,](configure-conditional-access.md)kunt u de apparaatgegevens van Defender voor eindpunt delen met Intune, waardoor de handhaving van het beleid wordt vergroot.

> [!IMPORTANT]
> U moet de integratie van zowel Intune als Defender voor Endpoint inschakelen om deze functie te kunnen gebruiken. Zie Voorwaardelijke toegang [configureren in Defender voor eindpunt](configure-conditional-access.md)voor meer informatie over specifieke stappen.

Deze functie is alleen beschikbaar als u het volgende hebt:

- Een licentie tenant voor Enterprise Mobility + Security E3 en Windows E5 (of Microsoft 365 Enterprise E5)
- Een actieve Microsoft Intune omgeving, met intune beheerde Windows 10 [Azure AD-joined](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join/).


### <a name="conditional-access-policy"></a>Beleid voor voorwaardelijke toegang

Wanneer u Intune-integratie inschakelen, wordt in Intune automatisch een klassiek CA-beleid (Conditional Access) aan het maken. Dit klassieke CA-beleid is een vereiste voor het instellen van statusrapporten op Intune. Het moet niet worden verwijderd.

> [!NOTE]
> Het klassieke CA-beleid dat door Intune is gemaakt, verschilt van het moderne beleid voor Voorwaardelijke [toegang,](https://docs.microsoft.com/azure/active-directory/conditional-access/overview/)dat wordt gebruikt voor het configureren van eindpunten.


## <a name="device-discovery"></a>Apparaatdetectie
Helpt u bij het vinden van niet-beheerbare apparaten die zijn verbonden met uw bedrijfsnetwerk zonder dat u extra apparaten of lastige proceswijzigingen nodig hebt. Met onboarded-apparaten kunt u onaangemande apparaten in uw netwerk vinden en beveiligingslekken en risico's beoordelen. Zie Apparaatdetectie voor [meer informatie.](device-discovery.md)

> [!NOTE]
> U kunt altijd filters toepassen om niet-beheerde apparaten uit de lijst met apparaatvoorraad uit te sluiten. U kunt ook de kolom onboardingstatus op API-query's gebruiken om niet-gebouwde apparaten te filteren. 

## <a name="preview-features"></a>Preview-functies

Meer informatie over nieuwe functies in de preview-release van Defender voor Eindpunt. Probeer aanstaande functies door de preview-ervaring in te- of uitschakelen.

U hebt toegang tot toekomstige functies, waarop u feedback kunt geven om de algehele ervaring te verbeteren voordat functies algemeen beschikbaar zijn.




## <a name="related-topics"></a>Verwante onderwerpen

- [Instellingen voor gegevensretentie bijwerken](data-retention-settings.md)
- [Waarschuwingsmeldingen configureren](configure-email-notifications.md)
