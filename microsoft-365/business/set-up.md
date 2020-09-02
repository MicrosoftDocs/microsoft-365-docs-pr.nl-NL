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
description: Ontdek de instellingsstappen voor Microsoft 365 Business Premium, waaronder het toevoegen van een domein en gebruikers, het instellen van beveiligingsbeleid en meer.
ms.openlocfilehash: cc20637d7a78bd34ecb61a4ed46eb06d564d63df
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324491"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a>Microsoft 365 Business Premium instellen in de wizard Setup

Bekijk deze video voor een overzicht van de configuratie van Microsoft 365 Business Premium.<br><br>

## <a name="add-your-domain-users-and-set-up-policies"></a>Uw domein, gebruikers en ingestelde beleidsregels toevoegen

Wanneer u Microsoft 365 Business Premium koopt, hebt u de mogelijkheid een domein te gebruiken dat u bezit, of u kunt een domein kopen tijdens de [registratie](sign-up.md).

- Als u tijdens de registratie een nieuw domein hebt gekocht, is uw domein helemaal ingesteld en kunt u doorgaan met [Gebruikers toevoegen en licenties toewijzen](#add-users-and-assign-licenses).

### <a name="add-your-domain-to-personalize-sign-in"></a>Uw domein toevoegen om uw aanmelding te personaliseren

1. Meld u aan bij [Microsoft 365-beheercentrum](https://admin.microsoft.com) met uw globale-beheerdersreferenties. 

2. Kies **Naar setup** om de wizard te starten.

    ![Selecteer Ga naar Setup.](../media/gotosetupinadmincenter.png)

3. Op de pagina **Uw Office-apps installeren** kunt u desgewenst de apps op uw eigen computer installeren.
    
4. Voer in de stap **Domein toevoegen** de domeinnaam in die u wilt gebruiken (zoals contoso.com).

    > [!IMPORTANT]
    > Als u tijdens de registratie een domein hebt gekocht, ziet u de stap **Een domein toevoegen** hier niet. Ga in plaats daarvan naar [Gebruikers toevoegen](#add-users-and-assign-licenses).

    ![Schermafbeelding van de aanmeldingspagina personaliseren.](../media/adddomain.png)

    
4. Volg de stappen in de wizard voor het [maken van DNS-records bij een DNS-hosting provider voor Microsoft 365 waarmee wordt](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) geverifieerd dat u de eigenaar bent van het domein. Als u weet wat uw domeinhost is, raadpleegt u ook de [hostspecifieke instructies](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Als uw hostingprovider GoDaddy of een andere host is die is ingeschakeld met [domeinverbinding](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), is het proces eenvoudig en wordt u automatisch gevraagd om u aan te melden en u namens Microsoft te laten verifiëren.

    ![Selecteer Autoriseren op de pagina GoDaddy Toegang bevestigen.](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>Gebruikers toevoegen en licenties toewijzen

U kunt gebruikers toevoegen in de wizard, maar u kunt ook [gebruikers later toevoegen](add-users-m365b.md) in het beheercentrum. Als u een lokale domeincontroller hebt, kunt u ook gebruikers toevoegen met [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).

#### <a name="add-users-in-the-wizard"></a>Gebruikers toevoegen in de wizard

Gebruikers die u in de wizard toevoegt, krijgen automatisch een licentie voor Microsoft 365 Business Premium toegewezen.

![Schermafbeelding van de pagina nieuwe gebruikers toevoegen in de wizard](../media/addnewuserspage.png)

1. Als uw Microsoft 365 Business Premium-abonnement bestaande gebruikers heeft (bijvoorbeeld als u Azure AD Connect gebruikt), krijgt u de mogelijkheid om nu licenties toe te wijzen. Wijs nu licenties aan hen toe.

2. Nadat u de gebruikers hebt toegevoegd, krijgt u ook een optie voor het delen van referenties met de nieuwe gebruikers die u hebt toegevoegd. U kunt deze afdrukken, hun een e-mail sturen of deze downloaden.

### <a name="connect-your-domain"></a>Uw domein verbinden

> [!NOTE]
> Als u ervoor hebt gekozen om het domein. onmicrosoft te gebruiken of Azure AD Connect hebt gebruikt voor het instellen van gebruikers, wordt deze stap niet weergegeven.
  
Als u services wilt instellen, moet u enkele records bij uw DNS-host of domeinregistrar bijwerken.
  
1. Meestal wordt uw registrar automatisch gedetecteerd met de wizard Setup, en wordt een koppeling weergegeven naar stapsgewijze instructies voor het bijwerken van uw NS-records op de website van de registrar. Als dit niet het geval is, [kunt u het naamservers wijzigen voor het instellen van Microsoft 365 met een domeinregistratie](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar). 

    - Als u bestaande DNS-records hebt, bijvoorbeeld een bestaande website, maar uw DNS-host is ingeschakeld voor [domeinverbinding](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), kiest u **Records toevoegen voor mij**. Accepteer alle standaardinstellingen op de pagina **Uw online services kiezen**, kies **Volgende** en kies **Autoriseren** op de pagina van uw DNS-host.
    - Als u bestaande DNS-records hebt met andere DNS-hosts (niet ingeschakeld voor domeinverbinding), kunt u uw eigen DNS-records beheren om ervoor te zorgen dat de bestaande services verbonden blijven. Zie [basisprincipes van domeinen](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) voor meer informatie.

        ![De pagina records activeren.](../media/activaterecords.png)

2. Volg de stappen in de wizard en e-mail en andere services worden voor u ingesteld.

### <a name="protect-your-organization"></a>Uw organisatie beschermen 

Het beleid dat u instelt in de wizard wordt automatisch toegepast op een [beveiligingsgroep](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) met de naam *alle gebruikers*. U kunt ook extra groepen maken waarmee u beleidsregels kunt toewijzen in het Beheercentrum.

1. Wanneer u de **bescherming van geavanceerde Cyber bedreigingen**vergemakkelijkt, wordt u aangeraden de standaardinstellingen te accepteren om [Office 365 Advance Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) te laten scannen op bestanden en koppelingen in Office-apps.

    ![Schermafbeelding van de pagina voor het verbeteren van de bescherming.](../media/increasetreatprotection.png)


2. Accepteer op de pagina **lekkage van gevoelige gegevens voorkomen** de standaardinstellingen voor het inschakelen van Office 365 preventie van gegevensverlies (DLP) om gevoelige gegevens in Office-apps bij te houden en te voorkomen dat deze buiten uw organisatie worden gedeeld.

3. Op de pagina **gegevens in Office beschermen voor mobiel apparaat** wilt u de mobiele app beheren, vouwt u de instellingen uit en bekijkt u ze en selecteert u vervolgens **beleid voor Mobile App Management maken**.

    ![Schermafbeelding van de pagina gegevens beschermen in Office voor mobiel.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a>Windows 10-Pc's beveiligen

Selecteer in het navigatievenster aan de linkerkant de optie **installeren** en kies vervolgens onder **Aanmelden en beveiliging** **de optie Beveilig uw Windows 10-computers**. Kies **weergave** om aan de slag te gaan. Zie [Beveilig uw Windows 10-computers](secure-win-10-pcs.md) voor uitgebreide instructies.

## <a name="deploy-office-365-client-apps"></a>Office 365-clienttoepassingen implementeren

Als u ervoor kiest om Office-apps automatisch te installeren tijdens de installatie, worden de apps op Windows 10-apparaten geïnstalleerd nadat de gebruikers zich hebben aangemeld bij Azure AD vanaf hun Windows-apparaten, met hun werk referenties.

Als u Office wilt installeren op mobiele iOS-en Android-apparaten, raadpleegt u [mobiele apparaten instellen voor gebruikers van Microsoft 365 Business Premium](set-up-mobile-devices.md).

U kunt Office ook afzonderlijk installeren. Zie [Office installeren op een PC of Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) voor instructies.

## <a name="see-also"></a>Zie ook

[Trainingsvideo's voor Microsoft 365 voor bedrijven](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
