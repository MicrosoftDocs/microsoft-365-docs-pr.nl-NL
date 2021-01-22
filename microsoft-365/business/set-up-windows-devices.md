---
title: Windows-apparaten instellen voor gebruikers van Microsoft 365 Business Premium
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
- okr_smb
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: Meer informatie over het instellen van Windows-apparaten waarop Windows 10 Pro voor Microsoft 365 Business Premium-gebruikers worden uitgevoerd, waarbij centraal beheer en beveiligingsbesturingselementen worden inschakelen.
ms.openlocfilehash: b1877d83f113a2ba23d0db374967e0afcd7fe067
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928719"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-premium-users"></a>Windows-apparaten instellen voor gebruikers van Microsoft 365 Business Premium

## <a name="prerequisites-for-setting-up-windows-devices-for-microsoft-365-business-premium-users"></a>Vereisten voor het instellen van Windows-apparaten voor gebruikers van Microsoft 365 Business Premium

Voordat u Windows-apparaten kunt instellen voor gebruikers van Microsoft 365 Business Premium, moet u ervoor zorgen dat op alle Windows-apparaten Windows 10 Pro, versie 1703 (makersupdate) wordt uitgevoerd. Windows 10 Pro is een vereiste voor de implementatie van Windows 10 Business. Dit is een set cloudservices en apparaatbeheerfuncties die een aanvulling vormen op Windows 10 Pro en die het centrale beheer en de beveiligingscontroles van Microsoft 365 Business Premium mogelijk maken.
  
Als u Windows-apparaten met Windows 7 Pro, Windows 8 Pro of Windows 8.1 Pro hebt, geeft uw Abonnement op Microsoft 365 Business Premium u recht op een upgrade naar Windows 10.
  
Volg de stappen in dit onderwerp voor meer informatie over het voor Windows-apparaten uitvoeren van een upgrade naar de Windows 10 Pro makersupdate. [Voor Windows-apparaten upgrade uitvoeren naar Windows Pro makersupdate](upgrade-to-windows-pro-creators-update.md).
  
Zie [Controleren of het apparaat is verbonden met Azure AD](#verify-the-device-is-connected-to-azure-ad) om te controleren of u de upgrade hebt of om te controleren of de upgrade heeft gewerkt.

Bekijk een korte video over het verbinden van Windows met Microsoft 365.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

Als je deze video nuttig vond, raadpleeg dan de [complete reeks trainingen voor kleine bedrijven en nieuwe gebruikers van Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a>Windows 10-apparaten koppelen aan Azure AD van uw organisatie

Wanneer voor alle Windows-apparaten in uw organisatie een upgrade is uitgevoerd naar Windows 10 Pro makersupdate of als windows 10 Pro makersupdate al wordt uitgevoerd, kunt u deze apparaten toevoegen aan Azure Active Directory van uw organisatie. Nadat de apparaten zijn samengevoegd, worden ze automatisch bijgewerkt naar Windows 10 Business, dat deel uitmaakt van uw Microsoft 365 Business Premium-abonnement.
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a>Voor een Windows 10 Pro-apparaat dat nieuw is of waarvoor pas een upgrade is uitgevoerd

Voor een nieuw apparaat met Windows 10 Pro makersupdate of voor een apparaat waarvoor wel een upgrade is uitgevoerd naar Windows 10 Pro makersupdate maar waarvoor nog geen apparaatinstellingen voor Windows 10 zijn uitgevoerd, doorloopt u de volgende stappen.
  
1. Doorloop de apparaatinstellingen voor Windows 10 totdat u de pagina **Hoe wilt u instellen?** op uw scherm ziet. 
    
    ![On the How would you like to set up page, choose Set up for an organization](../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. Kies hier **Instellen voor een organisatie en** voer uw gebruikersnaam en wachtwoord voor Microsoft 365 Business Premium in. 
    
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
  
6. Controleer op de pagina Controleer of **dit de pagina van** uw organisatie is of de gegevens juist zijn en kies **Deelnemen.**
  
   Aan de **set U bent klaar!** pagina, chosse **Done.**
  
   ![Kies Deelnemen in het scherm Zorg ervoor dat dit het scherm van uw organisatie is](../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
Als u bestanden hebt geüpload naar OneDrive voor Bedrijven, kunt u deze weer terug synchroniseren. Als u een hulpprogramma van derden hebt gebruikt om een profiel en bestanden te migreren, moet u deze ook synchroniseren naar het nieuwe profiel.
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a>Controleren of het apparaat is verbonden met Azure AD

Als u uw synchronisatiestatus wilt controleren, selecteert u op de **werk-** of schoolpagina **van** Access in Instellingen het gebied Verbonden met **_** _ om de knoppen Info en Verbinding verbreken weer te \<organization name\> **geven.**  Kies **Info** om de synchronisatiestatus op te halen. 
  
Kies Synchroniseren **op de pagina Synchronisatiestatus**  om het nieuwste beleid voor mobile device management op de pc op te halen.
  
Als u het Microsoft 365 Business Premium-account wilt gaan gebruiken, gaat u naar de **startknop** van Windows, klikt u met de rechtermuisknop op uw huidige accountafbeelding en schakelt u over **naar een andere account.** Meld u aan met het e-mailadres en wachtwoord van uw organisatie.
  
![Click Info button to view synchronization status](../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-pc-is-upgraded-to-windows-10-business"></a>Controleren of de pc is bijgewerkt naar Windows 10 Business

Controleer of uw Windows 10-apparaten die lid zijn van Azure AD, zijn bijgewerkt naar Windows 10 Business als onderdeel van uw Abonnement op Microsoft 365 Business Premium.
  
1. Ga naar **Instellingen** \> **Systeem** \> **Info**.
    
2. Controleer of bij **Editie** **Windows 10 Business** wordt vermeld.
    
    ![Verify that Windows edition is Windows 10 Business.](../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a>Volgende stappen

Zie Mobiele apparaten instellen voor gebruikers van [Microsoft 365 Business Premium](set-up-mobile-devices.md)als u een beveiligingsbeleid voor apparaten of apps wilt instellen. Zie Microsoft [365](manage.md)voor Bedrijven beheren.
  
## <a name="for-more-on-setting-up-and-using-microsoft-365-business-premium"></a>Voor meer informatie over het instellen en gebruiken van Microsoft 365 Business Premium

[Trainingsvideo's voor Microsoft 365 voor bedrijven](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
