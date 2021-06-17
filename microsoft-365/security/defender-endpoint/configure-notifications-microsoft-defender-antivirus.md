---
title: Meldingen Microsoft Defender Antivirus configureren
description: Informatie over het configureren en aanpassen van zowel standaard- als Microsoft Defender Antivirus meldingen op eindpunten.
keywords: meldingen, defender, antivirus, eindpunt, beheer, beheerder
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.topic: article
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/16/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: a7a838bb15cd011b750fbfa3d6df100ddf9f713c
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985406"
---
# <a name="configure-microsoft-defender-antivirus-notifications-that-appear-on-endpoints"></a>Meldingen Microsoft Defender Antivirus eindpunten configureren

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

In Windows 10 zijn toepassingsmeldingen over malwaredetectie en -herstel krachtiger, consistenter en beknopter. Microsoft Defender Antivirus meldingen worden weergegeven op eindpunten wanneer scans worden voltooid en bedreigingen worden gedetecteerd. Meldingen volgen zowel geplande als handmatig geactiveerde scans. Deze meldingen worden ook weergegeven in het **systeemmeldingscentrum** en er wordt regelmatig een overzicht van scans en bedreigingsdetecties weergegeven.

Als u deel uitmaakt van het beveiligingsteam van uw organisatie, kunt u configureren hoe meldingen worden weergegeven op eindpunten, zoals meldingen die vragen om een systeem opnieuw op te starten of die aangeven dat er een bedreiging is gedetecteerd en die zijn verwijderd.

## <a name="configure-antivirus-notifications-using-group-policy-or-the-windows-security-app"></a>Antivirusmeldingen configureren met groepsbeleid of de Windows-beveiliging app

U kunt de weergave van extra meldingen, zoals recente samenvattingen voor bedreigingsdetectie, configureren in de Windows-beveiliging [app](microsoft-defender-security-center-antivirus.md) en met groepsbeleid.

> [!NOTE]
> In Windows 10 versie 1607 werd de functie **Enhanced notifications** genoemd en geconfigureerd **onder Windows Instellingen**  >  **Update &**  >  **beveiligingsinstellingen Windows Defender.** In groepsbeleidsinstellingen voor alle versies van Windows 10 wordt de meldingsfunctie **Enhanced notifications genoemd.**

### <a name="use-group-policy-to-disable-additional-notifications"></a>Groepsbeleid gebruiken om extra meldingen uit te schakelen

1. Open op uw computer voor groepsbeleidsbeheer de [Console groepsbeleidsbeheer](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **bewerken.**

3. Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**

4. Selecteer **Beheersjablonen.**

5. Vouw de structuur uit Windows **onderdelen**  >  **Microsoft Defender Antivirus** > Reporting**.

6. Dubbelklik op **Verbeterde meldingen uitschakelen** en stel de optie in op **Ingeschakeld.** Selecteer vervolgens **OK**. Hierdoor worden er geen extra meldingen weergegeven.

> [!IMPORTANT]
> Als u extra meldingen uit schakelt, worden kritieke meldingen niet uitgeschakeld, zoals waarschuwingen voor bedreigingsdetectie en herstel.

### <a name="use-the-windows-security-app-to-disable-additional-notifications"></a>Gebruik de Windows-beveiliging-app om extra meldingen uit te schakelen

1. Open de Windows-beveiliging app door op het schildpictogram op de taakbalk te klikken of door te zoeken in het startmenu voor **beveiliging.**

2. Selecteer **Tegel & bescherming** tegen virussen (of het schildpictogram op de linkermenubalk) en selecteer vervolgens Instellingen voor & **virusbeveiliging**

3. Schuif naar de sectie Meldingen en selecteer **Meldingsinstellingen** **wijzigen.**

4. Schuif de schakelknop naar **Uit** of **Aan om** extra meldingen uit te schakelen of in te schakelen.

> [!IMPORTANT]
> Als u extra meldingen uit schakelt, worden kritieke meldingen niet uitgeschakeld, zoals waarschuwingen voor bedreigingsdetectie en herstel.

## <a name="configure-standard-notifications-on-endpoints-using-group-policy"></a>Standaardmeldingen voor eindpunten configureren met groepsbeleid

U kunt groepsbeleid gebruiken om:

- Extra, aangepaste tekst weergeven op eindpunten wanneer de gebruiker een actie moet uitvoeren
- Alle meldingen op eindpunten verbergen
- Rebootmeldingen op eindpunten verbergen

Het verbergen van meldingen kan handig zijn in situaties waarin u niet de hele interface Microsoft Defender Antivirus verbergen. Zie [Voorkomen dat gebruikers de](prevent-end-user-interaction-microsoft-defender-antivirus.md) gebruikersinterface van de Microsoft Defender Antivirus zien of gebruiken voor meer informatie. Meldingen verbergen vindt alleen plaats op eindpunten waarop het beleid is geïmplementeerd. Meldingen met betrekking tot acties die moeten worden ondernomen (zoals een herstart) worden nog steeds weergegeven op het Microsoft Endpoint Manager Endpoint Protection dashboard en [rapporten.](/configmgr/protect/deploy-use/monitor-endpoint-protection) 

Zie De app aanpassen Windows-beveiliging uw organisatie als u aangepaste contactgegevens wilt [toevoegen aan eindpuntmeldingen.](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)

### <a name="use-group-policy-to-hide-notifications"></a>Groepsbeleid gebruiken om meldingen te verbergen

1. Open op uw computer voor groepsbeleidsbeheer de [Console groepsbeleidsbeheer](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **bewerken.**

3. Ga in **groepsbeleidsbeheereditor** naar **Computerconfiguratie** en selecteer vervolgens **Beheersjablonen.**

4. Vouw de structuur uit Windows **onderdelen**  >  **Microsoft Defender Antivirus**  >  **clientinterface.** 

5. Dubbelklik op **Alle meldingen onderdrukken en** stel de optie in op **Ingeschakeld.** 

6. Selecteer **OK**. Hierdoor worden er geen extra meldingen weergegeven.

### <a name="use-group-policy-to-hide-reboot-notifications"></a>Groepsbeleid gebruiken om opnieuw opstarten-meldingen te verbergen

1. Open op uw computer voor groepsbeleidsbeheer de [Console groepsbeleidsbeheer](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **bewerken.**

2. Ga in **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie.**

3. Klik **op Beheersjablonen.**

4. Vouw de structuur uit Windows **onderdelen**  >  **Microsoft Defender Antivirus**  >  **clientinterface.**

5. Dubbelklik op **Rebootmeldingen onderdrukken** en stel de optie in op **Ingeschakeld.** 

5. Selecteer **OK**. Hierdoor worden er geen extra meldingen weergegeven.

