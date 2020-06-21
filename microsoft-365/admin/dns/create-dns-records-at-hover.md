---
title: DNS-records maken bij Hover for Microsoft
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
ms.assetid: 46ab4b10-6857-44b1-b08d-d1b5f45a69c6
description: Meer informatie over het verifiëren van uw domein en het instellen van DNS-records voor e-mail, Skype voor Bedrijven Online en andere services bij Hover voor Microsoft.
ms.openlocfilehash: e51cb77831f4e29ac3a51602a1bb19f8b0c9e0e3
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780347"
---
# <a name="create-dns-records-at-hover-for-microsoft"></a>DNS-records maken bij Hover for Microsoft

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Als Hover uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.
     
Nadat u deze records hebt toegevoegd bij Hover, wordt uw domein ingesteld om te werken met Microsoft-services.
  

  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie
<a name="BKMK_verify"> </a>

Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
Volg onderstaande stappen of [bekijk de video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).
  
1. To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.
    
    ![Aanmelden](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. Selecteer onder **Uw domeinen beheren**de naam van het domein dat u wilt bewerken.
    
    ![Een domein selecteren](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. Selecteer het tabblad **DNS.** 
    
    ![Het tabblad DNS selecteren](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. Selecteer **Nieuw toevoegen**.
    
    ![Selecteer Nieuw toevoegen](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. Selecteer in de vakken voor de nieuwe record de optie **TXT** voor het **recordtype** en typ of kopieer en plak de waarden uit de volgende tabel.
    
    ||||
    |:-----|:-----|:-----|
    |Hostname  <br/> |Recordtype  <br/> |Value  <br/> |
    |@  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![DNS-waarden typen of kopiëren en plakken](../../media/3b0d19f9-4138-47a7-aab2-137ad120ded6.png)
  
6. Kies **Opslaan**.
    
    ![Selecteer Opslaan](../../media/07dcf68e-34be-47dc-999e-0216de68cc9c.png)
  
7. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
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

Volg onderstaande stappen of [bekijk de video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).
  
1. To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.
    
    ![Aanmelden](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. Selecteer onder **Uw domeinen beheren**de naam van het domein dat u wilt bewerken.
    
    ![Een domein selecteren](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. Selecteer het tabblad **DNS.** 
    
    ![Het tabblad DNS selecteren](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. Selecteer **Nieuw toevoegen**.
    
    ![Selecteer Nieuw toevoegen](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. Selecteer in de vakken voor de nieuwe record de optie **MX** voor het **recordtype** en typ of kopieer en plak de waarden uit de volgende tabel.
    
    |**Hostnaam**|**Record Type**|**Priority**|**Hostname**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |0  <br/> Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit. <br/> | *\<domain-key\>*,,Mail.protection.outlook.com  <br/> **Let op:** Haal je *\<domain-key\>* van je Microsoft-account.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![DNS-waarden typen of kopiëren en plakken](../../media/2c8915fa-04a8-4d2a-a8ae-a79de0c8ef99.png)
  
6. Kies **Opslaan**.
    
    ![Selecteer Opslaan](../../media/266c30a4-6703-48fb-a919-b510ed966193.png)
  
7. Als er andere MX-records zijn, verwijdert u deze met behulp van de volgende tweestapsprocedure:
    
    Selecteer eerst verwijderen door een record te **verwijderen.**
    
    ![Muis over en selecteer Verwijderen](../../media/2ddf4902-8cd2-4969-a418-2cb592741e86.png)
  
    Selecteer ten tweede **Ja** om elke verwijdering te bevestigen. 
    
    ![Selecteer Ja om verwijdering te bevestigen](../../media/48756bd5-0205-4c4d-9803-9246795dbf4a.png)
  
    Herhaal dit proces tot u alle MX-records hebt verwijderd, behalve die welke u eerder in deze procedure hebt toegevoegd.
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>De CNAME-records toevoegen die zijn vereist voor Microsoft
<a name="BKMK_add_CNAME"> </a>

Volg onderstaande stappen of [bekijk de video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).
  
1. To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.
    
    ![Aanmelden](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. Selecteer onder **Uw domeinen beheren**de naam van het domein dat u wilt bewerken.
    
    ![Een domein selecteren](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. Selecteer het tabblad **DNS.** 
    
    ![Het tabblad DNS selecteren](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. Voeg de eerste van de zes CNAME-records toe.
    
    Selecteer **Nieuw toevoegen**.
    
    ![Selecteer Nieuw toevoegen](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. Selecteer in de lege vakken voor de nieuwe record de optie **CNAME** voor het **recordtype** en typ of kopieer en plak de waarden uit de eerste rij in de volgende tabel.
    
    |**Hostnaam**|**Record Type**|**Doelhost**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![DNS-waarden typen of kopiëren en plakken](../../media/6ae607f8-d26e-47f0-a0f2-3487d37e8c7f.png)
  
6. Kies **Opslaan**.
    
    ![Selecteer Opslaan](../../media/69aa3546-32de-4c17-a2e2-8c0cd133efaa.png)
  
7. Met de voorgaande drie stappen en de waarden uit de andere vijf rijen in de tabel voegt u de andere vijf CNAME-records toe.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Een TXT-record voor SPF toevoegen om spam tegen te gaan
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft. Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat. 
  
Volg onderstaande stappen of [bekijk de video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).
  
1. To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.
    
    ![Aanmelden](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. Selecteer onder **Uw domeinen beheren**de naam van het domein dat u wilt bewerken.
    
    ![Een domein selecteren](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. Selecteer het tabblad **DNS.** 
    
    ![Het tabblad DNS selecteren](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. Selecteer **Nieuw toevoegen**.
    
    ![Selecteer Nieuw toevoegen](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. Selecteer in de vakken voor de nieuwe record de optie **TXT** voor het **Recordtype** en typ of kopieer en plak de waarden uit de volgende tabel.
    
    |**Hostname**|**Record Type**|**Value**|
    |:-----|:-----|:-----|
    |@  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.           |
   
    ![DNS-waarden typen of kopiëren en plakken](../../media/ed36b9e0-aaa9-45fb-804d-7d4e82ba0c7f.png)
  
6. Kies **Opslaan**.
    
    ![Selecteer Opslaan](../../media/13a395b9-e0e8-4393-b568-5f99b2da39da.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>De twee SRV-records toevoegen die zijn vereist voor Microsoft
<a name="BKMK_add_SRV"> </a>

Volg onderstaande stappen of [bekijk de video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).
  
1. To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains). You'll be prompted to sign in.
    
    ![Aanmelden](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. Selecteer onder **Uw domeinen beheren**de naam van het domein dat u wilt bewerken.
    
    ![Een domein selecteren](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. Selecteer het tabblad **DNS.** 
    
    ![Het tabblad DNS selecteren](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. Voeg de eerste van de twee SRV-records toe.
    
    Selecteer **Nieuw toevoegen**.
    
    ![Selecteer Nieuw toevoegen](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. Selecteer in de lege vakken voor de nieuwe record de optie **SRV** voor het **recordtype** en typ of kopieer en plak de waarden uit de eerste rij in de volgende tabel.
    
    |**Hostname**|**Record Type**|**Prioriteit**|**Gewicht**|**Poort**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip._tls  <br/> |SRV  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls._tcp  <br/> |SRV  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   
    ![DNS-waarden typen of kopiëren en plakken](../../media/67562cd6-c598-4c37-af53-626f153c0197.png)
  
6. Kies **Opslaan**.
    
    ![Selecteer Opslaan](../../media/0d7ec216-9277-4709-b637-e94c8662730f.png)
  
7. Met de drie voorgaande stappen en de waarden uit de tweede rij in de tabel voegt u de andere SRV-record toe.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
