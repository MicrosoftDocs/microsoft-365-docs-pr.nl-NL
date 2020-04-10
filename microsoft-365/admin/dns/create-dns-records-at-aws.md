---
title: DNS-records bij AWS (Amazon Web Services) maken voor Office 365
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
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services bij Amazon Web Services (AWS) voor Office 365.
ms.openlocfilehash: f71e6fa5ce69d789cc7695d30e6447ae281a0e3f
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211845"
---
# <a name="create-dns-records-at-amazon-web-services-aws-for-office-365"></a><span data-ttu-id="44cff-103">DNS-records bij AWS (Amazon Web Services) maken voor Office 365</span><span class="sxs-lookup"><span data-stu-id="44cff-103">Create DNS records at Amazon Web Services (AWS) for Office 365</span></span>

 <span data-ttu-id="44cff-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="44cff-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="44cff-105">Als AWS uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records in te stellen voor e-mail, Skype Online voor Bedrijven, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="44cff-105">If AWS is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype Online for Business, and so on.</span></span>
  
<span data-ttu-id="44cff-106">Nadat u deze records bij AWS hebt toegevoegd, is uw domein ingesteld voor gebruik met Office 365-services.</span><span class="sxs-lookup"><span data-stu-id="44cff-106">After you add these records at AWS, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="44cff-107">Zie [Een openbare website gebruiken met Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9) voor informatie over webhosting en DNS voor websites met Office 365.</span><span class="sxs-lookup"><span data-stu-id="44cff-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="44cff-p101">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="44cff-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="44cff-111">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="44cff-111">Add a TXT record for verification</span></span>
<span data-ttu-id="44cff-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="44cff-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="44cff-p102">Voordat u uw domein met Office 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Office 365 bewezen.</span><span class="sxs-lookup"><span data-stu-id="44cff-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="44cff-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="44cff-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="44cff-117">Als u wilt beginnen, gaat u naar uw domeinenpagina bij AWS via [deze koppeling](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="44cff-117">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="44cff-118">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="44cff-118">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="44cff-119">Selecteer op de pagina **Resources** de optie **Gehoste zones**.</span><span class="sxs-lookup"><span data-stu-id="44cff-119">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="44cff-120">Selecteer op de pagina \*\* Gehoste zones \*\* in de kolom **Domeinnaam** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="44cff-120">On the \*\* Hosted Zones \*\* page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="44cff-121">Selecteer **Recordset maken**.</span><span class="sxs-lookup"><span data-stu-id="44cff-121">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="44cff-122">Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Create Record Set** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="44cff-122">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="44cff-123">(Kies in de vervolgkeuzelijsten de waarden **Type** en **Routing Policy**.)</span><span class="sxs-lookup"><span data-stu-id="44cff-123">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="44cff-p105">De aanhalingstekens die zijn vereist volgens de instructies op het scherm, worden automatisch ingevoegd. U hoeft deze niet handmatig te typen.</span><span class="sxs-lookup"><span data-stu-id="44cff-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
    |||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="44cff-126">**Name**</span><span class="sxs-lookup"><span data-stu-id="44cff-126">**Name**</span></span> <br/> |<span data-ttu-id="44cff-127">**Type**</span><span class="sxs-lookup"><span data-stu-id="44cff-127">**Type**</span></span> <br/> |<span data-ttu-id="44cff-128">**Alias**</span><span class="sxs-lookup"><span data-stu-id="44cff-128">**Alias**</span></span> <br/> |<span data-ttu-id="44cff-129">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="44cff-129">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="44cff-130">**Value**</span><span class="sxs-lookup"><span data-stu-id="44cff-130">**Value**</span></span> <br/> |<span data-ttu-id="44cff-131">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="44cff-131">**Routing Policy**</span></span> <br/> |
    |<span data-ttu-id="44cff-132">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="44cff-132">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="44cff-133">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="44cff-133">TXT - Text</span></span>  <br/> |<span data-ttu-id="44cff-134">No</span><span class="sxs-lookup"><span data-stu-id="44cff-134">No</span></span>  <br/> |<span data-ttu-id="44cff-135">300</span><span class="sxs-lookup"><span data-stu-id="44cff-135">300</span></span>  <br/> |<span data-ttu-id="44cff-136">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="44cff-136">MS=ms *XXXXXXXX*</span></span>  <br/><span data-ttu-id="44cff-137">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="44cff-137">**Note:** This is an example.</span></span> <span data-ttu-id="44cff-138">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365.</span><span class="sxs-lookup"><span data-stu-id="44cff-138">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="44cff-139">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="44cff-139">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="44cff-140">Simple</span><span class="sxs-lookup"><span data-stu-id="44cff-140">Simple</span></span>  <br/> |
   
