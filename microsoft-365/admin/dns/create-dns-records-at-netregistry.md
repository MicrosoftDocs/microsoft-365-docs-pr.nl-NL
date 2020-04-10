---
title: DNS-records maken bij Netregistry voor Office 365
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
- BEA160
ms.assetid: 48e09394-2287-4b3c-9853-21eadf61277e
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services bij Netregistry voor Office 365.
ms.openlocfilehash: e1f2414817357b8435bc002860a35c6e76d4314e
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211132"
---
# <a name="create-dns-records-at-netregistry-for-office-365"></a><span data-ttu-id="882c2-103">DNS-records maken bij Netregistry voor Office 365</span><span class="sxs-lookup"><span data-stu-id="882c2-103">Create DNS records at Netregistry for Office 365</span></span>

<span data-ttu-id="882c2-104">[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md) als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="882c2-104">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="882c2-105">Als Netregistry uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="882c2-105">If Netregistry is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="882c2-106">Dit zijn de belangrijkste records om toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="882c2-106">These are the main records to add.</span></span>
  
- [<span data-ttu-id="882c2-107">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="882c2-107">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)
    
- [<span data-ttu-id="882c2-108">Voeg een MX-record toe zodat e-mail voor uw domein bij Office 365 terechtkomt</span><span class="sxs-lookup"><span data-stu-id="882c2-108">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)

- [<span data-ttu-id="882c2-109">De CNAME-records toevoegen die voor Office 365 vereist zijn</span><span class="sxs-lookup"><span data-stu-id="882c2-109">Add the CNAME records that are required for Office 365</span></span>](#add-the-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="882c2-110">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="882c2-110">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="882c2-111">Voeg de vier SRV-records toe die voor Office 365 vereist zijn.</span><span class="sxs-lookup"><span data-stu-id="882c2-111">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="882c2-112">Nadat u deze records hebt toegevoegd bij Netregistry, wordt uw domein ingesteld voor gebruik met Office 365-services.</span><span class="sxs-lookup"><span data-stu-id="882c2-112">After you add these records at Netregistry, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="882c2-113">Zie [Een openbare website gebruiken met Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx) voor informatie over webhosting en DNS voor websites met Office 365.</span><span class="sxs-lookup"><span data-stu-id="882c2-113">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="882c2-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="882c2-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="882c2-117">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="882c2-117">Add a TXT record for verification</span></span>
<span data-ttu-id="882c2-118"><a name="bkmk_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="882c2-118"><a name="bkmk_txt"> </a></span></span>

<span data-ttu-id="882c2-p102">Voordat u uw domein met Office 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Office 365 bewezen.</span><span class="sxs-lookup"><span data-stu-id="882c2-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="882c2-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="882c2-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="882c2-p104">Ga naar uw domeinpagina van Netregistry via [deze koppeling](https://theconsole.netregistry.com.au/). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="882c2-p104">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/ed3c785f-01c3-49e7-affd-c04637c0ffe9.png)
  
2. <span data-ttu-id="882c2-126">Selecteer **Manage** (beheren) naast het domein dat u wilt beheren.</span><span class="sxs-lookup"><span data-stu-id="882c2-126">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/64ad542a-5ec4-4148-96f8-d6e163449352.png)
  
3. <span data-ttu-id="882c2-128">Selecteer **Zone Manager**.</span><span class="sxs-lookup"><span data-stu-id="882c2-128">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/e18c32f9-c1e7-4aa2-9aa6-8dc9c5ea44af.png)
  
