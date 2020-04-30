---
title: DNS-records maken bij Crazy Domains voor Microsoft
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
ms.assetid: 6386d63e-b78f-4736-90e7-b99a2c116a9f
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services bij Crazy Domains voor Microsoft.
ms.openlocfilehash: 5a5a0f4c92e14bdfd6c54249cd66c9e88abee075
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939329"
---
# <a name="create-dns-records-at-crazy-domains-for-microsoft"></a>DNS-records maken bij Crazy Domains voor Microsoft

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Als Crazy Domains uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.
  
Nadat u deze records hebt toegevoegd bij Crazy Domains, wordt uw domein ingesteld om te werken met Microsoft-services.
  

  
> [!NOTE]
> Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie
<a name="BKMK_verify"> </a>

Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
1. Ga eerst naar de pagina met domeinen bij Crazy Domains via [deze koppeling](https://manage.crazydomains.com/members/domains/). U wordt gevraagd u eerst aan te melden.
    
    ![Afbeelding van het lint](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. Selecteer **Domeinen**in de sectie **Mijn account** .
    
    ![Afbeelding van het lint](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. Selecteer **op** de pagina Domeinnamen in de sectie **Domein** de naam van het domein dat u bijwerkt. 
    
    ![Afbeelding van het lint](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. Selecteer in de sectie **DNS-instellingen** het vervolgkeuzelijstpictogram. 
    
    ![Afbeelding van het lint](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. Selecteer **Record toevoegen**.
    
    ![Afbeelding van het lint](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. Kies **TXT Record** in de vervolgkeuzelijst **Add Record**. 
    
    ![Afbeelding van het lint](../../media/f0ffdefb-d7a5-47df-bb5e-bf8a3bcc9b01.png)
  
7. Kies **Toevoegen**.
    
    ![Afbeelding van het lint](../../media/b0cd623a-67f7-4bae-a5b5-507f5a106123.png)
  
8. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.
    
    |**Sub Domain**|**Text Record**|
    |:-----|:-----|
    |(Laat dit veld leeg.)  <br/> |MS=ms *XXXXXXXX*  <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Afbeelding van het lint](../../media/3867de97-6a98-4475-9bda-470bac75d483.png)
  
9. Selecteer **Bijwerken**.
    
    ![Afbeelding van het lint](../../media/0e416df6-b7a2-4dd7-971c-f1cc31df30da.png)
  
10. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.
  
Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.
  
1. Ga in het Microsoft-beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.

    
2. Kies op de pagina **Domeinen** de naam van het domein dat u verifieert. 
    
    
  
3. Kies **Start setup** op de pagina **Setup**.
    
    
  
4. Kies **Verifiëren** op de pagina **Domein verifiëren**.
    
    
  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden
<a name="BKMK_add_MX"> </a>

1. Ga eerst naar de pagina met domeinen bij Crazy Domains via [deze koppeling](https://manage.crazydomains.com/members/domains/). U wordt gevraagd u eerst aan te melden.
    
    ![Afbeelding van het lint](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. Selecteer **Domeinen**in de sectie **Mijn account** .
    
    ![Afbeelding van het lint](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. Selecteer **op** de pagina Domeinnamen in de sectie **Domein** de naam van het domein dat u bijwerkt. 
    
    ![Afbeelding van het lint](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. Selecteer in de sectie **DNS-instellingen** het vervolgkeuzelijstpictogram. 
    
    ![Afbeelding van het lint](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. Selecteer **Record toevoegen**.
    
    ![Afbeelding van het lint](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. Kies **TXT Record** uit de vervolgkeuzelijst **Add Record**. 
    
    ![Afbeelding van het lint](../../media/63f7ab77-e686-4e7b-a3a2-1ac28a02d5f3.png)
  
7. Kies **Toevoegen**.
    
    ![Afbeelding van het lint](../../media/a60680a1-2513-498c-b42f-8ffa575ee48e.png)
  
8. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.
    
    (Kies de **waarde Prioriteit** in de vervolgkeuzelijst.) 
    
    |**Mail For Zone**|**Priority**|**Assigned To Server**|
    |:-----|:-----|:-----|
    |(Laat dit veld leeg.)  <br/> |1  <br/> Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit. <br/> | *\<domeinsleutel\>*  .mail.protection.outlook.com  <br/> **Let op:** Haal uw * \<domeinsleutel\> * uit uw Microsoft-account.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![Afbeelding van het lint](../../media/e27df6a6-19a6-4e58-9716-a74be1c3f8da.png)
  
9. Selecteer **Bijwerken**.
    
    ![Afbeelding van het lint](../../media/ba25cdef-a436-48bf-b0e9-5dffd03234a4.png)
  
10. Als er andere MX-records worden vermeld in de sectie **MX Record,** selecteert **u Wijzigen** voor een van deze records. 
    
    ![Afbeelding van het lint](../../media/9acdda39-33ec-4b24-ad83-91c26f9c599b.png)
  
11. Selecteer **Verwijderen**.
    
    ![Afbeelding van het lint](../../media/50b0e263-6f21-41b3-8fa0-7dd55dbe6c2e.png)
  
12. Selecteer **Bijwerken** om de verwijdering te bevestigen. 
    
    ![Afbeelding van het lint](../../media/db751bfe-31c2-4632-a491-6893eda38a51.png)
  
13. Verwijder op dezelfde manier alle andere MX-records in de lijst, met uitzondering van de MX-record die u eerder met deze procedure hebt toegevoegd.
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Voeg de zes CNAME-records toe die nodig zijn voor Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Ga eerst naar de pagina met domeinen bij Crazy Domains via [deze koppeling](https://manage.crazydomains.com/members/domains/). U wordt gevraagd u eerst aan te melden.
    
    ![Afbeelding van het lint](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. Selecteer **Domeinen**in de sectie **Mijn account** .
    
    ![Afbeelding van het lint](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. Selecteer **op** de pagina Domeinnamen in de sectie **Domein** de naam van het domein dat u bijwerkt. 
    
    ![Afbeelding van het lint](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. Selecteer in de sectie **DNS-instellingen** het vervolgkeuzelijstpictogram. 
    
    ![Afbeelding van het lint](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. Selecteer **Record toevoegen**.
    
    ![Afbeelding van het lint](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. Kies **CNAME Record** uit de vervolgkeuzelijst **Add Record**. 
    
    ![Afbeelding van het lint](../../media/2f02538b-fc79-46d2-a2b7-1022eaf0fb08.png)
  
7. Kies **Toevoegen**.
    
    ![Afbeelding van het lint](../../media/4c5929cf-1c21-4af9-899b-e36091f0f14d.png)
  
8. Voeg de eerste van de zes CNAME-records toe.
    
    Typ of kopieer en plak de waarden uit de eerste rij in de volgende tabel in de velden voor de nieuwe record.
    
    |**Sub Domain**|**Alias for**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![Afbeelding van het lint](../../media/81a7b837-3f4d-4565-89a9-380e4d318acf.png)
  
9. Selecteer **CNAME-record toevoegen**.
    
    ![Afbeelding van het lint](../../media/9bcba729-7085-4ebc-8183-ecde82f5c364.png)
  
10. Voeg de tweede CNAME-record toe:
    
    Gebruik in de vakken voor de nieuwe record de waarden uit de volgende rij in de tabel en selecteer vervolgens opnieuw **CNAME Record toevoegen**.
    
    Herhaal deze procedure totdat u alle zes CNAME-records hebt gemaakt.
    
11. Selecteer **Bijwerken** om uw wijzigingen op te slaan. 
    
    ![Afbeelding van het lint](../../media/dbe578f6-359c-428c-b296-ca624cecfc3c.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Een TXT-record voor SPF toevoegen om spam tegen te gaan
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft. Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat. 
  
1. Ga eerst naar de pagina met domeinen bij Crazy Domains via [deze koppeling](https://manage.crazydomains.com/members/domains/). U wordt gevraagd u eerst aan te melden.
    
    ![Afbeelding van het lint](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. Selecteer **Domeinen**in de sectie **Mijn account** .
    
    ![Afbeelding van het lint](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. Selecteer **op** de pagina Domeinnamen in de sectie **Domein** de naam van het domein dat u bijwerkt. 
    
    ![Afbeelding van het lint](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. Selecteer in de sectie **DNS-instellingen** het vervolgkeuzelijstpictogram. 
    
    ![Afbeelding van het lint](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. Selecteer **Record toevoegen**.
    
    ![Afbeelding van het lint](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. Kies **TXT Record** uit de vervolgkeuzelijst **Add Record**. 
    
    ![Afbeelding van het lint](../../media/7f2461e2-0468-49bd-9eb0-981e9b2f72d6.png)
  
7. Kies **Toevoegen**.
    
    ![Afbeelding van het lint](../../media/64ef9e1f-676d-46e2-9253-a83d9bcd1c4e.png)
  
8. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.
    
    |**Sub Domain**|**Text Record**|
    |:-----|:-----|
    |(Laat dit veld leeg.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.           |
   
    ![Afbeelding van het lint](../../media/e7fd524a-c94b-4cdd-b264-67abb532a71b.png)
  
9. Selecteer **Bijwerken**.
    
    ![Afbeelding van het lint](../../media/d4f378ee-0f14-46ae-ba32-1596660ecf91.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>De twee SRV-records toevoegen die zijn vereist voor Microsoft
<a name="BKMK_add_SRV"> </a>

1. Ga eerst naar de pagina met domeinen bij Crazy Domains via [deze koppeling](https://manage.crazydomains.com/members/domains/). U wordt gevraagd u eerst aan te melden.
    
    ![Afbeelding van het lint](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. Selecteer **Domeinen**in de sectie **Mijn account** .
    
    ![Afbeelding van het lint](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. Selecteer **op** de pagina Domeinnamen in de sectie **Domein** de naam van het domein dat u bijwerkt. 
    
    ![Afbeelding van het lint](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. Selecteer in de sectie **DNS-instellingen** het vervolgkeuzelijstpictogram. 
    
    ![Afbeelding van het lint](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. Selecteer **Record toevoegen**.
    
    ![Afbeelding van het lint](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. Kies **SRV Record** uit de vervolgkeuzelijst **Add Record**. 
    
    ![Afbeelding van het lint](../../media/156acebc-7f6d-4b5e-8493-6bc62ca0ee27.png)
  
7. Kies **Toevoegen**.
    
    ![Afbeelding van het lint](../../media/6a711df7-4215-49b2-b58f-1cf1a242b383.png)
  
8. Voeg de eerste van de twee SRV-records toe.
    
    Typ of kopieer en plak de waarden uit de eerste rij in de volgende tabel in de velden voor de nieuwe record.
    
    |**Record Type**|**Sub Domain**|**Prioriteit**|**Gewicht**|**Poort**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV Record  <br/> |_sip._tls  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |SRV Record  <br/> |_sipfederationtls._tcp  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   
    ![Afbeelding van het lint](../../media/cc0ea6eb-7358-434e-bd1a-2737725c6d41.png)
  
9. Selecteer **SRV-record toevoegen**.
    
    ![Afbeelding van het lint](../../media/de4ec312-6833-469a-b23a-f376140a35ca.png)
  
10. Voeg de andere SRV-record toe.
    
    Voeg in de vakken voor de nieuwe record de waarden uit de tweede rij in de tabel toe.
    
11. Selecteer **Bijwerken** om uw wijzigingen op te slaan. 
    
    ![Afbeelding van het lint](../../media/f0bb1dd6-3772-4293-bf74-710f635e0658.png)
  
> [!NOTE]
> Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
