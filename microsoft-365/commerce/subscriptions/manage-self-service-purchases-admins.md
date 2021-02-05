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
description: Beheerders kunnen informatie krijgen over het beheren van selfserviceaankopen die zijn gedaan door gebruikers in hun organisatie.
ms.openlocfilehash: 3e04f58c10b14aca8b356c064106b7107f144d91
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114691"
---
# <a name="manage-self-service-purchases-admin"></a>Selfservice-aankopen beheren (Beheerders)

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

Als beheerder kunt u selfserviceaankopen zien die zijn gedaan door personen in uw organisatie. U ziet de productnaam, de inkopernaam, de aangeschafte abonnementen, de vervaldatum, de aankoopprijs en de toegewezen gebruikers voor elke selfservice-aankoop. Indien vereist door uw organisatie, kunt u de selfservice-aankoop per product uitschakelen via PowerShell. U hebt hetzelfde beleid voor gegevensbeheer en toegang tot producten die zijn gekocht via selfservice-aankoop of centraal.

U kunt ook bepalen of gebruikers in uw organisatie selfservice-aankopen kunnen doen. Zie [AllowSelfServicePurchase gebruiken voor de MSChat PowerShell-module voor meer informatie.](allowselfservicepurchase-powershell.md)

## <a name="view-self-service-subscriptions"></a>Selfservice-abonnementen weergeven

1. Ga in het beheercentrum naar de **pagina Je**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">producten factureren.</a>
2. Selecteer op **het** tabblad Producten het filterpictogram en selecteer **Selfservice.**
3. Als u meer informatie over een abonnement wilt bekijken, kiest u er een in de lijst.

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a>Bekijken wie licenties heeft voor een abonnement voor selfservice-aankopen

1. Ga in het beheercentrum naar de **pagina**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Factureringslicenties.</a>
2. Selecteer het filterpictogram en kies **Selfservice.**
3. Selecteer een product om de licenties te zien die zijn toegewezen aan personen.
    > [!NOTE]
    > Als er meerdere aankopen voor een product zijn, wordt dat  product slechts één keer weergegeven en toont de kolom Beschikbare hoeveelheid het totaal van alle abonnementen die voor dat product zijn gekocht.
4. De **lijst** Gebruikers wordt gegroepeerd op de namen van personen die selfserviceaankopen hebben gedaan.
5. Als u een lijst met gebruikers met licenties voor deze abonnementen wilt exporteren, kiest u de abonnementen die u wilt exporteren en kiest u **Vervolgens Gebruikers exporteren.**

## <a name="disable-or-enable-self-service-purchases"></a>Selfservice-aankopen uitschakelen of inschakelen

U kunt selfservice-aankopen voor gebruikers in uw organisatie uitschakelen of inschakelen. De **MSChat** PowerShell-module bevat een **PolicyID-parameterwaarde** voor **Allow SelfServicePurchase** waarmee u kunt bepalen of gebruikers in uw organisatie selfserviceaankopen kunnen doen en voor welke producten.

U kunt de **MSShell** PowerShell-module gebruiken voor het volgende:

- De standaardwaarde van de **parameterwaarde AllowSelfServicePurchase** weergeven, of deze nu is in- of uitgeschakeld door een product
- Bekijk een lijst met toepasselijke producten en of selfservice-aankoop is in- of uitgeschakeld
- De huidige instelling voor een specifiek product weergeven of wijzigen om deze in of uit te schakelen

Zie [AllowSelfServicePurchase gebruiken voor de MSChat PowerShell-module voor meer informatie.](allowselfservicepurchase-powershell.md)

## <a name="centralize-licenses-under-a-single-subscription"></a>Licenties centraal maken onder één abonnement

U kunt bestaande licenties toewijzen of aanvullende abonnementen kopen via bestaande overeenkomsten voor gebruikers die zijn toegewezen aan selfservice-aankopen. Nadat u deze centraal gekochte licenties hebt toegewezen, kunt u inkopers vragen hun bestaande abonnementen te annuleren.

