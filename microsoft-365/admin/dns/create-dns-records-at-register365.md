---
title: DNS-records bij Register365 maken voor Office 365
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
ms.assetid: 004030b4-10ad-4026-96e7-011b6afc7e73
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services bij Register365 voor Office 365.
ms.openlocfilehash: 66c5c29d533b6897280ff99c449988c160022cf8
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211084"
---
# <a name="create-dns-records-at-register365-for-office-365"></a>DNS-records bij Register365 maken voor Office 365

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Als Register365 uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen. 
  
Dit zijn de belangrijkste records om toe te voegen.  
  
- [Een TXT-record toevoegen voor verificatie](#add-a-txt-record-for-verification)
    
- [Voeg een MX-record toe zodat e-mail voor uw domein bij Office 365 terechtkomt](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [De zes CNAME-records toevoegen die voor Office 365 vereist zijn](#add-the-six-cname-records-that-are-required-for-office-365)
    
- [Een TXT-record voor SPF toevoegen om spam tegen te gaan](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Voeg de vier SRV-records toe die voor Office 365 vereist zijn.](#add-the-two-srv-records-that-are-required-for-office-365)
    
Nadat u deze records bij Office 365 hebt toegevoegd, wordt uw domein ingesteld voor de Office 365-services.
  
Zie [Een openbare website gebruiken met Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9) voor informatie over webhosting en DNS voor websites met Office 365.
  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie
<a name="BKMK_verify"> </a>

Voordat u uw domein met Office 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Office 365 bewezen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
1. U gaat eerst naar uw domeinenpagina bij Register365 via [deze koppeling](https://admin.register365.com/dns/). U wordt gevraagd u eerst aan te melden.
    
    ![De aanmeldingspagina van het configuratiescherm](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. Zoek op de pagina **Dashboard** de naam van het domein dat u bijwerkt, en kies vervolgens **DNS Settings** in de vervolgkeuzelijst. 
    
    (Mogelijk moet u omlaag schuiven.)
    
    ![DNS-instellingen selecteren in de lijst](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. Typ of kopieer en plak op de pagina **Add/Modify DNS Zone**, in de sectie **A-, CNAME-, AAAA-, TXT- en NS-records**, de waarden uit de volgende tabel in de vakken voor de nieuwe record. 
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
    (Als u een rij moet toevoegen, selecteert u **A/CNAME RECORDS toevoegen (+)**.)
    
    (Mogelijk moet u omlaag schuiven.)
    
    |**Hostnaam**|**Type**|**Resultaat**|
    |:-----|:-----|:-----|
    |(Laat dit veld leeg.)  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Waarden invoeren op de pagina DNS-zone toevoegen/wijzigen](../../media/22326005-de95-464d-8e33-08ea31a89b2d.png)
  
4. Kies **Opslaan**.
    
    (Mogelijk moet u omlaag schuiven.)
    
    ![Selecteer Opslaan](../../media/157cfb98-d5d0-48a3-8dd1-c4e759c2f8a8.png)
  
5. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Office 365 en vraagt u of Office 365 naar de record wil zoeken.
  
Wanneer in Office 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.
  
1. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.
    
2. Kies op de pagina **Domeinen** de naam van het domein dat u verifieert. 
    
    
  
3. Kies **Start setup** op de pagina **Setup**.
    
    
  
4. Kies **Verifiëren** op de pagina **Domein verifiëren**.
    
    
  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Een MX-record toevoegen zodat e-mail voor uw domein bij Office 365 terechtkomt
<a name="BKMK_add_MX"> </a>

1. U gaat eerst naar uw domeinenpagina bij Register365 via [deze koppeling](https://admin.register365.com/dns/). U wordt gevraagd u eerst aan te melden.
    
    ![De aanmeldingspagina van het configuratiescherm](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. Zoek op de pagina **Dashboard** de naam van het domein dat u bijwerkt, en kies vervolgens **DNS Settings** in de vervolgkeuzelijst. 
    
    (Mogelijk moet u omlaag schuiven.)
    
    ![DNS-instellingen selecteren in de lijst](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. Typ of kopieer en plak op de pagina **Add/Modify DNS Zone**, in de sectie **Mail Exchange records**, de waarden uit de volgende tabel in de vakken voor de nieuwe record. 
    
    (Mogelijk moet u omlaag schuiven.)
    
    |**Hostnaam**|**Priority**|**Resultaat**|
    |:-----|:-----|:-----|
    |(Laat dit veld leeg.)  <br/> |1  <br/> Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit. <br/> | *\<domeinsleutel\>*  .mail.protection.outlook.com  <br/> **Let op:** Haal uw * \<domeinsleutel\> * op uit uw Office 365-account.  [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)     |
   
    ![Waarden invoeren op de pagina DNS-zone toevoegen/wijzigen](../../media/2d3645a8-9cb8-435e-b895-5535b6b1fffd.png)
  
4. Kies **Opslaan**.
    
    (Mogelijk moet u omlaag schuiven.)
    
    ![Selecteer Opslaan](../../media/0e565fb0-a126-4a48-8ff7-2c2d79d4af32.png)
  
5. Als er in de sectie **Mail exchange records** andere MX-records worden vermeld, verwijdert u elke record door deze te selecteren en vervolgens op het toetsenbord op de toets **Delete** te drukken. 
    
    ![Deleting records in the Mail exchange records section](../../media/8cc37e4f-2e85-4242-af0e-78149434167f.png)
  
6. Kies **Opslaan**.
    
    (Mogelijk moet u omlaag schuiven.)
    
    ![Selecteer Opslaan](../../media/1fb69bb5-b5df-4060-adf1-eb26cfaa6c4f.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>De zes CNAME-records toevoegen die voor Office 365 vereist zijn
<a name="BKMK_add_CNAME"> </a>

1. U gaat eerst naar uw domeinenpagina bij Register365 via [deze koppeling](https://admin.register365.com/dns/). U wordt gevraagd u eerst aan te melden.
    
    ![De aanmeldingspagina van het configuratiescherm](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. Zoek op de pagina **Dashboard** de naam van het domein dat u bijwerkt, en kies vervolgens **DNS Settings** in de vervolgkeuzelijst. 
    
    (Mogelijk moet u omlaag schuiven.)
    
    ![DNS-instellingen selecteren in de lijst](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. Typ of kopieer en plak op de pagina **Add/Modify DNS Zone** in de sectie **A-, CNAME, AAAA, TXT and NS Records** de waarden uit de volgende tabel in de vakken voor de nieuwe records. 
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
    (Als u een rij moet toevoegen, selecteert u **A/CNAME RECORDS toevoegen (+)**.)
    
    (Mogelijk moet u omlaag schuiven.)
    
    |****Host Name****|****Type****|****Result****|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![Waarden invoeren op de pagina DNS-zone toevoegen/wijzigen](../../media/3b79f0de-9cab-4c98-8fa8-c92b35241e8b.png)
  
4. Kies **Opslaan**.
    
    ![Selecteer Opslaan](../../media/8ded6428-af97-4fd8-9104-477fa22a5586.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Een TXT-record voor SPF toevoegen om spam tegen te gaan
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Office 365 te maken. In plaats daarvan voegt u de vereiste Office 365-waarden toe aan de huidige record, zodat u beschikt over  *één*  SPF-record waarin beide sets waarden zijn opgenomen. 
  
1. U gaat eerst naar uw domeinenpagina bij Register365 via [deze koppeling](https://admin.register365.com/dns/). U wordt gevraagd u eerst aan te melden.
    
    ![De aanmeldingspagina van het configuratiescherm](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. Zoek op de pagina **Dashboard** de naam van het domein dat u bijwerkt, en kies vervolgens **DNS Settings** in de vervolgkeuzelijst. 
    
    (Mogelijk moet u omlaag schuiven.)
    
    ![DNS-instellingen selecteren in de lijst](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. Typ of kopieer en plak op de pagina **Add/Modify DNS Zone**, in de sectie **A-, CNAME-, AAAA-, TXT- en NS-records**, de waarden uit de volgende tabel in de vakken voor de nieuwe record. 
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
    (Als u een rij moet toevoegen, selecteert u **A/CNAME RECORDS toevoegen (+)**.)
    
    (Mogelijk moet u omlaag schuiven.)
    
    |**Hostnaam**|**Type**|**Resultaat**|
    |:-----|:-----|:-----|
    |(Laat dit veld leeg.)  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.           |
   
    ![Waarden invoeren op de pagina DNS-zone toevoegen/wijzigen](../../media/33976398-da8a-439b-8e3d-534503b20ee0.png)
  
4. Kies **Opslaan**.
    
    (Mogelijk moet u omlaag schuiven.)
    
    ![Selecteer Opslaan](../../media/1d8da122-4861-4ca3-bc9b-d01f18557d4c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>De twee SRV-records toevoegen die voor Office 365 vereist zijn
<a name="BKMK_add_SRV"> </a>

1. U gaat eerst naar uw domeinenpagina bij Register365 via [deze koppeling](https://admin.register365.com/dns/). U wordt gevraagd u eerst aan te melden.
    
    ![De aanmeldingspagina van het configuratiescherm](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. Zoek op de pagina **Dashboard** de naam van het domein dat u bijwerkt, en kies vervolgens **DNS Settings** in de vervolgkeuzelijst. 
    
    (Mogelijk moet u omlaag schuiven.)
    
    ![DNS-instellingen selecteren in de lijst](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. Typ of kopieer en plak op de pagina **Add/Modify DNS Zone** in de sectie **Service records** de waarden uit de volgende tabel in de vakken voor de nieuwe records. 
    
    (Mogelijk moet u omlaag schuiven.)
    
    |**Name**|**Prioriteit**|**Gewicht**|**Poort**|**Result**|
    |:-----|:-----|:-----|:-----|:-----|
    |_sip._tls  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls._tcp  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   
    ![Waarden invoeren in de sectie Servicerecords](../../media/56bb1813-90e2-40c8-98bf-750e2dc3f8b6.png)
  
4. Kies **Opslaan**.
    
    (Mogelijk moet u omlaag schuiven.)
    
    ![Selecteer Opslaan](../../media/3b80757c-01e1-492d-b2ce-f721d71f7235.png)
  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
