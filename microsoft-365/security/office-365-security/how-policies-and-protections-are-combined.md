---
title: Hoe beleid en beveiligingen worden gecombineerd wanneer e-mail rood gemarkeerd is
description: Beschrijft welk beleid en beveiligingen van toepassing zijn wanneer e-mail meerdere beveiligingen tegenkomt en wordt gescand door meerdere vormen van detectie. Welk beleid is van toepassing en welke acties moeten worden ondernomen wanneer e-mail is gemarkeerd als malware, spam, spam met veel vertrouwen, phishing en bulk door EOP en/of ATP.
keywords: beveiliging, malware, Microsoft 365, M365, beveiligingscentrum, ATP, Microsoft Defender ATP, Office 365 ATP, Azure ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: 03/26/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: c6b3fcc931aa396187eb81d0db495f77877f667b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42812424"
---
# <a name="what-policy-applies-when-multiple-protection-methods-and-detection-scans-run-on-your-email"></a>Welk beleid is van toepassing wanneer meerdere beveiligingsmethoden en detectiescans op uw e-mail worden uitgevoerd

Mogelijk kan uw inkomende e-mail worden gemarkeerd door meerdere vormen van bescherming (bijvoorbeeld EOP *en* ATP) en meerdere detectiescans (zoals spam *en* phishing). Dit is mogelijk omdat er ATP Anti-phishing-beleid voor ATP-klanten en EOP Anti-phishing beleid voor EOP-klanten. Dit betekent ook dat het bericht meerdere detectiescans kan doornemen voor bijvoorbeeld malware, phishing en imitatie van gebruikers. Gezien al deze activiteiten kan er enige verwarring bestaan over welk beleid van toepassing is.

In het algemeen wordt een beleid dat op een bericht wordt toegepast, geïdentificeerd in de header **X-Forefront-Antispam-Report** in de eigenschap **CAT (Categorie).** Als u meerdere antiphishingbeleidsregels hebt, is deze met de hoogste prioriteit van toepassing.

Het onderstaande beleid is van toepassing op _alle organisaties._

|Priority |Beleid  |Categorie  |Waar beheerd |
|---------|---------|---------|---------|
|1     | Malware      | MALW (MALW)      | Malwarebeleid   |
|2     | Phishing     | PHSH PHSH     | Uw beleid voor spamfilters configureren     |
|3     | Veel vertrouwen spam      | HSPM (HSPM)        | Uw beleid voor spamfilters configureren        |
|4     | Spoofing        | Spoof        | Anti-phishing beleid, spoof intelligentie        |
|5     | Spam         | Spm         | Uw beleid voor spamfilters configureren         |
|6     | Bulk         | Bulk        | Uw beleid voor spamfilters configureren         |

Bovendien zijn deze beleidsregels van toepassing op _organisaties met ATP._

|Priority |Beleid  |Categorie  |Waar beheerd |
|---------|---------|---------|---------|
|7     | Imitatie van domeinen         | DIMP (DIMP)         | Office 365 ATP antiphishing- en antiphishingbeleid instellen        |
|8     | Imitatie van gebruiker        | UIMP (UIMP)         | Office 365 ATP antiphishing- en antiphishingbeleid instellen         |

Als u bijvoorbeeld twee beleidsregels hebt met hun respectieve prioriteiten:

|Beleid  |Priority  |Imitatie van gebruiker/domein  |Anti-spoofing  |
|---------|---------|---------|---------|
|A     | 1        | Op        |Uit         |
|B     | 2        | Uit        | Op        |

Als een bericht wordt geïdentificeerd als zowel _gebruikersimitatie_ als _spoofing_ (zie anti-spoofing in de bovenstaande tabel) en dezelfde set gebruikers die zijn ingesteld op beleid A, wordt het bericht gemarkeerd en behandeld als een _spoof_. Er wordt echter geen actie toegepast omdat hoewel spoof wordt uitgevoerd met een hogere prioriteit (4) dan User Impersonation (8), anti-spoofing is uitgeschakeld.

Houd er rekening mee dat beheerders een geprioriteerd lijst met beleidsregels kunnen maken (zie het prioriteitsveld hierboven), maar slechts één beleid voert de acties uit en past deze toe. Dat betekent dat een gebruiker in zowel beleid A als B het beleid met een hogere prioriteit (A is #1) zal uitvoeren en dat het bericht niet door verdere beleidsregels wordt gefilterd. Als de anti-spoofiing is uitgeschakeld, worden er geen acties uitgevoerd.

Omdat er een potentieel is om veel groepen gebruikers in veel beleidsregels te hebben, kan het zijn dat beheerders overwegen om minder beleidsregels met meer mogelijkheden te gebruiken. Het is ook belangrijk om er zeker van te zijn dat alle gebruikers onder een alomvattend beleid vallen.

Als u andere soorten phishingbeleid wilt toepassen, moet u de instellingen aanpassen van op wie de verschillende beleidsregels van toepassing zijn.



