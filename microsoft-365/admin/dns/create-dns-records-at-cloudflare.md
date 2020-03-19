---
title: DNS-records maken bij Cloudflare voor Office 365
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
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Meer informatie over het verifiëren van uw domein en het instellen van DNS-records voor e-mail, Skype voor Bedrijven Online en andere services bij Cloudflare voor Office 365.
ms.openlocfilehash: efd7a4a41a0cc27c2a50da732d648c87c79c6ff7
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42806375"
---
# <a name="create-dns-records-at-cloudflare-for-office-365"></a><span data-ttu-id="9b3de-103">DNS-records maken bij Cloudflare voor Office 365</span><span class="sxs-lookup"><span data-stu-id="9b3de-103">Create DNS records at Cloudflare for Office 365</span></span>

 <span data-ttu-id="9b3de-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="9b3de-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="9b3de-105">Als Cloudflare uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="9b3de-105">If Cloudflare is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="9b3de-106">Nadat u deze records bij Cloudflare hebt toegevoegd, is uw domein ingesteld voor gebruik met Office 365-services.</span><span class="sxs-lookup"><span data-stu-id="9b3de-106">After you add these records at Cloudflare, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="9b3de-107">Zie [Een openbare website gebruiken met Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx) voor informatie over webhosting en DNS voor websites met Office 365.</span><span class="sxs-lookup"><span data-stu-id="9b3de-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="9b3de-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9b3de-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="9b3de-111">De naamserverrecords (NS-records) van uw domein wijzigen</span><span class="sxs-lookup"><span data-stu-id="9b3de-111">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="9b3de-112"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="9b3de-112"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="9b3de-113">U moet deze procedure uitvoeren bij de domeinregistrar waar u uw domein hebt gekocht en geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="9b3de-113">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="9b3de-114">Toen u zich voor Cloudflare registreerde, hebt u een domein toegevoegd met behulp van het Cloudflare **Setup**-proces.</span><span class="sxs-lookup"><span data-stu-id="9b3de-114">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span></span> 
  
<span data-ttu-id="9b3de-p102">Het door u toegevoegde domein was aangeschaft bij een afzonderlijke domeinregistrar; Cloudflare biedt geen domeinregistratieservices. Als u DNS-records voor uw domein in Office 365 wilt verifiëren en maken, moet u eerst de naamservers bij uw domeinregistrar wijzigen zodat ze de naamservers van Cloudflare kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="9b3de-p102">The domain that you added was purchased from a separate domain registrar; Cloudflare does not offer domain registration services. To verify and create DNS records for your domain in Office 365, you first need to change the nameservers at your domain registrar so that they use Cloudflare's nameservers.</span></span>
  
<span data-ttu-id="9b3de-117">Als u de naamservers van het domein zelf wilt wijzigen op de website van de domeinregistrar, voert u de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="9b3de-117">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="9b3de-118">Zoek het gedeelte op de website van de domeinregistrar waarop u de naamservers voor uw domein kunt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="9b3de-118">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="9b3de-119">Maak twee naamserverrecords door de waarden in de volgende tabel te gebruiken of bewerk de bestaande naamserverrecords zodat ze overeenkomen met deze waarden:</span><span class="sxs-lookup"><span data-stu-id="9b3de-119">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="9b3de-120">Eerste naamserver</span><span class="sxs-lookup"><span data-stu-id="9b3de-120">First nameserver</span></span>  <br/> |<span data-ttu-id="9b3de-121">Gebruik de door Cloudflare opgegeven waarde voor de naamserver.</span><span class="sxs-lookup"><span data-stu-id="9b3de-121">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
    |<span data-ttu-id="9b3de-122">Tweede naamserver</span><span class="sxs-lookup"><span data-stu-id="9b3de-122">Second nameserver</span></span>  <br/> |<span data-ttu-id="9b3de-123">Gebruik de door Cloudflare opgegeven waarde voor de naamserver.</span><span class="sxs-lookup"><span data-stu-id="9b3de-123">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="9b3de-124">U moet ten minste twee naamserverrecords gebruiken.</span><span class="sxs-lookup"><span data-stu-id="9b3de-124">You should use at least two name server records.</span></span> <span data-ttu-id="9b3de-125">Als er andere naamservers worden vermeld, moet u deze verwijderen.</span><span class="sxs-lookup"><span data-stu-id="9b3de-125">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="9b3de-126">Sla uw wijzigingen op.</span><span class="sxs-lookup"><span data-stu-id="9b3de-126">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9b3de-p104">Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd. Vervolgens worden uw e-mail voor Office 365 en andere services ingesteld voor gebruik met uw domein.</span><span class="sxs-lookup"><span data-stu-id="9b3de-p104">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="9b3de-129">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="9b3de-129">Add a TXT record for verification</span></span>
