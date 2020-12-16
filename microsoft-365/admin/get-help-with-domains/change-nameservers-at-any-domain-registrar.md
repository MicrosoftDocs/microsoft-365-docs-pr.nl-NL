---
title: Naamservers wijzigen voor het instellen van Microsoft 365 met een domeinregistratie
f1.keywords:
- CSH
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: Lees hoe u uw domein kunt toevoegen en instellen in Microsoft 365, zodat uw services zoals e-mail en Skype voor bedrijven online uw eigen domeinnaam kunnen gebruiken.
ms.openlocfilehash: 492bc5d2a5f3fd9810f045e7effda1ea20fa15ed
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688247"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a>Naamservers wijzigen voor het instellen van Microsoft 365 met een domeinregistratie

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt. 
  
Controleer eerst [uw domein instellen (host-specifieke instructies)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) om te zien of er instructies voor uw registratieservice zijn. 
  
Volg deze instructies voor het toevoegen en instellen van uw domein in Microsoft 365, zodat uw services zoals e-mail en teams uw eigen domeinnaam kunnen gebruiken. U kunt dit doen door uw domein te verifiëren en de naamservers van uw domein te wijzigen in Microsoft 365 zodat de juiste DNS-records voor u kunnen worden ingesteld. Voer de volgende stappen uit als u de situatie in de volgende staten opneemt:
  
- U hebt een eigen domein en wilt dit instellen voor gebruik met Microsoft 365.
    
- U wilt dat Microsoft 365 uw DNS-records voor u beheert. (Als u wilt, kunt u [uw eigen DNS-records beheren](../setup/add-domain.md).)
    
## <a name="add-a-txt-or-mx-record-for-verification"></a>Een TXT- of MX-record toevoegen voor verificatie
<a name="BKMK_verify"> </a>

> [!NOTE]
> U hoeft standaard slechts een van deze records te maken. De voorkeur gaat uit naar het recordtype TXT, maar deze wordt niet door alle DNS-hostingproviders ondersteund. In dat geval kunt u in plaats hiervan een MX-record maken. 
  
Voordat u uw domein met Microsoft 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft 365 bewezen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a>Het gebied zoeken op de website van uw DNS-hosting provider waar u een nieuwe record kunt maken

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
|MS=ms *XXXXXXXX*  <br/> > [!NOTE]> Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Microsoft 365.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |Stel deze waarde in op **1 uur** of op het equivalent in minuten ( **60** ), seconden ( **3600** ) enzovoort.  <br/> |
   
**Als u een MX-record maakt, gebruikt u deze waarden:**
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Recordtype**|**Alias** of **Hostnaam**|**Value**|**Priority**|**TTL**|
|MX|Typ **@** of uw domeinnaam. |MS=ms *XXXXXXXX* > [!NOTE]> Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Microsoft 365.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |Gebruik een lagere prioriteit dan de prioriteit voor bestaande MX-records voor **Prioriteit** om conflicten met de MX-record voor de e-mailstroom te voorkomen. Zie [Wat is MX-prioriteit?](../setup/domains-faq.yml) voor meer informatie over prioriteit. |Stel deze waarde in op **1 uur** of op het equivalent in minuten ( **60** ), seconden ( **3600** ) enzovoort. |
   
### <a name="save-the-record"></a>Sla de record op

Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft 365 en vraagt u of Microsoft 365 naar de record wil zoeken.
  
Wanneer in Microsoft 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.
  

1. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.
    
2. Kies op de pagina **Domeinen** de naam van het domein dat u verifieert. 
    
  
3. Kies **Start setup** op de pagina **Setup**.
 
    
  
4. Kies **Verifiëren** op de pagina **Domein verifiëren**.
    
    
  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>De naamserverrecords (NS-records) van uw domein wijzigen
<a name="BKMK_nameservers"> </a>

Wanneer de laatste stap van de wizard domeinen instellen in Microsoft 365 wordt weergeven, hebt u één resterende taak. Voor het instellen van uw domein met Microsoft 365-Services, zoals e-mail, wijzigt u de naamserver-records (of NS-records) van uw domein in de registratiefunctie, zodat deze verwijzen naar de primaire en secundaire naamservers van Microsoft 365. Omdat Microsoft 365 uw DNS host, worden de vereiste DNS-records voor uw services automatisch voor u ingesteld. U kunt de naamserverrecords zelf bijwerken door de stappen in de Help-inhoud te volgen die uw domeinregistrar op de website heeft geplaatst. Als u niet bekend bent met DNS, neemt u contact op met de ondersteuning van de domeinregistrar.

::: moniker range="o365-worldwide"
  
