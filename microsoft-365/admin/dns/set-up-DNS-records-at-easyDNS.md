---
title: DNS-records maken bij easyDNS voor Office 365
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
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services bij easyDNS voor Office 365.
ms.openlocfilehash: 9d48896de8f841863e25929a46b2f1d2e1b3ced2
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210550"
---
# <a name="create-dns-records-at-easydns-for-office-365"></a>DNS-records maken bij easyDNS voor Office 365

[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md) als u niet kunt vinden wat u zoekt. 
  
U moet alle volgende DNS-records op de website van uw registrar toevoegen om e-mail naar Office 365 te routeren, uw domein te gebruiken voor Teams en Skype voor Bedrijven, enzovoort.
  
LET OP: SRV Records zijn momenteel NIET beschikbaar onder alle easyDNS-servicepakketten. Mogelijk moet u upgraden naar een hoger serviceniveau met easyDNS om SRV-records toe te voegen die nodig zijn voor Office 365 Skype voor Bedrijven.
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a>Controleren of u eigenaar bent van het domein met een TXT-record

1. Ga [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) naar en log in met uw referenties. 
    
2. Selecteer dns onder de kop **alle domeinen.** **dns.**
    
3. Selecteer onder de kop **TXT-records** de bewerkingsknop (moersleutelpictogram). 
    
4. Voer de volgende records in de tekstvelden in:
    
    |**Host**|**Tekst**|
    |:-----|:-----|
    |@  <br/> |MS=msXXXXXXXX (Gebruik de waarde die u wordt verstrekt op de pagina Domeinen van het beheercentrum)  <br/> |
   
5. Selecteer **VOLGENDE**. 
    
6. Controleer of de record correct is en selecteer **BEVESTIGEN**. 
    
7. Wacht een paar minuten voordat u verdergaat, zodat de record die u zojuist hebt gemaakt, zich over het internet kan verspreiden en kan worden gedetecteerd door Office 365.
    
8. Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Office 365 en vraagt u of Office 365 naar de record wil zoeken.
    
9. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.
    
10. Kies op de pagina **Domeinen** de naam van het domein dat u verifieert. 
    
11. Selecteer **Op** de pagina Setup de optie **Installatie starten.**
    
12. Kies **Verifiëren** op de pagina **Domein verifiëren**. 
    
## <a name="add-an-mx-record-to-route-email-to-office-365"></a>Een MX-record toevoegen om e-mail naar Office 365 te routeren

1. Ga [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) naar en log in met uw referenties. 
    
2. Selecteer dns onder de kop **alle domeinen.** **dns.**
    
3. Selecteer onder de kop **MX-records** de knop bewerken (moersleutelpictogram). 
    
4. Voer de volgende records in de tekstvelden in:
    
    |**E-MAIL VOOR ZONE**|**MAILSERVER**|**PREF PREF**|
    |:-----|:-----|:-----|
    |@  <br/> |\<domeinsleutel\>.mail.protection.outlook.com (Uw \<domeinsleutelwaarde\> ophalen op de pagina Domeinen van het beheercentrum)  <br/> |0  <br/> |
   
2. Als u uw andere MX-records wilt opslaan voor back-updoeleinden, kopieert u deze ergens naar beneden. Verwijder alle andere MX-records voordat u verdergaat met het verwijderen van alle andere MX-records.
    
5. Selecteer **VOLGENDE**. 
    
6. Controleer of de record correct is en selecteer **BEVESTIGEN**. 
    
## <a name="add-the-required-cname-records"></a>De vereiste CNAME-records toevoegen

1. Ga [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) naar en log in met uw referenties. 
    
2. Selecteer dns onder de kop **alle domeinen.** **dns.**
    
3. Selecteer onder de kop **CNAME/Alias records** de knop bewerken (moersleutelpictogram). 
    
4. Voer de volgende records in de tekstvelden in:


    |**HOST**|**Adres (Moet eindigen met een ".")**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com.  <br/> |
    |sip  <br/> |sipdir.online.lync.com.  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> |
   
5. Selecteer **VOLGENDE**. 
    
6. Controleer of de record correct is en selecteer **BEVESTIGEN**. 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Een TXT-record voor SPF toevoegen om spam tegen te gaan

1. Ga [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) naar en log in met uw referenties. 
    
2. Selecteer dns onder de kop **alle domeinen.** **dns.**
    
3. Selecteer onder de kop **TXT-records** de bewerkingsknop (moersleutelpictogram). 
    
4. Voer de volgende records in de tekstvelden in:
    
    |**Host**|**Tekst**|
    |:-----|:-----|
    |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> |
   
5. Selecteer **VOLGENDE**. 
    
6. Controleer of de record correct is en selecteer **BEVESTIGEN**. 
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>De twee SRV-records toevoegen die voor Office 365 vereist zijn

LET OP: SRV Records zijn momenteel NIET beschikbaar onder het Domein Plus-serviceniveau van easyDNS. Mogelijk moet u upgraden naar een hoger serviceniveau met easyDNS om SRV-records toe te voegen 
  
1. Ga [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) naar en log in met uw referenties. 
    
2. Selecteer dns onder de kop **alle domeinen.** **dns.**
    
3. Selecteer onder de kop **SRV-records** de knop bewerken (moersleutelpictogram). 
    
4. Voer de volgende records in de tekstvelden in:
    
    |**SERVICE**|**Proto**|**HOST**|**Pri**|**WGT**|**PORT**|**TARGET(Moet eindigen met een ".")**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |TLS  <br/> |@  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com.  <br/> |1800  <br/> |
    |_sipfederationtls  <br/> |TCP  <br/> |@  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> |1800  <br/> |
   
5. Selecteer **VOLGENDE**. 
    
6. Controleer of de record correct is en selecteer **BEVESTIGEN**. 
    

