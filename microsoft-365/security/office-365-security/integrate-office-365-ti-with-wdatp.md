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
description: Integratie van Office 365 Advanced Threat Protection met Microsoft Defender Advanced Threat Protection voor meer gedetailleerde informatie over risicobeheer.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0906b8b44922084a65999dd9ab10a09c827605c2
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201969"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a>Office 365 Advanced Threat Protection integreren met Microsoft Defender Advanced Threat Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (Office 365 ATP) kan worden geconfigureerd voor gebruik met [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender ATP).

Het integreren van Office 365-ATP met Microsoft Defender ATP kan de team monitor van uw beveiliging en de werking van de gebruikers snel uitvoeren als de apparaten van de gebruikers risico lopen. Wanneer de integratie is ingeschakeld, kunnen uw beveiligingsteam bijvoorbeeld de apparaten zien waarop het gedetecteerde e-mailbericht mogelijk invloed heeft en van het aantal recente meldingen voor deze apparaten in Microsoft Defender ATP. 

In de volgende afbeelding wordt getoond waarop op het tabblad **apparaten** de integratie met Microsoft Defender ATP is ingeschakeld:
  
![Wanneer Microsoft Defender ATP is ingeschakeld, kunt u een lijst met apparaten met waarschuwingen weergeven.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
In dit voorbeeld ziet u dat de geadresseerden van het gedetecteerde e-mailbericht vier apparaten hebben en dat er een waarschuwing is. Als u op de koppeling voor een apparaat klikt, wordt de pagina geopend in het Microsoft Defender-Beveiligingscentrum [https://securitycenter.windows.com](https://securitycenter.windows.com) .

> [!TIP]
> Meer **[informatie over het Microsoft Defender-Beveiligingscentrum](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (ook wel Microsoft Defender ATP Portal genoemd).
  
## <a name="requirements"></a>Vereisten

- Uw organisatie moet Office 365 ATP, abonnement 2 (of Office 365 E5) en Microsoft Defender ATP hebben.
    
- U moet een hoofdbeheerder zijn of de rol van beveiligingsbeheerder (zoals beveiligingsbeheerder) hebben die is toegewezen aan het [beveiligings &amp; conformiteitscentrum](https://protection.office.com). (Zie [machtigingen in het Security &amp; compliance Center](permissions-in-the-security-and-compliance-center.md))
    
- U moet in de beveiligings & nalevings centrum en het Microsoft Defender-Beveiligingscentrum toegang hebben tot zowel de [Verkenner (of realtime detectie)](threat-explorer.md) .
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a>Office 365 ATP integreren met Microsoft Defender ATP

Het integreren van Office 365-ATP met Microsoft Defender ATP wordt ingesteld met behulp van het beveiligings & nalevings centrum en het Microsoft Defender-Beveiligingscentrum.
  
1. Ga als globale beheerder of een beveiligingsbeheerder naar [https://protection.office.com](https://protection.office.com) en meld u aan. (U gaat nu naar het Beveiligingscentrum van Office 365 & nalevings centrum.)
    
2. Kies in het navigatiedeelvenster de optie **Threat Management**  >  **Explorer**.<br>![Verkenner in het menu Threat Management](../../media/ThreatMgmt-Explorer-nav.png)<br>
    
3. Kies in de rechterbovenhoek van het scherm **WDATP instellingen**.
    
4. Schakel in het dialoogvenster verbinding met Microsoft Defender ATP de optie **verbinding maken met Windows ATP**in.<br>![Microsoft Defender ATP-verbinding](../../media/Explorer-WDATPConnection-dialog.png)<br>
    
5. Ga naar het Microsoft Defender-Beveiligingscentrum ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).

6. Kies in de navigatiebalk de optie **instellingen**. Kies vervolgens onder **Algemeen** **geavanceerde functies**.

7. Schuif omlaag naar **Office 365 Threat Intelligence-verbinding**en zet de verbinding aan.<br/>![Office 365 Threat Intelligence-verbinding](../../media/mdatp-oatptoggle.png)<br>

## <a name="related-articles"></a>Verwante artikelen

[Oplossing voor onderzoek en antwoord van bedreigingen in Office 365](office-365-ti.md)
  
[Office 365 Advanced Threat Protection](office-365-atp.md)
  
[Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection)
