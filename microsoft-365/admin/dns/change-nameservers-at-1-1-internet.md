---
title: Naamservers wijzigen om Microsoft in te stellen met 1&1 IONOS
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
ms.assetid: 31efc571-c8b9-46fb-b42d-203c2fb25289
description: Lees hoe u Office 365 instellen dat door 21Vianet wordt beheerd om uw DNS-records te beheren, wanneer 1&1 Internet de DNS-hostingprovider is.
ms.openlocfilehash: 53e846b5a9672f3fbf0e003ec48261afc80c0abf
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630005"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-11-ionos"></a><span data-ttu-id="64be9-103">Naamservers wijzigen om Microsoft 365 in te stellen met 1&1 IONOS</span><span class="sxs-lookup"><span data-stu-id="64be9-103">Change nameservers to set up Microsoft 365 with 1&1 IONOS</span></span>

 <span data-ttu-id="64be9-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="64be9-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="64be9-105">Volg deze instructies als u wilt dat Microsoft 365 uw Microsoft 365 DNS-records voor u beheert.</span><span class="sxs-lookup"><span data-stu-id="64be9-105">Follow these instructions if you want Microsoft 365 to manage your Microsoft 365 DNS records for you.</span></span> <span data-ttu-id="64be9-106">(Als u dat liever hebt, u [al uw Microsoft 365 DNS-records beheren op 1&1 IONOS](create-dns-records-at-1-1-internet.md).)</span><span class="sxs-lookup"><span data-stu-id="64be9-106">(If you prefer, you can [manage all your Microsoft 365 DNS records at 1&1 IONOS](create-dns-records-at-1-1-internet.md).)</span></span> 
  

    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="64be9-107">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="64be9-107">Add a TXT record for verification</span></span>


