---
title: DNS-records bij Cloudflare maken voor Microsoft
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
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Lees hoe u uw domein verifieert en DNS-records instelt voor e-mail, Skype voor bedrijven online en andere services op Cloudflare voor Microsoft.
ms.openlocfilehash: 301ed156584d9a9a2b84b88db7d6969ade5b34a2
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646149"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a>DNS-records bij Cloudflare maken voor Microsoft

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Als Cloudflare uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.
  
Nadat u deze records bij Cloudflare hebt toegevoegd, is uw domein ingesteld voor gebruik met Microsoft 365-Services.
  
  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>De naamserverrecords (NS-records) van uw domein wijzigen
<a name="BKMK_Nameservers"> </a>

> [!IMPORTANT]
> U moet deze procedure uitvoeren bij de domeinregistrar waar u uw domein hebt gekocht en geregistreerd. 
  
Toen u zich voor Cloudflare registreerde, hebt u een domein toegevoegd met behulp van het Cloudflare **Setup**-proces. 
  
Het domein dat u hebt toegevoegd is aangeschaft bij Cloudflare of een afzonderlijke domeinregistratie. Als u DNS-records voor uw domein wilt controleren en maken in Microsoft 365, moet u eerst de naamservers van uw domeinregistratie wijzigen, zodat ze de naamservers van Cloudflare gebruiken.
  
Als u de naamservers van het domein zelf wilt wijzigen op de website van de domeinregistrar, voert u de volgende stappen uit:
  
1. Zoek het gedeelte op de website van de domeinregistrar waarop u de naamservers voor uw domein kunt wijzigen.
    
2. Maak twee naamserverrecords door de waarden in de volgende tabel te gebruiken of bewerk de bestaande naamserverrecords zodat ze overeenkomen met deze waarden:
    
    |||
    |:-----|:-----|
    |Eerste naamserver  <br/> |Gebruik de door Cloudflare opgegeven waarde voor de naamserver.  <br/> |
    |Tweede naamserver  <br/> |Gebruik de door Cloudflare opgegeven waarde voor de naamserver.  <br/> |
   
    > [!TIP]
    > U dient ten minste twee naamserver records te gebruiken. Als er andere naamservers worden weergegeven, moet u deze verwijderen. 
  
3. Sla uw wijzigingen op.
    
