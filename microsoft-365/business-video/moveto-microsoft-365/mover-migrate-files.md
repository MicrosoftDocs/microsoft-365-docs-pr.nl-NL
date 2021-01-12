---
title: 'Google-bestanden migreren naar Microsoft 365 voor bedrijven '
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
description: Informatie over het migreren van Google-bestanden naar Microsoft 365 voor bedrijven met behulp van de overzetten.
ms.openlocfilehash: a6f9dbf7803cb552c23b6c6abb13d13d6f3eda5d
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794599"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a>Google-bestanden migreren naar Microsoft 365 voor bedrijven 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

Wanneer u overstapt op Microsoft 365 voor bedrijven, wilt u uw bestanden migreren van Google Drive. U kunt de app voor de verhuizer gebruiken om bestanden te verplaatsen van persoonlijke en gedeelde stations. Zie [migratie van cloud clouds](https://docs.microsoft.com/sharepointmigration/mover-plan-migration) voor meer informatie

> [!NOTE]
> Met de overzetten maakt u een kopie van de bestanden en verplaatst u de kopieën naar Microsoft 365 voor bedrijven. De oorspronkelijke bestanden blijven ook in Google Drive.

## <a name="before-you-start"></a>Voordat u van start gaat

Alle gebruikers moeten zijn aangemeld bij Microsoft 365 voor bedrijven en hun OneDrive voor bedrijven instellen. Hiervoor gaat u naar [Office.com](https://office.com), meldt u zich aan met Microsft 365 for Business credentials en kies vervolgens OneDrive.

## <a name="try-it"></a>Probeer het zelf!

### <a name="install-mover"></a>Installatie overdrijf

1. Meld u aan bij uw Google Workspace-beheerconsole op [admin.Google.com](https://admin.google.com).

1. Kies **apps**, **apps voor Google Workspace** en vervolgens **app toevoegen aan de lijst voor installeren** van de domein.

1. Zoek de Verhuizer en selecteer deze.

1. Kies **domein installeren** en vervolgens **Doorgaan**.

1. Controleer de machtigingen, schakel het selectievakje in om de voorwaarden te accepteren en selecteer vervolgens **toestaan**, kies **volgende** en vervolgens **gereed**.

### <a name="create-connectors-and-run-the-migration"></a>Connectors maken en de migratie uitvoeren

1. Ga terug naar **apps voor Google Workspace Marketplace**.
1. Vernieuw de browser en selecteer de app over de **verhuizer** .
1. Schuif omlaag en klik op de koppeling voor universeel navigatie.
1. Selecteer **nieuwe connector machtigen**, ga naar **G suite (beheerder)** en kies **autoriseren**.
1. Wijzig desgewenst de **weergavenaam** en selecteer vervolgens **machtigen**.
1. Kies een Google-beheerdersaccount, Controleer de machtigingen en selecteer **toestaan**.

    Met de functie aandrijfman wordt het aantal team stations en gebruikersstations weergegeven dat is gedetecteerd. 

1. Kies onder **bestemming selecteren** de optie **nieuwe connector machtigen**, zoek **Office 365** en selecteer **autoriseren**.
1. Als u machtigingen wilt verlenen aan de app-app in uw Azure Active Directory, gaat u naar [aka.MS/Office365MoverAuth](https://aka.ms/Office365MoverAuth).
1. Selecteer **Office 365-Aandrijfing**, **machtigingen**, **verlenen beheerder akkoord voor uw bedrijf**.
1. Kies uw account, Controleer de machtigingen en selecteer **accepteren**.
1. Kies **Eigenschappen** en controleer of **gebruikerstoewijzing vereist is?** is ingeschakeld.
1. Ga terug naar de verplaatsings-app, Wijzig desgewenst de **weergavenaam**, kies **machtigen** en selecteer vervolgens een Microsoft-beheerdersaccount.

    Met de aandrijf functie wordt u geïnformeerd over het aantal sites en gebruikers van SharePoint Online (of SPO).
1. Kies **Doorgaan met migratie instellen**, selecteer **gebruikers toevoegen** en vervolgens **automatisch gebruikers ontdekken en toevoegen**.

    Met de app voor het verplaatsen van een map wordt geprobeerd om stations van het bronpad in Google toe te wijzen aan het doelpad in Microsoft 365. 

    Als een station niet automatisch wordt toegewezen, voegt u het doelpad toe aan een CSV-bestand, dat we later gebruiken om het gedeelde station te migreren naar een SharePoint-documentbibliotheek. 

1. In dit geval hebben we een SharePoint-site met de naam gemigreerde bestanden toegevoegd en noteert u de URL voor de pagina documenten. 
1. Vervolgens maakt u een CSV-bestand met de indeling van bronpad, doelpad en labels. 

    Zie [aka.MS/movercsv](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv)voor meer informatie.

    Wanneer u de URL van het doelpad toevoegt, moet u alles verwijderen na gedeelde documenten, bijvoorbeeld omdat deze volledige URL niet werkt: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`

    Wijzigen in: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`

1. Als het CSV-bestand klaar is, selecteert u **migratie acties**, **toevoegen aan migratie**, en **kiest u een bestand om te uploaden**.
1. Ga naar het CSV-bestand, selecteer het en kies vervolgens **openen**.
1. Selecteer de stations van de gebruiker van wie u de bestanden wilt migreren en kies vervolgens **migratie gebruikers starten**.
1. Controleer de migratiegegevens, Kies wanneer u de migratie wilt starten, ga akkoord met de **voorwaarden en** Selecteer vervolgens **Doorgaan**.

Met de app over de Verhuizer wordt u gewaarschuwd wanneer het migratieproces is voltooid.