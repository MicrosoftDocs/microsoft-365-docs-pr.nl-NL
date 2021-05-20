---
title: Complianceopties voor Microsoft 365 groepen, Teams en SharePoint samenwerking
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: Meer informatie over complianceopties voor Microsoft 365 groepen, Teams en SharePoint samenwerking.
ms.openlocfilehash: 236b977b22066830e1b36bc87676fd5fa2c9d3f5
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538121"
---
# <a name="compliance-options-for-microsoft-365-groups-teams-and-sharepoint-collaboration"></a>Complianceopties voor Microsoft 365 groepen, Teams en SharePoint samenwerking

Microsoft 365 biedt een volledige reeks hulpprogramma's om naleving te behouden terwijl uw gebruikers samenwerken. Bekijk deze opties en bedenk hoe deze worden toe te schrijven aan uw zakelijke behoeften, de gevoeligheid van uw gegevens en het bereik van personen met wie uw gebruikers moeten samenwerken.

De volgende tabel bevat een beknopt overzicht van de nalevingsbesturingselementen die beschikbaar zijn in Microsoft 365. Meer informatie vindt u in de volgende secties.

|Categorie|Omschrijving|Verwijzing|
|:-------|:----------|:--------|
|Bewaargegevens|||
||Groepen e-mail en SharePoint behouden|[Meer informatie over bewaarbeleid voor SharePoint en OneDrive](../compliance/retention-policies-sharepoint.md)|
||Chat en berichten behouden|[Meer informatie over bewaarbeleid voor Microsoft Teams](../compliance/retention-policies-teams.md)|
|Informatieclassificatie|||
||Groepen en teams classificeren|[Vertrouwelijkheidslabels gebruiken om inhoud te beveiligen in Microsoft Teams, Microsoft 365 Groepen en SharePoint-sites](../compliance/sensitivity-labels-teams-groups-sites.md)|
||Gevoelige inhoud automatisch classificeren|[Een vertrouwelijkheidslabel automatisch op inhoud toepassen](../compliance/apply-sensitivity-label-automatically.md)|
||Gevoelige inhoud versleutelen|[Toegang tot inhoud beperken door versleuteling toe te passen met vertrouwelijkheidslabels](../compliance/encryption-sensitivity-labels.md)|
|Gegevensbescherming|||
||Voorkomen dat gevoelige informatie verloren gaat|[Meer informatie over preventie van gegevensverlies](../compliance/dlp-learn-about-dlp.md)|
||Bescherm gevoelige informatie in een chatgesprek.|[Preventie en preventie van gegevensverlies Microsoft Teams](../compliance/dlp-microsoft-teams.md)|
||De gevoelige informatie van uw organisatie definiëren|[Aangepaste typen gevoelige informatie](../compliance/sensitive-information-type-learn-about.md)|
|Gebruikerssegmentatie|||
||Communicatie tussen gebruikerssegmenten beperken|[Informatiebelemmeringen](../compliance/information-barriers.md)|
|Data-ingezetenschap|||
||Gegevens opslaan op specifieke geografische locaties|[Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo)|

## <a name="information-retention"></a>Bewaargegevens

Bewaarbeleid is beschikbaar voor het behouden of verwijderen van items die worden gebruikt voor samenwerking in groepen en teams, zoals bestanden, berichten en e-mail. Beleidsregels kunnen worden ingesteld op behouden en verwijderen, alleen behouden of alleen verwijderen. Gegevens die onder een bewaarbeleid vallen, worden beveiligd als de groep of het team verloopt of anderszins wordt verwijderd.

Het configureren van een bewaarbeleid voor Microsoft 365 Groepen heeft betrekking op het groepspostvak en de bijbehorende SharePoint site en bestanden.

- [Meer informatie over bewaarbeleid voor SharePoint en OneDrive](../compliance/retention-policies-sharepoint.md)

Bewaarbeleid voor Teams chat- en kanaalberichten behouden. Hoewel chat- en kanaalberichten worden opgeslagen in Exchange postvakken, worden ze niet beïnvloed door Exchange bewaarbeleid. U moet uw bewaarbeleid zo instellen dat dit van toepassing is Teams chats en Teams kanaalberichten. 

Gebruikerschats worden voor onbepaalde tijd bewaard, zelfs als een gebruikersaccount wordt verwijderd. Als u deze gegevens niet voor onbepaalde tijd wilt bewaren, kunt u overwegen een bewaarbeleid te gebruiken om gebruikerschats na een bepaalde tijd te verwijderen of deze verwijdering op te nemen in het verwijderingsproces van de gebruiker.

- [Meer informatie over bewaarbeleid voor Microsoft Teams](../compliance/retention-policies-teams.md)

