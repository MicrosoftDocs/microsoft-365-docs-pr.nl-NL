---
title: Microsoft Defender Antivirus meldingen configureren
description: Meer informatie over het configureren en aanpassen van zowel standaard- als aanvullende Microsoft Defender Antivirus meldingen op eindpunten.
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

In Windows 10 zijn toepassingsmeldingen over malwaredetectie en -herstel robuuster, consistenter en beknopter.

Meldingen worden weergegeven op eindpunten wanneer handmatig geactiveerde en geplande scans worden voltooid en bedreigingen worden gedetecteerd. Deze meldingen worden ook weergegeven in het **berichtencentrum** en er wordt regelmatig een overzicht van scans en bedreigingsdetecties weergegeven.

U kunt ook configureren hoe standaard meldingen worden weer geven op eind punten, zoals meldingen voor opnieuw opstarten of wanneer een bedreiging is gedetecteerd en hersteld.

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a>De extra meldingen configureren die op eindpunten worden weergegeven

U kunt de weergave van aanvullende meldingen, zoals recente samenvattingen van bedreigingsdetectie, configureren in de [Windows-beveiliging-app](microsoft-defender-security-center-antivirus.md) en met groepsbeleid.

> [!NOTE]
> In Windows 10 versie 1607 werd de functie **Verbeterde meldingen** genoemd en kon worden geconfigureerd onder **Windows Instellingen** Update  >  **& beveiliging**  >  **Windows Defender**. In groepsbeleidsinstellingen in alle versies van Windows 10 wordt dit **uitgebreide meldingen** genoemd.

> [!IMPORTANT]
> Als u extra meldingen uitschakelt, worden kritieke meldingen, zoals waarschuwingen voor bedreigingsdetectie en herstel, niet uitgeschakeld.

**Gebruik de Windows-beveiliging-app om extra meldingen uit te schakelen:**

1. Open de Windows-beveiliging app door op het schildpictogram in de taakbalk te klikken of in het startmenu te zoeken naar **Beveiliging**.

2. Selecteer Virus & tegel **voor bedreigingsbeveiliging** (of het schildpictogram op de linkermenubalk) en selecteer vervolgens **Virus & instellingen voor bedreigingsbeveiliging**

3. Scrol naar de sectie **Meldingen** en klik op **Meldingsinstellingen wijzigen**.

4. Schuif de schakelaar naar **Uit** of **Aan** om extra meldingen uit of in te schakelen.

**Groepsbeleid gebruiken om aanvullende meldingen uit te schakelen:**

1. Open op de computer voor groepsbeleidsbeheer de [Console voor groepsbeleidsbeheer](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))en klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken**.

2. Ga in de **Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie**.

3. Klik **op Beheersjablonen**.

4. Vouw de structuur uit om **onderdelen > Microsoft Defender Antivirus > rapportage te Windows.**

5. Dubbelklik op **Verbeterde meldingen uitschakelen** en stel de optie in op **Ingeschakeld**. Klik op **OK**. Dit voorkomt dat er extra meldingen verschijnen.

## <a name="configure-standard-notifications-on-endpoints"></a>Standaardmeldingen op eindpunten configureren

U kunt groepsbeleid gebruiken om:

- Extra, aangepaste tekst weergeven op eindpunten wanneer de gebruiker een actie moet uitvoeren
- Alle meldingen op eindpunten verbergen
- Herstartmeldingen op eindpunten verbergen

Het verbergen van meldingen kan handig zijn in situaties waarin u niet de hele Microsoft Defender Antivirus interface kunt verbergen. Zie [Voorkomen dat gebruikers de Microsoft Defender Antivirus gebruikersinterface zien of ermee communiceren](prevent-end-user-interaction-microsoft-defender-antivirus.md) voor meer informatie. 

> [!NOTE]
> Het verbergen van meldingen vindt alleen plaats op eindpunten waarop het beleid is geïmplementeerd. Meldingen met betrekking tot acties die moeten worden uitgevoerd (zoals opnieuw opstarten) worden nog steeds weergegeven op het [Microsoft Endpoint Manager Endpoint Protection monitoringdashboard en rapporten](/configmgr/protect/deploy-use/monitor-endpoint-protection). 

Zie [De Windows-beveiliging-app voor uw organisatie aanpassen](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) voor instructies om aangepaste contactgegevens toe te voegen aan de meldingen die gebruikers op hun machines zien.

**Groepsbeleid gebruiken om meldingen te verbergen:**

1. Open op de computer voor groepsbeleidsbeheer de [Console voor groepsbeleidsbeheer](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))en klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken**.

2. Ga in de **Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie** en klik op **Beheersjablonen**.

3. Vouw de structuur uit om **onderdelen > Microsoft Defender Antivirus > clientinterface te Windows.** 

4. Dubbelklik op **Alle meldingen onderdrukken** en stel de optie in op **Ingeschakeld**. Klik op **OK**. Dit voorkomt dat er extra meldingen verschijnen.

**Groepsbeleid gebruiken om herstartmeldingen te verbergen:**

1. Open op de computer voor groepsbeleidsbeheer de [Console voor groepsbeleidsbeheer](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))en klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik op **Bewerken**.

2. Ga in de **Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie**.

3. Klik **op Beheersjablonen**.

4. Vouw de structuur uit om **onderdelen > Microsoft Defender Antivirus > clientinterface te Windows.**

5. Dubbelklik op **Opnieuw opstarten van meldingen onderdrukken** en stel de optie in op **Ingeschakeld**. Klik op **OK**. Dit voorkomt dat er extra meldingen verschijnen.

## <a name="related-topics"></a>Verwante onderwerpen

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Interactie van eindgebruikers met Microsoft Defender Antivirus configureren](configure-end-user-interaction-microsoft-defender-antivirus.md)
