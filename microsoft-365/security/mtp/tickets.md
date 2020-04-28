---
title: Tickets maken en volgen via ServiceNow
description: Microsoft 365 security center wordt verbeterd met de mogelijkheid om native te maken en te volgen tickets in ServiceNow. Beveiligingsbeheerders kunnen een aanbeveling voor een beveiligde score rechtstreeks naar ServiceNow verzenden en een ticket maken.
keywords: beveiliging, Microsoft 365, M365, beveiligde score, beveiligingscentrum, ServiceNow, tickets, taken
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: eb6af6b11d2d932f3bd2165aa3f597c14feb5ae8
ms.sourcegitcommit: b6c4b514b2cb6739af949780d7e2a5a5c8dcc161
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/27/2020
ms.locfileid: "43901020"
---
# <a name="manage-tickets-through-servicenow"></a>Tickets beheren via ServiceNow

ServiceNow is een populair cloud computing-platform dat bedrijven helpt bij het beheren van digitale workflows voor bedrijfsactiviteiten. Hun Now-platform heeft IT-workflows, werkstromen voor werknemers en klantworkflows. Microsoft werkt samen met ServiceNow om het eenvoudiger te maken voor IT-beheerders om hun tickets en taken op beide platforms te beheren. [Meer informatie over ServiceNow](https://www.servicenow.com/)

Microsoft 365 security center is nu verbeterd met de mogelijkheid om native te maken en te volgen tickets in ServiceNow. Beveiligingsbeheerders kunnen een [verbeteringsactie voor Microsoft Secure Score](microsoft-secure-score.md) rechtstreeks naar ServiceNow verzenden en een ticket maken. Zowel incident management en change management tickets kunnen worden gemaakt. Ze kunnen vervolgens worden gevolgd op de startpagina van het Microsoft-beveiligingscentrum en ServiceNow.

## <a name="prerequisites"></a>Vereisten

Toegang hebben tot het Microsoft 365-beveiligingscentrum en een Instantie ServiceNow met:  

* Kingston of hogere versie
* Hi-referenties voor beheerders hebben
* Beheerdersrechten hebben voor uw doelleverancier

ServiceNow raadt gebruikers aan de standaardinstellingen in uw ServiceNow-exemplaar te behouden. Het hebben van aanpassingen kan fouten veroorzaken bij het invullen van de installatiechecklist en integratie met het Microsoft 365-beveiligingscentrum.

## <a name="data-exchange"></a>Gegevensuitwisseling

Wanneer u het Microsoft 365-beveiligingscentrum aansluit op ServiceNow, ontvangt Microsoft de volgende aanvullende gegevens:

* Naam van instantie ServiceNow
* ServiceNow-client-id
* ServiceNow klant geheim
* ServiceNow toegang tot & tokens vernieuwen

Wanneer u een ServiceNow-ticket maakt vanuit het Microsoft 365-beveiligingscentrum, worden de volgende gegevens naar ServiceNow verzonden:

* Gebruikersnaam waarmee de het maken van het ticket wordt geïnitieerd
* Taaknaam
* Taakbeschrijving
* Priority
* Vervaldatum
* Aanbevelingsbron (aanbeveling van de gebruiker of aanbeveling van Microsoft)
* Aanbevelingscategorie (apparaten, gegevens, apps, identiteit, infrastructuur)

## <a name="connect-microsoft-365-security-center-to-servicenow"></a>Microsoft 365-beveiligingscentrum verbinden met ServiceNow

Navigeer naar de startpagina van het Microsoft 365-beveiligingscentrum om de ServiceNow-verbindingskaart te bekijken.

![Gebruikt u ServiceNow](../../media/do-you-use-servicenow-250.png)

Selecteer 'Verbinding maken met ServiceNow' om naar de installatiepagina servicenow te gaan. Volg de instructies om de Microsoft 365 Connector-app te autoriseren.

> [!NOTE]
> Voordat u de verbinding tussen Microsoft 365-beveiligingscentrum en ServiceNow autoriseert, moet u ervoor zorgen dat u de inlog- en wachtwoord van de integratiegebruiker gebruikt die u in de installatiestappen hebt gemaakt. Gebruik uw persoonlijke referenties niet.

Nadat u de aanwijzingen hebt gevolgd en de verbinding hebt autoriseren, bekijkt u de verbindingsstatus op zowel de verbindingspagina van het Microsoft 365-beveiligingscentrum als op de ervaring van de ServiceNow Microsoft 365 Ticketing Connector-app. Nu bent u helemaal klaar om te beginnen met het maken van taken!

## <a name="create-a-task-and-share-it-to-servicenow"></a>Een taak maken en delen met ServiceNow

Zodra de integratie is ingesteld, maakt u ServiceNow-taken op basis van specifieke verbeteringen van Microsoft Secure Score. Ga naar een verbeteringsactie in Secure Score in de Microsoft 365 security center portal en selecteer het pictogram 'Delen'. Een van de vervolgkeuzeopties is ServiceNow.

![ServiceNow delen in Secure Score](../../media/servicenow-share.png)

Er wordt een taak gegenereerd waar u de prioriteit instellen en de naam, beschrijving of vervaldatum bewerken. Zodra alle vereiste velden zijn ingevuld, stuurt u de taak naar ServiceNow.

De taak is zichtbaar in ServiceNow als een Microsoft 365-aanvraag voor beveiligings- en configuratiewijziging.

## <a name="track-tickets"></a>Tickets volgen

Zodra servicenow-tickets voor wijzigingsbeheer en incidentbeheer zijn gemaakt, worden ze weergegeven op kaarten op de startpagina van het Microsoft 365-beveiligingscentrum. Vanaf deze kaarten u een ticket maken, alle tickets bekijken of de ServiceNow-configuratie beheren.

![ServiceNow verander managementtickets](../../media/change-management-375.png)  ![ServiceNow incident management tickets](../../media/incident-management-375.png)

Als u uw ServiceNow-integratie opnieuw wilt inrichten of beheren in het Microsoft 365-beveiligingscentrum, selecteert u **ServiceNow-configuratie beheren** op een van de kaarten. Verwijder van daaruit de huidige ServiceNow-verbinding en pas de namen van de ticketstatus aan.

Met ServiceNow-tickets zichtbaar in het Microsoft 365-beveiligingscentrum, leven uw taken op een plaats waar ze kunnen worden gevolgd en uitgevoerd naast uw andere beveiligingsdashboarditems.

## <a name="troubleshooting"></a>Problemen oplossen

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a>U ontvangt een foutmelding in de eerste stap van de installatiechecklist (OAuth-creatie)

**Foutbericht**: Bewerking tegen 'oauth_entity' van scope 'x_mioms_m365ticket' is geweigerd vanwege het toegangsbeleid voor de randvan de lijst

De app gaat ervan uit dat elke beheerder op het Instantie ServiceNow OAuth-entiteiten kan maken en lezen. Deze fout kan worden veroorzaakt door een aanpassing op uw exemplaar van ServiceNow, die beperkt wie OAuth-entiteiten kan maken/lezen.

**ServiceNow raadt gebruikers aan de standaardfunctionaliteit te behouden.**

Stel de tabelconfiguraties van de tabel 'toepassingsregisters' in op standaard:

* Label = Aanvraagregistereren
* Naam = oauth_entity
* Toegankelijk vanaf = Alle toepassingsscopes
* Kan lezen = selectievakje ingeschakeld

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a>De OAuth-entiteit valideren die is gemaakt voor Microsoft 365 Security & Compliance-connector

Ga naar de tabel met toepassingsregisters **(Menu > System OAuth > Application Registry)** in ServiceNow en zoek de OAuth-entiteit die door u is gemaakt, met de naam die u hebt toegewezen.

### <a name="logging-in-as-the-integration-user"></a>Inloggen als integratiegebruiker

Voordat u de verbinding tussen Microsoft 365-beveiligingscentrum en ServiceNow autoriseert, moet u ervoor zorgen dat u de inlog- en wachtwoord van de integratiegebruiker gebruikt die u in de installatiestappen hebt gemaakt. Gebruik uw persoonlijke referenties niet.

1. Ga naar de autorisatiepagina in ServiceNow.
2. Als u bent aangemeld met uw persoonlijke referenties, selecteert u de koppeling **Niet u** in de rechterbovenhoek.
3. Meld u aan bij ServiceNow als de integratiegebruiker die u eerder hebt gemaakt op basis van de checklist voor installatie.  
4. Selecteer **Toestaan** op de pagina ServiceNow met de vraag of de Beveiligings - + complianceconnector verbinding kan maken met uw ServiceNow-account.
5. Ga verder met de installatiestappen.

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a>De integratiegebruiker valideren die is gemaakt met de installatiechecklist voor Microsoft 365 Security & Compliance-connector

Ga naar gebruikerstabel **(Menu > gebruikersbeheer > gebruikers)** in ServiceNow en zoek de integratiegebruiker die door u is gemaakt, met de naam die u hebt toegewezen.

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a>Uw bedrijf heeft eenmalige aanmelding ingeschakeld, waardoor u geen verbinding maken met ServiceNow via het Microsoft 365-beveiligingscentrum

Als uw bedrijf eenmalige aanmelding heeft ingeschakeld en u een fout ontvangt of als het inloggen mislukt, volgt u een van de twee oplossingen.

#### <a name="log-into-servicenow-as-the-integration-user"></a>Log in bij ServiceNow als integratiegebruiker

1. Navigeer terug naar de autorisatiepagina in ServiceNow.
2. Selecteer de koppeling **Niet-u** in de rechterbovenhoek.
3. Meld u aan bij ServiceNow als de integratiegebruiker die u eerder hebt gemaakt op basis van de checklist voor installatie.  
4. Selecteer **Toestaan** op de pagina ServiceNow met de vraag of de Beveiligings - + complianceconnector verbinding kan maken met uw ServiceNow-account.
5. Ga verder met de installatiestappen.

#### <a name="create-a-security-admin-user"></a>Een gebruiker van beveiligingsbeheerders maken

1. Maak een gebruiker met beheerdersbevoegdheden voor beveiligingsbeheer in Azure Active Directory. De gebruiker moet dezelfde naam en e-mailadres hebben als de integratiegebruiker die u hebt gemaakt met de checklist voor installatie. U de beveiligingsbeheerrol verwijderen nadat de aanmelding en verbinding is voltooid.
2. Meld u als gebruiker aan bij het Microsoft 365-beveiligingscentrum en volg de installatiestappen.

### <a name="ip-filtering"></a>IP-filtering

Als u IP-filtering hebt ingeschakeld, moet u mogelijk expliciet IP-adressen toestaan. Zie [IP-adrestoegangsbeheer](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) voor informatie over het toestaan van IP-bereiken in ServiceNow. Zie [Azure IP-bereiken en servicetags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) voor een lijst met IP-adressen die u toestaan.

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a>Installatie is voltooid, maar zie geen tickets en kan niet delen

Als de installatie- en installatiestappen zijn voltooid, maar u de ServiceNow-kaarten niet op de startpagina ziet en niet delen https://security.microsoft.com/ticketProvisioningmet ServiceNow vanuit Microsoft Secure Score, controleert u de status van de inrichtingspagina op. Selecteer **Autoriseren** en terugnaar de startpagina. De kaarten moeten verschijnen.

