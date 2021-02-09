---
title: Geautomatiseerde onderzoeks- en antwoordmogelijkheden configureren in Microsoft 365 Defender
description: Geautomatiseerd onderzoek en automatisch onderzoek configureren met self-of-spam in Microsoft 365 Defender
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.date: 02/08/2021
ms.custom: autoir
ms.reviewer: evaldm, isco
f1.keywords: CSH
ms.technology: m365d
ms.openlocfilehash: 311b5e85055d48fb653c4ca42826f0a92267b00e
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/08/2021
ms.locfileid: "50144995"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-365-defender"></a>Geautomatiseerde onderzoeks- en antwoordmogelijkheden configureren in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft 365 Defender bevat krachtige [geautomatiseerde](mtp-autoir.md) onderzoeks- en antwoordmogelijkheden die uw team voor beveiligingsbewerkingen veel tijd en moeite kunnen besparen. Met [zelfkritisch](mtp-autoir.md#how-automated-investigation-and-self-healing-works)werken deze functies de stappen na die een beveiligingsanalist zou ondernemen om bedreigingen te onderzoeken en te beantwoorden, alleen sneller en met meer schaalmogelijkheden. In dit artikel wordt beschreven hoe u geautomatiseerd onderzoek en antwoorden in Microsoft 365 Defender kunt configureren.

Als u geautomatiseerde onderzoeks- en antwoordmogelijkheden wilt configureren, gaat u als volgt te werk:

