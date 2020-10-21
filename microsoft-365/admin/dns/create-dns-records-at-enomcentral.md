---
title: DNS-records bij eNomCentral maken voor Microsoft
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
description: Lees hoe u uw domein verifieert en DNS-records instelt voor e-mail, Skype voor bedrijven online en andere services op eNomCentral voor Microsoft.
ms.openlocfilehash: c60c33f4be94e2f7719fdfc583500c6d1164991d
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646161"
---
# <a name="create-dns-records-at-enomcentral-for-microsoft"></a><span data-ttu-id="2c1a9-103">DNS-records bij eNomCentral maken voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="2c1a9-103">Create DNS records at eNomCentral for Microsoft</span></span>

 <span data-ttu-id="2c1a9-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="2c1a9-105">Als eNomCentral uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-105">If eNomCentral is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="2c1a9-106">Nadat u deze records bij eNomCentral hebt toegevoegd, is uw domein ingesteld voor gebruik met Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-106">After you add these records at eNomCentral, your domain will be set up to work with Microsoft services.</span></span>

> [!NOTE]
> <span data-ttu-id="2c1a9-p101">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2c1a9-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="2c1a9-110">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="2c1a9-110">Add a TXT record for verification</span></span>
<span data-ttu-id="2c1a9-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="2c1a9-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="2c1a9-p102">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="2c1a9-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>

