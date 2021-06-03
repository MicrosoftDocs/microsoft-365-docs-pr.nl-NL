---
title: Overzicht van beheer en API's
ms.reviewer: ''
description: Meer informatie over de beheerhulpmiddelen en API-categorieën in Microsoft Defender voor Eindpunt
keywords: onboarding, api, siem, rbac, access, portal, integratie, onderzoek, antwoord, entiteiten, entiteit, gebruikerscontext, toepassingscontext, streaming
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 78ab364f8a261b1201fad17ebf86adc1a7456a46
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730835"
---
# <a name="overview-of-management-and-apis"></a>Overzicht van beheer en API's 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mgt-apis-abovefoldlink)


Defender voor Eindpunt ondersteunt een groot aantal opties om ervoor te zorgen dat klanten het platform eenvoudig kunnen gebruiken. 

Als u erkent dat klantomgevingen en -structuren kunnen variëren, is Defender for Endpoint gemaakt met flexibiliteit en gedetailleerde controle om aan verschillende klantvereisten te voldoen. 

## <a name="endpoint-onboarding-and-portal-access"></a>Onboarding van eindpunten en portaltoegang 

Apparaat onboarding is volledig geïntegreerd in Microsoft Endpoint Manager en Microsoft Intune voor clientapparaten en Azure Defender voor serverapparaten, wat volledige end-to-end ervaring biedt voor configuratie, implementatie en monitoring. Daarnaast ondersteunt Microsoft Defender voor Eindpunt groepsbeleid en andere hulpprogramma's van derden die worden gebruikt voor apparatenbeheer.

Defender voor Eindpunt biedt een fijnkorrelige controle over wat gebruikers met toegang tot de portal kunnen zien en doen via de flexibiliteit van op rollen gebaseerde toegangsbeheer (RBAC). Het RBAC-model ondersteunt alle smaken van de structuur van beveiligingsteams:
- Wereldwijd verspreide organisaties en beveiligingsteams
- Teams voor beveiligingsbewerkingen met laagge lagenmodel
- Volledig gescheiden afdelingen met één gecentraliseerde teams voor globale beveiligingsbewerkingen 

## <a name="available-apis"></a>Beschikbare API's
De Microsoft Defender voor Eindpunt-oplossing is gebouwd op een platform dat klaar is voor integratie.

In Defender voor Eindpunt worden veel van de gegevens en acties via een set programmatische API's beschikbaar. Met deze API's kunt u werkstromen automatiseren en innoveren op basis van De mogelijkheden van Defender voor eindpunten.

![Afbeelding van de beschikbare API en integratie in Microsoft Defender voor Eindpunt](images/mdatp-apis.png)  

De API's van Defender voor eindpunten kunnen worden gegroepeerd in drie:
- Microsoft Defender voor eindpunt-API's 
- API voor onbewerkte voor gegevensstreaming
- SIEM-integratie

## <a name="microsoft-defender-for-endpoint-apis"></a>Microsoft Defender voor eindpunt-API's

Defender voor Eindpunt biedt een gelaagd API-model met gegevens en mogelijkheden in een gestructureerd, duidelijk en eenvoudig te gebruiken model, dat wordt belicht via een standaard azure AD-verificatie- en autorisatiemodel dat toegang biedt in context van gebruikers of SaaS-toepassingen. Het API-model is ontworpen om entiteiten en mogelijkheden in een consistente vorm weer te geven. 

Bekijk deze video voor een kort overzicht van de API's van Defender voor Eindpunt. 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

Met de **Onderzoeks-API** wordt de rijkdom van Defender voor Eindpunt beschreven, waarbij berekende of 'geprofileerde' entiteiten (bijvoorbeeld apparaat, gebruiker en bestand) en discrete gebeurtenissen (bijvoorbeeld procescreatie en bestandscreatie) worden beschreven, waarbij doorgaans een gedrag wordt beschreven dat betrekking heeft op een entiteit, waardoor toegang tot gegevens wordt mogelijk gemaakt via onderzoeksinterfaces die een querytoegang tot gegevens mogelijk maken. Zie Ondersteunde [API's voor meer informatie.](exposed-apis-list.md)

De **Response API** biedt de mogelijkheid om acties uit te voeren in de service en op apparaten, zodat klanten indicatoren kunnen opnemen, instellingen kunnen beheren, de status van een waarschuwing kunnen beheren en reactieacties kunnen uitvoeren op apparaten die programmatisch zijn, zoals apparaten isoleren van het netwerk, quarantainebestanden en andere apparaten. 

## <a name="streaming-api"></a>Streaming-API 
Streaming API biedt klanten de mogelijkheid om realtimegebeurtenissen en waarschuwingen van hun exemplaren te verzenden wanneer ze binnen één gegevensstroom voorkomen, wat een lage latentie, een hoog doorvoerbezorgingsmechanisme biedt.

Gebeurtenisgegevens worden rechtstreeks naar Azure-opslag voor gegevensopslag op lange termijn of naar Azure Event Hubs voor gebruik door visualisatieservices of extra gegevensverwerkingsmotoren. 

>[!NOTE]
>Streaming API is nu verplaatst naar Microsoft 365 Defender. Zie Streaming [API voor meer informatie.](raw-data-export.md)


## <a name="siem-api"></a>SIEM-API
Wanneer u beveiligingsgegevens en SIEM-integratie (Event Management) inschakelen, kunt u hiermee detecties uit Microsoft Defender-beveiligingscentrum halen met uw SIEM-oplossing of door rechtstreeks verbinding te maken met de REST-API voor detecties. Hiermee activeert u de sectie toegangsdetails van de SIEM-connector met vooraf ingevulde waarden en wordt er een toepassing gemaakt onder uw Azure Active Directory (Azure AD)-tenant. Zie [SIEM-integratie voor meer informatie.](enable-siem-integration.md)

## <a name="related-topics"></a>Verwante onderwerpen
- [Toegang tot de API's van Microsoft Defender voor eindpunten ](apis-intro.md)
- [Ondersteunde API's](exposed-apis-list.md)
- [Mogelijkheden voor technische partners](partner-integration.md)

