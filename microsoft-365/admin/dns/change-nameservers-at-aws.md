---
title: Naamservers wijzigen om Microsoft in te stellen met Amazon Web Services (AWS)
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
ms.assetid: 0ddbe33c-81ea-4c02-8db9-e71d3810c0ec
description: 'Meer informatie over hoe u Microsoft instellen om uw DNS-records te beheren bij Amazon Web Services (AWS). '
ms.openlocfilehash: 6efe06400652783ffbc6732b5c6327067c5c484c
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400675"
---
# <a name="change-nameservers-to-set-up-microsoft-with-amazon-web-services-aws"></a><span data-ttu-id="fe495-103">Naamservers wijzigen om Microsoft in te stellen met Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="fe495-103">Change nameservers to set up Microsoft with Amazon Web Services (AWS)</span></span>

 <span data-ttu-id="fe495-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="fe495-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="fe495-105">Volg deze instructies als u wilt dat Microsoft uw DNS-records voor u beheert.</span><span class="sxs-lookup"><span data-stu-id="fe495-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="fe495-106">(Als u dat liever hebt, u [al uw Microsoft DNS-records beheren bij AWS](create-dns-records-at-aws.md).)</span><span class="sxs-lookup"><span data-stu-id="fe495-106">(If you prefer, you can [manage all your Microsoft DNS records at AWS](create-dns-records-at-aws.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="fe495-107">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="fe495-107">Add a TXT record for verification</span></span>

