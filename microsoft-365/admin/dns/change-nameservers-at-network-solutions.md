---
title: Naamservers wijzigen voor het instellen van Office 365 bij Network Solutions
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
ms.assetid: d4ba60f3-4e1c-4180-99bd-250b8955be2a
description: 'Meer informatie over het instellen van uw aangepaste Office 365-domein met netwerkoplossingen als u wilt dat Office 365 uw DNS-records beheert. '
ms.openlocfilehash: 5eae7561baa6e0efb4436e6758d3fd972a2700cc
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "42812487"
---
# <a name="change-nameservers-to-set-up-office-365-with-network-solutions"></a><span data-ttu-id="a17d6-103">Naamservers wijzigen voor het instellen van Office 365 bij Network Solutions</span><span class="sxs-lookup"><span data-stu-id="a17d6-103">Change nameservers to set up Office 365 with Network Solutions</span></span>

 <span data-ttu-id="a17d6-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="a17d6-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="a17d6-p101">Volg deze instructies als u wilt dat Office 365 uw DNS-records voor Office 365 voor u beheert. (Desgewenst kunt u [al uw DNS-records voor Office 365 bij Network Solutions beheren](create-dns-records-at-network-solutions.md).)</span><span class="sxs-lookup"><span data-stu-id="a17d6-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Network Solutions](create-dns-records-at-network-solutions.md).)</span></span>
  
    
## <a name="add-a-txt-record-at-network-solutions-to-verify-that-you-own-the-domain"></a><span data-ttu-id="a17d6-107">Een TXT-record toevoegen op Network Solutions om te bevestigen dat u eigenaar van het domein bent</span><span class="sxs-lookup"><span data-stu-id="a17d6-107">Add a TXT record at Network Solutions to verify that you own the domain</span></span>

