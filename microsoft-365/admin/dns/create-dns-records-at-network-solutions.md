---
title: DNS-records maken bij Network Solutions voor Microsoft
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
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services bij Network Solutions voor Microsoft.
ms.openlocfilehash: e7ce1dd633aa916643f3dcbf7900fa7831608e78
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629297"
---
# <a name="create-dns-records-at-network-solutions-for-microsoft"></a><span data-ttu-id="d8abf-103">DNS-records maken bij Network Solutions voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="d8abf-103">Create DNS records at Network Solutions for Microsoft</span></span>

 <span data-ttu-id="d8abf-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="d8abf-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="d8abf-105">Als Network Solutions uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="d8abf-105">If Network Solutions is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="d8abf-106">Dit zijn de belangrijkste records om toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="d8abf-106">These are the main records to add.</span></span> <span data-ttu-id="d8abf-107">Volg onderstaande stappen of [bekijk de video](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="d8abf-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span> 
  
- [<span data-ttu-id="d8abf-108">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="d8abf-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="d8abf-109">Voeg een MX-record toe, zodat e-mail voor uw domein naar Microsoft komt</span><span class="sxs-lookup"><span data-stu-id="d8abf-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="d8abf-110">De CNAME-records toevoegen die voor Microsoft vereist zijn</span><span class="sxs-lookup"><span data-stu-id="d8abf-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="d8abf-111">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="d8abf-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="d8abf-112">Voeg de twee SRV-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="d8abf-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="d8abf-113">Nadat u deze records hebt toegevoegd bij Network Solutions, wordt uw domein ingesteld voor gebruik met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="d8abf-113">After you add these records at Network Solutions, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="d8abf-114">Zie Een openbare website gebruiken met Microsoft voor meer informatie over webhosting en DNS voor websites met [Microsoft.](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)</span><span class="sxs-lookup"><span data-stu-id="d8abf-114">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="d8abf-p102">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d8abf-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="d8abf-118">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="d8abf-118">Add a TXT record for verification</span></span>
<span data-ttu-id="d8abf-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="d8abf-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="d8abf-120">Voordat u uw domein bij Microsoft gebruikt, moeten we ervoor zorgen dat u eigenaar bent.</span><span class="sxs-lookup"><span data-stu-id="d8abf-120">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="d8abf-121">Uw mogelijkheid om in te loggen op uw account bij uw domeinregistrar en de DNS-record te maken bewijst microsoft dat u eigenaar bent van het domein.</span><span class="sxs-lookup"><span data-stu-id="d8abf-121">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d8abf-p104">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="d8abf-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="d8abf-124">Volg onderstaande stappen of [bekijk de video (start op 0:47)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="d8abf-124">Follow the steps below or [watch the video (start at 0:47)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="d8abf-125">Als u wilt beginnen, gaat u [via deze koppeling](https://www.networksolutions.com/manage-it) naar uw pagina met domeinen bij Network Solutions.</span><span class="sxs-lookup"><span data-stu-id="d8abf-125">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="d8abf-126">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="d8abf-126">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d8abf-127">Voordat u de knop **Aanmelden** selecteert, kiest u **Mijn domeinnamen beheren** in de **vervolgkeuzelijst Aanmelden.**</span><span class="sxs-lookup"><span data-stu-id="d8abf-127">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Mijn domeinnamen beheren kiezen en aanmelden bij Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="d8abf-129">Schakel het selectievakje in naast de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="d8abf-129">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Het selectievakje voor uw domein selecteren](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="d8abf-131">Selecteer **DNS bewerken**.</span><span class="sxs-lookup"><span data-stu-id="d8abf-131">Select **Edit DNS**.</span></span>
    
    ![DNS bewerken selecteren](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="d8abf-133">Selecteer **Geavanceerde DNS-records beheren**.</span><span class="sxs-lookup"><span data-stu-id="d8abf-133">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="d8abf-134">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="d8abf-134">(You may have to scroll down.)</span></span>
    
    ![Selecteer Geavanceerde DNS-records beheren](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="d8abf-136">Schuif omlaag naar de sectie **Tekst (TXT Records)** en selecteer **Vervolgens TXT Records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="d8abf-136">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![TXT-records bewerken selecteren](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="d8abf-138">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="d8abf-138">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
    |<span data-ttu-id="d8abf-139">**Host**</span><span class="sxs-lookup"><span data-stu-id="d8abf-139">**Host**</span></span>|<span data-ttu-id="d8abf-140">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d8abf-140">**TTL**</span></span>|<span data-ttu-id="d8abf-141">**Tekst**</span><span class="sxs-lookup"><span data-stu-id="d8abf-141">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="d8abf-142">(In het systeem wordt deze waarde gewijzigd in **@ (None)** wanneer u de record opslaat.)</span><span class="sxs-lookup"><span data-stu-id="d8abf-142">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="d8abf-143">3600</span><span class="sxs-lookup"><span data-stu-id="d8abf-143">3600</span></span>  <br/> |<span data-ttu-id="d8abf-144">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="d8abf-144">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="d8abf-145">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="d8abf-145">**Note:** This is an example.</span></span> <span data-ttu-id="d8abf-146">Gebruik hier de waarde van uw specifieke **bestemming of adrespunt** in de tabel.</span><span class="sxs-lookup"><span data-stu-id="d8abf-146">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="d8abf-147">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="d8abf-147">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)   |
       
    ![Waarden typen of plakken in de vakken voor de nieuwe record](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="d8abf-149">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="d8abf-149">Select **Continue**.</span></span>
    
    ![Selecteer Doorgaan](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="d8abf-151">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="d8abf-151">Select **Save Changes**.</span></span>
    
    ![Selecteer Wijzigingen opslaan](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="d8abf-153">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="d8abf-153">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="d8abf-154">Nu u de record op de site van uw domeinregistrar hebt toegevoegd, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="d8abf-154">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="d8abf-155">Wanneer Microsoft de juiste TXT-record vindt, wordt uw domein geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="d8abf-155">When Microsoft finds the correct TXT record, your domain is verified.</span></span>

1. <span data-ttu-id="d8abf-156">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="d8abf-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="d8abf-157">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="d8abf-157">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="d8abf-158">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="d8abf-158">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="d8abf-159">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="d8abf-159">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="d8abf-p107">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d8abf-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="d8abf-163">Voeg een MX-record toe, zodat e-mail voor uw domein naar Microsoft komt</span><span class="sxs-lookup"><span data-stu-id="d8abf-163">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="d8abf-164"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="d8abf-164"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="d8abf-165">Volg onderstaande stappen of [bekijk de video (start op 3:51)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="d8abf-165">Follow the steps below or [watch the video (start at 3:51)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="d8abf-166">Als u wilt beginnen, gaat u [via deze koppeling](https://www.networksolutions.com/manage-it) naar uw pagina met domeinen bij Network Solutions.</span><span class="sxs-lookup"><span data-stu-id="d8abf-166">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="d8abf-167">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="d8abf-167">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d8abf-168">Voordat u de knop **Aanmelden** selecteert, kiest u **Mijn domeinnamen beheren** in de **vervolgkeuzelijst Aanmelden.**</span><span class="sxs-lookup"><span data-stu-id="d8abf-168">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Mijn domeinnamen beheren kiezen en aanmelden bij Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="d8abf-170">Schakel het selectievakje in naast de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="d8abf-170">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Het selectievakje voor uw domein selecteren](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="d8abf-172">Selecteer **DNS bewerken**.</span><span class="sxs-lookup"><span data-stu-id="d8abf-172">Select **Edit DNS**.</span></span>
    
    ![DNS bewerken selecteren](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="d8abf-174">Selecteer **Geavanceerde DNS-records beheren**.</span><span class="sxs-lookup"><span data-stu-id="d8abf-174">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="d8abf-175">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="d8abf-175">(You may have to scroll down.)</span></span>
    
    ![Selecteer Geavanceerde DNS-records beheren](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="d8abf-177">Schuif omlaag naar de sectie **Mail Servers (MX Records)** en selecteer **VERVOLGENS MX Records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="d8abf-177">Scroll down to the **Mail Servers (MX Records)** section, and then select **Edit MX Records**.</span></span>
    
    ![MX-records bewerken selecteren](../../media/74b4e412-9073-4d2d-8710-fe340b223798.png)
  
6. <span data-ttu-id="d8abf-179">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="d8abf-179">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="d8abf-180">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="d8abf-180">**Priority**</span></span>|<span data-ttu-id="d8abf-181">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d8abf-181">**TTL**</span></span>|<span data-ttu-id="d8abf-182">**Mail Server**</span><span class="sxs-lookup"><span data-stu-id="d8abf-182">**Mail Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="d8abf-183">10</span><span class="sxs-lookup"><span data-stu-id="d8abf-183">10</span></span>  <br/> <span data-ttu-id="d8abf-184">Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="d8abf-184">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="d8abf-185">3600</span><span class="sxs-lookup"><span data-stu-id="d8abf-185">3600</span></span>  <br/> | <span data-ttu-id="d8abf-186">*\<domein-sleutel\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="d8abf-186">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="d8abf-187">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="d8abf-187">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="d8abf-188">**Let op:** Haal uw \* \<domeinsleutel\> \* uit uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="d8abf-188">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span> [<span data-ttu-id="d8abf-189">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="d8abf-189">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![Waarden typen of plakken in de vakken voor de nieuwe record](../../media/0bb96872-cc6e-4dfa-a649-fb7efbbf0012.png)
  
7. <span data-ttu-id="d8abf-191">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="d8abf-191">Select **Continue**.</span></span>
    
    ![Selecteer Doorgaan](../../media/963f758b-e79d-4452-8340-7eba8a3972c9.png)
  
8. <span data-ttu-id="d8abf-193">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="d8abf-193">Select **Save Changes**.</span></span>
    
    ![Selecteer Wijzigingen opslaan](../../media/7c2f784a-6dee-4364-866c-ad7202ef1fc2.png)
  
9. <span data-ttu-id="d8abf-195">Als er andere MX-records zijn, verwijdert u deze allemaal door voor elke record **Delete** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="d8abf-195">If there are any other MX records, delete all of them by selecting **Delete** for each record.</span></span> 
    
    ![Select the Delete check box for other MX records](../../media/709d6133-9f5d-490a-a91e-95e21ca94695.png)
  
10. <span data-ttu-id="d8abf-197">Wanneer ze allemaal zijn geselecteerd, selecteert u **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="d8abf-197">When they are all selected, select **Continue**.</span></span>
    
    ![Selecteer Doorgaan](../../media/4710f988-0bbc-4ba7-bf31-ca2392b2900e.png)
  
11. <span data-ttu-id="d8abf-199">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="d8abf-199">Select **Save Changes**.</span></span>
    
    ![Selecteer Wijzigingen opslaan](../../media/24432ec6-666b-4612-9488-37c06437959b.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="d8abf-201">De CNAME-records toevoegen die voor Microsoft vereist zijn</span><span class="sxs-lookup"><span data-stu-id="d8abf-201">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="d8abf-202"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="d8abf-202"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="d8abf-203">Volg onderstaande stappen of [bekijk de video (start op 4:43)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="d8abf-203">Follow the steps below or [watch the video (start at 4:43)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="d8abf-204">Als u wilt beginnen, gaat u [via deze koppeling](https://www.networksolutions.com/manage-it) naar uw pagina met domeinen bij Network Solutions.</span><span class="sxs-lookup"><span data-stu-id="d8abf-204">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="d8abf-205">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="d8abf-205">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d8abf-206">Voordat u de knop **Aanmelden** selecteert, kiest u **Mijn domeinnamen beheren** in de **vervolgkeuzelijst Aanmelden.**</span><span class="sxs-lookup"><span data-stu-id="d8abf-206">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Mijn domeinnamen beheren kiezen en aanmelden bij Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="d8abf-208">Schakel het selectievakje in naast de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="d8abf-208">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Het selectievakje voor uw domein selecteren](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="d8abf-210">Selecteer **DNS bewerken**.</span><span class="sxs-lookup"><span data-stu-id="d8abf-210">Select **Edit DNS**.</span></span>
    
    ![DNS bewerken selecteren](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="d8abf-212">Selecteer **Geavanceerde DNS-records beheren**.</span><span class="sxs-lookup"><span data-stu-id="d8abf-212">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="d8abf-213">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="d8abf-213">(You may have to scroll down.)</span></span>
    
    ![Selecteer Geavanceerde DNS-records beheren](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="d8abf-215">Schuif omlaag naar de sectie **Host Aliassen (CNAME Records)** en selecteer **CNAME Records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="d8abf-215">Scroll down to the **Host Aliases (CNAME Records)** section, and then select **Edit CNAME Records**.</span></span>
    
    ![CNAME-records bewerken onder Host Aliassen selecteren](../../media/2d0a4666-8d40-48f4-886c-64a5157baaf5.png)
  
6. <span data-ttu-id="d8abf-217">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de vier nieuwe records.</span><span class="sxs-lookup"><span data-stu-id="d8abf-217">In the boxes for the four new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="d8abf-218">**Alias**</span><span class="sxs-lookup"><span data-stu-id="d8abf-218">**Alias**</span></span>|<span data-ttu-id="d8abf-219">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d8abf-219">**TTL**</span></span>|<span data-ttu-id="d8abf-220">**Refers to Host Name**</span><span class="sxs-lookup"><span data-stu-id="d8abf-220">**Refers to Host Name**</span></span>|<span data-ttu-id="d8abf-221">**Other Host          (selecteer het keuzerondje **Other Host**)**</span><span class="sxs-lookup"><span data-stu-id="d8abf-221">**Other Host          (select the **Other Host** option button)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d8abf-222">autodiscover</span><span class="sxs-lookup"><span data-stu-id="d8abf-222">autodiscover</span></span>  <br/> |<span data-ttu-id="d8abf-223">3600</span><span class="sxs-lookup"><span data-stu-id="d8abf-223">3600</span></span>  <br/> |<span data-ttu-id="d8abf-224">(Geen instelling)</span><span class="sxs-lookup"><span data-stu-id="d8abf-224">(No setting)</span></span>  <br/> |<span data-ttu-id="d8abf-225">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="d8abf-225">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="d8abf-226">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="d8abf-226">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="d8abf-227">sip</span><span class="sxs-lookup"><span data-stu-id="d8abf-227">sip</span></span>  <br/> |<span data-ttu-id="d8abf-228">3600</span><span class="sxs-lookup"><span data-stu-id="d8abf-228">3600</span></span>  <br/> |<span data-ttu-id="d8abf-229">(Geen instelling)</span><span class="sxs-lookup"><span data-stu-id="d8abf-229">(No setting)</span></span>  <br/> |<span data-ttu-id="d8abf-230">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d8abf-230">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="d8abf-231">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="d8abf-231">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="d8abf-232">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="d8abf-232">lyncdiscover</span></span>  <br/> |<span data-ttu-id="d8abf-233">3600</span><span class="sxs-lookup"><span data-stu-id="d8abf-233">3600</span></span>  <br/> |<span data-ttu-id="d8abf-234">(Geen instelling)</span><span class="sxs-lookup"><span data-stu-id="d8abf-234">(No setting)</span></span>  <br/> |<span data-ttu-id="d8abf-235">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d8abf-235">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="d8abf-236">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="d8abf-236">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="d8abf-237">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="d8abf-237">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="d8abf-238">3600</span><span class="sxs-lookup"><span data-stu-id="d8abf-238">3600</span></span>  <br/> |<span data-ttu-id="d8abf-239">(Geen instelling)</span><span class="sxs-lookup"><span data-stu-id="d8abf-239">(No setting)</span></span>  <br/> |<span data-ttu-id="d8abf-240">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="d8abf-240">enterpriseregistration.windows.net</span></span>  <br/> <span data-ttu-id="d8abf-241">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="d8abf-241">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="d8abf-242">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="d8abf-242">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="d8abf-243">3600</span><span class="sxs-lookup"><span data-stu-id="d8abf-243">3600</span></span>  <br/> |<span data-ttu-id="d8abf-244">(Geen instelling)</span><span class="sxs-lookup"><span data-stu-id="d8abf-244">(No setting)</span></span>  <br/> |<span data-ttu-id="d8abf-245">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d8abf-245">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> <span data-ttu-id="d8abf-246">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="d8abf-246">**This value MUST end with a period (.)**</span></span> <br/> |
    
    ![Waarden voor de nieuwe records typen of plakken](../../media/5ce0b30c-b46c-4778-aa5a-fb5e2f0961c1.png)
  
7. <span data-ttu-id="d8abf-248">Wanneer u alle CNAME-records hebt toegevoegd die u nodig hebt, selecteert u **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="d8abf-248">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Selecteer Doorgaan](../../media/4978bd8b-f6a6-458d-9522-ad612b301c4a.png)
  
8. <span data-ttu-id="d8abf-250">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="d8abf-250">Select **Save Changes**.</span></span>
    
    ![Selecteer Wijzigingen opslaan](../../media/f005c38a-0d8d-4c61-bec6-15e60c89aa5a.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="d8abf-252">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="d8abf-252">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="d8abf-253"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="d8abf-253"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="d8abf-254">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="d8abf-254">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="d8abf-255">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="d8abf-255">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="d8abf-256">Als u al een SPF-record voor uw domein hebt, maakt u geen nieuwe voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d8abf-256">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="d8abf-257">Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat.</span><span class="sxs-lookup"><span data-stu-id="d8abf-257">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="d8abf-258">Volg onderstaande stappen of [bekijk de video (start op 5:35)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="d8abf-258">Follow the steps below or [watch the video (start at 5:35)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="d8abf-259">Als u wilt beginnen, gaat u [via deze koppeling](https://www.networksolutions.com/manage-it) naar uw pagina met domeinen bij Network Solutions.</span><span class="sxs-lookup"><span data-stu-id="d8abf-259">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="d8abf-260">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="d8abf-260">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d8abf-261">Voordat u de knop **Aanmelden** selecteert, kiest u **Mijn domeinnamen beheren** in de **vervolgkeuzelijst Aanmelden.**</span><span class="sxs-lookup"><span data-stu-id="d8abf-261">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Mijn domeinnamen beheren kiezen en aanmelden bij Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="d8abf-263">Schakel het selectievakje in naast de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="d8abf-263">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Het selectievakje voor uw domein selecteren](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="d8abf-265">Selecteer **DNS bewerken**.</span><span class="sxs-lookup"><span data-stu-id="d8abf-265">Select **Edit DNS**.</span></span>
    
    ![DNS bewerken selecteren](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="d8abf-267">Selecteer **Geavanceerde DNS-records beheren**.</span><span class="sxs-lookup"><span data-stu-id="d8abf-267">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="d8abf-268">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="d8abf-268">(You may have to scroll down.)</span></span>
    
    ![Selecteer Geavanceerde DNS-records beheren](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="d8abf-270">Schuif omlaag naar de sectie **Tekst (TXT Records)** en selecteer **Vervolgens TXT Records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="d8abf-270">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![TXT-records bewerken onder Tekst selecteren](../../media/a69a2631-6da2-4e81-99ab-9a9ab9b30b07.png)
  
6. <span data-ttu-id="d8abf-272">Typ of kopieer en plak de volgende waarden in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="d8abf-272">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="d8abf-273">**Host**</span><span class="sxs-lookup"><span data-stu-id="d8abf-273">**Host**</span></span>|<span data-ttu-id="d8abf-274">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d8abf-274">**TTL**</span></span>|<span data-ttu-id="d8abf-275">**Tekst**</span><span class="sxs-lookup"><span data-stu-id="d8abf-275">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="d8abf-276">(In het systeem wordt deze waarde gewijzigd in **@ (None)** wanneer u de record opslaat.)</span><span class="sxs-lookup"><span data-stu-id="d8abf-276">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="d8abf-277">3600</span><span class="sxs-lookup"><span data-stu-id="d8abf-277">3600</span></span>  <br/> |<span data-ttu-id="d8abf-278">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="d8abf-278">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="d8abf-279">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="d8abf-279">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span> |
       
    ![Waarden voor de nieuwe record typen of plakken](../../media/11564eca-e2ee-4f17-af2b-a00eb7c157db.png)
  
7. <span data-ttu-id="d8abf-281">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="d8abf-281">Select **Continue**.</span></span>
    
    ![Selecteer Doorgaan](../../media/482a8dae-0c79-47c4-8bd8-87965683de24.png)
  
8. <span data-ttu-id="d8abf-283">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="d8abf-283">Select **Save Changes**.</span></span>
    
    ![Selecteer Wijzigingen opslaan](../../media/600b8c6d-184f-4213-a50e-8f119ebf3ff0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="d8abf-285">Voeg de twee SRV-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="d8abf-285">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="d8abf-286"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="d8abf-286"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="d8abf-287">Volg onderstaande stappen of [bekijk de video (start op 6:18)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="d8abf-287">Follow the steps below or [watch the video (start at 6:18)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="d8abf-p113">Als u wilt beginnen, gaat u [via deze koppeling](https://www.networksolutions.com/manage-it) naar uw pagina met domeinen bij Network Solutions. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="d8abf-p113">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d8abf-290">Voordat u de knop **Aanmelden** selecteert, kiest u **Mijn domeinnamen beheren** in de **vervolgkeuzelijst Aanmelden.**</span><span class="sxs-lookup"><span data-stu-id="d8abf-290">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Mijn domeinnamen beheren kiezen en aanmelden bij Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="d8abf-292">Schakel het selectievakje in naast de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="d8abf-292">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Het selectievakje voor uw domein selecteren](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="d8abf-294">Selecteer **DNS bewerken**.</span><span class="sxs-lookup"><span data-stu-id="d8abf-294">Select **Edit DNS**.</span></span>
    
    ![DNS bewerken selecteren](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="d8abf-296">Selecteer **Geavanceerde DNS-records beheren**.</span><span class="sxs-lookup"><span data-stu-id="d8abf-296">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="d8abf-297">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="d8abf-297">(You may have to scroll down.)</span></span>
    
    ![Selecteer Geavanceerde DNS-records beheren](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="d8abf-299">Schuif omlaag naar de sectie **Service (SRV Records)** en selecteer **Vervolgens SRV Records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="d8abf-299">Scroll down to the **Service (SRV Records)** section, and then select **Edit SRV Records**.</span></span>
    
    ![SRV-records bewerken onder Service selecteren](../../media/9a9248ea-5de5-4e16-9364-f7600fa371f5.png)
  
6. <span data-ttu-id="d8abf-301">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de twee nieuwe records.</span><span class="sxs-lookup"><span data-stu-id="d8abf-301">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="d8abf-302">(Kies in de vervolgkeuzelijsten de waarden **Service** en **Protocol**.)</span><span class="sxs-lookup"><span data-stu-id="d8abf-302">(Choose the **Service** and **Protocol** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="d8abf-303">**Service**</span><span class="sxs-lookup"><span data-stu-id="d8abf-303">**Service**</span></span>|<span data-ttu-id="d8abf-304">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="d8abf-304">**Protocol**</span></span>|<span data-ttu-id="d8abf-305">**TTL**</span><span class="sxs-lookup"><span data-stu-id="d8abf-305">**TTL**</span></span>|<span data-ttu-id="d8abf-306">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="d8abf-306">**Priority**</span></span>|<span data-ttu-id="d8abf-307">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="d8abf-307">**Weight**</span></span>|<span data-ttu-id="d8abf-308">**Poort**</span><span class="sxs-lookup"><span data-stu-id="d8abf-308">**Port**</span></span>|<span data-ttu-id="d8abf-309">**Target**</span><span class="sxs-lookup"><span data-stu-id="d8abf-309">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="d8abf-310">_sip</span><span class="sxs-lookup"><span data-stu-id="d8abf-310">_sip</span></span>  <br/> |<span data-ttu-id="d8abf-311">_tls</span><span class="sxs-lookup"><span data-stu-id="d8abf-311">_tls</span></span>  <br/> |<span data-ttu-id="d8abf-312">3600</span><span class="sxs-lookup"><span data-stu-id="d8abf-312">3600</span></span>  <br/> |<span data-ttu-id="d8abf-313">100</span><span class="sxs-lookup"><span data-stu-id="d8abf-313">100</span></span>  <br/> |<span data-ttu-id="d8abf-314">1</span><span class="sxs-lookup"><span data-stu-id="d8abf-314">1</span></span>  <br/> |<span data-ttu-id="d8abf-315">443</span><span class="sxs-lookup"><span data-stu-id="d8abf-315">443</span></span>  <br/> |<span data-ttu-id="d8abf-316">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d8abf-316">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="d8abf-317">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="d8abf-317">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="d8abf-318">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="d8abf-318">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="d8abf-319">_tcp</span><span class="sxs-lookup"><span data-stu-id="d8abf-319">_tcp</span></span>  <br/> |<span data-ttu-id="d8abf-320">3600</span><span class="sxs-lookup"><span data-stu-id="d8abf-320">3600</span></span>  <br/> |<span data-ttu-id="d8abf-321">100</span><span class="sxs-lookup"><span data-stu-id="d8abf-321">100</span></span>  <br/> |<span data-ttu-id="d8abf-322">1</span><span class="sxs-lookup"><span data-stu-id="d8abf-322">1</span></span>  <br/> |<span data-ttu-id="d8abf-323">5061</span><span class="sxs-lookup"><span data-stu-id="d8abf-323">5061</span></span>  <br/> |<span data-ttu-id="d8abf-324">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d8abf-324">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="d8abf-325">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="d8abf-325">**This value MUST end with a period (.)**</span></span> <br/> |
       
    ![Waarden voor de nieuwe records typen of plakken](../../media/86968d1c-8e43-4e61-aeaa-37fc7d7ef7a7.png)
  
7. <span data-ttu-id="d8abf-327">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="d8abf-327">Select **Continue**.</span></span>
    
    ![Selecteer Doorgaan](../../media/bfe2c778-5d2b-4bb6-a79d-c3ff9caf9e1e.png)
  
8. <span data-ttu-id="d8abf-329">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="d8abf-329">Select **Save Changes**.</span></span>
    
    ![Selecteer Wijzigingen opslaan](../../media/6d323126-0ebe-45ab-8567-c234711d84c7.png)
  
> [!NOTE]
>  <span data-ttu-id="d8abf-p114">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d8abf-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
