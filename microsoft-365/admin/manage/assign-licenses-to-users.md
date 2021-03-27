---
title: Licenties aan gebruikers toewijzen
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- TopSMBIssues
- SaRA
- okr_SMB
- manage_licenses
- commerce
search.appverid:
- MET150
description: Handleiding over het toewijzen van licenties aan gebruikers.
ms.openlocfilehash: 3622be180ae622d5d08066cc03773a8175fe9342
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398155"
---
# <a name="assign-licenses-to-users"></a>Licenties aan gebruikers toewijzen

U kunt licenties toewijzen aan gebruikers op de pagina **Actieve gebruikers** of op de pagina **Licenties**. De methode die u gebruikt, is afhankelijk van of u productlicenties wilt toewijzen aan specifieke gebruikers of gebruikerslicenties wilt toewijzen aan een specifiek product.

> [!NOTE]
> Als beheerder kunt u geen licenties toewijzen of verwijderen voor een self-service aankoopabonnement dat door een gebruiker in uw organisatie is gekocht. U kunt [self-service aankoopabonnementen overnemen](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription)en vervolgens licenties toewijzen of opheffen.

[Informatie over het toevoegen van een gebruiker en tegelijkertijd toewijzen van een licentie](../add-users/add-users.md).

## <a name="before-you-begin"></a>Voordat u begint

- U moet algemeen, licentie-, of gebruikersbeheerder zijn om licenties toe te wijzen. Zie [Over beheerdersrollen in Microsoft 365](../add-users/about-admin-roles.md) voor meer informatie.
- U kunt [licenties toewijzen aan gebruikersaccounts met Office 365 PowerShell](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md).
- Voor groepslicenties, zie [Licenties toewijzen aan gebruikers op basis van groepslidmaatschap in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign)
- Sommige services, zoals Sway, worden automatisch aan gebruikers toegewezen.Het is niet nodig deze afzonderlijk toe te wijzen.

## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a>Gebruik de pagina Licenties om licenties aan gebruikers toe te wijzen

Met behulp van de pagina **Licenties** kunt u licenties voor een specifiek product toewijzen aan maximaal 20 gebruikers. Op de pagina **Licenties** wordt een lijst weergegeven met alle producten waarvoor u een abonnement hebt. U ziet ook het totale aantal licenties voor elk product, het aantal toegewezen licenties en het aantal beschikbare licenties.

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenties</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">beheercentrum</a> naar de pagina **Facturering** > **Licenties**.
::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">beheercentrum</a> naar de pagina **Facturering** > **Licenties**.

::: moniker-end

2. Selecteer een product.
3. Selecteer **Licenties toewijzen** op de pagina met productdetails.
4. Begin in het deelvenster **Licenties toewijzen aan gebruikers** met het typen van een naam en kies de naam in de resultaten om deze aan de lijst toe te voegen. U kunt maximaal 20 gebruikers tegelijk toevoegen.
4. Selecteer **Apps en services in- of uitschakelen** om de toegang tot bepaalde items toe te wijzen of te verwijderen.
6. Wanneer u klaar bent, selecteert u achtereenvolgens **Toewijzen** en **Sluiten**.

Als er een conflict is, wordt er een bericht weergegeven waarin wordt uitgelegd wat het probleem is en hoe u dit kunt oplossen. Als u bijvoorbeeld licenties hebt geselecteerd die conflicterende services bevatten, moet u de services die bij elke licentie zijn opgenomen controleren en het opnieuw proberen.

## <a name="change-the-apps-and-services-a-user-has-access-to"></a>De apps en services wijzigen waartoe een gebruiker toegang heeft

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenties</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">beheercentrum</a> naar de pagina **Facturering** > **Licenties**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">beheercentrum</a> naar de pagina **Facturering** > **Licenties**.

::: moniker-end

2. Selecteer op de pagina **Licenties** de rij voor een specifieke gebruiker.
3. Selecteer of deselecteer in het rechterdeelvenster de apps en services waarvoor u toegang wilt verlenen of verwijderen.
4. Wanneer u klaar bent, selecteert u achtereenvolgens **Opslaan** en **Sluiten**.

## <a name="use-the-active-users-page-to-assign-licenses"></a>Licenties toewijzen met de pagina Actieve gebruikers

Wanneer u de pagina **Actieve gebruikers** gebruikt om licenties toe te wijzen, wijst u gebruikerslicenties aan producten toe.

