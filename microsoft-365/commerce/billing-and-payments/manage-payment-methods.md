---
title: Betalingswijzen beheren
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
ms.custom:
- TopSMBIssues
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
description: Meer informatie over het beheren van uw betaalwijzen in het Microsoft 365-Beheercentrum.
ms.date: ''
ms.openlocfilehash: 81c7509fb2f3be982890ec6b68dafb83ff0c1876
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324232"
---
# <a name="manage-payment-methods"></a>Betalingswijzen beheren

::: moniker range="o365-21vianet"
> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).
::: moniker-end

Wanneer u zakelijke producten of services bij Microsoft koopt, kunt u een bestaande betaalwijze gebruiken of een nieuwe betalingswijze toevoegen. U kunt een creditcard of betaalkaart of bankrekening gebruiken om te betalen voor de dingen die u koopt.

Als uw bedrijfsaccount een factuur profiel heeft en u de eigenaar van het facturerings profiel of de Inzender voor facturerings profielen bent, kunt u het facturerings profiel gebruiken dat wordt ondersteund door een creditcard of factuur betaling om aankopen te doen of te betalen. Als u een factuur beheerder bent, kunt u alleen een factuur profiel gebruiken om facturen te betalen. Zie [facturerings profielen beheren](manage-billing-profiles.md)voor meer informatie over facturerings profielen en rollen.

Als uw bedrijfsaccount geen factuur profiel heeft, kan een globale beheerder of Factureringsbeheerder een bankrekening beheren die aan de bedrijfsaccount is toegevoegd. U kunt echter alleen creditcards die u toevoegt beheren of gebruiken.

> [!NOTE]
> De optie om te betalen met een bankrekening is niet beschikbaar in sommige landen of regio's.
>
> U moet een betaalwijze gebruiken die is uitgegeven uit hetzelfde land als uw Tenant.

## <a name="before-you-begin"></a>Voordat u begint

