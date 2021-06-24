---
title: Geblokkeerde gebruikers verwijderen uit de portal voor gebruikers met beperkte rechten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe ze gebruikers kunnen verwijderen van de pagina voor gebruikers met beperkte rechten in de Microsoft 365 Defender-portal. Gebruikers worden toegevoegd aan de portal voor gebruikers met beperkte rechten voor het verzenden van uitgaande spam, meestal vanwege een inbreuk op het account.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 924db948103a4d3b45c499f433961762a45931af
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082850"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-microsoft-365"></a>Geblokkeerde gebruikers verwijderen uit de portal voor gebruikers met beperkte rechten in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Als een gebruiker een van de uitgaande verzendlimieten overschrijdt zoals beschreven in [de service-limieten](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) of in [uitgaande spambeleid](configure-the-outbound-spam-policy.md), is het verzenden van e-mail door de gebruiker beperkt, maar kunnen ze wel e-mail ontvangen.

De gebruiker wordt toegevoegd aan de pagina voor **gebruikers met beperkte rechten** in de Microsoft 365 Defender-portal. Wanneer ze een e-mailbericht proberen te verzenden, wordt het bericht teruggestuurd in een rapport over niet-uitgevoerde bezorging (ook wel een NDR genoemd of niet-bezorgd berichten) met de foutcode [5.1.8](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) en de volgende tekst:

> 'Uw bericht kan niet worden bezorgd omdat u niet als een geldige afzender bent herkend. De meest voorkomende reden hiervoor is dat het e-mailadres verdacht is van het verzenden van spam en dat er geen e-mail meer mag worden verzonden.  Neemt u contact op met de beheerder voor hulp. Externe server retourneerde '550 5.1.8 Toegang geweigerd, slechte uitgaande afzender.'

Beheerders kunnen gebruikers verwijderen van de pagina voor gebruikers met beperkte rechten in Microsoft 365 Defender of in Exchange Online PowerShell.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent de Microsoft 365 Defender-portal bij <https://security.microsoft.com>. Als u rechtstreeks naar de pagina voor **gebruikers met beperkte rechten** wilt gaan, gebruikt u <https://security.microsoft.com/restrictedusers>.

- Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als je verbinding wilt maken met Exchange Online PowerShell.

- U moet over toegewezen machtigingen beschikken in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:
  - Als u gebruikers wilt verwijderen uit de portal voor gebruikers met beperkte rechten, moet u lid zijn van de rollengroep **Organisatiebeheer** of **Beveiligingsadministrator**.
  - Voor alleen-lezen toegang tot de portal voor gebruikers met beperkte rechten, moet u lid zijn van de rollengroep **Globale lezer** of **Beveiligingslezer**.

  Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.

  > [!NOTE]
  >
  > - Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.
  >
  > - De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.

- Een afzender die de uitgaande e-maillimieten overschrijdt, is een indicator van een verdacht account. Voordat u de gebruiker verwijdert uit de portal voor gebruikers met beperkte rechten, moet u de vereiste stappen volgen om het beheer van het account te herstellen. Zie voor meer informatie [Reageren op een verdacht e-mailaccount in Office 365](responding-to-a-compromised-email-account.md).

## <a name="use-the-microsoft-365-defender-portal-to-remove-a-user-from-the-restricted-users-list"></a>Ga naar de Microsoft 365 Defender-portal om een gebruiker te verwijderen uit de lijst met gebruikers met beperkte rechten

1. Ga in de Microsoft 365 Defender-portal naar **E-mail en samenwerking** > **Controleren** > **Gebruikers met beperkte rechten**.

2. Zoek en selecteer op de pagina **Gebruikers met beperkte rechten** de gebruiker die u wilt deblokkeren door op de gebruiker te klikken.

3. Klik op de actie **Deblokkeren** die wordt weergegeven.

4. Ga naar de flyout **Gebruiker deblokkeren** die wordt weergegeven, en lees de details over het account met beperkte rechten. Neem de aanbevelingen door om er zeker van te zijn dat u de juiste acties onderneemt voor het geval dat het account werkelijk is gecompromitteerd.

   Wanneer u klaar bent, klikt u op **Volgende**.

