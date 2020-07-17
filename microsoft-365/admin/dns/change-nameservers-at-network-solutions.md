---
title: Naamservers wijzigen om Microsoft in te stellen met Network Solutions
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: d4ba60f3-4e1c-4180-99bd-250b8955be2a
description: 'Meer informatie over het instellen van uw Microsoft-aangepaste domein met Network Solutions als u wilt dat Microsoft uw DNS-records beheert. '
ms.openlocfilehash: 502699cf3760460a13ee067b07737037f31fa4ee
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/08/2020
ms.locfileid: "45079875"
---
# <a name="change-nameservers-to-set-up-microsoft-with-network-solutions"></a><span data-ttu-id="15058-103">Naamservers wijzigen om Microsoft in te stellen met Network Solutions</span><span class="sxs-lookup"><span data-stu-id="15058-103">Change nameservers to set up Microsoft with Network Solutions</span></span>

 <span data-ttu-id="15058-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="15058-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="15058-105">Volg deze instructies als u wilt dat Microsoft uw DNS-records voor u beheert.</span><span class="sxs-lookup"><span data-stu-id="15058-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="15058-106">(Als u dat liever hebt, u [al uw DNS-records van Microsoft beheren bij Network Solutions](create-dns-records-at-network-solutions.md).)</span><span class="sxs-lookup"><span data-stu-id="15058-106">(If you prefer, you can [manage all your Microsoft DNS records at Network Solutions](create-dns-records-at-network-solutions.md).)</span></span>
  
    
## <a name="add-a-txt-record-at-network-solutions-to-verify-that-you-own-the-domain"></a><span data-ttu-id="15058-107">Een TXT-record toevoegen op Network Solutions om te bevestigen dat u eigenaar van het domein bent</span><span class="sxs-lookup"><span data-stu-id="15058-107">Add a TXT record at Network Solutions to verify that you own the domain</span></span>

<span data-ttu-id="15058-p102">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="15058-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="15058-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="15058-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="15058-112">Volg onderstaande stappen of [bekijk de video (start op 0:47)](https://support.microsoft.com/office/69b092e3-c026-4d19-a7d0-16cdb2d8b261).</span><span class="sxs-lookup"><span data-stu-id="15058-112">Follow the steps below or [watch the video (start at 0:47)](https://support.microsoft.com/office/69b092e3-c026-4d19-a7d0-16cdb2d8b261).</span></span>
  
