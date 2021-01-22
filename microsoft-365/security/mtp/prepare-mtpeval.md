---
title: Uw Test labomgeving met Microsoft 365 Defender voorbereiden
description: Aanmelding bij belanghebbenden, tijdlijnen, omgevingsoverwegingen en acceptatieorders voorbereiden bij het instellen van uw testtest of pilotomgeving met Microsoft 365 Defender
keywords: Voorbereiden van MTP-proefversie, voorbereiden van MTP-pilot, voorbereiden voor het uitvoeren van een MTP-pilot, een MTP-pilot uitvoeren, implementeren, voorbereiden, belanghebbende, tijdlijn, omgeving, eindpunt, server, beheer, acceptatie
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 35f1d3f0b5cefb0f14508571511449fc2c7d58a9
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930148"
---
# <a name="prepare-your-microsoft-365-defender-trial-lab-or-pilot-environment"></a>De testtest of testomgeving van Microsoft 365 Defender voorbereiden

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

Het maken van een testtest of pilotomgeving van Microsoft 365 Defender en deze implementeren bestaat uit drie fasen:

|![Fase 1: Voorbereiden](../../media/phase-diagrams/prepare.png)<br/>Fase 1: Voorbereiden |[![Fase 2: Instellen](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)<br/>[Fase 2: Instellen](setup-mtpeval.md) |[![Fase 3: Onboard](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)<br/>[Fase 3: Onboard](config-mtpeval.md) | [![Terug naar pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)<br/>[Terug naar pilot playbook](mtp-pilot.md) |
|--|--|--|--|
|*U bent hier!* | || |

U zit momenteel in de voorbereidingsfase.


Voorbereiding is belangrijk voor elke succesvolle implementatie. In deze sectie wordt u begeleid bij wat u moet overwegen wanneer u zich voorbereidt op het maken van een testtestomgeving of pilotomgeving voor uw Microsoft 365 Defender-implementatie.

## <a name="prerequisites"></a>Vereisten
Meer informatie over de licentie-, hardware- en softwarevereisten en andere configuratie-instellingen voor het inrichten en gebruiken van Microsoft 365 Defender. Bekijk de minimale vereisten voor [Microsoft 365 Defender,](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites) [Microsoft Defender voor](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements)eindpunt, Microsoft Defender voor [Office 365,](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) [Microsoft Defender voor identiteit,](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites) [Microsoft Cloud App-beveiliging.](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites)

## <a name="stakeholders-and-sign-off"></a>Belanghebbenden en aanmelding
Identificeer alle belanghebbenden die bij het project zijn betrokken en wie zich mogelijk moet afloggen, beoordelen of op de hoogte moeten blijven, ongeacht of ze willen worden geëvalueerd of een pilot moeten uitvoeren.

>[!NOTE]
>Mogelijk hebben niet alle organisaties de vervaldatum van de beveiligingsorganisatie om dergelijke rollen te hebben. Neem in dat geval contact op met uw managementteam over accountmogelijkheden voor beoordeling en goedkeuring.

Voeg belanghebbenden toe aan de onderstaande tabel, voor uw organisatie.

-   SO = Sign-off voor dit project

-   R = Dit project bekijken en input geven

-   I = goed geïnformeerd over dit project

| Naam                 | Rol                                                                                                                                                                                                          | Actie |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| Naam en e-mailadres invoeren | **Chief Information Security Officer (CISO) Een** leidinggevende die fungeert als sponsor binnen de organisatie *voor de implementatie van nieuwe technologie.*                                                  | SO     |
| Naam en e-mailadres invoeren | **Head of Cyber Defense Operations Center (CDOC)** A representative from the CDOC team charge of defining how this change is aligned with the *processes in the customers security operations team.*       | SO     |
| Naam en e-mailadres invoeren | **Beveiligingsarchitectuur** *Een vertegenwoordiger van het beveiligingsteam* die verantwoordelijk is voor het definiëren van de manier waarop deze wijziging wordt afgestemd op de kernbeveiligingsarchitectuur van de organisatie.                         | R      |
| Naam en e-mailadres invoeren | **Workplace Architect** *Een vertegenwoordiger van het IT-team* die verantwoordelijk is voor het definiëren van deze wijziging, komt overeen met de architectuur van de kernwerkplaats in de organisatie.                             | R      |
| Naam en e-mailadres invoeren | **Beveiligingsanalist** Een vertegenwoordiger van het CDOC-team die feedback kan geven over de detectiemogelijkheden, gebruikerservaring en de algehele bruikbaarheid van deze wijziging vanuit het perspectief van *beveiligingsbewerkingen.* | I      |

## <a name="prepare-your-azure-active-directory"></a>Uw Azure Active Directory voorbereiden
Sla deze stap over als synchronisatie tussen Active Directory en Azure Active Directory on-premises al is ingeschakeld. Bekijk de bestaande documentatie over best practices vanuit Azure Active Directory. De volgende stappen zijn geoptimaliseerd voor het evalueren of uitvoeren van een testfase van het Microsoft 365 Defender-project.

1. Ga naar de [Azure Active Directory-portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade) > **Azure AD Connect.** 
![Afbeelding van de portalpagina van Azure Active Directory](../../media/mtp-eval-1.png) <br> 

2. Klik **op Downloaden** van Microsoft Azure Active Directory **Connect** en breng dit over naar uw domeincontroller.
![Afbeelding van downloadpagina van Azure Active Directoru Connect](../../media/mtp-eval-2.png) <br>

3. Volg op de domeincontroller de wizard Azure Active Directory Connect. Lees de licentievoorwaarden en de privacyverklaring en schakel het selectievakje in als u ermee akkoord gaat. Klik op **Continue**.
![Afbeelding van welkomstpagina van Azure AD Connect](../../media/mtp-eval-3.png) <br>

4. Ga naar **Expresinstellingen.**
![Afbeelding van de pagina Express-instellingen](../../media/mtp-eval-4.png) <br>

5. Voer uw globale beheerdersreferenties in. Klik op **Volgende**.
![Afbeelding van de pagina Verbinding maken met Azure AD, waar u uw globale beheerdersreferenties moet invoeren](../../media/mtp-eval-5.png) <br>

6. Voer de beheerdersreferenties voor Active Directory Domain Services voor bedrijven in. Klik op **Volgende**.
![Afbeelding van de pagina Verbinding maken met AD DS, waar u uw referenties moet invoeren](../../media/mtp-eval-6.png) <br>

7. Klik **op Installeren** om de configuratie te bevestigen.
![Afbeelding van de bevestigingspagina van de configuratie](../../media/mtp-eval-7.png) <br>

8. Gefeliciteerd, u hebt Azure Active Directory Connect geconfigureerd.
![Afbeelding van een correct geconfigureerde pagina van Azure Active Directory Connect](../../media/mtp-eval-8.png) <br>

U kunt nu [gebruikers en groepen toevoegen aan Active Directory](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate) en een [SAM-R-beleid configureren.](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc)  


## <a name="configuration-order"></a>Configuratieorder
In de volgende tabel wordt de volgorde aangegeven die Microsoft aanbeveelt voor het configureren van de Microsoft 365 Defender-onderdelen voor de implementatie van uw testtest of pilotomgeving.

| Onderdeel                               | Beschrijving                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Rang van configuratieorder |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
|Microsoft Defender voor Office 365|Microsoft Defender voor Office 365 beschermt je organisatie tegen kwaadwillende bedreigingen afkomstig van e-mailberichten, koppelingen (URL’s) en hulpmiddelen voor samenwerking. <br> [Meer informatie.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)                                                                                                                                                                                                                                             | 1                   |
|Microsoft Defender for Identity|Microsoft Defender for Identity gebruikt Active Directory-signalen voor het identificeren, detecteren en onderzoeken van geavanceerde bedreigingen, gekromde identiteiten en kwaadaardige insideracties die zijn gericht op uw organisatie. <br> [Meer informatie](https://docs.microsoft.com/azure-advanced-threat-protection/).| 2 |
|Microsoft Cloud App Security| Microsoft Cloud App Security is een cloudtoegangsbeveiligingsagent (CASB) die op meerdere clouds werkt. Het biedt uitgebreide zichtbaarheid, controle over gegevensreizen en geavanceerde analyses om cyberaanvallen in al uw cloudservices te identificeren en te bestrijden. <br> [Meer informatie](https://docs.microsoft.com/cloud-app-security/).                                                                                                                                                                                                                                                                                                                                                                       |3                   |
|Microsoft Defender for Endpoint | De detectie- en antwoordmogelijkheden van het Eindpunt van Microsoft Defender voor eindpunt bieden geavanceerde detectie van aanvallen die in realtime bijna in realtime zijn en die kunnen worden ondernomen. Beveiligingsanalisten kunnen waarschuwingen effectief prioriteit geven, inzicht krijgen in het volledige bereik van een inbreuk en reactieacties ondernemen om bedreigingen te herstellen. <br> [Meer informatie.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)                                     |4                   |                                                                                                                                                                                                                                    

## <a name="next-step"></a>Volgende stap
|![Fase 2: Installatie](../../media/setup.png) <br>[Fase 2: Installatie](setup-mtpeval.md) | Uw Test lab of pilotomgeving met Microsoft 365 Defender instellen
|:-------|:-----|

