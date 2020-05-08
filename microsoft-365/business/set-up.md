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
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Ontdek de installatiestappen voor Microsoft 365 Business Premium, waaronder het toevoegen van een domein en gebruikers, het instellen van beveiligingsbeleid en meer.
ms.openlocfilehash: 03f446f790a664af85cc630048bc022d88b6e54f
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/08/2020
ms.locfileid: "44165771"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a>Microsoft 365 Business Premium instellen in de wizard Setup

Bekijk deze video voor een overzicht van microsoft 365 Business Premium setup.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

Als u deze video nuttig vond, raadpleegt u dan de [complete reeks trainingen voor kleine bedrijven en nieuwe gebruikers van Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="add-your-domain-users-and-set-up-policies"></a>Uw domein, gebruikers en beleid instellen toevoegen

[![Etiket om u te laten weten dat het beheercentrum wordt gewijzigd en meer informatie vindt u op aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

Wanneer u Microsoft 365 Business Premium koopt, hebt u de mogelijkheid om een domein te gebruiken dat u bezit of er een te kopen tijdens de [aanmelding.](sign-up.md)

- Als u een nieuw domein hebt gekocht toen u zich hebt aangemeld, is uw domein helemaal ingesteld en u overgaan naar [Gebruikers toevoegen en licenties toewijzen.](#add-users-and-assign-licenses)

### <a name="add-your-domain-to-personalize-sign-in"></a>Uw domein toevoegen om aanmelding te personaliseren

1. Meld u aan bij [het Microsoft 365-beheercentrum](https://admin.microsoft.com) met uw globale beheerdersreferenties. 

2. Kies **Ga naar setup om** de wizard te starten.

    ![Selecteer Ga naar instellen.](../media/gotosetupinadmincenter.png)

3. Op de pagina **Uw Office-apps installeren** u de apps optioneel op uw eigen computer installeren.
    
4. Voer in de stap **Domein toevoegen** de domeinnaam in die u wilt gebruiken (zoals contoso.com).

    > [!IMPORTANT]
    > Als u tijdens de aanmelding een domein hebt gekocht, ziet u hier **geen domeinstap toevoegen.** Ga in plaats daarvan naar [Gebruikers toevoegen.](#add-users-and-assign-licenses)

    ![Schermafbeelding van de pagina Uw aanmelding personaliseren.](../media/adddomain.png)

    
4. Volg de stappen in de wizard om [DNS-records te maken bij elke DNS-hostingprovider voor Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) die controleert of u eigenaar bent van het domein. Als u uw domeinhost kent, raadpleegt u ook de [hostspecifieke instructies.](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)

    Als uw hostingprovider GoDaddy is of een andere host die is ingeschakeld met [domeinverbinding,](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)is het proces eenvoudig en wordt u automatisch gevraagd om u aan te melden en microsoft namens u te laten verifiëren.

    ![Selecteer op de pagina Access bevestigen van GoDaddy Bevestigen de optie Autoriseren.](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>Gebruikers toevoegen en licenties toewijzen

U gebruikers toevoegen in de wizard, maar u later ook [gebruikers toevoegen](add-users-m365b.md) in het beheercentrum. Als u een lokale domeincontroller hebt, u bovendien gebruikers toevoegen met [Azure AD Connect.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

#### <a name="add-users-in-the-wizard"></a>Gebruikers toevoegen aan de wizard

Gebruikers die u in de wizard toevoegt, krijgen automatisch een Microsoft 365 Business Premium-licentie toegewezen.

![Schermafbeelding van de pagina Nieuwe gebruikers toevoegen in de wizard](../media/addnewuserspage.png)

1. Als uw Microsoft 365 Business Premium-abonnement bestaande gebruikers heeft (bijvoorbeeld als u Azure AD Connect hebt gebruikt), krijgt u nu de optie om licenties aan hen toe te wijzen. Wijs nu licenties aan hen toe.

2. Nadat u de gebruikers hebt toegevoegd, krijgt u ook een optie om referenties te delen met de nieuwe gebruikers die u hebt toegevoegd. U kunt deze afdrukken, hun een e-mail sturen of deze downloaden.

### <a name="connect-your-domain"></a>Uw domein verbinden

> [!NOTE]
> Als u ervoor kiest om het .onmicrosoft-domein te gebruiken of Azure AD Connect hebt gebruikt om gebruikers in te stellen, ziet u deze stap niet.
  
Als u services wilt instellen, moet u enkele records bij uw DNS-host of domeinregistrar bijwerken.
  
1. Meestal wordt uw registrar automatisch gedetecteerd met de installatiewizard en wordt een koppeling weergegeven naar stapsgewijze instructies voor het bijwerken van uw NS-records op de website van de registrar. Als dit niet het geval is, [wijzigt u naamservers om Office 365 in te stellen bij een domeinregistrar.](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar) 

    - Als u bestaande DNS-records hebt, bijvoorbeeld een bestaande website, maar uw DNS-host is ingeschakeld voor [domeinverbinding,](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)kiest u **Records voor mij toevoegen**. Accepteer op de pagina **Uw onlineservices kiezen** alle standaardinstellingen en kies **Volgende**en kies **Autoriseren** op de pagina van uw DNS-host.
    - Als u bestaande DNS-records hebt met andere DNS-hosts (niet ingeschakeld voor domeinverbinding), wilt u uw eigen DNS-records beheren om ervoor te zorgen dat de bestaande services verbonden blijven. Zie [de basisprincipes van het domein](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) voor meer informatie.

        ![Records-pagina activeren.](../media/activaterecords.png)

2. Volg de stappen in de wizard en e-mail en andere services worden voor u ingesteld.

### <a name="protect-your-organization"></a>Uw organisatie beschermen 

Het beleid dat u in de wizard hebt ingesteld, wordt automatisch toegepast op een [beveiligingsgroep](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) met de naam *Alle gebruikers*. U ook extra groepen maken om beleid toe te wijzen in het beheercentrum.

1. In de **optiebeveiliging verhogen tegen geavanceerde cyberbedreigingen**wordt aanbevolen dat u de standaardinstellingen accepteert om [Office 365 Advance Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) bestanden en koppelingen in Office-apps te laten scannen.

    ![Schermafbeelding van de pagina Bescherming vergroten.](../media/increasetreatprotection.png)


2. Accepteer op de pagina **Lekken van gevoelige gegevens** voorkomen de standaardinstellingen om Office 365 Data Loss Prevention (DLP) in te schakelen om gevoelige gegevens in Office-apps te volgen en het per ongeluk delen van deze gegevens buiten uw organisatie te voorkomen.

3. Laat op de pagina **Gegevens beveiligen in Office voor mobiel** het beheer van mobiele apps aan, vouw de instellingen uit en bekijk deze en selecteer vervolgens Beleid voor beheer van mobiele apps **maken**.

    ![Schermafbeelding van Gegevens beveiligen in de pagina Office voor mobiel.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a>Beveiligde Windows 10-pc's

Selecteer op de linkernavigatie de optie **Instellen** en kies vervolgens onder Aanmelding en beveiliging de optie **Uw Windows 10-computers beveiligen**. **Sign-in and security** Kies **Weergave** om aan de slag te gaan. Bekijk [uw Windows 10-computers beveiligen](secure-win-10-pcs.md) voor volledige instructies.

## <a name="deploy-office-365-client-apps"></a>Office 365-client-apps implementeren

Als u ervoor kiest om Office-apps automatisch te installeren tijdens de installatie, worden de apps geïnstalleerd op de Windows 10-apparaten zodra de gebruikers zich vanaf hun Windows-apparaten hebben aangemeld bij Azure AD met behulp van hun werkreferenties.

Zie Mobiele apparaten instellen voor Microsoft [365 Business Premium-gebruikers](set-up-mobile-devices.md)als u Office wilt installeren op mobiele iOS- of Android-apparaten.

U Office ook afzonderlijk installeren. Zie [Office installeren op een pc of Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) voor instructies.

## <a name="see-also"></a>Zie ook

[Trainingsvideo's voor Microsoft 365 voor bedrijven](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