1. [Controleer de vereisten.](#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
2. [Controleer of wijzig het automatiseringsniveau voor apparaatgroepen.](#review-or-change-the-automation-level-for-device-groups)
3. [Controleer het beveiligings- en waarschuwingsbeleid in Office 365.](#review-your-security-and-alert-policies-in-office-365)
4. [Zorg ervoor dat Microsoft 365 Defender is ingeschakeld.](#make-sure-microsoft-365-defender-is-turned-on)

Vervolgens kunt u, nadat u alles hebt ingesteld, acties weergeven en [beheren in het actiecentrum.](mtp-autoir-actions.md)

## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender"></a>Vereisten voor geautomatiseerd onderzoek en antwoorden in Microsoft 365 Defender

|Vereiste |Details |
|:----|:----|
|Abonnementsvereisten |Een van deze abonnementen: <br/>- Microsoft 365 E5<br/>- Microsoft 365 A5<br/>- Microsoft 365 E5-beveiliging<br/>- Microsoft 365 A5-beveiliging<br/>- Office 365 E5 plus Enterprise Mobility + Security E5 plus Windows E5<p> Zie [de licentievereisten voor Microsoft 365 Defender.](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements)|
|Netwerkvereisten |- [Microsoft Defender voor identiteit](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) ingeschakeld<br/>- [Microsoft Cloud-app-beveiliging](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) geconfigureerd<br/>- [Integratie van Microsoft Defender voor identiteit](https://docs.microsoft.com/cloud-app-security/mdi-integration) |
|Vereisten voor Windows-machine |- Windows 10, versie 1709 of hoger geïnstalleerd (zie release-informatie [voor Windows 10)](https://docs.microsoft.com/windows/release-information/) <br/>- De volgende bedreigingsbeveiligingsservices geconfigureerd:<br/>- [Microsoft Defender voor eindpunt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)<br/>- [Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|Beveiliging voor e-mailinhoud en Office-bestanden |[Microsoft Defender voor Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) geconfigureerd |
|Machtigingen | Als u geautomatiseerde onderzoeks- en antwoordmogelijkheden wilt configureren, moet de rol Globale beheerder of Beveiligingsbeheerder zijn toegewezen in Azure Active Directory ( ) of in het [https://portal.azure.com](https://portal.azure.com) Microsoft 365-beheercentrum ( [https://admin.microsoft.com](https://admin.microsoft.com) ).<p>Zie Vereiste machtigingen voor taken in het Actiecentrum als u wilt weten welke machtigingen u nodig hebt om te werken met geautomatiseerde onderzoeks- en antwoordmogelijkheden, zoals het controleren, goedkeuren of weigeren van acties die in behandeling [zijn.](mtp-action-center.md#required-permissions-for-action-center-tasks) |

## <a name="review-or-change-the-automation-level-for-device-groups"></a>Het automatiseringsniveau voor apparaatgroepen controleren of wijzigen

Of geautomatiseerde onderzoeken worden uitgevoerd en of herstelacties automatisch of alleen bij goedkeuring voor uw apparaten worden uitgevoerd, hangt af van bepaalde instellingen, zoals het apparaatgroepsbeleid van uw organisatie. Bekijk het automatiseringsniveau dat is ingesteld voor het groepsbeleid voor apparaten.

1. Ga naar het Microsoft Defender-beveiligingscentrum [https://securitycenter.windows.com](https://securitycenter.windows.com) () en meld u aan.
2. Ga naar  >  **Apparaatgroepen met instellingenmachtigingen.**  >  
3. Controleer het beleid van uw apparaatgroep. Bekijk met name de kolom **op herstelniveau.** We raden u aan **om de bedreigingen automatisch te herstellen met Volledige oplossing.**  Mogelijk moet u uw apparaatgroepen maken of bewerken om het bepaalde automatiseringsniveau te krijgen. Zie de volgende artikelen voor hulp bij deze taak:
   - [Hoe bedreigingen worden verteerd](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   - [Apparaatgroepen maken en beheren](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/machine-groups)

## <a name="review-your-security-and-alert-policies-in-office-365"></a>Uw beveiligings- en waarschuwingsbeleid in Office 365 controleren

Microsoft biedt ingebouwde [beleidsregels voor waarschuwingen die](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) u kunt gebruiken om bepaalde risico's vast te stellen. Deze risico's zijn onder andere misbruik van Exchange-beheerdersmachtigingen, malwareactiviteit, potentiële externe en interne bedreigingen en informatiebeheerrisico's. Sommige waarschuwingen kunnen automatische onderzoeken [en antwoorden activeren in Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) Zorg ervoor dat [de functies van Microsoft Defender voor Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) correct zijn geconfigureerd.

Hoewel bepaalde waarschuwingen en beveiligingsbeleid geautomatiseerde onderzoeken kunnen activeren, worden er niet automatisch herstelacties ondernomen voor e-mail en inhoud. In plaats daarvan wachten alle herstelacties voor e-mail en e-mailinhoud op goedkeuring door het team voor beveiligingsbewerkingen in [het actiecentrum.](mtp-action-center.md)

Beveiligingsinstellingen in Office 365 helpen e-mail en inhoud te beschermen. Als u deze instellingen wilt weergeven of wijzigen, volgt u de richtlijnen in [Beveiligen tegen bedreigingen.](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)

1. Ga in het Microsoft 365-beveiligingscentrum ( [https://security.microsoft.com](https://security.microsoft.com) ) naar **Policies**  >  **Threat Protection.**
2. Zorg ervoor dat alle volgende beleidsregels zijn geconfigureerd. Zie Beveiligen tegen bedreigingen voor hulp [en aanbevelingen.](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)
   - [Anti-malware (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-1---anti-malware-protection)
   - [Anti-phishing in Defender voor Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-2---anti-phishing-protection)
   - [Veilige bijlagen (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-attachments-policies)
   - [Veilige koppelingen (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-links-policies)
   - [Antispam (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-3---anti-spam-protection)
3. Zorg ervoor [dat Microsoft Defender voor Office 365 voor SharePoint, OneDrive en Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-5---turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams-workloads) is ingeschakeld.
4. Zorg ervoor [dat automatisch nul-uurs purge voor](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#zero-hour-auto-purge-for-email-in-eop) e-mailbeveiliging van kracht is.
5. (Deze stap is optioneel.) Controleer uw [Office 365-waarschuwingsbeleid](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) in het Microsoft 365-compliancecentrum ( [https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) ). Er zijn verschillende standaardbeleidsregels voor waarschuwingen in de categorie Risicobeheer. Sommige van deze waarschuwingen kunnen automatische onderzoeken en antwoorden activeren. Zie Beleidsregels voor [standaardwaarschuwingen voor meer informatie.](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?#default-alert-policies)

## <a name="make-sure-microsoft-365-defender-is-turned-on"></a>Zorg ervoor dat Microsoft 365 Defender is ingeschakeld

:::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="MTP aan":::

1. Ga naar het Microsoft 365-beveiligingscentrum [https://security.microsoft.com](https://security.microsoft.com) () en meld u aan.
2. Zoek in het navigatiedeelvenster naar **Incidenten,** **Actiecentrum** en **Zoeken,** zoals in de voorgaande afbeelding.
   - Als u **Incidenten,** **Actiecentrum en** **Zoeken** ziet, is Microsoft 365 Defender ingeschakeld. Zie de procedure, [Het automatiseringsniveau voor](#review-or-change-the-automation-level-for-device-groups) apparaatgroepen bekijken of wijzigen (in dit artikel).
   - Als U *Incidenten,* **Actiecentrum** of **Zoeken** niet ziet, is Microsoft 365 Defender mogelijk niet ingeschakeld.  In dit geval gaat u naar [Het actiecentrum bezoeken.](mtp-action-center.md)
3. Kies Instellingen Microsoft   >  **365 Defender** in het navigatiedeelvenster. Controleer of Microsoft 365 Defender is ingeschakeld. 

> [!TIP]
> Hulp nodig? Zie [Microsoft 365 Defender in turn on.](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable)

## <a name="next-steps"></a>Volgende stappen

- [Herstelacties in Microsoft 365 Defender](mtp-remediation-actions.md)
- [Naar het Actiecentrum](mtp-action-center.md)
