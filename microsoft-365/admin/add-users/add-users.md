---
title: Gebruikers toevoegen en licenties toewijzen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365_Setup
- Adm_O365_TOC
ms.custom:
- okr_smb
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Informatie over het tegelijkertijd toevoegen van gebruikers en het toewijzen van licenties aan Microsoft 365.
ms.date: 07/01/2020
ms.openlocfilehash: a7c5fcf1a129a1d434b6e641688ce4c5d234817d
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760000"
---
# <a name="add-users-and-assign-licenses-at-the-same-time"></a>Tegelijkertijd gebruikers toevoegen en licenties toewijzen

De personen in uw team hebben elk een gebruikersaccount nodig voordat ze zich kunnen aanmelden en toegang hebben tot [Microsoft 365 voor Bedrijven](https://www.microsoft.com/microsoft-365/business). De eenvoudigste manier om gebruikersaccounts toe te voegen, is om ze één voor één toe te voegen in het Microsoft 365-beheercentrum. Nadat u deze stap hebt uitgevoerd, hebben uw gebruikers Microsoft 365-licenties, aanmeldingsreferenties en Microsoft 365-postvakken.

## <a name="before-you-begin"></a>Voordat u begint

U moet een globale, licentie- of gebruikersbeheerder zijn om gebruikers toe te voegen en licenties toe te wijzen. Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.

## <a name="watch-add-users-in-the-admin-center"></a>Bekijk: Gebruikers toevoegen in het beheercentrum

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]

> [!NOTE]
> De stappen in de video laten een ander beginpunt zien voor het toevoegen van gebruikers, maar de resterende stappen zijn hetzelfde als de volgende procedure.

## <a name="add-users-one-at-a-time"></a>Gebruikers één voor één toevoegen

 ::: moniker range="o365-worldwide"

1. Ga naar het beheercentrum op <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Ga naar het beheercentrum op <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga naar het beheercentrum op <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.

::: moniker-end 

2. Ga naar **Gebruikers**  >  **Actieve gebruikers** en selecteer **Gebruiker toevoegen**.
3. Vul de basisgegevens in het deelvenster **Basisinformatie instellen** in en selecteer vervolgens **Volgende**.
    - **Naam** Vul de voor- en achternaam, weergavenaam en gebruikersnaam in.
    - **Domein** Kies het domein voor het account van de gebruiker. Als de gebruikersnaam van de gebruiker bijvoorbeeld Wander is en zijn domein contoso.com, dan zal hij zich aanmelden met wander@contoso.com.
    - **Wachtwoordinstellingen** Kies ervoor om het automatisch gegenereerde wachtwoord te gebruiken of maak zelf een sterk wachtwoord voor de gebruiker.
    - Gebruikers moeten hun wachtwoord na 90 dagen wijzigen. U kunt ook de optie **Laat deze persoon zijn wachtwoord wijzigen bij de volgende aanmelding** inschakelen.
    - Kies of u het wachtwoord in een e-mail wilt verzenden wanneer de gebruiker is toegevoegd.
4. Selecteer in het deelvenster **Productlicenties toewijzen** de locatie en de geschikte licentie voor de gebruiker. Als u geen beschikbare licenties hebt, kunt u nog steeds een gebruiker toevoegen en extra licenties kopen. Vouw **Apps** uit en selecteer of deselecteer apps om de apps te beperken waarvoor de gebruiker een licentie heeft. Selecteer **Volgende**.
5. Vouw in het venster **Optionele instellingen** **Rollen** uit als u van deze gebruiker een beheerder wilt maken en vouw **Profielgegevens** uit als u extra informatie over de gebruiker wilt toevoegen.
6. Selecteer **Volgende**, controleer de instellingen van de nieuwe gebruiker, breng de gewenste wijzigingen aan en selecteer vervolgens **Toevoegen voltooien** en **Sluiten**.

## <a name="add-multiple-users-at-the-same-time"></a>Verschillende gebruikers tegelijkertijd toevoegen

U kunt een van de volgende methoden gebruiken om meerdere gebruikers tegelijk toe te voegen:

- **Gebruik een spreadsheet om personen bulksgewijs toe te voegen.** Zie [Meerdere gebruikers tegelijk toevoegen](../../enterprise/add-several-users-at-the-same-time.md).
- **Automatiseer het toevoegen van accounts en het toewijzen van licenties.** Zie [Gebruikersaccounts maken met Microsoft 365 PowerShell](../../enterprise/create-user-accounts-with-microsoft-365-powershell.md). Kies deze methode als u al vertrouwd bent met het gebruik van Windows PowerShell-cmdlets.
- **Gebruikt u ActiveDirectory?** [Adreslijstsynchronisatie voor Microsoft 365 instellen](../../enterprise/set-up-directory-synchronization.md). Gebruik het hulpprogramma Azure Active Directory Connect om Active Directory-gebruikersaccounts (en andere Active Directory-objecten) te repliceren in Microsoft 365. Tijdens de synchronisatie worden alleen de gebruikersaccounts toegevoegd. U moet licenties toewijzen aan de gesynchroniseerde gebruikers voordat ze e-mail en andere Office-apps kunnen gebruiken.
- **Migreert u vanuit Exchange?** Zie [Manieren om meerdere e-mailaccounts naar Office 365 te migreren](/Exchange/mailbox-migration/mailbox-migration). Wanneer u meerdere postvakken naar Microsoft 365 wilt migreren met behulp van een cutover-, gefaseerde of een hybride Exchange-methode, voegt u gebruikers automatisch als onderdeel van de migratie toe. Tijdens de migratie worden alleen de gebruikersaccounts toegevoegd. U moet licenties toewijzen aan de gebruikers voordat ze e-mail en andere Office-apps kunnen gebruiken. Als u geen licentie toewijst aan een gebruiker, wordt het postvak uitgeschakeld na een respijtperiode van 30 dagen. Ontdek hoe u [licenties aan gebruikers kunt toewijzen](../manage/assign-licenses-to-users.md) via het Microsoft 365-beheercentrum.

## <a name="next-steps"></a>Volgende stappen

Nadat u een gebruiker toevoegt, krijgt u een e-mailmelding van Microsoft. Het e-mailbericht bevat de gebruikers-id en het wachtwoord van de persoon, zodat deze zich kan aanmelden bij Microsoft 365. Gebruik het gangbare proces voor het doorgeven van wachtwoorden. Deel de [Aan de slag-handleiding voor werknemers](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) met uw gebruikers om dingen in te stellen, zoals [Office-apps op een pc of Mac downloaden en installeren](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) en [Office-apps en e-mail op een mobiel apparaat instellen](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).

## <a name="related-content"></a>Verwante onderwerpen

[Een nieuwe werknemer toevoegen aan Microsoft 365](add-new-employee.md) (artikel)\
[Meerdere gebruikers tegelijk toevoegen aan Microsoft 365](../../enterprise/add-several-users-at-the-same-time.md) (artikel)\
[Een gebruiker herstellen in Microsoft 365](restore-user.md) (artikel)\
[Licenties toewijzen aan gebruikers](../manage/assign-licenses-to-users.md) (artikel)\
[Een gebruiker uit uw organisatie verwijderen](delete-a-user.md) (artikel)\