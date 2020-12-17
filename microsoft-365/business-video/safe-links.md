---
title: Veilige koppelingen beheren
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
description: Meer informatie over het beheren van veilige koppelingen om uw bedrijf te beschermen tegen kwaadwillende sites.
ms.openlocfilehash: eabb2c1f71b1183867ffcb005ba4f7e44ed6e4b7
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702068"
---
# <a name="manage-safe-links"></a>Veilige koppelingen beheren

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

Microsoft Defender voor Office 365, voorheen Microsoft 365 ATP of Advanced Threat Protection, helpt uw bedrijf te beschermen tegen kwaadaardige sites wanneer mensen klikken op koppelingen in Office-apps.

## <a name="try-it"></a>Probeer het zelf!

1. Ga naar het [Beheercentrum](https://admin.microsoft.com)en selecteer **Setup**.
1. Schuif omlaag om de **bescherming tegen geavanceerde bedreigingen te verbeteren**. Selecteer **weergeven**, **beheren** en vervolgens **veilige verbindingen voor ATP**.
1. Kies onder **beleidsregels die van toepassing zijn op de hele organisatie** het **standaard** beleid en selecteer vervolgens het pictogram **bewerken** .
1. Voer de URL in die u wilt blokkeren.
1. Selecteer **veilige koppelingen gebruiken in Office-apps, Office voor IOS en Android**. Selecteer **niet bijhouden wanneer gebruikers op veilige koppelingen klikken**. en selecteer **gebruikers niet laten klikken via veilige koppelingen naar de oorspronkelijke URL**. Dit kan al zijn geselecteerd als u het standaardbeleid instelt. Selecteer **Opslaan**.
1. Kies onder **beleidsregels die van toepassing zijn op specifieke geadresseerden** de optie **Aanbevolen regel voor veilige koppelingen** en selecteer vervolgens het pictogram **bewerken** .
1. Selecteer **instellingen**, Blader omlaag, voer de URL in die u niet wilt controleren en selecteer het pictogram **toevoegen** .
1. Selecteer **toegepast op** en selecteer vervolgens uw domeinnaam. Selecteer de extra domeinen waarop u de regel wilt toepassen. Selecteer **toevoegen**, **OK** en vervolgens **Opslaan**.

Veilige koppelingen voor ATP zijn nu geconfigureerd. U kunt maximaal 30 minuten wachten tot de wijzigingen van kracht worden.

Wanneer een gebruiker een e-mailbericht met koppelingen ontvangt, worden de koppelingen gescand. Als de koppelingen veilig worden beschouwd, kunnen ze klikken. Wanneer de koppeling in de lijst met geblokkeerde gebruikers staat, ziet u echter een bericht dat is geblokkeerd.