---
title: Beveiligingsinstellingen voor apps op Windows 10-pc's valideren
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
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Meer informatie over het valideren van Microsoft 365 Business app Protection-instellingen in Windows 10-apparaten.
ms.openlocfilehash: c54b053c1f6efbca8fd02431c416793a044c6821
ms.sourcegitcommit: 6a413a65b8c2e10cea08f0a15635b28a1362a582
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/19/2019
ms.locfileid: "38721855"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a>Beveiligingsinstellingen voor apps op Windows 10-pc's valideren

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a>Controleren of gebruikers geen bedrijfsgegevens kunnen kopiëren naar persoonlijke bestanden op bedrijfsapparaten

Nadat u [beveiligingsbeleid voor apps hebt ingesteld](protection-settings-for-windows-10-devices.md), kan het enkele uren duren voordat het beleid van kracht wordt op apparaten van gebruikers. Als u hebt ingeschakeld de **voorkomen dat gebruikers bedrijfsgegevens naar persoonlijke bestanden kopiëren en hen dwingen om werkbestanden op te slaan in OneDrive voor bedrijven** -instelling voor apparaten die eigendom zijn **van het bedrijf** , u dit controleren op het apparaat van de gebruiker nadat ze verbinding hebben gemaakt met Azure AD en aangemeld. 
  
 **Verbindingsinstellingen controleren**
  
1. Nadat u zich hebt aangemeld met Microsoft 365 Business-referenties en verbinding maakt met Azure AD (zoals beschreven in [Windows-apparaten instellen voor gebruikers van Microsoft 365 Business](set-up-windows-devices.md)), gaat u naar **Windows-instellingen** \> **Accounts** \> **Toegang tot werk of school**. Kies **Verbonden met Azure AD van \<naam tenant\>** en kies vervolgens **Info**.
    
    ![Click or tap Info on the Connected to Azure AD dialog.](media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. Op de **beheerde door** \<tenantnaam\> pagina, ziet u de **verbindingsgegevens** die een **beheer server-adres** zoals wordt weergegeven in de volgende afbeelding bevat. 
    
    ![Managed by page shows connection info of the device manager URL.](media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 **Controleren of u bedrijfsgegevens niet in een niet-beheerde app plakken**
  
1. Open Outlook 2016, geïnstalleerd door Microsoft 365 Business.
    
2. Open een e-mail en kopieer er een deel van de inhoud van.
    
    Open Kladblok en plak het deel hierin.
    
    U ontvangt een foutbericht waarin wordt bepaald dat de app geen toegang heeft tot inhoud.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    U kunt echter wel dezelfde inhoud in Word 2016 plakken.
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a>Controleren of gebruikers geen bedrijfsgegevens kunnen kopiëren naar persoonlijke bestanden op persoonlijke apparaten

 **Verbindingsinstellingen controleren**
  
1. Op uw Windows 10 Personal-apparaat waar u bent aangemeld als een lokale gebruiker, gaat u **naar Windows-instellingen**en klikt of tikt u op **accounts** \> **toegang werk of school**.
    
2. Kies **Verbinden** onder **Toegang tot werk of school**.
    
3. Voer uw Microsoft 365 Business-referenties in in het dialoogvenster **Een werk- of schoolaccount instellen** \> **Aanmelden**.
    
4. Kies op de pagina **Toegang tot werk of school** de optie **Werk- of schoolaccount** en vervolgens **Info**.
    
    ![Klik of tik op info in het dialoogvenster werk of schoolaccount.](media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. Op de pagina **toegang werk of school** ziet u de **verbindingsgegevens** met een adres van de **beheer server** , zoals in de volgende afbeelding wordt weergegeven, en bevat de woorden *OHW* en *mam* binnen. 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 **Controleren of u bedrijfsgegevens niet in een niet-beheerde app plakken**
  
1. Open Outlook 2016 en voeg eventueel uw Microsoft 365 Business-account toe en meld u aan met uw Microsoft 365 Business-referenties.
    
2. Open een e-mail en kopieer er een deel van de inhoud van.
    
    Open Kladblok en plak het deel hierin.
    
    Er wordt een foutbericht weergegeven dat de app geen toegang heeft tot inhoud.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    U kunt echter wel dezelfde inhoud in Word 2016 plakken.
    