> [!NOTE]
> Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd. Vervolgens zijn uw Microsoft-e-mail en andere services allemaal ingesteld voor gebruik met uw domein. 
  
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie
<a name="BKMK_verify"> </a>

Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
1. Ga eerst naar uw domeinenpagina bij Cloudflare via [deze koppeling](https://www.cloudflare.com/a/login). U wordt gevraagd u eerst aan te melden.
  
2. Selecteer op de **Start** pagina het domein dat u wilt bijwerken. 
  
3. Selecteer op de pagina **Overview** voor uw domein de optie **DNS**.

  
4. Klik op de pagina **DNS-beheer** op **record toevoegen**en selecteer vervolgens de waarden uit de volgende tabel. 
    
    |**Type**|**Name**|**Automatic TTL**|**Content**|
    |:-----|:-----|:-----|:----|
    |TXT  <br/> |@  <br/> |30 minutes  <br/> |MS=ms *XXXXXXXX*  <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. Kies **Opslaan**.
  
  
9. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
Nu u de record hebt toegevoegd aan de site van uw domeinregistratie, gaat u terug naar Microsoft en gaat u naar de record.
  
Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.
  
1. Ga in het Microsoft-beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.

    
2. Kies op de pagina **Domeinen** de naam van het domein dat u verifieert. 
    
    
  
3. Kies **Start setup** op de pagina **Setup**.
    
    
  
4. Kies **Verifiëren** op de pagina **Domein verifiëren**.
    
    
  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden
<a name="BKMK_add_MX"> </a>

1. Ga eerst naar uw domeinenpagina bij Cloudflare via [deze koppeling](https://www.cloudflare.com/a/login). U wordt gevraagd u eerst aan te melden.
  
2. Selecteer op de **Start** pagina het domein dat u wilt bijwerken. 
  
3. Selecteer op de pagina **Overview** voor uw domein de optie **DNS**.

  
4. Klik op de pagina **DNS-beheer** op **record toevoegen**en selecteer vervolgens de waarden uit de volgende tabel. 
    
    |**Type**|**Name**|**Mail server**|**Priority**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX  <br/> |@  <br/> |*\<domain-key\>*  .mail.protection.outlook.com  <br/> **Opmerking:** Ga  *\<domain-key\>*  naar uw Microsoft 365-account.   [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md) |1  <br/> Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit.    <br/>|30 minutes  <br/> |
   

  
5. Kies **Opslaan**.
  
9. Als er andere MX-records zijn vermeld in de sectie **MX Records**, verwijdert u ze door het pictogram **Delete (X)** te selecteren. 
  
10. Selecteer in het bevestigingsvenster de optie **verwijderen** om uw wijzigingen te bevestigen. 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>De zes CNAME-records toevoegen die vereist zijn voor Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Ga eerst naar uw domeinenpagina bij Cloudflare via [deze koppeling](https://www.cloudflare.com/a/login). U wordt gevraagd u eerst aan te melden.
    
  
2. Selecteer op de **Start** pagina het domein dat u wilt bijwerken. 
  
3. Selecteer op de pagina **Overview** voor uw domein de optie **DNS**.

  
4. Voeg de eerste van de vijf CNAME-records toe.
    
    Klik op de pagina **DNS-beheer** op **record toevoegen**en selecteer vervolgens de waarden uit de volgende tabel.
    
    
    |**Type**|**Naam**|**Doel**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |30 minutes  <br/> |
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |30 minutes  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |30 minutes  <br/> |
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |30 minutes  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |30 minutes  <br/> |
    |CNAME  <br/> |msoid  <br/> |clientconfig.microsoftonline-p.net  <br/> |30 minutes  <br/> |
    
  
5. Selecteer het pictogram van het **DNS-verkeer** (oranje wolk) om de Cloudflare-servers over te slaan.
  
6. Kies **Opslaan**.
  
7. Voeg als volgt de andere vijf CNAME-records toe:

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Een TXT-record voor SPF toevoegen om spam tegen te gaan
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Microsoft 365 te maken. In plaats daarvan voegt u de vereiste Microsoft 365-waarden toe aan de huidige record, zodat u beschikt over  *één*  SPF-record waarin beide sets waarden zijn opgenomen. 
  
1. Ga eerst naar uw domeinenpagina bij Cloudflare via [deze koppeling](https://www.cloudflare.com/a/login). U wordt gevraagd u eerst aan te melden.
    
  
2. Selecteer op de **Start** pagina het domein dat u wilt bijwerken. 
  
3. Selecteer op de pagina **Overview** voor uw domein de optie **DNS**.

  
4. Klik op de pagina **DNS-beheer** op **record toevoegen**en selecteer vervolgens de waarden uit de volgende tabel.  
    
    |**Type**|**Name**|**TTL**|**Content**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |@  <br/> |30 minutes  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.   |

 
5. Kies **Opslaan**.
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>De twee SRV-records toevoegen die zijn vereist voor Microsoft
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> Houd er rekening mee dat Cloudflare verantwoordelijk is voor het beschikbaar stellen van deze functionaliteit. In het geval van verschillen tussen de onderstaande stappen en de huidige Cloudflare-GUI (Graphical User Interface), kunt u de [Cloudflare-Community](https://community.cloudflare.com/)inzetten. 

1. Ga eerst naar uw domeinenpagina bij Cloudflare via [deze koppeling](https://www.cloudflare.com/a/login). U wordt gevraagd u eerst aan te melden.
      
2. Selecteer op de **Start** pagina het domein dat u wilt bijwerken. 
  
3. Selecteer op de pagina **Overview** voor uw domein de optie **DNS**.
  
4. Voeg de eerste van de twee SRV-records toe.

    Klik op de pagina **DNS-beheer** op **record toevoegen**en selecteer vervolgens de waarden uit de eerste rij van de volgende tabel.
        
    |**Type**|**Service**|**Protocol**|**Naam**|**TTL**|**Prioriteit**|**Gewicht**|**Poort**|**Doel**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV|_sip |TLS |Gebruik uw *Domain_Name*; bijvoorbeeld: contoso.com  |30 minutes | 100|1 |443 |sipfed.online.lync.com  |
    |SRV|_sipfederationtls | TCP|Gebruik uw *Domain_Name*; bijvoorbeeld: contoso.com   |30 minutes |100 |1 |5061 | sipfed.online.lync.com |

  
5. Kies **Opslaan**.

  
6. Als u de andere SRV-record wilt toevoegen, kiest u de waarden uit de tweede rij van de tabel. 

    
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
