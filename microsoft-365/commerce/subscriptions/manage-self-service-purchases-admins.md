---
title: Selfservice-aankopen beheren (beheerders)
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
description: Beheerders kunnen leren hoe ze selfservice-aankopen van gebruikers in hun organisatie kunnen beheren.
ms.openlocfilehash: 2ce12b7dba4e765745a94fa10f4ba15e7013e3c8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920178"
---
# <a name="manage-self-service-purchases-admin"></a>Selfservice-aankopen beheren (Beheerders)

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](../../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).

::: moniker-end

Als beheerder kunt u selfserviceaankopen zien die zijn gedaan door personen in uw organisatie. U ziet de productnaam, de naam van de inkoper, de gekochte abonnementen, de vervaldatum, de aankoopprijs en de toegewezen gebruikers voor elke selfserviceaankoop. Indien vereist door uw organisatie, kunt u de selfservice-aankoop per product uitschakelen via PowerShell. U hebt hetzelfde gegevensbeheer- en toegangsbeleid voor producten die zijn gekocht via selfserviceaankoop of centraal.

U kunt ook bepalen of gebruikers in uw organisatie selfserviceaankopen kunnen doen. Zie [AllowSelfServicePurchase gebruiken voor de MSCommerce PowerShell-module](allowselfservicepurchase-powershell.md)voor meer informatie.

## <a name="view-self-service-subscriptions"></a>Selfservice-abonnementen weergeven

1. Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Mijn producten</a>.
2. Selecteer op **het** tabblad Producten het filterpictogram en selecteer **vervolgens Selfservice.**
3. Als u meer informatie over een abonnement wilt bekijken, kiest u er een in de lijst.

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a>Bekijken wie licenties heeft voor een selfservice-aankoopabonnement

1. Ga in het beheercentrum naar de pagina   >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Factureringslicenties.</a>
2. Selecteer het filterpictogram en kies **vervolgens Selfservice.**
3. Selecteer een product om licenties te zien die aan personen zijn toegewezen.
    > [!NOTE]
    > Als er meerdere aankopen voor een product zijn, wordt dat  product slechts één keer weergegeven en wordt in de kolom Beschikbare hoeveelheid het totaal weergegeven van alle abonnementen die voor dat product zijn gekocht.
4. De **lijst** Gebruikers wordt gegroepeerd op de namen van personen die selfserviceaankopen hebben gedaan.
5. Als u een lijst met gebruikers met licenties voor deze abonnementen wilt exporteren, kiest u de abonnementen die u wilt exporteren en kiest u **Vervolgens Gebruikers exporteren.**

## <a name="disable-or-enable-self-service-purchases"></a>Selfservice-aankopen uitschakelen of inschakelen

U kunt selfservice-aankopen uitschakelen of inschakelen voor gebruikers in uw organisatie. De **MSCommerce** PowerShell-module bevat een **Beleids-id-parameterwaarde** voor **AllowSelfServicePurchase** waarmee u kunt bepalen of gebruikers in uw organisatie selfserviceaankopen kunnen doen en voor welke producten.

U kunt de **MSCommerce** PowerShell-module gebruiken om:

- De standaardtoestand van de **parameterwaarde AllowSelfServicePurchase** weergeven, ongeacht of deze is ingeschakeld of uitgeschakeld per product
- Een lijst met toepasselijke producten weergeven en controleren of selfserviceaankoop is ingeschakeld of uitgeschakeld
- De huidige instelling voor een specifiek product weergeven of wijzigen om het in of uit te schakelen

Zie [AllowSelfServicePurchase gebruiken voor de MSCommerce PowerShell-module](allowselfservicepurchase-powershell.md)voor meer informatie.

## <a name="centralize-licenses-under-a-single-subscription"></a>Licenties centraliseren onder één abonnement

U kunt bestaande licenties toewijzen of extra abonnementen kopen via bestaande overeenkomsten voor gebruikers die zijn toegewezen aan selfserviceaankopen. Nadat u deze centraal aangeschafte licenties hebt toegewezen, kunt u inkopers verzoeken hun bestaande abonnementen op te zeggen.

