---
title: DNS-records voor Office 365 maken met Windows-DNS
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
ms.assetid: 9eec911d-5773-422c-9593-40e1147ffbde
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services op windows-gebaseerde DNS voor Office 365.
ms.openlocfilehash: d33a2f79111f8951c3ec31ca5680877ad2e7d570
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210562"
---
# <a name="create-dns-records-for-office-365-using-windows-based-dns"></a><span data-ttu-id="d898f-103">DNS-records voor Office 365 maken met Windows-DNS</span><span class="sxs-lookup"><span data-stu-id="d898f-103">Create DNS records for Office 365 using Windows-based DNS</span></span>

 <span data-ttu-id="d898f-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="d898f-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
   
<span data-ttu-id="d898f-105">Als u uw eigen DNS-records met Windows-DNS host, volgt u de stappen in dit artikel voor het instellen van uw records voor e-mail, Skype voor Bedrijven Online, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="d898f-105">If you host your own DNS records using Windows-based DNS, follow the steps in this article to set up your records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="d898f-106">Om aan de slag te gaan, moet u [uw DNS-records vinden in Windows-gebaseerde DNS,](#find-your-dns-records-in-windows-based-dns) zodat u ze bijwerken.</span><span class="sxs-lookup"><span data-stu-id="d898f-106">To get started, you need to [find your DNS records in Windows-based DNS](#find-your-dns-records-in-windows-based-dns) so you can update them.</span></span> <span data-ttu-id="d898f-107">Zie [Niet-routeerbaar e-mailadres dat als UPN wordt gebruikt in uw active directory voor het gebruik van vooraf.](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory)</span><span class="sxs-lookup"><span data-stu-id="d898f-107">Also, if you're planning to synchronize your on-premises Active Directory with Office 365, see [Non-routable email address used as a UPN in your on-prem Active Directory](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory).</span></span>
  
<span data-ttu-id="d898f-108">Problemen met e-mailstroom of andere problemen na het toevoegen van DNS-records, zie [Problemen oplossen na het wijzigen van uw domeinnaam of DNS-records.](../get-help-with-domains/find-and-fix-issues.md)</span><span class="sxs-lookup"><span data-stu-id="d898f-108">Trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a><span data-ttu-id="d898f-109">Uw DNS-records vinden in Windows-DNS</span><span class="sxs-lookup"><span data-stu-id="d898f-109">Find your DNS records in Windows-based DNS</span></span>
<span data-ttu-id="d898f-110"><a name="BKMK_find_your_dns_1"> </a> Ga naar de pagina met de DNS-records voor uw domein.</span><span class="sxs-lookup"><span data-stu-id="d898f-110"><a name="BKMK_find_your_dns_1"> </a> Go to the page that has the DNS records for your domain.</span></span> <span data-ttu-id="d898f-111">Als u in Windows Server 2008 werkt, gaat u naar **Uitvoeren starten.** > **Run**</span><span class="sxs-lookup"><span data-stu-id="d898f-111">If you're working in Windows Server 2008, go to **Start** > **Run**.</span></span> <span data-ttu-id="d898f-112">Als u in Windows Server 2012 werkt, drukt u op de Windows-toets en **r**.</span><span class="sxs-lookup"><span data-stu-id="d898f-112">If you're working in Windows Server 2012, press the Windows key and **r**.</span></span> <span data-ttu-id="d898f-113">Typ **dnsmgmnt.msc**en selecteer **OK**.</span><span class="sxs-lookup"><span data-stu-id="d898f-113">Type **dnsmgmnt.msc**, and then select **OK**.</span></span> <span data-ttu-id="d898f-114">Vouw in DNS-beheer \*\* \<DNS-servernaam\> \> Forward Lookup Zones  \*\*uit.</span><span class="sxs-lookup"><span data-stu-id="d898f-114">In DNS Manager, expand **\<DNS server name\>  \> Forward Lookup Zones**.</span></span> <span data-ttu-id="d898f-115">Selecteer uw domein.</span><span class="sxs-lookup"><span data-stu-id="d898f-115">Select your domain.</span></span> <span data-ttu-id="d898f-116">Nu kunt u de DNS-records gaan maken.</span><span class="sxs-lookup"><span data-stu-id="d898f-116">You're now ready to create the DNS records.</span></span>
   
## <a name="add-mx-record"></a><span data-ttu-id="d898f-117">MX-record toevoegen</span><span class="sxs-lookup"><span data-stu-id="d898f-117">Add MX record</span></span>
<span data-ttu-id="d898f-118"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="d898f-118"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="d898f-119">Voeg een MX-record toe zodat e-mail voor uw domein naar Office 365 wordt verzonden.</span><span class="sxs-lookup"><span data-stu-id="d898f-119">Add an MX record so email for your domain will come to Office 365.</span></span>
- <span data-ttu-id="d898f-120">De MX-record die u toevoegt, bevat een waarde (de waarde **Adres waarnaar wordt verwezen**) die er ongeveer zo uitziet: \<MX token\>.mail.protection.outlook.com, waarbij \<MX-token\> een waarde is zoals MSxxxxxxx.</span><span class="sxs-lookup"><span data-stu-id="d898f-120">The MX record you'll add includes a value (the **Points to address** value) that looks something like this: \<MX token\>.mail.protection.outlook.com, where \<MX token\> is a value like MSxxxxxxx.</span></span> 
- <span data-ttu-id="d898f-121">Kopieer de waarde die wordt vermeld onder Adres punten naar adres in de rij MX in de sectie Exchange Online van de pagina DNS-records toevoegen in Office 365.</span><span class="sxs-lookup"><span data-stu-id="d898f-121">From the MX row in the Exchange Online section of the Add DNS records page in Office 365, copy the value listed under Points to address.</span></span> <span data-ttu-id="d898f-122">U gebruikt deze waarde in de record die u in deze taak maakt.</span><span class="sxs-lookup"><span data-stu-id="d898f-122">You'll use this value in the record you're creating in this task.</span></span> 
- <span data-ttu-id="d898f-123">Ga op de pagina DNS-beheer voor het domein naar **Action** > **Mail Exchanger (MX)**.</span><span class="sxs-lookup"><span data-stu-id="d898f-123">On the DNS Manager page for the domain, go to **Action** > **Mail Exchanger (MX)**.</span></span> <span data-ttu-id="d898f-124">Zie [Uw DNS-records zoeken in windows-gebaseerde DNS](#find-your-dns-records-in-windows-based-dns)voor het domein om deze pagina voor het domein te vinden.</span><span class="sxs-lookup"><span data-stu-id="d898f-124">To find this page for the domain, see [Find your DNS records in Windows-based DNS](#find-your-dns-records-in-windows-based-dns).</span></span>  
- <span data-ttu-id="d898f-125">Controleer in het dialoogvenster **Nieuwe bronrecord** of de velden zijn ingesteld op precies de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="d898f-125">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span> 
    - <span data-ttu-id="d898f-126">Host Name: </span><span class="sxs-lookup"><span data-stu-id="d898f-126">Host Name:</span></span> 
    - <span data-ttu-id="d898f-127">@Address: Plak hier de adreswaarde aan adres die u zojuist hebt gekopieerd uit Office 365.</span><span class="sxs-lookup"><span data-stu-id="d898f-127">@Address: Paste the Points to address  value that you just copied from Office 365 here.</span></span>  
    - <span data-ttu-id="d898f-128">Pref:</span><span class="sxs-lookup"><span data-stu-id="d898f-128">Pref:</span></span> 
- <span data-ttu-id="d898f-129">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="d898f-129">Select **Save Changes**.</span></span>
- <span data-ttu-id="d898f-130">Verouderde MX-records verwijderen.</span><span class="sxs-lookup"><span data-stu-id="d898f-130">Remove any obsolete MX records.</span></span> <span data-ttu-id="d898f-131">Als u oude MX-records voor dit domein hebt die e-mail ergens anders routeren, schakelt u het selectievakje naast elke oude record in en selecteert u **Ok verwijderen.** > **OK**</span><span class="sxs-lookup"><span data-stu-id="d898f-131">If you have any old MX records for this domain that route email somewhere else, select the check box next to each old record, and then select **Delete** > **OK**.</span></span> 
   
## <a name="add-cname-records"></a><span data-ttu-id="d898f-132">CNAME-records toevoegen</span><span class="sxs-lookup"><span data-stu-id="d898f-132">Add CNAME records</span></span>
<span data-ttu-id="d898f-133"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="d898f-133"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="d898f-134">Voeg de CNAME-records toe die voor Office 365 zijn vereist.</span><span class="sxs-lookup"><span data-stu-id="d898f-134">Add the CNAME records that are required for Office 365.</span></span> <span data-ttu-id="d898f-135">Als er extra CNAME-records worden weergegeven in Office 365, voegt u die toe aan de hand van dezelfde algemene stappen die hier worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d898f-135">If additional CNAME records are listed in Office 365, add those following the same general steps shown here.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d898f-136">Als u Mobile Device Management (MDM) voor Office 365 hebt, moet u twee extra CNAME-records maken.</span><span class="sxs-lookup"><span data-stu-id="d898f-136">If you have Mobile Device Management (MDM) for Office 365, then you must create two additional CNAME records.</span></span> <span data-ttu-id="d898f-137">Volg de stappen die u hebt gevolgd voor de andere vier CNAME-records, maar gebruik de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="d898f-137">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="d898f-138">(Als u geen MDM hebt, u deze stap overslaan.)</span><span class="sxs-lookup"><span data-stu-id="d898f-138">(If you do not have MDM, you can skip this step.)</span></span> 

- <span data-ttu-id="d898f-139">Ga op de pagina DNS-beheer voor het domein naar **Action** > **CNAME (CNAME).**</span><span class="sxs-lookup"><span data-stu-id="d898f-139">On the DNS Manager page for the domain, go to **Action** > **CNAME (CNAME)**.</span></span>
- <span data-ttu-id="d898f-140">Controleer in het dialoogvenster **Nieuwe bronrecord** of de velden zijn ingesteld op precies de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="d898f-140">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="d898f-141">Host naam: autodiscover</span><span class="sxs-lookup"><span data-stu-id="d898f-141">Host Name: autodiscover</span></span>
    - <span data-ttu-id="d898f-142">Type:</span><span class="sxs-lookup"><span data-stu-id="d898f-142">Type:</span></span> 
    - <span data-ttu-id="d898f-143">CNAMEAddress: autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="d898f-143">CNAMEAddress: autodiscover.outlook.com</span></span>
- <span data-ttu-id="d898f-144">Selecteer **O**K.</span><span class="sxs-lookup"><span data-stu-id="d898f-144">Select **O**K.</span></span>

<span data-ttu-id="d898f-145">Voeg de SIP CNAME-record toe.</span><span class="sxs-lookup"><span data-stu-id="d898f-145">Add the SIP CNAME record.</span></span> 
- <span data-ttu-id="d898f-146">Ga op de pagina DNS-beheer voor het domein naar **Action** \> **CNAME (CNAME).**</span><span class="sxs-lookup"><span data-stu-id="d898f-146">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> 
- <span data-ttu-id="d898f-147">Controleer in het dialoogvenster **Nieuwe bronrecord** of de velden zijn ingesteld op precies de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="d898f-147">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="d898f-148">Host naam: sip</span><span class="sxs-lookup"><span data-stu-id="d898f-148">Host Name: sip</span></span>
    - <span data-ttu-id="d898f-149">Type: CNAME</span><span class="sxs-lookup"><span data-stu-id="d898f-149">Type: CNAME</span></span>
    - <span data-ttu-id="d898f-150">Adres: sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d898f-150">Address: sipdir.online.lync.com</span></span>
- <span data-ttu-id="d898f-151">Kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="d898f-151">Select **OK**.</span></span>

<span data-ttu-id="d898f-152">Voeg de Skype voor Bedrijven Online Autodiscover CNAME-record toe.</span><span class="sxs-lookup"><span data-stu-id="d898f-152">Add the Skype for Business Online Autodiscover CNAME record.</span></span>  
- <span data-ttu-id="d898f-153">Ga op de pagina DNS-beheer voor het domein naar **Action** \> **CNAME (CNAME).**</span><span class="sxs-lookup"><span data-stu-id="d898f-153">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> <span data-ttu-id="d898f-154">Controleer in het dialoogvenster **Nieuwe bronrecord** of de velden zijn ingesteld op precies de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="d898f-154">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="d898f-155">Host naam: lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="d898f-155">Host Name: lyncdiscover</span></span>
    - <span data-ttu-id="d898f-156">Type: CNAME</span><span class="sxs-lookup"><span data-stu-id="d898f-156">Type: CNAME</span></span>
    - <span data-ttu-id="d898f-157">Adres: webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d898f-157">Address: webdir.online.lync.com</span></span>
- <span data-ttu-id="d898f-158">Kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="d898f-158">Select **OK**.</span></span>
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-office-365"></a><span data-ttu-id="d898f-159">Twee CNAME-records voor MDM (Mobile Device Management) voor Office 365 toevoegen</span><span class="sxs-lookup"><span data-stu-id="d898f-159">Add two CNAME records for Mobile Device Management (MDM) for Office 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d898f-160">Als u Mobile Device Management (MDM) voor Office 365 hebt, moet u twee extra CNAME-records maken.</span><span class="sxs-lookup"><span data-stu-id="d898f-160">If you have Mobile Device Management (MDM) for Office 365, then you must create two additional CNAME records.</span></span> <span data-ttu-id="d898f-161">Volg de stappen die u hebt gevolgd voor de andere vier CNAME-records, maar gebruik de waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="d898f-161">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> <span data-ttu-id="d898f-162">>(Als u geen MDM hebt, u deze stap overslaan.)</span><span class="sxs-lookup"><span data-stu-id="d898f-162">>(If you do not have MDM, you can skip this step.)</span></span> 
  

<span data-ttu-id="d898f-163">Voeg de MDM Enterpriseregistration CNAME-record toe.</span><span class="sxs-lookup"><span data-stu-id="d898f-163">Add the MDM Enterpriseregistration CNAME record.</span></span>  
- <span data-ttu-id="d898f-164">Ga op de pagina DNS-beheer voor het domein naar **Action** \> **CNAME (CNAME).**</span><span class="sxs-lookup"><span data-stu-id="d898f-164">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> 
- <span data-ttu-id="d898f-165">Controleer in het dialoogvenster **Nieuwe bronrecord** of de velden zijn ingesteld op precies de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="d898f-165">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
- <span data-ttu-id="d898f-166">Host name: enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="d898f-166">Host Name: enterpriseregistration</span></span>
- <span data-ttu-id="d898f-167">Type: CNAME</span><span class="sxs-lookup"><span data-stu-id="d898f-167">Type: CNAME</span></span>
- <span data-ttu-id="d898f-168">Adres: enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="d898f-168">Address: enterpriseregistration.windows.net</span></span>
- <span data-ttu-id="d898f-169">Kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="d898f-169">Select **OK**.</span></span> 

<span data-ttu-id="d898f-170">Voeg de MDM Enterpriseenrollment CNAME-record toe.</span><span class="sxs-lookup"><span data-stu-id="d898f-170">Add the MDM Enterpriseenrollment CNAME record.</span></span> 
-  <span data-ttu-id="d898f-171">Ga op de pagina DNS-beheer voor het domein naar **Action** \> **CNAME (CNAME).**</span><span class="sxs-lookup"><span data-stu-id="d898f-171">On the DNS Manager page for the domain, go to **Action** \> **CNAME (CNAME)**.</span></span> 
-  <span data-ttu-id="d898f-172">Controleer in het dialoogvenster **Nieuwe bronrecord** of de velden zijn ingesteld op precies de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="d898f-172">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    - <span data-ttu-id="d898f-173">Hostnaam: inschrijving voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="d898f-173">Host Name: enterpriseenrollment</span></span>
    - <span data-ttu-id="d898f-174">Type: CNAME</span><span class="sxs-lookup"><span data-stu-id="d898f-174">Type: CNAME</span></span>
    - <span data-ttu-id="d898f-175">Adres: enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d898f-175">Address: enterpriseenrollment-s.manage.microsoft.com</span></span>
- <span data-ttu-id="d898f-176">Kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="d898f-176">Select **OK**.</span></span>
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="d898f-177">Een TXT-record voor SPF toevoegen om spam tegen te gaan</span><span class="sxs-lookup"><span data-stu-id="d898f-177">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="d898f-178"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="d898f-178"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="d898f-179">U kunt maximaal 1 TXT-record hebben voor SPF voor een domein.</span><span class="sxs-lookup"><span data-stu-id="d898f-179">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="d898f-180">Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen.</span><span class="sxs-lookup"><span data-stu-id="d898f-180">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="d898f-181">Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Office 365 te maken.</span><span class="sxs-lookup"><span data-stu-id="d898f-181">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="d898f-182">In plaats daarvan voegt u de vereiste Office 365-waarden toe aan de huidige record, zodat u beschikt over  *één*  SPF-record waarin beide sets waarden zijn opgenomen.</span><span class="sxs-lookup"><span data-stu-id="d898f-182">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="d898f-183">Voeg de SPF TXT-record voor uw domein om spam te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="d898f-183">Add the SPF TXT record for your domain to help prevent email spam.</span></span>
  
- <span data-ttu-id="d898f-p111">Mogelijk hebt u al andere tekenreeksen in de TXT-waarde voor deze record (zoals tekenreeksen voor marketing-e-mail). Dit is geen probleem. Laat deze tekenreeksen staan en voeg deze toe, plaats dubbele aanhalingstekens rond elke tekenreeks om ze te scheiden.</span><span class="sxs-lookup"><span data-stu-id="d898f-p111">You might already have other strings in the TXT value for this record (such as strings for marketing email), which is fine. Leave those strings in place and add this one, placing double-quotes around each string to separate them.</span></span> 
- <span data-ttu-id="d898f-186">Ga op de pagina DNS-beheer voor uw domein naar **Actietekst** \> **(TXT).**</span><span class="sxs-lookup"><span data-stu-id="d898f-186">On the DNS Manager page for your domain, go to **Action** \> **Text (TXT)**.</span></span> 
-  <span data-ttu-id="d898f-187">Controleer in het dialoogvenster **Nieuwe bronrecord** of de velden zijn ingesteld op precies de volgende waarden.</span><span class="sxs-lookup"><span data-stu-id="d898f-187">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values.</span></span> 
 > [!IMPORTANT]
> <span data-ttu-id="d898f-188">In sommige versies van Windows DNS Manager is het mogelijk dat het domein zo is ingesteld dat wanneer u een txt-record maakt, de thuisnaam standaard wordt ingesteld op het bovenliggende domein.</span><span class="sxs-lookup"><span data-stu-id="d898f-188">In some versions of Windows DNS Manager, the domain may have been set up so that when you create a txt record, the home name defaults to the parent domain.</span></span> <span data-ttu-id="d898f-189">Als u in deze situatie een TXT-record toevoegt, stelt u de hostnaam in op leeg (geen waarde) in plaats van op @ of de domeinnaam.</span><span class="sxs-lookup"><span data-stu-id="d898f-189">In this situation, when adding a TXT record, set the host name to blank (no value) instead of setting it to @ or the domain name.</span></span> 

-  <span data-ttu-id="d898f-190">Hosttype: @</span><span class="sxs-lookup"><span data-stu-id="d898f-190">Host type: @</span></span>
-  <span data-ttu-id="d898f-191">Recordtype: TXT</span><span class="sxs-lookup"><span data-stu-id="d898f-191">Record Type: TXT</span></span>
-  <span data-ttu-id="d898f-192">Adres: v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="d898f-192">Address: v=spf1 include:spf.protection.outlook.com -all</span></span> 
         
-  <span data-ttu-id="d898f-193">Kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="d898f-193">Select **OK**.</span></span>
   
## <a name="add-srv-records"></a><span data-ttu-id="d898f-194">SRV-records toevoegen</span><span class="sxs-lookup"><span data-stu-id="d898f-194">Add SRV records</span></span>
<span data-ttu-id="d898f-195"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="d898f-195"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="d898f-196">Voeg de twee SRV-records toe die voor Office 365 zijn vereist.</span><span class="sxs-lookup"><span data-stu-id="d898f-196">Add the two SRV records that are required for Office 365.</span></span>

<span data-ttu-id="d898f-197">Voeg de SIP SRV-record voor Skype voor Bedrijven Online-webconferenties toe.</span><span class="sxs-lookup"><span data-stu-id="d898f-197">Add the SIP SRV record for Skype for Business Online web conferencing.</span></span>  <br/> 
-  <span data-ttu-id="d898f-198">Ga op de pagina DNS-beheer voor uw domein naar **Action** \> **Other New Records**.</span><span class="sxs-lookup"><span data-stu-id="d898f-198">On the DNS Manager page for your domain, go to **Action** \> **Other New Records**.</span></span> 
-   <span data-ttu-id="d898f-199">Selecteer **servicelocatie (SRV) in**het venster **Resourcerecordtype** en selecteer **Vervolgens Record maken**.</span><span class="sxs-lookup"><span data-stu-id="d898f-199">In the **Resource Record Type** window, select **Service Location (SRV)**, and then select **Create Record**.</span></span> 
-   <span data-ttu-id="d898f-200">Controleer in het dialoogvenster **Nieuwe bronrecord** of de velden zijn ingesteld op precies de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="d898f-200">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    -  <span data-ttu-id="d898f-201">Service: _sip</span><span class="sxs-lookup"><span data-stu-id="d898f-201">Service: _sip</span></span>
    -  <span data-ttu-id="d898f-202">Protocol: _tls</span><span class="sxs-lookup"><span data-stu-id="d898f-202">Protocol: _tls</span></span>
    -  <span data-ttu-id="d898f-203">Prioriteit: 100</span><span class="sxs-lookup"><span data-stu-id="d898f-203">Priority: 100</span></span>
    -  <span data-ttu-id="d898f-204">Gewicht: 1</span><span class="sxs-lookup"><span data-stu-id="d898f-204">Weight: 1</span></span>
    -  <span data-ttu-id="d898f-205">Poort: 443</span><span class="sxs-lookup"><span data-stu-id="d898f-205">Port: 443</span></span>
    -  <span data-ttu-id="d898f-206">Doel (hostnaam): sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d898f-206">Target (Hostname): sipdir.online.lync.com</span></span>
-  <span data-ttu-id="d898f-207">Kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="d898f-207">Select **OK**.</span></span> 


<span data-ttu-id="d898f-208">Voeg de SIP SRV-record voor Skype voor Bedrijven Online-federatie toe.</span><span class="sxs-lookup"><span data-stu-id="d898f-208">Add the SIP SRV record for Skype for Business Online federation.</span></span>  
-  <span data-ttu-id="d898f-209">Ga op de pagina DNS-beheer voor uw domein naar **Action** \> **Other New Records**.</span><span class="sxs-lookup"><span data-stu-id="d898f-209">On the DNS Manager page for your domain, go to **Action** \> **Other New Records**.</span></span>  
-  <span data-ttu-id="d898f-210">Selecteer **servicelocatie (SRV) in**het venster **Resourcerecordtype** en selecteer **Vervolgens Record maken**.</span><span class="sxs-lookup"><span data-stu-id="d898f-210">In the **Resource Record Type** window, select **Service Location (SRV)**, and then select **Create Record**.</span></span> 
-   <span data-ttu-id="d898f-211">Controleer in het dialoogvenster **Nieuwe bronrecord** of de velden zijn ingesteld op precies de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="d898f-211">In the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values:</span></span>  
    -  <span data-ttu-id="d898f-212">Service: _sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="d898f-212">Service: _sipfederationtls</span></span>
    -  <span data-ttu-id="d898f-213">Protocol: _tcp</span><span class="sxs-lookup"><span data-stu-id="d898f-213">Protocol: _tcp</span></span>
    -  <span data-ttu-id="d898f-214">Prioriteit: 100</span><span class="sxs-lookup"><span data-stu-id="d898f-214">Priority: 100</span></span>
    -  <span data-ttu-id="d898f-215">Gewicht: 1</span><span class="sxs-lookup"><span data-stu-id="d898f-215">Weight: 1</span></span>
    -  <span data-ttu-id="d898f-216">Poort: 5061</span><span class="sxs-lookup"><span data-stu-id="d898f-216">Port: 5061</span></span>
    -  <span data-ttu-id="d898f-217">Doel (hostnaam): sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="d898f-217">Target (Hostname): sipfed.online.lync.com</span></span>
-  <span data-ttu-id="d898f-218">Kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="d898f-218">Select **OK**.</span></span> 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a><span data-ttu-id="d898f-219">Een record toevoegen om te verifiëren dat u eigenaar bent van het domein, als dit nog niet is gedaan</span><span class="sxs-lookup"><span data-stu-id="d898f-219">Add a record to verify that you own the domain, if you haven't already</span></span>
<span data-ttu-id="d898f-220"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="d898f-220"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="d898f-p113">Voordat u de DNS-records toevoegt voor het instellen van de Office 365-services, moet door Office 365 worden bevestigd dat u eigenaar bent van het domein dat u toevoegt. Hiertoe voegt u een record toe aan de hand van onderstaande stappen.</span><span class="sxs-lookup"><span data-stu-id="d898f-p113">Before you add the DNS records to set up your Office 365 services, Office 365 has to confirm that you own the domain you're adding. To do this, you add a record, following the steps below.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d898f-223">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed.</span><span class="sxs-lookup"><span data-stu-id="d898f-223">This record is used only to verify that you own your domain; it doesn't affect anything else.</span></span> 
  

1. <span data-ttu-id="d898f-224">Verzamel informatie uit Office 365.</span><span class="sxs-lookup"><span data-stu-id="d898f-224">Gather information from Office 365.</span></span>  <br/> 
2. <span data-ttu-id="d898f-225">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="d898f-225">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span> 
3. <span data-ttu-id="d898f-226">Selecteer op de pagina **Domeinen** in de kolom **Acties** voor het domein dat u verifieert de optie **Setup starten**.</span><span class="sxs-lookup"><span data-stu-id="d898f-226">On the **Domains** page, in the **Actions** column for the domain that you are verifying, select **Start setup**.</span></span> 
4. <span data-ttu-id="d898f-227">Selecteer **stap 1 starten**op de pagina Een domein toevoegen aan Office **365** .</span><span class="sxs-lookup"><span data-stu-id="d898f-227">On the **Add a domain to Office 365** page, select **Start step 1**.</span></span> 
5. <span data-ttu-id="d898f-228">Kies **op** de pagina Bevestigen dat u eigenaar bent van uw domein de optie Algemene **instructies**in de **vervolgkeuzelijst Zie instructies voor het uitvoeren van deze stap met** de vervolgkeuzelijst .</span><span class="sxs-lookup"><span data-stu-id="d898f-228">On the **Confirm that you own your domain** page, in the **See instructions for performing this step with** drop-down list, choose **General instructions**.</span></span> 
6. <span data-ttu-id="d898f-229">Kopieer vanuit de tabel de waarde Doel of adres waarnaar wordt verwezen.</span><span class="sxs-lookup"><span data-stu-id="d898f-229">From the table, copy the Destination or Points to Address value.</span></span> <span data-ttu-id="d898f-230">Deze hebt u nodig voor de volgende stap.</span><span class="sxs-lookup"><span data-stu-id="d898f-230">You'll need it for the next step.</span></span> <span data-ttu-id="d898f-231">Het is raadzaam deze waarde te kopiëren en te plakken, zodat alle spatiëring ongewijzigd blijft.</span><span class="sxs-lookup"><span data-stu-id="d898f-231">We recommend copying and pasting this value, so that all of the spacing stays correct.</span></span>

<span data-ttu-id="d898f-232">Voeg een TXT-record toe.</span><span class="sxs-lookup"><span data-stu-id="d898f-232">Add a TXT record.</span></span> 
-  <span data-ttu-id="d898f-233">Ga op de pagina DNS-beheer voor uw domein naar **Actietekst** \> **(TXT).**</span><span class="sxs-lookup"><span data-stu-id="d898f-233">On the DNS Manager page for your domain, go to **Action** \> **Text (TXT)**.</span></span> 
-   <span data-ttu-id="d898f-234">**Selecteer**bewerken in het dialoogvenster **Nieuwe bronrecord** .</span><span class="sxs-lookup"><span data-stu-id="d898f-234">In the **New Resource Record** dialog box, select **Edit**.</span></span>  
-  <span data-ttu-id="d898f-235">Controleer in het gedeelte **Aangepaste hostnamen** van het dialoogvenster **Nieuwe bronrecord** of de velden zijn ingesteld op precies de volgende waarden.</span><span class="sxs-lookup"><span data-stu-id="d898f-235">In the **Custom Host Names** area of the **New Resource Record** dialog box, make sure that the fields are set to precisely the following values.</span></span> 

> [!IMPORTANT] 
> <span data-ttu-id="d898f-236">In sommige versies van Windows DNS Manager is het mogelijk dat het domein zo is ingesteld dat wanneer u een txt-record maakt, de thuisnaam standaard wordt ingesteld op het bovenliggende domein.</span><span class="sxs-lookup"><span data-stu-id="d898f-236">In some versions of Windows DNS Manager, the domain may have been set up so that when you create a txt record, the home name defaults to the parent domain.</span></span> <span data-ttu-id="d898f-237">Als u in deze situatie een TXT-record toevoegt, stelt u de hostnaam in op leeg (geen waarde) in plaats van op @ of de domeinnaam.</span><span class="sxs-lookup"><span data-stu-id="d898f-237">In this situation, when adding a TXT record, set the host name to blank (no value) instead of setting it to @ or the domain name.</span></span> 

- <span data-ttu-id="d898f-238">Host naam: @</span><span class="sxs-lookup"><span data-stu-id="d898f-238">Host Name: @</span></span>
- <span data-ttu-id="d898f-239">Type: TXT</span><span class="sxs-lookup"><span data-stu-id="d898f-239">Type: TXT</span></span>
- <span data-ttu-id="d898f-240">Adres: Plak hier de waarde Bestemming of Adres die u zojuist hebt gekopieerd uit Office 365.</span><span class="sxs-lookup"><span data-stu-id="d898f-240">Address: Paste the Destination or Points to Address value that you just copied from Office 365 here.</span></span>  
- <span data-ttu-id="d898f-241">Selecteer **OK** > **gereed**.</span><span class="sxs-lookup"><span data-stu-id="d898f-241">Select **OK** > **Done**.</span></span>

<span data-ttu-id="d898f-242">Controleer uw domein in Office 365.</span><span class="sxs-lookup"><span data-stu-id="d898f-242">Verify your domain in Office 365.</span></span>  
> [!IMPORTANT]
> <span data-ttu-id="d898f-243">Wacht ongeveer 15 minuten voordat u dit doet, zodat de record die u zojuist hebt gemaakt, kan worden bijgewerkt via het internet.</span><span class="sxs-lookup"><span data-stu-id="d898f-243">Wait about 15 minutes before you do this, so the record you just created can update across the Internet.</span></span>       

- <span data-ttu-id="d898f-244">Ga terug naar Office 365 en volg de onderstaande stappen om een controle aan te vragen.</span><span class="sxs-lookup"><span data-stu-id="d898f-244">Go back to Office 365 and follow the steps below to request a verification check.</span></span> <span data-ttu-id="d898f-245">Er wordt gecontroleerd op de TXT-record die u in de vorige stap hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="d898f-245">The check looks for the TXT record you added in the previous step.</span></span> <span data-ttu-id="d898f-246">Wanneer de juiste TXT-record wordt gevonden, wordt het domein geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="d898f-246">When it finds the correct TXT record, the domain is verified.</span></span>  
1. <span data-ttu-id="d898f-247">Ga in het beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Setup-domeinen.</a> **Setup**</span><span class="sxs-lookup"><span data-stu-id="d898f-247">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
2. <span data-ttu-id="d898f-248">Selecteer op de pagina **Domeinen** in de kolom **Actie** voor het domein dat u verifieert de optie **Installatie starten**.</span><span class="sxs-lookup"><span data-stu-id="d898f-248">On the **Domains** page, in the **Action** column for the domain you are verifying, select **Start setup**.</span></span> 
3. <span data-ttu-id="d898f-249">Selecteer op **de pagina Bevestigen dat u eigenaar bent van uw domein** de optie **Gereed, controleer nu**en selecteer vervolgens in het bevestigingsdialoogvenster **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="d898f-249">On the **Confirm that you own your domain** page, select **done, verify now**, and then in the confirmation dialog box, select **Finish**.</span></span> 
   
> [!NOTE]
>  <span data-ttu-id="d898f-p117">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d898f-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a><span data-ttu-id="d898f-253">Niet-routeerbaar e-mailadres gebruikt als een UPN in de on-premises Active Directory</span><span class="sxs-lookup"><span data-stu-id="d898f-253">Non-routable email address used as a UPN in your on-prem Active Directory</span></span>
<span data-ttu-id="d898f-254"><a name="BKMK_ADNote"> </a></span><span class="sxs-lookup"><span data-stu-id="d898f-254"><a name="BKMK_ADNote"> </a></span></span>

<span data-ttu-id="d898f-255">Als u van plan bent uw on-premises Active Directory te synchroniseren met Office 365, controleert u dan of het voorvoegsel van de user principal name (UPN-naam) van Active Directory een geldig domeinvoorvoegsel is en geen niet-ondersteund domeinvoorvoegsel, zoals @contoso.local.</span><span class="sxs-lookup"><span data-stu-id="d898f-255">If you're planning to synchronize your on-premises Active Directory with Office 365, you'll want to make sure that the Active Directory user principal name (UPN) suffix is a valid domain suffix, and not an unsupported domain suffix such as @contoso.local.</span></span> <span data-ttu-id="d898f-256">Als u het UPN-achtervoegsel wilt wijzigen, raadpleegt u [Een niet-routetabel domein voorbereiden voor adressynchronisatie.](https://support.office.com/article/e7968303-c234-46c4-b8b0-b5c93c6d57a7)</span><span class="sxs-lookup"><span data-stu-id="d898f-256">If you need to change your UPN suffix, see [How to prepare a non-routable domain for directory synchronization](https://support.office.com/article/e7968303-c234-46c4-b8b0-b5c93c6d57a7).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="d898f-p119">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d898f-p119">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
