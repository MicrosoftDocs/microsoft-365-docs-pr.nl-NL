---
title: E-mailregels maken om ransomware te voorkomen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Informatie over het maken van e-mailregels om ransomware te voorkomen.
ms.openlocfilehash: 0d8b4a9de881f47752ac0bfbf778453d6ee73046
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/04/2021
ms.locfileid: "50422251"
---
# <a name="create-email-rules-to-prevent-ransomware"></a>E-mailregels maken om ransomware te voorkomen

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

Microsoft 365 helpt uw bedrijf te beschermen tegen ransomware door te voorkomen dat potentieel gevaarlijke bestanden, zoals JavaScript-, batch- en uitvoerbare bestanden, in Outlook worden geopend. Als u dit beschermingsniveau wilt verhogen door regels toe te voegen die u voor extra typen bestanden blokkeren of waarschuwen, volgt u deze stappen.

## <a name="try-it"></a>Probeer het zelf!

1. Kies in het beheercentrum [https://admin.microsoft.com](https://admin.microsoft.com) de optie **Exchange** onder **Beheercentra.**
1. Kies e-mailstroom in **het menu aan de linkerkant.**
1. Kies op het tabblad Regels de pijl naast het plusteken (+) en kies **vervolgens Een nieuwe regel maken.**
1. Voer op **de nieuwe regelpagina** een naam in voor de regel, schuif omlaag en kies **Meer opties.**
1. Selecteer **onder Deze regel toepassen een** bijlage **en** selecteer vervolgens **de bestandsextensie die deze woorden bevat.**
1. Typ in het vak onder Typ woorden of woordgroepen de bestandsextensies die u wilt toepassen op de regel, zoals **bestandsextensies** die macro's kunnen bevatten. Gebruik het plusteken (+) om ze een voor een toe te voegen.

    Meer informatie over bestandstypen kunt u lezen door [Beveiligen tegen ransomware te lezen.](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware)

1. Schuif omlaag om de lijst te controleren en kies **OK.**
1. Kies op **de pagina** Nieuwe regel de optie **Voorwaarde toevoegen** en kies vervolgens een voorwaarde onder Ga als volgt **te werk.**
1. U kunt uit veel regelopties kiezen, maar in dit voorbeeld kiezen we de geadresseerde op de hoogte te stellen **met een bericht.**
1. Voer de berichttekst voor de melding in en kies **ok.**
1. Optioneel: Kies op de  **nieuwe** regelpagina uitzondering toevoegen en voer eventuele details in voor uitzonderingen op de regel, zoals berichten van vertrouwde afzenders.
1. Kies Opslaan op de nieuwe regelpagina **en** bekijk de informatie over het overzicht van de regels.