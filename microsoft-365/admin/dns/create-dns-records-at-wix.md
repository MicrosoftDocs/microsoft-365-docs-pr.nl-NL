---
title: DNS-records maken bij Wix voor Microsoft
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
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services bij Wix voor Microsoft.
ms.openlocfilehash: b5fe216e65954bbcbdd9a1da223258a8362743ca
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400290"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a>DNS-records maken bij Wix voor Microsoft

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Als Wix uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.
  
Dit zijn de belangrijkste records om toe te voegen. 
  
- [Een TXT-record toevoegen voor verificatie](#add-a-txt-record-for-verification)
    
- [Voeg een MX-record toe, zodat e-mail voor uw domein naar Microsoft komt.](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [Voeg de vijf CNAME-records toe die nodig zijn voor Microsoft.](#add-the-five-cname-records-that-are-required-for-microsoft)
    
- [Een TXT-record voor SPF toevoegen om spam tegen te gaan](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Voeg de twee SRV-records toe die nodig zijn voor Microsoft.](#add-the-two-srv-records-that-are-required-for-microsoft)
    
Nadat u deze records bij Wix hebt toegevoegd, wordt uw domein ingesteld om te werken met Microsoft-services.
  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie
<a name="BKMK_txt"> </a>

Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
1. Ga om te beginnen naar de pagina domeinen bij Wix via [deze link.](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) U wordt gevraagd u eerst aan te melden.
    
2. Selecteer op de pagina **Mijn domeinen** in het gebied **Geavanceerd** de knop **DNS bewerken.** 
    
3. Selecteer **+ Voeg een andere toe** in de rij **TXT (Text)** van de DNS-editor. 
    
4. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record. 
    
||||
|:-----|:-----|:-----|
|**Host Name** <br/> |**TXT-waarde** <br/> |**TTL** <br/> |
|Automatisch ingevuld  <br/> |MS=ms *XXXXXXXX*  <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.  [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)|1 uur <br/> |          |
   
5. Selecteer de knop **DNS opslaan** boven aan de DNS-editor. 
    
6. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.
  
Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.
  
1. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.
    
2. Kies op de pagina **Domeinen** de naam van het domein dat u verifieert. 
  
  
3. Kies **Start setup** op de pagina **Setup**.
   
  
4. Kies **Verifiëren** op de pagina **Domein verifiëren**.
    
    
  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden
<a name="BKMK_mx"> </a>

1. Ga om te beginnen naar de pagina domeinen bij Wix via [deze link.](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) U wordt gevraagd u eerst aan te melden.
    
2. Selecteer **op** de pagina Mijn domeinen in het gebied **Postvakken** de koppeling **Uw MX-records configureren.** 
    
3. Kies **Andere** in de vervolgkeuzelijst **Uw e-mailprovider.** 
    
4. Selecteer **+ Voeg er nog een toe**.
    
5. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record:
    
|**Host Name**|**Points to**|**Priority**|**TTL**|
|:-----|:-----|:-----|:-----|
|Automatisch ingevuld <br/> | *\<domain-key\>*.mail.protection.outlook.com  <br/> **Let op:** Haal uw *\<domain-key\>* van uw Microsoft-account.   [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md) |0  <br/> Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit. | 1 uur|
   
6. Als er andere MX-records worden vermeld, verwijdert u elk van deze records. 
    
7. Kies **OK**.
    
8. Selecteer **OK**in het bevestigingsdialoogvenster.
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a>Voeg de vijf CNAME-records toe die nodig zijn voor Microsoft
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
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft. Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat.  
  
1. Ga om te beginnen naar de pagina domeinen bij Wix via [deze link.](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) U wordt gevraagd u eerst aan te melden.
    
2. Selecteer op de pagina **Mijn domeinen** in het gebied **Geavanceerd** de knop **DNS bewerken.** 
    
3. Selecteer **+ Voeg een andere toe** in de rij **TXT (Text)** van de DNS-editor. 
    
4. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record:
    
|**Host Name**|**TXT-waarde**|**TTL**|
|:-----|:-----|:-----|
|[Laat dit leeg]  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.<br/> |TXT  <br/> | 1 uur |
   
5. Selecteer de knop **DNS opslaan** boven aan de DNS-editor. 
    
6. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>De twee SRV-records toevoegen die zijn vereist voor Microsoft
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
  

