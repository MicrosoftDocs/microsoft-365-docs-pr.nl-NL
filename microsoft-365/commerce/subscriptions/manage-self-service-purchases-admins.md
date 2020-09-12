---
title: Selfservice aankopen beheren (beheerders)
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Beheerders kunnen informatie lezen over het beheren van selfservice aankopen van gebruikers in hun organisatie.
ms.openlocfilehash: ca25bf0c3e3539196e81dcc289592028cc4dfa47
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546672"
---
# <a name="manage-self-service-purchases-admin"></a>Selfservice-aankopen beheren (Beheerders)

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Als beheerder kunt u zelf aankopen van personen in uw organisatie bekijken. U ziet de productnaam, de naam van de aankoop, de aangeschafte abonnementen, de vervaldatum, de aankoopprijs en de toegewezen gebruikers voor elke selfservice aankoop. Als dit nodig is voor uw organisatie, kunt u selfservice aankopen per product basis uitschakelen via PowerShell. U hebt dezelfde beleidsregels voor gegevensbeheer en toegang via producten die zijn gekocht via selfservice aankoop of centraal.

U kunt ook bepalen of gebruikers in uw organisatie selfservice aankopen kunnen verrichten. Zie voor meer informatie [AllowSelfServicePurchase gebruiken voor de MSCommerce PowerShell-module](allowselfservicepurchase-powershell.md).

## <a name="view-self-service-subscriptions"></a>Selfservice abonnementen weergeven

1. Ga in het Beheercentrum naar de pagina **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">uw producten</a> factureren.
2. Selecteer op het tabblad **Products** het pictogram filter en selecteer vervolgens **selfservice**.
3. Als u meer informatie over een abonnement wilt bekijken, kiest u een abonnement in de lijst.

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a>Weergeven wie licenties heeft voor een self-service Purchase-abonnement

1. Ga in het Beheercentrum naar de pagina **factuur**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenties</a> .
2. Selecteer het filterpictogram en kies vervolgens **self-service**.
3. Selecteer een product om licenties te zien die zijn toegewezen aan personen.
    > [!NOTE]
    > Als er meerdere aankopen voor een product zijn, wordt dat product slechts eenmaal vermeld en wordt in de kolom **beschikbare hoeveelheid** de som van alle abonnementen die voor dat product zijn gekocht weergegeven.
4. De lijst **gebruikers** wordt gegroepeerd op de namen van personen die selfservice aankopen hebben gedaan.
5. Als u een lijst wilt exporteren met gebruikers met een licentie voor deze abonnementen, kiest u de abonnementen die u wilt exporteren en vervolgens kiest u **gebruikers exporteren**.

## <a name="disable-or-enable-self-service-purchases"></a>Service voor selfservice aankopen in-of uitschakelen

U kunt selfservice aankopen van gebruikers in uw organisatie uitschakelen of inschakelen. De **MSCommerce** PowerShell-module bevat een **PolicyID** -parameterwaarde voor **AllowSelfServicePurchase** waarmee u kunt bepalen of gebruikers in uw organisatie selfservice aankopen kunnen voeren en voor welke producten.

U kunt de **MSCommerce** PowerShell-module gebruiken voor het volgende:

- De standaardstatus van de parameterwaarde van **AllowSelfServicePurchase** weergeven, ongeacht of deze is ingeschakeld of uitgeschakeld voor de productversie
- Een lijst met beschikbare producten weergeven en of selfservice aankoop is in-of uitgeschakeld
- De huidige instelling voor een specifiek product weergeven of wijzigen om dit in of uit te schakelen

Zie voor meer informatie [AllowSelfServicePurchase gebruiken voor de MSCommerce PowerShell-module](allowselfservicepurchase-powershell.md).

## <a name="centralize-licenses-under-a-single-subscription"></a>Licenties centraliseren onder één abonnement

U kunt bestaande licenties toewijzen of extra abonnementen kopen via bestaande overeenkomsten voor gebruikers die zijn toegewezen aan selfservice aankopen. Nadat u deze met een centraal aangeschafte licenties hebt toegewezen, kunt u vragen of kopers hun bestaande abonnementen annuleren.

