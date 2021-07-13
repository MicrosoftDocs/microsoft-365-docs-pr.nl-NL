---
title: Beheerdersrollen toewijzen aan de Microsoft 365-beheercentrum
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- okr_smb
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: eac4d046-1afd-4f1a-85fc-8219c79e1504
description: Lees hoe u beheerdersrollen kunt toewijzen aan een gebruiker of meerdere gebruikers in uw bedrijf, zodat ze specifieke taken kunnen uitvoeren in het beheercentrum.
ms.openlocfilehash: 575d1d8c6b0ffce40877fb41d28df82c24e84d04
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393773"
---
# <a name="assign-admin-roles"></a>Beheerdersrollen toewijzen

Als u de persoon bent die uw Microsoft Business-abonnement heeft gekocht, bent u de globale beheerder. Dit betekent dat u onbeperkte controle hebt over de producten in uw abonnementen en dat u toegang hebt tot de meeste gegevens.

Zie[Over beheerdersrollen](about-admin-roles.md) voor meer informatie.

Wanneer u nieuwe gebruikers toevoegt, als u ze geen beheerdersrol toewijst, zijn ze in de gebruikersrol en hebben ze geen beheerdersbevoegdheden aan een van de Microsoft-beheercentra.  Maar als u hulp nodig hebt om dingen voor elkaar te krijgen, kunt u een beheerdersrol toewijzen aan een gebruiker. Als u bijvoorbeeld iemand nodig hebt om wachtwoorden opnieuw in te stellen, moet u deze persoon niet de rol van globale beheerder toewijzen, maar de rol van wachtwoordbeheerder toewijzen. Te veel globale beheerders, met onbeperkte toegang tot uw gegevens en onlinezaken, is een beveiligingsrisico.

## <a name="watch-add-an-adminbrbr"></a>Kijken: Een beheerder toevoegen<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfO] 

Als je deze video nuttig vond, raadpleeg dan de [complete reeks trainingen voor kleine bedrijven en nieuwe gebruikers van Microsoft 365](../../business-video/index.yml).

## <a name="assign-admin-roles"></a>Beheerdersrollen toewijzen 

U kunt gebruikers op twee verschillende manieren aan een rol toewijzen:

- U kunt naar de details van de gebruiker gaan en Rollen **beheren om** een rol toe te wijzen aan de gebruiker.
- U kunt ook naar **Rollen** gaan en de rol selecteren en er vervolgens meerdere gebruikers aan toevoegen.

### <a name="assign-admin-roles-to-users-using-roles"></a>Beheerdersrollen toewijzen aan gebruikers met rollen

1. Ga in het beheercentrum naar **Rollen.** Kies de **tabbladen Azure AD** of **Intune** om de beheerdersrollen te bekijken die beschikbaar zijn voor uw organisatie.
2. Selecteer de beheerdersrol aan wie u de gebruiker wilt toewijzen.
3. Selecteer **Toegewezen beheerders**  >  **toevoegen.**
4. Typ de weergavenaam of **gebruikersnaam** van de gebruiker **en** selecteer de gebruiker in de lijst met suggesties.
5. Voeg meerdere gebruikers toe totdat u klaar bent.
6. Selecteer **Opslaan** en vervolgens wordt de gebruiker toegevoegd aan de lijst met toegewezen beheerders.

### <a name="assign-a-user-to-an-admin-role-from-active-users"></a>Een gebruiker toewijzen aan een beheerdersrol van Actieve gebruikers

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar **de pagina Gebruikers** actieve > [gebruikers.](https://go.microsoft.com/fwlink/p/?linkid=834822)

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar de pagina **Gebruikers** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar de pagina **Gebruikers** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.

::: moniker-end

2. Selecteer op **de pagina** Actieve gebruikers de gebruiker van wie u de beheerdersrol wilt wijzigen. Selecteer in het deelvenster Flyout onder **Rollen** de optie **Rollen beheren.**

3. Selecteer de beheerdersrol die u aan de gebruiker wilt toewijzen. Als u de rol die u zoekt niet ziet, **selecteert** u Alles onder aan de lijst bekijken.

## <a name="assign-admin-roles-to-multiple-users"></a>Beheerdersrollen toewijzen aan meerdere gebruikers

Zie Rollen toewijzen aan gebruikersaccounts met PowerShell als u PowerShell [kent.](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md) Dit is ideaal voor het toewijzen van rollen aan honderden gebruikers.
  
Voer de volgende instructies uit als u rollen wilt toewijzen aan tientallen gebruikers.

## <a name="check-admin-roles-in-your-organization"></a>Beheerdersrollen controleren in uw organisatie

Mogelijk hebt u niet de juiste machtigingen om beheerdersrollen toe te wijzen aan andere gebruikers. Controleer of u de juiste machtigingen hebt of vraag een andere beheerder om rollen voor u toe te wijzen.

U kunt beheerdersrolmachtigingen op twee verschillende manieren controleren:

- U kunt naar de details van de gebruiker gaan en kijken onder **Rollen** op de **pagina Account.**
- U kunt ook naar **Rollen gaan en** de beheerdersrol selecteren en toegewezen beheerders selecteren om te zien welke gebruikers zijn toegewezen.

## <a name="related-content"></a>Verwante inhoud

[Over Microsoft 365 beheerdersrollen](about-admin-roles.md) (artikel)\
[Beheerdersrolmachtigingen in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) (artikel)\
[Rollen toewijzen aan gebruikersaccounts met PowerShell](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md) (artikel)\
[Partnerrelaties machtigen of verwijderen](../misc/add-partner.md) (artikel)