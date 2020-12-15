---
title: Ga naar het Actiecentrum voor het weergeven en goedkeuren van uw automatisch onderzoek en hersteltaken
description: In het Actiecentrum vindt u meer informatie over geautomatiseerde onderzoek en het goedkeuren van acties met de status
keywords: Onderhoudscentrum, bedreigingsbeveiliging, onderzoek, waarschuwing, in behandeling, automatisch, detectie
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: aa9f433bc60949aa625d9346421b025121347a2c
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683317"
---
# <a name="the-action-center"></a>Het Actiecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

Gebruik het Actiecentrum ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) om de resultaten van huidig en vorig onderzoek over de apparaten en postvakken van uw organisatie te bekijken. Afhankelijk van het type Threat en resultd Verdict, kunnen [herstelacties](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) automatisch of na goedkeuring plaatsvinden via het team van uw organisatie. Alle herstelacties, of ze nu moeten worden goedgekeurd of al zijn goedgekeurd, worden in het Actiecentrum geconsolideerd. 

![Actiecentrum](../../media/air-actioncenter.png)

## <a name="a-single-pane-of-glass-experience"></a>Een "één ruit glas"-ervaring

Het Actiecentrum biedt een ' één ruit ruit ' voor taken, zoals:
- Acties voor herstel in behandeling goedkeuren;
- Een auditlogboek met al goedgekeurde herstelacties weergeven. en
- U bekijkt voltooide herstelbewerkingen.

Uw team van beveiligingsactiviteiten kan effectiever en efficiënt werken omdat het Actiecentrum een uitgebreide weergave biedt van Microsoft 365 Defender op het werk.

## <a name="go-to-the-action-center"></a>Ga naar het Actiecentrum

