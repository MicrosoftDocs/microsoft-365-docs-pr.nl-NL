---
title: Azure Activity Directory-rollen in het Microsoft 365-beheercentrum
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
description: Deze Azure-beheerdersrollen beheren in het Microsoft 365-beheercentrum.
ms.openlocfilehash: b07174763384150a7ae8cda6709f5d0ec5cb40ec
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904490"
---
# <a name="azure-active-directory-roles-in-the-microsoft-365-admin-center"></a>Azure Activity Directory-rollen in het Microsoft 365-beheercentrum

In het Microsoft 365-beheercentrum kunt u meer dan 30 Azure AD-rollen beheren. Deze rollen vormen echter een subset van de rollen die beschikbaar zijn in de Azure-Portal. Als u een groot bedrijf hebt, kunnen er rollen zijn in de Azure-portal die beantwoorden aan de behoeften van uw organisatie. Op zoek naar de gedetailleerde rolbeschrijvingen voor Azure AD? Bekijk [machtigingen voor beheerdersrollen in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).

Een gebruiker aan wie een beheerdersrol is toegewezen, heeft dezelfde toegangsrechten voor alle cloudservices waarop de organisatie zich heeft geabonneerd. Dit is onafhankelijk van het feit of u de rol toewijst in het Microsoft 365-beheercentrum, in het Azure Portal of door de Azure AD-module voor Windows PowerShell te gebruiken.

::: moniker range="o365-worldwide"

In het Microsoft 365-beheercentrum kunt u naar **Rollen** gaan en vervolgens een rol selecteren om het detailvenster te openen. Selecteer het tabblad **Machtigingen** om de gedetailleerde takenlijst weer te geven met wat de beheerders die aan die rol zijn toegewezen kunnen doen. Selecteer het tabblad **toegewezen** of **toegewezen beheerders** om gebruikers toe te voegen aan rollen. Zie [beheerdersrollen toewijzen](assign-admin-roles.md)voor meer informatie over het toewijzen van rollen in het Microsoft 365-beheercentrum.

::: moniker-end

## <a name="all-azure-ad-roles"></a>Alle Azure AD-rollen

