---
title: Problemen met rapportagehulpmiddelen voor Microsoft Defender AV oplossen
description: Veelvoorkomende problemen identificeren en oplossen wanneer u probeert te rapporteren in de AV-beveiligingsstatus van Microsoft Defender in Update Compliance
keywords: probleemoplossing, fout, fix, update compliance, oms, monitor, rapport, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3b1a1c807c86aa95148300298484319001b59963
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690773"
---
# <a name="troubleshoot-microsoft-defender-antivirus-reporting-in-update-compliance"></a>Problemen met Microsoft Defender Antivirusrapportage oplossen in Compliance bijwerken

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> Op 31 maart 2020 wordt de Microsoft Defender Antivirus-rapportagefunctie van Update Compliance verwijderd. U kunt beleidsregels voor beveiligings compliance blijven definiëren en controleren met [Microsoft Endpoint Manager,](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)waarmee u meer controle hebt over beveiligingsfuncties en updates.

U kunt Microsoft Defender Antivirus gebruiken met update compliance. U ziet de status voor E3-, B-, F1-, VL- en Pro-licenties. Voor E5-licenties moet u echter de [Microsoft Defender for Endpoint-portal gebruiken.](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) Zie Windows [10 productlicentieopties](https://www.microsoft.com/licensing/product-licensing/windows10.aspx)voor meer informatie over licentieopties.

Wanneer u [Windows Analytics Update Compliance](/windows/deployment/update/update-compliance-using#wdav-assessment) gebruikt om rapportage te verkrijgen over de beveiligingsstatus van apparaten of eindpunten in uw netwerk die Microsoft Defender Antivirus gebruiken, kunnen er problemen of problemen zijn.

Meestal zijn de meest voorkomende indicatoren van een probleem:
- U ziet slechts een klein aantal of een subset van alle apparaten die u verwachtte te zien
- U ziet helemaal geen apparaten
- De rapporten en informatie die u ziet, zijn verouderd (ouder dan een paar dagen)

Zie Microsoft [Defender Antivirus-gebeurtenissen](troubleshoot-microsoft-defender-antivirus.md)voor veelvoorkomende foutcodes en gebeurtenis-ID's die betrekking hebben op de Microsoft Defender Antivirus-service die niet gerelateerd zijn aan Update Compliance. 

Er zijn drie stappen om deze problemen op te lossen:

1. Controleren of u aan alle vereisten hebt voldaan
2. Uw verbinding met de cloudservice van Windows Defender controleren
3. Ondersteuningslogboeken verzenden

>[!IMPORTANT]
>Het duurt meestal 3 dagen voordat apparaten worden weergegeven in Naleving bijwerken.


## <a name="confirm-prerequisites"></a>Vereisten bevestigen

Om ervoor te zorgen dat apparaten correct worden uitgevoerd in Update compliance, moet u voldoen aan bepaalde vereisten voor zowel de Update Compliance-service als voor Microsoft Defender Antivirus:

>[!div class="checklist"]
>- Eindpunten gebruiken Microsoft Defender Antivirus als de enige antivirusbeveiligings-app. [Als u een andere antivirus-app gebruikt,](microsoft-defender-antivirus-compatibility.md) wordt Microsoft Defender AV uitgeschakeld en wordt het eindpunt niet gerapporteerd in Naleving bijwerken.
> - [Beveiliging in de cloud is ingeschakeld.](enable-cloud-protection-microsoft-defender-antivirus.md)
> - Eindpunten kunnen verbinding [maken met de MICROSOFT Defender AV-cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)
> - Als op het eindpunt Windows 10 versie 1607 of eerder wordt uitgevoerd, moeten diagnostische gegevens van [Windows 10 zijn](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level)ingesteld op het niveau Enhanced .
> - Het is 3 dagen geleden dat aan alle vereisten is voldaan

"U kunt Microsoft Defender Antivirus gebruiken met Update Compliance. U ziet de status voor E3-, B-, F1-, VL- en Pro-licenties. Voor E5-licenties moet u echter de Microsoft Defender for Endpoint-portal gebruiken ( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) . Zie Windows 10 productlicentieopties voor meer informatie over licentieopties.

Als aan de bovenstaande vereisten is voldaan, moet u mogelijk verder gaan met de volgende stap om diagnostische gegevens te verzamelen en naar ons te verzenden.

> [!div class="nextstepaction"]
> [Diagnostische gegevens verzamelen voor probleemoplossing voor update compliance](collect-diagnostic-data.md)  

## <a name="related-topics"></a>Verwante onderwerpen

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender Antivirus implementeren](deploy-manage-report-microsoft-defender-antivirus.md)