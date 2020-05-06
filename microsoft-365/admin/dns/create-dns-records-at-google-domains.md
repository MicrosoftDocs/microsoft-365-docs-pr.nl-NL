---
title: DNS-records maken bij Google Domains voor Microsoft
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: Lees informatie over het verifiëren van uw domein en het instellen van DNS-records voor e-mail, Lync en andere services bij Google Domains voor Microsoft.
ms.openlocfilehash: 6bfe32ba8f77adec97f4ab5ee40e92126be91f10
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049009"
---
# <a name="create-dns-records-at-google-domains-for-microsoft"></a><span data-ttu-id="f1d17-103">DNS-records maken bij Google Domains voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="f1d17-103">Create DNS records at Google Domains for Microsoft</span></span>

 <span data-ttu-id="f1d17-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="f1d17-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="f1d17-105">Als Google Domains uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Lync enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="f1d17-105">If Google Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Lync, and so on.</span></span>
  
<span data-ttu-id="f1d17-106">Nadat u deze records hebt toegevoegd bij Google Domains, wordt uw domein ingesteld voor gebruik met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="f1d17-106">After you add these records at Google Domains, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="f1d17-107">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden.</span><span class="sxs-lookup"><span data-stu-id="f1d17-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="f1d17-108">Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet.</span><span class="sxs-lookup"><span data-stu-id="f1d17-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="f1d17-109">Zie Problemen zoeken en oplossen na het toevoegen van [uw domein- of DNS-records in Microsoft](../get-help-with-domains/find-and-fix-issues.md)als u problemen ondervindt met e-mailstroom of andere problemen na het toevoegen van DNS-records.</span><span class="sxs-lookup"><span data-stu-id="f1d17-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Microsoft](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="f1d17-110">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="f1d17-110">Add a TXT record for verification</span></span>
<span data-ttu-id="f1d17-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="f1d17-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="f1d17-p102">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="f1d17-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f1d17-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="f1d17-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="f1d17-p104">Ga eerst naar de pagina met domeinen bij Google Domains via [deze koppeling](https://domains.google.com/registrar). U wordt gevraagd om u aan te melden. U gaat hiervoor als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="f1d17-p104">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="f1d17-119">Selecteer **Aanmelden**.</span><span class="sxs-lookup"><span data-stu-id="f1d17-119">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="f1d17-120">Voer uw inloggegevens in en selecteer **Opnieuw Aanmelden**.</span><span class="sxs-lookup"><span data-stu-id="f1d17-120">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="f1d17-121">Zoek op de pagina **Mijn domeinen** het domein dat u met Microsoft wilt gebruiken en selecteer de koppeling **MANAGE** ernaast.</span><span class="sxs-lookup"><span data-stu-id="f1d17-121">On the **My domains** page, find the domain you want to use with Microsoft, and select the **MANAGE** link next to it.</span></span> <span data-ttu-id="f1d17-122">Selecteer IN de linkernavigatie de optie **DNS**.</span><span class="sxs-lookup"><span data-stu-id="f1d17-122">In the left navigation, select **DNS**.</span></span>
    
3. <span data-ttu-id="f1d17-123">Typ of kopieer en plak de waarden uit de volgende tabel in de sectie **Custom resource records** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="f1d17-123">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="f1d17-124">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="f1d17-124">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="f1d17-125">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="f1d17-125">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f1d17-126">**Name**</span><span class="sxs-lookup"><span data-stu-id="f1d17-126">**Name**</span></span> <br/> |<span data-ttu-id="f1d17-127">**Type**</span><span class="sxs-lookup"><span data-stu-id="f1d17-127">**Type**</span></span> <br/> |<span data-ttu-id="f1d17-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f1d17-128">**TTL**</span></span> <br/> |<span data-ttu-id="f1d17-129">**Data**</span><span class="sxs-lookup"><span data-stu-id="f1d17-129">**Data**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="f1d17-130">TXT</span><span class="sxs-lookup"><span data-stu-id="f1d17-130">TXT</span></span>  <br/> |<span data-ttu-id="f1d17-131">1H</span><span class="sxs-lookup"><span data-stu-id="f1d17-131">1H</span></span>  <br/> |<span data-ttu-id="f1d17-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="f1d17-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="f1d17-133">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="f1d17-133">**Note:** This is an example.</span></span> <span data-ttu-id="f1d17-134">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="f1d17-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="f1d17-135">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="f1d17-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
4. <span data-ttu-id="f1d17-136">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="f1d17-136">Select **Add**.</span></span>
    
5. <span data-ttu-id="f1d17-137">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="f1d17-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="f1d17-138">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.</span><span class="sxs-lookup"><span data-stu-id="f1d17-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="f1d17-139">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="f1d17-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="f1d17-140">Ga in het Microsoft-beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="f1d17-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="f1d17-141">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="f1d17-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="f1d17-142">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="f1d17-142">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="f1d17-143">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="f1d17-143">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f1d17-p107">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f1d17-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="f1d17-147">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="f1d17-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="f1d17-148"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="f1d17-148"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="f1d17-p108">Ga eerst naar de pagina met domeinen bij Google Domains via [deze koppeling](https://domains.google.com/registrar). U wordt gevraagd om u aan te melden. U gaat hiervoor als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="f1d17-p108">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="f1d17-152">Selecteer **Aanmelden**.</span><span class="sxs-lookup"><span data-stu-id="f1d17-152">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="f1d17-153">Voer uw inloggegevens in en selecteer **Opnieuw Aanmelden**.</span><span class="sxs-lookup"><span data-stu-id="f1d17-153">Enter your login credentials, and then again select **Sign In**.</span></span>
4. <span data-ttu-id="f1d17-154">Selecteer **op** de pagina Domeinen in de sectie **Domein** de optie **DNS configureren** voor het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="f1d17-154">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="f1d17-155">Als u een G Suite-e-mailaccount hebt, moet u eerst de aan dit account gekoppelde MX-records verwijderen.</span><span class="sxs-lookup"><span data-stu-id="f1d17-155">If you have a G Suite email account, you must first delete the MX records associated with that account.</span></span> <span data-ttu-id="f1d17-156">De G Suite MX-records voorkomen dat u andere MX-records toevoegt, inclusief die welke voor Microsoft vereist zijn.</span><span class="sxs-lookup"><span data-stu-id="f1d17-156">The G Suite MX records prevent you from adding any other MX records, including those required for Microsoft.</span></span> <span data-ttu-id="f1d17-157">Als u de Suite G-records verwijdert, wordt uw G Suite-account niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="f1d17-157">Note that deleting the G Suite records does not delete your G Suite account.</span></span> <span data-ttu-id="f1d17-158">Voer de volgende stappen uit als u de MX-records voor G Suite wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="f1d17-158">To delete your G Suite MX records, use the following steps.</span></span> 
  
5. <span data-ttu-id="f1d17-159">Selecteer in de sectie **Synthetische records** in het gebied **G Suite** de optie **Verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="f1d17-159">In the **Synthetic records** section, in the **G Suite** area, select **Delete**.</span></span>
    
    <span data-ttu-id="f1d17-160">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="f1d17-160">(You may have to scroll down.)</span></span>
    
    ![Selecteren in de sectie Synthetische records](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. <span data-ttu-id="f1d17-162">Selecteer **Verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="f1d17-162">Select **Delete**.</span></span>
    
    ![Selecteren Verwijderen](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. <span data-ttu-id="f1d17-164">Typ of kopieer en plak de waarden uit de volgende tabel in de sectie **Custom resource records** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="f1d17-164">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="f1d17-165">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="f1d17-165">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="f1d17-166">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="f1d17-166">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="f1d17-167">**Name**</span><span class="sxs-lookup"><span data-stu-id="f1d17-167">**Name**</span></span>|<span data-ttu-id="f1d17-168">**Type**</span><span class="sxs-lookup"><span data-stu-id="f1d17-168">**Type**</span></span>|<span data-ttu-id="f1d17-169">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f1d17-169">**TTL**</span></span>|<span data-ttu-id="f1d17-170">**Data**</span><span class="sxs-lookup"><span data-stu-id="f1d17-170">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="f1d17-171">MX</span><span class="sxs-lookup"><span data-stu-id="f1d17-171">MX</span></span>  <br/> |<span data-ttu-id="f1d17-172">1H</span><span class="sxs-lookup"><span data-stu-id="f1d17-172">1H</span></span>  <br/> |<span data-ttu-id="f1d17-173">0  *\<domeinsleutel\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="f1d17-173">0  *\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="f1d17-174">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="f1d17-174">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="f1d17-p110">De **0** is de MX-prioriteitwaarde. Voeg deze toe aan het begin van de MX-waarde, van de rest van de waarde gescheiden door een spatie.  </span><span class="sxs-lookup"><span data-stu-id="f1d17-p110">The **0** is the MX priority value. Add it to the beginning of the MX value, separated from the remainder of the value by a space.  </span></span><br/> <span data-ttu-id="f1d17-177">**Opmerking**: Uw \<*domeinsleutel*\> kunt u ophalen uit uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="f1d17-177">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span>  [<span data-ttu-id="f1d17-178">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="f1d17-178">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          <span data-ttu-id="f1d17-179">Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit.</span><span class="sxs-lookup"><span data-stu-id="f1d17-179">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
    ![Waarden typen of plakken in de sectie Aangepaste resourcerecords](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. <span data-ttu-id="f1d17-181">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="f1d17-181">Select **Add**.</span></span>
    
    ![Selecteer Toevoegen](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. <span data-ttu-id="f1d17-183">Als er andere aangepaste MX-records zijn, verwijdert u deze.</span><span class="sxs-lookup"><span data-stu-id="f1d17-183">If there are any other Custom MX records, remove them.</span></span>
    
1. <span data-ttu-id="f1d17-184">Selecteer **Bewerken** in de rij MX-record.</span><span class="sxs-lookup"><span data-stu-id="f1d17-184">Select **Edit** in the MX record row.</span></span> 
    
    ![Selecteer Bewerken in de rij MX-record](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. <span data-ttu-id="f1d17-186">Selecteer voor elk van de andere Aangepaste MX-records de vermelding in het vak **Gegevens** en druk vervolgens op **delete** op het toetsenbord om die record te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="f1d17-186">For each of the other Custom MX records, select the entry in the **Data** box and then press the **Delete** key on your keyboard to delete that record.</span></span> 
    
    <span data-ttu-id="f1d17-187">Ga door totdat u de **Data**-vermelding voor alle andere MX-records hebt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="f1d17-187">Continue until you have deleted the **Data** entry for each of the other MX records.</span></span> 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. <span data-ttu-id="f1d17-189">Wanneer u de **gegevensvermelding** voor elk van de andere MX-records hebt verwijderd, selecteert u **Opslaan** om uw wijzigingen op te slaan.</span><span class="sxs-lookup"><span data-stu-id="f1d17-189">When you have deleted the **Data** entry for each of the other MX records, select **Save** to save your changes.</span></span> 
    
    ![Selecteer Opslaan](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="f1d17-191">Voeg de vijf CNAME-records toe die nodig zijn voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="f1d17-191">Add the five CNAME records that are required for Microsoft</span></span>

1. <span data-ttu-id="f1d17-192">Ga naar de pagina [Google Domeinen]https://domains.google.com/registrar) en meld u aan om aan de slag te gaan.</span><span class="sxs-lookup"><span data-stu-id="f1d17-192">To get started, go to your [Google Domains page] (https://domains.google.com/registrar) and sign in.</span></span>
    
2. <span data-ttu-id="f1d17-193">Selecteer **op** de pagina Domeinen in de sectie **Domein** de optie **DNS configureren** voor het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="f1d17-193">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="f1d17-194">Voeg de eerste CNAME-record toe.</span><span class="sxs-lookup"><span data-stu-id="f1d17-194">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="f1d17-195">Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in de sectie **Custom resource records** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="f1d17-195">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from first row of the following table.</span></span> 
    
    <span data-ttu-id="f1d17-196">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="f1d17-196">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="f1d17-197">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="f1d17-197">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="f1d17-198">**Name**</span><span class="sxs-lookup"><span data-stu-id="f1d17-198">**Name**</span></span>|<span data-ttu-id="f1d17-199">**Type**</span><span class="sxs-lookup"><span data-stu-id="f1d17-199">**Type**</span></span>|<span data-ttu-id="f1d17-200">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f1d17-200">**TTL**</span></span>|<span data-ttu-id="f1d17-201">**Data**</span><span class="sxs-lookup"><span data-stu-id="f1d17-201">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f1d17-202">autodiscover</span><span class="sxs-lookup"><span data-stu-id="f1d17-202">autodiscover</span></span>  <br/> |<span data-ttu-id="f1d17-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="f1d17-203">CNAME</span></span>  <br/> |<span data-ttu-id="f1d17-204">1H</span><span class="sxs-lookup"><span data-stu-id="f1d17-204">1H</span></span>  <br/> |<span data-ttu-id="f1d17-205">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="f1d17-205">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="f1d17-206">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="f1d17-206">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="f1d17-207">sip</span><span class="sxs-lookup"><span data-stu-id="f1d17-207">sip</span></span>  <br/> |<span data-ttu-id="f1d17-208">CNAME</span><span class="sxs-lookup"><span data-stu-id="f1d17-208">CNAME</span></span>  <br/> |<span data-ttu-id="f1d17-209">1H</span><span class="sxs-lookup"><span data-stu-id="f1d17-209">1H</span></span>  <br/> |<span data-ttu-id="f1d17-210">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="f1d17-210">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="f1d17-211">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="f1d17-211">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="f1d17-212">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="f1d17-212">lyncdiscover</span></span>  <br/> |<span data-ttu-id="f1d17-213">CNAME</span><span class="sxs-lookup"><span data-stu-id="f1d17-213">CNAME</span></span>  <br/> |<span data-ttu-id="f1d17-214">1H</span><span class="sxs-lookup"><span data-stu-id="f1d17-214">1H</span></span>  <br/> |<span data-ttu-id="f1d17-215">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="f1d17-215">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="f1d17-216">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="f1d17-216">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="f1d17-217">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="f1d17-217">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="f1d17-218">CNAME</span><span class="sxs-lookup"><span data-stu-id="f1d17-218">CNAME</span></span>  <br/> |<span data-ttu-id="f1d17-219">1H</span><span class="sxs-lookup"><span data-stu-id="f1d17-219">1H</span></span>  <br/> |<span data-ttu-id="f1d17-220">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="f1d17-220">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="f1d17-221">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="f1d17-221">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="f1d17-222">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="f1d17-222">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="f1d17-223">CNAME</span><span class="sxs-lookup"><span data-stu-id="f1d17-223">CNAME</span></span>  <br/> |<span data-ttu-id="f1d17-224">1H</span><span class="sxs-lookup"><span data-stu-id="f1d17-224">1H</span></span>  <br/> |<span data-ttu-id="f1d17-225">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="f1d17-225">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="f1d17-226">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="f1d17-226">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Waarden typen of plakken in de sectie Aangepaste resourcerecords](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. <span data-ttu-id="f1d17-228">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="f1d17-228">Select **Add**.</span></span>
    
    ![Selecteer Toevoegen](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. <span data-ttu-id="f1d17-230">Voeg de andere vier CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="f1d17-230">Add the other four CNAME records.</span></span>
    
    <span data-ttu-id="f1d17-231">Maak in de sectie **Aangepaste resourcerecords** een record met de waarden uit de volgende rij in de tabel en selecteer vervolgens opnieuw **Toevoegen** om die record te voltooien.</span><span class="sxs-lookup"><span data-stu-id="f1d17-231">In the **Custom resource records** section, create a record by using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="f1d17-232">Herhaal dit proces totdat u alle vereiste CNAME-records hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="f1d17-232">Repeat this process until you have created all of the required CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="f1d17-233">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="f1d17-233">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f1d17-234">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="f1d17-234">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="f1d17-235">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="f1d17-235">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="f1d17-236">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f1d17-236">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="f1d17-237">In plaats hiervan voegt u de vereiste Microsoft-waarden toe aan de huidige record, zodat u beschikt over één SPF-record waarin beide sets waarden zijn opgenomen.</span><span class="sxs-lookup"><span data-stu-id="f1d17-237">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="f1d17-238">Hebt u voorbeelden nodig?</span><span class="sxs-lookup"><span data-stu-id="f1d17-238">Need examples?</span></span> <span data-ttu-id="f1d17-239">Bekijk deze [Externe Domain Name System-records voor Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords).</span><span class="sxs-lookup"><span data-stu-id="f1d17-239">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords).</span></span> <span data-ttu-id="f1d17-240">Voor het valideren van uw SPF-record, kunt u een van deze [SPF-validatiehulpmiddelen](../setup/domains-faq.md) gebruiken.</span><span class="sxs-lookup"><span data-stu-id="f1d17-240">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="f1d17-p113">Ga eerst naar de pagina met domeinen bij Google Domains via [deze koppeling](https://domains.google.com/registrar). U wordt gevraagd om u aan te melden. U gaat hiervoor als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="f1d17-p113">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="f1d17-244">Selecteer **Aanmelden**.</span><span class="sxs-lookup"><span data-stu-id="f1d17-244">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="f1d17-245">Voer uw inloggegevens in en selecteer **Opnieuw Aanmelden**.</span><span class="sxs-lookup"><span data-stu-id="f1d17-245">Enter your login credentials, and then again select **Sign In**.</span></span>
    
3. <span data-ttu-id="f1d17-246">Selecteer **op** de pagina Domeinen in de sectie **Domein** de optie **DNS configureren** voor het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="f1d17-246">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="f1d17-247">Selecteer in de sectie **Aangepaste resourcerecords** in de rij TXT-record de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="f1d17-247">In the **Custom resource records** section, on the TXT record row, select **Edit**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="f1d17-p114">Google Domains slaat MX-records op als een set die meerdere records kan bevatten. Wanneer u minimaal één andere TXT-record hebt, zoals de TXT-record die u hebt gebruikt om uw domein te verifiëren, moet u de nieuwe TXT-records aan deze recordset toevoegen. Als u extra TXT-records als afzonderlijke vermeldingen probeert toe te voegen, wordt het foutbericht **Duplicate record** (Dubbele record) weergegeven.</span><span class="sxs-lookup"><span data-stu-id="f1d17-p114">Google Domains stores TXT records as a set that may contain multiple records. When you have at least one other TXT record, such as the TXT record you used to verify your domain, you must add TXT new records to that record set. Any attempt to enter additional TXT records as separate entries will result in a **Duplicate record** error message.</span></span> 
  
    ![Bewerken selecteren in de rij TXT-record](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. <span data-ttu-id="f1d17-252">Selecteer het **besturingselement (+).**</span><span class="sxs-lookup"><span data-stu-id="f1d17-252">Select the **(+)** control.</span></span> 
    
    ![Het plusbesturingselement selecteren](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. <span data-ttu-id="f1d17-254">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="f1d17-254">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="f1d17-255">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="f1d17-255">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="f1d17-256">**Data**</span><span class="sxs-lookup"><span data-stu-id="f1d17-256">**Data**</span></span>|
    |:-----|
    |<span data-ttu-id="f1d17-257">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="f1d17-257">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> 

    > [!NOTE]
    > <span data-ttu-id="f1d17-258">Het is raadzaam dit item te kopiëren en te plakken, zodat alle spatiëring ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="f1d17-258">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           
   
   ![Waarden typen of plakken in de sectie Aangepaste resourcerecords](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. <span data-ttu-id="f1d17-260">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f1d17-260">Select **Save**.</span></span>
    
    ![Selecteer Opslaan](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="f1d17-262">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="f1d17-262">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="f1d17-263"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="f1d17-263"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="f1d17-p115">Ga eerst naar de pagina met domeinen bij Google Domains via [deze koppeling](https://domains.google.com/registrar). U wordt gevraagd om u aan te melden. U gaat hiervoor als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="f1d17-p115">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
2. <span data-ttu-id="f1d17-267">Selecteer **Aanmelden**.</span><span class="sxs-lookup"><span data-stu-id="f1d17-267">Select **Sign In**.</span></span>
    
3. <span data-ttu-id="f1d17-268">Voer uw inloggegevens in en selecteer **Opnieuw Aanmelden**.</span><span class="sxs-lookup"><span data-stu-id="f1d17-268">Enter your login credentials, and then again select **Sign In**.</span></span>
    
4. <span data-ttu-id="f1d17-269">Selecteer **op** de pagina Domeinen in de sectie **Domein** de optie **DNS configureren** voor het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="f1d17-269">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
5. <span data-ttu-id="f1d17-270">Voeg de eerste SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="f1d17-270">Add the first SRV record.</span></span>
    
    <span data-ttu-id="f1d17-271">Typ of kopieer en plak de waarden uit de volgende tabel in de sectie **Custom resource records** in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="f1d17-271">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="f1d17-272">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="f1d17-272">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="f1d17-273">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="f1d17-273">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="f1d17-274">**Name**</span><span class="sxs-lookup"><span data-stu-id="f1d17-274">**Name**</span></span>|<span data-ttu-id="f1d17-275">**Type**</span><span class="sxs-lookup"><span data-stu-id="f1d17-275">**Type**</span></span>|<span data-ttu-id="f1d17-276">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f1d17-276">**TTL**</span></span>|<span data-ttu-id="f1d17-277">**Data**</span><span class="sxs-lookup"><span data-stu-id="f1d17-277">**Data**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f1d17-278">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="f1d17-278">_sip._tls</span></span>|<span data-ttu-id="f1d17-279">SRV</span><span class="sxs-lookup"><span data-stu-id="f1d17-279">SRV</span></span>|<span data-ttu-id="f1d17-280">1H</span><span class="sxs-lookup"><span data-stu-id="f1d17-280">1H</span></span>|<span data-ttu-id="f1d17-281">100 1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="f1d17-281">100 1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="f1d17-282">**Deze waarde MOET eindigen met een periode (.)** **Let op:** We raden u aan dit item te kopiëren en te plakken, zodat alle afstand correct blijft.</span><span class="sxs-lookup"><span data-stu-id="f1d17-282">**This value MUST end with a period (.)** **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="f1d17-283">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="f1d17-283">_sipfederationtls._tcp</span></span>|<span data-ttu-id="f1d17-284">SRV</span><span class="sxs-lookup"><span data-stu-id="f1d17-284">SRV</span></span>|<span data-ttu-id="f1d17-285">1H</span><span class="sxs-lookup"><span data-stu-id="f1d17-285">1H</span></span>|<span data-ttu-id="f1d17-286">100 1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="f1d17-286">100 1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="f1d17-287">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="f1d17-287">**This value MUST end with a period (.)**</span></span>

    <span data-ttu-id="f1d17-288">Het is raadzaam dit item te kopiëren en te plakken, zodat alle spatiëring ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="f1d17-288">We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>       
   
    ![Waarden typen of plakken in de sectie Aangepaste resourcerecords](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. <span data-ttu-id="f1d17-290">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="f1d17-290">Select **Add**.</span></span>
    
    ![Selecteer Toevoegen](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. <span data-ttu-id="f1d17-292">Voeg de andere SRV-record toe.</span><span class="sxs-lookup"><span data-stu-id="f1d17-292">Add the other SRV record.</span></span>
    
    <span data-ttu-id="f1d17-293">Maak in de sectie **Aangepaste resourcerecords** een record met de waarden uit de tweede rij in de tabel en selecteer vervolgens opnieuw **Toevoegen** om die record te voltooien.</span><span class="sxs-lookup"><span data-stu-id="f1d17-293">In the **Custom resource records** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="f1d17-p118">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f1d17-p118">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
