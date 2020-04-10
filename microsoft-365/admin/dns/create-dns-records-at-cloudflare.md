---
title: DNS-records maken bij Cloudflare voor Office 365
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
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services in Cloudflare voor Office 365.
ms.openlocfilehash: 8d64824f880bab9e6691ebf47c9508c555562fe4
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211809"
---
# <a name="create-dns-records-at-cloudflare-for-office-365"></a>DNS-records maken bij Cloudflare voor Office 365

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Als Cloudflare uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.
  
Nadat u deze records bij Cloudflare hebt toegevoegd, is uw domein ingesteld voor gebruik met Office 365-services.
  
Zie [Een openbare website gebruiken met Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx) voor informatie over webhosting en DNS voor websites met Office 365.
  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>De naamserverrecords (NS-records) van uw domein wijzigen
<a name="BKMK_Nameservers"> </a>

> [!IMPORTANT]
> U moet deze procedure uitvoeren bij de domeinregistrar waar u uw domein hebt gekocht en geregistreerd. 
  
Toen u zich voor Cloudflare registreerde, hebt u een domein toegevoegd met behulp van het Cloudflare **Setup**-proces. 
  
Het door u toegevoegde domein was aangeschaft bij een afzonderlijke domeinregistrar; Cloudflare biedt geen domeinregistratieservices. Als u DNS-records voor uw domein in Office 365 wilt verifiëren en maken, moet u eerst de naamservers bij uw domeinregistrar wijzigen zodat ze de naamservers van Cloudflare kunnen gebruiken.
  
Als u de naamservers van het domein zelf wilt wijzigen op de website van de domeinregistrar, voert u de volgende stappen uit:
  
1. Zoek het gedeelte op de website van de domeinregistrar waarop u de naamservers voor uw domein kunt wijzigen.
    
2. Maak twee naamserverrecords door de waarden in de volgende tabel te gebruiken of bewerk de bestaande naamserverrecords zodat ze overeenkomen met deze waarden:
    
    |||
    |:-----|:-----|
    |Eerste naamserver  <br/> |Gebruik de door Cloudflare opgegeven waarde voor de naamserver.  <br/> |
    |Tweede naamserver  <br/> |Gebruik de door Cloudflare opgegeven waarde voor de naamserver.  <br/> |
   
    > [!TIP]
    > U moet ten minste twee naamserverrecords gebruiken. Als er andere naamservers worden vermeld, moet u deze verwijderen. 
  
3. Sla uw wijzigingen op.
    
> [!NOTE]
> Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd. Vervolgens worden uw e-mail voor Office 365 en andere services ingesteld voor gebruik met uw domein. 
  
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie
<a name="BKMK_verify"> </a>

