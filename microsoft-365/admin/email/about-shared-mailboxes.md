---
title: Meer over gedeelde postvakken
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
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
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: Gedeelde postvakken worden gebruikt wanneer meerdere personen toegang nodig hebben tot hetzelfde postvak. Lees wat u moet weten voordat u een gedeeld postvak maakt.
ms.openlocfilehash: f5d46af5abdd528ce3db817dbabce015ed5abade
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094719"
---
# <a name="about-shared-mailboxes"></a>Meer over gedeelde postvakken

Gedeelde postvakken worden gebruikt als meerdere mensen toegang tot hetzelfde postvak nodig hebben, zoals bedrijfsgegevens, ondersteuningsadressen, recepties of andere functies die gedeeld worden door meerdere mensen.

Gebruikers met machtigingen voor het groepspostvak kunnen verzenden als of namens het groeps-e-mailadres als de beheerder die gebruiker daarvoor heeft gemachtigd. Dit is bijzonder handig voor helpdesk- en ondersteuningspostvakken, omdat gebruikers e-mails kunnen verzenden vanuit 'Contoso-ondersteuning' of 'Receptie gebouw A'.

Voordat u [een gedeeld postvak maakt,](create-a-shared-mailbox.md)zijn dit enkele dingen die u moet weten:

- **Licenties:** In uw gedeelde postvak kan maximaal 50 GB aan gegevens worden opgeslagen zonder dat u er een licentie aan toewijst. Als u meer gegevens wilt opslaan, dient u er een licentie aan toe te wijzen. Zie Limieten voor Exchange Online voor meer informatie over licenties [voor gedeelde postvakken.](https://technet.microsoft.com/library/exchange-online-limits.aspx#StorageLimits) Als de opslaglimiet voor een gedeeld postvak wordt bereikt, kunt u nog enige tijd e-mail ontvangen, maar geen nieuwe e-mail meer verzenden. Vervolgens kunt u ook geen e-mail meer ontvangen. Afzenders ontvangen dan een bewijs dat hun e-mail niet kan worden bezorgd.

- **Gebruikersmachtigingen:** U moet gebruikers machtigingen (lidmaatschap) geven om het gedeelde postvak te kunnen gebruiken. Alleen personen binnen uw organisatie kunnen een gedeeld postvak gebruiken.

- **Externe gebruikers:** U kunt personen buiten uw bedrijf (zoals personen met een Gmail-account) geen toegang tot uw gedeelde postvak geven. Als u dat toch wilt doen, kunt u een groep voor Outlook maken. Zie Een [Microsoft 365-groep maken in het beheercentrum voor meer informatie.](../create-groups/create-groups.md)

- **Gebruiken met Outlook:** U kunt niet alleen de webversie van Outlook vanuit uw browser gebruiken voor toegang tot gedeelde postvakken, maar ook de Outlook voor iOS-app of de app Outlook voor Android. Zie Een gedeeld postvak toevoegen [aan Outlook Mobile voor meer informatie.](https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f) U kunt ook een groep maken voor uw gedeelde postvak. Zie Groepen vergelijken voor [meer informatie.](../create-groups/compare-groups.md)

- **Versleuteling:** U kunt vanuit een gedeeld postvak verzonden e-mail niet versleutelen. Een gedeeld postvak heeft namelijk geen eigen beveiligingscontext (gebruikersnaam/wachtwoord) en kan dus niet aan een sleutel worden toegewezen. Als meer dan één persoon lid is en e-mailberichten verzendt/ontvangt die deze persoon met zijn of haar eigen sleutels heeft versleuteld, kunnen andere leden de e-mail mogelijk wel lezen en anderen mogelijk niet, afhankelijk van de openbare sleutel waarmee het e-mailbericht is versleuteld.

- **Postvakconversie:** U kunt gebruikerspostvakken converteren naar gedeelde postvakken. Zie [Het postvak van een gebruiker converteren naar een gedeeld postvak](convert-user-mailbox-to-shared-mailbox.md).

- **Beheerdersrollen:** Gebruikers met globale beheerders- of Exchange-beheerdersrollen kunnen gedeelde postvakken maken.

- **Abonnementsvereisten:** Als u een gedeeld postvak wilt maken, moet u zich abonneren op een Microsoft 365 voor Bedrijven-abonnement dat e-mail bevat (de Exchange Online-service). Het abonnement op Microsoft 365 Apps voor bedrijven bevat geen e-mail. Microsoft 365 Business Standard bevat wel e-mail.

- **Aanmelden:** Een gedeeld postvak is niet bedoeld voor directe aanmelding door het bijbehorende gebruikersaccount. U moet aanmelding voor het gedeelde postvakaccount altijd blokkeren en dit geblokkeerd houden.

- **Te veel gebruikers:** Wanneer er te veel aangewezen gebruikers tegelijk toegang hebben tot een gedeeld postvak, kunnen ze af en toe geen verbinding maken met dit postvak. In dit geval kunt u het aantal gebruikers verminderen of een andere werkbelasting gebruiken, zoals een Microsoft 365-groep of een openbare map.

- **Bericht verwijderen:** U kunt helaas niet voorkomen dat personen berichten uit een gedeeld postvak verwijderen. U kunt dit alleen maar doen door een Microsoft 365-groep te maken in plaats van een gedeeld postvak. Een groep in Outlook is net een gedeeld postvak. Zie Groepen vergelijken voor [een vergelijking.](../create-groups/compare-groups.md) Zie Meer informatie over groepen voor meer informatie [over groepen.](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)


> [!NOTE]
> Voor toegang tot een gedeeld postvak moet een gebruiker een Exchange Online-licentie hebben, maar voor het gedeelde postvak is geen afzonderlijke licentie vereist. Elk gedeeld postvak heeft een bijbehorend gebruikersaccount. Is het u opgevallen dat u niet werd gevraagd een wachtwoord in te voeren toen u het gedeelde postvak maakte? Het account heeft een wachtwoord, maar dat wordt gegenereerd door het systeem (onbekend). U mag het account niet gebruiken om u aan te melden bij het gedeelde postvak. Zonder licentie zijn gedeelde postvakken beperkt tot 50 GB. Als u de limiet wilt verhogen naar 100 GB, moet aan het gedeelde postvak een licentie voor Exchange Online (Abonnement 2) of een licentie voor Exchange Online (Abonnement 1) met een invoeglicentie voor Exchange Online Archiving zijn toegewezen. Hiermee kunt u ook automatisch uitv breidende archivering inschakelen voor een onbeperkte hoeveelheid archiefopslagcapaciteit. Als u een gedeeld postvak in een juridische procedure wilt plaatsen, moet het gedeelde postvak ook een licentie voor Exchange Online (Abonnement 2) of een licentie voor Exchange Online (Abonnement 1) hebben met een invoeglicentie voor Exchange Online Archiving. Als u geavanceerde functies wilt toepassen, zoals Microsoft Defender voor Office 365, Geavanceerd eDiscovery of automatisch bewaarbeleid, moet het gedeelde postvak een licentie voor deze functies hebben.

## <a name="related-articles"></a>Verwante artikelen

[Een gedeeld postvak maken](create-a-shared-mailbox.md)

[Een gedeeld postvak configureren](configure-a-shared-mailbox.md)

[Een gebruikerspostvak converteren naar een gedeeld postvak](convert-user-mailbox-to-shared-mailbox.md)

[Een licentie uit een gedeeld postvak verwijderen](remove-license-from-shared-mailbox.md)

[Problemen oplossen met gedeelde postvakken](resolve-issues-with-shared-mailboxes.md)
