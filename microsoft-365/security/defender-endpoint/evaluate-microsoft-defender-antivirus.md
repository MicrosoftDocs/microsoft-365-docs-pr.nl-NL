---
title: Microsoft Defender Antivirus evalueren
description: Bedrijven van alle groottes kunnen deze handleiding gebruiken om de beveiliging te evalueren en te testen die door Microsoft Defender Antivirus in Windows 10.
keywords: Microsoft Defender Antivirus, cloudbeveiliging, cloud, antimalware, beveiliging, defender, evalueren, testen, beschermen, vergelijken, realtime beveiliging
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4f789ab80d48966d4cf922811d05d74882d728fe
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274734"
---
# <a name="evaluate-microsoft-defender-antivirus"></a>Microsoft Defender Antivirus evalueren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

Gebruik deze handleiding om te bepalen hoe goed Microsoft Defender Antivirus u beschermt tegen virussen, malware en mogelijk ongewenste toepassingen.

>[!TIP]
>U kunt ook naar de demowebsite van Microsoft Defender voor Eindpunt demo.wd.microsoft.com om te bevestigen [dat](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) de volgende functies werken en te zien hoe ze werken:
>- Cloudbeveiliging
>- Snel leren (inclusief Blok op het eerste gezicht)
>- Mogelijk ongewenste blokkering van toepassingen

Hier wordt uitgelegd welke belangrijke beveiligingsfuncties van de volgende generatie beschikbaar Microsoft Defender Antivirus voor zowel kleine als grote ondernemingen en hoe ze de detectie en beveiliging van malware in uw netwerk vergroten.

U kunt ervoor kiezen om elke instelling onafhankelijk of allemaal tegelijk te configureren en te evalueren. We hebben vergelijkbare instellingen gegroepeerd op basis van normale evaluatiescenario's en bevatten instructies voor het gebruik van PowerShell om de instellingen in te stellen.

De handleiding is beschikbaar in PDF-indeling voor offlineweergave:

- [De handleiding downloaden in PDF-indeling](https://www.microsoft.com/download/details.aspx?id=54795)

U kunt ook een PowerShell downloaden waarmee alle instellingen die in de handleiding worden beschreven, automatisch worden ingeschakeld. U kunt het script verkrijgen naast de pdf-download hierboven of afzonderlijk uit powershellgalerie:

- [Het PowerShell-script downloaden om de instellingen automatisch te configureren](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings)

> [!IMPORTANT]
> De handleiding is momenteel bedoeld voor evaluatie van een enkele machine Microsoft Defender Antivirus. Het inschakelen van alle instellingen in deze handleiding is mogelijk niet geschikt voor implementatie in de echte wereld.
>
> Zie Implementatie van Microsoft Defender Antivirus voor de meest recente aanbevelingen voor implementatie en monitoring van Microsoft Defender Antivirus in een [netwerk.](deploy-manage-report-microsoft-defender-antivirus.md)

## <a name="related-topics"></a>Verwante onderwerpen

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Implementatie van Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)