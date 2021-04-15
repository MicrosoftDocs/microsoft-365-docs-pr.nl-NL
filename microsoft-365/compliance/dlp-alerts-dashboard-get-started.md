---
title: Aan de slag met het waarschuwingsdashboard voor de preventie van gegevensverlies
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Ga aan de slag met het definiëren en beheren van waarschuwingen voor preventiebeleid voor gegevensverlies.
ms.openlocfilehash: 7f070dd960cc00ad7899c75117cd2a3fcf679973
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51760728"
---
# <a name="get-started-with-the-data-loss-prevention-alert-dashboard"></a>Aan de slag met het waarschuwingsdashboard voor de preventie van gegevensverlies

DLP-beleid (Data Loss Prevention) kan beschermende acties uitvoeren om onbedoeld delen van gevoelige items te voorkomen. Wanneer een actie wordt ondernomen voor een gevoelig item, kunt u een melding krijgen door waarschuwingen voor DLP te configureren. In dit artikel wordt beschreven hoe u beleidsregels voor rich alert kunt definiëren die zijn gekoppeld aan uw DLP-beleid (Data Loss Prevention). U ziet hoe u het [DLP-dashboard](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts) voor waarschuwingsbeheer in het [Microsoft 365-compliancecentrum](https://compliance.microsoft.com/) kunt gebruiken om waarschuwingen, gebeurtenissen en bijbehorende metagegevens voor DLP-beleidsovertredingen weer te geven.

Als U nog geen DLP-waarschuwingen hebt, bekijkt u Meer informatie over het dashboard waarschuwingen [voor preventie van gegevensverlies](dlp-alerts-dashboard-learn.md)

## <a name="before-you-begin"></a>Voordat u begint

Voordat u begint, moet u de benodigde vereisten hebben:

-   Licenties voor het DLP-waarschuwingenbeheerdashboard
-   Licenties voor configuratieopties voor waarschuwingen
-   Rollen

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a>Licenties voor het DLP-waarschuwingsbeheerdashboard

Alle in aanmerking komende tenants voor Office 365 DLP hebben toegang tot het DLP-waarschuwingsbeheerdashboard. Als u wilt beginnen, komt u in aanmerking voor Office 365 DLP voor Exchange Online, SharePoint Online en OneDrive voor Bedrijven. Zie Welke licenties bieden een gebruiker de rechten om te profiteren van de service voor meer informatie over de licentievereisten voor Office 365 [DLP?](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16).

Klanten die [Endpoint DLP gebruiken](endpoint-dlp-learn-about.md) die in aanmerking komen voor [Teams DLP,](dlp-microsoft-teams.md) zien hun waarschuwingen voor DLP-eindpuntbeleid en Teams DLP-beleidswaarschuwingen in het DLP-waarschuwingsbeheerdashboard.

De **functie Inhoudsvoorbeeld** is alleen beschikbaar voor deze licenties:

- Microsoft 365 (E5)
- Office 365 (E5)
- Advanced Compliance (E5) add on
- Microsoft 365 E5/A5 Information Protection and Governance
- Microsft 365 E5/A5 Compliance

### <a name="licensing-for-alert-configuration-options"></a>Licenties voor configuratieopties voor waarschuwingen

Configuratie van een waarschuwing met één gebeurtenis: organisaties met een E1-, F1- of G1-abonnement of een E3- of **G3-abonnement** kunnen alleen waarschuwingsbeleid maken wanneer een waarschuwing wordt geactiveerd telkens wanneer een activiteit plaatsvindt.

**Configuratie van geaggregeerde** waarschuwingen: als u statistisch waarschuwingsbeleid wilt configureren op basis van een drempelwaarde, moet u een van de volgende licentieconfiguraties gebruiken:

- Een E5- of G5-abonnement
- Een E1-, F1- of G1-abonnement of een E3- of G3-abonnement met een van de volgende functies:
    - Office 365 Advanced Threat Protection Plan 2
    - Microsoft 365 E5 Compliance
    - Microsoft 365 eDiscovery- en Audit-invoeglicentie

### <a name="roles"></a>Rollen


Als u het DLP-waarschuwingsbeheerdashboard wilt weergeven of de configuratieopties voor waarschuwingen in een DLP-beleid wilt bewerken, moet u lid zijn van een van deze rollengroepen:

- Compliancebeheerder
- Compliancegegevensbeheerder
- Beveiligingsbeheerder
- Beveiligingsoperator
- Beveiligingslezer

Als u het DLP-dashboard voor waarschuwingsbeheer wilt openen, hebt u het volgende nodig:

- Waarschuwingen beheren

en een van deze twee rollen:

- DLP-compliancebeheer
- View-Only DLP Compliance Management

Als u toegang wilt tot de functie Inhoudsvoorbeeld en de overeenkomende gevoelige inhoud en contextfuncties, moet u lid zijn van:

- Inhoudsverkenner Inhoudsviewer-rollengroep

waarin de rol van de viewer voor gegevensclassificatieinhoud vooraf is toegewezen.

## <a name="dlp-alert-configuration"></a>DLP-waarschuwingsconfiguratie

Zie Waar moet u beginnen met preventie van gegevensverlies voor meer informatie over het configureren van een waarschuwing in [uw DLP-beleid.](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention)

### <a name="aggregate-event-alert-configuration"></a>Configuratie van gebeurteniswaarschuwingen aggregeren

Als uw organisatie is gelicentieerd [voor](#licensing-for-alert-configuration-options)configuratieopties voor samengevoegde waarschuwingen, ziet u deze opties wanneer u een DLP-beleid maakt of bewerkt.

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="Schermafbeelding met opties voor incidentenrapporten voor gebruikers die in aanmerking komen voor statistische configuratieopties voor waarschuwingen." border="false":::

Met deze configuratie kunt u een beleid instellen om een waarschuwing te genereren telkens wanneer een activiteit overeenkomt met de beleidsvoorwaarden of wanneer een bepaalde drempel wordt overschreden, op basis van het aantal activiteiten of op basis van het volume van geëfiltreerde gegevens.

### <a name="single-event-alert-configuration"></a>Configuratie van waarschuwingsgegevens voor één gebeurtenis

Als uw organisatie is gelicentieerd voor configuratieopties voor een waarschuwing voor één gebeurtenis, ziet u deze opties wanneer u een [DLP-beleid](#licensing-for-alert-configuration-options)maakt of bewerkt. Gebruik deze optie om een waarschuwing te maken die telkens wordt verhoogd wanneer een DLP-regel wordt gebruikt.

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="Schermafbeelding met opties voor incidentrapporten voor gebruikers die in aanmerking komen voor configuratieopties voor een waarschuwing voor één gebeurtenis." border="false":::

## <a name="investigate-a-dlp-alert"></a>Een DLP-waarschuwing onderzoeken

Werken met het DLP-dashboard voor waarschuwingsbeheer:

1. Ga in [het Microsoft 365-compliancecentrum](https://www.compliance.microsoft.com)naar **Preventie van gegevensverlies.**
2. Selecteer het **tabblad Waarschuwingen** om het dashboard met DLP-waarschuwingen weer te geven.
3. Selecteer een waarschuwing om details te zien:

:::image type="content" source="../media/alert-details.png" alt-text="Schermafbeelding met waarschuwingsdetails in het DLP-dashboard voor waarschuwingsbeheer." border="false":::

4. Selecteer het **tabblad** Gebeurtenissen om alle gebeurtenissen weer te geven die aan de waarschuwing zijn gekoppeld. U kunt een bepaalde gebeurtenis kiezen om de details ervan weer te geven. Zie Meer informatie over het dashboard Waarschuwingen voor preventie van gegevensverlies voor een lijst met enkele beschikbare [gebeurtenisdetails.](dlp-alerts-dashboard-learn.md)
5. Selecteer **Details** om de pagina **Overzicht voor** de waarschuwing te openen. De overzichtspagina bevat een overzicht:
    1. van wat er is gebeurd
    1. wie de acties heeft uitgevoerd die de beleidsmatch hebben veroorzaakt
    1. informatie over het overeenkomende beleid en meer 

6. Kies het **tabblad Gebeurtenissen** om toegang te krijgen tot het volgende:
    1. betrokken inhoud
    1. overeenkomende typen gevoelige informatie
    1. metagegevens

7. Selecteer het **tabblad Gevoelige infotypen** om details weer te geven over de gevoelige informatietypen die in de inhoud zijn gedetecteerd. Details zijn betrouwbaarheid, aantal en de inhoud die overeenkomt met het gevoelige informatietype.

8. Nadat u de waarschuwing hebt  onderzocht, gaat u terug naar het tabblad Overzicht waar u triage kunt beheren en de positie van de waarschuwing kunt beheren en opmerkingen kunt toevoegen.

- Als u de geschiedenis van werkstroombeheer wilt bekijken, kiest u **Managementlogboek.**
- Nadat u de vereiste actie voor de waarschuwing hebt ondernomen, stelt u de status van de waarschuwing in op **Opgelost.**

## <a name="see-also"></a>Zie ook

- [Meer informatie over waarschuwingen voor preventie van gegevensverlies en het dashboard waarschuwingen](dlp-alerts-dashboard-learn.md)
- [Een DLP-beleid maken, testen en afstemmen](create-test-tune-dlp-policy.md)