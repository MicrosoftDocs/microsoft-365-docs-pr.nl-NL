---
title: Naamservers wijzigen voor het instellen van Microsoft met Namecheap
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
ms.assetid: 84f467f6-28cf-40f0-94d0-a2a27ddfc2e7
description: 'Leer hoe u uw Microsoft-aangepaste domein instelt met Namecheap als u wilt dat Microsoft uw DNS-records beheert. '
ms.openlocfilehash: e305abb7768b286dbd24336c1dab39d919f9a0ac
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646449"
---
# <a name="change-nameservers-to-set-up-microsoft-with-namecheap"></a><span data-ttu-id="f3e4a-103">Naamservers wijzigen voor het instellen van Microsoft met Namecheap</span><span class="sxs-lookup"><span data-stu-id="f3e4a-103">Change nameservers to set up Microsoft with Namecheap</span></span>

 <span data-ttu-id="f3e4a-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="f3e4a-105">Voer de volgende instructies uit als u wilt dat Microsoft uw DNS-records voor u beheert.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="f3e4a-106">(Als u wilt, kunt u [al uw Microsoft DNS-records beheren op NameCheap](create-dns-records-at-namecheap.md).)</span><span class="sxs-lookup"><span data-stu-id="f3e4a-106">(If you prefer, you can [manage all your Microsoft DNS records at Namecheap](create-dns-records-at-namecheap.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="f3e4a-107">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="f3e4a-107">Add a TXT record for verification</span></span>

