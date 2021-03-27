---
title: Uw beheerdersaccounts beveiligen
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
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Meer informatie over het instellen en beveiligen van uw beheerdersaccounts.
ms.openlocfilehash: 0d687407fad1cec5da49dbc33ffeb84366f1c309
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398239"
---
# <a name="protect-your-administrator-accounts"></a>Uw beheerdersaccounts beveiligen

Aangezien beheerdersaccounts met verhoogde bevoegdheden worden gebruikt, zijn ze waardevolle doelen voor hackers en cybercriminelen. In dit artikel wordt het volgende beschreven:

- Een extra beheerdersaccount instellen voor noodgevallen.
- Deze accounts beveiligen.

Wanneer u zich registreert voor Microsoft 365 en uw gegevens in typt, wordt u automatisch de globale beheerder. Een globale beheerder heeft de ultieme controle over gebruikersaccounts en alle andere instellingen in het Microsoft-beheercentrum, maar er zijn veel verschillende soorten beheerdersaccounts met verschillende toegangsgraden. Zie [beheerdersrollen voor](/office365/admin/add-users/about-admin-roles) informatie over de verschillende toegangsniveaus voor elk type beheerdersrol.

## <a name="create-additional-admin-accounts"></a>Extra beheerdersaccounts maken

Beheeraccounts alleen gebruiken voor beheer. Beheerders moeten een afzonderlijk gebruikersaccount hebben voor regelmatig gebruik van Office-apps en hun beheeraccount alleen gebruiken wanneer dat nodig is voor het beheren van accounts en apparaten en tijdens het werken aan andere beheerfuncties. Het is ook een goed idee om de Microsoft 365-licentie te verwijderen uit de beheerdersaccounts, zodat u er niet voor hoeft te betalen.

U wilt ten minste één extra globale beheerdersaccount instellen om beheerder toegang te geven tot een andere vertrouwde werknemer. U kunt ook afzonderlijke beheerdersaccounts maken voor gebruikersbeheer (deze rol wordt **beheerder gebruikersbeheer genoemd).** Zie beheerdersrollen [voor meer informatie.](/office365/admin/add-users/about-admin-roles)

Extra beheerdersaccounts maken:

 1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">beheercentrum en</a> kies **gebruikers actieve** \> **gebruikers** in het linkernavigatienavigatiepunt.

    ![Kies Gebruikers en vervolgens Actieve gebruikers in de linkernavigatiebalk](../media/Activeusers.png)

 2. Selecteer op **de pagina** Actieve gebruikers de optie Een gebruiker  **toevoegen** boven aan de pagina en voer in het deelvenster Nieuwe gebruiker de naam en andere informatie in.
 3. Vouw de **sectie Rollen** uit en kies Globale **beheerder om** deze gebruiker globale beheerderstoegang te geven. U kunt ook **Aangepaste beheerder kiezen** en een van de rollen kiezen die worden weergegeven.

    Voer een alternatief e-mailbericht in het **tekstvak Alternatief e-mailadres** in. U kunt dit adres gebruiken om uw wachtwoordgegevens te herstellen als u wordt vergrendeld. Voor globale beheerders wordt ook een factuuroverzicht naar dit adres verzonden.

    ![De beheerdersrol kiezen](../media/adminroles.png)

 4. Verplaats in **de sectie Productlicenties** de selector voor **Microsoft 365 Business** naar **Uit** en de gebruiker **zonder productlicentie** maken naar **Aan.**

    ![De productlicentie kiezen](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a>Een account voor noodgevallenbeheerder maken

U moet ook een back-upaccount maken dat niet is ingesteld met meervoudige verificatie (MFA), zodat u uzelf niet per ongeluk vergrendelt (bijvoorbeeld als u uw telefoon verliest die u gebruikt als een tweede verificatieformulier). Zorg ervoor dat het wachtwoord voor dit account een woordgroep of ten minste 16 tekens lang is. Dit wordt vaak een 'break-glass account' genoemd.

## <a name="create-a-user-account-for-yourself"></a>Een gebruikersaccount voor uzelf maken

Gebruik uw gebruikersaccount om deel te nemen aan samenwerking met uw organisatie, inclusief het controleren van e-mail. Dit betekent dat uw beheerdersreferenties vergelijkbaar kunnen zijn met *De <span></span> @Contoso.org van Alice.Chavez* en dat uw gewone gebruikersaccount vergelijkbaar kan zijn met *De <span></span> @Contoso.com.*

Een nieuw gebruikersaccount maken:

1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">beheercentrum en</a> kies **gebruikers actieve** \> **gebruikers** in het linkernavigatienavigatiepunt.
2. Selecteer op **de pagina** Actieve gebruikers de optie Een gebruiker  **toevoegen** boven aan de pagina en voer in het deelvenster Nieuwe gebruiker de naam en andere informatie in.
3. Vouw de **sectie Rollen** uit en kies **Gebruiker (geen beheerderstoegang).**
4. Verplaats in **de sectie Productlicenties** de selector voor **Microsoft 365 Business** naar **Aan.**

## <a name="turn-on-security-defaults"></a>Beveiligingsinstellingen in- en uit-

Beveiligingsinstellingen helpen uw organisatie te beschermen tegen identiteitsgerelateerde aanvallen door vooraf geconfigureerde beveiligingsinstellingen te bieden die Microsoft namens uw organisatie beheert. Deze instellingen omvatten het inschakelen van meervoudige verificatie (MFA) voor alle beheerders en gebruikersaccounts. Zie Beveiligingsinstellingen inschakelen voor meer informatie over beveiligingsinstellingen en voor meer informatie over het inschakelen van [beveiligingsinstellingen.](m365-campaigns-conditional-access.md)

## <a name="additional-recommendations"></a>Aanvullende aanbevelingen

- Sluit alle niet-gerelateerde browsersessies en -apps, inclusief persoonlijke e-mailaccounts, voordat u beheerdersaccounts gebruikt. U kunt ook in privé- of incognitobrowservensters gebruiken.
- Nadat u beheerderstaken heeft uitgevoerd, moet u zich af melden bij de browsersessie.
