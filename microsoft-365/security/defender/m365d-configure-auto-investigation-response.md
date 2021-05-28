---
title: Geautomatiseerde onderzoeks- en antwoordmogelijkheden configureren in Microsoft 365 Defender
description: Automatisch onderzoek en antwoord configureren met self-healing in Microsoft 365 Defender
search.appverid: MET150
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: autoir
ms.reviewer: evaldm, isco
f1.keywords: CSH
ms.technology: m365d
ms.openlocfilehash: 685c23f4e8daac4f00e0bbd90dcaca9a80703559
ms.sourcegitcommit: a3359982fea01339c7377e3ee89f223788cee0bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/28/2021
ms.locfileid: "52696512"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-365-defender"></a>Geautomatiseerde onderzoeks- en antwoordmogelijkheden configureren in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft 365 Defender bevat krachtige [geautomatiseerde onderzoeks- en antwoordmogelijkheden](m365d-autoir.md) die uw team voor beveiligingsbewerkingen veel tijd en moeite kunnen besparen. Met [self-healing](m365d-autoir.md#how-automated-investigation-and-self-healing-works)bootsen deze mogelijkheden de stappen na die een beveiligingsanalist zou nemen om bedreigingen te onderzoeken en te beantwoorden, alleen sneller en met meer schaalbaarheid.

In dit artikel wordt beschreven hoe u geautomatiseerd onderzoek en antwoord configureert in Microsoft 365 Defender met de volgende stappen:

