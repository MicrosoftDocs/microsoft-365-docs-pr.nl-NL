---
title: Zakelijke e-mail en agenda migreren vanuit Google Workspace
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
description: Meer informatie over het migreren van e-mail, contactpersonen en agenda van Google Workspace naar Microsoft 365 voor Bedrijven.
ms.openlocfilehash: d6639032b379a2cd632b6ab6ee7e4082b1e7be0b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913620"
---
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a>Zakelijke e-mail en agenda migreren vanuit Google Workspace

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

U kunt een migratie van een beheerder naar Exchange Online vanuit Google Workspace gebruiken. U kunt de e-mail in één keer of in fasen migreren. De volgende stappen laten zien hoe u de e-mailgegevens in één keer kunt migreren. Zie Een [G Suite-migratie uitvoeren](/exchange/mailbox-migration/perform-g-suite-migration)voor meer informatie.

Het migratieproces neemt verschillende stappen en kan enkele uren tot een paar dagen duren, afhankelijk van de hoeveelheid gegevens die u migreert.

## <a name="try-it"></a>Probeer het zelf!

### <a name="create-a-google-service-account"></a>Een Google Service-account maken

1. Meld u met een Chrome-browser aan bij uw Google Workspace-beheerconsole op [admin.google.com.](https://admin.google.com) 
1. Ga in een nieuw tabblad of venster naar de [pagina Serviceaccounts.](https://console.developers.google.com/iam-admin/serviceaccounts) 
1. Selecteer **Project maken,** noem het project en kies **Maken.** 
1. Selecteer **Serviceaccount maken,** voer een naam in, kies **Maken** en vervolgens **Klaar.** 
1. Open **het** menu Acties, selecteer **Bewerken** en noteer de unieke id. U hebt deze id later in het proces nodig. 
1. Open de **sectie Overdracht voor het hele domein** tonen. 
1. Selecteer **G Suite Domain-wide Delegation inschakelen,** voer een productnaam in voor het toestemmingsscherm en kies **Opslaan.** 

    > [!NOTE]
> De productnaam wordt niet gebruikt door het migratieproces, maar is nodig om deze op te slaan in het dialoogvenster.     

1. Open het **menu** Acties opnieuw en selecteer **Sleutel maken.** 
1. Kies **JSON** en vervolgens **Maken.** 

     De persoonlijke sleutel wordt opgeslagen in de downloadmap op uw apparaat.
 
1. Selecteer **Sluiten**. 

### <a name="enable-api-usage-for-the-project"></a>API-gebruik voor het project inschakelen

1. Ga naar de [pagina API's.](https://console.developers.google.com/apis/library) 
1. Voer in de zoekbalk **gmail-API in.**
1. Selecteer deze en kies vervolgens **Inschakelen.**
1. Herhaal dit proces voor google Agenda API en Contacts API. 

### <a name="grant-access-to-the-service-account"></a>Toegang verlenen tot het serviceaccount

1. Ga terug naar de beheerconsole van Google Workspace. 
1. Selecteer **Beveiliging,** schuif omlaag en open **API-besturingselementen.** 
1. Schuif omlaag en selecteer **Overdracht voor het hele domein beheren.**
1. Selecteer **Nieuw toevoegen** en voer de client-id in die u eerder hebt gemaakt.
1. Voer vervolgens de OAuth-scopes voor Google-API's in. Deze zijn beschikbaar op [aka.ms/GoogleWorkspaceMigration](/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) in stap 5 en zijn:

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. Kies **Autor.** 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a>Een subdomein maken voor e-mail die naar Microsoft 365 gaat

1. Ga terug naar de **beheerconsole van Google Workspace.**
1. Selecteer Domeinen , **Domeinen beheren** en voeg vervolgens **een domeinalias toe.**  
1. Voer een domeinalias in, zoals `m365.contoso.com` .
1. Selecteer vervolgens **Doorgaan en controleer het eigendom van het domein.** 

    Domeinverificatie duurt meestal slechts enkele minuten, maar het kan tot 48 uur duren.

1. Ga naar het [Microsoft 365-beheercentrum.](https://admin.microsoft.com)
1. Selecteer in **het Microsoft 365-beheercentrum**, in het linkernavigatiemenu, **Alles** **tonen**, Instellingen **,** Domeinen en vervolgens Domein **toevoegen**. 
1. Voer het subdomein in dat u eerder hebt gemaakt en selecteer **Dit domein gebruiken.** 
1. Als u het domein wilt verbinden, selecteert u **Doorgaan.** 
1. Schuif omlaag en noteer de MX-records, CNAME-records en TXT-records. 
1. Ga terug naar de **Google-beheerconsole.**
1. Selecteer **Domeinen,** selecteer **Domeinen beheren,** **Details verifiëren** en vervolgens **Domein beheren.** 
1. Kies in de linkernavigatiebalk **DNS** en schuif omlaag naar **Aangepaste resourcerecords.** 
1. Open de vervolgkeuzekeuze van het recordtype en selecteer **MX,** voer de eerder genoteerde MX-recordgegevens in of kopieer en plak deze en kies **vervolgens Toevoegen.** 
1. Herhaal het proces voor de CNAME-record en de TXT-record. 

    Het kan enige tijd duren voor deze wijzigingen van kracht worden.  

1. Ga terug naar de plek waar u was gebleven in **het Microsoft 365-beheercentrum** en selecteer **Doorgaan.** 

Uw domein is nu ingesteld.  

### <a name="create-email-aliases-in-microsoft-365"></a>E-mailalias maken in Microsoft 365

Voordat de migratie kan beginnen, moet u e-mailalias maken voor uw gebruikers met het nieuwe subdomein. 

1. Als u de volgende stap wilt starten, selecteert u in de **wizard** Domeinen toevoegen in het Microsoft 365-beheercentrum de optie Ga naar **Actieve gebruikers.** 
1. Selecteer vervolgens een gebruiker, **gebruikersnaam en e-mail beheren.** 
1. Selecteer in **de vervolgkeuzekeuzegroep** Domeinen het subdomein dat u eerder hebt gemaakt. 
1. Voer een gebruikersnaam in, **selecteer Toevoegen**, **Wijzigingen opslaan** en sluit het venster. 

    Herhaal dit proces voor elke gebruiker. 

### <a name="start-the-migration-process"></a>Het migratieproces starten

Wanneer u klaar bent, kunt u migreren. 

1. Schuif in de linkernavigatie van het **Microsoft 365-beheercentrum** omlaag naar **Beheercentra** en selecteer **Exchange.** 
1. Kies **onder geadresseerden** **migratie**, selecteer **Nieuw**, Migreren naar **Exchange Online**, kies G **Suite-migratie** en vervolgens **Volgende**. 
1. Maak een CSV-bestand met een lijst met de postvakken die u wilt migreren. Zorg ervoor dat het bestand deze indeling volgt: 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      Zie voor meer [informatie aka.ms/GoogleWorkspaceMigration.](/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac) 

1. Selecteer **Bestand kiezen,** ga naar het CSV-bestand, kies het bestand, **selecteer Openen** en vervolgens **Volgende.** 
1. Controleer het e-mailadres van de beheerder dat u wilt gebruiken om te testen. 
1. Selecteer **Bestand kiezen,** ga naar het JSON-bestand dat u eerder hebt gemaakt (meestal in de map Downloads op uw computer), kies het bestand, **selecteer Openen** en vervolgens **Volgende.** 
1. Voer een naam in het **veld Nieuwe migratiebatchnaam in.**
1. Voer het subdomein in dat u hebt gemaakt in het veld **Doelbezorgingsdomein,** selecteer **Volgende** en vervolgens **Nieuw.** 
1. Wanneer de gegevens zijn opgeslagen, selecteert u **OK.** 

    U kunt nu de status van uw migratie bekijken. 

1. Nadat er enige tijd is verstreken, selecteert u Vernieuwen, afhankelijk van het aantal gebruikers dat u **migreert.** 
1. Als de status is gewijzigd in **Gesynchroniseerd,** selecteert u **Deze migratiebatch voltooien** en vervolgens **Ja.** 
1. Wanneer het proces is voltooid, wordt uw status gewijzigd in **Voltooid.** 
1. Als u wilt, kunt u **Details weergeven selecteren** voor meer informatie over de migratie. 
1. Selecteer **Sluiten**. 
1. Open Outlook om te controleren of alle e-mailberichten van Google Workspace zijn gemigreerd.
U kunt dit ook herhalen voor agenda-items en contactpersonen.