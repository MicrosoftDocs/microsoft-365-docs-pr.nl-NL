---
title: Microsoft 365 Business Premium instellen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
ms.openlocfilehash: e7ebe179c67077dc71ae4873b0711d0e810c701a
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044725"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a>Microsoft 365 Business Premium instellen in de installatiewizard

Bekijk deze video voor een overzicht van de configuratie van Microsoft 365 Business Premium.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

## <a name="add-your-domain-users-and-set-up-policies"></a>Uw domein en gebruikers toevoegen en beleidsregels instellen

Wanneer u Microsoft 365 Business Premium koopt, hebt u de mogelijkheid om een domein te gebruiken waar u eigenaar van bent, of om er een te kopen tijdens [de aanmelding.](sign-up.md)

- Als u tijdens de registratie een nieuw domein hebt gekocht, is uw domein helemaal ingesteld en kunt u doorgaan met [Gebruikers toevoegen en licenties toewijzen](#add-users-and-assign-licenses).

### <a name="add-your-domain-to-personalize-sign-in"></a>Uw domein toevoegen om uw aanmelding te personaliseren

1. Meld u aan bij [Microsoft 365-beheercentrum](https://admin.microsoft.com) met uw globale-beheerdersreferenties. 

2. Kies **Naar setup** om de wizard te starten.

    ![Selecteer Ga naar setup.](../media/gotosetupinadmincenter.png)

3. Op de pagina **Uw Office-apps installeren** kunt u desgewenst de apps op uw eigen computer installeren.
    
4. Voer in de stap **Domein toevoegen** de domeinnaam in die u wilt gebruiken (zoals contoso.com).

    > [!IMPORTANT]
    > Als u tijdens de registratie een domein hebt gekocht, ziet u de stap **Een domein toevoegen** hier niet. Ga in plaats daarvan naar [Gebruikers toevoegen](#add-users-and-assign-licenses).

    ![Schermafbeelding van de aanmeldingspagina Personaliseren.](../media/adddomain.png)

    
4. Volg de stappen in de wizard om DNS-records te maken bij een [DNS-hostingprovider voor Microsoft 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) waarbij wordt geverifieerd dat u eigenaar bent van het domein. Als u weet wat uw domeinhost is, raadpleegt u ook de [hostspecifieke instructies](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Als uw hostingprovider GoDaddy of een andere host is die is ingeschakeld met [domeinverbinding](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), is het proces eenvoudig en wordt u automatisch gevraagd om u aan te melden en u namens Microsoft te laten verifiëren.

    ![Selecteer Autoriseren op de pagina GoDaddy Toegang bevestigen.](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>Gebruikers toevoegen en licenties toewijzen

U kunt gebruikers toevoegen in de wizard, maar u kunt ook [gebruikers later toevoegen](add-users-m365b.md) in het beheercentrum. Als u een lokale domeincontroller hebt, kunt u ook gebruikers toevoegen met [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).

#### <a name="add-users-in-the-wizard"></a>Gebruikers toevoegen in de wizard

Aan alle gebruikers die u in de wizard toevoegt, wordt automatisch een Licentie voor Microsoft 365 Business Premium toegewezen.

![Schermafbeelding van de pagina Nieuwe gebruikers toevoegen in de wizard](../media/addnewuserspage.png)

1. Als uw Microsoft 365 Business Premium-abonnement bestaande gebruikers heeft (bijvoorbeeld als u Azure AD Connect hebt gebruikt), krijgt u de optie om nu licenties aan hen toe te wijzen. Wijs nu licenties aan hen toe.

2. Nadat u de gebruikers hebt toegevoegd, krijgt u ook een optie voor het delen van referenties met de nieuwe gebruikers die u hebt toegevoegd. U kunt deze afdrukken, hun een e-mail sturen of deze downloaden.

### <a name="connect-your-domain"></a>Uw domein verbinden

> [!NOTE]
> Als u ervoor hebt gekozen om het domein. onmicrosoft te gebruiken of Azure AD Connect hebt gebruikt voor het instellen van gebruikers, wordt deze stap niet weergegeven.
  
Als u services wilt instellen, moet u enkele records bij uw DNS-host of domeinregistrar bijwerken.
  
1. Meestal wordt uw registrar automatisch gedetecteerd met de wizard Setup, en wordt een koppeling weergegeven naar stapsgewijze instructies voor het bijwerken van uw NS-records op de website van de registrar. Als dit niet het geval is, wijzigt u naamservers voor het instellen van [Microsoft 365 bij een domeinregistrar.](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar) 

    - Als u bestaande DNS-records hebt, bijvoorbeeld een bestaande website, maar uw DNS-host is ingeschakeld voor [domeinverbinding](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), kiest u **Records toevoegen voor mij**. Accepteer alle standaardinstellingen op de pagina **Uw online services kiezen**, kies **Volgende** en kies **Autoriseren** op de pagina van uw DNS-host.
    - Als u bestaande DNS-records hebt met andere DNS-hosts (niet ingeschakeld voor domeinverbinding), kunt u uw eigen DNS-records beheren om ervoor te zorgen dat de bestaande services verbonden blijven. Zie [basisprincipes van domeinen](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) voor meer informatie.

        ![Pagina Records activeren.](../media/activaterecords.png)

2. Volg de stappen in de wizard en e-mail en andere services worden voor u ingesteld.

### <a name="protect-your-organization"></a>Uw organisatie beschermen 

Het beleid dat u in de wizard in stellen, wordt automatisch toegepast op een beveiligingsgroep [met de naam](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) Alle *gebruikers.* U kunt ook extra groepen maken voor het toewijzen van beleidsregels in het beheercentrum.

1. Als u de bescherming tegen geavanceerde **cyberaanvallen** wilt verhogen, wordt u aangeraden de standaardinstellingen te accepteren om Bestanden en koppelingen van [Office 365 Advance Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) te scannen in Office-apps.

    ![Schermafbeelding van de pagina Beveiliging verhogen.](../media/increasetreatprotection.png)


2. Accepteer  op de pagina Voorkom het lekken van gevoelige gegevens de standaardinstellingen om Office 365 Preventie van gegevensverlies (DLP) in te stellen om gevoelige gegevens in Office-apps bij te houden en te voorkomen dat deze per ongeluk worden gedeeld buiten uw organisatie.

3. Op de **pagina Gegevens beveiligen in Office** voor mobiele apparaten laat u het beheer van mobiele apps aan, vouwt u de instellingen uit en controleert u deze en selecteert u Beleid voor het beheer van mobiele apps **maken.**

    ![Schermafbeelding van de pagina Gegevens beveiligen in Office voor mobiele apparaten.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a>Windows 10-pc's beveiligen

Selecteer in het linkernavigatievenster **Setup** en kies vervolgens onder Aanmelden en beveiliging de optie **Uw Windows 10-computers beveiligen.**  Kies **Weergeven om** aan de slag te gaan. Zie [uw Windows 10-computers beveiligen voor](secure-win-10-pcs.md) volledige instructies.

## <a name="deploy-office-365-client-apps"></a>Office 365-clientapps implementeren

Als u ervoor kiest om Office-apps automatisch te installeren tijdens de installatie, worden de apps geïnstalleerd op de Windows 10-apparaten nadat de gebruikers zich met hun Windows-apparaten hebben aangemeld bij Azure AD, met hun werkreferenties.

Zie Mobiele apparaten instellen voor gebruikers van [Microsoft 365 Business Premium](set-up-mobile-devices.md)als u Office wilt installeren op mobiele iOS- of Android-apparaten.

U kunt Office ook afzonderlijk installeren. Zie [Office installeren op een pc of Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) voor instructies.

## <a name="see-also"></a>Zie ook

[Trainingsvideo's voor Microsoft 365 voor bedrijven](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
