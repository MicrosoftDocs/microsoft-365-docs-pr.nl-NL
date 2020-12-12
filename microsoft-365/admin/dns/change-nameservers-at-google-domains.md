---
title: Naamservers wijzigen voor het instellen van Microsoft met Google-domeinen
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
ms.assetid: 68a08e94-26c2-4df2-9216-026b8ec907ca
description: Meer informatie over hoe u Microsoft kunt instellen voor het beheren van de DNS-records van uw aangepaste domein bij Google domains.
ms.openlocfilehash: e475e222b6f1c9717008a49b172b0ecac5ec6fc7
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658438"
---
# <a name="change-nameservers-to-set-up-microsoft-with-google-domains"></a><span data-ttu-id="e29c5-103">Naamservers wijzigen voor het instellen van Microsoft met Google-domeinen</span><span class="sxs-lookup"><span data-stu-id="e29c5-103">Change nameservers to set up Microsoft with Google Domains</span></span>

 <span data-ttu-id="e29c5-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="e29c5-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="e29c5-105">Voer de volgende instructies uit als u wilt dat Microsoft uw DNS-records voor u beheert.</span><span class="sxs-lookup"><span data-stu-id="e29c5-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="e29c5-106">(Als u wilt, kunt u [al uw DNS-records bij Google domains beheren](create-dns-records-at-google-domains.md).)</span><span class="sxs-lookup"><span data-stu-id="e29c5-106">(If you prefer, you can [manage all your DNS records at Google Domains](create-dns-records-at-google-domains.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="e29c5-107">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="e29c5-107">Add a TXT record for verification</span></span>

<span data-ttu-id="e29c5-p102">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="e29c5-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="e29c5-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="e29c5-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="e29c5-112">Als u wilt beginnen, gaat u naar uw domeinen pagina bij Google domains via [deze koppeling](https://domains.google.com/registrar).</span><span class="sxs-lookup"><span data-stu-id="e29c5-112">To get started, go to your domains page at Google Domains via [this link](https://domains.google.com/registrar).</span></span> <span data-ttu-id="e29c5-113">U wordt gevraagd om u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="e29c5-113">You'll be prompted to sign in.</span></span> <span data-ttu-id="e29c5-114">U gaat hiervoor als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="e29c5-114">To do so:</span></span>
    
1. <span data-ttu-id="e29c5-115">Selecteer **Aanmelden**.</span><span class="sxs-lookup"><span data-stu-id="e29c5-115">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="e29c5-116">Voer uw aanmeldingsreferenties in en selecteer **Aanmelden**.</span><span class="sxs-lookup"><span data-stu-id="e29c5-116">Enter your login credentials and again select **Sign In**.</span></span>
    
2. <span data-ttu-id="e29c5-117">Selecteer op **de pagina** domains in de sectie **Domain** de optie **configure DNS** voor het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="e29c5-117">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="e29c5-118">Typ of kopieer en plak de waarden uit de volgende tabel in de sectie **Custom resource records** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="e29c5-118">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="e29c5-119">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="e29c5-119">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="e29c5-120">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="e29c5-120">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e29c5-121">**Name**</span><span class="sxs-lookup"><span data-stu-id="e29c5-121">**Name**</span></span> <br/> |<span data-ttu-id="e29c5-122">**Type**</span><span class="sxs-lookup"><span data-stu-id="e29c5-122">**Type**</span></span> <br/> |<span data-ttu-id="e29c5-123">**TTL**</span><span class="sxs-lookup"><span data-stu-id="e29c5-123">**TTL**</span></span> <br/> |<span data-ttu-id="e29c5-124">**Data**</span><span class="sxs-lookup"><span data-stu-id="e29c5-124">**Data**</span></span> <br/> |
|@  <br/> |<span data-ttu-id="e29c5-125">TXT</span><span class="sxs-lookup"><span data-stu-id="e29c5-125">TXT</span></span>  <br/> |<span data-ttu-id="e29c5-126">1U</span><span class="sxs-lookup"><span data-stu-id="e29c5-126">1H</span></span>  <br/> |<span data-ttu-id="e29c5-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="e29c5-127">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="e29c5-128">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="e29c5-128">**Note:** This is an example.</span></span> <span data-ttu-id="e29c5-129">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="e29c5-129">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="e29c5-130">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="e29c5-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)       <br/>  |
   
