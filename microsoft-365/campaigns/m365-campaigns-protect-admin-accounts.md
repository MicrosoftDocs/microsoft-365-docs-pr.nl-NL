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
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Meer informatie over het instellen en beveiligen van uw beheerdersaccounts.
ms.openlocfilehash: b74d9d2d69549bcaa476a346ba2a61fc24e0b3f3
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42808793"
---
# <a name="protect-your-administrator-accounts"></a>Uw beheerdersaccounts beveiligen

Omdat admin-accounts worden geleverd met verhoogde privileges, ze zijn waardevolle doelwitten voor hackers en cybercriminelen. In dit artikel wordt beschreven:

- Hoe maak je een extra beheerdersaccount voor noodgevallen in.
- Hoe deze accounts te beschermen.
 
Wanneer u zich aanmeldt voor Microsoft 365 Business en uw gegevens invoert, wordt u automatisch de globale beheerder. Een globale beheerder heeft de ultieme controle over gebruikersaccounts en alle andere instellingen in het Microsoft-beheercentrum, maar er zijn veel verschillende soorten beheerdersaccounts met verschillende mate van toegang. Zie [over beheerdersrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) voor informatie over de verschillende toegangsniveaus voor elk type beheerdersrol.


## <a name="create-additional-admin-accounts"></a>Extra beheerdersaccounts maken

Gebruik alleen beheerdersaccounts voor beheer. Beheerders moeten een apart gebruikersaccount hebben voor regelmatig gebruik van Office-apps en alleen hun beheerdersaccount gebruiken wanneer dat nodig is om accounts en apparaten te beheren en terwijl ze aan andere beheerfuncties werken. Het is ook een goed idee om de Microsoft 365 Business-licentie te verwijderen uit de beheerdersaccounts, zodat u er niet voor hoeft te betalen.

U wilt ten minste één extra globale beheerdersaccount instellen om beheerders toegang te geven tot een andere vertrouwde werknemer. U ook afzonderlijke beheerdersaccounts voor gebruikersbeheer maken (deze rol heet **Beheerder gebruikersbeheer).** Zie voor meer informatie [over beheerdersrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).

Ga als volgt te werk om extra beheerdersaccounts te maken:

 1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">beheercentrum</a> en kies **Gebruikers** \> **actieve gebruikers** in de linkernavigatie.

    ![Gebruikers kiezen en vervolgens Actieve gebruikers in de linkernavigatie](../media/Activeusers.png)

2. Selecteer op de pagina **Actieve gebruikers** de optie Een gebruiker boven aan de pagina **toevoegen** en voer in het deelvenster **Nieuwe gebruikers** de naam en andere informatie in.
3. Vouw de sectie **Rollen** uit en kies **Globale beheerder** om deze gebruikersglobale beheerder toegang te geven. U ook **aangepaste beheerder** kiezen en een van de rollen kiezen die worden weergegeven.

    Voer een alternatieve e-mail in het tekstvak **Alternatief e-mailadres** in. U dit adres gebruiken om uw wachtwoordgegevens te herstellen als u buitengesloten wordt. Voor globale beheerders wordt ook een factuuroverzicht naar dit adres verzonden.

    ![De beheerdersrol kiezen](../media/adminroles.png)
    
4. Verplaats in de sectie **Productlicenties** de kiezer voor **Microsoft 365 Business** naar **Uit** en de gebruiker maken **zonder productlicentie** naar **Aan.**

    ![Kies de productlicentie](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a>Een noodbeheerdersaccount maken

U moet ook een back-upaccount maken dat niet is ingesteld met multi-factor authenticatie (MFA), zodat u uzelf niet per ongeluk buitensluit (bijvoorbeeld als u uw telefoon verliest die u als tweede verificatieformulier gebruikt). Zorg ervoor dat het wachtwoord voor dit account een zin of ten minste 16 tekens lang is. Dit wordt vaak aangeduid als een "break-glass account."

## <a name="create-a-user-account-for-yourself"></a>Zelf een gebruikersaccount aanmaken

Gebruik uw gebruikersaccount om deel te nemen in samenwerking met uw organisatie, inclusief het controleren van e-mail. Dit betekent dat uw beheerdersreferenties vergelijkbaar kunnen zijn met *<span></span>Alice.Chavez @Contoso.org* en dat uw gewone gebruikersaccount mogelijk vergelijkbaar is met *Alice<span></span>@Contoso.com*.

Ga als lid van het volgende over een nieuw gebruikersaccount:
1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">beheercentrum</a> en kies **Gebruikers** \> **actieve gebruikers** in de linkernavigatie.
2. Selecteer op de pagina **Actieve gebruikers** de optie Een gebruiker boven aan de pagina **toevoegen** en voer in het deelvenster **Nieuwe gebruikers** de naam en andere informatie in.
3. Vouw de sectie **Rollen** uit en kies **Gebruiker (geen beheerderstoegang)**.
1. Verplaats in de sectie **Productlicenties** de kiezer voor **Microsoft 365 Business** naar **Aan**. 

## <a name="register-each-of-these-accounts-for-multi-factor-authentication"></a>Registreer elk van deze accounts voor multi-factor authenticatie


## <a name="additional-recommendations"></a>Aanvullende aanbevelingen

- Zorg ervoor dat beheerdersaccounts ook zijn ingesteld voor meervoudige verificatie. We laten u zien hoe u dit doet in [Beleid voor voorwaardelijke toegang configureren.](m365-campaigns-conditional-access.md)
- Sluit voordat u beheerdersaccounts gebruikt alle niet-gerelateerde browsersessies en -apps, inclusief persoonlijke e-mailaccounts. U ook privé- of incognitobrowservensters gebruiken.
- Nadat u beheerderstaken hebt voltooid, moet u zich afmelden bij de browsersessie.
