---
title: DNS-records maken op Dyn.com voor Microsoft
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
ms.assetid: 34e57a00-2a7d-469c-beec-089423f18369
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services op Dyn.com voor Microsoft.
ms.openlocfilehash: f9b705f94f05799b0aa97539e372c3efcfe2e4c8
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629585"
---
# <a name="create-dns-records-at-dyncom-for-microsoft"></a>DNS-records maken op Dyn.com voor Microsoft

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Als Dyn.com uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online enzovoort in te stellen.
 
Zie Een openbare website gebruiken met Microsoft voor meer informatie over webhosting en DNS voor websites met [Microsoft.](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)
  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie
<a name="BKMK_verify"> </a>

1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij Dyn.com via [deze koppeling](https://account.dyn.com/dns/). U wordt gevraagd u eerst aan te melden.
    
    ![Schermopname van het pictogram Meer mensen uitnodigen](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. Selecteer **op** de pagina Zone Level Services de optie **Dyn Standard DNS-service** voor het domein dat u wilt bewerken. 
    
3. Selecteer **Voorkeuren**op de **PAGINA DNS** voor uw domein .
    
4. Selecteer **Expertinterface inschakelen**.
    
5. Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add DNS Record** in de vakken voor de nieuwe record. 
    
    (Kies in de vervolgkeuzelijst de waarde **Type**.) 
    
    |**Host**|**TTL**|**Type**|**Data**|
    |:-----|:-----|:-----|:-----|
    |(Laat dit veld leeg.)  <br/> |600  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de waarde van uw specifieke **bestemming of adrespunt** in de tabel.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![Afbeelding van het te hebben van afbeelding van het gebruik-1-1](../../media/b3730b15-a313-4b4c-b91e-646eebb649e8.png)
  
6. Selecteer **Record maken**.
    
    ![Dyn-BP-Verify-1-2](../../media/8b63b4ee-dbd7-44a7-b1e6-c6892b02f13e.png)
  
7. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
Nu u de record op de site van uw domeinregistrar hebt toegevoegd, gaat u terug naar Microsoft en vraagt u de record aan.
  
Wanneer Microsoft de juiste TXT-record vindt, wordt uw domein geverifieerd.
  
1. Ga in het Microsoft-beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Instellingendomeinen.</a> **Settings**

    
2. Kies op de pagina **Domeinen** de naam van het domein dat u verifieert. 
    
    
  
3. Kies **Start setup** op de pagina **Setup**.
    
    
  
4. Kies **Verifiëren** op de pagina **Domein verifiëren**.
    
    
  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Voeg een MX-record toe, zodat e-mail voor uw domein naar Microsoft komt
<a name="BKMK_add_MX"> </a>

1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij Dyn.com via [deze koppeling](https://account.dyn.com/dns/). U wordt gevraagd u eerst aan te melden.
    
    ![Schermopname van het pictogram Meer mensen uitnodigen](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. Selecteer **op** de pagina Zone Level Services de optie **Dyn Standard DNS-service** voor het domein dat u wilt bewerken. 
    
3. Selecteer **Voorkeuren**op de PAGINA DNS voor uw domein .
    
4. Selecteer **Expertinterface inschakelen**.
    
5. Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add DNS Record** in de vakken voor de nieuwe record. 
    
    (Kies in de vervolgkeuzelijst de waarde **Type**.) 
    
    |**Host**|**TTL**|**Type**|**Data**|
    |:-----|:-----|:-----|:-----|
    |(Laat dit veld leeg.)  <br/> |600  <br/> |MX  <br/> |10  *\<domeinsleutel\>*  .mail.protection.outlook.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> De **10** is de MX-prioriteitwaarde. Voeg deze toe aan het begin van de MX-waarde, van de rest van de waarde gescheiden door een spatie.  <br/> **Let op:** Haal uw * \<domeinsleutel\> * uit uw Microsoft-account.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)      <br>    Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit. <br/> |
   
    ![Afbeelding van het te maken](../../media/62ac77b7-c84d-426d-9ec4-a28d6479ad04.png)
  
6. Selecteer **Record maken**.
    
    ![Dyn-BP-Configure-2-2](../../media/e84e2cca-75e3-4584-8a98-f2f89cb71bd3.png)
  
7. Als er andere MX-records zijn, verwijder deze dan door in de kolom **Delete** het selectievakje voor die records in te schakelen. 
    
    ![bloemen en tekst](../../media/f24f02cc-c0b7-42cf-a2ff-4d0fc203e4de.png)
  
8. Selecteer **Wijzigingen toepassen**.
    
    ![Dyn-BP-Configure-2-4](../../media/0cc23c2b-b6f2-4f58-af20-4c6506de7b43.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Voeg de zes CNAME-records toe die nodig zijn voor Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij Dyn.com via [deze koppeling](https://account.dyn.com/dns/). U wordt gevraagd u eerst aan te melden.
    
    ![Schermopname van het pictogram Meer mensen uitnodigen](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. Selecteer **op** de pagina Zone Level Services de optie **Dyn Standard DNS-service** voor het domein dat u wilt bewerken. 
    
3. Selecteer **Voorkeuren**op de **PAGINA DNS** voor uw domein .
    
4. Selecteer **Expertinterface inschakelen**.
    
5. Voeg de eerste van de zes CNAME-records toe.
    
    Typ of kopieer en plak in de sectie **Add DNS Record** de waarden uit de eerste rij van de volgende tabel in de vakken voor de nieuwe record. 
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
    |**Host**|**TTL**|**Type**|**Data**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |600  <br/> |CNAME  <br/> |autodiscover.outlook.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
    |sip  <br/> |600  <br/> |CNAME  <br/> |sipdir.online.lync.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
    |lyncdiscover  <br/> |600  <br/> |CNAME  <br/> |webdir.online.lync.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
    |enterpriseregistration  <br/> |600  <br/> |CNAME  <br/> |enterpriseregistration.windows.net.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
    |enterpriseenrollment  <br/> |600  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
   
    ![Afbeelding van het te maken](../../media/1fd80695-d3d7-4298-9ebe-97a69f46f1b2.png)
  
6. Selecteer **Record maken**.
    
    ![Dyn-BP-Configure-3-2](../../media/89551495-3fa5-44ab-96b2-855f70be0880.png)
  
7. Voeg de resterende vijf CNAME-records toe.
    
    Maak in de sectie **DNS-record toevoegen** een record met de waarden uit de volgende rij in de tabel en selecteer vervolgens opnieuw **Record maken** om die record te voltooien. 
    
    Herhaal deze procedure totdat u alle zes CNAME-records hebt gemaakt.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Een TXT-record voor SPF toevoegen om spam tegen te gaan
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, maakt u geen nieuwe voor Microsoft. Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat.
  
1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij Dyn.com via [deze koppeling](https://account.dyn.com/dns/). U wordt gevraagd u eerst aan te melden.
    
    ![Schermopname van het pictogram Meer mensen uitnodigen](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. Selecteer **op** de pagina Zone Level Services de optie **Dyn Standard DNS-service** voor het domein dat u wilt bewerken. 
    
3. Selecteer **Voorkeuren**op de **PAGINA DNS** voor uw domein .
    
4. Selecteer **Expertinterface inschakelen**.
    
5. Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add DNS Record** in de vakken voor de nieuwe record. 
    
    (Kies in de vervolgkeuzelijst de waarde **Type**.) 
    
    |**Host**|**TTL**|**Type**|**Data**|
    |:-----|:-----|:-----|:-----|
    |(Laat dit veld leeg.)  <br/> |600  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.           |
   
    ![Afbeelding van het te maken](../../media/f8511349-3ea2-40c3-9853-98e1a58a91b5.png)
  
6. Selecteer **Record maken**.
    
    ![Veld met meerdere waarden](../../media/bbe04835-d3c0-4146-8123-9781bb9eca51.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Voeg de twee SRV-records toe die nodig zijn voor Microsoft
<a name="BKMK_add_SRV"> </a>

1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij Dyn.com via [deze koppeling](https://account.dyn.com/dns/). Je wordt gevraagd om eerst in te loggen 
    
    ![Schermopname van het pictogram Meer mensen uitnodigen](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. Selecteer **op** de pagina Zone Level Services de optie **Dyn Standard DNS-service** voor het domein dat u wilt bewerken. 
    
3. Selecteer **Voorkeuren**op de **PAGINA DNS** voor uw domein .
    
4. Selecteer **Expertinterface inschakelen**.
    
5. Voeg de eerste van de twee SRV-records toe.
    
    Typ of kopieer en plak in de sectie **Add DNS Record** de waarden uit de eerste rij van de volgende tabel in de vakken voor de nieuwe record. 
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
    |**Host**|**TTL**|**Type**|**Data**|
    |:-----|:-----|:-----|:-----|
    |_sip._tls|600|SRV|100 1 443 sipdir.online.lync.com. **Deze waarde MOET eindigen op een punt (.)**<br>**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.           |
    |_sipfederationtls._tcp|600|SRV|100 1 5061 sipfed.online.lync.com. **Deze waarde MOET eindigen op een punt (.)**<br> **Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.           |
   
    ![Afbeelding van het te maken](../../media/a6873411-f4ce-4327-9145-02d435930976.png)
  
6. Selecteer **Record maken**.
    
    ![Dyn-BP-Configure-5-2](../../media/e6f33452-e527-473b-a645-b31ed70b0d43.png)
  
7. Voeg de andere SRV-record toe.
    
    Maak in de sectie **DNS-record toevoegen** een record met de waarden uit de tweede rij in de tabel en selecteer vervolgens opnieuw **Record maken** om die record te voltooien. 
    
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
