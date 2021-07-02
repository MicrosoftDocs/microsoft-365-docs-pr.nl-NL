---
title: Microsoft 365 Business Standard instellen
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- BEA160
description: Wanneer je Microsoft 365 Business Standard aanschaft, heb je de mogelijkheid om een domein te gebruiken dat je bezit of een domein te kopen tijdens de registratie.
ms.openlocfilehash: 188f6c396cfb3a4448306070da0fd75dd11a46b3
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227725"
---
# <a name="set-up-microsoft-business-standard"></a>Microsoft Business Standard installeren



## <a name="add-your-domain-to-personalize-sign-in"></a>Uw domein toevoegen om uw aanmelding te personaliseren

Wanneer u Microsoft 365 Business Standard aanschaft, hebt u de mogelijkheid om een domein te gebruiken dat u bezit of een domein te kopen tijdens de registratie.

- Als u tijdens de registratie een nieuw domein hebt gekocht, is uw domein helemaal ingesteld en kunt u doorgaan met [Gebruikers toevoegen en licenties toewijzen](#add-users-and-assign-licenses).

1. Meld u aan bij [Microsoft 365-beheercentrum](https://admin.microsoft.com) met uw globale-beheerdersreferenties. 

2. Kies **Naar setup** om de wizard te starten.

3. Op de pagina **Uw Office-apps installeren** kunt u desgewenst de apps op uw eigen computer installeren.
    
4. Voer in de stap **Domein toevoegen** de domeinnaam in die u wilt gebruiken (zoals contoso.com).

    > [!IMPORTANT]
    > Als u tijdens de registratie een domein hebt gekocht, ziet u de stap **Een domein toevoegen** hier niet. Go in plaats daarvan naar [Gebruikers toevoegen](#add-users-and-assign-licenses).

    
4. Volg de stappen in de wizard om [DNS-records te maken bij een DNS-hostingprovider voor Office 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) waarmee wordt geverifieerd of u eigenaar bent van het domein. Als u uw domeinhost kent, raadpleeg dan ook [Een domein toevoegen aan Microsoft 365](/microsoft-365/admin/setup/add-domain).

    Als uw hostingprovider GoDaddy of een andere host is die is ingeschakeld met [domeinverbinding](/office365/admin/get-help-with-domains/domain-connect), is het proces eenvoudig en wordt u automatisch gevraagd om u aan te melden en u namens Microsoft te laten verifiëren.

    ![Selecteer Autoriseren op de pagina GoDaddy Toegang bevestigen.](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a>Gebruikers toevoegen en licenties toewijzen

U kunt gebruikers toevoegen in de wizard, maar u kunt ook [gebruikers later toevoegen](../add-users/add-users.md) in het beheercentrum. Als u een lokale domeincontroller hebt, kunt u ook gebruikers toevoegen met [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).

## <a name="add-users-in-the-wizard"></a>Gebruikers toevoegen in de wizard

Alle gebruikers die u toevoegt in de wizard krijgen automatisch een Microsoft 365 Business Standard-licentie toegewezen.

1. Als uw Microsoft 365 Business Standard-abonnement bestaande gebruikers heeft (bijvoorbeeld als u Azure AD Connect hebt gebruikt), hebt u een optie om nu licenties aan hen toe te wijzen. Wijs nu licenties aan hen toe.

2. Nadat u de gebruikers hebt toegevoegd, krijgt u ook een optie voor het delen van inloggegevens met de toegevoegde gebruikers. U kunt de inloggegevens afdrukken, per e-mail versturen of downloaden.

## <a name="connect-your-domain"></a>Uw domein verbinden

> [!NOTE]
> Als u ervoor hebt gekozen om het domein. onmicrosoft te gebruiken of Azure AD Connect hebt gebruikt voor het instellen van gebruikers, wordt deze stap niet weergegeven.
  
Als u services wilt instellen, moet u enkele records bij uw DNS-host of domeinregistrar bijwerken.
  
1. Meestal wordt uw registrar automatisch gedetecteerd met de wizard Setup, en wordt een koppeling weergegeven naar stapsgewijze instructies voor het bijwerken van uw NS-records op de website van de registrar. Zo niet, gaat u naar[Naamservers wijzigen voor het instellen van Office 365 bij een domeinregistrar](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md). 

    - Als u bestaande DNS-records hebt, bijvoorbeeld een bestaande website, maar uw DNS-host is ingeschakeld voor [domeinverbinding](/office365/admin/get-help-with-domains/domain-connect), kiest u **Records toevoegen voor mij**. Accepteer alle standaardinstellingen op de pagina **Uw online services kiezen**, kies **Volgende** en kies **Autoriseren** op de pagina van uw DNS-host.
    - Als u bestaande DNS-records hebt met andere DNS-hosts (niet ingeschakeld voor domeinverbinding), kunt u uw eigen DNS-records beheren om ervoor te zorgen dat de bestaande services verbonden blijven. Zie [Basisinformatie over domeinen](/office365/admin/get-help-with-domains/dns-basics) voor meer informatie.

2. Volg de stappen in de wizard en e-mail en andere services worden voor u ingesteld.

    Wanneer het aanmeldingsproces is voltooid, wordt u doorgestuurd naar het beheercentrum, waar u een wizard volgt om Office-apps te installeren, uw domein toe te voegen, gebruikers toe te voegen en licenties toe te wijzen. Nadat u de eerste installatie hebt voltooid, kunt u de pagina **Instellingen** in het beheercentrum gebruiken om door te gaan met het instellen en configureren van de services die bij uw abonnementen worden geleverd.

    Voor meer informatie over de installatiewizard en de **Installatie** pagina in het beheercentrum, raadpleegt u [Verschil tussen de installatiewizard en de installatiepagina](o365-setup-wizard-and-setup-page.md).

## <a name="finish-setting-up"></a>Installatie voltooien

### <a name="set-up-outlook-for-email"></a>Outlook voor e-mail instellen

1. Zoek in het Startmenu van Windows naar Outlook en selecteer deze.

    (Als u een Mac gebruikt, kunt u Outlook openen in de werkbalk of opzoeken via Finder.)

    Kies **Volgende** in het welkomstscherm als u Outlook net hebt geïnstalleerd.

2. Kies **Bestand** \> **Info** \> **Account toevoegen**.

3. Voer uw Microsoft-e-mailadres in en selecteer **Verbinden**.

## <a name="watch-set-up-outlook-for-email"></a>Bekijk: Outlook voor e-mail instellen

> [!VIDEO https://www.microsoft.com/videoplayer/embed/9fe86884-8a83-42cc-bca9-61a12e6dad31?autoplay=false]
  
Meer informatie vindt u op [Outlook instellen voor e-mail](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f).
  
### <a name="import-email"></a>E-mail importeren

Als u Outlook met een ander e-mailaccount hebt gebruikt, kunt u de e-mail, agenda en contactpersonen van dat account importeren in uw nieuwe Microsoft-account.
  
1. **Uw oude e-mailberichten exporteren**

    Kies in Outlook **Bestand** \> **Openen &amp;Exporteren**\> **Importeren/Exporteren**.

    Selecteer **Naar een bestand exporteren** en volg de stappen voor het exporteren van uw Outlook-gegevensbestand (.pst) en eventuele submappen.

2. **Uw oude e-mails importeren**

    Kies in Outlook opnieuw **Bestand** \> **Openen &amp;Exporteren** \> **Importeren/Exporteren**.

    Selecteer deze keer **Importeren uit een ander programma of bestand** en volg de stappen om het back-upbestand dat u hebt gemaakt tijdens het exporteren van uw oude e-mails te importeren.

## <a name="watch-import-and-redirect-email"></a>Bekijk: E-mail importeren en omleiden

> [!VIDEO https://www.microsoft.com/videoplayer/embed/40f7df36-9e24-44e5-8791-e9ed0dd8fd21?autoplay=false]
  
Meer informatie vindt u op [E-mails in Outlook importeren](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de).

U kunt ook het Exchange-beheercentrum gebruiken om ieders e-mails te importeren. Voor meer informatie raadpleegt u [meerdere e-mailaccounts migreren](/Exchange/mailbox-migration/mailbox-migration).
  
### <a name="use-a-public-website"></a>Een openbare website gebruiken

Microsoft 365 bevat geen openbare website voor uw bedrijf. Als u er toch een wilt maken, kunt u een Microsoft-partner overwegen, zoals GoDaddy of WIX.
  
1. Ga in het beheercentrum naar **Resources** en kies vervolgens **Openbare website**.

2. Kies **Meer informatie** onder een van de opties en registreer u vervolgens bij een websitepartner. Gebruik daarna de hulpmiddelen van deze partner om uw website te configureren en ontwerpen.

## <a name="watch-create-your-business-website"></a>Video: Een zakelijke website maken

> [!VIDEO https://www.microsoft.com/videoplayer/embed/4839abc6-9323-4cbf-a79d-2907235f9ebb]

## <a name="related-content"></a>Verwante inhoud

[Een website maken](../../business-video/create-web-site.md) (video)\
[Microsoft 365 voor uw bedrijf](../../business-video/index.yml) (koppelingspagina)