Als u de naamservers van het domein zelf wilt wijzigen op de website van de domeinregistrar, volgt u deze stappen:
  
1. Het gebied zoeken op de website van de domeinregistratie waarop u de naamservers voor uw domein of een gebied waarop u aangepaste naamservers kunt gebruiken, kunt wijzigen.
    
2. Maak naamserver records, of bewerk de bestaande naamserver records zodat ze overeenkomen met de volgende waarden:
    
|||
|:-----|:-----|
|Eerste naamserver  <br/> |ns1.bdm.microsoftonline.com  <br/> |
|Tweede naamserver  <br/> |ns2.bdm.microsoftonline.com  <br/> |
|Derde naamserver  <br/> |ns3.bdm.microsoftonline.com  <br/> |
|Vierde naamserver  <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   > [!TIP]
   > Het is raadzaam om alle vier de records toe te voegen, maar als u met de registratiefunctie slechts twee wilt ondersteunen, voegt u **ns1.BDM.microsoftonline.com** en **ns2.BDM.microsoftonline.com** toe. 
  
3. Sla uw wijzigingen op.
    
> [!CAUTION]
> Wanneer u de naamserver records van uw domein wijzigt zodat ze verwijzen naar de Microsoft 365-naamservers, worden alle services die momenteel aan uw domein zijn gekoppeld, gewijzigd. Als u een of meer stappen van de wizard hebt overgeslagen, zoals het toevoegen van e-mailadressen, of als u uw domein gebruikt voor blogs, winkelwagentjes of andere services, zijn er extra stappen nodig. De kans bestaat namelijk dat de overgang uitvaltijd van de service tot gevolg heeft, en dat u bijvoorbeeld geen toegang meer heeft tot uw e-mail of dat uw huidige website ontoegankelijk wordt. 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. Zoek het gedeelte op de website van de domeinregistrar waarop u de naamservers voor uw domein kunt wijzigen.
    
2. Maak twee naamserverrecords, of bewerk de bestaande naamserverrecords zodat ze overeenkomen met de volgende waarden:
    
|||
|:-----|:-----|
|Eerste naamserver  <br/> |ns1.dns.partner.microsoftonline.cn  <br/> |
|Tweede naamserver  <br/> |ns2.dns.partner.microsoftonline.cn  <br/> |
   
   > [!TIP]
   > U dient ten minste twee naamserver-records te gebruiken. Als er andere naamservers worden vermeld, kunt u deze verwijderen of de wijzigingen in **ns3.DNS.partner.microsoftonline.cn** en **ns4.DNS.partner.microsoftonline.cn**. 
  
3. Sla uw wijzigingen op.
    
> [!CAUTION]
> Wanneer u de naamserver records van uw domein wijzigt zodat ze verwijzen naar de Office 365 die wordt beheerd door 21Vianet naamservers, worden alle services die op dat moment zijn gekoppeld aan uw domein van invloed. Als u een of meer stappen van de wizard hebt overgeslagen, zoals het toevoegen van e-mailadressen, of als u uw domein gebruikt voor blogs, winkelwagentjes of andere services, zijn er extra stappen nodig. De kans bestaat namelijk dat de overgang uitvaltijd van de service tot gevolg heeft, en dat u bijvoorbeeld geen toegang meer heeft tot uw e-mail of dat uw huidige website ontoegankelijk wordt. 

::: moniker-end
  
Hierna volgt een voorbeeld van extra stappen die mogelijk zijn vereist voor de hosting van e-mail en websites:
  
- Verplaats alle e-mailadressen die uw domein gebruiken naar Microsoft 365 voordat u de naam van uw NS-records wijzigt.
    
- Wilt u een domein toevoegen dat momenteel wordt gebruikt met een websiteadres, bijvoorbeeld www.fourthcoffee.com? Wanneer u het domein toevoegt, kunt u de volgende stappen uitvoeren om te voorkomen dat de website gehost blijft op de site waar de site wordt gehost, zodat personen de website nog kunnen bereiken nadat u de NS-records van het domein hebt gewijzigd zodat ze verwijzen naar Microsoft 365.

1. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.

2. Selecteer het domein op de pagina **domeinen** en kies vervolgens **DNS-records**.

3. Selecteer onder **DNS beheren** de optie **aangepaste records** en kies vervolgens **nieuwe aangepaste record**.

4. Selecteer het type DNS-record dat u wilt toevoegen en typ de gegevens voor de nieuwe record.

5. Kies **Opslaan**.
    
> [!NOTE]
> Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd. Vervolgens zijn uw Microsoft-e-mail en andere services allemaal ingesteld voor gebruik met uw domein. 
  
