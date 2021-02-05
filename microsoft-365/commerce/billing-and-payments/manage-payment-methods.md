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
description: Informatie over het beheren van uw betalingswijzen in het Microsoft 365-beheercentrum.
ms.date: ''
ms.openlocfilehash: 6cba5e33ba99212cb6e67a90d1535120ccac3c38
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114847"
---
# <a name="manage-payment-methods"></a>Betalingswijzen beheren

::: moniker range="o365-21vianet"
> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).
::: moniker-end

Wanneer u zakelijke producten of services koopt bij Microsoft, kunt u een bestaande betalingswijze gebruiken of een nieuwe toevoegen. U kunt een creditcard, betaalkaart of bankrekening gebruiken om te betalen voor de dingen die u koopt.

Als uw zakelijke account een factureringsprofiel heeft en u de eigenaar van het factureringsprofiel of de medewerker van het factureringsprofiel bent, kunt u het factureringsprofiel dat wordt back-by een creditcard of betaling per factuur gebruiken om aankopen te doen of rekeningen te betalen. Als u factuurbeheerder bent, kunt u alleen een factureringsprofiel gebruiken om facturen te betalen. Zie Factureringsprofielen beheren voor meer informatie over [factureringsprofielen en rollen.](manage-billing-profiles.md)

Als uw zakelijke account geen factureringsprofiel heeft, kan een globale beheerder of factureringsbeheerder een bankrekening beheren en gebruiken die aan het zakelijke account is toegevoegd. U kunt echter alleen creditcards beheren of gebruiken die u toevoegt.

> [!NOTE]
> De optie om met een bankrekening te betalen is in sommige landen of regio's niet beschikbaar.
>
> U moet een betalingswijze gebruiken die is uitgegeven vanuit hetzelfde land als uw tenant.

## <a name="before-you-begin"></a>Voordat u begint

