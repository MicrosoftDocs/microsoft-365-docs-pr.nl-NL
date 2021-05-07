---
title: Vergelijking berichtversleuteling (OME)
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: In dit artikel wordt uitgelegd wat de verschillen zijn tussen verschillende versies van Office 365-berichtversleuteling.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 92beb3625c0b115fe77f1667a448bf0bf9589040
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "52162588"
---
# <a name="compare-versions-of-ome"></a>Versies van OME vergelijken

> [!IMPORTANT]
> Op 28 februari 2021 heeft Microsoft de ondersteuning voor AD RMS in Exchange Online. Als u een hybride omgeving hebt geïmplementeerd waarin uw Exchange-postvakken online zijn en u IRM gebruikt met Active Directory RMS on-premises, moet u migreren naar Azure. Organisaties die zijn geïmplementeerd in de GCC Matige omgeving, worden ook beïnvloed. Zie 'Overzicht van AD RMS-afzetting in Exchange Online' in dit artikel voor informatie.

In de rest van dit artikel worden oudere Office 365-berichtversleuteling (OME) vergeleken met de nieuwe OME-mogelijkheden en Office 365 Advanced Message Encryption. De nieuwe mogelijkheden zijn een fusie en nieuwere versie van zowel OME als Information Rights Management (IRM). Unieke kenmerken van implementatie in GCC Hoog worden ook beschreven. De twee kunnen naast elkaar bestaan in uw organisatie. Zie Office 365-berichtversleuteling [(OME) voor informatie over hoe de nieuwe mogelijkheden werken.](ome.md)

Dit artikel maakt deel uit van een grotere reeks artikelen over Office 365-berichtversleuteling. Dit artikel is bedoeld voor beheerders en ITPro's. Als u alleen op zoek bent naar informatie over het verzenden of ontvangen van een versleuteld bericht, bekijkt u de lijst met artikelen in [Office 365-berichtversleuteling (OME)](ome.md) en zoekt u het artikel dat het beste bij uw behoeften past.

## <a name="overview-of-ad-rms-deprecation-in-exchange-online"></a>Overzicht van AD RMS-afzetting in Exchange Online

Exchange Online bevat IRM-functionaliteit (Information Rights Management) die online en offline bescherming biedt voor e-mailberichten en bijlagen. Standaard wordt Exchange Online Azure Information Protection gebruikt. Het is echter mogelijk dat uw organisatie Exchange Online IRM heeft geconfigureerd voor het gebruik van de on-premises Active Directory Rights Management Service (AD RMS). AD RMS-ondersteuning in Exchange Online wordt met pensioen. In plaats daarvan vervangt Azure Information Protection AD RMS volledig.

