---
title: DNS-records bij Network Solutions maken voor Office 365
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1dc55f9f-5309-450f-acc3-b2b4119c8be3
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services bij Network Solutions voor Office 365.
ms.openlocfilehash: 6bbe954f763e0cb06e9bf32b991e60da34393c57
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211120"
---
# <a name="create-dns-records-at-network-solutions-for-office-365"></a><span data-ttu-id="df085-103">DNS-records bij Network Solutions maken voor Office 365</span><span class="sxs-lookup"><span data-stu-id="df085-103">Create DNS records at Network Solutions for Office 365</span></span>

 <span data-ttu-id="df085-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="df085-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="df085-105">Als Network Solutions uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="df085-105">If Network Solutions is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="df085-106">Dit zijn de belangrijkste records om toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="df085-106">These are the main records to add.</span></span> <span data-ttu-id="df085-107">Volg onderstaande stappen of [bekijk de video](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="df085-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span> 
  
- [<span data-ttu-id="df085-108">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="df085-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="df085-109">Voeg een MX-record toe zodat e-mail voor uw domein bij Office 365 terechtkomt</span><span class="sxs-lookup"><span data-stu-id="df085-109">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="df085-110">De CNAME-records toevoegen die voor Office 365 vereist zijn</span><span class="sxs-lookup"><span data-stu-id="df085-110">Add the CNAME records that are required for Office 365</span></span>](#add-the-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="df085-111">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="df085-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="df085-112">Voeg de vier SRV-records toe die voor Office 365 vereist zijn.</span><span class="sxs-lookup"><span data-stu-id="df085-112">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="df085-113">Nadat u deze records bij Network Solutions hebt toegevoegd, is uw domein ingesteld voor gebruik met Office 365-services.</span><span class="sxs-lookup"><span data-stu-id="df085-113">After you add these records at Network Solutions, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="df085-114">Zie [Een openbare website gebruiken met Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9) voor informatie over webhosting en DNS voor websites met Office 365.</span><span class="sxs-lookup"><span data-stu-id="df085-114">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="df085-p102">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="df085-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="df085-118">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="df085-118">Add a TXT record for verification</span></span>
<span data-ttu-id="df085-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="df085-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="df085-p103">Voordat u uw domein met Office 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Office 365 bewezen.</span><span class="sxs-lookup"><span data-stu-id="df085-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="df085-p104">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="df085-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="df085-124">Volg onderstaande stappen of [bekijk de video (start op 0:47)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="df085-124">Follow the steps below or [watch the video (start at 0:47)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="df085-125">Als u wilt beginnen, gaat u [via deze koppeling](https://www.networksolutions.com/manage-it) naar uw pagina met domeinen bij Network Solutions.</span><span class="sxs-lookup"><span data-stu-id="df085-125">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="df085-126">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="df085-126">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="df085-127">Voordat u de knop **Aanmelden** selecteert, kiest u **Mijn domeinnamen beheren** in de **vervolgkeuzelijst Aanmelden.**</span><span class="sxs-lookup"><span data-stu-id="df085-127">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Mijn domeinnamen beheren kiezen en aanmelden bij Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="df085-129">Schakel het selectievakje in naast de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="df085-129">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Het selectievakje voor uw domein selecteren](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="df085-131">Selecteer **DNS bewerken**.</span><span class="sxs-lookup"><span data-stu-id="df085-131">Select **Edit DNS**.</span></span>
    
    ![DNS bewerken selecteren](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="df085-133">Selecteer **Geavanceerde DNS-records beheren**.</span><span class="sxs-lookup"><span data-stu-id="df085-133">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="df085-134">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="df085-134">(You may have to scroll down.)</span></span>
    
    ![Selecteer Geavanceerde DNS-records beheren](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="df085-136">Schuif omlaag naar de sectie **Tekst (TXT Records)** en selecteer **Vervolgens TXT Records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="df085-136">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![TXT-records bewerken selecteren](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="df085-138">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="df085-138">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
    |<span data-ttu-id="df085-139">**Host**</span><span class="sxs-lookup"><span data-stu-id="df085-139">**Host**</span></span>|<span data-ttu-id="df085-140">**TTL**</span><span class="sxs-lookup"><span data-stu-id="df085-140">**TTL**</span></span>|<span data-ttu-id="df085-141">**Tekst**</span><span class="sxs-lookup"><span data-stu-id="df085-141">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="df085-142">(In het systeem wordt deze waarde gewijzigd in **@ (None)** wanneer u de record opslaat.)</span><span class="sxs-lookup"><span data-stu-id="df085-142">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="df085-143">3600</span><span class="sxs-lookup"><span data-stu-id="df085-143">3600</span></span>  <br/> |<span data-ttu-id="df085-144">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="df085-144">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="df085-145">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="df085-145">**Note:** This is an example.</span></span> <span data-ttu-id="df085-146">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365.</span><span class="sxs-lookup"><span data-stu-id="df085-146">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>  [<span data-ttu-id="df085-147">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="df085-147">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)   |
       
    ![Waarden typen of plakken in de vakken voor de nieuwe record](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="df085-149">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="df085-149">Select **Continue**.</span></span>
    
    ![Selecteer Doorgaan](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="df085-151">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="df085-151">Select **Save Changes**.</span></span>
    
    ![Selecteer Wijzigingen opslaan](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="df085-153">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="df085-153">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="df085-154">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Office 365 en vraagt u of Office 365 naar de record wil zoeken.</span><span class="sxs-lookup"><span data-stu-id="df085-154">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="df085-155">Wanneer in Office 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="df085-155">When Office 365 finds the correct TXT record, your domain is verified.</span></span>

1. <span data-ttu-id="df085-156">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="df085-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="df085-157">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="df085-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="df085-158">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="df085-158">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="df085-159">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="df085-159">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="df085-p107">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="df085-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="df085-163">Een MX-record toevoegen zodat e-mail voor uw domein bij Office 365 terechtkomt</span><span class="sxs-lookup"><span data-stu-id="df085-163">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="df085-164"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="df085-164"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="df085-165">Volg onderstaande stappen of [bekijk de video (start op 3:51)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="df085-165">Follow the steps below or [watch the video (start at 3:51)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="df085-166">Als u wilt beginnen, gaat u [via deze koppeling](https://www.networksolutions.com/manage-it) naar uw pagina met domeinen bij Network Solutions.</span><span class="sxs-lookup"><span data-stu-id="df085-166">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="df085-167">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="df085-167">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="df085-168">Voordat u de knop **Aanmelden** selecteert, kiest u **Mijn domeinnamen beheren** in de **vervolgkeuzelijst Aanmelden.**</span><span class="sxs-lookup"><span data-stu-id="df085-168">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Mijn domeinnamen beheren kiezen en aanmelden bij Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="df085-170">Schakel het selectievakje in naast de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="df085-170">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Het selectievakje voor uw domein selecteren](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="df085-172">Selecteer **DNS bewerken**.</span><span class="sxs-lookup"><span data-stu-id="df085-172">Select **Edit DNS**.</span></span>
    
    ![DNS bewerken selecteren](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="df085-174">Selecteer **Geavanceerde DNS-records beheren**.</span><span class="sxs-lookup"><span data-stu-id="df085-174">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="df085-175">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="df085-175">(You may have to scroll down.)</span></span>
    
    ![Selecteer Geavanceerde DNS-records beheren](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="df085-177">Schuif omlaag naar de sectie **Mail Servers (MX Records)** en selecteer **VERVOLGENS MX Records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="df085-177">Scroll down to the **Mail Servers (MX Records)** section, and then select **Edit MX Records**.</span></span>
    
    ![MX-records bewerken selecteren](../../media/74b4e412-9073-4d2d-8710-fe340b223798.png)
  
6. <span data-ttu-id="df085-179">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="df085-179">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="df085-180">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="df085-180">**Priority**</span></span>|<span data-ttu-id="df085-181">**TTL**</span><span class="sxs-lookup"><span data-stu-id="df085-181">**TTL**</span></span>|<span data-ttu-id="df085-182">**Mail Server**</span><span class="sxs-lookup"><span data-stu-id="df085-182">**Mail Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="df085-183">10</span><span class="sxs-lookup"><span data-stu-id="df085-183">10</span></span>  <br/> <span data-ttu-id="df085-184">Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="df085-184">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="df085-185">3600</span><span class="sxs-lookup"><span data-stu-id="df085-185">3600</span></span>  <br/> | <span data-ttu-id="df085-186">*\<domein-sleutel\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="df085-186">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="df085-187">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="df085-187">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="df085-188">**Let op:** Haal uw \* \<domeinsleutel\> \* op uit uw Office 365-account.</span><span class="sxs-lookup"><span data-stu-id="df085-188">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span> [<span data-ttu-id="df085-189">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="df085-189">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![Waarden typen of plakken in de vakken voor de nieuwe record](../../media/0bb96872-cc6e-4dfa-a649-fb7efbbf0012.png)
  
7. <span data-ttu-id="df085-191">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="df085-191">Select **Continue**.</span></span>
    
    ![Selecteer Doorgaan](../../media/963f758b-e79d-4452-8340-7eba8a3972c9.png)
  
8. <span data-ttu-id="df085-193">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="df085-193">Select **Save Changes**.</span></span>
    
    ![Selecteer Wijzigingen opslaan](../../media/7c2f784a-6dee-4364-866c-ad7202ef1fc2.png)
  
9. <span data-ttu-id="df085-195">Als er andere MX-records zijn, verwijdert u deze allemaal door voor elke record **Delete** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="df085-195">If there are any other MX records, delete all of them by selecting **Delete** for each record.</span></span> 
    
    ![Select the Delete check box for other MX records](../../media/709d6133-9f5d-490a-a91e-95e21ca94695.png)
  
10. <span data-ttu-id="df085-197">Wanneer ze allemaal zijn geselecteerd, selecteert u **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="df085-197">When they are all selected, select **Continue**.</span></span>
    
    ![Selecteer Doorgaan](../../media/4710f988-0bbc-4ba7-bf31-ca2392b2900e.png)
  
11. <span data-ttu-id="df085-199">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="df085-199">Select **Save Changes**.</span></span>
    
    ![Selecteer Wijzigingen opslaan](../../media/24432ec6-666b-4612-9488-37c06437959b.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="df085-201">De CNAME-records toevoegen die voor Office 365 vereist zijn</span><span class="sxs-lookup"><span data-stu-id="df085-201">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="df085-202"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="df085-202"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="df085-203">Volg onderstaande stappen of [bekijk de video (start op 4:43)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="df085-203">Follow the steps below or [watch the video (start at 4:43)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="df085-204">Als u wilt beginnen, gaat u [via deze koppeling](https://www.networksolutions.com/manage-it) naar uw pagina met domeinen bij Network Solutions.</span><span class="sxs-lookup"><span data-stu-id="df085-204">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="df085-205">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="df085-205">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="df085-206">Voordat u de knop **Aanmelden** selecteert, kiest u **Mijn domeinnamen beheren** in de **vervolgkeuzelijst Aanmelden.**</span><span class="sxs-lookup"><span data-stu-id="df085-206">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Mijn domeinnamen beheren kiezen en aanmelden bij Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="df085-208">Schakel het selectievakje in naast de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="df085-208">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Het selectievakje voor uw domein selecteren](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="df085-210">Selecteer **DNS bewerken**.</span><span class="sxs-lookup"><span data-stu-id="df085-210">Select **Edit DNS**.</span></span>
    
    ![DNS bewerken selecteren](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="df085-212">Selecteer **Geavanceerde DNS-records beheren**.</span><span class="sxs-lookup"><span data-stu-id="df085-212">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="df085-213">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="df085-213">(You may have to scroll down.)</span></span>
    
    ![Selecteer Geavanceerde DNS-records beheren](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="df085-215">Schuif omlaag naar de sectie **Host Aliassen (CNAME Records)** en selecteer **CNAME Records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="df085-215">Scroll down to the **Host Aliases (CNAME Records)** section, and then select **Edit CNAME Records**.</span></span>
    
    ![CNAME-records bewerken onder Host Aliassen selecteren](../../media/2d0a4666-8d40-48f4-886c-64a5157baaf5.png)
  
6. <span data-ttu-id="df085-217">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de vier nieuwe records.</span><span class="sxs-lookup"><span data-stu-id="df085-217">In the boxes for the four new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="df085-218">**Alias**</span><span class="sxs-lookup"><span data-stu-id="df085-218">**Alias**</span></span>|<span data-ttu-id="df085-219">**TTL**</span><span class="sxs-lookup"><span data-stu-id="df085-219">**TTL**</span></span>|<span data-ttu-id="df085-220">**Refers to Host Name**</span><span class="sxs-lookup"><span data-stu-id="df085-220">**Refers to Host Name**</span></span>|<span data-ttu-id="df085-221">**Other Host          (selecteer het keuzerondje **Other Host**)**</span><span class="sxs-lookup"><span data-stu-id="df085-221">**Other Host          (select the **Other Host** option button)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="df085-222">autodiscover</span><span class="sxs-lookup"><span data-stu-id="df085-222">autodiscover</span></span>  <br/> |<span data-ttu-id="df085-223">3600</span><span class="sxs-lookup"><span data-stu-id="df085-223">3600</span></span>  <br/> |<span data-ttu-id="df085-224">(Geen instelling)</span><span class="sxs-lookup"><span data-stu-id="df085-224">(No setting)</span></span>  <br/> |<span data-ttu-id="df085-225">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="df085-225">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="df085-226">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="df085-226">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="df085-227">sip</span><span class="sxs-lookup"><span data-stu-id="df085-227">sip</span></span>  <br/> |<span data-ttu-id="df085-228">3600</span><span class="sxs-lookup"><span data-stu-id="df085-228">3600</span></span>  <br/> |<span data-ttu-id="df085-229">(Geen instelling)</span><span class="sxs-lookup"><span data-stu-id="df085-229">(No setting)</span></span>  <br/> |<span data-ttu-id="df085-230">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="df085-230">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="df085-231">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="df085-231">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="df085-232">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="df085-232">lyncdiscover</span></span>  <br/> |<span data-ttu-id="df085-233">3600</span><span class="sxs-lookup"><span data-stu-id="df085-233">3600</span></span>  <br/> |<span data-ttu-id="df085-234">(Geen instelling)</span><span class="sxs-lookup"><span data-stu-id="df085-234">(No setting)</span></span>  <br/> |<span data-ttu-id="df085-235">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="df085-235">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="df085-236">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="df085-236">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="df085-237">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="df085-237">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="df085-238">3600</span><span class="sxs-lookup"><span data-stu-id="df085-238">3600</span></span>  <br/> |<span data-ttu-id="df085-239">(Geen instelling)</span><span class="sxs-lookup"><span data-stu-id="df085-239">(No setting)</span></span>  <br/> |<span data-ttu-id="df085-240">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="df085-240">enterpriseregistration.windows.net</span></span>  <br/> <span data-ttu-id="df085-241">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="df085-241">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="df085-242">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="df085-242">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="df085-243">3600</span><span class="sxs-lookup"><span data-stu-id="df085-243">3600</span></span>  <br/> |<span data-ttu-id="df085-244">(Geen instelling)</span><span class="sxs-lookup"><span data-stu-id="df085-244">(No setting)</span></span>  <br/> |<span data-ttu-id="df085-245">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="df085-245">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> <span data-ttu-id="df085-246">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="df085-246">**This value MUST end with a period (.)**</span></span> <br/> |
    
    ![Waarden voor de nieuwe records typen of plakken](../../media/5ce0b30c-b46c-4778-aa5a-fb5e2f0961c1.png)
  
7. <span data-ttu-id="df085-248">Wanneer u alle CNAME-records hebt toegevoegd die u nodig hebt, selecteert u **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="df085-248">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Selecteer Doorgaan](../../media/4978bd8b-f6a6-458d-9522-ad612b301c4a.png)
  
8. <span data-ttu-id="df085-250">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="df085-250">Select **Save Changes**.</span></span>
    
    ![Selecteer Wijzigingen opslaan](../../media/f005c38a-0d8d-4c61-bec6-15e60c89aa5a.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="df085-252">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="df085-252">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="df085-253"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="df085-253"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="df085-254">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="df085-254">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="df085-255">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="df085-255">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="df085-256">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Office 365 te maken.</span><span class="sxs-lookup"><span data-stu-id="df085-256">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="df085-257">In plaats daarvan voegt u de vereiste Office 365-waarden toe aan de huidige record, zodat u beschikt over  *één*  SPF-record waarin beide sets waarden zijn opgenomen.</span><span class="sxs-lookup"><span data-stu-id="df085-257">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="df085-258">Volg onderstaande stappen of [bekijk de video (start op 5:35)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="df085-258">Follow the steps below or [watch the video (start at 5:35)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="df085-259">Als u wilt beginnen, gaat u [via deze koppeling](https://www.networksolutions.com/manage-it) naar uw pagina met domeinen bij Network Solutions.</span><span class="sxs-lookup"><span data-stu-id="df085-259">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="df085-260">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="df085-260">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="df085-261">Voordat u de knop **Aanmelden** selecteert, kiest u **Mijn domeinnamen beheren** in de **vervolgkeuzelijst Aanmelden.**</span><span class="sxs-lookup"><span data-stu-id="df085-261">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Mijn domeinnamen beheren kiezen en aanmelden bij Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="df085-263">Schakel het selectievakje in naast de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="df085-263">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Het selectievakje voor uw domein selecteren](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="df085-265">Selecteer **DNS bewerken**.</span><span class="sxs-lookup"><span data-stu-id="df085-265">Select **Edit DNS**.</span></span>
    
    ![DNS bewerken selecteren](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="df085-267">Selecteer **Geavanceerde DNS-records beheren**.</span><span class="sxs-lookup"><span data-stu-id="df085-267">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="df085-268">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="df085-268">(You may have to scroll down.)</span></span>
    
    ![Selecteer Geavanceerde DNS-records beheren](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="df085-270">Schuif omlaag naar de sectie **Tekst (TXT Records)** en selecteer **Vervolgens TXT Records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="df085-270">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![TXT-records bewerken onder Tekst selecteren](../../media/a69a2631-6da2-4e81-99ab-9a9ab9b30b07.png)
  
6. <span data-ttu-id="df085-272">Typ of kopieer en plak de volgende waarden in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="df085-272">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="df085-273">**Host**</span><span class="sxs-lookup"><span data-stu-id="df085-273">**Host**</span></span>|<span data-ttu-id="df085-274">**TTL**</span><span class="sxs-lookup"><span data-stu-id="df085-274">**TTL**</span></span>|<span data-ttu-id="df085-275">**Tekst**</span><span class="sxs-lookup"><span data-stu-id="df085-275">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="df085-276">(In het systeem wordt deze waarde gewijzigd in **@ (None)** wanneer u de record opslaat.)</span><span class="sxs-lookup"><span data-stu-id="df085-276">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="df085-277">3600</span><span class="sxs-lookup"><span data-stu-id="df085-277">3600</span></span>  <br/> |<span data-ttu-id="df085-278">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="df085-278">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="df085-279">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="df085-279">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span> |
       
    ![Waarden voor de nieuwe record typen of plakken](../../media/11564eca-e2ee-4f17-af2b-a00eb7c157db.png)
  
7. <span data-ttu-id="df085-281">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="df085-281">Select **Continue**.</span></span>
    
    ![Selecteer Doorgaan](../../media/482a8dae-0c79-47c4-8bd8-87965683de24.png)
  
8. <span data-ttu-id="df085-283">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="df085-283">Select **Save Changes**.</span></span>
    
    ![Selecteer Wijzigingen opslaan](../../media/600b8c6d-184f-4213-a50e-8f119ebf3ff0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="df085-285">De twee SRV-records toevoegen die voor Office 365 vereist zijn</span><span class="sxs-lookup"><span data-stu-id="df085-285">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="df085-286"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="df085-286"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="df085-287">Volg onderstaande stappen of [bekijk de video (start op 6:18)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="df085-287">Follow the steps below or [watch the video (start at 6:18)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="df085-p113">Als u wilt beginnen, gaat u [via deze koppeling](https://www.networksolutions.com/manage-it) naar uw pagina met domeinen bij Network Solutions. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="df085-p113">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="df085-290">Voordat u de knop **Aanmelden** selecteert, kiest u **Mijn domeinnamen beheren** in de **vervolgkeuzelijst Aanmelden.**</span><span class="sxs-lookup"><span data-stu-id="df085-290">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Mijn domeinnamen beheren kiezen en aanmelden bij Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="df085-292">Schakel het selectievakje in naast de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="df085-292">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Het selectievakje voor uw domein selecteren](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="df085-294">Selecteer **DNS bewerken**.</span><span class="sxs-lookup"><span data-stu-id="df085-294">Select **Edit DNS**.</span></span>
    
    ![DNS bewerken selecteren](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="df085-296">Selecteer **Geavanceerde DNS-records beheren**.</span><span class="sxs-lookup"><span data-stu-id="df085-296">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="df085-297">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="df085-297">(You may have to scroll down.)</span></span>
    
    ![Selecteer Geavanceerde DNS-records beheren](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="df085-299">Schuif omlaag naar de sectie **Service (SRV Records)** en selecteer **Vervolgens SRV Records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="df085-299">Scroll down to the **Service (SRV Records)** section, and then select **Edit SRV Records**.</span></span>
    
    ![SRV-records bewerken onder Service selecteren](../../media/9a9248ea-5de5-4e16-9364-f7600fa371f5.png)
  
6. <span data-ttu-id="df085-301">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de twee nieuwe records.</span><span class="sxs-lookup"><span data-stu-id="df085-301">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="df085-302">(Kies in de vervolgkeuzelijsten de waarden **Service** en **Protocol**.)</span><span class="sxs-lookup"><span data-stu-id="df085-302">(Choose the **Service** and **Protocol** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="df085-303">**Service**</span><span class="sxs-lookup"><span data-stu-id="df085-303">**Service**</span></span>|<span data-ttu-id="df085-304">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="df085-304">**Protocol**</span></span>|<span data-ttu-id="df085-305">**TTL**</span><span class="sxs-lookup"><span data-stu-id="df085-305">**TTL**</span></span>|<span data-ttu-id="df085-306">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="df085-306">**Priority**</span></span>|<span data-ttu-id="df085-307">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="df085-307">**Weight**</span></span>|<span data-ttu-id="df085-308">**Poort**</span><span class="sxs-lookup"><span data-stu-id="df085-308">**Port**</span></span>|<span data-ttu-id="df085-309">**Target**</span><span class="sxs-lookup"><span data-stu-id="df085-309">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="df085-310">_sip</span><span class="sxs-lookup"><span data-stu-id="df085-310">_sip</span></span>  <br/> |<span data-ttu-id="df085-311">_tls</span><span class="sxs-lookup"><span data-stu-id="df085-311">_tls</span></span>  <br/> |<span data-ttu-id="df085-312">3600</span><span class="sxs-lookup"><span data-stu-id="df085-312">3600</span></span>  <br/> |<span data-ttu-id="df085-313">100</span><span class="sxs-lookup"><span data-stu-id="df085-313">100</span></span>  <br/> |<span data-ttu-id="df085-314">1</span><span class="sxs-lookup"><span data-stu-id="df085-314">1</span></span>  <br/> |<span data-ttu-id="df085-315">443</span><span class="sxs-lookup"><span data-stu-id="df085-315">443</span></span>  <br/> |<span data-ttu-id="df085-316">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="df085-316">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="df085-317">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="df085-317">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="df085-318">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="df085-318">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="df085-319">_tcp</span><span class="sxs-lookup"><span data-stu-id="df085-319">_tcp</span></span>  <br/> |<span data-ttu-id="df085-320">3600</span><span class="sxs-lookup"><span data-stu-id="df085-320">3600</span></span>  <br/> |<span data-ttu-id="df085-321">100</span><span class="sxs-lookup"><span data-stu-id="df085-321">100</span></span>  <br/> |<span data-ttu-id="df085-322">1</span><span class="sxs-lookup"><span data-stu-id="df085-322">1</span></span>  <br/> |<span data-ttu-id="df085-323">5061</span><span class="sxs-lookup"><span data-stu-id="df085-323">5061</span></span>  <br/> |<span data-ttu-id="df085-324">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="df085-324">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="df085-325">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="df085-325">**This value MUST end with a period (.)**</span></span> <br/> |
       
    ![Waarden voor de nieuwe records typen of plakken](../../media/86968d1c-8e43-4e61-aeaa-37fc7d7ef7a7.png)
  
7. <span data-ttu-id="df085-327">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="df085-327">Select **Continue**.</span></span>
    
    ![Selecteer Doorgaan](../../media/bfe2c778-5d2b-4bb6-a79d-c3ff9caf9e1e.png)
  
8. <span data-ttu-id="df085-329">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="df085-329">Select **Save Changes**.</span></span>
    
    ![Selecteer Wijzigingen opslaan](../../media/6d323126-0ebe-45ab-8567-c234711d84c7.png)
  
> [!NOTE]
>  <span data-ttu-id="df085-p114">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="df085-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
