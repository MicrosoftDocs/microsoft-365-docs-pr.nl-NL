---
title: Naamservers wijzigen voor het instellen van Office 365 met Google-domeinen
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
ms.assetid: 68a08e94-26c2-4df2-9216-026b8ec907ca
description: Meer informatie over hoe u Office 365 instellen voor het beheren van de DNS-records van uw aangepaste domein op Google Domains.
ms.openlocfilehash: f6faaa4a7b6540086752e88da2051a73450f4455
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "42810497"
---
# <a name="change-nameservers-to-set-up-office-365-with-google-domains"></a><span data-ttu-id="11106-103">Naamservers wijzigen voor het instellen van Office 365 met Google-domeinen</span><span class="sxs-lookup"><span data-stu-id="11106-103">Change nameservers to set up Office 365 with Google Domains</span></span>

 <span data-ttu-id="11106-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="11106-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="11106-p101">Volg deze instructies als u wilt dat Office 365 uw DNS-records voor Office 365 voor u beheert. (Als u wilt, kunt u [al uw DNS-records voor Office 365 bij Google Domains beheren](create-dns-records-at-google-domains.md).)</span><span class="sxs-lookup"><span data-stu-id="11106-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Google Domains](create-dns-records-at-google-domains.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="11106-107">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="11106-107">Add a TXT record for verification</span></span>

<span data-ttu-id="11106-p102">Voordat u uw domein met Office 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Office 365 bewezen.</span><span class="sxs-lookup"><span data-stu-id="11106-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="11106-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="11106-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="11106-112">Om aan de slag te gaan, ga je naar je domeinenpagina bij Google Domains via [deze link.](https://domains.google.com/registrar)</span><span class="sxs-lookup"><span data-stu-id="11106-112">To get started, go to your domains page at Google Domains via [this link](https://domains.google.com/registrar).</span></span> <span data-ttu-id="11106-113">U wordt gevraagd om u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="11106-113">You'll be prompted to sign in.</span></span> <span data-ttu-id="11106-114">U gaat hiervoor als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="11106-114">To do so:</span></span>
    
1. <span data-ttu-id="11106-115">Selecteer **Aanmelden**.</span><span class="sxs-lookup"><span data-stu-id="11106-115">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="11106-116">Voer uw inloggegevens **in**en selecteer Opnieuw Aanmelden .</span><span class="sxs-lookup"><span data-stu-id="11106-116">Enter your login credentials and again select **Sign In**.</span></span>
    
2. <span data-ttu-id="11106-117">Selecteer **op** de pagina Domeinen in de sectie **Domein** de optie **DNS configureren** voor het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="11106-117">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="11106-118">Typ of kopieer en plak de waarden uit de volgende tabel in de sectie **Custom resource records** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="11106-118">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="11106-119">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="11106-119">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="11106-120">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="11106-120">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="11106-121">**Name**</span><span class="sxs-lookup"><span data-stu-id="11106-121">**Name**</span></span> <br/> |<span data-ttu-id="11106-122">**Type**</span><span class="sxs-lookup"><span data-stu-id="11106-122">**Type**</span></span> <br/> |<span data-ttu-id="11106-123">**TTL**</span><span class="sxs-lookup"><span data-stu-id="11106-123">**TTL**</span></span> <br/> |<span data-ttu-id="11106-124">**Data**</span><span class="sxs-lookup"><span data-stu-id="11106-124">**Data**</span></span> <br/> |
|@  <br/> |<span data-ttu-id="11106-125">TXT</span><span class="sxs-lookup"><span data-stu-id="11106-125">TXT</span></span>  <br/> |<span data-ttu-id="11106-126">1H</span><span class="sxs-lookup"><span data-stu-id="11106-126">1H</span></span>  <br/> |<span data-ttu-id="11106-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="11106-127">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="11106-128">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="11106-128">**Note:** This is an example.</span></span> <span data-ttu-id="11106-129">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365.</span><span class="sxs-lookup"><span data-stu-id="11106-129">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="11106-130">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="11106-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)       <br/>  |
   
4. <span data-ttu-id="11106-131">Selecteer **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="11106-131">Select **Add**.</span></span>
    
