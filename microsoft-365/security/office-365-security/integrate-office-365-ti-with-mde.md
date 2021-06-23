---
title: Microsoft Defender gebruiken voor Office 365 samen met Microsoft Defender voor Eindpunt
f1.keywords:
- NOCSH
keywords: integreren, Microsoft Defender, Microsoft Defender voor Eindpunt
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 06/10/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Gebruik Microsoft Defender voor Office 365 samen met Microsoft Defender voor Eindpunt voor meer gedetailleerde informatie over bedreigingen tegen uw apparaten en e-mailinhoud.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fed3a04a7a699b4689cd9d6d9d335a8ba51d2fd8
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083378"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>Microsoft Defender gebruiken voor Office 365 samen met Microsoft Defender voor Eindpunt

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender voor Office 365](defender-for-office-365.md) kan worden geconfigureerd voor gebruik met [Microsoft Defender voor Eindpunt.](/windows/security/threat-protection)

Als u Microsoft Defender voor Office 365 met Microsoft Defender voor Eindpunt integreert, kan uw beveiligingsteam uw beveiligingsactiviteiten helpen bij het controleren en snel actie ondernemen als de apparaten van gebruikers in gevaar zijn. Wanneer integratie bijvoorbeeld is ingeschakeld, kan uw beveiligingsteam de apparaten zien die mogelijk worden beïnvloed door een gedetecteerd e-mailbericht en hoeveel recente waarschuwingen er zijn gegenereerd voor die apparaten in Microsoft Defender voor Eindpunt.

In de volgende afbeelding ziet u hoe het tabblad **Apparaten** eruitziet wanneer Microsoft Defender voor endpoint-integratie is ingeschakeld:

![Wanneer Microsoft Defender voor Eindpunt is ingeschakeld, ziet u een lijst met apparaten met waarschuwingen.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

In dit voorbeeld kunt u zien dat de geadresseerden van het gedetecteerde e-mailbericht vier apparaten hebben en één een waarschuwing heeft. Als u op de koppeling voor een apparaat klikt, wordt de pagina geopend in [Microsoft 365 Defender portal](../defender-endpoint/microsoft-defender-security-center.md) (voorheen het Microsoft Defender-beveiligingscentrum).

> [!TIP]
> De Microsoft 365 Defender portal vervangt de Microsoft Defender-beveiligingscentrum. Zie [Microsoft Defender voor Eindpunt in Microsoft 365 Defender.](../defender/microsoft-365-security-center-mde.md)

## <a name="requirements"></a>Vereisten

- Uw organisatie moet Microsoft Defender hebben voor Office 365 (of Office 365 E5) en Microsoft Defender voor Eindpunt.

- U moet een globale beheerder zijn of een beveiligingsbeheerderrol (zoals beveiligingsbeheerder) hebben toegewezen in Microsoft 365. Zie [Machtigingen in de Microsoft 365 Defender-portal](permissions-microsoft-365-security-center.md) voor meer informatie.

- U moet toegang hebben tot [Explorer (of realtimedetecties).](threat-explorer.md)

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>Microsoft Defender voor Office 365 integreren met Microsoft Defender voor Eindpunt

De integratie van Microsoft Defender voor Office 365 met Microsoft Defender voor Eindpunt is ingesteld in zowel Defender voor Eindpunt als Defender voor Office 365.

1. Als globale beheerder of beveiligingsbeheerder opent u de Microsoft 365 Defender portal () en gaat u naar <https://security.microsoft.com> **E-mail & Samenwerkingsverkenner.** \>  Als u rechtstreeks naar de **explorerpagina wilt** gaan, gebruikt u <https://security.microsoft.com/threatexplorer> .

2. Klik op **de pagina** Explorer in de rechterbovenhoek van het scherm op **MDE Instellingen.**

3. Schakel in **de flyout** microsoft Defender voor eindpuntverbinding die wordt weergegeven de Verbinding maken in bij **Microsoft Defender voor** Eindpunt ![ (schakelknop in) in en klik vervolgens op Pictogram ](../../media/scc-toggle-on.png) Sluiten ![ ](../../media/m365-cc-sc-close-icon.png) **sluiten.**

    :::image type="content" source="../../media/explorer-mdeconnection-dialognew.png" alt-text="MDE-verbinding":::

4. Kies terug in het navigatiedeelvenster **Instellingen.** Kies **op Instellingen** pagina **Eindpunten**

5. Kies geavanceerde functies op **de pagina** Eindpunten die wordt **geopend.**

6. Schuif omlaag naar **Office 365 Threat Intelligence-verbinding** en schakel deze in ( ![ Schakel de schakelknop ](../../media/scc-toggle-on.png) in).

   Wanneer u klaar bent, klikt u op **Voorkeuren opslaan.**

## <a name="related-articles"></a>Verwante artikelen

[Mogelijkheden voor het onderzoeken en reageren van bedreigingen in Office 365](office-365-ti.md)

[Microsoft Defender voor Office 365](defender-for-office-365.md)

[Microsoft Defender voor Eindpunt](/windows/security/threat-protection)
