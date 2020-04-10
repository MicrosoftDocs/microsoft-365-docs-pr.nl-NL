---
title: DNS-records maken voor Azure DNS-zones
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
ms.assetid: fbcef2d7-ebaf-40d0-ba1f-cdaeff9f50ef
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services in Azure DNS-zones voor Office 365.
ms.openlocfilehash: 1c9ac04f74b205fa4a099fca634a41207e8083ba
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211048"
---
# <a name="create-dns-records-for-azure-dns-zones"></a><span data-ttu-id="50f2a-103">DNS-records maken voor Azure DNS-zones</span><span class="sxs-lookup"><span data-stu-id="50f2a-103">Create DNS records for Azure DNS zones</span></span>

 <span data-ttu-id="50f2a-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="50f2a-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="50f2a-105">Als Azure uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records in te stellen voor e-mail, Skype voor Bedrijven Online, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="50f2a-105">If Azure is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="50f2a-106">Dit zijn de belangrijkste records om toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="50f2a-106">These are the main records to add.</span></span> 
  
- [<span data-ttu-id="50f2a-107">De naamserverrecords (NS-records) van uw domein wijzigen</span><span class="sxs-lookup"><span data-stu-id="50f2a-107">Change your domain's nameserver (NS) records</span></span>](#change-your-domains-nameserver-ns-records)
    
- [<span data-ttu-id="50f2a-108">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="50f2a-108">Add a TXT record for verification</span></span>](#add-a-txt-record-for-verification)

- [<span data-ttu-id="50f2a-109">Voeg een MX-record toe zodat e-mail voor uw domein bij Office 365 terechtkomt</span><span class="sxs-lookup"><span data-stu-id="50f2a-109">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="50f2a-110">Voeg de vier CNAME-records toe die voor Office 365 vereist zijn.</span><span class="sxs-lookup"><span data-stu-id="50f2a-110">Add the four CNAME records that are required for Office 365</span></span>](#add-the-four-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="50f2a-111">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="50f2a-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [<span data-ttu-id="50f2a-112">Voeg de vier SRV-records toe die voor Office 365 vereist zijn.</span><span class="sxs-lookup"><span data-stu-id="50f2a-112">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="50f2a-113">Nadat u deze records bij Azure hebt toegevoegd, wordt uw domein ingesteld voor gebruik met Office 365-services.</span><span class="sxs-lookup"><span data-stu-id="50f2a-113">After you add these records at Azure, your domain will be set up to work with Office 365 services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="50f2a-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="50f2a-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="50f2a-117">De naamserverrecords (NS-records) van uw domein wijzigen</span><span class="sxs-lookup"><span data-stu-id="50f2a-117">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="50f2a-118"><a name="BKMK_NS"> </a></span><span class="sxs-lookup"><span data-stu-id="50f2a-118"><a name="BKMK_NS"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="50f2a-119">U moet deze procedure uitvoeren bij de domeinregistrar waar u uw domein hebt gekocht en geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="50f2a-119">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="50f2a-120">Toen u zich aanmeldde voor Azure, hebt u een brongroep binnen een DNS-zone gemaakt en vervolgens uw domeinnaam toegewezen aan die brongroep.</span><span class="sxs-lookup"><span data-stu-id="50f2a-120">When you signed up for Azure, you created a resource group within a DNS zone, and then assigned your domain name to that resource group.</span></span> <span data-ttu-id="50f2a-121">Die domeinnaam is geregistreerd bij een externe domeinregistrar; Azure biedt geen domeinregistratieservices.</span><span class="sxs-lookup"><span data-stu-id="50f2a-121">That domain name is registered to an external domain registrar; Azure does not offer domain registration services.</span></span>
  
<span data-ttu-id="50f2a-122">Als u DNS-records voor uw domein wilt verifiëren en maken in Office 365, moet u eerst de naamservers van uw domeinregistrar wijzigen, zodat ze de Azure-naamservers gebruiken die zijn toegewezen aan uw brongroep.</span><span class="sxs-lookup"><span data-stu-id="50f2a-122">To verify and create DNS records for your domain in Office 365, you first need to change the nameservers at your domain registrar so that they use the Azure nameservers assigned to your resource group.</span></span>
  
<span data-ttu-id="50f2a-123">Als u de naamservers van het domein zelf wilt wijzigen op de website van de domeinregistrar, voert u de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="50f2a-123">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="50f2a-124">Zoek het gedeelte op de website van de domeinregistrar waarop u de naamservers voor uw domein kunt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="50f2a-124">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="50f2a-125">Maak twee naamserverrecords door de waarden in de volgende tabel te gebruiken of bewerk de bestaande naamserverrecords zodat ze overeenkomen met deze waarden:</span><span class="sxs-lookup"><span data-stu-id="50f2a-125">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span> <span data-ttu-id="50f2a-126">Hieronder wordt een voorbeeld van door Azure toegewezen nameservers weergegeven.</span><span class="sxs-lookup"><span data-stu-id="50f2a-126">An example of Azure assigned nameservers is shown below.</span></span>
    


<span data-ttu-id="50f2a-127">**Voornaamserver:** Gebruik de naamserverwaarde die door Azure is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="50f2a-127">**First nameserver:** Use the name server value assigned by Azure.</span></span>  
<span data-ttu-id="50f2a-128">**Tweede naamserver:** Gebruik de naamserverwaarde die door Azure is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="50f2a-128">**Second nameserver:** Use the name server value assigned by Azure.</span></span>  

![Afbeelding van het lint](../../media/3e4805ea-608a-4df9-8f68-1fbf70d13d08.png)
  
> [!TIP]
> <span data-ttu-id="50f2a-130">U moet ten minste twee naamserverrecords gebruiken.</span><span class="sxs-lookup"><span data-stu-id="50f2a-130">You should use at least two name server records.</span></span> <span data-ttu-id="50f2a-131">Als er andere naamservers op de website van uw domeinregistrar worden vermeld, moet u deze verwijderen.</span><span class="sxs-lookup"><span data-stu-id="50f2a-131">If there are any other name servers listed at your domain registrar's website, you should delete them.</span></span> 
  
3. <span data-ttu-id="50f2a-132">Sla uw wijzigingen op.</span><span class="sxs-lookup"><span data-stu-id="50f2a-132">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="50f2a-p105">Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd. Vervolgens worden uw e-mail voor Office 365 en andere services ingesteld voor gebruik met uw domein.</span><span class="sxs-lookup"><span data-stu-id="50f2a-p105">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="50f2a-135">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="50f2a-135">Add a TXT record for verification</span></span>
<span data-ttu-id="50f2a-136"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="50f2a-136"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="50f2a-p106">Voordat u uw domein met Office 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Office 365 bewezen.</span><span class="sxs-lookup"><span data-stu-id="50f2a-p106">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="50f2a-p107">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="50f2a-p107">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="50f2a-141">Ga om aan de slag te gaan naar de pagina met domeinen in Azure via [deze koppeling.](https://portal.azure.com )</span><span class="sxs-lookup"><span data-stu-id="50f2a-141">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="50f2a-142">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="50f2a-142">You'll be prompted to log in first.</span></span>
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="50f2a-144">Typ **dns-zones**in de **zoekbalk** op de **dashboardpagina.**</span><span class="sxs-lookup"><span data-stu-id="50f2a-144">Using the **search bar** on the **Dashboard** page, type in **DNS zones**.</span></span> <span data-ttu-id="50f2a-145">Selecteer **dns-zones** onder het gedeelte **Services** in de resultatenweergave.</span><span class="sxs-lookup"><span data-stu-id="50f2a-145">In the results display, select **DNS zones** under the **Services** portion.</span></span> <span data-ttu-id="50f2a-146">Zodra u bent omgeleid, selecteert u het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="50f2a-146">Once you've been redirected, select the domain that you want to update.</span></span>
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="50f2a-148">Selecteer op de pagina **Instellingen** voor uw domein in het **gebied DNS-zone** de optie **+ Recordset .**</span><span class="sxs-lookup"><span data-stu-id="50f2a-148">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="50f2a-150">Selecteer in het **gebied Record toevoegen in** de vakken voor de nieuwe recordset de waarden in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="50f2a-150">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="50f2a-151">(Kies de **eenheidswaarden Type** en **TTL** in de vervolgkeuzelijsten.)</span><span class="sxs-lookup"><span data-stu-id="50f2a-151">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="50f2a-152">**Naam**</span><span class="sxs-lookup"><span data-stu-id="50f2a-152">**Name**</span></span>|<span data-ttu-id="50f2a-153">**Type**</span><span class="sxs-lookup"><span data-stu-id="50f2a-153">**Type**</span></span>|<span data-ttu-id="50f2a-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="50f2a-154">**TTL**</span></span>|<span data-ttu-id="50f2a-155">**TTL-eenheid**</span><span class="sxs-lookup"><span data-stu-id="50f2a-155">**TTL unit**</span></span>|<span data-ttu-id="50f2a-156">**Value**</span><span class="sxs-lookup"><span data-stu-id="50f2a-156">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="50f2a-157">TXT</span><span class="sxs-lookup"><span data-stu-id="50f2a-157">TXT</span></span>  <br/> |<span data-ttu-id="50f2a-158">1</span><span class="sxs-lookup"><span data-stu-id="50f2a-158">1</span></span>  <br/> |<span data-ttu-id="50f2a-159">Uren</span><span class="sxs-lookup"><span data-stu-id="50f2a-159">Hours</span></span>  <br/> |<span data-ttu-id="50f2a-160">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="50f2a-160">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="50f2a-p110">**Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="50f2a-p110">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![Afbeelding van het te maken van de afbeelding van het gebruik van Azure-Verifiëren 1-1](../../media/7d5a253c-e88f-4565-a00a-79bba52f9970.png)
  
5. <span data-ttu-id="50f2a-165">Kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="50f2a-165">Select **OK**.</span></span>
  
6. <span data-ttu-id="50f2a-166">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="50f2a-166">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="50f2a-167">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Office 365 en vraagt u of Office 365 naar de record wil zoeken.</span><span class="sxs-lookup"><span data-stu-id="50f2a-167">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="50f2a-168">Wanneer in Office 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="50f2a-168">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="50f2a-169">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="50f2a-169">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="50f2a-170">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="50f2a-170">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="50f2a-171">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="50f2a-171">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="50f2a-172">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="50f2a-172">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="50f2a-p111">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="50f2a-p111">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="50f2a-176">Een MX-record toevoegen zodat e-mail voor uw domein bij Office 365 terechtkomt</span><span class="sxs-lookup"><span data-stu-id="50f2a-176">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="50f2a-177"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="50f2a-177"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="50f2a-178">Ga om aan de slag te gaan naar de pagina met domeinen in Azure via [deze koppeling.](https://portal.azure.com )</span><span class="sxs-lookup"><span data-stu-id="50f2a-178">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="50f2a-179">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="50f2a-179">You'll be prompted to log in first.</span></span>
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="50f2a-181">Selecteer op de pagina **Dashboard** in het gebied **Alle bronnen** het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="50f2a-181">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="50f2a-183">Selecteer op de pagina **Instellingen** voor uw domein in het **gebied DNS-zone** de optie **+ Recordset .**</span><span class="sxs-lookup"><span data-stu-id="50f2a-183">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="50f2a-185">Selecteer in het **gebied Record toevoegen in** de vakken voor de nieuwe recordset de waarden in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="50f2a-185">In the **Add record set** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="50f2a-186">(Kies de **eenheidswaarden Type** en **TTL** in de vervolgkeuzelijsten.)</span><span class="sxs-lookup"><span data-stu-id="50f2a-186">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="50f2a-187">**Naam**</span><span class="sxs-lookup"><span data-stu-id="50f2a-187">**Name**</span></span>|<span data-ttu-id="50f2a-188">**Type**</span><span class="sxs-lookup"><span data-stu-id="50f2a-188">**Type**</span></span>|<span data-ttu-id="50f2a-189">**TTL**</span><span class="sxs-lookup"><span data-stu-id="50f2a-189">**TTL**</span></span>|<span data-ttu-id="50f2a-190">**TTL-eenheid**</span><span class="sxs-lookup"><span data-stu-id="50f2a-190">**TTL unit**</span></span>|<span data-ttu-id="50f2a-191">**Preference**</span><span class="sxs-lookup"><span data-stu-id="50f2a-191">**Preference**</span></span>|<span data-ttu-id="50f2a-192">**Mail Exchange**</span><span class="sxs-lookup"><span data-stu-id="50f2a-192">**Mail Exchange**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="50f2a-193">MX</span><span class="sxs-lookup"><span data-stu-id="50f2a-193">MX</span></span>  <br/> |<span data-ttu-id="50f2a-194">1</span><span class="sxs-lookup"><span data-stu-id="50f2a-194">1</span></span>  <br/> |<span data-ttu-id="50f2a-195">Uren</span><span class="sxs-lookup"><span data-stu-id="50f2a-195">Hours</span></span>  <br/> |<span data-ttu-id="50f2a-196">10</span><span class="sxs-lookup"><span data-stu-id="50f2a-196">10</span></span>  <br/> <span data-ttu-id="50f2a-197">Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.</span><span class="sxs-lookup"><span data-stu-id="50f2a-197">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="50f2a-198">*\<domeinsleutel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="50f2a-198">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="50f2a-199">**Let op:** Haal uw \* \<domeinsleutel\> \* op uit uw Office 365-account.</span><span class="sxs-lookup"><span data-stu-id="50f2a-199">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="50f2a-200">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="50f2a-200">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  
   
    ![Afbeelding van het te maken van de afbeelding smakende afbeelding van het bis](../../media/712c23ae-9d38-4af2-94e0-0704e70744fe.png)
  
5. <span data-ttu-id="50f2a-202">Kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="50f2a-202">Select **OK**.</span></span>
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-BP-2-2](../../media/2f24225f-69ac-41dc-91c5-93d327360f74.png)
  
6. <span data-ttu-id="50f2a-204">Als er andere MX-records worden vermeld in de sectie **MX Records,** moet u deze verwijderen.</span><span class="sxs-lookup"><span data-stu-id="50f2a-204">If there are any other MX records listed in the **MX Records** section, you must delete them.</span></span> 
    
    <span data-ttu-id="50f2a-205">Selecteer eerst in het **gebied met DNS-zone** de **set MX Record**.</span><span class="sxs-lookup"><span data-stu-id="50f2a-205">First, in the **DNS zone** area, select the **MX Record set**.</span></span>
    
    ![Afbeelding van het te maken van de afbeelding smakende afbeelding van het bis](../../media/9890da61-6fcd-4c61-888e-ccbb84f80cd0.png)
  
    <span data-ttu-id="50f2a-207">Selecteer vervolgens de MX-record die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="50f2a-207">Next, select the MX record you want to delete.</span></span>
    
    ![Afbeelding van het te maken van de afbeelding smakende afbeelding van het bis](../../media/afe54f12-66d2-4ff3-80e9-427448e4c32c.png)
  
7. <span data-ttu-id="50f2a-209">Selecteer het **menu Context (...)** en kies **Verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="50f2a-209">Select the **Context menu (…)**, and then choose **Remove**.</span></span>
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-BP-2-5](../../media/25219e25-bc14-4bc7-84ed-ee65eb28a8ed.png)
  
8. <span data-ttu-id="50f2a-211">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="50f2a-211">Select **Save**.</span></span>
    
    ![Afbeelding van het te maken van de afbeelding smakende afbeelding van de knop 2-6](../../media/c6133096-5e43-4637-9c01-b63ee4b03517.png)
  
## <a name="add-the-four-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="50f2a-213">Voeg de vier CNAME-records toe die voor Office 365 vereist zijn.</span><span class="sxs-lookup"><span data-stu-id="50f2a-213">Add the four CNAME records that are required for Office 365</span></span>
<span data-ttu-id="50f2a-214"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="50f2a-214"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="50f2a-215">Ga om aan de slag te gaan naar de pagina met domeinen in Azure via [deze koppeling.](https://portal.azure.com )</span><span class="sxs-lookup"><span data-stu-id="50f2a-215">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="50f2a-216">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="50f2a-216">You'll be prompted to log in first.</span></span>
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="50f2a-218">Selecteer op de pagina **Dashboard** in het gebied **Alle bronnen** het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="50f2a-218">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="50f2a-220">Selecteer op de pagina **Instellingen** voor uw domein in het **gebied DNS-zone** de optie **+ Recordset .**</span><span class="sxs-lookup"><span data-stu-id="50f2a-220">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="50f2a-222">Voeg de eerste van de vier CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="50f2a-222">Add the first of the four CNAME records.</span></span>
    
    <span data-ttu-id="50f2a-223">Typ of kopieer en plak de waarden uit de eerste rij in de volgende tabel in het **gebied Recordset toevoegen** in de vakken voor de nieuwe recordset.</span><span class="sxs-lookup"><span data-stu-id="50f2a-223">In the **Add record set** area, in the boxes for the new record set, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="50f2a-224">(Kies de **eenheidswaarden Type** en **TTL** in de vervolgkeuzelijsten.)</span><span class="sxs-lookup"><span data-stu-id="50f2a-224">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="50f2a-225">**Naam**</span><span class="sxs-lookup"><span data-stu-id="50f2a-225">**Name**</span></span>|<span data-ttu-id="50f2a-226">**Type**</span><span class="sxs-lookup"><span data-stu-id="50f2a-226">**Type**</span></span>|<span data-ttu-id="50f2a-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="50f2a-227">**TTL**</span></span>|<span data-ttu-id="50f2a-228">**TTL-eenheid**</span><span class="sxs-lookup"><span data-stu-id="50f2a-228">**TTL unit**</span></span>|<span data-ttu-id="50f2a-229">**Alias**</span><span class="sxs-lookup"><span data-stu-id="50f2a-229">**Alias**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="50f2a-230">autodiscover</span><span class="sxs-lookup"><span data-stu-id="50f2a-230">autodiscover</span></span>  <br/> |<span data-ttu-id="50f2a-231">CNAME</span><span class="sxs-lookup"><span data-stu-id="50f2a-231">CNAME</span></span>  <br/> |<span data-ttu-id="50f2a-232">1</span><span class="sxs-lookup"><span data-stu-id="50f2a-232">1</span></span>  <br/> |<span data-ttu-id="50f2a-233">Uren</span><span class="sxs-lookup"><span data-stu-id="50f2a-233">Hours</span></span>  <br/> |<span data-ttu-id="50f2a-234">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="50f2a-234">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="50f2a-235">sip</span><span class="sxs-lookup"><span data-stu-id="50f2a-235">sip</span></span>  <br/> |<span data-ttu-id="50f2a-236">CNAME</span><span class="sxs-lookup"><span data-stu-id="50f2a-236">CNAME</span></span>  <br/> |<span data-ttu-id="50f2a-237">1</span><span class="sxs-lookup"><span data-stu-id="50f2a-237">1</span></span>  <br/> |<span data-ttu-id="50f2a-238">Uren</span><span class="sxs-lookup"><span data-stu-id="50f2a-238">Hours</span></span>  <br/> |<span data-ttu-id="50f2a-239">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="50f2a-239">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="50f2a-240">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="50f2a-240">lyncdiscover</span></span>  <br/> |<span data-ttu-id="50f2a-241">CNAME</span><span class="sxs-lookup"><span data-stu-id="50f2a-241">CNAME</span></span>  <br/> |<span data-ttu-id="50f2a-242">1</span><span class="sxs-lookup"><span data-stu-id="50f2a-242">1</span></span>  <br/> |<span data-ttu-id="50f2a-243">Uren</span><span class="sxs-lookup"><span data-stu-id="50f2a-243">Hours</span></span>  <br/> |<span data-ttu-id="50f2a-244">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="50f2a-244">webdir.online.lync.com</span></span>  <br/> |
    
   
    ![Afbeelding van het te maken van de afbeelding smakende afbeelding van het menu Voor Azure](../../media/a1c4d869-da97-43b3-952c-d513a20231dc.png)
  
5. <span data-ttu-id="50f2a-246">Kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="50f2a-246">Select **OK**.</span></span>
    
    ![Afbeelding van het te maken van afbeelding van het gebruik van Azure-afbeelding](../../media/b89b51da-1c07-43cf-9fab-75d2e5eb3544.png)
  
6. <span data-ttu-id="50f2a-248">Voeg de andere drie CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="50f2a-248">Add each of the other three CNAME records.</span></span>
    
    <span data-ttu-id="50f2a-249">Selecteer in het **gebied met DE DNS-zone** de optie **+ Recordset**.</span><span class="sxs-lookup"><span data-stu-id="50f2a-249">In the **DNS zone** area, select **+ Record set**.</span></span> <span data-ttu-id="50f2a-250">Maak vervolgens in de lege recordset een record met de waarden uit de volgende rij in de tabel en selecteer opnieuw **OK** om die record te voltooien.</span><span class="sxs-lookup"><span data-stu-id="50f2a-250">Then, in the empty record set, create a record by using the values from the next row in the table, and again select **OK** to complete that record.</span></span> 
    
    <span data-ttu-id="50f2a-251">Herhaal deze procedure totdat u alle vier CNAME-records hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="50f2a-251">Repeat this process until you have created all four CNAME records.</span></span>
    
7.  <span data-ttu-id="50f2a-252">(Optioneel) Voeg 2 CNAME-records toe voor MDM.</span><span class="sxs-lookup"><span data-stu-id="50f2a-252">(Optional) Add 2 CNAME records for MDM.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="50f2a-253">Als u Mobile Device Management (MDM) voor Office 365 hebt, moet u twee extra CNAME-records maken.</span><span class="sxs-lookup"><span data-stu-id="50f2a-253">If you have Mobile Device Management (MDM) for Office 365, then you must create two additional CNAME records.</span></span> <span data-ttu-id="50f2a-254">Volg de stappen die u hebt gevolgd voor de andere vier CNAME-records, maar gebruik de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="50f2a-254">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="50f2a-255">(Als u geen MDM hebt, u deze stap overslaan.)</span><span class="sxs-lookup"><span data-stu-id="50f2a-255">(If you do not have MDM, you can skip this step.)</span></span> 
  
|<span data-ttu-id="50f2a-256">**Naam**</span><span class="sxs-lookup"><span data-stu-id="50f2a-256">**Name**</span></span>|<span data-ttu-id="50f2a-257">**Type**</span><span class="sxs-lookup"><span data-stu-id="50f2a-257">**Type**</span></span>|<span data-ttu-id="50f2a-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="50f2a-258">**TTL**</span></span>|<span data-ttu-id="50f2a-259">**TTL-eenheid**</span><span class="sxs-lookup"><span data-stu-id="50f2a-259">**TTL unit**</span></span>|<span data-ttu-id="50f2a-260">**Alias**</span><span class="sxs-lookup"><span data-stu-id="50f2a-260">**Alias**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="50f2a-261">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="50f2a-261">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="50f2a-262">CNAME</span><span class="sxs-lookup"><span data-stu-id="50f2a-262">CNAME</span></span>  <br/> |<span data-ttu-id="50f2a-263">1</span><span class="sxs-lookup"><span data-stu-id="50f2a-263">1</span></span>  <br/> |<span data-ttu-id="50f2a-264">Uren</span><span class="sxs-lookup"><span data-stu-id="50f2a-264">Hours</span></span>  <br/> |<span data-ttu-id="50f2a-265">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="50f2a-265">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="50f2a-266">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="50f2a-266">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="50f2a-267">CNAME</span><span class="sxs-lookup"><span data-stu-id="50f2a-267">CNAME</span></span>  <br/> |<span data-ttu-id="50f2a-268">1</span><span class="sxs-lookup"><span data-stu-id="50f2a-268">1</span></span>  <br/> |<span data-ttu-id="50f2a-269">Uren</span><span class="sxs-lookup"><span data-stu-id="50f2a-269">Hours</span></span>  <br/> |<span data-ttu-id="50f2a-270">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="50f2a-270">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="50f2a-271">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="50f2a-271">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="50f2a-272"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="50f2a-272"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="50f2a-273">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="50f2a-273">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="50f2a-274">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="50f2a-274">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="50f2a-275">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Office 365 te maken.</span><span class="sxs-lookup"><span data-stu-id="50f2a-275">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="50f2a-276">In plaats daarvan voegt u de vereiste Office 365-waarden toe aan de huidige record, zodat u beschikt over  *één*  SPF-record waarin beide sets waarden zijn opgenomen.</span><span class="sxs-lookup"><span data-stu-id="50f2a-276">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="50f2a-277">Ga om aan de slag te gaan naar de pagina met domeinen in Azure via [deze koppeling.](https://portal.azure.com )</span><span class="sxs-lookup"><span data-stu-id="50f2a-277">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="50f2a-278">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="50f2a-278">You'll be prompted to log in first.</span></span>
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="50f2a-280">Selecteer op de pagina **Dashboard** in het gebied **Alle bronnen** het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="50f2a-280">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="50f2a-282">Selecteer in het **gebied met DNS-zone** de **set TXT-record**.</span><span class="sxs-lookup"><span data-stu-id="50f2a-282">In the **DNS zone** area, select the **TXT record set**.</span></span>
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-afbeelding](../../media/03095196-5010-4072-8503-79b812084dbf.png)
  
4. <span data-ttu-id="50f2a-284">Selecteer in het gebied **Recordset-eigenschappen** in de vakken voor de nieuwe recordset de waarden in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="50f2a-284">In the **Record set properties** area, in the boxes for the new record set, select the values from the following table.</span></span> 
    
    <span data-ttu-id="50f2a-285">(Kies de **eenheidswaarden Type** en **TTL** in de vervolgkeuzelijsten.)</span><span class="sxs-lookup"><span data-stu-id="50f2a-285">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="50f2a-286">**Naam**</span><span class="sxs-lookup"><span data-stu-id="50f2a-286">**Name**</span></span>|<span data-ttu-id="50f2a-287">**Type**</span><span class="sxs-lookup"><span data-stu-id="50f2a-287">**Type**</span></span>|<span data-ttu-id="50f2a-288">**TTL**</span><span class="sxs-lookup"><span data-stu-id="50f2a-288">**TTL**</span></span>|<span data-ttu-id="50f2a-289">**TTL-eenheid**</span><span class="sxs-lookup"><span data-stu-id="50f2a-289">**TTL unit**</span></span>|<span data-ttu-id="50f2a-290">**Value**</span><span class="sxs-lookup"><span data-stu-id="50f2a-290">**Value**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="50f2a-291">TXT</span><span class="sxs-lookup"><span data-stu-id="50f2a-291">TXT</span></span>  <br/> |<span data-ttu-id="50f2a-292">1</span><span class="sxs-lookup"><span data-stu-id="50f2a-292">1</span></span>  <br/> |<span data-ttu-id="50f2a-293">Uren</span><span class="sxs-lookup"><span data-stu-id="50f2a-293">Hours</span></span>  <br/> |<span data-ttu-id="50f2a-294">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="50f2a-294">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="50f2a-295">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="50f2a-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           

    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-afbeelding](../../media/78e84c43-e0ce-433f-8e74-9157fb093cca.png)
  
5. <span data-ttu-id="50f2a-297">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="50f2a-297">Select **Save**.</span></span>
    
    ![Afbeelding van het te maken van de afbeelding smakende afbeelding van het menu 4-3](../../media/d7421c7f-ea63-4e11-8595-a482b8c165e0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="50f2a-299">De twee SRV-records toevoegen die voor Office 365 vereist zijn</span><span class="sxs-lookup"><span data-stu-id="50f2a-299">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="50f2a-300"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="50f2a-300"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="50f2a-301">Ga om aan de slag te gaan naar de pagina met domeinen in Azure via [deze koppeling.](https://portal.azure.com )</span><span class="sxs-lookup"><span data-stu-id="50f2a-301">To get started, go to your domains page at Azure by using [this link](https://portal.azure.com ).</span></span> <span data-ttu-id="50f2a-302">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="50f2a-302">You'll be prompted to log in first.</span></span>
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. <span data-ttu-id="50f2a-304">Selecteer op de pagina **Dashboard** in het gebied **Alle bronnen** het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="50f2a-304">On the **Dashboard** page, in the **All resources** area, select the domain that you want to update.</span></span> 
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. <span data-ttu-id="50f2a-306">Selecteer op de pagina **Instellingen** voor uw domein in het **gebied DNS-zone** de optie **+ Recordset .**</span><span class="sxs-lookup"><span data-stu-id="50f2a-306">On the **Settings** page for your domain, in the **DNS zone** area, select **+ Record set**.</span></span>
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. <span data-ttu-id="50f2a-308">Voeg de eerste van de twee SRV-records toe.</span><span class="sxs-lookup"><span data-stu-id="50f2a-308">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="50f2a-309">Selecteer in het **gebied Record toevoegen in** de vakken voor de nieuwe recordset de waarden uit de eerste rij in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="50f2a-309">In the **Add record set** area, in the boxes for the new record set, select the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="50f2a-310">(Kies de **eenheidswaarden Type** en **TTL** in de vervolgkeuzelijsten.)</span><span class="sxs-lookup"><span data-stu-id="50f2a-310">(Choose the **Type** and **TTL unit** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="50f2a-311">**Naam**</span><span class="sxs-lookup"><span data-stu-id="50f2a-311">**Name**</span></span>|<span data-ttu-id="50f2a-312">**Type**</span><span class="sxs-lookup"><span data-stu-id="50f2a-312">**Type**</span></span>|<span data-ttu-id="50f2a-313">**TTL**</span><span class="sxs-lookup"><span data-stu-id="50f2a-313">**TTL**</span></span>|<span data-ttu-id="50f2a-314">**TTL-eenheid**</span><span class="sxs-lookup"><span data-stu-id="50f2a-314">**TTL unit**</span></span>|<span data-ttu-id="50f2a-315">**Prioriteit**</span><span class="sxs-lookup"><span data-stu-id="50f2a-315">**Priority**</span></span>|<span data-ttu-id="50f2a-316">**Gewicht**</span><span class="sxs-lookup"><span data-stu-id="50f2a-316">**Weight**</span></span>|<span data-ttu-id="50f2a-317">**Poort**</span><span class="sxs-lookup"><span data-stu-id="50f2a-317">**Port**</span></span>|<span data-ttu-id="50f2a-318">**Target**</span><span class="sxs-lookup"><span data-stu-id="50f2a-318">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="50f2a-319">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="50f2a-319">_sip._tls</span></span>  <br/> |<span data-ttu-id="50f2a-320">SRV</span><span class="sxs-lookup"><span data-stu-id="50f2a-320">SRV</span></span>  <br/> |<span data-ttu-id="50f2a-321">1</span><span class="sxs-lookup"><span data-stu-id="50f2a-321">1</span></span>  <br/> |<span data-ttu-id="50f2a-322">Uren</span><span class="sxs-lookup"><span data-stu-id="50f2a-322">Hours</span></span>  <br/> |<span data-ttu-id="50f2a-323">100</span><span class="sxs-lookup"><span data-stu-id="50f2a-323">100</span></span>  <br/> |<span data-ttu-id="50f2a-324">1</span><span class="sxs-lookup"><span data-stu-id="50f2a-324">1</span></span>  <br/> |<span data-ttu-id="50f2a-325">443</span><span class="sxs-lookup"><span data-stu-id="50f2a-325">443</span></span>  <br/> |<span data-ttu-id="50f2a-326">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="50f2a-326">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="50f2a-327">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="50f2a-327">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="50f2a-328">SRV</span><span class="sxs-lookup"><span data-stu-id="50f2a-328">SRV</span></span>  <br/> |<span data-ttu-id="50f2a-329">1</span><span class="sxs-lookup"><span data-stu-id="50f2a-329">1</span></span>  <br/> |<span data-ttu-id="50f2a-330">Uren</span><span class="sxs-lookup"><span data-stu-id="50f2a-330">Hours</span></span>  <br/> |<span data-ttu-id="50f2a-331">100</span><span class="sxs-lookup"><span data-stu-id="50f2a-331">100</span></span>  <br/> |<span data-ttu-id="50f2a-332">1</span><span class="sxs-lookup"><span data-stu-id="50f2a-332">1</span></span>  <br/> |<span data-ttu-id="50f2a-333">5061</span><span class="sxs-lookup"><span data-stu-id="50f2a-333">5061</span></span>  <br/> |<span data-ttu-id="50f2a-334">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="50f2a-334">sipfed.online.lync.com</span></span>  <br/> 

    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-BP-5-1](../../media/a436e0b4-8bb8-4a66-9c22-4e3b2dcf54ff.png)
  
5. <span data-ttu-id="50f2a-336">Kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="50f2a-336">Select **OK**.</span></span>
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-BP-5-2](../../media/a35b6c8a-d001-4b3c-8a67-96b4890e564c.png)
  
6. <span data-ttu-id="50f2a-338">Voeg de andere SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="50f2a-338">Add the other SRV record.</span></span>
    
    <span data-ttu-id="50f2a-339">Typ of kopieer en plak de waarden uit de tweede rij van de tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="50f2a-339">In the boxes for the new record, type or copy and paste the values from the second row of the table.</span></span>
    
> [!NOTE]
> <span data-ttu-id="50f2a-p120">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="50f2a-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
