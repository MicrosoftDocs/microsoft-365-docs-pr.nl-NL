---
title: DNS-records maken wanneer uw domein wordt beheerd door Google (eNom)
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
ms.assetid: 3c490fbf-7833-4e43-be34-ed0dc3cce5e3
description: Meer informatie over toegang tot eNom en DNS maken via de pagina Google Domeinen.
ms.openlocfilehash: 566b3990c6cc3080eac9d1367531eea42ab135d1
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "42810487"
---
# <a name="create-dns-records-when-your-domain-is-managed-by-google-enom"></a><span data-ttu-id="9bdc5-103">DNS-records maken wanneer uw domein wordt beheerd door Google (eNom)</span><span class="sxs-lookup"><span data-stu-id="9bdc5-103">Create DNS records when your domain is managed by Google (eNom)</span></span>

 <span data-ttu-id="9bdc5-104">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="9bdc5-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="9bdc5-105">Als u uw e-mailaccounts wilt migreren naar Office 365, moet u een DNS-record aanmaken bij uw domeinregistrar.</span><span class="sxs-lookup"><span data-stu-id="9bdc5-105">To migrate your mail accounts to Office 365, you need to create a DNS record at your domain registrar.</span></span>
  
<span data-ttu-id="9bdc5-106">Als u uw domein via Google hebt gekocht terwijl u zich aanmeldt voor uw **Google Apps for Work-account,** worden uw DNS-records beheerd door Google, maar geregistreerd bij eNom.</span><span class="sxs-lookup"><span data-stu-id="9bdc5-106">If you purchased your domain through Google while signing up for your **Google Apps for Work** account, your DNS records are managed by Google but registered with eNom.</span></span> 
  
<span data-ttu-id="9bdc5-107">U hebt toegang tot eNom en maakt DNS via de pagina Google **Domeinen.**</span><span class="sxs-lookup"><span data-stu-id="9bdc5-107">You can access eNom, and create DNS, through the Google **Domains** page.</span></span> <span data-ttu-id="9bdc5-108">Voer gewoon de stappen in dit artikel uit.</span><span class="sxs-lookup"><span data-stu-id="9bdc5-108">Just follow the steps in this article.</span></span> 
  
## <a name="create-the-dns-record"></a><span data-ttu-id="9bdc5-109">De DNS-record maken</span><span class="sxs-lookup"><span data-stu-id="9bdc5-109">Create the DNS record</span></span>

