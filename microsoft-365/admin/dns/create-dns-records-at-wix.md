---
title: DNS-records maken bij Wix voor Office 365
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
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services op Wix voor Office 365.
ms.openlocfilehash: 8487c49e989bf2db345ae9e6d0e2970c5eb40cb6
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211060"
---
# <a name="create-dns-records-at-wix-for-office-365"></a>DNS-records maken bij Wix voor Office 365

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Als Wix uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.
  
Dit zijn de belangrijkste records om toe te voegen. 
  
- [Een TXT-record toevoegen voor verificatie](#add-a-txt-record-for-verification)
    
- [Voeg een MX-record toe zodat e-mail voor uw domein bij Office 365 terechtkomt](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [Voeg de vijf CNAME-records toe die vereist zijn voor Office 365](#add-the-five-cname-records-that-are-required-for-office-365).
    
- [Een TXT-record voor SPF toevoegen om spam tegen te gaan](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Voeg de vier SRV-records toe die voor Office 365 vereist zijn.](#add-the-two-srv-records-that-are-required-for-office-365)
    
Nadat u deze records bij Wix hebt toegevoegd, is uw domein ingesteld voor gebruik met Office 365-services.
  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie
<a name="BKMK_txt"> </a>

Voordat u uw domein met Office 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Office 365 bewezen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
1. Ga om te beginnen naar de pagina domeinen bij Wix via [deze link.](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) U wordt gevraagd u eerst aan te melden.
    
2. Selecteer op de pagina **Mijn domeinen** in het gebied **Geavanceerd** de knop **DNS bewerken.** 
    
3. Selecteer **+ Voeg een andere toe** in de rij **TXT (Text)** van de DNS-editor. 
    
4. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record. 
    
||||
|:-----|:-----|:-----|
|**Host Name** <br/> |**TXT-waarde** <br/> |**TTL** <br/> |
|Automatisch ingevuld  <br/> |MS=ms *XXXXXXXX*  <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365.  [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)|1 uur <br/> |          |
   
5. Selecteer de knop **DNS opslaan** boven aan de DNS-editor. 
    
6. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Office 365 en vraagt u of Office 365 naar de record wil zoeken.
  
Wanneer in Office 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.
  
1. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.
    
2. Kies op de pagina **Domeinen** de naam van het domein dat u verifieert. 
  
  
3. Kies **Start setup** op de pagina **Setup**.
   
  
4. Kies **Verifiëren** op de pagina **Domein verifiëren**.
    
    
  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Een MX-record toevoegen zodat e-mail voor uw domein bij Office 365 terechtkomt
<a name="BKMK_mx"> </a>

1. Ga om te beginnen naar de pagina domeinen bij Wix via [deze link.](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) U wordt gevraagd u eerst aan te melden.
    
2. Selecteer **op** de pagina Mijn domeinen in het gebied **Postvakken** de koppeling **Uw MX-records configureren.** 
    
3. Kies **Andere** in de vervolgkeuzelijst **Uw e-mailprovider.** 
    
4. Selecteer **+ Voeg er nog een toe**.
    
5. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record:
    
|**Host Name**|**Points to**|**Priority**|**TTL**|
|:-----|:-----|:-----|:-----|
|Automatisch ingevuld <br/> | *\<domeinsleutel\>*  .mail.protection.outlook.com  <br/> **Let op:** Haal uw * \<domeinsleutel\> * op uit uw Office 365-account.   [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md) |0  <br/> Zie [Wat is MX-prioriteit?](https://support.office.com/article/What-is-MX-priority-2784cc4d-95be-443d-b5f7-bb5dd867ba83) voor meer informatie over prioriteit. | 1 uur|
   
6. Als er andere MX-records worden vermeld, verwijdert u elk van deze records. 
    
7. Kies **OK**.
    
8. Selecteer **OK**in het bevestigingsdialoogvenster.
    
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a>De vijf CNAME-records toevoegen die nodig zijn voor Office 365
<a name="BKMK_cname"> </a>

1. Ga via [deze koppeling](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) naar de startpagina van Wix en meld u aan.
    
2. Selecteer op de pagina **Mijn domeinen** in het gebied **Geavanceerd** de knop **DNS bewerken.** 
    
3. Selecteer **+ Voeg een andere toe** in de rij **CNAME (Aliassen)** van de DNS-editor voor elke CNAME-record. 
    
4. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record:
    
|**Host Name**|**Verwijst naar**|**TTL**|
|:-----|:-----|:-----|
|autodiscover  <br/> |autodiscover.outlook.com  <br/> |1 uur  <br/> |
|sip  <br/> |sipdir.online.lync.com  <br/> |1 uur <br/> |
|lyncdiscover  <br/> |webdir.online.lync.com   <br/> |1 uur  <br/> |
|enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |1 uur <br/> |
|enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |1 uur  <br/> |
   
5. Selecteer de knop **DNS opslaan** boven aan de DNS-editor. 
    
6. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Een TXT-record voor SPF toevoegen om spam tegen te gaan
<a name="BKMK_spf"> </a>

> [!IMPORTANT]
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Office 365 te maken. In plaats daarvan voegt u de vereiste Office 365-waarden toe aan de huidige record, zodat u beschikt over  *één*  SPF-record waarin beide sets waarden zijn opgenomen.  
  
1. Ga om te beginnen naar de pagina domeinen bij Wix via [deze link.](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) U wordt gevraagd u eerst aan te melden.
    
2. Selecteer op de pagina **Mijn domeinen** in het gebied **Geavanceerd** de knop **DNS bewerken.** 
    
3. Selecteer **+ Voeg een andere toe** in de rij **TXT (Text)** van de DNS-editor. 
    
4. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record:
    
|**Host Name**|**TXT-waarde**|**TTL**|
|:-----|:-----|:-----|
|[Laat dit leeg]  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.<br/> |TXT  <br/> | 1 uur |
   
5. Selecteer de knop **DNS opslaan** boven aan de DNS-editor. 
    
6. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>De twee SRV-records toevoegen die voor Office 365 vereist zijn
<a name="BKMK_srv"> </a>

1. Ga om te beginnen naar de pagina domeinen bij Wix via [deze link.](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) U wordt gevraagd u eerst aan te melden.
    
2. Selecteer op de pagina **Mijn domeinen** in het gebied **Geavanceerd** de knop **DNS bewerken.** 
    
3. Selecteer **+ Voeg een andere toe** in de rij **SRV** van de DNS-editor. 
    
4. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record:
    
|**Service**|**Protocol**|**Naam**|**Gewicht**|**Poort**|**Doel**|**Priority**|**TTL**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|sip  |tls  |Automatisch ingevuld |1  |443   |sipdir.online.lync.com |100 |1 uur |
|sipfed|tcp |Automatisch ingevuld|1 |5061 |sipfed.online.lync.com|100 | 1 uur |
   
5. Selecteer de knop **DNS opslaan** boven aan de DNS-editor. 
    
6. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  

