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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Lees hoe u e-mail, contactpersonen en agenda migreert van Google Workspace naar Microsoft 365 voor Bedrijven.
ms.openlocfilehash: cb751b1d2f18b226021bb6f218b62f3ae426f6a4
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928244"
---
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a>Zakelijke e-mail en agenda migreren van Google Workspace

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

U kunt vanuit Google Workspace een migratie door beheerders naar Exchange Online gebruiken. U kunt de e-mail in één keer of in fasen migreren. De volgende stappen laten zien hoe u de e-mailgegevens in één keer migreert. Zie Een G Suite-migratie uitvoeren voor [meer informatie.](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration)

Het migratieproces is in enkele stappen en kan enkele uren tot een paar dagen duren, afhankelijk van de hoeveelheid gegevens die u migreert.

## <a name="try-it"></a>Probeer het zelf!

### <a name="create-a-google-service-account"></a>Een Google Service-account maken

1. Meld u met een Chrome-browser aan bij uw Google Workspace-beheerconsole op [admin.google.com.](https://admin.google.com) 
1. Navigeer in een nieuw tabblad of venster naar de [pagina Serviceaccounts.](https://console.developers.google.com/iam-admin/serviceaccounts) 
1. Selecteer **Project maken,** noem het project en kies **Maken.** 
1. Selecteer **Serviceaccount maken,** voer een naam in, kies **Maken** en vervolgens **Klaar.** 
1. Open **het** menu Acties, **selecteer** Bewerken en noteer de unieke id. U hebt deze id later in het proces nodig. 
1. Open de **sectie Delegatie voor het hele domein** tonen. 
1. Selecteer **Delegatie voor het hele G Suite-domein** inschakelen, voer een productnaam in voor het toestemmingsscherm en kies **Opslaan.** 

    > [!NOTE]
> De productnaam wordt niet gebruikt tijdens het migratieproces, maar moet worden op te slaan in het dialoogvenster.     

1. Open **het** menu Acties opnieuw en selecteer **Sleutel maken.** 
1. Kies **JSON** en vervolgens **Maken.** 

     De persoonlijke sleutel wordt opgeslagen in de downloadmap op uw apparaat.
 
1. Selecteer **Sluiten**. 

### <a name="enable-api-usage-for-the-project"></a>API-gebruik voor het project inschakelen

1. Ga naar de [pagina API's.](https://console.developers.google.com/apis/library) 
1. Voer in de zoekbalk de **Gmail-API in.**
1. Selecteer deze en kies **Inschakelen.**
1. Herhaal deze procedure voor google Agenda-API en Contactpersonen-API. 

### <a name="grant-access-to-the-service-account"></a>Toegang verlenen tot het serviceaccount

1. Ga terug naar de beheerconsole van Google Workspace. 
1. Selecteer **Beveiliging,** schuif omlaag en open **API-besturingselementen.** 
1. Schuif omlaag en selecteer **Delegatie voor het hele domein beheren.**
1. Selecteer **Nieuwe toevoegen** en voer de klant-id in die u eerder hebt noteren.
1. Voer vervolgens de OAuth-scopes voor Google API's in. Deze zijn beschikbaar op [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) in stap 5 en zijn:

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. Kies **Autor.** 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a>Een subdomein maken voor e-mail die naar Microsoft 365 gaat

1. Ga terug naar de **beheerconsole van Google Workspace.**
1. Selecteer Domeinen, **Domeinen beheren** en vervolgens Een **domeinalias toevoegen.**  
1. Voer een domeinalias in, zoals `m365.contoso.com` .
1. Selecteer vervolgens **Doorgaan en controleer het eigendom van het domein.** 

    Domeinverificatie duurt meestal slechts een paar minuten, maar dit kan tot 48 uur duren.

1. Ga naar het [Microsoft 365-beheercentrum.](https://admin.microsoft.com)
1. Selecteer in **het Microsoft 365-beheercentrum** in **het** linkernavigatiemenu Alles **tonen,** **Instellingen,** Domeinen en vervolgens **Domein toevoegen.** 
1. Voer het subdomein in dat u eerder hebt gemaakt en selecteer **Dit domein gebruiken.** 
1. Als u het domein wilt verbinden, selecteert u **Doorgaan.** 
1. Schuif omlaag en noteer de MX-records, CNAME-records en TXT-records. 
1. Ga terug naar de **Google-beheerconsole.**
1. Selecteer **Domeinen,** selecteer **Domeinen beheren,** **Controleer details** en vervolgens **Domein beheren.** 
1. Kies DNS in het linkernavigatie **navigatiecentrum** en schuif omlaag **naar Aangepaste resourcerecords.** 
1. Open de vervolgkeuze met recordtype en selecteer **MX,** typ of kopieer en plak de mx-recordgegevens die u eerder hebt genoteerd, en kies vervolgens **Toevoegen.** 
1. Herhaal dit proces voor de CNAME-record en de TXT-record. 

    Het kan even duren voor deze wijzigingen zijn doorgevoerd.  

1. Ga terug naar waar u was gebleven in het **Microsoft 365-beheercentrum** en selecteer **Doorgaan.** 

Uw domein is nu ingesteld.  

### <a name="create-email-aliases-in-microsoft-365"></a>E-mailaliassen maken in Microsoft 365

Voordat de migratie kan beginnen, moet u e-mailaliassen maken voor uw gebruikers met het nieuwe subdomein. 

1. Als u de volgende stap wilt starten, selecteert u in de **wizard** Domeinen toevoegen in het Microsoft 365-beheercentrum de optie Ga naar **Actieve gebruikers.** 
1. Selecteer een gebruiker en vervolgens **Gebruikersnaam en e-mailadres beheren.** 
1. Selecteer het subdomein **dat** u eerder hebt gemaakt in de vervolgkeuze voor domeinen. 
1. Voer een gebruikersnaam in, selecteer **Toevoegen,** **Wijzigingen opslaan** en sluit het venster. 

    Herhaal deze procedure voor elke gebruiker. 

### <a name="start-the-migration-process"></a>Het migratieproces starten

Wanneer u klaar bent, kunt u gaan migreren. 

1. Schuif in het linkernavigatienavigatiecentrum van **het Microsoft 365-beheercentrum** omlaag naar **beheercentra** en selecteer **Exchange.** 
1. Kies **migratie onder** geadresseerden, **selecteer** **Nieuw,** Migreren naar **Exchange Online,** **kies G Suite-migratie** en vervolgens **Volgende.** 
1. Maak een CSV-bestand met een lijst met de postvakken die u wilt migreren. Zorg ervoor dat het bestand de volgende indeling heeft: 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      Zie voor meer [informatie aka.ms/GoogleWorkspaceMigration.](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac) 

1. Selecteer **Bestand kiezen,** ga naar het CSV-bestand, kies het, **selecteer Openen** en vervolgens **Volgende.** 
1. Controleer het e-mailadres van de beheerder dat u wilt gebruiken voor het testen. 
1. Selecteer **Bestand kiezen,** ga naar het JSON-bestand dat u eerder hebt gemaakt (meestal in de map Downloads op uw computer), kies het, selecteer Openen **en** vervolgens **Volgende.** 
1. Voer een naam in het **veld Nieuwe migratiebatchnaam in.**
1. Voer het subdomein in dat u hebt gemaakt in het veld Doelbezorgingsdomein, selecteer **Volgende** en vervolgens **Nieuw.**  
1. Nadat de gegevens zijn opgeslagen, selecteert u **OK.** 

    U kunt nu de status van de migratie bekijken. 

1. Nadat enige tijd is verstreken, selecteert u Vernieuwen, afhankelijk van het aantal gebruikers dat u **wilt migreren.** 
1. Nadat de status is gewijzigd in **Gesynchroniseerd,** selecteert u **Deze migratiebatch voltooien** en vervolgens **Ja.** 
1. Wanneer het proces is voltooid, wordt uw status gewijzigd in **Voltooid.** 
1. Als u wilt, kunt u **Details weergeven selecteren** voor meer informatie over de migratie. 
1. Selecteer **Sluiten**. 
1. Open Outlook om te controleren of alle e-mailberichten van Google Workspace zijn gemigreerd.
U kunt dit ook herhalen voor agenda-items en contactpersonen.