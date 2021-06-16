---
title: Microsoft Defender voorbereiden op de implementatie van eindpunten
description: Goedkeuring van belanghebbenden, tijdlijnen, milieuoverwegingen en acceptatieorder voorbereiden voor de implementatie van Microsoft Defender voor Eindpunt
keywords: implementeren, voorbereiden, belanghebbenden, tijdlijn, omgeving, eindpunt, server, beheer, acceptatie
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
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 7841197594941354b21bd2104cd27ef37a1a25c9
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/16/2021
ms.locfileid: "52964594"
---
# <a name="prepare-microsoft-defender-for-endpoint-deployment"></a>Microsoft Defender voorbereiden op de implementatie van eindpunten

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Het implementeren van Defender voor Eindpunt is een proces in drie fasen:

| ![implementatiefase - voorbereiden](images/phase-diagrams/prepare.png)<br>Fase 1: Voorbereiden | [![implementatiefase - installatie](images/phase-diagrams/setup.png)](production-deployment.md)<br>[Fase 2: Instellen](production-deployment.md) | [![implementatiefase - onboard](images/phase-diagrams/onboard.png)](onboarding.md)<br>[Fase 3: Onboarden](onboarding.md) |
| ----- | ----- | ----- |
|*U bent er!* | ||


U bent momenteel bezig met de voorbereidingsfase.


Voorbereiding is essentieel voor een geslaagde implementatie. In dit artikel wordt u begeleid over de punten die u moet overwegen terwijl u zich voorbereidt op het implementeren van Defender voor Eindpunt.


## <a name="stakeholders-and-approval"></a>Belanghebbenden en goedkeuring
In de volgende sectie kunt u alle belanghebbenden identificeren die betrokken zijn bij het project en moeten ze goedkeuren, controleren of op de hoogte blijven.

Voeg belanghebbenden toe aan de onderstaande tabel voor uw organisatie.

-   SO = Project goedkeuren

-   R = Controleer dit project en geef input

-   I = Op de hoogte van dit project

| Naam                 | Rol                                                                                                                                                                                                          | Actie |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| Naam en e-mail invoeren | **CiSO (Chief Information Security Officer)** Een uitvoerend vertegenwoordiger die fungeert als sponsor binnen de *organisatie voor de implementatie van nieuwe technologie.*                                                  | SO     |
| Naam en e-mail invoeren | **Hoofd van het Cyber Defense Operations Center (CDOC) Een** vertegenwoordiger van het *CDOC-team* dat verantwoordelijk is voor het definiëren van de manier waarop deze wijziging wordt afgestemd op de processen in het beveiligingsteam van klanten.       | SO     |
| Naam en e-mail invoeren | **Beveiligingsarchitect** Een vertegenwoordiger van het beveiligingsteam die verantwoordelijk is voor het definiëren van de manier waarop deze wijziging wordt uitgelijnd met de *belangrijkste beveiligingsarchitectuur in de organisatie.*                         | R      |
| Naam en e-mail invoeren | **Werkplekarchitect** *Een vertegenwoordiger van het IT-team* die verantwoordelijk is voor het definiëren van de manier waarop deze wijziging wordt afgestemd op de basisarchitectuur van de werkplek in de organisatie.                             | R      |
| Naam en e-mail invoeren | **Beveiligingsanalist** Een vertegenwoordiger van het CDOC-team die input kan leveren over de detectiemogelijkheden, gebruikerservaring en het algemene nut van deze wijziging vanuit het perspectief van *beveiligingsbewerkingen.* | I      |


## <a name="environment"></a>Omgeving 


Deze sectie wordt gebruikt om ervoor te zorgen dat uw omgeving goed wordt begrepen door de belanghebbenden, zodat mogelijke afhankelijkheden en/of wijzigingen in technologieën of processen kunnen worden identificeren.

| Wat                                  | Beschrijving |
|---------------------------------------|-------------|
| Aantal eindpunten                        |    Totaal aantal eindpunten per besturingssysteem.         |
| Aantal servers                          |    Totaal aantal servers per versie van het besturingssysteem.    |
| Beheer-engine                     |    Naam en versie van de beheer-engine (bijvoorbeeld System Center Configuration Manager Current Branch 1803).         |
| CDOC-verdeling                     |    CDOC-structuur op hoog niveau (bijvoorbeeld Laag 1 uitbesteed aan Contoso, Tier 2 en Tier 3 in-house verspreid over Europa en Azië).         |
| Beveiligingsgegevens en -gebeurtenis (SIEM) |    SIEM-technologie in gebruik.         |


## <a name="role-based-access-control"></a>Toegangsbeheer op basis van rollen

