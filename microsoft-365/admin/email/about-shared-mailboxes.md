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
search.appverid:
- BCS160
- MET150
- MOE150
description: Gedeelde postvakken worden gebruikt wanneer meerdere personen toegang tot hetzelfde postvak nodig hebben. Meer informatie over wat u moet weten voordat u een gedeeld postvak maakt.
ms.openlocfilehash: fcdbb591e5b8f9b2c5490435b68e543c17a035a0
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629105"
---
# <a name="about-shared-mailboxes"></a>Meer over gedeelde postvakken

Gedeelde postvakken worden gebruikt als meerdere mensen toegang tot hetzelfde postvak nodig hebben, zoals bedrijfsgegevens, ondersteuningsadressen, recepties of andere functies die gedeeld worden door meerdere mensen.

Gebruikers met machtigingen voor het groepspostvak kunnen verzenden als of namens het groeps-e-mailadres als de beheerder die gebruiker daarvoor heeft gemachtigd. Dit is vooral handig voor hulp en ondersteuning postvakken omdat gebruikers e-mails kunnen verzenden van "Contoso Support" of "Building A Reception Desk.

Voordat u [een gedeeld postvak maakt,](create-a-shared-mailbox.md)zijn hier enkele dingen die u moet weten.

- **Licenties:** Uw gedeelde postvak kan tot 50 GB aan gegevens opslaan zonder dat u er een licentie aan toestelt. Als u meer gegevens wilt opslaan, dient u er een licentie aan toe te wijzen. Zie [Exchange Online-limieten](https://technet.microsoft.com/library/exchange-online-limits.aspx#StorageLimits)voor meer informatie over licenties voor gedeelde postvak . Als de opslaglimiet voor een gedeeld postvak wordt bereikt, kunt u nog enige tijd e-mail ontvangen, maar geen nieuwe e-mail meer verzenden. Vervolgens kunt u ook geen e-mail meer ontvangen. Afzenders ontvangen dan een bewijs dat hun e-mail niet kan worden bezorgd.

- **Gebruikersmachtigingen:** U moet gebruikers machtigingen (lidmaatschap) geven om het gedeelde postvak te gebruiken. Alleen personen binnen uw organisatie kunnen een gedeeld postvak gebruiken.

- **Externe gebruikers:** Je mensen buiten je bedrijf (zoals mensen met een Gmail-account) geen toegang geven tot je gedeelde postvak. Als u dat toch wilt doen, kunt u een groep voor Outlook maken. Zie [Een Microsoft 365-groep maken in het beheercentrum](../create-groups/create-groups.md)voor meer informatie.

-  **Gebruiken met Outlook:** Naast het gebruik van Outlook in de web vanuit uw browser om toegang te krijgen tot gedeelde postvakken, u ook de Outlook voor iOS-app of de Outlook voor Android-app gebruiken. Zie Een <a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">gedeeld postvak toevoegen aan Outlook Mobile</a>voor meer informatie. Een andere optie is het maken van een groep voor uw gedeelde postvak. Zie [Groepen vergelijken voor](../create-groups/compare-groups.md)meer informatie .  

- **Versleuteling:** U e-mail die vanuit een gedeeld postvak wordt verzonden, niet versleutelen. Dit komt omdat een gedeeld postvak geen eigen beveiligingscontext heeft (gebruikersnaam/wachtwoord), zodat het geen sleutel kan worden toegewezen. Als meer dan één persoon lid is en ze e-mails verzenden/ontvangen die ze met hun eigen sleutels hebben versleuteld, kunnen andere leden de e-mail lezen en anderen mogelijk niet, afhankelijk van met welke openbare sleutel de e-mail is versleuteld.

- **Postvakconversie:** U postvakken van gebruikers converteren naar gedeelde postvakken. Zie [Het postvak van een gebruiker converteren naar een gedeeld postvak](convert-user-mailbox-to-shared-mailbox.md).

- **Beheerdersrollen:** Gebruikers met algemene beheerders- of Exchange-beheerdersrollen kunnen gedeelde postvakken maken.

- **Abonnementsvereisten:** Als u een gedeeld postvak wilt maken, moet u zich abonneren op een Microsoft 365 voor bedrijven-abonnement met e-mail (de Exchange Online-service). Het Microsoft 365 Apps for Business-abonnement bevat geen e-mail. Microsoft 365 Business Standard wel.

- **Aanmelden:** Een gedeeld postvak is niet bedoeld voor directe aanmelding door het gekoppelde gebruikersaccount. Je moet altijd aanmelden voor het gedeelde postvakaccount blokkeren en blokkeren.

- **Te veel gebruikers:** Wanneer er te veel aangewezen gebruikers gelijktijdig toegang hebben tot een gedeeld postvak, kunnen ze met tussenpozen geen verbinding maken met dit postvak. In dit geval u overwegen het aantal gebruikers te verminderen of een andere workload te gebruiken, zoals een Microsoft 365-groep of openbare map.

- **Bericht verwijderen:** Helaas u niet voorkomen dat mensen berichten verwijderen in een gedeeld postvak. De enige manier om dit te omzeilen is het maken van een Microsoft 365-groep in plaats van een gedeeld postvak. Een groep in Outlook is als een gedeeld postvak. Zie [Groepen vergelijken voor](../create-groups/compare-groups.md)een vergelijking van de twee . Zie [Meer informatie over groepen voor](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2.aspx) meer informatie over groepen

## <a name="related-articles"></a>Verwante artikelen

[Een gedeeld postvak maken](create-a-shared-mailbox.md)

[Een gedeeld postvak configureren](configure-a-shared-mailbox.md)

[Een gebruikerspostvak converteren naar een gedeeld postvak](convert-user-mailbox-to-shared-mailbox.md)

[Een licentie uit een gedeeld postvak verwijderen](remove-license-from-shared-mailbox.md)

[Problemen oplossen met gedeelde postvakken](resolve-issues-with-shared-mailboxes.md)
