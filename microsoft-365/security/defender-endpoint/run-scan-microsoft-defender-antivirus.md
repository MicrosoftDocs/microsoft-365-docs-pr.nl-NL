---
title: On-demand scans uitvoeren en aanpassen in Microsoft Defender Antivirus
description: On-demand scans uitvoeren en configureren met behulp van PowerShell, Windows Management Instrumentation of afzonderlijk op eindpunten met de Windows-beveiliging app
keywords: scannen, on-demand, dos, intune, instant scan
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/10/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: b2910f9fe1c49178b8696d1a421248156b0fc4c2
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925729"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a>Microsoft Defender Antivirus-scans op aanvraag configureren en uitvoeren

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

U kunt een scan op aanvraag uitvoeren op afzonderlijke eindpunten. Deze scans worden direct uitgevoerd en u kunt parameters voor de scan definiëren, zoals de locatie of het type. Wanneer u een scan uit te voeren, kunt u kiezen uit drie typen: Snelle scan, volledige scan en aangepaste scan. Gebruik in de meeste gevallen een snelle scan. Een snelle scan bekijkt alle locaties waar malware kan zijn geregistreerd om te beginnen met het systeem, zoals registersleutels en bekende Windows opstartmappen. 

Gecombineerd met altijd-aan, realtime beveiliging, die bestanden controleert wanneer ze worden geopend en gesloten, en wanneer een gebruiker naar een map navigeert, biedt een snelle scan een sterke bescherming tegen malware die begint met malware op systeem- en kernelniveau. In de meeste gevallen is een snelle scan voldoende en is dit de aanbevolen optie voor geplande of on-demand scans.  [Meer informatie over scantypen.](schedule-antivirus-scans.md#quick-scan-full-scan-and-custom-scan)

> [!IMPORTANT]
> Microsoft Defender Antivirus wordt uitgevoerd in de context van het [LocalSystem-account](/windows/win32/services/localsystem-account) bij het uitvoeren van een lokale scan. Voor netwerkscans wordt de context van het apparaataccount gebruikt. Als het domeinapparaataccount niet over de juiste machtigingen voor toegang tot het delen heeft, werkt de scan niet. Controleer of het apparaat machtigingen heeft voor het delen van het access-netwerk.

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a>Een Microsoft Endpoint Manager gebruiken om een scan uit te voeren

1. Ga naar het Microsoft Endpoint Manager beheercentrum [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () en meld u aan.

2. Kies **Endpoint Security**  >  **Antivirus**.

3. Selecteer in de lijst met tabbladen **Windows 10 niet-ongezonde eindpunten.**

4. Selecteer quick **scan** (aanbevolen) of Volledig **scannen** in de lijst met acties.

[![AFBEELDING ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)

> [!TIP]
> Zie [Antimalware-](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)en firewalltaken voor meer informatie over het Microsoft Endpoint Manager voor het uitvoeren van een scan: Een scan op aanvraag uitvoeren.

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a>Het hulpprogramma mpcmdrun.exe opdrachtregel gebruiken om een scan uit te voeren

Gebruik de volgende `-scan` parameter:

```console
mpcmdrun.exe -scan -scantype 1
```

Zie Het opdrachtlijnhulpmiddel mpcmdrun.exe gebruiken voor het configureren en beheren van Microsoft Defender Antivirus voor meer informatie over het gebruik van het hulpprogramma en aanvullende parameters, zoals het starten van een volledige scan of het definiëren van [paden.](command-line-arguments-microsoft-defender-antivirus.md)

## <a name="use-microsoft-intune-to-run-a-scan"></a>Een Microsoft Intune gebruiken om een scan uit te voeren

1. Ga naar het Microsoft Endpoint Manager beheercentrum [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () en meld u aan.

2. Selecteer in de zijbalk **Apparaten**  >  **alle apparaten en** kies het apparaat dat u wilt scannen.

3. Selecteer **... Meer**. Selecteer in de opties **Snel scannen** (aanbevolen) of **Volledig scannen.**

## <a name="use-the-windows-security-app-to-run-a-scan"></a>De app Windows-beveiliging gebruiken om een scan uit te voeren

Zie [Een scan uitvoeren in de Windows-beveiliging app](microsoft-defender-security-center-antivirus.md) voor instructies voor het uitvoeren van een scan op afzonderlijke eindpunten.

## <a name="use-powershell-cmdlets-to-run-a-scan"></a>PowerShell-cmdlets gebruiken om een scan uit te voeren

Gebruik de volgende cmdlet:

```PowerShell
Start-MpScan
```

Zie [PowerShell-cmdlets gebruiken om powershell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) te configureren en uit te voeren Microsoft Defender Antivirus [defender-cmdlets](/powershell/module/defender/)voor meer informatie over het gebruik van PowerShell met Microsoft Defender Antivirus.

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a>Gebruik Windows Management Instruction (WMI) om een scan uit te voeren

Gebruik de [ **beginmethode** van](/previous-versions/windows/desktop/defender/start-msft-mpscan) de **MSFT_MpScan** klas.

Zie voor meer informatie over welke parameters zijn toegestaan Windows Defender [WMIv2-API's](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

