---
title: DNS-records maken bij Network Solutions for Microsoft
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
description: Meer informatie over het verifiëren van uw domein en het instellen van DNS-records voor e-mail, Skype voor Bedrijven Online en andere services bij Network Solutions for Microsoft.
ms.openlocfilehash: 25e85bf30527b49ada711af9ba5c418409acd24c
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780335"
---
# <a name="create-dns-records-at-network-solutions-for-microsoft"></a><span data-ttu-id="f0708-103">DNS-records maken bij Network Solutions for Microsoft</span><span class="sxs-lookup"><span data-stu-id="f0708-103">Create DNS records at Network Solutions for Microsoft</span></span>

 <span data-ttu-id="f0708-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="f0708-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="f0708-105">Als Network Solutions uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="f0708-105">If Network Solutions is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="f0708-106">Dit zijn de belangrijkste records om toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="f0708-106">These are the main records to add.</span></span> <span data-ttu-id="f0708-107">Volg onderstaande stappen of [bekijk de video](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span><span class="sxs-lookup"><span data-stu-id="f0708-107">Follow the steps below or [watch the video](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span></span> 
  
- [<span data-ttu-id="f0708-108">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="f0708-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="f0708-109">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="f0708-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="f0708-110">De CNAME-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="f0708-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="f0708-111">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="f0708-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="f0708-112">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="f0708-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="f0708-113">Nadat u deze records hebt toegevoegd bij Network Solutions, wordt uw domein ingesteld om te werken met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="f0708-113">After you add these records at Network Solutions, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="f0708-p102">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f0708-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="f0708-117">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="f0708-117">Add a TXT record for verification</span></span>
<span data-ttu-id="f0708-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="f0708-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="f0708-p103">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="f0708-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f0708-p104">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="f0708-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="f0708-123">Volg onderstaande stappen of [bekijk de video (start op 0:47)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span><span class="sxs-lookup"><span data-stu-id="f0708-123">Follow the steps below or [watch the video (start at 0:47)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span></span>
  
1. <span data-ttu-id="f0708-124">Als u wilt beginnen, gaat u [via deze koppeling](https://www.networksolutions.com/manage-it) naar uw pagina met domeinen bij Network Solutions.</span><span class="sxs-lookup"><span data-stu-id="f0708-124">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="f0708-125">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="f0708-125">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="f0708-126">Voordat u de **knop Aanmelden** selecteert, kiest u Eerst **Mijn domeinnamen beheren** in de vervolgkeuzelijst Aanmelden **bij:**</span><span class="sxs-lookup"><span data-stu-id="f0708-126">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Mijn domeinnamen beheren kiezen en aanmelden bij Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="f0708-128">Schakel het selectievakje in naast de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="f0708-128">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Het selectievakje voor uw domein selecteren](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="f0708-130">Selecteer **DNS bewerken**.</span><span class="sxs-lookup"><span data-stu-id="f0708-130">Select **Edit DNS**.</span></span>
    
    ![DNS bewerken selecteren](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="f0708-132">Selecteer **Geavanceerde DNS-records beheren**.</span><span class="sxs-lookup"><span data-stu-id="f0708-132">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="f0708-133">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="f0708-133">(You may have to scroll down.)</span></span>
    
    ![Selecteer Geavanceerde DNS-records beheren](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="f0708-135">Schuif omlaag naar de sectie **Tekst (TXT Records)** en selecteer **TXT-records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="f0708-135">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![TXT-records bewerken selecteren](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="f0708-137">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="f0708-137">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
    |<span data-ttu-id="f0708-138">**Host**</span><span class="sxs-lookup"><span data-stu-id="f0708-138">**Host**</span></span>|<span data-ttu-id="f0708-139">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f0708-139">**TTL**</span></span>|<span data-ttu-id="f0708-140">**Tekst**</span><span class="sxs-lookup"><span data-stu-id="f0708-140">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="f0708-141">(In het systeem wordt deze waarde gewijzigd in **@ (None)** wanneer u de record opslaat.)</span><span class="sxs-lookup"><span data-stu-id="f0708-141">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="f0708-142">3600</span><span class="sxs-lookup"><span data-stu-id="f0708-142">3600</span></span>  <br/> |<span data-ttu-id="f0708-143">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="f0708-143">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="f0708-144">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="f0708-144">**Note:** This is an example.</span></span> <span data-ttu-id="f0708-145">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="f0708-145">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="f0708-146">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="f0708-146">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)   |
       
    ![Waarden typen of plakken in de vakken voor de nieuwe record](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="f0708-148">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="f0708-148">Select **Continue**.</span></span>
    
    ![Selecteer Doorgaan](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="f0708-150">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f0708-150">Select **Save Changes**.</span></span>
    
    ![Wijzigingen opslaan selecteren](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="f0708-152">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="f0708-152">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="f0708-153">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="f0708-153">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="f0708-154">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="f0708-154">When Microsoft finds the correct TXT record, your domain is verified.</span></span>

1. <span data-ttu-id="f0708-155">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="f0708-155">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="f0708-156">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="f0708-156">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="f0708-157">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="f0708-157">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="f0708-158">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="f0708-158">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="f0708-p107">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f0708-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="f0708-162">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="f0708-162">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="f0708-163"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="f0708-163"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="f0708-164">Volg onderstaande stappen of [bekijk de video (start op 3:51)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span><span class="sxs-lookup"><span data-stu-id="f0708-164">Follow the steps below or [watch the video (start at 3:51)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span></span>
  
1. <span data-ttu-id="f0708-165">Als u wilt beginnen, gaat u [via deze koppeling](https://www.networksolutions.com/manage-it) naar uw pagina met domeinen bij Network Solutions.</span><span class="sxs-lookup"><span data-stu-id="f0708-165">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="f0708-166">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="f0708-166">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="f0708-167">Voordat u de **knop Aanmelden** selecteert, kiest u Eerst **Mijn domeinnamen beheren** in de vervolgkeuzelijst Aanmelden **bij:**</span><span class="sxs-lookup"><span data-stu-id="f0708-167">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Mijn domeinnamen beheren kiezen en aanmelden bij Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="f0708-169">Schakel het selectievakje in naast de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="f0708-169">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Het selectievakje voor uw domein selecteren](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="f0708-171">Selecteer **DNS bewerken**.</span><span class="sxs-lookup"><span data-stu-id="f0708-171">Select **Edit DNS**.</span></span>
    
    ![DNS bewerken selecteren](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="f0708-173">Selecteer **Geavanceerde DNS-records beheren**.</span><span class="sxs-lookup"><span data-stu-id="f0708-173">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="f0708-174">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="f0708-174">(You may have to scroll down.)</span></span>
    
    ![Selecteer Geavanceerde DNS-records beheren](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="f0708-176">Schuif omlaag naar de sectie **E-mailservers (MX Records)** en selecteer **MX-records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="f0708-176">Scroll down to the **Mail Servers (MX Records)** section, and then select **Edit MX Records**.</span></span>
    
    ![MX-records bewerken selecteren](../../media/74b4e412-9073-4d2d-8710-fe340b223798.png)
  
6. <span data-ttu-id="f0708-178">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="f0708-178">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="f0708-179">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="f0708-179">**Priority**</span></span>|<span data-ttu-id="f0708-180">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f0708-180">**TTL**</span></span>|<span data-ttu-id="f0708-181">**Mail Server**</span><span class="sxs-lookup"><span data-stu-id="f0708-181">**Mail Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="f0708-182">10</span><span class="sxs-lookup"><span data-stu-id="f0708-182">10</span></span>  <br/> <span data-ttu-id="f0708-183">Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="f0708-183">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="f0708-184">3600</span><span class="sxs-lookup"><span data-stu-id="f0708-184">3600</span></span>  <br/> | <span data-ttu-id="f0708-185">*\<domain-key\>* mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="f0708-185">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="f0708-186">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="f0708-186">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="f0708-187">**Let op:** Haal je *\<domain-key\>* van je Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="f0708-187">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span> [<span data-ttu-id="f0708-188">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="f0708-188">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![Waarden typen of plakken in de vakken voor de nieuwe record](../../media/0bb96872-cc6e-4dfa-a649-fb7efbbf0012.png)
  
7. <span data-ttu-id="f0708-190">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="f0708-190">Select **Continue**.</span></span>
    
    ![Selecteer Doorgaan](../../media/963f758b-e79d-4452-8340-7eba8a3972c9.png)
  
8. <span data-ttu-id="f0708-192">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f0708-192">Select **Save Changes**.</span></span>
    
    ![Wijzigingen opslaan selecteren](../../media/7c2f784a-6dee-4364-866c-ad7202ef1fc2.png)
  
9. <span data-ttu-id="f0708-194">Als er andere MX-records zijn, verwijdert u deze allemaal door voor elke record **Delete** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="f0708-194">If there are any other MX records, delete all of them by selecting **Delete** for each record.</span></span> 
    
    ![Select the Delete check box for other MX records](../../media/709d6133-9f5d-490a-a91e-95e21ca94695.png)
  
10. <span data-ttu-id="f0708-196">Wanneer ze allemaal zijn geselecteerd, selecteert u **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="f0708-196">When they are all selected, select **Continue**.</span></span>
    
    ![Selecteer Doorgaan](../../media/4710f988-0bbc-4ba7-bf31-ca2392b2900e.png)
  
11. <span data-ttu-id="f0708-198">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f0708-198">Select **Save Changes**.</span></span>
    
    ![Wijzigingen opslaan selecteren](../../media/24432ec6-666b-4612-9488-37c06437959b.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="f0708-200">De CNAME-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="f0708-200">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="f0708-201"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="f0708-201"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="f0708-202">Volg onderstaande stappen of [bekijk de video (start op 4:43)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span><span class="sxs-lookup"><span data-stu-id="f0708-202">Follow the steps below or [watch the video (start at 4:43)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span></span>
  
1. <span data-ttu-id="f0708-203">Als u wilt beginnen, gaat u [via deze koppeling](https://www.networksolutions.com/manage-it) naar uw pagina met domeinen bij Network Solutions.</span><span class="sxs-lookup"><span data-stu-id="f0708-203">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="f0708-204">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="f0708-204">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="f0708-205">Voordat u de **knop Aanmelden** selecteert, kiest u Eerst **Mijn domeinnamen beheren** in de vervolgkeuzelijst Aanmelden **bij:**</span><span class="sxs-lookup"><span data-stu-id="f0708-205">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Mijn domeinnamen beheren kiezen en aanmelden bij Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="f0708-207">Schakel het selectievakje in naast de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="f0708-207">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Het selectievakje voor uw domein selecteren](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="f0708-209">Selecteer **DNS bewerken**.</span><span class="sxs-lookup"><span data-stu-id="f0708-209">Select **Edit DNS**.</span></span>
    
    ![DNS bewerken selecteren](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="f0708-211">Selecteer **Geavanceerde DNS-records beheren**.</span><span class="sxs-lookup"><span data-stu-id="f0708-211">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="f0708-212">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="f0708-212">(You may have to scroll down.)</span></span>
    
    ![Selecteer Geavanceerde DNS-records beheren](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="f0708-214">Schuif omlaag naar de sectie **Host Aliases (CNAME Records)** en selecteer **CNAME Records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="f0708-214">Scroll down to the **Host Aliases (CNAME Records)** section, and then select **Edit CNAME Records**.</span></span>
    
    ![CNAME-records bewerken selecteren onder hostaliassen](../../media/2d0a4666-8d40-48f4-886c-64a5157baaf5.png)
  
6. <span data-ttu-id="f0708-216">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de vier nieuwe records.</span><span class="sxs-lookup"><span data-stu-id="f0708-216">In the boxes for the four new records, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="f0708-217">**Alias**</span><span class="sxs-lookup"><span data-stu-id="f0708-217">**Alias**</span></span>|<span data-ttu-id="f0708-218">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f0708-218">**TTL**</span></span>|<span data-ttu-id="f0708-219">**Refers to Host Name**</span><span class="sxs-lookup"><span data-stu-id="f0708-219">**Refers to Host Name**</span></span>|<span data-ttu-id="f0708-220">**Other Host          (selecteer het keuzerondje **Other Host**)**</span><span class="sxs-lookup"><span data-stu-id="f0708-220">**Other Host          (select the **Other Host** option button)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f0708-221">autodiscover</span><span class="sxs-lookup"><span data-stu-id="f0708-221">autodiscover</span></span>  <br/> |<span data-ttu-id="f0708-222">3600</span><span class="sxs-lookup"><span data-stu-id="f0708-222">3600</span></span>  <br/> |<span data-ttu-id="f0708-223">(Geen instelling)</span><span class="sxs-lookup"><span data-stu-id="f0708-223">(No setting)</span></span>  <br/> |<span data-ttu-id="f0708-224">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="f0708-224">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="f0708-225">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="f0708-225">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="f0708-226">sip</span><span class="sxs-lookup"><span data-stu-id="f0708-226">sip</span></span>  <br/> |<span data-ttu-id="f0708-227">3600</span><span class="sxs-lookup"><span data-stu-id="f0708-227">3600</span></span>  <br/> |<span data-ttu-id="f0708-228">(Geen instelling)</span><span class="sxs-lookup"><span data-stu-id="f0708-228">(No setting)</span></span>  <br/> |<span data-ttu-id="f0708-229">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="f0708-229">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="f0708-230">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="f0708-230">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="f0708-231">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="f0708-231">lyncdiscover</span></span>  <br/> |<span data-ttu-id="f0708-232">3600</span><span class="sxs-lookup"><span data-stu-id="f0708-232">3600</span></span>  <br/> |<span data-ttu-id="f0708-233">(Geen instelling)</span><span class="sxs-lookup"><span data-stu-id="f0708-233">(No setting)</span></span>  <br/> |<span data-ttu-id="f0708-234">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="f0708-234">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="f0708-235">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="f0708-235">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="f0708-236">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="f0708-236">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="f0708-237">3600</span><span class="sxs-lookup"><span data-stu-id="f0708-237">3600</span></span>  <br/> |<span data-ttu-id="f0708-238">(Geen instelling)</span><span class="sxs-lookup"><span data-stu-id="f0708-238">(No setting)</span></span>  <br/> |<span data-ttu-id="f0708-239">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="f0708-239">enterpriseregistration.windows.net</span></span>  <br/> <span data-ttu-id="f0708-240">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="f0708-240">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="f0708-241">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="f0708-241">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="f0708-242">3600</span><span class="sxs-lookup"><span data-stu-id="f0708-242">3600</span></span>  <br/> |<span data-ttu-id="f0708-243">(Geen instelling)</span><span class="sxs-lookup"><span data-stu-id="f0708-243">(No setting)</span></span>  <br/> |<span data-ttu-id="f0708-244">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f0708-244">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> <span data-ttu-id="f0708-245">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="f0708-245">**This value MUST end with a period (.)**</span></span> <br/> |
    
    ![Waarden typen of plakken voor de nieuwe records](../../media/5ce0b30c-b46c-4778-aa5a-fb5e2f0961c1.png)
  
7. <span data-ttu-id="f0708-247">Wanneer u alle CNAME-records hebt toegevoegd die u nodig hebt, selecteert u **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="f0708-247">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Selecteer Doorgaan](../../media/4978bd8b-f6a6-458d-9522-ad612b301c4a.png)
  
8. <span data-ttu-id="f0708-249">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f0708-249">Select **Save Changes**.</span></span>
    
    ![Wijzigingen opslaan selecteren](../../media/f005c38a-0d8d-4c61-bec6-15e60c89aa5a.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="f0708-251">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="f0708-251">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="f0708-252"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="f0708-252"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="f0708-253">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="f0708-253">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="f0708-254">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="f0708-254">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="f0708-255">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f0708-255">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="f0708-256">Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat.</span><span class="sxs-lookup"><span data-stu-id="f0708-256">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="f0708-257">Volg onderstaande stappen of [bekijk de video (start op 5:35)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span><span class="sxs-lookup"><span data-stu-id="f0708-257">Follow the steps below or [watch the video (start at 5:35)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span></span>
  
1. <span data-ttu-id="f0708-258">Als u wilt beginnen, gaat u [via deze koppeling](https://www.networksolutions.com/manage-it) naar uw pagina met domeinen bij Network Solutions.</span><span class="sxs-lookup"><span data-stu-id="f0708-258">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="f0708-259">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="f0708-259">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="f0708-260">Voordat u de **knop Aanmelden** selecteert, kiest u Eerst **Mijn domeinnamen beheren** in de vervolgkeuzelijst Aanmelden **bij:**</span><span class="sxs-lookup"><span data-stu-id="f0708-260">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Mijn domeinnamen beheren kiezen en aanmelden bij Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="f0708-262">Schakel het selectievakje in naast de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="f0708-262">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Het selectievakje voor uw domein selecteren](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="f0708-264">Selecteer **DNS bewerken**.</span><span class="sxs-lookup"><span data-stu-id="f0708-264">Select **Edit DNS**.</span></span>
    
    ![DNS bewerken selecteren](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="f0708-266">Selecteer **Geavanceerde DNS-records beheren**.</span><span class="sxs-lookup"><span data-stu-id="f0708-266">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="f0708-267">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="f0708-267">(You may have to scroll down.)</span></span>
    
    ![Selecteer Geavanceerde DNS-records beheren](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="f0708-269">Schuif omlaag naar de sectie **Tekst (TXT Records)** en selecteer **TXT-records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="f0708-269">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![TXT-records bewerken onder tekst selecteren](../../media/a69a2631-6da2-4e81-99ab-9a9ab9b30b07.png)
  
6. <span data-ttu-id="f0708-271">Typ of kopieer en plak de volgende waarden in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="f0708-271">In the boxes for the new record, type or copy and paste the following values.</span></span>
    
    |<span data-ttu-id="f0708-272">**Host**</span><span class="sxs-lookup"><span data-stu-id="f0708-272">**Host**</span></span>|<span data-ttu-id="f0708-273">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f0708-273">**TTL**</span></span>|<span data-ttu-id="f0708-274">**Tekst**</span><span class="sxs-lookup"><span data-stu-id="f0708-274">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> <span data-ttu-id="f0708-275">(In het systeem wordt deze waarde gewijzigd in **@ (None)** wanneer u de record opslaat.)</span><span class="sxs-lookup"><span data-stu-id="f0708-275">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="f0708-276">3600</span><span class="sxs-lookup"><span data-stu-id="f0708-276">3600</span></span>  <br/> |<span data-ttu-id="f0708-277">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="f0708-277">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="f0708-278">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="f0708-278">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span> |
       
    ![Waarden typen of plakken voor de nieuwe record](../../media/11564eca-e2ee-4f17-af2b-a00eb7c157db.png)
  
7. <span data-ttu-id="f0708-280">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="f0708-280">Select **Continue**.</span></span>
    
    ![Selecteer Doorgaan](../../media/482a8dae-0c79-47c4-8bd8-87965683de24.png)
  
8. <span data-ttu-id="f0708-282">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f0708-282">Select **Save Changes**.</span></span>
    
    ![Wijzigingen opslaan selecteren](../../media/600b8c6d-184f-4213-a50e-8f119ebf3ff0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="f0708-284">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="f0708-284">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="f0708-285"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="f0708-285"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="f0708-286">Volg onderstaande stappen of [bekijk de video (start op 6:18)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span><span class="sxs-lookup"><span data-stu-id="f0708-286">Follow the steps below or [watch the video (start at 6:18)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).</span></span>
  
1. <span data-ttu-id="f0708-p113">Als u wilt beginnen, gaat u [via deze koppeling](https://www.networksolutions.com/manage-it) naar uw pagina met domeinen bij Network Solutions. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="f0708-p113">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="f0708-289">Voordat u de **knop Aanmelden** selecteert, kiest u Eerst **Mijn domeinnamen beheren** in de vervolgkeuzelijst Aanmelden **bij:**</span><span class="sxs-lookup"><span data-stu-id="f0708-289">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Mijn domeinnamen beheren kiezen en aanmelden bij Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="f0708-291">Schakel het selectievakje in naast de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="f0708-291">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Het selectievakje voor uw domein selecteren](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="f0708-293">Selecteer **DNS bewerken**.</span><span class="sxs-lookup"><span data-stu-id="f0708-293">Select **Edit DNS**.</span></span>
    
    ![DNS bewerken selecteren](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="f0708-295">Selecteer **Geavanceerde DNS-records beheren**.</span><span class="sxs-lookup"><span data-stu-id="f0708-295">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="f0708-296">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="f0708-296">(You may have to scroll down.)</span></span>
    
    ![Selecteer Geavanceerde DNS-records beheren](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="f0708-298">Schuif omlaag naar de sectie **Service (SRV Records)** en selecteer **SRV-records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="f0708-298">Scroll down to the **Service (SRV Records)** section, and then select **Edit SRV Records**.</span></span>
    
    ![SRV-records bewerken selecteren onder Service](../../media/9a9248ea-5de5-4e16-9364-f7600fa371f5.png)
  
6. <span data-ttu-id="f0708-300">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de twee nieuwe records.</span><span class="sxs-lookup"><span data-stu-id="f0708-300">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="f0708-301">(Kies in de vervolgkeuzelijsten de waarden **Service** en **Protocol**.)</span><span class="sxs-lookup"><span data-stu-id="f0708-301">(Choose the **Service** and **Protocol** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="f0708-302">**Service**</span><span class="sxs-lookup"><span data-stu-id="f0708-302">**Service**</span></span>|<span data-ttu-id="f0708-303">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="f0708-303">**Protocol**</span></span>|<span data-ttu-id="f0708-304">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f0708-304">**TTL**</span></span>|<span data-ttu-id="f0708-305">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="f0708-305">**Priority**</span></span>|<span data-ttu-id="f0708-306">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="f0708-306">**Weight**</span></span>|<span data-ttu-id="f0708-307">**Poort**</span><span class="sxs-lookup"><span data-stu-id="f0708-307">**Port**</span></span>|<span data-ttu-id="f0708-308">**Target**</span><span class="sxs-lookup"><span data-stu-id="f0708-308">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f0708-309">_sip</span><span class="sxs-lookup"><span data-stu-id="f0708-309">_sip</span></span>  <br/> |<span data-ttu-id="f0708-310">_tls</span><span class="sxs-lookup"><span data-stu-id="f0708-310">_tls</span></span>  <br/> |<span data-ttu-id="f0708-311">3600</span><span class="sxs-lookup"><span data-stu-id="f0708-311">3600</span></span>  <br/> |<span data-ttu-id="f0708-312">100</span><span class="sxs-lookup"><span data-stu-id="f0708-312">100</span></span>  <br/> |<span data-ttu-id="f0708-313">1</span><span class="sxs-lookup"><span data-stu-id="f0708-313">1</span></span>  <br/> |<span data-ttu-id="f0708-314">443</span><span class="sxs-lookup"><span data-stu-id="f0708-314">443</span></span>  <br/> |<span data-ttu-id="f0708-315">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="f0708-315">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="f0708-316">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="f0708-316">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="f0708-317">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="f0708-317">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="f0708-318">_tcp</span><span class="sxs-lookup"><span data-stu-id="f0708-318">_tcp</span></span>  <br/> |<span data-ttu-id="f0708-319">3600</span><span class="sxs-lookup"><span data-stu-id="f0708-319">3600</span></span>  <br/> |<span data-ttu-id="f0708-320">100</span><span class="sxs-lookup"><span data-stu-id="f0708-320">100</span></span>  <br/> |<span data-ttu-id="f0708-321">1</span><span class="sxs-lookup"><span data-stu-id="f0708-321">1</span></span>  <br/> |<span data-ttu-id="f0708-322">5061</span><span class="sxs-lookup"><span data-stu-id="f0708-322">5061</span></span>  <br/> |<span data-ttu-id="f0708-323">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="f0708-323">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="f0708-324">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="f0708-324">**This value MUST end with a period (.)**</span></span> <br/> |
       
    ![Waarden typen of plakken voor de nieuwe records](../../media/86968d1c-8e43-4e61-aeaa-37fc7d7ef7a7.png)
  
7. <span data-ttu-id="f0708-326">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="f0708-326">Select **Continue**.</span></span>
    
    ![Selecteer Doorgaan](../../media/bfe2c778-5d2b-4bb6-a79d-c3ff9caf9e1e.png)
  
8. <span data-ttu-id="f0708-328">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f0708-328">Select **Save Changes**.</span></span>
    
    ![Wijzigingen opslaan selecteren](../../media/6d323126-0ebe-45ab-8567-c234711d84c7.png)
  
> [!NOTE]
>  <span data-ttu-id="f0708-p114">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f0708-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
