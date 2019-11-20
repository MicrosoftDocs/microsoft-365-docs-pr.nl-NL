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
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="41230-103">Beveiligingsinstellingen voor apps op Windows 10-pc's valideren</span><span class="sxs-lookup"><span data-stu-id="41230-103">Validate app protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a><span data-ttu-id="41230-104">Controleren of gebruikers geen bedrijfsgegevens kunnen kopiëren naar persoonlijke bestanden op bedrijfsapparaten</span><span class="sxs-lookup"><span data-stu-id="41230-104">Verify that users cannot copy company data to personal files on corporate devices</span></span>

<span data-ttu-id="41230-105">Nadat u [beveiligingsbeleid voor apps hebt ingesteld](protection-settings-for-windows-10-devices.md), kan het enkele uren duren voordat het beleid van kracht wordt op apparaten van gebruikers.</span><span class="sxs-lookup"><span data-stu-id="41230-105">After you [set up app protection policies](protection-settings-for-windows-10-devices.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="41230-106">Als u hebt ingeschakeld de **voorkomen dat gebruikers bedrijfsgegevens naar persoonlijke bestanden kopiëren en hen dwingen om werkbestanden op te slaan in OneDrive voor bedrijven** -instelling voor apparaten die eigendom zijn **van het bedrijf** , u dit controleren op het apparaat van de gebruiker nadat ze verbinding hebben gemaakt met Azure AD en aangemeld.</span><span class="sxs-lookup"><span data-stu-id="41230-106">If you turned **On** the **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** setting for company owned devices, you can check this on the user's device after they've connected to Azure AD and signed in.</span></span> 
  
 <span data-ttu-id="41230-107">**Verbindingsinstellingen controleren**</span><span class="sxs-lookup"><span data-stu-id="41230-107">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="41230-p102">Nadat u zich hebt aangemeld met Microsoft 365 Business-referenties en verbinding maakt met Azure AD (zoals beschreven in [Windows-apparaten instellen voor gebruikers van Microsoft 365 Business](set-up-windows-devices.md)), gaat u naar **Windows-instellingen** \> **Accounts** \> **Toegang tot werk of school**. Kies **Verbonden met Azure AD van \<naam tenant\>** en kies vervolgens **Info**.</span><span class="sxs-lookup"><span data-stu-id="41230-p102">After you sign in with Microsoft 365 Business credentials and connect to Azure AD as described in [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md), go to **Windows Settings** \> **Accounts** \> **Access work or school**. Choose **Connected to \<tenant name\> Azure AD**, and then choose **Info**.</span></span>
    
    ![Click or tap Info on the Connected to Azure AD dialog.](media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. <span data-ttu-id="41230-111">Op de **beheerde door** \<tenantnaam\> pagina, ziet u de **verbindingsgegevens** die een **beheer server-adres** zoals wordt weergegeven in de volgende afbeelding bevat.</span><span class="sxs-lookup"><span data-stu-id="41230-111">On the **Managed by** \<tenant name\> page, you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure.</span></span> 
    
    ![Managed by page shows connection info of the device manager URL.](media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 <span data-ttu-id="41230-113">**Controleren of u bedrijfsgegevens niet in een niet-beheerde app plakken**</span><span class="sxs-lookup"><span data-stu-id="41230-113">**Verify that you cannot paste company data in a non-managed app**</span></span>
  
1. <span data-ttu-id="41230-114">Open Outlook 2016, geïnstalleerd door Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="41230-114">Open Outlook 2016 that was installed by Microsoft 365 Business.</span></span>
    
2. <span data-ttu-id="41230-115">Open een e-mail en kopieer er een deel van de inhoud van.</span><span class="sxs-lookup"><span data-stu-id="41230-115">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="41230-116">Open Kladblok en plak het deel hierin.</span><span class="sxs-lookup"><span data-stu-id="41230-116">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="41230-117">U ontvangt een foutbericht waarin wordt bepaald dat de app geen toegang heeft tot inhoud.</span><span class="sxs-lookup"><span data-stu-id="41230-117">You'll receive an error that states the app can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="41230-119">U kunt echter wel dezelfde inhoud in Word 2016 plakken.</span><span class="sxs-lookup"><span data-stu-id="41230-119">You can, however, paste the same content into Word 2016.</span></span>
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a><span data-ttu-id="41230-120">Controleren of gebruikers geen bedrijfsgegevens kunnen kopiëren naar persoonlijke bestanden op persoonlijke apparaten</span><span class="sxs-lookup"><span data-stu-id="41230-120">Verify that users cannot copy company data to personal files on personal devices</span></span>

 <span data-ttu-id="41230-121">**Verbindingsinstellingen controleren**</span><span class="sxs-lookup"><span data-stu-id="41230-121">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="41230-122">Op uw Windows 10 Personal-apparaat waar u bent aangemeld als een lokale gebruiker, gaat u **naar Windows-instellingen**en klikt of tikt u op **accounts** \> **toegang werk of school**.</span><span class="sxs-lookup"><span data-stu-id="41230-122">On your Windows 10 personal device where you're logged in as a local user, go to **Windows Settings**, and click or tap **Accounts** \> **Access work or school**.</span></span>
    
2. <span data-ttu-id="41230-123">Kies **Verbinden** onder **Toegang tot werk of school**.</span><span class="sxs-lookup"><span data-stu-id="41230-123">Under the **Access work or school**, choose **Connect**.</span></span>
    
3. <span data-ttu-id="41230-124">Voer uw Microsoft 365 Business-referenties in in het dialoogvenster **Een werk- of schoolaccount instellen** \> **Aanmelden**.</span><span class="sxs-lookup"><span data-stu-id="41230-124">Enter your Microsoft 365 Business credential into the **Set up a work or school account dialog** \> **Sign in**.</span></span>
    
4. <span data-ttu-id="41230-125">Kies op de pagina **Toegang tot werk of school** de optie **Werk- of schoolaccount** en vervolgens **Info**.</span><span class="sxs-lookup"><span data-stu-id="41230-125">On the **Access work or school** page, choose the **Work or school account**, and then choose **Info**.</span></span>
    
    ![Klik of tik op info in het dialoogvenster werk of schoolaccount.](media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. <span data-ttu-id="41230-127">Op de pagina **toegang werk of school** ziet u de **verbindingsgegevens** met een adres van de **beheer server** , zoals in de volgende afbeelding wordt weergegeven, en bevat de woorden *OHW* en *mam* binnen.</span><span class="sxs-lookup"><span data-stu-id="41230-127">On the **Access work or school** page, you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure, and includes the words  *wip*  and  *mam*  within.</span></span> 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 <span data-ttu-id="41230-129">**Controleren of u bedrijfsgegevens niet in een niet-beheerde app plakken**</span><span class="sxs-lookup"><span data-stu-id="41230-129">**Verify that you cannot paste company data in a non-managed app**</span></span>
  
1. <span data-ttu-id="41230-130">Open Outlook 2016 en voeg eventueel uw Microsoft 365 Business-account toe en meld u aan met uw Microsoft 365 Business-referenties.</span><span class="sxs-lookup"><span data-stu-id="41230-130">Open Outlook 2016 and add your Microsoft 365 Business account if necessary and sign in with your Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="41230-131">Open een e-mail en kopieer er een deel van de inhoud van.</span><span class="sxs-lookup"><span data-stu-id="41230-131">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="41230-132">Open Kladblok en plak het deel hierin.</span><span class="sxs-lookup"><span data-stu-id="41230-132">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="41230-133">Er wordt een foutbericht weergegeven dat de app geen toegang heeft tot inhoud.</span><span class="sxs-lookup"><span data-stu-id="41230-133">You'll receive an error that states App can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="41230-135">U kunt echter wel dezelfde inhoud in Word 2016 plakken.</span><span class="sxs-lookup"><span data-stu-id="41230-135">You can, however, paste the same content into Word 2016.</span></span>
    

