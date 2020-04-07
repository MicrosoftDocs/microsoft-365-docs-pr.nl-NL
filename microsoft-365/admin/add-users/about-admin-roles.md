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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: da585eea-f576-4f55-a1e0-87090b6aaa9d
description: Beheerdersrollen worden toegewezen aan bedrijfsfuncties en geven machtigingen om specifieke taken uit te voeren in het Beheercentrum. De Servicebeheerder opent bijvoorbeeld supporttickets met Microsoft.
ms.custom: okr_smb
ms.openlocfilehash: ec601e5860460ab77760a5e18c834b987c6b3d07
ms.sourcegitcommit: 311bbd6f168225ede166d29696126a1e003eee0f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/06/2020
ms.locfileid: "43151393"
---
# <a name="about-admin-roles"></a>Informatie over beheerdersrollen

Uw abonnement wordt geleverd met een set beheerdersrollen die u kunt toewijzen aan gebruikers in uw organisatie. Elke beheerdersrol wordt toegewezen aan algemene bedrijfsfuncties en machtigt personen in uw organisatie om specifieke taken uit te voeren in de beheercentra. Zie [Beheerdersrollen toewijzen](assign-admin-roles.md) voor meer informatie.

> [!TIP] 
> Op zoek naar de gedetailleerde rolbeschrijvingen? Bekijk [machtigingen voor beheerdersrollen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).

## <a name="things-to-consider"></a>Aandachtspunten

Omdat beheerders toegang hebben tot gevoelige gegevens en bestanden, raden we u aan deze richtlijnen te volgen om de gegevens van uw organisatie veiliger te houden.

| Aanbeveling                  | Waarom is dit belangrijk?                 |
| :------------------- | :------------------- |
| Zet twee tot vier globale beheerders in  | Omdat alleen een andere globale beheerder het wachtwoord van een globale beheerder opnieuw kan instellen, raden wij u aan om ten minste twee globale beheerders in uw organisatie te hebben in geval van accountvergrendeling. Maar de globale beheerder heeft bijna onbeperkte toegang tot de instellingen van uw organisatie en de meeste gegevens. Wij raden u dan ook aan niet meer dan vier globale beheerders te hebben, omdat dit een beveiligingsrisico vormt. |
| De *minste strikte* functie toewijzen    | Het toewijzen van de *minste strikte* rol betekent dat beheerders alleen de toegang krijgen die ze nodig hebben om de taak uit te voeren. Als u bijvoorbeeld wilt dat iemand de wachtwoorden van werknemers opnieuw instelt, moet u geen onbeperkte globale beheerdersrol toewijzen, maar een beperkte beheerdersrol zoals Wachtwoordbeheerder of Helpdesk-beheerder. Dit helpt uw gegevens veilig te houden.                 |
| Meervoudige verificatie (MFA) voor beheerders vereisen                  |    Het is een goed idee om MFA te vereisen voor al uw gebruikers, maar beheerders moeten beslist verplicht worden om MFA te gebruiken om in te loggen. Met MFA doorlopen gebruikers een tweede identificatiemethode, om te verifiëren dat ze zijn wie ze zeggen dat ze zijn. Beheerders kunnen toegang hebben tot veel klant- en werknemersgegevens en als u MFA vereist, is het wachtwoord nutteloos zonder de tweede vorm van identificatie, zelfs als het wachtwoord van de beheerder wordt gecompromitteerd.  <br><br>Wanneer u MFA inschakelt, moet de gebruiker de volgende keer dat deze zich aanmeldt een alternatief e-mailadres en telefoonnummer opgeven voor accountherstel.  <br> [Meervoudige verificatie instellen](../security-and-compliance/set-up-multi-factor-authentication.md)          |

  
## <a name="some-roles-are-missing-from-active-users--manage-admin-roles-where-did-they-go"></a>Sommige rollen ontbreken in Actieve gebruikers > Beheerdersrollen beheren. Waar zijn ze gebleven?
Standaard tonen we eerst de rollen die de meeste organisaties gebruiken. Als u een rol niet kunt vinden, gaat u naar het einde van de lijst en selecteert u **Meer rollen weergeven**.

