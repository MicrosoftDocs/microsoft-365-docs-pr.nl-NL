---
title: Informatie over beheerdersrollen in het Microsoft 365-beheercentrum
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: da585eea-f576-4f55-a1e0-87090b6aaa9d
description: Beheerdersrollen worden toegewezen aan bedrijfsfuncties en geven machtigingen om specifieke taken uit te voeren in het Beheercentrum. Zo kan de servicebeheerder bijvoorbeeld supporttickets openen via het Beheercentrum.
ms.openlocfilehash: 5ee8f5732d67ee3913ac7de5bcb7328065b0c8ba
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445461"
---
# <a name="about-admin-roles"></a>Informatie over beheerdersrollen

Uw abonnement op Microsoft 365 of Office 365 wordt geleverd met een set beheerdersrollen die u kunt toewijzen aan gebruikers in uw organisatie via het Microsoft 365-beheercentrum. Elke beheerdersrol wordt toegewezen aan algemene bedrijfsfuncties en machtigt personen in uw organisatie om specifieke taken uit te voeren in de beheercentra.

In het Microsoft 365-beheercentrum kunt u Azure AD- en Microsoft Intune-rollen beheren. Deze rollen vormen echter een subset van de rollen die beschikbaar zijn in de Azure-Portal en het Intune-beheercentrum.

## <a name="before-you-begin"></a>Voordat u begint

Zoekt u een volledige lijst met uitgebreide beschrijvingen van Azure AD-rollen die u kunt beheren in het Microsoft 365-Beheercentrum? Bekijk de machtigingen voor de beheerdersrol in Azure Active Directory. [Machtigingen voor de beheerdersrol in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).

Zoekt u een volledige lijst met uitgebreide beschrijvingen van Intune-rollen die u kunt beheren in het Microsoft 365-Beheercentrum?  Bekijk [op rollen gebaseerd toegangsbeheer (RBAC) met Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control).

Zie [beheerdersrollen toewijzen](assign-admin-roles.md)voor meer informatie over het toewijzen van rollen in het Microsoft 365-beheercentrum.

### <a name="watch-what-is-an-admin"></a>Bekijk: Wat is een beheerder?

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1SRc0]

## <a name="security-guidelines-for-assigning-roles"></a>Beveiligingsrichtlijnen voor het toewijzen van rollen

Omdat beheerders toegang hebben tot gevoelige gegevens en bestanden, raden we u aan deze richtlijnen te volgen om de gegevens van uw organisatie veiliger te houden.

| Aanbeveling                  | Waarom is dit belangrijk?                 |
| :------------------- | :------------------- |
| Zet twee tot vier globale beheerders in  | Omdat alleen een andere globale beheerder het wachtwoord van een globale beheerder opnieuw kan instellen, raden wij u aan om ten minste twee globale beheerders in uw organisatie te hebben in geval van accountvergrendeling. Maar de globale beheerder heeft bijna onbeperkte toegang tot de instellingen van uw organisatie en de meeste gegevens. Wij raden u dan ook aan niet meer dan vier globale beheerders te hebben, omdat dit een beveiligingsrisico vormt. |
| De *minste strikte* functie toewijzen    | Het toewijzen van de *minste strikte* rol betekent dat beheerders alleen de toegang krijgen die ze nodig hebben om de taak uit te voeren. Als u bijvoorbeeld wilt dat iemand de wachtwoorden van werknemers opnieuw instelt, moet u geen onbeperkte globale beheerdersrol toewijzen, maar een beperkte beheerdersrol zoals Wachtwoordbeheerder of Helpdesk-beheerder. Dit helpt uw gegevens veilig te houden.                 |
| Meervoudige verificatie (MFA) voor beheerders vereisen                  |    Het is een goed idee om MFA te vereisen voor al uw gebruikers, maar beheerders moeten beslist verplicht worden om MFA te gebruiken om in te loggen. Met MFA doorlopen gebruikers een tweede identificatiemethode, om te verifiëren dat ze zijn wie ze zeggen dat ze zijn. Beheerders kunnen toegang hebben tot veel klant- en werknemersgegevens en als u MFA vereist, is het wachtwoord nutteloos zonder de tweede vorm van identificatie, zelfs als het wachtwoord van de beheerder wordt gecompromitteerd.  <br><br>Wanneer u MFA inschakelt, moet de gebruiker de volgende keer dat deze zich aanmeldt een alternatief e-mailadres en telefoonnummer opgeven voor accountherstel.  <br> [Meervoudige verificatie instellen](../security-and-compliance/set-up-multi-factor-authentication.md)          |