1. Ga in het beheercentrum naar de **pagina Services voor** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">facturering</a> aanschaffen.
2. Zoek en kies het product dat u wilt kopen en kies vervolgens **Kopen.**
3. Voltooi de resterende stappen om uw aankoop te voltooien.
4. Volg de stappen in [Weergeven wie](#view-who-has-licenses-for-a-self-service-purchase-subscription) licenties heeft voor een zelf aangeschaft abonnement om een lijst met gebruikers te exporteren waarnaar in de volgende stap moet worden verwezen.
5. Wijs licenties toe aan iedereen met een licentie in het andere abonnement. Zie Licenties toewijzen aan gebruikers voor [volledige stappen.](../../admin/manage/assign-licenses-to-users.md)
6. Neem contact op met de persoon die het abonnement voor selfservice-aankopen heeft gekocht en vraag hem of haar het [abonnement te annuleren.](manage-self-service-purchases-users.md#cancel-a-subscription)

## <a name="take-over-a-self-service-purchase-subscription"></a>Een abonnement voor selfservice aanschaffen overnemen

U kunt een abonnement voor selfservice-aankopen overnemen dat is gemaakt door een gebruiker in uw organisatie. Wanneer u een abonnement voor selfservice-aankopen over neemt, hebt u twee opties:

1. Verplaats de gebruikers naar een ander abonnement en annuleer het oorspronkelijke abonnement.
2. Annuleer het abonnement voor selfservice-aankopen en verwijder licenties van toegewezen gebruikers.

### <a name="move-users-to-a-different-subscription"></a>Gebruikers naar een ander abonnement overzetten

Wanneer u gebruikers over verplaatst naar een ander abonnement, wordt het oude abonnement automatisch geannuleerd. De gebruiker die oorspronkelijk het abonnement voor selfservice-aankopen heeft gekocht, ontvangt een e-mail met de informatie dat het abonnement is geannuleerd.

> [!NOTE]
> U moet een beschikbare licentie hebben voor elke gebruiker naar wie u overstapt in het abonnement waarin u gebruikers wilt over verplaatsen.

1. Ga in het beheercentrum naar de **pagina Je**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">producten factureren.</a>
2. Selecteer op **het** tabblad Producten het filterpictogram en selecteer **Selfservice.**
3. Selecteer het abonnement dat u wilt overnemen.
4. Selecteer op de pagina met **abonnementsdetails** in de sectie Abonnementen en instellingen de optie **Besturing van dit abonnement nemen.**
5. Selecteer Gebruikers verplaatsen in **het rechterdeelvenster.**
6. Selecteer het product waar u de gebruikers naar wilt verplaatsen en selecteer **vervolgens Gebruikers verplaatsen.**
7. Selecteer Gebruikers **verplaatsen in het** vak Gebruikers **verplaatsen** naar. Het verplaatsen kan enkele minuten duren. Sluit de browser niet terwijl het proces wordt uitgevoerd.
8. Wanneer het verplaatsen is voltooid, sluit u het **deelvenster Voltooid verplaatsen.**
9. Op de pagina met abonnementsgegevens wordt de **abonnementsstatus** voor het zelf aangeschafte abonnement weergegeven als **Verwijderd.**

### <a name="cancel-a-self-service-purchase-subscription"></a>Een abonnement voor selfservice-aankopen annuleren

Als u ervoor kiest om een abonnement voor selfservice-aankopen op te zeggen, hebben gebruikers met een licentie geen toegang meer tot het product. De gebruiker die oorspronkelijk het abonnement voor selfservice-aankopen heeft gekocht, ontvangt een e-mail met de informatie dat het abonnement is geannuleerd.

1. Ga in het beheercentrum naar de **pagina Je**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">producten factureren.</a>
2. Selecteer op **het** tabblad Producten het filterpictogram en selecteer **Selfservice.**
3. Selecteer het abonnement dat u wilt opzeggen.
4. Selecteer op de pagina met **abonnementsdetails** in de sectie Abonnementen en instellingen de optie **Besturing van dit abonnement nemen.**
5. Selecteer Abonnement annuleren in het **rechterdeelvenster.**
6. Selecteer een reden voor uw opzegging in de vervolgkeuzelijst en selecteer **Vervolgens Abonnement annuleren.**
7. Selecteer Abonnement **annuleren in** het vak Weet u zeker dat u wilt **opzeggen?**
8. Sluit het rechterdeelvenster.
9. Op de pagina met abonnementsgegevens wordt de **abonnementsstatus** weergegeven als **Verwijderd.**

## <a name="need-help-contact-us"></a>Hulp nodig? Neem contact met ons op.

Veelgestelde vragen over selfservice-aankopen vindt u veelgestelde vragen over [selfservice-aankopen.](self-service-purchase-faq.md)

Als u vragen hebt of hulp nodig hebt bij selfservice-aankopen, [neem dan contact op met de ondersteuning.](../../admin/contact-support-for-business-products.md)