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
description: 'Hier vindt u de stappen om een domein over te dragen van Microsoft naar een andere registrar. '
ms.openlocfilehash: f34e9733ab53c8bdc6f4432c96e6232ecc26ee06
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126345"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a>Een domein van Microsoft overbrengen naar een andere host

U kunt een domein Microsoft 365 60 dagen nadat u het domein bij Microsoft hebt gekocht, niet naar een andere registrar overbrengen.

> [!NOTE]
> Een _Whois-query_   toont een door Microsoft gekochte domeinregistrar als Wild West Domains LLC. Er mag echter alleen contact worden opgenomen met Microsoft met betrekking tot Microsoft 365 gekochte domein.

Volg deze stappen om een code bij Microsoft 365 te krijgen en ga vervolgens naar de andere website van de domeinregistrar om de overdracht van uw domeinnaam naar de nieuwe registrar in te stellen.

## <a name="transfer-a-domain"></a>Een domein overdragen

1. Ga in het beheercentrum naar   **Instellingen**   >  **Domeinen.**

2. Selecteer op **de pagina** Domeinen het Microsoft 365 domein dat u wilt overbrengen naar een andere domeinregistrar en selecteer vervolgens **Status controleren.**

3. Selecteer boven aan de pagina **Transfer domain.**

4. Selecteer op **de pagina Kiezen waar u uw domein wilt** overbrengen de optie Een andere **registrar** en klik vervolgens op **Volgende.**

5. Selecteer op **de pagina Domeinoverdracht** ontgrendelen de optie **Overdracht ontgrendelen voor < >** domein en selecteer **vervolgens Volgende**.

6. Controleer de contactgegevens van uw domeinoverdracht en selecteer **volgende**.

7. Kopieer de autorisatiecode en wacht ongeveer 30 minuten totdat de  status van uw domeinoverdracht is gewijzigd in **Ontgrendeld** voor overdracht op het tabblad Registratie voordat u verder gaat met de volgende stappen.

8. Ga naar de website van de domeinregistrar die u in de toekomst wilt beheren. Volg aanwijzingen voor het overbrengen van een domein (zoek hulp op hun website). Dit betekent meestal het betalen van overdrachtskosten en het geven van de Authcode aan de nieuwe registrar, zodat ze de overdracht kunnen starten. Microsoft e-mailt u om te bevestigen dat we de overdrachtsaanvraag hebben ontvangen en het domein wordt binnen 5 dagen overdraagd.

    U vindt het tabblad **Autorisatiecode Registratie** op  **de pagina** Domeinen in Microsoft 365.
    
    > [!TIP]
    > Voor .uk-domeinen is een andere procedure vereist. Neem contact op met Microsoft Support en vraag een **IPS-tagwijziging** aan die past bij de registrar die u in de toekomst uw domein wilt beheren. Nadat de tag is gewijzigd, wordt het domein onmiddellijk overboekt naar de nieuwe registrar. Vervolgens moet u samenwerken met de nieuwe registrar om de overdracht te voltooien, waarschijnlijk om overdrachtskosten te betalen en het overgedragen domein toe te voegen aan uw account met uw nieuwe registrar.

9. Nadat de overdracht is voltooid, verlengt u uw domein bij de nieuwe domeinregistrar.

10. Als u het proces wilt voltooien, gaat u terug naar **de pagina** Domeinen in het beheercentrum en selecteert u   **Domeinoverdracht voltooien.** Hiermee wordt het domein als niet meer gekocht bij Microsoft 365 en wordt het domeinabonnement uitgeschakeld. Het domein wordt niet verwijderd uit de tenant en heeft geen invloed op bestaande gebruikers en postvakken in het domein.

> [!NOTE]
> Microsoft 365 gekochte domeinen komen niet in aanmerking voor naamserverwijzigingen of het overbrengen van het domein tussen Microsoft 365 organisaties. Als een van deze gegevens vereist is, moet de domeinregistratie worden overgedragen aan een andere registrar.