1. Ga in het beheercentrum naar de pagina  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Factureringsaankoopservices.</a>
2. Zoek en kies het product dat u wilt kopen en kies vervolgens **Kopen.**
3. Voltooi de resterende stappen om uw aankoop te voltooien.
4. Volg de stappen in Bekijk wie [er licenties](#view-who-has-licenses-for-a-self-service-purchase-subscription) heeft voor een zelf aangeschaft abonnement om een lijst met gebruikers te exporteren waarnaar wordt verwezen in de volgende stap.
5. Wijs licenties toe aan iedereen met een licentie in het andere abonnement. Zie Licenties toewijzen aan gebruikers voor volledige [stappen.](../../admin/manage/assign-licenses-to-users.md)
6. Neem contact op met de persoon die het selfservice-aankoopabonnement heeft gekocht en vraag hem of haar om [het abonnement op te zeggen.](manage-self-service-purchases-users.md#cancel-a-subscription)

## <a name="take-over-a-self-service-purchase-subscription"></a>Een selfservice-aankoopabonnement overnemen

U kunt een selfservice-aankoopabonnement overnemen dat is gemaakt door een gebruiker in uw organisatie. Wanneer u een selfservice-aankoopabonnement over neemt, hebt u twee opties:

1. Verplaats de gebruikers naar een ander abonnement en annuleer het oorspronkelijke abonnement.
2. Annuleer het selfservice-aankoopabonnement en verwijder licenties van toegewezen gebruikers.

### <a name="move-users-to-a-different-subscription"></a>Gebruikers naar een ander abonnement overzetten

Wanneer u gebruikers naar een ander abonnement verplaatst, wordt het oude abonnement automatisch geannuleerd. De gebruiker die het selfservice-aankoopabonnement oorspronkelijk heeft gekocht, ontvangt een e-mail met de informatie dat het abonnement is geannuleerd.

> [!NOTE]
> U moet een beschikbare licentie hebben voor elke gebruiker die u verplaatst in het abonnement waar u gebruikers naar verplaatst.

1. Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Mijn producten</a>.
2. Selecteer op **het** tabblad Producten het filterpictogram en selecteer **vervolgens Selfservice.**
3. Selecteer het abonnement dat u wilt overnemen.
4. Selecteer op de pagina **abonnementsgegevens** in de sectie Abonnementen en instellingen de optie **Beheer van dit abonnement nemen.**
5. Selecteer in het rechterdeelvenster **Gebruikers verplaatsen.**
6. Selecteer het product waar u de gebruikers naar wilt verplaatsen en selecteer **vervolgens Gebruikers verplaatsen.**
7. Selecteer in **het vak Gebruikers verplaatsen** naar de optie Gebruikers **verplaatsen.** Het verplaatsen kan enkele minuten duren. Sluit uw browser niet terwijl het proces wordt uitgevoerd.
8. Wanneer het verhuisproces is voltooid, sluit u het **deelvenster Voltooid verplaatsen.**
9. Op de pagina Met abonnementsgegevens wordt de **abonnementsstatus** voor het zelf aangeschafte abonnement weergegeven als **Verwijderd.**

### <a name="cancel-a-self-service-purchase-subscription"></a>Een selfservice-aankoopabonnement opzeggen

Wanneer u ervoor kiest om een selfservice-aankoopabonnement op te zeggen, hebben gebruikers met licenties geen toegang meer tot het product. De gebruiker die het selfservice-aankoopabonnement oorspronkelijk heeft gekocht, ontvangt een e-mail met de informatie dat het abonnement is geannuleerd.

1. Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Mijn producten</a>.
2. Selecteer op **het** tabblad Producten het filterpictogram en selecteer **vervolgens Selfservice.**
3. Selecteer het abonnement dat u wilt opzeggen.
4. Selecteer op de pagina **abonnementsgegevens** in de sectie Abonnementen en instellingen de optie **Beheer van dit abonnement nemen.**
5. Selecteer in het rechterdeelvenster **Abonnement opzeggen.**
6. Selecteer een reden voor uw annulering in de vervolgkeuzelijst en selecteer vervolgens **Abonnement annuleren.**
7. Selecteer in **het vak Weet u zeker dat u wilt opzeggen?** de optie Abonnement **opzeggen.**
8. Sluit het rechterdeelvenster.
9. Op de pagina abonnementsgegevens wordt de **abonnementsstatus** weergegeven **als Verwijderd.**

## <a name="need-help-contact-us"></a>Hulp nodig? Neem contact met ons op.

Zie Veelgestelde vragen over selfservice-aankopen voor veelgestelde vragen over [selfserviceaankopen.](self-service-purchase-faq.md)

Als u vragen hebt of hulp nodig hebt bij selfserviceaankopen, [neem dan contact op met ondersteuning.](../../admin/contact-support-for-business-products.md)