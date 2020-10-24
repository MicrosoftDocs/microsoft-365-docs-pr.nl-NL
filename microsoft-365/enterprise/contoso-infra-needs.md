---
title: Contoso IT-infrastructuur en bedrijfsbehoeften
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Inzicht in de basisstructuur van de on-premises IT-infrastructuur van Contoso en de manier waarop de zakelijke behoeften van het bedrijf voldoen aan Microsoft 365 for Enterprise.
ms.openlocfilehash: 767374097efa116f116cff6f6ddf96d075eb71ed
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754584"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a>Contoso IT-infrastructuur en bedrijfsbehoeften

Contoso overstapt van een on-premises, gecentraliseerde IT-infrastructuur naar een in de Cloud uitgedeelde instelling voor het uitvoeren van persoonlijke productiviteit en toepassingen op basis van de Cloud.

## <a name="existing-contoso-it-infrastructure"></a>Bestaande infrastructuur contoso IT

Contoso maakt gebruik van een grotendeels gecentraliseerde on-premise IT-infrastructuur, met toepassingsdatacenters op het hoofdkantoor in Parijs.

Hier is Office Headquarters Office met Application datacenters, een DMZ en Internet.

![Bestaande infrastructuur contoso IT](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

De on-premises toepassingsdatacenters hosten: 

- Aangepaste line-of-business-toepassingen die gebruikmaken van SQL Server en andere Linux-databases.
- Een set verouderde SharePoint-servers.
- Servers op organisatie- en teamniveau voor bestandsopslag.

Bovendien ondersteunt elk regionaal hubkantoor een set servers met een vergelijkbare set applicaties. Deze servers worden onderhouden door regionale IT-afdelingen.

Doorzoekbaarheid in de applicaties en gegevens van deze afzonderlijke, geografisch verspreide datacenters blijft een uitdaging.

In het contoso Headquarters DMZ kunt u verschillende sets servers maken:

- Het hosten van de openbare website van contoso, van welke klanten producten, onderdelen, bevoorrading en dienst kunnen bestellen.
- Hosting van het partner-extranet voor communicatie en samenwerking met Contoso-partners.
- Op VPN'S gebaseerde externe toegang tot het intranet van Contoso en webproxy voor werknemers in het hoofdkantoor van Parijs.

## <a name="contoso-business-needs"></a>Bedrijfsbehoeften met contoso

De behoeften van Contoso Business zijn in vijf hoofdcategorieën onderverdeeld:

**Productiviteit**

- Eenvoudiger samenwerken

  E-mail en on-line samenwerking vervangen op basis van een online model dat wijzigingen in realtime toestaat in documenten, eenvoudiger onlinevergaderingen en vastgelegde gespreks threads.
- Verbeter de productiviteit voor externe en mobiele werknemers

  Met een groot aantal werknemers die in huis of in het veld werken, vervangt u de bewaarde VPN-oplossing door uitvoering van toegang tot contoso-gegevens en-bronnen in de Cloud.
- Verbeter de creativiteit en innovatie

  Profiteer van de nieuwste visuele leer- en ideeontwikkelingsmethoden, inclusief inkt en 3D-visualisatie.

**Beveiliging**

- Identiteits- en toegangsbeheer

  Afdwingen van meervoudige en andere vormen van verificatie en beveiliging van gebruikers-en beheerdersaccounts.

- Bedreigingsbeveiliging

  Bescherm tegen externe beveiligingsdreigingen, waaronder e-mail en op het besturingssysteem gebaseerde malware.

- Gegevensbeveiliging

  Vergrendel de toegang tot en codeer hoogwaardige digitale middelen, zoals klantgegevens, ontwerp- en fabricagespecificaties en werknemersinformatie.

- Beveiligingsbeheer

  Bewaak beveiligings-Posture en spoor en reageer op bedreigingen in realtime.

**Externe en mobiele toegang en zakelijke partners**

- Beveiliging voor externe en mobiele werknemers verbeteren

  Implementeer uw eigen apparaat (BYOD) en bedrijfseigendoms beheer ter waarborging om te zorgen voor beveiligde toegang, het corrigeren van toepassings gedrag en de bescherming van bedrijfsgegevens.

- De infrastructuur voor externe toegang voor werknemers reduceren

  Ondersteunings-en ondersteuningskosten verlagen en de prestaties van de Remote Access-oplossing verbeteren door regelmatig toegankelijke bronnen naar de cloud te verplaatsen.

- Zorgt voor betere connectiviteit en lagere overhead voor Business-to-susiness (B2B)-transacties

  Vervang een verouderd en kostbaar partner extranet met een in de cloud gebaseerde oplossing die federatieve verificatie gebruikt.

**Compliance**

- Voldoen aan regionale wettelijke voorschriften

  Zorg ervoor dat de naleving van industriële en regionale voorschriften voor het opslaan, versleutelen, data privacy en persoonlijke gegevens voorschriften, zoals de algemene verordening gegevensbescherming (AVG) voor de Europe Union, voldoen.

**Beheer**

- Minder IT-kosten voor het beheren van software die draait op client Pc's en-apparaten

  De installatie van updates voor het Windows-besturingssysteem en Microsoft 365-apps voor Enterprise binnen de organisatie automatiseren.

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a>Contoso Business behoeften toewijzen aan Microsoft 365 for Enterprise

De IT-afdeling van Contoso heeft bepaald dat de volgende toewijzingen van zakelijke behoeften aan Microsoft 365 E5-functies voorafgaand aan de implementatie:


| Categorie | Zakelijke behoefte | Microsoft 365 voor Enterprise-producten of-functies |
|:-------|:-----|:-----|
| Productiviteit |  |  |
|  | Eenvoudiger samenwerken | Microsoft Teams, SharePoint, OneDrive |
|  | Verbeter de productiviteit voor externe en mobiele werknemers | Werkbelasting en cloud-gebaseerde gegevens voor Microsoft 365 |
|  | Verbeter de creativiteit en innovatie | Windows Ink, Cortana op het werk, PowerPoint |
| Beveiliging |  |  |
|  | Identiteits- en toegangsbeheer | Toegewezen globale beheerdersaccounts met Azure multi-factor Authentication (MFA) en Azure Active Directory-geprivilegieerde identiteitsbeheer (PIM) <BR> MFA voor alle gebruikersaccounts <BR> Voorwaardelijke toegang <BR> Windows Hello <BR> Windows Credential Guard |
|  | Bedreigingsbeveiliging | Advanced Threat Analytics <BR> Windows Defender <BR> Advanced Threat Protection <BR> Office 365 Advanced Threat Protection <BR> Microsoft 365 Threat onderzoek en-antwoord <BR> |
|  | Gegevensbeveiliging | Azure-gegevensbeveiliging <BR> Preventie van gegevensverlies (DLP, Data Loss Prevention) <BR> Windows-gegevensbescherming (WIP) <BR> Microsoft Cloud App Security <BR> Microsoft Intune |
|  | Beveiligingsbeheer | Azure Security Center  <BR> Windows Defender-Beveiligingscentrum |
| Externe en mobiele toegang en zakelijke partners |  |  |
|  | Verbeterde beveiliging voor externe en mobiele werknemers | Microsoft Intune |
|  | De infrastructuur voor externe toegang voor werknemers reduceren | Werkbelasting en cloud-gebaseerde gegevens voor Microsoft 365 |
|  | De connectiviteit en lagere overhead voor B2B-transacties verbeteren | Federatieve verificatie en cloudgebaseerde bronnen |
| Naleving |  |  |
|  | Voldoen aan regionale wettelijke voorschriften | AVG-functies in Microsoft 365 |
| Beheer |  |  |
|  | Minder IT-kosten voor de installatie van clientupdates | Updates voor Windows 10 Enterprise <BR> Updates voor Microsoft 365-apps voor ondernemingen |
||||

## <a name="next-step"></a>Volgende stap

Meer informatie over het [on-premises netwerk van](contoso-networking.md) Contoso Corporation en hoe dit is geoptimaliseerd voor toegang en latentie tot microsoft 365 cloudresources.

## <a name="see-also"></a>Zie ook

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Testlabrichtlijnen](m365-enterprise-test-lab-guides.md)