1. <span data-ttu-id="f3e4a-p102">Ga eerst naar de domeinenpagina bij Namecheap via [deze koppeling](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). U wordt gevraagd u aan te melden en verder te gaan.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-p102">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="f3e4a-111">Kies op de **openings** pagina onder **account**de optie **Domain List** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-111">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="f3e4a-113">Zoek op de pagina **Domain List** de naam van het domein dat u wilt bewerken en selecteer vervolgens **Manage**.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-113">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="f3e4a-115">Selecteer **Advanced DNS**.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-115">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="f3e4a-117">Selecteer in de sectie **host records** de optie **add new record**.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-117">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="f3e4a-119">Selecteer in de vervolgkeuzelijst **Type** de optie **TXT Record**.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-119">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f3e4a-120">De vervolgkeuzelijst **type** wordt automatisch weergegeven wanneer u **nieuwe record toevoegen**selecteert.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-120">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span>
  
    ![Namecheap-BP-Verify-1-1](../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. <span data-ttu-id="f3e4a-122">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-122">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="f3e4a-123">(Kies de waarde **TTL** in de vervolgkeuzelijst.)</span><span class="sxs-lookup"><span data-stu-id="f3e4a-123">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
|<span data-ttu-id="f3e4a-124">**Type**</span><span class="sxs-lookup"><span data-stu-id="f3e4a-124">**Type**</span></span>|<span data-ttu-id="f3e4a-125">**Host**</span><span class="sxs-lookup"><span data-stu-id="f3e4a-125">**Host**</span></span>|<span data-ttu-id="f3e4a-126">**Waarde**</span><span class="sxs-lookup"><span data-stu-id="f3e4a-126">**Value**</span></span>|<span data-ttu-id="f3e4a-127">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f3e4a-127">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f3e4a-128">TXT</span><span class="sxs-lookup"><span data-stu-id="f3e4a-128">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="f3e4a-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="f3e4a-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="f3e4a-130">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-130">**Note**: This is an example.</span></span> <span data-ttu-id="f3e4a-131">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-131">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="f3e4a-132">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="f3e4a-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="f3e4a-133">30 min</span><span class="sxs-lookup"><span data-stu-id="f3e4a-133">30 min</span></span>  <br/> |
   
   ![NameCheap voor 1-2](../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. <span data-ttu-id="f3e4a-135">Selecteer het besturingselement **wijzigingen opslaan** (vinkje).</span><span class="sxs-lookup"><span data-stu-id="f3e4a-135">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Verify-1-3](../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. <span data-ttu-id="f3e4a-137">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="f3e4a-138">Nu u de record hebt toegevoegd aan de site van uw domeinregistratie, gaat u terug naar Microsoft en vraagt u naar de record.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="f3e4a-139">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="f3e4a-140">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="f3e4a-141">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="f3e4a-142">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-142">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="f3e4a-143">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="f3e4a-p104">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f3e4a-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="f3e4a-147">De naamserverrecords (NS-records) van uw domein wijzigen</span><span class="sxs-lookup"><span data-stu-id="f3e4a-147">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="f3e4a-148">Om het instellen van uw domein met Microsoft te voltooien, kunt u de NS-records van uw domein bij uw domeinregistratie wijzigen zodat deze verwijzen naar de primaire en secundaire naamservers van Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-148">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="f3e4a-149">Hierdoor wordt Microsoft zodanig geconfigureerd dat de DNS-records van het domein voor u worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-149">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="f3e4a-150">We toevoegen alle records, zodat e-mail, Skype voor bedrijven online en uw openbare website met uw domein werken, en u bent klaar.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-150">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="f3e4a-151">Als u de naamserver records van uw domein wijzigt zodat ze verwijzen naar de Microsoft-naamservers, worden dit van invloed op alle services die op dat moment zijn gekoppeld aan uw domein.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-151">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="f3e4a-152">Alle e-mailberichten die naar uw domein zijn verzonden (zoals rob@ *your_domain*  . com) worden bijvoorbeeld beschikbaar gemaakt voor Microsoft nadat u deze wijziging hebt aangebracht.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-152">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="f3e4a-153">Na het voltooien van de stappen in deze sectie, moeten  *alleen*  de volgende vier naamservers in de lijst staan: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  In de volgende procedure kunt u zien hoe u andere, ongewenste naamservers uit de lijst verwijdert en hoe u de  *juiste*  naamservers toevoegt als deze niet al in de lijst staan.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-153">When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.</span></span> 
  
1. <span data-ttu-id="f3e4a-p107">Ga eerst naar de domeinenpagina bij Namecheap via [deze koppeling](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). U wordt gevraagd u aan te melden en verder te gaan.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-p107">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="f3e4a-157">Kies op de **openings** pagina onder **account**de optie **Domain List** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-157">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="f3e4a-159">Zoek op de pagina **Domain List** de naam van het domein dat u wilt bewerken en selecteer vervolgens **Manage**.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-159">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="f3e4a-161">Selecteer **Domain**.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-161">Select **Domain**.</span></span>
    
    ![Namecheap-BP-Redelegate-1-1](../../media/59588406-794e-4ae4-8526-35e3111b5791.png)
  
5. <span data-ttu-id="f3e4a-163">Ga naar de sectie **NAMESERVERS** en selecteer **Custom** in de vervolgkeuzelijst **Namecheap Default**.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-163">Find the **NAMESERVERS** section, and then select **Custom** from the **Namecheap Default** drop-down list.</span></span> 
    
    ![Namecheap-BP-Redelegate-1-2](../../media/7df56295-fdb3-472f-9442-13f780c2c93e.png)
  
6. <span data-ttu-id="f3e4a-165">Afhankelijk van of er al naamservers worden vermeld op de pagina die wordt weergegeven, gaat u op een van de volgende twee manieren verder:</span><span class="sxs-lookup"><span data-stu-id="f3e4a-165">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures.</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="f3e4a-166">Als er nog GEEN naamservers worden vermeld</span><span class="sxs-lookup"><span data-stu-id="f3e4a-166">If there are NO nameservers already listed</span></span>
<span data-ttu-id="f3e4a-167"><a name="BKMK_ProcedureWithOUT"> </a></span><span class="sxs-lookup"><span data-stu-id="f3e4a-167"><a name="BKMK_ProcedureWithOUT"> </a></span></span>

1. <span data-ttu-id="f3e4a-168">Selecteer tweemaal **add naamserver** om twee nieuwe rijen toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-168">Select **ADD NAMESERVER** twice to add two new rows.</span></span>
    
    ![NameCheap voor een 1-3-1](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
2. <span data-ttu-id="f3e4a-170">Typ of kopieer en plak de waarden uit de volgende tabel in de **Nameserver**-vakken.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-170">In the **Nameserver** boxes, type or copy and paste the values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="f3e4a-171">**Nameserver 1**</span><span class="sxs-lookup"><span data-stu-id="f3e4a-171">**Nameserver 1**</span></span> <br/> |<span data-ttu-id="f3e4a-172">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="f3e4a-172">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="f3e4a-173">**Nameserver 2**</span><span class="sxs-lookup"><span data-stu-id="f3e4a-173">**Nameserver 2**</span></span> <br/> |<span data-ttu-id="f3e4a-174">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="f3e4a-174">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="f3e4a-175">**Nameserver 3**</span><span class="sxs-lookup"><span data-stu-id="f3e4a-175">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="f3e4a-176">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="f3e4a-176">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="f3e4a-177">**Nameserver 4**</span><span class="sxs-lookup"><span data-stu-id="f3e4a-177">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="f3e4a-178">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="f3e4a-178">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![NameCheap voor een 1-3-2](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
3. <span data-ttu-id="f3e4a-180">Het besturingselement **Opslaan** (vinkje) selecteren</span><span class="sxs-lookup"><span data-stu-id="f3e4a-180">Select the **Save** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Redelegate-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> <span data-ttu-id="f3e4a-182">Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-182">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="f3e4a-183">Vervolgens zijn uw Microsoft-e-mail en andere services allemaal ingesteld voor gebruik met uw domein.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-183">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="f3e4a-184">Als er WEL naamservers worden vermeld</span><span class="sxs-lookup"><span data-stu-id="f3e4a-184">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="f3e4a-p109">Voer deze stappen  *alleen*  uit als u andere bestaande naamservers hebt dan de vier  *juiste*  naamservers. (Dat wil zeggen, verwijder  *alleen*  huidige naamservers die een  *andere*  naam hebben dan **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** of **ns4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="f3e4a-p109">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="f3e4a-187">Als er andere naamservers in de **Nameserver**-vakken worden vermeld, verwijdert u elke vermelding door deze te selecteren en op de toets **Delete** op het toetsenbord te drukken.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-187">If there are any other nameservers listed in the **Nameserver** boxes, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Namecheap-BP-Redelegate-1-4](../../media/3270603a-c4f4-40b7-acad-733d56e2f53c.png)
  
2. <span data-ttu-id="f3e4a-189">Selecteer tweemaal **add naamserver** om twee nieuwe rijen toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-189">Select **ADD NAMESERVER** twice to add two new rows.</span></span> 
    
    ![NameCheap voor een 1-3-1](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
3. <span data-ttu-id="f3e4a-191">Typ of kopieer en plak de waarden uit de volgende tabel in de **Nameserver**-vakken.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-191">In the **Nameserver** boxes, type or copy and paste the values from the following table.</span></span>
 
    
|||
|:-----|:-----|
|<span data-ttu-id="f3e4a-192">**Name Server 1**</span><span class="sxs-lookup"><span data-stu-id="f3e4a-192">**Name Server 1**</span></span> <br/> |<span data-ttu-id="f3e4a-193">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="f3e4a-193">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="f3e4a-194">**Name Server 2**</span><span class="sxs-lookup"><span data-stu-id="f3e4a-194">**Name Server 2**</span></span> <br/> |<span data-ttu-id="f3e4a-195">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="f3e4a-195">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="f3e4a-196">**Nameserver 3**</span><span class="sxs-lookup"><span data-stu-id="f3e4a-196">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="f3e4a-197">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="f3e4a-197">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="f3e4a-198">**Nameserver 4**</span><span class="sxs-lookup"><span data-stu-id="f3e4a-198">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="f3e4a-199">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="f3e4a-199">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![NameCheap voor een 1-3-2](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
4. <span data-ttu-id="f3e4a-201">Het besturingselement **Opslaan** (vinkje) selecteren</span><span class="sxs-lookup"><span data-stu-id="f3e4a-201">Select the **Save** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Redelegate-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> <span data-ttu-id="f3e4a-203">Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-203">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="f3e4a-204">Vervolgens zijn uw Microsoft-e-mail en andere services allemaal ingesteld voor gebruik met uw domein.</span><span class="sxs-lookup"><span data-stu-id="f3e4a-204">Then your Microsoft email and other services will be all set to work with your domain.</span></span>
