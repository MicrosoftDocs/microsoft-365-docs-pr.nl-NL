---
title: Office 365 ATP integreren met Microsoft Defender ATP
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 04/13/2020
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
description: Integreer Office 365 Advanced Threat Protection met Microsoft Defender Advanced Threat Protection voor meer gedetailleerde informatie over bedreigingsbeheer.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1574def6959bf63f061ff35bae71aed9657de436
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036363"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a>Office 365 Advanced Threat Protection integreren met Microsoft Defender Advanced Threat Protection

Als u deel uitmaakt van het beveiligingsteam van uw organisatie, u [Office 365 Advanced Threat Protection](office-365-atp.md) en gerelateerde onderzoeks- en reactiefuncties integreren met Microsoft Defender Advanced Threat [Protection.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) Dit kan u helpen snel te begrijpen of de machines van gebruikers risico lopen wanneer u bedreigingen in Office 365 onderzoekt. Zodra de integratie is ingeschakeld, u bijvoorbeeld een lijst zien met machines die worden gebruikt door de ontvangers van een gedetecteerd e-mailbericht, evenals hoeveel recente waarschuwingen deze machines hebben in Microsoft Defender Advanced Threat Protection.
  
In de volgende afbeelding ziet u het tabblad **Apparaten** dat u ziet wanneer de ATP-integratie van Microsoft Defender is ingeschakeld:
  
![Wanneer Microsoft Defender ATP is ingeschakeld, u een lijst met apparaten met waarschuwingen zien.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
In dit voorbeeld u zien dat de ontvangers van het e-mailbericht vier apparaten hebben en één een waarschuwing heeft. Als u op de koppeling voor een apparaat klikt, wordt de pagina geopend in het Microsoft Defender Security Center.
  
## <a name="requirements"></a>Vereisten

- Uw organisatie moet beschikken over Office 365 ATP Plan 2 (of Office 365 E5) en Microsoft Defender ATP.
    
- U moet een globale beheerder zijn of een beveiligingsbeheerderrol (zoals beveiligingsbeheerder) toegewezen hebben in het [Security &amp; Compliance Center.](https://protection.office.com) (Zie [Machtigingen in &amp; het Security Compliance Center)](permissions-in-the-security-and-compliance-center.md)
    
- U moet toegang hebben tot zowel [Explorer (of real-time detecties)](threat-explorer.md) in het Security & Compliance Center en het Microsoft Defender Security Center.
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a>Office 365 ATP integreren met Microsoft Defender ATP

De integratie van Office 365 ATP met Microsoft Defender ATP wordt ingesteld met behulp van zowel het Security & Compliance Center als het Microsoft Defender Security Center.
  
1. Ga als globale beheerder of beveiligingsbeheerder naar [https://protection.office.com](https://protection.office.com) en meld u aan met uw werk- of schoolaccount.
    
2. Kies **Threat management** \> **Explorer**.<br>![Explorer in het menu Bedreigingsbeheer](../../media/ThreatMgmt-Explorer-nav.png)<br>
    
3. Kies **WDATP-instellingen**in de rechterbovenhoek van het scherm .
    
4. Schakel in het dialoogvenster Microsoft Defender ATP-verbinding **Verbinding maken met Windows ATP**in.<br>![Microsoft Defender ATP-verbinding](../../media/Explorer-WDATPConnection-dialog.png)<br>
    
5. Schakel de verbinding in het[https://securitycenter.windows.com](https://securitycenter.windows.com)Microsoft Defender Security Center in ( ).

## <a name="related-topics"></a>Verwante onderwerpen

[Mogelijkheden voor onderzoek naar en respons op bedreigingen in Office 365](office-365-ti.md)
  
[Office 365 Advanced Threat Protection](office-365-atp.md)
  

