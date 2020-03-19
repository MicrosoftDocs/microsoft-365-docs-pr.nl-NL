---
title: DNS-records bij Dyn.com maken voor Office 365
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
ms.assetid: 34e57a00-2a7d-469c-beec-089423f18369
description: Lees uw domein en stel DNS-records in voor e-mail, Skype voor Bedrijven Online en andere services op Dyn.com voor Office 365.
ms.openlocfilehash: a09ba409b1788432c5cd5c060252bb76b6903342
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "42810301"
---
# <a name="create-dns-records-at-dyncom-for-office-365"></a><span data-ttu-id="27f86-103">DNS-records bij Dyn.com maken voor Office 365</span><span class="sxs-lookup"><span data-stu-id="27f86-103">Create DNS records at Dyn.com for Office 365</span></span>

 <span data-ttu-id="27f86-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="27f86-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="27f86-105">Als Dyn.com uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="27f86-105">If Dyn.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
 
<span data-ttu-id="27f86-106">Zie [Een openbare website gebruiken met Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9) voor informatie over webhosting en DNS voor websites met Office 365.</span><span class="sxs-lookup"><span data-stu-id="27f86-106">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="27f86-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="27f86-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="27f86-110">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="27f86-110">Add a TXT record for verification</span></span>
<span data-ttu-id="27f86-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="27f86-111"><a name="BKMK_verify"> </a></span></span>

1. <span data-ttu-id="27f86-p102">Als u wilt beginnen, gaat u naar uw domeinenpagina bij Dyn.com via [deze koppeling](https://account.dyn.com/dns/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="27f86-p102">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Schermopname van het pictogram Meer mensen uitnodigen](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="27f86-115">Selecteer **op** de pagina Zone Level Services de optie **Dyn Standard DNS-service** voor het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="27f86-115">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="27f86-116">Selecteer **Voorkeuren**op de **PAGINA DNS** voor uw domein .</span><span class="sxs-lookup"><span data-stu-id="27f86-116">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="27f86-117">Selecteer **Expertinterface inschakelen**.</span><span class="sxs-lookup"><span data-stu-id="27f86-117">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="27f86-118">Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add DNS Record** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="27f86-118">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="27f86-119">(Kies in de vervolgkeuzelijst de waarde **Type**.)</span><span class="sxs-lookup"><span data-stu-id="27f86-119">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="27f86-120">**Host**</span><span class="sxs-lookup"><span data-stu-id="27f86-120">**Host**</span></span>|<span data-ttu-id="27f86-121">**TTL**</span><span class="sxs-lookup"><span data-stu-id="27f86-121">**TTL**</span></span>|<span data-ttu-id="27f86-122">**Type**</span><span class="sxs-lookup"><span data-stu-id="27f86-122">**Type**</span></span>|<span data-ttu-id="27f86-123">**Data**</span><span class="sxs-lookup"><span data-stu-id="27f86-123">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="27f86-124">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="27f86-124">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="27f86-125">600</span><span class="sxs-lookup"><span data-stu-id="27f86-125">600</span></span>  <br/> |<span data-ttu-id="27f86-126">TXT</span><span class="sxs-lookup"><span data-stu-id="27f86-126">TXT</span></span>  <br/> |<span data-ttu-id="27f86-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="27f86-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="27f86-p103">**Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="27f86-p103">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
       
   ![Afbeelding van het te hebben van afbeelding van het gebruik-1-1](../../media/b3730b15-a313-4b4c-b91e-646eebb649e8.png)
  
6. <span data-ttu-id="27f86-132">Selecteer **Record maken**.</span><span class="sxs-lookup"><span data-stu-id="27f86-132">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Verify-1-2](../../media/8b63b4ee-dbd7-44a7-b1e6-c6892b02f13e.png)
  
