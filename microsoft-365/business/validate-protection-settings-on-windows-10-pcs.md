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
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="720ab-103">Beveiligingsinstellingen voor apps op Windows 10-pc's valideren</span><span class="sxs-lookup"><span data-stu-id="720ab-103">Validate app protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a><span data-ttu-id="720ab-104">Controleren of gebruikers geen bedrijfsgegevens kunnen kopiëren naar persoonlijke bestanden op bedrijfsapparaten</span><span class="sxs-lookup"><span data-stu-id="720ab-104">Verify that users cannot copy company data to personal files on corporate devices</span></span>

<span data-ttu-id="720ab-p101">Nadat u [beveiligingsbeleid voor apps hebt ingesteld](protection-settings-for-windows-10-devices.md), kan het enkele uren duren voordat het beleid van kracht wordt op apparaten van gebruikers. Als u de instelling **Voorkomen dat gebruikers bedrijfsgegevens kopiëren naar persoonlijke bestanden en afdwingen dat werkbestanden worden opgeslagen in OneDrive voor Bedrijven** hebt **ingeschakeld** op apparaten die eigendom zijn van het bedrijf, kunt u dit controleren op het apparaat van de gebruiker nadat deze verbinding heeft gemaakt met Azure AD en zich heeft aangemeld.</span><span class="sxs-lookup"><span data-stu-id="720ab-p101">After you [set up app protection policies](protection-settings-for-windows-10-devices.md), it may take up to a few hours for the policy to take effect on users' devices. If you turned **On** the **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** setting for company owned devices, you can check this on the user's device after they have connected to Azure AD and signed in.</span></span> 
  
 <span data-ttu-id="720ab-107">**Verbindingsinstellingen controleren**</span><span class="sxs-lookup"><span data-stu-id="720ab-107">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="720ab-p102">Nadat u zich hebt aangemeld met Microsoft 365 Business-referenties en verbinding maakt met Azure AD (zoals beschreven in [Windows-apparaten instellen voor gebruikers van Microsoft 365 Business](set-up-windows-devices.md)), gaat u naar **Windows-instellingen** \> **Accounts** \> **Toegang tot werk of school**. Kies **Verbonden met Azure AD van \<naam tenant\>** en kies vervolgens **Info**.</span><span class="sxs-lookup"><span data-stu-id="720ab-p102">After you sign in with Microsoft 365 Business credentials and connect to Azure AD as described in [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md), go to **Windows Settings** \> **Accounts** \> **Access work or school**. Choose **Connected to \<tenant name\> Azure AD**, and then choose **Info**.</span></span>
    
    ![Click or tap Info on the Connected to Azure AD dialog.](media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. <span data-ttu-id="720ab-111">Op de pagina **Beheerd door** \<naam tenant\> kunt u de **verbindingsgegevens** zien met een **adres van een beheerserver**, zoals in de volgende afbeelding.</span><span class="sxs-lookup"><span data-stu-id="720ab-111">On the **Managed by** \<tenant name\> page you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure.</span></span> 
    
    ![Managed by page shows connection info of the device manager URL.](media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 <span data-ttu-id="720ab-113">**Controleren of u geen bedrijfsgegeven kunt plakken naar een niet-beheerde app**</span><span class="sxs-lookup"><span data-stu-id="720ab-113">**Verify that you cannot paste company data to a non-managed app**</span></span>
  
1. <span data-ttu-id="720ab-114">Open Outlook 2016, geïnstalleerd door Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="720ab-114">Open Outlook 2016 that was installed by Microsoft 365 Business.</span></span>
    
2. <span data-ttu-id="720ab-115">Open een e-mail en kopieer er een deel van de inhoud van.</span><span class="sxs-lookup"><span data-stu-id="720ab-115">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="720ab-116">Open Kladblok en plak het deel hierin.</span><span class="sxs-lookup"><span data-stu-id="720ab-116">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="720ab-117">U krijgt een foutmelding met de mededeling dat de app geen toegang heeft tot inhoud.</span><span class="sxs-lookup"><span data-stu-id="720ab-117">You will receive an error that states App can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="720ab-119">U kunt echter wel dezelfde inhoud in Word 2016 plakken.</span><span class="sxs-lookup"><span data-stu-id="720ab-119">You can, however, paste the same content into Word 2016.</span></span>
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a><span data-ttu-id="720ab-120">Controleren of gebruikers geen bedrijfsgegevens kunnen kopiëren naar persoonlijke bestanden op persoonlijke apparaten</span><span class="sxs-lookup"><span data-stu-id="720ab-120">Verify that users cannot copy company data to personal files on personal devices</span></span>

 <span data-ttu-id="720ab-121">**Verbindingsinstellingen controleren**</span><span class="sxs-lookup"><span data-stu-id="720ab-121">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="720ab-122">Ga op uw persoonlijke Windows 10-apparaat, waarop u als lokale gebruiker bent aangemeld, naar **Windows-instellingen** en klik of tik op **Accounts** \> **Toegang tot werk of school**.</span><span class="sxs-lookup"><span data-stu-id="720ab-122">On your Windows 10 personal device where you are logged in as a local user, go to **Windows Settings** and click or tap **Accounts** \> **Access work or school**.</span></span>
    
2. <span data-ttu-id="720ab-123">Kies **Verbinden** onder **Toegang tot werk of school**.</span><span class="sxs-lookup"><span data-stu-id="720ab-123">Under the **Access work or school**, choose **Connect**.</span></span>
    
3. <span data-ttu-id="720ab-124">Voer uw Microsoft 365 Business-referenties in in het dialoogvenster **Een werk- of schoolaccount instellen** \> **Aanmelden**.</span><span class="sxs-lookup"><span data-stu-id="720ab-124">Enter your Microsoft 365 Business credential into the **Set up a work or school account dialog** \> **Sign in**.</span></span>
    
4. <span data-ttu-id="720ab-125">Kies op de pagina **Toegang tot werk of school** de optie **Werk- of schoolaccount** en vervolgens **Info**.</span><span class="sxs-lookup"><span data-stu-id="720ab-125">On the **Access work or school** page, choose the **Work or school account**, and then choose **Info**.</span></span>
    
    ![Click or tap Info on the Work or school account dalog.](media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. <span data-ttu-id="720ab-127">Op de pagina **Toegang tot werk of school** ziet u de **verbindingsgegevens** met het **adres van de beheerserver**, zoals in de volgende afbeelding. Dit adres bevat de woorden  *wip*  en  *mam*  .</span><span class="sxs-lookup"><span data-stu-id="720ab-127">On the **Access work or school** page you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure, and includes the words  *wip*  and  *mam*  within.</span></span> 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 <span data-ttu-id="720ab-129">**Controleren of u geen bedrijfsgegeven kunt plakken naar een niet-beheerde app**</span><span class="sxs-lookup"><span data-stu-id="720ab-129">**Verify that you cannot paste company data to a non-managed app**</span></span>
  
1. <span data-ttu-id="720ab-130">Open Outlook 2016 en voeg eventueel uw Microsoft 365 Business-account toe en meld u aan met uw Microsoft 365 Business-referenties.</span><span class="sxs-lookup"><span data-stu-id="720ab-130">Open Outlook 2016 and add your Microsoft 365 Business account if necessary and sign in with your Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="720ab-131">Open een e-mail en kopieer er een deel van de inhoud van.</span><span class="sxs-lookup"><span data-stu-id="720ab-131">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="720ab-132">Open Kladblok en plak het deel hierin.</span><span class="sxs-lookup"><span data-stu-id="720ab-132">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="720ab-133">U krijgt een foutmelding met de mededeling dat de app geen toegang heeft tot inhoud.</span><span class="sxs-lookup"><span data-stu-id="720ab-133">You will receive an error that states App can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="720ab-135">U kunt echter wel dezelfde inhoud in Word 2016 plakken.</span><span class="sxs-lookup"><span data-stu-id="720ab-135">You can, however, paste the same content into Word 2016.</span></span>
    

