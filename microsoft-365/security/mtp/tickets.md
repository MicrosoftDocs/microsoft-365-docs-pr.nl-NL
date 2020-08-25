---
title: ServiceNow tickets integreren in Microsoft 365 Beveiligingscentrum en compliance Center
description: Informatie over het maken en bijhouden van tickets in ServiceNow vanuit het Microsoft 365 Beveiligingscentrum en compliance Center.
keywords: beveiliging, Microsoft 365, M365, compliance, compliance Center, Beveiligingscentrum, ServiceNow, tickets, taken, sneeuw, verbinding
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
ms.openlocfilehash: 12ac7d0a3d07749e16443e645f50de8fda185658
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2020
ms.locfileid: "46866777"
---
# <a name="integrate-servicenow-tickets-into-the-microsoft-365-security-center-and-compliance-center"></a>ServiceNow tickets integreren in Microsoft 365 Beveiligingscentrum en compliance Center

[!include[Prerelease information](../includes/prerelease.md)]

ServiceNow is een populaire Cloud computing platform waarmee bedrijven digitale werkstromen voor bedrijfsactiviteiten kunnen beheren. Hun platform bevat IT-werkstromen, werkstromen voor werknemers en workflows van klanten. [Meer informatie over ServiceNow](https://www.servicenow.com/)

Microsoft heeft een samenwerkingsverband gemaakt met ServiceNow, zodat IT-beheerders hun tickets en taken op beide platforms kunnen beheren. [Microsoft 365-Beveiligingscentrum](overview-security-center.md) en het [Microsoft 365 compliance-centrum](https://docs.microsoft.commicrosoft-365/compliance/microsoft-365-compliance-center) worden uitgebreid met de mogelijkheid om in ServiceNow in te stellen en tickets te volgen.

- [**ServiceNow tickets beheren in het Beveiligingscentrum**](tickets-security-center.md)
- **ServiceNow tickets beheren in het compliance Center** (binnenkort beschikbaar)

## <a name="prerequisites"></a>Vereisten

Toegang hebben tot het Microsoft 365-Beveiligingscentrum of het compliance Center en een ServiceNow-exemplaar met:  

* Kingston of hogere versie
* Beheerders HI-referenties hebben
* Beheerdersrechten hebben voor de instantie van uw doel leverancier

U wordt aangeraden gebruikers standaardinstellingen te behouden in uw ServiceNow-exemplaar. Het kan zijn dat bij het voltooien van de installatie checklist en integratie met het Microsoft 365-Beveiligingscentrum fouten zijn opgetreden bij het voltooien

## <a name="data-exchange"></a>Gegevensuitwisseling

Wanneer u het Microsoft 365 Beveiligingscentrum of compliance Center verbindt met ServiceNow, ontvangt Microsoft de volgende aanvullende gegevens:

* Naam van ServiceNow-exemplaar
* ServiceNow client-ID
* ServiceNow client Secret
* ServiceNow Access-& vernieuwingstokens

Wanneer u een ServiceNow-ticket maakt via het Microsoft 365-Beveiligingscentrum of nalevings centrum, worden de volgende gegevens naar ServiceNow verzonden:

* Gebruikers-ID waarmee het maken van tickets wordt gestart
* Taaknaam
* Taakbeschrijving
* Priority
* Vervaldatum
* Bron voor aanbevelingen (gebruikers aanbevelingen of Microsoft aanbevelingen)
* Aanbevelings categorie (apparaten, gegevens, apps, identiteit, infrastructuur)

## <a name="connect-to-servicenow"></a>Verbinding maken met ServiceNow

Ga naar [ServiceNow tickets maken en bijhouden in het Microsoft 365-Beveiligingscentrum](tickets-security-center.md) voor informatie over hoe u verbinding maakt met ServiceNow. Verbinding maken via het nalevings centrum voor Microsoft 365 is binnenkort beschikbaar.

## <a name="troubleshooting"></a>Problemen oplossen

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a>U ontvangt een foutbericht in de eerste stap van de installatie Controlelijst (OAuth-maken)

**Foutbericht**: leesbewerking voor ' oauth_entity ' van de scope ' x_mioms_m365ticket ' is geweigerd vanwege het toegangsbeleid voor meerdere regels via meerdere bereiken

De app ervan uitgaat dat de beheerder van het ServiceNow-exemplaar OAuth-entiteiten kan maken en lezen. Deze fout kan worden veroorzaakt door aanpassingen in uw exemplaar van ServiceNow die beperkingen opleggen voor het maken of lezen van OAuth-entiteiten.

**ServiceNow adviseert dat gebruikers standaardfunctionaliteit behouden.**

De tabel configuraties van Application registers instellen op standaard:

* Label = Application registraties
* Naam = oauth_entity
* Toegankelijk van = alle toepassings bereiken
* Vak kan lezen = selectievakje is geselecteerd

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a>De OAuth-entiteit die is gemaakt voor Microsoft 365-beveiliging valideren & compliance connector

Ga naar de tabel toepassingen registers (**Menu > systeem > voor toepassing toepassing**) in ServiceNow. Zoek de OAuth-entiteit die u hebt gemaakt, met de naam die u eraan hebt toegewezen.

### <a name="signing-in-as-the-integration-user"></a>Aanmelden als de integratiegebruiker

Voordat u de verbinding tussen Microsoft 365 Beveiligingscentrum en ServiceNow machtigt, moet u ervoor zorgen dat u de gebruikers van de gebruikersaanmelding gebruikt en het wachtwoord dat u hebt gemaakt tijdens de installatiestappen. Gebruik geen persoonlijke gegevens.

1. Ga naar de autorisatie pagina in ServiceNow.
2. Als u bent aangemeld met uw persoonlijke referenties, selecteert u de koppeling **niet** in de rechterbovenhoek.
3. Meld u aan bij ServiceNow als de integratiegebruiker die u eerder hebt gemaakt in de installatie controlelijst.  
4. Selecteer **toestaan** op de ServiceNow-pagina om te vragen of de Security + compliance connector verbinding kan maken met uw ServiceNow-account.
5. Ga verder met de instellingsstappen.

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a>De berekeningswijze valideren die is gemaakt met de installatie controlelijst voor Microsoft 365 Security & compliance connector

Ga naar de tabel gebruikers **(Menu > Gebruikersbeheer > gebruikers**) in ServiceNow en zoek de integratie-gebruiker die door u is gemaakt, met de naam die u eraan hebt toegewezen.

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a>Voor uw bedrijf is eenmalige aanmelding ingeschakeld waarmee u geen verbinding kunt maken met ServiceNow via het Microsoft 365-Beveiligingscentrum.

Als uw bedrijf eenmalige aanmelding heeft ingeschakeld en u een foutmelding krijgt of als het niet lukt om u aan te melden, voert u een van de twee oplossingen uit.

#### <a name="sign-in-to-servicenow-as-the-integration-user"></a>Meld u aan bij ServiceNow als de gebruikers van de integratie

1. Ga terug naar de autorisatie pagina in ServiceNow.
2. Selecteer de koppeling **niet die u** in de rechterbovenhoek.
3. Meld u aan bij ServiceNow als de integratiegebruiker die u eerder hebt gemaakt in de installatie controlelijst.  
4. Selecteer **toestaan** op de ServiceNow-pagina om te vragen of de Security + compliance connector verbinding kan maken met uw ServiceNow-account.
5. Ga verder met de instellingsstappen.

#### <a name="create-a-security-admin-user"></a>Een gebruiker met een beveiligingsbeheerder maken

1. Maak een gebruiker met bevoegdheden voor beveiligingsbeheerders in azure Active Directory. De gebruiker moet dezelfde naam en hetzelfde e-mailadres hebben als de integratiegebruiker die u hebt gemaakt vanuit de installatie controlelijst. U kunt de functie beveiligingsbeheerder verwijderen zodra de aanmelding en de verbinding zijn voltooid.
2. Meld u aan bij het Microsoft 365-Beveiligingscentrum als deze gebruiker en volg de instellingsstappen.

### <a name="ip-filtering"></a>IP-filters

Als u IP-filtering hebt ingeschakeld, moet u mogelijk IP-adressen expliciet toestaan. Zie [toegangsbeheer voor IP-adressen](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) voor informatie over het toestaan van IP-bereiken in ServiceNow. Zie [Azure IP-bereiken en service Tags-openbare Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) voor een lijst met IP-adressen die u wilt toestaan.

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a>De installatie is voltooid, maar u ziet geen tickets en kan niet delen

Als u klaar bent met de installatie-en configuratiestappen, maar de ServiceNow-kaarten op de startpagina niet worden weergegeven en u deze niet kunt delen met ServiceNow vanuit Microsoft Secure Score, controleert u de status van de inrichtings pagina op https://security.microsoft.com/ticketProvisioning . Selecteer **geautoriseerd** en ga terug naar de startpagina. De kaarten worden weergegeven.

## <a name="resources"></a>Resources

- [ServiceNow tickets beheren in het Beveiligingscentrum](tickets-security-center.md)