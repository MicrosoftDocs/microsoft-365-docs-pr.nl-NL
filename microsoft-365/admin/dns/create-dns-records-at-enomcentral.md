---
title: DNS-records maken op eNomCentral voor Office 365
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
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services op eNomCentral voor Office 365.
ms.openlocfilehash: dec76e0dde2775851ff464e3b8765f82dfb57625
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "42809568"
---
# <a name="create-dns-records-at-enomcentral-for-office-365"></a>DNS-records maken op eNomCentral voor Office 365

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Als eNomCentral uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.
  
Nadat u deze records bij eNomCentral hebt toegevoegd, is uw domein ingesteld voor gebruik met Office 365-services.
  
Zie [Een openbare website gebruiken met Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9) voor informatie over webhosting en DNS voor websites met Office 365.
  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie
<a name="BKMK_verify"> </a>

Voordat u uw domein met Office 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Office 365 bewezen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
Volg onderstaande stappen of [bekijk de video (start op 0:46)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Als u wilt beginnen, gaat u [via deze koppeling](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) naar uw pagina met domeinen bij eNom Central. U wordt gevraagd u aan te melden.
    
    ![Afbeelding van het te maken](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. Selecteer **onder mijn domeinen**de naam van het domein dat u wilt bewerken.
    
    ![Afbeelding van het te maken](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. Kies in de vervolgkeuzelijst **Manage Domain** de optie **Host Records**.
    
    ![Afbeelding van het te maken](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)
  
4. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.
    
    (Kies in de vervolgkeuzelijst de waarde **Record Type**.) 
    
    ||||
    |:-----|:-----|:-----|
    |**Host Name** <br/> |**Recordtype** <br/> |**Address** <br/> |
    |@  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![Afbeelding van het te maken](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)
  
5. Selecteer **Opslaan**.
    
    ![Afbeelding van het te maken](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)
  
6. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Office 365 en vraagt u of Office 365 naar de record wil zoeken.
  
Wanneer in Office 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.
  
1. Ga in het beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Instellingendomeinen.</a> **Settings**

    
2. Selecteer **op** de pagina Domeinen het domein dat u verifieert. 
    
    
  
3. Selecteer **op** de pagina Setup de optie **Installatie starten**.
    
    
  
4. Selecteer **op** de pagina Domein verifiëren de optie **Verifiëren**.
    
    
  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Voeg een MX-record toe zodat e-mail voor uw domein bij Office 365 terechtkomt
<a name="BKMK_add_MX"> </a>

Volg onderstaande stappen of [bekijk de video (start op 3:40)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Als u wilt beginnen, gaat u [via deze koppeling](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) naar uw pagina met domeinen bij eNom Central. U wordt gevraagd u aan te melden.
    
    ![Afbeelding van het te maken](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. Selecteer **onder mijn domeinen**de naam van het domein dat u wilt bewerken.
    
    ![Afbeelding van het te maken](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. Kies in de vervolgkeuzelijst **Manage Domain** de optie **Email Settings**.
    
    ![Afbeelding van het te maken](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)
  
4. Kies in de vervolgkeuzelijst **Service Selection** de optie **User (MX)**.
    
    ![Afbeelding van het te maken](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)
  
5. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.
    
    |**Hostnaam**|**Address**|**Pref**|
    |:-----|:-----|:-----|
    |@  <br/> | *\<domeinsleutel\>*  .mail.protection.outlook.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> **Let op:** Haal uw * \<domeinsleutel\> * op uit uw Office 365-account.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |10  <br/> Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.    <br/> |
       
   ![Afbeelding van het te maken](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)
  
6. Selecteer **Opslaan**.
    
    ![Afbeelding van het te maken](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)
  
7. Als er andere MX-records zijn, schakelt u de selectievakjes voor deze records in om deze te selecteren.
    
    ![Afbeelding van het te maken](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)
  
8. Selecteer **aangevinkt verwijderen**.
    
    ![Afbeelding van het te maken](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a>De CNAME-records toevoegen die voor Office 365 vereist zijn
<a name="BKMK_add_CNAME"> </a>

Volg onderstaande stappen of [bekijk de video (start op 4:24)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Als u wilt beginnen, gaat u [via deze koppeling](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) naar uw pagina met domeinen bij eNom Central. U wordt gevraagd u aan te melden.
    
    ![Afbeelding van het te maken](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. Selecteer **onder mijn domeinen**de naam van het domein dat u wilt bewerken.
    
    ![Afbeelding van het te maken](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. Kies in de vervolgkeuzelijst **Manage Domain** de optie **Host Records**.
    
    ![Afbeelding van het te maken](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. Selecteer **nieuwe rij**.
    
    ![Afbeelding van het te maken](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)
  
5. Typ of kopieer en plak de volgende waarden in de vakken voor de zes nieuwe records.
    
        (Choose the **Record Type** value from the drop-down list.) 
        
    |**Host Name**|**Recordtype**|**Address**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME (alias)  <br/> |autodiscover.outlook.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
    |sip  <br/> |CNAME (alias)  <br/> |sipdir.online.lync.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
    |lyncdiscover  <br/> |CNAME (alias)  <br/> |webdir.online.lync.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
    |enterpriseregistration  <br/> |CNAME (alias)  <br/> |enterpriseregistration.windows.net.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
    |enterpriseenrollment  <br/> |CNAME (alias)  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
   
    ![Afbeelding van het te maken](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)
  
6. Selecteer **Opslaan**.
    
    ![Afbeelding van het te maken](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Een TXT-record voor SPF toevoegen om spam tegen te gaan
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Office 365 te maken. In plaats daarvan voegt u de vereiste Office 365-waarden toe aan de huidige record, zodat u beschikt over  *één*  SPF-record waarin beide sets waarden zijn opgenomen.
  
Volg onderstaande stappen of [bekijk de video (start op 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Als u wilt beginnen, gaat u [via deze koppeling](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) naar uw pagina met domeinen bij eNom Central. U wordt gevraagd u aan te melden.
    
    ![Afbeelding van het te maken](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. Selecteer **onder mijn domeinen**de naam van het domein dat u wilt bewerken.
    
    ![Afbeelding van het te maken](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. Kies in de vervolgkeuzelijst **Manage Domain** de optie **Host Records**.
    
    ![Afbeelding van het te maken](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.
    
    (Kies in de vervolgkeuzelijst de waarde **Record Type**.) 
    
    |**Host Name**|**Recordtype**|**Address**|
    |:-----|:-----|:-----|
    |@  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.           |
   
   ![Afbeelding van het te maken](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)
  
5. Selecteer **Opslaan**.
    
    ![Afbeelding van het te maken](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Voeg de vier SRV-records toe die voor Office 365 vereist zijn.
<a name="BKMK_add_SRV"> </a>

Volg onderstaande stappen of [bekijk de video (start op 5:50)](https://support.office.com/article/Video-Create-DNS-records-at-eNomCentral-for-Office-365-3766a9e8-77dd-4a42-908d-89b076143e7d?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Als u wilt beginnen, gaat u [via deze koppeling](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) naar uw pagina met domeinen bij eNom Central. U wordt gevraagd u aan te melden.
    
    ![Afbeelding van het te maken](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)
  
2. Selecteer **onder mijn domeinen**de naam van het domein dat u wilt bewerken.
    
    ![Afbeelding van het te maken](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)
  
3. Kies in de vervolgkeuzelijst **Manage Domain** de optie **Host Records**.
    
    ![Afbeelding van het te maken](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)
  
4. Selecteer Rechts van **de nieuwe rij**De optie **SRV- of SPF-record toevoegen**.
    
    ![Afbeelding van het te maken](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)
  
5. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de twee nieuwe records.
    
    |**Service**|**Protocol**|**Prioriteit**|**Weight**|**Port**|**Target          (Hostname)**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
   
    ![Afbeelding van het te maken](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)
  
6. Selecteer **opslaan**
    
    ![Afbeelding van het te maken](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)
  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  