Als er een bericht wordt weergegeven in het Beheercentrum waarin wordt aangegeven dat u geen machtigingen hebt om een instelling of pagina te bewerken, komt dit omdat u een rol hebt toegewezen gekregen die deze machtiging niet omvat.

## <a name="commonly-used-microsoft-365-admin-center-roles"></a>Veelgebruikte rollen in het Microsoft 365-Beheercentrum

::: moniker range="o365-worldwide"

In het Microsoft 365-beheercentrum kunt u naar **Rollen**gaan en vervolgens een rol selecteren om het detailvenster te openen. Selecteer het tabblad **Machtigingen** om de gedetailleerde takenlijst weer te geven met wat de beheerders die aan die rol zijn toegewezen kunnen doen. Selecteer het tabblad **toegewezen** of **toegewezen beheerders** om gebruikers toe te voegen aan rollen.

::: moniker-end

Waarschijnlijk hoeft u alleen de volgende rollen in uw organisatie toe te wijzen. Standaard tonen we eerst de rollen die de meeste organisaties gebruiken. Als u een rol niet kunt vinden, gaat u naar het einde van de lijst en selecteert u **Alles weergeven per categorie**. (Zie [machtigingen voor beheerdersrol in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)voor meer informatie, waaronder de cmdlets die zijn gekoppeld aan een rol.)

|Beheerdersrol     |Aan wie moet deze rol worden toegewezen?  |
|---------|---------|
|Exchange-beheerder     |   Wijs de Exchange-beheerdersrol toe aan gebruikers die de e-mailpostvakken, Microsoft 365-groepen en Exchange Online van uw gebruikers moeten kunnen bekijken en beheren. <br><br> Exchange-beheerders kunnen ook het volgende doen:<br> - Verwijderde items herstellen in het postvak van een gebruiker <br> Gedelegeerden instellen voor 'Verzenden als' en 'Verzenden namens'. <br>  |
|Algemene beheerder     |   Wijs de Globale beheerdersrol toe aan gebruikers die wereldwijde toegang nodig hebben tot de meeste beheerfuncties en -gegevens via Microsoft online services. <br><br> Te veel gebruikers globale toegang geven is een beveiligingsrisico, we raden u dan ook aan om 2 tot 4 globale beheerders te hebben. <br><br> Alleen globale beheerders kunnen het volgende doen:<br> - Wachtwoorden voor alle gebruikers opnieuw instellen <br> - Domeinen toevoegen en beheren <br> <br> **Opmerking:** de persoon die zich heeft geregistreerd voor Microsoft Online Services, wordt automatisch een globale beheerder. |
|Algemene lezer    |   Wijs de rol van algemene lezer toe aan gebruikers die beheerdersfuncties en -instellingen moeten bekijken in beheercentra die de globale beheerder kan zien. De beheerder van de algemene lezers kan geen instellingen bewerken.   |
|Groepsbeheerder     |   Wijs de groepsbeheerdersrol toe aan gebruikers die alle groepsinstellingen in alle beheercentra moeten beheren, inclusief het Microsoft 365-Beheercentrum en de Azure Active Directory-Portal. <br><br> Groepsbeheerders kunnen het volgende doen:<br> - Microsoft 365-groepen maken, bewerken, verwijderen en herstellen <br> - Beleid voor het maken, verlopen en benoemen van groepen maken en bijwerken <br> - Azure Active Directory-beveiligingsgroepen maken, bewerken, verwijderen en herstellen| 
|Helpdesk-beheerder     |   Wijs de beheerdersrol Helpdesk toe aan gebruikers die de volgende taken moeten uitvoeren:<br> - Wachtwoorden opnieuw instellen <br> - Gebruikers dwingen zich af te melden <br> - Serviceaanvragen beheren <br> - De servicestatus bewaken <br> <br> **Opmerking**: de Helpdesk-beheerder kan alleen niet-beheerders helpen en gebruikers die deze rollen hebben toegewezen: Directory-lezer, Gast-invite, Helpdesk-beheerder, Berichtencentrum-lezer en Rapportlezer.      |
|Office-apps beheerder    |   Wijs de beheerdersrol Office Apps toe aan gebruikers die de volgende taken moeten uitvoeren: <br> - Gebruik de Office-cloudbeleidservice om cloudgebaseerd beleid voor Office te maken en te beheren <br> - Serviceaanvragen maken en beheren <br> - Inhoud over nieuwe functies beheren die gebruikers in hun Office-apps zien   <br> - De servicestatus bewaken  |
|Serviceondersteuningsbeheer   |   Wijs de rol Serviceondersteuningsbeheer als een extra rol toe aan beheerders of gebruikers van wie de rol het volgende niet omvat maar wat ze wel moeten kunnen doen: <br> - Serviceaanvragen openen en beheren <br> - Berichten in het berichtencentrum bekijken en delen   |
|SharePoint-beheerder    |   Wijs de SharePoint-beheerdersrol toe aan gebruikers die het SharePoint Online-beheercentrum moeten openen en beheren. <br><br>SharePoint-beheerders kunnen ook het volgende doen: <br> - Sites maken en verwijderen <br> - Siteverzamelingen en wereldwijde SharePoint-instellingen beheren   |
|Teams-servicebeheerder    |   Wijs de rol Teams-servicebeheerder toe aan gebruikers die het Teams-beheercentrum moeten openen en beheren. <br><br>Teams-servicebeheerders kunnen ook: <br> - Vergaderingen beheren <br> - Vergaderbruggen beheren <br> - Alle organisatiebrede instellingen beheren, inclusief federatie, Teams-upgrade en Teams-clientinstellingen   |
|Gebruikersbeheerder     |    Wijs de beheerdersrol Gebruikers toe aan gebruikers die de voor alle gebruikers de volgende taken moeten uitvoeren: <br> - Gebruikers en groepen toevoegen <br> - Licenties toewijzen <br> - De meeste gebruikerseigenschappen beheren <br> - Gebruikersweergaven maken en beheren <br> - Verloopbeleid voor wachtwoorden bijwerken <br> - Serviceaanvragen beheren <br> - De servicestatus bewaken <br><br>  De gebruikersbeheerder kan ook de volgende acties uitvoeren voor gebruikers die geen beheerders zijn en voor gebruikers die de volgende rollen hebben gekregen: adreslijst lezer, gast invite, helpdesk-beheerder, Message Center Reader, rapportlezer: <br> - Gebruikersnamen beheren<br> - Gebruikers verwijderen en herstellen<br> - Wachtwoorden opnieuw instellen <br> - Gebruikers dwingen zich af te melden <br> - Apparaatsleutels bijwerken (FIDO)   |

