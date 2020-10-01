---
title: Uw proefproject voor Microsoft Threat Protection plannen
description: Plan uw pilot Microsoft Threat Protection-project met belanghebbenden voor het beheren van de verwachtingen en zorg voor een succesvolle uitslag.
keywords: Proefversie van Microsoft Threat Protection, proefabonnement Microsoft Threat Protection, Microsoft Threat Protection evalueren in productie, Microsoft Threat Protection pilotproject, Cyber beveiliging, Geavanceerd permanent risico, beveiliging van uw bedrijf, apparatuur, apparaat, identiteit, gebruikers, gegevens, toepassingen, incidenten, geautomatiseerd onderzoek en herstel, geavanceerde jacht
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 21e6e3294b8fe722214d567963223b9e62737e34
ms.sourcegitcommit: b06a4f21da247edb03fdf6a01eafb7d4fb387b33
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/01/2020
ms.locfileid: "48333676"
---
# <a name="planning-your-pilot-microsoft-threat-protection-project"></a>Uw proefproject voor Microsoft Threat Protection plannen 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft Threat Protection
<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" bgcolor="#d5f5e3">
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-plan"> 
        <img src="../../media/mtp/plan.png" alt="Plan your pilot Microsoft Threat Protection project" title="Uw proefproject voor Microsoft Threat Protection plannen" />
      <br/>Abonnement</a><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval">
        <img src="../../media/mtp/prep.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="Uw proefabonnement voor Microsoft Threat Protection of een testomgeving voorbereiden" />
      <br/>Voorbereiden</a><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate">
        <img src="../../media/mtp/run-sim.png" alt="Run your Microsoft Threat Protection attack simulations" title="Simulaties van aanvallen van Microsoft Threat Protection uitvoeren" />
     <br/>Een aanval simuleren</a><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-close">
        <img src="../../media/mtp/close.png" alt="Close and summarize your Microsoft Threat Protection pilot" title="Uw proef Microsoft Threat Protection sluiten en samenvatten" />
     <br/>Sluiten en samenvatten</a><br>
    </td>
  </tr>
  <tr>
    <td style="width:25%; border:0;">
   
    </td>
    <td valign="top" style="width:25%; border:0;">
    
</td>
    <td valign="top" style="width:25%; border:0;">

</td>    
    <td valign="top" style="width:25%; border:0;">

</td>
  </tr>
</table>

U bevindt zich momenteel in de planningsfase.

Om ervoor te zorgen dat uw pilotproject een gunstige uitkomst is, is het van essentieel belang dat u de belanghebbenden snel goed keurt en goedkeuring van uw belanghebbenden ontvangt. De planning van elementen bevat identificatie bereik, gebruiks kwesties, vereisten en succescriteria.

Deze handleiding helpt u bij het plannen van uw pilotproject. 

>[!IMPORTANT]
>Volg voor optimale resultaten de instructies voor het testen.


## <a name="scope"></a>Scoop

Het bereik van de leider bepaalt hoe breed de test is, op basis van uw omgeving en de acceptabele testmethoden. Hier volgen enkele voorbeelden van aandachtspunten:
- Ontwikkelings-of testomgeving, waaronder eindpunten, servers, domeincontrollers.
- Productieomgeving met Microsoft 365, azure, Active Directory Services, eindpunten en servers

