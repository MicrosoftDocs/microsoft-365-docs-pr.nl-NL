---
title: Complianceopties voor Microsoft 365-groepen, Teams en SharePoint-samenwerking
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
description: Meer informatie over complianceopties voor Microsoft 365-groepen, Teams en SharePoint-samenwerking.
ms.openlocfilehash: 5006f0cf9f7eb174082d4fc2508bf112864fcba3
ms.sourcegitcommit: 1c53f114a810e7aaa2dc876b84d66348492ea36c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/20/2021
ms.locfileid: "51899350"
---
# <a name="compliance-options-for-microsoft-365-groups-teams-and-sharepoint-collaboration"></a>Complianceopties voor Microsoft 365-groepen, Teams en SharePoint-samenwerking

Microsoft 365 biedt een volledige reeks hulpprogramma's om naleving te behouden terwijl uw gebruikers samenwerken. Bekijk deze opties en bedenk hoe deze worden toe te schrijven aan uw zakelijke behoeften, de gevoeligheid van uw gegevens en het bereik van personen met wie uw gebruikers moeten samenwerken.

De volgende tabel bevat een beknopt overzicht van de nalevingsbesturingselementen die beschikbaar zijn in Microsoft 365. Meer informatie vindt u in de volgende secties.

|Categorie|Beschrijving|Verwijzing|
|:-------|:----------|:--------|
|Bewaargegevens|||
||Groepen e-mail en SharePoint-inhoud behouden|[Meer informatie over bewaarbeleid voor SharePoint en OneDrive](../compliance/retention-policies-sharepoint.md)|
||Chat en berichten behouden|[Meer informatie over bewaarbeleid voor Microsoft Teams](../compliance/retention-policies-teams.md)|
|Informatieclassificatie|||
||Groepen en teams classificeren|[Gevoeligheidslabels gebruiken om inhoud in Microsoft Teams, Microsoft 365-groepen en SharePoint-sites te beveiligen](../compliance/sensitivity-labels-teams-groups-sites.md)|
||Gevoelige inhoud automatisch classificeren|[Een vertrouwelijkheidslabel automatisch toepassen op inhoud](../compliance/apply-sensitivity-label-automatically.md)|
||Gevoelige inhoud versleutelen|[Toegang tot inhoud beperken door versleuteling toe te passen met vertrouwelijkheidslabels](../compliance/encryption-sensitivity-labels.md)|
|Gegevensbescherming|||
||Voorkomen dat gevoelige informatie verloren gaat|[Overzicht van preventie van gegevensverlies](../compliance/data-loss-prevention-policies.md)|
||Bescherm gevoelige informatie in een chatgesprek.|[Preventie van gegevensverlies en Microsoft Teams](../compliance/dlp-microsoft-teams.md)|
||De gevoelige informatie van uw organisatie definiëren|[Aangepaste gevoelige informatietypen](../compliance/sensitive-information-type-learn-about.md)|
|Gebruikerssegmentatie|||
||Communicatie tussen gebruikerssegmenten beperken|[Informatiebelemmeringen](../compliance/information-barriers.md)|

## <a name="information-retention"></a>Bewaargegevens

Bewaarbeleid is beschikbaar voor het behouden of verwijderen van items die worden gebruikt voor samenwerking in groepen en teams, zoals bestanden, berichten en e-mail. Beleidsregels kunnen worden ingesteld op behouden en verwijderen, alleen behouden of alleen verwijderen. Gegevens die onder een bewaarbeleid vallen, worden beveiligd als de groep of het team verloopt of anderszins wordt verwijderd.

Het configureren van een bewaarbeleid voor Microsoft 365 Groepen heeft betrekking op het groepspostvak en de bijbehorende SharePoint-site en -bestanden.

- [Meer informatie over bewaarbeleid voor SharePoint en OneDrive](../compliance/retention-policies-sharepoint.md)

Bewaarbeleid voor Teams behoudt chat- en kanaalberichten. Hoewel chat- en kanaalberichten worden opgeslagen in Exchange-postvakken, worden deze niet beïnvloed door exchange-bewaarbeleid. U moet uw bewaarbeleid instellen voor Teams-chats en Teams-kanaalberichten. 

Gebruikerschats worden voor onbepaalde tijd bewaard, zelfs als een gebruikersaccount wordt verwijderd. Als u deze gegevens niet voor onbepaalde tijd wilt bewaren, kunt u overwegen een bewaarbeleid te gebruiken om gebruikerschats na een bepaalde tijd te verwijderen of deze verwijdering op te nemen in het verwijderingsproces van de gebruiker.

