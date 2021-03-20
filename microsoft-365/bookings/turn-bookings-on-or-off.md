---
title: Microsoft Bookings in- of uitschakelen
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: Lees hoe u toegang krijgt tot Microsoft Bookings in Microsoft 365.
ms.openlocfilehash: 7b1582a480ac4fdcd5a131febcc59450aa13e299
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913764"
---
# <a name="turn-microsoft-bookings-on-or-off"></a>Microsoft Bookings in- of uitschakelen

Boekingen kunnen worden in- of uitgeschakeld voor uw hele organisatie of voor specifieke gebruikers. Wanneer u Bookings voor gebruikers int, kunnen ze een bookings-pagina maken, een agenda maken en andere personen toestaan om tijd met hen te boeken.

> [!NOTE]
> De beheerbesturingselementen die in deze secties worden beschreven, zijn niet beschikbaar voor Office 365 Beheerd door klanten van 21Vianet (China).

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a>Bookings in- of uitschakelen voor uw organisatie met behulp van het Microsoft 365-beheercentrum

1. Meld u als globale beheerder aan bij het Microsoft 365-beheercentrum.

2. Ga in het beheercentrum naar  **Instellingen**   \> **Organisatie-instellingen** en selecteer **Bookings**.

3. Schakel het selectievakje in voor **Toestaan dat uw organisatie Bookings** gebruikt om Bookings voor uw organisatie in of uit te schakelen.

   > [!NOTE]
   > Als u Bookings uit schakelt, wordt alle toegang tot de service uitgeschakeld, inclusief het maken en beheren van Bookings-pagina's.

4. Selecteer **Wijzigingen opslaan.**

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a>Bookings in- of uitschakelen voor uw organisatie met PowerShell

Als u Bookings voor uw organisatie wilt in- of uitschakelen met behulp van de PowerShell-cmdlet [Set-OrganizationConfig,](/powershell/module/exchange/set-organizationconfig)Verbinding maken met [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) en de volgende opdracht uitvoeren:

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a>Bookings in- of uitschakelen voor individuele gebruikers

U kunt Bookings uitschakelen voor afzonderlijke gebruikers.

1. Ga naar het Microsoft 365-beheercentrum en selecteer **gebruikers** \> **actieve gebruikers.**

1. Selecteer de gewenste gebruiker en selecteer **vervolgens Licenties en apps.**

1. Vouw **Apps uit** en het selectievakje voor Microsoft Bookings uit.

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a>Goedkeuring van personeel vereisen voordat u gratis/drukke informatie deelt

Beheerders kunnen werknemers in hun organisatie verplichten zich aan te geven voordat hun beschikbaarheidsgegevens worden gedeeld via Bookings en voordat ze kunnen worden geboekt via een boekingspagina. Deze instelling is beschikbaar in het Microsoft 365-beheercentrum onder **Instellingen** \> **Instellingen** \> **Bookings**.

Wanneer deze instelling is ingeschakeld, vinden werknemers die zijn toegevoegd als personeel in boekingsagenda's een koppeling Goedkeuren/weigeren in de e-mailmelding die ze ontvangen.

Deze functie wordt geleidelijk wereldwijd uitgerold voor Klanten van Microsoft 365. Als u deze optie niet ziet in het Microsoft 365-beheercentrum, gaat u snel terug.

## <a name="block-social-sharing-options"></a>Opties voor sociaal delen blokkeren

Beheerders kunnen bepalen hoe boekingspagina's worden gedeeld op sociale netwerken. Deze instelling is beschikbaar in het Microsoft 365-beheercentrum onder **Instellingen** \> **Instellingen** \> **Bookings**.

Deze functie wordt geleidelijk wereldwijd uitgerold voor Klanten van Microsoft 365. Als u deze optie niet ziet in het Microsoft 365-beheercentrum, gaat u snel terug.

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a>Alleen geselecteerde gebruikers toestaan Bookings-agenda's te maken

Met beleidsbeperkingen kunt u voorkomen dat gebruikers met een licentie Bookings-agenda's kunnen maken. U moet eerst Bookings inschakelen voor uw hele organisatie. Alle gebruikers in uw organisatie hebben Bookings-licenties, maar alleen gebruikers die in het beleid zijn opgenomen, kunnen Bookings-agenda's maken en hebben volledige controle over wie toegang heeft tot de agenda's die ze maken.

Gebruikers die in dit beleid zijn opgenomen, kunnen nieuwe Bookings-agenda's maken en kunnen als personeel in elke capaciteit (inclusief de beheerdersrol) worden toegevoegd aan bestaande Bookings-agenda's. Gebruikers die niet in dit beleid zijn opgenomen, kunnen geen nieuwe Bookings-agenda's maken en ontvangen een foutbericht als ze dit proberen.

U moet de volgende opdrachten uitvoeren met Exchange Online PowerShell. Zie Verbinding maken met Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)voor meer informatie over het uitvoeren van Exchange Online-cmdlets.

> [!IMPORTANT]
> In de onderstaande stappen wordt ervan uitgenomen dat er geen ander OWA-postvakbeleid (Outlook Web App) is gemaakt in uw organisatie.

1. Maak een nieuw postvakbeleid voor gebruikers die Bookings-agenda's mogen maken. (Het maken van een Boekingskalender is standaard toegestaan door nieuw postvakbeleid.)

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   Zie [New-OwaMailboxPolicy voor meer informatie.](/powershell/module/exchange/new-owamailboxpolicy)

2. Wijs dit beleid toe aan de relevante gebruikers door deze opdracht uit te voeren voor elke gebruiker die u toestemming wilt geven om Bookings-agenda's te maken.

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   Zie [Set-CASMailbox voor](/powershell/module/exchange/set-casmailbox)meer informatie.

3. Optioneel: Voer deze opdracht uit als u Bookings wilt uitschakelen voor alle andere gebruikers in uw organisatie.

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   Zie [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy)voor meer informatie.

Zie de volgende onderwerpen voor meer informatie over OWA-postvakbeleid:

- [Een beleid voor postvak in Outlook op het web maken in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [Een beleid voor outlook op het webpostvak toepassen of verwijderen op een postvak in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)