---
title: Beveiligingsinstellingen voor apps op Windows 10-pc's valideren
f1.keywords:
- NOCSH
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
description: Meer informatie over het valideren van beveiligingsinstellingen voor Microsoft 365 Business-apps in Windows 10-apparaten.
ms.openlocfilehash: 6573519ee2fe2d1eb82545755fa98b8c018e08ff
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594990"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a>Beveiligingsinstellingen voor apps op Windows 10-pc's valideren

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a>Controleren of gebruikers geen bedrijfsgegevens kunnen kopiëren naar persoonlijke bestanden op bedrijfsapparaten

Nadat u [beveiligingsbeleid voor apps hebt ingesteld](protection-settings-for-windows-10-devices.md), kan het enkele uren duren voordat het beleid van kracht wordt op apparaten van gebruikers. Als u **de** instelling Voorkomen dat gebruikers bedrijfsgegevens naar persoonlijke bestanden kopieert inschakelt en **hen dwingt werkbestanden op te slaan in** de instelling OneDrive voor Bedrijven voor apparaten die eigendom zijn van het bedrijf, u dit controleren op het apparaat van de gebruiker nadat ze zijn verbonden met Azure AD en zijn aangemeld. 
  
 **Verbindingsinstellingen controleren**
  
1. Nadat u zich hebt aangemeld met Microsoft 365 Business-referenties en verbinding maakt met Azure AD (zoals beschreven in [Windows-apparaten instellen voor gebruikers van Microsoft 365 Business](set-up-windows-devices.md)), gaat u naar **Windows-instellingen** \> **Accounts** \> **Toegang tot werk of school**. Kies **Verbonden met Azure AD van \<naam tenant\>** en kies vervolgens **Info**.
    
    ![Click or tap Info on the Connected to Azure AD dialog.](media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. Op de pagina\> Beheer **door** \<tenant u de **verbindingsgegevens** zien die een **managementserveradres** bevatten, zoals in de volgende afbeelding wordt weergegeven. 
    
    ![Managed by page shows connection info of the device manager URL.](media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 **Controleren of u bedrijfsgegevens niet plakken in een niet-beheerde app**
  
1. Open Outlook 2016, geïnstalleerd door Microsoft 365 Business.
    
2. Open een e-mail en kopieer er een deel van de inhoud van.
    
    Open Kladblok en plak het deel hierin.
    
    U ontvangt een foutmelding dat de app geen toegang heeft tot inhoud.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    U kunt echter wel dezelfde inhoud in Word 2016 plakken.
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a>Controleren of gebruikers geen bedrijfsgegevens kunnen kopiëren naar persoonlijke bestanden op persoonlijke apparaten

 **Verbindingsinstellingen controleren**
  
1. Ga op uw persoonlijke windows 10-apparaat waar u als lokale gebruiker bent aangemeld naar **Windows-instellingen**en klik of tik op het werk of de school **van Accounts** \> **Toegang.**
    
2. Kies **Verbinden** onder **Toegang tot werk of school**.
    
3. Voer uw Microsoft 365 Business-referenties in in het dialoogvenster **Een werk- of schoolaccount instellen** \> **Aanmelden**.
    
4. Kies op de pagina **Toegang tot werk of school** de optie **Werk- of schoolaccount** en vervolgens **Info**.
    
    ![Klik of tik op Info in het dialoogvenster Werk- of schoolaccount.](media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. Op de **pagina Werk of school toegang** u de **verbindingsgegevens** zien die een **managementserveradres** bevatten, zoals in de volgende afbeelding, en de woorden *wip* en *mam* binnenin bevat. 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 **Controleren of u bedrijfsgegevens niet plakken in een niet-beheerde app**
  
1. Open Outlook 2016 en voeg eventueel uw Microsoft 365 Business-account toe en meld u aan met uw Microsoft 365 Business-referenties.
    
2. Open een e-mail en kopieer er een deel van de inhoud van.
    
    Open Kladblok en plak het deel hierin.
    
    U ontvangt een foutmelding dat App geen toegang heeft tot inhoud.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    U kunt echter wel dezelfde inhoud in Word 2016 plakken.
    

