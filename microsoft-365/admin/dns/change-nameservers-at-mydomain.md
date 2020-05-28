---
title: Naamservers wijzigen om Microsoft in te stellen met MyDomain
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
ms.assetid: c5f6140a-4a12-401b-9bbd-7dfb0d6b0ba3
description: Meer informatie over hoe u Microsoft instellen voor het beheren van de DNS-records van uw aangepaste domein op MyDomain.
ms.openlocfilehash: d8fc61c3adbe8b5b865bd82b8c4e0944198921e7
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400627"
---
# <a name="change-nameservers-to-set-up-microsoft-with-mydomain"></a><span data-ttu-id="7e6d9-103">Naamservers wijzigen om Microsoft in te stellen met MyDomain</span><span class="sxs-lookup"><span data-stu-id="7e6d9-103">Change nameservers to set up Microsoft with MyDomain</span></span>

 <span data-ttu-id="7e6d9-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="7e6d9-105">Volg deze instructies als u wilt dat Microsoft uw DNS-records voor u beheert.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="7e6d9-106">(Als u dat liever hebt, u [al uw Microsoft DNS-records beheren bij MyDomain](create-dns-records-at-mydomain.md).)</span><span class="sxs-lookup"><span data-stu-id="7e6d9-106">(If you prefer, you can [manage all your Microsoft DNS records at MyDomain](create-dns-records-at-mydomain.md).)</span></span>
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="7e6d9-107">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="7e6d9-107">Add a TXT record for verification</span></span>

