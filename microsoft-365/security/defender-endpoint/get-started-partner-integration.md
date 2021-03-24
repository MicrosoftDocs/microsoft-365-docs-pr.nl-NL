---
title: Microsoft Defender voor Eindpunt-partner worden
ms.reviewer: ''
description: Meer informatie over de stappen en vereisten voor het integreren van uw oplossing met Microsoft Defender ATP en partner zijn
keywords: partner, integratie, oplossingsvalidatie, certificering, vereisten, lid, misa, toepassingsportal
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.openlocfilehash: ea7ebe1656c0173395df158b8f934ab388bea4ba
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058353"
---
# <a name="become-a-microsoft-defender-for-endpoint-partner"></a>Microsoft Defender voor Eindpunt-partner worden

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Als u een Defender voor Eindpunt-oplossingspartner wilt worden, moet u de volgende stappen volgen en voltooien.

## <a name="step-1-subscribe-to-a-microsoft-defender-for-endpoint-developer-license"></a>Stap 1: Een abonnement nemen op een licentie voor Ontwikkelaars van Microsoft Defender voor eindpunten
Abonneer u op [de licentie microsoft Defender voor endpoint-ontwikkelaars](https://winatpregistration-prd.trafficmanager.net/Developer/UserAgreement?Length=9). Met een abonnement kunt u een Microsoft Defender for Endpoint-tenant met maximaal 10 apparaten gebruiken om oplossingen te ontwikkelen die zijn geïntegreerd met Microsoft Defender voor Eindpunt. 

## <a name="step-2-fulfill-the-solution-validation-and-certification-requirements"></a>Stap 2: Voldoen aan de vereisten voor validatie en certificering van oplossingen
De beste manier voor technologiepartners om te certificeren dat hun integratie werkt, is door een gezamenlijke klant het voorgestelde integratieontwerp goed te laten keuren (de klant kan de optie Een **partner** aanbevelen gebruiken op de [pagina Partnertoepassing](https://securitycenter.microsoft.com/interoperability/partners) in het Microsoft Defender-beveiligingscentrum) en deze laten testen en degraderen naar het Microsoft Defender voor Eindpunt-team.

Zodra het Microsoft Defender voor Endpoint-team de integratie heeft beoordeeld en goedgekeurd, wordt u door ons doorverbonden als partner bij de Microsoft Intelligent Security Association.

## <a name="step-3-become-a--microsoft-intelligent-security-association-member"></a>Stap 3: Lid worden van microsoft Intelligent Security Association
[Microsoft Intelligent Security Association](https://www.microsoft.com/security/partnerships/intelligent-security-association) is een programma speciaal voor Microsoft-beveiligingspartners om uw beveiligingsproducten te verrijken en de vindbaarheid van uw integraties met Microsoft-beveiligingsproducten te verbeteren.

## <a name="step-4-get-listed-in-the-microsoft-defender-for-endpoint-partner-application-portal"></a>Stap 4: In de microsoft Defender for Endpoint-partnertoepassingsportal worden weergegeven
Microsoft Defender voor Eindpunt ondersteunt detectie en integratie van toepassingen van derden met behulp van de [in-productpartnerpagina](partner-applications.md) die is ingesloten in de Microsoft Defender voor endpoint-beheerportal. 

Als u wilt dat uw bedrijf als partner wordt vermeld op de pagina in-productpartner, moet u de volgende informatie verstrekken:

1. Een vierkant logo (SVG).
2. Naam van het product dat moet worden gepresenteerd.
3. Geef een productbeschrijving van 15 woorden op.
4. Koppeling naar de landingspagina voor de klant om de integratie of blogpost te voltooien die voldoende informatie voor klanten bevat. Elk persbericht, inclusief de productnaam van Microsoft Defender voor Eindpunt, moet worden beoordeeld door de marketing- en technische teams. Wacht ten minste 10 dagen totdat het revisieproces is uitgevoerd.
5.  Als u een Azure AD-benadering met meerdere tenants gebruikt, hebben we de naam van de Azure AD-toepassing nodig om het gebruik van de toepassing bij te houden.
6. Neem het User-Agent veld op in elke API-oproep die wordt gedaan naar openbare API's of Graph-beveiligings-API's van Microsoft Defender voor Eindpunt. Dit wordt gebruikt voor statistische doeleinden, probleemoplossing en partnerherkenning. Bovendien is deze stap een vereiste voor lidmaatschap van Microsoft Intelligent Security Association (MISA).

    Ga als volgt te werk:
    
    - Stel het User-Agent veld in elke HTTP-aanvraagkoptekst in op de onderstaande indeling.

    - `MdePartner-{CompanyName}-{ProductName}/{Version}`
    
    - Bijvoorbeeld: User-Agent: `MdePartner-Contoso-ContosoCognito/1.0.0`
    
    - Zie [RFC 2616 section-14.43](https://tools.ietf.org/html/rfc2616#section-14.43)voor meer informatie.

Samenwerking met Microsoft Defender voor Eindpunt helpt onze gemeenschappelijke klanten om de verdediging verder te stroomlijnen, te integreren en te versterken. We zijn blij dat u ervoor hebt gekozen om een Microsoft Defender for Endpoint-partner te worden en om ons gemeenschappelijke doel van het effectief beschermen van klanten en hun assets te bereiken door samen moderne bedreigingen te voorkomen en erop te reageren.

## <a name="related-topics"></a>Verwante onderwerpen
- [Technische partnerkansen](partner-integration.md)
