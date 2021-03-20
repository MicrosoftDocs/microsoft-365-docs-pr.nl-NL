---
title: DNS-records maken op Dyn.com voor Microsoft
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
ms.assetid: 34e57a00-2a7d-469c-beec-089423f18369
description: Informatie over het verifiëren van uw domein en het instellen van DNS-records voor e-mail, Skype voor Bedrijven Online en andere services op Dyn.com voor Microsoft.
ms.openlocfilehash: 432dc630d49cc3494d17b3f007f813d66dc6b1c3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910328"
---
# <a name="create-dns-records-at-dyncom-for-microsoft"></a><span data-ttu-id="cab4f-103">DNS-records maken op Dyn.com voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="cab4f-103">Create DNS records at Dyn.com for Microsoft</span></span>

 <span data-ttu-id="cab4f-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="cab4f-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="cab4f-105">Als Dyn.com uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="cab4f-105">If Dyn.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
 

  
> [!NOTE]
>  <span data-ttu-id="cab4f-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="cab4f-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="cab4f-109">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="cab4f-109">Add a TXT record for verification</span></span>
<span data-ttu-id="cab4f-110"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="cab4f-110"><a name="BKMK_verify"> </a></span></span>

1. <span data-ttu-id="cab4f-p102">Als u wilt beginnen, gaat u naar uw domeinenpagina bij Dyn.com via [deze koppeling](https://account.dyn.com/dns/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="cab4f-p102">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Schermopname van het pictogram Meer mensen uitnodigen](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="cab4f-114">Selecteer op **de pagina Zone Level Services** de optie **Dyn Standard DNS Service** voor het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="cab4f-114">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="cab4f-115">Selecteer voorkeuren **op de DNS-pagina** voor **uw domein.**</span><span class="sxs-lookup"><span data-stu-id="cab4f-115">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="cab4f-116">Selecteer **Expertinterface inschakelen.**</span><span class="sxs-lookup"><span data-stu-id="cab4f-116">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="cab4f-117">Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add DNS Record** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="cab4f-117">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="cab4f-118">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="cab4f-118">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="cab4f-119">**Host**</span><span class="sxs-lookup"><span data-stu-id="cab4f-119">**Host**</span></span>|<span data-ttu-id="cab4f-120">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cab4f-120">**TTL**</span></span>|<span data-ttu-id="cab4f-121">**Type**</span><span class="sxs-lookup"><span data-stu-id="cab4f-121">**Type**</span></span>|<span data-ttu-id="cab4f-122">**Data**</span><span class="sxs-lookup"><span data-stu-id="cab4f-122">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cab4f-123">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="cab4f-123">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="cab4f-124">600</span><span class="sxs-lookup"><span data-stu-id="cab4f-124">600</span></span>  <br/> |<span data-ttu-id="cab4f-125">TXT</span><span class="sxs-lookup"><span data-stu-id="cab4f-125">TXT</span></span>  <br/> |<span data-ttu-id="cab4f-126">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="cab4f-126">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="cab4f-127">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="cab4f-127">**Note:** This is an example.</span></span> <span data-ttu-id="cab4f-128">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="cab4f-128">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="cab4f-129">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="cab4f-129">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![Dyn-BP-Verify-1-1](../../media/b3730b15-a313-4b4c-b91e-646eebb649e8.png)
  
6. <span data-ttu-id="cab4f-131">Selecteer **Record maken.**</span><span class="sxs-lookup"><span data-stu-id="cab4f-131">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Verify-1-2](../../media/8b63b4ee-dbd7-44a7-b1e6-c6892b02f13e.png)
  
