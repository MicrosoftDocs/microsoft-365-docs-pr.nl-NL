---
title: E-mail regels voor Ransomware maken
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
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
description: Lees hoe u e-mail regels maakt om Ransomware te voorkomen.
ms.openlocfilehash: 85898480438225848fc09db9a9c507045f8a182c
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701675"
---
# <a name="create-email-rules-to-prevent-ransomware"></a>E-mail regels maken om Ransomware te voorkomen

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

Microsoft 365 helpt uw bedrijf te beschermen tegen Ransomware door potentieel gevaarlijke bestanden, zoals JavaScript, batch en uitvoerbare bestanden, te voorkomen te openen in Outlook. Ga als volgt te werk om de beveiliging van dit niveau te verhogen door regels toe te voegen die u voor andere typen bestanden blokkeren of waarschuwen.

## <a name="try-it"></a>Probeer het zelf!

1. Kies in het Beheercentrum op [https://admin.microsoft.com](https://admin.microsoft.com) **Exchange** onder **beheer centra**.
1. Kies in het menu aan de linkerkant de optie **e-mail stroom**.
1. Ga naar het tabblad regels, kies de pijl naast het plusteken (+) en kies vervolgens **een nieuwe regel maken**.
1. Voer op de pagina **nieuwe regel** een naam voor de regel in, schuif naar beneden en kies **meer opties**.
1. Selecteer een bijlage onder **deze regel toepassen als** u **een bijlage** selecteert en selecteer vervolgens **bestandsextensie bevat deze woorden**.
1. Voer in het vak onder **woorden of zinnen opgeven** de bestandsextensies in waarop de regel moet worden toegepast, zoals bestandsextensies die macro's kunnen bevatten. Gebruik het plusteken (+) om ze een voor een toe te voegen.

    Meer informatie over bestandstypen vindt u in [beveiliging tegen Ransomware](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware).

1. Schuif omlaag naar de lijst en kies vervolgens **OK**.
1. Kies op de pagina **nieuwe regel** de optie **voorwaarde toevoegen** en kies vervolgens een voorwaarde onder **Ga als volgt** te werk.
1. U kunt kiezen uit een groot aantal opties voor de regel, maar in dit voorbeeld zullen we kiezen **de geadresseerde op de hoogte te stellen van een bericht**.
1. Voer de berichttekst voor uw melding in en kies vervolgens **OK**.
1. Optioneel: Kies **uitzondering toevoegen** op de pagina **nieuwe regel** en voer de gegevens voor uitzonderingen voor de regel in, zoals berichten van vertrouwde afzenders.
1. Kies op de pagina nieuwe regel de optie **Opslaan** en Bekijk de informatie over de regel samenvatting.