<span data-ttu-id="2c1a9-116">Volg onderstaande stappen of [bekijk de video (start op 0:46)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="2c1a9-116">Follow the steps below or [watch the video (start at 0:46)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>

1. <span data-ttu-id="2c1a9-p104">Als u wilt beginnen, gaat u [via deze koppeling](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) naar uw pagina met domeinen bij eNom Central. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-p104">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>

   ![eNom voor 1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. <span data-ttu-id="2c1a9-120">Selecteer onder **My Domains**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-120">Under **my domains**, select the name of the domain that you want to edit.</span></span>

   ![eNom voor 1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. <span data-ttu-id="2c1a9-122">Kies in de vervolgkeuzelijst **Manage Domain** de optie **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-122">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>

   ![eNom voor 1-1](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)

4. <span data-ttu-id="2c1a9-124">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-124">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

   <span data-ttu-id="2c1a9-125">Kies in de vervolgkeuzelijst de waarde **record type** .</span><span class="sxs-lookup"><span data-stu-id="2c1a9-125">Choose the **Record Type** value from the drop-down list.</span></span>

   |<span data-ttu-id="2c1a9-126">Host name</span><span class="sxs-lookup"><span data-stu-id="2c1a9-126">Host Name</span></span>|<span data-ttu-id="2c1a9-127">Recordtype</span><span class="sxs-lookup"><span data-stu-id="2c1a9-127">Record Type</span></span>|<span data-ttu-id="2c1a9-128">Adres</span><span class="sxs-lookup"><span data-stu-id="2c1a9-128">Address</span></span>|
   |---|---|---|
   |@|<span data-ttu-id="2c1a9-129">TXT</span><span class="sxs-lookup"><span data-stu-id="2c1a9-129">TXT</span></span>|<span data-ttu-id="2c1a9-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="2c1a9-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="2c1a9-131">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-131">**Note:** This is an example.</span></span> <span data-ttu-id="2c1a9-132">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-132">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="2c1a9-133">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="2c1a9-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|

   ![eNom voor 1-2](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)

5. <span data-ttu-id="2c1a9-135">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-135">Select **save**.</span></span>

   ![eNom voor 1-3](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)

6. <span data-ttu-id="2c1a9-137">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>

<span data-ttu-id="2c1a9-138">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft 365 en vraagt u of Microsoft 365 naar de record wil zoeken.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>

<span data-ttu-id="2c1a9-139">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>

1. <span data-ttu-id="2c1a9-140">Ga in het Microsoft-beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="2c1a9-141">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-141">On the **Domains** page, select the domain that you are verifying.</span></span>

3. <span data-ttu-id="2c1a9-142">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-142">On the **Setup** page, select **Start setup**.</span></span>

4. <span data-ttu-id="2c1a9-143">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-143">On the **Verify domain** page, select **Verify**.</span></span>

> [!NOTE]
> <span data-ttu-id="2c1a9-p106">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2c1a9-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="2c1a9-147">Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="2c1a9-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="2c1a9-148"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="2c1a9-148"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="2c1a9-149">Volg onderstaande stappen of [bekijk de video (start op 3:40)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="2c1a9-149">Follow the steps below or [watch the video (start at 3:40)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>

1. <span data-ttu-id="2c1a9-p107">Als u wilt beginnen, gaat u [via deze koppeling](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) naar uw pagina met domeinen bij eNom Central. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-p107">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>

   ![eNom voor 1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. <span data-ttu-id="2c1a9-153">Selecteer onder **My Domains**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-153">Under **my domains**, select the name of the domain that you want to edit.</span></span>

   ![eNom voor 1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. <span data-ttu-id="2c1a9-155">Kies in de vervolgkeuzelijst **Manage Domain** de optie **Email Settings**.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-155">On the **Manage Domain** drop-down list, choose **Email Settings**.</span></span>

   ![eNom voor 1-3](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)

4. <span data-ttu-id="2c1a9-157">Kies in de vervolgkeuzelijst **Service Selection** de optie **User (MX)**.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-157">On the **Service Selection** drop-down list, choose **User (MX)**.</span></span>

   ![eNom voor 1-4](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)

5. <span data-ttu-id="2c1a9-159">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

   |<span data-ttu-id="2c1a9-160">Host name</span><span class="sxs-lookup"><span data-stu-id="2c1a9-160">Host Name</span></span>|<span data-ttu-id="2c1a9-161">Adres</span><span class="sxs-lookup"><span data-stu-id="2c1a9-161">Address</span></span>|<span data-ttu-id="2c1a9-162">Pref</span><span class="sxs-lookup"><span data-stu-id="2c1a9-162">Pref</span></span>|
   |---|---|---|
   |@| <span data-ttu-id="2c1a9-163">*\<domain-key\>*  . mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-163">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="2c1a9-164">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="2c1a9-164">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="2c1a9-165">**Opmerking:** Neem uw  *\<domain-key\>*  van uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-165">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span> [<span data-ttu-id="2c1a9-166">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="2c1a9-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="2c1a9-167">10</span><span class="sxs-lookup"><span data-stu-id="2c1a9-167">10</span></span>  <br/> <span data-ttu-id="2c1a9-168">Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit.   </span><span class="sxs-lookup"><span data-stu-id="2c1a9-168">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span>|

   ![eNom voor 2-1](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)

6. <span data-ttu-id="2c1a9-170">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-170">Select **save**.</span></span>

   ![eNom voor 2-2](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)

7. <span data-ttu-id="2c1a9-172">Als er andere MX-records zijn, schakelt u de selectievakjes voor deze records in om deze te selecteren.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-172">If there are any other existing MX records, select the check boxes for those records to select them.</span></span>

   ![eNom voor 2-3](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)

8. <span data-ttu-id="2c1a9-174">Selecteer **Delete checked**.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-174">Select **delete checked**.</span></span>

   ![eNom voor 2-4](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)

## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="2c1a9-176">De CNAME-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="2c1a9-176">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="2c1a9-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="2c1a9-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="2c1a9-178">Volg onderstaande stappen of [bekijk de video (start op 4:24)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="2c1a9-178">Follow the steps below or [watch the video (start at 4:24)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>

1. <span data-ttu-id="2c1a9-p109">Als u wilt beginnen, gaat u [via deze koppeling](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) naar uw pagina met domeinen bij eNom Central. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-p109">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>

   ![eNom voor 1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. <span data-ttu-id="2c1a9-182">Selecteer onder **My Domains**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-182">Under **my domains**, select the name of the domain that you want to edit.</span></span>

   ![eNom voor 1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. <span data-ttu-id="2c1a9-184">Kies in de vervolgkeuzelijst **Manage Domain** de optie **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-184">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>

   ![eNom voor 1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. <span data-ttu-id="2c1a9-186">Selecteer **nieuwe rij**.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-186">Select **new row**.</span></span>

   ![eNom voor 3-1](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)

5. <span data-ttu-id="2c1a9-188">Typ of kopieer en plak de volgende waarden in de vakken voor de zes nieuwe records.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-188">In the boxes for the six new records, type or copy and paste the following values.</span></span>

   <span data-ttu-id="2c1a9-189">Kies in de vervolgkeuzelijst de waarde **record type** .</span><span class="sxs-lookup"><span data-stu-id="2c1a9-189">Choose the **Record Type** value from the drop-down list.</span></span>

   |<span data-ttu-id="2c1a9-190">Host name</span><span class="sxs-lookup"><span data-stu-id="2c1a9-190">Host Name</span></span>|<span data-ttu-id="2c1a9-191">Recordtype</span><span class="sxs-lookup"><span data-stu-id="2c1a9-191">Record Type</span></span>|<span data-ttu-id="2c1a9-192">Adres</span><span class="sxs-lookup"><span data-stu-id="2c1a9-192">Address</span></span>|
   |---|---|---|
   |<span data-ttu-id="2c1a9-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="2c1a9-193">autodiscover</span></span>|<span data-ttu-id="2c1a9-194">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="2c1a9-194">CNAME (Alias)</span></span>|<span data-ttu-id="2c1a9-195">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-195">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="2c1a9-196">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="2c1a9-196">**This value MUST end with a period (.)**</span></span>|
   |<span data-ttu-id="2c1a9-197">sip</span><span class="sxs-lookup"><span data-stu-id="2c1a9-197">sip</span></span>|<span data-ttu-id="2c1a9-198">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="2c1a9-198">CNAME (Alias)</span></span>|<span data-ttu-id="2c1a9-199">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-199">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="2c1a9-200">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="2c1a9-200">**This value MUST end with a period (.)**</span></span>|
   |<span data-ttu-id="2c1a9-201">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="2c1a9-201">lyncdiscover</span></span>|<span data-ttu-id="2c1a9-202">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="2c1a9-202">CNAME (Alias)</span></span>|<span data-ttu-id="2c1a9-203">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-203">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="2c1a9-204">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="2c1a9-204">**This value MUST end with a period (.)**</span></span>|
   |<span data-ttu-id="2c1a9-205">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="2c1a9-205">enterpriseregistration</span></span>|<span data-ttu-id="2c1a9-206">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="2c1a9-206">CNAME (Alias)</span></span>|<span data-ttu-id="2c1a9-207">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-207">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="2c1a9-208">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="2c1a9-208">**This value MUST end with a period (.)**</span></span>|
   |<span data-ttu-id="2c1a9-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="2c1a9-209">enterpriseenrollment</span></span>|<span data-ttu-id="2c1a9-210">CNAME (alias)</span><span class="sxs-lookup"><span data-stu-id="2c1a9-210">CNAME (Alias)</span></span>|<span data-ttu-id="2c1a9-211">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-211">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="2c1a9-212">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="2c1a9-212">**This value MUST end with a period (.)**</span></span>|

   ![eNom voor 3-2](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)

6. <span data-ttu-id="2c1a9-214">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-214">Select **save**.</span></span>

   ![eNom voor 3-3](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="2c1a9-216">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="2c1a9-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="2c1a9-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="2c1a9-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="2c1a9-218">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="2c1a9-219">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="2c1a9-220">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="2c1a9-221">In plaats daarvan voegt u de vereiste Microsoft-waarden toe aan de huidige record, zodat u  *één*  SPF-record hebt die beide sets met waarden bevat.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>

<span data-ttu-id="2c1a9-222">Volg onderstaande stappen of [bekijk de video (start op 5:12)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="2c1a9-222">Follow the steps below or [watch the video (start at 5:12)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>

1. <span data-ttu-id="2c1a9-p111">Als u wilt beginnen, gaat u [via deze koppeling](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) naar uw pagina met domeinen bij eNom Central. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-p111">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>

   ![eNom voor 1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. <span data-ttu-id="2c1a9-226">Selecteer onder **My Domains**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-226">Under **my domains**, select the name of the domain that you want to edit.</span></span>

   ![eNom voor 1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. <span data-ttu-id="2c1a9-228">Kies in de vervolgkeuzelijst **Manage Domain** de optie **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-228">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>

   ![eNom voor 1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. <span data-ttu-id="2c1a9-230">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-230">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>

   <span data-ttu-id="2c1a9-231">Kies in de vervolgkeuzelijst de waarde **record type** .</span><span class="sxs-lookup"><span data-stu-id="2c1a9-231">Choose the **Record Type** value from the drop-down list.</span></span>

   |<span data-ttu-id="2c1a9-232">Host name</span><span class="sxs-lookup"><span data-stu-id="2c1a9-232">Host Name</span></span>|<span data-ttu-id="2c1a9-233">Recordtype</span><span class="sxs-lookup"><span data-stu-id="2c1a9-233">Record Type</span></span>|<span data-ttu-id="2c1a9-234">Adres</span><span class="sxs-lookup"><span data-stu-id="2c1a9-234">Address</span></span>|
   |---|---|---|
   |@|<span data-ttu-id="2c1a9-235">TXT</span><span class="sxs-lookup"><span data-stu-id="2c1a9-235">TXT</span></span>|<span data-ttu-id="2c1a9-236">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="2c1a9-236">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="2c1a9-237">**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-237">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>|

   ![eNom voor 4-1](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)

5. <span data-ttu-id="2c1a9-239">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-239">Select **save**.</span></span>

   ![eNom voor 4-2](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)

## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="2c1a9-241">De twee SRV-records toevoegen die zijn vereist voor Microsoft</span><span class="sxs-lookup"><span data-stu-id="2c1a9-241">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="2c1a9-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="2c1a9-242"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="2c1a9-243">Volg onderstaande stappen of [bekijk de video (start op 5:50)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span><span class="sxs-lookup"><span data-stu-id="2c1a9-243">Follow the steps below or [watch the video (start at 5:50)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).</span></span>

1. <span data-ttu-id="2c1a9-p112">Als u wilt beginnen, gaat u [via deze koppeling](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) naar uw pagina met domeinen bij eNom Central. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-p112">To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.</span></span>

   ![eNom voor 1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. <span data-ttu-id="2c1a9-247">Selecteer onder **My Domains**de naam van het domein dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-247">Under **my domains**, select the name of the domain that you want to edit.</span></span>

   ![eNom voor 1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. <span data-ttu-id="2c1a9-249">Kies in de vervolgkeuzelijst **Manage Domain** de optie **Host Records**.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-249">On the **Manage Domain** drop-down list, choose **Host Records**.</span></span>

   ![eNom voor 1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. <span data-ttu-id="2c1a9-251">Selecteer aan de rechterkant van **nieuwe rij**de optie **SRV-of SPF-record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-251">To the right of **new row**, select **add SRV or SPF record**.</span></span>

   ![eNom voor 5-1](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)

5. <span data-ttu-id="2c1a9-253">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de twee nieuwe records.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-253">In the boxes for the two new records, type or copy and paste the values from the following table.</span></span>

   |<span data-ttu-id="2c1a9-254">Service</span><span class="sxs-lookup"><span data-stu-id="2c1a9-254">Service</span></span>|<span data-ttu-id="2c1a9-255">Protocol</span><span class="sxs-lookup"><span data-stu-id="2c1a9-255">Protocol</span></span>|<span data-ttu-id="2c1a9-256">Priority</span><span class="sxs-lookup"><span data-stu-id="2c1a9-256">Priority</span></span>|<span data-ttu-id="2c1a9-257">Dikte</span><span class="sxs-lookup"><span data-stu-id="2c1a9-257">Weight</span></span>|<span data-ttu-id="2c1a9-258">Poort</span><span class="sxs-lookup"><span data-stu-id="2c1a9-258">Port</span></span>|<span data-ttu-id="2c1a9-259">Doel (hostnaam)</span><span class="sxs-lookup"><span data-stu-id="2c1a9-259">Target (Hostname)</span></span>|
   |---|---|---|---|---|---|
   |<span data-ttu-id="2c1a9-260">_sip</span><span class="sxs-lookup"><span data-stu-id="2c1a9-260">_sip</span></span>|<span data-ttu-id="2c1a9-261">_tls</span><span class="sxs-lookup"><span data-stu-id="2c1a9-261">_tls</span></span>|<span data-ttu-id="2c1a9-262">100</span><span class="sxs-lookup"><span data-stu-id="2c1a9-262">100</span></span>|<span data-ttu-id="2c1a9-263">1</span><span class="sxs-lookup"><span data-stu-id="2c1a9-263">1</span></span>|<span data-ttu-id="2c1a9-264">443</span><span class="sxs-lookup"><span data-stu-id="2c1a9-264">443</span></span>|<span data-ttu-id="2c1a9-265">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-265">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="2c1a9-266">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="2c1a9-266">**This value MUST end with a period (.)**</span></span>|
   |<span data-ttu-id="2c1a9-267">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="2c1a9-267">_sipfederationtls</span></span>|<span data-ttu-id="2c1a9-268">_tcp</span><span class="sxs-lookup"><span data-stu-id="2c1a9-268">_tcp</span></span>|<span data-ttu-id="2c1a9-269">100</span><span class="sxs-lookup"><span data-stu-id="2c1a9-269">100</span></span>|<span data-ttu-id="2c1a9-270">1</span><span class="sxs-lookup"><span data-stu-id="2c1a9-270">1</span></span>|<span data-ttu-id="2c1a9-271">5061</span><span class="sxs-lookup"><span data-stu-id="2c1a9-271">5061</span></span>|<span data-ttu-id="2c1a9-272">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="2c1a9-272">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="2c1a9-273">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="2c1a9-273">**This value MUST end with a period (.)**</span></span>|

   ![eNom voor 5-2](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)

6. <span data-ttu-id="2c1a9-275">Selecteer **Opslaan** .</span><span class="sxs-lookup"><span data-stu-id="2c1a9-275">Select **save**</span></span>

   ![eNom voor 5-3](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)

> [!NOTE]
> <span data-ttu-id="2c1a9-p113">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2c1a9-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