4. <span data-ttu-id="882c2-130">Kies **onder Een zonerecord toevoegen**de optie **TXT-record** in de lijst en selecteer **Vervolgens Nieuwe record maken**.</span><span class="sxs-lookup"><span data-stu-id="882c2-130">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/eb1761e6-9deb-4631-8deb-bc5d09926722.png)
  
    > [!NOTE]
    > <span data-ttu-id="882c2-132">U moet aanhalingstekens gebruiken voor en na de vermelding in het vak TXT.</span><span class="sxs-lookup"><span data-stu-id="882c2-132">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    <span data-ttu-id="882c2-133">Typ of kopieer en plak de waarden uit de volgende tabel in het formulier **New TXT Record** (nieuwe TXT-record).</span><span class="sxs-lookup"><span data-stu-id="882c2-133">In the **New TXT Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="882c2-134">**Naam**</span><span class="sxs-lookup"><span data-stu-id="882c2-134">**Name**</span></span>|<span data-ttu-id="882c2-135">**TTL (SEC)**</span><span class="sxs-lookup"><span data-stu-id="882c2-135">**TTL (SEC)**</span></span>|<span data-ttu-id="882c2-136">**TXT (Verwijst naar adres of waarde)**</span><span class="sxs-lookup"><span data-stu-id="882c2-136">**TXT (Points to address or value)**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="882c2-137">(laat leeg)</span><span class="sxs-lookup"><span data-stu-id="882c2-137">(leave blank)</span></span>  <br/> |<span data-ttu-id="882c2-138">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="882c2-138">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="882c2-139">"MS=msXXXXXXXX"</span><span class="sxs-lookup"><span data-stu-id="882c2-139">"MS=msXXXXXXXX"</span></span>  <br/> <span data-ttu-id="882c2-140">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="882c2-140">**Note:** This is an example.</span></span> <span data-ttu-id="882c2-141">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365.</span><span class="sxs-lookup"><span data-stu-id="882c2-141">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="882c2-142">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="882c2-142">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  |
       
    ![Netregistry_verificationTXTvalues](../../media/cfe8b05a-fa8b-4dba-9554-7a3466e6c012.png)
  
6. <span data-ttu-id="882c2-144">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="882c2-144">Select **Add record**.</span></span>
    
<span data-ttu-id="882c2-145">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Office 365 en vraagt u of Office 365 naar de record wil zoeken.</span><span class="sxs-lookup"><span data-stu-id="882c2-145">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="882c2-146">Wanneer in Office 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="882c2-146">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="882c2-147">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="882c2-147">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="882c2-148">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="882c2-148">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="882c2-149">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="882c2-149">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="882c2-150">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="882c2-150">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="882c2-p106">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="882c2-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="882c2-154">Een MX-record toevoegen zodat e-mail voor uw domein bij Office 365 terechtkomt</span><span class="sxs-lookup"><span data-stu-id="882c2-154">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="882c2-155"><a name="bkmk_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="882c2-155"><a name="bkmk_mx"> </a></span></span>

1. <span data-ttu-id="882c2-p107">Ga naar uw domeinpagina van Netregistry via [deze koppeling](https://theconsole.netregistry.com.au/). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="882c2-p107">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/80277b0e-547e-4635-aa6a-5d8ebe3fba85.png)
  
2. <span data-ttu-id="882c2-159">Selecteer **Manage** (beheren) naast het domein dat u wilt beheren.</span><span class="sxs-lookup"><span data-stu-id="882c2-159">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/96e2c6e4-21fd-4405-a4fe-b1188400b985.png)
  
3. <span data-ttu-id="882c2-161">Selecteer **Zone Manager**.</span><span class="sxs-lookup"><span data-stu-id="882c2-161">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/914021f6-dff3-4640-84d6-b83cf8f61cf1.png)
  
4. <span data-ttu-id="882c2-163">Verwijder **onder Huidige zonerecords**de standaardMX-records door **Verwijderen** naast elke MX-record in de lijst te selecteren.</span><span class="sxs-lookup"><span data-stu-id="882c2-163">Under **Current zone records**, remove the default MX records by selecting **Remove** next to each MX record in the list.</span></span> 
    
    ![Netregistry_MX_remove](../../media/494670a9-8b8d-46e5-8136-05e82212a115.png)
  
5. <span data-ttu-id="882c2-165">Kies **mx-record** in de lijst **onder Een zonerecord toevoegen**en selecteer Vervolgens Nieuwe record **maken**.</span><span class="sxs-lookup"><span data-stu-id="882c2-165">Under **Add a zone record**, choose **MX Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_MX_select](../../media/29b60eb9-6c40-490f-9669-e65b65962f37.png)
  
