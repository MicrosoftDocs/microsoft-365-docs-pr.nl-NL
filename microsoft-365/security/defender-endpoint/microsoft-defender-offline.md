---
title: Microsoft Defender Offline in Windows 10
description: U kunt deze Microsoft Defender Offline rechtstreeks vanuit de Windows Defender Antivirus app. U kunt ook beheren hoe deze wordt geïmplementeerd in uw netwerk.
keywords: scannen, defender, offline
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
ms.openlocfilehash: b2a6ee7c3f3ea2fb31b31d2f1db178bfd9847fbc
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007469"
---
# <a name="run-and-review-the-results-of-a-microsoft-defender-offline-scan"></a>De resultaten van een Microsoft Defender Offline-scan uitvoeren en bekijken

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Offline is een hulpprogramma voor het scannen van antimalware waarmee u een scan kunt starten en uitvoeren vanuit een vertrouwde omgeving. De scan wordt uitgevoerd van buiten de normale Windows-kernel, zodat deze zich kan richten op malware die probeert de Windows-shell te omzeilen, zoals virussen en rootkits die de master boot record (MBR) infecteren of overschrijven.

U kunt deze Microsoft Defender Offline als u vermoedt dat er een malware-infectie is, of als u wilt bevestigen dat het eindpunt grondig is opschoond na een malware-uitbraak.

In Windows 10 kunt Microsoft Defender Offline met één klik rechtstreeks vanuit de app Windows-beveiliging [uitvoeren.](microsoft-defender-security-center-antivirus.md) In eerdere versies van Windows moest een gebruiker een Microsoft Defender Offline installeren om opstartbare media te installeren, het eindpunt opnieuw op te starten en de opstartbare media te laden.

## <a name="prerequisites-and-requirements"></a>vereisten en vereisten

Microsoft Defender Offline in Windows 10 dezelfde hardwarevereisten als Windows 10. 

Zie de volgende onderwerpen voor meer Windows 10 vereisten:

- [Minimale hardwarevereisten](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)

- [Richtlijnen voor hardwarecomponenten](/windows-hardware/design/component-guidelines/components)

> [!NOTE]
> Microsoft Defender Offline wordt niet ondersteund op machines met ARM processors of op Windows Server Stock Keeping Units.

Als u Microsoft Defender Offline vanaf het eindpunt wilt uitvoeren, moet de gebruiker zijn aangemeld met beheerdersbevoegdheden.
 
## <a name="microsoft-defender-offline-updates"></a>Microsoft Defender Offline updates

Microsoft Defender Offline de meest recente beveiligingsupdates die beschikbaar zijn op het eindpunt. deze wordt bijgewerkt wanneer Windows Defender Antivirus wordt bijgewerkt. 

