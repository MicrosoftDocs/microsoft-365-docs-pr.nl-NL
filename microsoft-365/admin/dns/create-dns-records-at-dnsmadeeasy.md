---
title: DNS-records bij DNSMadeEasy maken voor Microsoft
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
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
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: Lees hoe u uw domein verifieert en DNS-records instelt voor e-mail, Skype voor bedrijven online en andere services op DNSMadeEasy voor Microsoft.
ms.openlocfilehash: 719b416564447b3a6f4108b747ae921b4f6f6bb8
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657946"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-microsoft"></a>DNS-records bij DNSMadeEasy maken voor Microsoft

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt. 
  
Als DNSMadeEasy uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online enzovoort in te stellen.
  
Nadat u deze records bij DNSMadeEasy hebt toegevoegd, is uw domein ingesteld voor gebruik met Microsoft-services.
  

  
> [!NOTE]
> Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie
<a name="BKMK_verify"> </a>

Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
> [!IMPORTANT]
> Voor DNSMadeEasy-accounts is het domein dat u hebt toegevoegd, aangeschaft bij een afzonderlijke domeinregistratie. DNSMadeEasy biedt geen Domain Registration Services. De mogelijkheid om u aan te melden bij DNSMadeEasy en de DNS-record te maken, is voldoende bewijs van eigendom. 
  
