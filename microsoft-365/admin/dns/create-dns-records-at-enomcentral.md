---
title: DNS-records maken bij eNomCentral voor Microsoft
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
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: Meer informatie over het verifiëren van uw domein en het instellen van DNS-records voor e-mail, Skype voor Bedrijven Online en andere services bij eNomCentral voor Microsoft.
ms.openlocfilehash: c964729c052f5c0b61441f14ce15a167caa06b72
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780395"
---
# <a name="create-dns-records-at-enomcentral-for-microsoft"></a>DNS-records maken bij eNomCentral voor Microsoft

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Als eNomCentral uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.
  
Nadat u deze records hebt toegevoegd bij eNomCentral, wordt uw domein ingesteld om te werken met Microsoft-services.

  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie
<a name="BKMK_verify"> </a>

Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
Volg onderstaande stappen of [bekijk de video (start op 0:46)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).
  
1. To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.
    
    ![Afbeelding van het knopen -1-1 van afbeelding](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. Selecteer onder **mijn domeinen**de naam van het domein dat u wilt bewerken.
    
    ![Afbeelding van het knopen -afbeeldingsman van eNom-BP-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. Kies in de vervolgkeuzelijst **Manage Domain** de optie **Host Records**.
    
    ![afbeelding van het aandeel ENom-BP-1-1](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)
  
4. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.
    
    Kies de waarde **Recordtype** in de vervolgkeuzelijst.
    
    ||||
    |:-----|:-----|:-----|
    |**Host Name** <br/> |**Recordtype** <br/> |**Address** <br/> |
    |@  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![afbeelding van het aandeel ENom-BP-1-2](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)
  
5. Selecteer **opslaan**.
    
    ![afbeelding van het aandeel ENom-BP-1-3](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)
  
6. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft 365 en vraagt u of Microsoft 365 naar de record wil zoeken.
  
Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.
  
1. Ga in het Microsoft-beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.

    
2. Kies op de pagina **Domeinen** de naam van het domein dat u verifieert. 
    
    
  
3. Kies **Start setup** op de pagina **Setup**.
    
    
  
4. Kies **Verifiëren** op de pagina **Domein verifiëren**.
    
    
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden
<a name="BKMK_add_MX"> </a>

Volg onderstaande stappen of [bekijk de video (start op 3:40)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).
  
1. To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.
    
    ![Afbeelding van het knopen -1-1 van afbeelding](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. Selecteer onder **mijn domeinen**de naam van het domein dat u wilt bewerken.
    
    ![Afbeelding van het knopen -afbeeldingsman van eNom-BP-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. Kies in de vervolgkeuzelijst **Manage Domain** de optie **Email Settings**.
    
    ![Afbeelding van het knopen -1-3 afbeelding van het eNom-BP-bp-](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)
  
4. Kies in de vervolgkeuzelijst **Service Selection** de optie **User (MX)**.
    
    ![Afbeelding van het knopen -1-4 afbeelding van het eNom-BP-](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)
  
5. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.
    
    |**Hostnaam**|**Address**|**Pref**|
    |:-----|:-----|:-----|
    |@  <br/> | *\<domain-key\>* mail.protection.outlook.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> **Let op:** Haal je *\<domain-key\>* van je Microsoft-account.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |10  <br/> Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit.    <br/> |
       
   ![Afbeelding van het knopen -2-1 afbeelding van het eNom-BP-](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)
  
6. Selecteer **opslaan**.
    
    ![Afbeelding van het knopen -2-2 voor afbeelding van het enom-BP-](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)
  
7. Als er andere MX-records zijn, schakelt u de selectievakjes voor deze records in om deze te selecteren.
    
    ![Afbeelding van het knopen -2-3 afbeelding van het eNom-BP-bp-2-3](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)
  
8. Selecteer **Verwijderen gecontroleerd**.
    
    ![Afbeelding van het knopen -2-4 afbeelding van het eNom-BP-](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>De CNAME-records toevoegen die zijn vereist voor Microsoft 
<a name="BKMK_add_CNAME"> </a>

Volg onderstaande stappen of [bekijk de video (start op 4:24)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).
  
1. To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.
    
    ![Afbeelding van het knopen -1-1 van afbeelding](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. Selecteer onder **mijn domeinen**de naam van het domein dat u wilt bewerken.
    
    ![Afbeelding van het knopen -afbeeldingsman van eNom-BP-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. Kies in de vervolgkeuzelijst **Manage Domain** de optie **Host Records**.
    
    ![Afbeelding van het knopen -afbeeldingsman van ENom-BP-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. Selecteer **een nieuwe rij**.
    
    ![Afbeelding van het knopen -afbeeldingsman van eNom-BP-3-1](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)
  
5. Typ of kopieer en plak de volgende waarden in de vakken voor de zes nieuwe records.
    
Kies de waarde **Recordtype** in de vervolgkeuzelijst.
        
    |**Host Name**|**Recordtype**|**Address**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME (alias)  <br/> |autodiscover.outlook.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
    |sip  <br/> |CNAME (alias)  <br/> |sipdir.online.lync.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
    |lyncdiscover  <br/> |CNAME (alias)  <br/> |webdir.online.lync.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
    |enterpriseregistration  <br/> |CNAME (alias)  <br/> |enterpriseregistration.windows.net.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
    |enterpriseenrollment  <br/> |CNAME (alias)  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
   
    ![eNom-BP-Configure-3-2](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)
  
6. Selecteer **opslaan**.
    
    ![Afbeelding van het knopen -3-3 van eNom-BP](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Een TXT-record voor SPF toevoegen om spam tegen te gaan
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft. Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat.
  
Volg onderstaande stappen of [bekijk de video (start op 5:12)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).
  
1. To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.
    
    ![Afbeelding van het knopen -1-1 van afbeelding](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. Selecteer onder **mijn domeinen**de naam van het domein dat u wilt bewerken.
    
    ![Afbeelding van het knopen -afbeeldingsman van eNom-BP-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. Kies in de vervolgkeuzelijst **Manage Domain** de optie **Host Records**.
    
    ![Afbeelding van het knopen -afbeeldingsman van ENom-BP-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.
    
Kies de waarde **Recordtype** in de vervolgkeuzelijst.
    
    |**Host Name**|**Recordtype**|**Address**|
    |:-----|:-----|:-----|
    |@  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.           |
   
   ![Afbeelding van het knopen -afbeeldingsman van eNom-BP-4-1](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)
  
5. Selecteer **opslaan**.
    
    ![Afbeelding van het knopen -afbeeldingsman van eNom-BP-4-2](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>De twee SRV-records toevoegen die zijn vereist voor Microsoft
<a name="BKMK_add_SRV"> </a>

Volg onderstaande stappen of [bekijk de video (start op 5:50)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).
  
1. To get started, go to your domains page at eNom Central by using [this link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). You'll be prompted to login.
    
    ![Afbeelding van het knopen -1-1 van afbeelding](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. Selecteer onder **mijn domeinen**de naam van het domein dat u wilt bewerken.
    
    ![Afbeelding van het knopen -afbeeldingsman van eNom-BP-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. Kies in de vervolgkeuzelijst **Manage Domain** de optie **Host Records**.
    
    ![Afbeelding van het knopen -afbeeldingsman van ENom-BP-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. Selecteer rechts van de **nieuwe rij** **SRV- of SPF-record toevoegen**.
    
    ![Afbeelding van het knopen -afbeeldingsman van eNom-BP-5-1](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)
  
5. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de twee nieuwe records.
    
    |**Service**|**Protocol**|**Prioriteit**|**Gewicht**|**Poort**|**Target          (Hostname)**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
   
    ![Afbeelding van het knopen -afbeeldingsman van eNom-BP-5-2](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)
  
6. Opslaan **selecteren**
    
    ![Afbeelding van het knopen -afbeeldingsman van ENom-BP-5-3](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  