### <a name="assign-licenses-to-multiple-users"></a>Licenties toewijzen aan meerdere gebruikers

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">beheercentrum</a> naar de pagina **Facturering** > **Actieve gebruikers**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">beheercentrum</a> naar de pagina **Facturering** > **Actieve gebruikers**.

::: moniker-end

2. Selecteer de cirkels naast de namen van de gebruikers aan wie u licenties wilt toewijzen.
3. Selecteer bovenaan **Meer opties (...)** en selecteer vervolgens **Productlicenties beheren**.
4. Selecteer in het deelvenster **Productlicenties beheren** **Toevoegen aan bestaande productlicentietoewijzingen** \> **Volgende**.
5. Zet de wisselknop in het deelvenster **Toevoegen aan bestaande producten** op **Aan** voor de licentie die u wilt toewijzen aan de geselecteerde gebruikers.\
    De standaardinstelling is dat alle services die zijn gekoppeld aan die licenties, automatisch worden toegewezen aan de gebruikers. U kunt beperken welke services beschikbaar zijn voor de gebruikers. Zet de wisselknoppen op **Uit** voor de services waarvan de gebruikers geen gebruik mogen maken.
6. Selecteer onderaan het deelvenster **Toevoegen** \> **Sluiten**.  

### <a name="assign-licenses-to-one-user"></a>Licenties aan een enkele gebruiker toewijzen

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">beheercentrum</a> naar de pagina **Facturering** > **Actieve gebruikers**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">beheercentrum</a> naar de pagina **Facturering** > **Actieve gebruikers**.

::: moniker-end

2. Selecteer de rij van de gebruiker aan wie u een licentie wilt toewijzen.
3. Selecteer in het rechterdeelvenster **Licenties en apps**.
4. Vouw de sectie **Licenties** uit en schakel de selectievakjes in voor de licenties die u wilt toewijzen. Selecteer vervolgens **Wijzigingen opslaan**.

## <a name="assign-a-license-to-a-guest-user"></a>Een licentie toewijzen aan een gastgebruiker

U kunt gastgebruikers uitnodigen om samen te werken met uw organisatie in het Azure Active Directory-beheercentrum. Raadpleeg [Wat is gastgebruikerstoegang in Azure Active Directory B2B?](/azure/active-directory/external-identities/what-is-b2b) voor meer informatie over gastgebruikers. Raadpleeg [Snelstart: Gastgebruikers toevoegen aan uw adreslijst in de Azure-portal](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal) als u geen gastgebruikers hebt.

> [!IMPORTANT]
> U moet een globale beheerder zijn om deze stappen uit te voeren.

1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Azure Active Directory-beheercentrum</a>
2. Kies **Gebruikers** in het navigatiedeelvenster.
3. Kies **Filters toevoegen** op de pagina **Gebruikers | Alle gebruikers (Preview)**.
4. Kies **Gebruikerstype** in het menu **Een veld kiezen** en vervolgens **Toepassen**.
5. Kies **Gast** in het volgende menu.
6. Kies in de lijst met resultaten de gebruiker die een licentie nodig heeft.
7. Kies **Licenties** onder **Beheren**.
8. Kies **Opdrachten**.
9. Kies het product waarvoor u een licentie wilt toewijzen op de pagina **Licentietoewijzingen bijwerken**.
10. Schakel aan de rechterkant de selectievakjes uit voor de services waarvoor u wilt dat de gastgebruiker geen toegang heeft.
11. Kies **Opslaan**.

## <a name="next-steps"></a>Volgende stappen

Als de Office-apps nog niet door uw gebruikers zijn geïnstalleerd, kunt u de [Aan de slag-handleiding voor werknemers](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) delen met uw gebruikers om dingen in te stellen, zoals [Microsoft 365 of Office 2019 op een pc of Mac downloaden en installeren](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) en [Office-apps en e-mail op een mobiel apparaat instellen](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).

## <a name="related-content"></a>Verwante onderwerpen

[Informatie over abonnementen en licenties](../../commerce/licenses/subscriptions-and-licenses.md) (artikel)\
[Licenties van gebruikers intrekken](remove-licenses-from-users.md) (artikel)\
[Licenties kopen of intrekken voor uw abonnement](../../commerce/licenses/buy-licenses.md) (artikel)