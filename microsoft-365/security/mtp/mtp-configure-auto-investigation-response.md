---
title: Geautomatiseerd onderzoek-en antwoord mogelijkheden in Microsoft Threat Protection configureren
description: Automatisch onderzoek en antwoord met zelfherstel configureren in Microsoft Threat Protection
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 09/17/2020
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection: M365-security-compliance.
ms.custom: autoir
ms.reviewer: evaldm, isco
f1.keywords: CSH
ms.openlocfilehash: f7bcfa4f08bee51408de33964f1dfd1e1db3bd33
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199743"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-threat-protection"></a>Geautomatiseerd onderzoek-en antwoord mogelijkheden in Microsoft Threat Protection configureren

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Microsoft Threat Protection bevat krachtige [functies voor geautomatiseerde onderzoek en reacties](mtp-autoir.md) waarmee u uw beveiligingsactiviteiten team veel tijd en inspanning kunt besparen. Met dit soort functies worden de stappen van een beveiligings analist afgehandeld, maar sneller en met meer mogelijkheid om te schalen. In dit artikel wordt uitgelegd hoe u een geautomatiseerd onderzoek en antwoord kunt configureren in Microsoft Threat Protection.

Voer de volgende stappen uit om geautomatiseerde onderzoek-en antwoord mogelijkheden te configureren:

1. [Controleer de vereisten](#prerequisites-for-automated-investigation-and-response-in-microsoft-threat-protection).
2. [Het automatiserings niveau voor apparaatgroepen controleren of wijzigen](#review-or-change-the-automation-level-for-device-groups).
3. [Controleer uw beveiligings-en waarschuwings beleid in Office 365](#review-your-security-and-alert-policies-in-office-365).
4. [Zorg ervoor dat Microsoft bedreigingsbeveiliging is ingeschakeld](#make-sure-microsoft-threat-protection-is-turned-on).

Wanneer u klaar bent [met de configuratie, bekijkt u de acties in behandeling en voltooid in het Actiecentrum](#review-pending-and-completed-actions-in-the-action-center). 


## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-threat-protection"></a>Vereisten voor automatisch onderzoek en reacties op Microsoft Threat Protection

|Vereiste |Details |
|--|--|
|Vereisten voor het abonnement |Een van de abonnementen: <br/>-Microsoft 365 E5 <br/>-Microsoft 365 A5 <br/>-Microsoft 365 E5-beveiliging<br/>-Microsoft 365 A5 beveiliging<br/>-Office 365 E5 Plus Enterprise Mobility + Security E5 Plus Windows E5<br/><br/>Zie [licentievereisten voor Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements).|
|Netwerkvereisten |- [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) ingeschakeld<br/>- [Microsoft Cloud-app-beveiliging](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) geconfigureerd<br/>- [Microsoft Cloud-app-beveiliging geïntegreerd met Azure ATP](https://docs.microsoft.com/cloud-app-security/aatp-integration) |
|Systeemvereisten voor Windows |-Windows 10, versie 1709 of hoger is geïnstalleerd (Zie [informatie over de release van Windows 10](https://docs.microsoft.com/windows/release-information/)) met de volgende instellingen voor de Threat Protection-Service:<br/>- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) <br/>- [Microsoft Defender antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|Bescherming voor e-mail inhoud en Office-bestanden |[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) is geconfigureerd |
|Machtigingen |-Als u geautomatiseerde onderzoek-en antwoord functies wilt configureren, moet u beschikken over de rol van globale beheerder of beveiligingsbeheerder die is toegewezen aan Azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) of in het Microsoft 365-Beheercentrum ( [https://admin.microsoft.com](https://admin.microsoft.com) ).<br/><br/>-Voor de vereiste machtigingen voor het werken met geautomatiseerde onderzoek-en antwoord functies, zoals het controleren, goedkeuren of weigeren van acties in behandeling, raadpleegt u de [vereiste machtigingen voor taken centrum taken](mtp-action-center.md#required-permissions-for-action-center-tasks). |

## <a name="review-or-change-the-automation-level-for-device-groups"></a>Het automatiserings niveau voor apparaatgroepen controleren of wijzigen

Of geautomatiseerd onderzoek wordt uitgevoerd en of herstelacties automatisch of alleen na goedkeuring van uw apparaten worden uitgevoerd, hangt af van bepaalde instellingen, zoals het beleid van de groeps beleidsregels van uw organisatie. Bekijk het niveau van automatiserings niveau voor uw apparaat in de groepsbeleidsregels.

### <a name="to-review-or-change-your-device-group-policies"></a>Het beleid voor Groepsbeleid controleren of wijzigen

1. Ga naar het Microsoft Defender-Beveiligingscentrum ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) en meld u aan.

2. Ga naar **instellingen**van het  >  **Permissions**  >  **apparaat**machtigingen. 

3. Controleer het beleid voor Groepsbeleid. Kijk vooral naar de kolom **herstelniveau** . We raden u aan dat u de functie voor **volledig herstel van bedreigingen automatisch**gebruikt.  Mogelijk moet u de Apparaatgroepen maken of bewerken om het gewenste automatiserings niveau te kunnen bereiken. Zie de volgende artikelen voor meer informatie over deze taak:

   - [Hoe bedreigingen worden hersteld](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   
   - [Apparaatgroepen maken en beheren](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/machine-groups) 

## <a name="review-your-security-and-alert-policies-in-office-365"></a>Controleer uw beveiligings-en waarschuwings beleid in Office 365

Microsoft beschikt over ingebouwde [waarschuwings beleidsregels](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) die bijdragen aan het identificeren van bepaalde Risico's. Dit zijn de Risico's voor Exchange-beheerders, misbruik van schadelijke activiteiten, potentiële externe en interne bedreigingen en informatiebeheer Risico's. Sommige waarschuwingen kunnen [automatisch onderzoek en antwoord activeren in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air). Zorg ervoor dat de functies voor [Geavanceerde bedreigingsbeveiliging van Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) juist zijn geconfigureerd.

Hoewel bepaalde waarschuwingen en beveiligingsbeleid het automatiseren van een geautomatiseerd onderzoek mogelijk maken, worden er automatisch geen herstelacties uitgevoerd voor e-mail en inhoud. In plaats daarvan worden alle herstelacties voor e-mailberichten en e-mail inhoud met de goedkeuring in het [Actiecentrum](mtp-action-center.md)wel goedgekeurd door het team van uw beveiligingsactiviteiten.

### <a name="to-view-or-change-your-security-and-alert-policies-in-office-365"></a>Het beleid voor beveiliging en waarschuwingen weergeven of wijzigen in Office 365

Met behulp van beveiligingsinstellingen in Office 365 kunt u e-mail en inhoud beveiligen. Als u deze instellingen wilt bekijken of wijzigen, volgt u de richtlijnen in [beveiliging tegen bedreigingen](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats).

1. Ga in het Microsoft 365 Security Center ( [https://security.microsoft.com/](https://security.microsoft.com/) ) naar **beleids**  >  **beveiliging tegen**beleid.

2. Zorg ervoor dat alle volgende beleidsregels zijn geconfigureerd. Voor hulp en aanbevelingen raadpleegt u [bescherming tegen bedreigingen](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats).

   - [Anti malware (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-1---anti-malware-protection)
   - [ATP anti-phishing (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-2---anti-phishing-protection)
   - [Veilige bijlage van ATP (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-attachments-policies)
   - [Veilige koppelingen voor ATP (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-links-policies)
   - [Anti spam (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-3---anti-spam-protection) 

4. Zorg ervoor dat [Office 365 ATP voor SharePoint, OneDrive en Microsoft teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-5---turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams-workloads) is ingeschakeld.

5. Zorg ervoor dat de [automatische opschoning van Zero uur voor e-mail](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#zero-hour-auto-purge-for-email-in-eop) beveiliging is ingeschakeld. 

8. (Dit is optioneel) Controleer uw [waarschuwings beleid voor Office 365](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) in het nalevings centrum van microsoft 365 ( [https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) ). Een aantal standaard waarschuwings beleidsregels bevindt zich in de categorie Threat Management. Sommige van deze meldingen kunnen automatisch onderzoek en antwoord activeren. Voor meer informatie raadpleegt u [standaard waarschuwings beleid](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?#default-alert-policies).
 
## <a name="make-sure-microsoft-threat-protection-is-turned-on"></a>Zorg ervoor dat Microsoft Bedreigingsbeveiliging is ingeschakeld

1. Ga naar het Microsoft 365-Beveiligingscentrum ( [https://security.microsoft.com](https://security.microsoft.com) ) en meld u aan.

2. Zoek in het navigatiedeelvenster naar **incidenten**, **Onderhoudscentrum**en **jacht**, zoals wordt weergegeven in de volgende afbeelding:<br/> :::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="MTP ingeschakeld":::

   - Als u **incidenten**, **Onderhoudscentrum**, **jacht en jacht**ziet, is Microsoft Threat Protection ingeschakeld. Ga verder met de volgende procedure, [het automatiserings niveau voor apparaatgroepen controleren of wijzigen](#review-or-change-the-automation-level-for-device-groups).

   - Als u *geen* **incidenten**, **Onderhoudscentrum**of **jacht**ziet, is Microsoft Threat Protection mogelijk niet ingeschakeld. Ga in dit geval verder met de volgende stap.

3. Kies in het navigatiedeelvenster de optie **instellingen**  >  **Microsoft Threat Protection**. Ga na of Microsoft bedreiging voor beveiliging is ingeschakeld. 

   Hulp nodig? Zie [Microsoft Threat Protection inschakelen](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable).

## <a name="review-pending-and-completed-actions-in-the-action-center"></a>Acties in behandeling en voltooid bekijken in het Actiecentrum

Nadat u automatisch onderzoek en antwoord hebt geconfigureerd in Microsoft Threat Protection, kunt u de volgende stap bezoeken om het Actiecentrum te openen [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) . Daar kunt u de acties die in behandeling zijn, controleren en goedkeuren en verwerkings acties weergeven die automatisch zijn doorgevoerd. 

[Bezoek het Actiecentrum](mtp-action-center.md).