<span data-ttu-id="9b3de-130"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="9b3de-130"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="9b3de-p105">Voordat u uw domein met Office 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Office 365 bewezen.</span><span class="sxs-lookup"><span data-stu-id="9b3de-p105">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9b3de-p106">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="9b3de-p106">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="9b3de-135">Ga eerst naar uw domeinenpagina bij Cloudflare via [deze koppeling](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="9b3de-135">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="9b3de-136">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="9b3de-136">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="9b3de-137">Selecteer op **de** startpagina het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="9b3de-137">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="9b3de-138">Selecteer **DNS**op de pagina **Overzicht** voor uw domein.</span><span class="sxs-lookup"><span data-stu-id="9b3de-138">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="9b3de-139">Klik op de pagina **DNS-beheer** op **Record toevoegen**en selecteer vervolgens de waarden in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="9b3de-139">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="9b3de-140">**Type**</span><span class="sxs-lookup"><span data-stu-id="9b3de-140">**Type**</span></span>|<span data-ttu-id="9b3de-141">**Name**</span><span class="sxs-lookup"><span data-stu-id="9b3de-141">**Name**</span></span>|<span data-ttu-id="9b3de-142">**Automatic TTL**</span><span class="sxs-lookup"><span data-stu-id="9b3de-142">**Automatic TTL**</span></span>|<span data-ttu-id="9b3de-143">**Content**</span><span class="sxs-lookup"><span data-stu-id="9b3de-143">**Content**</span></span>|
    |:-----|:-----|:-----|:----|
    |<span data-ttu-id="9b3de-144">TXT</span><span class="sxs-lookup"><span data-stu-id="9b3de-144">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="9b3de-145">30 minutes</span><span class="sxs-lookup"><span data-stu-id="9b3de-145">30 minutes</span></span>  <br/> |<span data-ttu-id="9b3de-146">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="9b3de-146">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="9b3de-p108">**Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="9b3de-p108">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>    |
  
    
