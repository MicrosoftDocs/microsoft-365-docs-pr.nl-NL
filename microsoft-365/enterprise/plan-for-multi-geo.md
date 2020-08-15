---
title: Microsoft 365 multi-geografische abonnement
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: Meer informatie over Microsoft 365 multi-geo, hoe meerdere geografische functies werken en welke geografische locaties beschikbaar zijn voor gegevensopslag.
ms.openlocfilehash: 1924141b86ba3e1c16e4760e0f40d61b6f47ce69
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689200"
---
# <a name="plan-for-microsoft-365-multi-geo"></a>Microsoft 365 multi-geografische abonnement

Deze richtlijnen zijn bedoeld voor beheerders van collectieve beleg bedrijven (MNCs) die de Microsoft 365-Tenant voorbereiden op extra geografies in overeenstemming met de aanwezigheidsgegevens van de onderneming om te voldoen aan de vereisten voor gegevens woonplaats.

In een configuratie van meerdere geo bestaat uw Microsoft 365-Tenant uit een centrale locatie en een of meer satelliet locaties. Dit is één Tenant die over meerdere geo-locaties beslaat. Uw Tenant gegevens, inclusief geografische locaties, worden gemasters in azure Active Directory (Azure AD).

Hier volgen enkele belangrijke termen in meerdere geografische termen waarmee u inzicht krijgt in de basisbeginselen van de configuratie:

