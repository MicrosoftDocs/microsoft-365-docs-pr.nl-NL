---
title: Microsoft 365 Business instellen met de wizard Setup
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
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Informatie over het instellen van Microsoft 365 Business door vier stappen uit te voeren.
ms.openlocfilehash: f57239b884bd2e186c0bc01973130a10fa4cfe84
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/16/2019
ms.locfileid: "26982192"
---
# <a name="set-up-microsoft-365-business-by-using-the-setup-wizard"></a>Microsoft 365 Business instellen met de wizard Setup

De stappen 1-4 hieronder.
  
### <a name="set-up-microsoft-365-business"></a>Microsoft 365 Business instellen

Bekijk een video over hoe Microsoft 365 Business instellen wanneer u een Active Directory op de locatie niet hebt:
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/0705c337-f3e8-4d28-bb6c-530cd28e99f2?autoplay=false]
  
De installatie stappen omvatten informatie over instellingen die de lokale Active Directory opnemen. Als u doorgaan wilt naar apparaten die deel uitmaakt van een domein, leest u de volgende artikelen voor twee verschillende manier in te schakelen die en voer de stappen uit voordat u de wizard Setup uitvoert:
  
- [Toestaan dat aan een domein toegevoegde Windows 10-apparaten door Microsoft 365 Business worden beheerd](manage-windows-devices.md)
    
    -Dit is de aanbevolen manier.
    
- [Toegang op-premises resources uit een Azure AD verbonden apparaat in Microsoft 365 Business](access-resources.md)
    
### <a name="step-1-personalize-sign-in"></a>Stap 1: Aanmelden aanpassen

