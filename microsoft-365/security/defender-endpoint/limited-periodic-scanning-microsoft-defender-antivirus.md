---
title: De functie voor beperkte periodieke Microsoft Defender Antivirus scannen inschakelen
description: Met beperkt periodiek scannen kunt u Microsoft Defender Antivirus naast uw andere geïnstalleerde AV-providers
keywords: lps, limited, periodic, scan, scanning, compatibility, 3rd party, other av, disable
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
ms.openlocfilehash: b2ae56c0f67501eb8603d5d28c4ed0c4af01a8c9
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274590"
---
# <a name="use-limited-periodic-scanning-in-microsoft-defender-antivirus"></a>Beperkt periodiek scannen gebruiken in Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

Beperkt periodiek scannen is een speciaal type bedreigingsdetectie en -herstel dat kan worden ingeschakeld wanneer u een ander antivirusproduct hebt geïnstalleerd op een Windows 10 apparaat.

Deze functie kan alleen in bepaalde situaties worden ingeschakeld. Zie voor meer informatie over beperkt periodiek scannen en hoe Microsoft Defender Antivirus met andere antivirusproducten werkt [Microsoft Defender Antivirus compatibiliteit.](microsoft-defender-antivirus-compatibility.md)

**Microsoft raadt het gebruik van deze functie niet aan in bedrijfsomgevingen. Dit is een functie die voornamelijk bedoeld is voor consumenten.** Deze functie gebruikt slechts een beperkte subset van de Microsoft Defender Antivirus om malware te detecteren en kan de meeste malware en mogelijk ongewenste software niet detecteren. Daarnaast zijn de beheer- en rapportagemogelijkheden beperkt. Microsoft raadt ondernemingen aan hun primaire antivirusoplossing te kiezen en deze uitsluitend te gebruiken.

## <a name="how-to-enable-limited-periodic-scanning"></a>Beperkt periodiek scannen inschakelen

Standaard worden Microsoft Defender Antivirus ingeschakeld op een Windows 10-apparaat als er geen ander antivirusproduct is geïnstalleerd of als het andere product verouderd, verlopen of niet correct werkt.

Als Microsoft Defender Antivirus is ingeschakeld, worden de gebruikelijke opties weergegeven om deze te configureren op dat apparaat:

![Windows-beveiliging app met Microsoft Defender AV-opties, inclusief scanopties, instellingen en bijwerkopties](images/vtp-wdav.png)

Als een ander antivirusproduct is geïnstalleerd en correct werkt, wordt Microsoft Defender Antivirus zelf uitgeschakeld. De Windows-beveiliging app wijzigt de sectie **Virus & bedreigingsbeveiliging** om de status van het AV-product weer te geven en geeft een koppeling naar de configuratieopties van het product.

Onder av-producten van derden wordt een nieuwe koppeling weergegeven als **Microsoft Defender Antivirus opties.** Als u op deze koppeling klikt, wordt de schakelknop die beperkt periodiek scannen in staat stelt, uitvlage. Houd er rekening mee dat de beperkte periodieke optie een schakeloptie is om periodiek scannen in of uit te schakelen. 

Als u de overstap naar **Aan** schuift, worden de standaard microsoft Defender AV-opties onder het AV-product van derden weer te geven. De beperkte optie voor periodiek scannen wordt onder aan de pagina weergegeven.

## <a name="related-articles"></a>Aanverwante artikelen

- [Gedrag, heuristiek en realtime bescherming configureren](configure-protection-features-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)