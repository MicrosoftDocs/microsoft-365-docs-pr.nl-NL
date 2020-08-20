---
title: DNS-records bij Wix maken voor Microsoft
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
description: Lees hoe u uw domein verifieert en DNS-records instelt voor e-mail, Skype voor bedrijven online en andere services op Wix voor Microsoft.
ms.openlocfilehash: fcc0f8e8187e22dde68149e0f2a80073312bff7f
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814442"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a>DNS-records bij Wix maken voor Microsoft

**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Als Wix uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.

Dit zijn de belangrijkste records om toe te voegen. 
  
- [Een TXT-record toevoegen voor verificatie](#add-a-txt-record-for-verification)
    
- [Voeg een MX-record toe zodat e-mail voor uw domein bij Microsoft komt](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).
    
- [Voeg de vijf CNAME-records toe die voor Microsoft vereist zijn](#add-the-five-cname-records-that-are-required-for-microsoft).
    
- [Een TXT-record voor SPF toevoegen om spam tegen te gaan](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Voeg de twee SRV-records toe die voor Microsoft vereist zijn](#add-the-two-srv-records-that-are-required-for-microsoft).
    
Nadat u deze records bij Wix hebt toegevoegd, is uw domein ingesteld voor gebruik met Microsoft-services.
  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 

  
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie
<a name="BKMK_txt"> </a>

Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 

> [!NOTE]
> WIX biedt geen ondersteuning voor DNS-vermeldingen voor subdomeinen.
  
1. Als u wilt beginnen, gaat u naar uw domeinen pagina bij Wix met behulp van [deze koppeling](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). U wordt gevraagd u eerst aan te melden.
    
2. Selecteer op de pagina **My Domains** in het gebied **Advanced** de knop **Edit DNS** . 
    
3. Selecteer **+ een andere toevoegen** in de rij **txt (text)** van de DNS-editor. 
    
4. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record. 
    
   ||||
   |:-----|:-----|:-----|
   | Host name <br/> | TXT Value <br/> | TTL <br/> |
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
> Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden
<a name="BKMK_mx"> </a>

1. Als u wilt beginnen, gaat u naar uw domeinen pagina bij Wix met behulp van [deze koppeling](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). U wordt gevraagd u eerst aan te melden.
    
2. Selecteer op de pagina **My Domains** in het gebied **postvakken** de koppeling **uw MX records configureren** . 
    
3. Kies in de vervolgkeuzelijst **uw e-mail provider** de optie **Overige** . 
    
4. Selecteer **+ een andere toevoegen**.
    
5. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record:
    
   | Host name | Verwijst naar | Priority | TTL |
   |:-----|:-----|:-----|:-----|
   |Automatisch ingevuld <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **Opmerking:** Neem uw  *\<domain-key\>*  van uw Microsoft-account.   [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md) |0  <br/> Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit. | 1 uur|
   
6. Als er andere MX-records worden vermeld, verwijdert u elke record. 
    
7. Selecteer **OK**.
    
8. Selecteer **OK**in het bevestigingsvenster.
    
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a>De vijf CNAME-records toevoegen die vereist zijn voor Microsoft
<a name="BKMK_cname"> </a>

1. Ga via [deze koppeling](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account) naar de startpagina van Wix en meld u aan.
    
2. Selecteer op de pagina **My Domains** in het gebied **Advanced** de knop **Edit DNS** . 
    
3. Selecteer in de rij **CNAME (Aliases)** van de DNS-editor **een koppeling toevoegen** voor elke CNAME-record. 
    
4. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record:
    
   | Host name | Verwijst naar | TTL |
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
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft. In plaats daarvan voegt u de vereiste Microsoft-waarden toe aan de huidige record, zodat u  *één*  SPF-record hebt die beide sets met waarden bevat.  
  
1. Als u wilt beginnen, gaat u naar uw domeinen pagina bij Wix met behulp van [deze koppeling](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). U wordt gevraagd u eerst aan te melden.
    
2. Selecteer op de pagina **My Domains** in het gebied **Advanced** de knop **Edit DNS** . 
    
3. Selecteer **+ een andere toevoegen** in de rij **txt (text)** van de DNS-editor. 
    
4. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record:
    
   | Host name | TXT Value | TTL |
   |:-----|:-----|:-----|
   |[laat dit leeg]  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.<br/> |TXT  <br/> | 1 uur |
   
5. Selecteer de knop **DNS opslaan** boven aan de DNS-editor. 
    
6. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>De twee SRV-records toevoegen die zijn vereist voor Microsoft
<a name="BKMK_srv"> </a>

1. Als u wilt beginnen, gaat u naar uw domeinen pagina bij Wix met behulp van [deze koppeling](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). U wordt gevraagd u eerst aan te melden.
    
2. Selecteer op de pagina **My Domains** in het gebied **Advanced** de knop **Edit DNS** . 
    
3. Selecteer **+ een andere toevoegen** in de rij **SRV** van de DNS-editor. 
    
4. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record:
    
   | Service | Protocol | Naam | Dikte | Poort | Doel | Priority | TTL |
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |sip  |tls  |Automatisch ingevuld |1  |443   |sipdir.online.lync.com |100 |1 uur |
   |sipfed|tcp |Automatisch ingevuld|1 |5061 |sipfed.online.lync.com|100 | 1 uur |
   
5. Selecteer de knop **DNS opslaan** boven aan de DNS-editor. 
    
6. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
> [!NOTE]
> Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