1. Ga naar [https://security.microsoft.com](https://security.microsoft.com) en meld u aan. 

2. Kies in het navigatiedeelvenster de optie **Onderhoudscentrum**. 

3. In het Actiecentrum ziet u twee tabbladen: **in behandeling** en **geschiedenis**.

    - Het tabblad **in behandeling** bevat verificatieverzoeken die moeten worden gecontroleerd en goedgekeurd door iemand in uw Beveiligingsteam om door te gaan. Zorg ervoor dat u de items die in behandeling zijn, controleert en actie onderneemt.

    - Het tabblad **geschiedenis** bevat eerdere onderzoeken-en herstelacties die automatisch zijn doorgevoerd. U kunt de gegevens voor de afgelopen dag, week, maand of zes maanden weergeven.

4. Als u alleen de kolommen wilt weergeven die u wilt weergeven, selecteert u **kolommen aanpassen**.<br/>![Actiecentrum in Microsoft 365 Defender](../../media/mtp-action-center.png)

5. Selecteer een item in de lijst om meer details over een onderzoek te bekijken. De weergave Details van onderzoek wordt geopend.<br/>![Details van onderzoek](../../media/mtp-air-investdetails.png)

    - Als het onderzoek betrekking heeft op e-mail inhoud (zoals de entiteit is een postvak), worden details van onderzoek geopend in het beveiligings & compliance Center ( [https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation) ). 

    - Als het onderzoek een apparaat omvat, worden details van het onderzoek geopend in het Beveiligingscentrum ( [https://security.microsoft.com](https://security.microsoft.com) ). 

> [!TIP]
> Laat het ons weten als u denkt dat er een probleem is opgetreden met een automatisch onderzoek en antwoord functies in Microsoft 365 Defender. Lees [hoe u in Microsoft 365 Defender onjuiste positieve en negatieve functies kunt melden voor automatisch onderzoek en Reacties (lucht)](mtp-autoir-report-false-positives-negatives.md).

## <a name="available-actions"></a>Beschikbare acties

Wanneer herstelacties worden uitgevoerd, worden deze weergegeven op het tabblad **geschiedenis** in het Actiecentrum. Dit zijn onder andere de volgende acties:

- Onderzoek pakket verzamelen 
- Apparaat isoleren (deze actie kan ongedaan worden gemaakt) 
- Verwijderen-computer 
- Uitvoering van release code 
- Release van quarantaine 
- Voorbeeld van aanvraag 
- Uitvoering van code beperken (deze actie kan ongedaan worden gemaakt) 
- Antivirus scan uitvoeren 
- Stoppen en quarantineen 

> [!NOTE]
> Naast de acties voor herstel die automatisch worden uitgevoerd, kunnen uw beveiligingsteam voor een handmatige actie maken van gedetecteerde bedreigingen. Zie voor meer informatie over automatische en handmatige herstelacties voor [herstelacties](mtp-remediation-actions.md).

## <a name="action-source"></a>Actie bron

(**Nieuw!**) Zoals u weet, brengt Microsoft 365 Defender automatisch onderzoek en antwoord mogelijkheden samen in meerdere services, zoals [Microsoft Defender voor eindpunten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) en [Microsoft Defender voor Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp). Het nieuwe en verbeterde Onderhoudscentrum bevat nu een kolom met een **actie bron** waarmee wordt aangegeven waar elke herstelactie vandaan komt. 

In de volgende tabel worden mogelijke waarden voor de **actie bronnen** beschreven:

| Waarde van actie bron | Beschrijving |
|:-----|:---|
| **Handmatige actie bij apparaat** | Een handmatige actie die op een apparaat is uitgevoerd. Voorbeelden hiervan zijn [isolatie van apparaten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network) of [Bestands quarantaine](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#stop-and-quarantine-files). |
| **Handmatige e-mail actie** | Een handmatige actie die heeft plaatsgevonden voor e-mail. Een voorbeeld is een voorbeeld van een tijdelijke verwijdering van e-mailberichten of [het herstellen van een e-mailbericht](https://docs.microsoft.com/microsoft-365/security/office-365-security/remediate-malicious-email-delivered-office-365). |
| **Actie automatisch apparaat** | Een geautomatiseerde actie die wordt uitgevoerd door een entiteit, zoals een bestand of proces. Voorbeelden van geautomatiseerde acties, waaronder het verzenden van een bestand naar Quarantine, stoppen van een proces, en het verwijderen van een registersleutel. (Zie [herstelacties in Microsoft Defender voor eindpunt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-auto-investigation#remediation-actions).) |
| **Geautomatiseerd e-mail actie** | Een geautomatiseerde actie die heeft plaatsgevonden voor e-mail inhoud, zoals een e-mailbericht, bijlage of URL. Voorbeelden van geautomatiseerde acties zijn een tijdelijke verwijdering van e-mailberichten, het blokkeren van Url's en uitschakelen van externe e-mail doorsturen. (Zie [herstelacties in Microsoft Defender voor Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions).) |
| **Geavanceerde jacht actie** | Acties die worden uitgevoerd op apparaten of e-mail met [geavanceerde jacht](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-overview). |
| **Verkenner, actie** | Acties die worden uitgevoerd op e-mail inhoud met [Explorer](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer). |
| **Handmatige actie van Live antwoord** | Acties die worden uitgevoerd op een apparaat met [Live antwoord](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response). Voorbeelden hiervan zijn een bestand verwijderen, een proces stoppen en een geplande taak verwijderen. |
| **Actie met Live antwoord** | Acties die worden uitgevoerd op een apparaat met [Microsoft Defender voor eindpunten-api's](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis). Voorbeelden van acties zijn het isoleren van een apparaat, het uitvoeren van antivirus scans en het verkrijgen van informatie over een bestand. |

## <a name="required-permissions-for-action-center-tasks"></a>Vereiste machtigingen voor taken in het Actiecentrum

Als u in het Actiecentrum in behandeling zijnde acties wilt goedkeuren of weigeren, moet u beschikken over de machtigingen die zijn toegewezen aan de hand van de volgende tabel:

|Herstelactie |Vereiste rollen en machtigingen |
|--|----|
|Microsoft Defender voor herstel van eindpunten (apparaten) |Rollen van beveiligingsbeheerders toegewezen in azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) of het Microsoft 365-Beheercentrum ( [https://admin.microsoft.com](https://admin.microsoft.com) )<br/>------<br/>De rol Active aanherstel actie toegewezen in Microsoft Defender voor eindpunt <br/> <br/> Zie de volgende bronnen voor meer informatie: <br/>- [Machtigingen voor beheerdersrollen in azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Rollen maken en beheren voor toegangsbeheer op basis van rollen (Microsoft Defender voor eindpunt)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)  |
|Microsoft Defender voor Office 365 herstel (Office-inhoud en e-mail)  |Rollen van beveiligingsbeheerders toegewezen in azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) of het Microsoft 365-Beheercentrum ( [https://admin.microsoft.com](https://admin.microsoft.com) )<br/>---en--- <br/>Rol zoeken en wissen toegewezen aan de beveiligings & compliance Center ( [https://protection.office.com](https://protection.office.com) ) <br/><br/>**Belangrijk**: als u alleen de rol van beveiligingsbeheerder hebt toegewezen aan de beveiligings & nalevings centrum, hebt u geen toegang tot de mogelijkheden van het Actiecentrum of microsoft 365. U moet de rol van beveiligingsbeheerder zijn toegewezen in azure Active Directory of het Microsoft 365-Beheercentrum. <br/><br/>Zie de volgende bronnen voor meer informatie: <br/>- [Machtigingen voor beheerdersrollen in azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Machtigingen in het nalevings centrum voor beveiligings &](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!NOTE]
> Gebruikers met de rol van globale beheerder die zijn toegewezen aan Azure Active Directory, kunnen een actie in behandeling goedkeuren of weigeren in het Actiecentrum. De beste manier om het aantal personen met de rol van globale beheerder in de organisatie te beperken. U wordt aangeraden gebruik te maken van de bovenstaande beveiligingsbeheerder, actieve herstelacties en de hierboven vermelde functies voor het Actiecentrum.

## <a name="next-steps"></a>Volgende stappen 

- [Acties die in behandeling zijn, goedkeuren of weigeren na een geautomatiseerd onderzoek](mtp-autoir-actions.md)
- [De resultaten van een geautomatiseerd onderzoek weergeven](mtp-autoir-results.md)

