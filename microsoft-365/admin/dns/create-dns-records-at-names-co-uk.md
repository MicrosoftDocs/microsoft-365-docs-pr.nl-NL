---
title: DNS-records maken op Names.co.uk voor Microsoft
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
ms.assetid: b6c15128-b456-49b4-8b5e-5b823c700f26
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services op Names.co.uk voor Microsoft.
ms.openlocfilehash: 2df1a18f00fd7cd48b0d24860ddcf651c2fdac4e
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048937"
---
# <a name="create-dns-records-at-namescouk-for-microsoft"></a>DNS-records maken op Names.co.uk voor Microsoft

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Als Names.co.uk uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online enzovoort in te stellen.
    
Nadat u deze records hebt toegevoegd aan Names.co.uk, wordt uw domein ingesteld voor gebruik met Microsoft-services.
  

  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie
<a name="BKMK_verify"> </a>

Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij Names.co.uk via [deze koppeling](https://account.names.co.uk/dashboard#/). U wordt gevraagd u eerst aan te melden.
    
    ![Afbeelding van het te maken dat u aangeeft op basis van afbeelding van het gebruik](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. Zoek op de pagina **Dashboard** de naam van het domein dat u bijwerkt, en kies vervolgens **DNS-instellingen** in de vervolgkeuzelijst. 
    
    (Mogelijk moet u omlaag schuiven.)
    
    ![Afbeelding van het te maken dat u aangeeft op basis van afbeelding van het gebruik](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. Typ of kopieer en plak op de pagina **Add/Modify DNS Zone**, in de sectie **A, CNAME, AAAA, TXT and NS records**, de waarden uit de volgende tabel in de vakken voor de nieuwe record. 
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
    (Als u een rij moet toevoegen, selecteert u **A/CNAME RECORDS toevoegen (+)**.)
    
    (Mogelijk moet u omlaag schuiven.)
        
    |**Hostnaam**|**Type**|**Resultaat**|
    |:-----|:-----|:-----|
    |(Laat dit veld leeg.)  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)    |
       
    ![Afbeelding van het te maken van de afbeelding van de knop Verifiëren-1-1](../../media/91ed1f22-a796-418d-bbb0-345e2cd99bde.png)
  
4. Kies **Opslaan**.
    
    (Mogelijk moet u omlaag schuiven.)
    
    ![Afbeelding van het te maken van de afbeelding van de knop Verifiëren-1-2](../../media/40e991f9-2209-4210-8762-981cca670d70.png)
  
5. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.
  
Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.
  
1. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.
    
2. Kies op de pagina **Domeinen** de naam van het domein dat u verifieert. 
    
    
  
3. Kies **Start setup** op de pagina **Setup**.
    
    
  
4. Kies **Verifiëren** op de pagina **Domein verifiëren**.
    
    
  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden
<a name="BKMK_add_MX"> </a>

1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij Names.co.uk via [deze koppeling](https://account.names.co.uk/dashboard#/). U wordt gevraagd u eerst aan te melden.
    
    ![Afbeelding van het te maken dat u aangeeft op basis van afbeelding van het gebruik](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. Zoek op de pagina **Dashboard** de naam van het domein dat u bijwerkt, en kies vervolgens **DNS-instellingen** in de vervolgkeuzelijst. 
    
    (Mogelijk moet u omlaag schuiven.)
    
    ![Afbeelding van het te maken dat u aangeeft op basis van afbeelding van het gebruik](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. Typ of kopieer en plak op de pagina **Add/Modify DNS Zone**, in de sectie **Mail Exchange records**, de waarden uit de volgende tabel in de vakken voor de nieuwe record. 
    
    (Mogelijk moet u omlaag schuiven.)
    
    |**Hostnaam**|**Priority**|**Resultaat**|
    |:-----|:-----|:-----|
    |(Laat dit veld leeg.)  <br/> |1  <br/> Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit. <br/> | *\<domeinsleutel\>*  .mail.protection.outlook.com  <br/> > [!NOTE]> Uw * \<domeinsleutel\> * ophalen van uw Microsoft-account.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![Afbeelding van het te maken dat u aangeeft op basis van afbeelding van het gebruik](../../media/e211d73d-864f-4114-864b-8e636c69f595.png)
  
4. Kies **Opslaan**.
    
    (Mogelijk moet u omlaag schuiven.)
    
    ![Afbeelding van het te maken dat u aangeeft op basis van afbeelding van het gebruik](../../media/01e6c801-daa2-40ca-84f9-dcac6422257c.png)
  
5. Als er in de sectie **Mail Exchange records** andere MX-records worden vermeld, verwijdert u elke record door deze te selecteren en vervolgens op het toetsenbord op de toets **Delete** te drukken. 
    
    ![Afbeelding van het te maken dat u aangeeft op basis van afbeelding van het gebruik](../../media/f8e43926-b724-4690-94e7-ec4b8d7a8da5.png)
  
6. Kies **Opslaan**.
    
    (Mogelijk moet u omlaag schuiven.)
    
    ![Afbeelding van het te maken dat u aangeeft op basis van afbeelding van het gebruik](../../media/cd705919-d0bd-408f-82be-b54e732cb05c.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Voeg de zes CNAME-records toe die nodig zijn voor Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij Names.co.uk via [deze koppeling](https://account.names.co.uk/dashboard#/). U wordt gevraagd u eerst aan te melden.
    
    ![Afbeelding van het te maken dat u aangeeft op basis van afbeelding van het gebruik](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. Zoek op de pagina **Dashboard** de naam van het domein dat u bijwerkt, en kies vervolgens **DNS-instellingen** in de vervolgkeuzelijst. 
    
    (Mogelijk moet u omlaag schuiven.)
    
    ![Afbeelding van het te maken dat u aangeeft op basis van afbeelding van het gebruik](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. Typ of kopieer en plak op de pagina **Add/Modify DNS Zone**, in de sectie **A, CNAME, AAAA, TXT and NS records**, de waarden uit de volgende tabel in de vakken voor de nieuwe record. 
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
    (Als u een rij moet toevoegen, selecteert u **A/CNAME RECORDS toevoegen (+)**.)
    
    (Mogelijk moet u omlaag schuiven.)
    
    |**Host Name**|**Type**|**Result**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
       
    ![Afbeelding van het te maken van afbeelding van het](../../media/392772bf-2ed3-4959-9a9a-bb1611905e86.png)
  
4. Kies **Opslaan**.
    
    ![Afbeelding van het te maken van afbeelding van het](../../media/c009795e-7eef-4804-bf23-556f498306cc.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Een TXT-record voor SPF toevoegen om spam tegen te gaan
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft. Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat.
  
1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij Names.co.uk via [deze koppeling](https://account.names.co.uk/dashboard#/). U wordt gevraagd u eerst aan te melden.
    
    ![Afbeelding van het te maken dat u aangeeft op basis van afbeelding van het gebruik](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. Zoek op de pagina **Dashboard** de naam van het domein dat u bijwerkt, en kies vervolgens **DNS-instellingen** in de vervolgkeuzelijst. 
    
    (Mogelijk moet u omlaag schuiven.)
    
    ![Afbeelding van het te maken dat u aangeeft op basis van afbeelding van het gebruik](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. Selecteer op de pagina **DNS-zones op account** in de kolom **Domeinnaam** de naam van het domein dat u bijwerkt. 
    
    ![Afbeelding van het te maken van de afbeelding van het](../../media/20254eec-6952-47ba-b12b-da32860ee7ef.png)
  
4. Typ of kopieer en plak op de pagina **Add/Modify DNS Zone**, in de sectie **A-, CNAME-, AAAA-, TXT- en NS-records**, de waarden uit de volgende tabel in de vakken voor de nieuwe record. 
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
    (Als u een rij moet toevoegen, selecteert u **A/CNAME RECORDS toevoegen (+)**.)
    
    (Mogelijk moet u omlaag schuiven.)
    
    |**Hostnaam**|**Type**|**Resultaat**|
    |:-----|:-----|:-----|
    |(Laat dit veld leeg.)  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.           |
       
    ![Afbeelding van het te maken:Bp-afbeelding](../../media/cfc61387-630e-4aa0-8762-ef36eaeda44a.png)
  
5. Kies **Opslaan**.
    
    (Mogelijk moet u omlaag schuiven.)
    
    ![Afbeelding van het te maken:Bp-afbeelding](../../media/b4d445a1-09c0-46c3-8141-672cc2831a9b.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>De twee SRV-records toevoegen die zijn vereist voor Microsoft
<a name="BKMK_add_SRV"> </a>

1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij Names.co.uk via [deze koppeling](https://account.names.co.uk/dashboard#/). U wordt gevraagd u eerst aan te melden.
    
    ![Afbeelding van het te maken dat u aangeeft op basis van afbeelding van het gebruik](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. Zoek op de pagina **Dashboard** de naam van het domein dat u bijwerkt, en kies vervolgens **DNS-instellingen** in de vervolgkeuzelijst. 
    
    (Mogelijk moet u omlaag schuiven.)
    
    ![Afbeelding van het te maken dat u aangeeft op basis van afbeelding van het gebruik](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. Typ of kopieer en plak op de pagina **Add/Modify DNS Zone**, in de sectie **Service records**, de waarden uit de volgende tabel in de vakken voor de nieuwe record. 
    
    (Mogelijk moet u omlaag schuiven.)
    
    |**Name**|**Prioriteit**|**Gewicht**|**Poort**|**Result**|
    |:-----|:-----|:-----|:-----|:-----|
    |_sip._tls  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls._tcp  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
       
    ![Afbeelding van het te maken:Bp-afbeelding](../../media/97a96523-005a-4058-9e12-19f6c3bf9b3b.png)
  
4. Kies **Opslaan**.
    
    (Mogelijk moet u omlaag schuiven.)
    
    ![Afbeelding van het te maken:Bp-afbeelding-5-2](../../media/bb617a5f-14f9-44b7-9256-bdef34d22d6b.png)
  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