5. Het volgende scherm biedt aanbevelingen om toekomstige inbreuk te voorkomen. Het inschakelen van meervoudige verificatie (MFA) en het opnieuw instellen van het wachtwoord zijn een goede verdediging.

   Wanneer u gereed bent, klikt u op **Verzenden**.

6. Klik op **Ja** ter bevestiging.

   > [!NOTE]
   > Het kan tot 24 uur duren voordat alle beperkingen voor de gebruiker zijn verwijderd.

## <a name="verify-the-alert-settings-for-restricted-users"></a>De instellingen voor de waarschuwing voor gebruikers met beperkte toegang verifiëren

In het standaard waarschuwingsbeleid genaamd **Gebruiker beperkt tot het verzenden van e-mail** worden beheerders automatisch gewaarschuwd wanneer gebruikers geblokkeerd zijn bij het verzend van e-mailberichten. U kunt deze instellingen controleren en aanvullende gebruikers toevoegen om op de hoogte te stellen. Zie voor meer informatie over waarschuwingsbeleid, [Waarschuwingsbeleid in Microsoft 365](../../compliance/alert-policies.md).

> [!IMPORTANT]
> Om meldingen te laten werken, moet zoeken in het auditlogboek zijn ingeschakeld. Voor meer informatie, zie [Auditlogboeken zoeken in- of uitschakelen](../../compliance/turn-audit-log-search-on-or-off.md).

1. Ga in de Microsoft 365 Defender-portal naar **E-mail en samenwerking** \> **Beleidsregels** \> **Waarschuwingsbeleid**.

2. Zoek en selecteer op de pagina **Waarschuwingsbeleid** de waarschuwing met de naam **Gebruiker heeft beperkte rechten voor het verzenden van e-mail**. U kunt de beleidsregels sorteren op naam of het **zoekvak** gebruiken om het beleid te vinden.

3. In de flyout **Gebruiker heeft beperkte rechten voor het verzenden van e-mail** die wordt weergegeven, controleert of configureert u de volgende instellingen:
   - **Status**: Controleer of de waarschuwing is ingesteld op ![Wisselknop aan](../../media/scc-toggle-on.png).
   - **Geadresseerden**: Klik op **Bewerken** en controleer of configureer de volgende instellingen in het snelmenu **Geadresseerden bewerken**:
     - **E-mailmeldingen verzenden**: Controleer of dit is ingeschakeld (**Aan**).
     - **Geadresseerden**: de standaardwaarde is **HuurderBeheerders** (betekenis, **wereldwijde beheerder** leden). Als u meer geadresseerden wilt toevoegen, klikt u in een leeg gebied van het vak. Een lijst met geadresseerden wordt weergegeven en u kunt een naam typen om een geadresseerde te filteren en te selecteren. U kunt een bestaande geadresseerde verwijderen uit het vak door te klikken op ![Pictogram verwijderen](../../media/m365-cc-sc-remove-selection-icon.png) naast de naam.
     - **Dagelijkse meldingslimiet**: de standaardwaarde is **Geen limiet** maar u kunt een limiet selecteren voor het maximum aantal meldingen per dag.

     Klik op **Opslaan** wanneer u gereed bent.

4. Wanneer u terug bent de doorlopende informatie **Gebruiker valt onder beperkte verzending van e-mail**, klikt u op **Sluiten**.

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a>Exchange Online PowerShell gebruiken om gebruikers weer te geven en te verwijderen uit de lijst met gebruikers met beperkte rechten

Voer de volgende opdracht uit om deze lijst weer te geven met gebruikers die geen e-mail kunnen verzenden:

```powershell
Get-BlockedSenderAddress
```

Als u meer informatie over een specifieke gebruiker wilt bekijken, vervangt u \<emailaddress\> door het e-mailadres van die gebruiker en voert u de volgende opdracht uit:

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

Zie [OntvangAdresGeblokkeerdeVerzender](/powershell/module/exchange/get-blockedsenderaddress) voor gedetailleerde syntaxis- en parameterinformatie.

Als u een gebruiker wilt verwijderen uit de lijst met gebruikers met beperkte rechten, vervangt u \<emailaddress\> door het e-mailadres van die gebruiker en voert u de volgende opdracht uit:

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

Zie [VerwijderAdresGeblokkeerdeVerzender](/powershell/module/exchange/remove-blockedsenderaddress) voor gedetailleerde syntaxis- en parameterinformatie.