6. <span data-ttu-id="882c2-167">Typ of kopieer en plak de waarden uit de volgende tabel in het formulier **Nieuwe MX-record.**</span><span class="sxs-lookup"><span data-stu-id="882c2-167">In the **New MX Record** form, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="882c2-168">**Naam**</span><span class="sxs-lookup"><span data-stu-id="882c2-168">**Name**</span></span>|<span data-ttu-id="882c2-169">**TTL (SEC)**</span><span class="sxs-lookup"><span data-stu-id="882c2-169">**TTL (SEC)**</span></span>|<span data-ttu-id="882c2-170">**Exchange (Adres- of waardeaanspraken)**</span><span class="sxs-lookup"><span data-stu-id="882c2-170">**Exchange (Points to address or value)**</span></span>|<span data-ttu-id="882c2-171">**Is de host volledig gekwalificeerd?**</span><span class="sxs-lookup"><span data-stu-id="882c2-171">**Is host fully qualified?**</span></span>|<span data-ttu-id="882c2-172">**Voorkeur (prioriteit)**</span><span class="sxs-lookup"><span data-stu-id="882c2-172">**Preference (Priority)**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="882c2-173">(laat leeg)</span><span class="sxs-lookup"><span data-stu-id="882c2-173">(leave blank)</span></span>  <br/> |<span data-ttu-id="882c2-174">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="882c2-174">3600 (seconds)</span></span>  <br/> | <span data-ttu-id="882c2-175">*\<domeinsleutel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="882c2-175">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="882c2-176">**Let op:** Haal uw \* \<domeinsleutel\> \* op uit uw Office 365-account.</span><span class="sxs-lookup"><span data-stu-id="882c2-176">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>  [<span data-ttu-id="882c2-177">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="882c2-177">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      |<span data-ttu-id="882c2-178">(schakel het selectievakje in)</span><span class="sxs-lookup"><span data-stu-id="882c2-178">(select the checkbox)</span></span>  <br/> |<span data-ttu-id="882c2-179">10</span><span class="sxs-lookup"><span data-stu-id="882c2-179">10</span></span>  <br/> <span data-ttu-id="882c2-180">Zie Wat is MX-prioriteit? voor meer informatie over prioriteit.</span><span class="sxs-lookup"><span data-stu-id="882c2-180">For more information about priority, see What is MX priority?</span></span>  <br/> |
       
    ![Netregistry_MX_values](../../media/518b3da6-4055-4e2d-b5ce-44a0fee25419.png)
  
7. <span data-ttu-id="882c2-182">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="882c2-182">Select **Add Record**.</span></span>
    
    ![Netregistry_MX_values_AddRecord](../../media/8194cb38-afa0-48ac-831c-fd34b6ad652e.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="882c2-184">De CNAME-records toevoegen die voor Office 365 vereist zijn</span><span class="sxs-lookup"><span data-stu-id="882c2-184">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="882c2-185"><a name="bkmk_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="882c2-185"><a name="bkmk_cname"> </a></span></span>

1. <span data-ttu-id="882c2-p109">Ga naar uw domeinpagina van Netregistry via [deze koppeling](https://theconsole.netregistry.com.au/). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="882c2-p109">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/cbf83dce-86d2-4008-9400-56def4b6fcd7.png)
  
2. <span data-ttu-id="882c2-189">Selecteer **Manage** (beheren) naast het domein dat u wilt beheren.</span><span class="sxs-lookup"><span data-stu-id="882c2-189">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/7bee4b0f-2c1d-43ca-b1bb-9b889ca0c5e4.png)
  
3. <span data-ttu-id="882c2-191">Selecteer **Zone Manager**.</span><span class="sxs-lookup"><span data-stu-id="882c2-191">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/58384add-0a9d-472b-a5d0-51ec8155fd41.png)
  
4. <span data-ttu-id="882c2-193">Kies **onder Een zonerecord toevoegen**de optie **CNAME Record** in de lijst en selecteer Vervolgens Nieuwe record **maken**.</span><span class="sxs-lookup"><span data-stu-id="882c2-193">Under  **Add a zone record**, choose **CNAME Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_CNAME_CreateNewRecord](../../media/7b4f133f-45da-48da-93c0-62f57c786165.png)
  
