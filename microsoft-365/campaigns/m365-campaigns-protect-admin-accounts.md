---
title: Uw beheerdersaccounts beveiligen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
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
description: Informatie over het instellen en beveiligen van uw beheerdersaccounts.
ms.openlocfilehash: 73e4b69571b1e1d0a4d1585224fe256ff135c40a
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044486"
---
# <a name="protect-your-administrator-accounts"></a>Uw beheerdersaccounts beveiligen

Omdat beheerdersaccounts worden met verhoogde bevoegdheden, zijn ze waardevolle doelen voor hackers en cybercriminelen. In dit artikel worden de volgende artikelen beschreven:

- Het instellen van een extra beheerdersaccount voor noodgevallen.
- Deze accounts beveiligen.

Wanneer u zich voor Microsoft 365 registreert en uw gegevens in voert, wordt u automatisch de globale beheerder. Een globale beheerder heeft de ultieme controle over gebruikersaccounts en alle andere instellingen in het Microsoft-beheercentrum, maar er zijn veel verschillende soorten beheerdersaccounts met verschillende toegangsgraden. Meer [informatie over beheerdersrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) vindt u in de verschillende toegangsniveaus voor elk type beheerdersrol.

## <a name="create-additional-admin-accounts"></a>Extra beheerdersaccounts maken

Gebruik alleen beheerdersaccounts voor beheer. Beheerders moeten een afzonderlijk gebruikersaccount hebben voor normaal gebruik van Office-apps en hun beheeraccount alleen gebruiken wanneer dat nodig is voor het beheren van accounts en apparaten, en terwijl ze aan andere beheerfuncties werken. Het is ook een goed idee om de Microsoft 365-licentie te verwijderen uit de beheerdersaccounts, zodat u er niet voor hoeft te betalen.

U moet ten minste één extra globale beheerdersaccount instellen om beheerderstoegang te verlenen aan een andere vertrouwde werknemer. U kunt ook afzonderlijke beheerdersaccounts maken voor gebruikersbeheer (deze rol wordt **beheerder Gebruikersbeheer genoemd).** Zie voor meer informatie [over beheerdersrollen.](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)

Extra beheerdersaccounts maken:

 1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">beheercentrum</a> en kies **Gebruikers** \> **actieve gebruikers** in het linkernavigatienavigatiebalkje.

    ![Kies Gebruikers en vervolgens Actieve gebruikers in het linkernavigatienavigatiebalkje](../media/Activeusers.png)

 2. Selecteer op **de** pagina  Actieve gebruikers een gebruiker toevoegen boven  aan de pagina en voer in het deelvenster Nieuwe gebruiker de naam en andere gegevens in.
 3. Vouw de **sectie Rollen** uit en kies Globale **beheerder om** deze gebruiker globale beheerderstoegang te geven. U kunt ook **Aangepaste beheerder kiezen** en een van de rollen kiezen die worden weergegeven.

    Voer een alternatief e-mailadres in het **tekstvak Alternatieve e-mailadres** in. U kunt dit adres gebruiken om uw wachtwoordgegevens te herstellen als u geen toegang hebt. Voor globale beheerders wordt ook een factuuroverzicht naar dit adres verzonden.

    ![De beheerdersrol kiezen](../media/adminroles.png)

 4. Verplaats in de **sectie Productlicenties** de selector  voor **Microsoft 365 Business** naar Uit en Gebruiker maken zonder **productlicentie** naar **Aan.**

    ![Kies de productlicentie](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a>Een beheerdersaccount voor noodgevallen maken

U moet ook een back-upaccount maken dat niet is ingesteld met meervoudige verificatie (MFA), zodat u uzelf niet per ongeluk vergrendelt (bijvoorbeeld als u uw telefoon verliest die u als tweede verificatiemethode gebruikt). Zorg ervoor dat het wachtwoord voor dit account bestaat uit een woordgroep of minimaal 16 tekens. Dit wordt vaak een 'break-glass-account' genoemd.

## <a name="create-a-user-account-for-yourself"></a>Een gebruikersaccount voor uzelf maken

Gebruik uw gebruikersaccount om deel te nemen aan samenwerking met uw organisatie, waaronder het controleren van e-mail. Dit betekent dat uw beheerdersreferenties kunnen lijken op *Moeten.Chavez <span></span> @Contoso.org* en dat uw normale gebruikersaccount mogelijk lijkt op *<span></span> @Contoso.com.*

Een nieuw gebruikersaccount maken:

1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">beheercentrum en</a> kies **Gebruikers** \> **actieve gebruikers** in het linkernavigatienavigatiebalkje.
2. Selecteer op **de** pagina  Actieve gebruikers een gebruiker toevoegen boven  aan de pagina en voer in het deelvenster Nieuwe gebruiker de naam en andere gegevens in.
3. Vouw de **sectie Rollen** uit en kies **Gebruiker (geen beheerderstoegang).**
4. Verplaats in **de sectie Productlicenties** de selector voor **Microsoft 365 Business** naar **Aan.**

## <a name="register-each-of-these-accounts-for-multi-factor-authentication"></a>Elk van deze accounts registreren voor meervoudige verificatie

Zorg ervoor dat voor deze accounts [meervoudige verificatie wordt gebruikt.](m365-campaigns-multifactor-authenication.md)

## <a name="additional-recommendations"></a>Aanvullende aanbevelingen

- Zorg ervoor dat beheerdersaccounts ook zijn ingesteld voor meervoudige verificatie. U ziet hoe u dit doet in Beleid [voor voorwaardelijke toegang configureren.](m365-campaigns-conditional-access.md)
- Sluit voordat u beheerdersaccounts gebruikt, alle niet-gerelateerde browsersessies en -apps, inclusief persoonlijke e-mailaccounts. U kunt ook privé- of incognito browservensters gebruiken.
- Nadat u beheertaken heeft uitgevoerd, moet u zich afloggen bij de browsersessie.
