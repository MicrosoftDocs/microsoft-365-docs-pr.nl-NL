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
ms.openlocfilehash: 83e779d59a8e763b3d0c0482966e75604d5f1574
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903212"
---
# <a name="about-shared-mailboxes"></a>Meer over gedeelde postvakken

Gedeelde postvakken worden gebruikt als meerdere mensen toegang tot hetzelfde postvak nodig hebben, zoals bedrijfsgegevens, ondersteuningsadressen, recepties of andere functies die gedeeld worden door meerdere mensen.

Gebruikers met machtigingen voor het groepspostvak kunnen verzenden als of namens het groeps-e-mailadres als de beheerder die gebruiker daarvoor heeft gemachtigd. Dit is bijzonder handig voor helpdesk- en ondersteuningspostvakken, omdat gebruikers e-mails kunnen verzenden vanuit 'Contoso-ondersteuning' of 'Receptie gebouw A'.

Voordat u [een gedeeld postvak maakt,](create-a-shared-mailbox.md)zijn hier enkele dingen die u moet weten:

- **Licenties:** Uw gedeelde postvak kan maximaal 50 GB aan gegevens opslaan zonder dat u er een licentie aan toewijst. Als u meer gegevens wilt opslaan, dient u er een licentie aan toe te wijzen. Zie Limieten voor Exchange Online voor meer informatie over licenties voor [gedeelde postvakken.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#StorageLimits) Als de opslaglimiet voor een gedeeld postvak wordt bereikt, kunt u nog enige tijd e-mail ontvangen, maar geen nieuwe e-mail meer verzenden. Vervolgens kunt u ook geen e-mail meer ontvangen. Afzenders ontvangen dan een bewijs dat hun e-mail niet kan worden bezorgd.

- **Gebruikersmachtigingen:** U moet gebruikers machtigingen (lidmaatschap) geven om het gedeelde postvak te kunnen gebruiken. Alleen personen binnen uw organisatie kunnen een gedeeld postvak gebruiken.

- **Externe gebruikers:** U kunt personen buiten uw bedrijf (zoals personen met een Gmail-account) geen toegang geven tot uw gedeelde postvak. Als u dat toch wilt doen, kunt u een groep voor Outlook maken. Zie Een [Microsoft 365-groep maken in het beheercentrum](../create-groups/create-groups.md)voor meer informatie.

- **Gebruiken met Outlook:** Naast het gebruik van de webversie van Outlook in uw browser voor toegang tot gedeelde postvakken, kunt u ook de Outlook voor iOS-app of de Outlook voor Android-app gebruiken. Zie Een gedeeld postvak toevoegen [aan Outlook Mobile voor meer informatie.](https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f) Een andere optie is om een groep te maken voor uw gedeelde postvak. Zie Groepen vergelijken [voor meer informatie.](../create-groups/compare-groups.md)

- **Versleuteling:** U kunt e-mail die vanuit een gedeeld postvak wordt verzonden, niet versleutelen. Dit komt omdat een gedeeld postvak geen eigen beveiligingscontext heeft (gebruikersnaam/wachtwoord), dus kan er geen sleutel aan worden toegewezen. Als meerdere personen lid zijn en e-mailberichten verzenden/ontvangen die ze met hun eigen sleutels hebben versleuteld, kunnen andere leden mogelijk de e-mail lezen en anderen niet, afhankelijk van de openbare sleutel waarmee de e-mail is versleuteld.

- **Postvakconversie:** U kunt gebruikerspostvakken converteren naar gedeelde postvakken. Zie [Het postvak van een gebruiker converteren naar een gedeeld postvak](convert-user-mailbox-to-shared-mailbox.md).

- **Beheerdersrollen:** Gebruikers met globale beheerders- of Exchange-beheerdersrollen kunnen gedeelde postvakken maken.

- **Abonnementsvereisten:** Als u een gedeeld postvak wilt maken, moet u zich abonneren op een Microsoft 365 voor Bedrijven-abonnement met e-mail (de Exchange Online-service). Het abonnement op Microsoft 365 Apps voor Bedrijven bevat geen e-mail. Microsoft 365 Business Standard bevat wel e-mail.

- **Aanmelden:** Een gedeeld postvak is niet bedoeld voor directe aanmelding door het bijbehorende gebruikersaccount. U moet de aanmelding voor het gedeelde postvakaccount altijd blokkeren en dit geblokkeerd houden.

- **Te veel gebruikers:** Als er te veel aangewezen gebruikers tegelijk toegang hebben tot een gedeeld postvak, kunnen ze af en toe geen verbinding maken met dit postvak. In dit geval kunt u overwegen het aantal gebruikers te verminderen of een andere werkbelasting te gebruiken, zoals een Microsoft 365-groep of Openbare map.

- **Bericht verwijderen:** Helaas kunt u niet voorkomen dat personen berichten in een gedeeld postvak verwijderen. U kunt dit alleen doen door een Microsoft 365-groep te maken in plaats van een gedeeld postvak. Een groep in Outlook is als een gedeeld postvak. Zie Groepen vergelijken voor een vergelijking [van de twee.](../create-groups/compare-groups.md) Zie Meer informatie over groepen voor [meer informatie over groepen.](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)


> [!NOTE]
> Als u toegang wilt tot een gedeeld postvak, moet een gebruiker een Exchange Online-licentie hebben, maar voor het gedeelde postvak is geen aparte licentie vereist. Elk gedeeld postvak heeft een bijbehorend gebruikersaccount. Is het u opgevallen dat u niet werd gevraagd een wachtwoord in te voeren toen u het gedeelde postvak maakte? Het account heeft een wachtwoord, maar dat wordt gegenereerd door het systeem (onbekend). U moet het account niet gebruiken om u aan te melden bij het gedeelde postvak. Zonder licentie zijn gedeelde postvakken beperkt tot 50 GB. Als u de limiet wilt verhogen tot 100 GB, moet aan het gedeelde postvak een Exchange Online Plan 2-licentie of een Exchange Online Plan 1-licentie met een exchange Online Archiving-invoeglicentie worden toegewezen. Hiermee kunt u ook automatisch uitbreidende archivering inschakelen voor een onbeperkte hoeveelheid archiefopslagcapaciteit. Als u een gedeeld postvak in de wacht wilt zetten voor juridische procedures, moet het gedeelde postvak een exchange Online Plan 2-licentie of een Exchange Online Plan 1-licentie hebben met een invoeglicentie voor Archiveren van Exchange Online. Als u geavanceerde functies wilt toepassen, zoals Microsoft Defender voor Office 365, Geavanceerd eDiscovery of beleid voor automatisch bewaren, moet het gedeelde postvak een licentie hebben voor deze functies.

## <a name="related-content"></a>Verwante onderwerpen

[Een gedeeld postvak maken](create-a-shared-mailbox.md)

[Een gedeeld postvak configureren](configure-a-shared-mailbox.md)

[Een gebruikerspostvak converteren naar een gedeeld postvak](convert-user-mailbox-to-shared-mailbox.md)

[Een licentie uit een gedeeld postvak verwijderen](remove-license-from-shared-mailbox.md)

[Problemen oplossen met gedeelde postvakken](resolve-issues-with-shared-mailboxes.md)