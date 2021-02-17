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
description: Beheerders kunnen meer informatie krijgen over het verwijderen van gebruikers uit de portal voor gebruikers met beperkte rechten in Office 365. Gebruikers worden toegevoegd aan de portal gebruikers met beperkte rechten voor het verzenden van uitgaande spam, meestal vanwege een inbreuk op het account.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1ba5334689ad58c8a50864a3618c0972b61dfd7f
ms.sourcegitcommit: a9ac702c9efc9defded3bfa65618b94bac00c237
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/16/2021
ms.locfileid: "50261547"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-office-365"></a>Geblokkeerde gebruikers verwijderen uit de portal voor gebruikers met beperkte rechten in Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Als een gebruiker een van de uitgaande verzendlimieten overschrijdt zoals beschreven in [de service-limieten](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) of in [uitgaande spambeleid](configure-the-outbound-spam-policy.md), is het verzenden van e-mail door de gebruiker beperkt, maar kunnen ze wel e-mail ontvangen.

De gebruiker wordt toegevoegd aan de portal voor gebruikers met beperkte rechten in het beveiligings- en compliancecentrum. Wanneer ze een e-mailbericht proberen te verzenden, wordt het bericht teruggestuurd in een rapport over niet-uitgevoerde bezorging (ook wel een NDR genoemd of niet-bezorgd berichten) met de foutcode [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) en de volgende tekst:

> 'Uw bericht kan niet worden bezorgd omdat u niet als een geldige afzender bent herkend. De meest voorkomende reden hiervoor is dat het e-mailadres verdacht is van het verzenden van spam en dat er geen e-mail meer mag worden verzonden.  Neemt u contact op met de beheerder voor hulp. Externe server retourneerde '550 5.1.8 Toegang geweigerd, slechte uitgaande afzender.'

Beheerders kunnen gebruikers verwijderen uit de portal met beperkte verzenders in het beveiligings- en compliancecentrum of in Exchange Online PowerShell.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de pagina met **Beperkte gebruikers** wilt gaan, gebruik dan <https://protection.office.com/restrictedusers>.

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als je verbinding wilt maken met Exchange Online PowerShell.

- Je moet beschikken over toegewezen machtigingen voor het uitvoeren van de procedures in dit onderwerp:
  - Als je gebruikers wilt verwijderen uit de portal voor gebruikers met beperkte rechten, moet je lid zijn van de functiegroep **Organisatiebeheer** of **Beveiligingsbeheer**.
  - Voor alleen-lezentoegang tot de portal met beperkte gebruikers moet je lid zijn van de functiegroep **Global Reader** of **Beveiligingslezer**.

  Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

  > [!NOTE]
  >
  > - Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen in het Beveiligings- en compliancecentrum _en_ machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.
  >
  > - De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.

- Een afzender die de uitgaande e-maillimieten overschrijdt, is een indicator van een verdacht account. Voordat u de gebruiker verwijdert uit de portal met beperkte gebruikers, moet u de vereiste stappen volgen om het beheer van het account te herstellen. Zie voor meer informatie [Reageren op een verdacht e-mailaccount in Office 365](responding-to-a-compromised-email-account.md).

## <a name="use-the-security--compliance-center-to-remove-a-user-from-the-restricted-users-list"></a>Ga naar het beveiligings- en compliancecentrum om een gebruiker te verwijderen uit de lijst met beperkte gebruikers

1. Ga in het beveiligings- en compliancecentrum naar **Risicobeheer** \> **Bekijken** \> **Quarantaine**.

2. Zoek en selecteer de gebruiker die u wilt deblokkeren. Klik in de kolom **Acties** op **Blokkering opheffen**.

3. Er wordt een doorlopende informatie weergeven over het account waarvan de verzending beperkt is. Neem de aanbevelingen door om er zeker van te zijn dat u de juiste acties neemt voor het geval dat het account werkelijk is aangetast. Selecteer **Volgende** indien afgerond.

