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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: 'Ga naar de stapsgewijze instructies voor het overzetten van een domein van Microsoft naar een andere bewaarder. '
ms.openlocfilehash: 1fb1fa50bd919bddb620a39d9edb46abb6710ba4
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645273"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a>Een domein van Microsoft overbrengen naar een andere host

U kunt een Microsoft 365-domein na de aankoop van Microsoft niet overzetten naar een andere bewaarder van de 60 dagen nadat u het domein hebt aangeschaft.

> [!NOTE]
> Met een _whois_-   query wordt een Microsoft aangeschafte Microsoft-domeinregistratie weergegeven als wilde westelijke domeinen LLC. U moet echter alleen Microsoft contact opnemen met de aangeschafte Microsoft 365-domein.

Ga als volgt te werk om een code te vinden bij Microsoft 365 en ga vervolgens naar de andere website van het domein registratief om uw domeinnaam in te stellen voor de nieuwe bewaarder.

## <a name="transfer-a-domain"></a>Een domein overbrengen

1. Ga in het Beheercentrum naar  **instellingen**   >  **domeinen**.

2. Selecteer op de pagina **Domains** het microsoft 365-domein dat u wilt overzetten naar een andere domeinregistratie, en selecteer vervolgens **status controleren**.

3. Selecteer boven aan de pagina de optie **domein overbrengen**.

4. Selecteer op de pagina **Kies waar u uw domein wilt overzetten** **een andere registratieservice**en klik op **volgende**.

5. Selecteer op de pagina **domein overdracht ontgrendelen** de optie **overdracht ontgrendelen voor <_uw domein_ > **en selecteer **volgende**.

6. Controleer de contactgegevens van uw domein overdracht en selecteer **volgende**.

7. Kopieer de autorisatiecode en wacht ongeveer 30 minuten voordat u de status van uw domein overzetten wilt wijzigen in **ontgrendeld voor overdracht** op het tabblad **registreren** voordat u verder gaat met de volgende stappen.

8. Ga naar de website van het domein registratieprogramma waarop u uw domeinnaam verder wilt beheren. Volg de aanwijzingen voor het overdragen van een domein (Zoek de Help op hun website). Dit betekent meestal dat u overschrijvings kosten betaalt en de Authcode naar de nieuwe registratieservice draagt, zodat ze de overdracht kunnen initiëren. Microsoft verstuurt u een e-mailbericht om te bevestigen dat u de overdrachtsaanvraag hebt ontvangen en dat het domein binnen 5 dagen zal overzetten.

    U vindt het tabblad autorisatiecode **registreren** op de pagina  **domeinen** in Microsoft 365.
    
    > [!TIP]
    > voor UK-domeinen is een andere procedure vereist. Neem contact op met Microsoft ondersteuning en vraag een IP-adres van een **IPS-wijziging** aan de bewaarder van uw domein dat u wilt beheren. Wanneer het label is gewijzigd, wordt het domein direct overgebracht naar de nieuwe bewaarder. U moet vervolgens met de nieuwe bewaarder samenwerken om de overdracht te voltooien, waarschijnlijk kosten in rekening te brengen en het overgedragen domein toe te voegen aan uw account met uw nieuwe bewaarder.

9. Na het overzetten verlengt u uw domein bij de nieuwe domeinregistratie.

10. Om het proces te voltooien, gaat u terug naar de pagina **domeinen** in het Beheercentrum en selecteert u vervolgens  **domein overdracht voltooien**. Hiermee wordt het domein gemarkeerd als niet langer aangeschaft bij Microsoft 365 en wordt het domein abonnement uitgeschakeld. Het domein wordt niet van de Tenant verwijderd en heeft geen invloed op bestaande gebruikers en postvakken op het domein.

> [!NOTE]
> Aangeschafte domeinen van Microsoft 365 komen niet in aanmerking voornaam server wijzigingen of het overbrengen van het domein tussen Microsoft 365-organisaties. Als een van deze twee is vereist, moet u de domeinregistratie overzetten naar een andere bewaarder.