1. [Controleer de vereisten.](#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
2. [Controleer of wijzig het automatiseringsniveau voor apparaatgroepen.](#review-or-change-the-automation-level-for-device-groups)
3. [Controleer uw beveiligings- en waarschuwingsbeleid in Office 365.](#review-your-security-and-alert-policies-in-office-365)
4. [Zorg ervoor Microsoft 365 Defender is ingeschakeld.](#make-sure-microsoft-365-defender-is-turned-on)

Nadat u alles hebt ingesteld, kunt u herstelacties bekijken en beheren [in het Actiecentrum.](m365d-autoir-actions.md)

## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender"></a>Vereisten voor geautomatiseerd onderzoek en antwoord in Microsoft 365 Defender

<br>

****

|Vereiste|Details|
|---|---|
|Abonnementsvereisten|Een van deze abonnementen: <ul><li>Microsoft 365 E5</li><li>Microsoft 365 A5</li><li>Microsoft 365 E3 met de Microsoft 365 E5 Security-invoegvoeging</li><li>Microsoft 365 A3 met de Microsoft 365 A5 Security-invoegvoegvoeging</li><li>Office 365 E5 plus Enterprise Mobility + Security E5 plus Windows E5</li></ul> <p> Zie [Microsoft 365 licentievereisten voor Defender.](./prerequisites.md#licensing-requirements)|
|Netwerkvereisten|<ul><li>[Microsoft Defender voor identiteit](/azure-advanced-threat-protection/what-is-atp) ingeschakeld</li><li>[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security) geconfigureerd</li><li>[Microsoft Defender voor identiteitsintegratie](/cloud-app-security/mdi-integration)</li></ul>|
|Windows machinevereisten|<ul><li>Windows 10, versie 1709 of hoger geïnstalleerd (Zie [Windows 10 releasegegevens](/windows/release-information/))</li><li>De volgende beveiligingsservices voor bedreigingen zijn geconfigureerd:<ul><li>[Microsoft Defender voor Eindpunt](../defender-endpoint/configure-endpoints.md)</li><li>[Microsoft Defender Antivirus](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)</li></ul></li></ul>|
|Beveiliging voor e-mailinhoud en Office bestanden|[Microsoft Defender voor Office 365](/microsoft-365/security/office-365-security/defender-for-office-365#configure-atp-policies) geconfigureerd|
|Machtigingen|Als u geautomatiseerde onderzoeks- en antwoordmogelijkheden wilt configureren, moet de rol globale beheerder of beveiligingsbeheerder zijn toegewezen in Azure Active Directory ( ) of in het <https://portal.azure.com> Microsoft 365 beheercentrum ( <https://admin.microsoft.com> ). <p> Zie Vereiste machtigingen voor actiecentrumtaken als u de machtigingen wilt krijgen die nodig zijn om te werken met geautomatiseerde onderzoeks- en antwoordmogelijkheden, zoals het controleren, goedkeuren of weigeren van lopende [acties.](m365d-action-center.md#required-permissions-for-action-center-tasks)|
|

## <a name="review-or-change-the-automation-level-for-device-groups"></a>Het automatiseringsniveau voor apparaatgroepen controleren of wijzigen

Of geautomatiseerde onderzoeken worden uitgevoerd en of herstelacties automatisch of alleen na goedkeuring voor uw apparaten worden uitgevoerd, is afhankelijk van bepaalde instellingen, zoals het beleid van de apparaatgroep van uw organisatie. Bekijk het geconfigureerde automatiseringsniveau voor het beleid van uw apparaatgroep.

1. Ga naar het Microsoft Defender-beveiligingscentrum ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) en meld u aan.
2. Ga naar **Instellingen**  >  **Machtigingen**  >  **Apparaatgroepen**.
3. Controleer het beleid van uw apparaatgroep. Kijk met name naar de kolom **Herstelniveau.** We raden u aan **om volledige bedreigingen automatisch te corrigeren.**  Mogelijk moet u uw apparaatgroepen maken of bewerken om het beste automatiseringsniveau te krijgen. Zie de volgende artikelen voor hulp bij deze taak:
   - [Hoe bedreigingen worden gesaneerd](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   - [Apparaatgroepen maken en beheren](/windows/security/threat-protection/microsoft-defender-atp/machine-groups)

## <a name="review-your-security-and-alert-policies-in-office-365"></a>Controleer uw beveiligings- en waarschuwingsbeleid in Office 365

Microsoft biedt ingebouwde [waarschuwingsbeleidsregels om](../../compliance/alert-policies.md) bepaalde risico's te identificeren. Deze risico's Exchange beheerdersmachtigingen misbruik, malwareactiviteit, potentiële externe en interne bedreigingen en risico's voor informatiebeheer. Sommige waarschuwingen kunnen automatisch [onderzoek en antwoord in](../office-365-security/office-365-air.md)Office 365. Zorg ervoor dat [uw Defender voor Office 365](../office-365-security/defender-for-office-365.md) functies correct zijn geconfigureerd.

Hoewel bepaalde waarschuwingen en beveiligingsbeleid geautomatiseerde onderzoeken kunnen activeren, worden er geen herstelacties automatisch voor e-mail *en inhoud ondernomen.* In plaats daarvan wachten alle herstelacties voor e-mail- en e-mailinhoud op goedkeuring van uw team voor beveiligingsbewerkingen in het [Actiecentrum.](m365d-action-center.md)

Beveiligingsinstellingen in Office 365 helpen bij het beveiligen van e-mail en inhoud. Als u deze instellingen wilt bekijken of wijzigen, volgt u de richtlijnen in [Beschermen tegen bedreigingen.](../office-365-security/protect-against-threats.md)

1. Ga in Microsoft 365 beveiligingscentrum [https://security.microsoft.com](https://security.microsoft.com) () naar **Beleidsregels & beleidsregels** \> **voor bedreigingsregels.**
2. Zorg ervoor dat alle volgende beleidsregels zijn geconfigureerd. Zie Beschermen tegen bedreigingen voor hulp en [aanbevelingen.](/microsoft-365/security/office-365-security/protect-against-threats)
   - [Anti-malware)](../office-365-security/protect-against-threats.md#part-1---anti-malware-protection-in-eop)
   - [Anti-phishing)](../office-365-security/protect-against-threats.md#part-2---anti-phishing-protection)
   - [Veilige bijlagen](../office-365-security/protect-against-threats.md#safe-attachments-policies-in-microsoft-defender-for-office-365)
   - [Veilige koppelingen](../office-365-security/protect-against-threats.md#safe-links-policies-in-microsoft-defender-for-office-365)
   - [Antispam](../office-365-security/protect-against-threats.md#part-3---anti-spam-protection-in-eop)
3. Zorg ervoor [dat Microsoft Defender voor Office 365 voor SharePoint, OneDrive en Microsoft Teams](../office-365-security/protect-against-threats.md#part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on) is ingeschakeld.
4. Zorg ervoor dat automatische purge van nul uur [voor e-mailbeveiliging](../office-365-security/protect-against-threats.md#zero-hour-auto-purge-for-email-in-eop) van kracht is.
5. (Deze stap is optioneel.) Controleer uw [Office 365 waarschuwingsbeleid](../../compliance/alert-policies.md) in het Microsoft 365 compliancecentrum ( [https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) ). Er zijn verschillende standaardwaarschuwingsbeleidsregels in de categorie Bedreigingsbeheer. Sommige van deze waarschuwingen kunnen automatisch onderzoek en antwoord activeren. Zie Standaardwaarschuwingsbeleid voor [meer informatie.](../../compliance/alert-policies.md#default-alert-policies)

## <a name="make-sure-microsoft-365-defender-is-turned-on"></a>Zorg ervoor Microsoft 365 Defender is ingeschakeld

:::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="MTP op":::

1. Meld u aan bij het Microsoft 365 beveiligingscentrum ( [https://security.microsoft.com](https://security.microsoft.com) ).
2. Zoek in het navigatiedeelvenster **naar Incidenten,** **Actiecentrum** en **Jagen,** zoals wordt weergegeven in de vorige afbeelding.
   - Als u **Incidenten,** **Actiecentrum** en **Jagen** ziet, Microsoft 365 Defender is ingeschakeld. Zie het [gedeelte Automatiseringsniveau controleren of wijzigen voor apparaatgroepen](#review-or-change-the-automation-level-for-device-groups) in dit artikel.
   - Als u *Incidenten,* **Actiecentrum** **of** Jagen niet **ziet,** is Microsoft 365 Defender mogelijk niet ingeschakeld. Ga in dit geval [naar het Actiecentrum](m365d-action-center.md)).
3. Kies in het navigatiedeelvenster **Instellingen**  >  **Microsoft 365 Defender.** Controleer of Microsoft 365 Defender is ingeschakeld.

> [!TIP]
> Hulp nodig? Zie [De Defender Microsoft 365 in- en uit.](m365d-enable.md)

## <a name="next-steps"></a>Volgende stappen

- [Herstelacties in Microsoft 365 Defender](m365d-remediation-actions.md)
- [Naar het Actiecentrum](m365d-action-center.md)