7. <span data-ttu-id="cab4f-133">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="cab4f-133">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="cab4f-134">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="cab4f-134">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="cab4f-135">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="cab4f-135">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="cab4f-136">Ga in het Microsoft-beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="cab4f-136">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="cab4f-137">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="cab4f-137">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="cab4f-138">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="cab4f-138">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="cab4f-139">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="cab4f-139">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="cab4f-p104">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="cab4f-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="cab4f-143">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="cab4f-143">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="cab4f-144"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="cab4f-144"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="cab4f-p105">Als u wilt beginnen, gaat u naar uw domeinenpagina bij Dyn.com via [deze koppeling](https://account.dyn.com/dns/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="cab4f-p105">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Schermopname van het pictogram Meer mensen uitnodigen](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="cab4f-148">Selecteer op **de pagina Zone Level Services** de optie **Dyn Standard DNS Service** voor het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="cab4f-148">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="cab4f-149">Selecteer voorkeuren op de DNS-pagina voor **uw domein.**</span><span class="sxs-lookup"><span data-stu-id="cab4f-149">On the DNS page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="cab4f-150">Selecteer **Expertinterface inschakelen.**</span><span class="sxs-lookup"><span data-stu-id="cab4f-150">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="cab4f-151">Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add DNS Record** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="cab4f-151">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="cab4f-152">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="cab4f-152">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="cab4f-153">**Host**</span><span class="sxs-lookup"><span data-stu-id="cab4f-153">**Host**</span></span>|<span data-ttu-id="cab4f-154">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cab4f-154">**TTL**</span></span>|<span data-ttu-id="cab4f-155">**Type**</span><span class="sxs-lookup"><span data-stu-id="cab4f-155">**Type**</span></span>|<span data-ttu-id="cab4f-156">**Data**</span><span class="sxs-lookup"><span data-stu-id="cab4f-156">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cab4f-157">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="cab4f-157">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="cab4f-158">600</span><span class="sxs-lookup"><span data-stu-id="cab4f-158">600</span></span>  <br/> |<span data-ttu-id="cab4f-159">MX</span><span class="sxs-lookup"><span data-stu-id="cab4f-159">MX</span></span>  <br/> |<span data-ttu-id="cab4f-160">10  *\<domain-key\>*  ,mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="cab4f-160">10  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="cab4f-161">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="cab4f-161">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="cab4f-p106">De **10** is de MX-prioriteitwaarde. Voeg deze toe aan het begin van de MX-waarde, van de rest van de waarde gescheiden door een spatie.  </span><span class="sxs-lookup"><span data-stu-id="cab4f-p106">The **10** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="cab4f-164">**Opmerking:** Haal uw  *\<domain-key\>*  uit uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="cab4f-164">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="cab4f-165">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="cab4f-165">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)      <br>    <span data-ttu-id="cab4f-166">Zie [Wat is MX-prioriteit?](../setup/domains-faq.yml) voor meer informatie over prioriteit.</span><span class="sxs-lookup"><span data-stu-id="cab4f-166">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> |
   
    ![Dyn-BP-Configure-2-1](../../media/62ac77b7-c84d-426d-9ec4-a28d6479ad04.png)
  
6. <span data-ttu-id="cab4f-168">Selecteer **Record maken.**</span><span class="sxs-lookup"><span data-stu-id="cab4f-168">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-2-2](../../media/e84e2cca-75e3-4584-8a98-f2f89cb71bd3.png)
  
7. <span data-ttu-id="cab4f-170">Als er andere MX-records zijn, verwijder deze dan door in de kolom **Delete** het selectievakje voor die records in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="cab4f-170">If there are any other MX records, remove them by selecting the check box for each one in the **Delete** column.</span></span> 
    
    ![bloemen en tekst](../../media/f24f02cc-c0b7-42cf-a2ff-4d0fc203e4de.png)
  