## <a name="how-can-i-tell-which-permissions-are-assigned-to-me"></a>Hoe kan ik zien welke machtigingen aan mij zijn toegewezen?
Als er een bericht wordt weergegeven in het Beheercentrum waarin wordt aangegeven dat u geen machtigingen hebt om een instelling of pagina te bewerken, komt dit omdat u een rol hebt toegewezen gekregen die deze machtiging niet omvat.

## <a name="what-about-the-azure-active-directory-roles"></a>Hoe zit het met de rollen in Azure Active Directory? 

De Azure-Portal heeft meer rollen beschikbaar dan het Microsoft 365-beheercentrum. Als u een groot bedrijf hebt, kunnen er rollen zijn in de Azure-portal die beantwoorden aan de behoeften van uw organisatie.

Zie [Machtigingen voor beheerdersrollen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)voor een lijst en een omschrijving van alle rollen in Azure Active Directory.

Een gebruiker aan wie een beheerdersrol is toegewezen, heeft dezelfde toegangsrechten voor alle cloudservices waarop de organisatie zich heeft geabonneerd. Dit is onafhankelijk van het feit of u de rol toewijst in het Microsoft 365-beheercentrum, in het Azure Portal of door de Azure AD-module voor Windows PowerShell te gebruiken.
  
## <a name="roles-available-in-the-microsoft-365-admin-center"></a>Rollen die beschikbaar zijn in het Microsoft 365-beheercentrum

In het Microsoft 365-beheercentrum kunt u meer dan 30 Azure AD-rollen beheren. Deze rollen vormen echter een subset van de rollen die beschikbaar zijn in de Azure-Portal.

::: moniker range="o365-worldwide"

In het Beheercentrum kunt u naar **Rollen**gaan en vervolgens een rol selecteren om het detailvenster te openen. Selecteer het tabblad **Machtigingen** om de gedetailleerde takenlijst weer te geven met wat de beheerders die aan die rol zijn toegewezen kunnen doen.

::: moniker-end

Waarschijnlijk hoeft u alleen de volgende rollen in uw organisatie toe te wijzen. (Zie [machtigingen voor beheerdersrol in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)voor meer informatie, waaronder de cmdlets die zijn gekoppeld aan een rol.)

