---
title: Office 365 Advanced Threat Protection integreren met Geavanceerde bedreigingsbeveiliging van Microsoft Defender
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 01/22/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection:
- M365-security-compliance
description: Integreer Office 365 Advanced Threat Protection met Microsoft Defender Advanced Threat Protection om meer gedetailleerde informatie over bedreigingsbeheer te bekijken.
ms.openlocfilehash: 8096a950e66ed94d6e056f40b737d89d48cb811e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42810419"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a>Office 365 Advanced Threat Protection integreren met Geavanceerde bedreigingsbeveiliging van Microsoft Defender

Als u deel uitmaakt van het beveiligingsteam van uw organisatie, u [Office 365 Advanced Threat Protection](office-365-atp.md) en gerelateerde onderzoeks- en responsfuncties integreren met Microsoft Defender Advanced Threat [Protection.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) Dit kan u helpen snel te begrijpen of de machines van gebruikers risico lopen wanneer u bedreigingen in Office 365 onderzoekt. Zodra de integratie is ingeschakeld, u bijvoorbeeld een lijst met machines zien die worden gebruikt door de ontvangers van een gedetecteerd e-mailbericht, evenals hoeveel recente waarschuwingen deze machines hebben in Microsoft Defender Advanced Threat Protection.
  
In de volgende afbeelding wordt het tabblad **Apparaten** weergegeven dat u ziet wanneer de Microsoft Defender ATP-integratie is ingeschakeld:
  
![Wanneer Microsoft Defender ATP is ingeschakeld, u een lijst met machines met waarschuwingen zien.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
In dit voorbeeld u zien dat de ontvangers van het e-mailbericht vier apparaten hebben en één een waarschuwing. Als u op de koppeling voor een apparaat klikt, wordt de pagina geopend in het Microsoft Defender Security Center.
  
## <a name="requirements"></a>Vereisten

- Uw organisatie moet beschikken over Office 365 ATP-abonnement 2 (of Office 365 E5) en Microsoft Defender ATP.
    
- U moet een Globale Office 365-beheerder zijn of een rol van beveiligingsbeheerder (zoals beveiligingsbeheerder) hebben toegewezen in het [Security &amp; Compliance Center.](https://protection.office.com) (Zie [machtigingen in het Office &amp; 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md))
    
- U moet toegang hebben tot zowel [Explorer (als realtime detecties)](threat-explorer.md) in het Security & Compliance Center en het Microsoft Defender Security Center.
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a>Office 365 ATP integreren met Microsoft Defender ATP

De integratie van Office 365 ATP met Microsoft Defender ATP is opgezet met behulp van zowel het Security & Compliance Center als het Microsoft Defender Security Center.
  
1. Als globale office 365-beheerder of beveiligingsbeheerder gaat u naar [https://protection.office.com](https://protection.office.com) en meldt u zich aan met uw werk- of schoolaccount voor Office 365.
    
2. Kies **Explorer voor bedreigingsbeheer** \> **.**<br>![Explorer in het menu Bedreigingsbeheer](../../media/ThreatMgmt-Explorer-nav.png)<br>
    
3. Kies in de rechterbovenhoek van het scherm **WDATP-instellingen**.
    
4. Schakel in het dialoogvenster Windows Defender ATP-verbinding Verbinding maken met Windows ATP in.<br>![Microsoft Defender ATP-verbinding](../../media/Explorer-WDATPConnection-dialog.png)<br>
    
5. Schakel de verbinding in in het Microsoft Defender Security Center.

  
## <a name="related-topics"></a>Verwante onderwerpen

[Onderzoek en reactie van office 365-bedreigingen](office-365-ti.md)
  
[Geavanceerde bedreigingsbeveiliging van Office 365](office-365-atp.md)
  

