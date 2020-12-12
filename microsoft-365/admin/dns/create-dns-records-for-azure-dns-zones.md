---
title: DNS-records voor Azure DNS-zones maken
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
ms.assetid: fbcef2d7-ebaf-40d0-ba1f-cdaeff9f50ef
description: Lees hoe u uw domein verifieert en DNS-records instelt voor e-mail, Skype voor bedrijven online en andere services op Azure DNS-zones voor Microsoft.
ms.openlocfilehash: c276570ec1d5ff079348bd8202ea597ef61e88f6
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656865"
---
# <a name="create-dns-records-for-azure-dns-zones"></a>DNS-records voor Azure DNS-zones maken

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt. 
  
Als Azure uw DNS-hosting provider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records in te stellen voor e-mail, Skype voor bedrijven online, enzovoort.
  
Dit zijn de belangrijkste records om toe te voegen. 
  
- [De naamserverrecords (NS-records) van uw domein wijzigen](#change-your-domains-nameserver-ns-records)
    
- [Een TXT-record toevoegen voor verificatie](#add-a-txt-record-for-verification)

- [Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [De vier CNAME-records toevoegen die vereist zijn voor Microsoft](#add-the-four-cname-records-that-are-required-for-microsoft)
    
- [Een TXT-record voor SPF toevoegen om spam tegen te gaan](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [De twee SRV-records toevoegen die zijn vereist voor Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft)
    
Nadat u deze records bij Azure hebt toegevoegd, is uw domein ingesteld voor gebruik met Microsoft-services.
  
> [!NOTE]
> Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>De naamserverrecords (NS-records) van uw domein wijzigen
<a name="BKMK_NS"> </a>

> [!IMPORTANT]
> U moet deze procedure uitvoeren bij de domeinregistrar waar u uw domein hebt gekocht en geregistreerd. 
  
Toen u zich registreerde voor Azure, hebt u een resourcegroep gemaakt in een DNS-zone en hebt u vervolgens uw domeinnaam aan die resourcegroep toegewezen. Deze domeinnaam is geregistreerd bij een externe domeinregistratie; Azure biedt geen Domain Registration Services.
  
Als u DNS-records voor uw domein wilt controleren en maken in Microsoft, moet u eerst de naamservers van uw domeinregistratie wijzigen, zodat ze de Azure naamservers gebruiken die aan de resourcegroep is toegewezen.
  
Als u de naamservers van het domein zelf wilt wijzigen op de website van de domeinregistrar, voert u de volgende stappen uit:
  
1. Zoek het gedeelte op de website van de domeinregistrar waarop u de naamservers voor uw domein kunt wijzigen.
    
2. Maak twee naamserverrecords door de waarden in de volgende tabel te gebruiken of bewerk de bestaande naamserverrecords zodat ze overeenkomen met deze waarden: Hieronder ziet u een voorbeeld van de aan Azure toegewezen naamservers.
    


**Eerste naamserver:** Gebruik de waarde van name server die is toegewezen door Azure.  
**Tweede naamserver:** Gebruik de waarde van name server die is toegewezen door Azure.  

![Afbeelding van Azure-1-1](../../media/3e4805ea-608a-4df9-8f68-1fbf70d13d08.png)
  
> [!TIP]
> U dient ten minste twee naamserver records te gebruiken. Als er andere naamservers worden weergegeven op de website van uw domeinregistratie, moet u deze verwijderen. 
  
3. Sla uw wijzigingen op.
    
> [!NOTE]
> Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd. Vervolgens zijn uw Microsoft-e-mail en andere services allemaal ingesteld voor gebruik met uw domein. 
  
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie
<a name="BKMK_verify"> </a>

Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
1. Als u wilt beginnen, gaat u naar uw domeinen pagina bij Azure met [deze koppeling](https://portal.azure.com ). U wordt gevraagd u eerst aan te melden.
    
    ![1-1-](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. Gebruik de **zoekbalk** op de **Dashboard** -pagina en typ **DNS zones**. Selecteer in de weergave resultaten de optie **DNS zones** onder het onderdeel **Services** . Als u het domein hebt doorgestuurd, selecteert u het domein dat u wilt bijwerken.
    
    ![1-2-](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. Selecteer op de pagina **instellingen** voor uw domein in het gebied **DNS-zone** de optie **+ record set**.
    
    ![1-3-](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. Selecteer in het gebied **Add Record set** de waarden uit de volgende tabel in de vakken voor de nieuwe recordset. 
    
    (Kies in de vervolgkeuzelijsten de waarden **type** en **TTL** .) 
    
    |**Naam**|**Type**|**TTL**|**TTL-eenheid**|**Value**|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |TXT  <br/> |1  <br/> |Uren  <br/> |MS=ms *XXXXXXXX*  <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Controle van Azure 1-1](../../media/7d5a253c-e88f-4565-a00a-79bba52f9970.png)
  
5. Selecteer **OK**.
  
6. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
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

1. Als u wilt beginnen, gaat u naar uw domeinen pagina bij Azure met [deze koppeling](https://portal.azure.com ). U wordt gevraagd u eerst aan te melden.
    
    ![1-1-](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. Selecteer op de pagina **Dashboard** , in het gebied **all resources** , het domein dat u wilt bijwerken. 
    
    ![1-2-](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. Selecteer op de pagina **instellingen** voor uw domein in het gebied **DNS-zone** de optie **+ record set**.
    
    ![1-3-](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. Selecteer in het gebied **Add Record set** de waarden uit de volgende tabel in de vakken voor de nieuwe recordset. 
    
    (Kies in de vervolgkeuzelijsten de waarden **type** en **TTL** .) 
    
    |**Naam**|**Type**|**TTL**|**TTL-eenheid**|**Preference**|**E-mail uitwisselen**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |1  <br/> |Uren  <br/> |10  <br/> Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit. <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **Opmerking:** Neem uw  *\<domain-key\>*  van uw Microsoft-account.   [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)  
   
    ![2-1-](../../media/712c23ae-9d38-4af2-94e0-0704e70744fe.png)
  
5. Selecteer **OK**.
    
    ![2-2-](../../media/2f24225f-69ac-41dc-91c5-93d327360f74.png)
  
6. Als er andere MX-records worden vermeld in de sectie **MX records** , moet u deze verwijderen. 
    
    Selecteer eerst de **MX-recordset** in het gebied **DNS zone** .
    
    ![2-3-](../../media/9890da61-6fcd-4c61-888e-ccbb84f80cd0.png)
  
    Vervolgens selecteert u de MX-record die u wilt verwijderen.
    
    ![2-4-](../../media/afe54f12-66d2-4ff3-80e9-427448e4c32c.png)
  
7. Selecteer het **context menu (...)** en kies vervolgens **verwijderen**.
    
    ![2-5-](../../media/25219e25-bc14-4bc7-84ed-ee65eb28a8ed.png)
  
8. Kies **Opslaan**.
    
    ![2-6-](../../media/c6133096-5e43-4637-9c01-b63ee4b03517.png)
  
## <a name="add-the-four-cname-records-that-are-required-for-microsoft"></a>De vier CNAME-records toevoegen die vereist zijn voor Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Als u wilt beginnen, gaat u naar uw domeinen pagina bij Azure met [deze koppeling](https://portal.azure.com ). U wordt gevraagd u eerst aan te melden.
    
    ![1-1-](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. Selecteer op de pagina **Dashboard** , in het gebied **all resources** , het domein dat u wilt bijwerken. 
    
    ![1-2-](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. Selecteer op de pagina **instellingen** voor uw domein in het gebied **DNS-zone** de optie **+ record set**.
    
    ![1-3-](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. Voeg de eerste van de vier CNAME-records toe.
    
    Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in het gebied **Add Record set** in de vakken voor de nieuwe recordset. 
    
    (Kies in de vervolgkeuzelijsten de waarden **type** en **TTL** .) 
    
    |**Naam**|**Type**|**TTL**|**TTL-eenheid**|**Alias**|
    |:-----|:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |1  <br/> |Uren  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |1  <br/> |Uren  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |1  <br/> |Uren  <br/> |webdir.online.lync.com  <br/> |
    
   
    ![3-1-](../../media/a1c4d869-da97-43b3-952c-d513a20231dc.png)
  
5. Selecteer **OK**.
    
    ![3-2-](../../media/b89b51da-1c07-43cf-9fab-75d2e5eb3544.png)
  
6. Voeg de andere drie CNAME-records toe.
    
    Selecteer in het gebied **DNS zone** de optie **+ record set**. Maak vervolgens een record met behulp van de waarden uit de volgende rij in de tabel en selecteer **OK** om de record te voltooien. 
    
    Herhaal deze procedure totdat u alle vier CNAME-records hebt gemaakt.
    
7.  Option Twee CNAME-records voor MDM toevoegen.

> [!IMPORTANT]
> Als u over MDM (Mobile Device Management) voor Microsoft beschikt, moet u twee extra CNAME-records maken. Volg de stappen die u hebt gevolgd voor de andere vier CNAME-records, maar gebruik de waarden uit de volgende tabel. (Als u geen MDM hebt, kunt u deze stap overslaan.) 
  
|**Naam**|**Type**|**TTL**|**TTL-eenheid**|**Alias**|
|:-----|:-----|:-----|:-----|:-----|
|enterpriseregistration  <br/> |CNAME  <br/> |1  <br/> |Uren  <br/> |enterpriseregistration.windows.net  <br/> |
|enterpriseenrollment  <br/> |CNAME  <br/> |1  <br/> |Uren  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Een TXT-record voor SPF toevoegen om spam tegen te gaan
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft. In plaats daarvan voegt u de vereiste Microsoft-waarden toe aan de huidige record, zodat u  *één*  SPF-record hebt die beide sets met waarden bevat. 
  
1. Als u wilt beginnen, gaat u naar uw domeinen pagina bij Azure met [deze koppeling](https://portal.azure.com ). U wordt gevraagd u eerst aan te melden.
    
    ![1-1-](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. Selecteer op de pagina **Dashboard** , in het gebied **all resources** , het domein dat u wilt bijwerken. 
    
    ![1-2-](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. Selecteer in het gebied **DNS zone** de **txt recordset**.
    
    ![4-1-](../../media/03095196-5010-4072-8503-79b812084dbf.png)
  
4. Selecteer in het gebied **eigenschappenset** van de record de waarden uit de volgende tabel in de vakken voor de nieuwe record set. 
    
    (Kies in de vervolgkeuzelijsten de waarden **type** en **TTL** .) 
    
    |**Naam**|**Type**|**TTL**|**TTL-eenheid**|**Value**|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |TXT  <br/> |1  <br/> |Uren  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.           

    ![4-2-](../../media/78e84c43-e0ce-433f-8e74-9157fb093cca.png)
  
5. Kies **Opslaan**.
    
    ![4-3-](../../media/d7421c7f-ea63-4e11-8595-a482b8c165e0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>De twee SRV-records toevoegen die zijn vereist voor Microsoft
<a name="BKMK_add_SRV"> </a>

1. Als u wilt beginnen, gaat u naar uw domeinen pagina bij Azure met [deze koppeling](https://portal.azure.com ). U wordt gevraagd u eerst aan te melden.
    
    ![1-1-](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. Selecteer op de pagina **Dashboard** , in het gebied **all resources** , het domein dat u wilt bijwerken. 
    
    ![1-2-](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. Selecteer op de pagina **instellingen** voor uw domein in het gebied **DNS-zone** de optie **+ record set**.
    
    ![1-3-](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. Voeg de eerste van de twee SRV-records toe.
    
    Selecteer in het gebied **Add Record set** de waarden uit de eerste rij in de volgende tabel in de vakken voor de nieuwe recordset. 
    
    (Kies in de vervolgkeuzelijsten de waarden **type** en **TTL** .) 
    
    |**Naam**|**Type**|**TTL**|**TTL-eenheid**|**Prioriteit**|**Gewicht**|**Poort**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip _sip._tls  <br/> |SRV  <br/> |1  <br/> |Uren  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls _sipfederationtls._tcp  <br/> |SRV  <br/> |1  <br/> |Uren  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> 

    ![5-1-](../../media/a436e0b4-8bb8-4a66-9c22-4e3b2dcf54ff.png)
  
5. Selecteer **OK**.
    
    ![5-2-](../../media/a35b6c8a-d001-4b3c-8a67-96b4890e564c.png)
  
6. Voeg de andere SRV-record toe.
    
    Typ of kopieer en plak de waarden uit de tweede rij van de tabel in de vakken voor de nieuwe record.
    
> [!NOTE]
> Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