>[!NOTE]
>Als u de volledige licentie nog niet hebt, kunt u een proefabonnement krijgen voor het [evalueren van Microsoft Threat Protection (Microsoft Threat Protection](https://aka.ms/mtp-trial-lab) plannen, voorbereiden, instellen, configureren en uitvoeren van uw pilotproject). De belanghebbenden kunnen een belangrijke rol spelen, zodat de procedure van begin tot eind wordt vergemakkelijkt.

De typen besturingssystemen die moeten worden geëvalueerd, worden ook gedefinieerd op basis van de organisatie-Makeup. Dit kan de volgende bebestaan: [Mac-eindpunten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements), [Linux-servers](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements), [Windows 10-eindpunten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions), [Windows Server 2016](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions).

## <a name="use-cases"></a>Gebruik zaken

Use-cases stellen de manier weer waarop het te testen instrument wordt gebruikt door de bedoelde gebruikers. Deze kunnen worden geformuleerd als gebruikers verhalen vanuit het oogpunt van een bepaalde persoon, zoals een SOC-analist. Bijvoorbeeld:
- Als SOC-analist moet ik waarschuwingen en gebeurtenissen op alle apparaten, gebruikers en postvakken in mijn netwerk weergeven, correleren, beoordelen, beoordelen en beheren. [Incidentenbeheer]
- Als SOC-Analyst moet ik het hulpmiddel en het proces voor het automatisch onderzoeken en beantwoorden van schadelijke gebeurtenissen in mijn netwerk hebben. [Automatische IR]
- Als SOC-analist moet ik de gegevens van mijn omgeving doorzoeken om bekende, potentiële bedreigingen en verdachte activiteiten te vinden. [Geavanceerde jacht]

Houd er rekening mee dat het gebruik van dit soort aanvragen binnen de parameters van het gedefinieerde bereik moet worden gemaakt. Als u bijvoorbeeld het test bereik omvat, is het niet mogelijk om een evaluatie te maken van hulpmiddelen zoals beveiliging van de Cloud-app van Microsoft.

## <a name="requirements"></a>Vereisten

Vanuit de lijst met begebruikte zaken, kunt u beginnen met het maken van vereisten. Voor de vereisten behoren functies een programma dient te voldoen aan de use cases. Deze vereisten kunnen worden opgesplitst in categorieën zoals configuratie en onderhoud, ondersteuning voor integraties en functie-specifieke vereisten, zoals de ondersteuning van de jacht en de mogelijkheid om aangepaste waarschuwingen te maken.

## <a name="test-plan"></a>Test plan

Afhankelijk van de vereisten, is het mogelijk dat er verschillende testmethoden geschikt zijn. Als u bijvoorbeeld de effectiviteit van geautomatiseerde herbemiddeling evalueert, moet het testplan stappen opnemen om de gedrag (en) te genereren waarmee een geautomatiseerde herstelactie binnen Microsoft Threat Protection werd geactiveerd. Als u een bepaald gedrag of een bepaalde aanval moet detecteren, dan kan de test meer stappen veroorzaken. U kunt het beste een plan op basis van de vereisten nauwkeurig testen.

## <a name="success-criteria"></a>Criteria voor succes

De criteria voor succes zijn uiteindelijk de balk die is ingesteld voor de waardering van wat u wilt testen. Of u nu Microsoft Threat Protection (of andere hulpmiddelen voor die materie) tegen andere hulpmiddelen of op een andere manier test, moet u een aantal meetbaarste criteria gebruiken om de waarde van het hulpmiddel te bepalen. Afhankelijk van de vereisten voor het bereik, de vereisten en het testen van het plan, wordt het resultaat van de test bepaald. Dit kan minder of niet meer zijn, en ook een gewogen score op basis van uw behoeften. Als u bijvoorbeeld een succesvolle aanduiding wilt hebben, moet een hulpmiddel mogelijk een Score van 80% hebben in bepaalde kritieke gebieden die u identificeert.

## <a name="scorecard"></a>Werd

U kunt ook een scorecard maken om alle elementen van uw plan bijeen te brengen. Hieronder ziet u een voorbeeld van een Scorecard:

|**Use-case**|**Vereisten**|**Configuratievereisten**|**Test plan**|**Verwacht resultaat**|**Status testen**|**Score**|**Opmerkingen**|
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|Incidentenbeheer|-Microsoft Threat Protection </br></br>-Azure ATP </br></br>-Microsoft Defender ATP </br></br>-Beveiliging van Microsoft Cloud-app (optioneel)|Zie de [vereisten](https://aka.ms/mtp-trial-lab) voor voorbereiden voor voorbereiden, instellen en configureren voor meer informatie |[Een aanval simuleren](mtp-pilot-simulate.md) <br></br>[Het incident onderzoeken](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#investigate-an-incident) |Onderzoekers kunnen inzicht krijgen in de reikwijdte en impact van het incident en het incident beheren||||
|AutoIR|-Microsoft Threat Protection </br></br>-Azure ATP </br></br>-Microsoft Defender ATP |Zie de [vereisten](https://aka.ms/mtp-trial-lab) voor voorbereiden voor voorbereiden, instellen en configureren voor meer informatie <br>AutoIR inschakelen  |[Een aanval simuleren](mtp-pilot-simulate.md) <br></br>[Automatisch onderzoek](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#automated-investigation-and-remediation) |Waarschuwingen en incidenten worden automatisch doorgevoerd door Microsoft Threat Protection||||
|Geavanceerd opsporen|-Microsoft Threat Protection </br></br>-Microsoft Defender ATP </br></br>-Office 365 ATP   |Zie de [vereisten](https://aka.ms/mtp-trial-lab) voor voorbereiden voor voorbereiden, instellen en configureren voor meer informatie|[Scenario voor Geavanceerd jacht](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#advanced-hunting-scenario) |Onderzoekers kunnen gegevens vinden via Geavanceerd jacht, draaien naar beïnvloede entiteiten en aangepaste detecties maken||||



## <a name="next-step"></a>Volgende stap
|![Voorbereidende fase](../../media/mtp/prep.png) <br>[Voorbereidende fase](prepare-mtpeval.md) | Uw testomgeving voor Microsoft Threat Protection voorbereiden
|:-------|:-----|
