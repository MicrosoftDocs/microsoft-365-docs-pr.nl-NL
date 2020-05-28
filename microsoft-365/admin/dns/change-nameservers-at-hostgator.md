---
title: Naamservers wijzigen om Microsoft in te stellen met Hostgator
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
ms.assetid: f3bd3c62-0477-48e4-b2b5-21e329d67985
description: Meer informatie over hoe u Microsoft instellen voor het beheren van de DNS-records van uw aangepaste domein bij Hostgator.
ms.openlocfilehash: 787fe5f5e768d9d93cfca9d1644037142822216e
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400639"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-hostgator"></a><span data-ttu-id="207f4-103">Naamservers wijzigen om Microsoft 365 in te stellen met Hostgator</span><span class="sxs-lookup"><span data-stu-id="207f4-103">Change nameservers to set up Microsoft 365 with Hostgator</span></span>

 <span data-ttu-id="207f4-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="207f4-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="207f4-105">Volg deze instructies als u wilt dat Microsoft uw DNS-records voor u beheert.</span><span class="sxs-lookup"><span data-stu-id="207f4-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="207f4-106">(Als u dat liever hebt, u [al uw Microsoft DNS-records beheren bij Hostgator](create-dns-records-at-hostgator.md).)</span><span class="sxs-lookup"><span data-stu-id="207f4-106">(If you prefer, you can [manage all your Microsoft DNS records at Hostgator](create-dns-records-at-hostgator.md).)</span></span>
  
    
## <a name="point-your-domain-to-your-hosting-account"></a><span data-ttu-id="207f4-107">Uw domein naar uw hostingaccount laten verwijzen.</span><span class="sxs-lookup"><span data-stu-id="207f4-107">Point your domain to your hosting account.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="207f4-108">U moet deze procedure uitvoeren voordat u de procedure in de volgende sectie, **Een TXT-record toevoegen voor verificatie**, uitvoert.</span><span class="sxs-lookup"><span data-stu-id="207f4-108">You must perform this procedure before you perform the procedure in the following section, **Add a TXT record for verification**.</span></span>
  
<span data-ttu-id="207f4-109">Volg deze stappen om uw domein en hostingaccounts te koppelen.</span><span class="sxs-lookup"><span data-stu-id="207f4-109">Follow these steps to associate your domain and hosting accounts.</span></span>
  