Hieronder ziet u een lijst met alle beheerdersrollen die beschikbaar zijn in het Microsoft 365-beheercentrum. Op zoek naar de gedetailleerde rolbeschrijvingen van Microsoft 365-beheerdersrollen? Bekijk [Informatie over beheerdersrollen](./about-admin-roles.md?view=o365-worldwide).

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
|Algemene lezer     |    Heeft alleen-lezen toegang tot alle beheerfuncties en de meeste gegevens in alle beheerdcentra. Zie [Machtigingen voor beheerdersrol in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader) voor een gedetailleerde beschrijving van de toegangsrechten en beperkingen van deze rol.    |
|Groepsbeheerder   |Maakt groepen en beheert alle groepsinstellingen in beheercentra.|
|Gast invite     |    Beheert uitnodigingen voor Azure Active Directory B2B-gastgebruikers.     |
|Helpdesk-beheerder     | Stelt wachtwoorden opnieuw in en verifieert opnieuw voor alle niet-beheerders en sommige beheerdersrollen, beheert serviceaanvragen en bewaakt de servicestatus.      |
|Insights-beheerder     | Beheert alle aspecten van de Microsoft 365 Insights-toepassing, leest Azure Active Directory-gegevens, kan de servicestatus controleren en serviceaanvragen maken en beheren.      |
|Insights-bedrijfsbeheerder     | Lees rapporten en inzichten in de Microsoft 365 Insights-toepassing.      |
|Intune-beheerder     | Volledige toegang tot intune, beheert gebruikers en apparaten om beleid te koppelen, maakt en beheert groepen.      |
|Kaizala-beheerder     |    Volledige toegang tot alle Kaizala-beheerfuncties en -gegevens, beheert serviceaanvragen.     |
|Licentiebeheerder     |     Wijst licenties toe en verwijdert deze van gebruikers en bewerkt hun gebruikslocatie.    |
|Privacy-lezer voor berichtencentrum     |    Toegang tot privacy-berichten in Berichtencentrum, ontvangt e-mail meldingen.     |
|Berichtencentrumlezer     | Leest en deelt normale berichten in Berichtencentrum, ontvangt wekelijkse e-mailsamenvattingen, heeft alleen-lezen toegang tot gebruikers, groepen, domeinen en abonnementen.     |
|Office-apps beheerder    |   Beheert cloudgebaseerd beleid voor Office en de nieuwe inhoud die gebruikers in hun Office-apps zien.   |
|Wachtwoordbeheerder    |   Wachtwoorden opnieuw instellen voor gebruikers die niet-beheerders of leden van de volgende rollen zijn: adreslijstlezers, gastuitnodiger, wachtwoordbeheerder. Deze rol kan het beheren van serviceaanvragen of het controleren van de servicestatus niet toestaan.   |
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
|SharePoint-beheerder     |    Volledige toegang tot SharePoint Online, beheert Microsoft 365-groepen, beheert serviceaanvragen en bewaakt de servicestatus.     |
|Skype voor Bedrijven-beheerder     | Volledige toegang tot alle Teams- en Skype-functies, Skype-gebruikerskenmerken, beheert serviceaanvragen en controleert de servicestatus.      |
|Teams-beheerder     |    Volledige toegang tot Teams- en Skype-beheercentrum, beheert Microsoft 365-groepen, beheert serviceaanvragen en bewaakt de servicestatus.     |
|Teams communicatiemanager     |    Wijst telefoonnummers toe, maakt en beheert spraak- en vergaderbeleid en leest oproepanalyses.     |
|Ondersteuningstechnicus voor Teams-communicatie     |    Leest oproeprecorddetails voor alle oproepdeelnemers om communicatieproblemen op te lossen.     |
|Ondersteuningsspecialist voor Teams-communicatie     |    Leest details van gebruikersoproepen voor een specifieke gebruiker, om communicatieproblemen op te lossen.|
|Gebruikersbeheerder     |   Gebruikerswachtwoorden opnieuw instellen, gebruikers en groepen maken en beheren, zoals filters, serviceaanvragen beheren en de servicestatus controleren.|

## <a name="delegated-administration-for-microsoft-partners"></a>Gedelegeerd beheer voor Microsoft-partners

Als u met een Microsoft-partner werkt, kunt u aan uw partner beheerdersrollen toewijzen. Zij kunnen op hun beurt gebruikers in uw bedrijf, of hun bedrijf, beheerdersrollen toewijzen. U wilt misschien dat ze dit doen, bijvoorbeeld als ze uw online organisatie voor u opzetten en beheren.
  
Een partner kan deze rollen toewijzen: 

- Volledig beheer, met de bevoegdheden die equivalent zijn aan een globale beheerder, met uitzondering van het beheren van meervoudige verificatie via het Partnercentrum.

- Beperkt beheer: de bevoegdheden van deze rol zijn te vergelijken met die van een helpdesk-beheerder.

Voordat de partner deze rollen aan gebruikers kan toewijzen, moet u de partner als gedelegeerde beheerder aan uw account toevoegen. Dit proces wordt geïnitieerd door een geautoriseerde partner. De partner stuurt u een e-mailbericht waarin u wordt gevraagd of u de partner toestemming wilt geven om te fungeren als gedelegeerde beheerder. Zie [Partnerrelaties autoriseren of verwijderen](../misc/add-partner.md)voor instructies.
  
## <a name="related-articles"></a>Verwante artikelen

[Over Microsoft 365-beheersrollen](about-admin-roles.md)

[Beheerdersrollen toewijzen](assign-admin-roles.md)
  
[Activiteitenoverzichten in het Microsoft 365-beheercentrum](../activity-reports/activity-reports.md)