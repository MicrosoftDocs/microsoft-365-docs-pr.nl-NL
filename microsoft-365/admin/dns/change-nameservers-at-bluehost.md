---
title: Naamservers wijzigen om Microsoft in te stellen met Bluehost
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
ms.assetid: 7712b6af-329c-43a0-af7b-c4e4c1befb0e
description: 'Meer informatie over hoe u Microsoft instellen om uw DNS-records te beheren bij Bluehost. '
ms.openlocfilehash: 63084b35c3f0d71764bca1995f25d7c6f0842a86
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629909"
---
# <a name="change-nameservers-to-set-up-microsoft-with-bluehost"></a><span data-ttu-id="71eb6-103">Naamservers wijzigen om Microsoft in te stellen met Bluehost</span><span class="sxs-lookup"><span data-stu-id="71eb6-103">Change nameservers to set up Microsoft with Bluehost</span></span>

 <span data-ttu-id="71eb6-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="71eb6-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="71eb6-105">Volg deze instructies als u wilt dat Microsoft uw DNS-records voor u beheert.</span><span class="sxs-lookup"><span data-stu-id="71eb6-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="71eb6-106">(Als u dat liever hebt, u [al uw DNS-records beheren bij Bluehost](create-dns-records-at-bluehost.md).)</span><span class="sxs-lookup"><span data-stu-id="71eb6-106">(If you prefer, you can [manage all your DNS records at Bluehost](create-dns-records-at-bluehost.md).)</span></span>
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="71eb6-107">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="71eb6-107">Add a TXT record for verification</span></span>

