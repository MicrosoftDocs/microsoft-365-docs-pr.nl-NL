---
title: DNS-records maken bij eNomCentral voor Microsoft
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
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: Informatie over het verifiëren van uw domein en het instellen van DNS-records voor e-mail, Skype voor Bedrijven Online en andere services bij eNomCentral voor Microsoft.
ms.openlocfilehash: 528659667ee062c8cf767bed0989558020032924
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910364"
---
# <a name="create-dns-records-at-enomcentral-for-microsoft"></a><span data-ttu-id="1bd4e-103">DNS-records maken bij eNomCentral voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="1bd4e-103">Create DNS records at eNomCentral for Microsoft</span></span>

 <span data-ttu-id="1bd4e-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="1bd4e-105">Als eNomCentral uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-105">If eNomCentral is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="1bd4e-106">Nadat u deze records bij eNomCentral hebt toevoegen, is uw domein ingesteld voor gebruik met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-106">After you add these records at eNomCentral, your domain will be set up to work with Microsoft services.</span></span>

> [!NOTE]
> <span data-ttu-id="1bd4e-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1bd4e-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="1bd4e-110">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="1bd4e-110">Add a TXT record for verification</span></span>
<span data-ttu-id="1bd4e-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="1bd4e-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="1bd4e-p102">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="1bd4e-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="1bd4e-116">Volg onderstaande stappen of [bekijk de video (start op 0:46)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="1bd4e-116">Follow the steps below or [watch the video (start at 0:46)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>

1. <span data-ttu-id="1bd4e-p104">Als u wilt beginnen, gaat u [via deze koppeling](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) naar uw pagina met domeinen bij eNom Central. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-p104">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. <span data-ttu-id="1bd4e-120">Selecteer **onder mijn domeinen** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-120">Under **my domains**, select the name of the domain that you want to edit.</span></span>

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. <span data-ttu-id="1bd4e-122">Kies in de vervolgkeuzelijst **Manage Domain** de optie **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-122">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>

   ![eNom-BP-Verify-1-1](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)

4. <span data-ttu-id="1bd4e-124">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-124">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

   <span data-ttu-id="1bd4e-125">Kies de **waarde Recordtype** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-125">Choose the **Record Type** value from the drop-down list.</span></span>

   |<span data-ttu-id="1bd4e-126">Hostnaam</span><span class="sxs-lookup"><span data-stu-id="1bd4e-126">Host Name</span></span>|<span data-ttu-id="1bd4e-127">Recordtype</span><span class="sxs-lookup"><span data-stu-id="1bd4e-127">Record Type</span></span>|<span data-ttu-id="1bd4e-128">Adres</span><span class="sxs-lookup"><span data-stu-id="1bd4e-128">Address</span></span>|
   |---|---|---|
   |@|<span data-ttu-id="1bd4e-129">TXT</span><span class="sxs-lookup"><span data-stu-id="1bd4e-129">TXT</span></span>|<span data-ttu-id="1bd4e-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="1bd4e-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="1bd4e-131">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-131">**Note:** This is an example.</span></span> <span data-ttu-id="1bd4e-132">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-132">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="1bd4e-133">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="1bd4e-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|

   ![eNom-BP-Verify-1-2](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)

5. <span data-ttu-id="1bd4e-135">Selecteer **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="1bd4e-135">Select **save**.</span></span>

   ![eNom-BP-Verify-1-3](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)

6. <span data-ttu-id="1bd4e-137">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="1bd4e-138">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft 365 en vraagt u of Microsoft 365 naar de record wil zoeken.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>

<span data-ttu-id="1bd4e-139">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>

1. <span data-ttu-id="1bd4e-140">Ga in het Microsoft-beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="1bd4e-141">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-141">On the **Domains** page, select the domain that you are verifying.</span></span>

3. <span data-ttu-id="1bd4e-142">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-142">On the **Setup** page, select **Start setup**.</span></span>

4. <span data-ttu-id="1bd4e-143">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-143">On the **Verify domain** page, select **Verify**.</span></span>

> [!NOTE]
> <span data-ttu-id="1bd4e-p106">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1bd4e-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="1bd4e-147">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="1bd4e-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="1bd4e-148"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="1bd4e-148"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="1bd4e-149">Volg onderstaande stappen of [bekijk de video (start op 3:40)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="1bd4e-149">Follow the steps below or [watch the video (start at 3:40)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>

