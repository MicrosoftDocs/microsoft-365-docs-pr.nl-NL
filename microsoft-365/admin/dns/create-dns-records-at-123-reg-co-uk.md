---
title: DNS-records maken op 123-reg.co.uk voor Office 365
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
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: Lees uw domein verifiëren en STEL DNS-records in voor e-mail, Skype voor Bedrijven Online en andere services op 123-reg.co.uk voor Office 365.
ms.openlocfilehash: 521426f039ac02e8c4566f5901fee49679de4e70
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211857"
---
# <a name="create-dns-records-at-123-regcouk-for-office-365"></a>DNS-records maken op 123-reg.co.uk voor Office 365

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Als 123-reg.co.uk uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.
  
Nadat u deze records bij 123-reg.co.uk hebt toegevoegd, is uw domein ingesteld voor gebruik met Office 365-services.
  
Zie [Een openbare website gebruiken met Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9) voor informatie over webhosting en DNS voor websites met Office 365.
  
> [!NOTE]
> Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie
<a name="BKMK_verify"> </a>

Voordat u uw domein met Office 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Office 365 bewezen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij 123-reg.co.uk via [deze koppeling](https://www.123-reg.co.uk/secure/cpanel/domain/overview). U wordt gevraagd u eerst aan te melden.
    
2. Selecteer op de pagina **Domain name overview** de naam van het domein dat u wilt bewerken. 
    
3. Kies in de vervolgkeuzelijst **Select action** de optie **DNS**. 
    
4. Selecteer **op** de pagina Uw DNS beheren het tabblad **Geavanceerd DNS.** 
    
5. Ga naar het gebied **Advanced DNS**. In de vakken voor de nieuwe record in dit gebied kunt u vervolgens de waarden uit de volgende tabel typen of kopiëren en plakken. 
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
    ||||
    |:-----|:-----|:-----|
    |**Hostname** <br/> |**Type** <br/> |**Destination TXT/SPF** <br/> |
    |@  <br/> |TXT/SPF  <br/> |MS=ms *XXXXXXXX*  <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365. [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |
   
6. Kies **Toevoegen**.
    
7. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Office 365 en vraagt u of Office 365 naar de record wil zoeken.
  
Wanneer in Office 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.
  
1. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.

    
2. Kies op de pagina **Domeinen** de naam van het domein dat u verifieert. 
    
3. Kies **Start setup** op de pagina **Setup**.
    
4. Kies **Verifiëren** op de pagina **Domein verifiëren**.
    
> [!NOTE]
> Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Een MX-record toevoegen zodat e-mail voor uw domein bij Office 365 terechtkomt
<a name="BKMK_add_MX"> </a>

1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij 123-reg.co.uk via [deze koppeling](https://www.123-reg.co.uk/secure/cpanel/domain/overview). U wordt gevraagd u eerst aan te melden.
    
2. Selecteer op de pagina **Domain name overview** de naam van het domein dat u wilt bewerken. 
    
3. Kies in de vervolgkeuzelijst **Select action** de optie **DNS**. 
    
4. Selecteer **op** de pagina Uw DNS beheren het tabblad **Geavanceerd DNS.** 
    
5. Ga naar het gebied **Advanced DNS**. In de vakken voor de nieuwe record in dit gebied kunt u vervolgens de waarden uit de volgende tabel typen of kopiëren en plakken. 
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
    |**Hostname**|**Type**|**Priority**|**Destination MX**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |1  <br/> Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.    <br/> | *\<domein-sleutel\>*  .mail.protection.outlook.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> **Opmerking**: Uw \<domeinsleutel\> kunt u ophalen uit uw Office 365-account. [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Waarden uit de tabel kopiëren en plakken](../../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. Kies **Toevoegen**.
    
    ![Selecteer Toevoegen](../../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. Als er andere MX-records zijn, verwijdert u deze door het pictogram **Verwijderen (Prullenbak)** voor die records te kiezen. 
    
    ![Verwijderen selecteren (pictogram prullenbak)](../../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>De zes CNAME-records toevoegen die voor Office 365 vereist zijn
<a name="BKMK_add_CNAME"> </a>

1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij 123-reg.co.uk via [deze koppeling](https://www.123-reg.co.uk/secure/cpanel/domain/overview). U wordt gevraagd u eerst aan te melden.
    
2. Selecteer op de pagina **Domain name overview** de naam van het domein dat u wilt bewerken. 
    
3. Kies in de vervolgkeuzelijst **Select action** de optie **DNS**. 
    
4. Selecteer **op** de pagina Uw DNS beheren het tabblad **Geavanceerd DNS.** 
    
5. Voeg de eerste van de zes CNAME-records toe.
    
    Ga naar het gebied **Advanced DNS**. In de vakken voor de nieuwe record in dit gebied kunt u vervolgens de waarden uit de volgende tabel typen of kopiëren en plakken. 
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
    |**Hostname**|**Type**|**Destination CNAME**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
   
    ![De waarden uit de tabel kopiëren en plakken](../../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. Kies **Toevoegen**.
    
    ![Selecteer Toevoegen](../../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. Voeg de overige vijf CNAME-records toe.
    
    Maak in de sectie **Geavanceerd DNS** een record met de waarden uit de volgende rij in de tabel en selecteer vervolgens opnieuw **Toevoegen** om die record te voltooien. 
    
    Herhaal deze procedure totdat u alle zes CNAME-records hebt gemaakt.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Een TXT-record voor SPF toevoegen om spam tegen te gaan
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> U kunt maximaal één TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals bezorgings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Office 365 te maken. In plaats daarvan voegt u de vereiste Office 365-waarden toe aan de huidige record, zodat u beschikt over  *één*  SPF-record waarin beide sets waarden zijn opgenomen. Hebt u voorbeelden nodig? Bekijk deze [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords). Voor het valideren van uw SPF-record kunt u een van deze [SPF-validatiehulpmiddelen](../setup/domains-faq.md) gebruiken. 
  
1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij 123-reg.co.uk via [deze koppeling](https://www.123-reg.co.uk/secure/cpanel/domain/overview). U wordt gevraagd u eerst aan te melden.
    
2. Selecteer op de pagina **Domain name overview** de naam van het domein dat u wilt bewerken. 
    
3. Kies in de vervolgkeuzelijst **Select action** de optie **DNS**. 
    
4. Selecteer **op** de pagina Uw DNS beheren het tabblad **Geavanceerd DNS.** 
    
5. Ga naar het gebied **Advanced DNS**. In de vakken voor de nieuwe record in dit gebied kunt u vervolgens de waarden uit de volgende tabel typen of kopiëren en plakken. 
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
    |**Hostname**|**Type**|**Destination TXT/SPF**|
    |:-----|:-----|:-----|
    |@  <br/> |TXT/SPF  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.           |
   
    ![Afbeelding van het te maken:Afbeelding van het te maken](../../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. Kies **Toevoegen**.
    
    ![Selecteer Toevoegen](../../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>De twee SRV-records toevoegen die voor Office 365 vereist zijn
<a name="BKMK_add_SRV"> </a>

1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij 123-reg.co.uk via [deze koppeling](https://www.123-reg.co.uk/secure/cpanel/domain/overview). U wordt gevraagd u eerst aan te melden.
    
2. Selecteer op de pagina **Domain name overview** de naam van het domein dat u wilt bewerken. 
    
3. Kies in de vervolgkeuzelijst **Select action** de optie **DNS**. 
    
4. Selecteer **op** de pagina Uw DNS beheren het tabblad **Geavanceerd DNS.** 
    
5. Voeg als volgt de eerste van de twee SRV-records toe:
    
    Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Advanced DNS** in de vakken voor de nieuwe record. 
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |Hostname|Type|Priority|TTL|Destination SRV|
    |_sip._tls|SRV|100|3600|1 443 sipdir.online.lync.com. **Deze waarde MOET eindigen op een punt (.)**<br> **Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.           |
    |_sipfederationtls._tcp|SRV|100|3600|1 5061 sipfed.online.lync.com. **Deze waarde MOET eindigen op een punt (.)** <br> **Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.           |
   
    ![De waarden uit de tabel kopiëren en plakken](../../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. Kies **Toevoegen**.
    
    ![Selecteer Toevoegen](../../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. De andere SRV-record toevoegen:
    
    Maak in de sectie **Geavanceerd DNS** een record met de waarden uit de tweede rij in de tabel en selecteer vervolgens opnieuw **Toevoegen** om die record te voltooien. 
    
> [!NOTE]
> Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