Voordat u uw domein met Office 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Office 365 bewezen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
1. Ga eerst naar uw domeinenpagina bij Cloudflare via [deze koppeling](https://www.cloudflare.com/a/login). U wordt gevraagd u eerst aan te melden.
  
2. Selecteer **op** de startpagina het domein dat u wilt bijwerken. 
  
3. Selecteer **DNS**op de pagina **Overzicht** voor uw domein.

  
4. Klik op de pagina **DNS-beheer** op **Record toevoegen**en selecteer de waarden in de volgende tabel. 
    
    |**Type**|**Name**|**Automatic TTL**|**Content**|
    |:-----|:-----|:-----|:----|
    |TXT  <br/> |@  <br/> |30 minutes  <br/> |MS=ms *XXXXXXXX*  <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. Kies **Opslaan**.
  
  
9. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Office 365 en vraagt u of Office 365 naar de record wil zoeken.
  
Wanneer in Office 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.
  
1. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.

    
2. Kies op de pagina **Domeinen** de naam van het domein dat u verifieert. 
    
    
  
3. Kies **Start setup** op de pagina **Setup**.
    
    
  
4. Kies **Verifiëren** op de pagina **Domein verifiëren**.
    
    
  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Een MX-record toevoegen zodat e-mail voor uw domein bij Office 365 terechtkomt
<a name="BKMK_add_MX"> </a>

1. Ga eerst naar uw domeinenpagina bij Cloudflare via [deze koppeling](https://www.cloudflare.com/a/login). U wordt gevraagd u eerst aan te melden.
  
2. Selecteer **op** de startpagina het domein dat u wilt bijwerken. 
  
3. Selecteer **DNS**op de pagina **Overzicht** voor uw domein.

  
4. Klik op de pagina **DNS-beheer** op **Record toevoegen**en selecteer de waarden in de volgende tabel. 
    
    |**Type**|**Naam**|**Mail server**|**Priority**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX  <br/> |@  <br/> |*\<domeinsleutel\>*  .mail.protection.outlook.com  <br/> **Let op:** Haal uw * \<domeinsleutel\> * op uit uw Office 365-account.   [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md) |1  <br/> Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.    <br/>|30 minutes  <br/> |
   

  
5. Kies **Opslaan**.
  
9. Als er andere MX-records zijn vermeld in de sectie **MX Records**, verwijdert u ze door het pictogram **Delete (X)** te selecteren. 
  
10. Selecteer **Verwijderen in** het bevestigingsdialoogvenster om uw wijzigingen te bevestigen. 

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>De zes CNAME-records toevoegen die vereist zijn voor Office 365
<a name="BKMK_add_CNAME"> </a>

1. Ga eerst naar uw domeinenpagina bij Cloudflare via [deze koppeling](https://www.cloudflare.com/a/login). U wordt gevraagd u eerst aan te melden.
    
  
2. Selecteer **op** de startpagina het domein dat u wilt bijwerken. 
  
3. Selecteer **DNS**op de pagina **Overzicht** voor uw domein.

  
4. Voeg de eerste van de vijf CNAME-records toe.
    
    Klik op de pagina **DNS-beheer** op **Record toevoegen**en selecteer de waarden in de volgende tabel.
    
    
    |**Type**|**Naam**|**Doel**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |30 minutes  <br/> |
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |30 minutes  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |30 minutes  <br/> |
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |30 minutes  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |30 minutes  <br/> |
    |CNAME  <br/> |msoid  <br/> |clientconfig.microsoftonline-p.net  <br/> |30 minutes  <br/> |
    
  
5. Selecteer het **pictogram DNS-verkeer** (oranje wolk) om de Cloudflare-servers te omzeilen.
  
6. Kies **Opslaan**.
  
7. Voeg als volgt de andere vijf CNAME-records toe:

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Een TXT-record voor SPF toevoegen om spam tegen te gaan
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Office 365 te maken. In plaats daarvan voegt u de vereiste Office 365-waarden toe aan de huidige record, zodat u beschikt over  *één*  SPF-record waarin beide sets waarden zijn opgenomen. 
  
1. Ga eerst naar uw domeinenpagina bij Cloudflare via [deze koppeling](https://www.cloudflare.com/a/login). U wordt gevraagd u eerst aan te melden.
    
  
2. Selecteer **op** de startpagina het domein dat u wilt bijwerken. 
  
3. Selecteer **DNS**op de pagina **Overzicht** voor uw domein.

  
4. Klik op de pagina **DNS-beheer** op **Record toevoegen**en selecteer de waarden in de volgende tabel.  
    
    |**Type**|**Naam**|**TTL**|**Content**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |@  <br/> |30 minutes  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.   |

 
5. Kies **Opslaan**.
    

  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>De twee SRV-records toevoegen die voor Office 365 vereist zijn
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> Houd er rekening mee dat Cloudflare verantwoordelijk is voor het beschikbaar maken van deze functionaliteit. Als u discrepanties ziet tussen de onderstaande stappen en de huidige Cloudflare GUI(Grafische gebruikersinterface), u gebruikmaken van de [Cloudflare-community.](https://community.cloudflare.com/) 

1. Ga eerst naar uw domeinenpagina bij Cloudflare via [deze koppeling](https://www.cloudflare.com/a/login). U wordt gevraagd u eerst aan te melden.
      
2. Selecteer **op** de startpagina het domein dat u wilt bijwerken. 
  
3. Selecteer **DNS**op de pagina **Overzicht** voor uw domein.
  
4. Voeg de eerste van de twee SRV-records toe.

    Klik op de pagina **DNS-beheer** op **Record toevoegen**en selecteer de waarden uit de eerste rij van de volgende tabel.
        
    |**Type**|**Service**|**Protocol**|**Naam**|**TTL**|**Prioriteit**|**Gewicht**|**Poort**|**Doel**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV|_sip |TLS |Gebruik uw *domain_name*; contoso.com bijvoorbeeld  |30 minutes | 100|1 |443 |sipfed.online.lync.com  |
    |SRV|_sipfederationtls | TCP|Gebruik uw *domain_name*; contoso.com bijvoorbeeld   |30 minutes |100 |1 |5061 | sipfed.online.lync.com |

  
5. Kies **Opslaan**.

  
6. Voeg de andere SRV-record toe door de waarden uit de tweede rij van de tabel te kiezen. 

    
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
