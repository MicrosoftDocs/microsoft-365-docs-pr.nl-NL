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
description: Meer informatie over het instellen en beveiligen van uw beheerdersaccounts.
ms.openlocfilehash: dc5f72cda0255641d7d2407d266a6ae584560733
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527184"
---
# <a name="protect-your-administrator-accounts"></a>Uw beheerdersaccounts beveiligen

Omdat admin accounts worden geleverd met verhoogde privileges, ze zijn waardevolle doelen voor hackers en cybercriminelen. Dit artikel beschrijft:

- Hoe stel je een extra beheerdersaccount in voor noodgevallen.
- Hoe deze accounts te beschermen.
 
Wanneer u zich aanmeldt voor Microsoft 365 en uw gegevens invoert, wordt u automatisch de globale beheerder. Een globale beheerder heeft de ultieme controle over gebruikersaccounts en alle andere instellingen in het Microsoft-beheercentrum, maar er zijn veel verschillende soorten beheerdersaccounts met verschillende mate van toegang. Zie [meer over beheerdersrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) voor informatie over de verschillende toegangsniveaus voor elk soort beheerdersrol.


## <a name="create-additional-admin-accounts"></a>Extra beheerdersaccounts maken

Gebruik alleen beheerdersaccounts voor beheer. Beheerders moeten een apart gebruikersaccount hebben voor regelmatig gebruik van Office-apps en hun administratieve account alleen gebruiken wanneer dat nodig is om accounts en apparaten te beheren en tijdens het werken aan andere beheerdersfuncties. Het is ook een goed idee om de Microsoft 365-licentie te verwijderen uit de admin-accounts, zodat u niet hoeft te betalen voor hen.

U wilt ten minste één extra globaal beheerdersaccount instellen om beheerders toegang te geven tot een andere vertrouwde werknemer. U ook afzonderlijke beheerdersaccounts maken voor gebruikersbeheer (deze rol wordt **beheerder van gebruikersbeheer**genoemd). Zie voor meer informatie [over beheerdersrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).

Ga als volgt te werk om extra beheerdersaccounts te maken:

 1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">beheercentrum</a> en kies **Users** \> **Gebruikers Actieve gebruikers** in het linkernavigatiesysteem.

    ![Gebruikers kiezen en vervolgens actieve gebruikers in het linkernavigatiesysteem](../media/Activeusers.png)

2. Selecteer op de pagina **Actieve gebruikers** de optie Een gebruiker boven aan de pagina **toevoegen** en voer in het deelvenster **Nieuwe gebruikers** de naam en andere informatie in.
3. Vouw de sectie **Rollen** uit en kies **Globale beheerder** om deze gebruiker algemene beheerderstoegang te geven. U ook **aangepaste beheerder** kiezen en een van de rollen kiezen die worden weergegeven.

    Voer een alternatieve e-mail in het tekstvak **Alternatief e-mailadres** in. U dit adres gebruiken om uw wachtwoordgegevens te herstellen als u buitengesloten wordt. Voor globale beheerders wordt ook een factureringsverklaring naar dit adres verzonden.

    ![De beheerdersrol kiezen](../media/adminroles.png)
    
4. Verplaats in de sectie **Productlicenties** de kiezer voor **Microsoft 365 Business** naar **Uit** en de gebruiker maken **zonder productlicentie** naar **Aan**.

    ![Kies de productlicentie](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a>Een noodbeheerderaccount maken

U moet ook een back-upaccount maken dat niet is ingesteld met multi-factor authenticatie (MFA), zodat u uzelf niet per ongeluk vergrendelt (bijvoorbeeld als u uw telefoon verliest die u als tweede vorm van verificatie gebruikt). Zorg ervoor dat het wachtwoord voor dit account een zin of ten minste 16 tekens lang is. Dit wordt vaak aangeduid als een "break-glass account."

## <a name="create-a-user-account-for-yourself"></a>Zelf een gebruikersaccount maken

Gebruik uw gebruikersaccount om deel te nemen aan samenwerking met uw organisatie, inclusief het controleren van e-mail. Dit betekent dat uw beheerdersreferenties vergelijkbaar kunnen zijn met *Alice.Chavez <span></span> @Contoso.org* en dat uw gewone gebruikersaccount vergelijkbaar is met *Alice <span></span> @Contoso.com*.

Ga als u een nieuw gebruikersaccount aanmaken:
1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">beheercentrum</a> en kies **Users** \> **Gebruikers Actieve gebruikers** in het linkernavigatiesysteem.
2. Selecteer op de pagina **Actieve gebruikers** de optie Een gebruiker boven aan de pagina **toevoegen** en voer in het deelvenster **Nieuwe gebruikers** de naam en andere informatie in.
3. Vouw de sectie **Rollen** uit en kies **Gebruiker (geen beheerderstoegang).**
1. Verplaats in de sectie **Productlicenties** de kiezer voor **Microsoft 365 Business** naar **Aan**. 

## <a name="register-each-of-these-accounts-for-multi-factor-authentication"></a>Elk van deze accounts registreren voor meervoudige verificatie


## <a name="additional-recommendations"></a>Aanvullende aanbevelingen

- Zorg ervoor dat beheerdersaccounts ook zijn ingesteld voor meervoudige verificatie. We laten je zien hoe je dit doen in [Het beleid voor voorwaardelijke toegang configureren.](m365-campaigns-conditional-access.md)
- Voordat u beheerdersaccounts gebruikt, sluit u alle niet-gerelateerde browsersessies en -apps, inclusief persoonlijke e-mailaccounts. U ook gebruiken in privé- of incognitobrowservensters.
- Nadat u beheerderstaken hebt voltooid, moet u zich afmelden bij de browsersessie.
