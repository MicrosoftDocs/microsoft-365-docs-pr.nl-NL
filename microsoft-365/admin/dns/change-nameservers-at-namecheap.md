---
title: Naamservers wijzigen voor het instellen van Office 365 bij Namecheap
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
ms.assetid: 84f467f6-28cf-40f0-94d0-a2a27ddfc2e7
description: 'Lees of u uw aangepaste Office 365-domein wilt instellen met Namecheap als u wilt dat Office 365 uw DNS-records beheert. '
ms.openlocfilehash: 3a26f2acb9bb52d05974f050b265dd3e1a0fc0cb
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "42806915"
---
# <a name="change-nameservers-to-set-up-office-365-with-namecheap"></a><span data-ttu-id="8dc9b-103">Naamservers wijzigen voor het instellen van Office 365 bij Namecheap</span><span class="sxs-lookup"><span data-stu-id="8dc9b-103">Change nameservers to set up Office 365 with Namecheap</span></span>

 <span data-ttu-id="8dc9b-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="8dc9b-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="8dc9b-p101">Volg deze instructies als u wilt dat Office 365 uw DNS-records voor Office 365 voor u beheert. (Als u wilt, kunt u [al uw DNS-records voor Office 365 bij Namecheap beheren](create-dns-records-at-namecheap.md).)</span><span class="sxs-lookup"><span data-stu-id="8dc9b-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Namecheap](create-dns-records-at-namecheap.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="8dc9b-107">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="8dc9b-107">Add a TXT record for verification</span></span>

