---
title: Microsoft 365 Business Standard instellen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
- TRN_SMB
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- okr_smb
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- BEA160
description: Meer informatie over het instellen van je abonnement op Microsoft 365 Business Standard.
ms.openlocfilehash: e69a3c75d77a8b4721558e72526a068df643f284
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644553"
---
# <a name="set-up-microsoft-business-standard"></a>Microsoft Business Standard installeren

Bekijk een korte video over het instellen van Microsoft 365 Business Standard.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4ELKR]

Als je deze video nuttig vond, raadpleeg dan de [complete reeks trainingen voor kleine bedrijven en nieuwe gebruikers van Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).
  
 *Deze stappen zijn bedoeld voor bedrijven en [non-profitorganisaties](https://go.microsoft.com/fwlink/p/?LinkId=627221) die het **[Microsoft 365 Business Standard-abonnement hebben.](https://go.microsoft.com/fwlink/p/?LinkId=627220)**_

Bekijk een korte video over het instellen van Microsoft 365 Business Standard (voorheen bekend als Office 365 Business Premium).<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/913be1ad-bae1-40c0-9ded-15bb477b828b]

Als je deze video nuttig vond, raadpleeg dan de [complete reeks trainingen voor kleine bedrijven en nieuwe gebruikers van Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="add-your-domain-to-personalize-sign-in"></a>Je domein toevoegen om je aanmelding te personaliseren

Wanneer je Microsoft 365 Business Standard aanschaft, heb je de mogelijkheid om een domein te gebruiken dat je bezit of een domein te kopen tijdens de registratie.

- Als je tijdens de registratie een nieuw domein hebt gekocht, is je domein helemaal ingesteld en kun je doorgaan met [Gebruikers toevoegen en licenties toewijzen](#add-users-and-assign-licenses).

1. Meld je aan bij [Microsoft 365-beheercentrum](https://admin.microsoft.com) met je globale-beheerdersreferenties. 

2. Kies _*Naar setup** om de wizard te starten.

3. Op de pagina **Uw Office-apps installeren** kun je desgewenst de apps op je eigen computer installeren.
    
4. Voer in de stap **Domein toevoegen** de domeinnaam in die je wilt gebruiken (zoals contoso.com).

    > [!IMPORTANT]
    > Als je tijdens de registratie een domein hebt gekocht, zie je de stap **Een domein toevoegen** hier niet. Ga in plaats daarvan naar [Gebruikers toevoegen](#add-users-and-assign-licenses).

    
4. Volg de stappen in de wizard om [DNS-records te maken bij een DNS-hostingprovider voor Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) waarmee wordt geverifieerd of je eigenaar bent van het domein. Als je weet wat je domeinhost is, raadpleeg dan ook de [hostspecifieke instructies](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Als je hostingprovider GoDaddy of een andere host is die [domeinverbinding](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect) gebruikt, is het proces eenvoudig en wordt je automatisch gevraagd om je aan te melden en je namens Microsoft te laten verifiëren.

    ![Selecteer Autoriseren op de pagina GoDaddy Toegang bevestigen.](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a>Gebruikers toevoegen en licenties toewijzen

Je kunt gebruikers toevoegen in de wizard, maar je kunt ook [gebruikers later toevoegen](../add-users/add-users.md) in het beheercentrum. Als je een lokale domeincontroller hebt, kun je ook gebruikers toevoegen met [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).

## <a name="add-users-in-the-wizard"></a>Gebruikers toevoegen in de wizard

Alle gebruikers die je toevoegt in de wizard krijgen automatisch een Microsoft 365 Business Standard-licentie toegewezen.

1. Als je Microsoft 365 Business Standard-abonnement bestaande gebruikers heeft (bijvoorbeeld als je Azure AD Connect hebt gebruikt), heb je een optie om nu licenties aan hen toe te wijzen. Wijs nu licenties aan hen toe.

2. Nadat je de gebruikers hebt toegevoegd, krijgt je ook een optie voor het delen van referenties met de nieuwe gebruikers die je hebt toegevoegd. Je kunt ze afdrukken, per e-mail versturen of downloaden.

## <a name="connect-your-domain"></a>Je domein verbinden

> [!NOTE]
> Als je ervoor hebt gekozen om het domein .onmicrosoft te gebruiken of Azure AD Connect hebt gebruikt voor het instellen van gebruikers, wordt deze stap niet weergegeven.
  
Als je services wilt instellen, moet je enkele records bij je DNS-host of domeinregistrar bijwerken.
  
1. Meestal wordt je registrar automatisch gedetecteerd met de wizard Setup, en wordt een koppeling weergegeven naar stapsgewijze instructies voor het bijwerken van je NS-records op de website van de registrar. Zo niet, ga dan naar[Naamservers wijzigen voor het instellen van Office 365 bij een domeinregistrar](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar). 

    - Als je bestaande DNS-records hebt, bijvoorbeeld een bestaande website, maar je DNS-host is ingeschakeld voor [domeinverbinding](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), kies je **Records toevoegen voor mij**. Accepteer alle standaardinstellingen op de pagina **Uw online services kiezen**, kies **Volgende** en kies **Autoriseren** op de pagina van je DNS-host.
    - Als je bestaande DNS-records hebt met andere DNS-hosts (niet ingeschakeld voor domeinverbinding), kun je je eigen DNS-records beheren om ervoor te zorgen dat de bestaande services verbonden blijven. Zie [basisprincipes van domeinen](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) voor meer informatie.

2. Volg de stappen in de wizard en e-mail en andere services worden voor je ingesteld.

    Wanneer het aanmeldingsproces is voltooid, wordt u doorgestuurd naar het beheercentrum, waar u een wizard volgt om Office-apps te installeren, uw domein toe te voegen, gebruikers toe te voegen en licenties toe te wijzen. Nadat je de eerste installatie hebt voltooid, kun je de pagina **Instellingen** in het beheercentrum gebruiken om door te gaan met het instellen en configureren van de services die bij je abonnementen worden geleverd.

    Voor meer informatie over de installatiewizard en de **Installatie**pagina in het beheercentrum, raadpleeg je [Verschil tussen de installatiewizard en de installatiepagina](o365-setup-wizard-and-setup-page.md).

## <a name="finish-setting-up"></a>Installatie voltooien

### <a name="set-up-outlook-for-email"></a>Outlook voor e-mail instellen

1. Zoek in het Startmenu van Windows naar Outlook en selecteer deze.

    (Als je een Mac gebruikt, kun je Outlook openen in de werkbalk of opzoeken via Finder.)

    Kies **Volgende** in het welkomstscherm als je Outlook net hebt geïnstalleerd.

2. Kies **Bestand** \> ** Info** \> **Account toevoegen**.

3. Voer je Microsoft-e-mailadres in en selecteer **Verbinden**.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/9fe86884-8a83-42cc-bca9-61a12e6dad31?autoplay=false]
  
Meer informatie vind je op [Outlook instellen voor e-mail](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f).
  
### <a name="import-email"></a>E-mail importeren

Als je Outlook met een ander e-mailaccount hebt gebruikt, kun je de e-mail, agenda en contactpersonen van dat account importeren in je nieuwe Microsoft-account.
  
1. **Je oude e-mailberichten exporteren**

    Kies in Outlook **Bestand** \> **Openen &amp;Exporteren **\> **Importeren/Exporteren**.

    Selecteer **Naar een bestand exporteren** en volg de stappen voor het exporteren van je Outlook-gegevensbestand (.pst) en eventuele submappen.

2. **Je oude e-mails importeren**

    Kies in Outlook opnieuw **Bestand** \> **Openen &amp;Exporteren** \> **Importeren/Exporteren**.

    Selecteer deze keer **Importeren uit een ander programma of bestand** en volg de stappen om het back-upbestand dat je hebt gemaakt tijdens het exporteren van je oude e-mails te importeren.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/40f7df36-9e24-44e5-8791-e9ed0dd8fd21?autoplay=false]
  
Meer informatie vind je in [E-mails in Outlook importeren](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de).

Je kunt ook het Exchange-beheercentrum gebruiken om ieders e-mails te importeren. Raadpleeg voor meer informatie [Meerdere e-mailaccounts migreren](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).
  
### <a name="use-a-public-website"></a>Een openbare website gebruiken

Microsoft 365 bevat geen openbare website voor je bedrijf. Als je er toch een wilt maken, kun je een Microsoft-partner overwegen, zoals GoDaddy of WIX.
  
1. Ga in het beheercentrum naar **Resources** en kies vervolgens **Openbare website**.

2. Kies **Meer informatie** onder een van de opties en registreer je vervolgens bij een websitepartner. Gebruik daarna de hulpmiddelen van deze partner om je website te configureren en te ontwerpen.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/4839abc6-9323-4cbf-a79d-2907235f9ebb]

Meer informatie vind je in [Een openbare website gebruiken](https://support.microsoft.com/office/3325d50e-d131-403c-a278-7f3296fe33a9).