---
title: DNS-records maken op web.com voor Microsoft
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services op web.com voor Microsoft.
ms.openlocfilehash: 2a9162c1ca6fc6a00e564e8f004768fac49bd3e3
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400302"
---
# <a name="create-dns-records-at-webcom-for-microsoft"></a>DNS-records maken op web.com voor Microsoft

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Als web.com uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records in te stellen voor e-mail, Skype voor Bedrijven Online, enzovoort.
  
Nadat u deze records op web.com hebt toegevoegd, wordt uw domein ingesteld voor gebruik met Microsoft-services.

  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>De naamserverrecords (NS-records) van uw domein wijzigen
<a name="BKMK_Nameservers"> </a>

> [!IMPORTANT]
> U moet deze procedure uitvoeren bij de domeinregistrar waar u uw domein hebt gekocht en geregistreerd. 
  
Wanneer u zich hebt aangemeld voor web.com, hebt u een domein toegevoegd met behulp van het **web.com-installatieproces.** 
  
Als u DNS-records voor uw domein in Microsoft wilt verifiëren en maken, moet u eerst de naamservers van uw domeinregistrar wijzigen, zodat ze de naamservers van web.com gebruiken.
  
Als u de naamservers van het domein zelf wilt wijzigen op de website van de domeinregistrar, voert u de volgende stappen uit:
  
1. Zoek het gedeelte op de website van de domeinregistrar waarop u de naamservers voor uw domein kunt wijzigen.
    
2. Maak twee naamserverrecords door de waarden in de volgende tabel te gebruiken of bewerk de bestaande naamserverrecords zodat ze overeenkomen met deze waarden:
    
    |||
    |:-----|:-----|
    |Eerste naamserver  <br/> |Gebruik de naamserverwaarde van web.com.  <br/> |
    |Tweede naamserver  <br/> |Gebruik de naamserverwaarde van web.com.  <br/> |
   
    > [!TIP]
    > U moet ten minste twee naamserverrecords gebruiken. Als er andere naamservers worden vermeld, moet u deze verwijderen. 
  
3. Sla uw wijzigingen op.
    
> [!NOTE]
> Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd. Vervolgens zijn uw Microsoft-e-mail en andere services helemaal klaar om met uw domein te werken. 
  
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie
<a name="BKMK_verify"> </a>

Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
1. Ga op web.com naar de pagina domeinen met [deze link](https://checkout.web.com/manage-it/index.jsp)om aan de slag te gaan. Log dan eerst in.
  
2. Selecteer op de pagina **Accountmanager** de optie **Mijn domeinnamen**. 
  
3. Selecteer onder **Mijn domein beheren***de optie **Geavanceerde DNS-records bewerken**.

  
4. Klik op de pagina **Domeinnamen** onder **Tekst (TXT Records)** op **TXT Records bewerken**en selecteer de waarden in de volgende tabel. 
    
    |**Host**|**TTL**|**Tekst**|
    |:-----|:-----|:----|
    |@  <br/> |3600  <br/> |MS=ms *XXXXXXXX*  <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. Selecteer **Doorgaan**.
  
  
6. Wacht een paar minuten voordat u uw nieuwe TXT-record verifieert, zodat de record die u zojuist hebt gemaakt, kan worden bijgewerkt via internet.
    
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

1. Ga op web.com naar de pagina domeinen met [deze link](https://checkout.web.com/manage-it/index.jsp)om aan de slag te gaan. Log dan eerst in.
  
2. Selecteer op de pagina **Accountmanager** de optie **Mijn domeinnamen**. 
  
3. Selecteer onder **Mijn domein beheren***de optie **Geavanceerde DNS-records bewerken**.

4. Klik **onder Mail Servers (MX Records)** op MX Records **bewerken**en selecteer de waarden in de volgende tabel. 
    
    |**Priority**|**TTL**|**Mail server**|
    |:-----|:-----|:-----|
    |1  <br/> Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit.    <br/> |3600  <br/> |*\<domain-key\>*.mail.protection.outlook.com  <br/> **Let op:** Haal uw *\<domain-key\>* van uw Microsoft-account.   [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md) |
   

5. Kies **Opslaan**.
  
6. Als er andere MX-records worden vermeld in de sectie **MX Records,** schakelt u het selectievakje naast de record onder **Verwijderen**in en schakelt **u Opslaan in.** 
  
7. Selecteer **wijzigingen opslaan**in het bevestigingsscherm . 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Voeg de zes CNAME-records toe die nodig zijn voor Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Ga op web.com naar de pagina domeinen met [deze link](https://checkout.web.com/manage-it/index.jsp)om aan de slag te gaan. U wordt gevraagd u eerst aan te melden.
     
2. Selecteer op de pagina **Accountmanager** de optie **Mijn domeinnamen**. 
  
3. Selecteer onder **Mijn domein beheren***de optie **Geavanceerde DNS-records bewerken**.

4. Voeg de eerste van de zes CNAME-records toe.
    
    Klik **onder Host Aliassen (CNAME Records)** op **CNAME Records bewerken**en selecteer de waarden in de volgende tabel.
    
    
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
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft. Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat. 
  
1. Ga op web.com naar de pagina domeinen met [deze link](https://checkout.web.com/manage-it/index.jsp)om aan de slag te gaan. Log dan eerst in.
    
  
2. Selecteer op de pagina **Accountmanager** de optie **Mijn domeinnamen**. 
  
3. Selecteer onder **Mijn domein beheren***de optie **Geavanceerde DNS-records bewerken**.

  
4. Klik op de pagina **Domeinnamen** onder **Tekst (TXT Records)** op **TXT Records bewerken**en selecteer de waarden in de volgende tabel.   
    
    |**Host**|**TTL**|**Tekst**|
    |:-----|:-----|:-----|
    |@  <br/> |3600  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.   |

 
5. Selecteer **Doorgaan**.

6. Selecteer **Wijzigingen opslaan**.
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>De twee SRV-records toevoegen die zijn vereist voor Microsoft
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> Houd er rekening mee dat web.com verantwoordelijk is voor het beschikbaar maken van deze functionaliteit. Als u discrepanties ziet tussen de onderstaande stappen en de huidige web.com GUI(Grafische gebruikersinterface), u gebruikmaken van de [web.com Community.](https://community.web.com.com/) 

1. Ga op web.com naar de pagina domeinen met [deze link](https://checkout.web.com/manage-it/index.jsp)om aan de slag te gaan. Log dan eerst in.
      
2. Selecteer op de pagina **Accountmanager** de optie **Mijn domeinnamen**. 
  
3. Selecteer onder **Mijn domein beheren***de optie **Geavanceerde DNS-records bewerken**.
  
4. Voeg de eerste van de twee SRV-records toe.

    Klik **onder Service (SRV Records)** op **SRV-records bewerken**en selecteer de waarden in de volgende tabel. 
        
    |**Service**|**Protocol**|**TTL**|**Prioriteit**|**Gewicht**|**Poort**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip |_tls |3600 | 100|1 |443 |sipfed.online.lync.com  |
    |_sipfederationtls |_tcp |3600 |100 |1 |5061 | sipfed.online.lync.com |

  
5. Voeg de andere SRV-record toe door de waarden uit de tweede rij van de tabel te kiezen. 
  
6. Selecteer **Doorgaan**.

7. Selecteer **Wijzigingen opslaan**.

    
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
