---
title: Meldingen Microsoft Defender Antivirus configureren
description: Informatie over het configureren en aanpassen van zowel standaard- als Microsoft Defender Antivirus meldingen op eindpunten.
keywords: meldingen, defender, antivirus, eindpunt, beheer, beheerder
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f885b6d7991e4175cd14be5bbe9e0a7c96b1580f
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572343"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a>De meldingen configureren die op eindpunten worden weergegeven

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

In Windows 10 zijn toepassingsmeldingen over malwaredetectie en -herstel krachtiger, consistenter en beknopter.

Meldingen worden weergegeven op eindpunten wanneer handmatig geactiveerde en geplande scans worden voltooid en bedreigingen worden gedetecteerd. Deze meldingen worden ook weergegeven in het **systeemmeldingscentrum** en er wordt regelmatig een overzicht van scans en bedreigingsdetecties weergegeven.

U kunt ook configureren hoe standaardmeldingen worden weergegeven op eindpunten, zoals meldingen voor het opnieuw opstarten of wanneer een bedreiging is gedetecteerd en geremediat.

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a>De extra meldingen configureren die op eindpunten worden weergegeven

U kunt de weergave van extra meldingen, zoals recente samenvattingen voor bedreigingsdetectie, configureren in de Windows-beveiliging [app](microsoft-defender-security-center-antivirus.md) en met groepsbeleid.

> [!NOTE]
> In Windows 10 versie 1607 werd de functie **Enhanced notifications** genoemd en kon deze worden geconfigureerd onder **Windows Instellingen**  >  **Update &**  >  **beveiligingsinstellingen Windows Defender.** In groepsbeleidsinstellingen in alle versies van Windows 10, wordt dit **enhanced notifications genoemd.**

> [!IMPORTANT]
> Als u extra meldingen uit schakelt, worden kritieke meldingen niet uitgeschakeld, zoals waarschuwingen voor bedreigingsdetectie en herstel.

**Gebruik de Windows-beveiliging app om extra meldingen uit te schakelen:**

1. Open de Windows-beveiliging app door op het schildpictogram op de taakbalk te klikken of door te zoeken in het startmenu voor **beveiliging.**

2. Selecteer **Tegel & bescherming** tegen virussen (of het schildpictogram op de linkermenubalk) en selecteer vervolgens Instellingen voor & **virusbeveiliging**

3. Schuif naar de sectie Meldingen en klik op **Meldingsinstellingen** **wijzigen.**

4. Schuif de schakelknop naar **Uit** of **Aan om** extra meldingen uit te schakelen of in te schakelen.

**Groepsbeleid gebruiken om extra meldingen uit te schakelen:**

1. Open op de computer groepsbeleidsbeheer de console Groepsbeleidsbeheer, [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**

2. Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**

3. Klik **op Beheersjablonen.**

4. Vouw de structuur uit Windows **onderdelen > Microsoft Defender Antivirus > Reporting.**

5. Dubbelklik op **Verbeterde meldingen uitschakelen** en stel de optie in op **Ingeschakeld.** Klik op **OK**. Hierdoor worden er geen extra meldingen weergegeven.

## <a name="configure-standard-notifications-on-endpoints"></a>Standaardmeldingen voor eindpunten configureren

U kunt groepsbeleid gebruiken om:

- Extra, aangepaste tekst weergeven op eindpunten wanneer de gebruiker een actie moet uitvoeren
- Alle meldingen op eindpunten verbergen
- Rebootmeldingen op eindpunten verbergen

Het verbergen van meldingen kan handig zijn in situaties waarin u niet de hele interface Microsoft Defender Antivirus verbergen. Zie [Voorkomen dat gebruikers de](prevent-end-user-interaction-microsoft-defender-antivirus.md) gebruikersinterface van de Microsoft Defender Antivirus zien of gebruiken voor meer informatie. 

> [!NOTE]
> Meldingen verbergen vindt alleen plaats op eindpunten waarop het beleid is geïmplementeerd. Meldingen met betrekking tot acties die moeten worden ondernomen (zoals een herstart) worden nog steeds weergegeven op het Microsoft Endpoint Manager Endpoint Protection dashboard en [rapporten.](/configmgr/protect/deploy-use/monitor-endpoint-protection) 

Zie [De app Windows-beveiliging voor](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) uw organisatie aanpassen voor instructies voor het toevoegen van aangepaste contactgegevens aan de meldingen die gebruikers op hun machines zien.

**Groepsbeleid gebruiken om meldingen te verbergen:**

1. Open op de computer groepsbeleidsbeheer de console Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.** [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2. Ga in **groepsbeleidseditor** naar **Computerconfiguratie** en klik op **Beheersjablonen.**

3. Vouw de structuur uit **Windows onderdelen > Microsoft Defender Antivirus > clientinterface.** 

4. Dubbelklik op **Alle meldingen onderdrukken en** stel de optie in op **Ingeschakeld.** Klik op **OK**. Hierdoor worden er geen extra meldingen weergegeven.

**Groepsbeleid gebruiken om opnieuw opstarten-meldingen te verbergen:**

1. Open op de computer groepsbeleidsbeheer de console Groepsbeleidsbeheer, [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken.**

2. Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**

3. Klik **op Beheersjablonen.**

4. Vouw de structuur uit **Windows onderdelen > Microsoft Defender Antivirus > clientinterface.**

5. Dubbelklik op **Rebootmeldingen onderdrukken** en stel de optie in op **Ingeschakeld.** Klik op **OK**. Hierdoor worden er geen extra meldingen weergegeven.

## <a name="related-topics"></a>Verwante onderwerpen

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Interactie tussen eindgebruikers configureren met Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md)