5. <span data-ttu-id="882c2-195">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="882c2-195">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="882c2-196">**Name**</span><span class="sxs-lookup"><span data-stu-id="882c2-196">**Name**</span></span>|<span data-ttu-id="882c2-197">**Type**</span><span class="sxs-lookup"><span data-stu-id="882c2-197">**Type**</span></span>|<span data-ttu-id="882c2-198">**TTL**</span><span class="sxs-lookup"><span data-stu-id="882c2-198">**TTL**</span></span>|<span data-ttu-id="882c2-199">**HOST (Adreswaarde of adreswaarde)**</span><span class="sxs-lookup"><span data-stu-id="882c2-199">**HOST (Points to or address value)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="882c2-200">autodiscover</span><span class="sxs-lookup"><span data-stu-id="882c2-200">autodiscover</span></span>  <br/> |<span data-ttu-id="882c2-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="882c2-201">CNAME</span></span>  <br/> |<span data-ttu-id="882c2-202">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="882c2-202">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="882c2-203">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="882c2-203">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="882c2-204">sip</span><span class="sxs-lookup"><span data-stu-id="882c2-204">sip</span></span>  <br/> |<span data-ttu-id="882c2-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="882c2-205">CNAME</span></span>  <br/> |<span data-ttu-id="882c2-206">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="882c2-206">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="882c2-207">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="882c2-207">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="882c2-208">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="882c2-208">lyncdiscover</span></span>  <br/> |<span data-ttu-id="882c2-209">CNAME</span><span class="sxs-lookup"><span data-stu-id="882c2-209">CNAME</span></span>  <br/> |<span data-ttu-id="882c2-210">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="882c2-210">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="882c2-211">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="882c2-211">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="882c2-212">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="882c2-212">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="882c2-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="882c2-213">CNAME</span></span>  <br/> |<span data-ttu-id="882c2-214">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="882c2-214">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="882c2-215">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="882c2-215">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="882c2-216">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="882c2-216">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="882c2-217">CNAME</span><span class="sxs-lookup"><span data-stu-id="882c2-217">CNAME</span></span>  <br/> |<span data-ttu-id="882c2-218">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="882c2-218">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="882c2-219">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="882c2-219">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![Netregistry_CNAME_values](../../media/93c479f0-3ce2-491a-9113-6dde1cd7131b.png)
      
6. <span data-ttu-id="882c2-221">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="882c2-221">Select **Add record**.</span></span>
    
    ![Netregistry_CNAME_values_AddRecord](../../media/046c8c64-ea71-4530-9fc6-69f0c70993b6.png)
  
7. <span data-ttu-id="882c2-223">Herhaal de vorige stappen om de vijf andere CNAME-records te maken.</span><span class="sxs-lookup"><span data-stu-id="882c2-223">Repeat the previous steps to create the other five CNAME records.</span></span>
    
    <span data-ttu-id="882c2-224">Typ of kopieer en plak voor elke record de waarden uit de volgende rij van de bovenstaande tabel in de velden voor die record.</span><span class="sxs-lookup"><span data-stu-id="882c2-224">For each record, type or copy and paste the values from the next row of the table above into the boxes for that record.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="882c2-225">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="882c2-225">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="882c2-226"><a name="bkmk_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="882c2-226"><a name="bkmk_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="882c2-227">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="882c2-227">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="882c2-228">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="882c2-228">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="882c2-229">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Office 365 te maken.</span><span class="sxs-lookup"><span data-stu-id="882c2-229">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="882c2-230">In plaats daarvan voegt u de vereiste Office 365-waarden toe aan de huidige record, zodat u beschikt over  *één*  SPF-record waarin beide sets waarden zijn opgenomen.</span><span class="sxs-lookup"><span data-stu-id="882c2-230">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="882c2-p111">Ga naar uw domeinpagina van Netregistry via [deze koppeling](https://theconsole.netregistry.com.au/). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="882c2-p111">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/a841f11f-1c0f-4926-acea-a2b8bb083984.png)
  
2. <span data-ttu-id="882c2-234">Selecteer **Manage** (beheren) naast het domein dat u wilt beheren.</span><span class="sxs-lookup"><span data-stu-id="882c2-234">Next to the domain you want to manage, select **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/4245bbbb-4e2d-49e7-a89c-679949aa3d18.png)
  