4. <span data-ttu-id="e29c5-131">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="e29c5-131">Select **Add**.</span></span>
    
5. <span data-ttu-id="e29c5-132">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="e29c5-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="e29c5-133">Nu u de record hebt toegevoegd aan de site van uw domeinregistratie, gaat u terug naar Microsoft en vraagt u naar de record.</span><span class="sxs-lookup"><span data-stu-id="e29c5-133">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="e29c5-134">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="e29c5-134">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="e29c5-135">Ga in het Microsoft-beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="e29c5-135">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="e29c5-136">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="e29c5-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="e29c5-137">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="e29c5-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="e29c5-138">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="e29c5-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e29c5-p106">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e29c5-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="e29c5-142">De naamserverrecords (NS-records) van uw domein wijzigen</span><span class="sxs-lookup"><span data-stu-id="e29c5-142">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="e29c5-143">Om het instellen van uw domein met Microsoft te voltooien, kunt u de NS-records van uw domein bij uw domeinregistratie wijzigen zodat deze verwijzen naar de primaire en secundaire naamservers van Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e29c5-143">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="e29c5-144">Hierdoor wordt Microsoft zodanig geconfigureerd dat de DNS-records van het domein voor u worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="e29c5-144">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="e29c5-145">We toevoegen alle records, zodat e-mail, Skype voor bedrijven online en uw openbare website met uw domein werken, en u bent klaar.</span><span class="sxs-lookup"><span data-stu-id="e29c5-145">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="e29c5-146">Als u de naamserver records van uw domein wijzigt zodat ze verwijzen naar de Microsoft-naamservers, worden dit van invloed op alle services die op dat moment zijn gekoppeld aan uw domein.</span><span class="sxs-lookup"><span data-stu-id="e29c5-146">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="e29c5-147">Alle e-mailberichten die naar uw domein zijn verzonden, zoals rob@ *your_domain.*</span><span class="sxs-lookup"><span data-stu-id="e29c5-147">For example, all email sent to your domain (like rob@ *your_domain.*</span></span>  <span data-ttu-id="e29c5-148">com) komt bij Microsoft binnen nadat u deze wijziging hebt aangebracht.</span><span class="sxs-lookup"><span data-stu-id="e29c5-148">com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="e29c5-p109">In de volgende procedure kunt u zien hoe u andere, ongewenste naamservers uit de lijst verwijdert en hoe u de juiste naamservers toevoegt als deze niet al in de lijst staan. > Na het voltooien van de stappen in deze sectie, moeten alleen de volgende vier naamservers in de lijst staan:</span><span class="sxs-lookup"><span data-stu-id="e29c5-p109">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list. > When you have completed the steps in this section, the only nameservers that should be listed are these four:</span></span> 
  
