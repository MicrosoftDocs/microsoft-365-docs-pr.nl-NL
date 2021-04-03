---
title: Beveiligingsinstellingen voor apps op Windows 10-pc's valideren
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Valideer de beveiligingsinstellingen van Microsoft 365 Business Premium-apps op Windows 10-apparaten en controleer of gebruikers bedrijfsgegevens niet kunnen kopiëren naar persoonlijke bestanden of niet-beheerde apps.
ms.openlocfilehash: e319ffa5149f055b5de45078facc8899acffc223
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579857"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a>Beveiligingsinstellingen voor apps op Windows 10-pc's valideren

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a>Controleren of gebruikers geen bedrijfsgegevens kunnen kopiëren naar persoonlijke bestanden op bedrijfsapparaten

Nadat u [beveiligingsbeleid voor apps hebt ingesteld](protection-settings-for-windows-10-devices.md), kan het enkele uren duren voordat het beleid van kracht wordt op apparaten van gebruikers. Als u  De instelling Voorkomen dat gebruikers bedrijfsgegevens kopiëren naar persoonlijke bestanden hebt ingeschakeld en ze dwingt om werkbestanden op te slaan in **OneDrive voor** Bedrijven voor apparaten die eigendom zijn van het bedrijf, kunt u dit controleren op het apparaat van de gebruiker nadat ze verbinding hebben gemaakt met Azure AD en zich hebben aangemeld. 
  
 **Verbindingsinstellingen controleren**
  
1. Nadat u zich hebt aanmelden met Microsoft 365 Business Premium-referenties en verbinding hebt met Azure AD, zoals beschreven in Windows-apparaten instellen voor [Microsoft 365 Business](set-up-windows-devices.md)Premium-gebruikers, gaat u naar **Windows Settings** Accounts Access werk of \>  \> **school.** Kies **Verbonden met Azure \<tenant name\> AD** en kies vervolgens **Info.**
    
    ![Click or tap Info on the Connected to Azure AD dialog.](../media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. Op de pagina Beheerd **door** ziet u de verbindingsgegevens met een Adres van \<tenant name\>  **managementserver,** zoals in de volgende afbeelding. 
    
    ![Managed by page shows connection info of the device manager URL.](../media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 **Controleren of u geen bedrijfsgegevens in een niet-beheerde app kunt plakken**
  
1. Open Outlook 2016 die is geïnstalleerd door Microsoft 365 Business Premium.
    
2. Open een e-mail en kopieer er een deel van de inhoud van.
    
    Open Kladblok en plak het deel hierin.
    
    U krijgt een foutmelding dat de app geen toegang heeft tot inhoud.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    U kunt echter wel dezelfde inhoud in Word 2016 plakken.
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a>Controleren of gebruikers geen bedrijfsgegevens kunnen kopiëren naar persoonlijke bestanden op persoonlijke apparaten

 **Verbindingsinstellingen controleren**
  
1. Ga op uw persoonlijke Windows 10-apparaat waar u bent aangemeld als lokale gebruiker naar **Windows-instellingen** en klik of tik op Werk of school  \> **accountstoegang.**
    
2. Kies **Verbinden** onder **Toegang tot werk of school**.
    
3. Voer uw Microsoft 365 Business Premium-referenties in in het dialoogvenster Een werk- of **schoolaccount** \> **instellen Aanmelden.**
    
4. Kies op de pagina **Toegang tot werk of school** de optie **Werk- of schoolaccount** en vervolgens **Info**.
    
    ![Klik of tik op Info in het dialoogvenster Werk- of schoolaccount.](../media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. Op de **werk-** of schoolpagina  van Access kunt u de verbindingsgegevens zien met een Adres van **de beheerserver,** zoals in de volgende afbeelding, en worden de woorden wip *en* *mam* binnen weergegeven. 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](../media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 **Controleren of u geen bedrijfsgegevens in een niet-beheerde app kunt plakken**
  
1. Open Outlook 2016 en voeg zo nodig uw Microsoft 365 Business Premium-account toe en meld u aan met uw Microsoft 365 Business Premium-referenties.
    
2. Open een e-mail en kopieer er een deel van de inhoud van.
    
    Open Kladblok en plak het deel hierin.
    
    U ontvangt een foutmelding dat App geen toegang heeft tot inhoud.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    U kunt echter wel dezelfde inhoud in Word 2016 plakken.
    

