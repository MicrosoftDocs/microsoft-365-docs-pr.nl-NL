---
title: Beveiligingsinstellingen voor apps op Windows 10-pc's valideren
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Informatie over het valideren van de beveiligingsinstellingen van Microsoft 365 Business app in Windows 10-apparaten.
ms.openlocfilehash: f00dd380103ad9498d77b0e8814bace3de168df4
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/28/2018
ms.locfileid: "26983292"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a>Beveiligingsinstellingen voor apps op Windows 10-pc's valideren

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a>Controleren of gebruikers geen bedrijfsgegevens kunnen kopiëren naar persoonlijke bestanden op bedrijfsapparaten

Nadat u [beveiligingsbeleid voor apps hebt ingesteld](protection-settings-for-windows-10-devices.md), kan het enkele uren duren voordat het beleid van kracht wordt op apparaten van gebruikers. Als u de instelling **Voorkomen dat gebruikers bedrijfsgegevens kopiëren naar persoonlijke bestanden en afdwingen dat werkbestanden worden opgeslagen in OneDrive voor Bedrijven** hebt **ingeschakeld** op apparaten die eigendom zijn van het bedrijf, kunt u dit controleren op het apparaat van de gebruiker nadat deze verbinding heeft gemaakt met Azure AD en zich heeft aangemeld. 
  
 **Verbindingsinstellingen controleren**
  
1. Nadat u zich hebt aangemeld met Microsoft 365 Business-referenties en verbinding maakt met Azure AD (zoals beschreven in [Windows-apparaten instellen voor gebruikers van Microsoft 365 Business](set-up-windows-devices.md)), gaat u naar **Windows-instellingen** \> **Accounts** \> **Toegang tot werk of school**. Kies **Verbonden met Azure AD van \<naam tenant\>** en kies vervolgens **Info**.
    
    ![Click or tap Info on the Connected to Azure AD dialog.](media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. Op de pagina **Beheerd door** \<naam tenant\> kunt u de **verbindingsgegevens** zien met een **adres van een beheerserver**, zoals in de volgende afbeelding. 
    
    ![Managed by page shows connection info of the device manager URL.](media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 **Controleren of u geen bedrijfsgegeven kunt plakken naar een niet-beheerde app**
  
1. Open Outlook 2016, geïnstalleerd door Microsoft 365 Business.
    
2. Open een e-mail en kopieer er een deel van de inhoud van.
    
    Open Kladblok en plak het deel hierin.
    
    U krijgt een foutmelding met de mededeling dat de app geen toegang heeft tot inhoud.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    U kunt echter wel dezelfde inhoud in Word 2016 plakken.
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a>Controleren of gebruikers geen bedrijfsgegevens kunnen kopiëren naar persoonlijke bestanden op persoonlijke apparaten

 **Verbindingsinstellingen controleren**
  
1. Ga op uw persoonlijke Windows 10-apparaat, waarop u als lokale gebruiker bent aangemeld, naar **Windows-instellingen** en klik of tik op **Accounts** \> **Toegang tot werk of school**.
    
2. Kies **Verbinden** onder **Toegang tot werk of school**.
    
3. Voer uw Microsoft 365 Business-referenties in in het dialoogvenster **Een werk- of schoolaccount instellen** \> **Aanmelden**.
    
4. Kies op de pagina **Toegang tot werk of school** de optie **Werk- of schoolaccount** en vervolgens **Info**.
    
    ![Click or tap Info on the Work or school account dalog.](media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. Op de pagina **Toegang tot werk of school** ziet u de **verbindingsgegevens** met het **adres van de beheerserver**, zoals in de volgende afbeelding. Dit adres bevat de woorden  *wip*  en  *mam*  . 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 **Controleren of u geen bedrijfsgegeven kunt plakken naar een niet-beheerde app**
  
1. Open Outlook 2016 en voeg eventueel uw Microsoft 365 Business-account toe en meld u aan met uw Microsoft 365 Business-referenties.
    
2. Open een e-mail en kopieer er een deel van de inhoud van.
    
    Open Kladblok en plak het deel hierin.
    
    U krijgt een foutmelding met de mededeling dat de app geen toegang heeft tot inhoud.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    U kunt echter wel dezelfde inhoud in Word 2016 plakken.
    

