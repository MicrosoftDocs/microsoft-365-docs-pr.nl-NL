---
title: DNS-records bij DNSMadeEasy maken voor Office 365
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
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services bij DNSMadeEasy voor Office 365.
ms.openlocfilehash: 29bdf78e3f9993267c5f0be3b107981bb9dd3fe3
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211797"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-office-365"></a>DNS-records bij DNSMadeEasy maken voor Office 365

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Als DNSMadeEasy uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online enzovoort in te stellen.
  
Nadat u deze records bij DNSMadeEasy hebt toegevoegd, is uw domein ingesteld voor gebruik met Office 365-services.
  
Zie [Een openbare website gebruiken met Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9) voor informatie over webhosting en DNS voor websites met Office 365.
  
> [!NOTE]
> Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie
<a name="BKMK_verify"> </a>

Voordat u uw domein met Office 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Office 365 bewezen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
> [!IMPORTANT]
> Voor DNSMadeEasy-accounts is het domein dat u hebt toegevoegd, gekocht bij een afzonderlijke domeinregistrar. DNSMadeEasy biedt geen domeinregistratieservices aan. Uw vermogen om in te loggen bij DNSMadeEasy en de DNS-record te maken is voldoende bewijs van eigendom. 
  
1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij DNSMadeEasy via [deze koppeling](https://cp.dnsmadeeasy.com/). U wordt gevraagd u eerst aan te melden.
    
2. Selecteer op de pagina **Beheerconsole** in het gebied **Onlangs bijgewerkte domeinen** het domein dat u wilt bijwerken. 
    
3. Selecteer op de pagina **Beheerde DNS** in het **+** gebied **TXT Records** het besturingselement ( Nieuw **toevoegen**).
    
    (Mogelijk moet u omlaag schuiven.)
    
4. Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add TXT Records** in de vakken voor de nieuwe record. 
    
    ||||
    |:-----|:-----|:-----|
    |**Naam** <br/> |**Waarde** <br/> |**TTL** <br/> |
    |(Laat dit veld leeg.)  <br/> |MS=ms *XXXXXXXX*  <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365. [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |1800  <br/> |
   
5. Selecteer **Verzenden**.
    
6. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
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

1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij DNSMadeEasy via [deze koppeling](https://cp.dnsmadeeasy.com/). U wordt gevraagd u eerst aan te melden.
    
2. Selecteer op de pagina **Beheerconsole** in het gebied **Onlangs bijgewerkte domeinen** het domein dat u wilt bijwerken. 
    
    Selecteer op de pagina **Beheerconsole** in het gebied **Onlangs bijgewerkte domeinen** het domein dat u wilt bijwerken. 
    
    ![Afbeelding van het voorkomen van DNSMadeEasy-Bp-1-2](../../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. Selecteer op de pagina **Beheerde DNS** in het gebied **MX Records** het **besturingselement (+)** **(Nieuw toevoegen).**
    
    (Mogelijk moet u omlaag schuiven.)
    
    ![Afbeelding van het te maken:DnsMadeEasy-BP-2-1](../../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add MX Records** in de vakken voor de nieuwe record. 
    
    (Mogelijk moet u omlaag schuiven.)
    
    |**Naam**|**Server**|**MX Level**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |(Laat dit veld leeg.)  <br/> | *\<domeinsleutel\>*  .mail.protection.outlook.com  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> **Opmerking**: Uw \<*domeinsleutel*\> kunt u ophalen uit uw Office 365-account. [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |10  <br/> Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.    <br/> |1800  <br/> |
   
    ![Afbeelding van het voorkomen van DNSMadeEasy-Bp-2-2](../../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. Selecteer **Verzenden**.
    
    ![Afbeelding van het te maken:DNSMadeEasy-BP-Afbeelding](../../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. Als er andere MX-records zijn vermeld in de sectie **MX Records**, verwijdert u deze door elk record te selecteren. 
    
    ![Afbeelding van het te maken:DNSMadeEasy-BP-Configureren-2-4-1](../../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. Wanneer alle records zijn geselecteerd, selecteert u **Geselecteerd verwijderen**.
    
    ![Afbeelding van het te maken:DNSMadeEasy-BP-Configureren-2-4-2](../../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. Selecteer **Verwijderen** om uw wijzigingen te bevestigen in het dialoogvenster **MX-records verwijderen.** 
    
    ![Afbeelding van het te maken:DNSMadeEasy-BP-Afbeelding](../../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a>De vijf CNAME-records toevoegen die nodig zijn voor Office 365
<a name="BKMK_add_CNAME"> </a>

1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij DNSMadeEasy via [deze koppeling](https://cp.dnsmadeeasy.com/). U wordt gevraagd u eerst aan te melden.
    
2. Selecteer op de pagina **Beheerconsole** in het gebied **Onlangs bijgewerkte domeinen** het domein dat u wilt bijwerken. 
    
3. Selecteer op de pagina **Beheerde DNS** in het gebied **CNAME Records** het besturingselement **(+)** **(Nieuw toevoegen).**
    
    (Mogelijk moet u omlaag schuiven.)
    
    ![Afbeelding van het te maken:DNSMadeEasy-BP-Afbeelding](../../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. Voeg de eerste van de vijf CNAME-records toe.
    
    Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in het gebied **Add CNAME Records** in de vakken voor de nieuwe record. 
    
    |**Name**|**Alias to**|**TTL**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |1800  <br/> |
    |sip  <br/> |sipdir.online.lync.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |1800  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |1800  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |1800  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |1800  <br/> |
   
    ![Afbeelding van het te maken:DNSMadeEasy-BP-Afbeelding](../../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. Selecteer **Verzenden**.
    
    ![Afbeelding van het te maken:DNSMadeEasy-BP-Afbeelding](../../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. Voeg elk van de andere vier CNAME-records toe.
    
    Selecteer in de sectie **CNAME Records** het **besturingselement (+)** **(Nieuw toevoegen),** een record maken met de waarden uit de volgende rij in de tabel en selecteer vervolgens opnieuw **Verzenden** om die record te voltooien. 
    
    Herhaal dit proces totdat u alle vijf CNAME-records hebt gemaakt.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Een TXT-record voor SPF toevoegen om spam tegen te gaan
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Office 365 te maken. In plaats daarvan voegt u de vereiste Office 365-waarden toe aan de huidige record, zodat u beschikt over  *één*  SPF-record waarin beide sets waarden zijn opgenomen. Hebt u voorbeelden nodig? Bekijk deze [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0). Als u uw SPF-record wilt valideren, u een van deze[SPF-validatietools](../setup/domains-faq.md)gebruiken. 
  
1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij DNSMadeEasy via [deze koppeling](https://cp.dnsmadeeasy.com/). U wordt gevraagd u eerst aan te melden.
    
2. Selecteer op de pagina **Beheerconsole** in het gebied **Onlangs bijgewerkte domeinen** het domein dat u wilt bijwerken. 
    
3. Selecteer op de pagina **Beheerde DNS** in het gebied **TXT Records** het **besturingselement (+)** **(Nieuw toevoegen).**
    
    (Mogelijk moet u omlaag schuiven.)
    
    ![Afbeelding van het te maken:Knopafbeelding-Afbeelding](../../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add TXT Records** in de vakken voor de nieuwe record. 
    
    |**Naam**|**Waarde**|**TTL**|
    |:-----|:-----|:-----|
    |(Laat dit veld leeg.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.           |1800  <br/> |
   
    ![Afbeelding van het te maken-de-afbeelding-4-2 van DNSMadeEasy-Bp](../../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. Selecteer **Verzenden**.
    
    ![Afbeelding van het te maken:DNSMadeEasy-BP-afbeelding](../../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>De twee SRV-records toevoegen die voor Office 365 vereist zijn
<a name="BKMK_add_SRV"> </a>

1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij DNSMadeEasy via [deze koppeling](https://cp.dnsmadeeasy.com/). U wordt gevraagd u eerst aan te melden.
    
2. Selecteer op de pagina **Beheerconsole** in het gebied **Onlangs bijgewerkte domeinen** het domein dat u wilt bijwerken. 
    
3. Selecteer op de pagina **Beheerde DNS** in het gebied **SRV Records** het **besturingselement (+)** **(Nieuw toevoegen).**
    
    (Mogelijk moet u omlaag schuiven)
    
    ![Afbeelding van het te maken:DnsMadeEasy-BP-Configureren-5-1](../../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. Voeg de eerste van de twee SRV-records toe.
    
    Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in het gebied **Add SRV Records** in de vakken voor de nieuwe record. 
    
    |**Name**|**Prioriteit**|**Gewicht**|**Poort**|**Host**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip._tls  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |1800  <br/> |
    |_sipfederationtls._tcp  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |1800  <br/> |
   
    ![Afbeelding van het te maken-Bp-5-2](../../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. Selecteer **Verzenden**.
    
    ![Afbeelding van het te maken-Bp-5-3](../../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. Voeg de andere SRV-record toe.
    
    Selecteer in de sectie **SRV Records** het **besturingselement (+)** **(Nieuw toevoegen),** een record maken met de waarden uit de volgende rij in de tabel en selecteer vervolgens opnieuw **Verzenden** om die record te voltooien. 
    
> [!NOTE]
> Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  

