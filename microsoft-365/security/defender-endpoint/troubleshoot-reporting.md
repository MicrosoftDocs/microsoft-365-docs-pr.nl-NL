---
title: Problemen met rapportagehulpmiddelen voor Microsoft Defender AV oplossen
description: Veelvoorkomende problemen identificeren en oplossen wanneer u probeert te rapporteren in de AV-beveiligingsstatus van Microsoft Defender in Update Compliance
keywords: probleemoplossing, fout, fix, update compliance, oms, monitor, rapport, Microsoft Defender AV
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
ms.openlocfilehash: ab987089c20d0a1d0baed152e7ddcfdd2878cc65
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843456"
---
# <a name="troubleshoot-microsoft-defender-antivirus-reporting-in-update-compliance"></a>Problemen met Microsoft Defender Antivirus-rapportage oplossen in Naleving van updates

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> Op 31 maart 2020 wordt de Microsoft Defender Antivirus van Update Compliance verwijderd. U kunt beleidsregels voor beveiligings compliance blijven definiëren en controleren met [Microsoft Endpoint Manager,](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)waardoor u meer controle hebt over beveiligingsfuncties en updates.

U kunt een Microsoft Defender Antivirus update compliance gebruiken. U ziet de status voor E3-, B-, F1-, VL- en Pro licenties. Voor E5-licenties moet u echter de [Microsoft Defender for Endpoint-portal gebruiken.](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) Zie voor meer informatie over licentieopties [Windows 10 opties voor productlicenties.](https://www.microsoft.com/licensing/product-licensing/windows10.aspx)

Wanneer u [Windows Analytics Update Compliance](/windows/deployment/update/update-compliance-using#wdav-assessment) gebruikt om rapportage te verkrijgen over de beveiligingsstatus van apparaten of eindpunten in uw netwerk die Microsoft Defender Antivirus gebruiken, kunnen er problemen of problemen zijn.

Meestal zijn de meest voorkomende indicatoren van een probleem:
- U ziet slechts een klein aantal of een subset van alle apparaten die u verwachtte te zien
- U ziet helemaal geen apparaten
- De rapporten en informatie die u ziet, zijn verouderd (ouder dan een paar dagen)

Voor veelvoorkomende foutcodes en gebeurtenis-ID's met betrekking tot de Microsoft Defender Antivirus service die niet gerelateerd zijn aan Compliance bijwerken, zie [Microsoft Defender Antivirus gebeurtenissen.](troubleshoot-microsoft-defender-antivirus.md) 

Er zijn drie stappen om deze problemen op te lossen:

1. Controleren of u aan alle vereisten hebt voldaan
2. Uw connectiviteit met de Windows Defender cloudservice controleren
3. Ondersteuningslogboeken verzenden

>[!IMPORTANT]
>Het duurt meestal 3 dagen voordat apparaten worden weergegeven in Naleving bijwerken.


## <a name="confirm-prerequisites"></a>Vereisten bevestigen

Om ervoor te zorgen dat apparaten correct worden uitgevoerd in Update compliance, moet u voldoen aan bepaalde vereisten voor zowel de Update Compliance-service als voor Microsoft Defender Antivirus:

>[!div class="checklist"]
>- Eindpunten gebruiken Microsoft Defender Antivirus als de enige antivirusbeveiligingsapp. [Als u een andere antivirus-app gebruikt,](microsoft-defender-antivirus-compatibility.md) wordt Microsoft Defender AV uitgeschakeld en wordt het eindpunt niet gerapporteerd in Naleving bijwerken.
> - [Beveiliging in de cloud is ingeschakeld.](enable-cloud-protection-microsoft-defender-antivirus.md)
> - Eindpunten kunnen verbinding [maken met de MICROSOFT Defender AV-cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)
> - Als het eindpunt wordt uitgevoerd Windows 10 versie 1607 of eerder, moeten Windows 10 diagnostische gegevens zijn ingesteld op [het niveau Verbeterd.](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level)
> - Het is 3 dagen geleden dat aan alle vereisten is voldaan

"U kunt een Microsoft Defender Antivirus update compliance gebruiken. U ziet de status voor E3-, B-, F1-, VL- en Pro licenties. Voor E5-licenties moet u echter de Microsoft Defender for Endpoint-portal (/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) gebruiken. Zie voor meer informatie over licentieopties Windows 10 opties voor productlicenties"

Als aan de bovenstaande vereisten is voldaan, moet u mogelijk verder gaan met de volgende stap om diagnostische gegevens te verzamelen en naar ons te verzenden.

> [!div class="nextstepaction"]
> [Diagnostische gegevens verzamelen voor probleemoplossing voor update compliance](collect-diagnostic-data.md)  

## <a name="related-topics"></a>Verwante onderwerpen

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Implementatie van Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)