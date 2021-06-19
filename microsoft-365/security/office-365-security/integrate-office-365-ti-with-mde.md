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
ms.openlocfilehash: e59f608a6f732f58002dfd2ff34666865ab23f3d
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028873"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>Microsoft Defender gebruiken voor Office 365 samen met Microsoft Defender voor Eindpunt

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender voor Office 365](defender-for-office-365.md) kan worden geconfigureerd voor gebruik met [Microsoft Defender voor Eindpunt.](/windows/security/threat-protection)

Als u Microsoft Defender voor Office 365 met Microsoft Defender voor Eindpunt integreert, kan uw beveiligingsteam uw beveiligingsactiviteiten helpen bij het controleren en snel actie ondernemen als de apparaten van gebruikers in gevaar zijn. Wanneer integratie bijvoorbeeld is ingeschakeld, kan uw beveiligingsteam de apparaten zien die mogelijk worden beïnvloed door een gedetecteerd e-mailbericht en hoeveel recente waarschuwingen er zijn gegenereerd voor die apparaten in Microsoft Defender voor Eindpunt.

In de volgende afbeelding ziet u hoe het tabblad **Apparaten** eruitziet wanneer Microsoft Defender voor endpoint-integratie is ingeschakeld:

![Wanneer Microsoft Defender voor Eindpunt is ingeschakeld, ziet u een lijst met apparaten met waarschuwingen.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

In dit voorbeeld kunt u zien dat de geadresseerden van het gedetecteerde e-mailbericht vier apparaten hebben en één een waarschuwing heeft. Als u op de koppeling voor een apparaat klikt, wordt de pagina geopend in [Microsoft 365 Defender](../defender-endpoint/microsoft-defender-security-center.md) (voorheen de Microsoft Defender-beveiligingscentrum).

> [!TIP]
> De Microsoft 365 Defender portal vervangt de Microsoft Defender-beveiligingscentrum. Zie [Microsoft Defender voor Eindpunt in Microsoft 365 Defender.](../defender/microsoft-365-security-center-mde.md)

## <a name="requirements"></a>Vereisten

- Uw organisatie moet Microsoft Defender hebben voor Office 365 (of Office 365 E5) en Microsoft Defender voor Eindpunt.

- U moet een globale beheerder zijn of een beveiligingsbeheerderrol (zoals beveiligingsbeheerder) hebben toegewezen in Microsoft 365. (Zie [Machtigingen in de Microsoft 365 Defender](permissions-in-the-security-and-compliance-center.md))

- U moet toegang hebben tot [Explorer (of realtimedetecties).](threat-explorer.md)

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>Microsoft Defender voor Office 365 integreren met Microsoft Defender voor Eindpunt

De integratie van Microsoft Defender voor Office 365 met Microsoft Defender voor Eindpunt is ingesteld in zowel Defender voor Eindpunt als Defender voor Office 365.

1. Als globale beheerder of beveiligingsbeheerder gaat u naar [https://security.microsoft.com](https://security.microsoft.com) en meld u aan. (Hiermee gaat u naar de Microsoft 365 Defender portal.)

2. Kies in het navigatiedeelvenster **E-mail & Samenwerkingsverkenner** \> .

3. Klik in de rechterbovenhoek van het scherm op **MDE-Instellingen.**

4. Schakel in het dialoogvenster Verbinding met Microsoft Defender voor eindpunt de Verbinding maken **microsoft Defender voor eindpunt in.**

    :::image type="content" source="../../media/explorer-mdeconnection-dialognew.png" alt-text="MDE-verbinding":::

5. Ga naar de Microsoft 365 Defender portal ( [https://security.microsoft.com](https://security.microsoft.com) .

6. Kies in de navigatiebalk **Instellingen.** Kies vervolgens onder **Algemeen** de optie **Geavanceerde functies.**

7. Schuif omlaag naar **Office 365 Threat Intelligence-verbinding** en schakel de verbinding in.

   ![Office 365 threat intelligence-verbinding](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a>Verwante artikelen

[Mogelijkheden voor het onderzoeken en reageren van bedreigingen in Office 365](office-365-ti.md)

[Microsoft Defender voor Office 365](defender-for-office-365.md)

[Microsoft Defender voor Eindpunt](/windows/security/threat-protection)
