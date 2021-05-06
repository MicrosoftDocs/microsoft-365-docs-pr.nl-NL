---
title: Intern risicobeheer plannen
description: Meer informatie over het plannen van beleidsregels voor insiderrisicobeheer in uw organisatie.
keywords: Microsoft 365, insider risk, risk management, compliance
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 8cd9e9a72cd7643238d118fe0aed519db9159470
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "52161728"
---
# <a name="plan-for-insider-risk-management"></a>Intern risicobeheer plannen

Voordat u aan de slag gaat met [insider risk management](insider-risk-management.md) in uw organisatie, zijn er belangrijke planningsactiviteiten en overwegingen die moeten worden beoordeeld door uw informatietechnologie- en compliancebeheerteams. Als u de implementatie op de volgende gebieden grondig begrijpt en plant, zorgt u ervoor dat de implementatie en het gebruik van functies voor insiderrisicobeheer soepel verloopt en wordt afgestemd op de best practices voor de oplossing.

## <a name="work-with-stakeholders-in-your-organization"></a>Werken met belanghebbenden in uw organisatie

Identificeer de juiste belanghebbenden in uw organisatie om samen te werken voor het uitvoeren van acties op waarschuwingen en gevallen voor insiderrisicobeheer. Sommige aanbevolen belanghebbenden die moeten overwegen om de [](insider-risk-management.md#workflow) initiële planning en de end-to-end insider-werkstroom voor risicobeheer op te nemen, zijn personen uit de volgende gebieden van uw organisatie:

- Informatietechnologie
- Compliance
- Privacy
- Beveiliging
- Personeelszaken
- Wettelijk

## <a name="determine-any-regional-compliance-requirements"></a>Eventuele vereisten voor regionale naleving bepalen

Verschillende geografische en organisatiegebieden kunnen nalevings- en privacyvereisten hebben die verschillen van andere gebieden van uw organisatie. Werk samen met de belanghebbenden op deze gebieden om ervoor te zorgen dat ze de nalevings- en privacybesturingselementen in insiderrisicobeheer begrijpen en hoe ze moeten worden gebruikt op verschillende gebieden van uw organisatie. In sommige scenario's kunnen nalevings- en privacyvereisten beleid vereisen dat bepaalde belanghebbenden aanwijzen of beperken van onderzoeken en gevallen op basis van het geval voor een gebruiker of wettelijke of beleidsvereisten voor het gebied.

Als u vereisten hebt voor specifieke belanghebbenden om betrokken te zijn bij gevalonderzoeken waarbij gebruikers betrokken zijn in bepaalde regio's, rollen of afdelingen, kunt u afzonderlijk (zelfs indien [identiek)](insider-risk-management-policies.md) beleid voor insider-risicobeheer implementeren dat is gericht op de verschillende regio's en populaties. Met deze configuratie kunnen de juiste belanghebbenden gemakkelijker zaken beheren die relevant zijn voor hun rollen en regio's. Daarnaast kunt u overwegen processen en beleid te maken voor regio's waar onderzoeker en revisoren dezelfde taal spreken als de gebruikers om het escalatieproces voor waarschuwingen en gevallen voor insiderrisicobeheer te stroomlijnen.

## <a name="plan-for-the-review-and-investigation-workflow"></a>De controle- en onderzoekswerkstroom plannen

Selecteer speciale belanghebbenden om de waarschuwingen en gevallen op een regelmatige tijdsfrequentie in het Microsoft 365 [controleren.](https://compliance.microsoft.com/) Zorg ervoor dat u begrijpt hoe u verschillende belanghebbenden toewijst aan de verschillende rollengroepen die beschikbaar zijn in insider risk management.

Afhankelijk van de structuur van uw compliancebeheerteam hebt u opties om gebruikers toe te wijzen aan specifieke rollengroepen om verschillende sets functies voor insiderrisicobeheer te beheren. Als u  het tabblad Machtigingen wilt weergeven in het Office 365 Beveiligings- & Compliancecentrum en rollengroepen wilt beheren, moet u zijn toegewezen aan de rollengroep Organisatiebeheer of moet u de rol Rollenbeheer *toegewezen* krijgen.  Kies uit deze opties voor rollengroep bij het configureren van insiderrisicobeheer:

| **Rollengroep** | **Rolmachtigingen** |
| :------------- | :------------------- |
| **Insider Risk Management** | Gebruik deze rollengroep om insiderrisicobeheer voor uw organisatie in één groep te beheren. Door alle gebruikersaccounts toe te voegen voor aangewezen beheerders, analisten, onderzoekers en auditors, kunt u machtigingen voor insiderrisicobeheer configureren in één groep. Deze rollengroep bevat alle machtigingen voor insiderrisicobeheer en bijbehorende machtigingen. Deze configuratie is de eenvoudigste manier om snel aan de slag te gaan met insider risk management en is geschikt voor organisaties die geen afzonderlijke machtigingen nodig hebben die zijn gedefinieerd voor afzonderlijke groepen gebruikers. |
| **Insider Risk Management Admin** | Gebruik deze rollengroep om in eerste instantie insiderrisicobeheer te configureren en later om beheerders van insiderrisico's te scheiden in een gedefinieerde groep. Gebruikers in deze rollengroep kunnen analyseinzichten in- en weergeven en insiderrisicobeheerbeleid, globale instellingen en rolgroeptoewijzingen maken, lezen, bijwerken en verwijderen. |
| **Analist intern risicobeheer** | Gebruik deze groep om machtigingen toe te wijzen aan gebruikers die fungeren als insiderrisicocaseanalisten. Gebruikers in deze rollengroep hebben toegang tot alle insiderrisicobeheerwaarschuwingen, cases, analyseinzichten en kennisgevingssjablonen. Ze hebben geen toegang tot het insiderrisico Inhoudsverkenner. |
| **Onderzoeker intern risicobeheer** | Gebruik deze groep om machtigingen toe te wijzen aan gebruikers die fungeren als insider-risicogegevensonderzoekers. Gebruikers in deze rollengroep hebben toegang tot alle waarschuwingen voor insiderrisicobeheer, cases, kennisgevingssjablonen en de Inhoudsverkenner voor alle gevallen. |
| **Insider Risk Management Auditors** | Gebruik deze groep om machtigingen toe te wijzen aan gebruikers die activiteiten voor insiderrisicobeheer controleren. Gebruikers in deze rollengroep hebben toegang tot het auditlogboek voor insiderrisico's. |

## <a name="understand-requirements-and-dependencies"></a>Vereisten en afhankelijkheden begrijpen

Afhankelijk van de manier waarop u beleid voor insiderrisicobeheer wilt implementeren, moet u over de juiste Microsoft 365 licenties en inzicht hebben in en plannen voor bepaalde vereisten voor oplossingen.

**Licenties:** Insider risk management is beschikbaar als onderdeel van een uitgebreide selectie Microsoft 365 licenties. Zie het artikel Aan [de slag met insider risk management voor meer](insider-risk-management-configure.md#subscriptions-and-licensing) informatie.

Als u geen bestaand Microsoft 365 Enterprise E5-abonnement hebt en insider risk management wilt proberen, kunt u [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) toevoegen aan uw bestaande abonnement [of](https://www.microsoft.com/microsoft-365/enterprise) u registreren voor een proefabonnement op Microsoft 365 Enterprise E5.

**Vereisten voor beleidssjabloon:** Afhankelijk van de beleidssjabloon die u kiest, zijn er vereisten die u moet begrijpen en plannen voordat u insider risk management in uw organisatie configureert:

- Wanneer u de sjabloon **Gegevensdiefstal** door vertrekkende gebruikers gebruikt, moet u een Microsoft 365 HR-connector configureren om regelmatig informatie over afzegging en beëindigingsdatum te importeren voor gebruikers in uw organisatie. Zie het [artikel Gegevens importeren met het HR-connectorartikel](import-hr-data.md) voor stapsgewijs richtlijnen voor het configureren van de Microsoft 365 HR-connector voor uw organisatie.
- Wanneer u **gegevenslekkensjablonen** gebruikt, moet u ten minste één DLP-beleid (Data Loss Prevention) configureren om gevoelige informatie in uw organisatie te definiëren en insiderrisicowaarschuwingen te ontvangen voor DLP-beleidswaarschuwingen met hoge ernst. Zie het [artikel DLP-beleid maken,](create-test-tune-dlp-policy.md) testen en afstemmen voor stapsgewijs richtlijnen voor het configureren van DLP-beleid voor uw organisatie.
- Wanneer u **sjablonen voor beveiligingsbeleidsovertreding** gebruikt, moet u Microsoft Defender voor Eindpunt inschakelen voor integratie van insiderrisicobeheer in het Defender-beveiligingscentrum om waarschuwingen voor beveiligingsovertreding te importeren. Zie het [artikel Geavanceerde functies configureren in Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/advanced-features) voor stapsgewijs richtlijnen voor het inschakelen van Defender voor endpoint-integratie met insiderrisicobeheer.
- Wanneer u **ontevreden gebruikerssjablonen** gebruikt, moet u een Microsoft 365 HR-connector configureren om regelmatig prestatie- of degradatiestatusgegevens te importeren voor gebruikers in uw organisatie. Zie het [artikel Gegevens importeren met het HR-connectorartikel](import-hr-data.md) voor stapsgewijs richtlijnen voor het configureren van de Microsoft 365 HR-connector voor uw organisatie.

## <a name="test-with-a-small-group-of-users-in-a-production-environment"></a>Testen met een kleine groep gebruikers in een productieomgeving

Voordat u de oplossing breed in uw productieomgeving inschakelen, kunt u overwegen het beleid te testen met een kleine set productiegebruikers terwijl u de benodigde naleving, privacy en juridische controle in uw organisatie voert. Als u insiderrisicobeheer in een testomgeving evalueert, moet u gesimuleerde gebruikersacties en andere signalen genereren om waarschuwingen te maken voor triage en gevallen voor verwerking. Deze methode is niet praktisch voor de meeste organisaties, dus het testen van insiderrisicobeheer met een kleine groep gebruikers in een productieomgeving heeft de voorkeur.

Houd de anonimisatiefunctie in beleidsinstellingen ingeschakeld om gebruikersweergavenamen in de insider risk management console te anonimiseren tijdens deze tests om de privacy binnen het hulpprogramma te behouden. Deze instelling helpt de privacy te beschermen van gebruikers met beleidswedstrijden en kan objectiviteit in gegevensonderzoeks- en analysebeoordelingen voor waarschuwingen voor insiderrisico's helpen bevorderen.

Als u geen waarschuwingen ziet direct na het configureren van een beleid voor insiderrisicobeheer, kan dit betekenen dat de minimale risicodrempel nog niet is bereikt. Een goede manier om te controleren of het beleid is geactiveerd en werkt zoals verwacht, is om te zien of de gebruiker binnen bereik is voor het beleid op de pagina **Gebruikers.**

## <a name="resources-for-stakeholders"></a>Resources voor belanghebbenden

Deel documentatie voor insiderrisicobeheer met de belanghebbenden in uw organisatie die zijn opgenomen in uw beheer- en herstelwerkstroom:

- [Intern risicobeleid maken en beheren](insider-risk-management-policies.md)
- [Waarschuwingen voor insider-risico onderzoeken](insider-risk-management-alerts.md)
- [Actie ondernemen in het geval van insider-risico](insider-risk-management-cases.md)
- [Casegegevens controleren met het insiderrisico Inhoudsverkenner](insider-risk-management-content-explorer.md)
- [Kennisgevingssjablonen voor insider-risico maken](insider-risk-management-notices.md)

## <a name="ready-to-get-started"></a>Klaar om aan de slag te gaan?

Wilt u insider risk management configureren voor uw organisatie? Bekijk de volgende artikelen:

- [Ga aan de slag met insider-instellingen voor risicobeheer om](insider-risk-management-settings.md) globale beleidsinstellingen te configureren.
- [Ga aan de slag met insider risk management om](insider-risk-management-configure.md) vereisten te configureren, beleid te maken en waarschuwingen te ontvangen.
