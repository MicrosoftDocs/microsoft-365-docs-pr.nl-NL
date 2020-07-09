---
title: Office 365 ATP integreren met Microsoft Defender ATP
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 07/08/2020
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
ms.openlocfilehash: bfb87edd24a22033b3771ba0fd3c4f1afbbc988e
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086706"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a>Office 365 Advanced Threat Protection integreren met geavanceerde bedreigingsbeveiliging van Microsoft Defender

[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (Office 365 ATP) kan worden geconfigureerd om te werken met [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender ATP).

Als u Office 365 ATP integreert met Microsoft Defender ATP, kan uw beveiligingsteam snel kunnen controleren en actie ondernemen als de apparaten van gebruikers gevaar lopen. Zodra integratie is ingeschakeld, kan uw beveiligingsteam bijvoorbeeld de apparaten zien die mogelijk worden beïnvloed door een gedetecteerd e-mailbericht en hoeveel recente waarschuwingen deze apparaten hebben in Microsoft Defender ATP. 

In de volgende afbeelding wordt weergegeven hoe het tabblad **Apparaten** eruitziet als Microsoft Defender ATP-integratie is ingeschakeld:
  
![Wanneer Microsoft Defender ATP is ingeschakeld, ziet u een lijst met apparaten met waarschuwingen.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
In dit voorbeeld u zien dat de ontvangers van het gedetecteerde e-mailbericht vier apparaten hebben en één een waarschuwing. Als u op de koppeling voor een apparaat klikt, wordt de pagina geopend in het Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).

> [!TIP]
> **[Meer informatie over het Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (ook wel de Microsoft Defender ATP-portal genoemd).)
  
## <a name="requirements"></a>Vereisten

- Uw organisatie moet beschikken over Office 365 ATP Plan 2 (of Office 365 E5) en Microsoft Defender ATP.
    
- U moet een globale beheerder zijn of een beveiligingsbeheerdersrol (zoals beveiligingsbeheerder) hebben toegewezen in het [Security &amp; Compliance Center](https://protection.office.com). (Zie [machtigingen in het Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))
    
- U moet toegang hebben tot zowel [Explorer (of real-time detecties)](threat-explorer.md) in het Security & Compliance Center als het Microsoft Defender Security Center.
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a>Office 365 ATP integreren met Microsoft Defender ATP

De integratie van Office 365 ATP met Microsoft Defender ATP is opgezet met behulp van zowel het Security & Compliance Center als het Microsoft Defender Security Center.
  
1. Ga als globale beheerder of beveiligingsbeheerder naar [https://protection.office.com](https://protection.office.com) en meld u aan. (Hiermee gaat u naar het Office 365 Security & Compliance Center.)
    
2. Kies in het navigatiedeelvenster **Bedreigingsbeheerverkenner**  >  **Explorer**.<br>![Explorer in het menu Bedreigingsbeheer](../../media/ThreatMgmt-Explorer-nav.png)<br>
    
3. Kies in de rechterbovenhoek van het scherm **WDATP-instellingen.**
    
4. Schakel verbinding **maken met Windows ATP**in het dialoogvenster Microsoft Defender ATP in .<br>![Microsoft Defender ATP-verbinding](../../media/Explorer-WDATPConnection-dialog.png)<br>
    
5. Ga naar het Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).

6. Kies **Instellingen op**de navigatiebalk . Kies vervolgens onder **Algemeen** **geavanceerde functies**.

7. Schuif omlaag naar de Verbinding Met De Informatie van de Bedreiging van **Office 365**en schakel de verbinding in.<br/>![Verbinding met de informatie over bedreigingen van Office 365](../../media/mdatp-oatptoggle.png)<br>

## <a name="related-articles"></a>Verwante artikelen

[Mogelijkheden voor bedreigingsonderzoek en -reactie in Office 365](office-365-ti.md)
  
[Office 365 Advanced Threat Protection](office-365-atp.md)
  
[Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection)