1. <span data-ttu-id="15058-p104">Als u wilt beginnen, gaat u [via deze koppeling](https://www.networksolutions.com/manage-it) naar uw pagina met domeinen bij Network Solutions. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="15058-p104">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="15058-115">Voordat u de **knop Aanmelden** selecteert, kiest u Eerst **Mijn domeinnamen beheren** in de vervolgkeuzelijst Aanmelden **bij:**</span><span class="sxs-lookup"><span data-stu-id="15058-115">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span>
  
    ![Mijn domeinnamen beheren kiezen en aanmelden bij Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="15058-117">Schakel het selectievakje in naast de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="15058-117">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Het selectievakje voor uw domein selecteren](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="15058-119">Selecteer **DNS bewerken**.</span><span class="sxs-lookup"><span data-stu-id="15058-119">Select **Edit DNS**.</span></span>
    
    ![DNS bewerken selecteren](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="15058-121">Selecteer **Geavanceerde DNS-records beheren**.</span><span class="sxs-lookup"><span data-stu-id="15058-121">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="15058-122">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="15058-122">(You may have to scroll down.)</span></span>
    
    ![Selecteer Geavanceerde DNS-records beheren](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="15058-124">Schuif omlaag naar de sectie **Tekst (TXT Records)** en selecteer **TXT-records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="15058-124">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![TXT-records bewerken selecteren](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="15058-126">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="15058-126">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
|<span data-ttu-id="15058-127">**Host**</span><span class="sxs-lookup"><span data-stu-id="15058-127">**Host**</span></span>|<span data-ttu-id="15058-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="15058-128">**TTL**</span></span>|<span data-ttu-id="15058-129">**Tekst**</span><span class="sxs-lookup"><span data-stu-id="15058-129">**Text**</span></span>|
|:-----|:-----|:-----|
|@  <br/> <span data-ttu-id="15058-130">(In het systeem wordt deze waarde gewijzigd in **@ (None)** wanneer u de record opslaat.)</span><span class="sxs-lookup"><span data-stu-id="15058-130">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="15058-131">3600</span><span class="sxs-lookup"><span data-stu-id="15058-131">3600</span></span>  <br/> |<span data-ttu-id="15058-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="15058-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="15058-133">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="15058-133">**Note**: This is an example.</span></span> <span data-ttu-id="15058-134">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="15058-134">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="15058-135">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="15058-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)
   
    
   ![Waarden typen of plakken in de vakken voor de nieuwe record](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="15058-137">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="15058-137">Select **Continue**.</span></span>
    
    ![Selecteer Doorgaan](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="15058-139">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="15058-139">Select **Save Changes**.</span></span>
    
    ![Wijzigingen opslaan selecteren](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="15058-141">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="15058-141">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="15058-142">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft 365 en vraagt u of Microsoft 365 naar de record wil zoeken.</span><span class="sxs-lookup"><span data-stu-id="15058-142">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="15058-143">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="15058-143">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="15058-144">Ga in het Microsoft-beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="15058-144">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="15058-145">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="15058-145">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="15058-146">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="15058-146">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="15058-147">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="15058-147">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="15058-p106">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="15058-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="15058-151">De naamserverrecords (NS-records) van uw domein wijzigen</span><span class="sxs-lookup"><span data-stu-id="15058-151">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="15058-152">Als u het instellen van uw domein met Microsoft wilt voltooien, wijzigt u de NS-records van uw domein bij uw domeinregistrar om naar de primaire en secundaire naamservers van Microsoft te wijzen.</span><span class="sxs-lookup"><span data-stu-id="15058-152">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="15058-153">Hiermee wordt Microsoft ingesteld om de DNS-records van het domein voor u bij te werken.</span><span class="sxs-lookup"><span data-stu-id="15058-153">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="15058-154">We voegen alle records toe, zodat e-mail, Skype voor Bedrijven Online en uw openbare website met uw domein werken en u helemaal klaar bent.</span><span class="sxs-lookup"><span data-stu-id="15058-154">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="15058-155">Wanneer u de NS-records van uw domein wijzigt om naar de Microsoft-naamservers te wijzen, worden alle services beïnvloed die momenteel aan uw domein zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="15058-155">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="15058-156">Alle e-mail die naar uw domein wordt verzonden (zoals rob@ *your_domain* .com) komt bijvoorbeeld naar Microsoft nadat u deze wijziging hebt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="15058-156">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span>
  
<span data-ttu-id="15058-157">Klaar om uw NS-records te wijzigen, zodat Microsoft uw domein kan instellen?</span><span class="sxs-lookup"><span data-stu-id="15058-157">Ready to change your NS records so Microsoft can set up your domain?</span></span> <span data-ttu-id="15058-158">Volg onderstaande stappen of [bekijk de video (start bij 2:23)](https://support.microsoft.com/office/69b092e3-c026-4d19-a7d0-16cdb2d8b261).</span><span class="sxs-lookup"><span data-stu-id="15058-158">Follow the steps below or [watch the video (start at 2:23)](https://support.microsoft.com/office/69b092e3-c026-4d19-a7d0-16cdb2d8b261).</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="15058-159">Wanneer u de stappen in deze sectie hebt voltooid, zijn de *enige* naamservers die moeten worden vermeld, deze vier: **ns1.bdm.microsoftonline.com,** **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**en **ns4.bdm.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="15058-159">When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**.</span></span> <span data-ttu-id="15058-160">In de volgende procedure kunt u zien hoe u andere, ongewenste naamservers uit de lijst verwijdert en hoe u de  *juiste*  naamservers toevoegt als deze niet al in de lijst staan.</span><span class="sxs-lookup"><span data-stu-id="15058-160">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.</span></span> 
  
1. <span data-ttu-id="15058-161">Als u wilt beginnen, gaat u [via deze koppeling](https://www.networksolutions.com/manage-it) naar uw pagina met domeinen bij Network Solutions.</span><span class="sxs-lookup"><span data-stu-id="15058-161">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="15058-162">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="15058-162">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="15058-163">Voordat u de **knop Aanmelden** selecteert, kiest u Eerst **Mijn domeinnamen beheren** in de vervolgkeuzelijst Aanmelden **bij:**</span><span class="sxs-lookup"><span data-stu-id="15058-163">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Mijn domeinnamen beheren kiezen en aanmelden bij Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="15058-165">Schakel het selectievakje in naast de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="15058-165">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Het selectievakje voor uw domein selecteren](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="15058-167">Selecteer **DNS bewerken**.</span><span class="sxs-lookup"><span data-stu-id="15058-167">Select **Edit DNS**.</span></span>
    
    ![DNS bewerken selecteren](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="15058-169">Selecteer **DNS verplaatsen**.</span><span class="sxs-lookup"><span data-stu-id="15058-169">Select **Move DNS**.</span></span>
    
    ![NetworkSolutionsBP-Redelegate-1-1](../../media/e57a30f3-63d5-4bcb-84c6-c8be21c261a2.png)
  
5. <span data-ttu-id="15058-171">Afhankelijk van of er al naamservers worden vermeld op de pagina die wordt weergegeven, gaat u op een van de volgende twee manieren verder:</span><span class="sxs-lookup"><span data-stu-id="15058-171">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="15058-172">Als er nog **GEEN** naamservers worden vermeld, [Als er nog GEEN naamservers worden vermeld](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="15058-172">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="15058-173">Als er **WEL** naamservers worden vermeld, [Als er WEL naamservers worden vermeld](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="15058-173">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="15058-174">Als er nog GEEN naamservers worden vermeld</span><span class="sxs-lookup"><span data-stu-id="15058-174">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="15058-175">Selecteer op de pagina **Domeinen** in de sectie **Domeinnaamservers opgeven** de optie Meer **naamservers toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="15058-175">On the **Domains** page, in the **Specify Domain Name Servers** section, select **Add More Name Servers**.</span></span>
    
    ![NetworkSolutionsBP-Redelegate-1-2-1](../../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
2. <span data-ttu-id="15058-177">Typ of kopieer en plak de naamserverwaarden uit de volgende tabel naar de pagina **Domain Names**.</span><span class="sxs-lookup"><span data-stu-id="15058-177">On the **Domain Names** page, type or copy and paste the nameserver values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="15058-178">**Name Server 1**</span><span class="sxs-lookup"><span data-stu-id="15058-178">**Name Server 1**</span></span> <br/> |<span data-ttu-id="15058-179">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="15058-179">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="15058-180">**Name Server 2**</span><span class="sxs-lookup"><span data-stu-id="15058-180">**Name Server 2**</span></span> <br/> |<span data-ttu-id="15058-181">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="15058-181">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="15058-182">**Name Server 2**</span><span class="sxs-lookup"><span data-stu-id="15058-182">**Name Server 2**</span></span> <br/> |<span data-ttu-id="15058-183">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="15058-183">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="15058-184">**Name Server 2**</span><span class="sxs-lookup"><span data-stu-id="15058-184">**Name Server 2**</span></span> <br/> |<span data-ttu-id="15058-185">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="15058-185">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    
![NetworkSolutionsBP-Redelegate-1-2-2](../../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
3. <span data-ttu-id="15058-187">Selecteer **DNS verplaatsen**.</span><span class="sxs-lookup"><span data-stu-id="15058-187">Select **Move DNS**.</span></span>
    
    ![NetworkSolutionsBP-Redelegate-1-2-3](../../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
4. <span data-ttu-id="15058-189">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="15058-189">Select **Save Changes**.</span></span>
    
    ![NetworkSolutionsBP-Redelegate-1-2-4](../../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> <span data-ttu-id="15058-191">Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd.</span><span class="sxs-lookup"><span data-stu-id="15058-191">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="15058-192">Vervolgens zijn uw Microsoft-e-mail en andere services helemaal klaar om met uw domein te werken.</span><span class="sxs-lookup"><span data-stu-id="15058-192">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="15058-193">Als er WEL naamservers worden vermeld</span><span class="sxs-lookup"><span data-stu-id="15058-193">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="15058-p113">Voer deze stappen  *alleen*  uit als u andere bestaande naamservers hebt dan de vier  *juiste*  naamservers. (Dat wil zeggen, verwijder  *alleen*  huidige naamservers die een  *andere*  naam hebben dan **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** of **ns4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="15058-p113">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span>
  
1. <span data-ttu-id="15058-196">Als er andere naamservers worden vermeld, verwijdert u elke vermelding door deze te selecteren en vervolgens te drukken op de toets **Delete** op het toetsenbord.</span><span class="sxs-lookup"><span data-stu-id="15058-196">If there are any other nameservers listed, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span>
    
    ![Afbeelding van het aandeel NetworkSolutions-BP-Redelegate-1-5](../../media/eeb8ad22-bf4a-43a8-b97a-f09c3654d89b.png)
  
2. <span data-ttu-id="15058-198">Selecteer **Meer naamservers toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="15058-198">Select **Add More Name Servers**.</span></span>
    
    ![NetworkSolutionsBP-Redelegate-1-2-1](../../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
3. <span data-ttu-id="15058-200">Typ of kopieer en plak de naamserverwaarden uit de volgende tabel naar de pagina **Domain Names**.</span><span class="sxs-lookup"><span data-stu-id="15058-200">On the **Domain Names** page, type or copy and paste the nameserver values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="15058-201">**Name Server 1**</span><span class="sxs-lookup"><span data-stu-id="15058-201">**Name Server 1**</span></span> <br/> |<span data-ttu-id="15058-202">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="15058-202">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="15058-203">**Name Server 2**</span><span class="sxs-lookup"><span data-stu-id="15058-203">**Name Server 2**</span></span> <br/> |<span data-ttu-id="15058-204">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="15058-204">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="15058-205">**Name Server 3**</span><span class="sxs-lookup"><span data-stu-id="15058-205">**Name Server 3**</span></span> <br/> |<span data-ttu-id="15058-206">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="15058-206">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="15058-207">**Name Server 4**</span><span class="sxs-lookup"><span data-stu-id="15058-207">**Name Server 4**</span></span> <br/> |<span data-ttu-id="15058-208">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="15058-208">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    
![NetworkSolutionsBP-Redelegate-1-2-2](../../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
4. <span data-ttu-id="15058-210">Selecteer **DNS verplaatsen**.</span><span class="sxs-lookup"><span data-stu-id="15058-210">Select **Move DNS**.</span></span>
    
    ![NetworkSolutionsBP-Redelegate-1-2-3](../../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
5. <span data-ttu-id="15058-212">Selecteer **Wijzigingen opslaan.**</span><span class="sxs-lookup"><span data-stu-id="15058-212">Select **Save Changes.**</span></span>
    
    ![NetworkSolutionsBP-Redelegate-1-2-4](../../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> <span data-ttu-id="15058-214">Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd.</span><span class="sxs-lookup"><span data-stu-id="15058-214">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="15058-215">Vervolgens zijn uw Microsoft-e-mail en andere services helemaal klaar om met uw domein te werken.</span><span class="sxs-lookup"><span data-stu-id="15058-215">Then your Microsoft email and other services will be all set to work with your domain.</span></span>
