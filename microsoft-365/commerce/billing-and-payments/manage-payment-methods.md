---
title: Betalingsmethoden beheren
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jamitche, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- TopSMBIssues
- okr_SMB
- AdminSurgePortfolio
- commerce_billing
- AdminTemplateSet
search.appverid: MET150
description: Wanneer u zakelijke producten of services van Microsoft koopt, kunt u een bestaande betalingswijze gebruiken of een nieuwe toevoegen in het Microsoft 365-beheercentrum.
ms.date: 04/02/2021
ms.openlocfilehash: e944547e69ea8774690852d1b3123578d40bd3c0
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394615"
---
# <a name="manage-payment-methods"></a>Betalingsmethoden beheren

> [!IMPORTANT]
> Vanaf 26 januari 2021 worden nieuwe bankrekeningen niet meer ondersteund voor klanten in België, Frankrijk, Italië, Luxemburg, Portugal, Spanje en de Verenigde Staten. Als u een bestaande klant bent in een van deze landen, kunt u voor uw abonnement blijven betalen via uw bestaande bankrekening en kunt u nieuwe abonnementen toevoegen, mits uw bankrekening een goede status heeft.

Wanneer u zakelijke producten of services van Microsoft koopt, kunt u een bestaande betalingsmethode gebruiken of een nieuwe toevoegen. U kunt een creditcard, betaalkaart of bankrekening gebruiken om te betalen voor de dingen die u koopt.

Als uw zakelijke account een factureringsprofiel heeft en u de eigenaar of inzender van het factureringsprofiel bent, kunt u het factureringsprofiel gebruiken waarvoor een creditcard- of factuurbetaling wordt gebruikt om aankopen te doen of facturen te betalen. Als u factureringsbeheerder bent, kunt u alleen een factureringsprofiel gebruiken om facturen te betalen. Zie voor meer informatie over factureringsprofielen en -rollen [Factureringsprofielen beheren](manage-billing-profiles.md).

Als uw zakelijke account geen factureringsprofiel heeft, kan elke globale of factureringsbeheerder elke bankrekening beheren en gebruiken die is toegevoegd aan het zakelijke account. U kunt echter alleen creditcards beheren of gebruiken die u zelf toevoegt.

> [!NOTE]
> De optie om te betalen via een bankrekening is niet beschikbaar in bepaalde landen of regio's.
>
> U moet een betalingsmethode gebruiken die wordt uitgegeven vanuit hetzelfde land als uw tenant.

## <a name="before-you-begin"></a>Voordat u begint

U moet een Globale of Factureringsbeheerder zijn om de stappen in dit artikel uit te voeren. Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.

## <a name="add-a-payment-method"></a>Een betalingsmethode toevoegen

