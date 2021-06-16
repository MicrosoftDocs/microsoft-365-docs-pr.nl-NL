---
title: Beheerde maptoegang evalueren
description: Bekijk hoe beheerde maptoegang kan helpen om te beschermen dat bestanden worden gewijzigd door schadelijke apps.
keywords: Exploit protection, windows 10, windows defender, ransomware, protect, evaluate, test, demo, try
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
ms.topic: conceptual
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 4254c5ea24d8c901ac5f6337b0c626afe02747e2
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926641"
---
# <a name="evaluate-controlled-folder-access"></a>Beheerde maptoegang evalueren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


[Gecontroleerde maptoegang](controlled-folders.md) is een functie waarmee u uw documenten en bestanden kunt beschermen tegen wijzigingen door verdachte of schadelijke apps. Gecontroleerde maptoegang wordt ondersteund op Windows Server 2019 en Windows 10 clients.

Het is vooral handig om te beschermen tegen [ransomware](https://www.microsoft.com/wdsi/threats/ransomware) die probeert uw bestanden te versleutelen en ze te laten gegijzeld.

In dit artikel kunt u gecontroleerde maptoegang evalueren. Hier wordt uitgelegd hoe u de auditmodus inschakelen, zodat u de functie rechtstreeks in uw organisatie kunt testen.

> [!TIP]
> U kunt ook naar de website voor demoscenario's van Microsoft Defender voor [Eindpunt](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) demo.wd.microsoft.com om te bevestigen dat de functie werkt en te zien hoe deze werkt.

## <a name="use-audit-mode-to-measure-impact"></a>Controlemodus gebruiken om de impact te meten

Schakel de gecontroleerde maptoegang in de auditmodus in om een record te zien van wat er zou zijn gebeurd als deze volledig was ingeschakeld.  Test hoe de functie in uw organisatie werkt om ervoor te zorgen dat deze geen invloed heeft op uw line-of-business-apps. U kunt ook een idee krijgen van het aantal pogingen om verdachte bestanden over een bepaalde periode te wijzigen.

Gebruik de volgende PowerShell-cmdlet om de auditmodus in te schakelen:

```PowerShell
Set-MpPreference -EnableControlledFolderAccess AuditMode
```

> [!TIP]
> Als u volledig wilt controleren hoe beheerde maptoegang in uw organisatie werkt, moet u een beheerhulpmiddel gebruiken om deze instelling te implementeren op apparaten in uw netwerk(en).
U kunt ook Groepsbeleid, Intune, MDM (Mobile Device Management) of Microsoft Endpoint Manager gebruiken om de instelling te configureren en te implementeren, zoals wordt beschreven in het onderwerp Hoofdbeheer voor [maptoegang.](controlled-folders.md)

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a>Gecontroleerde maptoegangsgebeurtenissen controleren in Windows Gebeurtenisviewer

De volgende gecontroleerde toegangsgebeurtenissen voor mappen worden weergegeven in Windows Gebeurtenisviewer onder Microsoft/Windows/Windows Defender/Operationele map.

Gebeurtenis-id | Omschrijving
-|-
 5007 | Gebeurtenis wanneer instellingen worden gewijzigd
 1124 | Gecontroleerde gecontroleerde maptoegangsgebeurtenis
 1123 | Gebeurtenis Geblokkeerde gecontroleerde maptoegang

> [!TIP]
> U kunt een abonnement [Windows gebeurtenis doorsturen configureren](/windows/win32/wec/setting-up-a-source-initiated-subscription) om de logboeken centraal te verzamelen. 

## <a name="customize-protected-folders-and-apps"></a>Beveiligde mappen en apps aanpassen

Tijdens de evaluatie wilt u mogelijk toevoegen aan de lijst met beveiligde mappen of bepaalde apps toestaan bestanden te wijzigen.

Zie [Belangrijke mappen beveiligen](controlled-folders.md) met beheerde maptoegang voor het configureren van de functie met beheerhulpmiddelen, zoals Groepsbeleid, PowerShell en MDM-configuratieserviceproviders (CSP's).

## <a name="see-also"></a>Zie ook

* [Belangrijke mappen beveiligen met gecontroleerde maptoegang](controlled-folders.md)
* [Microsoft Defender voor Eindpunt evalueren](evaluate-mde.md)
* [Controlemodus gebruiken](audit-windows-defender.md)
