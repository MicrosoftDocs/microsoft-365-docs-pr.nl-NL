---
title: DNS-records maken voor Azure DNS-zones
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
ms.assetid: fbcef2d7-ebaf-40d0-ba1f-cdaeff9f50ef
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services in Azure DNS-zones voor Microsoft.
ms.openlocfilehash: fcc3ea42b7414cdd5fc0c34bfae91104287d2379
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400266"
---
# <a name="create-dns-records-for-azure-dns-zones"></a>DNS-records maken voor Azure DNS-zones

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Als Azure uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records in te stellen voor e-mail, Skype voor Bedrijven Online, enzovoort.
  
Dit zijn de belangrijkste records om toe te voegen. 
  
- [De naamserverrecords (NS-records) van uw domein wijzigen](#change-your-domains-nameserver-ns-records)
    
- [Een TXT-record toevoegen voor verificatie](#add-a-txt-record-for-verification)

- [Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [Voeg de vier CNAME-records toe die voor Microsoft vereist zijn](#add-the-four-cname-records-that-are-required-for-microsoft)
    
- [Een TXT-record voor SPF toevoegen om spam tegen te gaan](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [De twee SRV-records toevoegen die zijn vereist voor Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft)
    
Nadat u deze records bij Azure hebt toegevoegd, wordt uw domein ingesteld voor gebruik met Microsoft-services.
  
> [!NOTE]
> Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>De naamserverrecords (NS-records) van uw domein wijzigen
<a name="BKMK_NS"> </a>

> [!IMPORTANT]
> U moet deze procedure uitvoeren bij de domeinregistrar waar u uw domein hebt gekocht en geregistreerd. 
  
Toen u zich aanmeldde voor Azure, hebt u een brongroep binnen een DNS-zone gemaakt en vervolgens uw domeinnaam toegewezen aan die brongroep. Die domeinnaam is geregistreerd bij een externe domeinregistrar; Azure biedt geen domeinregistratieservices.
  
Als u DNS-records voor uw domein in Microsoft wilt verifiëren en maken, moet u eerst de naamservers van uw domeinregistrar wijzigen, zodat ze de Azure-naamservers gebruiken die aan uw brongroep zijn toegewezen.
  
Als u de naamservers van het domein zelf wilt wijzigen op de website van de domeinregistrar, voert u de volgende stappen uit:
  
1. Zoek het gedeelte op de website van de domeinregistrar waarop u de naamservers voor uw domein kunt wijzigen.
    
2. Maak twee naamserverrecords door de waarden in de volgende tabel te gebruiken of bewerk de bestaande naamserverrecords zodat ze overeenkomen met deze waarden: Hieronder wordt een voorbeeld van door Azure toegewezen nameservers weergegeven.
    


**Voornaamserver:** Gebruik de naamserverwaarde die door Azure is toegewezen.  
**Tweede naamserver:** Gebruik de naamserverwaarde die door Azure is toegewezen.  

![Afbeelding van het lint](../../media/3e4805ea-608a-4df9-8f68-1fbf70d13d08.png)
  
> [!TIP]
> U moet ten minste twee naamserverrecords gebruiken. Als er andere naamservers op de website van uw domeinregistrar worden vermeld, moet u deze verwijderen. 
  
3. Sla uw wijzigingen op.
    
> [!NOTE]
> Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd. Vervolgens zijn uw Microsoft-e-mail en andere services helemaal klaar om met uw domein te werken. 
  
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie
<a name="BKMK_verify"> </a>

Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
1. Ga om aan de slag te gaan naar de pagina met domeinen in Azure via [deze koppeling.](https://portal.azure.com ) U wordt gevraagd u eerst aan te melden.
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. Typ **dns-zones**in de **zoekbalk** op de **dashboardpagina.** Selecteer **dns-zones** onder het gedeelte **Services** in de resultatenweergave. Zodra u bent omgeleid, selecteert u het domein dat u wilt bijwerken.
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. Selecteer op de pagina **Instellingen** voor uw domein in het **gebied DNS-zone** de optie **+ Recordset .**
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. Selecteer in het **gebied Record toevoegen in** de vakken voor de nieuwe recordset de waarden in de volgende tabel. 
    
    (Kies de **eenheidswaarden Type** en **TTL** in de vervolgkeuzelijsten.) 
    
    |**Naam**|**Type**|**TTL**|**TTL-eenheid**|**Value**|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |TXT  <br/> |1  <br/> |Uren  <br/> |MS=ms *XXXXXXXX*  <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Afbeelding van het te maken van de afbeelding van het gebruik van Azure-Verifiëren 1-1](../../media/7d5a253c-e88f-4565-a00a-79bba52f9970.png)
  
5. Kies **OK**.
  
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

1. Ga om aan de slag te gaan naar de pagina met domeinen in Azure via [deze koppeling.](https://portal.azure.com ) U wordt gevraagd u eerst aan te melden.
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. Selecteer op de pagina **Dashboard** in het gebied **Alle bronnen** het domein dat u wilt bijwerken. 
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. Selecteer op de pagina **Instellingen** voor uw domein in het **gebied DNS-zone** de optie **+ Recordset .**
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. Selecteer in het **gebied Record toevoegen in** de vakken voor de nieuwe recordset de waarden in de volgende tabel. 
    
    (Kies de **eenheidswaarden Type** en **TTL** in de vervolgkeuzelijsten.) 
    
    |**Naam**|**Type**|**TTL**|**TTL-eenheid**|**Preference**|**Mail Exchange**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |1  <br/> |Uren  <br/> |10  <br/> Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit.    <br/> | *\<domain-key\>*.mail.protection.outlook.com  <br/> **Let op:** Haal uw *\<domain-key\>* van uw Microsoft-account.   [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)  
   
    ![Afbeelding van het te maken van de afbeelding smakende afbeelding van het bis](../../media/712c23ae-9d38-4af2-94e0-0704e70744fe.png)
  
5. Kies **OK**.
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-BP-2-2](../../media/2f24225f-69ac-41dc-91c5-93d327360f74.png)
  
6. Als er andere MX-records worden vermeld in de sectie **MX Records,** moet u deze verwijderen. 
    
    Selecteer eerst in het **gebied met DNS-zone** de **set MX Record**.
    
    ![Afbeelding van het te maken van de afbeelding smakende afbeelding van het bis](../../media/9890da61-6fcd-4c61-888e-ccbb84f80cd0.png)
  
    Selecteer vervolgens de MX-record die u wilt verwijderen.
    
    ![Afbeelding van het te maken van de afbeelding smakende afbeelding van het bis](../../media/afe54f12-66d2-4ff3-80e9-427448e4c32c.png)
  
7. Selecteer het **menu Context (...)** en kies **Verwijderen**.
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-BP-2-5](../../media/25219e25-bc14-4bc7-84ed-ee65eb28a8ed.png)
  
8. Kies **Opslaan**.
    
    ![Afbeelding van het te maken van de afbeelding smakende afbeelding van de knop 2-6](../../media/c6133096-5e43-4637-9c01-b63ee4b03517.png)
  
## <a name="add-the-four-cname-records-that-are-required-for-microsoft"></a>Voeg de vier CNAME-records toe die voor Microsoft vereist zijn
<a name="BKMK_add_CNAME"> </a>

1. Ga om aan de slag te gaan naar de pagina met domeinen in Azure via [deze koppeling.](https://portal.azure.com ) U wordt gevraagd u eerst aan te melden.
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. Selecteer op de pagina **Dashboard** in het gebied **Alle bronnen** het domein dat u wilt bijwerken. 
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. Selecteer op de pagina **Instellingen** voor uw domein in het **gebied DNS-zone** de optie **+ Recordset .**
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. Voeg de eerste van de vier CNAME-records toe.
    
    Typ of kopieer en plak de waarden uit de eerste rij in de volgende tabel in het **gebied Recordset toevoegen** in de vakken voor de nieuwe recordset. 
    
    (Kies de **eenheidswaarden Type** en **TTL** in de vervolgkeuzelijsten.) 
    
    |**Naam**|**Type**|**TTL**|**TTL-eenheid**|**Alias**|
    |:-----|:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |1  <br/> |Uren  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |1  <br/> |Uren  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |1  <br/> |Uren  <br/> |webdir.online.lync.com  <br/> |
    
   
    ![Afbeelding van het te maken van de afbeelding smakende afbeelding van het menu Voor Azure](../../media/a1c4d869-da97-43b3-952c-d513a20231dc.png)
  
5. Kies **OK**.
    
    ![Afbeelding van het te maken van afbeelding van het gebruik van Azure-afbeelding](../../media/b89b51da-1c07-43cf-9fab-75d2e5eb3544.png)
  
6. Voeg de andere drie CNAME-records toe.
    
    Selecteer in het **gebied met DE DNS-zone** de optie **+ Recordset**. Maak vervolgens in de lege recordset een record met de waarden uit de volgende rij in de tabel en selecteer opnieuw **OK** om die record te voltooien. 
    
    Herhaal deze procedure totdat u alle vier CNAME-records hebt gemaakt.
    
7.  (Optioneel) Voeg 2 CNAME-records toe voor MDM.

> [!IMPORTANT]
> Als u Mobile Device Management (MDM) voor Microsoft hebt, moet u twee extra CNAME-records maken. Volg de stappen die u hebt gevolgd voor de andere vier CNAME-records, maar gebruik de waarden uit de volgende tabel. (Als u geen MDM hebt, u deze stap overslaan.) 
  
|**Naam**|**Type**|**TTL**|**TTL-eenheid**|**Alias**|
|:-----|:-----|:-----|:-----|:-----|
|enterpriseregistration  <br/> |CNAME  <br/> |1  <br/> |Uren  <br/> |enterpriseregistration.windows.net  <br/> |
|enterpriseenrollment  <br/> |CNAME  <br/> |1  <br/> |Uren  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Een TXT-record voor SPF toevoegen om spam tegen te gaan
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft. Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat. 
  
1. Ga om aan de slag te gaan naar de pagina met domeinen in Azure via [deze koppeling.](https://portal.azure.com ) U wordt gevraagd u eerst aan te melden.
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. Selecteer op de pagina **Dashboard** in het gebied **Alle bronnen** het domein dat u wilt bijwerken. 
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. Selecteer in het **gebied met DNS-zone** de **set TXT-record**.
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-afbeelding](../../media/03095196-5010-4072-8503-79b812084dbf.png)
  
4. Selecteer in het gebied **Recordset-eigenschappen** in de vakken voor de nieuwe recordset de waarden in de volgende tabel. 
    
    (Kies de **eenheidswaarden Type** en **TTL** in de vervolgkeuzelijsten.) 
    
    |**Naam**|**Type**|**TTL**|**TTL-eenheid**|**Value**|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |TXT  <br/> |1  <br/> |Uren  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.           

    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-afbeelding](../../media/78e84c43-e0ce-433f-8e74-9157fb093cca.png)
  
5. Kies **Opslaan**.
    
    ![Afbeelding van het te maken van de afbeelding smakende afbeelding van het menu 4-3](../../media/d7421c7f-ea63-4e11-8595-a482b8c165e0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>De twee SRV-records toevoegen die zijn vereist voor Microsoft
<a name="BKMK_add_SRV"> </a>

1. Ga om aan de slag te gaan naar de pagina met domeinen in Azure via [deze koppeling.](https://portal.azure.com ) U wordt gevraagd u eerst aan te melden.
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. Selecteer op de pagina **Dashboard** in het gebied **Alle bronnen** het domein dat u wilt bijwerken. 
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. Selecteer op de pagina **Instellingen** voor uw domein in het **gebied DNS-zone** de optie **+ Recordset .**
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-bp-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. Voeg de eerste van de twee SRV-records toe.
    
    Selecteer in het **gebied Record toevoegen in** de vakken voor de nieuwe recordset de waarden uit de eerste rij in de volgende tabel. 
    
    (Kies de **eenheidswaarden Type** en **TTL** in de vervolgkeuzelijsten.) 
    
    |**Naam**|**Type**|**TTL**|**TTL-eenheid**|**Prioriteit**|**Gewicht**|**Poort**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip._tls  <br/> |SRV  <br/> |1  <br/> |Uren  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls._tcp  <br/> |SRV  <br/> |1  <br/> |Uren  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> 

    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-BP-5-1](../../media/a436e0b4-8bb8-4a66-9c22-4e3b2dcf54ff.png)
  
5. Kies **OK**.
    
    ![Afbeelding van het te maken voor afbeelding van het gebruik van Azure-BP-5-2](../../media/a35b6c8a-d001-4b3c-8a67-96b4890e564c.png)
  
6. Voeg de andere SRV-record toe.
    
    Typ of kopieer en plak de waarden uit de tweede rij van de tabel in de vakken voor de nieuwe record.
    
> [!NOTE]
> Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