Als u een betalingsmethode toevoegt, worden hier geen abonnementen aan gekoppeld. Voor meer informatie over het toewijzen van een enkel abonnement aan de betalingsmethode, raadpleegt u [Betalingsmethode voor één abonnement wijzigen](#change-a-payment-method-for-a-single-subscription). Zie [Een betalingsmethode vervangen](#replace-a-payment-method) als u de betalingsmethode voor alle abonnement wilt vervangen met een nieuwe.

1. Ga in het Beheercentrum naar de pagina **Facturering** > **Facturen en betalingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Betalingsmethoden</a>. 
2. Selecteer **Betaalmethode toevoegen**.
3. Kies op de pagina **Betalingsmethoden** een betalingsmethode uit het vervolgkeuzemenu.
4. Voer de gegevens voor de nieuwe creditcard of bankrekening in en selecteer vervolgens **Toevoegen**.

## <a name="update-payment-method-details"></a>Gegevens betalingsmethode bijwerken

Voor een bestaande betalingsmethode kunt u de naam wijzigen op de creditcard of betaalkaart, het factuuradres of de vervaldatum. U kunt het kaart- of rekeningnummer echter niet wijzigen. Als het rekeningnummer is gewijzigd, kunt u dit [vervangen door een andere betalingsmethode](#replace-a-payment-method) en vervolgens [de oude verwijderen](#delete-a-payment-method).

1. Ga in het Beheercentrum naar de pagina **Facturering** > **Facturen en betalingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Betalingsmethoden</a>. 
2. Selecteer de rij van de betalingsmethode die u wilt bijwerken. Selecteer de optie **Bewerken** in het rechterdeelvenster.
3. Werk de gegevens van uw betalingsmethode bij, waaronder de naam op de creditcard of betaalkaart, het factuuradres of de vervaldatum, en selecteer vervolgens **Opslaan**.

## <a name="replace-a-payment-method"></a>Een betalingsmethode vervangen

Wanneer u een betalingsmethode vervangt, vervangt u deze voor alle abonnementen en factureringsprofielen die dezelfde betalingsmethode gebruiken. Als u een betalingsmethode vervangt, wordt de bestaande betalingsmethode niet verwijderd. U kunt deze nog steeds selecteren en gebruiken voor andere abonnementen en factureringsprofielen.

Voor meer informatie over het wijzigen van de betalingsmethode voor een enel abonnement, raadpleegt u [Betalingsmethode voor één abonnement wijzigen](#change-a-payment-method-for-a-single-subscription).

1. Ga in het Beheercentrum naar de pagina **Facturering** > **Facturen en betalingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Betalingsmethoden</a>. 
2. Selecteer de rij van de betalingsmethode die u wilt vervangen. Het rechterdeelvenster bevat alle factureringsprofielen en afzonderlijke abonnementen die gebruikmaken van de geselecteerde betalingsmethode.
3. Selecteer in het rechterdeelvenster **Betalingsmethode vervangen voor alle items**.
4. Als u een bestaande betalingsmethode wilt gebruiken, kiest u een methode in de vervolgkeuzelijst en selecteert u **Vervangen**.
    > [!NOTE]
    > Als er abonnementen zijn gekoppeld aan een factureringsprofiel, kunt u alleen een creditcard of betaalkaart gebruiken om ervoor te betalen. Als uw bankrekeningen worden vermeld op de pagina **Betalingsmethoden**, kunt u deze niet selecteren in de vervolgkeuzelijst.
5. Als u een nieuwe betalingsmethode wilt toevoegen, selecteert u **Betalingsmethode toevoegen**.
6. Voer in het deelvenster **Een betalingsmethode toevoegen** de accountgegevens in en selecteer **Opslaan**. U moet een betalingsmethode gebruiken uit hetzelfde land als uw tenant.
7. De nieuwe betalingsmethode is al geselecteerd in de vervolgkeuzelijst. Selecteer **Vervangen**.

## <a name="change-a-payment-method-for-a-single-subscription"></a>Een betalingsmethode wijzigen voor één abonnement

U kunt de betalingsmethode wijzigen die voor één abonnement wordt gebruikt.

1. Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Mijn producten</a>.
2. Zoek in het tabblad **Producten** het abonnement waarvoor u wilt betalen met de alternatieve betalingsmethode.
3. Selecteer de drie puntjes (meer acties) en selecteer **Betalingswijze vervangen**.
4. Kies in het deelvenster **Betalingsmethode vervangen** in de vervolgkeuzelijst een alternatieve betalingsmethode of kies voor het toevoegen van een betalingsmethode.
5. Als u een betalingsmethode toevoegt, voert u de kaart- of rekeninggegevens in en selecteert u **Opslaan**.
6. Controleer of de geselecteerde betalingsmethode juist is en selecteer **Vervangen**.

## <a name="delete-a-payment-method"></a>Een betalingsmethode verwijderen

U kunt alleen een betalingsmethode verwijderen die niet is gekoppeld aan een abonnement of factureringsprofiel. Dit geldt voor alle abonnementen, ongeacht de status.

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a>Een betalingsmethode verwijderen waar geen abonnementen of factureringsprofielen aan zijn gekoppeld

Als uw betalingsmethode niet is gekoppeld aan een abonnement of factureringsprofiel, kunt u deze direct verwijderen.

1. Ga in het Beheercentrum naar de pagina **Facturering** > **Facturen en betalingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Betalingsmethoden</a>. 
2. Zoek de betalingswijze die u wilt verwijderen, selecteer de drie puntjes en selecteer **Verwijderen**.
3. Selecteer onderaan het rechterdeelvenster **Verwijderen**.

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a>Een betalingsmethode verwijderen waar abonnementen of factureringsprofielen aan zijn gekoppeld

Als een betalingswijze is gekoppeld aan abonnementen of factureringsprofielen, vervangt u deze eerst door een bestaande betalingsmethode of voegt u een nieuwe toe en verwijdert u vervolgens de oude betalingsmethode.

1. Ga in het Beheercentrum naar de pagina **Facturering** > **Facturen en betalingen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Betalingsmethoden</a>. 
2. Selecteer de rij van de betalingsmethode die u wilt verwijderen. In het rechterdeelvenster worden bestaande abonnementen vermeld die deze betalingsmethode gebruiken.
3. Selecteer in het rechterdeelvenster **Verwijderen**.
4. Als u een bestaande betalingsmethode wilt gebruiken, kiest u een methode in de vervolgkeuzelijst en selecteert u **Volgende** en vervolgens **Verwijderen**.
    > [!NOTE]
    > Als er abonnementen zijn gekoppeld aan een factureringsprofiel, kunt u alleen een creditcard gebruiken om ervoor te betalen. Als uw bankrekeningen worden vermeld op de pagina **Betalingsmethoden**, kunt u deze niet kiezen in de vervolgkeuzelijst.
5. Als u een nieuwe betalingsmethode wilt toevoegen, selecteert u **Betalingsmethode toevoegen**.
6. Kies het type betalingswijze dat u wilt toevoegen, voer de accountgegevens in en selecteer vervolgens **Opslaan**.
7. De nieuwe betalingsmethode is al geselecteerd in de vervolgkeuzelijst. Selecteer **Volgende**.
8. Selecteer **Verwijderen**.

## <a name="troubleshoot-payment-methods"></a>Problemen met betalingsmethoden oplossen

| Probleem | Stappen voor probleemoplossing |
|:----------|:-----|
|**Ik krijg een foutbericht met de tekst 'De browser is momenteel ingesteld op het blokkeren van cookies.'** |Laat uw browser cookies van derden toestaan en probeer het opnieuw. |
|**Mijn creditcard is geweigerd.** |Als u via creditcard of betaalpas betaalt, maar uw kaart wordt geweigerd, ontvangt u een e-mailbericht met de mededeling dat Microsoft de betaling niet kon verwerken. Controleer eerst nog een keer of de kaartgegevens&mdash;het nummer, de vervaldatum, de naam op de kaart en het adres, inclusief plaats en postcode&mdash; exact dezelfde zijn als op de kaart en uw afschrift. U kunt uw kaartgegevens bijwerken en de betaling onmiddellijk verzenden via de koppeling **Saldo betalen** in de sectie **Facturering** van de pagina abonnementsgegevens. Zie voor meer informatie [Wat gebeurt er als ik een openstaand saldo heb?](pay-for-your-subscription.md#what-if-i-have-an-outstanding-balance)  <br/><br/>  Neem contact op met de bank als uw creditcard alsnog wordt geweigerd. Het kan zijn dat uw kaart niet is geactiveerd. Als u onlangs een kaart met bijgewerkte vervaldatum via de post hebt ontvangen, moet u deze misschien nog activeren. U kunt ook bij uw bank navragen of uw kaart mogelijk niet is goedgekeurd voor online, internationale of terugkerende transacties.   |
|**Ik wil een creditcard- of bankrekeningnummer bijwerken.** |U kunt het nummer van een creditcard of bankrekening niet wijzigen in een bestaande betalingsmethode. Als het nummer van uw creditcard of rekening is gewijzigd, kunt u [deze vervangen door een andere betalingsmethode](#replace-a-payment-method), waarmee alle actieve abonnementen van de betalingsmethode naar de nieuwe worden verplaatst. Vervolgens kunt u [de oude betalingsmethode verwijderen](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached). |
|**Ik heb maar één creditcard of bankrekening in mijn account en die wil ik verwijderen.** |Als u maar één betalingsmethode hebt, moet u deze [vervangen door een nieuwe betalingsmethode](#replace-a-payment-method) voordat u deze kunt verwijderen. |
|**Betalen via kaart of bankrekening.**  |U moet een betalingsmethode gebruiken die wordt uitgegeven vanuit hetzelfde land als uw tenant. Als u problemen ondervindt met het invoeren van de gegevens van uw kaart of bankrekening, kunt [contact opnemen met ondersteuning](../../business-video/get-help-support.md). |

## <a name="related-content"></a>Verwante onderwerpen

[Uw zakelijke abonnement betalen](pay-for-your-subscription.md) (artikel)\
[Uw factureringsprofielen beheren](manage-billing-profiles.md) (artikel)\
[Uw factureringsfrequentie wijzigen](change-payment-frequency.md) (artikel)