5. <span data-ttu-id="11106-132">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="11106-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="11106-133">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Office 365 en vraagt u of Office 365 naar de record wil zoeken.</span><span class="sxs-lookup"><span data-stu-id="11106-133">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="11106-134">Wanneer in Office 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="11106-134">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="11106-135">Ga in het beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Instellingendomeinen.</a> **Settings**</span><span class="sxs-lookup"><span data-stu-id="11106-135">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="11106-136">Selecteer **op** de pagina Domeinen het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="11106-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="11106-137">Selecteer **op** de pagina Setup de optie **Installatie starten**.</span><span class="sxs-lookup"><span data-stu-id="11106-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="11106-138">Selecteer **op** de pagina Domein verifiëren de optie **Verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="11106-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="11106-p106">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="11106-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="11106-142">De naamserverrecords (NS-records) van uw domein wijzigen</span><span class="sxs-lookup"><span data-stu-id="11106-142">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="11106-p107">U voltooit het instellen van uw domein met Office 365 door de NS-records van uw domein bij uw domeinregistrar te wijzigen, zodat deze verwijzen naar de primaire en secundaire naamservers van Office 365. Hiermee wordt Office 365 zo ingesteld dat de DNS-records van het domein voor u worden bijgewerkt. Alle benodigde records worden toegevoegd zodat e-mail, Skype voor Bedrijven Online en uw openbare website met uw domein kunnen werken. Daarna bent u klaar.</span><span class="sxs-lookup"><span data-stu-id="11106-p107">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="11106-146">Als u de NS-records van uw domein laat verwijzen naar de naamservers van Office 365, is dit van invloed op alle services die momenteel aan uw domein zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="11106-146">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="11106-147">Bijvoorbeeld alle e-mail die naar uw domein wordt verzonden (zoals rob@ *your_domain.*</span><span class="sxs-lookup"><span data-stu-id="11106-147">For example, all email sent to your domain (like rob@ *your_domain.*</span></span>  <span data-ttu-id="11106-148">com) naar Office 365 komen nadat u deze wijziging hebt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="11106-148">com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="11106-p109">In de volgende procedure kunt u zien hoe u andere, ongewenste naamservers uit de lijst verwijdert en hoe u de juiste naamservers toevoegt als deze niet al in de lijst staan. > Na het voltooien van de stappen in deze sectie, moeten alleen de volgende vier naamservers in de lijst staan:</span><span class="sxs-lookup"><span data-stu-id="11106-p109">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list. > When you have completed the steps in this section, the only nameservers that should be listed are these four:</span></span> 
  
1. <span data-ttu-id="11106-p110">Ga eerst naar de pagina met domeinen bij Google Domains via [deze koppeling](https://domains.google.com/registrar). U wordt gevraagd om u aan te melden. U gaat hiervoor als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="11106-p110">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="11106-154">Selecteer **Aanmelden**.</span><span class="sxs-lookup"><span data-stu-id="11106-154">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="11106-155">Voer uw inloggegevens in en selecteer **Opnieuw Aanmelden**.</span><span class="sxs-lookup"><span data-stu-id="11106-155">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="11106-156">Selecteer **op** de pagina Domeinen in de sectie **Domein** de optie **DNS configureren** voor het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="11106-156">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="11106-157">Selecteer op de pagina **Domains** in de sectie **Name servers** de optie **Use custom name servers**.</span><span class="sxs-lookup"><span data-stu-id="11106-157">On the **Domains** page, in the **Name servers** section, select **Use custom name servers**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-1](../../media/e264bc05-5a56-4962-bcaf-e2d999f62278.png)
  
4. <span data-ttu-id="11106-159">Afhankelijk van of er al naamservers worden vermeld op de pagina die wordt weergegeven, gaat u op een van de volgende twee manieren verder:</span><span class="sxs-lookup"><span data-stu-id="11106-159">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="11106-160">Als er nog **GEEN** naamservers worden vermeld, [Als er nog GEEN naamservers worden vermeld](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="11106-160">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="11106-161">Als er **WEL** naamservers worden vermeld, [Als er WEL naamservers worden vermeld](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="11106-161">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="11106-162">Als er nog GEEN naamservers worden vermeld</span><span class="sxs-lookup"><span data-stu-id="11106-162">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="11106-163">Voeg de eerste naamserver toe.</span><span class="sxs-lookup"><span data-stu-id="11106-163">Add the first nameserver.</span></span>
    
    <span data-ttu-id="11106-164">In de sectie **Name servers** typt of kopieert en plakt u in het vak **NAME SERVER** de eerste waarde uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="11106-164">In the **Name servers** section, in the **NAME SERVER** box, type or copy and paste the first value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="11106-165">**First name server**</span><span class="sxs-lookup"><span data-stu-id="11106-165">**First name server**</span></span> <br/> |<span data-ttu-id="11106-166">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="11106-166">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="11106-167">**Second name server**</span><span class="sxs-lookup"><span data-stu-id="11106-167">**Second name server**</span></span> <br/> |<span data-ttu-id="11106-168">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="11106-168">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="11106-169">**Derde naamserver**</span><span class="sxs-lookup"><span data-stu-id="11106-169">**Third name server**</span></span> <br/> |<span data-ttu-id="11106-170">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="11106-170">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="11106-171">**Vierde naamserver**</span><span class="sxs-lookup"><span data-stu-id="11106-171">**Fourth name server**</span></span> <br/> |<span data-ttu-id="11106-172">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="11106-172">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Afbeelding van het lint](../../media/6d14544d-7783-4ed4-b4dd-691624af7172.png)
  
2. <span data-ttu-id="11106-174">Selecteer het **besturingselement + (toevoegen)** om een lege rij te maken.</span><span class="sxs-lookup"><span data-stu-id="11106-174">Select the **+ (add)** control to create an empty row.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-3](../../media/ea23e5fc-07e1-4ffc-b8cf-8526867b752d.png)
  
3. <span data-ttu-id="11106-176">De andere drie naamserverrecords toevoegen.</span><span class="sxs-lookup"><span data-stu-id="11106-176">Add the other three Nameserver records.</span></span>
    
    <span data-ttu-id="11106-177">Maak in de sectie **Aangepaste naamservers gebruiken** een record met de waarden uit de volgende rij in de tabel en selecteer vervolgens het **besturingselement + (toevoegen)** om een andere rij toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="11106-177">In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then select the **+ (add)** control to add another row.</span></span> 
    
    <span data-ttu-id="11106-178">Herhaal deze procedure totdat u alle vier de naamserverrecords hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="11106-178">Repeat this process until you have created all four Nameserver records.</span></span>
    
4. <span data-ttu-id="11106-179">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="11106-179">Select **Save**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> <span data-ttu-id="11106-p111">Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd. Vervolgens worden uw e-mail voor Office 365 en andere services ingesteld voor gebruik met uw domein.</span><span class="sxs-lookup"><span data-stu-id="11106-p111">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="11106-183">Als er WEL naamservers worden vermeld</span><span class="sxs-lookup"><span data-stu-id="11106-183">If there ARE nameservers already listed</span></span>

1. <span data-ttu-id="11106-184">Als er andere naamservers worden vermeld, selecteert u **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="11106-184">If there are any other nameservers listed, select **Edit**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="11106-185">Volg deze stappen alleen als u bestaande naamservers hebt, andere dan de vier juiste naamservers.</span><span class="sxs-lookup"><span data-stu-id="11106-185">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="11106-186">(Dat wil zeggen, alleen huidige naamservers verwijderen die *geen* naam hebben **ns1.bdm.microsoftonline.com,** **ns2.bdm.microsoftonline.com,** **ns3.bdm.microsoftonline.com**of **ns4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="11106-186">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Google-Domains-BP-Redelegate-1-6-1](../../media/fb45d120-55ab-42c2-bdb6-19b130c3c7db.png)
  
2. <span data-ttu-id="11106-188">Verwijder vervolgens elk item door het te selecteren en op de toets **Delete** op het toetsenbord te drukken.</span><span class="sxs-lookup"><span data-stu-id="11106-188">Delete each one by selecting it, and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-6-2](../../media/524e64ad-56e6-4254-8a64-e4a4c3230f89.png)
  