U moet een globale beheerder of factureringsbeheerder zijn om de taken in dit artikel uit te voeren. Raadpleeg [Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.

## <a name="add-a-payment-method"></a>Een betalingsmethode toevoegen

Als u een betalingswijze toevoegt, worden er geen abonnementen aan koppelen. Zie Een betalingswijze wijzigen voor één abonnement als u één abonnement wilt toewijzen aan [de betalingswijze.](#change-a-payment-method-for-a-single-subscription) Zie Een betalingswijze vervangen als u alle abonnementen wilt vervangen die een andere betalingswijze gebruiken door [de nieuwe betalingswijze.](#replace-a-payment-method)

1. Ga in het beheercentrum naar de **pagina Factureringsrekeningen**  >  **&**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">betalingen.</a>
2. Selecteer **Betaalmethode toevoegen**.
3. Kies op de pagina **Betalingsmethoden** een betalingsmethode uit het vervolgkeuzemenu.
4. Voer de gegevens voor de nieuwe kaart of bankrekening in en selecteer Vervolgens **Toevoegen.**

## <a name="update-payment-method-details"></a>Betalingswijzegegevens bijwerken

U kunt de naam van een bestaande betalingswijze wijzigen op de creditcard of betaalkaart, het factuuradres of de vervaldatum. U kunt het kaart- of rekeningnummer echter niet wijzigen. Als het rekeningnummer is gewijzigd, [vervangt u het](#replace-a-payment-method)door een andere betalingswijze en verwijdert u vervolgens het [oude.](#delete-a-payment-method)

1. Ga in het beheercentrum naar de **pagina Factureringsrekeningen**  >  **&**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">betalingen.</a>
2. Selecteer de rij van de betalingswijze die u wilt bijwerken. Selecteer Bewerken in het **rechterdeelvenster.**
3. Werk de gegevens van uw betalingswijze bij, inclusief de naam op de creditcard of betaalkaart, het factuuradres of de vervaldatum, en selecteer **opslaan.**

## <a name="replace-a-payment-method"></a>Een betalingswijze vervangen

Wanneer u een betalingswijze vervangt, vervangt u deze voor alle abonnementen en factureringsprofielen die dezelfde betalingswijze gebruiken. Als u een betalingswijze vervangt, wordt de bestaande betalingswijze niet verwijderd. Het is nog steeds beschikbaar voor u om andere abonnementen en factureringsprofielen te selecteren en te gebruiken.

Zie Een betalingswijze wijzigen voor één abonnement als u de betalingswijze voor één [abonnement wilt wijzigen.](#change-a-payment-method-for-a-single-subscription)

1. Ga in het beheercentrum naar de **pagina Factureringsrekeningen**  >  **&**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">betalingen.</a>
2. Selecteer de rij van de betalingswijze die u wilt vervangen. Het rechterdeelvenster bevat alle factureringsprofielen en afzonderlijke abonnementen die gebruikmaken van de geselecteerde betalingswijze.
3. Selecteer in het rechterdeelvenster **De betalingswijze vervangen voor alle items.**
4. Als u een bestaande betalingswijze wilt gebruiken, kiest u er een in de vervolgkeuzelijst en selecteert u **Vervolgens Vervangen.**
    > [!NOTE]
    > Als er abonnementen zijn gekoppeld aan een factureringsprofiel, kunt u er alleen een creditcard of betaalkaart voor gebruiken. Als uw bankrekening op de  pagina Betalingswijzen wordt vermeld, kunt u deze niet selecteren in de vervolgkeuzelijst.
5. Als u een nieuwe betalingswijze wilt toevoegen, **selecteert u Betalingswijze toevoegen.**
6. Voer in **het deelvenster Een betalingswijze** toevoegen de accountgegevens in en selecteer **Opslaan.** U moet een betalingswijze gebruiken uit hetzelfde land als uw tenant.
7. De nieuwe betalingswijze is al geselecteerd in de vervolgkeuzelijst. Selecteer **Vervangen.**

## <a name="change-a-payment-method-for-a-single-subscription"></a>Een betalingswijze wijzigen voor één abonnement

U kunt de betalingswijze wijzigen die wordt gebruikt om voor één abonnement te betalen.

1. Ga in het beheercentrum naar de **pagina Je**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">producten factureren.</a>
2. Zoek op **het** tabblad Producten het abonnement dat u wilt betalen met de alternatieve betalingswijze.
3. Selecteer **Meer acties** (drie puntjes) en selecteer vervolgens **Betalingswijze vervangen.**
4. Kies in **het deelvenster Betalingswijze** vervangen in de vervolgkeuzelijst een alternatieve betalingswijze of kies ervoor om een betalingswijze toe te voegen.
5. Als u een betalingswijze toevoegt, voert u de kaart- of accountgegevens in en selecteert u **Opslaan.**
6. Controleer of de geselecteerde betalingswijze juist is en selecteer vervolgens **Vervangen.**

## <a name="delete-a-payment-method"></a>Een betalingswijze verwijderen

U kunt alleen een betalingswijze verwijderen die niet is gekoppeld aan een abonnement of factureringsprofiel. Dit geldt voor alle abonnementen, ongeacht hun status.

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a>Een betalingswijze verwijderen zonder dat abonnementen of factureringsprofielen zijn gekoppeld

Als een betalingswijze niet is gekoppeld aan een abonnement of factureringsprofiel, kunt u deze onmiddellijk verwijderen.

1. Ga in het beheercentrum naar de **pagina Factureringsrekeningen**  >  **&**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">betalingen.</a>
2. Zoek de betalingswijze die u wilt verwijderen, selecteer de drie puntjes en selecteer **vervolgens Verwijderen.**
3. Selecteer Verwijderen onder in het **rechterdeelvenster.**

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a>Een betalingswijze verwijderen waarbij abonnementen of factureringsprofielen zijn bijgevoegd

Als een betalingswijze is gekoppeld aan abonnementen of factureringsprofielen, vervangt u deze eerst door een bestaande betalingswijze of voegt u een nieuwe toe en verwijdert u vervolgens de oude betalingswijze.

1. Ga in het beheercentrum naar de **pagina Factureringsrekeningen**  >  **&**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">betalingen.</a>
2. Selecteer de rij voor de betalingswijze die u wilt verwijderen. In het rechterdeelvenster worden bestaande abonnementen vermeld die deze betalingswijze gebruiken.
3. Selecteer Verwijderen in het **rechterdeelvenster.**
4. Als u een bestaande betalingswijze wilt gebruiken, kiest u er een in de vervolgkeuzelijst, **selecteert** u Volgende en vervolgens **Verwijderen.**
    > [!NOTE]
    > Als u abonnementen hebt gekoppeld aan een factureringsprofiel, kunt u alleen een creditcard gebruiken om ervoor te betalen. Als uw bankrekening op de  pagina Betalingswijzen wordt vermeld, kunt u deze niet kiezen in de vervolgkeuzelijst.
5. Als u een nieuwe betalingswijze wilt toevoegen, **selecteert u Betalingswijze toevoegen.**
6. Kies het type betalingswijze dat u wilt toevoegen, voer de accountgegevens in en selecteer **Opslaan.**
7. De nieuwe betalingswijze is al geselecteerd in de vervolgkeuzelijst. Selecteer **Volgende**.
8. Selecteer **Verwijderen.**

## <a name="troubleshoot-payment-methods"></a>Problemen met betalingsmethoden oplossen

| Probleem | Stappen voor probleemoplossing |
|:----------|:-----|
|**Ik krijg een foutbericht met de tekst 'De browser is ingesteld op het blokkeren van cookies'.** |Laat uw browser cookies van derden toestaan en probeer het opnieuw. |
|**Mijn creditcard of betaalkaart is geweigerd.** |Als u met een creditcard of betaalkaart betaalt en uw kaart wordt geweigerd, ontvangt u een e-mailbericht dat Microsoft de betaling niet kan verwerken. Controleer nog eens of het kaartnummer, de vervaldatum, de naam op de kaart en het adres, inclusief plaats en postcode, exact zo worden weergegeven als op de kaart en het &mdash; &mdash; overzicht. U kunt uw kaartgegevens bijwerken en de  betaling direct indienen via de koppeling Saldo betalen in het gedeelte **Facturering** van de pagina met abonnementsgegevens. Zie Wat gebeurt er als [ik een openstaand saldo heb?](pay-for-your-subscription.md#what-if-i-have-an-outstanding-balance)  <br/><br/>  Neem contact op met uw bank als uw bank het bericht 'geweigerd' blijft zien. Het is mogelijk dat uw kaart niet actief is. Als u onlangs de kaart met een bijgewerkte vervaldatum in de e-mail hebt ontvangen, zorg er dan voor dat deze is geactiveerd. Uw bank kan u ook vertellen of uw kaart niet is goedgekeurd voor online, internationale of terugkerende transacties. |
|**Ik wil het nummer van een kaart of bankrekening bijwerken.** |U kunt het kaart- of rekeningnummer van een bestaande betalingswijze niet wijzigen. Als uw kaart- of rekeningnummer is [gewijzigd,](#replace-a-payment-method)vervangt u het door een andere betalingswijze, waarmee alle actieve abonnementen van de betalingswijze worden verplaatst naar de nieuwe, en verwijdert u vervolgens de oude [betalingswijze.](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached) |
|**Ik heb maar één kaart of bankrekening in mijn account en ik wil deze verwijderen.** |Als u slechts één betalingswijze hebt, moet u deze vervangen door een nieuwe [betalingswijze](#replace-a-payment-method) voordat u deze kunt verwijderen. |
|**Ik kan mijn creditcard of bankrekening niet toevoegen.**  |U moet een betalingswijze gebruiken die is uitgegeven vanuit hetzelfde land als uw tenant. Als u problemen hebt met het invoeren van uw kaart- of bankrekeninggegevens, kunt u [contact opnemen met de ondersteuning.](../../admin/contact-support-for-business-products.md) |

## <a name="related-content"></a>Verwante onderwerpen

[Uw zakelijke abonnement betalen](pay-for-your-subscription.md) (artikel)\
[Factureringsprofielen beheren](manage-billing-profiles.md) (artikel)\
[De factureringsfrequentie wijzigen](change-payment-frequency.md) (artikel)
