---
title: DNS-records maken voor Azure DNS-zones
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
ms.assetid: fbcef2d7-ebaf-40d0-ba1f-cdaeff9f50ef
description: Meer informatie over het verifiëren van uw domein en het instellen van DNS-records voor e-mail, Skype voor Bedrijven Online en andere services in Azure DNS-zones voor Office 365.
ms.openlocfilehash: 30e54da8ffd51165b1cc0d2eb82d9d02eefdaf4d
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "42805941"
---
# <a name="create-dns-records-for-azure-dns-zones"></a>DNS-records maken voor Azure DNS-zones

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Als Azure uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records in te stellen voor e-mail, Skype voor Bedrijven Online, enzovoort.
  
Dit zijn de belangrijkste records om toe te voegen. 
  
- [De naamserverrecords (NS-records) van uw domein wijzigen](#change-your-domains-nameserver-ns-records)
    
- [Een TXT-record toevoegen voor verificatie](#add-a-txt-record-for-verification)

- [Voeg een MX-record toe zodat e-mail voor uw domein bij Office 365 terechtkomt](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [Voeg de vier CNAME-records toe die voor Office 365 vereist zijn.](#add-the-four-cname-records-that-are-required-for-office-365)
    
- [Een TXT-record voor SPF toevoegen om spam tegen te gaan](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Voeg de vier SRV-records toe die voor Office 365 vereist zijn.](#add-the-two-srv-records-that-are-required-for-office-365)
    
Nadat u deze records hebt toegevoegd aan Azure, wordt uw domein ingesteld voor gebruik met Office 365-services.
  
> [!NOTE]
> Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>De naamserverrecords (NS-records) van uw domein wijzigen
<a name="BKMK_NS"> </a>

> [!IMPORTANT]
> U moet deze procedure uitvoeren bij de domeinregistrar waar u uw domein hebt gekocht en geregistreerd. 
  
Toen u zich hebt aangemeld voor Azure, hebt u een brongroep gemaakt binnen een DNS-zone en vervolgens uw domeinnaam toegewezen aan die brongroep. Die domeinnaam is geregistreerd bij een externe domeinregistrar; Azure biedt geen domeinregistratieservices aan.
  
Als u DNS-records voor uw domein in Office 365 wilt verifiëren en maken, moet u eerst de naamservers bij uw domeinregistrar wijzigen, zodat ze de Azure-naamservers gebruiken die aan uw brongroep zijn toegewezen.
  
Als u de naamservers van het domein zelf wilt wijzigen op de website van de domeinregistrar, voert u de volgende stappen uit:
  
1. Zoek het gedeelte op de website van de domeinregistrar waarop u de naamservers voor uw domein kunt wijzigen.
    
2. Maak twee naamserverrecords door de waarden in de volgende tabel te gebruiken of bewerk de bestaande naamserverrecords zodat ze overeenkomen met deze waarden: Hieronder wordt een voorbeeld van azure toegewezen naamservers weergegeven.
    


**Voornaamserver:** Gebruik de naamserverwaarde die is toegewezen door Azure.  
**Tweede naamserver:** Gebruik de naamserverwaarde die is toegewezen door Azure.  

![Afbeelding van het lint](../../media/3e4805ea-608a-4df9-8f68-1fbf70d13d08.png)
  
> [!TIP]
> U moet ten minste twee naamserverrecords gebruiken. Als er andere naamservers op de website van uw domeinregistrar staan, moet u deze verwijderen. 
  
3. Sla uw wijzigingen op.
    
> [!NOTE]
> Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd. Vervolgens worden uw e-mail voor Office 365 en andere services ingesteld voor gebruik met uw domein. 
  
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie
<a name="BKMK_verify"> </a>

Voordat u uw domein met Office 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Office 365 bewezen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
1. Ga naar de pagina domeinen bij Azure via [deze koppeling](https://portal.azure.com )om aan de slag te gaan. U wordt gevraagd u eerst aan te melden.
    
    ![Afbeelding van het jaar van Afbeelding van het bureaublad van Azure-BP](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. Typ met de **zoekbalk** op de **pagina Dashboard** **DNS-zones**in . Selecteer in de weergave resultaten **DNS-zones** onder het gedeelte **Services.** Zodra u bent omgeleid, selecteert u het domein dat u wilt bijwerken.
    
    ![Afbeelding van het jaar van Afbeelding van het bureaublad van Azure-BP](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. Selecteer **+ Recordset op**de pagina **Instellingen** voor uw domein in het gebied van de **DNS-zone.**
    
    ![Afbeelding van het jaar van Afbeelding van het bureaublad van Azure-BP](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. Selecteer in het gebied **Recordset toevoegen** in de vakken voor de nieuwe recordset de waarden uit de volgende tabel. 
    
    (Kies de waarden **type** en **TTL** in de vervolgkeuzelijsten.) 
    
    |**Naam**|**Type**|**TTL**|**TTL-eenheid**|**Value**|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |TXT  <br/> |1  <br/> |Uur  <br/> |MS=ms *XXXXXXXX*  <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Afbeelding van het jaar van Azure-BP-verifiëren-1-1](../../media/7d5a253c-e88f-4565-a00a-79bba52f9970.png)
  
5. Selecteer **OK**.
  
6. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Office 365 en vraagt u of Office 365 naar de record wil zoeken.
  
Wanneer in Office 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.
  
1. Ga in het beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Instellingendomeinen.</a> **Settings**
    
2. Selecteer op de pagina **Domeinen** het domein dat u verifieert. 
    
    
  
3. Selecteer op de pagina **Setup** de optie **Startsetup**.
    
    
  
4. Selecteer op de pagina **Domein verifiëren** de optie **Verifiëren**.
    
    
  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Voeg een MX-record toe zodat e-mail voor uw domein bij Office 365 terechtkomt
<a name="BKMK_add_MX"> </a>

1. Ga naar de pagina domeinen bij Azure via [deze koppeling](https://portal.azure.com )om aan de slag te gaan. U wordt gevraagd u eerst aan te melden.
    
    ![Afbeelding van het jaar van Afbeelding van het bureaublad van Azure-BP](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. Selecteer op de pagina **Dashboard** in het gebied **Alle resources** het domein dat u wilt bijwerken. 
    
    ![Afbeelding van het jaar van Afbeelding van het bureaublad van Azure-BP](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. Selecteer **+ Recordset op**de pagina **Instellingen** voor uw domein in het gebied van de **DNS-zone.**
    
    ![Afbeelding van het jaar van Afbeelding van het bureaublad van Azure-BP](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. Selecteer in het gebied **Recordset toevoegen** in de vakken voor de nieuwe recordset de waarden uit de volgende tabel. 
    
    (Kies de waarden **type** en **TTL** in de vervolgkeuzelijsten.) 
    
    |**Naam**|**Type**|**TTL**|**TTL-eenheid**|**Preference**|**Postuitwisseling**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |1  <br/> |Uur  <br/> |10  <br/> Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.    <br/> | *\<domeinsleutel\>*  .mail.protection.outlook.com  <br/> **Let op:** Haal uw * \<domeinsleutel\> * uit uw Office 365-account.   [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)  
   
    ![Afbeelding van het jaar van Afbeelding van het bureaublad van Azure-BP](../../media/712c23ae-9d38-4af2-94e0-0704e70744fe.png)
  
5. Selecteer **OK**.
    
    ![Afbeelding van het jaar van Afbeelding van het bureaublad van Azure-BP](../../media/2f24225f-69ac-41dc-91c5-93d327360f74.png)
  
6. Als er andere MX-records in de sectie **MX Records** staan, moet u deze verwijderen. 
    
    Selecteer eerst in het **DNS-zonegebied** de **MX Record-set**.
    
    ![Afbeelding van het jaar van Afbeelding van het bureaublad van Azure-BP](../../media/9890da61-6fcd-4c61-888e-ccbb84f80cd0.png)
  
    Selecteer vervolgens de MX-record die u wilt verwijderen.
    
    ![Afbeelding van het jaar van Afbeelding van het bureaublad van Azure-BP](../../media/afe54f12-66d2-4ff3-80e9-427448e4c32c.png)
  
7. Selecteer het **menu Context (...)** en kies **Verwijderen.**
    
    ![Afbeelding van het jaar van Afbeelding van het bureaublad](../../media/25219e25-bc14-4bc7-84ed-ee65eb28a8ed.png)
  
8. Kies **Opslaan**.
    
    ![Afbeelding van het jaar van Afbeelding van het bureaublad van Azure-BP](../../media/c6133096-5e43-4637-9c01-b63ee4b03517.png)
  
## <a name="add-the-four-cname-records-that-are-required-for-office-365"></a>Voeg de vier CNAME-records toe die voor Office 365 vereist zijn.
<a name="BKMK_add_CNAME"> </a>

1. Ga naar de pagina domeinen bij Azure via [deze koppeling](https://portal.azure.com )om aan de slag te gaan. U wordt gevraagd u eerst aan te melden.
    
    ![Afbeelding van het jaar van Afbeelding van het bureaublad van Azure-BP](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. Selecteer op de pagina **Dashboard** in het gebied **Alle resources** het domein dat u wilt bijwerken. 
    
    ![Afbeelding van het jaar van Afbeelding van het bureaublad van Azure-BP](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. Selecteer **+ Recordset op**de pagina **Instellingen** voor uw domein in het gebied van de **DNS-zone.**
    
    ![Afbeelding van het jaar van Afbeelding van het bureaublad van Azure-BP](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. Voeg de eerste van de vier CNAME-records toe.
    
    Typ of kopieer en plak de waarden uit de eerste rij in de volgende tabel in het gebied **Recordset toevoegen** in de vakken voor de nieuwe recordset en kopieer en plak de waarden uit de eerste rij. 
    
    (Kies de waarden **type** en **TTL** in de vervolgkeuzelijsten.) 
    
    |**Naam**|**Type**|**TTL**|**TTL-eenheid**|**Alias**|
    |:-----|:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |1  <br/> |Uur  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |1  <br/> |Uur  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |1  <br/> |Uur  <br/> |webdir.online.lync.com  <br/> |
    
   
    ![Afbeelding van het jaar van Afbeelding van het bureaublad van Azure-BP](../../media/a1c4d869-da97-43b3-952c-d513a20231dc.png)
  
5. Selecteer **OK**.
    
    ![Afbeelding van het jaar van Afbeelding van het bureaublad van Azure-BP](../../media/b89b51da-1c07-43cf-9fab-75d2e5eb3544.png)
  
6. Voeg de andere drie CNAME-records toe.
    
    Selecteer **+ Recordset in**het gebied VAN DE **DNS-zone.** Maak vervolgens in de lege recordset een record met behulp van de waarden uit de volgende rij in de tabel en selecteer **opnieuw OK** om die record te voltooien. 
    
    Herhaal deze procedure totdat u alle vier CNAME-records hebt gemaakt.
    
7.  (Optioneel) Voeg 2 CNAME-records toe voor MDM.

> [!IMPORTANT]
> Als u Mobile Device Management (MDM) voor Office 365 hebt, moet u twee extra CNAME-records maken. Volg de stappen die u hebt gevolgd voor de andere vier CNAME-records, maar gebruik de waarden uit de volgende tabel. (Als u geen MDM hebt, u deze stap overslaan.) 
  
|**Naam**|**Type**|**TTL**|**TTL-eenheid**|**Alias**|
|:-----|:-----|:-----|:-----|:-----|
|enterpriseregistration  <br/> |CNAME  <br/> |1  <br/> |Uur  <br/> |enterpriseregistration.windows.net  <br/> |
|enterpriseenrollment  <br/> |CNAME  <br/> |1  <br/> |Uur  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Een TXT-record voor SPF toevoegen om spam tegen te gaan
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Office 365 te maken. In plaats daarvan voegt u de vereiste Office 365-waarden toe aan de huidige record, zodat u beschikt over  *één*  SPF-record waarin beide sets waarden zijn opgenomen. 
  
1. Ga naar de pagina domeinen bij Azure via [deze koppeling](https://portal.azure.com )om aan de slag te gaan. U wordt gevraagd u eerst aan te melden.
    
    ![Afbeelding van het jaar van Afbeelding van het bureaublad van Azure-BP](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. Selecteer op de pagina **Dashboard** in het gebied **Alle resources** het domein dat u wilt bijwerken. 
    
    ![Afbeelding van het jaar van Afbeelding van het bureaublad van Azure-BP](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. Selecteer in het **dns-zonegebied** de **TXT-recordset**.
    
    ![Afbeelding van het jaar van Afbeelding en 4-1 van Azure-BP](../../media/03095196-5010-4072-8503-79b812084dbf.png)
  
4. Selecteer in het eigenschappenvak **Recordset** in de vakken voor de nieuwe recordset de waarden uit de volgende tabel. 
    
    (Kies de waarden **type** en **TTL** in de vervolgkeuzelijsten.) 
    
    |**Naam**|**Type**|**TTL**|**TTL-eenheid**|**Value**|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |TXT  <br/> |1  <br/> |Uur  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.           

    ![Afbeelding van het jaar van Afbeelding en 4-2 van Azure-BP](../../media/78e84c43-e0ce-433f-8e74-9157fb093cca.png)
  
5. Kies **Opslaan**.
    
    ![Afbeelding van het jaar van Afbeelding en 4-3 voor Afbeelding van het bureaublad van Azure-BP](../../media/d7421c7f-ea63-4e11-8595-a482b8c165e0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Voeg de vier SRV-records toe die voor Office 365 vereist zijn.
<a name="BKMK_add_SRV"> </a>

1. Ga naar de pagina domeinen bij Azure via [deze koppeling](https://portal.azure.com )om aan de slag te gaan. U wordt gevraagd u eerst aan te melden.
    
    ![Afbeelding van het jaar van Afbeelding van het bureaublad van Azure-BP](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. Selecteer op de pagina **Dashboard** in het gebied **Alle resources** het domein dat u wilt bijwerken. 
    
    ![Afbeelding van het jaar van Afbeelding van het bureaublad van Azure-BP](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. Selecteer **+ Recordset op**de pagina **Instellingen** voor uw domein in het gebied van de **DNS-zone.**
    
    ![Afbeelding van het jaar van Afbeelding van het bureaublad van Azure-BP](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. Voeg de eerste van de twee SRV-records toe.
    
    Selecteer in het gebied **Recordset toevoegen** in de vakken voor de nieuwe recordset de waarden van de eerste rij in de volgende tabel. 
    
    (Kies de waarden **type** en **TTL** in de vervolgkeuzelijsten.) 
    
    |**Naam**|**Type**|**TTL**|**TTL-eenheid**|**Priority**|**Weight**|**Port**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip._tls  <br/> |SRV  <br/> |1  <br/> |Uur  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls._tcp  <br/> |SRV  <br/> |1  <br/> |Uur  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> 

    ![Afbeelding van het jaar van Afbeelding van het bureaublad](../../media/a436e0b4-8bb8-4a66-9c22-4e3b2dcf54ff.png)
  
5. Selecteer **OK**.
    
    ![Afbeelding van het jaar van Afbeelding van het bureaublad](../../media/a35b6c8a-d001-4b3c-8a67-96b4890e564c.png)
  
6. Voeg de andere SRV-record toe.
    
    Typ of kopieer en plak de waarden uit de tweede rij van de tabel in de vakken voor de nieuwe record.
    
> [!NOTE]
> Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