6. <span data-ttu-id="44cff-141">Selecteer **Maken**.</span><span class="sxs-lookup"><span data-stu-id="44cff-141">Select **Create**.</span></span>
    
7. <span data-ttu-id="44cff-142">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="44cff-142">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="44cff-143">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Office 365 en vraagt u of Office 365 naar de record wil zoeken.</span><span class="sxs-lookup"><span data-stu-id="44cff-143">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="44cff-144">Wanneer in Office 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="44cff-144">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="44cff-145">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="44cff-145">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="44cff-146">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="44cff-146">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="44cff-147">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="44cff-147">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="44cff-148">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="44cff-148">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="44cff-p107">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="44cff-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="44cff-152">Een MX-record toevoegen zodat e-mail voor uw domein bij Office 365 terechtkomt</span><span class="sxs-lookup"><span data-stu-id="44cff-152">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="44cff-153"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="44cff-153"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="44cff-p108">Als u wilt beginnen, gaat u naar uw domeinenpagina bij AWS via [deze koppeling](https://console.aws.amazon.com/route53/home). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="44cff-p108">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="44cff-156">Selecteer op de pagina **Resources** de optie **Gehoste zones**.</span><span class="sxs-lookup"><span data-stu-id="44cff-156">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="44cff-157">Selecteer op de pagina **Gehoste zones** in de kolom **Domeinnaam** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="44cff-157">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="44cff-158">Selecteer **Recordset maken**.</span><span class="sxs-lookup"><span data-stu-id="44cff-158">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="44cff-159">Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Create Record Set** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="44cff-159">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="44cff-160">(Kies in de vervolgkeuzelijsten de waarden **Type** en **Routing Policy**.)</span><span class="sxs-lookup"><span data-stu-id="44cff-160">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="44cff-161">**Naam**</span><span class="sxs-lookup"><span data-stu-id="44cff-161">**Name**</span></span>|<span data-ttu-id="44cff-162">**Type**</span><span class="sxs-lookup"><span data-stu-id="44cff-162">**Type**</span></span>|<span data-ttu-id="44cff-163">**Alias**</span><span class="sxs-lookup"><span data-stu-id="44cff-163">**Alias**</span></span>|<span data-ttu-id="44cff-164">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="44cff-164">**TTL (Seconds)**</span></span>|<span data-ttu-id="44cff-165">**Value**</span><span class="sxs-lookup"><span data-stu-id="44cff-165">**Value**</span></span>|<span data-ttu-id="44cff-166">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="44cff-166">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="44cff-167">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="44cff-167">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="44cff-168">MX - e-mailuitwisseling</span><span class="sxs-lookup"><span data-stu-id="44cff-168">MX - Mail exchange</span></span>  <br/> |<span data-ttu-id="44cff-169">Nee</span><span class="sxs-lookup"><span data-stu-id="44cff-169">No</span></span>  <br/> |<span data-ttu-id="44cff-170">300</span><span class="sxs-lookup"><span data-stu-id="44cff-170">300</span></span>  <br/> |<span data-ttu-id="44cff-171">0  *\< domeinsleutel\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="44cff-171">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="44cff-p109">De 0 is de MX-prioriteitwaarde. Voeg deze toe aan het begin van de MX-waarde, van de rest van de waarde gescheiden door een spatie.  </span><span class="sxs-lookup"><span data-stu-id="44cff-p109">The 0 is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="44cff-174">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="44cff-174">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="44cff-175">**Opmerking**: Uw \<*domeinsleutel*\> kunt u ophalen uit uw Office 365-account.</span><span class="sxs-lookup"><span data-stu-id="44cff-175">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span> [<span data-ttu-id="44cff-176">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="44cff-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="44cff-177">Simple</span><span class="sxs-lookup"><span data-stu-id="44cff-177">Simple</span></span>  <br/> |
       
    ![Afbeelding van het te maken van afbeelding van het](../../media/94a71ce7-1b3b-4b1a-9ad3-9592db133075.png)
  
6. <span data-ttu-id="44cff-179">Selecteer **Maken**.</span><span class="sxs-lookup"><span data-stu-id="44cff-179">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-2-2](../../media/1c050c72-c04f-48d5-a8e9-44cd83ddd33e.png)
  
