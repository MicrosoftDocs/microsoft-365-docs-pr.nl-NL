---
title: Licenties aan gebruikers toewijzen
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- TopSMBIssues
- SaRA
- okr_SMB
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Handleiding over het toewijzen van licenties aan gebruikers.
ms.date: 08/14/2020
ms.openlocfilehash: ec2f9ae2e580987266c636343a66d7c21138e4c3
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645129"
---
# <a name="assign-licenses-to-users"></a>Licenties aan gebruikers toewijzen

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

::: moniker range="o365-worldwide"

U kunt licenties toewijzen aan gebruikers op de pagina **Actieve gebruikers** of op de pagina **Licenties**. De methode die u gebruikt, is afhankelijk van of u productlicenties wilt toewijzen aan specifieke gebruikers of gebruikerslicenties wilt toewijzen aan een specifiek product.

::: moniker-end

[Informatie over het toevoegen van een gebruiker en tegelijkertijd toewijzen van een licentie](../add-users/add-users.md).

## <a name="before-you-begin"></a>Voordat u begint

- U moet algemeen, licentie-, of gebruikersbeheerder zijn om licenties toe te wijzen. Zie [Over beheerdersrollen in Microsoft 365](../add-users/about-admin-roles.md) voor meer informatie.
- U kunt [licenties toewijzen aan gebruikersaccounts met Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?linkid=850410).
- Voor groepslicenties, zie [Licenties toewijzen aan gebruikers op basis van groepslidmaatschap in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)
- Sommige services, zoals Sway, worden automatisch aan gebruikers toegewezen.Het is niet nodig deze afzonderlijk toe te wijzen.

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a>Gebruik de pagina Licenties om licenties aan gebruikers toe te wijzen

Met behulp van de pagina **Licenties** kunt u licenties voor een specifiek product toewijzen aan maximaal 20 gebruikers. Op de pagina **Licenties** wordt een lijst weergegeven met alle producten waarvoor u een abonnement hebt. U ziet ook het totale aantal licenties voor elk product, het aantal toegewezen licenties en het aantal beschikbare licenties.

1. Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenties</a>.
2. Selecteer een product.
3. Selecteer **Licenties toewijzen** op de pagina met productdetails.
4. Begin in het deelvenster **Licenties toewijzen aan gebruikers** met het typen van een naam en kies de naam in de resultaten om deze aan de lijst toe te voegen. U kunt maximaal 20 gebruikers tegelijk toevoegen.
5. Selecteer **Apps en services in- of uitschakelen** om de toegang tot bepaalde items toe te wijzen of te verwijderen.
6. Wanneer u klaar bent, selecteert u achtereenvolgens **Toewijzen** en **Sluiten**.

Als er een conflict is, wordt er een bericht weergegeven waarin wordt uitgelegd wat het probleem is en hoe u dit kunt oplossen. Als u bijvoorbeeld licenties hebt geselecteerd die conflicterende services bevatten, moet u de services die bij elke licentie zijn opgenomen controleren en het opnieuw proberen.

## <a name="change-the-apps-and-services-a-user-has-access-to"></a>De apps en services wijzigen waartoe een gebruiker toegang heeft

1. Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenties</a>.
2. Selecteer op de pagina **Licenties** de rij voor een specifieke gebruiker.
3. Selecteer of deselecteer in het rechterdeelvenster de apps en services waarvoor u toegang wilt verlenen of verwijderen.
4. Wanneer u klaar bent, selecteert u achtereenvolgens **Opslaan** en **Sluiten**.

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-assign-licenses"></a>Licenties toewijzen met de pagina Actieve gebruikers

Wanneer u de pagina **Actieve gebruikers** gebruikt om licenties toe te wijzen, wijst u gebruikerslicenties aan producten toe.

### <a name="assign-licenses-to-multiple-users"></a>Licenties toewijzen aan meerdere gebruikers

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.
2. Selecteer de cirkels naast de namen van de gebruikers aan wie u licenties wilt toewijzen.
3. Selecteer bovenaan **Meer opties (...)** en selecteer vervolgens **Productlicenties beheren**.
4. Selecteer in het deelvenster **Productlicenties beheren** **Toevoegen aan bestaande productlicentietoewijzingen** \> **Volgende**.
5. Zet de wisselknop in het deelvenster **Toevoegen aan bestaande producten** op **Aan** voor de licentie die u wilt toewijzen aan de geselecteerde gebruikers.\
    De standaardinstelling is dat alle services die zijn gekoppeld aan die licenties, automatisch worden toegewezen aan de gebruikers. U kunt beperken welke services beschikbaar zijn voor de gebruikers. Zet de wisselknoppen op **Uit** voor de services waarvan de gebruikers geen gebruik mogen maken.
