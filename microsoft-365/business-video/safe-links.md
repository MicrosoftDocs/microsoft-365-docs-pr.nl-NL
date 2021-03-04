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
description: Lees hoe u veilige koppelingen beheert om uw bedrijf te beschermen tegen schadelijke sites.
ms.openlocfilehash: 0f0cc6845f699ba5b05c30e21f876f4b4d47b6a6
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/04/2021
ms.locfileid: "50422241"
---
# <a name="manage-safe-links"></a>Veilige koppelingen beheren

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

Microsoft Defender voor Office 365, voorheen Microsoft 365 ATP of Advanced Threat Protection genoemd, helpt uw bedrijf te beschermen tegen schadelijke sites wanneer personen op koppelingen in Office-apps klikken.

## <a name="try-it"></a>Probeer het zelf!

1. Ga naar het [beheercentrum](https://admin.microsoft.com)en selecteer **Setup.**
1. Schuif omlaag naar **Beveiliging tegen geavanceerde bedreigingen vergroten.** Selecteer **Weergeven,** **Beheren** en vervolgens **Veilige koppelingen met ATP.**
1. Kies onder Beleid dat van toepassing  is **op** de hele organisatie het standaardbeleid en selecteer vervolgens het **pictogram** Bewerken.
1. Voer een URL in die u wilt blokkeren.
1. Selecteer **Veilige koppelingen gebruiken in Office-apps, Office voor iOS en Android.** selecteer **Niet bijhouden wanneer gebruikers op veilige koppelingen klikken;** en selecteer **Niet door gebruikers laten klikken door veilige koppelingen naar de oorspronkelijke URL.** Deze zijn mogelijk al geselecteerd als u het standaardbeleid in stelt. Kies **Opslaan**.
1. Kies **onder Beleid dat van toepassing** is op specifieke geadresseerden de optie **Regel** aanbevolen veilige koppelingen en selecteer vervolgens het **pictogram** Bewerken.
1. Selecteer **instellingen,** schuif omlaag, voer de URL in die u niet wilt controleren en selecteer vervolgens het **pictogram** Toevoegen.
1. Selecteer **toegepast op** en selecteer vervolgens uw domeinnaam. Selecteer eventuele extra domeinen op wie u de regel wilt toepassen. Selecteer **Toevoegen,** **OK** en vervolgens **Opslaan.**

Veilige koppelingen met ATP zijn nu geconfigureerd. Het kan 30 minuten duren voordat de wijzigingen van kracht worden.

Wanneer een gebruiker een e-mailbericht met koppelingen ontvangt, worden de koppelingen gescand. Als de koppelingen veilig worden beschouwd, kan erop worden geklikt. Als de koppeling echter op de lijst met geblokkeerde berichten staat, zien gebruikers een bericht dat de koppeling is geblokkeerd.