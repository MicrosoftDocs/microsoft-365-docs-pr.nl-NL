---
title: Ga naar het Actiecentrum om uw geautomatiseerde onderzoeks- en hersteltaken te bekijken en goed te keuren
description: Het Onderhoudscentrum gebruiken om details over geautomatiseerd onderzoek te bekijken en lopende acties goed te keuren
keywords: Action Center, bescherming van bedreigingen, onderzoek, alert, in afwachting, geautomatiseerd, detectie
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
ms.openlocfilehash: 77bc0f088a9779396a56a9cc8cc9ae6ecbdadea7
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/28/2020
ms.locfileid: "46503101"
---
# <a name="the-action-center"></a>Het Actiecentrum

**Van toepassing op:**
- Microsoft Threat Protection

Gebruik het Onderhoudscentrum om de resultaten van huidige en eerdere onderzoeken te bekijken op de apparaten en postvakken van uw organisatie. Afhankelijk van het type bedreiging en het daaruit voortvloeiende vonnis, worden [herstelacties](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) automatisch of na goedkeuring door het beveiligingsteam van uw organisatie uitgevoerd. Alle herstelacties, of ze nu goedgekeurd zijn of al zijn goedgekeurd, worden geconsolideerd in het Actiecentrum. 

![Actiecentrum](../../media/air-actioncenter.png)

## <a name="a-single-pane-of-glass-experience"></a>Een "enkele ruit" ervaring

Het Actiecentrum biedt een "enkel glasvenster" ervaring voor taken, zoals:
- Goedkeuring in afwachting van herstelacties;
- Een controlelogboek van reeds goedgekeurde herstelacties weergeven; En
- Voltooide herstelacties bekijken.

Uw beveiligingsteam kan effectiever en efficiënter werken, omdat het Onderhoudscentrum een uitgebreid overzicht biedt van Microsoft Threat Protection op het werk.

## <a name="go-to-the-action-center"></a>Naar het actiecentrum gaan

1. Ga naar [https://security.microsoft.com](https://security.microsoft.com) en meld je aan. 

2. Kies in het navigatiedeelvenster **Het centrum van Actie**. 

3. In het Onderhoudscentrum ziet u twee tabbladen: **In behandeling** en **geschiedenis**.

    - Op het tabblad **In behandeling** worden onderzoeken weergegeven waarvoor iemand in uw beveiligingsteam moet worden gecontroleerd en goedgekeurd om door te gaan. Zorg ervoor dat u objecten in behandeling bekijkt en actie onderneemt voor lopende objecten die u hier ziet.

    - Op het tabblad **Geschiedenis** worden eerdere onderzoeken en herstelacties weergegeven die automatisch zijn uitgevoerd. U gegevens van de afgelopen dag, week, maand of zes maanden bekijken.

4. Als u alleen de kolommen wilt **weergeven**die u wilt zien, selecteert u Kolommen aanpassen .<br/>![Onderhoudscentrum in Microsoft Threat Protection](../../media/mtp-action-center.png)

5. Selecteer een item in de lijst om meer details over een onderzoek weer te geven. De weergave details van het onderzoek wordt geopend.<br/>![Onderzoeksdetails](../../media/mtp-air-investdetails.png)

    - Als het onderzoek betrekking heeft op e-mailinhoud (zoals de entiteit een postvak), worden de onderzoeksgegevens geopend in het Security & Compliance Center ( [https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation) ). 

    - Als het onderzoek een apparaat betreft, openen de onderzoeksdetails in het veiligheidscentrum ( [https://security.microsoft.com](https://security.microsoft.com) ). 

> [!TIP]
> Als u denkt dat er iets is gemist of ten onrechte is gedetecteerd door geautomatiseerde onderzoeks- en reactiefuncties in Microsoft Threat Protection, laat het ons dan weten! Zie [Hoe foutieve positieven/negatieven te rapporteren in geautomatiseerde mogelijkheden voor onderzoek en respons (AIR) in Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).

## <a name="available-actions"></a>Beschikbare acties

Als herstelacties worden uitgevoerd, worden ze weergegeven op het tabblad Geschiedenis in het Centrum van Het Actiecentrum. Dergelijke acties omvatten het volgende:

- Verzamel onderzoekspakket 
- Apparaat isoleren (deze actie kan ongedaan worden gemaakt) 
- Buitenboordmachine 
- Uitvoering van de code vrijgeven 
- Loslaten uit quarantaine 
- Voorbeeld aanvragen 
- Codeuitvoering beperken (deze actie kan ongedaan worden gemaakt) 
- Antivirusscan uitvoeren 
- Stoppen en in quarantaine 

## <a name="required-permissions-for-action-center-tasks"></a>Vereiste machtigingen voor Action Center-taken

Als u lopende acties in het Onderhoudscentrum wilt goedkeuren of afwijzen, moet u machtigingen hebben toegewezen die zijn toegewezen in de volgende tabel:

|Saneringsactie |Vereiste rollen en machtigingen |
|--|----|
|Microsoft Defender ATP-herstel (apparaten) |Rol beveiligingsbeheerder toegewezen in Azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) of het Microsoft 365-beheercentrum ( [https://admin.microsoft.com](https://admin.microsoft.com) )<br/>--- of ---<br/>Rol actieve herstelacties toegewezen in Microsoft Defender ATP <br/> <br/> Zie de volgende bronnen voor meer informatie: <br/>- [Machtigingen voor beheerdersrol in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Rollen maken en beheren voor toegangscontrole op basis van rollen (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)  |
|Office 365 ATP-herstel (Office-inhoud en -e-mail)  |Rol beveiligingsbeheerder toegewezen in Azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) of het Microsoft 365-beheercentrum ( [https://admin.microsoft.com](https://admin.microsoft.com) )<br/>--- en --- <br/>Zoek- en zuiveringsrol toegewezen aan het Security & Compliance Center ( [https://protection.office.com](https://protection.office.com) ) <br/><br/>**BELANGRIJK:** als u de rol beveiligingsbeheerder alleen hebt toegewezen in het Security & Compliance Center, hebt u geen toegang tot het Onderhoudscentrum of de mogelijkheden voor Microsoft Threat Protection. U moet de rol Beveiligingsbeheerder hebben toegewezen in Azure Active Directory of het Microsoft 365-beheercentrum. <br/><br/>Zie de volgende bronnen voor meer informatie: <br/>- [Machtigingen voor beheerdersrol in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Machtigingen in het Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!NOTE]
> Gebruikers die de rol Global Administrator hebben toegewezen in Azure Active Directory, kunnen elke lopende actie in het Onderhoudscentrum goedkeuren of weigeren. Als aanbevolen procedures moet uw organisatie echter het aantal mensen beperken dat de rol Global Administrator heeft toegewezen. We raden u aan de hierboven genoemde machtigingen voor het Onderhoudscentrum te gebruiken voor machtigingen voor het Onderhoudscentrum.

## <a name="next-steps"></a>Volgende stappen 

- [Meer informatie over incidenten in Microsoft Threat Protection](incidents-overview.md)

- [Bekijk de resultaten van een geautomatiseerd onderzoek](mtp-autoir-results.md)

- [Meer informatie over jagen in Microsoft Threat Protection](advanced-hunting-overview.md)

