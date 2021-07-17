---
title: Architectuurvereisten en planningsconcepten voor Microsoft Defender bekijken voor Office 365, bouw-, bouw- en ontwerpkaders
description: Het technische diagram voor Microsoft Defender voor Office 365 in Microsoft 365 Defender helpt u bij het begrijpen van identiteiten in Microsoft 365 voordat u uw proeflaboratorium of testomgeving maakt.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 07/01/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 15c84921dcfb4644241cf83ce4ffb6403180b9d4
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457878"
---
# <a name="review-microsoft-defender-for-office-365-architecture-requirements-and-key-concepts"></a>Microsoft Defender bekijken voor Office 365 architectuurvereisten en belangrijke concepten


**Van toepassing op:**
- Microsoft 365 Defender

Dit artikel is [stap 1 van 3](eval-defender-office-365-overview.md) in het proces van het instellen van de evaluatieomgeving voor Microsoft Defender voor Office 365. Zie het [overzichtsartikel](eval-defender-office-365-overview.md)voor meer informatie over dit proces.

Voordat u Defender inschakelen Office 365, moet u de architectuur begrijpen en aan de vereisten voldoen. In dit artikel worden de architectuur, de belangrijkste concepten en de vereisten beschreven waar uw Exchange Online aan moet voldoen.

## <a name="understand-the-architecture"></a>De architectuur begrijpen

In het volgende diagram wordt de basislijnarchitectuur voor Microsoft Defender Office die een SMTP-gateway van derden of on-premises integratie kan bevatten. Hybride coëxistentiescenario's (d.i. productiepostvakken zijn zowel on-premises als online) vereisen complexere configuraties en worden niet behandeld in dit artikel of evaluatierichtsnoer.

![Architectuur voor Microsoft Defender voor Office 365](../../media/defender/m365-defender-office-architecture.png)

In de volgende tabel wordt deze afbeelding beschreven.

|Uitroepen  |Omschrijving  |
|---------|---------|
|1     | De hostserver voor de externe afzender voert meestal een openbare DNS-opzoekactie uit naar een MX-record, waarmee de doelserver het bericht door kan sturen.  Deze verwijzing kan rechtstreeks Exchange Online (EXO) of een SMTP-gateway die is geconfigureerd om door te geven tegen EXO.  |
|2     | Exchange Online Protection onderhandelt en valideert de inkomende verbinding en controleert de berichtkoppen en inhoud om te bepalen welk extra beleid, labeling of verwerking vereist is.  |
|3     | Exchange Online is geïntegreerd met Microsoft Defender voor Office 365 om geavanceerdere bedreigingsbeveiliging, beperking en herstel te bieden. |
|4     | Een bericht dat niet schadelijk, geblokkeerd of in quarantaine is geplaatst, wordt verwerkt en bezorgd bij de geadresseerde in EXO, waar gebruikersvoorkeuren met betrekking tot ongewenste e-mail, postvakregels of andere instellingen worden geëvalueerd en geactiveerd. |
|5     | Integratie met on-premises Active Directory kan worden ingeschakeld met Azure AD Verbinding maken om objecten en accounts met e-mail te synchroniseren en in te delen op Azure Active Directory en Exchange Online. |
|6     | Wanneer u een on-premises omgeving integreert, wordt het sterk aangeraden een Exchange-server te gebruiken voor ondersteund beheer en beheer van e-mailgerelateerde kenmerken, instellingen en configuraties |
|7     | Microsoft Defender voor Office 365 deelt signalen naar Microsoft 365 Defender voor uitgebreide detectie en respons (XDR).|

On-premises integratie is gebruikelijk, maar optioneel. Als uw omgeving alleen cloud is, werkt deze richtlijn ook voor u.

## <a name="understand-key-concepts"></a>Belangrijke concepten begrijpen

In de volgende tabel worden belangrijke concepten geïdentificeerd die belangrijk zijn om te begrijpen bij het evalueren, configureren en implementeren van MDO.


