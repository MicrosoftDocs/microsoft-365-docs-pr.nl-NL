---
title: Aan de slag met recordbeheer in Microsoft 365
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Hebt u een oplossing voor recordbeheer nodig voor Microsoft 365 die inhoud van hoge waarde beheert voor juridische, zakelijke of wettelijke verplichtingen, maar niet zeker weet waar u moet beginnen? Lees enkele praktische richtlijnen om aan de slag te gaan.
ms.openlocfilehash: 2ab5eaa494094dcbf0723f426fcbd644901c22bb
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "52162286"
---
# <a name="get-started-with-records-management"></a>Aan de slag met recordbeheer

>*[Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Klaar om te beginnen met het beheren van de inhoud van hoge waarde van uw organisatie voor juridische, zakelijke of wettelijke verplichtingen door gebruik te maken van een oplossing voor recordbeheer in Microsoft 365? Gebruik de volgende richtlijnen op hoog niveau om aan de slag te gaan:

1. **Informatie over de oplossing voor recordbeheer** en welke acties zijn toegestaan of geblokkeerd wanneer documenten en e-mailberichten worden gedeclareerd als records: [Meer informatie over recordbeheer](records-management.md). 

2. **Meer informatie over retentielabels en hoe retentie werkt** voor SharePoint en Exchange, omdat retentielabels worden gebruikt om records te declareren: [Meer informatie over retentiebeleid en retentielabels](retention.md)

3. **Maak uw bestandsplan voor bewaarinstellingen en -acties** door [een bestaand plan te importeren](file-plan-manager.md#import-retention-labels-into-your-file-plan ) als u er een hebt, of [nieuwe retentielabels te maken om als records te declareren](declare-records.md).

4. **Uw retentielabels publiceren en toepassen**. Retentielabels zijn herbruikbare bouwstenen die kunnen worden gebruikt in meerdere beleidsregels en kunnen worden opgenomen in gebruikerswerkstromen: 
    
    - [Retentielabels maken en deze toepassen in apps](create-apply-retention-labels.md)
    - [Een retentielabel automatisch toepassen op inhoud](apply-retention-labels-automatically.md)

## <a name="subscription-and-licensing-requirements-for-records-management"></a>Abonnements- en licentievereisten voor recordbeheer

Een aantal verschillende abonnementen ondersteunen recordbeheer en de licentievereisten voor gebruikers zijn afhankelijk van de functies die u gebruikt.

Zie de [Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance) om de opties te zien voor de licentieverlening aan uw gebruikers om voordeel te halen uit de functies van Microsoft 365-compliance. Zie voor recordbeheer de sectie [Records Management](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#records-management) en een gerelateerde PDF- of Excel-download voor licentievereisten op functieniveau.

## <a name="permissions-required-for-records-management"></a>Machtigingen vereist voor recordbeheer

Leden van uw complianceteam die verantwoordelijk zijn voor recordbeheer hebben machtigingen nodig voor het [Microsoft 365-compliancecentrum](https://compliance.microsoft.com/). Standaard heeft de tenantbeheerder (globale beheerder) toegang tot deze locatie en kan deze compliance officers en andere personen toegang verlenen zonder hen alle machtigingen van een tenantbeheerder te geven. Als u machtigingen wilt verlenen voor dit beperkte beheer, raden we u aan gebruikers toe te voegen aan de beheerdersrolgroep **Records Management**, die machtigingen verleent voor alle functies die betrekking hebben op recordbeheer, waaronder [verwijderingsbeoordeling en verificatie](disposition.md). 

Voor een alleen-lezen rol kunt u een nieuwe rollengroep maken en de rol **Recordbeheer alleen-weergeven** aan deze groep toevoegen. 

Zie [Machtigingen in het Beveiligings- en compliancecentrum](../security/defender-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center) voor meer informatie over rolgroepen en rollen.

Zie [Gebruikers toegang geven tot het Beveiligings- en compliancecentrum](../security/defender-365-security/grant-access-to-the-security-and-compliance-center.md) voor instructies om gebruikers aan rolgroepen toe te voegen en rollen toe te wijzen.

Deze machtigingen zijn alleen vereist om retentielabels te maken, te configureren en toe te passen voor het declareren van records, en om de verwijdering te beheren. De persoon die deze labels configureert, heeft geen toegang tot de inhoud nodig.

## <a name="common-scenarios-for-records-management"></a>Veelvoorkomende scenario's voor recordbeheer

Gebruik de volgende tabel om uw zakelijke vereisten toe te passen op scenario's die worden ondersteund door recordbeheer.

> [!NOTE]
> Aangezien recordbeheer gebruikmaakt van retentielabels om een item als een record te markeren, worden veel scenario's in deze tabel ook weergegeven als [veelvoorkomende scenario's voor retentiebeleid en retentielabels](get-started-with-retention.md#common-scenarios-for-retention-policies-and-retention-labels).

|Ik wil het volgende doen|Documentatie|
|----------------|---------------|
|Een record declareren |[Records declareren met behulp van retentielabels](declare-records.md)|
|Een record bijwerken |[Versiebeheer van records gebruiken om records bij te werken die zijn opgeslagen in SharePoint of OneDrive](record-versioning.md)|
|Beheerders en gebruikers handmatig acties voor documenten en e-mailberichten laten toepassen en verwijderen: <br />-  SharePoint <br />- OneDrive <br />- Outlook en Outlook op het web|[Retentielabels maken en deze toepassen in apps](create-apply-retention-labels.md)|
|Sitebeheerders de standaardacties laten instellen voor het bewaren en verwijderen van alle inhoud in een SharePoint-bibliotheek, -map of -documentenset|[Retentielabels maken en deze toepassen in apps](create-apply-retention-labels.md)|
|Gebruikers automatisch acties laten toepassen voor het bewaren en verwijderen op e-mailberichten met behulp van Outlook-regels|[Retentielabels maken en deze toepassen in apps](create-apply-retention-labels.md)|
|Beheerders acties laten toepassen op een model voor documentbegrip en deze verwijderen, zodat deze automatisch worden toegepast op geïdentificeerde documenten in een SharePoint-bibliotheek|[Retentielabels maken en deze toepassen in apps](create-apply-retention-labels.md)|
|Automatisch acties voor bewaren en verwijderen toepassen op documenten en e-mailberichten |[Een retentielabel automatisch toepassen op inhoud](apply-retention-labels-automatically.md)|
|De retentieperiode starten wanneer een gebeurtenis plaatsvindt, zoals:  <br />- Werknemers verlaten de organisatie <br />- Contracten verlopen <br />- Einde productleven| [Retentie starten als zich een gebeurtenis voordoet](event-driven-retention.md)|
|Wijzigingen in beleid beperken om te voldoen aan wettelijke vereisten of beveiliging tegen malafide beheerders| [Behoudvergrendeling gebruiken om wijzigingen in retentiebeleid en retentielabelbeleid te beperken](retention-preservation-lock.md)
|De levenscyclus van verschillende documenttypen beheren in SharePoint| [Retentielabels gebruiken om de levenscyclus van in SharePoint opgeslagen documenten te beheren](auto-apply-retention-labels-scenario.md)|
|Zorg ervoor dat iemand beoordeelt en goedkeurt voordat inhoud wordt verwijderd aan het einde van de retentieperiode|[Verwijderingsbeoordelingen](disposition.md#disposition-reviews) |
|Bewijs van verwijderen van inhoud die definitief wordt verwijderd aan het einde van de retentieperiode|[Verwijdering van records](disposition.md#disposition-of-records) |
| Controleren hoe en waar instellingen voor behouden en verwijderen op items worden toegepast | [Controleren van retentielabels](retention.md#monitoring-retention-labels) |

## <a name="end-user-documentation-for-records"></a>Documentatie voor eindgebruikers voor records

Retentielabels die worden gebruikt voor recordbeheer zijn aanwezig in de gebruikersinterface in Microsoft 365-apps. Zorg ervoor dat u richtlijnen biedt voor eindgebruikers en uw helpdesk voordat u retentielabels implementeert in uw productienetwerk.

De meest effectieve documentatie voor eindgebruikers wordt aangepast en u geeft instructies voor de namen en configuraties van retentielabels die u kiest. Zie het volgende bericht voor een downloadpakket dat u kunt gebruiken om gebruikers te trainen en ingebruikname te stimuleren: [Training van eindgebruikers voor retentielabels in M365 – Hoe kunt u uw ingebruikname versnellen?](https://techcommunity.microsoft.com/t5/microsoft-security-and/end-user-training-for-retention-labels-in-m365-how-to-accelerate/ba-p/1750861).

In de volgende sectie vindt u ook basisinstructies voor gebruikers: [Handmatig toepassen van retentielabels](create-apply-retention-labels.md#manually-apply-retention-labels).