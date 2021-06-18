---
title: Microsoft Defender Antivirus in de Windows-beveiliging app
description: Met Microsoft Defender Antivirus nu opgenomen in de Windows-beveiliging app, kunt u veelvoorkomende taken bekijken, vergelijken en uitvoeren.
keywords: wdav, antivirus, firewall, beveiliging, windows
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
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: c15e68a74c9bf518822fce211d6c7d5c4dbc3f2c
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007442"
---
# <a name="microsoft-defender-antivirus-in-the-windows-security-app"></a>Microsoft Defender Antivirus in de Windows-beveiliging app

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

In Windows 10 versie 1703 en hoger maakt de Windows Defender deel uit van de Windows-beveiliging.

Instellingen die eerder deel uitmaakten van de Windows Defender-client en hoofd-Windows Instellingen zijn gecombineerd en verplaatst naar de nieuwe app, die standaard is geïnstalleerd als onderdeel van Windows 10, versie 1703.

> [!IMPORTANT]
> Het uitschakelen van de Windows-beveiliging Center-service wordt niet uitgeschakeld Microsoft Defender Antivirus of [Windows Defender Firewall.](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) Deze worden automatisch uitgeschakeld wanneer een antivirus- of firewallproduct van derden is geïnstalleerd en up-to-date wordt gehouden.
>
> Als u de Windows-beveiliging Center-service uit schakelt of de bijbehorende instellingen voor groepsbeleid configureert om te voorkomen dat de service wordt gebruikt of uitgevoerd, kan de Windows-beveiliging-app verouderde of onjuiste informatie weergeven over antivirus- of firewallproducten die u op het apparaat hebt geïnstalleerd.
> Het kan ook voorkomen dat Microsoft Defender Antivirus zichzelf inschakelen als u een oude of verouderde antivirussoftware van derden hebt of als u antivirusproducten van derden verwijdert die u eerder hebt geïnstalleerd.
> Hierdoor wordt de beveiliging van uw apparaat aanzienlijk lager en kan dit leiden tot malware-infecties.

Zie het [Windows-beveiliging artikel](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) voor meer informatie over andere Windows beveiligingsfuncties die in de app kunnen worden gecontroleerd.

De Windows-beveiliging app is een clientinterface op Windows 10, versie 1703 en hoger. Het is niet de Microsoft Defender-beveiligingscentrum webportal die wordt gebruikt voor het controleren en beheren van [Microsoft Defender voor Eindpunt.](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)

## <a name="review-virus-and-threat-protection-settings-in-the-windows-security-app"></a>Instellingen voor virus- en bedreigingsbeveiliging in de Windows-beveiliging controleren

:::image type="content" source="../../media/wdav-protection-settings-wdsc.png" alt-text="Instellingen voor virus- en bedreigingsbeveiliging in Windows-beveiliging app":::

1. Open de Windows-beveiliging app door op het schildpictogram in de taakbalk te klikken of door te zoeken in het startmenu voor **Defender.**

2. Selecteer de **tegel Virus & bedreigingsbeveiliging** (of het schildpictogram op de linkermenubalk).
   
In de volgende secties wordt beschreven hoe u enkele van de meest voorkomende taken uitvoert bij het controleren of werken met de bedreigingsbeveiliging die door Microsoft Defender Antivirus in de Windows-beveiliging app.

> [!NOTE]
> Als deze instellingen zijn geconfigureerd en geïmplementeerd met groepsbeleid, zijn de instellingen die in deze sectie worden beschreven grijs en niet beschikbaar voor gebruik op afzonderlijke eindpunten. Wijzigingen die zijn aangebracht via een groepsbeleidsobject, moeten eerst worden geïmplementeerd op afzonderlijke eindpunten voordat de instelling wordt bijgewerkt in de Windows-instellingen. In [het onderwerp Interactie tussen eindgebruikers configureren Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md) wordt beschreven hoe lokale beleidsinstellingen kunnen worden geconfigureerd.

## <a name="run-a-scan-with-the-windows-security-app"></a>Een scan uitvoeren met de Windows-beveiliging app

1. Open de Windows-beveiliging app door te zoeken in het startmenu **voor** Beveiliging en selecteer vervolgens **Windows-beveiliging.**

2. Selecteer de **tegel Virus & bedreigingsbeveiliging** (of het schildpictogram op de linkermenubalk).

3. Selecteer **Snel scannen.** Of als u een volledige scan wilt uitvoeren, **selecteert** u Scanopties en selecteert u vervolgens een optie, zoals **Volledige scan.**

## <a name="review-the-security-intelligence-update-version-and-download-the-latest-updates-in-the-windows-security-app"></a>Bekijk de versie van de beveiligingsinformatieupdate en download de meest recente updates in de Windows-beveiliging app

:::image type="content" source="../../media/wdav-wdsc-defs.png" alt-text="Versienummer beveiligingsinformatie":::

1. Open de Windows-beveiliging app door te zoeken in het startmenu *voor* Beveiliging en selecteer vervolgens **Windows-beveiliging.**

2. Selecteer de **tegel Virus & bedreigingsbeveiliging** (of het schildpictogram op de linkermenubalk).

