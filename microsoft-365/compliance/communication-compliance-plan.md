---
title: Communicatiecompliance plannen
description: Meer informatie over het plannen van communicatie compliance in uw organisatie.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: d64edc9d80722080db18c45127bfc82110d1ea9e
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/18/2020
ms.locfileid: "52161521"
---
# <a name="plan-for-communication-compliance"></a>Communicatiecompliance plannen

Voordat u aan [de](communication-compliance.md) slag gaat met communicatie compliance in uw organisatie, zijn er belangrijke planningsactiviteiten en overwegingen die moeten worden beoordeeld door uw informatietechnologie- en compliancebeheerteams. Als u de implementatie op de volgende gebieden grondig begrijpt en plant, zorgt u ervoor dat de implementatie en het gebruik van communicatie compliance-functies soepel verloopt en wordt afgestemd op de best practices voor de oplossing.

## <a name="work-with-stakeholders-in-your-organization"></a>Werken met belanghebbenden in uw organisatie

Identificeer de juiste belanghebbenden in uw organisatie om samen te werken voor het uitvoeren van acties op het gebied van waarschuwingen voor communicatie compliance. Sommige aanbevolen belanghebbenden die rekening moeten houden met de initiële planning en de end-to-end communicatie [compliance-werkstroom](communication-compliance.md#workflow) zijn personen uit de volgende gebieden van uw organisatie:

- Informatietechnologie
- Compliance
- Privacy
- Beveiliging
- Personeelszaken
- Juridisch

## <a name="plan-for-the-investigation-and-remediation-workflow"></a>De werkstroom voor onderzoek en herstel plannen

Selecteer speciale belanghebbenden om de waarschuwingen en gevallen op een regelmatige tijdsfrequentie in het Microsoft 365 [controleren.](https://compliance.microsoft.com/) Zorg ervoor dat u begrijpt hoe u gebruikers en belanghebbenden toewijst aan verschillende rollengroepen voor communicatie compliance in uw organisatie.

Afhankelijk van hoe u communicatiebeleid en waarschuwingen wilt beheren, moet u gebruikers toewijzen aan een of meer rollengroepen voor beheerders, revisoren en onderzoeker. U hebt de optie om gebruikers toe te wijzen aan specifieke rollengroepen om verschillende sets communicatie-compliancefuncties te beheren. Of u kunt besluiten om alle communicatie-compliancegebruikers toe te wijzen aan de rolgroep Communicatie compliance. Gebruik één rollengroep of meerdere groepen om het beste aan uw vereisten voor compliancebeheer te voldoen.

Plan een keuze uit deze opties voor rollengroep bij het configureren van communicatie compliance:

|**Rol**|**Rolmachtigingen**|
|:-----|:-----|
| **Naleving van communicatie** | Gebruik deze rollengroep om communicatie compliance voor uw organisatie in één groep te beheren. Door alle gebruikersaccounts toe te voegen voor aangewezen beheerders, analisten, onderzoeker en kijkers, kunt u communicatie compliancemachtigingen configureren in één groep. Deze rollengroep bevat alle machtigingsrollen voor communicatie compliance. Deze configuratie is de eenvoudigste manier om snel aan de slag te gaan met communicatie-compliance en is geschikt voor organisaties die geen afzonderlijke machtigingen nodig hebben die zijn gedefinieerd voor afzonderlijke groepen gebruikers. |
| **Communicatie compliancebeheerder** | Gebruik deze rollengroep om communicatie compliance in eerste instantie te configureren en later om beheerders van communicatie compliance te scheiden in een gedefinieerde groep. Gebruikers die aan deze rollengroep zijn toegewezen, kunnen communicatie compliancebeleid, globale instellingen en toewijzingen voor rollengroepen maken, lezen, bijwerken en verwijderen. Gebruikers die aan deze rollengroep zijn toegewezen, kunnen geen berichtwaarschuwingen weergeven. |
| **Communicatie compliance-analist** | Gebruik deze groep om machtigingen toe te wijzen aan gebruikers die fungeren als communicatie-complianceanalisten. Gebruikers die aan deze rollengroep zijn toegewezen, kunnen beleid weergeven waarin ze zijn toegewezen als revisoren, metagegevens van berichten weergeven (geen berichtinhoud), escaleren naar extra revisoren of meldingen verzenden naar gebruikers. Analisten kunnen waarschuwingen in behandeling niet oplossen. |
| **Communicatie compliance-onderzoeker** | Gebruik deze groep om machtigingen toe te wijzen aan gebruikers die fungeren als communicatie compliance-onderzoeker. Gebruikers die aan deze rollengroep zijn toegewezen, kunnen metagegevens en inhoud van berichten bekijken, escaleren naar extra revisoren, escaleren naar een Advanced eDiscovery-geval, meldingen naar gebruikers verzenden en de waarschuwing oplossen. |
| **Viewer voor communicatie compliance** | Gebruik deze groep om machtigingen toe te wijzen aan gebruikers die communicatierapporten beheren. Gebruikers die aan deze rollengroep zijn toegewezen, hebben toegang tot alle rapportagewidgets op de startpagina communicatie compliance en kunnen alle communicatie compliancerapporten bekijken. |

## <a name="plan-for-policies"></a>Beleid plannen

Het maken van communicatie compliancebeleid is snel en eenvoudig met de vooraf gedefinieerde [sjablonen](communication-compliance-feature-reference.md#policy-templates) voor aanstootgevende taal, gevoelige informatie en naleving van regelgeving. Aangepaste communicatie compliancebeleid biedt de flexibiliteit voor het opsporen en onderzoeken van problemen die specifiek zijn voor uw organisatie en vereisten.

Houd bij het plannen van communicatie compliancebeleid rekening met de volgende gebieden:

- Overweeg om alle gebruikers in uw organisatie toe te voegen als in-scope voor uw communicatie compliancebeleid. Het identificeren van specifieke gebruikers als in-scope voor afzonderlijke beleidsregels is in sommige gevallen handig, maar de meeste organisaties moeten alle gebruikers opnemen in communicatie compliancebeleid dat is geoptimaliseerd voor pesterijen of detectie van onderscheid.
- Als u de installatie wilt vereenvoudigen, kunt u overwegen groepen te maken voor personen die hun communicatie moeten herzien. Als u groepen gebruikt; mogelijk hebt u er meerdere nodig. Als u bijvoorbeeld de communicatie tussen twee verschillende groepen personen wilt scannen of als u een groep wilt opgeven die niet onder toezicht staat.
- Configureer het percentage van de communicatie dat moet worden beoordeeld op 100% om ervoor te zorgen dat beleid alle aandachtspunten in communicatie voor uw organisatie opsneert.
- U kunt communicatie van externe bronnen [scannen](communication-compliance-feature-reference.md#supported-communication-types) op gegevens die zijn geïmporteerd in postvakken in uw Microsoft 365 organisatie. Als u de controle van communicatie in deze platforms wilt opnemen, moet u een verbindingslijn voor deze services configureren voordat de voorwaarden voor berichtenvergaderingen worden gecontroleerd door communicatiebeleid.
- Beleid kan ondersteuning bieden voor het controleren van andere talen dan het Engels in aangepaste communicatiebeleidsregels. Maak een [aangepaste woordenlijst met](communication-compliance-feature-reference.md#custom-keyword-dictionaries) aanstootgevende woorden in de taal van uw keuze of bouw uw eigen machine-learningmodel met behulp van [trainbare](classifier-get-started-with.md) classificaties in Microsoft 365.
- Alle organisaties hebben verschillende communicatiestandaarden en beleidsbehoeften. Controleer op specifieke trefwoorden met behulp van [compliancevoorwaarden](communication-compliance-feature-reference.md#conditional-settings) voor communicatie of controleer op specifieke soorten informatie met [aangepaste gevoelige informatietypen.](create-a-custom-sensitive-information-type.md)

## <a name="ready-to-get-started"></a>Klaar om aan de slag te gaan?

Zie Communicatie compliance configureren voor Microsoft 365 [of](communication-compliance-configure.md) bekijk de case study voor [Contoso](communication-compliance-case-study.md) en hoe ze snel een communicatie compliancebeleid hebben geconfigureerd om te controleren op aanstootgevende taal in Microsoft Teams, Exchange Online en Yammer communicatie. Microsoft 365
