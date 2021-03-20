---
title: Ga naar het Actiecentrum om uw geautomatiseerde onderzoeks- en hersteltaken weer te geven en goed te keuren
description: Het Actiecentrum gebruiken om details over geautomatiseerd onderzoek weer te geven en acties in behandeling goed te keuren
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
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 02/01/2021
ms.openlocfilehash: c1eba9d78d45068788789825c3513a0fa70255b9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917130"
---
# <a name="the-action-center"></a>Het Actiecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

## <a name="a-single-pane-of-glass-experience"></a>Een 'enkel deelvenster met glas'

Het actiecentrum biedt een 'enkel deelvenster met glas' voor taken, zoals:
- Goedkeuring van herstelacties in behandeling;
- Een auditlogboek weergeven van al goedgekeurde herstelacties; en
- Voltooide herstelacties controleren.

Uw beveiligingsteam kan effectiever en efficiënter werken, omdat het Actiecentrum een uitgebreide weergave biedt van Microsoft 365 Defender op het werk.

## <a name="a-new-unified-action-center"></a>Een nieuw, geïntegreerd actiecentrum

We zijn blij om een nieuw, geïntegreerd actiecentrum aan te kondigen ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) )! 

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="Unified Action center in Microsoft 365 Defender":::

Het verbeterde Actiecentrum bevat lopende en voltooide herstelacties voor uw apparaten, e-mail & samenwerkingsinhoud en identiteiten op één locatie.
- Als u eerder het Office 365 Security & Compliance Center () hebt gebruikt, probeert u het nieuwe, geïntegreerde Actiecentrum in het [https://protection.office.com](https://protection.office.com) Microsoft 365-beveiligingscentrum ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ).
- Als u het Actiecentrum in het Microsoft Defender-beveiligingscentrum () gebruikt, probeert u het nieuwe, geïntegreerde Actiecentrum in het [https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center) Microsoft 365-beveiligingscentrum ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ).
- Als u al gebruik hebt gemaakt van het Microsoft 365-beveiligingscentrum ( ), ziet u verschillende [https://security.microsoft.com](https://security.microsoft.com) verbeteringen in het Actiecentrum ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ).

Het geïntegreerde actiecentrum brengt herstelacties samen in Defender voor Eindpunt en Defender voor Office 365. Het definieert een gemeenschappelijke taal voor alle herstelacties en biedt een geïntegreerde onderzoekservaring. Het Actiecentrum biedt uw beveiligingsbewerkingsteam een 'enkel deelvenster met glas' om herstelacties weer te geven en te beheren.  

U kunt het geïntegreerde actiecentrum gebruiken als u de juiste machtigingen en een of meer van de volgende abonnementen hebt:

- [Defender voor Eindpunt](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Defender voor Office 365](../office-365-security/office-365-atp.md)
- [Microsoft 365 Defender](./microsoft-threat-protection.md)

> [!TIP]
> Zie Vereisten voor meer [informatie.](./prerequisites.md)

## <a name="using-the-action-center"></a>Het actiecentrum gebruiken

1. Ga naar [https://security.microsoft.com](https://security.microsoft.com) en meld u aan. 
2. Kies actiecentrum in het **navigatiedeelvenster.** 

Wanneer u het Actiecentrum bezoekt, ziet u twee tabbladen: Acties in behandeling en Geschiedenis. De volgende tabel bevat een overzicht van wat u op elk tabblad ziet:

|Tab  |Beschrijving  |
|---------|---------|
|**In behandeling**     | Hiermee wordt een lijst weergegeven met acties die aandacht vereisen. U kunt acties één voor één goedkeuren of weigeren of meerdere acties selecteren als ze hetzelfde type actie hebben (zoals Quarantainebestand). <p>**TIP:** Controleer en keur in behandeling zijnde acties zo snel mogelijk goed (of weiger) zodat uw geautomatiseerde onderzoeken tijdig kunnen worden voltooid.       |
|**Geschiedenis**     | Fungeert als een auditlogboek voor acties die zijn uitgevoerd, zoals: <br/>- Herstelacties die zijn ondernomen als gevolg van geautomatiseerde onderzoeken <br/>- Herstelacties die zijn ondernomen op verdachte of schadelijke e-mailberichten, bestanden of URL's<br/>- Herstelacties die zijn goedgekeurd door uw beveiligingsteam <br/>- Opdrachten die zijn uitgevoerd en herstelacties die zijn toegepast tijdens livereactiesessies<br/>- Herstelacties die zijn ondernomen door uw antivirusbeveiliging <p>Biedt een manier om bepaalde acties ongedaan te maken (zie [Voltooide acties ongedaan maken).](mtp-autoir-actions.md#undo-completed-actions)        |

U kunt gegevens aanpassen, sorteren, filteren en exporteren in het Actiecentrum.

:::image type="content" source="../../media/m3d-action-center-columnsfilters.png" alt-text="Met het Actiecentrum kunt u uw lijst met acties sorteren, filteren en aanpassen":::

- Selecteer een kolomkoppen om items in oplopende of aflopende volgorde te sorteren.
- Gebruik het tijdsperiodefilter om gegevens voor de afgelopen dag, week, 30 dagen of 6 maanden weer te geven.
- Kies de kolommen die u wilt weergeven.
- Geef op hoeveel items u wilt opnemen op elke pagina met gegevens.
- Gebruik filters om alleen de items te bekijken die u wilt zien.
- Selecteer **Exporteren om** resultaten te exporteren naar een CSV-bestand.

## <a name="actions-tracked-in-the-action-center"></a>Bij te houden acties in het actiecentrum

Alle acties, ongeacht of ze in behandeling zijn of al zijn genomen, worden bijgespoord in het Actiecentrum. Beschikbare acties zijn onder andere:

- Onderzoekspakket verzamelen 
- Apparaat isoleren (deze actie kan ongedaan worden gemaakt) 
- Offboard-machine 
- Uitvoering van releasecode 
- Release uit quarantaine 
- Voorbeeld aanvragen 
- Codeuitvoering beperken (deze actie kan ongedaan worden gemaakt) 
- Antivirusscan uitvoeren 
- Stoppen en in quarantaine plaatsen 

Naast herstelacties die automatisch worden ondernomen als gevolg van geautomatiseerde onderzoeken, houdt het Actiecentrum ook acties bij die uw beveiligingsteam heeft ondernomen om gedetecteerde bedreigingen aan te pakken en acties die zijn ondernomen als gevolg van functies voor [bedreigingsbeveiliging](mtp-autoir.md)in Microsoft 365 Defender. Zie Herstelacties voor meer informatie over automatische en handmatige [herstelacties.](mtp-remediation-actions.md)

## <a name="viewing-action-source-details"></a>Details van actiebron weergeven

(**NIEUW!**) Het verbeterde Actiecentrum bevat nu een **kolom Actiebron** waarin wordt be informatie over waar elke actie vandaan komt. In de volgende tabel worden mogelijke **actiebronwaarden** beschreven:

| Actiebronwaarde | Beschrijving |
|:-----|:---|
| **Handmatige apparaatactie** | Een handmatige actie op een apparaat. Voorbeelden hiervan [zijn apparaatisolatie](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network) [of bestands quarantaine.](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#stop-and-quarantine-files) |
| **Handmatige e-mailactie** | Een handmatige actie voor e-mail. Een voorbeeld hiervan is het verwijderen van e-mailberichten of [het herstellen van een e-mailbericht.](../office-365-security/remediate-malicious-email-delivered-office-365.md) |
| **Geautomatiseerde apparaatactie** | Een geautomatiseerde actie die wordt ondernomen op een entiteit, zoals een bestand of proces. Voorbeelden van geautomatiseerde acties zijn het verzenden van een bestand naar quarantaine, het stoppen van een proces en het verwijderen van een registersleutel. (Zie [Herstelacties in Microsoft Defender voor Eindpunt](/windows/security/threat-protection/microsoft-defender-atp/manage-auto-investigation#remediation-actions).) |
| **Geautomatiseerde e-mailactie** | Een geautomatiseerde actie voor e-mailinhoud, zoals een e-mailbericht, bijlage of URL. Voorbeelden van geautomatiseerde acties zijn het zacht verwijderen van e-mailberichten, het blokkeren van URL's en het uitschakelen van externe e-mail doorsturen. (Zie [Herstelacties in Microsoft Defender voor Office 365](../office-365-security/air-remediation-actions.md).) |
| **Geavanceerde actie voor de jacht** | Acties die zijn ondernomen op apparaten of e-mail [met geavanceerde zoekacties.](./advanced-hunting-overview.md) |
| **Explorer-actie** | Acties voor e-mailinhoud met [Explorer](../office-365-security/threat-explorer.md). |
| **Handmatige livereactieactie** | Acties die zijn ondernomen op een apparaat met [livereactie.](/windows/security/threat-protection/microsoft-defender-atp/live-response) Voorbeelden hiervan zijn het verwijderen van een bestand, het stoppen van een proces en het verwijderen van een geplande taak. |
| **Livereactieactie** | Acties die zijn ondernomen op een apparaat [met Microsoft Defender voor eindpunt-API's.](/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis) Voorbeelden van acties zijn het isoleren van een apparaat, het uitvoeren van een antivirusscan en het verkrijgen van informatie over een bestand. |

## <a name="required-permissions-for-action-center-tasks"></a>Vereiste machtigingen voor actiecentrumtaken

Als u taken wilt uitvoeren, zoals het goedkeuren of weigeren van acties in behandeling in het actiecentrum, moet u machtigingen hebben toegewezen zoals vermeld in de volgende tabel:

|Herstelactie |Vereiste rollen en machtigingen |
|--|----|
|Microsoft Defender voor herstel van eindpunten (apparaten) |**Beveiligingsbeheerderrol** toegewezen in Azure Active Directory ( ) of [https://portal.azure.com](https://portal.azure.com) het Microsoft 365-beheercentrum ( [https://admin.microsoft.com](https://admin.microsoft.com) )<br/>--- of ---<br/>**Rol actieve herstelacties** toegewezen in Microsoft Defender voor eindpunt <br/> <br/> Zie de volgende bronnen voor meer informatie: <br/>- [Beheerdersrolmachtigingen in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Rollen maken en beheren voor op rollen gebaseerde toegangsbeheer (Microsoft Defender voor Eindpunt)](/windows/security/threat-protection/microsoft-defender-atp/user-roles)  |
|Herstel van Microsoft Defender voor Office 365 (Office-inhoud en e-mail)  |**Beveiligingsbeheerderrol** toegewezen in Azure Active Directory ( ) of [https://portal.azure.com](https://portal.azure.com) het Microsoft 365-beheercentrum ( [https://admin.microsoft.com](https://admin.microsoft.com) )<br/>--- en --- <br/>**Zoek- en purge-rol** toegewezen aan het Beveiligings- & Compliancecentrum ( [https://protection.office.com](https://protection.office.com) ) <br/><br/>**BELANGRIJK:** Als de  rol beveiligingsbeheerder alleen is toegewezen in het Office 365-beveiligings- & compliancecentrum ( ), hebt u geen toegang tot de mogelijkheden van het Actiecentrum of [https://protection.office.com](https://protection.office.com) Microsoft 365 Defender. U moet de rol **Beveiligingsbeheerder** hebben toegewezen in Azure Active Directory of het Microsoft 365-beheercentrum. <br/><br/>Zie de volgende bronnen voor meer informatie: <br/>- [Beheerdersrolmachtigingen in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Machtigingen in het beveiligings- & compliancecentrum](../office-365-security/permissions-in-the-security-and-compliance-center.md) |

> [!TIP]
> Gebruikers die de rol **Globale beheerder** hebben toegewezen in Azure Active Directory, kunnen acties in behandeling in het actiecentrum goedkeuren of weigeren. Als beste gewoonte moet uw organisatie echter het aantal personen beperken dat de rol Globale beheerder **heeft** toegewezen. We raden u **aan** de beveiligingsbeheerder,  **actieve herstelacties** en rollen zoeken en zuiveren te gebruiken die in de vorige tabel voor machtigingen van het Actiecentrum worden vermeld.

## <a name="next-step"></a>Volgende stap 

- [Herstelacties controleren en beheren](mtp-autoir-actions.md)