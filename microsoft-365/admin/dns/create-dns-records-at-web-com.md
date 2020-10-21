---
title: DNS-records bij web.com maken voor Microsoft
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
description: Lees hoe u uw domein verifieert en DNS-records instelt voor e-mail, Skype voor bedrijven online en andere services op web.com voor Microsoft.
ms.openlocfilehash: 25df88e05e96e2394628bf89c8cc07af2d0eac1e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645753"
---
# <a name="create-dns-records-at-webcom-for-microsoft"></a>DNS-records bij web.com maken voor Microsoft

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Als web.com uw DNS-hosting provider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records in te stellen voor e-mail, Skype voor bedrijven online, enzovoort.
  
Nadat u deze records bij web.com hebt toegevoegd, is uw domein ingesteld voor gebruik met Microsoft-services.

  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>De naamserverrecords (NS-records) van uw domein wijzigen
<a name="BKMK_Nameservers"> </a>

> [!IMPORTANT]
> U moet deze procedure uitvoeren bij de domeinregistrar waar u uw domein hebt gekocht en geregistreerd. 
  
Toen u zich registreerde voor web.com, hebt u een domein toegevoegd door middel van het **installatie** proces van web.com. 
  
Als u DNS-records voor uw domein wilt controleren en maken in Microsoft, moet u eerst de naamservers van uw domeinregistratie wijzigen, zodat ze de naamservers van web. com gebruiken.
  
Als u de naamservers van het domein zelf wilt wijzigen op de website van de domeinregistrar, voert u de volgende stappen uit:
  
1. Zoek het gedeelte op de website van de domeinregistrar waarop u de naamservers voor uw domein kunt wijzigen.
    
2. Maak twee naamserverrecords door de waarden in de volgende tabel te gebruiken of bewerk de bestaande naamserverrecords zodat ze overeenkomen met deze waarden:
    
    |||
    |:-----|:-----|
    |Eerste naamserver  <br/> |Gebruik de naamserver-waarde van web.com.  <br/> |
    |Tweede naamserver  <br/> |Gebruik de naamserver-waarde van web.com.  <br/> |
   
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
  