Microsoft raadt aan het concept van de minste bevoegdheden te gebruiken. Defender voor Eindpunt maakt gebruik van ingebouwde rollen binnen Azure Active Directory. Microsoft raadt [aan de verschillende beschikbare rollen](/azure/active-directory/active-directory-assign-admin-roles-azure-portal) te bekijken en de juiste te kiezen om aan uw behoeften voor elke persona voor deze toepassing te voldoen. Sommige rollen moeten mogelijk tijdelijk worden toegepast en worden verwijderd nadat de implementatie is voltooid.

| Persona's                     | Rollen | Azure AD-rol (indien nodig) | Toewijzen aan |
|------------------------------|-------|-----------------------------|-----------|
| Beveiligingsbeheerder       |       |                             |           |
| Beveiligingsanalist             |       |                             |           |
| Eindpuntbeheerder       |       |                             |           |
| Infrastructuurbeheerder |       |                             |           |
| Bedrijfseigenaar/belanghebbende   |       |                             |           |

Microsoft raadt [gebruikers](/azure/active-directory/active-directory-privileged-identity-management-configure) aan Privileged Identity Management te gebruiken om uw rollen te beheren voor extra controle, controle en toegangscontrole voor gebruikers met adreslijstmachtigingen.

Defender voor Eindpunt ondersteunt twee manieren om machtigingen te beheren:

-   **Beheer van basismachtigingen:** Machtigingen instellen voor volledige toegang of alleen-lezen. In het geval van basismachtigingen hebben beheergebruikers met de rol globale beheerder of beveiligingsbeheerder in Azure Active Directory volledige toegang, terwijl de rol van de beveiligingslezer alleen-lezen toegang heeft.

-   **RBAC (Role-based Access Control)**: Stel granulaire machtigingen in door rollen te definiëren, Gebruikersgroepen van Azure AD toe te wijzen aan de rollen en gebruikersgroepen toegang te verlenen tot apparaatgroepen. Voor meer informatie. zie [Portaltoegang beheren met behulp van op rollen gebaseerd toegangsbeheer.](rbac.md)

Microsoft raadt aan gebruik te maken van RBAC om ervoor te zorgen dat alleen gebruikers met een zakelijke rechtvaardiging toegang hebben tot Defender voor Eindpunt.

