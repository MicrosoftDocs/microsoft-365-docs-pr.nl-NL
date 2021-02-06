---
title: Een domein van Microsoft overbrengen naar een andere host
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: 'In dit artikel vindt u de stappen voor het overbrengen van een domein van Microsoft naar een andere registrar. '
ms.openlocfilehash: f34e9733ab53c8bdc6f4432c96e6232ecc26ee06
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126345"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a>Een domein van Microsoft overbrengen naar een andere host

U kunt een Microsoft 365-domein niet 60 dagen na de aankoop van het domein bij Microsoft overbrengen naar een andere registrar.

> [!NOTE]
> Een _Whois-query_   toont een door Microsoft gekochte domeinregistrar als Wild West Domains LLC. U hoeft echter alleen contact op te nemen met Microsoft met betrekking tot uw door Microsoft 365 aangeschafte domein.

Volg deze stappen om een code op te vragen bij Microsoft 365 en ga naar de website van de andere domeinregistrar om het overzetten van uw domeinnaam naar de nieuwe registrar in te stellen.

## <a name="transfer-a-domain"></a>Een domein overbrengen

1. Ga in het beheercentrum naar   **Settings**   >  **Domains.**

2. Selecteer op **de pagina** Domeinen het Microsoft 365-domein dat u wilt overbrengen naar een andere domeinregistrar en selecteer vervolgens **Status controleren.**

3. Selecteer domein overstappen boven aan **de pagina.**

4. Selecteer een andere **registrar** **op de pagina** Kies waar u uw domein wilt over dragen en klik op **Volgende.**

5. Selecteer op **de pagina Domein overboeking** **>** ontgrendelen de optie <domein ontgrendelen en selecteer vervolgens **Volgende.**

6. Controleer de contactgegevens van uw domeinoverdracht en selecteer vervolgens **Volgende.**

7. Kopieer de autorisatiecode en wacht ongeveer 30 minuten totdat de  status van uw domeinoverdracht is gewijzigd in **Ontgrendeld** voor overdracht op het tabblad Registratie voordat u verder gaat met de volgende stappen.

8. Ga naar de website van de domeinregistrar die uw domeinnaam in de toekomst wilt beheren. Volg de aanwijzingen voor het overzetten van een domein (zoek naar hulp op de website van het domein). Dit houdt meestal in dat u betaalt voor de overboekingskosten en dat u de authcode aan de nieuwe registrar geeft zodat deze de overdracht kan starten. Microsoft zal u een e-mail sturen om te bevestigen dat we de overboekingsaanvraag hebben ontvangen en het domein wordt binnen 5 dagen over overdragen.

    U vindt het tabblad Registratie van **autorisatiecode**  **op de pagina** Domeinen in Microsoft 365.
    
    > [!TIP]
    > Voor .uk-domeinen is een andere procedure vereist. Neem contact op met Microsoft Ondersteuning en vraag om een wijziging van de **IPS-label** voor de registrar die uw domein in de toekomst wilt beheren. Wanneer de tag is gewijzigd, wordt het domein onmiddellijk over verplaatst naar de nieuwe registrar. Vervolgens moet u samenwerken met de nieuwe registrar om de overdracht te voltooien. U betaalt waarschijnlijk kosten voor de overdracht en voegt het overgedragen domein toe aan uw account bij uw nieuwe registrar.

9. Nadat de overdracht is voltooid, verlengt u uw domein bij de nieuwe domeinregistrar.

10. Om het proces te voltooien, gaat u terug naar **de pagina** Domeinen in het beheercentrum en selecteert u   **Vervolgens Volledige domeinoverdracht.** Hiermee wordt het domein markeren als niet meer aangeschaft bij Microsoft 365 en wordt het domeinabonnement uitgeschakeld. Het domein wordt niet uit de tenant verwijderd en is niet van invloed op bestaande gebruikers en postvakken in het domein.

> [!NOTE]
> Door Microsoft 365 aangeschafte domeinen komen niet in aanmerking voor naamserverwijzigingen of het overzetten van het domein tussen Microsoft 365-organisaties. Als een van deze vereist is, moet de domeinregistratie worden overgebracht naar een andere registrar.
