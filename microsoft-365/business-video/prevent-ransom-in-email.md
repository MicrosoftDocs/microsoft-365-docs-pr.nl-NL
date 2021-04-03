---
title: E-mailregels maken om ransomware te voorkomen
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: Meer informatie over het maken van e-mailregels om ransomware te voorkomen.
ms.openlocfilehash: 96822916753f2f70d481c213e7e31046f7081446
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580496"
---
# <a name="create-email-rules-to-prevent-ransomware"></a>E-mailregels maken om ransomware te voorkomen

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

Microsoft 365 helpt uw bedrijf te beschermen tegen ransomware door te voorkomen dat potentieel gevaarlijke bestanden, zoals JavaScript, batch en uitvoerbare bestanden, worden geopend in Outlook. Als u dit beschermingsniveau wilt verhogen door regels toe te voegen die u blokkeren of waarschuwen voor extra typen bestanden, volgt u deze stappen.

## <a name="try-it"></a>Probeer het zelf!

1. Kies exchange in het beheercentrum [https://admin.microsoft.com](https://admin.microsoft.com) bij **, onder** **Beheercentra.**
1. Kies e-mailstroom in het menu aan **de linkerkant.**
1. Kies op het tabblad Regels de pijl naast het plusteken (+) en kies **vervolgens Een nieuwe regel maken.**
1. Voer op **de nieuwe regelpagina** een naam voor de regel in, schuif naar de onderkant en kies **meer opties.**
1. Selecteer **onder Deze regel toepassen als**, selecteer Elke **bijlage** en selecteer **vervolgens bestandsextensie bevat deze woorden.**
1. Voer in het vak onder woorden of woordgroepen de bestandsextensies in die u wilt toepassen op de regel, zoals **bestandsextensies** die macro's kunnen bevatten. Gebruik het plusteken (+) om ze een voor een toe te voegen.

    Lees Beschermen tegen ransomware voor meer informatie over [bestandstypen.](../admin/security-and-compliance/secure-your-business-data.md#ransomware)

1. Schuif omlaag om de lijst te bekijken en kies **OK.**
1. Kies op **de pagina** Nieuwe regel de optie **Voorwaarde toevoegen** en kies vervolgens een voorwaarde onder Ga als volgt **te werk.**
1. U hebt een groot aantal regelopties om uit te kiezen, maar in dit voorbeeld kiezen we ervoor om de geadresseerde op de hoogte te stellen **met een bericht.**
1. Voer berichttekst in voor uw melding en kies **OK.**
1. Optioneel: Kies op de  **nieuwe regelpagina** uitzondering toevoegen en voer alle details in voor uitzonderingen op de regel, zoals berichten van vertrouwde afzenders.
1. Kies op de nieuwe regelpagina **Opslaan** en bekijk de overzichtsgegevens van de regel.