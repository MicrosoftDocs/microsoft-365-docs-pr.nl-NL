---
title: Naamservers wijzigen om Microsoft 365 in te stellen bij elke domeinregistrar
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
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: Meer informatie over het toevoegen en instellen van uw domein in Microsoft 365, zodat uw services zoals e-mail en Skype voor Bedrijven Online uw eigen domeinnaam gebruiken.
ms.custom: okr_smb
ms.openlocfilehash: e987d1194d3ee86548a6628310ebdfd14cdbb9ea
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628504"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a>Naamservers wijzigen om Microsoft 365 in te stellen bij elke domeinregistrar

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Controleer [Eerst uw domein instellen (hostspecifieke instructies)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) om te zien of we instructies hebben voor uw registrar. 
  
Volg deze instructies om uw domein toe te voegen en in te stellen in Microsoft 365, zodat uw services zoals e-mail en Skype voor Bedrijven Online uw eigen domeinnaam gebruiken. Om dit te doen, verifieert u uw domein en wijzigt u vervolgens de naamservers van uw domein in Microsoft 365, zodat de juiste DNS-records voor u kunnen worden ingesteld. Voer de volgende stappen uit als in de volgende instructies uw situatie wordt beschreven:
  
- U hebt uw eigen domein en wilt het instellen om te werken met Microsoft 365.
    
- U wilt dat Microsoft 365 uw DNS-records voor u beheert. (Als u wilt, kunt u [uw eigen DNS-records beheren](../setup/add-domain.md).)
    
## <a name="add-a-txt-or-mx-record-for-verification"></a>Een TXT- of MX-record toevoegen voor verificatie
<a name="BKMK_verify"> </a>

> [!NOTE]
> U hoeft standaard slechts een van deze records te maken. De voorkeur gaat uit naar het recordtype TXT, maar deze wordt niet door alle DNS-hostingproviders ondersteund. In dat geval kunt u in plaats hiervan een MX-record maken. 
  
Voordat u uw domein met Microsoft 365 gebruikt, moeten we ervoor zorgen dat u eigenaar bent. Uw mogelijkheid om in te loggen op uw account bij uw domeinregistrar en de DNS-record te maken bewijst microsoft 365 dat u eigenaar bent van het domein.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a>Zoek het gebied op de website van uw DNS-hostingprovider waar u een nieuwe record maken

1. Meld u aan bij de website van uw DNS-hostingprovider.
    
2. Selecteer uw domein.
    
3. Zoek de pagina waarop u DNS-records voor uw domein kunt bewerken.
    
### <a name="create-the-record"></a>De record maken

Voer een van de volgende handelingen uit, afhankelijk van of u een TXT-record of een MX-record maakt:
  
**Als u een TXT-record maakt, gebruikt u deze waarden:**
    
|||||
|:-----|:-----|:-----|:-----|
|**Recordtype** <br/> |**Alias** of **Hostnaam** <br/> |**Waarde** <br/> |**TTL** <br/> |
|TXT  <br/> |Voer een van de volgende handelingen uit: Typ **@** of laat het veld leeg, of typ de naam van uw domein.  <br/> > [!NOTE]> Verschillende DNS-hosts hebben verschillende vereisten voor dit veld.           
|MS=ms *XXXXXXXX*  <br/> > [!NOTE]> Dit is een voorbeeld. Gebruik hier de waarde van uw specifieke **bestemming of adresinrichten** in de tabel in Microsoft 365.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |Stel deze waarde in op **1 uur** of op het equivalent in minuten ( **60** ), seconden ( **3600** ) enzovoort.  <br/> |
   
