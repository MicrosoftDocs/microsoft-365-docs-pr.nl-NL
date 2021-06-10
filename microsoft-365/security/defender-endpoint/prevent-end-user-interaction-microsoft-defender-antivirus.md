---
title: De interface Microsoft Defender Antivirus verbergen
description: U kunt de tegel virus- en bedreigingsbeveiliging verbergen in de Windows-beveiliging app.
keywords: ui lockdown, headless mode, hide app, hide settings, hide interface
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 06ee2f1cb68df0a957818e1fccb45628487c39fd
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274914"
---
# <a name="prevent-users-from-seeing-or-interacting-with-the-microsoft-defender-antivirus-user-interface"></a>Voorkomen dat gebruikers de gebruikersinterface van de Microsoft Defender Antivirus zien of gebruiken

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

U kunt Groepsbeleid gebruiken om te voorkomen dat gebruikers op eindpunten de Microsoft Defender Antivirus zien. U kunt ook voorkomen dat ze scans onderbreken.

## <a name="hide-the-microsoft-defender-antivirus-interface"></a>De interface Microsoft Defender Antivirus verbergen

In Windows 10, versie 1703, worden Microsoft Defender Antivirus-meldingen verborgen door de interface te verbergen en wordt voorkomen dat de tegel Virus & bedreigingsbeveiliging wordt weergegeven in de Windows-beveiliging-app.

Met de instelling ingesteld op **Ingeschakeld:**

![Schermafbeelding van Windows-beveiliging zonder het schildpictogram en de sectie virus- en bedreigingsbeveiliging](images/defender/wdav-headless-mode-1703.png)

Met de instelling ingesteld op **Uitgeschakeld of** niet geconfigureerd:

![Schermafbeelding van Windows-beveiliging met het schildpictogram en de sectie virus- en bedreigingsbeveiliging](images/defender/wdav-headless-mode-off-1703.png)

>[!NOTE]
>Als u de interface verbergt, worden Microsoft Defender Antivirus meldingen ook niet weergegeven op het eindpunt. Microsoft Defender voor eindpuntmeldingen wordt nog steeds weergegeven. U kunt de meldingen die op eindpunten worden weergegeven, ook [afzonderlijk configureren](configure-notifications-microsoft-defender-antivirus.md)

In eerdere versies van Windows 10, verbergt de instelling de Windows Defender clientinterface. Als de gebruiker probeert deze te openen, ontvangt deze een waarschuwing met de melding 'Uw systeembeheerder heeft beperkte toegang tot deze app'.

![Waarschuwingsbericht wanneer de headless-modus is ingeschakeld in Windows 10, versies eerder dan 1703](images/defender/wdav-headless-mode-1607.png)

## <a name="use-group-policy-to-hide-the-microsoft-defender-av-interface-from-users"></a>Groepsbeleid gebruiken om de AV-interface van Microsoft Defender te verbergen voor gebruikers

1. Open op uw groepsbeleidsbeheercomputer de [console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**

2. Ga met **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**

3. Klik **op Beheersjablonen.**

4. Vouw de structuur uit **Windows onderdelen > Microsoft Defender Antivirus > clientinterface.**

5. Dubbelklik op de instelling voor de modus Gebruikersinterface zonder hoofd **inschakelen** en stel de optie in op **Ingeschakeld.** Klik op **OK**. 

Zie [Voorkomen dat gebruikers beleidsinstellingen](configure-local-policy-overrides-microsoft-defender-antivirus.md) lokaal wijzigen voor meer opties om te voorkomen dat gebruikers de beveiliging op hun pc wijzigen.

## <a name="prevent-users-from-pausing-a-scan"></a>Voorkomen dat gebruikers een scan onderbreken

U kunt voorkomen dat gebruikers scans onderbreken, wat handig kan zijn om ervoor te zorgen dat geplande of on-demand scans niet worden onderbroken door gebruikers.

> [!NOTE]
> Deze instelling wordt niet ondersteund op Windows 10.

### <a name="use-group-policy-to-prevent-users-from-pausing-a-scan"></a>Groepsbeleid gebruiken om te voorkomen dat gebruikers een scan onderbreken

1. Open op uw groepsbeleidsbeheercomputer de [console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**

2. Ga met **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**

3. Klik **op Beheersjablonen.**

4. Vouw de boom uit Windows **onderdelen**  >  **Microsoft Defender Antivirus**  >  **Scannen.**

5. Dubbelklik op de **instelling Toestaan dat gebruikers de scan onderbreken** en stel de optie in op **Uitgeschakeld.** Klik op **OK**. 

## <a name="related-articles"></a>Aanverwante artikelen

- [De meldingen configureren die op eindpunten worden weergegeven](configure-notifications-microsoft-defender-antivirus.md)

- [Interactie tussen eindgebruikers configureren met Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md)

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)