1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij DNSMadeEasy via [deze koppeling](https://cp.dnsmadeeasy.com/). U wordt gevraagd u eerst aan te melden.
    
2. Selecteer het domein dat u wilt bijwerken in het gebied **Recently updated domains** op de pagina **Management Console** . 
    
3. Selecteer op de pagina **Managed DNS** in het gebied **TXT records** het **+** besturingselement () ( **Add New**).
    
    (Mogelijk moet u omlaag schuiven.)
    
4. Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add TXT Records** in de vakken voor de nieuwe record. 
    
    ||||
    |:-----|:-----|:-----|
    |**Naam** <br/> |**Waarde** <br/> |**TTL** <br/> |
    |(Laat dit veld leeg.)  <br/> |MS=ms *XXXXXXXX*  <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel. [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |1800  <br/> |
   
5. Selecteer **Submit**.
    
6. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.
  
Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.
  
1. Ga in het Microsoft-beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.

    
2. Kies op de pagina **Domeinen** de naam van het domein dat u verifieert. 
    
3. Kies **Start setup** op de pagina **Setup**.
    
4. Kies **Verifiëren** op de pagina **Domein verifiëren**.
    
> [!NOTE]
> Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden
<a name="BKMK_add_MX"> </a>

1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij DNSMadeEasy via [deze koppeling](https://cp.dnsmadeeasy.com/). U wordt gevraagd u eerst aan te melden.
    
2. Selecteer het domein dat u wilt bijwerken in het gebied **Recently updated domains** op de pagina **Management Console** . 
    
    Selecteer het domein dat u wilt bijwerken in het gebied **Recently updated domains** op de pagina **Management Console** . 
    
    ![DNSMadeEasy voor 1-2](../../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. Selecteer op de pagina **Managed DNS** in het gebied **MX records** het besturingselement **(+)** ( **Add New**).
    
    (Mogelijk moet u omlaag schuiven.)
    
    ![DNSMadeEasy voor 2-1](../../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add MX Records** in de vakken voor de nieuwe record. 
    
    (Mogelijk moet u omlaag schuiven.)
    
    |**Name**|**Server**|**MX Level**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |(Laat dit veld leeg.)  <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> **Opmerking:** Haal uw \<*domain-key*\> uit uw Microsoft-account. [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |10  <br/> Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit.    <br/> |1800  <br/> |
   
    ![DNSMadeEasy voor 2-2](../../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. Selecteer **Submit**.
    
    ![DNSMadeEasy voor 2-3](../../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. Als er andere MX-records zijn vermeld in de sectie **MX Records**, verwijdert u deze door elk record te selecteren. 
    
    ![DNSMadeEasy voor 2-4-1](../../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. Wanneer alle records zijn geselecteerd, selecteert u **Delete selected**.
    
    ![DNSMadeEasy voor 2-4-2](../../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. Selecteer in het dialoogvenster **MX-records verwijderen** de optie **verwijderen** om uw wijzigingen te bevestigen. 
    
    ![DNSMadeEasy voor 2-5](../../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a>De vijf CNAME-records toevoegen die vereist zijn voor Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij DNSMadeEasy via [deze koppeling](https://cp.dnsmadeeasy.com/). U wordt gevraagd u eerst aan te melden.
    
2. Selecteer het domein dat u wilt bijwerken in het gebied **Recently updated domains** op de pagina **Management Console** . 
    
3. Selecteer op de pagina **Managed DNS** in het gebied **CNAME records** het besturingselement **(+)** ( **Add New**).
    
    (Mogelijk moet u omlaag schuiven.)
    
    ![DNSMadeEasy voor 3-1](../../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. Voeg de eerste van de vijf CNAME-records toe.
    
    Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in het gebied **Add CNAME Records** in de vakken voor de nieuwe record. 
    
    |**Name**|**Alias to**|**TTL**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |1800  <br/> |
    |sip  <br/> |sipdir.online.lync.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |1800  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |1800  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |1800  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |1800  <br/> |
   
    ![DNSMadeEasy voor 3-2](../../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. Selecteer **Submit**.
    
    ![DNSMadeEasy voor 3-3](../../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. Voeg de andere vier CNAME-records toe.
    
    Selecteer in de sectie **CNAME records** het besturingselement **(+)** ( **Add New**), maak een record met behulp van de waarden uit de volgende rij in de tabel en selecteer vervolgens nogmaals **Submit** om het maken van die record af te ronden. 
    
    Herhaal deze procedure totdat u alle vijf CNAME-records hebt gemaakt.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Een TXT-record voor SPF toevoegen om spam tegen te gaan
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft. In plaats daarvan voegt u de vereiste Microsoft-waarden toe aan de huidige record, zodat u  *één*  SPF-record hebt die beide sets met waarden bevat. Hebt u voorbeelden nodig? Bekijk deze [Externe Domain Name System-records voor Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records). Voor het valideren van uw SPF-record gebruikt u een van deze[SPF-validatie hulpmiddelen](../setup/domains-faq.yml). 
  
1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij DNSMadeEasy via [deze koppeling](https://cp.dnsmadeeasy.com/). U wordt gevraagd u eerst aan te melden.
    
2. Selecteer het domein dat u wilt bijwerken in het gebied **Recently updated domains** op de pagina **Management Console** . 
    
3. Selecteer op de pagina **Managed DNS** in het gebied **TXT records** het besturingselement **(+)** ( **Add New**).
    
    (Mogelijk moet u omlaag schuiven.)
    
    ![DNSMadeEasy voor 4-1](../../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add TXT Records** in de vakken voor de nieuwe record. 
    
    |**Naam**|**Waarde**|**TTL**|
    |:-----|:-----|:-----|
    |(Laat dit veld leeg.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.           |1800  <br/> |
   
    ![DNSMadeEasy voor 4-2](../../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. Selecteer **Submit**.
    
    ![DNSMadeEasy voor 4-3](../../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>De twee SRV-records toevoegen die zijn vereist voor Microsoft
<a name="BKMK_add_SRV"> </a>

1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij DNSMadeEasy via [deze koppeling](https://cp.dnsmadeeasy.com/). U wordt gevraagd u eerst aan te melden.
    
2. Selecteer het domein dat u wilt bijwerken in het gebied **Recently updated domains** op de pagina **Management Console** . 
    
3. Selecteer op de pagina **Managed DNS** in het gebied **SRV records** het besturingselement **(+)** ( **Add New**).
    
    (Mogelijk moet u omlaag schuiven)
    
    ![DNSMadeEasy voor 5-1](../../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. Voeg de eerste van de twee SRV-records toe.
    
    Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in het gebied **Add SRV Records** in de vakken voor de nieuwe record. 
    
    |**Name**|**Prioriteit**|**Gewicht**|**Poort**|**Host**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip _sip._tls  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |1800  <br/> |
    |_sipfederationtls _sipfederationtls._tcp  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |1800  <br/> |
   
    ![DNSMadeEasy voor 5-2](../../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. Selecteer **Submit**.
    
    ![DNSMadeEasy voor 5-3](../../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. Voeg de andere SRV-record toe.
    
    Selecteer in de sectie **SRV records** het besturingselement **(+)** ( **nieuwe toevoegen**), maak een record met behulp van de waarden uit de volgende rij in de tabel en selecteer vervolgens opnieuw **Submit** om het maken van die record af te ronden. 
    
> [!NOTE]
> Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md). 
  

