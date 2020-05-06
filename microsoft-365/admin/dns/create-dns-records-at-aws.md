---
title: DNS-records maken bij Amazon Web Services (AWS) voor Microsoft
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
ms.assetid: 7a2efd75-0771-4897-ba7b-082fe5bfa9da
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services bij Amazon Web Services (AWS) voor Microsoft.
ms.openlocfilehash: d75822feef5848575b8ec7fe09f834f67cdc6c55
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049105"
---
# <a name="create-dns-records-at-amazon-web-services-aws-for-microsoft"></a><span data-ttu-id="7b6b0-103">DNS-records maken bij Amazon Web Services (AWS) voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="7b6b0-103">Create DNS records at Amazon Web Services (AWS) for Microsoft</span></span>

 <span data-ttu-id="7b6b0-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="7b6b0-105">Als AWS uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records in te stellen voor e-mail, Skype Online voor Bedrijven, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-105">If AWS is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype Online for Business, and so on.</span></span>
  
<span data-ttu-id="7b6b0-106">Nadat u deze records bij AWS hebt toegevoegd, wordt uw domein ingesteld om te werken met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-106">After you add these records at AWS, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="7b6b0-p101">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7b6b0-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="7b6b0-110">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="7b6b0-110">Add a TXT record for verification</span></span>
<span data-ttu-id="7b6b0-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="7b6b0-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="7b6b0-p102">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7b6b0-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="7b6b0-116">Als u wilt beginnen, gaat u naar uw domeinenpagina bij AWS via [deze koppeling](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="7b6b0-116">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="7b6b0-117">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-117">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="7b6b0-118">Selecteer op de pagina **Resources** de optie **Gehoste zones**.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-118">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="7b6b0-119">Selecteer op de pagina **Gehoste zones** in de kolom **Domeinnaam** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-119">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="7b6b0-120">Selecteer **Recordset maken**.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-120">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="7b6b0-121">Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Create Record Set** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-121">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="7b6b0-122">(Kies in de vervolgkeuzelijsten de waarden **Type** en **Routing Policy**.)</span><span class="sxs-lookup"><span data-stu-id="7b6b0-122">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="7b6b0-p105">De aanhalingstekens die zijn vereist volgens de instructies op het scherm, worden automatisch ingevoegd. U hoeft deze niet handmatig te typen.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
    |||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7b6b0-125">**Name**</span><span class="sxs-lookup"><span data-stu-id="7b6b0-125">**Name**</span></span> <br/> |<span data-ttu-id="7b6b0-126">**Type**</span><span class="sxs-lookup"><span data-stu-id="7b6b0-126">**Type**</span></span> <br/> |<span data-ttu-id="7b6b0-127">**Alias**</span><span class="sxs-lookup"><span data-stu-id="7b6b0-127">**Alias**</span></span> <br/> |<span data-ttu-id="7b6b0-128">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="7b6b0-128">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="7b6b0-129">**Value**</span><span class="sxs-lookup"><span data-stu-id="7b6b0-129">**Value**</span></span> <br/> |<span data-ttu-id="7b6b0-130">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="7b6b0-130">**Routing Policy**</span></span> <br/> |
    |<span data-ttu-id="7b6b0-131">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="7b6b0-131">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="7b6b0-132">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="7b6b0-132">TXT - Text</span></span>  <br/> |<span data-ttu-id="7b6b0-133">No</span><span class="sxs-lookup"><span data-stu-id="7b6b0-133">No</span></span>  <br/> |<span data-ttu-id="7b6b0-134">300</span><span class="sxs-lookup"><span data-stu-id="7b6b0-134">300</span></span>  <br/> |<span data-ttu-id="7b6b0-135">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="7b6b0-135">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="7b6b0-136">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-136">**Note:** This is an example.</span></span> <span data-ttu-id="7b6b0-137">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-137">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span> [<span data-ttu-id="7b6b0-138">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="7b6b0-138">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="7b6b0-139">Simple</span><span class="sxs-lookup"><span data-stu-id="7b6b0-139">Simple</span></span>  <br/> |
   
6. <span data-ttu-id="7b6b0-140">Selecteer **Maken**.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-140">Select **Create**.</span></span>
    
7. <span data-ttu-id="7b6b0-141">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-141">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="7b6b0-142">Nu u de record op de site van uw domeinregistrar hebt toegevoegd, gaat u terug naar Microsoft en vraagt u om een zoekopdracht naar de record.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-142">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="7b6b0-143">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-143">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="7b6b0-144">Ga in het Microsoft-beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-144">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="7b6b0-145">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-145">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="7b6b0-146">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-146">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="7b6b0-147">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-147">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7b6b0-p107">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7b6b0-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft-365"></a><span data-ttu-id="7b6b0-151">Voeg een MX-record toe, zodat e-mail voor uw domein naar Microsoft 365 komt</span><span class="sxs-lookup"><span data-stu-id="7b6b0-151">Add an MX record so email for your domain will come to Microsoft 365</span></span>
<span data-ttu-id="7b6b0-152"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="7b6b0-152"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="7b6b0-p108">Als u wilt beginnen, gaat u naar uw domeinenpagina bij AWS via [deze koppeling](https://console.aws.amazon.com/route53/home). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-p108">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="7b6b0-155">Selecteer op de pagina **Resources** de optie **Gehoste zones**.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-155">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="7b6b0-156">Selecteer op de pagina **Gehoste zones** in de kolom **Domeinnaam** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-156">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="7b6b0-157">Selecteer **Recordset maken**.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-157">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="7b6b0-158">Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Create Record Set** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-158">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="7b6b0-159">(Kies in de vervolgkeuzelijsten de waarden **Type** en **Routing Policy**.)</span><span class="sxs-lookup"><span data-stu-id="7b6b0-159">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="7b6b0-160">**Naam**</span><span class="sxs-lookup"><span data-stu-id="7b6b0-160">**Name**</span></span>|<span data-ttu-id="7b6b0-161">**Type**</span><span class="sxs-lookup"><span data-stu-id="7b6b0-161">**Type**</span></span>|<span data-ttu-id="7b6b0-162">**Alias**</span><span class="sxs-lookup"><span data-stu-id="7b6b0-162">**Alias**</span></span>|<span data-ttu-id="7b6b0-163">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="7b6b0-163">**TTL (Seconds)**</span></span>|<span data-ttu-id="7b6b0-164">**Value**</span><span class="sxs-lookup"><span data-stu-id="7b6b0-164">**Value**</span></span>|<span data-ttu-id="7b6b0-165">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="7b6b0-165">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7b6b0-166">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="7b6b0-166">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="7b6b0-167">MX - e-mailuitwisseling</span><span class="sxs-lookup"><span data-stu-id="7b6b0-167">MX - Mail exchange</span></span>  <br/> |<span data-ttu-id="7b6b0-168">Nee</span><span class="sxs-lookup"><span data-stu-id="7b6b0-168">No</span></span>  <br/> |<span data-ttu-id="7b6b0-169">300</span><span class="sxs-lookup"><span data-stu-id="7b6b0-169">300</span></span>  <br/> |<span data-ttu-id="7b6b0-170">0  *\< domeinsleutel\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-170">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="7b6b0-p109">De 0 is de MX-prioriteitwaarde. Voeg deze toe aan het begin van de MX-waarde, van de rest van de waarde gescheiden door een spatie.  </span><span class="sxs-lookup"><span data-stu-id="7b6b0-p109">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="7b6b0-173">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="7b6b0-173">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="7b6b0-174">**Let op:** Haal \<uw domeinsleutel\> op van uw Microsoft 365-account. *domain-key*</span><span class="sxs-lookup"><span data-stu-id="7b6b0-174">**Note:** Get your \<*domain-key*\> from your Microsoft 365 account.</span></span> [<span data-ttu-id="7b6b0-175">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="7b6b0-175">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="7b6b0-176">Simple</span><span class="sxs-lookup"><span data-stu-id="7b6b0-176">Simple</span></span>  <br/> |
       
    ![Afbeelding van het te maken van afbeelding van het](../../media/94a71ce7-1b3b-4b1a-9ad3-9592db133075.png)
  
6. <span data-ttu-id="7b6b0-178">Selecteer **Maken**.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-178">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-2-2](../../media/1c050c72-c04f-48d5-a8e9-44cd83ddd33e.png)
  
7. <span data-ttu-id="7b6b0-180">Als er andere MX-records zijn, verwijdert u deze.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-180">If there are any other MX records, remove them.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7b6b0-181">AWS slaat MX-records op als een set die meerdere records kan bevatten.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-181">AWS stores MX records as a set that may contain multiple records.</span></span> <span data-ttu-id="7b6b0-182">**Selecteer recordset verwijderen NIET,** omdat hiermee al uw MX-records worden verwijderd, inclusief de records die u zojuist hebt toegevoegd. **Delete Record Set**</span><span class="sxs-lookup"><span data-stu-id="7b6b0-182">**DO NOT** select **Delete Record Set**, as this will delete all of your MX records, including the one you just added.</span></span> <span data-ttu-id="7b6b0-183">Gebruik in plaats daarvan de volgende instructies.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-183">Use the following instructions instead.</span></span> 
  
    <span data-ttu-id="7b6b0-184">Selecteer eerst de MX-recordset.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-184">First, select the MX record set.</span></span>
    
    ![AWS-BP-Configure-2-3](../../media/9d9388cb-e2d0-43b7-928c-e1d07e519c6f.png)
  
    <span data-ttu-id="7b6b0-186">Vervolgens verwijdert u in het gebied **Edit Record Set** (recordset bewerken) elk van de oude MX-records door de record te selecteren in het vak **Value** en op de toets **Delete** op uw toetsenbord te drukken.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-186">Next, in the **Edit Record Set** area, delete each obsolete MX record by selecting the entry in the **Value** box and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![AWS-BP-Configure-2-4](../../media/c3b0c1bc-21ab-44cc-84b7-f504725c5540.png)
  
8. <span data-ttu-id="7b6b0-188">Selecteer **Recordset opslaan**.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-188">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-2-5](../../media/86f0998d-f5d4-4750-a93d-ac13b318c40b.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="7b6b0-190">Voeg de vijf CNAME-records toe die nodig zijn voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7b6b0-190">Add the five CNAME records that are required for Microsoft 365</span></span>
<span data-ttu-id="7b6b0-191"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="7b6b0-191"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="7b6b0-p112">Als u wilt beginnen, gaat u naar uw domeinenpagina bij AWS via [deze koppeling](https://console.aws.amazon.com/route53/home). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-p112">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="7b6b0-194">Selecteer op de pagina **Resources** de optie **Gehoste zones**.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-194">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="7b6b0-195">Selecteer op de pagina **Gehoste zones** in de kolom **Domeinnaam** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-195">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="7b6b0-196">Selecteer **Recordset maken**.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-196">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="7b6b0-197">Voeg de eerste CNAME-record toe.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-197">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="7b6b0-198">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in het gebied **Create Record Set** (recordset maken) in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-198">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="7b6b0-199">(Kies in de vervolgkeuzelijsten de waarden **Type** en **Routing Policy**.)</span><span class="sxs-lookup"><span data-stu-id="7b6b0-199">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="7b6b0-200">**Naam**</span><span class="sxs-lookup"><span data-stu-id="7b6b0-200">**Name**</span></span>|<span data-ttu-id="7b6b0-201">**Type**</span><span class="sxs-lookup"><span data-stu-id="7b6b0-201">**Type**</span></span>|<span data-ttu-id="7b6b0-202">**Alias**</span><span class="sxs-lookup"><span data-stu-id="7b6b0-202">**Alias**</span></span>|<span data-ttu-id="7b6b0-203">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="7b6b0-203">**TTL (Seconds)**</span></span>|<span data-ttu-id="7b6b0-204">**Value**</span><span class="sxs-lookup"><span data-stu-id="7b6b0-204">**Value**</span></span>|<span data-ttu-id="7b6b0-205">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="7b6b0-205">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7b6b0-206">autodiscover</span><span class="sxs-lookup"><span data-stu-id="7b6b0-206">autodiscover</span></span>  <br/> |<span data-ttu-id="7b6b0-207">CNAME - Canonical name</span><span class="sxs-lookup"><span data-stu-id="7b6b0-207">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="7b6b0-208">Nee</span><span class="sxs-lookup"><span data-stu-id="7b6b0-208">No</span></span>  <br/> |<span data-ttu-id="7b6b0-209">300</span><span class="sxs-lookup"><span data-stu-id="7b6b0-209">300</span></span>  <br/> |<span data-ttu-id="7b6b0-210">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-210">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="7b6b0-211">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="7b6b0-211">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="7b6b0-212">Simple</span><span class="sxs-lookup"><span data-stu-id="7b6b0-212">Simple</span></span>  <br/> |
    |<span data-ttu-id="7b6b0-213">sip</span><span class="sxs-lookup"><span data-stu-id="7b6b0-213">sip</span></span>  <br/> |<span data-ttu-id="7b6b0-214">CNAME - Canonical name</span><span class="sxs-lookup"><span data-stu-id="7b6b0-214">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="7b6b0-215">Nee</span><span class="sxs-lookup"><span data-stu-id="7b6b0-215">No</span></span>  <br/> |<span data-ttu-id="7b6b0-216">300</span><span class="sxs-lookup"><span data-stu-id="7b6b0-216">300</span></span>  <br/> |<span data-ttu-id="7b6b0-217">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-217">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="7b6b0-218">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="7b6b0-218">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="7b6b0-219">Simple</span><span class="sxs-lookup"><span data-stu-id="7b6b0-219">Simple</span></span>  <br/> |
    |<span data-ttu-id="7b6b0-220">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="7b6b0-220">lyncdiscover</span></span>  <br/> |<span data-ttu-id="7b6b0-221">CNAME - Canonical name</span><span class="sxs-lookup"><span data-stu-id="7b6b0-221">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="7b6b0-222">Nee</span><span class="sxs-lookup"><span data-stu-id="7b6b0-222">No</span></span>  <br/> |<span data-ttu-id="7b6b0-223">300</span><span class="sxs-lookup"><span data-stu-id="7b6b0-223">300</span></span>  <br/> |<span data-ttu-id="7b6b0-224">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-224">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="7b6b0-225">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="7b6b0-225">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="7b6b0-226">Dat is eenvoudig</span><span class="sxs-lookup"><span data-stu-id="7b6b0-226">Simple</span></span>  <br/> |
    |<span data-ttu-id="7b6b0-227">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="7b6b0-227">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="7b6b0-228">CNAME - Canonical name</span><span class="sxs-lookup"><span data-stu-id="7b6b0-228">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="7b6b0-229">Nee</span><span class="sxs-lookup"><span data-stu-id="7b6b0-229">No</span></span>  <br/> |<span data-ttu-id="7b6b0-230">300</span><span class="sxs-lookup"><span data-stu-id="7b6b0-230">300</span></span>  <br/> |<span data-ttu-id="7b6b0-231">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-231">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="7b6b0-232">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="7b6b0-232">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="7b6b0-233">Simple</span><span class="sxs-lookup"><span data-stu-id="7b6b0-233">Simple</span></span>  <br/> |
    |<span data-ttu-id="7b6b0-234">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="7b6b0-234">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="7b6b0-235">CNAME - Canonical name</span><span class="sxs-lookup"><span data-stu-id="7b6b0-235">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="7b6b0-236">Nee</span><span class="sxs-lookup"><span data-stu-id="7b6b0-236">No</span></span>  <br/> |<span data-ttu-id="7b6b0-237">300</span><span class="sxs-lookup"><span data-stu-id="7b6b0-237">300</span></span>  <br/> |<span data-ttu-id="7b6b0-238">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-238">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="7b6b0-239">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="7b6b0-239">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="7b6b0-240">Simple</span><span class="sxs-lookup"><span data-stu-id="7b6b0-240">Simple</span></span>  <br/> |
   
    ![Afbeelding van het te maken van afbeelding van het gebruik](../../media/895c71bd-0e3a-425e-9681-98c1c67e714b.png)
  
6. <span data-ttu-id="7b6b0-242">Selecteer **Maken**.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-242">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-3-2](../../media/33964846-5282-44a4-b241-62ce02b96735.png)
  
7. <span data-ttu-id="7b6b0-244">Voeg de andere vier CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-244">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="7b6b0-245">Selecteer op de pagina **Gehoste zones** **Recordset maken,** maak een record met de waarden uit de volgende rij in de tabel en selecteer vervolgens opnieuw **Maken** om die record te voltooien.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-245">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
    <span data-ttu-id="7b6b0-246">Herhaal dit proces totdat u alle vijf CNAME-records hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-246">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="7b6b0-247">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="7b6b0-247">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="7b6b0-248"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="7b6b0-248"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="7b6b0-249">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-249">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="7b6b0-250">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-250">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="7b6b0-251">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-251">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="7b6b0-252">Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-252">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="7b6b0-253">Hebt u voorbeelden nodig?</span><span class="sxs-lookup"><span data-stu-id="7b6b0-253">Need examples?</span></span> <span data-ttu-id="7b6b0-254">Bekijk deze [Externe Domain Name System-records voor Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records).</span><span class="sxs-lookup"><span data-stu-id="7b6b0-254">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="7b6b0-255">Als u uw SPF-record wilt valideren, u een van deze[SPF-validatietools](../setup/domains-faq.md)gebruiken.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-255">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="7b6b0-256">Als u wilt beginnen, gaat u naar uw domeinenpagina bij AWS via [deze koppeling](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="7b6b0-256">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="7b6b0-257">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-257">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="7b6b0-258">Selecteer op de pagina **Resources** de optie **Gehoste zones**.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-258">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="7b6b0-259">Selecteer op de pagina **Gehoste zones** in de kolom **Domeinnaam** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-259">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="7b6b0-260">Selecteer de **TXT-recordset.**</span><span class="sxs-lookup"><span data-stu-id="7b6b0-260">Select the **TXT** record set.</span></span> 
    
    ![AWS-BP-Configure-4-1](../../media/0310fa66-c016-4987-80df-930f1c8f3c39.png)
  
5. <span data-ttu-id="7b6b0-p115">Druk in het gebied **Edit Record Set** aan het einde van de huidige invoer in het vak **Value:** voor de bestaande record op Enter op uw toetsenbord om een nieuwe regel te maken, en typ of plak op die nieuwe regel (onder de bestaande waarde) de waarde uit de volgende tabel. (U ziet een voorbeeld in de afbeelding onder de tabel.)</span><span class="sxs-lookup"><span data-stu-id="7b6b0-p115">In the **Edit Record Set** area, at the end of the current entry in the **Value:** box for the existing record, press Enter on your keyboard to create a new line; and then, on that new line (under the existing value), type or copy and paste the value from the following table. (You can see an example in the illustration below the table.)</span></span> 
    
    |<span data-ttu-id="7b6b0-264">**Waarde:**</span><span class="sxs-lookup"><span data-stu-id="7b6b0-264">**Value:**</span></span>|
    |:-----|
    |<span data-ttu-id="7b6b0-265">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="7b6b0-265">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="7b6b0-p116">(De aanhalingstekens die volgens de instructies op het scherm vereist zijn, worden automatisch ingevoegd. U hoeft deze niet handmatig te typen.)  </span><span class="sxs-lookup"><span data-stu-id="7b6b0-p116">(The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.)  </span></span><br/> <span data-ttu-id="7b6b0-268">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-268">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Afbeelding van het te maken van afbeelding van het gebruik](../../media/beb3c086-eaf8-4245-9860-18512a3ff72e.png)
  
6. <span data-ttu-id="7b6b0-270">Selecteer **Recordset opslaan**.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-270">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-4-3](../../media/94b9306c-bdc9-4f84-ad6f-6d12edbfde90.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft-365"></a><span data-ttu-id="7b6b0-272">Voeg de twee SRV-records toe die nodig zijn voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7b6b0-272">Add the two SRV records that are required for Microsoft 365</span></span>
<span data-ttu-id="7b6b0-273"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="7b6b0-273"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="7b6b0-p117">Als u wilt beginnen, gaat u naar uw domeinenpagina bij AWS via [deze koppeling](https://console.aws.amazon.com/route53/home). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-p117">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="7b6b0-276">Selecteer op de pagina **Resources** de optie **Gehoste zones**.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-276">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="7b6b0-277">Selecteer op de pagina **Gehoste zones** in de kolom **Domeinnaam** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-277">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="7b6b0-278">Selecteer **Recordset maken**.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-278">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="7b6b0-279">Voeg de eerste SRV-record toe:</span><span class="sxs-lookup"><span data-stu-id="7b6b0-279">Add the first SRV record:</span></span>
    
    <span data-ttu-id="7b6b0-280">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in het gebied **Create Record Set** (recordset maken) in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-280">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="7b6b0-281">(Kies in de vervolgkeuzelijsten de waarden **Type** en **Routing Policy**.)</span><span class="sxs-lookup"><span data-stu-id="7b6b0-281">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="7b6b0-282">**Name**</span><span class="sxs-lookup"><span data-stu-id="7b6b0-282">**Name**</span></span>|<span data-ttu-id="7b6b0-283">**Type**</span><span class="sxs-lookup"><span data-stu-id="7b6b0-283">**Type**</span></span>|<span data-ttu-id="7b6b0-284">**Alias**</span><span class="sxs-lookup"><span data-stu-id="7b6b0-284">**Alias**</span></span>|<span data-ttu-id="7b6b0-285">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="7b6b0-285">**TTL (Seconds)**</span></span>|<span data-ttu-id="7b6b0-286">**Value**</span><span class="sxs-lookup"><span data-stu-id="7b6b0-286">**Value**</span></span>|<span data-ttu-id="7b6b0-287">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="7b6b0-287">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="7b6b0-288">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="7b6b0-288">_sip._tls</span></span>|<span data-ttu-id="7b6b0-289">SRV - Service locator</span><span class="sxs-lookup"><span data-stu-id="7b6b0-289">SRV - Service locator</span></span>|<span data-ttu-id="7b6b0-290">Nee</span><span class="sxs-lookup"><span data-stu-id="7b6b0-290">No</span></span>|<span data-ttu-id="7b6b0-291">300</span><span class="sxs-lookup"><span data-stu-id="7b6b0-291">300</span></span>|<span data-ttu-id="7b6b0-292">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-292">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="7b6b0-293">**Deze waarde MOET eindigen met een periode (.)**></span><span class="sxs-lookup"><span data-stu-id="7b6b0-293">**This value MUST end with a period (.)**></span></span><br> <span data-ttu-id="7b6b0-294">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-294">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="7b6b0-295">Simple</span><span class="sxs-lookup"><span data-stu-id="7b6b0-295">Simple</span></span>|
    |<span data-ttu-id="7b6b0-296">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="7b6b0-296">_sipfederationtls._tcp</span></span>|<span data-ttu-id="7b6b0-297">SRV - Service locator</span><span class="sxs-lookup"><span data-stu-id="7b6b0-297">SRV - Service locator</span></span>|<span data-ttu-id="7b6b0-298">Nee</span><span class="sxs-lookup"><span data-stu-id="7b6b0-298">No</span></span>|<span data-ttu-id="7b6b0-299">300</span><span class="sxs-lookup"><span data-stu-id="7b6b0-299">300</span></span>|<span data-ttu-id="7b6b0-300">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-300">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="7b6b0-301">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="7b6b0-301">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="7b6b0-302">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-302">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="7b6b0-303">Simple</span><span class="sxs-lookup"><span data-stu-id="7b6b0-303">Simple</span></span>|
   
    ![Afbeelding van het te maken van afbeelding van het gebruik](../../media/c3f841d3-6076-428f-bb04-e71cc5f392fa.png)
  
6. <span data-ttu-id="7b6b0-305">Selecteer **Maken**.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-305">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-5-2](../../media/1bf5dc58-a46b-47a5-bd69-7c2147dd4e50.png)
  
7. <span data-ttu-id="7b6b0-307">De andere SRV-record toevoegen:</span><span class="sxs-lookup"><span data-stu-id="7b6b0-307">To add the other SRV record:</span></span>
    
    <span data-ttu-id="7b6b0-308">Selecteer op de pagina **Gehoste zones** **Recordset maken,** maak een record met de waarden uit de volgende rij in de tabel en selecteer vervolgens opnieuw **Maken** om die record te voltooien.</span><span class="sxs-lookup"><span data-stu-id="7b6b0-308">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="7b6b0-p120">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7b6b0-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