1. <span data-ttu-id="9bdc5-110">Selecteer **Aanmelden**op de [Console van Google-beheer.](https://www.google.com/work/apps/business)</span><span class="sxs-lookup"><span data-stu-id="9bdc5-110">At the [Google Admin console](https://www.google.com/work/apps/business), select **Sign In**.</span></span>
    
    ![Google-Apps-Configure-1-1-0](../../media/37a6e9f6-319e-4c02-aa18-d8d06df7953d.png)
  
2. <span data-ttu-id="9bdc5-112">Voer uw domeinnaam in en selecteer **Ga**.</span><span class="sxs-lookup"><span data-stu-id="9bdc5-112">Enter your domain name, and then select **Go**.</span></span>
    
    ![Knopafbeelding](../../media/2caf8dcb-4d40-4cfa-bc40-d634e454e699.png)
  
3. <span data-ttu-id="9bdc5-114">Selecteer onder aan de pagina **meer besturingselementen**.</span><span class="sxs-lookup"><span data-stu-id="9bdc5-114">At the bottom of the page, select **More controls**.</span></span>
    
    ![Google-Apps-Configure-1-2-0](../../media/1518ff78-035b-423e-85a3-c16d7faa0968.png)
  
4. <span data-ttu-id="9bdc5-116">Selecteer **Domeinen**.</span><span class="sxs-lookup"><span data-stu-id="9bdc5-116">Select **Domains**.</span></span>
    
    ![Google-Apps-Configure-1-2-1](../../media/c2972c06-9bca-43bd-9876-2cee63043bf1.png)
  
5. <span data-ttu-id="9bdc5-118">Selecteer op de pagina **Domeinen** de optie **Domeinen toevoegen/verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="9bdc5-118">On the **Domains** page, select **Add/remove domains**.</span></span>
    
    ![Google-Apps-Configure-1-2-2](../../media/07b8068f-9a05-40aa-a041-fc495c729a18.png)
  
6. <span data-ttu-id="9bdc5-120">Selecteer op de pagina **Domeinen** de optie **Geavanceerde DNS-instellingen**.</span><span class="sxs-lookup"><span data-stu-id="9bdc5-120">On the **Domains** page, select **Advanced DNS settings**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9bdc5-121">Als u geen domeinnaam via Google hebt aangeschaft terwijl u zich registreerde voor uw account bij **Google Apps for Work**, hebt u geen **Geavanceerde DNS-instellingen** op uw pagina **Domeinen**.</span><span class="sxs-lookup"><span data-stu-id="9bdc5-121">If you didn't purchase a domain name through Google while signing up for your **Google Apps for Work** account, you won't have **Advanced DNS settings** on your **Domains** page.</span></span> <span data-ttu-id="9bdc5-122">U moet dan rechtstreeks naar de website van uw domeinhost gaan voor toegang tot uw DNS-instellingen, en vervolgens deze en de volgende stappen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="9bdc5-122">Instead, you must go directly to your domain host's web site to access your DNS settings and to perform this and the following steps.</span></span> <span data-ttu-id="9bdc5-123">Zie [Toegang tot de domeininstellingen van g suite](https://support.google.com/a/answer/54693?hl=en) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9bdc5-123">See [Access your G Suite domain settings](https://support.google.com/a/answer/54693?hl=en) for more information.</span></span> 
  
    ![Google-Apps-eNom-Configureren-1-3](../../media/b244b29c-e479-40be-b380-4ffa0f74b421.png)
  
7. <span data-ttu-id="9bdc5-125">Selecteer **aanmelden bij DNS-console**op de pagina **Geavanceerde DNS-instellingen.**</span><span class="sxs-lookup"><span data-stu-id="9bdc5-125">On the **Advanced DNS settings** page, select **Sign in to DNS Console**.</span></span> <span data-ttu-id="9bdc5-126">Noteer de **aanmeldingsnaam** en het **wachtwoord**.</span><span class="sxs-lookup"><span data-stu-id="9bdc5-126">Note the **Sign-in name** and **Password** information.</span></span> <span data-ttu-id="9bdc5-127">U hebt deze nodig in de volgende stap.</span><span class="sxs-lookup"><span data-stu-id="9bdc5-127">You'll need it in the next step.</span></span> 
    
    ![Google-Apps-eNom-Configureren-1-4](../../media/056a2767-462f-4847-acee-d01e3f773add.png)
  
8. <span data-ttu-id="9bdc5-129">Meld u op de pagina **Geavanceerde DNS-instellingen** aan bij **Domeinbeheer** van Google met de **aanmeldingsnaam** en het **wachtwoord**.</span><span class="sxs-lookup"><span data-stu-id="9bdc5-129">Log in to the Google **Domain Manager** using the **Sign-in name** and **Password** from the **Advanced DNS settings** page.</span></span> 
    
    ![Google-Apps-eNom-Configureren-1-5](../../media/08b74652-8cdb-4560-a5fd-0899f86deee8.png)
  
9. <span data-ttu-id="9bdc5-131">Selecteer op de ***pagina domain_name*** in de sectie **Hostrecords** de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="9bdc5-131">On the ***domain_name*** page, in the **Host Records** section, select **Edit**.</span></span>
    
    ![Google-Apps-eNom-Configureren-1-6](../../media/d54fec18-b9d1-4796-8397-0393c964eade.png)
  
10. <span data-ttu-id="9bdc5-133">Selecteer in de sectie **Hostrecords** de optie **Nieuw toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="9bdc5-133">In the **Host Records** section, select **Add New**.</span></span>
    
    ![Google-Apps-eNom-Configureren-1-7](../../media/3562806a-4328-4e60-a717-0566841204cf.png)
  
11. <span data-ttu-id="9bdc5-135">Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.</span><span class="sxs-lookup"><span data-stu-id="9bdc5-135">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="9bdc5-136">**HOST**</span><span class="sxs-lookup"><span data-stu-id="9bdc5-136">**HOST**</span></span>|<span data-ttu-id="9bdc5-137">**TXT VALUE**</span><span class="sxs-lookup"><span data-stu-id="9bdc5-137">**TXT VALUE**</span></span>|<span data-ttu-id="9bdc5-138">**RECORDTYPE**</span><span class="sxs-lookup"><span data-stu-id="9bdc5-138">**RECORD TYPE**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> ||<span data-ttu-id="9bdc5-139">TXT</span><span class="sxs-lookup"><span data-stu-id="9bdc5-139">TXT</span></span>  <br/> |

    > [!NOTE]
    > <span data-ttu-id="9bdc5-140">Dit is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="9bdc5-140">This is an example.</span></span> <span data-ttu-id="9bdc5-141">Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365.</span><span class="sxs-lookup"><span data-stu-id="9bdc5-141">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> 
  
    [<span data-ttu-id="9bdc5-142">Hoe kan ik dit vinden?</span><span class="sxs-lookup"><span data-stu-id="9bdc5-142">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)
  
12. <span data-ttu-id="9bdc5-143">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="9bdc5-143">Select **Save**.</span></span>
    
    ![Google-Apps-eNom-Configureren-1-9](../../media/7a6f7b45-8f79-487b-afe4-05949c2c04e8.png)
  
13. <span data-ttu-id="9bdc5-145">Selecteer **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="9bdc5-145">Select **Save Changes**.</span></span>
    
    ![Google-Apps-Configure-1-11](../../media/7f321236-33fb-4a7d-9d03-26605e9e558c.png)
  
> [!NOTE]
>  <span data-ttu-id="9bdc5-p105">Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9bdc5-p105">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