3. <span data-ttu-id="11106-190">In de sectie **Name servers** typt of kopieert en plakt u de waarden uit de volgende tabel in de rijen **NAME SERVER**.</span><span class="sxs-lookup"><span data-stu-id="11106-190">Still in the **Name servers** section, in the **NAME SERVER** rows, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="11106-191">**First name server**</span><span class="sxs-lookup"><span data-stu-id="11106-191">**First name server**</span></span> <br/> |<span data-ttu-id="11106-192">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="11106-192">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="11106-193">**Second name server**</span><span class="sxs-lookup"><span data-stu-id="11106-193">**Second name server**</span></span> <br/> |<span data-ttu-id="11106-194">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="11106-194">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="11106-195">**Derde naamserver**</span><span class="sxs-lookup"><span data-stu-id="11106-195">**Third name server**</span></span> <br/> |<span data-ttu-id="11106-196">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="11106-196">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="11106-197">**Vierde naamserver**</span><span class="sxs-lookup"><span data-stu-id="11106-197">**Fourth name server**</span></span> <br/> |<span data-ttu-id="11106-198">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="11106-198">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Afbeelding van het lint](../../media/e008dccb-d789-4f52-8ecc-02831b7c6fb2.png)
  
4. <span data-ttu-id="11106-200">Selecteer het besturingselement **+(toevoegen)** om een lege rij te maken.</span><span class="sxs-lookup"><span data-stu-id="11106-200">Select the **+(add)** control to create an empty row.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-8](../../media/6ce40b1e-8464-443f-a64a-825dc8764590.png)
  
5. <span data-ttu-id="11106-202">Voer de andere twee naamserverrecords toe.</span><span class="sxs-lookup"><span data-stu-id="11106-202">Add the other two Nameserver records.</span></span>
    
    <span data-ttu-id="11106-203">Maak in de sectie **Aangepaste naamservers gebruiken** een record met de waarden uit de volgende rij in de tabel en selecteer vervolgens het besturingselement **+(toevoegen)** om een andere rij toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="11106-203">In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then select the **+(add)** control to add another row.</span></span> 
    
    <span data-ttu-id="11106-204">Herhaal deze procedure totdat u alle vier de naamserverrecords hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="11106-204">Repeat this process until you have created all four Nameserver records.</span></span>
    
6. <span data-ttu-id="11106-205">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="11106-205">Select **Save**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> <span data-ttu-id="11106-p113">Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd. Vervolgens worden uw e-mail voor Office 365 en andere services ingesteld voor gebruik met uw domein.</span><span class="sxs-lookup"><span data-stu-id="11106-p113">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
