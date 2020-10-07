---
title: Nalevings opties voor Microsoft 365 groepen, teams en de samenwerking via SharePoint
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
description: Meer informatie over nalevings opties voor Microsoft 365 groepen, teams en de samenwerking via SharePoint.
ms.openlocfilehash: 0383b0728d9b8ea12ce75de8bf0e250932d14ae5
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377531"
---
# <a name="compliance-options-for-microsoft-365-groups-teams-and-sharepoint-collaboration"></a>Nalevings opties voor Microsoft 365 groepen, teams en de samenwerking via SharePoint

Microsoft 365 biedt een volledige suite met hulpmiddelen waarmee naleving kan worden bijgehouden wanneer gebruikers samenwerken. Bekijk deze opties en kijk hoe ze zijn toegewezen aan uw bedrijfsbehoeften, de gevoeligheid van uw gegevens en het bereik van personen waarmee uw gebruikers kunnen samenwerken.

De volgende tabel bevat een beknopt overzicht van de besturingselementen voor naleving die beschikbaar zijn in Microsoft 365. Meer informatie vindt u in de volgende secties.

|Categorie|Beschrijving|Verwijzing|
|:-------|:----------|:--------|
|Informatie retentie|||
||Groepen e-mail en SharePoint-inhoud bewaren|[Meer informatie over bewaarbeleid voor SharePoint en OneDrive](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-sharepoint)|
||Chatberichten en berichten behouden|[Meer informatie over bewaarbeleid voor Microsoft teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)|
|Informatie classificatie|||
||Groepen en teams classificeren|[De beschikbaarheid van labels gebruiken om inhoud te beschermen in Microsoft teams, Microsoft 365-groepen en SharePoint-sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||Gevoelige inhoud automatisch classificeren|[Een vertrouwelijkheidslabel automatisch toepassen op inhoud](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)|
||Gevoelige inhoud versleutelen|[Toegang tot inhoud beperken door versleuteling toe te passen met vertrouwelijkheidslabels](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)|
|Gegevensbescherming|||
||Voorkomen dat vertrouwelijke informatie verloren gaat|[Overzicht van preventie van gegevensverlies](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)|
||Beveilig gevoelige informatie in chat.|[Preventie van gegevensverlies en Microsoft teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)|
||De gevoelige informatie van uw organisatie definiëren|[Aangepaste gevoelige informatietypen](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)|
|Gebruikers segmentatie|||
||Communicatie tussen gebruikerssegmenten beperken|[Informatiebelemmeringen](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)|

## <a name="information-retention"></a>Informatie retentie

Bewaarbeleid is beschikbaar voor het bewaren of verwijderen van items die worden gebruikt voor samenwerking in groepen en teams, inclusief bestanden, berichten en e-mailberichten. Beleidsregels kunnen worden ingesteld op bewaren en wissen, zodat u alleen maar wilt bewaren of verwijderen. Gegevens die betrekking hebben op het bewaarbeleid, zijn beveiligd in het geval dat de groep of het team vervalt of anderszins wordt verwijderd.

Als u een bewaarbeleid configureert voor Microsoft 365-groepen, behandelt het postvak van de groep en de bijbehorende SharePoint-site en-bestanden.

- [Meer informatie over bewaarbeleid voor SharePoint en OneDrive](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-sharepoint)

Bewaarbeleid voor teams behoudt chat-en kanaalberichten. Wanneer chat-en kanaalberichten zijn opgeslagen in Exchange-postvakken, hebben ze geen invloed op het bewaarbeleid voor Exchange. U moet het bewaarbeleid instellen voor het toepassen van chatberichten en teams-kanaalberichten in teams:

- [Meer informatie over bewaarbeleid voor Microsoft teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)

- [Bewaarbeleid in Microsoft teams](https://docs.microsoft.com/microsoftteams/retention-policies)

U kunt één bewaarbeleid instellen voor toepassing op Microsoft 365 groepen, teams chatten en teams-kanaalberichten. 

Aanvullende informatiebronnen:

- [Overzicht van bewaarbeleid](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)

- [Bewaar Tags en bewaarbeleid](https://docs.microsoft.com/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies) in Exchange

## <a name="information-classification"></a>Informatie classificatie

U kunt met behulp van behulp van palletlabels de toegang krijgen tot gasttoegang, de privacy van groepen en teams, en door niet-beheerde apparaten voor groepen en teams. Wanneer u het label toepast, worden deze instellingen automatisch geconfigureerd volgens de naam instellingen.

- [De beschikbaarheid van labels gebruiken om inhoud te beschermen in Microsoft teams, Microsoft 365-groepen en SharePoint-sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

U kunt Microsoft 365 configureren voor het automatisch toepassen van gevoelige labels op bestanden en e-mailberichten op basis van de criteria die u opgeeft, waaronder het detecteren van gevoelige gegevenstypen of het vergelijken van patronen met Train bare classificaties.

- [Een vertrouwelijkheidslabel automatisch toepassen op inhoud](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)

Met behulp van coderings labels kunt u bestanden versleutelen, zodat alleen personen met machtigingen kunnen worden ontsleuteld en gelezen.

- [Toegang tot inhoud beperken door versleuteling toe te passen met vertrouwelijkheidslabels](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)

- [Een team configureren met beveiligingsisolatie](https://docs.microsoft.com/microsoft-365/solutions/secure-teams-security-isolation)

Aanvullende informatiebronnen:

- [Meer informatie over vertrouwelijkheidslabels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)


## <a name="information-protection"></a>Gegevensbescherming

DLP-beleidsregels kunnen voorkomen dat vertrouwelijke gegevens in SharePoint, Exchange en teams met onbedoeld delen worden gedeeld. U kunt beleidsregels maken om te bepalen welke acties worden uitgevoerd (zoals het blokkeren van toegang) op basis van een set regels.

- [Overzicht van preventie van gegevensverlies](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)

DLP in teams kan u helpen gevoelige informatie in teams-chat en kanaalberichten te beschermen door berichten te verwijderen die gevoelige informatie bevatten.

- [Preventie van gegevensverlies en Microsoft teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)

Als u gevoelige informatie hebt die uniek is voor uw organisatie, zoals projectcode namen, kunt u uw eigen gevoelige informatie typen maken en deze toepassen op DLP-beleidsregels om inhoud in groepen, teams en SharePoint te beveiligen.

- [Aangepaste gevoelige informatietypen](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)

## <a name="user-segmentation"></a>Gebruikers segmentatie

Met informatie barrières kunt u uw gegevens en gebruikers segmenteren voor het beperken van ongewenste communicatie en samenwerking tussen groepen en de belangen van uw organisatie te voorkomen. Met informatie barrières kunt u beleidsregels maken voor het samenwerken, chatten, bellen of uitnodigingen voor vergaderingen tussen groepen personen binnen uw organisatie.

- [Informatiebelemmeringen](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)

- [Informatie belemmeringen voor Microsoft teams](https://docs.microsoft.com/microsoftteams/information-barriers-in-teams)

- [Informatie barrières met SharePoint gebruiken](https://docs.microsoft.com/sharepoint/information-barriers)

## <a name="related-topics"></a>Verwante onderwerpen

[Beveiliging en naleving voor Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/security-and-compliance)

[Informatie beschermen](https://docs.microsoft.com/microsoft-365/compliance/protect-information)


