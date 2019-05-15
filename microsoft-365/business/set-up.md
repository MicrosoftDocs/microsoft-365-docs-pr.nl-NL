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
ms.openlocfilehash: f3a9ad62f5ec8779296e800b9ecc8d6181d7aff7
ms.sourcegitcommit: f420a5cdedf3ec2babc6d8ad7e7c79da0b08e115
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/13/2019
ms.locfileid: "33966973"
---
# <a name="set-up-microsoft-365-business-in-the-setup-wizard"></a>Microsoft 365 Business instellen in de wizard setup

## <a name="add-your-domain-users-and-set-up-policies"></a>Uw domein, gebruikers, toevoegen en instellen van het beleid

![Banner die verwijzen naar https://aka.ms/aboutM365preview.](media/m365admincenterchanging.png)

Wanneer u Microsoft 365 Business aanschaft, hebt u de mogelijkheid van een domein dat u de eigenaar of kopen tijdens de [aanmelding](sign-up.md).

- Als u een nieuw domein gekocht toen u zich aanmeldde, uw domein is ingesteld op alle en u kunt [gebruikers toevoegen en toewijzen van licenties](#add-users-and-assign-licenses)kunt verplaatsen.

### <a name="add-your-domain-to-personalize-sign-in"></a>Toevoegen van uw domein om aan te passen-in

1. Aanmelden bij [Microsoft 365 admin center](https://admin.microsoft.com) via uw globale Administrator-referenties. 

2. Kies **een domein gebruikers** **toevoegen** of toevoegen om de wizard te starten.
    > [!IMPORTANT]
    > Als u tijdens de aanmelding bij een domein hebt aangeschaft, kun je het niet Zie **een domein toevoegen** stap hier. Ga in plaats daarvan naar [gebruikers toevoegen](#add-users-and-assign-licenses) .

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

![Schermafbeelding van de pagina nieuwe gebruikers toevoegen in de wizard](media/addnewuserspage.png)

1. Als uw abonnement op Microsoft 365 Business bestaande gebruikers (bijvoorbeeld, als u verbinden met Azure AD) heeft, krijgt u een optie voor het toewijzen van licenties voor hen nu. Wijs nu licenties aan hen toe.

3. Nadat u de gebruikers hebt toegevoegd, krijgt u ook een optie voor het delen van referenties met de nieuwe gebruikers die u hebt toegevoegd. U kunt deze afdrukken, hun een e-mail sturen of deze downloaden.

4. Sla het migreren van e-mailberichten over en kies **Volgende** op de pagina **E-mailberichten migreren**. 

    Als u van een andere e-mailprovider verplaatst en kopieer de gegevens later wilt, kunt u [e-mail migreren en contactpersonen voor Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).


### <a name="connect-your-domain"></a>Uw domein verbinden

> [!NOTE]
> Als u wilt gebruiken het .onmicrosoft domein of verbinden met Azure AD gebruikt om gebruikers in te stellen, worden er niet in deze stap.
  
Als u services wilt instellen, moet u enkele records bij uw DNS-host of domeinregistrar bijwerken.
  
1. Meestal wordt uw registrar automatisch gedetecteerd met de installatiewizard en wordt een koppeling weergegeven naar stapsgewijze instructies voor het bijwerken van uw NS-records op de website van de registrar. Als dat niet het geval, [nameservers voor het instellen van Office 365 met een domeinregistratieservice wijzigen](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2). 

    - Als u bestaande DNS-records, bijvoorbeeld met een bestaande website, wilt u uw eigen DNS-records om ervoor te zorgen dat de bestaande services blijven beheren. Zie [de grondbeginselen van het domein](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) voor meer informatie.

        ![Verbinding maken met uw domein pagina met ik mijn eigen DNS-records kunt beheren.](media/connectyourdomainpage.png)

2. Volg de stappen in de wizard en e-mailadres en andere diensten zal worden voor u ingesteld.

### <a name="set-up-security-policies-and-device-configurations"></a>Instellen van beveiligingsbeleid en -configuraties 

Het beleid dat u hebt ingesteld in de wizard worden automatisch toegepast op de [groep](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) *Alle gebruikers*. Ook kunt u extra groepen wilt toewijzen, beleid voor het in het admin center.

1. Op het **werkbestanden op mobiele apparaten beveiligen** de optie is **Protect werkbestanden bij verlies of diefstal van de apparaten** standaard geselecteerd. U hebt een optie om te **beheren hoe gebruikers toegang kunnen krijgen tot Office-bestanden op mobiele apparaten**inschakelen en deze optie wordt aanbevolen.

    ![Screenshot van bescherming van werk-bestanden op mobiele apparaten pagina.](media/protectworkfilesondevices.png)

     - Vouw de **werkbestanden beveiligen bij verlies of diefstal van de apparaten** voor het weergeven van de [standaardwaarden](protect-work-files-on-lost-or-stolen-device.md):

        ![Screenshot van standaardwaarden voor het beveiligen van bestanden op apparaten verloren.](media/protectworkfilesondevicesdefault.png)

    - Selecteren **hoe gebruikers toegang kunnen krijgen tot Office-bestanden op mobiele apparaten beheren** en uitbreiden om de [waarden](manage-user-access-on-mobile-devices.md)weer te geven. Het is raadzaam tijdens setup toepassingenbeleid maken voor Android, iOS en Windows 10 de standaardwaarden die voor alle gebruikers gelden te accepteren. Nadat de installatie is voltooid, kunt u meer beleidsregels maken.

        ![Screenshot van beveiligingsinstellingen voor Office-bestanden op een mobiel.](media/useraccessonmobile.png)

2. De laatste stap op bescherming van gegevens en apparaten kunt u een beleid instellen voor het beveiligen van Windows 10-apparaten. Deze instellingen worden automatisch toegepast wanneer een gebruiker Windows 10 verbinding met uw organisatie maakt. U kunt **beveiligde Windows 10-apparaten** als u wilt zien en wijzigen van de [standaardwaarden](secure-windows-10-devices.md)kunt uitbreiden.
3. U kunt ook op Windows 10-apparaten [automatisch installeren van Office](install-office-on-windows-10-during-setup.md) .

    ![Screenshot van Windows 10 apparaat configuratiepagina instellen.](media/setwin10config.png)



## <a name="deploy-office-365-client-apps"></a>Office 365-clienttoepassingen installeren

Als u Office apps in automatisch geïnstalleerd tijdens de installatie van, installeert de apps op de Windows 10-apparaten nadat de gebruikers zijn aangemeld bij Azure AD van hun Windows-apparaten met de referenties van hun werk.
Zie [mobiele apparaten voor Microsoft 365 zakelijke gebruikers](set-up-mobile-devices.md)Office installeren op mobiele iOS- of Android apparaten.

U kunt Office ook afzonderlijk installeren. Zie [Office op een PC of Mac installeren](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc471665) voor instructies.