7. <span data-ttu-id="44cff-181">Als er andere MX-records zijn, verwijdert u deze.</span><span class="sxs-lookup"><span data-stu-id="44cff-181">If there are any other MX records, remove them.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="44cff-182">AWS slaat MX-records op als een set die meerdere records kan bevatten.</span><span class="sxs-lookup"><span data-stu-id="44cff-182">AWS stores MX records as a set that may contain multiple records.</span></span> <span data-ttu-id="44cff-183">**Selecteer recordset verwijderen NIET,** omdat hiermee al uw MX-records worden verwijderd, inclusief de records die u zojuist hebt toegevoegd. **Delete Record Set**</span><span class="sxs-lookup"><span data-stu-id="44cff-183">**DO NOT** select **Delete Record Set**, as this will delete all of your MX records, including the one you just added.</span></span> <span data-ttu-id="44cff-184">Gebruik in plaats daarvan de volgende instructies.</span><span class="sxs-lookup"><span data-stu-id="44cff-184">Use the following instructions instead.</span></span> 
  
    <span data-ttu-id="44cff-185">Selecteer eerst de MX-recordset.</span><span class="sxs-lookup"><span data-stu-id="44cff-185">First, select the MX record set.</span></span>
    
    ![AWS-BP-Configure-2-3](../../media/9d9388cb-e2d0-43b7-928c-e1d07e519c6f.png)
  
    <span data-ttu-id="44cff-187">Vervolgens verwijdert u in het gebied **Edit Record Set** (recordset bewerken) elk van de oude MX-records door de record te selecteren in het vak **Value** en op de toets **Delete** op uw toetsenbord te drukken.</span><span class="sxs-lookup"><span data-stu-id="44cff-187">Next, in the **Edit Record Set** area, delete each obsolete MX record by selecting the entry in the **Value** box and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![AWS-BP-Configure-2-4](../../media/c3b0c1bc-21ab-44cc-84b7-f504725c5540.png)
  
