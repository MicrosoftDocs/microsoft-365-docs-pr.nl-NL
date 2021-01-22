---
title: Ga naar het Actiecentrum om uw geautomatiseerde onderzoeks- en hersteltaken weer te geven en goed te keuren
description: Het Actiecentrum gebruiken om details over geautomatiseerd onderzoek te bekijken en acties die in behandeling zijn goed te keuren
keywords: Actiecentrum, bedreigingsbeveiliging, onderzoek, waarschuwing, in behandeling, geautomatiseerd, detectie
search.appverid: met150
ms.prod: m365-security
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
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 12/09/2020
ms.technology: m365d
ms.openlocfilehash: 45e02e4ce7d5d813cc8215a1f27ed9c415707cb1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930424"
---
# <a name="the-action-center"></a>Het Actiecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

Gebruik het Actiecentrum () om de resultaten te bekijken van lopende en eerdere onderzoeken voor de apparaten en [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) postvakken van uw organisatie. Afhankelijk van het type bedreiging en het resulterende resultaat kunnen [herstelacties](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) automatisch of na goedkeuring door het beveiligingsteam van uw organisatie worden uitgevoerd. Alle herstelacties, of ze nu wachten op goedkeuring of al zijn goedgekeurd, worden samengevoegd in het actiecentrum. 

![Actiecentrum](../../media/air-actioncenter.png)

## <a name="a-single-pane-of-glass-experience"></a>Een 'enkel deelvenster met ruit'

Het Actiecentrum biedt een 'enkel deelvenster met glas' voor taken, zoals:
- Acties in behandeling voor het goedkeuren van herstelacties;
- Een auditlogboek met reeds goedgekeurde herstelacties weergeven; en
- Voltooide herstelacties bekijken.

Uw team voor beveiligingsbewerkingen kan effectiever en efficiënter werken, omdat het actiecentrum een uitgebreide weergave biedt van Microsoft 365 Defender op het werk.

## <a name="go-to-the-action-center"></a>Ga naar het Actiecentrum

