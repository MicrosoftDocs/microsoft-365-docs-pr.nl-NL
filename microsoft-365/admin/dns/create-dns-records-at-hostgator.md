---
title: DNS-records bij Hostgator maken voor Microsoft
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
ms.assetid: 5f0c840e-4140-4571-88ed-cf235ff142d6
description: Lees hoe u uw domein verifieert en DNS-records instelt voor e-mail, Skype voor bedrijven online en andere services op Hostgator voor Microsoft.
ms.openlocfilehash: f8cfc417a7ff9821fd40b33c8dfe9932dd454d18
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645993"
---
# <a name="create-dns-records-at-hostgator-for-microsoft"></a>DNS-records bij Hostgator maken voor Microsoft

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Als Hostgator uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.
  
> [!IMPORTANT]
> U moet de eerste procedurebelow uitvoeren, [uw domein naar uw hosting account laten verwijzen](#point-your-domain-to-your-hosting-account)voordat u de DNS-records toevoegt met behulp van een van de overige procedures in dit artikel. 

Wanneer u alle wijzigingen hebt aangebracht op Hostgator, wordt uw domein ingesteld voor gebruik met Microsoft-services.
  

  
> [!NOTE]
> Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="point-your-domain-to-your-hosting-account"></a>Uw domein naar uw hostingaccount laten verwijzen
<a name="BKMK_PointDomain"> </a>

> [!IMPORTANT]
> Voer eerst deze procedure uit voordat u een van de overige procedures in dit artikel uitvoert. 
  
Volg deze stappen om uw domein en hostingaccounts te koppelen.
  
1. Ga eerst naar uw pagina voor domeinbeheer bij Hostgator via [deze koppeling](https://portal.hostgator.com/). U wordt gevraagd u aan te melden.
    
2. Selecteer **domeinen** aan de linkerkant.
  
3. Selecteer op de pagina **domeinen beheren** het domein dat u wilt bijwerken. 
  
4. Selecteer in het pop-outmenu aan de linkerkant de optie **name servers**.
  
5. Op de pagina **name servers** voor uw domein, in de vervolgkeuzelijst **dit domein automatisch naar de** vervolgkeuzelijst van mijn host-account, kiest u het hosting account dat is gekoppeld aan uw domein. 
  
6. Selecteer **Save name servers**.
    
  
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie
<a name="BKMK_verify"> </a>

> [!IMPORTANT]
> Voer voordat u deze procedure uitvoert eerst de procedure uit in het eerste gedeelte van dit artikel: [Uw domein naar uw hostingaccount laten verwijzen](#point-your-domain-to-your-hosting-account). 
  
Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
1. Als u wilt beginnen, gaat u naar de pagina cPanel bij Hostgator. U wordt gevraagd u eerst aan te melden.
    
    (Aan elk gehost account bij Hostgator is een uniek cPanel-adres toegewezen. Het adres van uw cPanel ziet er ongeveer als volgt uit: https://YourSiteAddress:secure-port-number nummer-beveiligde-poort. De registratie-e-mail die u hebt ontvangen van Hostgator, geeft dit adres aan en u kunt ook een koppeling voor cPanel **op de beschikbare pagina** weergeven.)
    
    > [!IMPORTANT]
    > Als u cPanel aan uw domein wilt koppelen, hebt u een hostingaccount bij Hostgator nodig. Als u aan de slag wilt met Microsoft, kunt u een hosting account kopen bij Hostgator of [uw naamservers delegeren naar Microsoft](change-nameservers-at-hostgator.md). 
  
2. Selecteer op de pagina **Control Panel** , in het gebied **Domains** , de optie **Advanced zone editor**.
    
3. Typ of kopieer en plak in het gebied add a record in de vakken voor de nieuwe record de waarden uit de volgende tabel op de pagina **Advanced zone editor** in het gebied **add a record** in de vakken voor de nieuwe record. 
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Name** <br/> |**TTL** <br/> |**Type** <br/> |**TXT Data** <br/> |
    |Gebruik uw  *Domain_Name*. (bijvoorbeeld fourthcoffee.com)  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |1  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel. [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |
   
4. Selecteer **Record toevoegen**.
    
5. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.
  
Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.
  
1. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.
    
2. Kies op de pagina **Domeinen** de naam van het domein dat u verifieert. 
    
3. Kies **Start setup** op de pagina **Setup**.
    
4. Kies **Verifiëren** op de pagina **Domein verifiëren**.
    
> [!NOTE]
> Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden
<a name="BKMK_add_MX"> </a>

> [!IMPORTANT]
> Voer voordat u deze procedure uitvoert eerst de procedure uit in het eerste gedeelte van dit artikel: [Uw domein naar uw hostingaccount laten verwijzen](#point-your-domain-to-your-hosting-account). 
  
1. Als u wilt beginnen, gaat u naar de pagina cPanel bij Hostgator. U wordt gevraagd u eerst aan te melden.
    
    (Aan elk gehost account bij Hostgator is een uniek cPanel-adres toegewezen. Het adres van uw cPanel ziet er ongeveer als volgt uit: https://YourSiteAddress:secure-port-number nummer-beveiligde-poort. De registratie-e-mail die u hebt ontvangen van Hostgator, geeft dit adres aan en u kunt ook een koppeling voor cPanel **op de beschikbare pagina** weergeven.)
    
    > [!IMPORTANT]
    > Als u cPanel aan uw domein wilt koppelen, hebt u een hostingaccount bij Hostgator nodig. Als u aan de slag wilt met Microsoft, kunt u een hosting account kopen bij Hostgator of [uw naamservers delegeren naar Microsoft](change-nameservers-at-hostgator.md). 
  
2. Selecteer op de pagina **Control Panel** in het gebied **mail** de optie **MX Entry**.
    
 
3. Selecteer **Remote Mail Exchanger** in het gebied **Email Routing**.

4. Selecteer **Wijzigen**.
  
5. Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **add a new record** in de vakken voor de nieuwe record. 
    
    |**Priority**|**Destination**|
    |:-----|:-----|
    |0  <br/> Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit. <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **Opmerking:** Haal uw \< *domain-key*  \> uit uw Microsoft-account.  [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |
  
6. Selecteer **add new record**.
   
 
7. Als er andere MX-records in de sectie **MX Records** staan, verwijdert u elke record. 

    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>De zes CNAME-records toevoegen die vereist zijn voor Microsoft
<a name="BKMK_add_CNAME"> </a>

> [!IMPORTANT]
> Voer voordat u deze procedure uitvoert eerst de procedure uit in het eerste gedeelte van dit artikel: [Uw domein naar uw hostingaccount laten verwijzen](#point-your-domain-to-your-hosting-account). 
  
1. Als u wilt beginnen, gaat u naar de pagina cPanel bij Hostgator. U wordt gevraagd u eerst aan te melden.
    
    (Aan elk gehost account bij Hostgator is een uniek cPanel-adres toegewezen. Het adres van uw cPanel ziet er ongeveer als volgt uit: https://YourSiteAddress:secure-port-number nummer-beveiligde-poort. De registratie-e-mail die u hebt ontvangen van Hostgator, geeft dit adres aan en u kunt ook een koppeling voor cPanel **op de beschikbare pagina** weergeven.)
    
    > [!IMPORTANT]
    > Als u cPanel aan uw domein wilt koppelen, hebt u een hostingaccount bij Hostgator nodig. Als u aan de slag wilt met Microsoft, kunt u een hosting account kopen bij Hostgator of [uw naamservers delegeren naar Microsoft](change-nameservers-at-hostgator.md). 
  
2. Selecteer op de pagina **Control Panel** , in het gebied **Domains** , de optie **Advanced zone editor**.
    
3. Voeg de eerste van de zes CNAME-records toe.
    
    Typ of kopieer en plak in het gebied **add a record** in de vakken voor de nieuwe record de waarden uit de eerste rij van de volgende tabel in de vakken voor de nieuwe record op de pagina **Advanced zone editor** . 
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
    |**Name**|**TTL**|**Type**|**CNAME**|
    |:-----|:-----|:-----|:-----|
    |autodiscover. *Domain_Name*. (bijvoorbeeld autodiscover.fourthcoffee.com.)  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |3600  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip. *Domain_Name*. (bijvoorbeeld sip.fourthcoffee.com.)  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |3600  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover. *Domain_Name*. (bijvoorbeeld lyncdiscover.fourthcoffee.com.)  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |3600  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration. *Domain_Name*. (bijvoorbeeld enterpriseregistration.fourthcoffee.com).  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |3600  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment. *Domain_Name*. (bijvoorbeeld enterpriseregistration.fourthcoffee.com).  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |3600  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |

  
4. Selecteer **Record toevoegen**.

5. Voeg als volgt de andere vijf CNAME-records toe:
    
    Maak in de sectie **add a record** een record met behulp van de waarden uit de volgende rij van de tabel en selecteer vervolgens opnieuw **add record** om deze record te voltooien. 
    
    Herhaal deze procedure totdat u alle zes CNAME-records hebt gemaakt.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Een TXT-record voor SPF toevoegen om spam tegen te gaan
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft. In plaats hiervan voegt u de vereiste Microsoft-waarden toe aan de huidige record, zodat u beschikt over één SPF-record waarin beide sets waarden zijn opgenomen. Hebt u voorbeelden nodig? Bekijk deze [Externe Domain Name System-records voor Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records#bkmk_spfrecords). Voor het valideren van uw SPF-record, kunt u een van deze [SPF-validatiehulpmiddelen](../setup/domains-faq.md) gebruiken. 
  
> [!IMPORTANT]
> Voer voordat u deze procedure uitvoert eerst de procedure uit in het eerste gedeelte van dit artikel: [Uw domein naar uw hostingaccount laten verwijzen](#point-your-domain-to-your-hosting-account). 
  
1. Als u wilt beginnen, gaat u naar de pagina cPanel bij Hostgator. U wordt gevraagd u eerst aan te melden.
    
    (Aan elk gehost account bij Hostgator is een uniek cPanel-adres toegewezen. Het adres van uw cPanel ziet er ongeveer als volgt uit: https://YourSiteAddress:secure-port-number nummer-beveiligde-poort. De registratie-e-mail die u hebt ontvangen van Hostgator, geeft dit adres aan en u kunt ook een koppeling voor cPanel **op de beschikbare pagina** weergeven.)
    
    > [!IMPORTANT]
    > Als u cPanel aan uw domein wilt koppelen, hebt u een hostingaccount bij Hostgator nodig. Als u aan de slag wilt met Microsoft, kunt u een hosting account kopen bij Hostgator of [uw naamservers delegeren naar Microsoft](change-nameservers-at-hostgator.md). 
  
2. Selecteer op de pagina **Control Panel** , in het gebied **Domains** , de optie **Advanced zone editor**.
    
3. Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add a Record** in de vakken voor de nieuwe record op de pagina **Advanced DNS Zone Editor**. 
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
    |**Name**|**TTL**|**Type**|**TXT Data**|
    |:-----|:-----|:-----|:-----|
    |Gebruik uw  *Domain_Name*. (bijvoorbeeld fourthcoffee.com)  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |3600  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.           |
  
4. Selecteer **Record toevoegen**.
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>De twee SRV-records toevoegen die zijn vereist voor Microsoft
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> Voer voordat u deze procedure uitvoert eerst de procedure uit in het eerste gedeelte van dit artikel: [Uw domein naar uw hostingaccount laten verwijzen](#point-your-domain-to-your-hosting-account). 
  
1. Als u wilt beginnen, gaat u naar de pagina cPanel bij Hostgator. U wordt gevraagd u eerst aan te melden.
    
    (Aan elk gehost account bij Hostgator is een uniek cPanel-adres toegewezen. Het adres van uw cPanel ziet er ongeveer als volgt uit: https://YourSiteAddress:secure-port-number nummer-beveiligde-poort. De registratie-e-mail die u hebt ontvangen van Hostgator, geeft dit adres aan en u kunt ook een koppeling voor cPanel **op de beschikbare pagina** weergeven.)
    
    > [!IMPORTANT]
    > Als u cPanel aan uw domein wilt koppelen, hebt u een hostingaccount bij Hostgator nodig. Als u aan de slag wilt met Microsoft, kunt u een hosting account kopen bij Hostgator of [uw naamservers delegeren naar Microsoft](change-nameservers-at-hostgator.md). 
  
2. Selecteer op de pagina **Control Panel** , in het gebied **Domains** , de optie **Advanced zone editor**.

    
3. Voeg de eerste van de twee SRV-records toe.
    
    Typ of kopieer en plak de waarden uit de eerste rij in de volgende tabel in de vakken voor de nieuwe record in het gebied **Add a Record** op de pagina **Advanced DNS Zone Editor**. 
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
    |**Name**|**TTL**|**Type**|**Prioriteit**|**Gewicht**|**Poort**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip _sip._tls. *Domain_Name*. (bijvoorbeeld _sip. _tls. fourthcoffee. com.)  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |3600  <br/> |SRV  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls _sipfederationtls._tcp. *Domain_Name*. (bijvoorbeeld _sipfederationtls. _tcp. fourthcoffee. com.)  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |3600  <br/> |SRV  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   

4. Selecteer **Record toevoegen**.

  
5. Voeg de andere SRV-record toe.
    
    Maak in de sectie **add a record** een record met behulp van de waarden uit de volgende rij van de tabel en selecteer vervolgens opnieuw **add record** om deze record te voltooien. 
    
> [!NOTE]
> Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md). 