|Beheerdersrol     |Aan wie moet deze rol worden toegewezen?  |
|---------|---------|
|Exchange-beheerder     |   Wijs de Exchange-beheerdersrol toe aan gebruikers die de e-mailpostvakken, Office 365-groepen en Exchange Online van uw gebruikers moeten kunnen bekijken en beheren. <br><br> Exchange-beheerders kunnen ook het volgende doen:<br> - Verwijderde items herstellen in het postvak van een gebruiker <br> Gedelegeerden instellen voor 'Verzenden als' en 'Verzenden namens'. <br>  |
|Algemene beheerder     |   Wijs de Globale beheerdersrol toe aan gebruikers die wereldwijde toegang nodig hebben tot de meeste beheerfuncties en -gegevens via Microsoft online services. <br><br> Te veel gebruikers globale toegang geven is een beveiligingsrisico, we raden u dan ook aan om 2 tot 4 globale beheerders te hebben. <br><br> Alleen globale beheerders kunnen het volgende doen:<br> - Wachtwoorden voor alle gebruikers opnieuw instellen <br> - Domeinen toevoegen en beheren <br> <br> **Opmerking:** de persoon die zich heeft geregistreerd voor Microsoft Online Services, wordt automatisch een globale beheerder. |
|Algemene lezer    |   Wijs de rol van algemene lezer toe aan gebruikers die beheerdersfuncties en -instellingen moeten bekijken in beheercentra die de globale beheerder kan zien. De beheerder van de algemene lezers kan geen instellingen bewerken.   |
|Groepsbeheerder     |   Wijs de groepsbeheerdersrol toe aan gebruikers die alle groepsinstellingen in alle beheercentra moeten beheren, inclusief het Microsoft 365-Beheercentrum en de Azure Active Directory-Portal. <br><br> Groepsbeheerders kunnen het volgende doen:<br> - Office 365 Groepen maken, bewerken, verwijderen en herstellen <br> - Beleid voor het maken, verlopen en benoemen van groepen maken en bijwerken <br> - Azure Active Directory-beveiligingsgroepen maken, bewerken, verwijderen en herstellen| 
|Helpdesk-beheerder     |   Wijs de beheerdersrol Helpdesk toe aan gebruikers die de volgende taken moeten uitvoeren:<br> - Wachtwoorden opnieuw instellen <br> - Gebruikers dwingen zich af te melden <br> - Serviceaanvragen beheren <br> - De servicestatus bewaken <br> <br> **Opmerking**: de Helpdesk-beheerder kan alleen niet-beheerders helpen en gebruikers die deze rollen hebben toegewezen: Directory-lezer, Gast-invite, Helpdesk-beheerder, Berichtencentrum-lezer en Rapportlezer.      |
|Office-apps beheerder    |   Wijs de beheerdersrol Office Apps toe aan gebruikers die de volgende taken moeten uitvoeren: <br> - Gebruik de Office-cloudbeleidservice om cloudgebaseerd beleid voor Office te maken en te beheren <br> - Serviceaanvragen maken en beheren <br> - Inhoud over nieuwe functies beheren die gebruikers in hun Office-apps zien   <br> - De servicestatus bewaken  |
|Servicebeheerder    |   Wijs de service-beheerdersrol als een extra rol toe aan beheerders of gebruikers wiens rol niet het volgende omvat, maar die nog steeds het volgende moeten doen: <br> - Serviceaanvragen openen en beheren <br> - Berichten in het berichtencentrum bekijken en delen   |
|SharePoint-beheerder    |   Wijs de SharePoint-beheerdersrol toe aan gebruikers die het SharePoint Online-beheercentrum moeten openen en beheren. <br><br>SharePoint-beheerders kunnen ook het volgende doen: <br> - Sites maken en verwijderen <br> - Siteverzamelingen en wereldwijde SharePoint-instellingen beheren   |
|Teams-servicebeheerder    |   Wijs de rol Teams-servicebeheerder toe aan gebruikers die het Teams-beheercentrum moeten openen en beheren. <br><br>Teams-servicebeheerders kunnen ook: <br> - Vergaderingen beheren <br> - Vergaderbruggen beheren <br> - Alle organisatiebrede instellingen beheren, inclusief federatie, Teams-upgrade en Teams-clientinstellingen   |
|Gebruikersbeheerder     |    Wijs de beheerdersrol Gebruikers toe aan gebruikers die de voor alle gebruikers de volgende taken moeten uitvoeren: <br> - Gebruikers en groepen toevoegen <br> - Licenties toewijzen <br> - De meeste gebruikerseigenschappen beheren <br> - Gebruikersweergaven maken en beheren <br> - Verloopbeleid voor wachtwoorden bijwerken <br> - Serviceaanvragen beheren <br> - De servicestatus bewaken <br><br>  De gebruikersbeheerder kan ook de volgende acties uitvoeren voor gebruikers die geen beheerders zijn en voor gebruikers die de volgende rollen hebben gekregen: adreslijst lezer, gast invite, helpdesk-beheerder, Message Center Reader, rapportlezer: <br> - Gebruikersnamen beheren<br> - Gebruikers verwijderen en herstellen<br> - Wachtwoorden opnieuw instellen <br> - Gebruikers dwingen zich af te melden <br> - Apparaatsleutels bijwerken (FIDO)   |

### <a name="all-roles"></a>Alle rollen

 Hieronder ziet u een lijst met alle beheerdersrollen die beschikbaar zijn in het Microsoft 365-beheercentrum.