5. <span data-ttu-id="9b3de-150">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="9b3de-150">Select **Save**.</span></span>
  
  
9. <span data-ttu-id="9b3de-151">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="9b3de-151">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="9b3de-152">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Office 365 en vraagt u of Office 365 naar de record wil zoeken.</span><span class="sxs-lookup"><span data-stu-id="9b3de-152">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="9b3de-153">Wanneer in Office 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="9b3de-153">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="9b3de-154">Ga in het beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Instellingendomeinen.</a> **Settings**</span><span class="sxs-lookup"><span data-stu-id="9b3de-154">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="9b3de-155">Selecteer op de pagina **Domeinen** het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="9b3de-155">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="9b3de-156">Selecteer op de pagina **Setup** de optie **Startsetup**.</span><span class="sxs-lookup"><span data-stu-id="9b3de-156">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="9b3de-157">Selecteer op de pagina **Domein verifiëren** de optie **Verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="9b3de-157">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="9b3de-p109">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9b3de-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="9b3de-161">Voeg een MX-record toe zodat e-mail voor uw domein bij Office 365 terechtkomt</span><span class="sxs-lookup"><span data-stu-id="9b3de-161">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="9b3de-162"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="9b3de-162"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="9b3de-p110">Ga eerst naar uw domeinenpagina bij Cloudflare via [deze koppeling](https://www.cloudflare.com/a/login). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="9b3de-p110">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="9b3de-165">Selecteer op **de** startpagina het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="9b3de-165">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="9b3de-166">Selecteer **DNS**op de pagina **Overzicht** voor uw domein.</span><span class="sxs-lookup"><span data-stu-id="9b3de-166">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="9b3de-167">Klik op de pagina **DNS-beheer** op **Record toevoegen**en selecteer vervolgens de waarden in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="9b3de-167">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="9b3de-168">**Type**</span><span class="sxs-lookup"><span data-stu-id="9b3de-168">**Type**</span></span>|<span data-ttu-id="9b3de-169">**Name**</span><span class="sxs-lookup"><span data-stu-id="9b3de-169">**Name**</span></span>|<span data-ttu-id="9b3de-170">**Mail server**</span><span class="sxs-lookup"><span data-stu-id="9b3de-170">**Mail server**</span></span>|<span data-ttu-id="9b3de-171">**Priority**</span><span class="sxs-lookup"><span data-stu-id="9b3de-171">**Priority**</span></span>|<span data-ttu-id="9b3de-172">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9b3de-172">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9b3de-173">MX</span><span class="sxs-lookup"><span data-stu-id="9b3de-173">MX</span></span>  <br/> |@  <br/> |<span data-ttu-id="9b3de-174">*\<domeinsleutel\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9b3de-174">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="9b3de-175">**Let op:** Haal uw \* \<domeinsleutel\> \* uit uw Office 365-account.</span><span class="sxs-lookup"><span data-stu-id="9b3de-175">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="9b3de-176">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="9b3de-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="9b3de-177">1</span><span class="sxs-lookup"><span data-stu-id="9b3de-177">1</span></span>  <br/> <span data-ttu-id="9b3de-178">Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="9b3de-178">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/>|<span data-ttu-id="9b3de-179">30 minutes</span><span class="sxs-lookup"><span data-stu-id="9b3de-179">30 minutes</span></span>  <br/> |
   

  
5. <span data-ttu-id="9b3de-180">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="9b3de-180">Select **Save**.</span></span>
  
9. <span data-ttu-id="9b3de-181">Als er andere MX-records zijn vermeld in de sectie **MX Records**, verwijdert u ze door het pictogram **Delete (X)** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="9b3de-181">If there are any other MX records listed in the **MX Records** section, delete them by selecting the **Delete (X)** icon.</span></span> 
  
10. <span data-ttu-id="9b3de-182">Selecteer **Verwijderen** om uw wijzigingen te bevestigen in het bevestigingsdialoogvenster.</span><span class="sxs-lookup"><span data-stu-id="9b3de-182">In the confirmation dialog box, select **Delete** to confirm your changes.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="9b3de-183">De zes CNAME-records toevoegen die nodig zijn voor Office 365</span><span class="sxs-lookup"><span data-stu-id="9b3de-183">Add the Six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="9b3de-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="9b3de-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="9b3de-p112">Ga eerst naar uw domeinenpagina bij Cloudflare via [deze koppeling](https://www.cloudflare.com/a/login). U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="9b3de-p112">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="9b3de-187">Selecteer op **de** startpagina het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="9b3de-187">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="9b3de-188">Selecteer **DNS**op de pagina **Overzicht** voor uw domein.</span><span class="sxs-lookup"><span data-stu-id="9b3de-188">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="9b3de-189">Voeg de eerste van de vijf CNAME-records toe.</span><span class="sxs-lookup"><span data-stu-id="9b3de-189">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="9b3de-190">Klik op de pagina **DNS-beheer** op **Record toevoegen**en selecteer vervolgens de waarden in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="9b3de-190">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="9b3de-191">**Type**</span><span class="sxs-lookup"><span data-stu-id="9b3de-191">**Type**</span></span>|<span data-ttu-id="9b3de-192">**Name**</span><span class="sxs-lookup"><span data-stu-id="9b3de-192">**Name**</span></span>|<span data-ttu-id="9b3de-193">**Target**</span><span class="sxs-lookup"><span data-stu-id="9b3de-193">**Target**</span></span>|<span data-ttu-id="9b3de-194">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9b3de-194">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9b3de-195">CNAME</span><span class="sxs-lookup"><span data-stu-id="9b3de-195">CNAME</span></span>  <br/> |<span data-ttu-id="9b3de-196">autodiscover</span><span class="sxs-lookup"><span data-stu-id="9b3de-196">autodiscover</span></span>  <br/> |<span data-ttu-id="9b3de-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9b3de-197">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="9b3de-198">30 minutes</span><span class="sxs-lookup"><span data-stu-id="9b3de-198">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="9b3de-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="9b3de-199">CNAME</span></span>  <br/> |<span data-ttu-id="9b3de-200">sip</span><span class="sxs-lookup"><span data-stu-id="9b3de-200">sip</span></span>  <br/> |<span data-ttu-id="9b3de-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9b3de-201">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="9b3de-202">30 minutes</span><span class="sxs-lookup"><span data-stu-id="9b3de-202">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="9b3de-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="9b3de-203">CNAME</span></span>  <br/> |<span data-ttu-id="9b3de-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="9b3de-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="9b3de-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9b3de-205">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="9b3de-206">30 minutes</span><span class="sxs-lookup"><span data-stu-id="9b3de-206">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="9b3de-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="9b3de-207">CNAME</span></span>  <br/> |<span data-ttu-id="9b3de-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="9b3de-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="9b3de-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="9b3de-209">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="9b3de-210">30 minutes</span><span class="sxs-lookup"><span data-stu-id="9b3de-210">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="9b3de-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="9b3de-211">CNAME</span></span>  <br/> |<span data-ttu-id="9b3de-212">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="9b3de-212">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="9b3de-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9b3de-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="9b3de-214">30 minutes</span><span class="sxs-lookup"><span data-stu-id="9b3de-214">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="9b3de-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="9b3de-215">CNAME</span></span>  <br/> |<span data-ttu-id="9b3de-216">msoid</span><span class="sxs-lookup"><span data-stu-id="9b3de-216">msoid</span></span>  <br/> |<span data-ttu-id="9b3de-217">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="9b3de-217">clientconfig.microsoftonline-p.net</span></span>  <br/> |<span data-ttu-id="9b3de-218">30 minutes</span><span class="sxs-lookup"><span data-stu-id="9b3de-218">30 minutes</span></span>  <br/> |
    
  
5. <span data-ttu-id="9b3de-219">Selecteer het **pictogram DNS-verkeer** (orange cloud) om de Cloudflare-servers te omzeilen.</span><span class="sxs-lookup"><span data-stu-id="9b3de-219">Select the **DNS Traffic** icon (orange cloud) to bypass the Cloudflare servers.</span></span>
  
6. <span data-ttu-id="9b3de-220">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="9b3de-220">Select **Save**.</span></span>
  
7. <span data-ttu-id="9b3de-221">Voeg als volgt de andere vijf CNAME-records toe:</span><span class="sxs-lookup"><span data-stu-id="9b3de-221">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="9b3de-222">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="9b3de-222">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="9b3de-223"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="9b3de-223"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="9b3de-224">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="9b3de-224">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="9b3de-225">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="9b3de-225">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="9b3de-226">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Office 365 te maken.</span><span class="sxs-lookup"><span data-stu-id="9b3de-226">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="9b3de-227">In plaats daarvan voegt u de vereiste Office 365-waarden toe aan de huidige record, zodat u beschikt over  *één*  SPF-record waarin beide sets waarden zijn opgenomen.</span><span class="sxs-lookup"><span data-stu-id="9b3de-227">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="9b3de-228">Ga eerst naar uw domeinenpagina bij Cloudflare via [deze koppeling](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="9b3de-228">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="9b3de-229">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="9b3de-229">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="9b3de-230">Selecteer op **de** startpagina het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="9b3de-230">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="9b3de-231">Selecteer **DNS**op de pagina **Overzicht** voor uw domein.</span><span class="sxs-lookup"><span data-stu-id="9b3de-231">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="9b3de-232">Klik op de pagina **DNS-beheer** op **Record toevoegen**en selecteer vervolgens de waarden in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="9b3de-232">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>  
    
    |<span data-ttu-id="9b3de-233">**Type**</span><span class="sxs-lookup"><span data-stu-id="9b3de-233">**Type**</span></span>|<span data-ttu-id="9b3de-234">**Naam**</span><span class="sxs-lookup"><span data-stu-id="9b3de-234">**Name**</span></span>|<span data-ttu-id="9b3de-235">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9b3de-235">**TTL**</span></span>|<span data-ttu-id="9b3de-236">**Content**</span><span class="sxs-lookup"><span data-stu-id="9b3de-236">**Content**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9b3de-237">TXT</span><span class="sxs-lookup"><span data-stu-id="9b3de-237">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="9b3de-238">30 minutes</span><span class="sxs-lookup"><span data-stu-id="9b3de-238">30 minutes</span></span>  <br/> |<span data-ttu-id="9b3de-239">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="9b3de-239">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="9b3de-240">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="9b3de-240">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="9b3de-241">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="9b3de-241">Select **Save**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="9b3de-242">Voeg de vier SRV-records toe die voor Office 365 vereist zijn.</span><span class="sxs-lookup"><span data-stu-id="9b3de-242">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="9b3de-243"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="9b3de-243"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="9b3de-244">Houd er rekening mee dat Cloudflare verantwoordelijk is voor het beschikbaar maken van deze functionaliteit.</span><span class="sxs-lookup"><span data-stu-id="9b3de-244">Please keep in mind that Cloudflare is responsible for making this functionality available.</span></span> <span data-ttu-id="9b3de-245">Als u verschillen ziet tussen de onderstaande stappen en de huidige Cloudflare GUI(Grafische gebruikersinterface), maak dan gebruik van de [Cloudflare-community.](https://community.cloudflare.com/)</span><span class="sxs-lookup"><span data-stu-id="9b3de-245">In case you see discrepancies between the steps below and the current Cloudflare GUI(Graphical User Interface), please leverage the [Cloudflare Community](https://community.cloudflare.com/).</span></span> 

1. <span data-ttu-id="9b3de-246">Ga eerst naar uw domeinenpagina bij Cloudflare via [deze koppeling](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="9b3de-246">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="9b3de-247">U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="9b3de-247">You'll be prompted to log in first.</span></span>
      
2. <span data-ttu-id="9b3de-248">Selecteer op **de** startpagina het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="9b3de-248">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="9b3de-249">Selecteer **DNS**op de pagina **Overzicht** voor uw domein.</span><span class="sxs-lookup"><span data-stu-id="9b3de-249">On the **Overview** page for your domain, select **DNS**.</span></span>
  
4. <span data-ttu-id="9b3de-250">Voeg de eerste van de twee SRV-records toe.</span><span class="sxs-lookup"><span data-stu-id="9b3de-250">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="9b3de-251">Klik op de pagina **DNS-beheer** op **Record toevoegen**en selecteer vervolgens de waarden in de eerste rij van de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="9b3de-251">On the **DNS management** page, click **Add record**, and then select the values from the first row of the following table.</span></span>
        
    |<span data-ttu-id="9b3de-252">**Type**</span><span class="sxs-lookup"><span data-stu-id="9b3de-252">**Type**</span></span>|<span data-ttu-id="9b3de-253">**Service**</span><span class="sxs-lookup"><span data-stu-id="9b3de-253">**Service**</span></span>|<span data-ttu-id="9b3de-254">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="9b3de-254">**Protocol**</span></span>|<span data-ttu-id="9b3de-255">**Naam**</span><span class="sxs-lookup"><span data-stu-id="9b3de-255">**Name**</span></span>|<span data-ttu-id="9b3de-256">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9b3de-256">**TTL**</span></span>|<span data-ttu-id="9b3de-257">**Priority**</span><span class="sxs-lookup"><span data-stu-id="9b3de-257">**Priority**</span></span>|<span data-ttu-id="9b3de-258">**Weight**</span><span class="sxs-lookup"><span data-stu-id="9b3de-258">**Weight**</span></span>|<span data-ttu-id="9b3de-259">**Port**</span><span class="sxs-lookup"><span data-stu-id="9b3de-259">**Port**</span></span>|<span data-ttu-id="9b3de-260">**Doel**</span><span class="sxs-lookup"><span data-stu-id="9b3de-260">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9b3de-261">SRV</span><span class="sxs-lookup"><span data-stu-id="9b3de-261">SRV</span></span>|<span data-ttu-id="9b3de-262">_sip</span><span class="sxs-lookup"><span data-stu-id="9b3de-262">_sip</span></span> |<span data-ttu-id="9b3de-263">TLS</span><span class="sxs-lookup"><span data-stu-id="9b3de-263">TLS</span></span> |<span data-ttu-id="9b3de-264">Gebruik uw *domain_name*; contoso.com</span><span class="sxs-lookup"><span data-stu-id="9b3de-264">Use your *domain_name*; for example, contoso.com</span></span>  |<span data-ttu-id="9b3de-265">30 minutes</span><span class="sxs-lookup"><span data-stu-id="9b3de-265">30 minutes</span></span> | <span data-ttu-id="9b3de-266">100</span><span class="sxs-lookup"><span data-stu-id="9b3de-266">100</span></span>|<span data-ttu-id="9b3de-267">1</span><span class="sxs-lookup"><span data-stu-id="9b3de-267">1</span></span> |<span data-ttu-id="9b3de-268">443</span><span class="sxs-lookup"><span data-stu-id="9b3de-268">443</span></span> |<span data-ttu-id="9b3de-269">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9b3de-269">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="9b3de-270">SRV</span><span class="sxs-lookup"><span data-stu-id="9b3de-270">SRV</span></span>|<span data-ttu-id="9b3de-271">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="9b3de-271">_sipfederationtls</span></span> | <span data-ttu-id="9b3de-272">TCP</span><span class="sxs-lookup"><span data-stu-id="9b3de-272">TCP</span></span>|<span data-ttu-id="9b3de-273">Gebruik uw *domain_name*; contoso.com</span><span class="sxs-lookup"><span data-stu-id="9b3de-273">Use your *domain_name*; for example, contoso.com</span></span>   |<span data-ttu-id="9b3de-274">30 minutes</span><span class="sxs-lookup"><span data-stu-id="9b3de-274">30 minutes</span></span> |<span data-ttu-id="9b3de-275">100</span><span class="sxs-lookup"><span data-stu-id="9b3de-275">100</span></span> |<span data-ttu-id="9b3de-276">1</span><span class="sxs-lookup"><span data-stu-id="9b3de-276">1</span></span> |<span data-ttu-id="9b3de-277">5061</span><span class="sxs-lookup"><span data-stu-id="9b3de-277">5061</span></span> | <span data-ttu-id="9b3de-278">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="9b3de-278">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="9b3de-279">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="9b3de-279">Select **Save**.</span></span>

  
6. <span data-ttu-id="9b3de-280">Voeg de andere SRV-record toe door de waarden uit de tweede rij van de tabel te kiezen.</span><span class="sxs-lookup"><span data-stu-id="9b3de-280">Add the other SRV record by choosing the values from the second row of the table.</span></span> 

    
> [!NOTE]
>  <span data-ttu-id="9b3de-p117">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9b3de-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