8. <span data-ttu-id="44cff-189">Selecteer **Recordset opslaan**.</span><span class="sxs-lookup"><span data-stu-id="44cff-189">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-2-5](../../media/86f0998d-f5d4-4750-a93d-ac13b318c40b.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="44cff-191">De vijf CNAME-records toevoegen die nodig zijn voor Office 365</span><span class="sxs-lookup"><span data-stu-id="44cff-191">Add the five CNAME records that are required for Office 365</span></span>
<span data-ttu-id="44cff-192"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="44cff-192"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="44cff-p112">Als u wilt beginnen, gaat u naar uw domeinenpagina bij AWS via [deze koppeling](https://console.aws.amazon.com/route53/home). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="44cff-p112">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="44cff-195">Selecteer op de pagina **Resources** de optie **Gehoste zones**.</span><span class="sxs-lookup"><span data-stu-id="44cff-195">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="44cff-196">Selecteer op de pagina **Gehoste zones** in de kolom **Domeinnaam** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="44cff-196">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="44cff-197">Selecteer **Recordset maken**.</span><span class="sxs-lookup"><span data-stu-id="44cff-197">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="44cff-198">Voeg de eerste CNAME-record toe.</span><span class="sxs-lookup"><span data-stu-id="44cff-198">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="44cff-199">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in het gebied **Create Record Set** (recordset maken) in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="44cff-199">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="44cff-200">(Kies in de vervolgkeuzelijsten de waarden **Type** en **Routing Policy**.)</span><span class="sxs-lookup"><span data-stu-id="44cff-200">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="44cff-201">**Naam**</span><span class="sxs-lookup"><span data-stu-id="44cff-201">**Name**</span></span>|<span data-ttu-id="44cff-202">**Type**</span><span class="sxs-lookup"><span data-stu-id="44cff-202">**Type**</span></span>|<span data-ttu-id="44cff-203">**Alias**</span><span class="sxs-lookup"><span data-stu-id="44cff-203">**Alias**</span></span>|<span data-ttu-id="44cff-204">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="44cff-204">**TTL (Seconds)**</span></span>|<span data-ttu-id="44cff-205">**Value**</span><span class="sxs-lookup"><span data-stu-id="44cff-205">**Value**</span></span>|<span data-ttu-id="44cff-206">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="44cff-206">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="44cff-207">autodiscover</span><span class="sxs-lookup"><span data-stu-id="44cff-207">autodiscover</span></span>  <br/> |<span data-ttu-id="44cff-208">CNAME - Canonical name</span><span class="sxs-lookup"><span data-stu-id="44cff-208">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="44cff-209">Nee</span><span class="sxs-lookup"><span data-stu-id="44cff-209">No</span></span>  <br/> |<span data-ttu-id="44cff-210">300</span><span class="sxs-lookup"><span data-stu-id="44cff-210">300</span></span>  <br/> |<span data-ttu-id="44cff-211">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="44cff-211">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="44cff-212">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="44cff-212">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="44cff-213">Simple</span><span class="sxs-lookup"><span data-stu-id="44cff-213">Simple</span></span>  <br/> |
    |<span data-ttu-id="44cff-214">sip</span><span class="sxs-lookup"><span data-stu-id="44cff-214">sip</span></span>  <br/> |<span data-ttu-id="44cff-215">CNAME - Canonical name</span><span class="sxs-lookup"><span data-stu-id="44cff-215">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="44cff-216">Nee</span><span class="sxs-lookup"><span data-stu-id="44cff-216">No</span></span>  <br/> |<span data-ttu-id="44cff-217">300</span><span class="sxs-lookup"><span data-stu-id="44cff-217">300</span></span>  <br/> |<span data-ttu-id="44cff-218">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="44cff-218">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="44cff-219">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="44cff-219">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="44cff-220">Simple</span><span class="sxs-lookup"><span data-stu-id="44cff-220">Simple</span></span>  <br/> |
    |<span data-ttu-id="44cff-221">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="44cff-221">lyncdiscover</span></span>  <br/> |<span data-ttu-id="44cff-222">CNAME - Canonical name</span><span class="sxs-lookup"><span data-stu-id="44cff-222">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="44cff-223">Nee</span><span class="sxs-lookup"><span data-stu-id="44cff-223">No</span></span>  <br/> |<span data-ttu-id="44cff-224">300</span><span class="sxs-lookup"><span data-stu-id="44cff-224">300</span></span>  <br/> |<span data-ttu-id="44cff-225">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="44cff-225">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="44cff-226">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="44cff-226">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="44cff-227">Dat is eenvoudig</span><span class="sxs-lookup"><span data-stu-id="44cff-227">Simple</span></span>  <br/> |
    |<span data-ttu-id="44cff-228">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="44cff-228">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="44cff-229">CNAME - Canonical name</span><span class="sxs-lookup"><span data-stu-id="44cff-229">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="44cff-230">Nee</span><span class="sxs-lookup"><span data-stu-id="44cff-230">No</span></span>  <br/> |<span data-ttu-id="44cff-231">300</span><span class="sxs-lookup"><span data-stu-id="44cff-231">300</span></span>  <br/> |<span data-ttu-id="44cff-232">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="44cff-232">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="44cff-233">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="44cff-233">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="44cff-234">Simple</span><span class="sxs-lookup"><span data-stu-id="44cff-234">Simple</span></span>  <br/> |
    |<span data-ttu-id="44cff-235">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="44cff-235">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="44cff-236">CNAME - Canonical name</span><span class="sxs-lookup"><span data-stu-id="44cff-236">CNAME - Canonical name</span></span>  <br/> |<span data-ttu-id="44cff-237">Nee</span><span class="sxs-lookup"><span data-stu-id="44cff-237">No</span></span>  <br/> |<span data-ttu-id="44cff-238">300</span><span class="sxs-lookup"><span data-stu-id="44cff-238">300</span></span>  <br/> |<span data-ttu-id="44cff-239">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="44cff-239">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="44cff-240">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="44cff-240">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="44cff-241">Simple</span><span class="sxs-lookup"><span data-stu-id="44cff-241">Simple</span></span>  <br/> |
   
    ![Afbeelding van het te maken van afbeelding van het gebruik](../../media/895c71bd-0e3a-425e-9681-98c1c67e714b.png)
  
6. <span data-ttu-id="44cff-243">Selecteer **Maken**.</span><span class="sxs-lookup"><span data-stu-id="44cff-243">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-3-2](../../media/33964846-5282-44a4-b241-62ce02b96735.png)
  
7. <span data-ttu-id="44cff-245">Voeg de andere vier CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="44cff-245">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="44cff-246">Selecteer op de pagina **Gehoste zones** **Recordset maken,** maak een record met de waarden uit de volgende rij in de tabel en selecteer vervolgens opnieuw **Maken** om die record te voltooien.</span><span class="sxs-lookup"><span data-stu-id="44cff-246">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
    <span data-ttu-id="44cff-247">Herhaal dit proces totdat u alle vijf CNAME-records hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="44cff-247">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="44cff-248">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="44cff-248">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="44cff-249"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="44cff-249"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="44cff-250">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="44cff-250">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="44cff-251">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="44cff-251">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="44cff-252">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Office 365 te maken.</span><span class="sxs-lookup"><span data-stu-id="44cff-252">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="44cff-253">In plaats daarvan voegt u de vereiste Office 365-waarden toe aan de huidige record, zodat u beschikt over  *één*  SPF-record waarin beide sets waarden zijn opgenomen.</span><span class="sxs-lookup"><span data-stu-id="44cff-253">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="44cff-254">Hebt u voorbeelden nodig?</span><span class="sxs-lookup"><span data-stu-id="44cff-254">Need examples?</span></span> <span data-ttu-id="44cff-255">Bekijk deze [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span><span class="sxs-lookup"><span data-stu-id="44cff-255">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="44cff-256">Als u uw SPF-record wilt valideren, u een van deze[SPF-validatietools](../setup/domains-faq.md)gebruiken.</span><span class="sxs-lookup"><span data-stu-id="44cff-256">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="44cff-257">Als u wilt beginnen, gaat u naar uw domeinenpagina bij AWS via [deze koppeling](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="44cff-257">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="44cff-258">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="44cff-258">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="44cff-259">Selecteer op de pagina **Resources** de optie **Gehoste zones**.</span><span class="sxs-lookup"><span data-stu-id="44cff-259">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="44cff-260">Selecteer op de pagina **Gehoste zones** in de kolom **Domeinnaam** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="44cff-260">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="44cff-261">Selecteer de **TXT-recordset.**</span><span class="sxs-lookup"><span data-stu-id="44cff-261">Select the **TXT** record set.</span></span> 
    
    ![AWS-BP-Configure-4-1](../../media/0310fa66-c016-4987-80df-930f1c8f3c39.png)
  
5. <span data-ttu-id="44cff-p115">Druk in het gebied **Edit Record Set** aan het einde van de huidige invoer in het vak **Value:** voor de bestaande record op Enter op uw toetsenbord om een nieuwe regel te maken, en typ of plak op die nieuwe regel (onder de bestaande waarde) de waarde uit de volgende tabel. (U ziet een voorbeeld in de afbeelding onder de tabel.)</span><span class="sxs-lookup"><span data-stu-id="44cff-p115">In the **Edit Record Set** area, at the end of the current entry in the **Value:** box for the existing record, press Enter on your keyboard to create a new line; and then, on that new line (under the existing value), type or copy and paste the value from the following table. (You can see an example in the illustration below the table.)</span></span> 
    
    |<span data-ttu-id="44cff-265">**Waarde:**</span><span class="sxs-lookup"><span data-stu-id="44cff-265">**Value:**</span></span>|
    |:-----|
    |<span data-ttu-id="44cff-266">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="44cff-266">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="44cff-p116">(De aanhalingstekens die volgens de instructies op het scherm vereist zijn, worden automatisch ingevoegd. U hoeft deze niet handmatig te typen.)  </span><span class="sxs-lookup"><span data-stu-id="44cff-p116">(The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.)  </span></span><br/> <span data-ttu-id="44cff-269">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="44cff-269">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Afbeelding van het te maken van afbeelding van het gebruik](../../media/beb3c086-eaf8-4245-9860-18512a3ff72e.png)
  
6. <span data-ttu-id="44cff-271">Selecteer **Recordset opslaan**.</span><span class="sxs-lookup"><span data-stu-id="44cff-271">Select **Save Record Set**.</span></span>
    
    ![AWS-BP-Configure-4-3](../../media/94b9306c-bdc9-4f84-ad6f-6d12edbfde90.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="44cff-273">De twee SRV-records toevoegen die voor Office 365 vereist zijn</span><span class="sxs-lookup"><span data-stu-id="44cff-273">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="44cff-274"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="44cff-274"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="44cff-p117">Als u wilt beginnen, gaat u naar uw domeinenpagina bij AWS via [deze koppeling](https://console.aws.amazon.com/route53/home). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="44cff-p117">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="44cff-277">Selecteer op de pagina **Resources** de optie **Gehoste zones**.</span><span class="sxs-lookup"><span data-stu-id="44cff-277">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="44cff-278">Selecteer op de pagina **Gehoste zones** in de kolom **Domeinnaam** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="44cff-278">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="44cff-279">Selecteer **Recordset maken**.</span><span class="sxs-lookup"><span data-stu-id="44cff-279">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="44cff-280">Voeg de eerste SRV-record toe:</span><span class="sxs-lookup"><span data-stu-id="44cff-280">Add the first SRV record:</span></span>
    
    <span data-ttu-id="44cff-281">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in het gebied **Create Record Set** (recordset maken) in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="44cff-281">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    <span data-ttu-id="44cff-282">(Kies in de vervolgkeuzelijsten de waarden **Type** en **Routing Policy**.)</span><span class="sxs-lookup"><span data-stu-id="44cff-282">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    |<span data-ttu-id="44cff-283">**Name**</span><span class="sxs-lookup"><span data-stu-id="44cff-283">**Name**</span></span>|<span data-ttu-id="44cff-284">**Type**</span><span class="sxs-lookup"><span data-stu-id="44cff-284">**Type**</span></span>|<span data-ttu-id="44cff-285">**Alias**</span><span class="sxs-lookup"><span data-stu-id="44cff-285">**Alias**</span></span>|<span data-ttu-id="44cff-286">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="44cff-286">**TTL (Seconds)**</span></span>|<span data-ttu-id="44cff-287">**Value**</span><span class="sxs-lookup"><span data-stu-id="44cff-287">**Value**</span></span>|<span data-ttu-id="44cff-288">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="44cff-288">**Routing Policy**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="44cff-289">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="44cff-289">_sip._tls</span></span>|<span data-ttu-id="44cff-290">SRV - Service locator</span><span class="sxs-lookup"><span data-stu-id="44cff-290">SRV - Service locator</span></span>|<span data-ttu-id="44cff-291">Nee</span><span class="sxs-lookup"><span data-stu-id="44cff-291">No</span></span>|<span data-ttu-id="44cff-292">300</span><span class="sxs-lookup"><span data-stu-id="44cff-292">300</span></span>|<span data-ttu-id="44cff-293">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="44cff-293">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="44cff-294">**Deze waarde MOET eindigen met een periode (.)**></span><span class="sxs-lookup"><span data-stu-id="44cff-294">**This value MUST end with a period (.)**></span></span><br> <span data-ttu-id="44cff-295">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="44cff-295">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="44cff-296">Simple</span><span class="sxs-lookup"><span data-stu-id="44cff-296">Simple</span></span>|
    |<span data-ttu-id="44cff-297">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="44cff-297">_sipfederationtls._tcp</span></span>|<span data-ttu-id="44cff-298">SRV - Service locator</span><span class="sxs-lookup"><span data-stu-id="44cff-298">SRV - Service locator</span></span>|<span data-ttu-id="44cff-299">Nee</span><span class="sxs-lookup"><span data-stu-id="44cff-299">No</span></span>|<span data-ttu-id="44cff-300">300</span><span class="sxs-lookup"><span data-stu-id="44cff-300">300</span></span>|<span data-ttu-id="44cff-301">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="44cff-301">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="44cff-302">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="44cff-302">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="44cff-303">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="44cff-303">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="44cff-304">Simple</span><span class="sxs-lookup"><span data-stu-id="44cff-304">Simple</span></span>|
   
    ![Afbeelding van het te maken van afbeelding van het gebruik](../../media/c3f841d3-6076-428f-bb04-e71cc5f392fa.png)
  
6. <span data-ttu-id="44cff-306">Selecteer **Maken**.</span><span class="sxs-lookup"><span data-stu-id="44cff-306">Select **Create**.</span></span>
    
    ![AWS-BP-Configure-5-2](../../media/1bf5dc58-a46b-47a5-bd69-7c2147dd4e50.png)
  
7. <span data-ttu-id="44cff-308">De andere SRV-record toevoegen:</span><span class="sxs-lookup"><span data-stu-id="44cff-308">To add the other SRV record:</span></span>
    
    <span data-ttu-id="44cff-309">Selecteer op de pagina **Gehoste zones** **Recordset maken,** maak een record met de waarden uit de volgende rij in de tabel en selecteer vervolgens opnieuw **Maken** om die record te voltooien.</span><span class="sxs-lookup"><span data-stu-id="44cff-309">In the **Hosted Zones** page, select **Create Record Set**, create a record using the values from the next row in the table, and then again select **Create** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="44cff-p120">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="44cff-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