## <a name="delegated-administration-for-microsoft-partners"></a>Gedelegeerd beheer voor Microsoft-partners

Als u met een Microsoft-partner werkt, kunt u aan uw partner beheerdersrollen toewijzen. Zij kunnen op hun beurt gebruikers in uw bedrijf, of hun bedrijf, beheerdersrollen toewijzen. U wilt misschien dat ze dit doen, bijvoorbeeld als ze uw online organisatie voor u opzetten en beheren.
  
Een partner kan deze rollen toewijzen: 
  
- **Volledig beheer** Bevoegdheden van deze rol zijn te vergelijken met die van een globale beheerder, met uitzondering van het beheren van meervoudige verificatie via het Partnercentrum.

- **Beperkt beheer** Bevoegdheden van deze rol zijn te vergelijken met die van een helpdesk-beheerder.

Voordat de partner deze rollen aan gebruikers kan toewijzen, moet u de partner als gedelegeerde beheerder aan uw account toevoegen. Dit proces wordt geïnitieerd door een geautoriseerde partner. De partner stuurt u een e-mailbericht waarin u wordt gevraagd of u de partner toestemming wilt geven om te fungeren als gedelegeerde beheerder. Zie [Partnerrelaties autoriseren of verwijderen](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner)voor instructies.
  
## <a name="related-articles"></a>Verwante artikelen

[Beheerdersrollen toewijzen](assign-admin-roles.md)

[Informatie over Azure AD-rollen in het Microsoft 365-beheercentrum](azure-ad-roles-in-the-mac.md)

[Exchange Online-beheerdersrol](about-exchange-online-admin-role.md)
  
[Activiteitenoverzichten in het Microsoft 365-beheercentrum](../activity-reports/activity-reports.md)