- [Bewaarbeleid in Microsoft Teams](/microsoftteams/retention-policies)

Er kan één bewaarbeleid worden ingesteld om van toepassing te zijn op Teams chatberichten en Teams kanaalberichten. 

Aanvullende informatiebronnen:

- [Overzicht van bewaarbeleid](../compliance/retention.md)

- [Bewaarlabels en bewaarbeleid](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies) in Exchange

## <a name="information-classification"></a>Informatieclassificatie

U kunt gevoeligheidslabels gebruiken voor gasttoegang, groeps- en team privacy en toegang via niet-beheerde apparaten voor groepen en teams. Door het label toe te passen, worden deze instellingen automatisch geconfigureerd volgens de labelinstellingen.

- [Vertrouwelijkheidslabels gebruiken om inhoud te beveiligen in Microsoft Teams, Microsoft 365 Groepen en SharePoint-sites](../compliance/sensitivity-labels-teams-groups-sites.md)

U kunt Microsoft 365 configureren om gevoeligheidslabels automatisch toe te passen op bestanden en e-mailberichten op basis van de criteria die u opgeeft, inclusief het detecteren van gevoelige informatietypen of patronen die overeenkomen met trainbare classificaties.

- [Een vertrouwelijkheidslabel automatisch op inhoud toepassen](../compliance/apply-sensitivity-label-automatically.md)

U kunt gevoeligheidslabels gebruiken om bestanden te versleutelen, zodat alleen personen met machtigingen ze kunnen ontsleutelen en lezen.

- [Toegang tot inhoud beperken door versleuteling toe te passen met vertrouwelijkheidslabels](../compliance/encryption-sensitivity-labels.md)

- [Een team configureren met beveiligingsisolatie](./secure-teams-security-isolation.md)

Aanvullende informatiebronnen:

- [Meer informatie over vertrouwelijkheidslabels](../compliance/sensitivity-labels.md)


## <a name="information-protection"></a>Gegevensbescherming

Met DLP-beleid kunt u voorkomen dat gevoelige informatie per ongeluk wordt gedeeld SharePoint, Exchange en Teams. U kunt beleidsregels maken waarin acties worden opgegeven die moeten worden ondernomen (zoals het blokkeren van toegang) op basis van een set regels.

- [Meer informatie over preventie van gegevensverlies](../compliance/dlp-learn-about-dlp.md)

DLP in Teams kan helpen bij het beveiligen van gevoelige informatie in Teams chat- en kanaalberichten door berichten te verwijderen die gevoelige informatie bevatten.

- [Preventie en preventie van gegevensverlies Microsoft Teams](../compliance/dlp-microsoft-teams.md)

Als u gevoelige informatie hebt die uniek is voor uw organisatie, zoals projectcodenamen, kunt u uw eigen typen gevoelige informatie maken en deze toepassen op DLP-beleid om inhoud in groepen, teams en Sharepoint te beveiligen.

- [Aangepaste typen gevoelige informatie](../compliance/sensitive-information-type-learn-about.md)

## <a name="user-segmentation"></a>Gebruikerssegmentatie

Met informatiebarrières kunt u uw gegevens en gebruikers segmenteren om ongewenste communicatie en samenwerking tussen groepen te beperken en conflicten in uw organisatie te voorkomen. Met informatiebarrières kunt u beleidsregels maken om bestandssamenwerking, chatten, bellen of vergaderuitnodigingen tussen groepen personen in uw organisatie toe te staan of te voorkomen.

- [Informatiebelemmeringen](../compliance/information-barriers.md)

- [Informatiebarrières in Microsoft Teams](/microsoftteams/information-barriers-in-teams)

- [Gebruik informatiebarrières met SharePoint](/sharepoint/information-barriers)

## <a name="data-residency"></a>Data-ingezetenschap

Met Microsoft 365 Multi-Geo kunt u gegevens inrichten en opslaan op de geolocaties die u hebt gekozen om te voldoen aan de vereisten voor gegevensopslag. In een multi-geo-omgeving bestaat uw Microsoft 365-tenant uit een centrale locatie (waar uw Microsoft 365-abonnement oorspronkelijk is ingericht) en een of meer satellietlocaties waar u gegevens kunt opslaan.

- [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo)

- [Plannen voor Microsoft 365 Multi-Geo](/microsoft-365/enterprise/plan-for-multi-geo)

## <a name="related-topics"></a>Verwante onderwerpen

[Planning van samenwerkingsbeheer stap voor stap](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Uw samenwerkingsbeheerplan maken](collaboration-governance-first.md)

[Beveiliging en naleving voor Exchange Online](/exchange/security-and-compliance/security-and-compliance)

[Gegevens beveiligen](../compliance/information-protection.md)