1. Als u wilt beginnen, gaat u naar uw domeinen pagina bij web.com met behulp van [deze koppeling](https://checkout.web.com/manage-it/index.jsp). Meld u eerst aan.
  
2. Selecteer op de pagina **account beheer** de optie **mijn domeinnamen**. 
  
3. Selecteer onder * * beheren * mijn domein * * * de optie **Geavanceerde DNS-records bewerken**.

  
4. Klik op de pagina **Domain names** onder **Text (TXT records)** op **Edit TXT records**en selecteer vervolgens de waarden uit de volgende tabel. 
    
    |**Host**|**TTL**|**Tekst**|
    |:-----|:-----|:----|
    |@  <br/> |3600  <br/> |MS=ms *XXXXXXXX*  <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. Selecteer **Doorgaan**.
  
  
6. Wacht een paar minuten voordat u de nieuwe TXT-record verifieert, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
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

1. Als u wilt beginnen, gaat u naar uw domeinen pagina bij web.com met behulp van [deze koppeling](https://checkout.web.com/manage-it/index.jsp). Meld u eerst aan.
  
2. Selecteer op de pagina **account beheer** de optie **mijn domeinnamen**. 
  
3. Selecteer onder * * beheren * mijn domein * * * de optie **Geavanceerde DNS-records bewerken**.

4. Klik onder **e-mail servers (MX records)** op **Edit MX records**en selecteer vervolgens de waarden uit de volgende tabel. 
    
    |**Priority**|**TTL**|**Mail server**|
    |:-----|:-----|:-----|
    |1  <br/> Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit.    <br/> |3600  <br/> |*\<domain-key\>*  .mail.protection.outlook.com  <br/> **Opmerking:** Neem uw  *\<domain-key\>*  van uw Microsoft-account.   [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md) |
   

5. Kies **Opslaan**.
  
6. Als er andere MX-records worden vermeld in de sectie **MX records** , selecteert u het selectievakje naast de record onder **verwijderen**en selecteert u **Opslaan**. 
  
7. Selecteer in het bevestigingsvenster de optie **Save Changes**. 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>De zes CNAME-records toevoegen die vereist zijn voor Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Als u wilt beginnen, gaat u naar uw domeinen pagina bij web.com met behulp van [deze koppeling](https://checkout.web.com/manage-it/index.jsp). U wordt gevraagd u eerst aan te melden.
     
2. Selecteer op de pagina **account beheer** de optie **mijn domeinnamen**. 
  
3. Selecteer onder * * beheren * mijn domein * * * de optie **Geavanceerde DNS-records bewerken**.

4. Voeg de eerste van de zes CNAME-records toe.
    
    Klik onder **Host Aliases (CNAME records)** op **Edit CNAME records**en selecteer vervolgens de waarden uit de volgende tabel.
    
    
    |**Alias**|**TTL**|**Refers to Host Name**|**Andere host**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |3600  <br/> |@ (geen)  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |3600  <br/> |@ (geen)  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |3600  <br/> |@ (geen)  <br/> | webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |3600  <br/> |@ (geen)  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |3600  <br/> |@ (geen)  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
    |msoid  <br/> |3600  <br/> |@ (geen)  <br/> |clientconfig.microsoftonline-p.net  <br/> |
    
  
5. Selecteer **Doorgaan**.
  
6. Voeg als volgt de andere vijf CNAME-records toe:

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Een TXT-record voor SPF toevoegen om spam tegen te gaan
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft. In plaats daarvan voegt u de vereiste Microsoft-waarden toe aan de huidige record, zodat u  *één*  SPF-record hebt die beide sets met waarden bevat. 
  
1. Als u wilt beginnen, gaat u naar uw domeinen pagina bij web.com met behulp van [deze koppeling](https://checkout.web.com/manage-it/index.jsp). Meld u eerst aan.
    
  
2. Selecteer op de pagina **account beheer** de optie **mijn domeinnamen**. 
  
3. Selecteer onder * * beheren * mijn domein * * * de optie **Geavanceerde DNS-records bewerken**.

  
4. Klik op de pagina **Domain names** onder **Text (TXT records)** op **Edit TXT records**en selecteer vervolgens de waarden uit de volgende tabel.   
    
    |**Host**|**TTL**|**Tekst**|
    |:-----|:-----|:-----|
    |@  <br/> |3600  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.   |

 
5. Selecteer **Doorgaan**.

6. Selecteer **Wijzigingen opslaan**.
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>De twee SRV-records toevoegen die zijn vereist voor Microsoft
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> Houd er rekening mee dat web.com verantwoordelijk is voor het beschikbaar stellen van deze functionaliteit. In het geval van verschillen tussen de onderstaande stappen en de huidige web.com-GUI (Graphical User Interface), kunt u de [Web.com-community](https://community.web.com.com/)inzetten. 

1. Als u wilt beginnen, gaat u naar uw domeinen pagina bij web.com met behulp van [deze koppeling](https://checkout.web.com/manage-it/index.jsp). Meld u eerst aan.
      
2. Selecteer op de pagina **account beheer** de optie **mijn domeinnamen**. 
  
3. Selecteer onder * * beheren * mijn domein * * * de optie **Geavanceerde DNS-records bewerken**.
  
4. Voeg de eerste van de twee SRV-records toe.

    Klik onder **service (SRV records)** op **Edit SRV records**en selecteer vervolgens de waarden uit de volgende tabel. 
        
    |**Service**|**Protocol**|**TTL**|**Prioriteit**|**Gewicht**|**Poort**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip |_tls |3600 | 100|1 |443 |sipfed.online.lync.com  |
    |_sipfederationtls |_tcp |3600 |100 |1 |5061 | sipfed.online.lync.com |

  
5. Als u de andere SRV-record wilt toevoegen, kiest u de waarden uit de tweede rij van de tabel. 
  
6. Selecteer **Doorgaan**.

7. Selecteer **Wijzigingen opslaan**.

    
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