1. <span data-ttu-id="207f4-p102">Ga eerst naar uw pagina met de klantenportal bij Hostgator via [deze koppeling](https://portal.hostgator.com/domain/manage). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="207f4-p102">To get started, go to your customer portal page at Hostgator by using [this link](https://portal.hostgator.com/domain/manage). You'll be prompted to log in.</span></span>
    
    ![Takenlijsten verbinden met Outlook](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. <span data-ttu-id="207f4-113">Selecteer het tabblad **Domeinen.**</span><span class="sxs-lookup"><span data-stu-id="207f4-113">Select the **Domains** tab.</span></span>
    
    ![Office 2010-lint](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. <span data-ttu-id="207f4-115">Selecteer op de pagina **Domeinen beheren** in het gebied **Mijn domeinen** het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="207f4-115">On the **Manage Domains** page, in the **My Domains** area, select the domain you want to update.</span></span>
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. <span data-ttu-id="207f4-117">Selecteer op de pagina **Domeinenoverzicht** in het gebied **Naamservers** de optie **Wijzigen**.</span><span class="sxs-lookup"><span data-stu-id="207f4-117">On the **Domains Overview** page, in the **Name Servers** area, select **Change**.</span></span>
    
    ![Afbeelding van knop Doorzichtige kleur instellen](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. <span data-ttu-id="207f4-119">Kies op de pagina **Naamservers** voor uw domein in de vervolgkeuzelijst **Hostingaccount** selecteren de **hostingaccount** die aan uw domein is gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="207f4-119">On the **Name Servers** page for your domain, in the **Select Hosting Account** drop-down list, choose the **hosting account** that is associated with your domain.</span></span>
    
    ![Power BI-dashboards](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. <span data-ttu-id="207f4-121">Selecteer **Naamservers opslaan**.</span><span class="sxs-lookup"><span data-stu-id="207f4-121">Select **Save Name Servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-9](../../media/b52a825a-6d54-49ba-87c8-52f770fdfa0c.png)
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="207f4-123">Een TXT-record toevoegen voor verificatie</span><span class="sxs-lookup"><span data-stu-id="207f4-123">Add a TXT record for verification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="207f4-124">Voordat u deze procedure uitvoert, moet u eerst de procedure uitvoeren in het eerste deel van dit artikel, [Uw domein naar uw hostingaccount leiden.](#point-your-domain-to-your-hosting-account)</span><span class="sxs-lookup"><span data-stu-id="207f4-124">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account.](#point-your-domain-to-your-hosting-account).</span></span>
  
<span data-ttu-id="207f4-p103">Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.</span><span class="sxs-lookup"><span data-stu-id="207f4-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="207f4-p104">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="207f4-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>
  
1. <span data-ttu-id="207f4-p105">Als u wilt beginnen, gaat u naar de pagina cPanel bij Hostgator. U wordt gevraagd u eerst aan te melden.</span><span class="sxs-lookup"><span data-stu-id="207f4-p105">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="207f4-p106">(Aan elk gehost account bij Hostgator is een uniek cPanel-adres toegewezen. Het adres van uw cPanel ziet er ongeveer als volgt uit: https://YourSiteAddress:secure-port-number nummer-beveiligde-poort. U vindt dit adres in de e-mail die u bij aanmelding van Hostgator hebt ontvangen.)</span><span class="sxs-lookup"><span data-stu-id="207f4-p106">(Each hosted account at Hostgator is assigned a unique cPanel address. Your cPanel address should look like this: https://YourSiteAddress:secure-port-number. The sign-up email you received from Hostgator will specify that address.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="207f4-134">Als u cPanel aan uw domein wilt koppelen, hebt u een hostingaccount bij Hostgator nodig.</span><span class="sxs-lookup"><span data-stu-id="207f4-134">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="207f4-135">Om aan de slag te gaan, u een hostingaccount kopen bij Hostgator of [de NS-records (nameserver) van uw domein wijzigen](#change-your-domains-nameserver-ns-records) om naar Microsoft te wijzen.</span><span class="sxs-lookup"><span data-stu-id="207f4-135">To get started, you can either purchase a hosting account from Hostgator or [change your domain's nameserver (NS) records](#change-your-domains-nameserver-ns-records) to point to Microsoft.</span></span> 
  
2. <span data-ttu-id="207f4-136">Selecteer op de pagina **Configuratiescherm** in het gebied **Domeinen** de optie **Advanced DNS Zone Editor**.</span><span class="sxs-lookup"><span data-stu-id="207f4-136">On the **Control Panel** page, in the **Domains** area, select **Advanced DNS Zone Editor**.</span></span>
    
    <span data-ttu-id="207f4-137">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="207f4-137">(You may have to scroll down.)</span></span> 
    
3. <span data-ttu-id="207f4-138">Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add a Record** in de vakken voor de nieuwe record op de pagina **Advanced DNS Zone Editor**.</span><span class="sxs-lookup"><span data-stu-id="207f4-138">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="207f4-139">(Kies in de vervolgkeuzelijst de waarde **Type**).</span><span class="sxs-lookup"><span data-stu-id="207f4-139">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="207f4-140">**Name**</span><span class="sxs-lookup"><span data-stu-id="207f4-140">**Name**</span></span> <br/> |<span data-ttu-id="207f4-141">**TTL**</span><span class="sxs-lookup"><span data-stu-id="207f4-141">**TTL**</span></span> <br/> |<span data-ttu-id="207f4-142">**Type**</span><span class="sxs-lookup"><span data-stu-id="207f4-142">**Type**</span></span> <br/> |<span data-ttu-id="207f4-143">**TXT Data**</span><span class="sxs-lookup"><span data-stu-id="207f4-143">**TXT Data**</span></span> <br/> |
|<span data-ttu-id="207f4-p108">Gebruik uw  *domeinnaam*  (bijvoorbeeld fourthcoffee.com).</span><span class="sxs-lookup"><span data-stu-id="207f4-p108">Use your  *domain_name*  . (for example, fourthcoffee.com.)  </span></span><br/> <span data-ttu-id="207f4-146">**Deze waarde MOET eindigen op een punt (.)**</span><span class="sxs-lookup"><span data-stu-id="207f4-146">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="207f4-147">1</span><span class="sxs-lookup"><span data-stu-id="207f4-147">1</span></span>  <br/> |<span data-ttu-id="207f4-148">TXT</span><span class="sxs-lookup"><span data-stu-id="207f4-148">TXT</span></span>  <br/> |<span data-ttu-id="207f4-149">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="207f4-149">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="207f4-150">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="207f4-150">**Note:** This is an example.</span></span> <span data-ttu-id="207f4-151">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.</span><span class="sxs-lookup"><span data-stu-id="207f4-151">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="207f4-152">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="207f4-152">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     <br/>  |
   
4. <span data-ttu-id="207f4-153">Selecteer **Record toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="207f4-153">Select **Add Record**.</span></span>
    
5. <span data-ttu-id="207f4-154">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="207f4-154">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="207f4-155">Nu u de record op de site van uw domeinregistrar hebt toegevoegd, gaat u terug naar Microsoft en vraagt u om een zoekopdracht naar de record.</span><span class="sxs-lookup"><span data-stu-id="207f4-155">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="207f4-156">Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="207f4-156">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="207f4-157">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="207f4-157">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="207f4-158">Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="207f4-158">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="207f4-159">Kies **Start setup** op de pagina **Setup**.</span><span class="sxs-lookup"><span data-stu-id="207f4-159">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="207f4-160">Kies **Verifiëren** op de pagina **Domein verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="207f4-160">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="207f4-p110">Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="207f4-p110">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="207f4-164">De naamserverrecords (NS-records) van uw domein wijzigen</span><span class="sxs-lookup"><span data-stu-id="207f4-164">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="207f4-165">Als u het instellen van uw domein met Microsoft wilt voltooien, wijzigt u de NS-records van uw domein bij uw domeinregistrar om naar de primaire en secundaire naamservers van Microsoft te wijzen.</span><span class="sxs-lookup"><span data-stu-id="207f4-165">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="207f4-166">Hiermee wordt Microsoft ingesteld om de DNS-records van het domein voor u bij te werken.</span><span class="sxs-lookup"><span data-stu-id="207f4-166">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="207f4-167">We voegen alle records toe zodat e-mail, Skype voor Bedrijven Online en uw openbare website met uw domein werken en u helemaal klaar bent.</span><span class="sxs-lookup"><span data-stu-id="207f4-167">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="207f4-168">Wanneer u de NS-records van uw domein wijzigt om naar de Microsoft-naamservers te wijzen, worden alle services die momenteel aan uw domein zijn gekoppeld, beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="207f4-168">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="207f4-169">Alle e-mail die naar uw *your_domain* domein wordt verzonden (zoals rob@ your_domain.com) wordt bijvoorbeeld naar Microsoft verzonden nadat u deze wijziging hebt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="207f4-169">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="207f4-170">In de volgende procedure kunt u zien hoe u andere, ongewenste naamservers uit de lijst verwijdert en hoe u de juiste naamservers toevoegt als deze niet al in de lijst staan.</span><span class="sxs-lookup"><span data-stu-id="207f4-170">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="207f4-171">Wanneer u de stappen in deze sectie hebt voltooid, zijn deze vier de enige nameservers: **ns1.bdm.microsoftonline.com,** **ns2.bdm.microsoftonline.com,** **ns3.bdm.microsoftonline.com**en **ns4.bdm.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="207f4-171">When you have completed the steps in this section, the only nameservers that should be listed are these four:  **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**.</span></span>
  
1. <span data-ttu-id="207f4-p114">Ga eerst naar uw pagina met de klantenportal bij Hostgator via [deze koppeling](https://portal.hostgator.com/domain/manage). U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="207f4-p114">To get started, go to your customer portal page at Hostgator by using [this link](https://portal.hostgator.com/domain/manage). You'll be prompted to log in.</span></span>
    
    ![Takenlijsten verbinden met Outlook](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. <span data-ttu-id="207f4-175">Selecteer het tabblad **Domeinen.**</span><span class="sxs-lookup"><span data-stu-id="207f4-175">Select the **Domains** tab.</span></span> 
    
    ![Office 2010-lint](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. <span data-ttu-id="207f4-177">Selecteer op de pagina **Domeinen beheren** in het gebied **Mijn domeinen** het domein dat u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="207f4-177">On the **Manage Domains** page, in the **My Domains** area, select the domain you want to update.</span></span> 
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. <span data-ttu-id="207f4-179">Selecteer op de pagina **Domeinoverzicht** in het gebied **Naamservers** de optie **Wijzigen**.</span><span class="sxs-lookup"><span data-stu-id="207f4-179">On the **Domain Overview** page, in the **Name Servers** area, select **Change**.</span></span>
    
    ![Afbeelding van knop Doorzichtige kleur instellen](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. <span data-ttu-id="207f4-181">Kies op de pagina **Naamservers** voor uw domein in de vervolgkeuzelijst **Hostingaccount** selecteren de **hostingaccount** die aan uw domein is gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="207f4-181">On the **Name Servers** page for your domain, in the **Select Hosting Account** drop-down list, choose the **hosting account** that is associated with your domain.</span></span> 
    
    ![Power BI-dashboards](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. <span data-ttu-id="207f4-183">Selecteer **Handmatig mijn naamservers instellen**.</span><span class="sxs-lookup"><span data-stu-id="207f4-183">Select **Manually set my name servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-5](../../media/5b73ae32-f26e-48aa-b5ad-6da20f1c491a.png)
  
7.   <span data-ttu-id="207f4-185">**LET OP:** Volg deze stappen alleen als u bestaande naamservers hebt, andere dan de vier juiste naamservers.</span><span class="sxs-lookup"><span data-stu-id="207f4-185">**CAUTION**: Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="207f4-186">(Dat wil zeggen, alleen huidige naamservers verwijderen die *geen* naam hebben **ns1.bdm.microsoftonline.com,** **ns2.bdm.microsoftonline.com,** **ns3.bdm.microsoftonline.com**of **ns4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="207f4-186">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span>
  
        <span data-ttu-id="207f4-187">Met de pagina **Name Servers** voor uw domein geopend, verwijdert u elke naamserver in de lijst met naamservers door deze te selecteren en op de toets **Delete** op het toetsenbord te drukken.</span><span class="sxs-lookup"><span data-stu-id="207f4-187">Still on the **Name Servers** page for your domain, in the list of nameservers, delete each nameserver in the list by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
   ![O365_Adddomain_wizard_1_7a](../../media/fa9820e7-28bb-4792-b16c-51e54d83feb1.png)
  
8. <span data-ttu-id="207f4-189">Terwijl u zich nog in de lijst met naamservers bevindt, typt of kopieert en plakt u de eerste twee waarden uit de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="207f4-189">Still in the list of nameservers, type or copy and paste the first two values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="207f4-190">**Name Server 1:**</span><span class="sxs-lookup"><span data-stu-id="207f4-190">**Name Server 1:**</span></span> <br/> |<span data-ttu-id="207f4-191">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="207f4-191">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="207f4-192">**Name Server 2**</span><span class="sxs-lookup"><span data-stu-id="207f4-192">**Name Server 2:**</span></span> <br/> |<span data-ttu-id="207f4-193">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="207f4-193">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="207f4-194">**Name Server 3:**</span><span class="sxs-lookup"><span data-stu-id="207f4-194">**Name Server 3:**</span></span> <br/> |<span data-ttu-id="207f4-195">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="207f4-195">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="207f4-196">**Name Server 4:**</span><span class="sxs-lookup"><span data-stu-id="207f4-196">**Name Server 4:**</span></span> <br/> |<span data-ttu-id="207f4-197">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="207f4-197">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Afbeelding van het lint](../../media/a8c10aa7-30b0-4bc8-9596-20256d396274.png)
  
9. <span data-ttu-id="207f4-199">Voeg de andere waarden voor de naamserver toe.</span><span class="sxs-lookup"><span data-stu-id="207f4-199">Add the other nameserver values.</span></span>
    
    <span data-ttu-id="207f4-200">Selecteer **(+)** toevoegen en typ of kopieer en plak de waarde uit de volgende rij van de tabel in het vak voor de record.</span><span class="sxs-lookup"><span data-stu-id="207f4-200">Select **(+)** add, and then type or copy and paste the value from the next row of the table into the box for the record.</span></span> 
    
    <span data-ttu-id="207f4-201">Herhaal deze procedure totdat u alle vier naamserverrecords hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="207f4-201">Repeat this process until you have created all four nameserver records.</span></span>
    
    ![Hostgator-BP-Redelegate-1-7-2](../../media/92159a39-e498-4220-9b0d-ae2e718c7fb9.png)
  
10. <span data-ttu-id="207f4-203">Selecteer **Naamservers opslaan**.</span><span class="sxs-lookup"><span data-stu-id="207f4-203">Select **Save Name Servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-8](../../media/bd6b0dfa-5d39-4805-970d-7ab153cff117.png)
  
> [!NOTE]
> <span data-ttu-id="207f4-205">Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd.</span><span class="sxs-lookup"><span data-stu-id="207f4-205">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="207f4-206">Vervolgens zijn uw Microsoft-e-mail en andere services helemaal klaar om met uw domein te werken.</span><span class="sxs-lookup"><span data-stu-id="207f4-206">Then your Microsoft email and other services will be all set to work with your domain.</span></span>
