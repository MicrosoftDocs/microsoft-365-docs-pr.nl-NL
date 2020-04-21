---
title: Ga naar het actiecentrum om uw geautomatiseerde onderzoeks- en hersteltaken weer te geven en goed te keuren
description: Het Onderhoudscentrum gebruiken om details over geautomatiseerd onderzoek weer te geven en acties in behandeling goed te keuren
keywords: Onderhoudscentrum, bescherming tegen bedreigingen, onderzoek, waarschuwing, in afwachting, geautomatiseerd, detectie
search.appverid: met150
ms.prod: M365-security-compliance
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: c3406ebf5962d6f0ac08c1ee280bab725cf1c3bd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626956"
---
# <a name="the-action-center"></a>Het Actiecentrum

**Geldt voor:**
- Microsoft Threat Protection

Gebruik het actiecentrum om de resultaten van lopende en eerdere onderzoeken te bekijken op de apparaten en postvakken van uw organisatie. Afhankelijk van het type bedreiging en de daaruit voortvloeiende uitspraak, worden [herstelacties](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) automatisch of na goedkeuring door het beveiligingsteam van uw organisatie uitgevoerd. Alle herstelacties, ongeacht of ze in behandeling zijn of al zijn goedgekeurd, worden geconsolideerd in het actiecentrum. 

![Actiecentrum](../../media/air-actioncenter.png)

## <a name="a-single-pane-of-glass-experience"></a>Een "enkele ruit" ervaring

Het actiecentrum biedt een 'enkele ruit'-ervaring voor taken, zoals:
- Goedkeuring van lopende herstelacties;
- Een controlelogboek van reeds goedgekeurde herstelacties bekijken; En
- Voltooide herstelacties controleren.

Uw beveiligingsteam kan effectiever en efficiënter werken, omdat het Actiecentrum een uitgebreid overzicht biedt van Microsoft Threat Protection op het werk.

## <a name="go-to-the-action-center"></a>Ga naar het actiecentrum

1. Ga [https://security.microsoft.com](https://security.microsoft.com) naar en meld je aan. 

2. Kies In het navigatiedeelvenster de optie **Actiecentrum**. 

3. In het actiecentrum ziet u twee tabbladen: **In behandeling** en **geschiedenis**.

    - Op het tabblad **In behandeling** worden onderzoeken weergegeven die moeten worden gecontroleerd en goedgekeurd door iemand in uw beveiligingsteam om door te gaan. Zorg ervoor dat u de in behandeling zijnde objecten die u hier ziet, controleert en actie onderneemt.

    - Op het tabblad **Geschiedenis** worden eerdere onderzoeken en herstelacties weergegeven die automatisch zijn uitgevoerd. U gegevens van de afgelopen dag, week, maand of zes maanden bekijken.

4. Als u alleen de kolommen wilt weergeven die u wilt zien, selecteert u **Kolommen aanpassen**.<br/>![Onderhoudscentrum in Microsoft-bedreigingsbeveiliging](../../media/mtp-action-center.png)

5. Selecteer een item in de lijst om meer details over een onderzoek weer te geven. De weergave onderzoeksdetails wordt geopend.<br/>![Onderzoeksdetails](../../media/mtp-air-investdetails.png)

    - Als het onderzoek betrekking heeft op e-mailinhoud (zoals de entiteit is een[https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation)postvak), worden de onderzoeksgegevens geopend in het Security & Compliance Center ( ). 

    - Als het onderzoek een apparaat betreft, worden[https://security.microsoft.com](https://security.microsoft.com)de onderzoeksgegevens geopend in het beveiligingscentrum ( ). 

> [!TIP]
> Als u denkt dat er iets is gemist of verkeerd is gedetecteerd door geautomatiseerde onderzoeks- en reactiefuncties in Microsoft Threat Protection, laat het ons dan weten! Zie [Hoe valse positieven/negatieven in geautomatiseerde onderzoeks- en reactiemogelijkheden (AIR) kunnen worden gemeld in Microsoft Threat Protection.](mtp-autoir-report-false-positives-negatives.md)

## <a name="required-permissions-for-action-center-tasks"></a>Vereiste machtigingen voor Actiecentrumtaken

Als u in behandeling zijnde acties in het Actiecentrum wilt goedkeuren of afwijzen, moet u machtigingen hebben toegewezen zoals vermeld in de volgende tabel:

|Herstelactie |Vereiste rollen en machtigingen |
|--|----|
|Microsoft Defender ATP-herstel (apparaten) |Beveiligingsbeheerrol toegewezen in Azure[https://portal.azure.com](https://portal.azure.com)Active Directory ( ) of[https://admin.microsoft.com](https://admin.microsoft.com)het Microsoft 365-beheercentrum ( )<br/>--- of ---<br/>Rol actieve herstelacties toegewezen in Microsoft Defender ATP <br/> <br/> Zie de volgende bronnen voor meer informatie: <br/>- [Machtigingen voor beheerdersrollen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Rollen voor op rollen gebaseerd toegangscontrole (Microsoft Defender ATP) maken en beheren](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)  |
|Office 365 ATP-herstel (Office-inhoud en e-mail)  |Beveiligingsbeheerrol toegewezen in Azure[https://portal.azure.com](https://portal.azure.com)Active Directory ( ) of[https://admin.microsoft.com](https://admin.microsoft.com)het Microsoft 365-beheercentrum ( )<br/>--- en --- <br/>Zoek- en zuiveringsrol toegewezen aan[https://protection.office.com](https://protection.office.com)het Beveiligingscentrum & Compliance Center ( ) <br/><br/>**BELANGRIJK:** als u de functie Beveiligingsbeheerder alleen hebt toegewezen in het Security & Compliance Center, hebt u geen toegang tot het onderhoudscentrum of de mogelijkheden voor Microsoft Threat Protection. U moet de functie Beveiligingsbeheerder hebben toegewezen in Azure Active Directory of het Microsoft 365-beheercentrum. <br/><br/>Zie de volgende bronnen voor meer informatie: <br/>- [Machtigingen voor beheerdersrollen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Machtigingen in het Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!NOTE]
> Gebruikers die de functie Globale beheerder hebben toegewezen in Azure Active Directory, kunnen elke actie in behandeling in het Actiecentrum goedkeuren of afwijzen. Als aanbevolen praktijk moet uw organisatie echter het aantal mensen beperken dat de rol Globale beheerder heeft toegewezen. We raden u aan de hierboven vermelde beveiligingsbeheerder, actieve herstelacties en zoek- en zuiveringsrollen te gebruiken voor machtigingen voor het Onderhoudscentrum.

## <a name="next-steps"></a>Volgende stappen 

- [Meer informatie over incidenten in Microsoft Threat Protection](incidents-overview.md)

- [Bekijk de resultaten van een geautomatiseerd onderzoek](mtp-autoir-results.md)

- [Meer informatie over jagen in Microsoft Threat Protection](advanced-hunting-overview.md)

