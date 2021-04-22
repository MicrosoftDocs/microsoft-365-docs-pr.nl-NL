---
title: Uw proeflabomgeving van Microsoft 365 Defender voorbereiden
description: Aanmelding van belanghebbenden, tijdlijnen, milieuoverwegingen en acceptatieorders voorbereiden bij het instellen van uw proeflaboratorium of testomgeving van Microsoft 365 Defender
keywords: Microsoft 365 Defender trial prep, Microsoft 365 Defender pilot prep, prep for running a Microsoft 365 Defender pilot project, run a pilot Microsoft 365 Defender project, deploy, prepare, stakeholder, timeline, environment, endpoint, server, management, adoption
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d5e98cead84c0be76ca252b23f3c2d062b22dd73
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935615"
---
# <a name="prepare-your-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Uw proeflaboratorium of testomgeving voor Microsoft 365 Defender voorbereiden

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

Het maken van een proeflaboratorium of testomgeving van Microsoft 365 Defender en de implementatie ervan is een proces in drie fasen:

|![Fase 1: Voorbereiden](../../media/phase-diagrams/prepare.png)<br/>Fase 1: Voorbereiden |[![Fase 2: Instellen](../../media/phase-diagrams/setup.png)](setup-m365deval.md)<br/>[Fase 2: Instellen](setup-m365deval.md) |[![Fase 3: Onboarden](../../media/phase-diagrams/onboard.png)](config-m365d-eval.md)<br/>[Fase 3: Onboarden](config-m365d-eval.md) | [![Terug naar pilot](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)<br/>[Terug naar pilot playbook](m365d-pilot.md) |
|--|--|--|--|
|*U bent er!* | || |

U bent momenteel bezig met de voorbereidingsfase.


Voorbereiding is essentieel voor een geslaagde implementatie. In deze sectie wordt u begeleid bij wat u moet overwegen terwijl u zich voorbereidt op het maken van een proeflaboratorium of testomgeving voor uw Microsoft 365 Defender-implementatie.

## <a name="prerequisites"></a>Vereisten
Meer informatie over de licentie-, hardware- en softwarevereisten en andere configuratie-instellingen voor het inrichten en gebruiken van Microsoft 365 Defender. Bekijk de minimumvereisten voor [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/prerequisites), [Microsoft Defender voor](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements)Eindpunt , Microsoft Defender voor Office [365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description), [Microsoft Defender voor identiteit](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites), Microsoft Cloud App [Security](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites).

## <a name="stakeholders-and-sign-off"></a>Belanghebbenden en aanmelding
Identificeer alle belanghebbenden die betrokken zijn bij het project en wie zich mogelijk moeten aanmelden, controleren of op de hoogte moeten blijven, ongeacht of ze een testproject willen evalueren of uitvoeren.

>[!NOTE]
>Niet alle organisaties hebben mogelijk de vervaldatum van de beveiligingsorganisatie om dergelijke rollen te hebben. In dat geval overlegt u met uw leidinggevende team over controle- en goedkeuringsaccountvaardigheden.

Voeg belanghebbenden toe aan de onderstaande tabel voor uw organisatie.

-   SO = Aanmelden bij dit project

-   R = Controleer dit project en geef input

-   I = Op de hoogte van dit project

| Naam                 | Rol                                                                                                                                                                                                          | Actie |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| Naam en e-mail invoeren | **CiSO (Chief Information Security Officer)** Een uitvoerend vertegenwoordiger die fungeert als sponsor binnen de *organisatie voor de implementatie van nieuwe technologie.*                                                  | SO     |
| Naam en e-mail invoeren | **Hoofd van het Cyber Defense Operations Center (CDOC) Een** vertegenwoordiger van het *CDOC-team* dat verantwoordelijk is voor het definiëren van de manier waarop deze wijziging wordt afgestemd op de processen in het beveiligingsteam van klanten.       | SO     |
| Naam en e-mail invoeren | **Beveiligingsarchitect** Een vertegenwoordiger van het beveiligingsteam die verantwoordelijk is voor het definiëren van de manier waarop deze wijziging wordt uitgelijnd met de *belangrijkste beveiligingsarchitectuur in de organisatie.*                         | R      |
| Naam en e-mail invoeren | **Werkplekarchitect** *Een vertegenwoordiger van het IT-team* die verantwoordelijk is voor het definiëren van de manier waarop deze wijziging wordt afgestemd op de basisarchitectuur van de werkplek in de organisatie.                             | R      |
| Naam en e-mail invoeren | **Beveiligingsanalist** Een vertegenwoordiger van het CDOC-team die feedback kan geven over de detectiemogelijkheden, gebruikerservaring en het algemene nut van deze wijziging vanuit het perspectief van *beveiligingsbewerkingen.* | I      |

## <a name="prepare-your-azure-active-directory"></a>Uw Azure Active Directory voorbereiden
Sla deze stap over als u synchronisatie al hebt ingeschakeld tussen Active Directory en Azure Active Directory on premises. Bekijk bestaande best practices-documentatie vanuit Azure Active Directory. De volgende stappen zijn geoptimaliseerd om een testproject van Microsoft 365 Defender te evalueren of uit te voeren.

1. Ga naar de [Azure Active Directory-portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade) > **Azure AD Connect**. 
![Afbeelding van de portalpagina van Azure Active Directory](../../media/mtp-eval-1.png) <br> 

2. Klik **op Downloaden** van Microsoft Azure Active Directory **Connect** en breng deze over naar uw domeincontroller.
![Afbeelding van de downloadpagina van Azure Active Directoru Connect](../../media/mtp-eval-2.png) <br>

3. Volg de wizard Azure Active Directory Connect op de domeincontroller. Lees de licentievoorwaarden en privacyverklaring en schakel het selectievakje in als u akkoord gaat. Klik op **Continue**.
![Afbeelding van de welkomstpagina van Azure AD Connect](../../media/mtp-eval-3.png) <br>

4. Ga naar **Express-instellingen.**
![Afbeelding van de pagina Express-instellingen](../../media/mtp-eval-4.png) <br>

5. Voer uw globale beheerdersreferenties in. Klik op **Volgende**.
![Afbeelding van de pagina Verbinding maken met Azure AD waar u uw globale beheerdersreferenties moet invoeren](../../media/mtp-eval-5.png) <br>

6. Voer uw beheerdersreferenties voor Active Directory Domain Services in. Klik op **Volgende**.
![Afbeelding van de pagina Verbinding maken met AD DS waar u uw referenties moet invoeren](../../media/mtp-eval-6.png) <br>

7. Klik **op Installeren** om de configuratie te bevestigen.
![Afbeelding van configuratiebevestigingspagina](../../media/mtp-eval-7.png) <br>

8. Gefeliciteerd, u hebt Azure Active Directory Connect geconfigureerd.
![Afbeelding van een geconfigureerde Azure Active Directory Connect-pagina](../../media/mtp-eval-8.png) <br>

U kunt nu [gebruikers en groepen toevoegen aan Active Directory](/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate) en een [SAM-R-beleid configureren.](/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc)  


## <a name="configuration-order"></a>Configuratieorder
In de volgende tabel wordt aangegeven welke volgorde Microsoft aanbeveelt voor het configureren van de Microsoft 365 Defender-onderdelen voor de implementatie van uw proeflaboratorium of testomgeving.

| Onderdeel                               | Beschrijving                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Rangschikking van configuratieorders |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
|Microsoft Defender voor Office 365|Microsoft Defender voor Office 365 beschermt je organisatie tegen kwaadwillende bedreigingen afkomstig van e-mailberichten, koppelingen (URL’s) en hulpmiddelen voor samenwerking. <br> [Meer informatie.](/microsoft-365/security/office-365-security/defender-for-office-365)                                                                                                                                                                                                                                             | 1                   |
|Microsoft Defender for Identity|Microsoft Defender voor identiteit gebruikt Active Directory-signalen om geavanceerde bedreigingen, gecompromitteerde identiteiten en kwaadaardige insideracties die zijn gericht op uw organisatie te identificeren, te detecteren en te onderzoeken. <br> [Meer informatie](/azure-advanced-threat-protection/).| 2 |
|Microsoft Cloud App Security| Microsoft Cloud App Security is een Cloud Access Security Broker (CASB) die op meerdere clouds werkt. Het biedt uitgebreide zichtbaarheid, controle over het reizen van gegevens en geavanceerde analyses om cyberaanvallen in al uw cloudservices te identificeren en te bestrijden. <br> [Meer informatie](/cloud-app-security/).                                                                                                                                                                                                                                                                                                                                                                       |3                   |
|Microsoft Defender voor Eindpunt | Microsoft Defender voor Eindpunt de mogelijkheden voor detectie van en reactie op eindpunten bieden detectie van geavanceerde aanvallen die bijna in realtime en uitvoerbaar zijn. Beveiligingsanalisten kunnen waarschuwingen effectief prioriteit geven, zichtbaarheid krijgen in het volledige bereik van een beveiligingsschending en reactieacties ondernemen om bedreigingen te herstellen. <br> [Meer informatie.](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)                                     |4                   |                                                                                                                                                                                                                                    

## <a name="next-step"></a>Volgende stap
|![Fase 2: Instellen](../../media/setup.png) <br>[Fase 2: Instellen](setup-m365deval.md) | Uw proeflaboratorium of testomgeving voor Microsoft 365 Defender instellen
|:-------|:-----|
