---
title: Integreer ServiceNow-tickets in het Microsoft 365-beveiligingscentrum en het compliancecenter
description: Meer informatie over het maken en bijhouden van tickets in ServiceNow vanuit het Microsoft 365-beveiligingscentrum en het compliancecenter.
keywords: beveiliging, Microsoft 365, M365, compliance, compliance center, security center, ServiceNow, tickets, taken, SNOW, verbinding
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
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: d258bf3ec4c04eafd22e850329ca925b4c974e94
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086665"
---
# <a name="integrate-servicenow-tickets-into-the-microsoft-365-security-center-and-compliance-center"></a>Integreer ServiceNow-tickets in het Microsoft 365-beveiligingscentrum en het compliancecenter

[!include[Prerelease information](../includes/prerelease.md)]

ServiceNow is een populair cloud computing-platform dat bedrijven helpt bij het beheren van digitale workflows voor bedrijfsactiviteiten. Hun Now-platform heeft IT-workflows, workflows voor werknemers en workflows voor klanten. [Meer informatie over ServiceNow](https://www.servicenow.com/)

Microsoft werkt samen met ServiceNow om het voor IT-beheerders gemakkelijker te maken om hun tickets en taken op beide platforms te beheren. [Microsoft 365 security center](overview-security-center.md) en het [Microsoft 365 compliance center](https://docs.microsoft.commicrosoft-365/compliance/microsoft-365-compliance-center) worden uitgebreid met de mogelijkheid om native tickets te maken en bij te houden in ServiceNow.

- [**ServiceNow-tickets beheren in het beveiligingscentrum**](tickets-security-center.md)
- **ServiceNow-tickets beheren in het compliance center** (binnenkort beschikbaar)

## <a name="prerequisites"></a>Vereisten

Heb toegang tot het Microsoft 365-beveiligingscentrum of compliance center en een ServiceNow-exemplaar met:  

* Kingston of hogere versie
* Beheerders-HI-referenties hebben
* Beheerdersbevoegdheden hebben op de instantie van uw doelleverancier

ServiceNow raadt gebruikers aan de standaardinstellingen in uw ServiceNow-exemplaar te behouden. Het hebben van aanpassingen kan fouten veroorzaken bij het invullen van de installatiechecklist en integratie met het Microsoft 365-beveiligingscentrum.

## <a name="data-exchange"></a>Gegevensuitwisseling

Wanneer u het Microsoft 365-beveiligingscentrum of het compliancecenter verbindt met ServiceNow, ontvangt Microsoft de volgende aanvullende gegevens:

* Naam serviceNow-instantie
* ServiceNow-client-id
* ServiceNow-clientgeheim
* ServiceNow-toegang & tokens vernieuwen

Wanneer u een ServiceNow-ticket maakt vanuit het Microsoft 365-beveiligingscentrum of compliance center, worden de volgende gegevens naar ServiceNow verzonden:

* Gebruikersnaam waarmee het ticket wordt gestart
* Taaknaam
* Taakbeschrijving
* Priority
* Vervaldatum
* Aanbevelingsbron (Aanbeveling van de gebruiker of Aanbeveling van Microsoft)
* Aanbevelingscategorie (Apparaten, Gegevens, Apps, Identiteit, Infrastructuur)

## <a name="connect-to-servicenow"></a>Verbinding maken met ServiceNow

Ga naar [ServiceNow-tickets maken en bijhouden in het Microsoft 365-beveiligingscentrum](tickets-security-center.md) voor meer informatie over hoe u verbinding maken met ServiceNow. Verbinding maken vanuit het Microsoft 365 compliance center is binnenkort beschikbaar.

## <a name="troubleshooting"></a>Problemen oplossen

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a>U ontvangt een foutmelding in de eerste stap van de installatiechecklist (OAuth creation)

**Foutbericht**: Lees de bewerking tegen 'oauth_entity' van scope 'x_mioms_m365ticket' is geweigerd vanwege het toegangsbeleid voor de verschillende scopes van de tabel

De app gaat ervan uit dat elke beheerder op de ServiceNow-instantie OAuth-entiteiten kan maken en lezen. Deze fout kan worden veroorzaakt door een aanpassing in uw exemplaar van ServiceNow, die beperkt wie OAuth-entiteiten kan maken/lezen.

**ServiceNow raadt gebruikers aan de standaardfunctionaliteit te behouden.**

Stel de tabelconfiguraties 'toepassingsregisters' in op standaard:

* Label = Toepassingsregisters
* Naam = oauth_entity
* Toegankelijk vanaf = Alle toepassingsscopes
* Kan lezen = selectievakje ingeschakeld

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a>De OAuth-entiteit valideren die is gemaakt voor Microsoft 365 Security & Compliance-connector

Ga naar de tabel toepassingsregisters **(Menu > System OAuth > Application Registry)** in ServiceNow en zoek de OAuth-entiteit die door u is gemaakt, met de naam die u hebt toegewezen.

### <a name="logging-in-as-the-integration-user"></a>Inloggen als integratiegebruiker

Voordat u de verbinding tussen Microsoft 365-beveiligingscentrum en ServiceNow autoriseert, moet u de aanmelding en het wachtwoord van de integratiegebruiker gebruiken die u in de installatiestappen hebt gemaakt. Gebruik uw persoonlijke referenties niet.

1. Ga naar de autorisatiepagina in ServiceNow.
2. Als u bent aangemeld met uw persoonlijke referenties, selecteert u de koppeling **Niet u** in de rechterbovenhoek.
3. Meld u aan bij ServiceNow als de integratiegebruiker die u eerder hebt gemaakt vanuit de installatiechecklist.  
4. Selecteer **Toestaan** op de ServiceNow-pagina waarin wordt gevraagd of de Security + Compliance Connector verbinding kan maken met uw ServiceNow-account.
5. Ga verder met de installatiestappen.

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a>De integratiegebruiker valideren die is gemaakt met de installatiechecklist voor Microsoft 365 Security & Compliance-connector

Ga naar Gebruikerstabel **(menu > gebruikersbeheer > gebruikers)** in ServiceNow en zoek de integratiegebruiker die door u is gemaakt, met de naam die u hebt toegewezen.

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a>Uw bedrijf heeft één aanmelding ingeschakeld waardoor u geen verbinding maken met ServiceNow via het Microsoft 365-beveiligingscentrum

Als uw bedrijf eenmalige aanmelding heeft ingeschakeld en u een fout ontvangt of als u niet inlogt, volgt u een van de twee oplossingen.

#### <a name="log-into-servicenow-as-the-integration-user"></a>Log in bij ServiceNow als integratiegebruiker

1. Navigeer terug naar de autorisatiepagina in ServiceNow.
2. Selecteer de koppeling **Niet u** in de rechterbovenhoek.
3. Meld u aan bij ServiceNow als de integratiegebruiker die u eerder hebt gemaakt vanuit de installatiechecklist.  
4. Selecteer **Toestaan** op de ServiceNow-pagina waarin wordt gevraagd of de Security + Compliance Connector verbinding kan maken met uw ServiceNow-account.
5. Ga verder met de installatiestappen.

#### <a name="create-a-security-admin-user"></a>Een beveiligingsbeheerder maken

1. Maak een gebruiker met beveiligingsbeheerbevoegdheden in Azure Active Directory. De gebruiker moet dezelfde naam en e-mailadres hebben als de integratiegebruiker die u hebt gemaakt vanuit de installatiechecklist. U de rol van de beveiligingsbeheerder verwijderen zodra de aanmelding en verbinding is voltooid.
2. Meld u als gebruiker aan bij het Microsoft 365-beveiligingscentrum en volg de installatiestappen.

### <a name="ip-filtering"></a>IP-filtering

Als u IP-filtering hebt ingeschakeld, moet u mogelijk expliciet IP-adressen toestaan. Zie [IP-adrestoegangsbeheer](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) voor informatie over het toestaan van IP-bereiken in ServiceNow. Zie [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) for a list of IP addresses to allow.

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a>De installatie is voltooid, maar zie geen tickets en kan niet delen

Als de installatie- en installatiestappen zijn voltooid, maar u de ServiceNow-kaarten niet op de startpagina ziet en niet delen met ServiceNow vanuit Microsoft Secure Score, controleert u de status van de inrichtingspagina op https://security.microsoft.com/ticketProvisioning . Selecteer **Autoriseren** en ga terug naar de startpagina. De kaarten moeten verschijnen.

## <a name="resources"></a>Resources

- [ServiceNow-tickets beheren in het beveiligingscentrum](tickets-security-center.md)