1. <span data-ttu-id="e29c5-p110">Ga eerst naar de pagina met domeinen bij Google Domains via [deze koppeling](https://domains.google.com/registrar). U wordt gevraagd om u aan te melden. U gaat hiervoor als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="e29c5-p110">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="e29c5-154">Selecteer **Aanmelden**.</span><span class="sxs-lookup"><span data-stu-id="e29c5-154">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="e29c5-155">Voer uw aanmeldingsreferenties in en selecteer vervolgens **Aanmelden**.</span><span class="sxs-lookup"><span data-stu-id="e29c5-155">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="e29c5-156">Selecteer op **de pagina** domains in de sectie **Domain** de optie **configure DNS** voor het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="e29c5-156">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="e29c5-157">Selecteer op de pagina **Domains** in de sectie **Name servers** de optie **Use custom name servers**.</span><span class="sxs-lookup"><span data-stu-id="e29c5-157">On the **Domains** page, in the **Name servers** section, select **Use custom name servers**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-1](../../media/e264bc05-5a56-4962-bcaf-e2d999f62278.png)
  
4. <span data-ttu-id="e29c5-159">Afhankelijk van of er al naamservers worden vermeld op de pagina die wordt weergegeven, gaat u op een van de volgende twee manieren verder:</span><span class="sxs-lookup"><span data-stu-id="e29c5-159">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="e29c5-160">Als er nog **GEEN** naamservers worden vermeld, [Als er nog GEEN naamservers worden vermeld](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="e29c5-160">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="e29c5-161">Als er **WEL** naamservers worden vermeld, [Als er WEL naamservers worden vermeld](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="e29c5-161">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="e29c5-162">Als er nog GEEN naamservers worden vermeld</span><span class="sxs-lookup"><span data-stu-id="e29c5-162">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="e29c5-163">Voeg de eerste naamserver toe.</span><span class="sxs-lookup"><span data-stu-id="e29c5-163">Add the first nameserver.</span></span>
    
    <span data-ttu-id="e29c5-164">In de sectie **Name servers** typt of kopieert en plakt u in het vak **NAME SERVER** de eerste waarde uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="e29c5-164">In the **Name servers** section, in the **NAME SERVER** box, type or copy and paste the first value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="e29c5-165">**First name server**</span><span class="sxs-lookup"><span data-stu-id="e29c5-165">**First name server**</span></span> <br/> |<span data-ttu-id="e29c5-166">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="e29c5-166">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="e29c5-167">**Second name server**</span><span class="sxs-lookup"><span data-stu-id="e29c5-167">**Second name server**</span></span> <br/> |<span data-ttu-id="e29c5-168">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="e29c5-168">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="e29c5-169">**Derde naamserver**</span><span class="sxs-lookup"><span data-stu-id="e29c5-169">**Third name server**</span></span> <br/> |<span data-ttu-id="e29c5-170">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="e29c5-170">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="e29c5-171">**Vierde naamserver**</span><span class="sxs-lookup"><span data-stu-id="e29c5-171">**Fourth name server**</span></span> <br/> |<span data-ttu-id="e29c5-172">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="e29c5-172">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Met Google-domeinen 1-2](../../media/6d14544d-7783-4ed4-b4dd-691624af7172.png)
  
2. <span data-ttu-id="e29c5-174">Selecteer het besturingselement **+ (toevoegen)** om een lege rij te maken.</span><span class="sxs-lookup"><span data-stu-id="e29c5-174">Select the **+ (add)** control to create an empty row.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-3](../../media/ea23e5fc-07e1-4ffc-b8cf-8526867b752d.png)
  
3. <span data-ttu-id="e29c5-176">De andere drie naamserverrecords toevoegen.</span><span class="sxs-lookup"><span data-stu-id="e29c5-176">Add the other three Nameserver records.</span></span>
    
    <span data-ttu-id="e29c5-177">Maak in de sectie **Custom name servers gebruiken** een record met behulp van de waarden uit de volgende rij in de tabel en selecteer vervolgens het besturingselement **+ (toevoegen)** om een nieuwe rij toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="e29c5-177">In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then select the **+ (add)** control to add another row.</span></span> 
    
    <span data-ttu-id="e29c5-178">Herhaal deze procedure totdat u alle vier de naamserverrecords hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="e29c5-178">Repeat this process until you have created all four Nameserver records.</span></span>
    
4. <span data-ttu-id="e29c5-179">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="e29c5-179">Select **Save**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> <span data-ttu-id="e29c5-181">Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd.</span><span class="sxs-lookup"><span data-stu-id="e29c5-181">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="e29c5-182">Vervolgens zijn uw Microsoft-e-mail en andere services allemaal ingesteld voor gebruik met uw domein.</span><span class="sxs-lookup"><span data-stu-id="e29c5-182">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="e29c5-183">Als er WEL naamservers worden vermeld</span><span class="sxs-lookup"><span data-stu-id="e29c5-183">If there ARE nameservers already listed</span></span>

1. <span data-ttu-id="e29c5-184">Als er andere naamservers worden vermeld, selecteert u **bewerken**.</span><span class="sxs-lookup"><span data-stu-id="e29c5-184">If there are any other nameservers listed, select **Edit**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="e29c5-185">Ga als volgt te werk als u een bestaande naamservers hebt dan de vier juiste naamservers.</span><span class="sxs-lookup"><span data-stu-id="e29c5-185">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="e29c5-186">(Dat wil zeggen dat u alleen huidige naamservers met de  *naam* **ns1.BDM.microsoftonline.com**, **ns2.BDM.microsoftonline.com**, **ns3.BDM.microsoftonline.com** of **ns4.BDM.microsoftonline.com**) verwijdert.</span><span class="sxs-lookup"><span data-stu-id="e29c5-186">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Google-Domains-BP-Redelegate-1-6-1](../../media/fb45d120-55ab-42c2-bdb6-19b130c3c7db.png)
  