<span data-ttu-id="fe495-p102">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="fe495-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fe495-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="fe495-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="fe495-p104">Als u wilt beginnen, gaat u naar uw domeinenpagina bij AWS via [deze koppeling](https://console.aws.amazon.com/route53/home). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="fe495-p104">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="fe495-114">Selecteer op de pagina **Resources** de optie **Gehoste zones**.</span><span class="sxs-lookup"><span data-stu-id="fe495-114">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="fe495-115">Selecteer op de pagina **Gehoste zones** in de kolom **Domeinnaam** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="fe495-115">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="fe495-116">Selecteer **Recordset maken**.</span><span class="sxs-lookup"><span data-stu-id="fe495-116">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="fe495-117">Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Create Record Set** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="fe495-117">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="fe495-118">(Kies in de vervolgkeuzelijsten de waarden **Type** en **Routing Policy**.)</span><span class="sxs-lookup"><span data-stu-id="fe495-118">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="fe495-p105">De aanhalingstekens die zijn vereist volgens de instructies op het scherm, worden automatisch ingevoegd. U hoeft deze niet handmatig te typen.</span><span class="sxs-lookup"><span data-stu-id="fe495-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fe495-121">**Name**</span><span class="sxs-lookup"><span data-stu-id="fe495-121">**Name**</span></span> <br/> |<span data-ttu-id="fe495-122">**Type**</span><span class="sxs-lookup"><span data-stu-id="fe495-122">**Type**</span></span> <br/> |<span data-ttu-id="fe495-123">**Alias**</span><span class="sxs-lookup"><span data-stu-id="fe495-123">**Alias**</span></span> <br/> |<span data-ttu-id="fe495-124">**TTL (Seconds)**</span><span class="sxs-lookup"><span data-stu-id="fe495-124">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="fe495-125">**Value**</span><span class="sxs-lookup"><span data-stu-id="fe495-125">**Value**</span></span> <br/> |<span data-ttu-id="fe495-126">**Routing Policy**</span><span class="sxs-lookup"><span data-stu-id="fe495-126">**Routing Policy**</span></span> <br/> |
|<span data-ttu-id="fe495-127">(Laat dit veld leeg)</span><span class="sxs-lookup"><span data-stu-id="fe495-127">(Leave this field empty)</span></span>  <br/> |<span data-ttu-id="fe495-128">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="fe495-128">TXT - Text</span></span>  <br/> |<span data-ttu-id="fe495-129">No</span><span class="sxs-lookup"><span data-stu-id="fe495-129">No</span></span>  <br/> |<span data-ttu-id="fe495-130">300</span><span class="sxs-lookup"><span data-stu-id="fe495-130">300</span></span>  <br/> |<span data-ttu-id="fe495-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="fe495-131">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="fe495-132">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="fe495-132">**Note:** This is an example.</span></span> <span data-ttu-id="fe495-133">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="fe495-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="fe495-134">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="fe495-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  <br/>  |<span data-ttu-id="fe495-135">Simple</span><span class="sxs-lookup"><span data-stu-id="fe495-135">Simple</span></span> <br/> |
   
6. <span data-ttu-id="fe495-136">Selecteer **Maken**.</span><span class="sxs-lookup"><span data-stu-id="fe495-136">Select **Create**.</span></span>
    
7. <span data-ttu-id="fe495-137">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="fe495-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="fe495-138">Nu u de record op de site van uw domeinregistrar hebt toegevoegd, gaat u terug naar Microsoft en vraagt u om een zoekopdracht naar de record.</span><span class="sxs-lookup"><span data-stu-id="fe495-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="fe495-139">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="fe495-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="fe495-140">Ga in het Microsoft-beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="fe495-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="fe495-141">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="fe495-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="fe495-142">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="fe495-142">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="fe495-143">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="fe495-143">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="fe495-p107">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="fe495-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="fe495-147">De naamserverrecords (NS-records) van uw domein wijzigen</span><span class="sxs-lookup"><span data-stu-id="fe495-147">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="fe495-148">Als u het instellen van uw domein met Microsoft wilt voltooien, wijzigt u de NS-records van uw domein bij uw domeinregistrar om naar de primaire en secundaire naamservers van Microsoft te wijzen.</span><span class="sxs-lookup"><span data-stu-id="fe495-148">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="fe495-149">Hiermee wordt Microsoft ingesteld om de DNS-records van het domein voor u bij te werken.</span><span class="sxs-lookup"><span data-stu-id="fe495-149">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="fe495-150">We voegen alle records toe zodat e-mail, Skype voor Bedrijven Online en uw openbare website met uw domein werken en u helemaal klaar bent.</span><span class="sxs-lookup"><span data-stu-id="fe495-150">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="fe495-151">Wanneer u de NS-records van uw domein wijzigt om naar de Microsoft-naamservers te wijzen, worden alle services die momenteel aan uw domein zijn gekoppeld, beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="fe495-151">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="fe495-152">Alle e-mail die naar uw *your_domain* domein wordt verzonden (zoals rob@ your_domain.com) wordt bijvoorbeeld naar Microsoft verzonden nadat u deze wijziging hebt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="fe495-152">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="fe495-p110">In de volgende procedure kunt u zien hoe u andere, ongewenste naamservers uit de lijst verwijdert en hoe u de juiste naamservers toevoegt als deze niet al in de lijst staan. >  Na het voltooien van de stappen in deze sectie, moeten alleen de volgende vier naamservers in de lijst staan: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="fe495-p110">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed. >  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="fe495-155">Als u wilt beginnen, gaat u naar uw domeinenpagina bij AWS via [deze koppeling](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="fe495-155">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="fe495-156">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="fe495-156">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="fe495-157">Selecteer op de pagina **Resources** de optie **Gehoste zones**.</span><span class="sxs-lookup"><span data-stu-id="fe495-157">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="fe495-158">Selecteer op de pagina **Gehoste zones** in de kolom **Domeinnaam** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="fe495-158">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="fe495-159">Selecteer de **Nameserver**-recordset.</span><span class="sxs-lookup"><span data-stu-id="fe495-159">Select the **Nameserver** record set.</span></span> 
    
    ![Select the recordset](../../media/24e618e4-0a16-43a2-9886-f4f5dac79374.png)
  
5. <span data-ttu-id="fe495-161">Verwijder in de recordset **NS - Name server** in het vak **Value** alle naamservers door ze allemaal te selecteren en op de toets **Delete** op het toetsenbord te drukken.</span><span class="sxs-lookup"><span data-stu-id="fe495-161">In the **NS - Name server** record set in the **Value** box, delete all of the nameservers by selecting them all and then pressing the **Delete** key on your keyboard.</span></span> 
    
    > [!CAUTION]
    > <span data-ttu-id="fe495-162">Volg deze stappen alleen als u bestaande naamservers hebt, andere dan de vier juiste naamservers.</span><span class="sxs-lookup"><span data-stu-id="fe495-162">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="fe495-163">(Dat wil zeggen, alleen huidige naamservers verwijderen die *geen* naam hebben **ns1.bdm.microsoftonline.com,** **ns2.bdm.microsoftonline.com,** **ns3.bdm.microsoftonline.com**of **ns4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="fe495-163">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Select and delete all of the nameservers in the Value box](../../media/ecf1e897-fa7d-4abc-b00b-bf55b8ed2139.png)
  
6. <span data-ttu-id="fe495-165">Selecteer 1 uur in het gebied **TTL (Seconden):** **1uur** (1 uur).</span><span class="sxs-lookup"><span data-stu-id="fe495-165">In the **TTL (Seconds):** area, select **1h** (1 Hour).</span></span> 
    
    ![Selecteer 1Uur voor een uur](../../media/c70070e1-4bde-41a7-b271-9d22c475edf6.png)
  
7. <span data-ttu-id="fe495-167">In de recordset **NS - Name server** en het vak **Value** typt of kopieert en plakt u bovendien de waarde uit **Eerste regel** uit de volgende tabel, drukt u op **Enter** op het toetsenbord en typt of kopieert en plakt u de waarde van de volgende **regel**.</span><span class="sxs-lookup"><span data-stu-id="fe495-167">Still in the **NS - Name server** record set, in the **Value** box, type or copy and paste the **First line** value from the following table, then press the **Enter** key on your keyboard and type or copy and paste the next **line** value.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="fe495-168">Elke naamserverwaarde  *moet*  op een afzonderlijke regel in het vak **Value** staan, zoals wordt weergegeven in de volgende afbeelding.</span><span class="sxs-lookup"><span data-stu-id="fe495-168">Each nameserver value  *must*  be on its own separate line within the **Value** box, as shown in the following illustration.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="fe495-169">**Eerste regel**</span><span class="sxs-lookup"><span data-stu-id="fe495-169">**First line**</span></span> <br/> |<span data-ttu-id="fe495-170">ns1.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="fe495-170">ns1.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="fe495-171">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="fe495-171">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="fe495-172">**Tweede regel**</span><span class="sxs-lookup"><span data-stu-id="fe495-172">**Second line**</span></span> <br/> |<span data-ttu-id="fe495-173">ns2.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="fe495-173">ns2.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="fe495-174">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="fe495-174">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="fe495-175">**Derde regel**</span><span class="sxs-lookup"><span data-stu-id="fe495-175">**Third line**</span></span> <br/> |<span data-ttu-id="fe495-176">ns3.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="fe495-176">ns3.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="fe495-177">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="fe495-177">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="fe495-178">**Vierde regel**</span><span class="sxs-lookup"><span data-stu-id="fe495-178">**Fourth line**</span></span> <br/> |<span data-ttu-id="fe495-179">ns4.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="fe495-179">ns4.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="fe495-180">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="fe495-180">**This value MUST end with a period (.)**</span></span> <br/> |
   
   ![De waarde Eerste regel typen of plakken in het vak Waarde](../../media/b63f41e0-51ef-4ab2-a4b8-ee7380e5ab35.png)
  
8. <span data-ttu-id="fe495-182">Selecteer **Recordset opslaan**.</span><span class="sxs-lookup"><span data-stu-id="fe495-182">Select **Save Record Set**.</span></span>
    
    ![Recordset opslaan selecteren](../../media/ab3c0558-bb7c-41e4-871e-ea82f1553476.png)
  
> [!NOTE]
> <span data-ttu-id="fe495-184">Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd.</span><span class="sxs-lookup"><span data-stu-id="fe495-184">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="fe495-185">Vervolgens zijn uw Microsoft-e-mail en andere services helemaal klaar om met uw domein te werken.</span><span class="sxs-lookup"><span data-stu-id="fe495-185">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