U vindt hier meer informatie over machtigingsrichtlijnen: Rollen maken en de rol toewijzen aan [een Azure Active Directory groep.](/microsoft-365/security/defender-endpoint/user-roles#create-roles-and-assign-the-role-to-an-azure-active-directory-group)

In de volgende voorbeeldtabel wordt de structuur van het Cyber Defense Operations Center in uw omgeving bepaald, zodat u de RBAC-structuur kunt bepalen die nodig is voor uw omgeving.

| Laag   | Beschrijving                                                                                                                                                                                                 | Machtiging Vereist |
|--------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
| Laag 1 | **Team voor lokale beveiligingsbewerkingen / IT-team**<br>Dit team triages and investigates alerts contained within their geocation and escalates to Tier 2 in cases where a active remediation is required.                                              |                     |
| Laag 2 | **Team voor regionale beveiligingsbewerkingen**<br>Dit team kan alle apparaten voor hun regio zien en herstelacties uitvoeren.                                                                                                                        |        Gegevens weergeven               |
| Laag 3 | **Team voor globale beveiligingsbewerkingen**<br>Dit team bestaat uit beveiligingsexperts en is gemachtigd om alle acties vanuit de portal te bekijken en uit te voeren. | Gegevens weergeven <br>  Signaleringsonderzoek Actieve herstelacties <br> Signaleringsonderzoek Actieve herstelacties <br> Portalsysteeminstellingen beheren <br> Beveiligingsinstellingen beheren |



## <a name="adoption-order"></a>Acceptatieorder
In veel gevallen hebben organisaties bestaande eindpuntbeveiligingsproducten. Het absolute minimum dat elke organisatie had moeten hebben, had een antivirusoplossing moeten zijn. Maar in sommige gevallen heeft een organisatie mogelijk al een EDR geïmplanteerd.

In het verleden was het vervangen van een beveiligingsoplossing tijdsintensief en moeilijk te bereiken vanwege de strakke haken in de toepassingslaag en infrastructuurafhankelijkheden. Omdat Defender voor Eindpunt echter is ingebouwd in het besturingssysteem, is het nu eenvoudig om oplossingen van derden te vervangen.

Kies het onderdeel van Defender voor Eindpunt dat moet worden gebruikt en verwijder de onderdelen die niet van toepassing zijn. In de onderstaande tabel wordt aangegeven welke volgorde Microsoft aanbeveelt voor de manier waarop het eindpuntbeveiligingspakket moet worden ingeschakeld.

| Onderdeel                               | Beschrijving                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Rang van acceptatieorders |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
| Endpoint Detection & Response (EDR)     | Defender voor Endpoint-eindpuntdetectie en -respons bieden geavanceerde detecties voor aanvallen die in realtime en actie kunnen worden ondernomen. Beveiligingsanalisten kunnen waarschuwingen effectief prioriteit geven, zichtbaarheid krijgen in het volledige bereik van een beveiligingsschending en reactieacties ondernemen om bedreigingen te herstellen. <br> [Meer informatie.](/windows/security/threat-protection/windows-defender-atp/overview-endpoint-detection-response)                                                                                                                                                                                                                                             | 1                   |
|Threat & Vulnerability Management (TVM)|Threat & Vulnerability Management is een onderdeel van Microsoft Defender voor Endpoint en biedt zowel beveiligingsbeheerders als beveiligingsbewerkingsteams unieke waarde, waaronder: <br> - Realtime eindpuntdetectie en -respons (EDR) die zijn gerelateerd aan eindpuntproblemen <br> - De kwetsbaarheidscontext van een apparaat van onschatbare waarde tijdens incidentonderzoeken <br> - Ingebouwde herstelprocessen via Microsoft Intune en Microsoft-System Center Configuration Manager <br> [Meer informatie](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Introducing-a-risk-based-approach-to-threat-and-vulnerability/ba-p/377845).| 2 |
| Next-generation protection (NGP)        | Microsoft Defender Antivirus is een ingebouwde antimalwareoplossing die bescherming biedt van de volgende generatie voor desktops, draagbare computers en servers. Microsoft Defender Antivirus bevat: <br> -Beveiliging in de cloud voor het detecteren en blokkeren van nieuwe en nieuwe bedreigingen. Naast machine learning en intelligente beveiliging Graph maakt beveiliging in de cloud deel uit van de volgende generatie technologieën die de Microsoft Defender Antivirus.   <br> - Altijd-on scannen met behulp van geavanceerde controle van bestands- en procesgedrag en andere heuristische functies (ook wel 'real-time protection' genoemd). <br> - Speciale beveiligingsupdates op basis van machine learning, menselijke en geautomatiseerde analyse van big data en uitgebreid onderzoek naar bedreigingsresistentie. <br> [Meer informatie](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10).                                                                                                                                                                                                                                                                                                                                                                       |3                   |
| Attack Surface Reduction (ASR)          | Met de surface reduction-mogelijkheden in Microsoft Defender voor Eindpunt kunt u de apparaten en toepassingen in de organisatie beschermen tegen nieuwe en nieuwe bedreigingen. <br> [Meer informatie.](/windows/security/threat-protection/windows-defender-atp/overview-attack-surface-reduction)                                                                                                                                                                                                                                                                                                                                                                                       | 4                   |
| Auto Investigation & Remediation (AIR)  | Microsoft Defender voor Eindpunt gebruikt Geautomatiseerde onderzoeken om het aantal waarschuwingen dat afzonderlijk moet worden onderzocht aanzienlijk te verminderen. De functie Geautomatiseerd onderzoek maakt gebruik van verschillende inspectiealgoritmen en processen die door analisten (zoals playbooks) worden gebruikt om waarschuwingen te onderzoeken en onmiddellijk herstelmaatregelen te nemen om inbreuken op te lossen. Hierdoor wordt het waarschuwingsvolume aanzienlijk verminderd, zodat experts voor beveiligingsbewerkingen zich kunnen richten op geavanceerdere bedreigingen en andere hoogwaardige initiatieven. <br>[Meer informatie.](/windows/security/threat-protection/windows-defender-atp/automated-investigations-windows-defender-advanced-threat-protection) | Niet van toepassing      |
| Microsoft Threat Experts (MTE)          | Microsoft Threat Experts is een beheerde huntingservice die Beveiligingscentrums (SOC's) voorziet van monitoring en analyse op expertniveau om ervoor te zorgen dat kritieke bedreigingen in hun unieke omgevingen niet worden gemist. <br>[Meer informatie.](/windows/security/threat-protection/windows-defender-atp/microsoft-threat-experts)                                                                                                                                                                                                                                                                                                                     | Niet van toepassing      |

## <a name="next-step"></a>Volgende stap


![Fase 2: Instellen](images/setup.png) <br>[Fase 2: Instellen](production-deployment.md) 
 
Microsoft Defender instellen voor endpoint-implementatie 
