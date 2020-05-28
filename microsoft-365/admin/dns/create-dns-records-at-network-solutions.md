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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1dc55f9f-5309-450f-acc3-b2b4119c8be3
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services bij Network Solutions voor Microsoft.
ms.openlocfilehash: 0804abef84dc97a290d3f8084cd20e0ad3d3c5ef
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400350"
---
# <a name="create-dns-records-at-network-solutions-for-microsoft"></a><span data-ttu-id="6a4a3-103">DNS-records maken bij Network Solutions voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="6a4a3-103">Create DNS records at Network Solutions for Microsoft</span></span>

 <span data-ttu-id="6a4a3-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="6a4a3-105">Als Network Solutions uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-105">If Network Solutions is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="6a4a3-106">Dit zijn de belangrijkste records om toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-106">These are the main records to add.</span></span> <span data-ttu-id="6a4a3-107">Volg onderstaande stappen of [bekijk de video](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="6a4a3-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span> 
  
- [<span data-ttu-id="6a4a3-108">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="6a4a3-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="6a4a3-109">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="6a4a3-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="6a4a3-110">De CNAME-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="6a4a3-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="6a4a3-111">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="6a4a3-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="6a4a3-112">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="6a4a3-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="6a4a3-113">Nadat u deze records hebt toegevoegd bij Network Solutions, wordt uw domein ingesteld voor gebruik met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-113">After you add these records at Network Solutions, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="6a4a3-p102">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6a4a3-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="6a4a3-117">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="6a4a3-117">Add a TXT record for verification</span></span>
<span data-ttu-id="6a4a3-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="6a4a3-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="6a4a3-p103">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6a4a3-p104">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="6a4a3-123">Volg onderstaande stappen of [bekijk de video (start op 0:47)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="6a4a3-123">Follow the steps below or [watch the video (start at 0:47)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="6a4a3-124">Als u wilt beginnen, gaat u [via deze koppeling](https://www.networksolutions.com/manage-it) naar uw pagina met domeinen bij Network Solutions.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-124">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="6a4a3-125">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-125">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="6a4a3-126">Voordat u de knop **Aanmelden** selecteert, kiest u **Mijn domeinnamen beheren** in de **vervolgkeuzelijst Aanmelden.**</span><span class="sxs-lookup"><span data-stu-id="6a4a3-126">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Mijn domeinnamen beheren kiezen en aanmelden bij Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="6a4a3-128">Schakel het selectievakje in naast de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-128">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Het selectievakje voor uw domein selecteren](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="6a4a3-130">Selecteer **DNS bewerken**.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-130">Select **Edit DNS**.</span></span>
    
    ![DNS bewerken selecteren](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="6a4a3-132">Selecteer **Geavanceerde DNS-records beheren**.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-132">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="6a4a3-133">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="6a4a3-133">(You may have to scroll down.)</span></span>
    
    ![Selecteer Geavanceerde DNS-records beheren](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="6a4a3-135">Schuif omlaag naar de sectie **Tekst (TXT Records)** en selecteer **Vervolgens TXT Records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-135">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![TXT-records bewerken selecteren](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="6a4a3-137">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-137">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
    |<span data-ttu-id="6a4a3-138">**Host**</span><span class="sxs-lookup"><span data-stu-id="6a4a3-138">**Host**</span></span>|<span data-ttu-id="6a4a3-139">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6a4a3-139">**TTL**</span></span>|<span data-ttu-id="6a4a3-140">**Tekst**</span><span class="sxs-lookup"><span data-stu-id="6a4a3-140">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="6a4a3-141">(In het systeem wordt deze waarde gewijzigd in **@ (None)** wanneer u de record opslaat.)</span><span class="sxs-lookup"><span data-stu-id="6a4a3-141">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="6a4a3-142">3600</span><span class="sxs-lookup"><span data-stu-id="6a4a3-142">3600</span></span>  <br/> |<span data-ttu-id="6a4a3-143">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="6a4a3-143">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="6a4a3-144">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-144">**Note:** This is an example.</span></span> <span data-ttu-id="6a4a3-145">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-145">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="6a4a3-146">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="6a4a3-146">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)   |
       
    ![Waarden typen of plakken in de vakken voor de nieuwe record](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="6a4a3-148">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-148">Select **Continue**.</span></span>
    
    ![Selecteer Doorgaan](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="6a4a3-150">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-150">Select **Save Changes**.</span></span>
    
    ![Selecteer Wijzigingen opslaan](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="6a4a3-152">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-152">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="6a4a3-153">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-153">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="6a4a3-154">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-154">When Microsoft finds the correct TXT record, your domain is verified.</span></span>

1. <span data-ttu-id="6a4a3-155">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-155">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="6a4a3-156">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-156">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="6a4a3-157">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-157">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="6a4a3-158">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-158">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="6a4a3-p107">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6a4a3-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="6a4a3-162">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="6a4a3-162">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="6a4a3-163"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="6a4a3-163"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="6a4a3-164">Volg onderstaande stappen of [bekijk de video (start op 3:51)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="6a4a3-164">Follow the steps below or [watch the video (start at 3:51)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="6a4a3-165">Als u wilt beginnen, gaat u [via deze koppeling](https://www.networksolutions.com/manage-it) naar uw pagina met domeinen bij Network Solutions.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-165">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="6a4a3-166">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-166">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="6a4a3-167">Voordat u de knop **Aanmelden** selecteert, kiest u **Mijn domeinnamen beheren** in de **vervolgkeuzelijst Aanmelden.**</span><span class="sxs-lookup"><span data-stu-id="6a4a3-167">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Mijn domeinnamen beheren kiezen en aanmelden bij Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="6a4a3-169">Schakel het selectievakje in naast de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-169">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Het selectievakje voor uw domein selecteren](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="6a4a3-171">Selecteer **DNS bewerken**.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-171">Select **Edit DNS**.</span></span>
    
    ![DNS bewerken selecteren](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="6a4a3-173">Selecteer **Geavanceerde DNS-records beheren**.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-173">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="6a4a3-174">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="6a4a3-174">(You may have to scroll down.)</span></span>
    
    ![Selecteer Geavanceerde DNS-records beheren](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="6a4a3-176">Schuif omlaag naar de sectie **Mail Servers (MX Records)** en selecteer **VERVOLGENS MX Records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-176">Scroll down to the **Mail Servers (MX Records)** section, and then select **Edit MX Records**.</span></span>
    
    ![MX-records bewerken selecteren](../../media/74b4e412-9073-4d2d-8710-fe340b223798.png)
  
6. <span data-ttu-id="6a4a3-178">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-178">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="6a4a3-179">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="6a4a3-179">**Priority**</span></span>|<span data-ttu-id="6a4a3-180">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6a4a3-180">**TTL**</span></span>|<span data-ttu-id="6a4a3-181">**Mail Server**</span><span class="sxs-lookup"><span data-stu-id="6a4a3-181">**Mail Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="6a4a3-182">10</span><span class="sxs-lookup"><span data-stu-id="6a4a3-182">10</span></span>  <br/> <span data-ttu-id="6a4a3-183">Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="6a4a3-183">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="6a4a3-184">3600</span><span class="sxs-lookup"><span data-stu-id="6a4a3-184">3600</span></span>  <br/> | <span data-ttu-id="6a4a3-185">*\<domain-key\>* mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-185">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="6a4a3-186">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="6a4a3-186">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="6a4a3-187">**Let op:** Haal uw *\<domain-key\>* van uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-187">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span> [<span data-ttu-id="6a4a3-188">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="6a4a3-188">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![Waarden typen of plakken in de vakken voor de nieuwe record](../../media/0bb96872-cc6e-4dfa-a649-fb7efbbf0012.png)
  
7. <span data-ttu-id="6a4a3-190">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-190">Select **Continue**.</span></span>
    
    ![Selecteer Doorgaan](../../media/963f758b-e79d-4452-8340-7eba8a3972c9.png)
  
8. <span data-ttu-id="6a4a3-192">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-192">Select **Save Changes**.</span></span>
    
    ![Selecteer Wijzigingen opslaan](../../media/7c2f784a-6dee-4364-866c-ad7202ef1fc2.png)
  
9. <span data-ttu-id="6a4a3-194">Als er andere MX-records zijn, verwijdert u deze allemaal door voor elke record **Delete** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-194">If there are any other MX records, delete all of them by selecting **Delete** for each record.</span></span> 
    
    ![Select the Delete check box for other MX records](../../media/709d6133-9f5d-490a-a91e-95e21ca94695.png)
  
10. <span data-ttu-id="6a4a3-196">Wanneer ze allemaal zijn geselecteerd, selecteert u **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-196">When they are all selected, select **Continue**.</span></span>
    
    ![Selecteer Doorgaan](../../media/4710f988-0bbc-4ba7-bf31-ca2392b2900e.png)
  
11. <span data-ttu-id="6a4a3-198">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-198">Select **Save Changes**.</span></span>
    
    ![Selecteer Wijzigingen opslaan](../../media/24432ec6-666b-4612-9488-37c06437959b.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="6a4a3-200">De CNAME-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="6a4a3-200">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="6a4a3-201"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="6a4a3-201"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="6a4a3-202">Volg onderstaande stappen of [bekijk de video (start op 4:43)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="6a4a3-202">Follow the steps below or [watch the video (start at 4:43)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="6a4a3-203">Als u wilt beginnen, gaat u [via deze koppeling](https://www.networksolutions.com/manage-it) naar uw pagina met domeinen bij Network Solutions.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-203">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="6a4a3-204">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-204">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="6a4a3-205">Voordat u de knop **Aanmelden** selecteert, kiest u **Mijn domeinnamen beheren** in de **vervolgkeuzelijst Aanmelden.**</span><span class="sxs-lookup"><span data-stu-id="6a4a3-205">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Mijn domeinnamen beheren kiezen en aanmelden bij Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="6a4a3-207">Schakel het selectievakje in naast de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-207">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Het selectievakje voor uw domein selecteren](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="6a4a3-209">Selecteer **DNS bewerken**.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-209">Select **Edit DNS**.</span></span>
    
    ![DNS bewerken selecteren](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="6a4a3-211">Selecteer **Geavanceerde DNS-records beheren**.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-211">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="6a4a3-212">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="6a4a3-212">(You may have to scroll down.)</span></span>
    
    ![Selecteer Geavanceerde DNS-records beheren](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="6a4a3-214">Schuif omlaag naar de sectie **Host Aliassen (CNAME Records)** en selecteer **CNAME Records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-214">Scroll down to the **Host Aliases (CNAME Records)** section, and then select **Edit CNAME Records**.</span></span>
    
    ![CNAME-records bewerken onder Host Aliassen selecteren](../../media/2d0a4666-8d40-48f4-886c-64a5157baaf5.png)
  
6. <span data-ttu-id="6a4a3-216">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de vier nieuwe records.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-216">In the boxes for the four new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="6a4a3-217">**Alias**</span><span class="sxs-lookup"><span data-stu-id="6a4a3-217">**Alias**</span></span>|<span data-ttu-id="6a4a3-218">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6a4a3-218">**TTL**</span></span>|<span data-ttu-id="6a4a3-219">**Refers to Host Name**</span><span class="sxs-lookup"><span data-stu-id="6a4a3-219">**Refers to Host Name**</span></span>|<span data-ttu-id="6a4a3-220">**Other Host          (selecteer het keuzerondje **Other Host**)**</span><span class="sxs-lookup"><span data-stu-id="6a4a3-220">**Other Host          (select the **Other Host** option button)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6a4a3-221">autodiscover</span><span class="sxs-lookup"><span data-stu-id="6a4a3-221">autodiscover</span></span>  <br/> |<span data-ttu-id="6a4a3-222">3600</span><span class="sxs-lookup"><span data-stu-id="6a4a3-222">3600</span></span>  <br/> |<span data-ttu-id="6a4a3-223">(Geen instelling)</span><span class="sxs-lookup"><span data-stu-id="6a4a3-223">(No setting)</span></span>  <br/> |<span data-ttu-id="6a4a3-224">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-224">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="6a4a3-225">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="6a4a3-225">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="6a4a3-226">sip</span><span class="sxs-lookup"><span data-stu-id="6a4a3-226">sip</span></span>  <br/> |<span data-ttu-id="6a4a3-227">3600</span><span class="sxs-lookup"><span data-stu-id="6a4a3-227">3600</span></span>  <br/> |<span data-ttu-id="6a4a3-228">(Geen instelling)</span><span class="sxs-lookup"><span data-stu-id="6a4a3-228">(No setting)</span></span>  <br/> |<span data-ttu-id="6a4a3-229">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-229">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="6a4a3-230">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="6a4a3-230">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="6a4a3-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="6a4a3-231">lyncdiscover</span></span>  <br/> |<span data-ttu-id="6a4a3-232">3600</span><span class="sxs-lookup"><span data-stu-id="6a4a3-232">3600</span></span>  <br/> |<span data-ttu-id="6a4a3-233">(Geen instelling)</span><span class="sxs-lookup"><span data-stu-id="6a4a3-233">(No setting)</span></span>  <br/> |<span data-ttu-id="6a4a3-234">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-234">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="6a4a3-235">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="6a4a3-235">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="6a4a3-236">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="6a4a3-236">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="6a4a3-237">3600</span><span class="sxs-lookup"><span data-stu-id="6a4a3-237">3600</span></span>  <br/> |<span data-ttu-id="6a4a3-238">(Geen instelling)</span><span class="sxs-lookup"><span data-stu-id="6a4a3-238">(No setting)</span></span>  <br/> |<span data-ttu-id="6a4a3-239">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="6a4a3-239">enterpriseregistration.windows.net</span></span>  <br/> <span data-ttu-id="6a4a3-240">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="6a4a3-240">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="6a4a3-241">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="6a4a3-241">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="6a4a3-242">3600</span><span class="sxs-lookup"><span data-stu-id="6a4a3-242">3600</span></span>  <br/> |<span data-ttu-id="6a4a3-243">(Geen instelling)</span><span class="sxs-lookup"><span data-stu-id="6a4a3-243">(No setting)</span></span>  <br/> |<span data-ttu-id="6a4a3-244">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="6a4a3-244">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> <span data-ttu-id="6a4a3-245">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="6a4a3-245">**This value MUST end with a period (.)**</span></span> <br/> |
    
    ![Waarden voor de nieuwe records typen of plakken](../../media/5ce0b30c-b46c-4778-aa5a-fb5e2f0961c1.png)
  
7. <span data-ttu-id="6a4a3-247">Wanneer u alle CNAME-records hebt toegevoegd die u nodig hebt, selecteert u **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-247">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Selecteer Doorgaan](../../media/4978bd8b-f6a6-458d-9522-ad612b301c4a.png)
  
8. <span data-ttu-id="6a4a3-249">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-249">Select **Save Changes**.</span></span>
    
    ![Selecteer Wijzigingen opslaan](../../media/f005c38a-0d8d-4c61-bec6-15e60c89aa5a.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="6a4a3-251">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="6a4a3-251">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="6a4a3-252"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="6a4a3-252"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="6a4a3-253">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-253">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="6a4a3-254">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-254">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="6a4a3-255">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-255">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="6a4a3-256">Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-256">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="6a4a3-257">Volg onderstaande stappen of [bekijk de video (start op 5:35)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="6a4a3-257">Follow the steps below or [watch the video (start at 5:35)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="6a4a3-258">Als u wilt beginnen, gaat u [via deze koppeling](https://www.networksolutions.com/manage-it) naar uw pagina met domeinen bij Network Solutions.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-258">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="6a4a3-259">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-259">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="6a4a3-260">Voordat u de knop **Aanmelden** selecteert, kiest u **Mijn domeinnamen beheren** in de **vervolgkeuzelijst Aanmelden.**</span><span class="sxs-lookup"><span data-stu-id="6a4a3-260">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Mijn domeinnamen beheren kiezen en aanmelden bij Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="6a4a3-262">Schakel het selectievakje in naast de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-262">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Het selectievakje voor uw domein selecteren](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="6a4a3-264">Selecteer **DNS bewerken**.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-264">Select **Edit DNS**.</span></span>
    
    ![DNS bewerken selecteren](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="6a4a3-266">Selecteer **Geavanceerde DNS-records beheren**.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-266">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="6a4a3-267">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="6a4a3-267">(You may have to scroll down.)</span></span>
    
    ![Selecteer Geavanceerde DNS-records beheren](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="6a4a3-269">Schuif omlaag naar de sectie **Tekst (TXT Records)** en selecteer **Vervolgens TXT Records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-269">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![TXT-records bewerken onder Tekst selecteren](../../media/a69a2631-6da2-4e81-99ab-9a9ab9b30b07.png)
  
6. <span data-ttu-id="6a4a3-271">Typ of kopieer en plak de volgende waarden in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-271">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="6a4a3-272">**Host**</span><span class="sxs-lookup"><span data-stu-id="6a4a3-272">**Host**</span></span>|<span data-ttu-id="6a4a3-273">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6a4a3-273">**TTL**</span></span>|<span data-ttu-id="6a4a3-274">**Tekst**</span><span class="sxs-lookup"><span data-stu-id="6a4a3-274">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="6a4a3-275">(In het systeem wordt deze waarde gewijzigd in **@ (None)** wanneer u de record opslaat.)</span><span class="sxs-lookup"><span data-stu-id="6a4a3-275">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="6a4a3-276">3600</span><span class="sxs-lookup"><span data-stu-id="6a4a3-276">3600</span></span>  <br/> |<span data-ttu-id="6a4a3-277">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="6a4a3-277">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="6a4a3-278">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-278">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span> |
       
    ![Waarden voor de nieuwe record typen of plakken](../../media/11564eca-e2ee-4f17-af2b-a00eb7c157db.png)
  
7. <span data-ttu-id="6a4a3-280">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-280">Select **Continue**.</span></span>
    
    ![Selecteer Doorgaan](../../media/482a8dae-0c79-47c4-8bd8-87965683de24.png)
  
8. <span data-ttu-id="6a4a3-282">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-282">Select **Save Changes**.</span></span>
    
    ![Selecteer Wijzigingen opslaan](../../media/600b8c6d-184f-4213-a50e-8f119ebf3ff0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="6a4a3-284">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="6a4a3-284">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="6a4a3-285"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="6a4a3-285"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="6a4a3-286">Volg onderstaande stappen of [bekijk de video (start op 6:18)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="6a4a3-286">Follow the steps below or [watch the video (start at 6:18)](https://support.office.com/article/Video-Create-DNS-records-at-Network-Solutions-for-Office-365-c49698c2-6991-47fb-b5ac-18e49a505099?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="6a4a3-p113">Als u wilt beginnen, gaat u [via deze koppeling](https://www.networksolutions.com/manage-it) naar uw pagina met domeinen bij Network Solutions. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-p113">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="6a4a3-289">Voordat u de knop **Aanmelden** selecteert, kiest u **Mijn domeinnamen beheren** in de **vervolgkeuzelijst Aanmelden.**</span><span class="sxs-lookup"><span data-stu-id="6a4a3-289">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Mijn domeinnamen beheren kiezen en aanmelden bij Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="6a4a3-291">Schakel het selectievakje in naast de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-291">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Het selectievakje voor uw domein selecteren](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="6a4a3-293">Selecteer **DNS bewerken**.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-293">Select **Edit DNS**.</span></span>
    
    ![DNS bewerken selecteren](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="6a4a3-295">Selecteer **Geavanceerde DNS-records beheren**.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-295">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="6a4a3-296">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="6a4a3-296">(You may have to scroll down.)</span></span>
    
    ![Selecteer Geavanceerde DNS-records beheren](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="6a4a3-298">Schuif omlaag naar de sectie **Service (SRV Records)** en selecteer **Vervolgens SRV Records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-298">Scroll down to the **Service (SRV Records)** section, and then select **Edit SRV Records**.</span></span>
    
    ![SRV-records bewerken onder Service selecteren](../../media/9a9248ea-5de5-4e16-9364-f7600fa371f5.png)
  
6. <span data-ttu-id="6a4a3-300">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de twee nieuwe records.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-300">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="6a4a3-301">(Kies in de vervolgkeuzelijsten de waarden **Service** en **Protocol**.)</span><span class="sxs-lookup"><span data-stu-id="6a4a3-301">(Choose the **Service** and **Protocol** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="6a4a3-302">**Service**</span><span class="sxs-lookup"><span data-stu-id="6a4a3-302">**Service**</span></span>|<span data-ttu-id="6a4a3-303">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="6a4a3-303">**Protocol**</span></span>|<span data-ttu-id="6a4a3-304">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6a4a3-304">**TTL**</span></span>|<span data-ttu-id="6a4a3-305">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="6a4a3-305">**Priority**</span></span>|<span data-ttu-id="6a4a3-306">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="6a4a3-306">**Weight**</span></span>|<span data-ttu-id="6a4a3-307">**Poort**</span><span class="sxs-lookup"><span data-stu-id="6a4a3-307">**Port**</span></span>|<span data-ttu-id="6a4a3-308">**Target**</span><span class="sxs-lookup"><span data-stu-id="6a4a3-308">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6a4a3-309">_sip</span><span class="sxs-lookup"><span data-stu-id="6a4a3-309">_sip</span></span>  <br/> |<span data-ttu-id="6a4a3-310">_tls</span><span class="sxs-lookup"><span data-stu-id="6a4a3-310">_tls</span></span>  <br/> |<span data-ttu-id="6a4a3-311">3600</span><span class="sxs-lookup"><span data-stu-id="6a4a3-311">3600</span></span>  <br/> |<span data-ttu-id="6a4a3-312">100</span><span class="sxs-lookup"><span data-stu-id="6a4a3-312">100</span></span>  <br/> |<span data-ttu-id="6a4a3-313">1</span><span class="sxs-lookup"><span data-stu-id="6a4a3-313">1</span></span>  <br/> |<span data-ttu-id="6a4a3-314">443</span><span class="sxs-lookup"><span data-stu-id="6a4a3-314">443</span></span>  <br/> |<span data-ttu-id="6a4a3-315">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-315">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="6a4a3-316">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="6a4a3-316">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="6a4a3-317">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="6a4a3-317">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="6a4a3-318">_tcp</span><span class="sxs-lookup"><span data-stu-id="6a4a3-318">_tcp</span></span>  <br/> |<span data-ttu-id="6a4a3-319">3600</span><span class="sxs-lookup"><span data-stu-id="6a4a3-319">3600</span></span>  <br/> |<span data-ttu-id="6a4a3-320">100</span><span class="sxs-lookup"><span data-stu-id="6a4a3-320">100</span></span>  <br/> |<span data-ttu-id="6a4a3-321">1</span><span class="sxs-lookup"><span data-stu-id="6a4a3-321">1</span></span>  <br/> |<span data-ttu-id="6a4a3-322">5061</span><span class="sxs-lookup"><span data-stu-id="6a4a3-322">5061</span></span>  <br/> |<span data-ttu-id="6a4a3-323">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-323">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="6a4a3-324">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="6a4a3-324">**This value MUST end with a period (.)**</span></span> <br/> |
       
    ![Waarden voor de nieuwe records typen of plakken](../../media/86968d1c-8e43-4e61-aeaa-37fc7d7ef7a7.png)
  
7. <span data-ttu-id="6a4a3-326">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-326">Select **Continue**.</span></span>
    
    ![Selecteer Doorgaan](../../media/bfe2c778-5d2b-4bb6-a79d-c3ff9caf9e1e.png)
  
8. <span data-ttu-id="6a4a3-328">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6a4a3-328">Select **Save Changes**.</span></span>
    
    ![Selecteer Wijzigingen opslaan](../../media/6d323126-0ebe-45ab-8567-c234711d84c7.png)
  
> [!NOTE]
>  <span data-ttu-id="6a4a3-p114">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6a4a3-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