1. Ga naar [https://security.microsoft.com](https://security.microsoft.com) en meld u aan. 

2. Kies Actiecentrum in het **navigatiedeelvenster.** 

3. In het actiecentrum ziet u twee **tabbladen:** In behandeling en **Geschiedenis.**

    - Op **het tabblad** In behandeling worden onderzoeken vermeld die moeten worden beoordeeld en goedgekeurd door iemand van het team voor beveiligingsbewerkingen om door te kunnen gaan. Controleer en onderneemt actie voor items die u hier ziet.

    - Het **tabblad** Geschiedenis bevat eerdere onderzoeken en herstelacties die automatisch zijn gedaan. U kunt gegevens weergeven voor de afgelopen dag, week, maand of zes maanden.

4. Als u alleen de kolommen wilt zien die u wilt zien, **selecteert u Kolommen aanpassen.**<br/>![Actiecentrum in Microsoft 365 Defender](../../media/mtp-action-center.png)

5. Selecteer een item in de lijst om meer details over een onderzoek weer te geven. De weergave details van het onderzoek wordt geopend.<br/>![Details van onderzoek](../../media/mtp-air-investdetails.png)

    - Als het onderzoek betrekking heeft op e-mailinhoud (zoals de entiteit is een postvak), worden onderzoeksdetails geopend in het beveiligings- & Compliancecentrum ( [https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation) ). 

    - Als het onderzoek een apparaat omvat, worden details van onderzoek geopend in het beveiligingscentrum ( [https://security.microsoft.com](https://security.microsoft.com) ). 

> [!TIP]
> Als u denkt dat er iets is gemist of ten onrechte is gedetecteerd door geautomatiseerde onderzoeks- en antwoordfuncties in Microsoft 365 Defender, laat het ons dan weten. Zie Hoe u fout-positieven/negatieven rapporteert in mogelijkheden voor geautomatiseerd onderzoek en reactie [(AIR) in Microsoft 365 Defender.](mtp-autoir-report-false-positives-negatives.md)

## <a name="available-actions"></a>Beschikbare acties

Wanneer herstelacties worden ondernomen, worden deze  weergegeven op het tabblad Geschiedenis in het actiecentrum. Dit zijn onder andere de volgende acties:

- Pakket voor onderzoek verzamelen 
- Apparaat isoleren (deze actie kan ongedaan worden gemaakt) 
- Offboard machine 
- Uitvoering van releasecode 
- Uit quarantaine worden vrijgegeven 
- Voorbeeld aanvraag 
- De uitvoering van code beperken (deze actie kan ongedaan worden gemaakt) 
- Antivirusscan uitvoeren 
- Stoppen en quarantaine 

> [!NOTE]
> Naast herstelacties die automatisch worden uitgevoerd, kan het team voor beveiligingsbewerkingen handmatig acties uitvoeren om gedetecteerde bedreigingen aan te pakken. Zie Herstelacties voor meer informatie over automatische en [handmatige herstelacties.](mtp-remediation-actions.md)

## <a name="action-source"></a>Actiebron

**(NIEUW!**) Zoals u weet, brengt Microsoft 365 Defender geautomatiseerde onderzoeks- en antwoordmogelijkheden samen voor meerdere services, zoals [Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) voor eindpunt en Microsoft Defender voor [Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) Het nieuwe en verbeterde actiecentrum bevat nu een **kolom** voor actiebron waarin wordt verteld waar elke herstelactie vandaan komt. 

In de volgende tabel worden mogelijke **actiebronwaarden** beschreven:

| Waarde van actiebron | Beschrijving |
|:-----|:---|
| **Handmatige apparaatactie** | Een handmatige actie die wordt ondernomen op een apparaat. Voorbeelden hiervan [zijn apparaatisolatie](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network) [of bestands quarantaine.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#stop-and-quarantine-files) |
| **Handmatige e-mailactie** | Een handmatige actie die wordt ondernomen op e-mail. Een voorbeeld hiervan is het zacht verwijderen van e-mailberichten [of het herstellen van een e-mailbericht.](https://docs.microsoft.com/microsoft-365/security/office-365-security/remediate-malicious-email-delivered-office-365) |
| **Automatische apparaatactie** | Een geautomatiseerde actie die wordt ondernomen op een entiteit, zoals een bestand of proces. Voorbeelden van geautomatiseerde acties zijn het verzenden van een bestand naar quarantaine, het stoppen van een proces en het verwijderen van een registersleutel. (Zie [Herstelacties in Microsoft Defender voor Eindpunt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-auto-investigation#remediation-actions).) |
| **Automatische e-mailactie** | Een automatische actie die wordt ondernomen op e-mailinhoud, zoals een e-mailbericht, bijlage of URL. Voorbeelden van geautomatiseerde acties zijn het zacht verwijderen van e-mailberichten, het blokkeren van URL's en het uitschakelen van externe doorsturen van e-mail. (Zie [Herstelacties in Microsoft Defender voor Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions).) |
| **Geavanceerde zoekactie** | Acties die worden ondernomen op apparaten of e-mail [met geavanceerd zoeken.](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-overview) |
| **Explorer-actie** | Acties die worden ondernomen op e-mailinhoud met [Explorer.](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) |
| **Handmatige live antwoordactie** | Acties die worden ondernomen op een apparaat met [live-antwoorden.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) Voorbeelden hiervan zijn het verwijderen van een bestand, het stoppen van een proces en het verwijderen van een geplande taak. |
| **Live antwoordactie** | Acties die worden ondernomen op een [apparaat met Microsoft Defender for Endpoint API's.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis) Voorbeelden van acties zijn het isoleren van een apparaat, het uitvoeren van een antivirusscan en het verkrijgen van informatie over een bestand. |

## <a name="required-permissions-for-action-center-tasks"></a>Vereiste machtigingen voor taken in het Actiecentrum

Als u acties in behandeling in het Actiecentrum wilt goedkeuren of weigeren, moet u machtigingen hebben toegewezen zoals vermeld in de volgende tabel:

|Herstelactie |Vereiste rollen en machtigingen |
|--|----|
|Herstel van Microsoft Defender voor eindpunt (apparaten) |Rol van beveiligingsbeheerder toegewezen in Azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) of het Microsoft 365-beheercentrum ( [https://admin.microsoft.com](https://admin.microsoft.com) )<br/>--- of ---<br/>Rol actieve herstelacties toegewezen in Microsoft Defender voor eindpunt <br/> <br/> Zie de volgende bronnen voor meer informatie: <br/>- [Machtigingen voor beheerdersrol in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Rollen maken en beheren voor toegangsbeheer op basis van rollen (Microsoft Defender voor eindpunt)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)  |
|Herstel van Microsoft Defender voor Office 365 (Office-inhoud en e-mail)  |Rol van beveiligingsbeheerder toegewezen in Azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) of het Microsoft 365-beheercentrum ( [https://admin.microsoft.com](https://admin.microsoft.com) )<br/>--- en --- <br/>De rol Zoeken en purge is toegewezen aan het & Compliancecentrum [https://protection.office.com](https://protection.office.com) () <br/><br/>**BELANGRIJK:** als aan u de rol Beveiligingsbeheerder alleen in het beveiligings- &-compliancecentrum is toegewezen, hebt u geen toegang tot de mogelijkheden van het Actiecentrum of Microsoft 365 Defender. De rol Beveiligingsbeheerder moet zijn toegewezen in Azure Active Directory of het Microsoft 365-beheercentrum. <br/><br/>Zie de volgende bronnen voor meer informatie: <br/>- [Machtigingen voor beheerdersrol in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Machtigingen in het & compliancecentrum](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!NOTE]
> Gebruikers aan wie de rol globale beheerder is toegewezen in Azure Active Directory, kunnen acties die in behandeling zijn in het actiecentrum goedkeuren of weigeren. Het wordt echter als een goede gewoonte gezien dat uw organisatie het aantal personen moet beperken aan wie de rol van globale beheerder is toegewezen. U wordt aangeraden de hierboven genoemde beveiligingsbeheerder, actieve herstelacties en zoek- en purge-rollen te gebruiken voor machtigingen van het actiecentrum.

## <a name="next-steps"></a>Volgende stappen 

- [Acties die in behandeling zijn na een geautomatiseerd onderzoek goedkeuren of weigeren](mtp-autoir-actions.md)
- [De resultaten van een geautomatiseerd onderzoek weergeven](mtp-autoir-results.md)

