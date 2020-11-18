---
title: Uw proef omgeving voor Microsoft 365 Defender voorbereiden
description: Het afmelden van een belanghebbende, tijdlijnen, overwegingen voor de omgeving en de acceptatie orde voorkomen bij het instellen van uw Microsoft 365-proefabonnement voor de proefversie of pilot omgeving
keywords: MTP-proefabonnement, MTP pilot prep, prep voor het uitvoeren van een MTP pilot-project, uitvoering van een testprogramma voor MTP-project, implementatie, voorbereiden, belanghebbende, tijdlijn, omgeving, eindpunt, Server, beheer, acceptatie
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.openlocfilehash: 7149524de868a3670807556f5f423ba0ee4a772a
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131237"
---
# <a name="prepare-your-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Uw proefabonnement voor Microsoft 365 Defender of pilot omgeving voorbereiden

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

U maakt een Microsoft 365-proefabonnement voor proef omgevingen of pilot omgevingen en de implementatie ervan is een proces van drie fasen:

|![Fase 1: voorbereiding](../../media/phase-diagrams/prepare.png)<br/>Fase 1: voorbereiding |[![Fase 2: instellen](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)<br/>[Fase 2: instellen](setup-mtpeval.md) |[![Fase 3: onboarding](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)<br/>[Fase 3: onboarding](config-mtpeval.md) | [![Terug naar de pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)<br/>[Terug naar de pilot Playbook](mtp-pilot.md) |
|--|--|--|--|
|*Dat is alles!* | || |

U bevindt zich in de voorbereidende fase.


De voorbereiding is essentieel voor een succesvolle implementatie. In deze sectie wordt uitgelegd wat u moet doen als u een proefabonnement voor de implementatie van Microsoft 365 wilt maken.

## <a name="prerequisites"></a>Vereisten
Meer informatie over de licenties, hardware-en softwarevereisten en andere configuratie-instellingen voor het inrichten en gebruiken van Microsoft 365 Defender. Zie de minimale vereisten voor [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites), [Microsoft Defender for endpoints](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements), [microsoft Defender for Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description), Microsoft-app [voor identiteit](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites), beveiliging van de [Cloud-app van Microsoft](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites).

## <a name="stakeholders-and-sign-off"></a>Belanghebbenden en afmelden
Identificeer alle belanghebbenden die deelnemen aan het project en wie kan zich mogelijk registreren, beoordelen, of op de hoogte blijven, of u nu een proefproject wilt maken of uitvoeren.

>[!NOTE]
>Het kan zijn dat niet alle organisaties de beveiliging van de organisatie hebben voor deze rollen. Neem in dat geval contact op met uw leiderschaps team over controle en goedkeuring accountabilities.

Voeg belanghebbenden toe aan de onderstaande tabel voor uw organisatie.

-   DUS = afmelden voor dit project

-   R = het project controleren en de invoer geven

-   I = op de hoogte gesteld van dit project

| Naam                 | Rol                                                                                                                                                                                                          | Actierij |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| Voer naam en e-mailadres in | **Chief Information Security Officer (ciso)** *een vertegenwoordiger van de directeur die fungeert als sponsor binnen de organisatie voor de nieuwe technologie-implementatie.*                                                  | ZOVEEL     |
| Voer naam en e-mailadres in | **Hoofd van Cyber defensie Operations Center (CDOC)** *een medewerker van het CDOC-team dat verantwoordelijk is voor het bepalen van de manier waarop deze wijziging wordt uitgelijnd met de processen in het team beveiligingsactiviteiten.*       | ZOVEEL     |
| Voer naam en e-mailadres in | **Beveiligings architect** *een medewerker van het beveiligingsteam dat verantwoordelijk is voor het bepalen van de manier waarop deze wijziging wordt afgestemd op de kern beveiligingsarchitectuur van de organisatie.*                         | S      |
| Voer naam en e-mailadres in | **Workplace architect** *een medewerker van het IT-team die verantwoordelijk is voor het bepalen van de manier waarop deze wijziging wordt uitgelijnd met de core Workplace Architecture van de organisatie.*                             | S      |
| Voer naam en e-mailadres in | **Beveiligings analist** *een vertegenwoordiger van het CDOC-team die feedback kan geven over de detectie functies, de gebruikerservaring en de algehele bruikbaarheid van deze wijziging vanuit een oogpunt van beveiligingsactiviteiten.* | Vind      |

## <a name="prepare-your-azure-active-directory"></a>Azure Active Directory voorbereiden
Sla deze stap over als u al synchronisatie tussen Active Directory en Azure Active Directory hebt ingeschakeld. Bekijk bestaande documentatie voor aanbevolen procedures van Azure Active Directory. De volgende stappen zijn geoptimaliseerd voor het evalueren of uitvoeren van een pilot Microsoft 365 Defender-project.

1. Ga naar [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade) Portal > **Azure AD Connect**. 
![Afbeelding van Azure Active Directory-portal pagina](../../media/mtp-eval-1.png) <br> 

2. Klik op **downloaden** van **Microsoft Azure Active Directory Connect** en breng dit over naar de domein controller.
![Afbeelding van de downloadpagina van Azure Active Directoru Connect](../../media/mtp-eval-2.png) <br>

3. Op de domeincontroller volgt u de wizard Azure Active Directory Connect. Lees de licentievoorwaarden en het Privacy-kennisgeving en schakel het selectievakje in als u ermee akkoord gaat. Klik op **Continue**.
![Afbeelding van de welkomstpagina van Azure AD Connect](../../media/mtp-eval-3.png) <br>

4. Ga naar **instellingen voor expres**.
![Afbeelding van de pagina met snelle instellingen](../../media/mtp-eval-4.png) <br>

5. Voer uw globale-beheerdersreferenties in. Klik op **Volgende**.
![Afbeelding van de pagina verbinding maken met een Azure AD waarop u de referenties van een globale beheerder moet invoeren](../../media/mtp-eval-5.png) <br>

6. Voer de referenties van uw Active Directory Domain Services Enterprise-beheerder in. Klik op **Volgende**.
![Afbeelding van de pagina verbinding maken met AD DS waar u uw referenties moet invoeren](../../media/mtp-eval-6.png) <br>

7. Klik op **installeren** om de configuratie te bevestigen.
![Afbeelding van de pagina configuratie bevestiging](../../media/mtp-eval-7.png) <br>

8. Gefeliciteerd, u hebt Azure Active Directory Connect geconfigureerd.
![Afbeelding van een correct geconfigureerde pagina van Azure Active Directory Connect](../../media/mtp-eval-8.png) <br>

U kunt nu [gebruikers en groepen toevoegen aan Active Directory](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate) en [een SAM-R-beleid configureren](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc).  


## <a name="configuration-order"></a>Configuratie volgorde
In de volgende tabel wordt aangegeven welke volgorde Microsoft adviseert voor het configureren van de Microsoft 365-onderdelen voor de implementatie van proefversie of pilot omgeving.

| Invoert                               | Beschrijving                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Rangschikking van de configuratie volgorde |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
|Microsoft Defender voor Office 365|Microsoft Defender voor Office 365 beschermt je organisatie tegen kwaadwillende bedreigingen afkomstig van e-mailberichten, koppelingen (URL’s) en hulpmiddelen voor samenwerking. <br> [Meer informatie.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)                                                                                                                                                                                                                                             | 1                   |
|Microsoft Defender for Identity|Microsoft Defender for Identity maakt gebruik van Active Directory-signalen voor het identificeren, detecteren en onderzoeken van geavanceerde bedreigingen, compromisloze identiteiten, en het uitvoeren van schadelijke Insider-acties die worden doorgestuurd naar uw organisatie. <br> [Meer informatie](https://docs.microsoft.com/azure-advanced-threat-protection/).| 3 |
|Microsoft Cloud App Security| Microsoft Cloud-app-beveiliging is een Cloud Access Security Broker (CASB) die op meerdere clouds werkt. Het biedt uitgebreide zichtbaarheid, controle over gegevens reis en geavanceerde analyses voor het identificeren en bestrijden van cyberthreats in alle cloudservices. <br> [Meer informatie](https://docs.microsoft.com/cloud-app-security/).                                                                                                                                                                                                                                                                                                                                                                       |driefasig                   |
|Microsoft Defender voor Eindpunt  | Microsoft Defender voor detectie van eindpunten voor eindpunten biedt geavanceerde aanvals detectie die bij realtime en actie mogelijk zijn. Beveiligings analisten kunnen waarschuwingen effectiever uitstellen, inzicht krijgen in de volledige reikwijdte van een overtreding en antwoord acties uitvoeren om bedreigingen te herstellen. <br> [Meer informatie.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)                                     |3                   |                                                                                                                                                                                                                                    

## <a name="next-step"></a>Volgende stap
|![Fase 2: instellen](../../media/setup.png) <br>[Fase 2: instellen](setup-mtpeval.md) | Uw proefabonnement voor Microsoft 365 Defender of pilot omgeving instellen
|:-------|:-----|

