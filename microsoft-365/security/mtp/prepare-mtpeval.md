---
title: Uw testomgeving voor Microsoft Threat Protection voorbereiden
description: Het afmelden van een belanghebbende, tijdlijnen, overwegingen voor de omgeving en de acceptatie bestellen bij het instellen van uw Microsoft Threat Protection-proefversie voor het lab of de proef omgeving
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 97e75b07721c180fe6b4df56c2d9cc819b610802
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195545"
---
# <a name="prepare-your-microsoft-threat-protection-trial-lab-or-pilot-environment"></a>Uw proefabonnement voor Microsoft Threat Protection of een testomgeving voorbereiden

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft Threat Protection

U maakt een Microsoft Threat Protection-proefversie voor proef omgevingen of pilot omgevingen en de implementatie hiervan is een proces van drie fasen:

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" bgcolor="#d5f5e3">
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Uw proefabonnement voor Microsoft Threat Protection of een testomgeving voorbereiden" />
      <br/>Fase 1: voorbereiding </a><br>
    </td>
     <td align="center"  >
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Uw Microsoft Threat Protection-proefversie Lab of pilot omgeving instellen" />
      <br/>Fase 2: instellen </a><br>
        </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval">
        <img src="../../media/config-onboard.png" alt="Configure each Microsoft Threat Protection pillar" title="Elke Microsoft Threat Protection-pijler configureren en de eindpunten voorbereiden" />
      <br/>Fase 3: & onboard configureren</a><br>
</td>
  </tr>
  <tr>
    <td style="width:25%; border:0;">
   
    </td>
    <td valign="top" style="width:25%; border:0;">
    
</td>
    <td valign="top" style="width:25%; border:0;">

</td>    
  </tr>
</table>

U bevindt zich in de voorbereidende fase.


De voorbereiding is essentieel voor een succesvolle implementatie. In deze sectie wordt uitgelegd wat u moet doen als u een proefabonnement voor de implementatie van Microsoft Threat Protection maakt.

## <a name="prerequisites"></a>Vereisten
Meer informatie over de licenties, hardware-en softwarevereisten en andere configuratie-instellingen voor het inrichten en gebruiken van Microsoft Threat Protection. Zie de minimale vereisten voor [Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites), [Microsoft Defender atp](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements), [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description), [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites), beveiliging van de [Microsoft Cloud-app](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites).

## <a name="stakeholders-and-sign-off"></a>Belanghebbenden en afmelden
In het volgende gedeelte wordt aangegeven welke belanghebbenden deel uitmaken van het project en wie kan zich mogelijk registreren, raadplegen of op de hoogte blijven van de belanghebbenden, of het nu gaat om evaluatie of het uitvoeren van een pilot.

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
| Voer naam en e-mailadres in | **Beveiligings analist** *een vertegenwoordiger van het CDOC-team wie invoer kan geven op de detectiemogelijkheden, de gebruikerservaring en de algehele bruikbaarheid van deze wijziging vanuit een oogpunt van beveiligingsactiviteiten.* | Vind      |

## <a name="prepare-your-azure-active-directory"></a>Azure Active Directory voorbereiden
Sla deze stap over als u al synchronisatie tussen Active Directory en Azure Active Directory hebt ingeschakeld. Bekijk bestaande documentatie voor aanbevolen procedures van Azure Active Directory. De volgende stappen zijn geoptimaliseerd voor het evalueren of uitvoeren van een pilot Microsoft Threat Protection-project.

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
In de volgende tabel ziet u de volgorde waarin Microsoft adviseert om de Microsoft Threat Protection-onderdelen voor de implementatie van een proefabonnement of pilot omgeving te configureren.

| Invoert                               | Beschrijving                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Rangschikking van de configuratie volgorde |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
| Office 365 Advanced Threat Protection| Office 365 ATP beschermt uw organisatie tegen kwaadaardige bedreigingen van e-mailberichten, koppelingen (Url's) en samenwerkingsprogramma's. <br> [Meer informatie.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)                                                                                                                                                                                                                                             | 1                   |
|Azure Advanced Threat Protection|Azure ATP maakt gebruik van Active Directory-signalen voor het identificeren, detecteren en onderzoeken van geavanceerde bedreigingen, compromisloze identiteiten, en het uitvoeren van schadelijke Insider-acties die worden doorgestuurd naar uw organisatie. <br> [Meer informatie](https://docs.microsoft.com/azure-advanced-threat-protection/).| 3 |
|Microsoft Cloud App Security| Microsoft Cloud-app-beveiliging is een Cloud Access Security Broker (CASB) die op meerdere clouds werkt. Het biedt uitgebreide zichtbaarheid, controle over gegevens reis en geavanceerde analyses voor het identificeren en bestrijden van cyberthreats in alle cloudservices. <br> [Meer informatie](https://docs.microsoft.com/cloud-app-security/).                                                                                                                                                                                                                                                                                                                                                                       |driefasig                   |
|Microsoft Defender Advanced Threat Protection | De detectie-en antwoord mogelijkheden van Microsoft Defender ATP voor Microsoft Defender bieden geavanceerde aanvals detectie die bij realtime en op actie kan worden uitgevoerd. Beveiligings analisten kunnen waarschuwingen effectiever uitstellen, inzicht krijgen in de volledige reikwijdte van een overtreding en antwoord acties uitvoeren om bedreigingen te herstellen. <br> [Meer informatie.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)                                     |3                   |                                                                                                                                                                                                                                    

## <a name="next-step"></a>Volgende stap
|![Fase 2: instellen](../../media/setup.png) <br>[Fase 2: instellen](setup-mtpeval.md) | Uw Microsoft Threat Protection-proefversie Lab of pilot omgeving instellen
|:-------|:-----|