<span data-ttu-id="a17d6-p102">Voordat u uw domein met Office 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Office 365 bewezen.</span><span class="sxs-lookup"><span data-stu-id="a17d6-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a17d6-p103">Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.</span><span class="sxs-lookup"><span data-stu-id="a17d6-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="a17d6-112">Volg onderstaande stappen of [bekijk de video (start op 0:47)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-Network-Solutions-69b092e3-c026-4d19-a7d0-16cdb2d8b261?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="a17d6-112">Follow the steps below or [watch the video (start at 0:47)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-Network-Solutions-69b092e3-c026-4d19-a7d0-16cdb2d8b261?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="a17d6-p104">Als u wilt beginnen, gaat u [via deze koppeling](https://www.networksolutions.com/manage-it) naar uw pagina met domeinen bij Network Solutions. U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="a17d6-p104">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a17d6-115">Voordat u de knop **Inloggen** selecteert, kiest u eerst **Mijn domeinnamen beheren** in de **inloglijst naar:** vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="a17d6-115">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span>
  
    ![Mijn domeinnamen beheren kiezen en aanmelden bij Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="a17d6-117">Schakel het selectievakje in naast de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="a17d6-117">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Het selectievakje voor uw domein selecteren](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="a17d6-119">Selecteer **DNS bewerken**.</span><span class="sxs-lookup"><span data-stu-id="a17d6-119">Select **Edit DNS**.</span></span>
    
    ![Selecteer DNS bewerken](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="a17d6-121">Selecteer **Geavanceerde DNS-records beheren**.</span><span class="sxs-lookup"><span data-stu-id="a17d6-121">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="a17d6-122">(Mogelijk moet u omlaag schuiven.)</span><span class="sxs-lookup"><span data-stu-id="a17d6-122">(You may have to scroll down.)</span></span>
    
    ![Geavanceerde DNS-records beheren selecteren](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="a17d6-124">Schuif omlaag naar de sectie **Tekst (TXT Records)** en selecteer **TXT-records bewerken**.</span><span class="sxs-lookup"><span data-stu-id="a17d6-124">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![Selecteer TXT-records bewerken](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="a17d6-126">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="a17d6-126">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
|<span data-ttu-id="a17d6-127">**Host**</span><span class="sxs-lookup"><span data-stu-id="a17d6-127">**Host**</span></span>|<span data-ttu-id="a17d6-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a17d6-128">**TTL**</span></span>|<span data-ttu-id="a17d6-129">**Tekst**</span><span class="sxs-lookup"><span data-stu-id="a17d6-129">**Text**</span></span>|
|:-----|:-----|:-----|
|@  <br/> <span data-ttu-id="a17d6-130">(In het systeem wordt deze waarde gewijzigd in **@ (None)** wanneer u de record opslaat.)</span><span class="sxs-lookup"><span data-stu-id="a17d6-130">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="a17d6-131">3600</span><span class="sxs-lookup"><span data-stu-id="a17d6-131">3600</span></span>  <br/> |<span data-ttu-id="a17d6-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="a17d6-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="a17d6-133">**Opmerking:** Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="a17d6-133">**Note**: This is an example.</span></span> <span data-ttu-id="a17d6-134">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365.</span><span class="sxs-lookup"><span data-stu-id="a17d6-134">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="a17d6-135">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="a17d6-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)
   
    
   ![Waarden typen of plakken in de vakken voor de nieuwe record](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="a17d6-137">Selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="a17d6-137">Select **Continue**.</span></span>
    
    ![Doorgaan selecteren](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="a17d6-139">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="a17d6-139">Select **Save Changes**.</span></span>
    
    ![Wijzigingen opslaan selecteren](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="a17d6-141">Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="a17d6-141">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="a17d6-142">Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Office 365 en vraagt u of Office 365 naar de record wil zoeken.</span><span class="sxs-lookup"><span data-stu-id="a17d6-142">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="a17d6-143">Wanneer in Office 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="a17d6-143">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="a17d6-144">Ga in het beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Instellingendomeinen.</a> **Settings**</span><span class="sxs-lookup"><span data-stu-id="a17d6-144">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="a17d6-145">Selecteer op de pagina **Domeinen** het domein dat u verifieert.</span><span class="sxs-lookup"><span data-stu-id="a17d6-145">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="a17d6-146">Selecteer op de pagina **Setup** de optie **Startsetup**.</span><span class="sxs-lookup"><span data-stu-id="a17d6-146">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="a17d6-147">Selecteer op de pagina **Domein verifiëren** de optie **Verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="a17d6-147">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="a17d6-p106">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a17d6-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="a17d6-151">De naamserverrecords (NS-records) van uw domein wijzigen</span><span class="sxs-lookup"><span data-stu-id="a17d6-151">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="a17d6-p107">U voltooit het instellen van uw domein met Office 365 door de NS-records van uw domein bij uw domeinregistrar te wijzigen, zodat deze verwijzen naar de primaire en secundaire naamservers van Office 365. Hiermee wordt Office 365 zo ingesteld dat de DNS-records van het domein voor u worden bijgewerkt. Alle benodigde records worden toegevoegd zodat e-mail, Skype voor Bedrijven Online en uw openbare website met uw domein kunnen werken. Daarna bent u klaar.</span><span class="sxs-lookup"><span data-stu-id="a17d6-p107">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="a17d6-p108">Als u de NS-records van uw domein laat verwijzen naar de naamservers van Office 365, is dit van invloed op alle services die momenteel aan uw domein zijn gekoppeld. Zo wordt bijvoorbeeld alle e-mail die naar uw domein wordt verzonden (zoals william@ *uw_domein*  .com), naar Office 365 verzonden zodra u deze wijziging hebt aangebracht.</span><span class="sxs-lookup"><span data-stu-id="a17d6-p108">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change.</span></span>
  
<span data-ttu-id="a17d6-p109">Bent u klaar voor het wijzigen van uw NS-records zodat Office 365 uw domein kan instellen? Volg onderstaande stappen of [bekijk de video (start bij 2:23)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-Network-Solutions-69b092e3-c026-4d19-a7d0-16cdb2d8b261?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="a17d6-p109">Ready to change your NS records so Office 365 can set up your domain? Follow the steps below or [watch the video (start at 2:23)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-Network-Solutions-69b092e3-c026-4d19-a7d0-16cdb2d8b261?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="a17d6-159">Wanneer u de stappen in deze sectie hebt voltooid, zijn de *enige* nameservers die moeten worden vermeld deze vier: **ns1.bdm.microsoftonline.com,** **ns2.bdm.microsoftonline.com,** **ns3.bdm.microsoftonline.com**en **ns4.bdm.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="a17d6-159">When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**.</span></span> <span data-ttu-id="a17d6-160">In de volgende procedure kunt u zien hoe u andere, ongewenste naamservers uit de lijst verwijdert en hoe u de  *juiste*  naamservers toevoegt als deze niet al in de lijst staan.</span><span class="sxs-lookup"><span data-stu-id="a17d6-160">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.</span></span> 
  
1. <span data-ttu-id="a17d6-161">Als u wilt beginnen, gaat u [via deze koppeling](https://www.networksolutions.com/manage-it) naar uw pagina met domeinen bij Network Solutions.</span><span class="sxs-lookup"><span data-stu-id="a17d6-161">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="a17d6-162">U wordt gevraagd u aan te melden.</span><span class="sxs-lookup"><span data-stu-id="a17d6-162">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a17d6-163">Voordat u de knop **Inloggen** selecteert, kiest u eerst **Mijn domeinnamen beheren** in de **inloglijst naar:** vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="a17d6-163">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Mijn domeinnamen beheren kiezen en aanmelden bij Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="a17d6-165">Schakel het selectievakje in naast de naam van het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="a17d6-165">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Het selectievakje voor uw domein selecteren](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="a17d6-167">Selecteer **DNS bewerken**.</span><span class="sxs-lookup"><span data-stu-id="a17d6-167">Select **Edit DNS**.</span></span>
    
    ![Selecteer DNS bewerken](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="a17d6-169">Selecteer **DNS verplaatsen**.</span><span class="sxs-lookup"><span data-stu-id="a17d6-169">Select **Move DNS**.</span></span>
    
    ![NetworkSolutionsBP-Opnieuw delegeren-1-1](../../media/e57a30f3-63d5-4bcb-84c6-c8be21c261a2.png)
  
5. <span data-ttu-id="a17d6-171">Afhankelijk van of er al naamservers worden vermeld op de pagina die wordt weergegeven, gaat u op een van de volgende twee manieren verder:</span><span class="sxs-lookup"><span data-stu-id="a17d6-171">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="a17d6-172">Als er nog **GEEN** naamservers worden vermeld, [Als er nog GEEN naamservers worden vermeld](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="a17d6-172">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="a17d6-173">Als er **WEL** naamservers worden vermeld, [Als er WEL naamservers worden vermeld](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="a17d6-173">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="a17d6-174">Als er nog GEEN naamservers worden vermeld</span><span class="sxs-lookup"><span data-stu-id="a17d6-174">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="a17d6-175">Selecteer op de pagina **Domeinen** in de sectie **Domeinnaamservers opgeven** de optie **Meer naamservers toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="a17d6-175">On the **Domains** page, in the **Specify Domain Name Servers** section, select **Add More Name Servers**.</span></span>
    
    ![NetworkSolutionsBP-Opnieuw delegeren-1-2-1](../../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
2. <span data-ttu-id="a17d6-177">Typ of kopieer en plak de naamserverwaarden uit de volgende tabel naar de pagina **Domain Names**.</span><span class="sxs-lookup"><span data-stu-id="a17d6-177">On the **Domain Names** page, type or copy and paste the nameserver values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="a17d6-178">**Name Server 1**</span><span class="sxs-lookup"><span data-stu-id="a17d6-178">**Name Server 1**</span></span> <br/> |<span data-ttu-id="a17d6-179">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a17d6-179">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="a17d6-180">**Name Server 2**</span><span class="sxs-lookup"><span data-stu-id="a17d6-180">**Name Server 2**</span></span> <br/> |<span data-ttu-id="a17d6-181">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a17d6-181">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="a17d6-182">**Name Server 2**</span><span class="sxs-lookup"><span data-stu-id="a17d6-182">**Name Server 2**</span></span> <br/> |<span data-ttu-id="a17d6-183">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a17d6-183">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="a17d6-184">**Name Server 2**</span><span class="sxs-lookup"><span data-stu-id="a17d6-184">**Name Server 2**</span></span> <br/> |<span data-ttu-id="a17d6-185">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a17d6-185">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    
![NetworkSolutionsBP-Opnieuw delegeren-1-2-2](../../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
3. <span data-ttu-id="a17d6-187">Selecteer **DNS verplaatsen**.</span><span class="sxs-lookup"><span data-stu-id="a17d6-187">Select **Move DNS**.</span></span>
    
    ![NetworkSolutionsBP-Opnieuw delegeren-1-2-3](../../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
4. <span data-ttu-id="a17d6-189">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="a17d6-189">Select **Save Changes**.</span></span>
    
    ![NetworkSolutionsBP-Opnieuw delegeren-1-2-4](../../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> <span data-ttu-id="a17d6-p112">Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd. Vervolgens worden uw e-mail voor Office 365 en andere services ingesteld voor gebruik met uw domein.</span><span class="sxs-lookup"><span data-stu-id="a17d6-p112">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="a17d6-193">Als er WEL naamservers worden vermeld</span><span class="sxs-lookup"><span data-stu-id="a17d6-193">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="a17d6-p113">Voer deze stappen  *alleen*  uit als u andere bestaande naamservers hebt dan de vier  *juiste*  naamservers. (Dat wil zeggen, verwijder  *alleen*  huidige naamservers die een  *andere*  naam hebben dan **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** of **ns4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="a17d6-p113">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span>
  
1. <span data-ttu-id="a17d6-196">Als er andere naamservers worden vermeld, verwijdert u elke vermelding door deze te selecteren en vervolgens te drukken op de toets **Delete** op het toetsenbord.</span><span class="sxs-lookup"><span data-stu-id="a17d6-196">If there are any other nameservers listed, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span>
    
    ![Afbeelding van het lint](../../media/eeb8ad22-bf4a-43a8-b97a-f09c3654d89b.png)
  
2. <span data-ttu-id="a17d6-198">Selecteer **Meer naamservers toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="a17d6-198">Select **Add More Name Servers**.</span></span>
    
    ![NetworkSolutionsBP-Opnieuw delegeren-1-2-1](../../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
3. <span data-ttu-id="a17d6-200">Typ of kopieer en plak de naamserverwaarden uit de volgende tabel naar de pagina **Domain Names**.</span><span class="sxs-lookup"><span data-stu-id="a17d6-200">On the **Domain Names** page, type or copy and paste the nameserver values from the following table.</span></span>
 
    
|||
|:-----|:-----|
|<span data-ttu-id="a17d6-201">**Name Server 1**</span><span class="sxs-lookup"><span data-stu-id="a17d6-201">**Name Server 1**</span></span> <br/> |<span data-ttu-id="a17d6-202">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a17d6-202">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="a17d6-203">**Name Server 2**</span><span class="sxs-lookup"><span data-stu-id="a17d6-203">**Name Server 2**</span></span> <br/> |<span data-ttu-id="a17d6-204">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a17d6-204">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="a17d6-205">**Name Server 3**</span><span class="sxs-lookup"><span data-stu-id="a17d6-205">**Name Server 3**</span></span> <br/> |<span data-ttu-id="a17d6-206">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a17d6-206">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="a17d6-207">**Name Server 4**</span><span class="sxs-lookup"><span data-stu-id="a17d6-207">**Name Server 4**</span></span> <br/> |<span data-ttu-id="a17d6-208">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a17d6-208">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    
![NetworkSolutionsBP-Opnieuw delegeren-1-2-2](../../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
4. <span data-ttu-id="a17d6-210">Selecteer **DNS verplaatsen**.</span><span class="sxs-lookup"><span data-stu-id="a17d6-210">Select **Move DNS**.</span></span>
    
    ![NetworkSolutionsBP-Opnieuw delegeren-1-2-3](../../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
5. <span data-ttu-id="a17d6-212">Selecteer **Wijzigingen opslaan.**</span><span class="sxs-lookup"><span data-stu-id="a17d6-212">Select **Save Changes.**</span></span>
    
    ![NetworkSolutionsBP-Opnieuw delegeren-1-2-4](../../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> <span data-ttu-id="a17d6-p114">Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd. Vervolgens worden uw e-mail voor Office 365 en andere services ingesteld voor gebruik met uw domein.</span><span class="sxs-lookup"><span data-stu-id="a17d6-p114">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span>