**Als u een MX-record maakt, gebruikt u deze waarden:**
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Recordtype**|**Alias** of **Hostnaam**|**Value**|**Priority**|**TTL**|
|MX|Typ **@** of uw domeinnaam. |MS=ms *XXXXXXXX* > [!NOTE]> Dit is een voorbeeld. Gebruik hier de waarde van uw specifieke **bestemming of adresinrichten** in de tabel in Microsoft 365.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |Gebruik een lagere prioriteit dan de prioriteit voor bestaande MX-records voor **Prioriteit** om conflicten met de MX-record voor de e-mailstroom te voorkomen. Zie [Wat is MX-prioriteit?](../setup/domains-faq.md#what-is-mx-priority) voor meer informatie over prioriteit. |Stel deze waarde in op **1 uur** of op het equivalent in minuten ( **60** ), seconden ( **3600** ) enzovoort. |
   
### <a name="save-the-record"></a>De record opslaan

Nu u de record op de site van uw domeinregistrar hebt toegevoegd, gaat u terug naar Microsoft 365 en vraagt u Microsoft 365 om de record te zoeken.
  
Wanneer Microsoft 365 de juiste TXT-record vindt, wordt uw domein geverifieerd.
  

1. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.
    
2. Kies op de pagina **Domeinen** de naam van het domein dat u verifieert. 
    
  
3. Kies **Start setup** op de pagina **Setup**.
 
    
  
4. Kies **Verifiëren** op de pagina **Domein verifiëren**.
    
    
  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>De naamserverrecords (NS-records) van uw domein wijzigen
<a name="BKMK_nameservers"> </a>

Wanneer u bij de laatste stap van de wizard domeinensetup in Microsoft 365 komt, blijft er nog één taak over. Als u uw domein wilt instellen met Microsoft 365-services, zoals e-mail, wijzigt u de naamserver-records (of NS) van uw domein bij uw domeinregistrar om te wijzen op de primaire en secundaire naamservers van Microsoft 365. Omdat Microsoft 365 uw DNS host, worden vervolgens de vereiste DNS-records voor uw services automatisch voor u ingesteld. U kunt de naamserverrecords zelf bijwerken door de stappen in de Help-inhoud te volgen die uw domeinregistrar op de website heeft geplaatst. Als u niet bekend bent met DNS, neemt u contact op met de ondersteuning van de domeinregistrar.

::: moniker range="o365-worldwide"
  
Als u de naamservers van het domein zelf wilt wijzigen op de website van de domeinregistrar, volgt u deze stappen:
  
1. Zoek het gedeelte op de website van de domeinregistrar waarop u de naamservers voor uw domein kunt wijzigen.
    
2. Maak twee naamserverrecords, of bewerk de bestaande naamserverrecords zodat ze overeenkomen met de volgende waarden:
    
|||
|:-----|:-----|
|Eerste naamserver  <br/> |ns1.bdm.microsoftonline.com  <br/> |
|Tweede naamserver  <br/> |ns2.bdm.microsoftonline.com  <br/> |
   
   > [!TIP]
   > U moet ten minste twee nameserverrecords gebruiken. Als er andere naamservers worden vermeld, u deze verwijderen of wijzigen in **ns3.bdm.microsoftonline.com** en **ns4.bdm.microsoftonline.com.** 
  
3. Sla uw wijzigingen op.
    
> [!CAUTION]
> Wanneer u de NS-records van uw domein wijzigt om naar de Microsoft 365-naamservers te wijzen, worden alle services die momenteel aan uw domein zijn gekoppeld, beïnvloed. Als u een of meer stappen van de wizard hebt overgeslagen, zoals het toevoegen van e-mailadressen, of als u uw domein gebruikt voor blogs, winkelwagentjes of andere services, zijn er extra stappen nodig. De kans bestaat namelijk dat de overgang uitvaltijd van de service tot gevolg heeft, en dat u bijvoorbeeld geen toegang meer heeft tot uw e-mail of dat uw huidige website ontoegankelijk wordt. 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. Zoek het gedeelte op de website van de domeinregistrar waarop u de naamservers voor uw domein kunt wijzigen.
    
2. Maak twee naamserverrecords, of bewerk de bestaande naamserverrecords zodat ze overeenkomen met de volgende waarden:
    
|||
|:-----|:-----|
|Eerste naamserver  <br/> |ns1.dns.partner.microsoftonline.cn  <br/> |
|Tweede naamserver  <br/> |ns2.dns.partner.microsoftonline.cn  <br/> |
   
   > [!TIP]
   > U moet ten minste twee nameserverrecords gebruiken. Als er andere naamservers worden vermeld, u deze verwijderen of wijzigen in **ns3.dns.partner.microsoftonline.cn** en **ns4.dns.partner.microsoftonline.cn.** 
  
3. Sla uw wijzigingen op.
    
> [!CAUTION]
> Wanneer u de NS-records van uw domein wijzigt om te wijzen op de Office 365 die wordt beheerd door 21Vianet-naamservers, worden alle services die momenteel aan uw domein zijn gekoppeld, beïnvloed. Als u een of meer stappen van de wizard hebt overgeslagen, zoals het toevoegen van e-mailadressen, of als u uw domein gebruikt voor blogs, winkelwagentjes of andere services, zijn er extra stappen nodig. De kans bestaat namelijk dat de overgang uitvaltijd van de service tot gevolg heeft, en dat u bijvoorbeeld geen toegang meer heeft tot uw e-mail of dat uw huidige website ontoegankelijk wordt. 

::: moniker-end
  
Hierna volgt een voorbeeld van extra stappen die mogelijk zijn vereist voor de hosting van e-mail en websites:
  
- Verplaats alle e-mailadressen die uw domein gebruiken naar Microsoft 365 voordat u uw NS-records wijzigt.
    
- Wilt u een domein toevoegen dat momenteel wordt gebruikt met een websiteadres, zoals www.fourthcoffee.com? U onderstaande stappen nemen terwijl u het domein toevoegt om de website gehost te houden waar de site nu wordt gehost, zodat mensen nog steeds naar de website kunnen gaan nadat u de NS-records van het domein hebt gewijzigd om naar Microsoft 365 te wijzen.

1. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.

3. Selecteer een domein op de pagina Domeinen.

4. Selecteer **onder DNS-instellingen** **Aangepaste records**en kies Vervolgens Nieuwe aangepaste **record**.

5. Selecteer het type DNS-record dat u wilt toevoegen en typ de gegevens voor de nieuwe record.

6. Kies **Opslaan**.
    
> [!NOTE]
> Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd. Vervolgens zijn uw Microsoft-e-mail en andere services helemaal klaar om met uw domein te werken. 
  

