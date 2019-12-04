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
- TRN_SMB
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Meer informatie over het instellen van Microsoft 365 Business.
ms.openlocfilehash: 7ab6ae095ae30f8ceb74be69fcee20f31977ae21
ms.sourcegitcommit: 8fda7852b2a5baa92b8a365865b014ea6d100bbc
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/03/2019
ms.locfileid: "39818887"
---
# <a name="set-up-microsoft-365-business-in-the-setup-wizard"></a>Microsoft 365 Business instellen in de wizard Setup

Bekijk deze video voor een overzicht van Microsoft 365 Business Setup.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

Als u deze video nuttig vond, Bekijk dan de [complete trainingreeks voor kleine bedrijven en die nieuw bij Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="add-your-domain-users-and-set-up-policies"></a>Uw domein, gebruikers en beleidsinstellingen toevoegen

[![Etiket om u te laten weten dat het beheercentrum wordt gewijzigd en meer informatie vindt u op aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

Wanneer u Microsoft 365 Business aanschaft, hebt u de mogelijkheid om een domein te gebruiken waarvan u eigenaar bent, of om er een te kopen tijdens de [aanmelding](sign-up.md).

- Als u een nieuw domein hebt aangeschaft toen u zich aanmeldde, is uw domein allemaal ingesteld en u verplaatsen naar [gebruikers toevoegen en licenties toewijzen](#add-users-and-assign-licenses).

### <a name="add-your-domain-to-personalize-sign-in"></a>Uw domein toevoegen om aanmelding te personaliseren

1. Meld u aan bij [Microsoft 365 Admin Center](https://admin.microsoft.com) met behulp van de referenties van uw globale beheerder. 

2. Kies **Ga naar Setup** om de wizard te starten.

    ![Selecteer Ga naar Setup.](media/gotosetupinadmincenter.png)

3. Op de pagina **uw Office-apps installeren** u desgewenst de apps op uw eigen computer installeren.
    
4. Voer in de stap **domein toevoegen** de domeinnaam in die u wilt gebruiken (zoals contoso.com).

    > [!IMPORTANT]
    > Als u een domein heeft aangeschaft tijdens de aanmelding, ziet u hier geen **domein toevoegen** . Ga in plaats daarvan naar [gebruikers toevoegen](#add-users-and-assign-licenses) .

    ![Screenshot van de Personaliseer je inlogpagina.](media/adddomain.png)

    
4. Volg de stappen in de wizard om [DNS-records te maken bij elke DNS-hosting provider voor Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) die controleert of u de eigenaar van het domein bent. Als u uw domeinhost kent, raadpleegt u ook de [hostspecifieke instructies](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Als uw hosting provider GoDaddy is of een andere host die is ingeschakeld met [Domain Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), is het proces eenvoudig en wordt u automatisch gevraagd om in te loggen en Microsoft namens u te laten verifiëren.

    ![Selecteer op GoDaddy toegangspagina bevestigen de optie autoriseren.](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>Gebruikers toevoegen en licenties toewijzen

U gebruikers toevoegen in de wizard, maar u ook [gebruikers later toevoegen](add-users-m365b.md) in het Beheercentrum. Als u een lokale domeincontroller hebt, u bovendien gebruikers met [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)toevoegen.

#### <a name="add-users-in-the-wizard"></a>Gebruikers toevoegen in de wizard

Gebruikers die u toevoegt aan de wizard krijgen automatisch een licentie voor Microsoft 365 Business toegewezen.

![Schermafbeelding van de pagina nieuwe gebruikers toevoegen in de wizard](media/addnewuserspage.png)

1. Als uw Microsoft 365 Business-abonnement bestaande gebruikers heeft (bijvoorbeeld, als u Azure AD Connect hebt gebruikt), krijgt u een optie om licenties toe te wijzen aan hen nu. Wijs nu licenties aan hen toe.

2. Nadat u de gebruikers hebt toegevoegd, krijgt u ook een optie om referenties te delen met de nieuwe gebruikers die u hebt toegevoegd. U kunt deze afdrukken, hun een e-mail sturen of deze downloaden.

### <a name="connect-your-domain"></a>Uw domein verbinden

> [!NOTE]
> Als u ervoor kiest om het domein. onmicrosoft te gebruiken of Azure AD Connect gebruikt om gebruikers in te stellen, wordt deze stap niet weergegeven.
  
Als u services wilt instellen, moet u enkele records bij uw DNS-host of domeinregistrar bijwerken.
  
1. Meestal wordt uw registrar automatisch gedetecteerd met de installatiewizard en wordt een koppeling weergegeven naar stapsgewijze instructies voor het bijwerken van uw NS-records op de website van de registrar. Als dit niet het [geval is, wijzigt u nameservers om Office 365 in te stellen met een domeinregistrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2). 

    - Als u bestaande DNS-records hebt, bijvoorbeeld een bestaande website, maar uw DNS-host is ingeschakeld voor [domein verbinding](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), kiest u **records toevoegen voor mij**. Accepteer alle standaardinstellingen op de pagina **Kies uw online services** en kies **volgende**en kies **autoriseren** op de pagina van uw DNS-host.
    - Als u bestaande DNS-records hebt met andere DNS-hosts (niet ingeschakeld voor domein verbinding), wilt u uw eigen DNS-records beheren om ervoor te zorgen dat de bestaande services verbonden blijven. Zie [basisbeginselen](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) van het domein voor meer informatie.

        ![Pagina records activeren.](media/activaterecords.png)

2. Volg de stappen in de wizard en e-mail en andere services worden voor u ingesteld.

### <a name="protect-your-organization"></a>Bescherm uw organisatie 

Het beleid dat u in de wizard hebt ingesteld, wordt automatisch toegepast op een [beveiligingsgroep](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) met de naam *alle gebruikers*. U ook extra groepen maken om beleidsregels toe te wijzen in het Admin Center.

1. Op de **verhoging van de bescherming tegen geavanceerde cyberdreigingen**, is het raadzaam dat u de standaardwaarden om te laten [Office 365 vooraf bedreigingsbeveiliging](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) scan bestanden en koppelingen in Office-apps accepteren.

    ![Screenshot van verhoging bescherming pagina.](media/increasetreatprotection.png)


2. Accepteer op de pagina **lekken van gevoelige gegevens voorkomen** de standaardinstellingen om Office 365 preventie van gegevensverlies (DLP) in te schakelen om gevoelige gegevens in Office-apps bij te houden en te voorkomen dat deze buiten uw organisatie per ongeluk worden gedeeld.

3. Op de pagina **gegevens beveiligen in Office voor mobiel** laat u beheer van mobiele apps ingeschakeld, vouwt u de instellingen uit en controleert u deze en selecteert u vervolgens **beheerbeleid voor mobiele apps maken**.

    ![Screenshot van gegevens beschermen in Office voor mobiele pagina.](media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a>Beveiligde Windows 10-Pc's

Selecteer op de linkernavigatiebalk **instellingen** en kies vervolgens onder **zingen en beveiliging** **uw Windows 10-computers beveiligen**. Kies **weergave** om aan de slag te gaan. Zie [uw Windows 10-computers beveiligen](secure-win-10-pcs.md) voor volledige instructies.

## <a name="deploy-office-365-client-apps"></a>Office 365-client-Apps implementeren

Als u ervoor kiest om automatisch Office-apps te installeren tijdens de installatie, worden de apps geïnstalleerd op de Windows 10-apparaten zodra de gebruikers zich hebben aangemeld bij Azure AD vanaf hun Windows-apparaten, met hun werkreferenties.

Als u Office op mobiele iOS-of Android-apparaten wilt installeren, raadpleegt u [mobiele apparaten instellen voor zakelijke gebruikers van Microsoft 365](set-up-mobile-devices.md).

U Office ook afzonderlijk installeren. Zie [Office installeren op een PC of Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) voor instructies.

## <a name="see-also"></a>Zie ook

[Microsoft 365 zakelijke trainingsvideo's](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
