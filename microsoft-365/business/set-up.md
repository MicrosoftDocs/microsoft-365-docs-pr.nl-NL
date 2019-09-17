---
title: Microsoft 365 Business instellen
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
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Meer informatie over het instellen van Microsoft 365 Business.
ms.openlocfilehash: 1efb7379930f639cf10875cf5aa6731001bb41c8
ms.sourcegitcommit: 2e5ae52bb641ee1f72c077260b5d0f35622935fe
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2019
ms.locfileid: "37005193"
---
# <a name="set-up-microsoft-365-business-in-the-setup-wizard"></a>Microsoft 365 Business instellen in de wizard Setup

## <a name="add-your-domain-users-and-set-up-policies"></a>Uw domein, gebruikers en beleidsinstellingen toevoegen

![Banner die naar https://aka.ms/aboutM365previewwijst.](media/m365admincenterchanging.png)

Wanneer u Microsoft 365 Business aanschaft, hebt u de mogelijkheid om een domein te gebruiken waarvan u eigenaar bent, of om er een te kopen tijdens de [aanmelding](sign-up.md).

- Als u een nieuw domein hebt aangeschaft toen u zich aanmeldde, is uw domein allemaal ingesteld en u verplaatsen naar [gebruikers toevoegen en licenties toewijzen](#add-users-and-assign-licenses).

### <a name="add-your-domain-to-personalize-sign-in"></a>Uw domein toevoegen om aanmelding te personaliseren

1. Meld u aan bij [Microsoft 365 Admin Center](https://admin.microsoft.com) met behulp van de referenties van uw globale beheerder. 

2. Kies **een domein toevoegen** of **gebruikers toevoegen** om de wizard te starten.
    > [!IMPORTANT]
    > Als u een domein heeft aangeschaft tijdens de aanmelding, ziet u hier geen **domein toevoegen** . Ga in plaats daarvan naar [gebruikers toevoegen](#add-users-and-assign-licenses) .

    ![Selecteer een domein toevoegen.](media/addadomainadmincenter.png)
    
3. Voer in de wizard de domeinnaam in die u wilt gebruiken (zoals contoso.com).


    ![Screenshot van de Personaliseer je inlogpagina.](media/personalizesignin.png)

    
4. Volg de stappen in de wizard om [DNS-records te maken bij elke DNS-hosting provider voor Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) die controleert of u de eigenaar van het domein bent. Als u uw domeinhost kent, raadpleegt u ook de [hostspecifieke instructies](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Als uw hosting provider GoDaddy is of een andere host die is ingeschakeld met [Domain Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), is het proces eenvoudig en wordt u automatisch gevraagd om in te loggen en Microsoft namens u te laten verifiëren:

    ![Selecteer op GoDaddy toegangspagina bevestigen de optie autoriseren.](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>Gebruikers toevoegen en licenties toewijzen

U gebruikers toevoegen in de wizard, maar u ook [gebruikers later toevoegen](add-users-m365b.md) in het Beheercentrum. Als u een lokale domeincontroller hebt, u bovendien gebruikers met [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)toevoegen.

#### <a name="add-users-in-the-wizard"></a>Gebruikers toevoegen in de wizard

Gebruikers die u toevoegt aan de wizard krijgen automatisch een licentie voor Microsoft 365 Business toegewezen.

![Schermafbeelding van de pagina nieuwe gebruikers toevoegen in de wizard](media/addnewuserspage.png)

1. Als uw Microsoft 365 Business-abonnement bestaande gebruikers heeft (bijvoorbeeld, als u Azure AD Connect hebt gebruikt), krijgt u een optie om licenties toe te wijzen aan hen nu. Wijs nu licenties aan hen toe.

3. Nadat u de gebruikers hebt toegevoegd, krijgt u ook een optie om referenties te delen met de nieuwe gebruikers die u hebt toegevoegd. U kunt deze afdrukken, hun een e-mail sturen of deze downloaden.

4. Sla het migreren van e-mailberichten over en kies **Volgende** op de pagina **E-mailberichten migreren**. 

    Als u van een andere e-mailprovider verhuist en uw gegevens later wilt kopiëren, u [e-mail en contactpersonen migreren naar Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).


### <a name="connect-your-domain"></a>Uw domein verbinden

> [!NOTE]
> Als u ervoor kiest om het domein. onmicrosoft te gebruiken of Azure AD Connect gebruikt om gebruikers in te stellen, wordt deze stap niet weergegeven.
  
Als u services wilt instellen, moet u enkele records bij uw DNS-host of domeinregistrar bijwerken.
  
1. Meestal wordt uw registrar automatisch gedetecteerd met de installatiewizard en wordt een koppeling weergegeven naar stapsgewijze instructies voor het bijwerken van uw NS-records op de website van de registrar. Als dit niet het [geval is, wijzigt u nameservers om Office 365 in te stellen met een domeinregistrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2). 

    - Als u bestaande DNS-records hebt, bijvoorbeeld een bestaande website, maar uw DNS-host is ingeschakeld voor [domein verbinding](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), kiest u **records toevoegen voor mij**. 
    - Als u bestaande DNS-records hebt met andere DNS-hosts (niet ingeschakeld voor domein verbinding), wilt u uw eigen DNS-records beheren om ervoor te zorgen dat de bestaande services verbonden blijven. Zie [basisbeginselen](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) van het domein voor meer informatie.

        ![Verbind uw domein pagina met ik beheer mijn eigen DNS-records.](media/connectyourdomainpage.png)

2. Volg de stappen in de wizard en e-mail en andere services worden voor u ingesteld.

### <a name="set-up-security-policies-and-device-configurations"></a>Beveiligingsbeleid en apparaatconfiguraties instellen 

Het beleid dat u in de wizard hebt ingesteld, wordt automatisch toegepast op een [beveiligingsgroep](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) met de naam *alle gebruikers*. U ook extra groepen maken om beleidsregels toe te wijzen in het Admin Center.

1. Op de **Bescherm uw werkbestanden op mobiele apparaten** de optie **werkbestanden beveiligen wanneer apparaten zijn verloren of gestolen** is standaard geselecteerd. U hebt een optie om in te schakelen **beheren hoe gebruikers toegang hebben tot Office-bestanden op mobiele apparaten**, en dit wordt aanbevolen.

    ![Screenshot van werkbestanden beschermen op de pagina mobiele apparaten.](media/protectworkfilesondevices.png)

     - Vouw **werkbestanden beveiligen wanneer apparaten zijn verloren of gestolen** om de [Standaardwaarden](protect-work-files-on-lost-or-stolen-device.md)weer te geven:

        ![Screenshot van standaardwaarden voor het beschermen van bestanden op verloren apparaten.](media/protectworkfilesondevicesdefault.png)

    - Selecteer **beheren hoe gebruikers toegang hebben tot Office-bestanden op mobiele apparaten** en vouw deze uit om de [Standaardwaarden](manage-user-access-on-mobile-devices.md)weer te geven. We raden u aan de standaardwaarden tijdens de installatie te accepteren om toepassings beleidsregels te maken voor Android, iOS en Windows 10 die van toepassing zijn op alle gebruikers. Nadat de installatie is voltooid, kunt u meer beleidsregels maken.

        ![Screenshot van beveiligingsinstellingen voor Office-bestanden op mobiel.](media/useraccessonmobile.png)

2. De laatste stap op gegevens en apparaten beveiligen, u beleid instellen voor het beveiligen van Windows 10-apparaten. Deze instellingen worden automatisch toegepast wanneer Windows 10 van een gebruiker verbinding met uw organisatie maakt. U **beveiligde Windows 10-apparaten** uitvouwen om de [Standaardwaarden](secure-windows-10-devices.md)te bekijken en te wijzigen.
3. U er ook voor kiezen om [Office automatisch te installeren](install-office-on-windows-10-during-setup.md) op Windows 10-apparaten.

    ![Screenshot van set Windows 10 Device configuration pagina.](media/setwin10config.png)



## <a name="deploy-office-365-client-apps"></a>Office 365-client-Apps implementeren

Als u ervoor kiest om automatisch Office-apps te installeren tijdens de installatie, worden de apps geïnstalleerd op de Windows 10-apparaten zodra de gebruikers zich hebben aangemeld bij Azure AD vanaf hun Windows-apparaten met hun werkreferenties.
Als u Office op mobiele iOS-of Android-apparaten wilt installeren, raadpleegt u [mobiele apparaten instellen voor zakelijke gebruikers van Microsoft 365](set-up-mobile-devices.md).

U Office ook afzonderlijk installeren. Zie [Office installeren op een PC of Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) voor instructies.