|Beheerdersrol     |Beschrijving  |
|---------|---------|
|Toepassingsbeheerder     |    Volledige toegang tot bedrijfstoepassingen, toepassingsregistraties en proxy-instellingen van toepassingen.     |
|Toepassingsontwikkelaar     |    Creëer toepassingsregistraties en geef toestemming voor app-toegang namens hen.     |
|Verificatiebeheerder     |    Kan gebruikers verplichten om authenticatie opnieuw te registreren voor niet-wachtwoordreferenties, zoals MFA.     |
|Azure Information Protection-beheerder     |   Beheert labels voor het Azure Information Protection-beleid, beheert beveiligingssjablonen en activeert bescherming.       |
|Factureringsbeheerder     |    Schaft producten aan, beheert abonnementen en ondersteuningstickets, en bewaakt de servicestatus.     |
|Cloud Toepassingsbeheerder     | Volledige toegang tot bedrijfstoepassingen en toepassingsregistraties. Geen toepassingsproxy.     |
|Cloud apparaat-beheerder     |    Kan apparaten inschakelen, uitschakelen en verwijderen en BitLocker-toetsen voor Windows 10 lezen.     |
|Beheerder voor naleving     |    Beheert wettelijke vereisten en eDiscovery-zaken, houdt gegevensbeheer voor locaties, identiteiten en apps bij.     |
|Gegevensbeheerder voor naleving     |    Houdt gegevens bij, zorgt ervoor dat deze worden beschermd, krijgt inzicht in problemen en helpt risico's te beperken.     |
|Beheerder voor voorwaardelijke toegang     |   Beheert de instellingen voor voorwaardelijke toegang van Azure Active Directory, maar niet het beleid voor voorwaardelijke toegang van Exchange ActiveSync.      |
|Fiatteur voor toegang tot klant-lockbox     |      Beheert de klant-lockbox-aanvragen en schakelt deze in of uit.   |
|Beheerder van bureaubladanalyse     |   Kan de beheerprogramma's en -services van het bureaublad openen en beheren.      |
|Dynamics 365-beheerder     |  Volledige toegang tot Microsoft Dynamics 365 Online, beheert serviceaanvragen, bewaakt de servicestatus.       |
|Exchange-beheerder     |  Volledige toegang tot Exchange Online, kan groepen maken en beheren, serviceaanvragen beheren en de servicestatus controleren.    |
|Externe identiteitsprovider beheerder    |     Configureer identiteitsproviders voor gebruik in directe federatie.    |
|Algemene beheerder     |    Heeft onbeperkte toegang tot alle beheerfuncties en de meeste gegevens in alle beheerdcentra.     |
|Algemene lezer     |    Heeft alleen-lezen toegang tot alle beheerfuncties en de meeste gegevens in alle beheerdcentra. Zie [Machtigingen voor beheerdersrol in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader) voor een gedetailleerde beschrijving van de toegangsrechten en beperkingen van deze rol.    |
|Groepsbeheerder   |Maakt groepen en beheert alle groepsinstellingen in beheercentra.|
|Gast invite     |    Beheert uitnodigingen voor Azure Active Directory B2B-gastgebruikers.     |
|Helpdesk-beheerder     | Stelt wachtwoorden opnieuw in en verifieert opnieuw voor alle niet-beheerders en sommige beheerdersrollen, beheert serviceaanvragen en bewaakt de servicestatus.      |
|Intune-beheerder     | Volledige toegang tot intune, beheert gebruikers en apparaten om beleid te koppelen, maakt en beheert groepen.      |
|Kaizala-beheerder     |    Volledige toegang tot alle Kaizala-beheerfuncties en -gegevens, beheert serviceaanvragen.     |
|Licentiebeheerder     |     Wijst licenties toe en verwijdert deze van gebruikers en bewerkt hun gebruikslocatie.    |
|Privacy-lezer voor berichtencentrum     |    Toegang tot privacy-berichten in Berichtencentrum, ontvangt e-mail meldingen.     |
|Berichtencentrumlezer     | Leest en deelt normale berichten in Berichtencentrum, ontvangt wekelijkse e-mailsamenvattingen, heeft alleen-lezen toegang tot gebruikers, groepen, domeinen en abonnementen.     |
|Office-apps beheerder    |   Beheert cloudgebaseerd beleid voor Office en de nieuwe inhoud die gebruikers in hun Office-apps zien.   |
|Power BI-beheerder    |   Volledige toegang tot Power BL-beheertaken, beheert serviceaanvragen en bewaakt de servicestatus.   |
|Power platform-beheerder     |    Volledige toegang tot Microsoft Dynamics 365, PowerApps, beleid voor preventie van gegevensverlies en Microsoft Flow.     |
|Beheerder van rolbevoegdheden     |    Hiermee beheert u roltoewijzingen en alle toegangsbeheerfuncties voor het beheer van vertrouwde identiteiten.     |
|Bevoorrechte verificatiebeheerder     |    Deze stelt wachtwoorden opnieuw in, werkt niet-wachtwoordreferenties bij, dwingt gebruikers zich af te melden, bewaakt de servicestatus en beheert serviceaanvragen.     |
|Rapportenlezer     |   Leest gebruiksrapportagegegevens van het rapportagedashboard, PowerBI-acceptatie-inhoudspakket, inlograpporten en Microsoft Graph-rapportage-API.      |
|Zoekbeheerder     |    Volledige toegang tot Microsoft Search, wijst de rollen zoekbeheer en zoekeditor toe, beheert redactionele inhoud, bewaakt de servicestatus en maakt serviceaanvragen.     |
|Zoekeditor     |    Kan alleen inhoud maken, bewerken en verwijderen voor Microsoft Search, zoals bladwijzers, Q & A en locaties.     |
|Beveiligingsbeheerder     |    Beheert de beveiliging van de organisatie, beheert het beveiligingsbeleid, beoordeelt beveiligingsanalyses en rapporten, bewaakt het dreigingslandschap.     |
|Beveiligingsoperator     |    Onderzoekt en reageert op beveiligingswaarschuwingen, beheert functies in het Identiteitsbeschermingscentrum en bewaakt de gezondheid van de service.     |
|Beveiligingslezer     |    Alleen-lezen toegang tot beveiligingsfuncties, aanmeldrapporten en auditlogboeken.     |
|Service support-beheerder     |    Maakt serviceaanvragen voor Azure-, Microsoft 365-en Office 365-services en bewaakt de servicestatus.     |
|SharePoint-beheerder     |    Volledige toegang tot SharePoint Online, beheert Office 365-groepen, beheert serviceaanvragen en bewaakt de servicestatus.     |
|Skype voor Bedrijven-beheerder     | Volledige toegang tot alle Teams- en Skype-functies, Skype-gebruikerskenmerken, beheert serviceaanvragen en controleert de servicestatus.      |
|Teams-beheerder     |    Volledige toegang tot Teams- en Skype-beheercentrum, beheert Office 365-groepen, beheert serviceaanvragen en bewaakt de servicestatus.     |
|Teams communicatiemanager     |    Wijst telefoonnummers toe, maakt en beheert spraak- en vergaderbeleid en leest oproepanalyses.     |
|Ondersteuningstechnicus voor Teams-communicatie     |    Leest oproeprecorddetails voor alle oproepdeelnemers om communicatieproblemen op te lossen.     |
|Ondersteuningsspecialist voor Teams-communicatie     |    Leest details van gebruikersoproepen voor een specifieke gebruiker, om communicatieproblemen op te lossen.|
|Gebruikersbeheerder     |   Gebruikerswachtwoorden opnieuw instellen, gebruikers en groepen maken en beheren, zoals filters, serviceaanvragen beheren en de servicestatus controleren.|

