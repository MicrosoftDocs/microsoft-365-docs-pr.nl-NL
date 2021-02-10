---
title: Microsoft Defender voor Office 365 gebruiken samen met Microsoft Defender voor eindpunt
f1.keywords:
- NOCSH
keywords: integreren, Microsoft Defender, ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 01/21/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Gebruik Microsoft Defender voor Office 365 samen met Microsoft Defender voor Eindpunt voor meer gedetailleerde informatie over bedreigingen voor uw apparaten en e-mailinhoud.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 035834e1e4855c0e47defed06043a5fdbd0e63bd
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166085"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>Microsoft Defender voor Office 365 gebruiken samen met Microsoft Defender voor eindpunt

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender voor Office 365](office-365-atp.md) kan worden geconfigureerd voor gebruik met [Microsoft Defender voor het eindpunt.](https://docs.microsoft.com/windows/security/threat-protection)

Door Microsoft Defender voor Office 365 te integreren met Microsoft Defender voor het eindpunt, kan het team voor beveiligingsbewerkingen controleren en snel actie ondernemen als de apparaten van gebruikers risico lopen. Als de integratie is ingeschakeld, kan het team voor beveiligingsbewerkingen bijvoorbeeld de apparaten zien die mogelijk worden beïnvloed door een gedetecteerd e-mailbericht en kunnen er recente waarschuwingen worden gegenereerd voor deze apparaten in Microsoft Defender for Endpoint.

In de volgende afbeelding ziet u hoe **het** tabblad Apparaten eruitziet wanneer u integratie met Microsoft Defender voor eindpunt hebt ingeschakeld:

![Wanneer Microsoft Defender voor eindpunt is ingeschakeld, ziet u een lijst met apparaten met waarschuwingen.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

In dit voorbeeld ziet u dat de geadresseerden van het gedetecteerde e-mailbericht vier apparaten hebben en één apparaat een waarschuwing heeft. Als u op de koppeling voor een apparaat klikt, wordt de pagina geopend in het Microsoft Defender-beveiligingscentrum <https://securitycenter.windows.com> ().

> [!TIP]
> **[Meer informatie over het Microsoft Defender-beveiligingscentrum](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (ook wel de portal van Microsoft Defender voor eindpunt genoemd).

## <a name="requirements"></a>Vereisten

- Uw organisatie moet over Microsoft Defender voor Office 365 (of Office 365 E5) en Microsoft Defender voor eindpunt gaan.

- U moet een globale beheerder zijn of een rol als beveiligingsbeheerder hebben (zoals beveiligingsbeheerder) die is toegewezen in het & [compliancecentrum.](https://protection.office.com) (Zie [Machtigingen in het beveiligings- & Compliancecentrum)](permissions-in-the-security-and-compliance-center.md)

- U moet toegang hebben tot [Explorer (of realtime detecties)](threat-explorer.md) in het beveiligings- & compliancecentrum en het Microsoft Defender-beveiligingscentrum.

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>Microsoft Defender voor Office 365 integreren met Microsoft Defender voor eindpunt

De integratie van Microsoft Defender voor Office 365 met Microsoft Defender voor eindpunt wordt ingesteld via zowel het beveiligings- & compliancecentrum als het Microsoft Defender-beveiligingscentrum.

1. Als globale beheerder of beveiligingsbeheerder gaat u naar en meld u <https://protection.office.com> aan. (Hiermee gaat u naar het Office 365-& compliancecentrum.)

2. Kies **Bedreigingsbeheerverkenner** in het \> **navigatiedeelvenster.**

   ![Explorer in het menu Bedreigingsbeheer](../../media/ThreatMgmt-Explorer-nav.png)

3. Kies in de rechterbovenhoek van het scherm **Defender voor eindpuntinstellingen (MDE-instellingen).**

4. Schakel in het dialoogvenster Verbinding maken met Microsoft Defender voor eindpunt **verbinding in met Microsoft Defender voor eindpunt.**

   ![Verbinding met Microsoft Defender voor eindpunt](../../media/Explorer-WDATPConnection-dialog.png)

5. Ga naar het Microsoft Defender-beveiligingscentrum <https://securitycenter.windows.com> ().

6. Kies Instellingen op de **navigatiebalk.** Kies vervolgens onder **Algemeen** geavanceerde **functies.**

7. Schuif omlaag naar **De verbinding met Office 365 Threat Intelligence** en schakel de verbinding in.

   ![Verbinding voor bedreigingsinformatie in Office 365](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a>Verwante artikelen

[Mogelijkheden voor bedreigingsonderzoek en -antwoorden in Office 365](office-365-ti.md)

[Microsoft Defender voor Office 365](office-365-atp.md)

[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection)
