---
title: Geef het door de cloud geleverde beveiligingsniveau op voor Microsoft Defender Antivirus
description: Stel uw niveau van beveiliging in de cloud in voor Microsoft Defender Antivirus.
keywords: Microsoft Defender Antivirus, antimalware, beveiliging, defender, cloud, agressiviteit, beschermingsniveau
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.date: 10/26/2020
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: fb4dd3114c411385f1a38cf7b0fd391a1b159b99
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924465"
---
# <a name="specify-the-cloud-delivered-protection-level"></a>Niveau voor door cloud geleverde beveiliging opgeven

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

U kunt uw niveau van cloudbeveiliging opgeven dat wordt geboden door Microsoft Defender Antivirus met Microsoft Endpoint Manager (aanbevolen) of groepsbeleid.

> [!TIP]
> Cloudbeveiliging is niet alleen beveiliging voor bestanden die zijn opgeslagen in de cloud. De Microsoft Defender Antivirus cloudservice is een mechanisme voor het leveren van bijgewerkte beveiliging aan uw netwerk en apparaten (ook wel eindpunten genoemd). Cloudbeveiliging met Microsoft Defender Antivirus maakt gebruik van gedistribueerde resources en machine learning om uw eindpunten te beschermen tegen een snelheid die veel sneller is dan traditionele beveiligingsinformatie-updates. Microsoft Intune en Microsoft Endpoint Manager maken nu deel uit van [Microsoft Endpoint Manager.](/mem/endpoint-manager-overview) 


## <a name="use-microsoft-endpoint-manager-to-specify-the-level-of-cloud-delivered-protection"></a>Gebruik Microsoft Endpoint Manager om het niveau van door de cloud geleverde beveiliging op te geven

1. Ga naar het Microsoft Endpoint Manager beheercentrum [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () en meld u aan.

2. Kies **Endpoint Security**  >  **Antivirus**.

3. Selecteer een antivirusprofiel. (Als u nog geen profiel hebt of als u een nieuw profiel wilt maken, zie Apparaatbeperkingsinstellingen [configureren in Microsoft Intune.](/intune/device-restrictions-configure)

4. Selecteer **Eigenschappen**. Kies vervolgens naast **Configuratie-instellingen** de optie **Bewerken.**

5. Vouw **Cloudbeveiliging uit** en  selecteer een van de volgende opties in de lijst beveiligingsniveau in de cloud:

    1. **Hoog:** Hiermee wordt een sterk detectieniveau toegepast.
    2. **Hoog plus:** gebruikt het **hoge** niveau en past extra beveiligingsmaatregelen toe (mogelijk van invloed op de prestaties van de client).
    3. **Nul tolerantie:** blokkeert alle onbekende uitvoerbare bestanden.

6. Kies **Controleren+ opslaan** en kies vervolgens **Opslaan.** 

> [!TIP]
> Hebt u hulp nodig? Zie de volgende bronnen:
> - [Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
> - [Instellingen voor eindpuntbeveiliging toevoegen in Intune](/mem/intune/protect/endpoint-protection-configure)
  

## <a name="use-group-policy-to-specify-the-level-of-cloud-delivered-protection"></a>Groepsbeleid gebruiken om het niveau van door de cloud geleverde beveiliging op te geven

1.  Open op uw groepsbeleidsbeheercomputer de [console Groepsbeleidsbeheer](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en klik vervolgens op **Bewerken.**

3.  Ga in **de Editor voor groepsbeleidsbeheer** naar **Beheersjablonen voor computerconfiguratie.**  >  

4.  Vouw de boom uit Windows **onderdelen**  >  **Microsoft Defender Antivirus**  >  **MpEngine**.

5.  Dubbelklik op de **instelling Beveiligingsniveau voor de cloud** selecteren en stel deze in op **Ingeschakeld.** Selecteer het beveiligingsniveau:
    - **Standaardblokkeringsniveau** biedt een sterke detectie zonder het risico op het detecteren van legitieme bestanden te vergroten.
    - **Matig blokkeringsniveau** biedt alleen gemiddeld voor detecties met hoog vertrouwen
    - **Met hoog blokkeringsniveau** wordt een sterk detectieniveau toegepast terwijl de prestaties van de client worden geoptimaliseerd (maar kunt u ook een grotere kans op onwaar-positieven bieden).
    - **Hoog + blokkeringsniveau** past extra beveiligingsmaatregelen toe (mogelijk van invloed op de prestaties van de client en vergroot de kans op onwaar positieven).
    - **Het blokkeringsniveau nul** tolerantie blokkeert alle onbekende uitvoerbare bestanden.
    
    > [!WARNING]
    > Hoewel het onwaarschijnlijk is dat u deze overstap naar **Hoog** of Hoog **+** inschakelt, kunnen sommige legitieme bestanden worden gedetecteerd (hoewel u de optie hebt om de blokkering te deblokkeren of te betwisten).

6. Klik op **OK**.

7. Implementeer het bijgewerkte groepsbeleidsobject. Zie [Group Policy Management Console](/windows/win32/srvnodes/group-policy)

> [!TIP]
> Gebruikt u on-premises groepsbeleidsobjecten? Bekijk hoe ze vertalen in de cloud. [Analyseer uw on-premises groepsbeleidsobjecten met groepsbeleidsanalyse in Microsoft Endpoint Manager - Preview.](/mem/intune/configuration/group-policy-analytics) 
  
## <a name="related-articles"></a>Aanverwante artikelen

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Cloudbeveiliging inschakelen](enable-cloud-protection-microsoft-defender-antivirus.md)
- [Antimalware-beleid maken en implementeren: Cloudbeveiligingsservice](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)