1. <span data-ttu-id="1bd4e-p107">Als u wilt beginnen, gaat u [via deze koppeling](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) naar uw pagina met domeinen bij eNom Central. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-p107">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. <span data-ttu-id="1bd4e-153">Selecteer **onder mijn domeinen** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-153">Under **my domains**, select the name of the domain that you want to edit.</span></span>

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. <span data-ttu-id="1bd4e-155">Kies in de vervolgkeuzelijst **Manage Domain** de optie **Email Settings**.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-155">On the **Manage Domain** drop-down list, choose **Email Settings**.</span></span>

   ![eNom-BP-Configure-1-3](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)

4. <span data-ttu-id="1bd4e-157">Kies in de vervolgkeuzelijst **Service Selection** de optie **User (MX)**.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-157">On the **Service Selection** drop-down list, choose **User (MX)**.</span></span>

   ![eNom-BP-Configure-1-4](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)

5. <span data-ttu-id="1bd4e-159">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

   |<span data-ttu-id="1bd4e-160">Hostnaam</span><span class="sxs-lookup"><span data-stu-id="1bd4e-160">Host Name</span></span>|<span data-ttu-id="1bd4e-161">Adres</span><span class="sxs-lookup"><span data-stu-id="1bd4e-161">Address</span></span>|<span data-ttu-id="1bd4e-162">Pref</span><span class="sxs-lookup"><span data-stu-id="1bd4e-162">Pref</span></span>|
   |---|---|---|
   |@| <span data-ttu-id="1bd4e-163">*\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-163">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="1bd4e-164">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="1bd4e-164">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="1bd4e-165">**Opmerking:** Haal uw  *\<domain-key\>*  uit uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-165">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span> [<span data-ttu-id="1bd4e-166">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="1bd4e-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="1bd4e-167">10</span><span class="sxs-lookup"><span data-stu-id="1bd4e-167">10</span></span>  <br/> <span data-ttu-id="1bd4e-168">Zie [Wat is MX-prioriteit?](../setup/domains-faq.yml) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="1bd4e-168">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span>|

   ![eNom-BP-Configure-2-1](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)

6. <span data-ttu-id="1bd4e-170">Selecteer **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="1bd4e-170">Select **save**.</span></span>

   ![eNom-BP-Configure-2-2](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)

7. <span data-ttu-id="1bd4e-172">Als er andere MX-records zijn, schakelt u de selectievakjes voor deze records in om deze te selecteren.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-172">If there are any other existing MX records, select the check boxes for those records to select them.</span></span>

   ![eNom-BP-Configure-2-3](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)

8. <span data-ttu-id="1bd4e-174">Selecteer **delete checked**.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-174">Select **delete checked**.</span></span>

   ![eNom-BP-Configure-2-4](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)

## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="1bd4e-176">De CNAME-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="1bd4e-176">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="1bd4e-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="1bd4e-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="1bd4e-178">Volg onderstaande stappen of [bekijk de video (start op 4:24)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="1bd4e-178">Follow the steps below or [watch the video (start at 4:24)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>

1. <span data-ttu-id="1bd4e-p109">Als u wilt beginnen, gaat u [via deze koppeling](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) naar uw pagina met domeinen bij eNom Central. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-p109">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. <span data-ttu-id="1bd4e-182">Selecteer **onder mijn domeinen** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-182">Under **my domains**, select the name of the domain that you want to edit.</span></span>

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. <span data-ttu-id="1bd4e-184">Kies in de vervolgkeuzelijst **Manage Domain** de optie **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-184">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>

   ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. <span data-ttu-id="1bd4e-186">Selecteer **nieuwe rij**.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-186">Select **new row**.</span></span>

   ![eNom-BP-Configure-3-1](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)

5. <span data-ttu-id="1bd4e-188">Typ of kopieer en plak de volgende waarden in de vakken voor de zes nieuwe records.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-188">In the boxes for the six new records, type or copy and paste the following values.</span></span>

   <span data-ttu-id="1bd4e-189">Kies de **waarde Recordtype** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-189">Choose the **Record Type** value from the drop-down list.</span></span>

   |<span data-ttu-id="1bd4e-190">Hostnaam</span><span class="sxs-lookup"><span data-stu-id="1bd4e-190">Host Name</span></span>|<span data-ttu-id="1bd4e-191">Recordtype</span><span class="sxs-lookup"><span data-stu-id="1bd4e-191">Record Type</span></span>|<span data-ttu-id="1bd4e-192">Adres</span><span class="sxs-lookup"><span data-stu-id="1bd4e-192">Address</span></span>|
   |---|---|---|
   |<span data-ttu-id="1bd4e-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="1bd4e-193">autodiscover</span></span>|<span data-ttu-id="1bd4e-194">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="1bd4e-194">CNAME (Alias)</span></span>|<span data-ttu-id="1bd4e-195">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-195">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="1bd4e-196">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="1bd4e-196">**This value MUST end with a period (.)**</span></span>|
   |<span data-ttu-id="1bd4e-197">sip</span><span class="sxs-lookup"><span data-stu-id="1bd4e-197">sip</span></span>|<span data-ttu-id="1bd4e-198">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="1bd4e-198">CNAME (Alias)</span></span>|<span data-ttu-id="1bd4e-199">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-199">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="1bd4e-200">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="1bd4e-200">**This value MUST end with a period (.)**</span></span>|
   |<span data-ttu-id="1bd4e-201">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="1bd4e-201">lyncdiscover</span></span>|<span data-ttu-id="1bd4e-202">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="1bd4e-202">CNAME (Alias)</span></span>|<span data-ttu-id="1bd4e-203">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="1bd4e-204">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="1bd4e-204">**This value MUST end with a period (.)**</span></span>|
   |<span data-ttu-id="1bd4e-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="1bd4e-205">enterpriseregistration</span></span>|<span data-ttu-id="1bd4e-206">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="1bd4e-206">CNAME (Alias)</span></span>|<span data-ttu-id="1bd4e-207">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="1bd4e-208">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="1bd4e-208">**This value MUST end with a period (.)**</span></span>|
   |<span data-ttu-id="1bd4e-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="1bd4e-209">enterpriseenrollment</span></span>|<span data-ttu-id="1bd4e-210">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="1bd4e-210">CNAME (Alias)</span></span>|<span data-ttu-id="1bd4e-211">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-211">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="1bd4e-212">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="1bd4e-212">**This value MUST end with a period (.)**</span></span>|

   ![eNom-BP-Configure-3-2](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)

6. <span data-ttu-id="1bd4e-214">Selecteer **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="1bd4e-214">Select **save**.</span></span>

   ![eNom-BP-Configure-3-3](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="1bd4e-216">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="1bd4e-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="1bd4e-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="1bd4e-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="1bd4e-218">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="1bd4e-219">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="1bd4e-220">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="1bd4e-221">Voeg in plaats daarvan de vereiste Microsoft-waarden  toe aan de huidige record, zodat u één SPF-record hebt met beide sets waarden.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="1bd4e-222">Volg onderstaande stappen of [bekijk de video (start op 5:12)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="1bd4e-222">Follow the steps below or [watch the video (start at 5:12)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>

1. <span data-ttu-id="1bd4e-p111">Als u wilt beginnen, gaat u [via deze koppeling](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) naar uw pagina met domeinen bij eNom Central. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-p111">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. <span data-ttu-id="1bd4e-226">Selecteer **onder mijn domeinen** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-226">Under **my domains**, select the name of the domain that you want to edit.</span></span>

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. <span data-ttu-id="1bd4e-228">Kies in de vervolgkeuzelijst **Manage Domain** de optie **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-228">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>

   ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. <span data-ttu-id="1bd4e-230">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-230">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

   <span data-ttu-id="1bd4e-231">Kies de **waarde Recordtype** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-231">Choose the **Record Type** value from the drop-down list.</span></span>

   |<span data-ttu-id="1bd4e-232">Hostnaam</span><span class="sxs-lookup"><span data-stu-id="1bd4e-232">Host Name</span></span>|<span data-ttu-id="1bd4e-233">Recordtype</span><span class="sxs-lookup"><span data-stu-id="1bd4e-233">Record Type</span></span>|<span data-ttu-id="1bd4e-234">Adres</span><span class="sxs-lookup"><span data-stu-id="1bd4e-234">Address</span></span>|
   |---|---|---|
   |@|<span data-ttu-id="1bd4e-235">TXT</span><span class="sxs-lookup"><span data-stu-id="1bd4e-235">TXT</span></span>|<span data-ttu-id="1bd4e-236">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="1bd4e-236">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="1bd4e-237">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-237">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>|

   ![eNom-BP-Configure-4-1](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)

5. <span data-ttu-id="1bd4e-239">Selecteer **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="1bd4e-239">Select **save**.</span></span>

   ![eNom-BP-Configure-4-2](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)

## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="1bd4e-241">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="1bd4e-241">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="1bd4e-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="1bd4e-242"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="1bd4e-243">Volg onderstaande stappen of [bekijk de video (start op 5:50)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="1bd4e-243">Follow the steps below or [watch the video (start at 5:50)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>

1. <span data-ttu-id="1bd4e-p112">Als u wilt beginnen, gaat u [via deze koppeling](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) naar uw pagina met domeinen bij eNom Central. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-p112">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. <span data-ttu-id="1bd4e-247">Selecteer **onder mijn domeinen** de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-247">Under **my domains**, select the name of the domain that you want to edit.</span></span>

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. <span data-ttu-id="1bd4e-249">Kies in de vervolgkeuzelijst **Manage Domain** de optie **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-249">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>

   ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. <span data-ttu-id="1bd4e-251">Selecteer rechts van **de nieuwe rij** de optie SRV- of **SPF-record toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="1bd4e-251">To the right of **new row**, select **add SRV or SPF record**.</span></span>

   ![eNom-BP-Configure-5-1](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)

5. <span data-ttu-id="1bd4e-253">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de twee nieuwe records.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-253">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>

   |<span data-ttu-id="1bd4e-254">Service</span><span class="sxs-lookup"><span data-stu-id="1bd4e-254">Service</span></span>|<span data-ttu-id="1bd4e-255">Protocol</span><span class="sxs-lookup"><span data-stu-id="1bd4e-255">Protocol</span></span>|<span data-ttu-id="1bd4e-256">Priority</span><span class="sxs-lookup"><span data-stu-id="1bd4e-256">Priority</span></span>|<span data-ttu-id="1bd4e-257">Gewicht</span><span class="sxs-lookup"><span data-stu-id="1bd4e-257">Weight</span></span>|<span data-ttu-id="1bd4e-258">Poort</span><span class="sxs-lookup"><span data-stu-id="1bd4e-258">Port</span></span>|<span data-ttu-id="1bd4e-259">Doel (Hostnaam)</span><span class="sxs-lookup"><span data-stu-id="1bd4e-259">Target (Hostname)</span></span>|
   |---|---|---|---|---|---|
   |<span data-ttu-id="1bd4e-260">_sip</span><span class="sxs-lookup"><span data-stu-id="1bd4e-260">_sip</span></span>|<span data-ttu-id="1bd4e-261">_tls</span><span class="sxs-lookup"><span data-stu-id="1bd4e-261">_tls</span></span>|<span data-ttu-id="1bd4e-262">100</span><span class="sxs-lookup"><span data-stu-id="1bd4e-262">100</span></span>|<span data-ttu-id="1bd4e-263">1</span><span class="sxs-lookup"><span data-stu-id="1bd4e-263">1</span></span>|<span data-ttu-id="1bd4e-264">443</span><span class="sxs-lookup"><span data-stu-id="1bd4e-264">443</span></span>|<span data-ttu-id="1bd4e-265">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-265">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="1bd4e-266">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="1bd4e-266">**This value MUST end with a period (.)**</span></span>|
   |<span data-ttu-id="1bd4e-267">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="1bd4e-267">_sipfederationtls</span></span>|<span data-ttu-id="1bd4e-268">_tcp</span><span class="sxs-lookup"><span data-stu-id="1bd4e-268">_tcp</span></span>|<span data-ttu-id="1bd4e-269">100</span><span class="sxs-lookup"><span data-stu-id="1bd4e-269">100</span></span>|<span data-ttu-id="1bd4e-270">1</span><span class="sxs-lookup"><span data-stu-id="1bd4e-270">1</span></span>|<span data-ttu-id="1bd4e-271">5061</span><span class="sxs-lookup"><span data-stu-id="1bd4e-271">5061</span></span>|<span data-ttu-id="1bd4e-272">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1bd4e-272">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="1bd4e-273">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="1bd4e-273">**This value MUST end with a period (.)**</span></span>|

   ![eNom-BP-Configure-5-2](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)

6. <span data-ttu-id="1bd4e-275">Opslaan **selecteren**</span><span class="sxs-lookup"><span data-stu-id="1bd4e-275">Select **save**</span></span>

   ![eNom-BP-Configure-5-3](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)

> [!NOTE]
> <span data-ttu-id="1bd4e-p113">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1bd4e-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>