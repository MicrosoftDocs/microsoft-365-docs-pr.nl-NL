---
title: Microsoft Defender gebruiken voor Office 365 samen met Microsoft Defender voor Eindpunt
f1.keywords:
- NOCSH
keywords: integreren, Microsoft Defender, Microsoft Defender voor Eindpunt
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
description: Gebruik Microsoft Defender voor Office 365 samen met Microsoft Defender voor Eindpunt voor meer gedetailleerde informatie over bedreigingen tegen uw apparaten en e-mailinhoud.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e6ad81102a9702a725f40fcdb5421a2b19b0086d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934031"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>Microsoft Defender gebruiken voor Office 365 samen met Microsoft Defender voor Eindpunt

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender voor Office 365](defender-for-office-365.md) kan worden geconfigureerd voor gebruik met [Microsoft Defender voor Eindpunt.](/windows/security/threat-protection)

Als u Microsoft Defender voor Office 365 met Microsoft Defender voor Eindpunt integreert, kan uw beveiligingsteam uw beveiligingsactiviteiten helpen bij het controleren en snel actie ondernemen als de apparaten van gebruikers in gevaar zijn. Wanneer integratie bijvoorbeeld is ingeschakeld, kan uw beveiligingsteam de apparaten zien die mogelijk worden beïnvloed door een gedetecteerd e-mailbericht en hoeveel recente waarschuwingen er zijn gegenereerd voor die apparaten in Microsoft Defender voor Eindpunt.

In de volgende afbeelding ziet u hoe het tabblad **Apparaten** eruitziet wanneer Microsoft Defender voor endpoint-integratie is ingeschakeld:

![Wanneer Microsoft Defender voor Eindpunt is ingeschakeld, ziet u een lijst met apparaten met waarschuwingen.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

In dit voorbeeld kunt u zien dat de geadresseerden van het gedetecteerde e-mailbericht vier apparaten hebben en één een waarschuwing heeft. Als u op de koppeling voor een apparaat klikt, wordt de pagina geopend in de Microsoft Defender-beveiligingscentrum ( <https://securitycenter.windows.com> ).

> [!TIP]
> **[Meer informatie over de Microsoft Defender-beveiligingscentrum](/windows/security/threat-protection/microsoft-defender-atp/use)** (ook wel de Microsoft Defender for Endpoint-portal genoemd.)

## <a name="requirements"></a>Vereisten

- Uw organisatie moet Microsoft Defender hebben voor Office 365 (of Office 365 E5) en Microsoft Defender voor Eindpunt.

- U moet een globale beheerder zijn of een beveiligingsbeheerderrol (zoals beveiligingsbeheerder) hebben toegewezen in het Beveiligings- [& Compliancecentrum.](https://protection.office.com) (Zie [Machtigingen in het beveiligings- & Compliancecentrum](permissions-in-the-security-and-compliance-center.md))

- U moet toegang hebben tot [Zowel Explorer (of realtime detecties)](threat-explorer.md) in het Beveiligings- & compliancecentrum als de Microsoft Defender-beveiligingscentrum.

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>Microsoft Defender voor Office 365 integreren met Microsoft Defender voor Eindpunt

De integratie van Microsoft Defender voor Office 365 met Microsoft Defender voor Eindpunt wordt ingesteld met behulp van zowel het Beveiligings- & Compliancecentrum als de Microsoft Defender-beveiligingscentrum.

1. Als globale beheerder of beveiligingsbeheerder gaat u naar <https://protection.office.com> en meld u aan. (Hiermee gaat u naar het Office 365 beveiligings- & compliancecentrum.)

2. Kies in het navigatiedeelvenster **Bedreigingsbeheer** \> **Explorer.**

   ![Explorer in het menu Bedreigingsbeheer](../../media/ThreatMgmt-Explorer-nav.png)

3. Kies in de rechterbovenhoek van het scherm **De optie Defender voor eindpunten Instellingen (MDE Instellingen)**.

4. Schakel in het dialoogvenster Verbinding met Microsoft Defender voor eindpunt de Verbinding maken **microsoft Defender voor eindpunt in.**

   ![Verbinding met Microsoft Defender voor eindpunt](../../media/Explorer-WDATPConnection-dialog.png)

5. Ga naar de Microsoft Defender-beveiligingscentrum ( <https://securitycenter.windows.com> ).

6. Kies in de navigatiebalk **Instellingen.** Kies vervolgens onder **Algemeen** de optie **Geavanceerde functies.**

7. Schuif omlaag naar **Office 365 Threat Intelligence-verbinding** en schakel de verbinding in.

   ![Office 365 threat intelligence-verbinding](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a>Aanverwante artikelen

[Mogelijkheden voor het onderzoeken en reageren van bedreigingen in Office 365](office-365-ti.md)

[Microsoft Defender voor Office 365](defender-for-office-365.md)

[Microsoft Defender voor Eindpunt](/windows/security/threat-protection)