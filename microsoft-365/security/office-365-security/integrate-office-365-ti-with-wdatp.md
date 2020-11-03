---
title: Microsoft Defender voor Office 365 samen met Microsoft Defender voor eindpunt gebruiken
f1.keywords:
- NOCSH
keywords: integreren, Microsoft Defender, ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 09/29/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Gebruik Microsoft Defender voor Office 365 samen met Microsoft Defender for Endpoint voor meer informatie over bedreigingen voor uw apparaten en e-mail inhoud.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6b8bec8d3ebe52de9b4e1b919b2aceee20b5b5b0
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842354"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>Microsoft Defender voor Office 365 samen met Microsoft Defender voor eindpunt gebruiken

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender voor Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) kan worden geconfigureerd voor gebruik met [Microsoft Defender voor eindpunt](https://docs.microsoft.com/windows/security/threat-protection).

Integratie van Microsoft Defender voor Office 365 met Microsoft Defender voor eindpunten kan uw beheer van beveiligingsactiviteiten ondersteunen en snel actie ondernemen als de apparaten van de gebruikers risico lopen. Wanneer de integratie is ingeschakeld, kunnen uw beveiligingsteam bijvoorbeeld de apparaten zien die van invloed zijn op het gedetecteerde e-mailbericht, en het aantal recente waarschuwingen voor deze apparaten in Microsoft Defender voor eindpunt. 

In de volgende afbeelding wordt getoond waarop op het tabblad **apparaten** de integratie met Microsoft Defender voor eindpunten is ingeschakeld:
  
![Wanneer Microsoft Defender for Endpoint is ingeschakeld, kunt u een lijst met apparaten met waarschuwingen weergeven.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
In dit voorbeeld ziet u dat de geadresseerden van het gedetecteerde e-mailbericht vier apparaten hebben en dat er een waarschuwing is. Als u op de koppeling voor een apparaat klikt, wordt de pagina geopend in het Microsoft Defender-Beveiligingscentrum [https://securitycenter.windows.com](https://securitycenter.windows.com) .

> [!TIP]
> Meer **[informatie over het Microsoft Defender-Beveiligingscentrum](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (ook wel Microsoft Defender for Endpoint Portal genoemd).
  
## <a name="requirements"></a>Vereisten

- Uw organisatie moet Microsoft Defender voor Office 365 (of Office 365 E5) en Microsoft Defender voor eindpunten hebben.
    
- U moet een hoofdbeheerder zijn of de rol van beveiligingsbeheerder (zoals beveiligingsbeheerder) hebben die is toegewezen aan het [beveiligings &amp; conformiteitscentrum](https://protection.office.com). (Zie [machtigingen in het Security &amp; compliance Center](permissions-in-the-security-and-compliance-center.md))
    
- U moet in de beveiligings & nalevings centrum en het Microsoft Defender-Beveiligingscentrum toegang hebben tot zowel de [Verkenner (of realtime detectie)](threat-explorer.md) .
    
## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>Microsoft Defender voor Office 365 integreren met Microsoft Defender voor eindpunt

Integratie van Microsoft Defender voor Office 365 met Microsoft Defender voor eindpunt is ingesteld met behulp van het beveiligings & nalevings centrum en het Microsoft Defender-Beveiligingscentrum.
  
1. Ga als globale beheerder of een beveiligingsbeheerder naar [https://protection.office.com](https://protection.office.com) en meld u aan. (U gaat nu naar het Beveiligingscentrum van Office 365 & nalevings centrum.)
    
2. Kies in het navigatiedeelvenster de optie **Threat Management**  >  **Explorer**.<br>![Verkenner in het menu Threat Management](../../media/ThreatMgmt-Explorer-nav.png)<br>
    
3. Kies in de rechterbovenhoek van het scherm de optie **Defender voor Eindpunts instellingen**.
    
4. Schakel in het dialoogvenster Microsoft Defender for Endpoint verbinding het selectievakje **verbinding maken met Microsoft Defender voor eindpunt** in.<br>![Microsoft Defender voor eindpunt verbinding](../../media/Explorer-WDATPConnection-dialog.png)<br>
    
5. Ga naar het Microsoft Defender-Beveiligingscentrum ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).

6. Kies in de navigatiebalk de optie **instellingen**. Kies vervolgens onder **Algemeen** **geavanceerde functies**.

7. Schuif omlaag naar **Office 365 Threat Intelligence-verbinding** en zet de verbinding aan.<br/>![Office 365 Threat Intelligence-verbinding](../../media/mdatp-oatptoggle.png)<br>

## <a name="related-articles"></a>Verwante artikelen

[Oplossing voor onderzoek en antwoord van bedreigingen in Office 365](office-365-ti.md)
  
[Microsoft Defender voor Office 365](office-365-atp.md)
  
[Microsoft Defender voor eindpunt](https://docs.microsoft.com/windows/security/threat-protection)