## <a name="delegated-administration-for-microsoft-partners"></a>Gedelegeerd beheer voor Microsoft-partners

Als u met een Microsoft-partner werkt, kunt u aan uw partner beheerdersrollen toewijzen. Zij kunnen op hun beurt gebruikers in uw bedrijf, of hun bedrijf, beheerdersrollen toewijzen. U wilt misschien dat ze dit doen, bijvoorbeeld als ze uw online organisatie voor u opzetten en beheren.
  
Een partner kan deze rollen toewijzen: 
  
- Volledig beheer, met de bevoegdheden die equivalent zijn aan een globale beheerder, met uitzondering van het beheren van meervoudige verificatie via het Partnercentrum.
    
- Beperkt beheer: de bevoegdheden van deze rol zijn te vergelijken met die van een helpdesk-beheerder.

Voordat de partner deze rollen aan gebruikers kan toewijzen, moet u de partner als gedelegeerde beheerder aan uw account toevoegen. Dit proces wordt geïnitieerd door een geautoriseerde partner. De partner stuurt u een e-mailbericht waarin u wordt gevraagd of u de partner toestemming wilt geven om te fungeren als gedelegeerde beheerder. Zie [Partnerrelaties autoriseren of verwijderen](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner)voor instructies.
  
## <a name="related-articles"></a>Verwante artikelen

[Beheerdersrollen toewijzen](assign-admin-roles.md)
  
[Activiteitenoverzichten in het Microsoft 365-beheercentrum](../activity-reports/activity-reports.md)
