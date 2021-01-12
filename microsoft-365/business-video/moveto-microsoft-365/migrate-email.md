---
title: Zakelijke e-mail en agenda migreren van Google Workspace
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
description: Leer hoe u e-mail, contactpersonen en agenda van Google Workspace migreert naar Microsoft 365 voor bedrijven.
ms.openlocfilehash: ab70a43fb7c26c23ebc9024b1cd2803c164a0aa4
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794603"
---
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a>Zakelijke e-mail en agenda migreren van Google Workspace

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

U kunt een door de beheerder uitgevoerde migratie gebruiken voor Exchange Online vanuit Google Workspace. U kunt de e-mail allemaal tegelijk migreren of in fasen. In de volgende stappen wordt uitgelegd hoe u de e-mail gegevens in één keer migreert. Zie voor meer informatie [een G suite-migratie uitvoeren](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration).

Het migratieproces gaat meerdere stappen uit en kan een paar dagen duren, afhankelijk van de hoeveelheid gegevens die u wilt migreren.

## <a name="try-it"></a>Probeer het zelf!

### <a name="create-a-google-service-account"></a>Een Google-service account maken

1. Meld u met een Chrome-browser aan bij uw Google Workspace-beheerconsole op [admin.Google.com](https://admin.google.com). 
1. Ga in een nieuw tabblad of venster naar de pagina [service accounts](https://console.developers.google.com/iam-admin/serviceaccounts) . 
1. Selecteer **project maken**, geef een naam op voor het project en kies **maken**. 
1. Selecteer **serviceaccount maken**, voer een naam in, kies **maken** en klik vervolgens op **gereed**. 
1. Open het menu **acties** , selecteer **bewerken** en noteer de unieke id. U hebt deze ID later in het proces nodig. 
1. Open de sectie **delegeren op domeinniveau weergeven** . 
1. Selecteer **Schakel G suite Domain-Wide delegering in**, voer een productnaam in voor het scherm voor toestemming en kies **Opslaan**. 

    > [!NOTE]
> De productnaam wordt niet door het migratieproces gebruikt, maar is nodig om in het dialoogvenster op te slaan.     

1. Open het menu **acties** opnieuw en klik op **sleutel maken**. 
1. Kies **JSON** en vervolgens **Create**. 

     De persoonlijke sleutel wordt opgeslagen in de downloadmap van uw apparaat.
 
1. Selecteer **Sluiten**. 

### <a name="enable-api-usage-for-the-project"></a>API-gebruik voor het project inschakelen

1. Ga naar de [pagina api's](https://console.developers.google.com/apis/library). 
1. Voer **Gmail-API** in de zoekbalk in.
1. Selecteer het en kies **inschakelen**.
1. Herhaal dit proces voor de API van Google agenda en contactpersonen. 

### <a name="grant-access-to-the-service-account"></a>Toegang verlenen aan het serviceaccount

1. Ga terug naar de beheerconsole van Google Workspace. 
1. Selecteer **beveiliging**, Blader omlaag en open **besturingselementen** voor de API. 
1. Schuif omlaag en selecteer **delegeren op domeinniveau beheren**.
1. Selecteer **nieuwe toevoegen** en voer de client-id in die u eerder hebt gemaakt.
1. Voer vervolgens de OAuth-bereiken voor Google-Api's in. Deze bevindt zich in [aka.MS/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) in stap 5 en zijn:

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. Kies **machtigen**. 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a>Een subdomein maken voor e-mail die naar Microsoft 365 wordt verzonden

1. Ga terug naar de beheerconsole van **Google Workspace** .
1. Selecteer **domeinen**, **domeinen beheren** en voeg vervolgens **een domeinalias toe**. 
1. Voer een domeinalias like in `m365.contoso.com` .
1. Selecteer vervolgens **Doorgaan en domein eigendom verifiëren**. 

    De domeinverificatie duurt meestal enkele minuten, maar het kan tot 48 uur duren.

1. Ga naar het [Microsoft 365-Beheercentrum](https://admin.microsoft.com).
1. In het **Microsoft 365-Beheercentrum**, in het linkernavigatievenster, selecteert u **AllesWeergeven**, **instellingen**, **domeinen** en vervolgens **domein toevoegen**. 
1. Voer het subdomein in dat u eerder hebt gemaakt en selecteer vervolgens **dit domein gebruiken**. 
1. Als u verbinding wilt maken met het domein, selecteert u **Doorgaan**. 
1. Schuif omlaag en noteer de MX-records, CNAME-records en TXT-records. 
1. Ga terug naar de **Google-beheerconsole**.
1. Selecteer **domeinen**, selecteer **domeinen beheren**, **Controleer de gegevens** en klik vervolgens op **domein beheren**. 
1. Kies in het linkernavigatievenster de optie **DNS** en schuif omlaag naar **Custom resource records**. 
1. Open de vervolgkeuzelijst recordtype en selecteer **MX**, typ of kopieer en plak de gegevens van de MX-record die u eerder hebt vermeld, en kies vervolgens **toevoegen**. 
1. Herhaal het proces voor de CNAME-record en de TXT-record. 

    Het kan enige tijd duren voordat deze wijzigingen worden doorgevoerd.  

1. Ga terug naar de plaats waar u was gebleven in **Microsoft 365-Beheercentrum** en selecteer **Doorgaan**. 

Uw domein is nu ingesteld.  

### <a name="create-email-aliases-in-microsoft-365"></a>E-mail aliassen maken in Microsoft 365

Voordat de migratie kan beginnen, moet u e-mail aliassen voor uw gebruikers maken met het nieuwe subdomein. 

1. Als u wilt beginnen met de volgende stap, selecteert u in de wizard **domeinen toevoegen** in het microsoft 365-Beheercentrum de optie **Ga naar actieve gebruikers**. 
1. Selecteer een gebruiker en vervolgens **gebruikersnaam en E-mail beheren**. 
1. Selecteer in de vervolgkeuzelijst **Domains** het subdomein dat u eerder hebt gemaakt. 
1. Voer een gebruikersnaam in, selecteer **toevoegen**, **wijzigingen opslaan** en sluit het venster. 

    Herhaal dit proces voor elke gebruiker. 

### <a name="start-the-migration-process"></a>Het migratieproces starten

Wanneer u klaar bent met migreren, kunt u de migratie voltooien. 

1. Ga in het linkernavigatievenster van het **Microsoft 365-Beheercentrum** naar **beheer centra** en selecteer **Exchange**. 
1. Kies in het vak **geadresseerden** de optie **Migration**, selecteer **Nieuw**, **migreren naar Exchange Online**, kies de optie **G suite-migratie** en vervolgens **volgende**. 
1. Maak een CSV-bestand met een lijst met de postvakken die u wilt migreren. Zorg ervoor dat het bestand de volgende indeling heeft: 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      Zie [aka.MS/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac)voor meer informatie. 

1. Selecteer **bestand kiezen**, ga naar het CSV-bestand, kies het bestand, selecteer **openen** en klik op **volgende**. 
1. Controleer het e-mailadres van de beheerder dat u wilt gebruiken om te testen. 
1. Selecteer **bestand kiezen**, ga naar het JSON-bestand dat u eerder hebt gemaakt (meestal in de map downloads op uw computer), kies dit, selecteer **openen** en klik op **volgende**. 
1. Voer een naam in het **veld nieuwe migratie batchnaam** in.
1. Typ het subdomein dat u hebt gemaakt in het veld **doel leverings domein** , selecteer **volgende** en klik vervolgens op **Nieuw**. 
1. Wanneer de gegevens zijn opgeslagen, selecteert u **OK**. 

    U kunt nu de status van uw migratie bekijken. 

1. Selecteer **vernieuwen**, afhankelijk van het aantal gebruikers dat u migreert, op het moment dat u de migratie hebt voltooid. 
1. Wanneer de status is gewijzigd in **gesynchroniseerd**, selecteert u **deze migratie batch voltooien** en vervolgens **Ja**. 
1. Wanneer het proces is voltooid, wordt uw status gewijzigd in **voltooid**. 
1. Als u wilt, kunt u **Details weergeven** selecteren voor meer informatie over de migratie. 
1. Selecteer **Sluiten**. 
1. Open Outlook om te controleren of alle e-mailberichten van Google Workspace zijn gemigreerd.
U kunt dit voor agenda-items en contactpersonen ook herhalen.