1. Meld u aan bij [Microsoft 365 Business](https://portal.microsoft.com) met uw globale-beheerdersreferenties. Kies de tegel **Beheerder** om naar het beheercentrum te gaan. 
    
2. Kies **Setup starten** (afhankelijk van uw status ziet u in plaats hiervan mogelijk **Doorgaan met setup** in het beheercentrum om de wizard te starten. 
    
3. Voer de domeinnaam in die u wilt gebruiken (zoals contoso.com).
    
    Ga verder en geef uw domein, zelfs als u dit hebt gecontroleerd tijdens het gebruik van Azure AD Connect, bijvoorbeeld. De volgende twee stappen niet van toepassing op u als u Azure AD verbinden om te controleren of uw domein gebruikt.
    
4. Volg de stappen in de wizard [maken DNS-records bij een DNS-hosting provider voor Office 365](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) waarmee wordt gecontroleerd of dat u de eigenaar van het domein. 
    
    Ziet u een voorbeeld van de video van [Video: Office 365-instelling in het nieuwe Admin Center](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8). Opmerking: deze video bevat niet de stappen van de bescherming van gegevens van Microsoft 365 Business.
    
    ![Screenshot of the Business Cloud Suite setup wizard.](media/3c4fd40c-2de1-4a87-8ee0-78d3928c7bb7.png)
  
### <a name="step-2-add-users-and-assign-licenses"></a>Stap 2: Toevoegen van gebruikers en toewijzen van licenties

1. U kunt hier gebruikers toevoegen of u kunt [gebruikers later toevoegen](add-users-m365b.md) in het beheercentrum. 
    
    Aan gebruikers die u toevoegt, wordt automatisch een Microsoft 365 Business-licentie toegewezen.
    
2. Als uw Microsoft 365 Business-abonnement bestaande gebruikers heeft (bijvoorbeeld als u Azure AD Connect hebt gebruikt), hebt u een optie om nu licenties aan hen toe te wijzen. Wijs nu licenties aan hen toe.
    
3. U krijgt ook een optie voor het delen van referenties met de nieuwe gebruikers die u hebt toegevoegd. U kunt deze afdrukken, hun een e-mail sturen of deze downloaden.
    
4. Sla het migreren van e-mailberichten over en kies **Volgende** op de pagina **E-mailberichten migreren**. 
    
    Als u van een andere e-mailprovider verplaatst en kopieer de gegevens later wilt, kunt u [e-mail migreren en contactpersonen voor Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).
    
    ![Screenshot of two new users added in the setup wizard](media/8f729967-5c65-4ceb-b737-18119db40564.png)
  
### <a name="step-3-connect-your-domain"></a>Stap 3: Uw domein verbinding

> [!NOTE]
> Als u hebt gekozen voor het gebruik van het domein .onmicrosoft of Azure AD Connect gebruikt, ziet u deze stap niet. 
  
Als u services wilt instellen, moet u enkele records bij uw DNS-host of domeinregistrar bijwerken.
  
1. De wizard setup detecteert uw registratieservice meestal en geeft u een koppeling naar de stapsgewijze instructies voor het bijwerken van de NS-records bij de domeinregistratie. Als dat niet het geval, [nameservers voor het instellen van Office 365 met een domeinregistratieservice wijzigen](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).
    
2. E-mail en andere services worden voor u ingesteld
    
### <a name="step-4-manage-devices-and-work-files"></a>Stap 4: Apparaten beheren en bestanden te werken

1. Op de **werkbestanden beveiligen op uw mobiele apparaten** instellen pagina **beveiligen werkbestanden bij verlies of diefstal van de apparaten** en instellingen **beheren hoe gebruikers toegang kunnen krijgen tot Office-bestanden op mobiele apparaten** **aan**. U kunt ook toegang krijgen tot elk sub instellen door te klikken op de pijltjes naast elke instelling.
  
  Alle werkbestanden van uw gelicentieerde gebruikers kunnen nu worden beveiligd op iOS en Android-apparaten, zodra ze [Office apps installeren](set-up-mobile-devices.md) (en te verifiëren met hun referenties Microsoft 365 Business). 
  
  ![Screenshot of protect work files on your mobile devices page](media/3139a9aa-6228-4e74-8166-c6a886d7319f.PNG)
  
2. Klik op de pagina **configuratie van Windows 10 instellen** instellen **Secure Windows 10-apparaten** **aan**.
  
   U kunt ook toegang krijgen tot elke Sub instellen door te klikken op de dubbele punthaken ernaast.
  
3. De **Installatie van Office op Windows 10-apparaten** instelt op **Ja** als alle gebruikers computers Windows 10 hebt en geen bestaande Office installeert of klik-en-klaar Office wordt geïnstalleerd. Als dit niet het geval is, moet u deze optie instelt op **Nee**. Kunt u [automatisch installeren van Office](auto-install-or-uninstall-office.md) later via het admin center nadat u de computer van gebruikers hebt voorbereid. Zie [Office client-installatie voorbereiden](prepare-for-office-client-deployment.md)voor meer informatie.
  
    De gelicentieerde gebruikers werkbestanden op apparaten met Windows 10 worden zodra ze worden geprojecteerd [deelnemen aan hun Windows 10-apparaat](set-up-windows-devices.md) naar een Business 365 Microsoft Azure AD-domein of [Windows 10 op een nieuwe computer hebt geïnstalleerd](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx) , terwijl het tegelijkertijd lid worden van de Microsoft-365 Business Azure AD-domein. 
  
4. Klik op **volgende** en u klaar bent met de installatie. 
  
    Laat ons feedback op deze stap om te helpen bij het verbeteren van de ervaring.
  
    ![Screenshot of Prepare Windows 10 devices page](media/bff701c1-48a3-44f4-aa95-9d959d57c85b.PNG)
  
## <a name="additional-security-settings"></a>Extra beveiligingsinstellingen

Naast de beveiliging en naleving instellen in de wizard setup kunt u ook de volgende aanvullende instellingen instellen:
  
- Bescherming tegen onveilige bijlagen instellen. **Advanced Threat Protection** (ATP) identificeert schadelijke inhoud en vervolgens blokkeert levering van onveilige bijlagen te beschermen u tegen phishing-trucs en ransomware infecties. Zie bijlage bescherming activeren [Office 365 ATP veilige bijlagen beleid instellen](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy).
    
- Bescherm uw omgeving wanneer de gebruiker op een schadelijke koppelingen. ATP onderzoekt koppelingen in e-mailbericht op het moment dat een gebruiker klikt. Als u een koppeling onveilig is, wordt de gebruiker gewaarschuwd niet te bezoeken of op de hoogte gesteld dat de site is geblokkeerd. Dit biedt bescherming tegen phishing-trucs. [Instellen van het beleid van Office 365 ATP veilige koppelingen](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) of [Office 365 ATP veilige koppelingen beleid instellen](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).
    
- U kunt alle inhoud met inbegrip van verwijderde items door het volledige postvak van een gebruiker plaatsen op **rechtszaak houdt**behouden. Zie voor meer informatie 
- Het [vasthouden van e-mail met Exchange Online archiveren instellen](security-features.md#set-up-email-retention-with-exchange-online-archiving).
    
- Stel aangepaste **bewaarbeleid**, bijvoorbeeld gedurende een bepaalde tijd behouden of definitief verwijderen van inhoud aan het einde van de bewaarperiode. Kunt u aangepaste bewaarbeleid in effecten en Ga naar de **Data governance** conformiteit \> **vasthouden**, en volg de stappen in de wizard. Voor meer informatie, Zie [overzicht van het bewaarbeleid](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).
    
## <a name="next-steps"></a>Volgende stappen

Voor gebruikers die de benodigde licenties al hebben, is de volgende stap het instellen van apparaten.<br/> Zie [Windows-apparaten instellen voor gebruikers van Microsoft 365 Business](set-up-windows-devices.md) en [Mobiele apparaten instellen voor gebruikers van Microsoft 365 Business](set-up-mobile-devices.md). <br/>Zie [Microsoft 365 Business beheren](manage.md) voor koppelingen naar onderwerpen over het instellen van beveiligingsbeleid voor apparaten en apps en over het verwijderen van gegevens uit gebruikersapparaten. 
  


