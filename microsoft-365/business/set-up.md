---
title: Microsoft 365 Business instellen
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
description: Informatie over het instellen van Microsoft 365 Business.
ms.openlocfilehash: e635b828609fc47cd8b92bb179a25bcc43cb0a1a
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660754"
---
# <a name="set-up-microsoft-365-business"></a>Microsoft 365 Business instellen

Voordat u begint, Zie [Microsoft 365 Business ophalen](get-microsoft-365-business.md) voor aanmelding details.

Bekijk een [korte video over het instellen van Microsoft 365 Business](https://support.office.com/article/38003e30-9d10-44cf-b596-f1b5f662bfa1) met behulp van de wizard, en wanneer er een Active Directory op de gebouwen
  

## <a name="overview"></a>Overzicht

De meeste van de instellen van de stappen in de wizard setup kan worden uitgevoerd, maar de andere opties worden ook weergegeven.

1. [Uw domein toevoegen](#add-your-domain-to-personalize-sign-in) (als u uw domein tijdens het [aanmelden](sign-up.md)hebt gekocht, wordt deze stap hebt gedaan.)
2. Gebruikers toevoegen. U kunt dit op een van de drie manieren doen:
    - In de [wizard setup](#add-users-in-the-wizard).
    - Adreslijstsynchronisatie toevoegen van [gebruikers met Azure AD verbinding](#add-users-by-using-azure-ad-connect) gebruiken als u een Active directory op gebouwen.
    - U kunt ook [gebruikers later toevoegen](add-users-m365b.md) in het beheercentrum.
3. Beveiligingsbeleid instellen en configureren van apparaten. U kunt dit op een van de drie manieren doen:
    - In de [wizard setup](#set-up-policies-in-the-wizard).  
    - In de [admin center](#modify-or-add-policies-in-the-admin-center).
    - Klik in het [beheercentrum Intune](https://docs.microsoft.com/intune/what-is-device-management).
4. Instellen en beheren van apparaten in Windows 10.

    Wanneer u een apparaat met WIndows 10 naar Azure AD, krijgen alle beleidsregels toegepast op.
    - Configuraties in de [wizard setup van](#set-up-policies-in-the-wizard)Windows 10 instellen.
    - Lid worden van een [nieuw apparaat met Windows 10](set-up-windows-devices.md#for-a-brand-new-or-newly-upgraded-windows-10-pro-device) naar Azure AD.
    - Lid worden van een [bestaande Windows 10-apparaat](set-up-windows-devices.md#for-a-device-already-set-up-and-running-windows-10-pro) naar Azure AD.
1. Installeer Office 365 Business.
    - Automatisch kunt in de Windows-apparaten u Office installeren met de [wizard setup](#set-up-policies-in-the-wizard).
    - Automatisch [Office installeren](auto-install-or-uninstall-office.md) vanaf het admin center.
    - Laat de gebruikers [installeren Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) voor Windows en apparaten.
     
1. Extra beveiliging instellen.
    - De wizard setup voegt beleid om uw apparaten te beveiligen, maar kunt u ook profiteren van de mogelijkheden voor [Extra beveiliging](#additional-security-settings) kunt veilig uw gegevens, accounts en e-mailberichten. 

## <a name="add-your-domain-users-and-set-up-policies"></a>Uw domein, gebruikers toevoegen en instellen van het beleid

![Banner die verwijzen naar https://aka.ms/aboutM365preview.](media/m365admincenterchanging.png)

Wanneer u Microsoft 365 Business aanschaft, hebt u de mogelijkheid van een domein dat u de eigenaar of kopen tijdens de [aanmelding](sign-up.md).

- Als u een nieuw domein gekocht toen u zich aanmeldde, uw domein is ingesteld op alle en u kunt [gebruikers toevoegen en toewijzen van licenties](#add-users-and-assign-licenses)kunt verplaatsen.

### <a name="add-your-domain-to-personalize-sign-in"></a>Toevoegen van uw domein om aan te passen-in

1. Aanmelden bij [Microsoft 365 admin center](https://admin.microsoft.com) via uw globale Administrator-referenties. 

2. Kies **een domein toevoegen** om de wizard te starten.

    ![Selecteer een domein toevoegen.](media/addadomainadmincenter.png)
    
3. Voer in de wizard de naam van het domein dat u wilt gebruiken (zoals contoso.com).


    ![Screenshot van het aanpassen van uw pagina.](media/personalizesignin.png)

    
4. Volg de stappen in de wizard [maken DNS-records bij een DNS-hosting provider voor Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) waarmee wordt gecontroleerd of dat u de eigenaar van het domein. Als u uw domeinhost, Zie ook de [host-specifieke instructies](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Als uw hostingprovider GoDaddy, het proces is eenvoudig en wordt u automatisch gevraagd aangemeld en laten verifiëren namens Microsoft:

    ![Selecteer machtigen op GoDaddy bevestigen Access-pagina.](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>Gebruikers toevoegen en licenties toewijzen

In de wizard kunt u gebruikers toevoegen, maar u kunt ook [gebruikers later toevoegen](add-users-m365b.md) in het beheercentrum. Als er een lokale domeincontroller, kunt u ook gebruikers met [Azure AD verbinden](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)toevoegen.

#### <a name="add-users-in-the-wizard"></a>Gebruikers toevoegen in de wizard

Gebruikers die u in de wizard toevoegt krijgen automatisch een licentie van Microsoft 365 Business toegewezen.
Als u een lokale domeincontroller en Active Directory gebruikt, Zie [ddd gebruikers met Azure AD verbinding](#add-users-by-using-azure-ad-connect).

![Schermafbeelding van de pagina nieuwe gebruikers toevoegen in de wizard](media/addnewuserspage.png)

1. Als uw Microsoft 365 Business-abonnement bestaande gebruikers heeft (bijvoorbeeld als u Azure AD Connect hebt gebruikt), hebt u een optie om nu licenties aan hen toe te wijzen. Wijs nu licenties aan hen toe.

3. Nadat u de gebruikers hebt toegevoegd, krijgt u ook een optie voor het delen van referenties met de nieuwe gebruikers die u hebt toegevoegd. U kunt deze afdrukken, hun een e-mail sturen of deze downloaden.

4. Sla het migreren van e-mailberichten over en kies **Volgende** op de pagina **E-mailberichten migreren**. 

    Als u van een andere e-mailprovider verplaatst en kopieer de gegevens later wilt, kunt u [e-mail migreren en contactpersonen voor Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).

#### <a name="add-users-by-using-azure-ad-connect"></a>Gebruikers toevoegen met behulp van Azure AD verbinden

 Als er een lokale domeincontroller met Active Directory, gesynchroniseerd u uw gebruikers met Microsoft 365 Business met [Azure AD verbinding](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express). Voltooien voordat u de wizard setup. U kunt deze in het admin center downloaden:

- Ga naar **gebruikers** \> **actieve gebruikers**, selecteer de ovalen boven aan de pagina en selecteer vervolgens **adreslijstsynchronisatie** Azure AD verbinden downloaden.

    ![Selecteer op de pagina actieve gebruikers ellipsen > Directory snchronization.](media/setupdirsync.png)

    > [!IMPORTANT]
    > Als u gebruikers op deze manier maakt, moet u nog steeds licenties hieraan toewijzen in het beheercentrum.

##### <a name="continue-to-access-domain-joined-apps-and-devices"></a>Doorgaan naar deel uitmaakt van een domein apps en apparaten

Als u doorgaan wilt naar deel uitmaakt van een domein apps en apparaten, lees de volgende artikelen voor twee verschillende richtingen die in te schakelen:
  
- [Toestaan dat aan een domein toegevoegde Windows 10-apparaten door Microsoft 365 Business worden beheerd](manage-windows-devices.md)
    - Dit is de aanbevolen manier.

- [Toegang op-premises resources uit een Azure AD verbonden apparaat in Microsoft 365 Business](access-resources.md)

### <a name="connect-your-domain"></a>Uw domein verbinden

> [!NOTE]
> Als u wilt gebruiken het .onmicrosoft domein of verbinden met Azure AD gebruikt om gebruikers in te stellen, worden er niet in deze stap.
  
Als u services wilt instellen, moet u enkele records bij uw DNS-host of domeinregistrar bijwerken.
  
1. Meestal wordt uw registrar automatisch gedetecteerd met de installatiewizard en wordt een koppeling weergegeven naar stapsgewijze instructies voor het bijwerken van uw NS-records op de website van de registrar. Als dat niet het geval, [nameservers voor het instellen van Office 365 met een domeinregistratieservice wijzigen](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2). 

    - Als u bestaande DNS-records, bijvoorbeeld met een bestaande website, wilt u uw eigen DNS-records om ervoor te zorgen dat de bestaande services blijven beheren. Zie [de grondbeginselen van het domein](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) voor meer informatie.

        ![Verbinding maken met uw domein pagina met ik mijn eigen DNS-records kunt beheren.](media/connectyourdomainpage.png)

2. Volg de stappen in de wizard en e-mailadres en andere diensten zal worden voor u ingesteld.

### <a name="set-up-security-policies-and-device-configurations"></a>Instellen van beveiligingsbeleid en -configuraties 

Dit beleid van toepassing op alle gebruikers u een licentie verlenen tot, of een groep gebruikers als u verschillende soorten beleid toewijzen aan een groep gebruikers.

#### <a name="set-up-policies-in-the-wizard"></a>Instellen van het beleid van de wizard

Het beleid dat u hebt ingesteld in de wizard worden automatisch toegepast op de [groep](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) *Alle gebruikers*.

1. Op het **werkbestanden op mobiele apparaten beveiligen** de optie is **Protect werkbestanden bij verlies of diefstal van de apparaten** standaard geselecteerd. U hebt een optie om te **beheren hoe gebruikers toegang kunnen krijgen tot Office-bestanden op mobiele apparaten**inschakelen en deze optie wordt aanbevolen.

    ![Screenshot van bescherming van werk-bestanden op mobiele apparaten pagina.](media/protectworkfilesondevices.png)

     - Als u **de werkbestanden beveiligen wanneer apparaten zijn verloren of gestolen**uitvouwt, worden de [standaardwaarden](protect-work-files-on-lost-or-stolen-device.md) vooraf geselecteerde:

        ![Screenshot van standaardwaarden voor het beveiligen van bestanden op apparaten verloren.](media/protectworkfilesondevicesdefault.png)

    - Als u selecteren **hoe gebruikers toegang kunnen krijgen tot Office-bestanden op mobiele apparaten beheren** en vouwen, worden de [standaardwaarden](manage-user-access-on-mobile-devices.md) weergegeven. Het is raadzaam dat u de standaardwaarden tijdens de installatie accepteert om beleid voor toepassingen voor Android, iOS en Windows 10 te maken die voor alle gebruikers gelden. Nadat de installatie is voltooid, kunt u meer beleidsregels maken.

        ![Screenshot van beveiligingsinstellingen voor Office-bestanden op een mobiel.](media/useraccessonmobile.png)

2. De laatste stap op bescherming van gegevens en apparaten kunt u een beleid instellen voor het beveiligen van Windows 10-apparaten. Deze instellingen worden automatisch toegepast wanneer een gebruiker Windows 10 verbinding met uw organisatie maakt. U kunt **beveiligde Windows 10-apparaten** als u wilt zien en wijzigen van de [standaardwaarden](secure-windows-10-devices.md)kunt uitbreiden.
3. U kunt ook op Windows 10-apparaten [automatisch installeren van Office](install-office-on-windows-10-during-setup.md) .

    ![Screenshot van Windows 10 apparaat configuratiepagina instellen.](media/setwin10config.png)

#### <a name="modify-or-add-policies-in-the-admin-center"></a>Wijzigen of toevoegen van beleid in het admin center

Zie [Microsoft 365 Business beheren](manage.md) voor koppelingen naar onderwerpen over het weergeven en wijzigen van apparaat- en app-bescherming beleid, en hoe u kunt gegevens verwijderen uit of opnieuw ingesteld Gebruikersapparaten.

## <a name="deploy-and-manage-windows-10"></a>Implementeren en beheren van Windows 10
Zie [Windows apparaten voor gebruikers van Microsoft 365 Business instellen](set-up-windows-devices.md) handmatig verbinding maken met Azure AD, hetzij tijdens de installatie voor nieuwe computers, of door het profiel aanmelden voor bestaande computers wijzigen. 

### <a name="use-autopilot-to-set-up-new-devices"></a>Automatische piloot gebruiken voor het instellen van nieuwe apparaten

U kunt [Windows Automatische piloot](add-autopilot-devices-and-profile.md) automatisch vooraf configureren voor een gebruiker **nieuwe** Windows 10-apparaten, maar is het misschien gemakkelijker om een [partner](https://www.microsoft.com/solution-providers/search) die dit voor u kan doen. U kunt ook gaat u naar de [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) en vragen een deskundige cloud-technologie nieuwe apparaten die u voor u aanschaft ingesteld.

### <a name="access-on-premises-resources"></a>Toegang op ruimten resources

Als uw organisatie gebruikmaakt van Windows Server Active Directory op lokalen, kunt u Microsoft 365 Business instellen ter bescherming van uw Windows 10-apparaten, terwijl zij toch toegang tot bronnen voor ruimten die lokale verificatie vereisen. Volg de stappen in [Windows 10-apparaten worden beheerd door Microsoft 365 Business domein behoren](manage-windows-devices.md) tot dit instellen. Dit is de aanbevolen methode en apparaten in deze toestand worden genoemd hybride Azure AD verbonden apparaten.

Als uw bedrijf een lokale Active Directory met sommige op-ruimten (zoals bestandsshares en printers), u kunt uw Azure AD verbonden apparaten toegang geven tot deze bronnen door de stappen hier: [toegang op-premises resources uit een Azure AD verbonden apparaat in Microsoft 365 Business](access-resources.md).

## <a name="deploy-office-365-client-apps"></a>Office 365-clienttoepassingen installeren

Als u Office apps in automatisch geïnstalleerd tijdens de installatie van, installeert de apps op de Windows 10-apparaten nadat de gebruikers zijn aangemeld bij Azure AD van hun Windows-apparaten met de referenties van hun werk.
Zie [mobiele apparaten voor Microsoft 365 zakelijke gebruikers](set-up-mobile-devices.md)Office installeren op mobiele iOS- of Android apparaten.

U kunt Office ook afzonderlijk installeren. Zie [Office op een PC of Mac installeren](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc471665) voor instructies.

## <a name="additional-security-settings"></a>Extra beveiligingsinstellingen

Naast de beveiliging en naleving instellen in de wizard setup kunt u ook de volgende aanvullende instellingen instellen:
  
- **E-mail beveiliging tegen ongewenste software**
- **Geavanceerde Threat Protection (ATP) veilige bijlagen**
- **ATP veilig koppelingen**
- **APT anti-phishing**
- **Exchange Online Archiving**
- **Gegevensverlies voorkomen (DLP)**
- **Azure informatiebescherming** (Plan 1)
- **Intune portal beschikbaarheid**

Zie [Geavanceerde beveiligingsbeleid instellen](set-up-advanced-security.md)om op te halen is gestart.

Zie ook de [top 10 manieren voor het beveiligen van uw bedrijf Microsoft 365](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) voor een overzicht van aanbevolen beveiligingsprocedures.