- [Meer informatie over bewaarbeleid voor Microsoft Teams](../compliance/retention-policies-teams.md)

- [Bewaarbeleid in Microsoft Teams](/microsoftteams/retention-policies)

Er kan één bewaarbeleid worden ingesteld dat van toepassing is op Teams-chat- en Teams-kanaalberichten. 

Aanvullende informatiebronnen:

- [Overzicht van bewaarbeleid](../compliance/retention.md)

- [Bewaarlabels en bewaarbeleid](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies) in Exchange

## <a name="information-classification"></a>Informatieclassificatie

U kunt gevoeligheidslabels gebruiken voor gasttoegang, groeps- en team privacy en toegang via niet-beheerde apparaten voor groepen en teams. Door het label toe te passen, worden deze instellingen automatisch geconfigureerd volgens de labelinstellingen.

- [Gevoeligheidslabels gebruiken om inhoud in Microsoft Teams, Microsoft 365-groepen en SharePoint-sites te beveiligen](../compliance/sensitivity-labels-teams-groups-sites.md)

U kunt Microsoft 365 zo configureren dat gevoeligheidslabels automatisch worden toegepast op bestanden en e-mailberichten op basis van de criteria die u opgeeft, inclusief het detecteren van gevoelige informatietypen of patronen die overeenkomen met trainbare classificaties.

- [Een vertrouwelijkheidslabel automatisch toepassen op inhoud](../compliance/apply-sensitivity-label-automatically.md)

U kunt gevoeligheidslabels gebruiken om bestanden te versleutelen, zodat alleen personen met machtigingen ze kunnen ontsleutelen en lezen.

- [Toegang tot inhoud beperken door versleuteling toe te passen met vertrouwelijkheidslabels](../compliance/encryption-sensitivity-labels.md)

- [Een team configureren met beveiligingsisolatie](./secure-teams-security-isolation.md)

Aanvullende informatiebronnen:

- [Meer informatie over vertrouwelijkheidslabels](../compliance/sensitivity-labels.md)


## <a name="information-protection"></a>Gegevensbescherming

DLP-beleid kan voorkomen dat gevoelige informatie per ongeluk wordt gedeeld in SharePoint, Exchange en Teams. U kunt beleidsregels maken waarin acties worden opgegeven die moeten worden ondernomen (zoals het blokkeren van toegang) op basis van een set regels.

- [Overzicht van preventie van gegevensverlies](../compliance/data-loss-prevention-policies.md)

DLP in Teams kan helpen bij het beveiligen van gevoelige informatie in Teams-chat- en kanaalberichten door berichten te verwijderen die gevoelige informatie bevatten.

- [Preventie van gegevensverlies en Microsoft Teams](../compliance/dlp-microsoft-teams.md)

Als u gevoelige informatie hebt die uniek is voor uw organisatie, zoals projectcodenamen, kunt u uw eigen typen gevoelige informatie maken en deze toepassen op DLP-beleid om inhoud in groepen, teams en Sharepoint te beveiligen.

- [Aangepaste gevoelige informatietypen](../compliance/sensitive-information-type-learn-about.md)

## <a name="user-segmentation"></a>Gebruikerssegmentatie

Met informatiebarrières kunt u uw gegevens en gebruikers segmenteren om ongewenste communicatie en samenwerking tussen groepen te beperken en conflicten in uw organisatie te voorkomen. Met informatiebarrières kunt u beleidsregels maken om bestandssamenwerking, chatten, bellen of vergaderuitnodigingen tussen groepen personen in uw organisatie toe te staan of te voorkomen.

- [Informatiebelemmeringen](../compliance/information-barriers.md)

- [Informatiebarrières in Microsoft Teams](/microsoftteams/information-barriers-in-teams)

- [Informatiebarrières gebruiken met SharePoint](/sharepoint/information-barriers)

## <a name="related-topics"></a>Verwante onderwerpen

[Planning van samenwerkingsbeheer stap voor stap](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Uw samenwerkingsbeheerplan maken](collaboration-governance-first.md)

[Beveiliging en naleving voor Exchange Online](/exchange/security-and-compliance/security-and-compliance)

[Gegevens beveiligen](../compliance/information-protection.md)
