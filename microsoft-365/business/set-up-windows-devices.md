---
title: Windows-pc's instellen voor gebruikers van Microsoft 365 Business
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: 'Meer informatie over het instellen van Windows-apparaten met Windows 10 Pro voor Microsoft 365 Business-gebruikers. '
ms.openlocfilehash: 427e1c25b5c6ad52ab280502133a0e2808bb48b1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42090644"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-users"></a>Windows-pc's instellen voor gebruikers van Microsoft 365 Business

## <a name="prerequisites"></a>Vereisten

Voordat u Windows-apparaten voor gebruikers van Microsoft 365 Business kunt instellen, moet u ervoor zorgen dat op alle Windows-apparaten Windows 10 Pro, versie 1703 (makersupdate) wordt uitgevoerd. Windows 10 Pro is een vereiste voor de implementatie van Windows 10 Business. Dat is een set cloudservices en apparaatbeheerfuncties die een aanvulling vormt op Windows 10 Pro en die het centrale beheer en de besturingselementen voor beveiliging van Microsoft 365 Business inschakelt.
  
Als u Windows-apparaten met Windows 7 Pro, Windows 8 Pro of Windows 8.1 Pro hebt, geeft uw abonnement op Microsoft 365 Business u recht op een upgrade naar Windows 10.
  
Volg de stappen in dit onderwerp voor meer informatie over het voor Windows-apparaten uitvoeren van een upgrade naar de Windows 10 Pro makersupdate. [Voor Windows-apparaten upgrade uitvoeren naar Windows Pro makersupdate](upgrade-to-windows-pro-creators-update.md).
  
Zie [Controleren of het apparaat is verbonden met Azure AD](#verify-the-device-is-connected-to-azure-ad) om te controleren of u de upgrade hebt of om te controleren of de upgrade is uitgevoerd.

Bekijk een korte video over het verbinden van Windows met Microsoft 365.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

Als u deze video nuttig vond, raadpleegt u dan de [complete training voor kleine bedrijven en degene die nieuw zijn bij Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a>Windows 10-apparaten koppelen aan Azure AD van uw organisatie

Wanneer alle Windows-apparaten in uw organisatie zijn geüpgraded naar Windows 10 Pro Creators Update of al Windows 10 Pro Creators Update uitvoeren, u lid worden van deze apparaten in de Azure Active Directory van uw organisatie. Zodra de apparaten zijn samengevoegd, worden ze automatisch geüpgraded naar Windows 10 Business, dat deel uitmaakt van uw Microsoft 365 Business-abonnement.
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a>Voor een Windows 10 Pro-apparaat dat nieuw is of waarvoor pas een upgrade is uitgevoerd

Voor een nieuw apparaat met Windows 10 Pro makersupdate of voor een apparaat waarvoor wel een upgrade is uitgevoerd naar Windows 10 Pro makersupdate maar waarvoor nog geen apparaatinstellingen voor Windows 10 zijn uitgevoerd, doorloopt u de volgende stappen.
  
1. Doorloop de apparaatinstellingen voor Windows 10 totdat u de pagina **Hoe wilt u instellen?** op uw scherm ziet. 
    
    ![On the How would you like to set up page, choose Set up for an organization](../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. Kies hier voor **Instellen voor een organisatie** en typ vervolgens uw gebruikersnaam en wachtwoord voor Microsoft 365 Business. 
    
3. Voltooi de apparaatinstellingen voor Windows 10.
    
   Als u klaar bent, wordt de gebruiker verbonden met Azure AD van uw organisatie. In [Controleren of het apparaat is verbonden met Azure AD](#verify-the-device-is-connected-to-azure-ad) kunt u zien hoe u dit kunt controleren. 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a>Voor een apparaat dat al is ingesteld en waarop Windows 10 Pro wordt uitgevoerd

 **Gebruikers verbinden met Azure AD**:
  
1. Klik op de Windows-pc van de gebruiker, waarop Windows 10 Pro, versie 1703 (makersupdate) wordt uitgevoerd (zie [vereisten](pre-requisites-for-data-protection.md)), op het Windows-logo en klik op het pictogram Instellingen.
  
   ![In the Start menu, click Windows Settings icon](../media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. Ga in **Instellingen** naar **Accounts**
  
   ![In Windows Settings, go to Accounts](../media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. Klik op de pagina **Uw info** op **Toegang tot werk of school** \> **Verbinden**.
  
   ![Choose Connect under Access work or school](../media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. Kies in het dialoogvenster **Een werk- of schoolaccount instellen** onder **Andere acties** de optie **Dit apparaat toevoegen aan Azure Active Directory**.
  
   ![Click Join this device to Azure Active Directory](../media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. Voer uw werk- of school-e-mailadres in op de pagina **Aanmelden** \> **Volgende**.
  
   Voer op de pagina **Wachtwoord opgeven** uw wachtwoord in \> **Aanmelden**.
  
   ![Enter your work or school email on the Let's get you signed in page](../media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. Controleer op de pagina **Controleren of dit uw organisatie is,** controleer of de informatie juist is en klik op **Deelnemen**.
  
   Klik op de pagina **U bent nu helemaal klaar** op **Gereed**.
  
   ![On the Make sure this is your organization screen, click Join](../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
Als u bestanden hebt geüpload naar OneDrive voor Bedrijven, kunt u deze weer terug synchroniseren. Als u een hulpprogramma van derden hebt gebruikt om profiel en bestanden te migreren, synchroniseert u deze ook met het nieuwe profiel.
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a>Controleren of het apparaat is verbonden met Azure AD

Als u de synchronisatiestatus wilt controleren, klikt u op de pagina **Toegang tot werk of school** in **Instellingen** in het gebied **Verbonden met** _ \<organization name\> _ om de knoppen **Info** en **Verbinding verbreken** weer te geven. Klik op **Info** om de synchronisatiestatus te bekijken. 
  
Klik op de pagina Synchronisatiestatus op Synchroniseren om het recentste beleid voor het beheren van mobiele apparaten naar de pc te downloaden.
  
Als u het Microsoft 365 Business-account wilt gebruiken, gaat u naar de **knop** Start van Windows, klikt u met de rechtermuisknop op uw weergegeven accountafbeelding en vervolgens van **account wisselen**. Meld u aan met het e-mailadres en wachtwoord van uw organisatie.
  
![Click Info button to view synchronization status](../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-device-is-upgraded-to-windows-10-business"></a>Controleren of het apparaat is bijgewerkt naar Windows 10 Business

Controleer of voor de Windows 10-apparaten die aan Azure AD zijn gekoppeld, een upgrade naar Windows 10 Business is uitgevoerd, als onderdeel van uw abonnement op Microsoft 365 Business.
  
1. Ga naar **Instellingen** \> **Systeem** \> **Info**.
    
2. Controleer of bij **Editie** **Windows 10 Business** wordt vermeld.
    
    ![Verify that Windows edition is Windows 10 Business.](../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a>Volgende stappen

Voor het instellen van mobiele apparaten raadpleegt u [Mobiele apparaten instellen voor gebruikers van Microsoft 365 Business](set-up-mobile-devices.md). Voor het instellen van het beveiligingsbeleid voor apparaten of apps raadpleegt u [Microsoft 365 Business beheren](manage.md).
  
## <a name="see-also"></a>Zie ook

[Trainingsvideo's voor Microsoft 365 Business](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