6. Selecteer onderaan het deelvenster **Toevoegen** \> **Sluiten**.  

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-multiple-users"></a>Licenties toewijzen aan meerdere gebruikers

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.
2. Vink de selectievakjes aan naast de namen van de gebruikers aan wie u licenties wilt toewijzen.
3. Selecteer in het deelvenster **Bulkacties** de optie **Productlicenties bewerken**.
4. Selecteer in het deelvenster **Producten toewijzen** **Toevoegen aan bestaande productlicentietoewijzingen** \> ** Volgende**.
5. Zet de wisselknop op **Aan** voor de licenties die u wilt toewijzen aan de geselecteerde gebruikers.\
    De standaardinstelling is dat alle services die zijn gekoppeld aan die licenties, automatisch worden toegewezen aan de gebruikers. U kunt beperken welke services beschikbaar zijn voor de gebruikers. Zet de wisselknoppen op **Uit** voor de services waarvan de gebruikers geen gebruik mogen maken.
6. Selecteer onderaan in het deelvenster **Toevoegen aan bestaande producten** **Toevoegen** \> **Sluiten** \> **Sluiten**.

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-multiple-users"></a>Licenties toewijzen aan meerdere gebruikers

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.
2. Vink de selectievakjes aan naast de namen van de gebruikers aan wie u licenties wilt toewijzen.
3. Selecteer in het deelvenster **Bulkacties** de optie **Productlicenties bewerken**.
4. Selecteer in het deelvenster **Producten toewijzen** **Toevoegen aan bestaande productlicentietoewijzingen** \> ** Volgende**.
5. Zet de wisselknop op **Aan** voor de licenties die u wilt toewijzen aan de geselecteerde gebruikers.\
    De standaardinstelling is dat alle services die zijn gekoppeld aan die licenties, automatisch worden toegewezen aan de gebruikers. U kunt beperken welke services beschikbaar zijn voor de gebruikers. Zet de wisselknoppen op **Uit** voor de services waarvan de gebruikers geen gebruik mogen maken.
6. Selecteer onderaan in het deelvenster **Toevoegen aan bestaande producten** **Toevoegen** \> **Sluiten** \> **Sluiten**.

::: moniker-end

::: moniker range="o365-worldwide"

### <a name="assign-licenses-to-one-user"></a>Licenties aan een enkele gebruiker toewijzen

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.
2. Selecteer de rij van de gebruiker aan wie u een licentie wilt toewijzen.
3. Selecteer in het rechterdeelvenster **Licenties en apps**.
4. Vouw de sectie **Licenties** uit en schakel de selectievakjes in voor de licenties die u wilt toewijzen. Selecteer vervolgens **Wijzigingen opslaan**.

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-one-user"></a>Licenties aan een enkele gebruiker toewijzen

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.
2. Vink het selectievakje aan naast de naam van de gebruiker aan wie u een licentie wilt toewijzen.
3. Selecteer de optie **Bewerken** in het rechterdeelvenster in de rij **Productlicenties**.
4. Zet in het deelvenster **Productlicenties** de wisselknop op **Aan** voor de licentie die u aan deze gebruiker wilt toewijzen.\
    De standaardinstelling is dat alle services die zijn gekoppeld aan die licentie, automatisch worden toegewezen aan de gebruiker. U kunt beperken welke services beschikbaar zijn voor de gebruiker. Zet de wisselknoppen op **Uit** voor de services waarvan die gebruiker geen gebruik mag maken.
5. Selecteer onderaan het deelvenster **Productlicenties** de opties **Opslaan** \> **Sluiten** \> **Sluiten**.

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-one-user"></a>Licenties aan een enkele gebruiker toewijzen

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.
2. Vink het selectievakje aan naast de naam van de gebruiker aan wie u een licentie wilt toewijzen.
3. Selecteer de optie **Bewerken** in het rechterdeelvenster in de rij **Productlicenties**.
4. Zet in het deelvenster **Productlicenties** de wisselknop op **Aan** voor de licentie die u aan deze gebruiker wilt toewijzen.\
    De standaardinstelling is dat alle services die zijn gekoppeld aan die licentie, automatisch worden toegewezen aan de gebruiker. U kunt beperken welke services beschikbaar zijn voor de gebruiker. Zet de wisselknoppen op **Uit** voor de services waarvan die gebruiker geen gebruik mag maken.
5. Selecteer onderaan het deelvenster **Productlicenties** de opties **Opslaan** \> **Sluiten** \> **Sluiten**.

::: moniker-end

## <a name="assign-a-license-to-a-guest-user"></a>Een licentie toewijzen aan een gastgebruiker

U kunt gastgebruikers uitnodigen om samen te werken met uw organisatie in Azure Active Directory-Beheercentrum. Raadpleeg [Wat is gastgebruikerstoegang in Azure Active Directory B2B?](https://docs.microsoft.com/azure/active-directory/external-identities/what-is-b2b) voor meer informatie over gastgebruikers. Raadpleeg [Snelstart: Gastgebruikers toevoegen aan uw adreslijst in de Azure-portal](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal) als u geen gastgebruikers hebt.

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