Zie Ad RMS migreren naar [Azure RMS in](https://support.microsoft.com/help/5001237)Exchange Online . Dit artikel bevat aanbevelingen voor migratieopties.

## <a name="side-by-side-comparison-of-ome-features-and-capabilities"></a>Naast elkaar vergelijken van OME-functies en -mogelijkheden

|           **Situatie**           | **OME (verouderd)**    | **IRM in AD RMS**        | **Nieuwe OME-mogelijkheden** |
|-----------------------------------|-------------------|-------------------|--------------------------|
|*Een versleutelde e-mail verzenden*        |Via Exchange regels voor e-mailstroom|Eindgebruikers die zijn gestart vanaf Outlook bureaublad of Outlook op internet; of via Exchange regels voor e-mailstroom|Eindgebruiker die is gestart vanaf Outlook bureaublad, Outlook voor Mac of Outlook op internet; via Exchange regels voor e-mailstroom (ook wel transportregels genoemd) en Preventie van gegevensverlies (DLP)|
|*Sjabloon Rechtenbeheer*       |   N.v.t.      |Optie Niet doorsturen en aangepaste sjablonen|Optie Niet doorsturen, optie alleen-versleutelen en aangepaste sjablonen|
|*Type geadresseerde*                   |Interne en externe geadresseerden|Alleen interne geadresseerden         |Interne en externe geadresseerden|
|*Ervaring voor interne geadresseerde*|Geadresseerden ontvangen een HTML-bericht dat ze downloaden en openen in een webbrowser of mobiele app|Native inline experience in Outlook clients|Native inline experience for recipients in the same organization using Outlook clients.  Geadresseerden kunnen berichten lezen vanuit de OME-portal met andere clients dan Outlook (geen download of app vereist).|
|*Ervaring voor externe geadresseerde*|Geadresseerden ontvangen een HTML-bericht dat ze downloaden en openen in een webbrowser of mobiele app|N.v.t.|Native inline-ervaring voor Microsoft 365 geadresseerden. Alle andere geadresseerden kunnen een bericht lezen vanuit de OME-portal (geen download of app vereist).|
|*Machtigingen voor bijlagen*           |Geen beperkingen voor bijlagen|Bijlagen zijn beveiligd|Bijlagen zijn beveiligd voor de optie Niet doorsturen en aangepaste sjablonen. Beheerders kunnen kiezen of bijlagen voor de optie alleen-versleutelen al dan niet zijn beveiligd.|
|*Ondersteuning voor uw eigen sleutel (BYOK)*|Geen                |Geen               |BYOK ondersteund          |
||

## <a name="advantages-of-the-new-ome-capabilities-over-legacy-ome"></a>Voordelen van de nieuwe OME-mogelijkheden ten opzichte van oudere OME

De nieuwe mogelijkheden bieden de volgende voordelen:

- Mogelijkheid om de optie alleen-versleutelen te gebruiken (waardoor veilige samenwerking mogelijk is), de optie Niet doorsturen en aangepaste beperkingen.
- Afzenders kunnen e-mail die is versleuteld met de nieuwe mogelijkheden handmatig verzenden Outlook desktopcl clients, Outlook voor Mac en Outlook webcl clients.
- Microsoft 365 ontvangers kunnen een inline-ervaring gebruiken in ondersteunde Outlook clients. Beheerders kunnen er ook voor kiezen om Microsoft 365 een merkervaring weer te geven.
- Accounts buiten Microsoft 365, zoals Gmail-, Yahoo- en Microsoft-accounts, worden federatief gemaakt met de OME-portal, die een betere gebruikerservaring biedt voor deze geadresseerden. Alle andere identiteiten gebruiken een een-time pass-code om versleutelde berichten te openen.
- Beheerders kunnen huisstijl aanpassen en meerdere huisstijlsjablonen maken.
- Beheerders kunnen e-mailberichten intrekken die zijn versleuteld met de nieuwe mogelijkheden.
- De nieuwe mogelijkheden bieden gedetailleerde gebruiksrapporten via het Beveiligings &amp; compliancecentrum.

## <a name="office-365-advanced-message-encryption-capabilities"></a>Office 365 Advanced Message Encryption mogelijkheden

Office 365 Advanced Message Encryption biedt extra mogelijkheden naast de nieuwe OME-mogelijkheden. U moet de nieuwe Office 365-berichtversleuteling in uw organisatie hebben ingesteld om de mogelijkheden voor geavanceerde berichtversleuteling te kunnen gebruiken. Om deze mogelijkheden te kunnen gebruiken, moeten geadresseerden ook beveiligde e-mail bekijken en beantwoorden via de OME-portal. De geavanceerde mogelijkheden zijn:

- Bericht intrekken

- Berichtverloop

- Meerdere huisstijlsjablonen

Office 365 Advanced Message Encryption wordt niet ondersteund in GCC Hoog.

Zie voor meer informatie over het gebruik van geavanceerde berichtversleuteling [Office 365 Advanced Message Encryption.](ome-advanced-message-encryption.md)

## <a name="unique-characteristics-of-office-365-message-encryption-in-a-gcc-high-deployment"></a>Unieke kenmerken van Office 365-berichtversleuteling in een GCC Hoge implementatie

Als u van plan bent om Office 365-berichtversleuteling te gebruiken in een GCC High-omgeving, zijn er enkele unieke kenmerken met betrekking tot de gebruikerservaring.

### <a name="encrypted-email-between-gcc-high-and-gcc-high-recipients"></a>Versleutelde e-mail tussen GCC hoge en GCC hoge geadresseerden

Afzenders kunnen e-mailberichten handmatig versleutelen in Outlook voor pc en Mac en Outlook op het web, of organisaties kunnen een beleid instellen om e-mailberichten te versleutelen met Exchange regels voor e-mailstroom.

Ontvangers in GCC High ontvangen dezelfde inline leeservaring in Outlook voor pc en Mac en Outlook op het web als alle andere gebruikers.

### <a name="encrypted-email-between-gcc-high-and-non-gcc-high-recipients"></a>Versleutelde e-mail tussen GCC hoge en niet-GCC hoge geadresseerden

Afzenders in GCC Hoog kunnen versleutelde e-mail verzenden buiten de GCC Hoge rand en omgekeerd.

Alle geadresseerden buiten GCC High, inclusief commerciële Microsoft 365-gebruikers, Outlook.com-gebruikers en andere gebruikers van andere e-mailproviders, zoals Gmail en Yahoo, ontvangen een inwikkelmail. Met deze wrapper-e-mail wordt de geadresseerde omgeleid naar de OME Portal, waar de geadresseerde het bericht kan lezen en beantwoorden. Dit geldt ook voor afzenders buiten GCC hoog verzendende OME-versleutelde e-mail naar GCC Hoog.

## <a name="coexistence-of-legacy-ome-and-the-new-capabilities-in-the-same-tenant"></a>Coëxistentie van oudere OME en de nieuwe mogelijkheden in dezelfde tenant

U kunt zowel oudere OME als de nieuwe mogelijkheden in dezelfde tenant gebruiken. Als beheerder doet u dit door te kiezen welke versie van OME u wilt gebruiken wanneer u uw regels voor e-mailstroom maakt.

- Als u de oudere versie van OME wilt opgeven, gebruikt u Exchange actie E-mailstroomregel **Toepassen op de vorige versie van OME**.

- Als u de nieuwe mogelijkheden wilt opgeven, gebruikt u Exchange actie E-mailstroomregel **toepassen Office 365-berichtversleuteling en rechtenbescherming**.

Gebruikers kunnen handmatig e-mail verzenden die is versleuteld met de nieuwe mogelijkheden van Outlook bureaublad, Outlook voor Mac en Outlook op het web.

## <a name="migrate-from-legacy-ome-to-the-new-capabilities"></a>Migreren van oudere OME naar de nieuwe mogelijkheden

Hoewel beide versies van OME naast elkaar kunnen bestaan, raden we u ten zeerste aan om uw oude e-mailstroomregels te bewerken met de regelactie De vorige versie van **OME** toepassen om de nieuwe mogelijkheden te gebruiken. Werk deze regels bij om de actie E-mailstroomregel toepassen **Office 365-berichtversleuteling en rechtenbescherming te gebruiken.** Zie Regels voor e-mailstroom definiëren [om e-mailberichten te](define-mail-flow-rules-to-encrypt-email.md)versleutelen in Office 365.

## <a name="get-started-with-ome"></a>Aan de slag met OME

Meestal worden de nieuwe OME-mogelijkheden automatisch ingeschakeld voor uw organisatie. Zie Nieuwe mogelijkheden Office 365-berichtversleuteling [voor meer informatie over de nieuwe OME-mogelijkheden binnen uw organisatie.](set-up-new-message-encryption-capabilities.md)

De oudere versie van OME wordt automatisch ingeschakeld voor uw organisatie als u Azure Information Protection hebt ingeschakeld. In het verleden werkte oudere OME zelfs als Azure Information Protection niet was ingeschakeld. Dit is niet langer het geval.

Als u oudere OME wilt gaan gebruiken, configureert u, als u Azure Information Protection hebt ingeschakeld, e-mailstroomregels met de regelactie De vorige versie van **OME toepassen.** Zie Regels voor e-mailstroom [definiëren om e-mailberichten te versleutelen](define-mail-flow-rules-to-encrypt-email.md)voor instructies.