|Concept  |Omschrijving |Meer informatie  |
|---------|---------|---------|
|Exchange Online Protection      |    Exchange Online Protection (EOP) is de cloudfilterservice die uw organisatie helpt beschermen tegen spam- en malware-e-mailberichten. EOP is opgenomen in alle Microsoft 365 licenties die Exchange Online.     |   [Overzicht Exchange Online Protection](../office-365-security/exchange-online-protection-overview.md)      |
|Beveiliging tegen malware     |    Organisaties met postvakken in EXO worden automatisch beschermd tegen malware.     |  [Anti-malwarebeveiliging in EOP](../office-365-security/anti-malware-protection.md)       |
|Beveiliging tegen ongewenste e-mail     |   Organisaties met postvakken in EXO worden automatisch beschermd tegen ongewenste e-mail en spambeleid.      |  [Bescherming tegen spam in EOP](../office-365-security/anti-spam-protection.md)       |
|Bescherming tegen phishing |  MDO biedt geavanceerdere bescherming tegen phishing met betrekking tot phishing, whaling, ransomware en andere schadelijke activiteiten.   | [Aanvullende bescherming tegen phishing in Microsoft Defender voor Office 365](../office-365-security/anti-phishing-protection.md)   |
|Beveiliging tegen adresvervalsing (spoofing)     |   EOP bevat functies om uw organisatie te beschermen tegen vervalste (vervalste) afzenders.      |   [Beveiliging tegen adresvervalsing in EOP](../office-365-security/anti-spoofing-protection.md)      |
|Veilige bijlagen     |   Safe Bijlagen bieden een extra beveiligingslaag door een virtuele omgeving te gebruiken om bijlagen in e-mailberichten te controleren en te 'laten onttonen' voordat ze worden bezorgd.      |   [Safe Bijlagen in Microsoft Defender voor Office 365](../office-365-security/safe-attachments.md)      |
|Safe bijlagen voor SharePoint, OneDrive en Microsoft Teams     |    Daarnaast biedt Safe Bijlagen voor SharePoint, OneDrive en Microsoft Teams een extra beveiligingslaag voor bestanden die zijn geüpload naar opslagopslag in de cloud.     |  [Veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams](../office-365-security/mdo-for-spo-odb-and-teams.md)       |
|Veilige koppelingen     | Safe Koppelingen is een functie waarmee URL's worden gescand en herschreven in binnenkomende e-mailberichten en waarmee deze koppelingen worden geverifieerd voordat ze worden bezorgd of geklikt.        |   [Safe Koppelingen in Microsoft Defender voor Office 365](../office-365-security/safe-links.md)      |
|    |         |         |

Zie Microsoft Defender voor meer informatie over de mogelijkheden van Microsoft Defender Office voor meer informatie [over Office 365 servicebeschrijving.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

## <a name="review-architecture-requirements"></a>Architectuurvereisten controleren
Een succesvolle MDO-evaluatie- of productiepilot gaat uit van de volgende vereisten:
- Alle postvakken van de geadresseerde zijn momenteel in Exchange Online.
- Uw openbare MX-record wordt rechtstreeks naar EOP of een SMTP-gateway van derden verzonden, die vervolgens binnenkomende externe e-mail rechtstreeks doorverdient naar EOP.
- Uw primaire e-maildomein is geconfigureerd als *gezaghebbend* in Exchange Online.
- U hebt mapgebaseerd *edgeblocking* (DBEB) zo nodig geïmplementeerd en geconfigureerd. Zie Directory Based Edge Blocking gebruiken om berichten te weigeren die naar ongeldige [geadresseerden zijn verzonden](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)voor meer informatie.

> [!IMPORTANT]
> Als deze vereisten niet van toepassing zijn of als u nog steeds in een hybride coëxistentiescenario werkt, kan een Microsoft Defender voor Office 365-evaluatie complexere of geavanceerdere configuraties vereisen die niet volledig in deze richtlijnen worden behandeld.

## <a name="siem-integration"></a>SIEM-integratie

U kunt Microsoft Defender voor Office 365 integreren met Azure Sentinel om beveiligingsgebeurtenissen in uw organisatie uitgebreider te analyseren en playbooks te maken voor een effectieve en onmiddellijke reactie. Zie voor meer informatie [Verbinding maken waarschuwingen van Microsoft Defender voor Office 365.](/azure/sentinel/connect-office-365-advanced-threat-protection)

Microsoft Defender voor Office 365 kan ook worden geïntegreerd in andere SIEM-oplossingen (Security Information and Event Management) met de [Office 365 Activity Management API](/office/office-365-management-api/office-365-management-activity-api-reference).

## <a name="next-steps"></a>Volgende stappen

Stap 2 van 3: [De evaluatieomgeving van Microsoft Defender inschakelen voor Office 365](eval-defender-office-365-enable-eval.md)

Ga terug naar het overzicht voor [Microsoft Defender evalueren voor Office 365](eval-defender-office-365-overview.md)

Ga terug naar het overzicht voor [Evalueren en Microsoft 365 Defender](eval-overview.md) 

