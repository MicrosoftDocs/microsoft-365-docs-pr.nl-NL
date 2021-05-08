---
title: Definieer hoe mobiele apparaten worden bijgewerkt door Microsoft Defender Antivirus
description: Beheer hoe mobiele apparaten, zoals laptops, moeten worden bijgewerkt met beveiligingsupdates voor Microsoft Defender Antivirus.
keywords: updates, beveiliging, planningsupdates, batterij, mobiel apparaat, laptop, notitieblok, opt-in, microsoft-update, wsus, overschrijven
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
ms.openlocfilehash: 143b0cb4bac1d3307e440f98fa4278f38e07c7f2
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269538"
---
# <a name="manage-updates-for-mobile-devices-and-virtual-machines-vms"></a>Updates beheren voor mobiele apparaten en virtuele machines (VM's)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

Mobiele apparaten en VM's hebben mogelijk meer configuratie nodig om ervoor te zorgen dat de prestaties niet worden beïnvloed door updates.

Er zijn twee instellingen die handig zijn voor deze apparaten:

- Kies voor Microsoft Update op mobiele computers zonder WSUS-verbinding
- Beveiligingsintelligentie-updates voorkomen wanneer de batterij wordt gebruikt

De volgende artikelen kunnen ook handig zijn in deze situaties:
- [Geplande scans en inhaalscans configureren](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Updates beheren voor eindpunten die verouderd zijn](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Implementatiehandleiding voor Microsoft Defender Antivirus in een VDI-omgeving (Virtual Desktop Infrastructure)](deployment-vdi-microsoft-defender-antivirus.md)

## <a name="opt-in-to-microsoft-update-on-mobile-computers-without-a-wsus-connection"></a>Kies voor Microsoft Update op mobiele computers zonder WSUS-verbinding

U kunt Microsoft Update gebruiken om beveiligingsinformatie op mobiele apparaten met Microsoft Defender Antivirus up-to-date te houden wanneer ze niet zijn verbonden met het bedrijfsnetwerk of anders geen WSUS-verbinding hebben. 

Dit betekent dat beveiligingsupdates kunnen worden geleverd op apparaten (via Microsoft Update), zelfs als u WSUS hebt ingesteld om Microsoft Update te overschrijven.

U kunt op een van de volgende manieren kiezen voor Microsoft Update op het mobiele apparaat:

- Wijzig de instelling met Groepsbeleid.
- Gebruik een VBScript om een script te maken en voer het vervolgens uit op elke computer in uw netwerk.
- Kies handmatig op elke computer in uw netwerk via **het** menu Instellingen.

### <a name="use-group-policy-to-opt-in-to-microsoft-update"></a>Groepsbeleid gebruiken om u aan te geven bij Microsoft Update

1. Open op uw groepsbeleidsbeheercomputer de console Groepsbeleidsbeheer, [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **Bewerken.**

2. Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**

3. Selecteer **Beleid en** **beheersjablonen.**

4. Vouw de boom uit naar **Windows-onderdelen**  >  **Microsoft Defender Antivirus** Signature  >  **Updates**.

5. Stel **Beveiligingsintelligentie-updates van Microsoft Update toestaan** in op **Ingeschakeld** en selecteer **OK.**


### <a name="use-a-vbscript-to-opt-in-to-microsoft-update"></a>Een VBScript gebruiken om u aan te geven bij Microsoft Update

1. Gebruik de instructies in het [MSDN-artikel Opt-In to Microsoft Update](/windows/win32/wua_sdk/opt-in-to-microsoft-update) om de VBScript te maken.

2. Voer de VBScript uit die u op elke computer in uw netwerk hebt gemaakt.

### <a name="manually-opt-in-to-microsoft-update"></a>Handmatig kiezen voor Microsoft Update

1. Open **Windows Update** in Update & **beveiligingsinstellingen** op de computer waarin u zich wilt opgeven.

2. Selecteer **Geavanceerde** opties.

3. Schakel het selectievakje Voor mij updates voor andere **Microsoft-producten in** wanneer ik Windows bij werk.

## <a name="prevent-security-intelligence-updates-when-running-on-battery-power"></a>Beveiligingsintelligentie-updates voorkomen wanneer de batterij wordt gebruikt

U kunt Microsoft Defender Antivirus zo configureren dat alleen beveiligingsupdates worden gedownload wanneer de pc is verbonden met een bekabelde stroombron. 

### <a name="use-group-policy-to-prevent-security-intelligence-updates-on-battery-power"></a>Groepsbeleid gebruiken om beveiligingsintelligentie-updates voor accu's te voorkomen

1.  Open op uw groepsbeleidsbeheercomputer de console Groepsbeleidsbeheer, kies het groepsbeleidsobject dat u wilt configureren en open het voor bewerken. [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2.  Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**

3.  Selecteer **Beleid en** **beheersjablonen.**

4.  Vouw de structuur uit **naar Windows-onderdelen** Microsoft Defender Antivirus Signature Updates en stel beveiligingsintelligentie-updates toestaan wanneer u op de batterij werkt in  >    >  op **Uitgeschakeld.**  Selecteer vervolgens **OK**. 

Met deze actie wordt voorkomen dat beveiligingsupdates worden gedownload wanneer de pc op de batterij staat.

## <a name="related-articles"></a>Verwante artikelen

- [Microsoft Defender Antivirus-updates beheren en basislijnen toepassen](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus bijwerken en beheren in Windows 10](deploy-manage-report-microsoft-defender-antivirus.md)