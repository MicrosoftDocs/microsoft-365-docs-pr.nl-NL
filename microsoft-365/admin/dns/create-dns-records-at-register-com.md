---
title: DNS-records bij Register.com maken voor Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55bd8c38-3316-48ae-a368-4959b2c1684e
description: Lees uw domein en stel DNS-records in voor e-mail, Skype voor Bedrijven Online en andere services op Register.com voor Office 365.
ms.openlocfilehash: 0210c03a48112d9cc517ae15f879db3b40eb8c94
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "42808882"
---
# <a name="create-dns-records-at-registercom-for-office-365"></a><span data-ttu-id="0c4f4-103">DNS-records bij Register.com maken voor Office 365</span><span class="sxs-lookup"><span data-stu-id="0c4f4-103">Create DNS records at Register.com for Office 365</span></span>

 <span data-ttu-id="0c4f4-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="0c4f4-105">Als Register.com uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-105">If Register.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="0c4f4-106">Dit zijn de belangrijkste records om toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-106">These are the main records to add.</span></span> <span data-ttu-id="0c4f4-107">Volg onderstaande stappen of [bekijk de video](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="0c4f4-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
- [<span data-ttu-id="0c4f4-108">Een TXT-record toevoegen op Register.com om te bevestigen dat u eigenaar van het domein bent</span><span class="sxs-lookup"><span data-stu-id="0c4f4-108">Add a TXT record at Register.com to verify that you own the domain</span></span>](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [<span data-ttu-id="0c4f4-109">Voeg een MX-record toe zodat e-mail voor uw domein bij Office 365 terechtkomt</span><span class="sxs-lookup"><span data-stu-id="0c4f4-109">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="0c4f4-110">De CNAME-records toevoegen die voor Office 365 vereist zijn</span><span class="sxs-lookup"><span data-stu-id="0c4f4-110">Add the CNAME records that are required for Office 365</span></span>](#add-the-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="0c4f4-111">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="0c4f4-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [<span data-ttu-id="0c4f4-112">Voeg de vier SRV-records toe die voor Office 365 vereist zijn.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-112">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="0c4f4-113">Nadat u deze records bij Register.com hebt toegevoegd, is uw domein ingesteld voor gebruik met Office 365-services.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-113">After you add these records at Register.com, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="0c4f4-114">Zie [Een openbare website gebruiken met Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9) voor informatie over webhosting en DNS voor websites met Office 365.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-114">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="0c4f4-p102">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0c4f4-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a><span data-ttu-id="0c4f4-118">Een TXT-record toevoegen op Register.com om te bevestigen dat u eigenaar van het domein bent</span><span class="sxs-lookup"><span data-stu-id="0c4f4-118">Add a TXT record at Register.com to verify that you own the domain</span></span>
<span data-ttu-id="0c4f4-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="0c4f4-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="0c4f4-p103">Voordat u uw domein met Office 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Office 365 bewezen.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0c4f4-p104">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="0c4f4-124">Volg onderstaande stappen of [bekijk de video (start op 0:44)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="0c4f4-124">Follow the steps below or [watch the video (start at 0:44)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="0c4f4-125">Als u wilt beginnen, gaat u [via deze koppeling](https://www.register.com/myaccount/) naar uw pagina met domeinen bij Register.com.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-125">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="0c4f4-126">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-126">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="0c4f4-127">Selecteer **Domeinen**.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-127">Select **Domains**.</span></span>
    
3. <span data-ttu-id="0c4f4-128">Selecteer **Beheren**.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-128">Select **Manage**.</span></span>
    
4. <span data-ttu-id="0c4f4-129">Zoek de rij met de naam van het domein dat u wilt wijzigen. en selecteer vervolgens in die rij **Beheren**.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-129">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="0c4f4-130">Schuif omlaag naar de sectie **Geavanceerde technische instellingen** en selecteer Vervolgens **TXT Records (SPF) bewerken.**</span><span class="sxs-lookup"><span data-stu-id="0c4f4-130">Scroll down to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
6. <span data-ttu-id="0c4f4-131">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="0c4f4-132">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="0c4f4-132">**Host Name**</span></span> <br/> |<span data-ttu-id="0c4f4-133">**TXT Record**</span><span class="sxs-lookup"><span data-stu-id="0c4f4-133">**TXT Record**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="0c4f4-134">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="0c4f4-134">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="0c4f4-135">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-135">**Note:** This is an example.</span></span> <span data-ttu-id="0c4f4-136">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-136">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="0c4f4-137">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="0c4f4-137">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="0c4f4-138">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-138">Select **Continue**.</span></span>
    
8. <span data-ttu-id="0c4f4-139">Selecteer op de volgende pagina **opnieuw doorgaan** om uw wijzigingen te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-139">On the next page, select **Continue** again to confirm your changes.</span></span> 
    
9. <span data-ttu-id="0c4f4-140">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="0c4f4-141">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Office 365 en vraagt u of Office 365 naar de record wil zoeken.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="0c4f4-142">Wanneer in Office 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="0c4f4-143">Ga in het beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Instellingendomeinen.</a> **Settings**</span><span class="sxs-lookup"><span data-stu-id="0c4f4-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="0c4f4-144">Selecteer **op** de pagina Domeinen het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="0c4f4-145">Selecteer **op** de pagina Setup de optie **Installatie starten**.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-145">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="0c4f4-146">Selecteer **op** de pagina Domein verifiëren de optie **Verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-146">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0c4f4-p107">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0c4f4-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="0c4f4-150">Een MX-record toevoegen zodat e-mail voor uw domein bij Office 365 terechtkomt</span><span class="sxs-lookup"><span data-stu-id="0c4f4-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="0c4f4-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="0c4f4-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="0c4f4-152">Volg onderstaande stappen of [bekijk de video (start op 3:32)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="0c4f4-152">Follow the steps below or [watch the video (start at 3:32)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="0c4f4-153">Als u wilt beginnen, gaat u [via deze koppeling](https://www.register.com/myaccount/) naar uw pagina met domeinen bij Register.com.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-153">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="0c4f4-154">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-154">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="0c4f4-155">Selecteer **Domeinen**.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-155">Select **Domains**.</span></span>
    
3. <span data-ttu-id="0c4f4-156">Selecteer **Beheren**.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-156">Select **Manage**.</span></span>
    
4. <span data-ttu-id="0c4f4-157">Zoek de rij met de naam van het domein dat u wilt wijzigen. en selecteer vervolgens in die rij **Beheren**.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-157">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="0c4f4-158">Schuif naar de sectie **Geavanceerde technische instellingen** en selecteer Vervolgens Records voor Mail **Exchanger bewerken**.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-158">Scroll to the **Advanced Technical Settings** section, and then select **Edit Mail Exchanger Records**.</span></span>
    
    ![Selecteer Records voor Mail Exchanger bewerken](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. <span data-ttu-id="0c4f4-160">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-160">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="0c4f4-161">(Kies de **waarde Prioriteit** in de vervolgkeuzelijst.)</span><span class="sxs-lookup"><span data-stu-id="0c4f4-161">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="0c4f4-162">\*\*\*\*Hostnaam\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="0c4f4-162">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="0c4f4-163">\*\*\*\*Priority\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="0c4f4-163">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="0c4f4-164">\*\*\*\*Mail Server\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="0c4f4-164">\*\*\*\*Mail Server\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="0c4f4-165">High</span><span class="sxs-lookup"><span data-stu-id="0c4f4-165">High</span></span>  <br/> <span data-ttu-id="0c4f4-166">Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="0c4f4-166">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="0c4f4-167">*\<domeinsleutel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="0c4f4-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <br/><span data-ttu-id="0c4f4-168">**Let op:** Haal \<uw domeinsleutel\> op uit uw Office 365-account. *domain-key*</span><span class="sxs-lookup"><span data-stu-id="0c4f4-168">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span> <br> [<span data-ttu-id="0c4f4-169">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="0c4f4-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![De waarde uit de tabel kopiëren en plakken](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. <span data-ttu-id="0c4f4-171">Als er al andere MX-records staan vermeld, selecteert u elk van deze records om ze te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-171">If there were any other MX records already listed, select each of those records to be deleted.</span></span>
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. <span data-ttu-id="0c4f4-173">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-173">Select **Continue**.</span></span>
    
    ![Selecteer Doorgaan](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. <span data-ttu-id="0c4f4-175">Selecteer op de volgende pagina **Opnieuw doorgaan** om uw wijzigingen te bevestigen en op te slaan.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-175">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Selecteer Doorgaan](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="0c4f4-177">De CNAME-records toevoegen die voor Office 365 vereist zijn</span><span class="sxs-lookup"><span data-stu-id="0c4f4-177">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="0c4f4-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="0c4f4-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="0c4f4-179">Volg onderstaande stappen of [bekijk de video (start op 4:23)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="0c4f4-179">Follow the steps below or [watch the video (start at 4:23)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="0c4f4-180">Als u wilt beginnen, gaat u [via deze koppeling](https://www.register.com/myaccount/) naar uw pagina met domeinen bij Register.com.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-180">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="0c4f4-181">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-181">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="0c4f4-182">Selecteer **Domeinen**.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-182">Select **Domains**.</span></span>
    
3. <span data-ttu-id="0c4f4-183">Selecteer **Beheren**.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-183">Select **Manage**.</span></span>
    
4. <span data-ttu-id="0c4f4-184">Zoek de rij met de naam van het domein dat u wilt wijzigen. en selecteer vervolgens in die rij **Beheren**.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-184">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="0c4f4-185">Schuif naar de sectie **Geavanceerde technische instellingen** en selecteer Vervolgens **Domeinaliasrecords bewerken**.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-185">Scroll to the **Advanced Technical Settings** section, and then select **Edit Domain Aliases Records**.</span></span>
    
    ![Domeinaliasrecords bewerken selecteren](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. <span data-ttu-id="0c4f4-187">Selecteer **Meer domeinaliassen toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-187">Select **Add more domain aliases**.</span></span>
    
    ![Meer domeinenaliassen toevoegen selecteren](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. <span data-ttu-id="0c4f4-189">De vereiste CNAME-records toevoegen.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-189">Add the required CNAME records.</span></span>
    
    <span data-ttu-id="0c4f4-190">Typ of kopieer en plak de waarden uit de eerste rij in de volgende tabel in de velden voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-190">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="0c4f4-191">\*\*\*\*Eerste veld (zonder label)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="0c4f4-191">\*\*\*\*First field (unlabeled)\*\*\*\*</span></span>|<span data-ttu-id="0c4f4-192">\*\*\*\*Verwijst naar\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="0c4f4-192">\*\*\*\*Points to\*\*\*\*</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="0c4f4-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="0c4f4-193">autodiscover</span></span>  <br/> |<span data-ttu-id="0c4f4-194">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="0c4f4-194">autodiscover.outlook.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="0c4f4-195">sip</span><span class="sxs-lookup"><span data-stu-id="0c4f4-195">sip</span></span>  <br/> |<span data-ttu-id="0c4f4-196">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0c4f4-196">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="0c4f4-197">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="0c4f4-197">lyncdiscover</span></span>  <br/> |<span data-ttu-id="0c4f4-198">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0c4f4-198">webdir.online.lync.com</span></span> <br/>  <br/> |
    |<span data-ttu-id="0c4f4-199">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="0c4f4-199">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="0c4f4-200">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="0c4f4-200">enterpriseregistration.windows.net</span></span>  <br/>  <br/> |
    |<span data-ttu-id="0c4f4-201">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="0c4f4-201">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="0c4f4-202">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="0c4f4-202">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/>  <br/> |
   
     ![De DNS-waarden uit de tabel kopiëren en plakken](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. <span data-ttu-id="0c4f4-204">Wanneer u alle CNAME-records hebt toegevoegd die u nodig hebt, selecteert u **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-204">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Selecteer Doorgaan](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. <span data-ttu-id="0c4f4-206">Selecteer op de volgende pagina **Opnieuw doorgaan** om uw wijzigingen te bevestigen en op te slaan.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-206">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Selecteer Doorgaan](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="0c4f4-208">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="0c4f4-208">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="0c4f4-209"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="0c4f4-209"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="0c4f4-210">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-210">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="0c4f4-211">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-211">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="0c4f4-212">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Office 365 te maken.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-212">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="0c4f4-213">In plaats daarvan voegt u de vereiste Office 365-waarden toe aan de huidige record, zodat u beschikt over één SPF-record waarin beide sets waarden zijn opgenomen.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-213">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span></span>  
  
<span data-ttu-id="0c4f4-214">Volg onderstaande stappen of [bekijk de video (start op 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="0c4f4-214">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="0c4f4-215">Als u wilt beginnen, gaat u [via deze koppeling](https://www.register.com/myaccount/) naar uw pagina met domeinen bij Register.com.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-215">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="0c4f4-216">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-216">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="0c4f4-217">Selecteer **Domeinen**.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-217">Select **Domains**.</span></span>
    
3. <span data-ttu-id="0c4f4-218">Selecteer **Beheren**.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-218">Select **Manage**.</span></span>
    
4. <span data-ttu-id="0c4f4-219">Zoek de rij met de naam van het domein dat u wilt wijzigen. en selecteer vervolgens in die rij **Beheren**.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-219">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="0c4f4-220">Schuif naar de sectie **Geavanceerde technische instellingen** en selecteer Vervolgens **TXT Records (SPF) bewerken.**</span><span class="sxs-lookup"><span data-stu-id="0c4f4-220">Scroll to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
    ![TXT-records bewerken (SPF) selecteren](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. <span data-ttu-id="0c4f4-222">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-222">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="0c4f4-223">\*\*\*\*Host Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="0c4f4-223">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="0c4f4-224">\*\*\*\*TXT Record\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="0c4f4-224">\*\*\*\*TXT Record\*\*\*\*</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="0c4f4-225">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="0c4f4-225">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="0c4f4-226">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-226">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>  |
   
     ![De waarden uit de tabel kopiëren en plakken](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. <span data-ttu-id="0c4f4-228">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-228">Select **Continue**.</span></span>
    
    ![Selecteer Doorgaan](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. <span data-ttu-id="0c4f4-230">Selecteer op de volgende pagina **Opnieuw doorgaan** om uw wijzigingen te bevestigen en op te slaan.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-230">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Selecteer Doorgaan](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="0c4f4-232">Voeg de vier SRV-records toe die voor Office 365 vereist zijn.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-232">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="0c4f4-233"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="0c4f4-233"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="0c4f4-234">Volg onderstaande stappen of [bekijk de video (start op 5:55)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="0c4f4-234">Follow the steps below or [watch the video (start at 5:55)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="0c4f4-p112">Als u wilt beginnen, gaat u [via deze koppeling](https://www.register.com/myaccount/) naar uw pagina met domeinen bij Register.com. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-p112">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="0c4f4-237">Selecteer **Domeinen**.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-237">Select **Domains**.</span></span>
    
3. <span data-ttu-id="0c4f4-238">Selecteer **Beheren**.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-238">Select **Manage**.</span></span>
    
4. <span data-ttu-id="0c4f4-239">Zoek de rij met de naam van het domein dat u wilt wijzigen. en selecteer vervolgens in die rij **Beheren**.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-239">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="0c4f4-240">Schuif naar de sectie **Geavanceerde technische instellingen** en selecteer Vervolgens **SRV-records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-240">Scroll to the **Advanced Technical Settings** section, and then select **Edit SRV Records**.</span></span>
    
    ![SRV-records bewerken selecteren](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. <span data-ttu-id="0c4f4-242">Voeg als volgt de eerste van de twee SRV-records toe:</span><span class="sxs-lookup"><span data-stu-id="0c4f4-242">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="0c4f4-243">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-243">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="0c4f4-244">(Kies de **waarde Prioriteit** in de vervolgkeuzelijst.)</span><span class="sxs-lookup"><span data-stu-id="0c4f4-244">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="0c4f4-245">\*\*\*\*Service\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="0c4f4-245">\*\*\*\*Service\*\*\*\*</span></span>|<span data-ttu-id="0c4f4-246">\*\*\*\*Proto\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="0c4f4-246">\*\*\*\*Proto\*\*\*\*</span></span>|<span data-ttu-id="0c4f4-247">\*\*\*\*Name\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="0c4f4-247">\*\*\*\*Name\*\*\*\*</span></span>|<span data-ttu-id="0c4f4-248">\*\*\*\*Priority\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="0c4f4-248">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="0c4f4-249">\*\*\*\*Gewicht\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="0c4f4-249">\*\*\*\*Weight\*\*\*\*</span></span>|<span data-ttu-id="0c4f4-250">\*\*\*\*Port\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="0c4f4-250">\*\*\*\*Port\*\*\*\*</span></span>|<span data-ttu-id="0c4f4-251">\*\*\*\*Target\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="0c4f4-251">\*\*\*\*Target\*\*\*\*</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="0c4f4-252">_sip</span><span class="sxs-lookup"><span data-stu-id="0c4f4-252">_sip</span></span>  <br/> |<span data-ttu-id="0c4f4-253">_tls</span><span class="sxs-lookup"><span data-stu-id="0c4f4-253">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="0c4f4-254">High</span><span class="sxs-lookup"><span data-stu-id="0c4f4-254">High</span></span>  <br/> |<span data-ttu-id="0c4f4-255">1</span><span class="sxs-lookup"><span data-stu-id="0c4f4-255">1</span></span>  <br/> |<span data-ttu-id="0c4f4-256">443</span><span class="sxs-lookup"><span data-stu-id="0c4f4-256">443</span></span>  <br/> |<span data-ttu-id="0c4f4-257">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0c4f4-257">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="0c4f4-258">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="0c4f4-258">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="0c4f4-259">_tcp</span><span class="sxs-lookup"><span data-stu-id="0c4f4-259">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="0c4f4-260">High</span><span class="sxs-lookup"><span data-stu-id="0c4f4-260">High</span></span>  <br/> |<span data-ttu-id="0c4f4-261">1</span><span class="sxs-lookup"><span data-stu-id="0c4f4-261">1</span></span>  <br/> |<span data-ttu-id="0c4f4-262">5061</span><span class="sxs-lookup"><span data-stu-id="0c4f4-262">5061</span></span>  <br/> |<span data-ttu-id="0c4f4-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0c4f4-263">sipfed.online.lync.com</span></span>  <br/>  <br/> |
   
    ![De waarden uit de tabel kopiëren en plakken](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. <span data-ttu-id="0c4f4-265">Selecteer **Meer SRV-records toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-265">Select **Add more SRV records**.</span></span>
    
    ![Meer SRV-records toevoegen selecteren](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. <span data-ttu-id="0c4f4-267">Voeg als volgt de tweede SRV-record toe:</span><span class="sxs-lookup"><span data-stu-id="0c4f4-267">Add the second SRV record:</span></span>
    
    <span data-ttu-id="0c4f4-268">Typ of kopieer en plak de waarden uit de tweede rij van de bovenstaande tabel in de velden van de tweede record.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-268">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
9. <span data-ttu-id="0c4f4-269">Wanneer u beide SRV-records hebt toegevoegd, selecteert u **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-269">When you have added both of the SRV records, select **Continue**.</span></span>
    
    ![Selecteer Doorgaan](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. <span data-ttu-id="0c4f4-271">Selecteer op de volgende pagina **Opnieuw doorgaan** om uw wijzigingen te bevestigen en op te slaan.</span><span class="sxs-lookup"><span data-stu-id="0c4f4-271">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Selecteer Doorgaan](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> <span data-ttu-id="0c4f4-p113">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0c4f4-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