3. <span data-ttu-id="882c2-236">Selecteer **Zone Manager**.</span><span class="sxs-lookup"><span data-stu-id="882c2-236">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/372e5918-b6dc-4268-8f9a-0aa71d65deef.png)
  
4. <span data-ttu-id="882c2-238">Kies **onder Een zonerecord toevoegen**de optie **TXT-record** in de lijst en selecteer **Vervolgens Nieuwe record maken**.</span><span class="sxs-lookup"><span data-stu-id="882c2-238">Under **Add a zone record**, choose **TXT Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_TXT_select](../../media/a2930d03-853a-4f1e-9205-d00f25bed35f.png)
  
5. <span data-ttu-id="882c2-240">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="882c2-240">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="882c2-241">U moet aanhalingstekens gebruiken voor en na de vermelding in het vak TXT.</span><span class="sxs-lookup"><span data-stu-id="882c2-241">You must use quotation marks before and after the entry in the TXT box.</span></span> 
  
    |<span data-ttu-id="882c2-242">**Name**</span><span class="sxs-lookup"><span data-stu-id="882c2-242">**Name**</span></span>|<span data-ttu-id="882c2-243">**Type**</span><span class="sxs-lookup"><span data-stu-id="882c2-243">**Type**</span></span>|<span data-ttu-id="882c2-244">**TTL**</span><span class="sxs-lookup"><span data-stu-id="882c2-244">**TTL**</span></span>|<span data-ttu-id="882c2-245">**TXT-gegevens (doel)**</span><span class="sxs-lookup"><span data-stu-id="882c2-245">**TXT Data (Target)**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="882c2-246">(laat leeg)</span><span class="sxs-lookup"><span data-stu-id="882c2-246">(leave blank)</span></span>  <br/> |<span data-ttu-id="882c2-247">TXT</span><span class="sxs-lookup"><span data-stu-id="882c2-247">TXT</span></span>  <br/> |<span data-ttu-id="882c2-248">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="882c2-248">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="882c2-249">"v=spf1 include:spf.protection.outlook.com -all"</span><span class="sxs-lookup"><span data-stu-id="882c2-249">"v=spf1 include:spf.protection.outlook.com -all"</span></span>  <br/> <span data-ttu-id="882c2-250">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="882c2-250">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Netregistry_SPF-TXT-waarden](../../media/a369345a-d774-48bc-8160-b628ab8247f9.png)
  