1. Ga **in het Beheercentrum naar de** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Services voor aankopen van aankopen</a> .
2. Zoek en selecteer het product dat u wilt kopen en kies vervolgens **kopen**.
3. Voer de resterende stappen uit om uw aankoop te voltooien.
4. Volg de stappen in [weergave met licenties voor een zelf gekocht abonnement](#view-who-has-licenses-for-a-self-service-purchase-subscription) voor het exporteren van een lijst met gebruikers waarnaar wordt verwezen in de volgende stap.
5. Wijs licenties toe aan iedereen die een licentie heeft in het andere abonnement. Zie [licenties toewijzen aan gebruikers](../../admin/manage/assign-licenses-to-users.md)voor de volledige stappen.
6. Neem contact op met de persoon die het self-service Purchase-abonnement heeft gekocht en vraag of ze het zelf willen [opzeggen](manage-self-service-purchases-users.md#cancel-a-subscription).

## <a name="take-over-a-self-service-purchase-subscription"></a>Een self-service Purchase-abonnement nemen

U kunt een self-service Purchase-abonnement nemen die door een gebruiker in uw organisatie is gemaakt. Wanneer u een self-service Purchase-abonnement overneemt, hebt u twee opties:

1. Verplaats de gebruikers naar een ander abonnement en Annuleer het oorspronkelijke abonnement.
2. Het selfservice aankoop abonnement annuleren en licenties van toegewezen gebruikers verwijderen.

### <a name="move-users-to-a-different-subscription"></a>Gebruikers naar een ander abonnement overzetten

Wanneer u gebruikers naar een ander abonnement verplaatst, wordt het oude abonnement automatisch geannuleerd. De gebruiker die het selfservice aankoop abonnement oorspronkelijk heeft gekocht, ontvangt een e-mail met de mededeling dat het abonnement is geannuleerd.

> [!NOTE]
> U moet een beschikbare licentie hebben voor elke gebruiker die u overgaat in het abonnement waarnaar u gebruikers verplaatst.

1. Ga in het Beheercentrum naar de pagina **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">uw producten</a> factureren.
2. Selecteer op het tabblad **Products** het pictogram filter en selecteer vervolgens **selfservice**.
3. Selecteer het abonnement dat u wilt overnemen.
4. Selecteer op de pagina Details van abonnement in het gedeelte **Abonnementen en instellingen** de optie **beheer van dit abonnement overnemen**.
5. Selecteer in het rechterdeelvenster de optie **gebruikers verplaatsen**.
6. Selecteer het product waarnaar u de gebruikers wilt verplaatsen en selecteer **gebruikers verplaatsen**.
7. Selecteer in het vak **gebruikers verplaatsen naar** de optie **gebruikers verplaatsen**. Het verplaatsings proces kan enkele minuten duren. Sluit uw browser niet tijdens het uitvoeren van het proces.
8. Wanneer het proces is voltooid, sluit u het **deelvenster doorgaan met voltooien**.
9. Op de pagina Details van abonnement wordt de status van het **abonnement** voor het aangeschafte abonnement voor selfservice en **verwijderd**weergegeven.

### <a name="cancel-a-self-service-purchase-subscription"></a>Een self-service Purchase-abonnement opzeggen

Wanneer u ervoor kiest een abonnement voor selfservice aankopen te annuleren, hebben gebruikers met licenties geen toegang tot het product. De gebruiker die het selfservice aankoop abonnement oorspronkelijk heeft gekocht, ontvangt een e-mail met de mededeling dat het abonnement is geannuleerd.

1. Ga in het Beheercentrum naar de pagina **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">uw producten</a> factureren.
2. Selecteer op het tabblad **Products** het pictogram filter en selecteer vervolgens **selfservice**.
3. Selecteer het abonnement dat u wilt opzeggen.
4. Selecteer op de pagina Details van abonnement in het gedeelte **Abonnementen en instellingen** de optie **beheer van dit abonnement overnemen**.
5. Selecteer in het rechterdeelvenster de optie **abonnement opzeggen**.
6. Selecteer een reden voor de annulering in de vervolgkeuzelijst en selecteer vervolgens **abonnement opzeggen**.
7. Selecteer in het vak **weet u zeker dat u wilt annuleren?** de optie **abonnement opzeggen**.
8. Sluit het rechterdeelvenster.
9. Op de pagina Details van abonnement wordt de status van het **abonnement** weergegeven als **verwijderd**.

## <a name="need-help-contact-us"></a>Hulp nodig? Neem contact met ons op.

Zie Veelgestelde vragen over [selfservice aankopen](self-service-purchase-faq.md)voor veelgestelde vragen over selfservice aankopen.

[Neem contact op met de ondersteuning](../../admin/contact-support-for-business-products.md)als u vragen hebt of hulp nodig hebt bij selfservice aankopen.