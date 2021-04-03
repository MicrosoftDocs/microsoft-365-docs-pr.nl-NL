---
title: Veilige koppelingen beheren
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
description: Meer informatie over het beheren van veilige koppelingen om uw bedrijf te beschermen tegen schadelijke sites.
ms.openlocfilehash: ce0c1ba6e4099b6eaf4ec974938170020b8a5892
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580628"
---
# <a name="manage-safe-links"></a>Veilige koppelingen beheren

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

Microsoft Defender voor Office 365 , voorheen Microsoft 365 ATP of Advanced Threat Protection genoemd, helpt uw bedrijf te beschermen tegen schadelijke sites wanneer mensen op koppelingen in Office-apps klikken.

## <a name="try-it"></a>Probeer het zelf!

1. Ga naar het [beheercentrum](https://admin.microsoft.com)en selecteer **Setup.**
1. Schuif omlaag om **de beveiliging tegen geavanceerde bedreigingen te vergroten.** Selecteer **Beeld,** **Beheren** en vervolgens **ATP Safe Koppelingen.**
1. Kies **onder Beleidsregels die van toepassing zijn op** de hele organisatie het standaardbeleid en selecteer vervolgens het **pictogram** Bewerken. 
1. Voer een URL in die u wilt blokkeren.
1. Selecteer **Veilige koppelingen gebruiken in Office-apps, Office voor iOS en Android;** selecteer **Niet bijhouden wanneer gebruikers op veilige koppelingen klikken.** en selecteer Gebruikers niet door veilige koppelingen **naar de oorspronkelijke URL laten klikken.** Deze zijn mogelijk al geselecteerd als u het standaardbeleid hebt ingesteld. Kies **Opslaan**.
1. Kies **onder Beleidsregels die van toepassing zijn op** specifieke geadresseerden de optie Aanbevolen regel voor veilige **koppelingen** en selecteer vervolgens het **pictogram** Bewerken.
1. Selecteer **instellingen,** schuif omlaag, voer de URL in die u niet wilt controleren en selecteer vervolgens het **pictogram** Toevoegen.
1. Selecteer **toegepast op** en selecteer vervolgens uw domeinnaam. Selecteer eventuele extra domeinen op wie u de regel wilt toepassen. Selecteer **Toevoegen**, **OK** en vervolgens **Opslaan**.

ATP-veilige koppelingen zijn nu geconfigureerd. Laat uw wijzigingen maximaal 30 minuten van kracht worden.

Wanneer een gebruiker een e-mailbericht met koppelingen ontvangt, worden de koppelingen gescand. Als de koppelingen veilig worden geacht, kunnen ze worden geklikt. Als de koppeling echter in de geblokkeerde lijst staat, zien gebruikers een bericht dat de koppeling is geblokkeerd.