---
title: DNS-records maken bij Register.com voor Microsoft
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55bd8c38-3316-48ae-a368-4959b2c1684e
description: Meer informatie over het verifiëren van uw domein en het instellen van DNS-records voor e-mail, Skype voor Bedrijven Online en andere services bij Register.com voor Microsoft.
ms.openlocfilehash: 7a11fa248f2602eb02fe1242234d26584bd33fd2
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780323"
---
# <a name="create-dns-records-at-registercom-for-microsoft"></a><span data-ttu-id="9e6f9-103">DNS-records maken bij Register.com voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="9e6f9-103">Create DNS records at Register.com for Microsoft</span></span>

 <span data-ttu-id="9e6f9-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="9e6f9-105">Als Register.com uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-105">If Register.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="9e6f9-106">Dit zijn de belangrijkste records om toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-106">These are the main records to add.</span></span> <span data-ttu-id="9e6f9-107">Volg onderstaande stappen of [bekijk de video](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="9e6f9-107">Follow the steps below or [watch the video](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
- [<span data-ttu-id="9e6f9-108">Een TXT-record toevoegen op Register.com om te bevestigen dat u eigenaar van het domein bent</span><span class="sxs-lookup"><span data-stu-id="9e6f9-108">Add a TXT record at Register.com to verify that you own the domain</span></span>](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [<span data-ttu-id="9e6f9-109">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="9e6f9-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="9e6f9-110">De CNAME-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="9e6f9-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="9e6f9-111">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="9e6f9-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [<span data-ttu-id="9e6f9-112">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="9e6f9-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="9e6f9-113">Nadat u deze records hebt toegevoegd op Register.com, wordt uw domein ingesteld om te werken met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-113">After you add these records at Register.com, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="9e6f9-114">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-114">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="9e6f9-115">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-115">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="9e6f9-116">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9e6f9-116">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a><span data-ttu-id="9e6f9-117">Een TXT-record toevoegen op Register.com om te bevestigen dat u eigenaar van het domein bent</span><span class="sxs-lookup"><span data-stu-id="9e6f9-117">Add a TXT record at Register.com to verify that you own the domain</span></span>
<span data-ttu-id="9e6f9-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="9e6f9-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="9e6f9-119">Before you use your domain with Microsoft, we have to make sure that you own it.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-119">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="9e6f9-120">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-120">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9e6f9-121">This record is used only to verify that you own your domain; it doesn't affect anything else.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-121">This record is used only to verify that you own your domain; it doesn't affect anything else.</span></span> <span data-ttu-id="9e6f9-122">You can delete it later, if you like.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-122">You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="9e6f9-123">Volg onderstaande stappen of [bekijk de video (start op 0:44)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="9e6f9-123">Follow the steps below or [watch the video (start at 0:44)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="9e6f9-124">Als u wilt beginnen, gaat u [via deze koppeling](https://www.register.com/myaccount/) naar uw pagina met domeinen bij Register.com.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-124">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="9e6f9-125">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-125">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="9e6f9-126">Selecteer **Domeinen**.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-126">Select **Domains**.</span></span>
    
3. <span data-ttu-id="9e6f9-127">Selecteer **Beheren**.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-127">Select **Manage**.</span></span>
    
4. <span data-ttu-id="9e6f9-128">Zoek de rij met de naam van het domein dat u wilt wijzigen. en selecteer vervolgens in die rij **Beheren**.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-128">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="9e6f9-129">Schuif omlaag naar de sectie **Geavanceerde technische instellingen** en selecteer **TXT-records bewerken (SPF)**.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-129">Scroll down to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
6. <span data-ttu-id="9e6f9-130">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-130">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="9e6f9-131">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="9e6f9-131">**Host Name**</span></span> <br/> |<span data-ttu-id="9e6f9-132">**TXT Record**</span><span class="sxs-lookup"><span data-stu-id="9e6f9-132">**TXT Record**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="9e6f9-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="9e6f9-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="9e6f9-134">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-134">**Note:** This is an example.</span></span> <span data-ttu-id="9e6f9-135">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-135">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="9e6f9-136">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="9e6f9-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="9e6f9-137">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-137">Select **Continue**.</span></span>
    
8. <span data-ttu-id="9e6f9-138">Selecteer op de volgende pagina **Opnieuw Doorgaan** om uw wijzigingen te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-138">On the next page, select **Continue** again to confirm your changes.</span></span> 
    
9. <span data-ttu-id="9e6f9-139">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="9e6f9-140">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="9e6f9-141">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="9e6f9-142">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="9e6f9-143">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="9e6f9-144">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-144">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="9e6f9-145">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-145">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9e6f9-146">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-146">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="9e6f9-147">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-147">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="9e6f9-148">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9e6f9-148">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="9e6f9-149">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="9e6f9-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="9e6f9-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="9e6f9-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="9e6f9-151">Volg onderstaande stappen of [bekijk de video (start op 3:32)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="9e6f9-151">Follow the steps below or [watch the video (start at 3:32)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="9e6f9-152">Als u wilt beginnen, gaat u [via deze koppeling](https://www.register.com/myaccount/) naar uw pagina met domeinen bij Register.com.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-152">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="9e6f9-153">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-153">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="9e6f9-154">Selecteer **Domeinen**.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-154">Select **Domains**.</span></span>
    
3. <span data-ttu-id="9e6f9-155">Selecteer **Beheren**.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-155">Select **Manage**.</span></span>
    
4. <span data-ttu-id="9e6f9-156">Zoek de rij met de naam van het domein dat u wilt wijzigen. en selecteer vervolgens in die rij **Beheren**.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-156">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="9e6f9-157">Schuif naar de sectie **Geavanceerde technische instellingen** en selecteer **E-mailuitwisselingsrecords bewerken**.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-157">Scroll to the **Advanced Technical Settings** section, and then select **Edit Mail Exchanger Records**.</span></span>
    
    ![E-mail exchanger records bewerken selecteren](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. <span data-ttu-id="9e6f9-159">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="9e6f9-160">(Kies de **prioriteitswaarde** in de vervolgkeuzelijst.)</span><span class="sxs-lookup"><span data-stu-id="9e6f9-160">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="9e6f9-161">\*\*\*\*Hostnaam\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="9e6f9-161">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="9e6f9-162">\*\*\*\*Priority\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="9e6f9-162">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="9e6f9-163">\*\*\*\*Mail Server\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="9e6f9-163">\*\*\*\*Mail Server\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="9e6f9-164">High</span><span class="sxs-lookup"><span data-stu-id="9e6f9-164">High</span></span>  <br/> <span data-ttu-id="9e6f9-165">Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="9e6f9-165">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="9e6f9-166">*\<domain-key\>*,,Mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9e6f9-166">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <br/><span data-ttu-id="9e6f9-167">**Let op:** Haal je \<*domain-key*\> van je Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-167">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> <br> [<span data-ttu-id="9e6f9-168">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="9e6f9-168">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![De waarde uit de tabel kopiëren en plakken](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. <span data-ttu-id="9e6f9-170">Als er al andere MX-records staan vermeld, selecteert u elk van deze records om ze te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-170">If there were any other MX records already listed, select each of those records to be deleted.</span></span>
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. <span data-ttu-id="9e6f9-172">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-172">Select **Continue**.</span></span>
    
    ![Selecteer Doorgaan](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. <span data-ttu-id="9e6f9-174">Selecteer op de volgende pagina **Opnieuw Doorgaan** om de wijzigingen te bevestigen en op te slaan.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-174">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Selecteer Doorgaan](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="9e6f9-176">De CNAME-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="9e6f9-176">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="9e6f9-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="9e6f9-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="9e6f9-178">Volg onderstaande stappen of [bekijk de video (start op 4:23)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="9e6f9-178">Follow the steps below or [watch the video (start at 4:23)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="9e6f9-179">Als u wilt beginnen, gaat u [via deze koppeling](https://www.register.com/myaccount/) naar uw pagina met domeinen bij Register.com.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-179">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="9e6f9-180">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-180">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="9e6f9-181">Selecteer **Domeinen**.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-181">Select **Domains**.</span></span>
    
3. <span data-ttu-id="9e6f9-182">Selecteer **Beheren**.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-182">Select **Manage**.</span></span>
    
4. <span data-ttu-id="9e6f9-183">Zoek de rij met de naam van het domein dat u wilt wijzigen. en selecteer vervolgens in die rij **Beheren**.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-183">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="9e6f9-184">Schuif naar de sectie **Geavanceerde technische instellingen** en selecteer **Domeinaliassenrecords bewerken**.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-184">Scroll to the **Advanced Technical Settings** section, and then select **Edit Domain Aliases Records**.</span></span>
    
    ![Records domeinaliassen bewerken selecteren](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. <span data-ttu-id="9e6f9-186">Selecteer **Meer domeinaliassen toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-186">Select **Add more domain aliases**.</span></span>
    
    ![Selecteer Meer domeinen aliassen toevoegen](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. <span data-ttu-id="9e6f9-188">De vereiste CNAME-records toevoegen.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-188">Add the required CNAME records.</span></span>
    
    <span data-ttu-id="9e6f9-189">Typ of kopieer en plak de waarden uit de eerste rij in de volgende tabel in de velden voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-189">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="9e6f9-190">\*\*\*\*Eerste veld (zonder label)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="9e6f9-190">\*\*\*\*First field (unlabeled)\*\*\*\*</span></span>|<span data-ttu-id="9e6f9-191">\*\*\*\*Verwijst naar\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="9e6f9-191">\*\*\*\*Points to\*\*\*\*</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="9e6f9-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="9e6f9-192">autodiscover</span></span>  <br/> |<span data-ttu-id="9e6f9-193">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9e6f9-193">autodiscover.outlook.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="9e6f9-194">sip</span><span class="sxs-lookup"><span data-stu-id="9e6f9-194">sip</span></span>  <br/> |<span data-ttu-id="9e6f9-195">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9e6f9-195">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="9e6f9-196">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="9e6f9-196">lyncdiscover</span></span>  <br/> |<span data-ttu-id="9e6f9-197">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9e6f9-197">webdir.online.lync.com</span></span> <br/>  <br/> |
    |<span data-ttu-id="9e6f9-198">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="9e6f9-198">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="9e6f9-199">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="9e6f9-199">enterpriseregistration.windows.net</span></span>  <br/>  <br/> |
    |<span data-ttu-id="9e6f9-200">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="9e6f9-200">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="9e6f9-201">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9e6f9-201">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/>  <br/> |
   
     ![De DNS-waarden uit de tabel kopiëren en plakken](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. <span data-ttu-id="9e6f9-203">Wanneer u alle CNAME-records hebt toegevoegd die u nodig hebt, selecteert u **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-203">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Selecteer Doorgaan](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. <span data-ttu-id="9e6f9-205">Selecteer op de volgende pagina **Opnieuw Doorgaan** om de wijzigingen te bevestigen en op te slaan.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-205">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Selecteer Doorgaan](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="9e6f9-207">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="9e6f9-207">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="9e6f9-208"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="9e6f9-208"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e6f9-209">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-209">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="9e6f9-210">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-210">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="9e6f9-211">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-211">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="9e6f9-212">In plaats hiervan voegt u de vereiste Microsoft-waarden toe aan de huidige record, zodat u beschikt over één SPF-record waarin beide sets waarden zijn opgenomen.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-212">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span>  
  
<span data-ttu-id="9e6f9-213">Volg onderstaande stappen of [bekijk de video (start op 5:12)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="9e6f9-213">Follow the steps below or [watch the video (start at 5:12)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="9e6f9-214">Als u wilt beginnen, gaat u [via deze koppeling](https://www.register.com/myaccount/) naar uw pagina met domeinen bij Register.com.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-214">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="9e6f9-215">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-215">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="9e6f9-216">Selecteer **Domeinen**.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-216">Select **Domains**.</span></span>
    
3. <span data-ttu-id="9e6f9-217">Selecteer **Beheren**.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-217">Select **Manage**.</span></span>
    
4. <span data-ttu-id="9e6f9-218">Zoek de rij met de naam van het domein dat u wilt wijzigen. en selecteer vervolgens in die rij **Beheren**.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-218">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="9e6f9-219">Schuif naar de sectie **Geavanceerde technische instellingen** en selecteer **TXT-records bewerken (SPF)**.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-219">Scroll to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
    ![Selecteer TXT-records bewerken (SPF)](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. <span data-ttu-id="9e6f9-221">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-221">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="9e6f9-222">\*\*\*\*Host Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="9e6f9-222">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="9e6f9-223">\*\*\*\*TXT Record\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="9e6f9-223">\*\*\*\*TXT Record\*\*\*\*</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="9e6f9-224">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="9e6f9-224">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="9e6f9-225">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-225">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>  |
   
     ![De waarden uit de tabel kopiëren en plakken](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. <span data-ttu-id="9e6f9-227">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-227">Select **Continue**.</span></span>
    
    ![Selecteer Doorgaan](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. <span data-ttu-id="9e6f9-229">Selecteer op de volgende pagina **Opnieuw Doorgaan** om de wijzigingen te bevestigen en op te slaan.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-229">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Selecteer Doorgaan](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="9e6f9-231">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="9e6f9-231">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="9e6f9-232"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="9e6f9-232"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="9e6f9-233">Volg onderstaande stappen of [bekijk de video (start op 5:55)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="9e6f9-233">Follow the steps below or [watch the video (start at 5:55)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="9e6f9-234">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="9e6f9-234">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="9e6f9-235">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-235">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="9e6f9-236">Selecteer **Domeinen**.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-236">Select **Domains**.</span></span>
    
3. <span data-ttu-id="9e6f9-237">Selecteer **Beheren**.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-237">Select **Manage**.</span></span>
    
4. <span data-ttu-id="9e6f9-238">Zoek de rij met de naam van het domein dat u wilt wijzigen. en selecteer vervolgens in die rij **Beheren**.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-238">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="9e6f9-239">Schuif naar de sectie **Geavanceerde technische instellingen** en selecteer **SRV-records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-239">Scroll to the **Advanced Technical Settings** section, and then select **Edit SRV Records**.</span></span>
    
    ![SRV-records bewerken selecteren](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. <span data-ttu-id="9e6f9-241">Voeg als volgt de eerste van de twee SRV-records toe:</span><span class="sxs-lookup"><span data-stu-id="9e6f9-241">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="9e6f9-242">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-242">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="9e6f9-243">(Kies de **prioriteitswaarde** in de vervolgkeuzelijst.)</span><span class="sxs-lookup"><span data-stu-id="9e6f9-243">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="9e6f9-244">\*\*\*\*Service\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="9e6f9-244">\*\*\*\*Service\*\*\*\*</span></span>|<span data-ttu-id="9e6f9-245">\*\*\*\*Proto\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="9e6f9-245">\*\*\*\*Proto\*\*\*\*</span></span>|<span data-ttu-id="9e6f9-246">\*\*\*\*Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="9e6f9-246">\*\*\*\*Name\*\*\*\*</span></span>|<span data-ttu-id="9e6f9-247">\*\*\*\*Priority\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="9e6f9-247">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="9e6f9-248">\*\*\*\*Gewicht\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="9e6f9-248">\*\*\*\*Weight\*\*\*\*</span></span>|<span data-ttu-id="9e6f9-249">\*\*\*\*Port\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="9e6f9-249">\*\*\*\*Port\*\*\*\*</span></span>|<span data-ttu-id="9e6f9-250">\*\*\*\*Target\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="9e6f9-250">\*\*\*\*Target\*\*\*\*</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9e6f9-251">_sip</span><span class="sxs-lookup"><span data-stu-id="9e6f9-251">_sip</span></span>  <br/> |<span data-ttu-id="9e6f9-252">_tls</span><span class="sxs-lookup"><span data-stu-id="9e6f9-252">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="9e6f9-253">High</span><span class="sxs-lookup"><span data-stu-id="9e6f9-253">High</span></span>  <br/> |<span data-ttu-id="9e6f9-254">1</span><span class="sxs-lookup"><span data-stu-id="9e6f9-254">1</span></span>  <br/> |<span data-ttu-id="9e6f9-255">443</span><span class="sxs-lookup"><span data-stu-id="9e6f9-255">443</span></span>  <br/> |<span data-ttu-id="9e6f9-256">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9e6f9-256">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="9e6f9-257">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="9e6f9-257">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="9e6f9-258">_tcp</span><span class="sxs-lookup"><span data-stu-id="9e6f9-258">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="9e6f9-259">High</span><span class="sxs-lookup"><span data-stu-id="9e6f9-259">High</span></span>  <br/> |<span data-ttu-id="9e6f9-260">1</span><span class="sxs-lookup"><span data-stu-id="9e6f9-260">1</span></span>  <br/> |<span data-ttu-id="9e6f9-261">5061</span><span class="sxs-lookup"><span data-stu-id="9e6f9-261">5061</span></span>  <br/> |<span data-ttu-id="9e6f9-262">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9e6f9-262">sipfed.online.lync.com</span></span>  <br/>  <br/> |
   
    ![De waarden uit de tabel kopiëren en plakken](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. <span data-ttu-id="9e6f9-264">Selecteer **Meer SRV-records toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-264">Select **Add more SRV records**.</span></span>
    
    ![Selecteer Meer SRV-records toevoegen](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. <span data-ttu-id="9e6f9-266">Voeg als volgt de tweede SRV-record toe:</span><span class="sxs-lookup"><span data-stu-id="9e6f9-266">Add the second SRV record:</span></span>
    
    <span data-ttu-id="9e6f9-267">Typ of kopieer en plak de waarden uit de tweede rij van de bovenstaande tabel in de velden van de tweede record.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-267">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
9. <span data-ttu-id="9e6f9-268">Wanneer u beide SRV-records hebt toegevoegd, selecteert u **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-268">When you have added both of the SRV records, select **Continue**.</span></span>
    
    ![Selecteer Doorgaan](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. <span data-ttu-id="9e6f9-270">Selecteer op de volgende pagina **Opnieuw Doorgaan** om de wijzigingen te bevestigen en op te slaan.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-270">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Selecteer Doorgaan](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> <span data-ttu-id="9e6f9-272">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-272">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="9e6f9-273">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="9e6f9-273">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="9e6f9-274">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9e6f9-274">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
