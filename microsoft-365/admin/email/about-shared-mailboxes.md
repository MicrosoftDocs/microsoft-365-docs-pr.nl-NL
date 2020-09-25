---
title: Meer over gedeelde postvakken
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Gedeelde postvakken worden gebruikt wanneer meerdere personen toegang hebben tot hetzelfde postvak. Meer informatie over wat u moet weten voordat u een gedeeld postvak maakt.
ms.openlocfilehash: f6feae1662093ffea2537a62c5e8fdf28c622166
ms.sourcegitcommit: 96b4593becc9450af136c528844e858c6e88b5a9
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/25/2020
ms.locfileid: "48269347"
---
# <a name="about-shared-mailboxes"></a>Meer over gedeelde postvakken

Gedeelde postvakken worden gebruikt als meerdere mensen toegang tot hetzelfde postvak nodig hebben, zoals bedrijfsgegevens, ondersteuningsadressen, recepties of andere functies die gedeeld worden door meerdere mensen.

Gebruikers met machtigingen voor het groepspostvak kunnen verzenden als of namens het groeps-e-mailadres als de beheerder die gebruiker daarvoor heeft gemachtigd. Dit is bijzonder handig voor helpdesk- en ondersteuningspostvakken, omdat gebruikers e-mails kunnen verzenden vanuit 'Contoso-ondersteuning' of 'Receptie gebouw A'.

Voordat u [een gedeeld postvak maakt](create-a-shared-mailbox.md), vindt u hier enkele zaken die u moet weten:

- **Licenties:** Met uw gedeelde Postvak kunt u 50 GB gegevens opslaan zonder dat u een licentie toewijst. Als u meer gegevens wilt opslaan, dient u er een licentie aan toe te wijzen. Zie [limieten voor Exchange Online](https://technet.microsoft.com/library/exchange-online-limits.aspx#StorageLimits)voor meer informatie over licenties voor het gebruik van een gedeeld postvak. Als de opslaglimiet voor een gedeeld postvak wordt bereikt, kunt u nog enige tijd e-mail ontvangen, maar geen nieuwe e-mail meer verzenden. Vervolgens kunt u ook geen e-mail meer ontvangen. Afzenders ontvangen dan een bewijs dat hun e-mail niet kan worden bezorgd.

- **Gebruikersmachtigingen:** Als u het gedeelde postvak wilt gebruiken, moet u gebruikersmachtigingen (lidmaatschap) verlenen. Alleen personen binnen uw organisatie kunnen een gedeeld postvak gebruiken.

- **Externe gebruikers:** U kunt personen van buiten uw bedrijf, zoals gebruikers met een Gmail-account, geen toegang geven tot uw gedeelde Postvak. Als u dat toch wilt doen, kunt u een groep voor Outlook maken. Zie [een Microsoft 365-groep maken in het Beheercentrum](../create-groups/create-groups.md)voor meer informatie.

-  **Gebruiken met Outlook:** U kunt niet alleen de webversie van Outlook vanuit uw browser gebruiken voor toegang tot gedeelde postvakken, maar ook de app Outlook voor iOS of de app Outlook voor Android. Zie <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">een gedeeld postvak toevoegen aan Outlook Mobile</a>voor meer informatie. Een andere optie is om een groep voor uw gedeelde Postvak te maken. Zie [Groepen vergelijken](../create-groups/compare-groups.md)voor meer informatie.  

- **Versleuteling:** U kunt vanuit een gedeeld postvak verzonden e-mail niet versleutelen. Dit komt doordat een gedeeld postvak geen eigen beveiligingscontext (gebruikersnaam/wachtwoord) heeft, zodat er geen sleutel kan worden toegewezen. Als meer dan één persoon een lid is en ze berichten verzenden/ontvangen die ze hebben versleuteld met hun eigen toetsen, kunnen andere leden het e-mailbericht misschien wel lezen en ook niet op andere leden, afhankelijk van de openbare sleutel waarop het e-mailbericht is versleuteld.

- **Postvak conversie:** U kunt gebruikerspostvakken converteren naar gedeelde postvakken. Zie [Het postvak van een gebruiker converteren naar een gedeeld postvak](convert-user-mailbox-to-shared-mailbox.md).

- **Beheerdersrollen:** Gebruikers met globale beheerder of Exchange-beheerdersrollen kunnen gedeelde postvakken maken.

- **Vereisten voor het abonnement:** Als u een gedeeld postvak wilt maken, moet u een abonnement nemen op een Microsoft 365 voor bedrijven-abonnement dat e-mail bevat (de Exchange Online-service). In het Microsoft 365 apps voor bedrijven-abonnement is geen e-mail inbegrepen. Microsoft 365 Business Standard omvat ook e-mail.

- **Aanmelden:** Een gedeeld postvak is niet bedoeld voor direct aanmelden door het bijbehorende gebruikersaccount. U moet de aanmelding altijd blokkeren voor het account van het gedeelde Postvak en deze blokkeren behouden.

- **Te veel gebruikers:** Wanneer er te veel bepaalde gebruikers toegang hebben tot een gedeeld postvak, kunnen ze soms niet langer verbinding maken met dit postvak. In dit geval kunt u het aantal gebruikers verminderen of een andere werkbelasting gebruiken, bijvoorbeeld een Microsoft 365-groep of een openbare map.

- **Bericht verwijderen:** Helaas kunt u niet voorkomen dat mensen berichten in een gedeeld postvak verwijderen. De enige manier om dit te maken is door een Microsoft 365-groep te maken in plaats van een gedeeld postvak. Een groep in Outlook lijkt op een gedeeld postvak. Zie [Groepen vergelijken](../create-groups/compare-groups.md)voor een vergelijking van de twee. Zie meer [informatie over groepen](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)voor meer informatie over groepen.

## <a name="related-articles"></a>Verwante artikelen

[Een gedeeld postvak maken](create-a-shared-mailbox.md)

[Een gedeeld postvak configureren](configure-a-shared-mailbox.md)

[Een gebruikerspostvak converteren naar een gedeeld postvak](convert-user-mailbox-to-shared-mailbox.md)

[Een licentie uit een gedeeld postvak verwijderen](remove-license-from-shared-mailbox.md)

[Problemen oplossen met gedeelde postvakken](resolve-issues-with-shared-mailboxes.md)