3. Selecteer **Virus- & beveiligingsupdates voor bedreigingen.** De momenteel geïnstalleerde versie wordt weergegeven, samen met informatie over wanneer deze is gedownload. U kunt uw huidige gegevens controleren op de nieuwste versie die beschikbaar is voor handmatig downloaden of het wijzigingslogboek voor die versie controleren. Zie [Beveiligingsinformatie-updates voor Microsoft Defender Antivirus en andere Microsoft-antimalware.](https://www.microsoft.com/en-us/wdsi/defenderupdates)

4. Selecteer **Controleren op updates om** nieuwe beveiligingsupdates te downloaden (als deze er zijn).

## <a name="ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app"></a>Controleren Microsoft Defender Antivirus is ingeschakeld in de Windows-beveiliging app

1. Open de Windows-beveiliging app door te zoeken in het startmenu *voor* Beveiliging en selecteer vervolgens **Windows-beveiliging.**

2. Selecteer de **tegel Virus & bedreigingsbeveiliging** (of het schildpictogram op de linkermenubalk).

3. Selecteer **Virusbeveiliging & beveiligingsinstellingen voor bedreigingen.**

4. Schakel de schakelknop **Realtimebeveiliging** in op **Aan.**

    > [!NOTE]
    > Als u **realtimebeveiliging uitschakelt,** wordt deze na een korte vertraging automatisch weer inschakelen. Dit is om ervoor te zorgen dat u beschermd bent tegen malware en bedreigingen.
    > Als u een ander antivirusproduct installeert, schakelt Microsoft Defender Antivirus zichzelf automatisch uit en wordt deze als zodanig aangegeven in de Windows-beveiliging app. Er wordt een instelling weergegeven waarmee u beperkt periodiek scannen [kunt inschakelen.](limited-periodic-scanning-microsoft-defender-antivirus.md)

## <a name="add-exclusions-for-microsoft-defender-antivirus-in-the-windows-security-app"></a>Uitsluitingen toevoegen voor Microsoft Defender Antivirus in de Windows-beveiliging app

1. Open de Windows-beveiliging app door te zoeken in het startmenu *voor* Beveiliging en selecteer vervolgens **Windows-beveiliging.**

2. Selecteer de **tegel Virus & bedreigingsbeveiliging** (of het schildpictogram op de linkermenubalk).

3. Selecteer onder **Instellingen beheren** de optie Virus & instellingen **voor bedreigingsbeveiliging.**

4. Selecteer onder **de instelling Uitsluitingen** de optie **Uitsluitingen toevoegen of verwijderen.** 

5. Selecteer het pluspictogram **+** () om het type te kiezen en stel de opties in voor elke uitsluiting. 

De volgende tabel bevat een overzicht van uitsluitingstypen en wat er gebeurt:

|Type uitsluiting  |Gedefinieerd door  |Wat gebeurt er?  |
|---------|---------|---------|
|**Bestand** |Locatie <br/>Voorbeeld: `c:\sample\sample.test` |Het specifieke bestand wordt overgeslagen door Microsoft Defender Antivirus. |
|**Map**    |Locatie <br/>Voorbeeld: `c:\test\sample`       |Alle items in de opgegeven map worden overgeslagen door Microsoft Defender Antivirus.         |
|**Bestandstype**   |Bestandsextensie <br/>Voorbeeld: `.test` |Alle bestanden met de `.test` extensie op uw apparaat worden overgeslagen door Microsoft Defender Antivirus.         |
|**Proces**     |Uitvoerbaar bestandspad <br>Voorbeeld: `c:\test\process.exe`         |Het specifieke proces en alle bestanden die door dat proces worden geopend, worden overgeslagen door Microsoft Defender Antivirus.         |

Zie de volgende bronnen voor meer informatie:
- [Uitsluitingen configureren en valideren op basis van bestandsextensie en maplocatie](./configure-extension-file-exclusions-microsoft-defender-antivirus.md) 
- [Uitsluitingen configureren voor bestanden die door processen zijn geopend](./configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="review-threat-detection-history-in-the-windows-defender-security-center-app"></a>Geschiedenis van bedreigingsdetectie bekijken in Windows Defender beveiligingscentrum-app

1. Open de Windows-beveiliging app door te zoeken in het startmenu *voor* Beveiliging en selecteer vervolgens **Windows-beveiliging.**

2. Selecteer de **tegel Virus & bedreigingsbeveiliging** (of het schildpictogram op de linkermenubalk).

3. Selecteer **Beveiligingsgeschiedenis.** Recente items worden weergegeven.

## <a name="set-ransomware-protection-and-recovery-options"></a>Opties voor beveiliging en herstel van ransomware instellen

1. Open de Windows-beveiliging app door te zoeken in het startmenu *voor* Beveiliging en selecteer vervolgens **Windows-beveiliging.**

2. Selecteer de **tegel Virus & bedreigingsbeveiliging** (of het schildpictogram op de linkermenubalk).

3. Selecteer **onder Ransomware-beveiliging** de optie **Ransomware-beveiliging beheren.**

4. Zie Belangrijke mappen beveiligen met gecontroleerde maptoegang als u instellingen **voor** gecontroleerde maptoegang [wilt wijzigen.](/microsoft-365/security/defender-endpoint/controlled-folders)

5. Als u herstelopties voor  ransomware wilt instellen, selecteert u Instellen onder **Ransomware data recovery** en volgt u de instructies voor het koppelen of instellen van uw OneDrive-account, zodat u eenvoudig kunt herstellen van een ransomware-aanval.

## <a name="see-also"></a>Zie ook
- [Microsoft Defender Antivirus](microsoft-defender-antivirus-in-windows-10.md)