2. <span data-ttu-id="e29c5-188">Verwijder vervolgens elk item door het te selecteren en op de toets **Delete** op het toetsenbord te drukken.</span><span class="sxs-lookup"><span data-stu-id="e29c5-188">Delete each one by selecting it, and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-6-2](../../media/524e64ad-56e6-4254-8a64-e4a4c3230f89.png)
  
3. <span data-ttu-id="e29c5-190">In de sectie **Name servers** typt of kopieert en plakt u de waarden uit de volgende tabel in de rijen **NAME SERVER**.</span><span class="sxs-lookup"><span data-stu-id="e29c5-190">Still in the **Name servers** section, in the **NAME SERVER** rows, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="e29c5-191">**First name server**</span><span class="sxs-lookup"><span data-stu-id="e29c5-191">**First name server**</span></span> <br/> |<span data-ttu-id="e29c5-192">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="e29c5-192">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="e29c5-193">**Second name server**</span><span class="sxs-lookup"><span data-stu-id="e29c5-193">**Second name server**</span></span> <br/> |<span data-ttu-id="e29c5-194">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="e29c5-194">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="e29c5-195">**Derde naamserver**</span><span class="sxs-lookup"><span data-stu-id="e29c5-195">**Third name server**</span></span> <br/> |<span data-ttu-id="e29c5-196">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="e29c5-196">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="e29c5-197">**Vierde naamserver**</span><span class="sxs-lookup"><span data-stu-id="e29c5-197">**Fourth name server**</span></span> <br/> |<span data-ttu-id="e29c5-198">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="e29c5-198">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Met Google-domeinen 1-7](../../media/e008dccb-d789-4f52-8ecc-02831b7c6fb2.png)
  
4. <span data-ttu-id="e29c5-200">Selecteer het besturingselement **+ (toevoegen)** om een lege rij te maken.</span><span class="sxs-lookup"><span data-stu-id="e29c5-200">Select the **+(add)** control to create an empty row.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-8](../../media/6ce40b1e-8464-443f-a64a-825dc8764590.png)
  
5. <span data-ttu-id="e29c5-202">Voer de andere twee naamserverrecords toe.</span><span class="sxs-lookup"><span data-stu-id="e29c5-202">Add the other two Nameserver records.</span></span>
    
    <span data-ttu-id="e29c5-203">Maak in de sectie **Custom name servers gebruiken** een record met behulp van de waarden uit de volgende rij in de tabel en selecteer vervolgens het besturingselement **+ (toevoegen)** om een nieuwe rij toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="e29c5-203">In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then select the **+(add)** control to add another row.</span></span> 
    
    <span data-ttu-id="e29c5-204">Herhaal deze procedure totdat u alle vier de naamserverrecords hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="e29c5-204">Repeat this process until you have created all four Nameserver records.</span></span>
    
6. <span data-ttu-id="e29c5-205">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="e29c5-205">Select **Save**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> <span data-ttu-id="e29c5-207">Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd.</span><span class="sxs-lookup"><span data-stu-id="e29c5-207">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="e29c5-208">Vervolgens zijn uw Microsoft-e-mail en andere services allemaal ingesteld voor gebruik met uw domein.</span><span class="sxs-lookup"><span data-stu-id="e29c5-208">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