7. <span data-ttu-id="27f86-134">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="27f86-134">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="27f86-135">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Office 365 en vraagt u of Office 365 naar de record wil zoeken.</span><span class="sxs-lookup"><span data-stu-id="27f86-135">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="27f86-136">Wanneer in Office 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="27f86-136">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="27f86-137">Ga in het beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Instellingendomeinen.</a> **Settings**</span><span class="sxs-lookup"><span data-stu-id="27f86-137">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="27f86-138">Selecteer **op** de pagina Domeinen het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="27f86-138">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="27f86-139">Selecteer **op** de pagina Setup de optie **Installatie starten**.</span><span class="sxs-lookup"><span data-stu-id="27f86-139">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="27f86-140">Selecteer **op** de pagina Domein verifiëren de optie **Verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="27f86-140">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="27f86-p104">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="27f86-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="27f86-144">Voeg een MX-record toe zodat e-mail voor uw domein bij Office 365 terechtkomt</span><span class="sxs-lookup"><span data-stu-id="27f86-144">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="27f86-145"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="27f86-145"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="27f86-p105">Als u wilt beginnen, gaat u naar uw domeinenpagina bij Dyn.com via [deze koppeling](https://account.dyn.com/dns/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="27f86-p105">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Schermopname van het pictogram Meer mensen uitnodigen](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="27f86-149">Selecteer **op** de pagina Zone Level Services de optie **Dyn Standard DNS-service** voor het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="27f86-149">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="27f86-150">Selecteer **Voorkeuren**op de PAGINA DNS voor uw domein .</span><span class="sxs-lookup"><span data-stu-id="27f86-150">On the DNS page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="27f86-151">Selecteer **Expertinterface inschakelen**.</span><span class="sxs-lookup"><span data-stu-id="27f86-151">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="27f86-152">Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add DNS Record** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="27f86-152">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="27f86-153">(Kies in de vervolgkeuzelijst de waarde **Type**.)</span><span class="sxs-lookup"><span data-stu-id="27f86-153">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="27f86-154">**Host**</span><span class="sxs-lookup"><span data-stu-id="27f86-154">**Host**</span></span>|<span data-ttu-id="27f86-155">**TTL**</span><span class="sxs-lookup"><span data-stu-id="27f86-155">**TTL**</span></span>|<span data-ttu-id="27f86-156">**Type**</span><span class="sxs-lookup"><span data-stu-id="27f86-156">**Type**</span></span>|<span data-ttu-id="27f86-157">**Data**</span><span class="sxs-lookup"><span data-stu-id="27f86-157">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="27f86-158">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="27f86-158">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="27f86-159">600</span><span class="sxs-lookup"><span data-stu-id="27f86-159">600</span></span>  <br/> |<span data-ttu-id="27f86-160">MX</span><span class="sxs-lookup"><span data-stu-id="27f86-160">MX</span></span>  <br/> |<span data-ttu-id="27f86-161">10  *\<domeinsleutel\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="27f86-161">10  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="27f86-162">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="27f86-162">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="27f86-p106">De **10** is de MX-prioriteitwaarde. Voeg deze toe aan het begin van de MX-waarde, van de rest van de waarde gescheiden door een spatie.  </span><span class="sxs-lookup"><span data-stu-id="27f86-p106">The **10** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="27f86-165">**Let op:** Haal uw \* \<domeinsleutel\> \* op uit uw Office 365-account.</span><span class="sxs-lookup"><span data-stu-id="27f86-165">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="27f86-166">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="27f86-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      <br>    <span data-ttu-id="27f86-167">Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="27f86-167">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |
   
    ![Afbeelding van het te maken](../../media/62ac77b7-c84d-426d-9ec4-a28d6479ad04.png)
  
6. <span data-ttu-id="27f86-169">Selecteer **Record maken**.</span><span class="sxs-lookup"><span data-stu-id="27f86-169">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-2-2](../../media/e84e2cca-75e3-4584-8a98-f2f89cb71bd3.png)
  
7. <span data-ttu-id="27f86-171">Als er andere MX-records zijn, verwijder deze dan door in de kolom **Delete** het selectievakje voor die records in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="27f86-171">If there are any other MX records, remove them by selecting the check box for each one in the **Delete** column.</span></span> 
    
    ![bloemen en tekst](../../media/f24f02cc-c0b7-42cf-a2ff-4d0fc203e4de.png)
  
