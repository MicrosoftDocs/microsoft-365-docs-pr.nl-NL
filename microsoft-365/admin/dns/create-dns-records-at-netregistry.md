---
title: DNS-records bij netregistry voor Microsoft maken
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
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
- BEA160
ms.assetid: 48e09394-2287-4b3c-9853-21eadf61277e
description: Lees hoe u uw domein verifieert en DNS-records instelt voor e-mail, Skype voor bedrijven online en andere services op netregistry voor Microsoft.
ms.openlocfilehash: 857645c685cce946b39a7c3dcadb0a45b43686cf
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657801"
---
# <a name="create-dns-records-at-netregistry-for-microsoft"></a><span data-ttu-id="ef7c1-103">DNS-records bij netregistry voor Microsoft maken</span><span class="sxs-lookup"><span data-stu-id="ef7c1-103">Create DNS records at Netregistry for Microsoft</span></span>

<span data-ttu-id="ef7c1-104">[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml) als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-104">[Check the Domains FAQ](../setup/domains-faq.yml) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="ef7c1-105">Als Netregistry uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-105">If Netregistry is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="ef7c1-106">Dit zijn de belangrijkste records om toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-106">These are the main records to add.</span></span>
  
- [<span data-ttu-id="ef7c1-107">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="ef7c1-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="ef7c1-108">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="ef7c1-108">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)

- [<span data-ttu-id="ef7c1-109">De CNAME-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="ef7c1-109">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="ef7c1-110">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="ef7c1-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="ef7c1-111">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="ef7c1-111">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="ef7c1-112">Nadat u deze records bij netregistry hebt toegevoegd, is uw domein ingesteld voor gebruik met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-112">After you add these records at Netregistry, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="ef7c1-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ef7c1-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="ef7c1-116">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="ef7c1-116">Add a TXT record for verification</span></span>
<span data-ttu-id="ef7c1-117"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="ef7c1-117"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="ef7c1-p102">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ef7c1-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="ef7c1-p104">Ga naar uw domeinpagina van Netregistry via [deze koppeling](https://theconsole.netregistry.com.au/). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-p104">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/ed3c785f-01c3-49e7-affd-c04637c0ffe9.png)
  
2. <span data-ttu-id="ef7c1-125">Selecteer **Manage** (beheren) naast het domein dat u wilt beheren.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-125">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/64ad542a-5ec4-4148-96f8-d6e163449352.png)
  
3. <span data-ttu-id="ef7c1-127">Selecteer **Zone Manager**.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-127">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/e18c32f9-c1e7-4aa2-9aa6-8dc9c5ea44af.png)
  
4. <span data-ttu-id="ef7c1-129">Kies in de lijst onder **add a zone record** de optie **TXT record** en selecteer **Create New record**.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-129">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/eb1761e6-9deb-4631-8deb-bc5d09926722.png)
  
    > [!NOTE]
    > <span data-ttu-id="ef7c1-131">U moet aanhalingstekens vóór en na de invoer in het vak TXT gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-131">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    <span data-ttu-id="ef7c1-132">Typ of kopieer en plak de waarden uit de volgende tabel in het formulier **New TXT Record** (nieuwe TXT-record).</span><span class="sxs-lookup"><span data-stu-id="ef7c1-132">In the **New TXT Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="ef7c1-133">**Naam**</span><span class="sxs-lookup"><span data-stu-id="ef7c1-133">**Name**</span></span>|<span data-ttu-id="ef7c1-134">**TTL (SEC)**</span><span class="sxs-lookup"><span data-stu-id="ef7c1-134">**TTL (SEC)**</span></span>|<span data-ttu-id="ef7c1-135">**TXT (Verwijst naar adres of waarde)**</span><span class="sxs-lookup"><span data-stu-id="ef7c1-135">**TXT (Points to address or value)**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="ef7c1-136">(laat leeg)</span><span class="sxs-lookup"><span data-stu-id="ef7c1-136">(leave blank)</span></span>  <br/> |<span data-ttu-id="ef7c1-137">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="ef7c1-137">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="ef7c1-138">"MS = msXXXXXXXX"</span><span class="sxs-lookup"><span data-stu-id="ef7c1-138">"MS=msXXXXXXXX"</span></span>  <br/> <span data-ttu-id="ef7c1-139">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-139">**Note:** This is an example.</span></span> <span data-ttu-id="ef7c1-140">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-140">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="ef7c1-141">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="ef7c1-141">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
       
    ![Netregistry_verificationTXTvalues](../../media/cfe8b05a-fa8b-4dba-9554-7a3466e6c012.png)
  
6. <span data-ttu-id="ef7c1-143">Selecteer **record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-143">Select **Add record**.</span></span>
    
<span data-ttu-id="ef7c1-144">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-144">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="ef7c1-145">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-145">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="ef7c1-146">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-146">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="ef7c1-147">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-147">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="ef7c1-148">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-148">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="ef7c1-149">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-149">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="ef7c1-p106">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ef7c1-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="ef7c1-153">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="ef7c1-153">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="ef7c1-154"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="ef7c1-154"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="ef7c1-p107">Ga naar uw domeinpagina van Netregistry via [deze koppeling](https://theconsole.netregistry.com.au/). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-p107">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/80277b0e-547e-4635-aa6a-5d8ebe3fba85.png)
  
2. <span data-ttu-id="ef7c1-158">Selecteer **Manage** (beheren) naast het domein dat u wilt beheren.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-158">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/96e2c6e4-21fd-4405-a4fe-b1188400b985.png)
  
3. <span data-ttu-id="ef7c1-160">Selecteer **Zone Manager**.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-160">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/914021f6-dff3-4640-84d6-b83cf8f61cf1.png)
  
4. <span data-ttu-id="ef7c1-162">Verwijder onder **huidige zonerecords** de standaard MX-records door **verwijderen** naast elke MX-record in de lijst te selecteren.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-162">Under **Current zone records**, remove the default MX records by selecting **Remove** next to each MX record in the list.</span></span> 
    
    ![Netregistry_MX_remove](../../media/494670a9-8b8d-46e5-8136-05e82212a115.png)
  
5. <span data-ttu-id="ef7c1-164">Kies onder **add a zone record** de optie **MX record** in de lijst en selecteer **Create New record**.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-164">Under **Add a zone record**, choose **MX Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_MX_select](../../media/29b60eb9-6c40-490f-9669-e65b65962f37.png)
  
6. <span data-ttu-id="ef7c1-166">Typ of kopieer en plak de waarden uit de volgende tabel in het **nieuwe MX-record** formulier.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-166">In the **New MX Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="ef7c1-167">**Naam**</span><span class="sxs-lookup"><span data-stu-id="ef7c1-167">**Name**</span></span>|<span data-ttu-id="ef7c1-168">**TTL (SEC)**</span><span class="sxs-lookup"><span data-stu-id="ef7c1-168">**TTL (SEC)**</span></span>|<span data-ttu-id="ef7c1-169">**Exchange (verwijst naar adres of waarde)**</span><span class="sxs-lookup"><span data-stu-id="ef7c1-169">**Exchange (Points to address or value)**</span></span>|<span data-ttu-id="ef7c1-170">**Is host volledig gekwalificeerd?**</span><span class="sxs-lookup"><span data-stu-id="ef7c1-170">**Is host fully qualified?**</span></span>|<span data-ttu-id="ef7c1-171">**Voorkeur (prioriteit)**</span><span class="sxs-lookup"><span data-stu-id="ef7c1-171">**Preference (Priority)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ef7c1-172">(laat leeg)</span><span class="sxs-lookup"><span data-stu-id="ef7c1-172">(leave blank)</span></span>  <br/> |<span data-ttu-id="ef7c1-173">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="ef7c1-173">3600 (seconds)</span></span>  <br/> | <span data-ttu-id="ef7c1-174">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ef7c1-174">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="ef7c1-175">**Opmerking:** Neem uw  *\<domain-key\>*  van uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-175">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>  [<span data-ttu-id="ef7c1-176">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="ef7c1-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      |<span data-ttu-id="ef7c1-177">(Selecteer het selectievakje)</span><span class="sxs-lookup"><span data-stu-id="ef7c1-177">(select the checkbox)</span></span>  <br/> |<span data-ttu-id="ef7c1-178">10</span><span class="sxs-lookup"><span data-stu-id="ef7c1-178">10</span></span>  <br/> <span data-ttu-id="ef7c1-179">Zie Wat is MX-prioriteit? voor meer informatie over prioriteit.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-179">For more information about priority, see What is MX priority?</span></span>  <br/> |
       
    ![Netregistry_MX_values](../../media/518b3da6-4055-4e2d-b5ce-44a0fee25419.png)
  
7. <span data-ttu-id="ef7c1-181">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-181">Select **Add Record**.</span></span>
    
    ![Netregistry_MX_values_AddRecord](../../media/8194cb38-afa0-48ac-831c-fd34b6ad652e.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="ef7c1-183">De CNAME-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="ef7c1-183">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="ef7c1-184"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="ef7c1-184"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="ef7c1-p109">Ga naar uw domeinpagina van Netregistry via [deze koppeling](https://theconsole.netregistry.com.au/). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-p109">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/cbf83dce-86d2-4008-9400-56def4b6fcd7.png)
  
2. <span data-ttu-id="ef7c1-188">Selecteer **Manage** (beheren) naast het domein dat u wilt beheren.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-188">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/7bee4b0f-2c1d-43ca-b1bb-9b889ca0c5e4.png)
  
3. <span data-ttu-id="ef7c1-190">Selecteer **Zone Manager**.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-190">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/58384add-0a9d-472b-a5d0-51ec8155fd41.png)
  
4. <span data-ttu-id="ef7c1-192">Kies in de lijst onder  **add a zone record** de optie **CNAME record** en selecteer **Create New record**.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-192">Under  **Add a zone record**, choose **CNAME Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_CNAME_CreateNewRecord](../../media/7b4f133f-45da-48da-93c0-62f57c786165.png)
  
5. <span data-ttu-id="ef7c1-194">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-194">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="ef7c1-195">**Naam**</span><span class="sxs-lookup"><span data-stu-id="ef7c1-195">**Name**</span></span>|<span data-ttu-id="ef7c1-196">**Type**</span><span class="sxs-lookup"><span data-stu-id="ef7c1-196">**Type**</span></span>|<span data-ttu-id="ef7c1-197">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ef7c1-197">**TTL**</span></span>|<span data-ttu-id="ef7c1-198">**HOST (verwijst naar of adreswaarde)**</span><span class="sxs-lookup"><span data-stu-id="ef7c1-198">**HOST (Points to or address value)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ef7c1-199">autodiscover</span><span class="sxs-lookup"><span data-stu-id="ef7c1-199">autodiscover</span></span>  <br/> |<span data-ttu-id="ef7c1-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="ef7c1-200">CNAME</span></span>  <br/> |<span data-ttu-id="ef7c1-201">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="ef7c1-201">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="ef7c1-202">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ef7c1-202">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="ef7c1-203">sip</span><span class="sxs-lookup"><span data-stu-id="ef7c1-203">sip</span></span>  <br/> |<span data-ttu-id="ef7c1-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="ef7c1-204">CNAME</span></span>  <br/> |<span data-ttu-id="ef7c1-205">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="ef7c1-205">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="ef7c1-206">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ef7c1-206">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="ef7c1-207">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="ef7c1-207">lyncdiscover</span></span>  <br/> |<span data-ttu-id="ef7c1-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="ef7c1-208">CNAME</span></span>  <br/> |<span data-ttu-id="ef7c1-209">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="ef7c1-209">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="ef7c1-210">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ef7c1-210">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="ef7c1-211">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="ef7c1-211">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="ef7c1-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="ef7c1-212">CNAME</span></span>  <br/> |<span data-ttu-id="ef7c1-213">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="ef7c1-213">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="ef7c1-214">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="ef7c1-214">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="ef7c1-215">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="ef7c1-215">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="ef7c1-216">CNAME</span><span class="sxs-lookup"><span data-stu-id="ef7c1-216">CNAME</span></span>  <br/> |<span data-ttu-id="ef7c1-217">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="ef7c1-217">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="ef7c1-218">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="ef7c1-218">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![Netregistry_CNAME_values](../../media/93c479f0-3ce2-491a-9113-6dde1cd7131b.png)
      
6. <span data-ttu-id="ef7c1-220">Selecteer **record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-220">Select **Add record**.</span></span>
    
    ![Netregistry_CNAME_values_AddRecord](../../media/046c8c64-ea71-4530-9fc6-69f0c70993b6.png)
  
7. <span data-ttu-id="ef7c1-222">Herhaal de vorige stappen om de vijf andere CNAME-records te maken.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-222">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="ef7c1-223">Typ of kopieer en plak voor elke record de waarden uit de volgende rij van de bovenstaande tabel in de velden voor die record.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-223">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="ef7c1-224">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="ef7c1-224">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="ef7c1-225"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="ef7c1-225"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="ef7c1-226">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-226">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="ef7c1-227">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="ef7c1-228">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-228">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="ef7c1-229">In plaats daarvan voegt u de vereiste Microsoft-waarden toe aan de huidige record, zodat u  *één*  SPF-record hebt die beide sets met waarden bevat.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-229">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="ef7c1-p111">Ga naar uw domeinpagina van Netregistry via [deze koppeling](https://theconsole.netregistry.com.au/). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-p111">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/a841f11f-1c0f-4926-acea-a2b8bb083984.png)
  
2. <span data-ttu-id="ef7c1-233">Selecteer **Manage** (beheren) naast het domein dat u wilt beheren.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-233">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/4245bbbb-4e2d-49e7-a89c-679949aa3d18.png)
  
3. <span data-ttu-id="ef7c1-235">Selecteer **Zone Manager**.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-235">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/372e5918-b6dc-4268-8f9a-0aa71d65deef.png)
  
4. <span data-ttu-id="ef7c1-237">Kies in de lijst onder **add a zone record** de optie **TXT record** en selecteer **Create New record**.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-237">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/a2930d03-853a-4f1e-9205-d00f25bed35f.png)
  
5. <span data-ttu-id="ef7c1-239">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-239">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="ef7c1-240">U moet aanhalingstekens vóór en na de invoer in het vak TXT gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-240">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    |<span data-ttu-id="ef7c1-241">**Naam**</span><span class="sxs-lookup"><span data-stu-id="ef7c1-241">**Name**</span></span>|<span data-ttu-id="ef7c1-242">**Type**</span><span class="sxs-lookup"><span data-stu-id="ef7c1-242">**Type**</span></span>|<span data-ttu-id="ef7c1-243">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ef7c1-243">**TTL**</span></span>|<span data-ttu-id="ef7c1-244">**TXT-gegevens (doel)**</span><span class="sxs-lookup"><span data-stu-id="ef7c1-244">**TXT Data (Target)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ef7c1-245">(laat leeg)</span><span class="sxs-lookup"><span data-stu-id="ef7c1-245">(leave blank)</span></span>  <br/> |<span data-ttu-id="ef7c1-246">TXT</span><span class="sxs-lookup"><span data-stu-id="ef7c1-246">TXT</span></span>  <br/> |<span data-ttu-id="ef7c1-247">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="ef7c1-247">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="ef7c1-248">"v = spf1 include:SPF. Protection. Outlook. com-all"</span><span class="sxs-lookup"><span data-stu-id="ef7c1-248">"v=spf1 include:spf.protection.outlook.com -all"</span></span>  <br/> <span data-ttu-id="ef7c1-249">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-249">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Netregistry_SPF-TXTvalues](../../media/a369345a-d774-48bc-8160-b628ab8247f9.png)
  
6. <span data-ttu-id="ef7c1-251">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-251">Select **Add Record**.</span></span>
    
    ![Netregistry_SPF-TXTvalues_AddRecord](../../media/063bfbaf-940a-489f-970f-29c026b4b312.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="ef7c1-253">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="ef7c1-253">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="ef7c1-254"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="ef7c1-254"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="ef7c1-p112">Ga naar uw domeinpagina van Netregistry via [deze koppeling](https://theconsole.netregistry.com.au/). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-p112">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/accf6584-e5f4-4d68-a641-0f8847f8370f.png)
  
2. <span data-ttu-id="ef7c1-258">Selecteer  **Manage (beheren**) naast het domein dat u wilt beheren.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-258">Next to the domain you want to manage, select  **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/e0ddc79e-0123-4e24-8380-9645bdb41aac.png)
  
3. <span data-ttu-id="ef7c1-260">Selecteer **Zone Manager**.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-260">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/f122888b-3cc5-40ec-adac-0ede04799d9a.png)
  
4. <span data-ttu-id="ef7c1-262">Kies onder  **add a zone record** de optie **SRV record** in de lijst en selecteer vervolgens **Create New record**.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-262">Under  **Add a zone record**, choose **SRV Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_SRV_select](../../media/e5dab850-acd1-48b8-8b4a-e3b9777cf508.png)
  
5. <span data-ttu-id="ef7c1-264">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-264">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ef7c1-265">Het veld naam is een combinatie van de service (bijvoorbeeld _sip) en protocol (bijvoorbeeld _tls).</span><span class="sxs-lookup"><span data-stu-id="ef7c1-265">The Name field is a combination of the service (for example, _sip) and protocol (for example, _tls).</span></span> 
  
    |<span data-ttu-id="ef7c1-266">**Type**</span><span class="sxs-lookup"><span data-stu-id="ef7c1-266">**Type**</span></span>|<span data-ttu-id="ef7c1-267">**Naam**</span><span class="sxs-lookup"><span data-stu-id="ef7c1-267">**Name**</span></span>|<span data-ttu-id="ef7c1-268">**TTL (SEC)**</span><span class="sxs-lookup"><span data-stu-id="ef7c1-268">**TTL (SEC)**</span></span>|<span data-ttu-id="ef7c1-269">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="ef7c1-269">**Priority**</span></span>|<span data-ttu-id="ef7c1-270">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="ef7c1-270">**Weight**</span></span>|<span data-ttu-id="ef7c1-271">**Poort**</span><span class="sxs-lookup"><span data-stu-id="ef7c1-271">**Port**</span></span>|<span data-ttu-id="ef7c1-272">**Target**</span><span class="sxs-lookup"><span data-stu-id="ef7c1-272">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ef7c1-273">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="ef7c1-273">SRV (service)</span></span>  <br/> |<span data-ttu-id="ef7c1-274">_sip _sip._tls</span><span class="sxs-lookup"><span data-stu-id="ef7c1-274">_sip._tls</span></span>  <br/> |<span data-ttu-id="ef7c1-275">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="ef7c1-275">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="ef7c1-276">100</span><span class="sxs-lookup"><span data-stu-id="ef7c1-276">100</span></span>  <br/> |<span data-ttu-id="ef7c1-277">1</span><span class="sxs-lookup"><span data-stu-id="ef7c1-277">1</span></span>  <br/> |<span data-ttu-id="ef7c1-278">443</span><span class="sxs-lookup"><span data-stu-id="ef7c1-278">443</span></span>  <br/> |<span data-ttu-id="ef7c1-279">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ef7c1-279">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="ef7c1-280">SRV (Service)</span><span class="sxs-lookup"><span data-stu-id="ef7c1-280">SRV (service)</span></span>  <br/> |<span data-ttu-id="ef7c1-281">_sipfederationtls _sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="ef7c1-281">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="ef7c1-282">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="ef7c1-282">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="ef7c1-283">100</span><span class="sxs-lookup"><span data-stu-id="ef7c1-283">100</span></span>  <br/> |<span data-ttu-id="ef7c1-284">1</span><span class="sxs-lookup"><span data-stu-id="ef7c1-284">1</span></span>  <br/> |<span data-ttu-id="ef7c1-285">5061</span><span class="sxs-lookup"><span data-stu-id="ef7c1-285">5061</span></span>  <br/> |<span data-ttu-id="ef7c1-286">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ef7c1-286">sipfed.online.lync.com</span></span>  <br/> |
       
    ![Netregistry_SRV_values](../../media/49292846-1598-4b8c-9940-db6e10675753.png)
  
6. <span data-ttu-id="ef7c1-288">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-288">Select **Add Record**.</span></span>
    
    ![Netregistry_SRV_values_AddRecord](../../media/abc82061-939f-4757-87e4-0e8f9e43ebcb.png)
  
7. <span data-ttu-id="ef7c1-290">Herhaal de vorige stappen om de andere SRV-record te maken.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-290">Repeat the previous steps to create the other SRV record.</span></span>
    
    <span data-ttu-id="ef7c1-291">Typ of kopieer en plak de waarden uit de tweede rij van de bovenstaande tabel in de vakken voor de tweede record.</span><span class="sxs-lookup"><span data-stu-id="ef7c1-291">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ef7c1-p113">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ef7c1-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