> [!NOTE]
> Voordat u een offlinescan uitwerkt, moet u proberen microsoft Defender AV-beveiliging bij te werken. U kunt een update met groepsbeleid forceeren of updates naar eindpunten implementeren, of u kunt de meest recente beveiligingsupdates handmatig downloaden en installeren vanaf de [Microsoft Malware Protection Center.](https://www.microsoft.com/security/portal/definitions/adl.aspx)

Zie het [onderwerp Microsoft Defender Antivirus beveiligingsinformatieupdates](manage-protection-updates-microsoft-defender-antivirus.md) beheren voor meer informatie.

## <a name="usage-scenarios"></a>Gebruiksscenario's

In Windows 10, versie 1607, kunt u handmatig een offlinescan forcen. Als de gebruiker Windows Defender dat de Microsoft Defender Offline moet uitvoeren, wordt de gebruiker op het eindpunt gevraagd. 

De noodzaak om een offlinescan uit te voeren, wordt ook in Microsoft Endpoint Manager als u deze gebruikt om uw eindpunten te beheren.

De prompt kan optreden via een melding, vergelijkbaar met de volgende:

:::image type="content" source="../../media/notification.png" alt-text="Melding voor het uitvoeren van Microsoft Defender Offline":::

De gebruiker krijgt ook een melding binnen de Windows Defender client.

In Configuration Manager kunt u de status van eindpunten identificeren door te navigeren naar Controle **> Overzicht > Beveiliging > Endpoint Protection Status > System Center Endpoint Protection Status.** 

Microsoft Defender Offline scans worden aangegeven onder **Malware herstelstatus** als **Offline scannen vereist**.

:::image type="content" source="../../media/sccm-wdo.png" alt-text="Microsoft Defender Offline scan is vereist":::

## <a name="configure-notifications"></a>Meldingen configureren

Microsoft Defender Offline meldingen zijn geconfigureerd in dezelfde beleidsinstelling als andere AV-meldingen van Microsoft Defender.

Zie het onderwerp De meldingen configureren die worden weergegeven in het onderwerp eindpunten voor meer informatie over meldingen in [Windows Defender.](configure-notifications-microsoft-defender-antivirus.md)

## <a name="run-a-scan"></a>Een scan uitvoeren 

> [!IMPORTANT]
> Voordat u de Microsoft Defender Offline, moet u alle bestanden opslaan en de lopende programma's afsluiten. De Microsoft Defender Offline scan duurt ongeveer 15 minuten. Het eindpunt wordt opnieuw gestart wanneer de scan is voltooid. De scan wordt uitgevoerd buiten de gebruikelijke Windows omgeving. De gebruikersinterface wordt anders weergegeven dan een normale scan uitgevoerd door Windows Defender. Nadat de scan is voltooid, wordt het eindpunt opnieuw gestart en Windows normaal geladen.

U kunt een Microsoft Defender Offline uitvoeren met de volgende opties:

- PowerShell
- Windows Beheerinstrumentatie (WMI)
- De Windows-beveiliging app



### <a name="use-powershell-cmdlets-to-run-an-offline-scan"></a>PowerShell-cmdlets gebruiken om een offlinescan uit te voeren

Gebruik de volgende cmdlets:

```PowerShell
Start-MpWDOScan
```

Zie [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) gebruiken om Microsoft Defender Antivirus en [Defender-cmdlets](/powershell/module/defender/) te configureren en uit te voeren voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.

### <a name="use-windows-management-instruction-wmi-to-run-an-offline-scan"></a>Gebruik Windows Management Instruction (WMI) om een offlinescan uit te voeren

Gebruik de [**MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) om een offlinescan uit te voeren.

In het volgende WMI-scriptfragment wordt onmiddellijk een Microsoft Defender Offline-scan uitgevoerd, waardoor het eindpunt opnieuw wordt gestart, de offlinescan wordt uitgevoerd en vervolgens opnieuw wordt gestart en Windows.

```console
wmic /namespace:\\root\Microsoft\Windows\Defender path MSFT_MpWDOScan call Start 
```

Zie het volgende voor meer informatie:
- [Windows Defender WMIv2-API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-the-windows-defender-security-app-to-run-an-offline-scan"></a>De beveiligings-Windows Defender gebruiken om een offlinescan uit te voeren

1. Open de Windows-beveiliging app door op het schildpictogram in de taakbalk te klikken of door te zoeken in het startmenu voor **Defender.**

2. Klik op **de tegel & virusbeveiliging** (of het schildpictogram op de linkermenubalk) en klik vervolgens op **het** label Geavanceerd scannen:
    
3. Selecteer **Microsoft Defender Offline scannen en** klik op Nu **scannen.**

    > [!NOTE]
    > In Windows 10, versie 1607, kan de offlinescan worden uitgevoerd onder **Windows Instellingen**  >  **Update & beveiligingsupdate** Windows Defender of vanuit de Windows Defender  >   client.


## <a name="review-scan-results"></a>Scanresultaten controleren

Microsoft Defender Offline scanresultaten worden weergegeven in de sectie [Scangeschiedenis van de Windows-beveiliging app.](microsoft-defender-security-center-antivirus.md) 


## <a name="related-articles"></a>Verwante artikelen

- [De resultaten van scans en herstel aanpassen, starten en controleren](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)