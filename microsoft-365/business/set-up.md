---
title: Microsoft 365 Business Premium instellen
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- TRN_SMB
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Ontdek de installatiestappen voor Microsoft 365 Business Premium, waaronder het toevoegen van een domein en gebruikers, het instellen van beveiligingsbeleid en meer.
ms.openlocfilehash: 74a98e915577cf86ec32a706bd3b8f558f49db95
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227634"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a>Een Microsoft 365 Business Premium instellen in de installatiewizard

## <a name="watch-overview-of-microsoft-365-setup"></a>Bekijk: Overzicht van Microsoft 365 setup

Bekijk deze video voor een overzicht van Microsoft 365 Business Premium installatie.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

## <a name="add-your-domain-users-and-set-up-policies"></a>Uw domein, gebruikers toevoegen en beleidsregels instellen

Wanneer u Microsoft 365 Business Premium, kunt u een domein gebruiken dat u bezit of een domein kopen tijdens [de aanmelding.](sign-up.md)

- Als u tijdens de registratie een nieuw domein hebt gekocht, is uw domein helemaal ingesteld en kunt u doorgaan met [Gebruikers toevoegen en licenties toewijzen](#add-users-and-assign-licenses).

### <a name="add-your-domain-to-personalize-sign-in"></a>Uw domein toevoegen om uw aanmelding te personaliseren

1. Meld u aan bij [Microsoft 365-beheercentrum](https://admin.microsoft.com) met uw globale-beheerdersreferenties. 

2. Kies **Naar setup** om de wizard te starten.

    ![Selecteer Ga naar setup.](../media/gotosetupinadmincenter.png)

3. Op de pagina **Uw Office-apps installeren** kunt u desgewenst de apps op uw eigen computer installeren.
    
4. Voer in de stap **Domein toevoegen** de domeinnaam in die u wilt gebruiken (zoals contoso.com).

    > [!IMPORTANT]
    > Als u tijdens de registratie een domein hebt gekocht, ziet u de stap **Een domein toevoegen** hier niet. Go in plaats daarvan naar [Gebruikers toevoegen](#add-users-and-assign-licenses).

    ![Schermafbeelding van de pagina Uw aanmelding aan uw persoonlijke voorkeur personaliseren.](../media/adddomain.png)

    
4. Volg de stappen in de wizard om DNS-records te maken bij een [DNS-hostingprovider](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) voor Microsoft 365 waarbij wordt gecontroleerd of u de eigenaar bent van het domein. Als u de domeinhost kent, zie ook [Een domein toevoegen aan Microsoft 365.](/microsoft-365/admin/setup/add-domain)

    Als uw hostingprovider GoDaddy of een andere host is die is ingeschakeld met [domeinverbinding](/office365/admin/get-help-with-domains/domain-connect), is het proces eenvoudig en wordt u automatisch gevraagd om u aan te melden en u namens Microsoft te laten verifiëren.

    ![Selecteer Autoriseren op de pagina GoDaddy Toegang bevestigen.](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>Gebruikers toevoegen en licenties toewijzen

U kunt gebruikers toevoegen in de wizard, maar u kunt ook [gebruikers later toevoegen](../admin/add-users/add-users.md) in het beheercentrum. Als u een lokale domeincontroller hebt, kunt u ook gebruikers toevoegen met [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).

#### <a name="add-users-in-the-wizard"></a>Gebruikers toevoegen in de wizard

Alle gebruikers die u in de wizard toevoegt, krijgen automatisch een licentie Microsoft 365 Business Premium toegewezen.

![Schermafbeelding van de pagina Nieuwe gebruikers toevoegen in de wizard](../media/addnewuserspage.png)

1. Als uw Microsoft 365 Business Premium bestaande gebruikers heeft (bijvoorbeeld als u Azure AD-Verbinding maken gebruikt), krijgt u nu een optie om licenties aan hen toe te wijzen. Wijs nu licenties aan hen toe.

2. Nadat u de gebruikers hebt toegevoegd, krijgt u ook een optie voor het delen van inloggegevens met de toegevoegde gebruikers. U kunt de inloggegevens afdrukken, per e-mail versturen of downloaden.

### <a name="connect-your-domain"></a>Uw domein verbinden

> [!NOTE]
> Als u ervoor hebt gekozen om het domein. onmicrosoft te gebruiken of Azure AD Connect hebt gebruikt voor het instellen van gebruikers, wordt deze stap niet weergegeven.
  
Als u services wilt instellen, moet u enkele records bij uw DNS-host of domeinregistrar bijwerken.
  
1. Meestal wordt uw registrar automatisch gedetecteerd met de wizard Setup, en wordt een koppeling weergegeven naar stapsgewijze instructies voor het bijwerken van uw NS-records op de website van de registrar. Als dit niet het geval is, [wijzigt u naamservers](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md)voor het instellen van Microsoft 365 domeinregistrar. 

    - Als u bestaande DNS-records hebt, bijvoorbeeld een bestaande website, maar uw DNS-host is ingeschakeld voor [domeinverbinding](/office365/admin/get-help-with-domains/domain-connect), kiest u **Records toevoegen voor mij**. Accepteer alle standaardinstellingen op de pagina **Uw online services kiezen**, kies **Volgende** en kies **Autoriseren** op de pagina van uw DNS-host.
    - Als u bestaande DNS-records hebt met andere DNS-hosts (niet ingeschakeld voor domeinverbinding), kunt u uw eigen DNS-records beheren om ervoor te zorgen dat de bestaande services verbonden blijven. Zie [Basisinformatie over domeinen](/office365/admin/get-help-with-domains/dns-basics) voor meer informatie.

        ![Pagina Records activeren.](../media/activaterecords.png)

2. Volg de stappen in de wizard en e-mail en andere services worden voor u ingesteld.

### <a name="protect-your-organization"></a>Uw organisatie beveiligen 

Het beleid dat u in de wizard hebt ingesteld, wordt automatisch toegepast op een [beveiligingsgroep](/office365/admin/create-groups/compare-groups#security-groups) met de naam *Alle gebruikers.* U kunt ook extra groepen maken om beleid toe te wijzen in het beheercentrum.

1. Bij Het **vergroten van de** beveiliging tegen geavanceerde cyberdreigingen wordt aanbevolen dat u de standaardinstellingen accepteert om bestanden en koppelingen in Office 365 Office [Geavanceerde](../security/office-365-security/defender-for-office-365.md) bedreigingsbeveiliging te laten scannen.

    ![Schermafbeelding van de pagina Beveiliging verhogen.](../media/increasetreatprotection.png)


2. Accepteer  op de pagina Lekken van gevoelige gegevens voorkomen de standaardinstellingen om Office 365 Data Loss Prevention (DLP) in te stellen om gevoelige gegevens in Office-apps bij te houden en te voorkomen dat deze per ongeluk buiten uw organisatie worden gedeeld.

3. Laat op de pagina Gegevens **beveiligen in Office** voor mobiele apparaten het beheer van mobiele apps aan, vouw de instellingen uit en controleer ze en selecteer vervolgens Beleid voor mobiel **app-beheer maken.**

    ![Schermafbeelding van Gegevens beveiligen in Office pagina voor mobiele apparaten.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a>Windows 10-pc's beveiligen

Selecteer in het linkernavigatienavigatiebalkje  **Setup** en kies vervolgens onder Aanmelden en beveiliging de optie Uw **Windows 10 computers.** Kies **Weergeven om** aan de slag te gaan. Zie [uw computer Windows 10 voor](secure-win-10-pcs.md) volledige instructies.

## <a name="deploy-office-365-client-apps"></a>Client-Office 365 implementeren

Als u ervoor kiest om automatisch Office-apps te installeren tijdens de installatie, worden de apps geïnstalleerd op de Windows 10-apparaten zodra de gebruikers zich hebben aangemeld bij Azure AD vanaf hun Windows-apparaten, met hun werkreferenties.

Als u Office op mobiele iOS- of Android-apparaten wilt installeren, zie Mobiele apparaten instellen voor [Microsoft 365 Business Premium gebruikers.](set-up-mobile-devices.md)

U kunt de Office ook afzonderlijk installeren. Zie [installatie Office op een pc of Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) voor instructies.

## <a name="related-content"></a>Verwante inhoud

[Trainingsvideo's voor Microsoft 365 voor bedrijven](../business-video/index.yml) (koppelingspagina)