-   **Tenant** : de representatie van een organisatie in microsoft 365 waaraan meestal een of meer domeinen zijn gekoppeld (bijvoorbeeld https://contoso.sharepoint.com) . 

-   **Geografische locaties** : de geografische locaties die beschikbaar zijn voor het hosten van gegevens in een microsoft 365-Tenant.

-   **Satelliet locaties** : de extra geo-locaties die u hebt geconfigureerd voor het hosten van gegevens in uw microsoft 365-Tenant. Meervoudige geo-tenants zijn meer dan één geografische locatie, bijvoorbeeld Noord-Amerika en Europa.

-   **Voorkeurs gegevenslocatie (PDL)** : de geografische locatie waar de Exchange-en OneDrive-gegevens van een individuele gebruiker worden opgeslagen. Dit kan door de beheerder worden ingesteld op een van de geo-locaties die voor de Tenant zijn geconfigureerd. Als u de PDL-site wijzigt voor een gebruiker die al een OneDrive-site heeft, worden de OneDrive-gegevens niet automatisch naar de nieuwe geo-locatie verplaatst. Zie [een OneDrive-bibliotheek naar een andere geografische locatie verplaatsen](move-onedrive-between-geo-locations.md) voor meer informatie. Als ze een Exchange-postvak hebben, wordt het postvak automatisch naar de nieuwe voorkeurs locatie van de gegevens verplaatst.

Voor het inschakelen van meervoudige geo hebt u vier belangrijke stappen nodig:

1.  Werk samen met uw accountteam om de mogelijkheden voor meervoudige geo toe te voegen _in Microsoft 365_ serviceplan.

2.  Kies de gewenste satelliet locatie (s) en voeg ze toe aan uw Tenant.

3.  Stel de gewenste locatie in voor de gegevenslocatie van uw gebruikers op de gewenste locatie voor de satelliet. Wanneer een nieuwe OneDrive-site of een ander Exchange-postvak wordt ingericht voor een gebruiker, wordt deze naar de persoonlijke team site ingericht.

4.  Migreer de bestaande OneDrive-sites van uw gebruikers vanaf de centrale locatie naar de gewenste locatie. (Exchange-postvakken worden automatisch gemigreerd wanneer u de PDL van een gebruiker instelt.)

Zie voor meer informatie over deze stappen [Microsoft 365 multi-geo configureren](multi-geo-tenant-configuration.md) .

> [!IMPORTANT]
> Houd er rekening mee dat Microsoft 365 multi-geo niet is ontworpen voor prestatieoptimalisatie, zodat het voldoet aan de vereisten voor data woonplaats. Zie [netwerk planning en prestaties optimaliseren voor Microsoft 365](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) of neem contact op met de ondersteuningsgroep voor informatie over de prestaties optimaliseren voor microsoft 365.

U kunt alle volgende locaties configureren voor satelliet locaties waar u OneDrive-en SharePoint-sites kunt hosten, en Exchange-postvakken. Wanneer u een meervoudige geo-indeling plant, maakt u een lijst met de locaties die u wilt toevoegen aan uw Microsoft 365-Tenant. U wordt aangeraden te beginnen met een of twee satelliet locaties en vervolgens geleidelijk verder uitbreidbaar naar meer geografische locaties, indien nodig.

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

Wanneer u meerdere geografische gebruikers configureert, moet u de mogelijkheid nemen om uw on-premises infrastructuur samen te voegen tijdens het migreren naar Microsoft 365. Als u bijvoorbeeld on-premises bedrijven in Singapore en Maleisië hebt, kunt u deze samenvoegen op de locatie van de APC-Satellite, mits u dit kunt doen met de vereisten voor data woonplaats.

## <a name="best-practices"></a>Aanbevolen procedures

U wordt geadviseerd om een testgebruiker in Microsoft 365 te maken voor het uitvoeren van een eerste test. U wordt aangeraden bepaalde stappen voor testen en verificatie met deze gebruiker uit te voeren voordat u de uitnodigingen voor de productie van Microsoft 365.

Wanneer u klaar bent met het testen van de gebruiker, selecteert u een testgroep – bijvoorbeeld van de IT-afdeling, zodat u de eerste keer OneDrive en Exchange op een nieuwe geografische locatie kunt gebruiken. Selecteer voor de eerste groep gebruikers die nog geen OneDrive hebben. We raden u niet meer dan vijf personen in deze aanvankelijke groep aan en vouwen de aanpak met een batchprocedure geleidelijk.

Elke gebruiker moet een *Voorkeurs gegevenslocatie* (PDL) instellen, zodat microsoft 365 kan bepalen in welke geo-locatie de OneDrive wordt ingericht. De voorkeurs gegevenslocatie van de gebruiker moet overeenkomen met een van de gekozen satelliet locaties of uw centrale locatie. Hoewel het veld PDL niet verplicht is, is het raadzaam een PDL voor alle gebruikers in te stellen. Werkbelasting van een gebruiker zonder een PDL op de centrale locatie wordt ingericht.

Maak een lijst van uw gebruikers en neem hun UPN (User Principal Name) en de locatie code op voor de juiste gegevenslocatie van de gewenste gegevens. Neem de testgebruiker op en uw eerste testgroep waarmee u wilt beginnen. U hebt deze lijst nodig voor de configuratieprocedures.

Als uw gebruikers worden gesynchroniseerd vanuit een on-premises Active Directory-systeem naar Azure Active Directory, moet u de gewenste gegevenslocatie instellen als een Active Directory-kenmerk en dit synchroniseren met behulp van Azure Active Directory Connect. U kunt de voor keurige gegevenslocatie niet rechtstreeks configureren voor gesynchroniseerde gebruikers met behulp van Azure AD PowerShell. De stappen voor het instellen van PDL in Active Directory en het synchroniseren van de app zijn bedoeld in [Azure Active Directory Connect Sync: voorkeurs gegevenslocatie voor Microsoft 365-bronnen configureren](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).

Het beheer van een multigeo-Tenant kan verschillen van een niet-meervoudige geo-Tenant, net zoals een groot aantal SharePoint-en OneDrive-instellingen en-services. U wordt aangeraden [een multifunctionele omgeving te beheren](administering-a-multi-geo-environment.md) voordat u met uw configuratie verdergaat.

Lees de [gebruikerservaring in een meerv-geografische omgeving](multi-geo-user-experience.md) voor informatie over de ervaring van de eindgebruikers in een omgeving met meerdere geografische locaties.

Zie [teams-ervaring in een Microsoft 365 OneDrive en SharePoint Online-pacht](https://docs.microsoft.com/microsoftteams/teams-experience-o365odb-spo-multi-geo)voor meer informatie over de teams-ervaring in een microsoft 365-multitenancy.

Als u wilt beginnen met het configureren van Microsoft 365 multi-geo, raadpleegt u [Microsoft 365 multi-geo configureren](multi-geo-tenant-configuration.md).

Als u klaar bent met de configuratie, kunt u de [OneDrive-bibliotheken van uw gebruikers](move-onedrive-between-geo-locations.md) naar behoefte migreren, zodat uw gebruikers vanaf de gewenste gegevenslocaties kunnen werken.