6. <span data-ttu-id="882c2-252">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="882c2-252">Select **Add Record**.</span></span>
    
    ![Netregistry_SPF-TXTvalues_AddRecord](../../media/063bfbaf-940a-489f-970f-29c026b4b312.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="882c2-254">De twee SRV-records toevoegen die voor Office 365 vereist zijn</span><span class="sxs-lookup"><span data-stu-id="882c2-254">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="882c2-255"><a name="bkmk_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="882c2-255"><a name="bkmk_srv"> </a></span></span>

1. <span data-ttu-id="882c2-p112">Ga naar uw domeinpagina van Netregistry via [deze koppeling](https://theconsole.netregistry.com.au/). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="882c2-p112">To get started, go to your domains page in Netregistry by using [this link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.</span></span>
    
    ![Netregistry_login](../../media/accf6584-e5f4-4d68-a641-0f8847f8370f.png)
  
2. <span data-ttu-id="882c2-259">Selecteer Naast het domein dat u wilt beheren de optie **Beheren**.</span><span class="sxs-lookup"><span data-stu-id="882c2-259">Next to the domain you want to manage, select  **Manage**.</span></span>
    
    ![Netregistry_Manage](../../media/e0ddc79e-0123-4e24-8380-9645bdb41aac.png)
  
3. <span data-ttu-id="882c2-261">Selecteer **Zone Manager**.</span><span class="sxs-lookup"><span data-stu-id="882c2-261">Select **Zone Manager**.</span></span>
    
    ![Netregistry_selectZoneManager](../../media/f122888b-3cc5-40ec-adac-0ede04799d9a.png)
  
4. <span data-ttu-id="882c2-263">Kies **onder Een zonerecord toevoegen**de optie **SRV-record** in de lijst en selecteer **Vervolgens Nieuwe record maken**.</span><span class="sxs-lookup"><span data-stu-id="882c2-263">Under  **Add a zone record**, choose **SRV Record** from the list, and then select **Create new record**.</span></span>
    
    ![Netregistry_SRV_select](../../media/e5dab850-acd1-48b8-8b4a-e3b9777cf508.png)
  
5. <span data-ttu-id="882c2-265">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="882c2-265">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="882c2-266">Het veld Naam is een combinatie van de service (bijvoorbeeld _sip) en protocol (bijvoorbeeld _tls).</span><span class="sxs-lookup"><span data-stu-id="882c2-266">The Name field is a combination of the service (for example, _sip) and protocol (for example, _tls).</span></span> 
  
    |<span data-ttu-id="882c2-267">**Type**</span><span class="sxs-lookup"><span data-stu-id="882c2-267">**Type**</span></span>|<span data-ttu-id="882c2-268">**Naam**</span><span class="sxs-lookup"><span data-stu-id="882c2-268">**Name**</span></span>|<span data-ttu-id="882c2-269">**TTL (SEC)**</span><span class="sxs-lookup"><span data-stu-id="882c2-269">**TTL (SEC)**</span></span>|<span data-ttu-id="882c2-270">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="882c2-270">**Priority**</span></span>|<span data-ttu-id="882c2-271">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="882c2-271">**Weight**</span></span>|<span data-ttu-id="882c2-272">**Poort**</span><span class="sxs-lookup"><span data-stu-id="882c2-272">**Port**</span></span>|<span data-ttu-id="882c2-273">**Target**</span><span class="sxs-lookup"><span data-stu-id="882c2-273">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="882c2-274">SRV (service)</span><span class="sxs-lookup"><span data-stu-id="882c2-274">SRV (service)</span></span>  <br/> |<span data-ttu-id="882c2-275">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="882c2-275">_sip._tls</span></span>  <br/> |<span data-ttu-id="882c2-276">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="882c2-276">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="882c2-277">100</span><span class="sxs-lookup"><span data-stu-id="882c2-277">100</span></span>  <br/> |<span data-ttu-id="882c2-278">1</span><span class="sxs-lookup"><span data-stu-id="882c2-278">1</span></span>  <br/> |<span data-ttu-id="882c2-279">443</span><span class="sxs-lookup"><span data-stu-id="882c2-279">443</span></span>  <br/> |<span data-ttu-id="882c2-280">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="882c2-280">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="882c2-281">SRV (service)</span><span class="sxs-lookup"><span data-stu-id="882c2-281">SRV (service)</span></span>  <br/> |<span data-ttu-id="882c2-282">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="882c2-282">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="882c2-283">3600 (seconden)</span><span class="sxs-lookup"><span data-stu-id="882c2-283">3600 (seconds)</span></span>  <br/> |<span data-ttu-id="882c2-284">100</span><span class="sxs-lookup"><span data-stu-id="882c2-284">100</span></span>  <br/> |<span data-ttu-id="882c2-285">1</span><span class="sxs-lookup"><span data-stu-id="882c2-285">1</span></span>  <br/> |<span data-ttu-id="882c2-286">5061</span><span class="sxs-lookup"><span data-stu-id="882c2-286">5061</span></span>  <br/> |<span data-ttu-id="882c2-287">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="882c2-287">sipfed.online.lync.com</span></span>  <br/> |
       
    ![Netregistry_SRV_values](../../media/49292846-1598-4b8c-9940-db6e10675753.png)
  
6. <span data-ttu-id="882c2-289">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="882c2-289">Select **Add Record**.</span></span>
    
    ![Netregistry_SRV_values_AddRecord](../../media/abc82061-939f-4757-87e4-0e8f9e43ebcb.png)
  
7. <span data-ttu-id="882c2-291">Herhaal de vorige stappen om de andere SRV-record te maken.</span><span class="sxs-lookup"><span data-stu-id="882c2-291">Repeat the previous steps to create the other SRV record.</span></span>
    
    <span data-ttu-id="882c2-292">Typ of kopieer en plak de waarden uit de tweede rij van de bovenstaande tabel in de vakken voor de tweede record.</span><span class="sxs-lookup"><span data-stu-id="882c2-292">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="882c2-p113">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="882c2-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