<span data-ttu-id="71eb6-108">Voordat u uw domein bij Microsoft gebruikt, moeten we ervoor zorgen dat u eigenaar bent.</span><span class="sxs-lookup"><span data-stu-id="71eb6-108">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="71eb6-109">Uw mogelijkheid om in te loggen op uw account bij uw domeinregistrar en de DNS-record te maken bewijst microsoft dat u eigenaar bent van het domein.</span><span class="sxs-lookup"><span data-stu-id="71eb6-109">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="71eb6-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="71eb6-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="71eb6-112">Ga eerst naar de pagina met domeinen bij Bluehost via [deze koppeling](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="71eb6-112">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="71eb6-113">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="71eb6-113">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="71eb6-114">Op de pagina **Domains**, in het gebied **domain**, zoekt u de rij voor het domein dat u wilt wijzigen, en schakelt u vervolgens het selectievakje in voor dat domein.</span><span class="sxs-lookup"><span data-stu-id="71eb6-114">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="71eb6-115">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="71eb6-115">(You may have to scroll down.)</span></span> 
    
3. <span data-ttu-id="71eb6-116">Selecteer **dns-records beheren**in het **domain_name-gebied** in de rij **DNS-zoneeditor** .</span><span class="sxs-lookup"><span data-stu-id="71eb6-116">In the **domain_name** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="71eb6-117">Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add DNS Record** in de vakken voor de nieuwe record op de pagina DNS Zone Editor.</span><span class="sxs-lookup"><span data-stu-id="71eb6-117">On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="71eb6-118">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="71eb6-118">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="71eb6-119">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="71eb6-119">**Host Record**</span></span> <br/> |<span data-ttu-id="71eb6-120">**TTL**</span><span class="sxs-lookup"><span data-stu-id="71eb6-120">**TTL**</span></span> <br/> |<span data-ttu-id="71eb6-121">**Type**</span><span class="sxs-lookup"><span data-stu-id="71eb6-121">**Type**</span></span> <br/> |<span data-ttu-id="71eb6-122">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="71eb6-122">**TXT Value**</span></span> <br/> |
|@  <br/> |<span data-ttu-id="71eb6-123">14400</span><span class="sxs-lookup"><span data-stu-id="71eb6-123">14400</span></span>  <br/> |<span data-ttu-id="71eb6-124">TXT</span><span class="sxs-lookup"><span data-stu-id="71eb6-124">TXT</span></span>  <br/> |<span data-ttu-id="71eb6-125">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="71eb6-125">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="71eb6-126">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="71eb6-126">**Note:** This is an example.</span></span> <span data-ttu-id="71eb6-127">Gebruik hier de waarde van uw specifieke **bestemming of adrespunt** in de tabel.</span><span class="sxs-lookup"><span data-stu-id="71eb6-127">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="71eb6-128">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="71eb6-128">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
5. <span data-ttu-id="71eb6-129">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="71eb6-129">Select **add record**.</span></span>
    
6. <span data-ttu-id="71eb6-130">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="71eb6-130">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="71eb6-131">Nu u de record op de site van uw domeinregistrar hebt toegevoegd, gaat u terug naar Microsoft en vraagt u om een zoekopdracht naar de record.</span><span class="sxs-lookup"><span data-stu-id="71eb6-131">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="71eb6-132">Wanneer Microsoft de juiste TXT-record vindt, wordt uw domein geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="71eb6-132">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="71eb6-133">Ga in het Microsoft-beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Instellingendomeinen.</a> **Settings**</span><span class="sxs-lookup"><span data-stu-id="71eb6-133">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="71eb6-134">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="71eb6-134">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="71eb6-135">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="71eb6-135">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="71eb6-136">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="71eb6-136">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="71eb6-137">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden.</span><span class="sxs-lookup"><span data-stu-id="71eb6-137">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="71eb6-138">Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet.</span><span class="sxs-lookup"><span data-stu-id="71eb6-138">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="71eb6-139">Zie Problemen zoeken en oplossen na het toevoegen van [uw domein- of DNS-records](../get-help-with-domains/find-and-fix-issues.md)als u problemen ondervindt met e-mailstroom of andere problemen na het toevoegen van DNS-records.</span><span class="sxs-lookup"><span data-stu-id="71eb6-139">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="71eb6-140">De naamserverrecords (NS-records) van uw domein wijzigen</span><span class="sxs-lookup"><span data-stu-id="71eb6-140">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="71eb6-141">Als u het instellen van uw domein met Microsoft wilt voltooien, wijzigt u de NS-records van uw domein bij uw domeinregistrar om naar de primaire en secundaire naamservers te wijzen.</span><span class="sxs-lookup"><span data-stu-id="71eb6-141">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the  primary and secondary name servers.</span></span> <span data-ttu-id="71eb6-142">Hiermee wordt Microsoft ingesteld om de DNS-records van het domein voor u bij te werken.</span><span class="sxs-lookup"><span data-stu-id="71eb6-142">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="71eb6-143">We voegen alle records toe zodat e-mail, Skype voor Bedrijven Online en uw openbare website met uw domein werken en u helemaal klaar bent.</span><span class="sxs-lookup"><span data-stu-id="71eb6-143">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="71eb6-144">Wanneer u de NS-records van uw domein wijzigt om naar de Microsoft-naamservers te wijzen, worden alle services die momenteel aan uw domein zijn gekoppeld, beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="71eb6-144">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="71eb6-145">Alle e-mail die naar uw *your_domain* domein wordt verzonden (zoals rob@ your_domain.com) wordt bijvoorbeeld naar Microsoft verzonden nadat u deze wijziging hebt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="71eb6-145">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="71eb6-p109">In de volgende procedure kunt u zien hoe u andere, ongewenste naamservers uit de lijst verwijdert en hoe u de juiste naamservers toevoegt als deze niet al in de lijst staan. >  Na het voltooien van de stappen in deze sectie, moeten alleen de volgende vier naamservers in de lijst staan: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="71eb6-p109">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed. >  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="71eb6-148">Ga eerst naar de pagina met domeinen bij Bluehost via [deze koppeling](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="71eb6-148">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="71eb6-149">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="71eb6-149">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="71eb6-150">Schakel op de **pagina domeinen** in het **domain_name-gebied** het selectievakje voor uw domein in en selecteer **vervolgens naamservers**.</span><span class="sxs-lookup"><span data-stu-id="71eb6-150">On the **domains** page, in the **domain_name** area, select the checkbox for your domain, and then select **name servers**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-1](../../media/8f384386-197c-4272-9675-82037922dac4.png)
  
3. <span data-ttu-id="71eb6-152">Selecteer aangepaste **naamservers gebruiken**in het **domain_name-gebied** .</span><span class="sxs-lookup"><span data-stu-id="71eb6-152">In the **domain_name** area, select **Use Custom Nameservers**.</span></span>
    
    ![Verbeterde animatiepaden](../../media/9fb47d21-c4ce-4eee-af90-c9569870a329.png)
  
4. <span data-ttu-id="71eb6-154">Afhankelijk van of er al naamservers worden vermeld op de pagina die wordt weergegeven, gaat u op een van de volgende twee manieren verder:</span><span class="sxs-lookup"><span data-stu-id="71eb6-154">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="71eb6-155">Als er nog **GEEN** naamservers worden vermeld, [Als er nog GEEN naamservers worden vermeld](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="71eb6-155">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="71eb6-156">Als er **WEL** naamservers worden vermeld, [Als er WEL naamservers worden vermeld](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="71eb6-156">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="71eb6-157">Als er nog GEEN naamservers worden vermeld</span><span class="sxs-lookup"><span data-stu-id="71eb6-157">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="71eb6-158">Typ of kopieer en plak in de sectie **Use Custom Nameservers** de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="71eb6-158">In the **Use Custom Nameservers** section, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="71eb6-159">**Eerste lege rij**</span><span class="sxs-lookup"><span data-stu-id="71eb6-159">**First empty row**</span></span> <br/> |<span data-ttu-id="71eb6-160">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="71eb6-160">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="71eb6-161">**Tweede lege rij**</span><span class="sxs-lookup"><span data-stu-id="71eb6-161">**Second empty row**</span></span> <br/> |<span data-ttu-id="71eb6-162">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="71eb6-162">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Afbeelding van het lint](../../media/07b13d6d-a34e-45b5-afd5-48ebd4c1344f.png)
  
2. <span data-ttu-id="71eb6-164">Selecteer **Rij toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="71eb6-164">Select **Add Row**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
3. <span data-ttu-id="71eb6-166">Terwijl u zich nog in de sectie **Use Custom Nameservers** bevindt, typt of kopieert en plakt u de waarden uit de eerste rij van de volgende tabel in de nieuwe, lege rij.</span><span class="sxs-lookup"><span data-stu-id="71eb6-166">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the first row of the following table into the new empty row.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="71eb6-167">**Derde lege rij**</span><span class="sxs-lookup"><span data-stu-id="71eb6-167">**Third empty row**</span></span> <br/> |<span data-ttu-id="71eb6-168">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="71eb6-168">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="71eb6-169">**Vierde lege rij**</span><span class="sxs-lookup"><span data-stu-id="71eb6-169">**Fourth empty row**</span></span> <br/> |<span data-ttu-id="71eb6-170">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="71eb6-170">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    ![Bluehost-BP-Redelegate-1-3-3](../../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
4. <span data-ttu-id="71eb6-171">Als u de vierde Nameserver-record wilt toevoegen, selecteert u Rij opnieuw **toevoegen** en maakt u een record met de waarden uit de laatste rij van de bovenstaande tabel.</span><span class="sxs-lookup"><span data-stu-id="71eb6-171">To add the fourth Nameserver record, select **Add Row** again, and create a record using the values from the last row of the above table.</span></span> 
    
5. <span data-ttu-id="71eb6-172">Selecteer **naamserverinstellingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="71eb6-172">Select **save nameserver settings**.</span></span>
    
    ![Theta](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> <span data-ttu-id="71eb6-174">Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd.</span><span class="sxs-lookup"><span data-stu-id="71eb6-174">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="71eb6-175">Vervolgens zijn uw Microsoft-e-mail en andere services helemaal klaar om met uw domein te werken.</span><span class="sxs-lookup"><span data-stu-id="71eb6-175">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="71eb6-176">Als er WEL naamservers worden vermeld</span><span class="sxs-lookup"><span data-stu-id="71eb6-176">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="71eb6-177">Volg deze stappen alleen als u bestaande naamservers hebt, andere dan de vier juiste naamservers.</span><span class="sxs-lookup"><span data-stu-id="71eb6-177">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="71eb6-178">(Dat wil zeggen, alleen huidige naamservers verwijderen die *geen* naam hebben **ns1.bdm.microsoftonline.com,** **ns2.bdm.microsoftonline.com,** **ns3.bdm.microsoftonline.com**of **ns4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="71eb6-178">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="71eb6-179">Als er andere naamservers worden vermeld, verwijdert u elke vermelding door deze te selecteren en vervolgens te drukken op de toets **Delete** op het toetsenbord.</span><span class="sxs-lookup"><span data-stu-id="71eb6-179">If there are any other name servers listed, delete each of them by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Bluehost-BP-Redelegate-1-5](../../media/d1051c43-f8ff-46d7-af26-3975d3f0f621.png)
  
2. <span data-ttu-id="71eb6-181">Terwijl u zich nog in de sectie **Use Custom Nameservers** bevindt, typt of kopieert en plakt u de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="71eb6-181">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="71eb6-182">**Eerste lege rij**</span><span class="sxs-lookup"><span data-stu-id="71eb6-182">**First empty row**</span></span> <br/> |<span data-ttu-id="71eb6-183">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="71eb6-183">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="71eb6-184">**Tweede lege rij**</span><span class="sxs-lookup"><span data-stu-id="71eb6-184">**Second empty row**</span></span> <br/> |<span data-ttu-id="71eb6-185">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="71eb6-185">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Afbeelding van het lint](../../media/1523debf-5eb0-4765-8e05-bcd56e375c20.png)
  
3. <span data-ttu-id="71eb6-187">Selecteer **Rij toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="71eb6-187">Select **Add Row**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
4. <span data-ttu-id="71eb6-189">Terwijl u zich nog in de sectie **Use Custom Nameservers** bevindt, typt of kopieert en plakt u de waarden uit de eerste rij van de volgende tabel in de nieuwe, lege rij.</span><span class="sxs-lookup"><span data-stu-id="71eb6-189">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the first row of the following table into the new empty row.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="71eb6-190">**Derde lege rij**</span><span class="sxs-lookup"><span data-stu-id="71eb6-190">**Third empty row**</span></span> <br/> |<span data-ttu-id="71eb6-191">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="71eb6-191">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="71eb6-192">**Vierde lege rij**</span><span class="sxs-lookup"><span data-stu-id="71eb6-192">**Fourth empty row**</span></span> <br/> |<span data-ttu-id="71eb6-193">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="71eb6-193">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Afbeelding van het lint](../../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
5. <span data-ttu-id="71eb6-195">Als u de vierde Nameserver-record wilt toevoegen, selecteert u Rij opnieuw **toevoegen** en maakt u een record met de waarden uit de laatste rij van de bovenstaande tabel.</span><span class="sxs-lookup"><span data-stu-id="71eb6-195">To add the fourth Nameserver record, select **Add Row** again, and create a record using the values from the last row of the above table.</span></span> 
    
6. <span data-ttu-id="71eb6-196">Selecteer **naamserverinstellingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="71eb6-196">Select **save nameserver settings**.</span></span>
    
    ![Theta](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> <span data-ttu-id="71eb6-198">Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd.</span><span class="sxs-lookup"><span data-stu-id="71eb6-198">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="71eb6-199">Vervolgens zijn uw Microsoft-e-mail en andere services helemaal klaar om met uw domein te werken.</span><span class="sxs-lookup"><span data-stu-id="71eb6-199">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
