---
title: De beperkte periodieke scanfunctie voor Microsoft Defender Antivirus inschakelen
description: Met beperkt periodiek scannen kunt u Naast uw andere geïnstalleerde AV-providers ook Microsoft Defender Antivirus gebruiken
keywords: lps, limited, periodic, scan, scanning, compatibility, 3rd party, other av, disable
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 82c4bc1feec1556dc864558a843ed5e911c3ef3d
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764481"
---
# <a name="use-limited-periodic-scanning-in-microsoft-defender-antivirus"></a>Beperkt periodiek scannen gebruiken in Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

Beperkt periodiek scannen is een speciaal type bedreigingsdetectie en -herstel dat kan worden ingeschakeld wanneer u een ander antivirusproduct hebt geïnstalleerd op een Windows 10-apparaat.

Deze functie kan alleen in bepaalde situaties worden ingeschakeld. Zie Microsoft Defender Antivirus compatibility voor meer informatie over beperkt periodiek scannen en hoe Microsoft Defender Antivirus werkt met andere [antivirusproducten.](microsoft-defender-antivirus-compatibility.md)

**Microsoft raadt het gebruik van deze functie niet aan in bedrijfsomgevingen. Dit is een functie die voornamelijk bedoeld is voor consumenten.** Deze functie gebruikt slechts een beperkte subset van de Microsoft Defender Antivirus-mogelijkheden om malware te detecteren en kan de meeste malware en mogelijk ongewenste software niet detecteren. Daarnaast zijn de beheer- en rapportagemogelijkheden beperkt. Microsoft raadt ondernemingen aan hun primaire antivirusoplossing te kiezen en deze uitsluitend te gebruiken.

## <a name="how-to-enable-limited-periodic-scanning"></a>Beperkt periodiek scannen inschakelen

Standaard wordt Microsoft Defender Antivirus ingeschakeld op een Windows 10-apparaat als er geen ander antivirusproduct is geïnstalleerd of als het andere product verouderd, verlopen of niet correct werkt.

Als Microsoft Defender Antivirus is ingeschakeld, worden de gebruikelijke opties weergegeven om het te configureren op dat apparaat:

![Windows Security-app met Microsoft Defender AV-opties, inclusief scanopties, instellingen en bijwerkopties](images/vtp-wdav.png)

Als een ander antivirusproduct is geïnstalleerd en goed werkt, wordt Microsoft Defender Antivirus zelf uitgeschakeld. De Windows Security-app wijzigt de sectie **Virus & bedreigingsbeveiliging** om de status van het AV-product weer te geven en geeft een koppeling naar de configuratieopties van het product.

Onder av-producten van derden wordt een nieuwe koppeling weergegeven als **Microsoft Defender Antivirus-opties.** Als u op deze koppeling klikt, wordt de schakelknop die beperkt periodiek scannen in staat stelt, uitvlage. Houd er rekening mee dat de beperkte periodieke optie een schakeloptie is om periodiek scannen in of uit te schakelen. 

Als u de overstap naar **Aan** schuift, worden de standaard microsoft Defender AV-opties onder het AV-product van derden weer te geven. De beperkte optie voor periodiek scannen wordt onder aan de pagina weergegeven.

## <a name="related-articles"></a>Verwante artikelen

- [Gedrag, heuristiek en realtime bescherming configureren](configure-protection-features-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)