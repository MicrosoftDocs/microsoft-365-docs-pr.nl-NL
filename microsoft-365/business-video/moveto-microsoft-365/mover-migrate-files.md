---
title: 'Google-bestanden migreren naar Microsoft 365 voor Bedrijven '
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Meer informatie over het migreren van Google-bestanden naar Microsoft 365 voor Bedrijven met behulp van Mover.
ms.openlocfilehash: 6feabff7e36e84f7dba56e74333648325cf43920
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913572"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a>Google-bestanden migreren naar Microsoft 365 voor Bedrijven 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

Wanneer u naar Microsoft 365 voor Bedrijven gaat, wilt u uw bestanden migreren vanuit Google Drive. U kunt de Mover-app gebruiken om bestanden te verplaatsen van persoonlijke en gedeelde stations. Zie [Mover Cloud Migration](/sharepointmigration/mover-plan-migration)voor meer informatie.

> [!NOTE]
> Mover maakt een kopie van de bestanden en verplaatst de kopieën naar Microsoft 365 voor Bedrijven. De oorspronkelijke bestanden blijven ook in Google Drives.

## <a name="before-you-start"></a>Voordat u van start gaat

Alle gebruikers moeten zich hebben aangemeld bij Microsoft 365 voor Bedrijven en hun OneDrive voor Bedrijven hebben ingesteld. Hiervoor gaat u naar [office.com,](https://office.com)meld u aan met uw microsoft 365 voor bedrijven-referenties en kiest u Vervolgens OneDrive.

## <a name="try-it"></a>Probeer het zelf!

### <a name="install-mover"></a>Mover installeren

1. Meld u aan bij uw Google Workspace-beheerconsole [op admin.google.com.](https://admin.google.com)

1. Kies **Apps**  >  **Google Workspace Marketplace-apps** App toevoegen aan lijst domein  >  **installeren**.

1. Zoek naar Mover en selecteer deze.

1. Kies **Domein installeren** en ga vervolgens **door.**

1. Controleer de machtigingen, schakel het selectievakje in om akkoord te gaan met de voorwaarden en selecteer vervolgens Toestaan **,** kies **Volgende** en vervolgens **Klaar.**

### <a name="create-connectors-and-run-the-migration"></a>Verbindingslijnen maken en de migratie uitvoeren

1. Ga terug **naar Google Workspace Marketplace-apps.**
1. Vernieuw uw browser en selecteer de **Mover-app.**
1. Schuif omlaag en kies de universele navigatiekoppeling.
1. Selecteer **Nieuwe verbindingslijn machtigen,** **zoek G Suite (beheerder)** en kies **Machtigen.**
1. Wijzig de **weergavenaam**, als u wilt, en selecteer vervolgens **Autor.**
1. Kies een Google-beheerdersaccount, controleer de machtigingen en selecteer **Vervolgens Toestaan.**

    Mover geeft het aantal teamstations en gebruikersstations weer dat is gevonden. 

1. Kies **onder Doel selecteren** de optie Nieuwe **verbindingslijn machtigen**, zoek **Office 365** en selecteer **Autor.**
1. Als u machtigingen wilt verlenen voor de Mover-app in uw Azure Active Directory, gaat u naar [aka.ms/Office365MoverAuth.](https://aka.ms/Office365MoverAuth)
1. Selecteer **Office 365 Mover**, **Machtigingen**, **Beheerders toestemming geven voor uw bedrijf**.
1. Kies uw account, controleer de machtigingen en selecteer **Accepteren.**
1. Kies **Eigenschappen** en controleer of **gebruikerstoewijzing** vereist is? is ingeschakeld.
1. Ga terug naar de Mover-app, wijzig de **weergavenaam**, kies indien u wilt Autor toestemming **en** selecteer vervolgens een Microsoft-beheerdersaccount.

    Mover informeert u over het aantal SharePoint Online-sites (of SPO)-sites en gebruikers dat is gevonden.
1. Kies **Doorgaan met migratie-instelling,** **selecteer Gebruikers toevoegen** en vervolgens Gebruikers automatisch ontdekken en **toevoegen.**

    De Mover-app probeert stations van het bronpad in Google toe te wijden aan het doelpad in Microsoft 365. 

    Als een station niet automatisch wordt uitgedeeld, voegt u het doelpad toe aan een CSV-bestand, dat we later gebruiken om het gedeelde station te migreren naar een SharePoint-documentbibliotheek. 

1. In dit geval hebben we een SharePoint-site met de naam Gemigreerde bestanden toegevoegd en hebben we kennis genomen van de URL voor de pagina documenten. 
1. Vervolgens hebben we een CSV-bestand gemaakt met de indeling Bronpad, Doelpad en Tags. 

    Zie voor meer [informatie aka.ms/movercsv.](/sharepointmigration/mover-create-migration-csv)

    Wanneer u de URL van het doelpad toevoegt, verwijdert u alles na Gedeelde documenten. Deze volledige URL werkt bijvoorbeeld niet: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`

    Wijzig het in: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`

1. Zodra uw CSV-bestand gereed is, selecteert u **Migratieacties**, **Toevoegen aan migratie**, Kies een bestand dat u wilt **uploaden**.
1. Ga naar het CSV-bestand, selecteer het bestand en kies **Openen.**
1. Selecteer de gebruikersstations waarvan u de bestanden wilt migreren en kies **Vervolgens Migrerende gebruikers starten.**
1. Controleer de migratiegegevens, kies wanneer u de migratie wilt starten, ga akkoord met de Voorwaarden **en** selecteer **doorgaan.**

De Mover-app informeert u wanneer het migratieproces is voltooid.