<span data-ttu-id="7e6d9-p102">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7e6d9-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="7e6d9-p104">Ga eerst naar de pagina met domeinen bij MyDomain via [deze koppeling](https://www.mydomain.com/controlpanel). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-p104">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="7e6d9-114">Kies in de sectie **Mijn favorieten** de optie **Domain Central**.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-114">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="7e6d9-115">Kies onder **Domein** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-115">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="7e6d9-116">Kies in de rij **Overzicht** de optie **DNS**.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-116">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="7e6d9-117">Kies in de vervolgkeuzelijst **Wijzigen** de optie **TXT/SPF-record**.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-117">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="7e6d9-118">Typ of kopieer en plak de waarden uit de volgende tabel in het vak voor de nieuwe record onder **Content**.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-118">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
||
|:-----|
|<span data-ttu-id="7e6d9-119">**Content**</span><span class="sxs-lookup"><span data-stu-id="7e6d9-119">**Content**</span></span> <br/> |
|<span data-ttu-id="7e6d9-120">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="7e6d9-120">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="7e6d9-121">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-121">**Note**: This is an example.</span></span> <span data-ttu-id="7e6d9-122">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-122">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="7e6d9-123">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="7e6d9-123">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="7e6d9-124">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-124">Select **Add**.</span></span>
    
8. <span data-ttu-id="7e6d9-125">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-125">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="7e6d9-126">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft 365 en vraagt u of Microsoft 365 naar de record wil zoeken.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-126">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="7e6d9-127">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-127">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="7e6d9-128">Ga in het Microsoft-beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-128">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="7e6d9-129">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-129">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="7e6d9-130">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-130">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="7e6d9-131">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-131">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7e6d9-p106">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7e6d9-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="7e6d9-135">De naamserverrecords (NS-records) van uw domein wijzigen</span><span class="sxs-lookup"><span data-stu-id="7e6d9-135">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="7e6d9-136">Als u het instellen van uw domein met Microsoft wilt voltooien, wijzigt u de NS-records van uw domein bij uw domeinregistrar om naar de primaire en secundaire naamservers van Microsoft te wijzen.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-136">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="7e6d9-137">Hiermee wordt Microsoft ingesteld om de DNS-records van het domein voor u bij te werken.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-137">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="7e6d9-138">We voegen alle records toe zodat e-mail, Skype voor Bedrijven Online en uw openbare website met uw domein werken en u helemaal klaar bent.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-138">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="7e6d9-139">Wanneer u de NS-records van uw domein wijzigt om naar de Microsoft-naamservers te wijzen, worden alle services die momenteel aan uw domein zijn gekoppeld, beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-139">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="7e6d9-140">Bijvoorbeeld alle e-mail die naar uw domein wordt verzonden (zoals rob@ *your_domain.*</span><span class="sxs-lookup"><span data-stu-id="7e6d9-140">For example, all email sent to your domain (like rob@ *your_domain.*</span></span> <span data-ttu-id="7e6d9-141">com) zal beginnen te komen naar Microsoft nadat u deze wijziging.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-141">com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="7e6d9-p109">In de volgende procedure kunt u zien hoe u andere, ongewenste naamservers uit de lijst verwijdert en hoe u de juiste naamservers toevoegt als deze niet al in de lijst staan.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-p109">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list. </span></span><br/> <span data-ttu-id="7e6d9-143">Wanneer u de stappen in deze sectie hebt voltooid, zijn de enige nameservers die moeten worden vermeld:</span><span class="sxs-lookup"><span data-stu-id="7e6d9-143">When you have completed the steps in this section, the only nameservers that should be listed are these four:</span></span>
  
1. <span data-ttu-id="7e6d9-p110">Ga eerst naar de pagina met domeinen bij MyDomain via [deze koppeling](https://www.mydomain.com/controlpanel). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-p110">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="7e6d9-146">Kies in de sectie **Mijn favorieten** de optie **Domain Central**.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-146">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="7e6d9-147">Kies onder **Domein** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-147">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="7e6d9-148">Selecteer **naamservers**in de rij **Overzicht** .</span><span class="sxs-lookup"><span data-stu-id="7e6d9-148">In the **Overview** row, select **Nameservers**.</span></span>
    
    ![Afbeelding van het lint](../../media/49e91235-44b5-46d6-a82e-8f11329db3d6.png)
  
5. <span data-ttu-id="7e6d9-150">Selecteer in de sectie **Update Name Servers** de optie **Use different name servers**.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-150">In the **Update Name Servers** section, select **Use different name servers**.</span></span>
    
    ![Afbeelding van het lint](../../media/f869fb26-54dc-4b66-8378-a78a79b582bd.png)
  
6. <span data-ttu-id="7e6d9-152">Afhankelijk van het feit of er al nameservers op de pagina staan die nu wordt weergegeven, gaat u verder met een van de twee volgende procedures.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-152">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures.</span></span>
    
### <a name="if-the-correct-nameservers-are-already-listed"></a><span data-ttu-id="7e6d9-153">Als de correcte naamservers WEL worden vermeld</span><span class="sxs-lookup"><span data-stu-id="7e6d9-153">If the correct nameservers ARE already listed</span></span>

- <span data-ttu-id="7e6d9-154">Als de correcte naamservers al worden vermeld, kunt u deze stap overslaan.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-154">If the correct nameservers are already listed, you can skip this step.</span></span>
    
    ![Afbeelding van het lint](../../media/601f6a46-15bd-4a92-b792-ac628ff86628.png)
  
### <a name="if-the-correct-nameservers-are-not-already-listed"></a><span data-ttu-id="7e6d9-156">Als de correcte naamservers NIET worden vermeld</span><span class="sxs-lookup"><span data-stu-id="7e6d9-156">If the correct nameservers are NOT already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="7e6d9-157">Volg deze stappen alleen als u bestaande naamservers hebt, andere dan de vier juiste naamservers.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-157">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="7e6d9-158">(Dat wil zeggen, alleen huidige naamservers verwijderen die *geen* naam hebben **ns1.bdm.microsoftonline.com,** **ns2.bdm.microsoftonline.com,** **ns3.bdm.microsoftonline.com**of **ns4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="7e6d9-158">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="7e6d9-159">Verwijder de bestaande naamservers door elke vermelding te selecteren in het veld **Nameserver 1:** en vervolgens op de toets **Delete** op het toetsenbord te drukken.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-159">Delete the existing nameservers by selecting each entry in the **Nameserver:** field, and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Afbeelding van het lint](../../media/5024cd27-a2b1-42a2-99e4-5ceb5e6eddb9.png)
  
2. <span data-ttu-id="7e6d9-161">Selecteer Twee maal **meer toevoegen** om twee nieuwe naamserverrijen toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-161">Select **Add More** twice to add two new Nameserver rows.</span></span> 
    
    ![Afbeelding van het lint](../../media/19307893-2f73-4e4d-9221-a5870e09ab48.png)
  
3. <span data-ttu-id="7e6d9-163">Typ of kopieer en plak de naamserverwaarden uit de volgende tabel in de vakken voor de records.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-163">In the boxes for the records, type or copy and paste the nameserver values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="7e6d9-164">**Nameserver 1**</span><span class="sxs-lookup"><span data-stu-id="7e6d9-164">**Nameserver 1**</span></span> <br/> |<span data-ttu-id="7e6d9-165">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="7e6d9-165">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="7e6d9-166">**Nameserver 2**</span><span class="sxs-lookup"><span data-stu-id="7e6d9-166">**Nameserver 2**</span></span> <br/> |<span data-ttu-id="7e6d9-167">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="7e6d9-167">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="7e6d9-168">**Nameserver 3**</span><span class="sxs-lookup"><span data-stu-id="7e6d9-168">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="7e6d9-169">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="7e6d9-169">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="7e6d9-170">**Nameserver 4**</span><span class="sxs-lookup"><span data-stu-id="7e6d9-170">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="7e6d9-171">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="7e6d9-171">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Afbeelding van het lint](../../media/7427e99c-49c7-4a2e-a5bf-66fc46900cd1.png)
  
4. <span data-ttu-id="7e6d9-173">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-173">Select **Save**.</span></span>
    
    ![Afbeelding van het lint](../../media/48473816-b881-47f0-9344-74622efa3bf8.png)
  
> [!NOTE]
> <span data-ttu-id="7e6d9-175">Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-175">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="7e6d9-176">Vervolgens zijn uw Microsoft-e-mail en andere services helemaal klaar om met uw domein te werken.</span><span class="sxs-lookup"><span data-stu-id="7e6d9-176">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
