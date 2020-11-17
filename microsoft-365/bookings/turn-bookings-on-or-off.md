---
title: Microsoft bookings in-of uitschakelen
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: Meer informatie over het verkrijgen van toegang tot Microsoft bookings in Microsoft 365.
ms.openlocfilehash: 7e4eaa1e474f3f49807b842097c855193f028af0
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126589"
---
# <a name="turn-microsoft-bookings-on-or-off"></a>Microsoft bookings in-of uitschakelen

U kunt bookings in-of uitschakelen voor uw gehele organisatie of voor specifieke gebruikers. Wanneer u Bookings voor gebruikers inschakelt, kan hij of zij een Bookings pagina maken, een agenda maken en andere personen de tijd boek stellen.

> [!NOTE]
> De besturingselementen voor beheerders die in deze secties worden beschreven, zijn niet beschikbaar voor Office 365, beheerd door 21Vianet (China)-klanten.

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a>Bookings in-of uitschakelen voor uw organisatie met behulp van het Microsoft 365-Beheercentrum

1. Meld u aan bij het Microsoft 365-Beheercentrum als globale beheerder.

2. Ga in het Beheercentrum naar  **instellingen**   \> **org** en selecteer **Bookings**.

3. Schakel het selectievakje in om **ervoor te zorgen dat uw organisatie** reserveringen in-of uitschakelt voor uw organisatie.

   > [!NOTE]
   > Als u reserveringen uitschakelt, wordt alle toegang tot de service, waaronder het maken en beheren van Bookings pagina's, uitgeschakeld.

4. Selecteer **Save Changes**.

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a>Bookings in-of uitschakelen voor uw organisatie met behulp van PowerShell

[Maak verbinding met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) en voer de volgende opdracht uit om bookings in of uit te schakelen voor uw organisatie met behulp van de PowerShell [-cmdlet Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig).

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a>Bookings uitschakelen voor individuele gebruikers

U kunt Bookings uitschakelen voor individuele gebruikers.

1. Ga naar het Microsoft 365-Beheercentrum en selecteer **gebruikers** met \> **actieve gebruikers**.

1. Selecteer de gewenste gebruiker en selecteer vervolgens **licenties en apps**.

1. Vouw **apps** uit en wis het selectievakje voor Microsoft bookings.

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a>Goedkeuring van personeelsleden vereisen voordat beschikbaarheidsinfo wordt gedeeld

Beheerders kunnen werknemers in hun organisatie vragen zich aan te melden voordat ze hun beschikbaarheidsgegevens delen via Bookings en voordat ze kunnen worden bookable via een reserverings pagina. Deze instelling is beschikbaar in het Microsoft 365-Beheercentrum onder **instellingen voorinstellingen** \> **Settings** \> **Bookings**.

Wanneer deze instelling is ingeschakeld, vinden werknemers die zijn toegevoegd als medewerkers in de boekings agenda's, een koppeling goedkeuren/weigeren in de e-mail melding die ze ontvangen.

Deze functie wordt geleidelijk ter wereld ingevoerd voor klanten van Microsoft 365. Als u deze optie niet ziet in het Microsoft 365-Beheercentrum, kom dan binnenkort terug.

## <a name="block-social-sharing-options"></a>Opties voor sociale delen blokkeren

Beheerders kunnen bepalen hoe boekings pagina's worden gedeeld op sociale netwerken. Deze instelling is beschikbaar in het Microsoft 365-Beheercentrum onder **instellingen voorinstellingen** \> **Settings** \> **Bookings**.

Deze functie wordt geleidelijk ter wereld ingevoerd voor klanten van Microsoft 365. Als u deze optie niet ziet in het Microsoft 365-Beheercentrum, kom dan binnenkort terug.

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a>Alleen geselecteerde gebruikers toestaan om boekings agenda's te maken

Door beleidsbeperkingen te gebruiken, kunt u instellen dat gebruikers met een licentie geen Bookings-agenda's kunnen maken. U dient eerst Bookings te activeren voor de hele organisatie. Alle gebruikers in uw organisatie hebben wel een boekings licentie, maar alleen de gebruikers in het beleid kunnen Bookings-agenda's maken en volledig bepalen wie er toegang heeft tot de agenda's die ze maken.

Gebruikers die deel uitmaken van dit beleid, kunnen nieuwe boekings agenda's maken en kunnen als werknemers aan de gewenste capaciteit (waaronder de rol van de beheerder) worden toegevoegd aan bestaande Bookings-agenda's. Gebruikers die geen deel uitmaken van dit beleid, kunnen geen nieuwe boekings agenda's maken en er wordt een foutbericht weergegeven wanneer ze dit proberen.

U moet de volgende opdrachten uitvoeren met Exchange Online PowerShell. Zie [verbinding maken met Exchange Online PowerShell (verbinding maken met Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)) voor meer informatie over het uitvoeren van cmdlets voor Exchange Online.

> [!IMPORTANT]
> In de volgende stappen wordt ervan uitgegaan dat er geen ander postvak beleid van Outlook Web app (OWA) in uw organisatie is gemaakt.

1. Maak een nieuw postvak beleid voor gebruikers die toestemming hebben om Bookings-agenda's te maken. (Het maken van een agenda via Bookings is standaard toegestaan voor nieuw postvak beleid.)

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   Zie [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy)voor meer informatie.

2. Wijs dit beleid toe aan de relevante gebruikers door deze opdracht uit te voeren voor elke gebruiker die u wilt machtigen om Bookings-agenda's te maken.

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   Zie [Set-CASMailbox](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox)voor meer informatie.

3. Optioneel: Voer deze opdracht uit als u de reserveringen wilt uitschakelen voor alle andere gebruikers in uw organisatie.

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   Zie [set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy)voor meer informatie.

Raadpleeg de volgende onderwerpen voor meer informatie over het gebruik van OWA-postvak beleidsregels:

- [Een postvak beleid voor de webversie van Outlook maken in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [Beleidsregels voor het postvak van de webversie van Outlook op een postvak in Exchange Online toepassen of verwijderen](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)