4. Het volgende scherm biedt aanbevelingen om toekomstige inbreuk te voorkomen. Meervoudige verificatie (MFA) inschakelen en de wachtwoorden wijzigen, is een goed beveiligingsmiddel. Klik op **Blokkering opheffen van gebruikers** indien afgerond.

5. Klik op **Ja** ter bevestiging.

   > [!NOTE]
   > Het kan tot 24 uur duren voordat alle beperkingen voor de gebruiker zijn verwijderd.

## <a name="verify-the-alert-settings-for-restricted-users"></a>De instellingen voor de waarschuwing voor gebruikers met beperkte toegang verifiëren

In het standaard waarschuwingsbeleid genaamd **Gebruiker beperkt tot het verzenden van e-mail** worden beheerders automatisch gewaarschuwd wanneer gebruikers geblokkeerd zijn bij het verzend van e-mailberichten. U kunt deze instellingen controleren en aanvullende gebruikers toevoegen om op de hoogte te stellen. Zie voor meer informatie over waarschuwingsbeleid, [Waarschuwingsbeleid in het beveiligings- en compliancecentrum](../../compliance/alert-policies.md).

> [!IMPORTANT]
> Om meldingen te laten werken, moet zoeken in het auditlogboek zijn ingeschakeld. Voor meer informatie, zie [Auditlogboeken zoeken in- of uitschakelen](../../compliance/turn-audit-log-search-on-or-off.md).

1. Ga in het beveiligings- en compliancecentrum naar **Waarschuwingen** \> **Waarschuwingsbeleid**.

2. Zoek en selecteer de waarschuwing **Gebruiker mag geen e-mai sturen**-waarschuwing.

3. In de doorlopende informatie die wordt weergegeven, controleert of configureert u de volgende instellingen:

   - **Status**: Controleer of de waarschuwing is ingesteld op ![Wisselknop aan](../../media/scc-toggle-on.png).

   - **Geadresseerden**: Klik op **Bewerken** en controleer of configureer de volgende instellingen in het snelmenu **Geadresseerden bewerken**:

     - **E-mailmeldingen verzenden**: Controleer of het selectievakje is ingeschakeld (**Aan**).

     - **Geadresseerden**: de standaardwaarde is **HuurderBeheerders** (betekenis, **wereldwijde beheerder** leden). Als u meer geadresseerden wilt toevoegen, klikt u in een leeg gebied van het vak. Een lijst met geadresseerden wordt weergegeven en u kunt een naam typen om een geadresseerde te filteren en te selecteren. U kunt een bestaande geadresseerde verwijderen uit het vak door te klikken op ![Pictogram verwijderen](../../media/scc-remove-icon.png) naast de naam.

     - **Dagelijkse meldingslimiet**: de standaardwaarde is **Geen limiet** maar u kunt een limiet selecteren voor het maximum aantal meldingen per dag.

     Klik op **Opslaan** wanneer u gereed bent.

4. Wanneer u terug bent de doorlopende informatie **Gebruiker valt onder beperkte verzending van e-mail**, klikt u op **Sluiten**.

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a>Exchange Online PowerShell gebruiken om gebruikers weer te geven en te verwijderen uit de lijst met beperkte gebruikers

Voer de volgende opdracht uit om deze lijst weer te geven met gebruikers die geen e-mail kunnen verzenden:

```powershell
Get-BlockedSenderAddress
```

Als u meer informatie over een specifieke gebruiker wilt bekijken, vervangt u \<emailaddress\> door het e-mailadres van die gebruiker en voert u de volgende opdracht uit:

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

Zie [OntvangAdresGeblokkeerdeVerzender](https://docs.microsoft.com/powershell/module/exchange/get-blockedsenderaddress) voor gedetailleerde syntaxis- en parameterinformatie.

Als u een gebruiker wilt verwijderen uit de lijst met beperkte gebruikers, vervangt u \<emailaddress\> door het e-mailadres van die gebruiker en voert u de volgende opdracht uit:

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

Zie [VerwijderAdresGeblokkeerdeVerzender](https://docs.microsoft.com/powershell/module/exchange/remove-blockedsenderaddress) voor gedetailleerde syntaxis- en parameterinformatie.