U moet een globale beheerder of Factureringsbeheerder zijn om de taken in dit artikel uit te voeren. Raadpleeg [Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.

## <a name="add-a-payment-method"></a>Een betalingsmethode toevoegen

Bij het toevoegen van een betalingswijze worden geen abonnementen gekoppeld. Zie [een betalingswijze voor één abonnement wijzigen](#change-a-payment-method-for-a-single-subscription)als u één abonnement aan de betalingsmethode wilt toewijzen. Zie [een betalingsmethode vervangen](#replace-a-payment-method)als u alle abonnementen met een andere betaalmethode wilt vervangen door de nieuwe.

1. Ga in het Beheercentrum naar de pagina **facturerings**  >  **&** betaal  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">methoden</a> voor betalingen.
2. Selecteer **Betaalmethode toevoegen**.
3. Kies op de pagina **Betalingsmethoden** een betalingsmethode uit het vervolgkeuzemenu.
4. Voer de gegevens voor de nieuwe kaart of bankrekening in en selecteer vervolgens **toevoegen**.

## <a name="update-payment-method-details"></a>Details van betalingsmethode bijwerken

U kunt de naam van de creditcard of betaalkaart, het factuuradres of de vervaldatum voor een bestaande betalingsmethode wijzigen. U kunt echter de kaart of het rekeningnummer niet wijzigen. Als het accountnummer is gewijzigd, [vervangt u dit door een andere betalingsmethode](#replace-a-payment-method)en [verwijdert u de oude](#delete-a-payment-method).

1. Ga in het Beheercentrum naar de pagina **facturerings**  >  **&** betaal  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">methoden</a> voor betalingen.
2. Selecteer de rij met de betalingsmethode die u wilt bijwerken. Selecteer in het rechterdeelvenster **bewerken**.
3. Werk uw gegevens voor uw betaalwijze bij, waaronder de naam van de creditcard of betaalkaart, het factuuradres of de vervaldatum, en selecteer vervolgens **Opslaan**.

## <a name="replace-a-payment-method"></a>Een betalingswijze vervangen

Wanneer u een betaalmethode vervangt, vervangt u deze voor alle abonnementen en facturerings profielen die dezelfde betalingsmethode gebruiken. Door een betalingswijze te vervangen, wordt de bestaande betalingsmethode niet verwijderd. Het is nog steeds beschikbaar om te selecteren en te gebruiken voor andere abonnementen en facturerings profielen.

Zie [een betalingswijze voor één abonnement wijzigen](#change-a-payment-method-for-a-single-subscription)als u de betalingswijze voor één abonnement wilt wijzigen.

1. Ga in het Beheercentrum naar de pagina **facturerings**  >  **&** betaal  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">methoden</a> voor betalingen.
2. Selecteer de rij met de betaalwijze die u wilt vervangen. Het rechterdeelvenster bevat alle facturerings profielen en afzonderlijke abonnementen die gebruikmaken van de geselecteerde betaalwijze.
3. Selecteer in het rechterdeelvenster de optie **betalingsmethode vervangen voor alle items**.
4. Als u een bestaande betaalwijze wilt gebruiken, kiest u een in de vervolgkeuzelijst en selecteert u vervolgens **vervangen**.
    > [!NOTE]
    > Als u abonnementen hebt die zijn gekoppeld aan een facturerings profiel, kunt u een creditcard of betaalkaart gebruiken om hiervoor een factuur te betalen. Als u op de pagina **betaalwijzen** bankrekeningen hebt vermeld, kunnen ze niet selecteren in de vervolgkeuzelijst.
5. Als u een nieuwe betalingsmethode wilt toevoegen, selecteert u **betalingsmethode toevoegen**.
6. Voer in het deelvenster **een betalingswijze toevoegen** de accountgegevens in en selecteer **Opslaan**. U moet een betaalwijze gebruiken van hetzelfde land als uw Tenant.
7. De nieuwe betalingswijze is al geselecteerd in de vervolgkeuzelijst. Selecteer **vervangen**.

## <a name="change-a-payment-method-for-a-single-subscription"></a>Een betalingswijze voor één abonnement wijzigen

U kunt de betaalwijze voor één abonnement wijzigen.

1. Ga in het Beheercentrum naar de pagina **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">uw producten</a> factureren.
2. Zoek op het tabblad **producten** naar het abonnement waarvoor u wilt betalen met een andere betaalwijze.
3. Selecteer **meer acties** (drie puntjes) en selecteer vervolgens **betalingsmethode vervangen**.
4. Kies in het deelvenster **betalingsmethode vervangen** in de vervolgkeuzelijst een andere betalingsmethode of kies toevoegen om een betalingswijze toe te voegen.
5. Als u een betaalmethode toevoegt, voert u de gegevens van de kaart of rekening in en selecteert u vervolgens **Opslaan**.
6. Controleer of de geselecteerde betaalwijze juist is en selecteer **vervangen**.

## <a name="delete-a-payment-method"></a>Een betalingswijze verwijderen

U kunt alleen een betalingswijze verwijderen die niet is gekoppeld aan een abonnement of facturerings profiel. Dit geldt voor alle abonnementen, ongeacht hun status.

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a>Een betalingswijze verwijderen waaraan geen abonnementen of facturerings profielen zijn gekoppeld

Als een betalingswijze niet is gekoppeld aan een abonnement of facturerings profiel, kunt u deze onmiddellijk verwijderen.

1. Ga in het Beheercentrum naar de pagina **facturerings**  >  **&** betaal  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">methoden</a> voor betalingen.
2. Zoek de betaalwijze die u wilt verwijderen, selecteer de drie puntjes en selecteer vervolgens **verwijderen**.
3. Selecteer **verwijderen**onder aan het rechterdeelvenster.

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a>Een betalingswijze verwijderen waaraan abonnementen of facturerings profielen zijn toegevoegd

Als aan een abonnement of factuur profielen een betaalwijze is gekoppeld, vervangt u deze eerst door een bestaande betaalmethode of voegt u een nieuwe betalingsmethode toe.

1. Ga in het Beheercentrum naar de pagina **facturerings**  >  **&** betaal  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">methoden</a> voor betalingen.
2. Selecteer de rij voor de betalingswijze die u wilt verwijderen. Het rechterdeelvenster bevat bestaande abonnementen die gebruikmaken van deze betalingsmethode.
3. Klik in het rechterdeelvenster op **verwijderen**.
4. Als u een bestaande betaalwijze wilt gebruiken, kiest u er een in de vervolgkeuzelijst, selecteert u **volgende**en selecteert u vervolgens **verwijderen**.
    > [!NOTE]
    > Als u abonnementen hebt die zijn gekoppeld aan een factuur profiel, kunt u deze alleen met een creditcard betalen. Als u op de pagina **betaalwijzen** bankrekeningen hebt vermeld, zijn deze niet beschikbaar voor keuze in de vervolgkeuzelijst.
5. Als u een nieuwe betalingsmethode wilt toevoegen, selecteert u **betalingsmethode toevoegen**.
6. Kies het type betaalwijze dat u wilt toevoegen, voer de accountgegevens in en selecteer **Opslaan**.
7. De nieuwe betalingswijze is al geselecteerd in de vervolgkeuzelijst. Selecteer **Volgende**.
8. Selecteer **verwijderen**.

## <a name="troubleshoot-payment-methods"></a>Problemen met betalingsmethoden oplossen

|**Probleem**|**Stappen voor probleemoplossing**|
|:----------|:-----|
|**Ik krijg een foutbericht met de tekst ' de browser is momenteel ingesteld op het blokkeren van cookies. '** |Laat uw browser cookies van derden toestaan en probeer het opnieuw. |
|**Mijn creditcard of betaalkaart is geweigerd.** |Als u met een creditcard of betaalkaart betaalt en uw creditcard wordt geweigerd, ontvangt u een e-mailbericht met de mededeling dat Microsoft de betaling niet kan verwerken. Controleer het nummer van de kaartgegevens &mdash; , de vervaldatum, de naam van de kaart en het adres, inclusief plaats, provincie en postcode, &mdash; op dezelfde manier als op de kaart en uw afschrift worden weergegeven. U kunt uw kaart informatie bijwerken en direct de betaling indienen met behulp van de koppeling voor de **Vereffenings balans** in de sectie **facturering** van de pagina Details van abonnement. Zie [Wat als mijn creditcard is geweigerd en mijn betaling achterstallig is?](pay-for-your-subscription.md#what-if-my-credit-card-was-declined-and-my-payment-is-past-due) voor meer informatie.  <br/><br/>  Neem contact op met uw bank als u het bericht ' geweigerd ' blijft zien. Mogelijk is uw kaart niet actief. Als u de kaart onlangs in het e-mailbericht met een bijgewerkte vervaldatum hebt ontvangen, controleert u of deze is geactiveerd. U kunt in uw bank ook aangeven of uw kaart niet is goedgekeurd voor online, buitenlandse of terugkerende transacties. |
|**Ik wil een creditcard-of bankrekeningnummer bijwerken.** |U kunt de kaart of het rekeningnummer van een bestaande betaalwijze niet wijzigen. Als uw kaart of accountnummer is gewijzigd, [vervangt u dit door een andere betalingsmethode](#replace-a-payment-method), zodat alle actieve abonnementen van de betaalmethode naar het nieuwe abonnement worden verplaatst en vervolgens [de oude betaalmethode verwijdert](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached). |
|**Ik heb maar één kaart of bankrekening in mijn account en die wil ik verwijderen.** |Als u slechts één betaalmethode hebt, moet u [deze vervangen door een nieuwe betaalmethode](#replace-a-payment-method) voordat u deze kunt verwijderen. |
|**Ik kan mijn creditcard of bankrekening niet toevoegen.**  |U moet een betaalwijze gebruiken die is uitgegeven uit hetzelfde land als uw Tenant. Als u problemen ondervindt bij het invoeren van uw kaart-of bankrekeninggegevens, kunt u [contact opnemen met ondersteuning](../../admin/contact-support-for-business-products.md). |

## <a name="related-content"></a>Verwante onderwerpen

[Betalen voor uw zakelijke abonnement](pay-for-your-subscription.md) (artikel) \
[Facturerings profielen beheren](manage-billing-profiles.md) (artikel) \
[De frequentie van facturering wijzigen](change-payment-frequency.md) (artikel)