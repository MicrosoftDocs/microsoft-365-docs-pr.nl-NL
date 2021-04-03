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
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="f3b0d-103">Beveiligingsinstellingen voor apps op Windows 10-pc's valideren</span><span class="sxs-lookup"><span data-stu-id="f3b0d-103">Validate app protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a><span data-ttu-id="f3b0d-104">Controleren of gebruikers geen bedrijfsgegevens kunnen kopiëren naar persoonlijke bestanden op bedrijfsapparaten</span><span class="sxs-lookup"><span data-stu-id="f3b0d-104">Verify that users cannot copy company data to personal files on corporate devices</span></span>

<span data-ttu-id="f3b0d-105">Nadat u [beveiligingsbeleid voor apps hebt ingesteld](protection-settings-for-windows-10-devices.md), kan het enkele uren duren voordat het beleid van kracht wordt op apparaten van gebruikers.</span><span class="sxs-lookup"><span data-stu-id="f3b0d-105">After you [set up app protection policies](protection-settings-for-windows-10-devices.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="f3b0d-106">Als u  De instelling Voorkomen dat gebruikers bedrijfsgegevens kopiëren naar persoonlijke bestanden hebt ingeschakeld en ze dwingt om werkbestanden op te slaan in **OneDrive voor** Bedrijven voor apparaten die eigendom zijn van het bedrijf, kunt u dit controleren op het apparaat van de gebruiker nadat ze verbinding hebben gemaakt met Azure AD en zich hebben aangemeld.</span><span class="sxs-lookup"><span data-stu-id="f3b0d-106">If you turned **On** the **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** setting for company owned devices, you can check this on the user's device after they've connected to Azure AD and signed in.</span></span> 
  
 <span data-ttu-id="f3b0d-107">**Verbindingsinstellingen controleren**</span><span class="sxs-lookup"><span data-stu-id="f3b0d-107">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="f3b0d-108">Nadat u zich hebt aanmelden met Microsoft 365 Business Premium-referenties en verbinding hebt met Azure AD, zoals beschreven in Windows-apparaten instellen voor [Microsoft 365 Business](set-up-windows-devices.md)Premium-gebruikers, gaat u naar **Windows Settings** Accounts Access werk of \>  \> **school.**</span><span class="sxs-lookup"><span data-stu-id="f3b0d-108">After you sign in with Microsoft 365 Business Premium credentials and connect to Azure AD as described in [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md), go to **Windows Settings** \> **Accounts** \> **Access work or school**.</span></span> <span data-ttu-id="f3b0d-109">Kies **Verbonden met Azure \<tenant name\> AD** en kies vervolgens **Info.**</span><span class="sxs-lookup"><span data-stu-id="f3b0d-109">Choose **Connected to \<tenant name\> Azure AD**, and then choose **Info**.</span></span>
    
    ![Click or tap Info on the Connected to Azure AD dialog.](../media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. <span data-ttu-id="f3b0d-111">Op de pagina Beheerd **door** ziet u de verbindingsgegevens met een Adres van \<tenant name\>  **managementserver,** zoals in de volgende afbeelding.</span><span class="sxs-lookup"><span data-stu-id="f3b0d-111">On the **Managed by** \<tenant name\> page, you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure.</span></span> 
    
    ![Managed by page shows connection info of the device manager URL.](../media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 <span data-ttu-id="f3b0d-113">**Controleren of u geen bedrijfsgegevens in een niet-beheerde app kunt plakken**</span><span class="sxs-lookup"><span data-stu-id="f3b0d-113">**Verify that you cannot paste company data in a non-managed app**</span></span>
  
1. <span data-ttu-id="f3b0d-114">Open Outlook 2016 die is geïnstalleerd door Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="f3b0d-114">Open Outlook 2016 that was installed by Microsoft 365 Business Premium.</span></span>
    
2. <span data-ttu-id="f3b0d-115">Open een e-mail en kopieer er een deel van de inhoud van.</span><span class="sxs-lookup"><span data-stu-id="f3b0d-115">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="f3b0d-116">Open Kladblok en plak het deel hierin.</span><span class="sxs-lookup"><span data-stu-id="f3b0d-116">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="f3b0d-117">U krijgt een foutmelding dat de app geen toegang heeft tot inhoud.</span><span class="sxs-lookup"><span data-stu-id="f3b0d-117">You'll receive an error that states the app can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="f3b0d-119">U kunt echter wel dezelfde inhoud in Word 2016 plakken.</span><span class="sxs-lookup"><span data-stu-id="f3b0d-119">You can, however, paste the same content into Word 2016.</span></span>
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a><span data-ttu-id="f3b0d-120">Controleren of gebruikers geen bedrijfsgegevens kunnen kopiëren naar persoonlijke bestanden op persoonlijke apparaten</span><span class="sxs-lookup"><span data-stu-id="f3b0d-120">Verify that users cannot copy company data to personal files on personal devices</span></span>

 <span data-ttu-id="f3b0d-121">**Verbindingsinstellingen controleren**</span><span class="sxs-lookup"><span data-stu-id="f3b0d-121">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="f3b0d-122">Ga op uw persoonlijke Windows 10-apparaat waar u bent aangemeld als lokale gebruiker naar **Windows-instellingen** en klik of tik op Werk of school  \> **accountstoegang.**</span><span class="sxs-lookup"><span data-stu-id="f3b0d-122">On your Windows 10 personal device where you're logged in as a local user, go to **Windows Settings**, and click or tap **Accounts** \> **Access work or school**.</span></span>
    
2. <span data-ttu-id="f3b0d-123">Kies **Verbinden** onder **Toegang tot werk of school**.</span><span class="sxs-lookup"><span data-stu-id="f3b0d-123">Under the **Access work or school**, choose **Connect**.</span></span>
    
3. <span data-ttu-id="f3b0d-124">Voer uw Microsoft 365 Business Premium-referenties in in het dialoogvenster Een werk- of **schoolaccount** \> **instellen Aanmelden.**</span><span class="sxs-lookup"><span data-stu-id="f3b0d-124">Enter your Microsoft 365 Business Premium credential into the **Set up a work or school account dialog** \> **Sign in**.</span></span>
    
4. <span data-ttu-id="f3b0d-125">Kies op de pagina **Toegang tot werk of school** de optie **Werk- of schoolaccount** en vervolgens **Info**.</span><span class="sxs-lookup"><span data-stu-id="f3b0d-125">On the **Access work or school** page, choose the **Work or school account**, and then choose **Info**.</span></span>
    
    ![Klik of tik op Info in het dialoogvenster Werk- of schoolaccount.](../media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. <span data-ttu-id="f3b0d-127">Op de **werk-** of schoolpagina  van Access kunt u de verbindingsgegevens zien met een Adres van **de beheerserver,** zoals in de volgende afbeelding, en worden de woorden wip *en* *mam* binnen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="f3b0d-127">On the **Access work or school** page, you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure, and includes the words  *wip*  and  *mam*  within.</span></span> 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](../media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 <span data-ttu-id="f3b0d-129">**Controleren of u geen bedrijfsgegevens in een niet-beheerde app kunt plakken**</span><span class="sxs-lookup"><span data-stu-id="f3b0d-129">**Verify that you cannot paste company data in a non-managed app**</span></span>
  
1. <span data-ttu-id="f3b0d-130">Open Outlook 2016 en voeg zo nodig uw Microsoft 365 Business Premium-account toe en meld u aan met uw Microsoft 365 Business Premium-referenties.</span><span class="sxs-lookup"><span data-stu-id="f3b0d-130">Open Outlook 2016 and add your Microsoft 365 Business Premium account if necessary and sign in with your Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="f3b0d-131">Open een e-mail en kopieer er een deel van de inhoud van.</span><span class="sxs-lookup"><span data-stu-id="f3b0d-131">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="f3b0d-132">Open Kladblok en plak het deel hierin.</span><span class="sxs-lookup"><span data-stu-id="f3b0d-132">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="f3b0d-133">U ontvangt een foutmelding dat App geen toegang heeft tot inhoud.</span><span class="sxs-lookup"><span data-stu-id="f3b0d-133">You'll receive an error that states App can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="f3b0d-135">U kunt echter wel dezelfde inhoud in Word 2016 plakken.</span><span class="sxs-lookup"><span data-stu-id="f3b0d-135">You can, however, paste the same content into Word 2016.</span></span>
    