8. <span data-ttu-id="cab4f-172">Selecteer **Wijzigingen toepassen.**</span><span class="sxs-lookup"><span data-stu-id="cab4f-172">Select **Apply Changes**.</span></span>
    
    ![Dyn-BP-Configure-2-4](../../media/0cc23c2b-b6f2-4f58-af20-4c6506de7b43.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="cab4f-174">Voeg de zes CNAME-records toe die vereist zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="cab4f-174">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="cab4f-175"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="cab4f-175"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="cab4f-p108">Als u wilt beginnen, gaat u naar uw domeinenpagina bij Dyn.com via [deze koppeling](https://account.dyn.com/dns/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="cab4f-p108">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Schermopname van het pictogram Meer mensen uitnodigen](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="cab4f-179">Selecteer op **de pagina Zone Level Services** de optie **Dyn Standard DNS Service** voor het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="cab4f-179">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="cab4f-180">Selecteer voorkeuren **op de DNS-pagina** voor **uw domein.**</span><span class="sxs-lookup"><span data-stu-id="cab4f-180">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="cab4f-181">Selecteer **Expertinterface inschakelen.**</span><span class="sxs-lookup"><span data-stu-id="cab4f-181">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="cab4f-182">Voeg de eerste van de zes CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="cab4f-182">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="cab4f-183">Typ of kopieer en plak in de sectie **Add DNS Record** de waarden uit de eerste rij van de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="cab4f-183">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="cab4f-184">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="cab4f-184">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="cab4f-185">**Host**</span><span class="sxs-lookup"><span data-stu-id="cab4f-185">**Host**</span></span>|<span data-ttu-id="cab4f-186">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cab4f-186">**TTL**</span></span>|<span data-ttu-id="cab4f-187">**Type**</span><span class="sxs-lookup"><span data-stu-id="cab4f-187">**Type**</span></span>|<span data-ttu-id="cab4f-188">**Data**</span><span class="sxs-lookup"><span data-stu-id="cab4f-188">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cab4f-189">autodiscover</span><span class="sxs-lookup"><span data-stu-id="cab4f-189">autodiscover</span></span>  <br/> |<span data-ttu-id="cab4f-190">600</span><span class="sxs-lookup"><span data-stu-id="cab4f-190">600</span></span>  <br/> |<span data-ttu-id="cab4f-191">CNAME</span><span class="sxs-lookup"><span data-stu-id="cab4f-191">CNAME</span></span>  <br/> |<span data-ttu-id="cab4f-192">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="cab4f-192">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="cab4f-193">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="cab4f-193">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="cab4f-194">sip</span><span class="sxs-lookup"><span data-stu-id="cab4f-194">sip</span></span>  <br/> |<span data-ttu-id="cab4f-195">600</span><span class="sxs-lookup"><span data-stu-id="cab4f-195">600</span></span>  <br/> |<span data-ttu-id="cab4f-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="cab4f-196">CNAME</span></span>  <br/> |<span data-ttu-id="cab4f-197">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="cab4f-197">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="cab4f-198">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="cab4f-198">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="cab4f-199">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="cab4f-199">lyncdiscover</span></span>  <br/> |<span data-ttu-id="cab4f-200">600</span><span class="sxs-lookup"><span data-stu-id="cab4f-200">600</span></span>  <br/> |<span data-ttu-id="cab4f-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="cab4f-201">CNAME</span></span>  <br/> |<span data-ttu-id="cab4f-202">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="cab4f-202">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="cab4f-203">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="cab4f-203">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="cab4f-204">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="cab4f-204">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="cab4f-205">600</span><span class="sxs-lookup"><span data-stu-id="cab4f-205">600</span></span>  <br/> |<span data-ttu-id="cab4f-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="cab4f-206">CNAME</span></span>  <br/> |<span data-ttu-id="cab4f-207">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="cab4f-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="cab4f-208">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="cab4f-208">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="cab4f-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="cab4f-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="cab4f-210">600</span><span class="sxs-lookup"><span data-stu-id="cab4f-210">600</span></span>  <br/> |<span data-ttu-id="cab4f-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="cab4f-211">CNAME</span></span>  <br/> |<span data-ttu-id="cab4f-212">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="cab4f-212">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="cab4f-213">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="cab4f-213">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Dyn-BP-Configure-3-1](../../media/1fd80695-d3d7-4298-9ebe-97a69f46f1b2.png)
  
6. <span data-ttu-id="cab4f-215">Selecteer **Record maken.**</span><span class="sxs-lookup"><span data-stu-id="cab4f-215">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-3-2](../../media/89551495-3fa5-44ab-96b2-855f70be0880.png)
  
7. <span data-ttu-id="cab4f-217">Voeg de resterende vijf CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="cab4f-217">Add the remaining five CNAME records.</span></span>
    
    <span data-ttu-id="cab4f-218">Maak in de sectie **ADD DNS Record** een record met behulp van de waarden uit de volgende rij in de tabel en selecteer vervolgens opnieuw **Record** maken om die record te voltooien.</span><span class="sxs-lookup"><span data-stu-id="cab4f-218">In the **Add DNS Record** section, create a record by using the values from the next row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
    <span data-ttu-id="cab4f-219">Herhaal deze procedure totdat u alle zes CNAME-records hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="cab4f-219">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="cab4f-220">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="cab4f-220">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="cab4f-221"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="cab4f-221"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="cab4f-222">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="cab4f-222">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="cab4f-223">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="cab4f-223">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="cab4f-224">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cab4f-224">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="cab4f-225">Voeg in plaats daarvan de vereiste Microsoft-waarden  toe aan de huidige record, zodat u één SPF-record hebt met beide sets waarden.</span><span class="sxs-lookup"><span data-stu-id="cab4f-225">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="cab4f-p110">Als u wilt beginnen, gaat u naar uw domeinenpagina bij Dyn.com via [deze koppeling](https://account.dyn.com/dns/). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="cab4f-p110">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/). You'll be prompted to login first.</span></span>
    
    ![Schermopname van het pictogram Meer mensen uitnodigen](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="cab4f-229">Selecteer op **de pagina Zone Level Services** de optie **Dyn Standard DNS Service** voor het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="cab4f-229">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="cab4f-230">Selecteer voorkeuren **op de DNS-pagina** voor **uw domein.**</span><span class="sxs-lookup"><span data-stu-id="cab4f-230">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="cab4f-231">Selecteer **Expertinterface inschakelen.**</span><span class="sxs-lookup"><span data-stu-id="cab4f-231">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="cab4f-232">Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add DNS Record** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="cab4f-232">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="cab4f-233">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="cab4f-233">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="cab4f-234">**Host**</span><span class="sxs-lookup"><span data-stu-id="cab4f-234">**Host**</span></span>|<span data-ttu-id="cab4f-235">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cab4f-235">**TTL**</span></span>|<span data-ttu-id="cab4f-236">**Type**</span><span class="sxs-lookup"><span data-stu-id="cab4f-236">**Type**</span></span>|<span data-ttu-id="cab4f-237">**Data**</span><span class="sxs-lookup"><span data-stu-id="cab4f-237">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cab4f-238">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="cab4f-238">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="cab4f-239">600</span><span class="sxs-lookup"><span data-stu-id="cab4f-239">600</span></span>  <br/> |<span data-ttu-id="cab4f-240">TXT</span><span class="sxs-lookup"><span data-stu-id="cab4f-240">TXT</span></span>  <br/> |<span data-ttu-id="cab4f-241">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="cab4f-241">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="cab4f-242">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="cab4f-242">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-Configure-4-1](../../media/f8511349-3ea2-40c3-9853-98e1a58a91b5.png)
  
6. <span data-ttu-id="cab4f-244">Selecteer **Record maken.**</span><span class="sxs-lookup"><span data-stu-id="cab4f-244">Select **Create Record**.</span></span>
    
    ![Veld met meerdere waarden](../../media/bbe04835-d3c0-4146-8123-9781bb9eca51.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="cab4f-246">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="cab4f-246">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="cab4f-247"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="cab4f-247"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="cab4f-248">Als u wilt beginnen, gaat u naar uw domeinenpagina bij Dyn.com via [deze koppeling](https://account.dyn.com/dns/).</span><span class="sxs-lookup"><span data-stu-id="cab4f-248">To get started, go to your domains page at Dyn.com by using [this link](https://account.dyn.com/dns/).</span></span> <span data-ttu-id="cab4f-249">U wordt gevraagd u eerst aan te melden</span><span class="sxs-lookup"><span data-stu-id="cab4f-249">You'll be prompted to login first</span></span> 
    
    ![Schermopname van het pictogram Meer mensen uitnodigen](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. <span data-ttu-id="cab4f-251">Selecteer op **de pagina Zone Level Services** de optie **Dyn Standard DNS Service** voor het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="cab4f-251">On the **Zone Level Services** page, select **Dyn Standard DNS Service** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="cab4f-252">Selecteer voorkeuren **op de DNS-pagina** voor **uw domein.**</span><span class="sxs-lookup"><span data-stu-id="cab4f-252">On the **DNS** page for your domain, select **Preferences**.</span></span>
    
4. <span data-ttu-id="cab4f-253">Selecteer **Expertinterface inschakelen.**</span><span class="sxs-lookup"><span data-stu-id="cab4f-253">Select **Enable Expert Interface**.</span></span>
    
5. <span data-ttu-id="cab4f-254">Voeg de eerste van de twee SRV-records toe.</span><span class="sxs-lookup"><span data-stu-id="cab4f-254">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="cab4f-255">Typ of kopieer en plak in de sectie **Add DNS Record** de waarden uit de eerste rij van de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="cab4f-255">In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span> 
    
    <span data-ttu-id="cab4f-256">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="cab4f-256">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="cab4f-257">**Host**</span><span class="sxs-lookup"><span data-stu-id="cab4f-257">**Host**</span></span>|<span data-ttu-id="cab4f-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cab4f-258">**TTL**</span></span>|<span data-ttu-id="cab4f-259">**Type**</span><span class="sxs-lookup"><span data-stu-id="cab4f-259">**Type**</span></span>|<span data-ttu-id="cab4f-260">**Data**</span><span class="sxs-lookup"><span data-stu-id="cab4f-260">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cab4f-261">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="cab4f-261">_sip._tls</span></span>|<span data-ttu-id="cab4f-262">600</span><span class="sxs-lookup"><span data-stu-id="cab4f-262">600</span></span>|<span data-ttu-id="cab4f-263">SRV</span><span class="sxs-lookup"><span data-stu-id="cab4f-263">SRV</span></span>|<span data-ttu-id="cab4f-264">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="cab4f-264">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="cab4f-265">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="cab4f-265">**This value MUST end with a period (.)**</span></span><br><span data-ttu-id="cab4f-266">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="cab4f-266">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="cab4f-267">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="cab4f-267">_sipfederationtls._tcp</span></span>|<span data-ttu-id="cab4f-268">600</span><span class="sxs-lookup"><span data-stu-id="cab4f-268">600</span></span>|<span data-ttu-id="cab4f-269">SRV</span><span class="sxs-lookup"><span data-stu-id="cab4f-269">SRV</span></span>|<span data-ttu-id="cab4f-270">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="cab4f-270">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="cab4f-271">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="cab4f-271">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="cab4f-272">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="cab4f-272">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Dyn-BP-Configure-5-1](../../media/a6873411-f4ce-4327-9145-02d435930976.png)
  
6. <span data-ttu-id="cab4f-274">Selecteer **Record maken.**</span><span class="sxs-lookup"><span data-stu-id="cab4f-274">Select **Create Record**.</span></span>
    
    ![Dyn-BP-Configure-5-2](../../media/e6f33452-e527-473b-a645-b31ed70b0d43.png)
  
7. <span data-ttu-id="cab4f-276">Voeg de andere SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="cab4f-276">Add the other SRV record.</span></span>
    
    <span data-ttu-id="cab4f-277">Maak in de sectie **ADD DNS Record** een record met behulp van de waarden uit de tweede rij in de tabel en selecteer vervolgens opnieuw **Record** maken om die record te voltooien.</span><span class="sxs-lookup"><span data-stu-id="cab4f-277">In the **Add DNS Record** section, create a record by using the values from the second row in the table, and then again select **Create Record** to complete that record.</span></span> 
    
> [!NOTE]
>  <span data-ttu-id="cab4f-p114">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="cab4f-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
