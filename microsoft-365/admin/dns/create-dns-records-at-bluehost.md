---
title: DNS-records maken bij Bluehost voor Microsoft
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
ms.assetid: 657934ff-d9d2-4563-9ccf-ef4832a03a99
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services bij Bluehost voor Microsoft.
ms.openlocfilehash: a39e44794ad0d8c66cd0786f88642541c6978a8c
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629717"
---
# <a name="create-dns-records-at-bluehost-for-microsoft"></a>DNS-records maken bij Bluehost voor Microsoft

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Als Bluehost uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online enzovoort in te stellen.
  
Nadat u deze records bij Bluehost hebt toegevoegd, wordt uw domein ingesteld voor gebruik met Microsoft-services.
  
Zie Een openbare website gebruiken met Microsoft voor meer informatie over webhosting en DNS voor websites met [Microsoft.](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)
  
> [!NOTE]
> Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Zie Problemen zoeken en oplossen na het toevoegen van [uw domein- of DNS-records](../get-help-with-domains/find-and-fix-issues.md)als u problemen ondervindt met e-mailstroom of andere problemen na het toevoegen van DNS-records. 
  
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie
<a name="BKMK_verify"> </a>

Voordat u uw domein bij Microsoft gebruikt, moeten we ervoor zorgen dat u eigenaar bent. Uw mogelijkheid om in te loggen op uw account bij uw domeinregistrar en de DNS-record te maken bewijst microsoft dat u eigenaar bent van het domein.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
1. Ga eerst naar de pagina met domeinen bij Bluehost via [deze koppeling](https://my.bluehost.com/cgi/dm). U wordt gevraagd u eerst aan te melden.
    
2. Op de pagina **Domains**, in het gebied **domain**, zoekt u de rij voor het domein dat u wilt wijzigen, en schakelt u vervolgens het selectievakje in voor dat domein. 
    
    (Mogelijk moet u omlaag schuiven.)
    
3. Selecteer **dns-records beheren**in het ***domain_name-gebied*** in de rij **DNS-zoneeditor** .
    
4. Typ of kopieer en plak de waarden uit de volgende tabel op de pagina ** DNS-zoneeditor ** in het gebied **DNS-record toevoegen** in de vakken voor de nieuwe record. 
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Host Record** <br/> |**TTL** <br/> |**Type** <br/> |**TXT Value** <br/> |
    |@  <br/> |14400  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de waarde van uw specifieke **bestemming of adrespunt** in de tabel. [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |
   
5. Selecteer **Record toevoegen**.
    
6. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
Nu u de record op de site van uw domeinregistrar hebt toegevoegd, gaat u terug naar Microsoft en vraagt u om een zoekopdracht naar de record.
  
Wanneer Microsoft de juiste TXT-record vindt, wordt uw domein geverifieerd.
  
1. Ga in het Microsoft-beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Instellingendomeinen.</a> **Settings**

    
2. Kies op de pagina **Domeinen** de naam van het domein dat u verifieert. 
    
3. Kies **Start setup** op de pagina **Setup**.
    
4. Kies **Verifiëren** op de pagina **Domein verifiëren**.
    
> [!NOTE]
> Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Zie Problemen zoeken en oplossen na het toevoegen van [uw domein- of DNS-records](../get-help-with-domains/find-and-fix-issues.md)als u problemen ondervindt met e-mailstroom of andere problemen na het toevoegen van DNS-records. 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Voeg een MX-record toe, zodat e-mail voor uw domein naar Microsoft komt
<a name="BKMK_add_MX"> </a>

1. Ga eerst naar de pagina met domeinen bij Bluehost via [deze koppeling](https://my.bluehost.com/cgi/dm). U wordt gevraagd u eerst aan te melden.
    
2. Op de pagina **Domains**, in het gebied **domain**, zoekt u de rij voor het domein dat u wilt wijzigen, en schakelt u vervolgens het selectievakje in voor dat domein. 
    
    (Mogelijk moet u omlaag schuiven.)
    
3. Selecteer **dns-records beheren**in het ***domain_name-gebied*** in de rij **DNS-zoneeditor** .
    
4. Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add DNS Record** in de vakken voor de nieuwe record op de pagina **DNS Zone Editor**. 
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
    |**Host Record**|**TTL**|**Type**|**Points To**|**Priority**|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |14400  <br/> |MX  <br/> | *\<domeinsleutel\>*  .mail.protection.outlook.com  <br/>**Let op:** Haal \<uw domeinsleutel\> uit uw *Microsoft-account.* [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |0  <br/> Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit. <br/> |
   
   ![Type kiezen in de vervolgkeuzelijst](../../media/70791420-d83c-4a5d-a46c-5cc3bc67f565.png)
  
5. Selecteer **Record toevoegen**.
    
    ![Selecteer Record toevoegen](../../media/c7ef9733-1665-4dbf-accc-caadf1574abc.png)
  
6. Als het gedeelte **MX (Mail Exchanger)** andere MX-records bevat, verwijdert u deze. 
    
    Selecteer **Verwijderen** voor een van de andere MX-records.
    
    ![Verwijderen selecteren voor elke extra MX-record](../../media/6be17f54-3f33-47af-a9db-4689141530c2.png)
  
7. Selecteer **OK**in het bevestigingsdialoogvenster.
    
    ![Selecteer OK](../../media/a50df7a3-2906-4cc0-87d4-1231ab234230.png)
  
8. Verwijder op dezelfde manier alle andere MX-records die al worden vermeld.
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Voeg de zes CNAME-records toe die nodig zijn voor Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Ga eerst naar de pagina met domeinen bij Bluehost via [deze koppeling](https://my.bluehost.com/cgi/dm). U wordt gevraagd u eerst aan te melden.
    
2. Op de pagina **Domains**, in het gebied **domain**, zoekt u de rij voor het domein dat u wilt wijzigen, en schakelt u vervolgens het selectievakje in voor dat domein. 
    
    (Mogelijk moet u omlaag schuiven.)
    
3. Selecteer **dns-records beheren**in het ***domain_name-gebied*** in de rij **DNS-zoneeditor** .
    
4. Zoek in de sectie **A-records** de rij voor de **record voor automatisch ontdekken** en selecteer vervolgens **verwijderen** voor die rij. 
    
    > [!IMPORTANT]
    > U moet de bestaande **record voor automatisch ontdekken** verwijderen *voordat* u de **autodiscoverrecord** toevoegt die door Microsoft vereist is. U kunt in Bluehost geen twee **autodiscover** -records tegelijk behouden. 
  
    ![Selecteren Verwijderen](../../media/416a447e-3710-4ae7-8bf1-459381af4f6e.png)
  
5. Kies **OK**.
    
    ![Selecteer OK](../../media/0c8f409d-c39f-4ed2-9c95-9af3e61c2411.png)
  
6. Maak de eerste van de zes CNAME-records.
    
    Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in het gebied **Add DNS Record** in de vakken voor de nieuwe record op de pagina **DNS Zone Editor**. 
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
    |**Host Record**|**TTL**|**Type**|**Points To**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |14400  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |14400  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |14400  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |14400  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |14400  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![De eerste CNAME-record maken](../../media/4f12e9b1-9dec-4bc2-aa15-8bffa71fe131.png)
  
7. Selecteer **Record toevoegen**.
    
    ![Selecteer Record toevoegen](../../media/c2782250-a9a6-4aee-bb15-f57cb0008587.png)
  
8. Voeg als volgt de andere vijf CNAME-records toe:
    
    Maak nog steeds in de sectie **DNS-record toevoegen** een record met de waarden uit de volgende rij in de tabel en selecteer vervolgens opnieuw **Record toevoegen** om die record te voltooien. 
    
    Herhaal deze procedure totdat u alle zes CNAME-records hebt gemaakt.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Een TXT-record voor SPF toevoegen om spam tegen te gaan
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, maakt u geen nieuwe voor Microsoft. Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat. Hebt u voorbeelden nodig? Bekijk deze [externe domeinnaamsysteemrecords voor Microsoft.](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0) Als u uw SPF-record wilt valideren, u een van deze[SPF-validatietools](../setup/domains-faq.md)gebruiken. 
  
1. Ga eerst naar de pagina met domeinen bij Bluehost via [deze koppeling](https://my.bluehost.com/cgi/dm). U wordt gevraagd u eerst aan te melden.
    
2. Op de pagina **Domains**, in het gebied **domain**, zoekt u de rij voor het domein dat u wilt wijzigen, en schakelt u vervolgens het selectievakje in voor dat domein. 
    
    (Mogelijk moet u omlaag schuiven.)
    
3. Selecteer **dns-records beheren**in het ***domain_name-gebied*** in de rij **DNS-zoneeditor** .
    
4. Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add DNS Record** in de vakken voor de nieuwe record op de pagina **DNS Zone Editor**. 
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
        
    |**Host Record**|**TTL**|**Type**|**TXT Value**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |14400  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.           |
   
    ![De Waarde TXT kopiëren](../../media/b2dabd7a-ee3d-4209-aa1e-0233eb8cf3b9.png)
  
5. Selecteer **Record toevoegen**.
    
    ![Selecteer Record toevoegen](../../media/c050e9a2-2274-4640-8f0f-6752d382df5d.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Voeg de twee SRV-records toe die nodig zijn voor Microsoft
<a name="BKMK_add_SRV"> </a>

1. Ga eerst naar de pagina met domeinen bij Bluehost via [deze koppeling](https://my.bluehost.com/cgi/dm). U wordt gevraagd u eerst aan te melden.
    
2. Op de pagina **Domains**, in het gebied **domain**, zoekt u de rij voor het domein dat u wilt wijzigen, en schakelt u vervolgens het selectievakje in voor dat domein. 
    
    (Mogelijk moet u omlaag schuiven.)
    
3. Selecteer **dns-records beheren**in het ***domain_name-gebied*** in de rij **DNS-zoneeditor** .
    
4. Maak als volgt de eerste van de twee SRV-records.
    
    Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in het gebied **Add DNS Record** in de vakken voor de nieuwe record op de pagina **DNS Zone Editor**. 
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
    |**Service**|**Protocol**|**Host**|**TTL**|**Type**|**Prioriteit**|**Gewicht**|**Poort**|**Points To**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |@  <br/> |14400  <br/> |SRV  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |@  <br/> |14400  <br/> |SRV  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   
    ![De waarde voor de nieuwe record kopiëren](../../media/e2911bca-c00b-4b8a-837f-f1d438c474c4.png)
  
5. Selecteer **Record toevoegen**.
    
    ![Selecteer Record toevoegen](../../media/0fd6a587-03fd-4bce-8321-b14e6ad21f5c.png)
  
6. Voeg de andere SRV-record toe.
    
    Maak nog steeds in de sectie **DNS-record toevoegen** een record met de waarden uit de andere rij in de tabel en selecteer vervolgens opnieuw **Record toevoegen** om die record te voltooien. 
    
> [!NOTE]
> Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Zie Problemen zoeken en oplossen na het toevoegen van [uw domein- of DNS-records](../get-help-with-domains/find-and-fix-issues.md)als u problemen ondervindt met e-mailstroom of andere problemen na het toevoegen van DNS-records. 
  

