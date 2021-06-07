---
title: De time-Microsoft Defender Antivirus voor cloudblokkering configureren
description: U kunt configureren hoe lang Microsoft Defender Antivirus een bestand kan worden uitgevoerd terwijl u wacht op een cloudbepaling.
keywords: Microsoft Defender Antivirus, antimalware, beveiliging, defender, cloud, time-out, blok, punt, seconden
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 06/04/2021
ms.openlocfilehash: dfb75b77119d9550931c3e476323bde67a3b148f
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789085"
---
# <a name="configure-the-cloud-block-timeout-period"></a>De time-outperiode voor cloudblokkering configureren

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

Wanneer Microsoft Defender Antivirus een verdacht bestand vindt, kan het voorkomen dat het bestand wordt uitgevoerd terwijl de Microsoft Defender Antivirus [cloudservice wordt opgevraagd.](cloud-protection-microsoft-defender-antivirus.md)

De standaardperiode dat het bestand is [geblokkeerd,](configure-block-at-first-sight-microsoft-defender-antivirus.md) is 10 seconden. Als u een beveiligingsbeheerder bent, kunt u meer tijd opgeven om te wachten voordat het bestand mag worden uitgevoerd. Door de time-outperiode voor cloudblokkering uit te breiden, kan ervoor worden gezorgd dat er voldoende tijd is om een juiste bepaling te ontvangen van de Microsoft Defender Antivirus cloudservice.

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a>Vereisten voor het gebruik van de time-out voor uitgebreide cloudblokkering

[Blok op het eerste gezicht](configure-block-at-first-sight-microsoft-defender-antivirus.md) en de vereisten moeten zijn ingeschakeld voordat u een langere time-outperiode kunt opgeven.

## <a name="specify-the-extended-timeout-period-using-microsoft-endpoint-manager"></a>De verlengde time-outperiode opgeven met Microsoft Endpoint Manager

U kunt de time-outperiode voor cloudblokkering opgeven met een [eindpuntbeveiligingsbeleid in Microsoft Endpoint Manager.](/mem/intune/protect/endpoint-security-policy)

1. Ga naar het Endpoint Manager [https://endpoint.microsoft.com/](https://endpoint.microsoft.com/) () en meld u aan.

2. Selecteer **Endpoint-beveiliging** en kies **vervolgens** onder Beheren de optie **Antivirus.**

3. Selecteer (of maak) een antivirusbeleid.

4. Vouw cloudbeveiliging uit in **de** sectie **Configuratie-instellingen.** Geef vervolgens in **het vak Verlengde time-out in** seconden van de Defender Cloud de tijd in seconden op van 1 seconde naar 50 seconden. Wat u opgeeft, wordt toegevoegd aan de standaard 10 seconden.

5. (Deze stap is optioneel) Andere wijzigingen aanbrengen in uw antivirusbeleid. (Hulp nodig? Zie [Instellingen voor Microsoft Defender Antivirus beleid in Microsoft Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-windows).)

6. Kies **Volgende** en werk het configureren van uw beleid af.

## <a name="specify-the-extended-timeout-period-using-group-policy"></a>De verlengde time-outperiode opgeven met groepsbeleid

U kunt Groepsbeleid gebruiken om een uitgebreide time-out voor cloudcontroles op te geven.

1. Open op uw groepsbeleidscomputer de [console Groepsbeleidsbeheer](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2. Klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **bewerken.**

3. Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie** en selecteer vervolgens **Beheersjablonen.**

3. Vouw de boom uit Windows **onderdelen**  >  **Microsoft Defender Antivirus**  >  **MpEngine**.

4. Dubbelklik op **Uitgebreide cloudcontrole configureren** en controleer of de optie is ingeschakeld. 

   Geef de extra tijd op om te voorkomen dat het bestand wordt uitgevoerd terwijl u wacht op een cloudbepaling. Geef de extra tijd in seconden op van 1 seconde naar 50 seconden. Wat u opgeeft, wordt toegevoegd aan de standaard 10 seconden.

5. Selecteer **OK**.

 