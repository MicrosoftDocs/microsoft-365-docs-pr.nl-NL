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
ms.openlocfilehash: 577921f7f33eafbbe652dcf825a145d89f1ff556
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42057201"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="fb2e1-103">Beveiligingsinstellingen voor apps op Windows 10-pc's valideren</span><span class="sxs-lookup"><span data-stu-id="fb2e1-103">Validate app protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a><span data-ttu-id="fb2e1-104">Controleren of gebruikers geen bedrijfsgegevens kunnen kopiëren naar persoonlijke bestanden op bedrijfsapparaten</span><span class="sxs-lookup"><span data-stu-id="fb2e1-104">Verify that users cannot copy company data to personal files on corporate devices</span></span>

<span data-ttu-id="fb2e1-105">Nadat u [beveiligingsbeleid voor apps hebt ingesteld](protection-settings-for-windows-10-devices.md), kan het enkele uren duren voordat het beleid van kracht wordt op apparaten van gebruikers.</span><span class="sxs-lookup"><span data-stu-id="fb2e1-105">After you [set up app protection policies](protection-settings-for-windows-10-devices.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="fb2e1-106">Als u **de** instelling Voorkomen dat gebruikers bedrijfsgegevens naar persoonlijke bestanden kopieert inschakelt en **hen dwingt werkbestanden op te slaan in** de instelling OneDrive voor Bedrijven voor apparaten die eigendom zijn van het bedrijf, u dit controleren op het apparaat van de gebruiker nadat ze zijn verbonden met Azure AD en zijn aangemeld.</span><span class="sxs-lookup"><span data-stu-id="fb2e1-106">If you turned **On** the **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** setting for company owned devices, you can check this on the user's device after they've connected to Azure AD and signed in.</span></span> 
  
 <span data-ttu-id="fb2e1-107">**Verbindingsinstellingen controleren**</span><span class="sxs-lookup"><span data-stu-id="fb2e1-107">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="fb2e1-p102">Nadat u zich hebt aangemeld met Microsoft 365 Business-referenties en verbinding maakt met Azure AD (zoals beschreven in [Windows-apparaten instellen voor gebruikers van Microsoft 365 Business](set-up-windows-devices.md)), gaat u naar **Windows-instellingen** \> **Accounts** \> **Toegang tot werk of school**. Kies **Verbonden met Azure AD van \<naam tenant\>** en kies vervolgens **Info**.</span><span class="sxs-lookup"><span data-stu-id="fb2e1-p102">After you sign in with Microsoft 365 Business credentials and connect to Azure AD as described in [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md), go to **Windows Settings** \> **Accounts** \> **Access work or school**. Choose **Connected to \<tenant name\> Azure AD**, and then choose **Info**.</span></span>
    
    ![Click or tap Info on the Connected to Azure AD dialog.](../media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. <span data-ttu-id="fb2e1-111">Op de pagina\> Beheer **door** \<tenant u de **verbindingsgegevens** zien die een **managementserveradres** bevatten, zoals in de volgende afbeelding wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="fb2e1-111">On the **Managed by** \<tenant name\> page, you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure.</span></span> 
    
    ![Managed by page shows connection info of the device manager URL.](../media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 <span data-ttu-id="fb2e1-113">**Controleren of u bedrijfsgegevens niet plakken in een niet-beheerde app**</span><span class="sxs-lookup"><span data-stu-id="fb2e1-113">**Verify that you cannot paste company data in a non-managed app**</span></span>
  
1. <span data-ttu-id="fb2e1-114">Open Outlook 2016, geïnstalleerd door Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="fb2e1-114">Open Outlook 2016 that was installed by Microsoft 365 Business.</span></span>
    
2. <span data-ttu-id="fb2e1-115">Open een e-mail en kopieer er een deel van de inhoud van.</span><span class="sxs-lookup"><span data-stu-id="fb2e1-115">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="fb2e1-116">Open Kladblok en plak het deel hierin.</span><span class="sxs-lookup"><span data-stu-id="fb2e1-116">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="fb2e1-117">U ontvangt een foutmelding dat de app geen toegang heeft tot inhoud.</span><span class="sxs-lookup"><span data-stu-id="fb2e1-117">You'll receive an error that states the app can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="fb2e1-119">U kunt echter wel dezelfde inhoud in Word 2016 plakken.</span><span class="sxs-lookup"><span data-stu-id="fb2e1-119">You can, however, paste the same content into Word 2016.</span></span>
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a><span data-ttu-id="fb2e1-120">Controleren of gebruikers geen bedrijfsgegevens kunnen kopiëren naar persoonlijke bestanden op persoonlijke apparaten</span><span class="sxs-lookup"><span data-stu-id="fb2e1-120">Verify that users cannot copy company data to personal files on personal devices</span></span>

 <span data-ttu-id="fb2e1-121">**Verbindingsinstellingen controleren**</span><span class="sxs-lookup"><span data-stu-id="fb2e1-121">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="fb2e1-122">Ga op uw persoonlijke windows 10-apparaat waar u als lokale gebruiker bent aangemeld naar **Windows-instellingen**en klik of tik op het werk of de school **van Accounts** \> **Toegang.**</span><span class="sxs-lookup"><span data-stu-id="fb2e1-122">On your Windows 10 personal device where you're logged in as a local user, go to **Windows Settings**, and click or tap **Accounts** \> **Access work or school**.</span></span>
    
2. <span data-ttu-id="fb2e1-123">Kies **Verbinden** onder **Toegang tot werk of school**.</span><span class="sxs-lookup"><span data-stu-id="fb2e1-123">Under the **Access work or school**, choose **Connect**.</span></span>
    
3. <span data-ttu-id="fb2e1-124">Voer uw Microsoft 365 Business-referenties in in het dialoogvenster **Een werk- of schoolaccount instellen** \> **Aanmelden**.</span><span class="sxs-lookup"><span data-stu-id="fb2e1-124">Enter your Microsoft 365 Business credential into the **Set up a work or school account dialog** \> **Sign in**.</span></span>
    
4. <span data-ttu-id="fb2e1-125">Kies op de pagina **Toegang tot werk of school** de optie **Werk- of schoolaccount** en vervolgens **Info**.</span><span class="sxs-lookup"><span data-stu-id="fb2e1-125">On the **Access work or school** page, choose the **Work or school account**, and then choose **Info**.</span></span>
    
    ![Klik of tik op Info in het dialoogvenster Werk- of schoolaccount.](../media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. <span data-ttu-id="fb2e1-127">Op de **pagina Werk of school toegang** u de **verbindingsgegevens** zien die een **managementserveradres** bevatten, zoals in de volgende afbeelding, en de woorden *wip* en *mam* binnenin bevat.</span><span class="sxs-lookup"><span data-stu-id="fb2e1-127">On the **Access work or school** page, you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure, and includes the words  *wip*  and  *mam*  within.</span></span> 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](../media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 <span data-ttu-id="fb2e1-129">**Controleren of u bedrijfsgegevens niet plakken in een niet-beheerde app**</span><span class="sxs-lookup"><span data-stu-id="fb2e1-129">**Verify that you cannot paste company data in a non-managed app**</span></span>
  
1. <span data-ttu-id="fb2e1-130">Open Outlook 2016 en voeg eventueel uw Microsoft 365 Business-account toe en meld u aan met uw Microsoft 365 Business-referenties.</span><span class="sxs-lookup"><span data-stu-id="fb2e1-130">Open Outlook 2016 and add your Microsoft 365 Business account if necessary and sign in with your Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="fb2e1-131">Open een e-mail en kopieer er een deel van de inhoud van.</span><span class="sxs-lookup"><span data-stu-id="fb2e1-131">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="fb2e1-132">Open Kladblok en plak het deel hierin.</span><span class="sxs-lookup"><span data-stu-id="fb2e1-132">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="fb2e1-133">U ontvangt een foutmelding dat App geen toegang heeft tot inhoud.</span><span class="sxs-lookup"><span data-stu-id="fb2e1-133">You'll receive an error that states App can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="fb2e1-135">U kunt echter wel dezelfde inhoud in Word 2016 plakken.</span><span class="sxs-lookup"><span data-stu-id="fb2e1-135">You can, however, paste the same content into Word 2016.</span></span>
    