8. <span data-ttu-id="27f86-173">Selecteer **Wijzigingen toepassen**.</span><span class="sxs-lookup"><span data-stu-id="27f86-173">Select **Apply Changes**.</span></span>
    
    ![Dyn-BP-Configure-2-4](../../media/0cc23c2b-b6f2-4f58-af20-4c6506de7b43.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="27f86-175">De zes CNAME-records toevoegen die voor Office 365 vereist zijn</span><span class="sxs-lookup"><span data-stu-id="27f86-175">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="27f86-176"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="27f86-176"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="27f86-p108">Als u wilt beginnen, gaat u naar uw domeinenpagina bij Dyn.com via [deze koppeling](https://account.dyn.com/dns/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="27f86-p108">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Schermopname van het pictogram Meer mensen uitnodigen](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="27f86-180">Selecteer **op** de pagina Zone Level Services de optie **Dyn Standard DNS-service** voor het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="27f86-180">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="27f86-181">Selecteer **Voorkeuren**op de **PAGINA DNS** voor uw domein .</span><span class="sxs-lookup"><span data-stu-id="27f86-181">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="27f86-182">Selecteer **Expertinterface inschakelen**.</span><span class="sxs-lookup"><span data-stu-id="27f86-182">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="27f86-183">Voeg de eerste van de zes CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="27f86-183">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="27f86-184">Typ of kopieer en plak in de sectie **Add DNS Record** de waarden uit de eerste rij van de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="27f86-184">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="27f86-185">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="27f86-185">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="27f86-186">**Host**</span><span class="sxs-lookup"><span data-stu-id="27f86-186">**Host**</span></span>|<span data-ttu-id="27f86-187">**TTL**</span><span class="sxs-lookup"><span data-stu-id="27f86-187">**TTL**</span></span>|<span data-ttu-id="27f86-188">**Type**</span><span class="sxs-lookup"><span data-stu-id="27f86-188">**Type**</span></span>|<span data-ttu-id="27f86-189">**Data**</span><span class="sxs-lookup"><span data-stu-id="27f86-189">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="27f86-190">autodiscover</span><span class="sxs-lookup"><span data-stu-id="27f86-190">autodiscover</span></span>  <br/> |<span data-ttu-id="27f86-191">600</span><span class="sxs-lookup"><span data-stu-id="27f86-191">600</span></span>  <br/> |<span data-ttu-id="27f86-192">CNAME</span><span class="sxs-lookup"><span data-stu-id="27f86-192">CNAME</span></span>  <br/> |<span data-ttu-id="27f86-193">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="27f86-193">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="27f86-194">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="27f86-194">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="27f86-195">sip</span><span class="sxs-lookup"><span data-stu-id="27f86-195">sip</span></span>  <br/> |<span data-ttu-id="27f86-196">600</span><span class="sxs-lookup"><span data-stu-id="27f86-196">600</span></span>  <br/> |<span data-ttu-id="27f86-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="27f86-197">CNAME</span></span>  <br/> |<span data-ttu-id="27f86-198">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="27f86-198">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="27f86-199">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="27f86-199">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="27f86-200">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="27f86-200">lyncdiscover</span></span>  <br/> |<span data-ttu-id="27f86-201">600</span><span class="sxs-lookup"><span data-stu-id="27f86-201">600</span></span>  <br/> |<span data-ttu-id="27f86-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="27f86-202">CNAME</span></span>  <br/> |<span data-ttu-id="27f86-203">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="27f86-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="27f86-204">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="27f86-204">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="27f86-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="27f86-205">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="27f86-206">600</span><span class="sxs-lookup"><span data-stu-id="27f86-206">600</span></span>  <br/> |<span data-ttu-id="27f86-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="27f86-207">CNAME</span></span>  <br/> |<span data-ttu-id="27f86-208">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="27f86-208">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="27f86-209">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="27f86-209">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="27f86-210">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="27f86-210">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="27f86-211">600</span><span class="sxs-lookup"><span data-stu-id="27f86-211">600</span></span>  <br/> |<span data-ttu-id="27f86-212">CNAME</span><span class="sxs-lookup"><span data-stu-id="27f86-212">CNAME</span></span>  <br/> |<span data-ttu-id="27f86-213">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="27f86-213">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="27f86-214">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="27f86-214">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Afbeelding van het te maken](../../media/1fd80695-d3d7-4298-9ebe-97a69f46f1b2.png)
  
6. <span data-ttu-id="27f86-216">Selecteer **Record maken**.</span><span class="sxs-lookup"><span data-stu-id="27f86-216">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-3-2](../../media/89551495-3fa5-44ab-96b2-855f70be0880.png)
  
7. <span data-ttu-id="27f86-218">Voeg de resterende vijf CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="27f86-218">Add the remaining five CNAME records.</span></span>
    
    <span data-ttu-id="27f86-219">Maak in de sectie **DNS-record toevoegen** een record met de waarden uit de volgende rij in de tabel en selecteer vervolgens opnieuw **Record maken** om die record te voltooien.</span><span class="sxs-lookup"><span data-stu-id="27f86-219">In the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
    <span data-ttu-id="27f86-220">Herhaal deze procedure totdat u alle zes CNAME-records hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="27f86-220">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="27f86-221">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="27f86-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="27f86-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="27f86-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="27f86-223">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="27f86-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="27f86-224">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="27f86-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="27f86-225">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Office 365 te maken.</span><span class="sxs-lookup"><span data-stu-id="27f86-225">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="27f86-226">In plaats daarvan voegt u de vereiste Office 365-waarden toe aan de huidige record, zodat u beschikt over  *één*  SPF-record waarin beide sets waarden zijn opgenomen.</span><span class="sxs-lookup"><span data-stu-id="27f86-226">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="27f86-p110">Als u wilt beginnen, gaat u naar uw domeinenpagina bij Dyn.com via [deze koppeling](https://account.dyn.com/dns/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="27f86-p110">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Schermopname van het pictogram Meer mensen uitnodigen](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="27f86-230">Selecteer **op** de pagina Zone Level Services de optie **Dyn Standard DNS-service** voor het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="27f86-230">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="27f86-231">Selecteer **Voorkeuren**op de **PAGINA DNS** voor uw domein .</span><span class="sxs-lookup"><span data-stu-id="27f86-231">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="27f86-232">Selecteer **Expertinterface inschakelen**.</span><span class="sxs-lookup"><span data-stu-id="27f86-232">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="27f86-233">Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add DNS Record** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="27f86-233">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="27f86-234">(Kies in de vervolgkeuzelijst de waarde **Type**.)</span><span class="sxs-lookup"><span data-stu-id="27f86-234">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="27f86-235">**Host**</span><span class="sxs-lookup"><span data-stu-id="27f86-235">**Host**</span></span>|<span data-ttu-id="27f86-236">**TTL**</span><span class="sxs-lookup"><span data-stu-id="27f86-236">**TTL**</span></span>|<span data-ttu-id="27f86-237">**Type**</span><span class="sxs-lookup"><span data-stu-id="27f86-237">**Type**</span></span>|<span data-ttu-id="27f86-238">**Data**</span><span class="sxs-lookup"><span data-stu-id="27f86-238">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="27f86-239">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="27f86-239">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="27f86-240">600</span><span class="sxs-lookup"><span data-stu-id="27f86-240">600</span></span>  <br/> |<span data-ttu-id="27f86-241">TXT</span><span class="sxs-lookup"><span data-stu-id="27f86-241">TXT</span></span>  <br/> |<span data-ttu-id="27f86-242">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="27f86-242">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="27f86-243">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="27f86-243">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Afbeelding van het te maken](../../media/f8511349-3ea2-40c3-9853-98e1a58a91b5.png)
  
6. <span data-ttu-id="27f86-245">Selecteer **Record maken**.</span><span class="sxs-lookup"><span data-stu-id="27f86-245">Select **Create Record**.</span></span>
    
    ![Veld met meerdere waarden](../../media/bbe04835-d3c0-4146-8123-9781bb9eca51.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="27f86-247">Voeg de vier SRV-records toe die voor Office 365 vereist zijn.</span><span class="sxs-lookup"><span data-stu-id="27f86-247">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="27f86-248"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="27f86-248"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="27f86-249">Als u wilt beginnen, gaat u naar uw domeinenpagina bij Dyn.com via [deze koppeling](https://account.dyn.com/dns/).</span><span class="sxs-lookup"><span data-stu-id="27f86-249">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/).</span></span> <span data-ttu-id="27f86-250">Je wordt gevraagd om eerst in te loggen</span><span class="sxs-lookup"><span data-stu-id="27f86-250">You'll be prompted to login first</span></span> 
    
    ![Schermopname van het pictogram Meer mensen uitnodigen](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="27f86-252">Selecteer **op** de pagina Zone Level Services de optie **Dyn Standard DNS-service** voor het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="27f86-252">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="27f86-253">Selecteer **Voorkeuren**op de **PAGINA DNS** voor uw domein .</span><span class="sxs-lookup"><span data-stu-id="27f86-253">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="27f86-254">Selecteer **Expertinterface inschakelen**.</span><span class="sxs-lookup"><span data-stu-id="27f86-254">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="27f86-255">Voeg de eerste van de twee SRV-records toe.</span><span class="sxs-lookup"><span data-stu-id="27f86-255">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="27f86-256">Typ of kopieer en plak in de sectie **Add DNS Record** de waarden uit de eerste rij van de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="27f86-256">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="27f86-257">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="27f86-257">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="27f86-258">**Host**</span><span class="sxs-lookup"><span data-stu-id="27f86-258">**Host**</span></span>|<span data-ttu-id="27f86-259">**TTL**</span><span class="sxs-lookup"><span data-stu-id="27f86-259">**TTL**</span></span>|<span data-ttu-id="27f86-260">**Type**</span><span class="sxs-lookup"><span data-stu-id="27f86-260">**Type**</span></span>|<span data-ttu-id="27f86-261">**Data**</span><span class="sxs-lookup"><span data-stu-id="27f86-261">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="27f86-262">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="27f86-262">_sip._tls</span></span>|<span data-ttu-id="27f86-263">600</span><span class="sxs-lookup"><span data-stu-id="27f86-263">600</span></span>|<span data-ttu-id="27f86-264">SRV</span><span class="sxs-lookup"><span data-stu-id="27f86-264">SRV</span></span>|<span data-ttu-id="27f86-265">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="27f86-265">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="27f86-266">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="27f86-266">**This value MUST end with a period (.)**</span></span><br><span data-ttu-id="27f86-267">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="27f86-267">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="27f86-268">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="27f86-268">_sipfederationtls._tcp</span></span>|<span data-ttu-id="27f86-269">600</span><span class="sxs-lookup"><span data-stu-id="27f86-269">600</span></span>|<span data-ttu-id="27f86-270">SRV</span><span class="sxs-lookup"><span data-stu-id="27f86-270">SRV</span></span>|<span data-ttu-id="27f86-271">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="27f86-271">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="27f86-272">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="27f86-272">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="27f86-273">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="27f86-273">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Afbeelding van het te maken](../../media/a6873411-f4ce-4327-9145-02d435930976.png)
  
6. <span data-ttu-id="27f86-275">Selecteer **Record maken**.</span><span class="sxs-lookup"><span data-stu-id="27f86-275">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-5-2](../../media/e6f33452-e527-473b-a645-b31ed70b0d43.png)
  
7. <span data-ttu-id="27f86-277">Voeg de andere SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="27f86-277">Add the other SRV record.</span></span>
    
    <span data-ttu-id="27f86-278">Maak in de sectie **DNS-record toevoegen** een record met de waarden uit de tweede rij in de tabel en selecteer vervolgens opnieuw **Record maken** om die record te voltooien.</span><span class="sxs-lookup"><span data-stu-id="27f86-278">In the **Add DNS Record** section, create a record by using the values from the second row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
> [!NOTE]
>  <span data-ttu-id="27f86-p114">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="27f86-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
