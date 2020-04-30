---
title: DNS-records maken bij Amazon Web Services (AWS) voor Microsoft
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
ms.assetid: 7a2efd75-0771-4897-ba7b-082fe5bfa9da
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services bij Amazon Web Services (AWS) voor Microsoft.
ms.openlocfilehash: daac9a8efedc8a2710217e352d9793ead954d2c3
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939353"
---
# <a name="create-dns-records-at-amazon-web-services-aws-for-microsoft"></a>DNS-records maken bij Amazon Web Services (AWS) voor Microsoft

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Als AWS uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records in te stellen voor e-mail, Skype Online voor Bedrijven, enzovoort.
  
Nadat u deze records bij AWS hebt toegevoegd, wordt uw domein ingesteld om te werken met Microsoft-services.
  

  
> [!NOTE]
> Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie
<a name="BKMK_verify"> </a>

Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij AWS via [deze koppeling](https://console.aws.amazon.com/route53/home). U wordt gevraagd u eerst aan te melden.
    
2. Selecteer op de pagina **Resources** de optie **Gehoste zones**.
    
3. Selecteer op de pagina **Gehoste zones** in de kolom **Domeinnaam** de naam van het domein dat u wilt bewerken. 
    
4. Selecteer **Recordset maken**.
    
5. Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Create Record Set** in de vakken voor de nieuwe record. 
    
    (Kies in de vervolgkeuzelijsten de waarden **Type** en **Routing Policy**.) 
    
    > [!TIP]
    > De aanhalingstekens die zijn vereist volgens de instructies op het scherm, worden automatisch ingevoegd. U hoeft deze niet handmatig te typen. 
  
    |||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |**Name** <br/> |**Type** <br/> |**Alias** <br/> |**TTL (Seconds)** <br/> |**Value** <br/> |**Routing Policy** <br/> |
    |(Laat dit veld leeg.)  <br/> |TXT - Text  <br/> |No  <br/> |300  <br/> |MS=ms *XXXXXXXX*  <br/>**Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Microsoft 365. [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |Simple  <br/> |
   
6. Selecteer **Maken**.
    
7. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
Nu u de record op de site van uw domeinregistrar hebt toegevoegd, gaat u terug naar Microsoft en vraagt u om een zoekopdracht naar de record.
  
Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.
  
1. Ga in het Microsoft-beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.

    
2. Kies op de pagina **Domeinen** de naam van het domein dat u verifieert. 
    
3. Kies **Start setup** op de pagina **Setup**.
    
4. Kies **Verifiëren** op de pagina **Domein verifiëren**.
    
> [!NOTE]
> Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft-365"></a>Voeg een MX-record toe, zodat e-mail voor uw domein naar Microsoft 365 komt
<a name="BKMK_add_MX"> </a>

1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij AWS via [deze koppeling](https://console.aws.amazon.com/route53/home). U wordt gevraagd u eerst aan te melden.
    
2. Selecteer op de pagina **Resources** de optie **Gehoste zones**.
    
3. Selecteer op de pagina **Gehoste zones** in de kolom **Domeinnaam** de naam van het domein dat u wilt bewerken. 
    
4. Selecteer **Recordset maken**.
    
5. Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Create Record Set** in de vakken voor de nieuwe record. 
    
    (Kies in de vervolgkeuzelijsten de waarden **Type** en **Routing Policy**.) 
    
    |**Naam**|**Type**|**Alias**|**TTL (Seconds)**|**Value**|**Routing Policy**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |(Laat dit veld leeg.)  <br/> |MX - e-mailuitwisseling  <br/> |Nee  <br/> |300  <br/> |0  *\< domeinsleutel\>*  .mail.protection.outlook.com.  <br/> De 0 is de MX-prioriteitwaarde. Voeg deze toe aan het begin van de MX-waarde, van de rest van de waarde gescheiden door een spatie.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> **Let op:** Haal \<uw domeinsleutel\> op van uw Microsoft 365-account. *domain-key* [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |Simple  <br/> |
       
    ![Afbeelding van het te maken van afbeelding van het](../../media/94a71ce7-1b3b-4b1a-9ad3-9592db133075.png)
  
6. Selecteer **Maken**.
    
    ![AWS-BP-Configure-2-2](../../media/1c050c72-c04f-48d5-a8e9-44cd83ddd33e.png)
  
7. Als er andere MX-records zijn, verwijdert u deze.
    
    > [!IMPORTANT]
    > AWS slaat MX-records op als een set die meerdere records kan bevatten. **Selecteer recordset verwijderen NIET,** omdat hiermee al uw MX-records worden verwijderd, inclusief de records die u zojuist hebt toegevoegd. **Delete Record Set** Gebruik in plaats daarvan de volgende instructies. 
  
    Selecteer eerst de MX-recordset.
    
    ![AWS-BP-Configure-2-3](../../media/9d9388cb-e2d0-43b7-928c-e1d07e519c6f.png)
  
    Vervolgens verwijdert u in het gebied **Edit Record Set** (recordset bewerken) elk van de oude MX-records door de record te selecteren in het vak **Value** en op de toets **Delete** op uw toetsenbord te drukken. 
    
    ![AWS-BP-Configure-2-4](../../media/c3b0c1bc-21ab-44cc-84b7-f504725c5540.png)
  
8. Selecteer **Recordset opslaan**.
    
    ![AWS-BP-Configure-2-5](../../media/86f0998d-f5d4-4750-a93d-ac13b318c40b.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft-365"></a>Voeg de vijf CNAME-records toe die nodig zijn voor Microsoft 365
<a name="BKMK_add_CNAME"> </a>

1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij AWS via [deze koppeling](https://console.aws.amazon.com/route53/home). U wordt gevraagd u eerst aan te melden.
    
2. Selecteer op de pagina **Resources** de optie **Gehoste zones**.
    
3. Selecteer op de pagina **Gehoste zones** in de kolom **Domeinnaam** de naam van het domein dat u wilt bewerken. 
    
4. Selecteer **Recordset maken**.
    
5. Voeg de eerste CNAME-record toe.
    
    Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in het gebied **Create Record Set** (recordset maken) in de vakken voor de nieuwe record. 
    
    (Kies in de vervolgkeuzelijsten de waarden **Type** en **Routing Policy**.) 
    
    |**Naam**|**Type**|**Alias**|**TTL (Seconds)**|**Value**|**Routing Policy**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME - Canonical name  <br/> |Nee  <br/> |300  <br/> |autodiscover.outlook.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |Simple  <br/> |
    |sip  <br/> |CNAME - Canonical name  <br/> |Nee  <br/> |300  <br/> |sipdir.online.lync.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |Simple  <br/> |
    |lyncdiscover  <br/> |CNAME - Canonical name  <br/> |Nee  <br/> |300  <br/> |webdir.online.lync.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |Dat is eenvoudig  <br/> |
    |enterpriseregistration  <br/> |CNAME - Canonical name  <br/> |Nee  <br/> |300  <br/> |enterpriseregistration.windows.net.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |Simple  <br/> |
    |enterpriseenrollment  <br/> |CNAME - Canonical name  <br/> |Nee  <br/> |300  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |Simple  <br/> |
   
    ![Afbeelding van het te maken van afbeelding van het gebruik](../../media/895c71bd-0e3a-425e-9681-98c1c67e714b.png)
  
6. Selecteer **Maken**.
    
    ![AWS-BP-Configure-3-2](../../media/33964846-5282-44a4-b241-62ce02b96735.png)
  
7. Voeg de andere vier CNAME-records toe.
    
    Selecteer op de pagina **Gehoste zones** **Recordset maken,** maak een record met de waarden uit de volgende rij in de tabel en selecteer vervolgens opnieuw **Maken** om die record te voltooien. 
    
    Herhaal dit proces totdat u alle vijf CNAME-records hebt gemaakt.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Een TXT-record voor SPF toevoegen om spam tegen te gaan
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft. Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat. Hebt u voorbeelden nodig? Bekijk deze [Externe Domain Name System-records voor Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0). Als u uw SPF-record wilt valideren, u een van deze[SPF-validatietools](../setup/domains-faq.md)gebruiken. 
  
1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij AWS via [deze koppeling](https://console.aws.amazon.com/route53/home). U wordt gevraagd u eerst aan te melden.
    
2. Selecteer op de pagina **Resources** de optie **Gehoste zones**.
    
3. Selecteer op de pagina **Gehoste zones** in de kolom **Domeinnaam** de naam van het domein dat u wilt bewerken. 
    
4. Selecteer de **TXT-recordset.** 
    
    ![AWS-BP-Configure-4-1](../../media/0310fa66-c016-4987-80df-930f1c8f3c39.png)
  
5. Druk in het gebied **Edit Record Set** aan het einde van de huidige invoer in het vak **Value:** voor de bestaande record op Enter op uw toetsenbord om een nieuwe regel te maken, en typ of plak op die nieuwe regel (onder de bestaande waarde) de waarde uit de volgende tabel. (U ziet een voorbeeld in de afbeelding onder de tabel.) 
    
    |**Waarde:**|
    |:-----|
    |v=spf1 include:spf.protection.outlook.com -all  <br/> (De aanhalingstekens die volgens de instructies op het scherm vereist zijn, worden automatisch ingevoegd. U hoeft deze niet handmatig te typen.)  <br/> **Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.           |
   
    ![Afbeelding van het te maken van afbeelding van het gebruik](../../media/beb3c086-eaf8-4245-9860-18512a3ff72e.png)
  
6. Selecteer **Recordset opslaan**.
    
    ![AWS-BP-Configure-4-3](../../media/94b9306c-bdc9-4f84-ad6f-6d12edbfde90.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft-365"></a>Voeg de twee SRV-records toe die nodig zijn voor Microsoft 365
<a name="BKMK_add_SRV"> </a>

1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij AWS via [deze koppeling](https://console.aws.amazon.com/route53/home). U wordt gevraagd u eerst aan te melden.
    
2. Selecteer op de pagina **Resources** de optie **Gehoste zones**.
    
3. Selecteer op de pagina **Gehoste zones** in de kolom **Domeinnaam** de naam van het domein dat u wilt bewerken. 
    
4. Selecteer **Recordset maken**.
    
5. Voeg de eerste SRV-record toe:
    
    Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in het gebied **Create Record Set** (recordset maken) in de vakken voor de nieuwe record. 
    
    (Kies in de vervolgkeuzelijsten de waarden **Type** en **Routing Policy**.) 
    
    |**Name**|**Type**|**Alias**|**TTL (Seconds)**|**Value**|**Routing Policy**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip._tls|SRV - Service locator|Nee|300|100 1 443 sipdir.online.lync.com. **Deze waarde MOET eindigen met een periode (.)**><br> **Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.           |Simple|
    |_sipfederationtls._tcp|SRV - Service locator|Nee|300|100 1 5061 sipfed.online.lync.com. **Deze waarde MOET eindigen op een punt (.)**<br> **Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.           |Simple|
   
    ![Afbeelding van het te maken van afbeelding van het gebruik](../../media/c3f841d3-6076-428f-bb04-e71cc5f392fa.png)
  
6. Selecteer **Maken**.
    
    ![AWS-BP-Configure-5-2](../../media/1bf5dc58-a46b-47a5-bd69-7c2147dd4e50.png)
  
7. De andere SRV-record toevoegen:
    
    Selecteer op de pagina **Gehoste zones** **Recordset maken,** maak een record met de waarden uit de volgende rij in de tabel en selecteer vervolgens opnieuw **Maken** om die record te voltooien. 
    
> [!NOTE]
> Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md). 
  
