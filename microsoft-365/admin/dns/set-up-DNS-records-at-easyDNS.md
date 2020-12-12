---
title: DNS-records bij easyDNS maken voor Microsoft
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
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: Lees hoe u uw domein verifieert en DNS-records instelt voor e-mail, Skype voor bedrijven online en andere services op easyDNS voor Microsoft.
ms.openlocfilehash: a971a722f071ef5df9ce0fba387cfacfeb409f5b
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656817"
---
# <a name="create-dns-records-at-easydns-for-microsoft"></a>DNS-records bij easyDNS maken voor Microsoft

[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml) als u niet kunt vinden wat u zoekt. 
  
Voor het routeren van e-mail naar Microsoft moet u alle volgende DNS-records toevoegen op de website van uw bewaarder, uw domein gebruiken voor teams en Skype voor bedrijven, enzovoort.
  
Opmerking: SRV-records zijn momenteel niet beschikbaar onder alle easyDNS-servicepakketten. Mogelijk moet u upgraden naar een hoger serviceniveau met easyDNS om SRV-records toe te voegen die vereist zijn voor Skype voor bedrijven.
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a>Controleren of u de eigenaar bent van het domein met een TXT-record

1. Ga naar [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) en meld u aan met uw referenties. 
    
2. Selecteer DNS onder de kop **all domains** **.**
    
3. Selecteer onder de kop **TXT-records** de knop bewerken (gereedschap pictogram). 
    
4. Voer de volgende records in de tekstvelden in:
    
    |**Host**|**Tekst**|
    |:-----|:-----|
    |@  <br/> |MS = msXXXXXXXX (gebruik de waarde die u hebt opgegeven op de pagina domeinen in het Beheercentrum).  <br/> |
   
5. Selecteer **volgende**. 
    
6. Controleer of de record klopt en selecteer vervolgens **bevestigen**. 
    
7. Wacht een paar minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden gedetecteerd en door Microsoft wordt gedetecteerd.
    
8. Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.
    
9. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.
    
10. Kies op de pagina **Domeinen** de naam van het domein dat u verifieert. 
    
11. Selecteer op de pagina **Setup** de optie **Setup starten.**
    
12. Kies **Verifiëren** op de pagina **Domein verifiëren**. 
    
## <a name="add-an-mx-record-to-route-email-to-microsoft"></a>Een MX-record toevoegen om e-mail rond Microsoft te routeren

1. Ga naar [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) en meld u aan met uw referenties. 
    
2. Selecteer DNS onder de kop **all domains** **.**
    
3. Selecteer onder de kop **MX-records** de knop bewerken (gereedschap pictogram). 
    
4. Voer de volgende records in de tekstvelden in:
    
    |**E-MAIL VOOR ZONE**|**E-MAIL SERVER**|**PREF**|
    |:-----|:-----|:-----|
    |@  <br/> |\<domain-key\>. mail.protection.outlook.com (de \<domain-key\> waarde van de pagina Domains voor het Beheercentrum kopen)  <br/> |0  <br/> |
   
2. Als u uw andere MX-records wilt opslaan voor reservekopieën, kopieert u deze naar een willekeurige plaats. Verwijder alle andere MX-records hier voordat u verdergaat.
    
5. Selecteer **volgende**. 
    
6. Controleer of de record klopt en selecteer vervolgens **bevestigen**. 
    
## <a name="add-the-required-cname-records"></a>De vereiste CNAME-records toevoegen

1. Ga naar [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) en meld u aan met uw referenties. 
    
2. Selecteer DNS onder de kop **all domains** **.**
    
3. Selecteer onder de kop **CNAME/alias records** de knop bewerken (gereedschap pictogram). 
    
4. Voer de volgende records in de tekstvelden in:


    |**HOST**|**Adres (moet eindigen op een '. ')**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com.  <br/> |
    |sip  <br/> |sipdir.online.lync.com.  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> |
   
5. Selecteer **volgende**. 
    
6. Controleer of de record klopt en selecteer vervolgens **bevestigen**. 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Een TXT-record voor SPF toevoegen om spam tegen te gaan

1. Ga naar [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) en meld u aan met uw referenties. 
    
2. Selecteer DNS onder de kop **all domains** **.**
    
3. Selecteer onder de kop **TXT-records** de knop bewerken (gereedschap pictogram). 
    
4. Voer de volgende records in de tekstvelden in:
    
    |**Host**|**Tekst**|
    |:-----|:-----|
    |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> |
   
5. Selecteer **volgende**. 
    
6. Controleer of de record klopt en selecteer vervolgens **bevestigen**. 
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>De twee SRV-records toevoegen die zijn vereist voor Microsoft

Opmerking: SRV-records zijn momenteel niet beschikbaar onder easyDNS ' domein plus serviceniveau. Mogelijk moet u een upgrade uitvoeren naar een hoger serviceniveau met easyDNS om SRV-records toe te voegen 
  
1. Ga naar [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) en meld u aan met uw referenties. 
    
2. Selecteer DNS onder de kop **all domains** **.**
    
3. Selecteer onder de kop **SRV records** de knop bewerken (gereedschap pictogram). 
    
4. Voer de volgende records in de tekstvelden in:
    
    |**SERVICE**|**Protocol**|**HOST**|**PRIORITEIT**|**WGT**|**PORT**|**DOEL (moet eindigen op '. ')**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |TLS  <br/> |@  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com.  <br/> |1800  <br/> |
    |_sipfederationtls  <br/> |TCP  <br/> |@  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> |1800  <br/> |
   
5. Selecteer **volgende**. 
    
6. Controleer of de record klopt en selecteer vervolgens **bevestigen**. 
    