1. <span data-ttu-id="8dc9b-p102">Ga eerst naar de domeinenpagina bij Namecheap via [deze koppeling](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). U wordt gevraagd u aan te melden en verder te gaan.</span><span class="sxs-lookup"><span data-stu-id="8dc9b-p102">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="8dc9b-111">Kies op de **bestemmingspagina** onder **Account**de optie **Lijst met domeinen** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="8dc9b-111">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="8dc9b-113">Zoek op de pagina **Domeinlijst** de naam van het domein dat u wilt bewerken en selecteer **Beheren**.</span><span class="sxs-lookup"><span data-stu-id="8dc9b-113">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="8dc9b-115">Selecteer **Geavanceerde DNS**.</span><span class="sxs-lookup"><span data-stu-id="8dc9b-115">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="8dc9b-117">Selecteer IN de sectie **HOST RECORDS** de optie NIEUWE **RECORD TOEVOEGEN**.</span><span class="sxs-lookup"><span data-stu-id="8dc9b-117">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="8dc9b-119">Selecteer in de vervolgkeuzelijst **Type** de optie **TXT Record**.</span><span class="sxs-lookup"><span data-stu-id="8dc9b-119">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8dc9b-120">De vervolgkeuzelijst **Type** wordt automatisch weergegeven wanneer u **NIEUWE RECORD TOEVOEGEN selecteert.**</span><span class="sxs-lookup"><span data-stu-id="8dc9b-120">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span>
  
    ![Namecheap-BP-Verify-1-1](../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. <span data-ttu-id="8dc9b-122">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="8dc9b-122">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="8dc9b-123">(Kies de **TTL-waarde** in de vervolgkeuzelijst.)</span><span class="sxs-lookup"><span data-stu-id="8dc9b-123">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
|<span data-ttu-id="8dc9b-124">**Type**</span><span class="sxs-lookup"><span data-stu-id="8dc9b-124">**Type**</span></span>|<span data-ttu-id="8dc9b-125">**Host**</span><span class="sxs-lookup"><span data-stu-id="8dc9b-125">**Host**</span></span>|<span data-ttu-id="8dc9b-126">**Value**</span><span class="sxs-lookup"><span data-stu-id="8dc9b-126">**Value**</span></span>|<span data-ttu-id="8dc9b-127">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8dc9b-127">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8dc9b-128">TXT</span><span class="sxs-lookup"><span data-stu-id="8dc9b-128">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="8dc9b-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="8dc9b-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="8dc9b-130">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="8dc9b-130">**Note**: This is an example.</span></span> <span data-ttu-id="8dc9b-131">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365.</span><span class="sxs-lookup"><span data-stu-id="8dc9b-131">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="8dc9b-132">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="8dc9b-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="8dc9b-133">30 min</span><span class="sxs-lookup"><span data-stu-id="8dc9b-133">30 min</span></span>  <br/> |
   
   ![Namecheap-BP-Verify-1-2](../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. <span data-ttu-id="8dc9b-135">Selecteer het besturingselement **Wijzigingen opslaan** (vinkje).</span><span class="sxs-lookup"><span data-stu-id="8dc9b-135">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Verify-1-3](../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. <span data-ttu-id="8dc9b-137">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="8dc9b-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="8dc9b-138">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Office 365 en vraagt u of Office 365 naar de record wil zoeken.</span><span class="sxs-lookup"><span data-stu-id="8dc9b-138">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="8dc9b-139">Wanneer in Office 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="8dc9b-139">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="8dc9b-140">Ga in het beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Instellingendomeinen.</a> **Settings**</span><span class="sxs-lookup"><span data-stu-id="8dc9b-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="8dc9b-141">Selecteer **op** de pagina Domeinen het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="8dc9b-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="8dc9b-142">Selecteer **op** de pagina Setup de optie **Installatie starten**.</span><span class="sxs-lookup"><span data-stu-id="8dc9b-142">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="8dc9b-143">Selecteer **op** de pagina Domein verifiëren de optie **Verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="8dc9b-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="8dc9b-p104">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8dc9b-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="8dc9b-147">De naamserverrecords (NS-records) van uw domein wijzigen</span><span class="sxs-lookup"><span data-stu-id="8dc9b-147">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="8dc9b-p105">U voltooit het instellen van uw domein met Office 365 door de NS-records van uw domein bij uw domeinregistrar te wijzigen, zodat deze verwijzen naar de primaire en secundaire naamservers van Office 365. Hiermee wordt Office 365 zo ingesteld dat de DNS-records van het domein voor u worden bijgewerkt. Alle benodigde records worden toegevoegd zodat e-mail, Skype voor Bedrijven Online en uw openbare website met uw domein kunnen werken. Daarna bent u klaar.</span><span class="sxs-lookup"><span data-stu-id="8dc9b-p105">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="8dc9b-p106">Als u de NS-records van uw domein laat verwijzen naar de naamservers van Office 365, is dit van invloed op alle services die momenteel aan uw domein zijn gekoppeld. Zo wordt bijvoorbeeld alle e-mail die naar uw domein wordt verzonden (zoals william@ *uw_domein*  .com), naar Office 365 verzonden zodra u deze wijziging hebt aangebracht.</span><span class="sxs-lookup"><span data-stu-id="8dc9b-p106">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="8dc9b-153">Na het voltooien van de stappen in deze sectie, moeten  *alleen*  de volgende vier naamservers in de lijst staan: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  In de volgende procedure kunt u zien hoe u andere, ongewenste naamservers uit de lijst verwijdert en hoe u de  *juiste*  naamservers toevoegt als deze niet al in de lijst staan.</span><span class="sxs-lookup"><span data-stu-id="8dc9b-153">When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.</span></span> 
  
1. <span data-ttu-id="8dc9b-p107">Ga eerst naar de domeinenpagina bij Namecheap via [deze koppeling](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). U wordt gevraagd u aan te melden en verder te gaan.</span><span class="sxs-lookup"><span data-stu-id="8dc9b-p107">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="8dc9b-157">Kies op de **bestemmingspagina** onder **Account**de optie **Lijst met domeinen** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="8dc9b-157">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="8dc9b-159">Zoek op de pagina **Domeinlijst** de naam van het domein dat u wilt bewerken en selecteer **Beheren**.</span><span class="sxs-lookup"><span data-stu-id="8dc9b-159">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="8dc9b-161">Selecteer **Domein**.</span><span class="sxs-lookup"><span data-stu-id="8dc9b-161">Select **Domain**.</span></span>
    
    ![Namecheap-BP-Redelegate-1-1](../../media/59588406-794e-4ae4-8526-35e3111b5791.png)
  
5. <span data-ttu-id="8dc9b-163">Ga naar de sectie **NAMESERVERS** en selecteer **Custom** in de vervolgkeuzelijst **Namecheap Default**.</span><span class="sxs-lookup"><span data-stu-id="8dc9b-163">Find the **NAMESERVERS** section, and then select **Custom** from the **Namecheap Default** drop-down list.</span></span> 
    
    ![Namecheap-BP-Redelegate-1-2](../../media/7df56295-fdb3-472f-9442-13f780c2c93e.png)
  
6. <span data-ttu-id="8dc9b-165">Afhankelijk van het feit of er al nameservers op de pagina staan die nu wordt weergegeven, gaat u verder met een van de twee volgende procedures.</span><span class="sxs-lookup"><span data-stu-id="8dc9b-165">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures.</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="8dc9b-166">Als er nog GEEN naamservers worden vermeld</span><span class="sxs-lookup"><span data-stu-id="8dc9b-166">If there are NO nameservers already listed</span></span>
<span data-ttu-id="8dc9b-167"><a name="BKMK_ProcedureWithOUT"> </a></span><span class="sxs-lookup"><span data-stu-id="8dc9b-167"><a name="BKMK_ProcedureWithOUT"> </a></span></span>

1. <span data-ttu-id="8dc9b-168">Selecteer **NaamSERVER toevoegen** twee maal om twee nieuwe rijen toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="8dc9b-168">Select **ADD NAMESERVER** twice to add two new rows.</span></span>
    
    ![Afbeelding van het lint](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
2. <span data-ttu-id="8dc9b-170">Typ of kopieer en plak de waarden uit de volgende tabel in de **Nameserver**-vakken.</span><span class="sxs-lookup"><span data-stu-id="8dc9b-170">In the **Nameserver** boxes, type or copy and paste the values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="8dc9b-171">**Nameserver 1**</span><span class="sxs-lookup"><span data-stu-id="8dc9b-171">**Nameserver 1**</span></span> <br/> |<span data-ttu-id="8dc9b-172">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="8dc9b-172">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="8dc9b-173">**Nameserver 2**</span><span class="sxs-lookup"><span data-stu-id="8dc9b-173">**Nameserver 2**</span></span> <br/> |<span data-ttu-id="8dc9b-174">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="8dc9b-174">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="8dc9b-175">**Nameserver 3**</span><span class="sxs-lookup"><span data-stu-id="8dc9b-175">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="8dc9b-176">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="8dc9b-176">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="8dc9b-177">**Nameserver 4**</span><span class="sxs-lookup"><span data-stu-id="8dc9b-177">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="8dc9b-178">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="8dc9b-178">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Afbeelding van het lint](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
3. <span data-ttu-id="8dc9b-180">Selecteer het besturingselement **Opslaan** (vinkje).</span><span class="sxs-lookup"><span data-stu-id="8dc9b-180">Select the **Save** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Redelegate-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> <span data-ttu-id="8dc9b-p108">Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd. Vervolgens worden uw e-mail voor Office 365 en andere services ingesteld voor gebruik met uw domein.</span><span class="sxs-lookup"><span data-stu-id="8dc9b-p108">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="8dc9b-184">Als er WEL naamservers worden vermeld</span><span class="sxs-lookup"><span data-stu-id="8dc9b-184">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="8dc9b-p109">Voer deze stappen  *alleen*  uit als u andere bestaande naamservers hebt dan de vier  *juiste*  naamservers. (Dat wil zeggen, verwijder  *alleen*  huidige naamservers die een  *andere*  naam hebben dan **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** of **ns4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="8dc9b-p109">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="8dc9b-187">Als er andere naamservers in de **Nameserver**-vakken worden vermeld, verwijdert u elke vermelding door deze te selecteren en op de toets **Delete** op het toetsenbord te drukken.</span><span class="sxs-lookup"><span data-stu-id="8dc9b-187">If there are any other nameservers listed in the **Nameserver** boxes, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Namecheap-BP-Redelegate-1-4](../../media/3270603a-c4f4-40b7-acad-733d56e2f53c.png)
  
2. <span data-ttu-id="8dc9b-189">Selecteer **NaamSERVER toevoegen** twee maal om twee nieuwe rijen toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="8dc9b-189">Select **ADD NAMESERVER** twice to add two new rows.</span></span> 
    
    ![Afbeelding van het lint](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
3. <span data-ttu-id="8dc9b-191">Typ of kopieer en plak de waarden uit de volgende tabel in de **Nameserver**-vakken.</span><span class="sxs-lookup"><span data-stu-id="8dc9b-191">In the **Nameserver** boxes, type or copy and paste the values from the following table.</span></span>
 
    
|||
|:-----|:-----|
|<span data-ttu-id="8dc9b-192">**Name Server 1**</span><span class="sxs-lookup"><span data-stu-id="8dc9b-192">**Name Server 1**</span></span> <br/> |<span data-ttu-id="8dc9b-193">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="8dc9b-193">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="8dc9b-194">**Name Server 2**</span><span class="sxs-lookup"><span data-stu-id="8dc9b-194">**Name Server 2**</span></span> <br/> |<span data-ttu-id="8dc9b-195">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="8dc9b-195">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="8dc9b-196">**Nameserver 3**</span><span class="sxs-lookup"><span data-stu-id="8dc9b-196">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="8dc9b-197">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="8dc9b-197">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="8dc9b-198">**Nameserver 4**</span><span class="sxs-lookup"><span data-stu-id="8dc9b-198">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="8dc9b-199">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="8dc9b-199">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Afbeelding van het lint](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
4. <span data-ttu-id="8dc9b-201">Selecteer het besturingselement **Opslaan** (vinkje).</span><span class="sxs-lookup"><span data-stu-id="8dc9b-201">Select the **Save** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Redelegate-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> <span data-ttu-id="8dc9b-p110">Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd. Vervolgens worden uw e-mail voor Office 365 en andere services ingesteld voor gebruik met uw domein.</span><span class="sxs-lookup"><span data-stu-id="8dc9b-p110">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span>