<span data-ttu-id="64be9-108">Voordat u uw domein met Microsoft 365 gebruikt, moeten we ervoor zorgen dat u eigenaar bent.</span><span class="sxs-lookup"><span data-stu-id="64be9-108">Before you use your domain with Microsoft 365, we have to make sure that you own it.</span></span> <span data-ttu-id="64be9-109">Uw mogelijkheid om in te loggen op uw account bij uw domeinregistrar en de DNS-record te maken bewijst microsoft 365 dat u eigenaar bent van het domein.</span><span class="sxs-lookup"><span data-stu-id="64be9-109">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="64be9-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="64be9-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="64be9-112">Volg onderstaande stappen of [bekijk de video (start op 0:42)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-1-1-Internet-0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="64be9-112">Follow the steps below or [watch the video (start at 0:42)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-1-1-Internet-0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="64be9-113">Om aan de slag te gaan, ga je naar je domeinenpagina op 1&1 IONOS via [deze link.](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F)</span><span class="sxs-lookup"><span data-stu-id="64be9-113">To get started, go to your domains page at 1&1 IONOS via [this link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span></span> <span data-ttu-id="64be9-114">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="64be9-114">You'll be prompted to log in.</span></span> 
    
2. <span data-ttu-id="64be9-115">Selecteer onder **MY DOMAINS** de optie **Manage domains**.</span><span class="sxs-lookup"><span data-stu-id="64be9-115">Under **MY DOMAINS**, select **Manage domains**.</span></span>
    
3. <span data-ttu-id="64be9-116">Zoek op de pagina **Domain Center** het domein dat u wilt bijwerken. selecteer vervolgens het **besturingselement Paneel** **(v)** voor dat domein.</span><span class="sxs-lookup"><span data-stu-id="64be9-116">On the **Domain Center** page, find the domain that you want to update; then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="64be9-117">Selecteer **DNS-instellingen bewerken**in het gebied **Domeininstellingen** .</span><span class="sxs-lookup"><span data-stu-id="64be9-117">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="64be9-118">Selecteer **Record toevoegen**in de sectie **TXT- en SRV-records** .</span><span class="sxs-lookup"><span data-stu-id="64be9-118">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
    <span data-ttu-id="64be9-119">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="64be9-119">(You may have to scroll down.)</span></span> 
    
6. <span data-ttu-id="64be9-120">Ga naar het gebied **Add Record**. In de vakken voor de nieuwe record in dit gebied kunt u vervolgens de waarden uit de volgende tabel typen of kopiëren en plakken.</span><span class="sxs-lookup"><span data-stu-id="64be9-120">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
||||
|:-----|:-----|:-----|
|<span data-ttu-id="64be9-121">**Type**</span><span class="sxs-lookup"><span data-stu-id="64be9-121">**Type**</span></span> <br/> |<span data-ttu-id="64be9-122">**Voorvoegsel**</span><span class="sxs-lookup"><span data-stu-id="64be9-122">**Prefix**</span></span> <br/> |<span data-ttu-id="64be9-123">**Naamwaarde**</span><span class="sxs-lookup"><span data-stu-id="64be9-123">**Name Value**</span></span> <br/> |
|<span data-ttu-id="64be9-124">TXT</span><span class="sxs-lookup"><span data-stu-id="64be9-124">TXT</span></span>  <br/> |<span data-ttu-id="64be9-125">(Laat dit veld leeg.)</span><span class="sxs-lookup"><span data-stu-id="64be9-125">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="64be9-126">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="64be9-126">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="64be9-127">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="64be9-127">**Note**: This is an example.</span></span> <span data-ttu-id="64be9-128">Gebruik hier de waarde van uw specifieke **bestemming of adresinrichten** in de tabel in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="64be9-128">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span> [<span data-ttu-id="64be9-129">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="64be9-129">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
7. <span data-ttu-id="64be9-130">Selecteer **Opslaan**en vervolgens opnieuw **opslaan.**</span><span class="sxs-lookup"><span data-stu-id="64be9-130">Select **Save**, and then **Save** again.</span></span> 
    
8. <span data-ttu-id="64be9-131">Selecteer **Ja**. in het dialoogvenster **DNS-instellingen bewerken** .</span><span class="sxs-lookup"><span data-stu-id="64be9-131">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
9. <span data-ttu-id="64be9-132">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="64be9-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="64be9-133">Nu u de record op de site van uw domeinregistrar hebt toegevoegd, gaat u terug naar Microsoft 365 en vraagt u Microsoft 365 om de record te zoeken.</span><span class="sxs-lookup"><span data-stu-id="64be9-133">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="64be9-134">Wanneer Microsoft 365 de juiste TXT-record vindt, wordt uw domein geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="64be9-134">When Microsoft 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="64be9-135">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="64be9-135">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="64be9-136">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="64be9-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="64be9-137">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="64be9-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="64be9-138">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="64be9-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="64be9-139">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden.</span><span class="sxs-lookup"><span data-stu-id="64be9-139">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="64be9-140">Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet.</span><span class="sxs-lookup"><span data-stu-id="64be9-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="64be9-141">Zie Problemen zoeken en oplossen na het toevoegen van [uw domein- of DNS-records in Microsoft 365](../get-help-with-domains/find-and-fix-issues.md)als u problemen ondervindt met e-mailstroom of andere problemen na het toevoegen van DNS-records.</span><span class="sxs-lookup"><span data-stu-id="64be9-141">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Microsoft 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="64be9-142">De naamserverrecords (NS-records) van uw domein wijzigen</span><span class="sxs-lookup"><span data-stu-id="64be9-142">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="64be9-143">Als u het instellen van uw domein met Microsoft 365 wilt voltooien, wijzigt u de NS-records van uw domein bij uw domeinregistrar om naar de primaire en secundaire naamservers van Microsoft 365 te wijzen.</span><span class="sxs-lookup"><span data-stu-id="64be9-143">To complete setting up your domain with Microsoft 365, you change your domain's NS records at your domain registrar to point to the Microsoft 365 primary and secondary name servers.</span></span> <span data-ttu-id="64be9-144">Hiermee wordt Microsoft 365 ingesteld om de DNS-records van het domein voor u bij te werken.</span><span class="sxs-lookup"><span data-stu-id="64be9-144">This sets up Microsoft 365 to update the domain's DNS records for you.</span></span> <span data-ttu-id="64be9-145">We voegen alle records toe zodat e-mail, Skype voor Bedrijven Online en uw openbare website met uw domein werken en u helemaal klaar bent.</span><span class="sxs-lookup"><span data-stu-id="64be9-145">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="64be9-146">Wanneer u de NS-records van uw domein wijzigt om naar de Microsoft 365-naamservers te wijzen, worden alle services die momenteel aan uw domein zijn gekoppeld, beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="64be9-146">When you change your domain's NS records to point to the Microsoft 365 name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="64be9-147">Alle e-mail die naar uw domein wordt verzonden (zoals rob@ *your_domain* .com) wordt bijvoorbeeld naar Microsoft 365 verzonden nadat u deze wijziging hebt aangemaakt.</span><span class="sxs-lookup"><span data-stu-id="64be9-147">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft 365 after you make this change.</span></span> 
  
<span data-ttu-id="64be9-148">Klaar om uw NS-records te wijzigen, zodat Microsoft 365 uw domein kan instellen?</span><span class="sxs-lookup"><span data-stu-id="64be9-148">Ready to change your NS records so Microsoft 365 can set up your domain?</span></span> <span data-ttu-id="64be9-149">Volg onderstaande stappen of [bekijk de video (start bij 365)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-1-1-Internet-0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="64be9-149">Follow the steps below or [watch the video (start at 2:47)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-1-1-Internet-0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="64be9-p110">In de volgende procedure kunt u zien hoe u andere, ongewenste naamservers uit de lijst verwijdert en hoe u de juiste naamservers toevoegt als deze niet al in de lijst staan. >  Na het voltooien van de stappen in deze sectie, moeten alleen de volgende vier naamservers in de lijst staan: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="64be9-p110">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed. >  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="64be9-152">Ga om aan de slag te gaan naar de pagina domeinen op 1&1 IONOS via [deze link.](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F)</span><span class="sxs-lookup"><span data-stu-id="64be9-152">To get started, go to your domains page at 1&1 IONOS by using [this link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span></span> <span data-ttu-id="64be9-153">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="64be9-153">You'll be prompted to log in.</span></span> 
    
2. <span data-ttu-id="64be9-154">Selecteer onder **MY DOMAINS** de optie **Manage domains**.</span><span class="sxs-lookup"><span data-stu-id="64be9-154">Under **MY DOMAINS**, select **Manage domains**.</span></span>
    
3. <span data-ttu-id="64be9-155">Zoek op de pagina **Domain Center** het domein dat u wilt bijwerken en selecteer vervolgens het besturingselement **Paneel** **(v)** voor dat domein.</span><span class="sxs-lookup"><span data-stu-id="64be9-155">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="64be9-156">Selecteer **DNS-instellingen bewerken**in het gebied **Domeininstellingen** .</span><span class="sxs-lookup"><span data-stu-id="64be9-156">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="64be9-157">In de sectie **Name Server Settings** selecteert u **Other name servers**.</span><span class="sxs-lookup"><span data-stu-id="64be9-157">In the **Name Server Settings** section, select **Other name servers**.</span></span>
    
    <span data-ttu-id="64be9-158">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="64be9-158">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="64be9-159">Afhankelijk van of er al naamservers worden vermeld op de pagina die wordt weergegeven, gaat u op een van de volgende twee manieren verder:</span><span class="sxs-lookup"><span data-stu-id="64be9-159">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="64be9-160">Als er nog **GEEN** naamservers worden vermeld, [Als er nog GEEN naamservers worden vermeld](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="64be9-160">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="64be9-161">Als er **WEL** naamservers worden vermeld, [Als er WEL naamservers worden vermeld](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="64be9-161">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="64be9-162">Als er nog GEEN naamservers worden vermeld</span><span class="sxs-lookup"><span data-stu-id="64be9-162">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="64be9-163">Typ of kopieer en plak de waarde uit de volgende tabel in het vak **Name server 1**.</span><span class="sxs-lookup"><span data-stu-id="64be9-163">In the **Name server 1** box, type or copy and paste the value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="64be9-164">**Name server 1**</span><span class="sxs-lookup"><span data-stu-id="64be9-164">**Name server 1**</span></span> <br/> |<span data-ttu-id="64be9-165">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="64be9-165">ns1.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Een waarde invoeren in het vak Naamserver 1](../../media/34509935-461f-427f-9796-c3cf840bd9be.png)
  
2. <span data-ttu-id="64be9-167">In de vervolgkeuzelijst **Additional name servers** kiest u **My secondary name servers**.</span><span class="sxs-lookup"><span data-stu-id="64be9-167">In the **Additional name servers** drop-down list, choose **My secondary name servers**.</span></span>
    
    ![Choosing My secondary name servers in the list](../../media/7eb14856-86da-45c2-910c-c72312250a18.png)
  
3. <span data-ttu-id="64be9-169">Typ of kopieer en plak de waarde uit de volgende tabel in het vak **Name server 2, 3, and 4**.</span><span class="sxs-lookup"><span data-stu-id="64be9-169">In the **Name server 2, 3, and 4** boxes, type or copy and paste the value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="64be9-170">**Name server 2**</span><span class="sxs-lookup"><span data-stu-id="64be9-170">**Name server 2**</span></span> <br/> |<span data-ttu-id="64be9-171">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="64be9-171">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="64be9-172">**Name server 3**</span><span class="sxs-lookup"><span data-stu-id="64be9-172">**Name server 3**</span></span> <br/> |<span data-ttu-id="64be9-173">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="64be9-173">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="64be9-174">**Name server 4**</span><span class="sxs-lookup"><span data-stu-id="64be9-174">**Name server 4**</span></span> <br/> |<span data-ttu-id="64be9-175">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="64be9-175">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    ![Entering name server values](../../media/0f15880c-88b6-4133-8f31-62f0d98ee63f.png)
  
4. <span data-ttu-id="64be9-176">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="64be9-176">Select **Save**.</span></span>
    
    ![Opslaan selecteren op de pagina Naamserverinstellingen](../../media/864f7927-7127-4784-b8d2-dadfea2f9dc8.png)
  
5. <span data-ttu-id="64be9-178">Selecteer **Ja**. in het dialoogvenster **DNS-instellingen bewerken** .</span><span class="sxs-lookup"><span data-stu-id="64be9-178">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
    ![Opslaan selecteren in het dialoogvenster DNS-instellingen bewerken](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> <span data-ttu-id="64be9-180">Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd.</span><span class="sxs-lookup"><span data-stu-id="64be9-180">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="64be9-181">Vervolgens zijn uw Microsoft-e-mail en andere services helemaal klaar om met uw domein te werken.</span><span class="sxs-lookup"><span data-stu-id="64be9-181">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="64be9-182">Als er WEL naamservers worden vermeld</span><span class="sxs-lookup"><span data-stu-id="64be9-182">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="64be9-p113">Voer deze stappen  *alleen*  uit als u andere bestaande naamservers hebt dan de vier  *juiste*  naamservers. (Dat wil zeggen, verwijder  *alleen*  huidige naamservers die een  *andere*  naam hebben dan **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** of **ns4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="64be9-p113">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="64be9-185">Als er al naamservers in de **Name server**-vakken worden vermeld, verwijdert u elke vermelding door deze te selecteren en op de toets **Delete** op het toetsenbord te drukken.</span><span class="sxs-lookup"><span data-stu-id="64be9-185">If there are already nameservers listed in the **Name server** boxes, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Deleting name servers](../../media/af0a68cc-b058-4925-b3b1-52dfded003c1.png)
  
2. <span data-ttu-id="64be9-187">Typ of kopieer en plak de waarden uit de volgende tabel in het vak **Name server 1, 2, 3, and 4**.</span><span class="sxs-lookup"><span data-stu-id="64be9-187">In the **Name server 1, 2, 3, and 4** boxes, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="64be9-188">**Name server 1**</span><span class="sxs-lookup"><span data-stu-id="64be9-188">**Name server 1**</span></span> <br/> |<span data-ttu-id="64be9-189">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="64be9-189">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="64be9-190">**Name server 2**</span><span class="sxs-lookup"><span data-stu-id="64be9-190">**Name server 2**</span></span> <br/> |<span data-ttu-id="64be9-191">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="64be9-191">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="64be9-192">**Name server 3**</span><span class="sxs-lookup"><span data-stu-id="64be9-192">**Name server 3**</span></span> <br/> |<span data-ttu-id="64be9-193">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="64be9-193">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="64be9-194">**Name server 4**</span><span class="sxs-lookup"><span data-stu-id="64be9-194">**Name server 4**</span></span> <br/> |<span data-ttu-id="64be9-195">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="64be9-195">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Waarden van naamserver invoeren](../../media/52826bd1-0596-4103-a728-d5d28b9610d2.png)
  
3. <span data-ttu-id="64be9-197">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="64be9-197">Select **Save**.</span></span>
    
    ![Opslaan selecteren op de pagina Naamserverinstellingen](../../media/cd10e4fb-b7fa-480f-855b-a443f2705cf2.png)
  
4. <span data-ttu-id="64be9-199">Selecteer **Ja**. in het dialoogvenster **DNS-instellingen bewerken** .</span><span class="sxs-lookup"><span data-stu-id="64be9-199">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
    ![Opslaan selecteren in het dialoogvenster DNS-instellingen bewerken](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> <span data-ttu-id="64be9-201">Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd.</span><span class="sxs-lookup"><span data-stu-id="64be9-201">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="64be9-202">Vervolgens zijn uw Microsoft-e-mail en andere services helemaal klaar om met uw domein te werken.</span><span class="sxs-lookup"><span data-stu-id="64be9-202">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  


