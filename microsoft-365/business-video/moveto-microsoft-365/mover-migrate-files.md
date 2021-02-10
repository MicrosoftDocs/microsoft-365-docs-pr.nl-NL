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
description: Lees hoe u Google-bestanden migreert naar Microsoft 365 voor Bedrijven met behulp van Mover.
ms.openlocfilehash: 72ea81ad86a20e01b4650915fef96a713b207c3b
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166157"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a>Google-bestanden migreren naar Microsoft 365 voor Bedrijven 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

Wanneer u overstapt op Microsoft 365 voor Bedrijven, wilt u uw bestanden migreren vanuit Google Drive. U kunt de app Mover gebruiken om bestanden te verplaatsen van persoonlijke en gedeelde stations. Zie [Mover Cloud Migration](https://docs.microsoft.com/sharepointmigration/mover-plan-migration)voor meer informatie.

> [!NOTE]
> Mover maakt een kopie van de bestanden en verplaatst de kopieën naar Microsoft 365 voor Bedrijven. De oorspronkelijke bestanden blijven ook in Google Drives behouden.

## <a name="before-you-start"></a>Voordat u van start gaat

Alle gebruikers moeten zich hebben aangemeld bij Microsoft 365 voor Bedrijven en hun OneDrive voor Bedrijven hebben ingesteld. U doet dit door naar de [office.com,](https://office.com)u aan te melden met uw referenties voor Microsoft 365 voor Bedrijven en vervolgens OneDrive te kiezen.

## <a name="try-it"></a>Probeer het zelf!

### <a name="install-mover"></a>Mover installeren

1. Meld u aan bij de beheerconsole van Google Workspace [admin.google.com.](https://admin.google.com)

1. Kies **Apps**  >  **Google Workspace Marketplace-apps** App toevoegen aan de lijst voor het installeren van  >  **domeinen.**

1. Zoek naar Mover en selecteer deze.

1. Kies **Domein installeren** en vervolgens **Doorgaan.**

1. Controleer de machtigingen, schakel het selectievakje in om akkoord te gaan met de voorwaarden, selecteer Vervolgens **Toestaan,** **kies Volgende** en vervolgens **Klaar.**

### <a name="create-connectors-and-run-the-migration"></a>Connectors maken en de migratie uitvoeren

1. Ga terug **naar De Marketplace-apps van Google Workspace.**
1. Vernieuw uw browser en selecteer de **Mover-app.**
1. Schuif omlaag en kies de universele navigatiekoppeling.
1. Selecteer **Nieuwe connector autor toestemming geven,** zoek **G Suite (beheer)** en kies **Autorbeheerder.**
1. Wijzig indien **nodig de weergavenaam** en selecteer **Autor.**
1. Kies een Google-beheerdersaccount, controleer de machtigingen en selecteer **Toestaan.**

    Mover geeft het aantal teamstations en gebruikersstations weer dat is gevonden. 

1. Kies **onder Bestemming selecteren** Nieuwe connector **autor elke** keer, zoek Office **365** en selecteer **Autor.**
1. Als u machtigingen wilt verlenen aan de Mover-app in uw Azure Active Directory, gaat u [naar aka.ms/Office365MoverAuth.](https://aka.ms/Office365MoverAuth)
1. Selecteer **Office 365 Mover,** **Machtigingen,** **beheermachtiging verlenen voor uw bedrijf.**
1. Kies uw account, controleer de machtigingen en selecteer **Accepteren.**
1. Kies **Eigenschappen en** controleer of **gebruikerstoewijzing** vereist is? is ingeschakeld.
1. Ga terug naar de Mover-app, wijzig indien nodig de weergavenaam en selecteer een Microsoft-beheerdersaccount. 

    Mover informeert u over het aantal SharePoint Online-sites (of SPO-sites) en gebruikers dat is gevonden.
1. Kies **Doorgaan met migratie instellen,** selecteer Gebruikers **toevoegen** en vervolgens Gebruikers automatisch ontdekken **en toevoegen.**

    De Mover-app probeert stations uit het bronpad in Google toe te staan aan het doelpad in Microsoft 365. 

    Als een station niet automatisch wordt weergegeven, voegt u het doelpad toe aan een CSV-bestand, dat we later gebruiken om het gedeelde station te migreren naar een SharePoint-documentbibliotheek. 

1. In dit geval hebben we een SharePoint-site met de naam Gemigreerde bestanden toegevoegd en een notitie gemaakt van de URL voor de pagina documenten. 
1. Vervolgens hebben we een CSV-bestand gemaakt met de indeling bronpad, doelpad en tags. 

    Zie de aka.ms/movercsv voor [meer informatie.](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv)

    Wanneer u de URL van het doelpad toevoegt, verwijdert u alles na Gedeelde documenten. Deze volledige URL werkt bijvoorbeeld niet: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`

    Wijzig deze in: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`

1. Wanneer het CSV-bestand klaar is, selecteert u **Migratieacties,** Toevoegen **aan migratie,** **Kies een bestand om te uploaden.**
1. Ga naar het CSV-bestand, selecteer dit en kies **Openen.**
1. Selecteer de stations van de gebruiker van wie u de bestanden wilt migreren en **kies Migratie van gebruikers starten.**
1. Controleer de migratiegegevens, kies wanneer u de migratie wilt starten, ga akkoord met de **algemene** voorwaarden en selecteer **Doorgaan.**

De Mover-app laat u weten wanneer het migratieproces is voltooid.
