---
title: Contoso IT-infrastructuur en zakelijke behoeften
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
description: Inzicht in de basisstructuur van de on-premises IT-infrastructuur van Contoso en hoe aan de zakelijke behoeften van het bedrijf wordt voldaan door Microsoft 365 voor ondernemingen.
ms.openlocfilehash: 72d502b5078a1e572eeba27832550af52907e209
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558404"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a>Contoso IT-infrastructuur en zakelijke behoeften

Contoso maakt de overstap van een on-premises, gecentraliseerde IT-infrastructuur naar een cloudinclusieve installatie met persoonlijke productiviteitsbelastingen en -toepassingen in de cloud.

## <a name="existing-contoso-it-infrastructure"></a>Bestaande IT-infrastructuur van Contoso

Contoso maakt gebruik van een grotendeels gecentraliseerde on-premise IT-infrastructuur, met toepassingsdatacenters op het hoofdkantoor in Parijs.

Hier bevindt zich het hoofdkantoor met toepassingscentra, een DMZ en internet.

![Bestaande IT-infrastructuur van Contoso](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

De on-premises toepassingsdatacenters hosten: 

- Aangepaste line-of-business-toepassingen die gebruikmaken van SQL Server en andere Linux-databases.
- Een set verouderde SharePoint-servers.
- Servers op organisatie- en teamniveau voor bestandsopslag.

Bovendien ondersteunt elk regionaal hubkantoor een set servers met een vergelijkbare set applicaties. Deze servers worden onderhouden door regionale IT-afdelingen.

Doorzoekbaarheid in de applicaties en gegevens van deze afzonderlijke, geografisch verspreide datacenters blijft een uitdaging.

In het Contoso-hoofdkantoor DMZ bieden verschillende sets servers het volgende:

- Hosting voor de openbare Website van Contoso, waaruit klanten producten, onderdelen, leveringen en service kunnen bestellen.
- Hosting van het partner-extranet voor communicatie en samenwerking met Contoso-partners.
- Op VPN'S gebaseerde externe toegang tot het intranet van Contoso en webproxy voor werknemers in het hoofdkantoor van Parijs.

## <a name="contoso-business-needs"></a>Zakelijke behoeften van Contoso

De zakelijke behoeften van Contoso zijn onderverdeeld in vijf hoofdcategorieën:

**Productiviteit**

- Eenvoudiger samenwerken

  Vervang samenwerking op basis van e-mail en bestanden door een onlinemodel waarmee realtime wijzigingen in documenten, eenvoudigere onlinevergaderingen en vastgelegde gespreksthreads mogelijk zijn.
- Verbeter de productiviteit voor externe en mobiele werknemers

  Als veel werknemers thuis of in het veld werken, vervangt u de vpn-oplossing met knelpunten door performant toegang tot Contoso-gegevens en -resources in de cloud.
- Verbeter de creativiteit en innovatie

  Profiteer van de nieuwste visuele leer- en ideeontwikkelingsmethoden, inclusief inkt en 3D-visualisatie.

**Beveiliging**

- Identiteits- en toegangsbeheer

  Dwing multifactor- en andere vormen van verificatie af en bescherm gebruikers- en beheerdersaccountreferenties.

- Bedreigingsbeveiliging

  Bescherm tegen externe beveiligingsdreigingen, waaronder e-mail en op het besturingssysteem gebaseerde malware.

- Gegevensbeveiliging

  Vergrendel de toegang tot en codeer hoogwaardige digitale middelen, zoals klantgegevens, ontwerp- en fabricagespecificaties en werknemersinformatie.

- Beveiligingsbeheer

  Controleer de beveiligingshouding en detecteer en reageer in realtime op bedreigingen.

**Externe en mobiele toegang en zakelijke partners**

- De beveiliging voor externe en mobiele werknemers verbeteren

  Implementeert bring your own device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.

- De infrastructuur voor externe toegang voor werknemers reduceren

  Verminder de kosten voor onderhoud en ondersteuning en verbeter de prestaties voor oplossing voor externe toegang door veelgebruikte resources naar de cloud te verplaatsen.

- Betere connectiviteit en lagere overhead voor B2B-transacties (Business-to-Susiness)

  Vervang een ouder en duur partner extranet door een cloudoplossing die federatief verificatie gebruikt.

**Compliance**

- Voldoen aan regionale wettelijke voorschriften

  Zorg ervoor dat de industrie- en regionale voorschriften voor gegevensopslag, versleuteling, privacy van gegevens en persoonsgegevens worden nageleefd, zoals de Algemene verordening gegevensbescherming (AVG) voor de Europese Unie.

**Beheer**

- Lagere IT-overhead voor het beheren van software die wordt uitgevoerd op client-pc's en -apparaten

  Automatiseer de installatie van updates voor het Windows besturingssysteem en Microsoft 365-apps voor ondernemingen in de hele organisatie.

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a>Contoso-bedrijven toewijzen moet Microsoft 365 voor bedrijven

De IT-afdeling Contoso heeft de volgende toewijzing van bedrijfsbehoeften vastgesteld Microsoft 365 E5 functies vóór de implementatie:


| Categorie | Zakelijke behoefte | Microsoft 365 voor ondernemingsproducten of -functies |
|:-------|:-----|:-----|
| Productiviteit |  |  |
|  | Eenvoudiger samenwerken | Microsoft Teams, SharePoint, OneDrive |
|  | Verbeter de productiviteit voor externe en mobiele werknemers | Werkbelasting en cloud-gebaseerde gegevens voor Microsoft 365 |
|  | Verbeter de creativiteit en innovatie | Windows Ink, Cortana op het werk, PowerPoint |
| Beveiliging |  |  |
|  | Identiteits- en toegangsbeheer | Toegewezen globale beheerdersaccounts met Azure AD Multi-Factor Authentication (MFA) en Azure AD Privileged Identity Management (PIM) <BR> MFA voor alle gebruikersaccounts <BR> Voorwaardelijke toegang <BR> Windows Hello <BR> Windows Credential Guard |
|  | Bedreigingsbeveiliging | Advanced Threat Analytics <BR> Windows Defender <BR> Defender voor Office 365 <BR> Microsoft Defender voor Office 365 <BR> Microsoft 365 bedreigingsonderzoek en -antwoord <BR> |
|  | Gegevensbeveiliging | Azure-gegevensbeveiliging <BR> Preventie van gegevensverlies (DLP, Data Loss Prevention) <BR> Windows-gegevensbescherming (WIP) <BR> Microsoft Cloud App Security <BR> Microsoft Intune |
|  | Beveiligingsbeheer | Azure Defender  <BR> Windows Defender-Beveiligingscentrum |
| Externe en mobiele toegang en zakelijke partners |  |  |
|  | Verbeterde beveiliging voor externe en mobiele werknemers | Microsoft Intune |
|  | De infrastructuur voor externe toegang voor werknemers reduceren | Werkbelasting en cloud-gebaseerde gegevens voor Microsoft 365 |
|  | Connectiviteit en lagere overhead voor B2B-transacties verbeteren | Federatieve verificatie en cloudgebaseerde bronnen |
| Naleving |  |  |
|  | Voldoen aan regionale wettelijke voorschriften | GDPR-functies in Microsoft 365 |
| Beheer |  |  |
|  | Lagere IT-overhead voor het installeren van clientupdates | Updates voor Windows 10 Enterprise <BR> Updates voor Microsoft 365-apps voor ondernemingen |
||||

## <a name="next-step"></a>Volgende stap

Meer informatie over het [on-premises](contoso-networking.md) netwerk van Contoso Corporation en hoe het is geoptimaliseerd voor toegang en latentie om Microsoft 365 cloudbronnen te gebruiken.

## <a name="see-also"></a>Zie ook

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Testlabrichtlijnen](m365-enterprise-test-lab-guides.md)
