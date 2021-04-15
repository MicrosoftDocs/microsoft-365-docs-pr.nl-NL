---
title: De time-outperiode voor microsoft Defender Antivirus-cloudblokkering configureren
description: U kunt configureren hoe lang Microsoft Defender Antivirus een bestand blokkeert terwijl u wacht op een cloudbepaling.
keywords: Microsoft Defender Antivirus, antimalware, beveiliging, defender, cloud, time-out, blok, punt, seconden
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 372d679f45d6f87392b612f757e6bdf1c6c6b9ad
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765801"
---
# <a name="configure-the-cloud-block-timeout-period"></a>De time-outperiode voor cloudblokkering configureren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

Wanneer Microsoft Defender Antivirus een verdacht bestand vindt, kan het voorkomen dat het bestand wordt uitgevoerd terwijl het de [Microsoft Defender Antivirus-cloudservice opvraagt.](cloud-protection-microsoft-defender-antivirus.md)

De standaardperiode dat het bestand wordt [geblokkeerd,](configure-block-at-first-sight-microsoft-defender-antivirus.md) is 10 seconden. U kunt een extra periode opgeven om te wachten voordat het bestand mag worden uitgevoerd. Dit kan ervoor zorgen dat er voldoende tijd is om een juiste bepaling te ontvangen van de Microsoft Defender Antivirus-cloudservice.

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a>Vereisten voor het gebruik van de time-out voor uitgebreide cloudblokkering

[Blok op het eerste gezicht](configure-block-at-first-sight-microsoft-defender-antivirus.md) en de vereisten moeten zijn ingeschakeld voordat u een langere time-outperiode kunt opgeven.

## <a name="specify-the-extended-timeout-period"></a>De verlengde time-outperiode opgeven

U kunt Groepsbeleid gebruiken om een uitgebreide time-out voor cloudcontroles op te geven.

1. Open op de computer groepsbeleidsbeheer de console Groepsbeleidsbeheer, [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**

2. Ga in **groepsbeleidseditor** naar **Computerconfiguratie** en klik op **Beheersjablonen.**

3. De structuur uitbreiden naar **Windows-onderdelen > Microsoft Defender Antivirus > MpEngine**

4. Dubbelklik op **Uitgebreide cloudcontrole configureren** en controleer of de optie is ingeschakeld. Geef de extra tijd op om te voorkomen dat het bestand wordt uitgevoerd terwijl u wacht op een cloudbepaling. U kunt de extra tijd in seconden opgeven van 1 seconde tot 50 seconden. Deze tijd wordt toegevoegd aan de standaard 10 seconden.

5. Klik op **OK**.

## <a name="related-topics"></a>Verwante onderwerpen

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Antivirustechnologieën van de volgende generatie gebruiken via door de cloud geleverde beveiliging](cloud-protection-microsoft-defender-antivirus.md)
- [Blok configureren op het eerste gezicht](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [Beveiliging via de cloud inschakelen](enable-cloud-protection-microsoft-defender-antivirus.md)