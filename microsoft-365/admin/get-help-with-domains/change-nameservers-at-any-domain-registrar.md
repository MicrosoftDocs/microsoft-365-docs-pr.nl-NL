---
title: Naamservers wijzigen voor het instellen van Office 365 bij een domeinregistrar
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
description: Meer informatie over het toevoegen en instellen van uw domein in Office 365, zodat uw services zoals e-mail en Skype voor Bedrijven Online uw eigen domeinnaam gebruiken.
ms.custom: okr_smb
ms.openlocfilehash: 3030fc33a6d528fd6cb4e97c27cdbb7c251e9a97
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42807419"
---
# <a name="change-nameservers-to-set-up-office-365-with-any-domain-registrar"></a>Naamservers wijzigen voor het instellen van Office 365 bij een domeinregistrar

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Controleer [Eerst uw domein instellen (hostspecifieke instructies)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) om te zien of we instructies hebben voor uw registrar. 
  
Volg deze instructies om uw domein toe te voegen aan Office 365 en in te stellen, zodat services als e-mail en Skype voor Bedrijven Online gebruikmaken van uw eigen domeinnaam. Hiervoor moet u uw domein verifiëren en de naamservers van uw domein wijzigen in Office 365, zodat de juiste DNS-records voor u kunnen worden ingesteld. Voer de volgende stappen uit als in de volgende instructies uw situatie wordt beschreven:
  
- U hebt een eigen domein en wilt dit configureren voor gebruik met Office 365.
    
- U wilt Office 365 de DNS-records voor u laten beheren. (Als u wilt, kunt u [uw eigen DNS-records beheren](../setup/add-domain.md).)
    
## <a name="add-a-txt-or-mx-record-for-verification"></a>Een TXT- of MX-record toevoegen voor verificatie
<a name="BKMK_verify"> </a>

> [!NOTE]
> U hoeft standaard slechts een van deze records te maken. De voorkeur gaat uit naar het recordtype TXT, maar deze wordt niet door alle DNS-hostingproviders ondersteund. In dat geval kunt u in plaats hiervan een MX-record maken. 
  
Voordat u uw domein met Office 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Office 365 bewezen.
  
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
|**Recordtype** <br/> |**Alias** of **Hostnaam** <br/> |**Value** <br/> |**TTL** <br/> |
|TXT  <br/> |Voer een van de volgende handelingen uit: Typ **@** of laat het veld leeg, of typ de naam van uw domein.  <br/> > [!NOTE]> Verschillende DNS-hosts hebben verschillende vereisten voor dit veld.           
|MS=ms *XXXXXXXX*  <br/> > [!NOTE]> Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |Stel deze waarde in op **1 uur** of op het equivalent in minuten ( **60** ), seconden ( **3600** ) enzovoort.  <br/> |
   
**Als u een MX-record maakt, gebruikt u deze waarden:**
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Recordtype**|**Alias** of **Hostnaam**|**Value**|**Priority**|**TTL**|
|MX|Typ **@** of uw domeinnaam. |MS=ms *XXXXXXXX* > [!NOTE]> Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |Voor **Prioriteit**, gebruikt u een lagere prioriteit dan de prioriteit voor bestaande MX-records om conflicten met de MX-record te voorkomen die wordt gebruikt voor e-mailstroom. Zie [Wat is MX-prioriteit?](../setup/domains-faq.md#what-is-mx-priority) voor meer informatie over prioriteit.    |Stel deze waarde in op **1 uur** of op het equivalent in minuten ( **60** ), seconden ( **3600** ) enzovoort. |
   
### <a name="save-the-record"></a>De record opslaan

Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Office 365 en vraagt u of Office 365 naar de record wil zoeken.
  
Wanneer in Office 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.
  

1. Ga in het beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Instellingendomeinen.</a> **Settings**
    
2. Selecteer **op** de pagina Domeinen het domein dat u verifieert. 
    
  
3. Selecteer **op** de pagina Setup de optie **Installatie starten**.
 
    
  
4. Selecteer **op** de pagina Domein verifiëren de optie **Verifiëren**.
    
    
  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>De naamserverrecords (NS-records) van uw domein wijzigen
<a name="BKMK_nameservers"> </a>

Wanneer u de laatste stap van de wizard voor het instellen van domeinen in Office 365 hebt bereikt, moet u nog één taak uitvoeren. Om uw domein in te stellen met Office 365-services, zoals e-mail, wijzigt u de naamserverrecords van uw domein (of NS-records) bij uw domeinregistrar zodat deze naar de primaire en secundaire naamservers van Office 365 wijzen. Omdat uw DNS wordt gehost door Office 365, worden de voor uw services vereiste records vervolgens automatisch voor u ingesteld. U kunt de naamserverrecords zelf bijwerken door de stappen in de Help-inhoud te volgen die uw domeinregistrar op de website heeft geplaatst. Als u niet bekend bent met DNS, neemt u contact op met de ondersteuning van de domeinregistrar.

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
> Wanneer u de NS-records van uw domein wijzigt zodat deze wijzen naar de naamservers van Office 365, is dit van invloed op alle services die momenteel aan uw domein zijn gekoppeld. Als u een of meer stappen van de wizard hebt overgeslagen, zoals het toevoegen van e-mailadressen, of als u uw domein gebruikt voor blogs, winkelwagentjes of andere services, zijn er extra stappen nodig. De kans bestaat namelijk dat de overgang uitvaltijd van de service tot gevolg heeft, en dat u bijvoorbeeld geen toegang meer heeft tot uw e-mail of dat uw huidige website ontoegankelijk wordt. 

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
  
- Verplaats alle e-mailadressen die uw domein gebruiken naar Office 365 voordat u uw NS-records wijzigt.
    
- Wilt u een domein toevoegen dat momenteel wordt gebruikt met een websiteadres, zoals www.fourthcoffee.com? U onderstaande stappen uitvoeren terwijl u het domein toevoegt om de website gehost te houden waar de site nu wordt gehost, zodat mensen nog steeds naar de website kunnen gaan nadat u de NS-records van het domein hebt gewijzigd om naar Office 365 te wijzen.

1. Ga in het beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Instellingendomeinen.</a> **Settings**

3. Selecteer een domein op de pagina Domeinen.

4. Selecteer **onder DNS-instellingen** **Aangepaste records**en kies Vervolgens Nieuwe aangepaste **record**.

5. Selecteer het type DNS-record dat u wilt toevoegen en typ de gegevens voor de nieuwe record.

6. Kies **Opslaan**.
    
> [!NOTE]
> Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd. Vervolgens worden uw e-mail voor Office 365 en andere services ingesteld voor gebruik met uw domein. 
  

