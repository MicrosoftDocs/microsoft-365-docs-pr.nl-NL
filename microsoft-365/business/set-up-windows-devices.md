---
title: Windows-apparaten instellen voor Microsoft 365 Business Premium-gebruikers
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: Meer informatie over het instellen van Windows-apparaten met Windows 10 Pro voor Microsoft 365 Business Premium-gebruikers, waarmee gecentraliseerde beheer- en beveiligingsbesturingselementen mogelijk zijn.
ms.openlocfilehash: 85ac3c964792a132d5699703e543289020e38f57
ms.sourcegitcommit: e5bc49f0a25954d008b6cc09c2b98bb7bfe1aa2f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785847"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-premium-users"></a>Windows-apparaten instellen voor Microsoft 365 Business Premium-gebruikers

## <a name="prerequisites-for-setting-up-windows-devices-for-microsoft-365-business-premium-users"></a>Voorwaarden voor het instellen van Windows-apparaten voor Microsoft 365 Business Premium-gebruikers

Voordat u Windows-apparaten instellen voor Microsoft 365 Business Premium-gebruikers, controleert u of op alle Windows-apparaten Windows 10 Pro, versie 1703 (Creators Update) wordt uitgevoerd. Windows 10 Pro is een voorwaarde voor de implementatie van Windows 10 Business, een reeks cloudservices en mogelijkheden voor apparaatbeheer die windows 10 Pro aanvullen en de gecentraliseerde beheer- en beveiligingscontroles van Microsoft 365 Business Premium mogelijk maken.
  
Als u Windows-apparaten hebt met Windows 7 Pro, Windows 8 Pro of Windows 8.1 Pro, geeft uw Microsoft 365 Business Premium-abonnement recht op een Windows 10-upgrade.
  
Volg de stappen in dit onderwerp voor meer informatie over het voor Windows-apparaten uitvoeren van een upgrade naar de Windows 10 Pro makersupdate. [Voor Windows-apparaten upgrade uitvoeren naar Windows Pro makersupdate](upgrade-to-windows-pro-creators-update.md).
  
Zie [Controleren of het apparaat is verbonden met Azure AD](#verify-the-device-is-connected-to-azure-ad) om te controleren of u de upgrade hebt uitgevoerd of om te controleren of de upgrade heeft gewerkt.

Bekijk een korte video over het verbinden van Windows met Microsoft 365.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

Als u deze video nuttig vond, raadpleegt u dan de [complete reeks trainingen voor kleine bedrijven en nieuwe gebruikers van Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a>Windows 10-apparaten koppelen aan Azure AD van uw organisatie

Wanneer alle Windows-apparaten in uw organisatie zijn geüpgraded naar Windows 10 Pro Creators Update of al Windows 10 Pro Creators Update draaien, u deze apparaten koppelen aan de Azure Active Directory van uw organisatie. Zodra de apparaten zijn aangesloten, worden ze automatisch geüpgraded naar Windows 10 Business, dat deel uitmaakt van uw Microsoft 365 Business Premium-abonnement.
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a>Voor een Windows 10 Pro-apparaat dat nieuw is of waarvoor pas een upgrade is uitgevoerd

Voor een nieuw apparaat met Windows 10 Pro makersupdate of voor een apparaat waarvoor wel een upgrade is uitgevoerd naar Windows 10 Pro makersupdate maar waarvoor nog geen apparaatinstellingen voor Windows 10 zijn uitgevoerd, doorloopt u de volgende stappen.
  
1. Doorloop de apparaatinstellingen voor Windows 10 totdat u de pagina **Hoe wilt u instellen?** op uw scherm ziet. 
    
    ![On the How would you like to set up page, choose Set up for an organization](../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. Kies hier **Instellen voor een organisatie** en voer vervolgens uw gebruikersnaam en wachtwoord in voor Microsoft 365 Business Premium. 
    
3. Voltooi de apparaatinstellingen voor Windows 10.
    
   Once you're done, the user will be connected to your organization's Azure AD. See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to make sure. 
  
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
  
   On the **You're all set!** page, click **Done**.
  
   ![On the Make sure this is your organization screen, click Join](../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
Als u bestanden hebt geüpload naar OneDrive voor Bedrijven, kunt u deze weer terug synchroniseren. Als u een hulpprogramma van derden hebt gebruikt om profiel en bestanden te migreren, synchroniseert u deze ook met het nieuwe profiel.
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a>Controleren of het apparaat is verbonden met Azure AD

Als u uw synchronisatiestatus wilt verifiëren, klikt u op de pagina **Access-werk of school** in **Instellingen**in het gebied **Verbonden met** _ _ om de \<organization name\> knoppen **Info** en **Loskoppelen**bloot te leggen. Klik op **Info** om de synchronisatiestatus te bekijken. 
  
Klik op de pagina Synchronisatiestatus op Synchroniseren om het recentste beleid voor het beheren van mobiele apparaten naar de pc te downloaden.
  
Als u het Microsoft 365 Business Premium-account wilt gebruiken, gaat u naar de knop **Start** van Windows, klikt u met de rechtermuisknop op de afbeelding van uw huidige account en **schakelt u vervolgens van account .** Meld u aan met het e-mailadres en wachtwoord van uw organisatie.
  
![Click Info button to view synchronization status](../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-device-is-upgraded-to-windows-10-business"></a>Controleren of het apparaat is bijgewerkt naar Windows 10 Business

Controleer of uw Azure AD-apparaten die zijn aangesloten bij Windows 10-apparaten zijn geüpgraded naar Windows 10 Business als onderdeel van uw Microsoft 365 Business Premium-abonnement.
  
1. Ga naar **Instellingen** \> **Systeem** \> **Info**.
    
2. Controleer of bij **Editie** **Windows 10 Business** wordt vermeld.
    
    ![Verify that Windows edition is Windows 10 Business.](../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a>Volgende stappen

Zie [Microsoft 365](set-up-mobile-devices.md) [voor bedrijven](manage.md)beheren als u uw mobiele apparaten wilt instellen.
  
## <a name="for-more-on-setting-up-and-using-microsoft-365-business-premium"></a>Voor meer informatie over het instellen en gebruiken van Microsoft 365 Business Premium

[Trainingsvideo's voor Microsoft 365 voor bedrijven](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
