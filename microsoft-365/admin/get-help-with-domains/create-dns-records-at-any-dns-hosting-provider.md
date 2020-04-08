---
title: DNS-records maken bij een DNS-hostingprovider voor Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 7b7b075d-79f9-4e37-8a9e-fb60c1d95166
description: Lees hier hoe u uw domein kunt verifiëren en DNS-records kunt maken bij een DNS-hostingprovider voor Office 365.
ms.custom: okr_smb
ms.openlocfilehash: 2d3c726f70ffb4588f7ae2fc8b53bf8f0c60e258
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42806189"
---
# <a name="create-dns-records-at-any-dns-hosting-provider-for-office-365"></a>DNS-records maken bij een DNS-hostingprovider voor Office 365

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Bekijk onze lijst met [hostspecifieke instructies](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580) om uw host te vinden en volg de stappen om alle records toe te voegen die u nodig hebt. 
  
Als u niet weet wie de DNS-hostingprovider of domeinregistrar voor uw domein is, raadpleegt u [Zoeken naar uw domeinregistrar of DNS-hostingprovider](../get-help-with-domains/find-your-domain-registrar.md).
  
Als u de records zelf wilt instellen, moet u deze records toevoegen. Houd er rekening mee dat uw verificatierecord en MX-record uniek zijn voor uw domein. Om die in te stellen, moet u een specifieke ‘token’-waarde ophalen en gebruiken voor uw domein. In de onderstaande stappen wordt uitgelegd hoe u dit doet.
  
> [!IMPORTANT]
> De exacte naam van de vakken of *velden* waarin u de gegevens typt of plakt voor het maken van elk type DNS-record, zijn anders voor elke DNS-host. Mogelijk heeft uw DNS-host Help-informatie op zijn website om u te helpen bij het toewijzen van de instructies, die hier worden weergegeven, aan de juiste velden op de website. Controleer in [DNS-records maken voor Office 365](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23.aspx) of we stapsgewijze instructies hebben voor uw DNS-host. > Bepaalde DNS-hosts staan niet toe dat u alle vereiste recordtypen maakt. Dit [zorgt voor servicebeperkingen](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) in Office 365. Als bijvoorbeeld de host van uw domein SRV-, TXT- of CNAME-records niet ondersteunt, raden we u aan dat u [uw domein overbrengt](../get-help-with-domains/buy-a-domain-name.md) naar een DNS-host die wel alle vereiste records ondersteunt. We raden aan dat u uw domein overbrengt naar GoDaddy voor een snel en geautomatiseerd proces voor het instellen van Office 365. 
  
> [!NOTE]
> Het duurt gewoonlijk maar een paar minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen vinden en oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-or-mx-record-for-verification"></a>Een TXT- of MX-record toevoegen voor verificatie
<a name="BKMK_verify"> </a>

> [!NOTE]
> U hoeft standaard slechts een van deze records te maken. De voorkeur gaat uit naar het recordtype TXT, maar deze wordt niet door alle DNS-hostingproviders ondersteund. In dat geval kunt u in plaats hiervan een MX-record maken. 
  
Voordat u uw domein met Office 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Office 365 bewezen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
 **Zoek het gedeelte op de website van uw DNS-hostingprovider waar u een nieuwe record kunt maken.**
  
1. Meld u aan bij de website van uw DNS-hostingprovider.
    
2. Selecteer uw domein.
    
3. Zoek de pagina waarop u DNS-records voor uw domein kunt bewerken.
    
 **Maak de record.**
  
1. Voer een van de volgende handelingen uit, afhankelijk van of u een TXT-record of een MX-record maakt:
    
  - **Als u een TXT-record maakt, gebruikt u deze waarden:**
    
|||||
|:-----|:-----|:-----|:-----|
|**Recordtype**|**Alias** of **Hostnaam**|**Waarde**|**TTL**|
|TXT|Voer een van de volgende handelingen uit: Typ **@** of laat het veld leeg, of typ de naam van uw domein.  <br/> **Let op:** Verschillende DNS-hosts hebben verschillende vereisten voor dit veld. |MS=ms *XXXXXXXX*  <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365.  <br/>        [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)     <br/>     |Stel deze waarde in op **1 uur** of op het equivalent in minuten ( **60** ), seconden ( **3600** ) enzovoort.  |
   
  - **Als u een MX-record maakt, gebruikt u deze waarden:**
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Recordtype**|**Alias** of **Hostnaam**|**Value**|**Priority**|**TTL**|
|MX|Typ **@** of uw domeinnaam. |MS=ms *XXXXXXXX* <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365.    <br/>       [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)     <br/>     |Gebruik een lagere prioriteit dan de prioriteit voor bestaande MX-records voor **Prioriteit** om conflicten met de MX-record voor de e-mailstroom te voorkomen. <br/> Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit. <br/> |Stel deze waarde in op **1 uur** of op het equivalent in minuten ( **60** ), seconden ( **3600** ) enzovoort. |
   
2. Sla de record op.
    
Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Office 365 en vraagt u of Office 365 naar de record wil zoeken.
  
Wanneer in Office 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.
  
1. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.
    
2. Kies op de pagina **Domeinen** de naam van het domein dat u verifieert. 
  
3. Kies **Start setup** op de pagina **Setup**.
       
4. Kies **Verifiëren** op de pagina **Domein verifiëren**.   
  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-mx-record-to-route-email"></a>MX-record toevoegen om e-mail te routeren
<a name="BKMK_add_MX"> </a>

Voeg een MX-record toe zodat e-mail voor uw domein naar Office 365 wordt verzonden.  *Wanneer u de MX-record van uw domein bijwerkt, wordt alle nieuwe e-mail voor iedereen die uw domein gebruikt, verzonden naar Office 365*. Elk e-mailbericht dat u al hebt, blijft bij uw huidige e-mailhost, tenzij u besluit [e-mail en contactpersonen te migreren naar Office 365](../setup/migrate-email-and-contacts-admin.md) naar Office 365. 
  
  
 **Taak**
  
De pagina zoeken waarop u records voor uw domein kunt maken.
  
1. Meld u aan bij de website van uw DNS-host.
    
2. Selecteer uw domein.
    
3. Zoek de pagina waarop u DNS-records voor uw domein kunt bewerken.
    
::: moniker range="o365-worldwide"

De MX-record die u toevoegt, bevat een waarde (de waarde **Adres waarnaar wordt verwezen**) die er ongeveer zo uitziet: \<MX token\>.mail.protection.outlook.com, waarbij \<MX-token\> een waarde is zoals MSxxxxxxx. 

::: moniker-end

::: moniker range="o365-germany"

De MX-record die u toevoegt, bevat een waarde (de waarde **Adres waarnaar wordt verwezen**) die er ongeveer zo uitziet: \<<MX token\>.mail.protection.outlook.de, waarbij \<MX-token\> een waarde is zoals MSxxxxxxx. 

::: moniker-end

1. Voeg op de website van uw DNS-host een nieuwe MX-record toe.
    
    Nu krijgt u [de informatie voor de MX-record](../get-help-with-domains/information-for-dns-records.md) van Office 365. 
    
2. Voor de MX-record (in de stap hierboven) kopieert u de waarde **Adres waarnaar wordt verwezen**. 
    
    U gebruikt deze waarde in de record die u op de site van uw DNS-host maakt, zoals wordt beschreven in de volgende stap.
    
3. Controleer in de nieuwe MX-record op de site van uw DNS-host of de velden zijn ingesteld op precies de volgende waarden:
    
  - **Recordtype**: **MX**
    
  - **Prioriteit**: Stel de prioriteit in van de MX-record op de hoogst beschikbare waarde, meestal **0**.
    
    Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit.
    
  - **Host Name**: **@**
    
  - **Adres waarnaar wordt verwezen**: Plak hier de waarde van het **Adres waarnaar wordt verwezen** die u zojuist uit Office 365 hebt gekopieerd. 
    
  - **TTL**: Stel deze waarde in op **1 uur** of op het equivalent in minuten (**60**), seconden (**3600**) enzovoort. 
    
4. Sla de record op.
    
Verwijder eventuele andere MX-records.
  
Als er MX-records voor dit domein aanwezig zijn waarmee e-mail ergens anders dan naar Office 365 wordt verzonden, moet u ze allemaal verwijderen.
  
## <a name="add-three-cname-records"></a>Drie CNAME-records toevoegen
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

Volg onderstaande stappen om de drie CNAME-records toe te voegen die zijn vereist voor Office 365. Als er extra CNAME-records worden weergegeven in Office 365, voegt u die toe aan de hand van dezelfde algemene stappen die hier worden weergegeven.
  
Op de website van uw DNS-host maakt u drie nieuwe CNAME-records, meestal één voor één.
  
1. Typ of kopieer en plak de volgende waarden in de vakken voor elke nieuwe record. Nadat u elk van de eerste drie nieuwe records hebt toegevoegd, kiest u om nog een CNAME-record te maken.
    
|||||
|:-----|:-----|:-----|:-----|
|**Recordtype** <br/> |**Host** <br/> |**Verwijst naar** <br/> |**TTL** <br/> |
|CNAME (alias)  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |1 uur  <br/> |
|CNAME (alias)  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |1 uur  <br/> |
|CNAME (alias)  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |1 uur  <br/> |
   
   > [!NOTE]
   > Voor **TTL**: Stel deze waarde in op **1 uur** of op het equivalent in minuten (**60**), seconden (**3600**) enzovoort. > Deze records zijn niet van toepassing op Exchange-, Lync- of Skype voor bedrijven-hybride implementaties. 
  
2. Sla de records op als u klaar bent.
    
::: moniker-end
::: moniker range="o365-germany"

Volg onderstaande stappen om de drie CNAME-records toe te voegen die zijn vereist voor Office 365. Als er extra CNAME-records worden weergegeven in Office 365, voegt u die toe aan de hand van dezelfde algemene stappen die hier worden weergegeven.
  
Op de website van uw DNS-host maakt u drie nieuwe CNAME-records, meestal één voor één.
  
1. Typ of kopieer en plak de volgende waarden in de vakken voor elke nieuwe record. Nadat u elk van de eerste drie nieuwe records hebt toegevoegd, kiest u om nog een CNAME-record te maken.
    
|||||
|:-----|:-----|:-----|:-----|
|**Recordtype** <br/> |**Host** <br/> |**Verwijst naar** <br/> |**TTL** <br/> |
|CNAME (alias)  <br/> |autodiscover  <br/> |autodiscover-outlook.office.de  <br/> |1 uur  <br/> |
|CNAME (alias)  <br/> |lyncdiscover  <br/> |webdir.online.skype.de  <br/> |1 uur  <br/> |
|CNAME (alias)  <br/> |sip  <br/> |sipdir.online.lync.de  <br/> |1 uur  <br/> |
   
   > [!NOTE]
   > Voor **TTL**: Stel deze waarde in op **1 uur** of op het equivalent in minuten (**60**), seconden (**3600**) enzovoort. > Deze records zijn niet van toepassing op Exchange-, Lync- of Skype voor bedrijven-hybride implementaties. 
  
2. Sla de records op als u klaar bent.
    
::: moniker-end

::: moniker range="o365-21vianet"

Volg onderstaande stappen om de drie CNAME-records toe te voegen die zijn vereist voor Office 365. Als er extra CNAME-records worden weergegeven in Office 365, voegt u die toe aan de hand van dezelfde algemene stappen die hier worden weergegeven.
  
Op de website van uw DNS-host maakt u drie nieuwe CNAME-records, meestal één voor één.
  
1. Typ of kopieer en plak de volgende waarden in de vakken voor elke nieuwe record. Nadat u elk van de eerste drie nieuwe records hebt toegevoegd, kiest u om nog een CNAME-record te maken.
    
|||||
|:-----|:-----|:-----|:-----|
|**Recordtype** <br/> |**Host** <br/> |**Verwijst naar** <br/> |**TTL** <br/> |
|CNAME (alias)  <br/> |autodiscover  <br/> |autodiscover.partner.outlook.cn  <br/> |1 uur  <br/> |
|CNAME (alias)  <br/> |lyncdiscover  <br/> |webdir.online.partner.lync.cn  <br/> |1 uur  <br/> |
|CNAME (alias)  <br/> |sip  <br/> |sipdir.online.partner.lync.cn  <br/> |1 uur  <br/> |
   
   > [!NOTE]
   > Voor **TTL**: Stel deze waarde in op **1 uur** of op het equivalent in minuten (**60**), seconden (**3600**) enzovoort. > Deze records zijn niet van toepassing op Exchange-, Lync- of Skype voor bedrijven-hybride implementaties. 
  
2. Sla de records op als u klaar bent.
    
::: moniker-end

## <a name="add-two-cname-records-for-mobile-device-management-mdm-for-office-365"></a>Twee CNAME-records voor MDM (Mobile Device Management) voor Office 365 toevoegen
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

> [!IMPORTANT]
> Als u Mobile Device Management (MDM) voor Office 365 hebt, moet u twee extra CNAME-records maken. Volg de stappen die u hebt gevolgd voor de andere vier CNAME-records, maar gebruik de waarden uit de volgende tabel. > (Als u geen MDM hebt, kunt u deze stap overslaan.) 
  
|||||
|:-----|:-----|:-----|:-----|
|**Recordtype** <br/> |**Host** <br/> |**Verwijst naar** <br/> |**TTL** <br/> |
|CNAME (alias)  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |1 uur  <br/> |
|CNAME (alias)  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment.manage.microsoft.com  <br/> |1 uur  <br/> |
   
::: moniker-end

::: moniker range="o365-germany"

> [!IMPORTANT]
> Als u Mobile Device Management (MDM) voor Office 365 hebt, moet u twee extra CNAME-records maken. Volg de stappen die u hebt gevolgd voor de andere vier CNAME-records, maar gebruik de waarden uit de volgende tabel. > (Als u geen MDM hebt, kunt u deze stap overslaan.) 
  
|||||
|:-----|:-----|:-----|:-----|
|**Recordtype** <br/> |**Host** <br/> |**Verwijst naar** <br/> |**TTL** <br/> |
|CNAME (alias)  <br/> |enterpriseregistration  <br/> |enterpriseregistration.microsoftonline.de  <br/> |1 uur  <br/> |
|CNAME (alias)  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |1 uur  <br/> |
   
::: moniker-end

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Een TXT-record voor SPF toevoegen om spam tegen te gaan
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

> [!IMPORTANT]
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Office 365 te maken. In plaats daarvan voegt u de vereiste Office 365-waarden toe aan de huidige record, zodat u beschikt over  *één*  SPF-record waarin beide sets waarden zijn opgenomen.
  
Op de website van uw DNS-host, bewerkt u de bestaande SPF-record of maakt u een nieuwe TXT-record voor SPF.
  
> [!IMPORTANT]
> SPF is ontworpen om spoofing te voorkomen, maar er zijn spoofing-technieken waartegen SPF geen bescherming kan bieden. Om u tegen deze technieken te beschermen, moet u, nadat u SPF hebt geconfigureerd, ook DKIM en DMARC voor Office 365 configureren. Raadpleeg [DKIM gebruiken om uitgaande e-mail te valideren die wordt verzonden vanaf uw domein in Office 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx). Zie vervolgens [DMARC gebruiken om e-mail in Office 365 te valideren](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx). 
  
1. Typ of kopieer en plak in de vakken voor de nieuwe record de verzameling waarden hieronder die op uw situatie van toepassing zijn.
    
|||||
|:-----|:-----|:-----|:-----|
|**Recordtype** <br/> |**Host** <br/> |**TXT-waarde** <br/> |**TTL** <br/> |
|TXT (Text)  <br/> |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.           |1 uur  <br/> |
   
   Voor **TTL**: stel deze waarde in op **1 uur** of op het equivalent in minuten (**60**), seconden (**3600**), enzovoort. 
    
2. Sla de record op als u klaar bent.
    
3. Voor het valideren van uw SPF-record gebruikt u een van deze [SPF-validatiehulpmiddelen](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)

::: moniker-end

::: moniker range="o365-germany"

> [!IMPORTANT]
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Office 365 te maken. In plaats daarvan voegt u de vereiste Office 365-waarden toe aan de huidige record, zodat u beschikt over  *één*  SPF-record waarin beide sets waarden zijn opgenomen. 
  
Op de website van uw DNS-host, bewerkt u de bestaande SPF-record of maakt u een nieuwe TXT-record voor SPF.
  
> [!IMPORTANT]
> SPF is ontworpen om spoofing te voorkomen, maar er zijn spoofing-technieken waartegen SPF geen bescherming kan bieden. Om u tegen deze technieken te beschermen, moet u, nadat u SPF hebt geconfigureerd, ook DKIM en DMARC voor Office 365 configureren. Raadpleeg [DKIM gebruiken om uitgaande e-mail te valideren die wordt verzonden vanaf uw domein in Office 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx). Zie vervolgens [DMARC gebruiken om e-mail in Office 365 te valideren](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx). 
  
1. Typ of kopieer en plak in de vakken voor de nieuwe record de verzameling waarden hieronder die op uw situatie van toepassing zijn.
    
|||||
|:-----|:-----|:-----|:-----|
|**Recordtype**|**Host**|**TXT-waarde**|**TTL**|
|TXT (Text)|@|v=spf1 include:spf.protection.outlook.de -all <br/>  Het is raadzaam dit item te kopiëren en te plakken, zodat alle spatiëring ongewijzigd blijft.           |1 uur|
   
   Voor **TTL**: stel deze waarde in op **1 uur** of op het equivalent in minuten (**60**), seconden (**3600**), enzovoort. 
    
2. Sla de record op als u klaar bent.
    
3. Voor het valideren van uw SPF-record gebruikt u een van deze [SPF-validatiehulpmiddelen](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)
    
::: moniker-end

::: moniker range="o365-21vianet"

> [!IMPORTANT]
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Office 365 te maken. In plaats daarvan voegt u de vereiste Office 365-waarden toe aan de huidige record, zodat u beschikt over  *één*  SPF-record waarin beide sets waarden zijn opgenomen. 
  
Op de website van uw DNS-host, bewerkt u de bestaande SPF-record of maakt u een nieuwe TXT-record voor SPF.
  
> [!IMPORTANT]
> SPF is ontworpen om spoofing te voorkomen, maar er zijn spoofing-technieken waartegen SPF geen bescherming kan bieden. Om u tegen deze technieken te beschermen, moet u, nadat u SPF hebt geconfigureerd, ook DKIM en DMARC voor Office 365 configureren. Raadpleeg [DKIM gebruiken om uitgaande e-mail te valideren die wordt verzonden vanaf uw domein in Office 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx). Zie vervolgens [DMARC gebruiken om e-mail in Office 365 te valideren](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx). 
  
1. Typ of kopieer en plak in de vakken voor de nieuwe record de verzameling waarden hieronder die op uw situatie van toepassing zijn.
    
|||||
|:-----|:-----|:-----|:-----|
|**Recordtype**|**Host**|**TXT-waarde**|**TTL**|
|TXT (Text)|@|v=spf1 include:spf.protection.partner.outlook.cn -all> [!NOTE]> Het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.           |1 uur|
   
   Voor **TTL**: stel deze waarde in op **1 uur** of op het equivalent in minuten (**60**), seconden (**3600**), enzovoort. 
    
2. Sla de record op als u klaar bent.
    
3. Voor het valideren van uw SPF-record gebruikt u een van deze [SPF-validatiehulpmiddelen](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)
    
::: moniker-end

## <a name="add-two-srv-records"></a>Twee SRV-records toevoegen
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

Op de website van uw DNS-host maakt u twee nieuwe SRV-records, meestal één voor één. Dit houdt in dat u na het toevoegen van de eerste nieuwe record via de website aangeeft dat u nog een SRV-record wilt maken.
  
1. Typ of kopieer en plak de volgende waarden in de vakken voor elke nieuwe record. **(Zie onderstaande opmerkingen voor het maken van SRV-records maken wanneer uw DNS-host deze niet allemaal als afzonderlijke velden heeft.)**
    
||||||||||
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**Recordtype** <br/> |**Naam** <br/> |**Doel** <br/> |**Protocol** <br/> |**Service** <br/> |**Prioriteit** <br/> |**Gewicht** <br/> |**Poort** <br/> |**TTL** <br/> |
|SRV (service)  <br/> |@  <br/> (Of laat leeg als @ is niet toegestaan)  <br/> |sipdir.online.lync.com  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1 uur  <br/> |
|SRV (service)  <br/> |@  <br/> (Of laat leeg als @ is niet toegestaan)  <br/> |sipfed.online.lync.com  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1 uur  <br/> |
   
  > [!NOTE]
  >  Voor **Naam**: als uw DNS-host niet toestaat dat u dit instelt op **@**, laat u dit vak leeg.  Gebruik deze methode *alleen* wanneer uw DNS-host afzonderlijke velden voor de waarden Service en Protocol heeft. Raadpleeg anders onderstaande opmerkingen bij Service en Protocol. 

>  Voor **Service** en **Protocol**: als uw DNS-host niet in deze velden voor SRV-records voorziet, geeft u de waarden voor **Service** en **Protocol** op als de waarde **Naam** van de record. (Opmerking: Afhankelijk van uw DNS-host kan het veld **Naam** anders heten, als **Host**, **Hostnaam** of **Subdomein**.) Voor het instellen van de gecombineerde waarde maakt u één tekenreeks, waarin de waarden van elkaar zijn gescheiden door een punt.  Bijvoorbeeld: **Naam**: _sip._tls 

>  Voor **Prioriteit**, **Gewicht** en **Poort**: als uw DNS-host niet in deze velden voor SRV-records voorziet, geeft u ze op als de waarde **Doel** van de record. (Opmerking: Afhankelijk van uw DNS-host kan het veld **Doel** anders heten, als **Inhoud**, **IP-adres** of **Doelhost**.) Voor het instellen van de gecombineerde waarde maakt u één tekenreeks, waarin de waarden van elkaar zijn gescheiden door een spatie en sluit u af met een punt. De waarden moeten in de volgende volgorde worden opgenomen: Prioriteit, Gewicht, Poort, Doel. Bijvoorbeeld: **Doel**: 100 1 443 sipdir.online.lync.com. 

>  Variatie voor **Prioriteit**, **Gewicht** en **Poort**: sommige DNS-host bieden enkele, maar niet alle vereiste velden apart. Voor deze DNS-hostsites host geeft u de waarden die niet afzonderlijk worden weergegeven als een gecombineerde tekenreeks op, in de juiste volgorde, bij de waarde **Doel** van de record. (Opmerking: Afhankelijk van uw DNS-host kan het veld **Doel** anders heten, als **Inhoud**, **IP-adres** of **Doelhost**.) Voor het instellen van de gecombineerde waarde maakt u één tekenreeks voor de velden die niet afzonderlijk worden weergegeven, waarin de waarden van elkaar zijn gescheiden door spaties. De waarden moeten worden opgenomen *in de juiste volgorde*, waarbij waarden waarvoor afzonderlijke velden beschikbaar zijn, worden weggelaten: Prioriteit, Gewicht, Poort, Doel. Wanneer er voor Prioriteit bijvoorbeeld een apart veld is, voegt u alleen de waarden voor Gewicht, Poort en Doel samen: **Doel**: 1 443 sipdir.online.lync.com 

> Voor **TTL**: stel deze waarde in op **1 uur** of op het equivalent in minuten (**60**), seconden (**3600**), enzovoort. 
  
2. Sla de records op als u klaar bent.
    
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
::: moniker-end


::: moniker range="o365-germany"

Op de website van uw DNS-host maakt u twee nieuwe SRV-records, meestal één voor één. Dit houdt in dat u na het toevoegen van de eerste nieuwe record via de website aangeeft dat u nog een SRV-record wilt maken.
  
1. Typ of kopieer en plak de volgende waarden in de vakken voor elke nieuwe record. **(Zie onderstaande opmerkingen voor het maken van SRV-records maken wanneer uw DNS-host deze niet allemaal als afzonderlijke velden heeft.)**
    
||||||||||
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**Recordtype** <br/> |**Naam** <br/> |**Doel** <br/> |**Protocol** <br/> |**Service** <br/> |**Prioriteit** <br/> |**Gewicht** <br/> |**Poort** <br/> |**TTL** <br/> |
|SRV (service)  <br/> |@  <br/> (Of laat leeg als @ is niet toegestaan)  <br/> |sipdir.online.lync.de  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1 uur  <br/> |
|SRV (service)  <br/> |@  <br/> (Of laat leeg als @ is niet toegestaan)  <br/> |sipfed.online.lync.de  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1 uur  <br/> |
   
 > [!NOTE]
 >  Voor **Naam**: als uw DNS-host niet toestaat dat u dit instelt op **@**, laat u dit vak leeg.  Gebruik deze methode *alleen* wanneer uw DNS-host afzonderlijke velden voor de waarden Service en Protocol heeft. Raadpleeg anders onderstaande opmerkingen bij Service en Protocol. 

>  Voor **Service** en **Protocol**: als uw DNS-host niet in deze velden voor SRV-records voorziet, geeft u de waarden voor **Service** en **Protocol** op als de waarde **Naam** van de record. (Opmerking: Afhankelijk van uw DNS-host kan het veld **Naam** anders heten, als **Host**, **Hostnaam** of **Subdomein**.) Voor het instellen van de gecombineerde waarde maakt u één tekenreeks, waarin de waarden van elkaar zijn gescheiden door een punt. >  Bijvoorbeeld: **Naam**: _sip._tls 

>  Voor **Prioriteit**, **Gewicht** en **Poort**: als uw DNS-host niet in deze velden voor SRV-records voorziet, geeft u ze op als de waarde **Doel** van de record. (Opmerking: Afhankelijk van uw DNS-host kan het veld **Doel** anders heten, als **Inhoud**, **IP-adres** of **Doelhost**.) Voor het instellen van de gecombineerde waarde maakt u één tekenreeks, waarin de waarden van elkaar zijn gescheiden door een spatie en sluit u af met een punt. De waarden moeten in de volgende volgorde worden opgenomen: Prioriteit, Gewicht, Poort, Doel. >  Bijvoorbeeld: **Doel**: 100 1 443 sipdir.online.lync.de. 

>  Variatie voor **Prioriteit**, **Gewicht** en **Poort**: sommige DNS-host bieden enkele, maar niet alle vereiste velden apart. Voor deze DNS-hostsites host geeft u de waarden die niet afzonderlijk worden weergegeven als een gecombineerde tekenreeks op, in de juiste volgorde, bij de waarde **Doel** van de record. (Opmerking: Afhankelijk van uw DNS-host kan het veld **Doel** anders heten, als **Inhoud**, **IP-adres** of **Doelhost**.) Voor het instellen van de gecombineerde waarde maakt u één tekenreeks voor de velden die niet afzonderlijk worden weergegeven, waarin de waarden van elkaar zijn gescheiden door spaties. De waarden moeten worden opgenomen *in de juiste volgorde*, waarbij waarden waarvoor afzonderlijke velden beschikbaar zijn, worden weggelaten: Prioriteit, Gewicht, Poort, Doel. >  Wanneer er voor Prioriteit bijvoorbeeld een apart veld is, voegt u alleen de waarden voor Gewicht, Poort en Doel samen: **Doel**: 1 443 sipdir.online.lync.de 

>  Voor **TTL**: stel deze waarde in op **1 uur** of op het equivalent in minuten (**60**), seconden (**3600**), enzovoort. 
  
2. Sla de records op als u klaar bent.
    
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
::: moniker-end


::: moniker range="o365-21vianet"

Op de website van uw DNS-host maakt u twee nieuwe SRV-records, meestal één voor één. Dit houdt in dat u na het toevoegen van de eerste nieuwe record via de website aangeeft dat u nog een SRV-record wilt maken.
  
1. Typ of kopieer en plak de volgende waarden in de vakken voor elke nieuwe record. **(Zie onderstaande opmerkingen voor het maken van SRV-records maken wanneer uw DNS-host deze niet allemaal als afzonderlijke velden heeft.)**
    
||||||||||
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**Recordtype** <br/> |**Naam** <br/> |**Doel** <br/> |**Protocol** <br/> |**Service** <br/> |**Prioriteit** <br/> |**Gewicht** <br/> |**Poort** <br/> |**TTL** <br/> |
|SRV (service)  <br/> |@  <br/> (Of laat leeg als @ is niet toegestaan)  <br/> |sipdir.online.partner.lync.cn  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1 uur  <br/> |
|SRV (service)  <br/> |@  <br/> (Of laat leeg als @ is niet toegestaan)  <br/> |sipfed.online.partner.lync.cn  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1 uur  <br/> |
   
 > [!NOTE]
 >  Voor **Naam**: als uw DNS-host niet toestaat dat u dit instelt op **@**, laat u dit vak leeg.  Gebruik deze methode *alleen* wanneer uw DNS-host afzonderlijke velden voor de waarden Service en Protocol heeft. Raadpleeg anders onderstaande opmerkingen bij Service en Protocol. 

>  Voor **Service** en **Protocol**: als uw DNS-host niet in deze velden voor SRV-records voorziet, geeft u de waarden voor **Service** en **Protocol** op als de waarde **Naam** van de record. (Opmerking: Afhankelijk van uw DNS-host kan het veld **Naam** anders heten, als **Host**, **Hostnaam** of **Subdomein**.) Voor het instellen van de gecombineerde waarde maakt u één tekenreeks, waarin de waarden van elkaar zijn gescheiden door een punt. >  Bijvoorbeeld: **Naam**: _sip._tls 

>  Voor **Prioriteit**, **Gewicht** en **Poort**: als uw DNS-host niet in deze velden voor SRV-records voorziet, geeft u ze op als de waarde **Doel** van de record. (Opmerking: Afhankelijk van uw DNS-host kan het veld **Doel** anders heten, als **Inhoud**, **IP-adres** of **Doelhost**.) Voor het instellen van de gecombineerde waarde maakt u één tekenreeks, waarin de waarden van elkaar zijn gescheiden door een spatie en sluit u af met een punt. De waarden moeten in de volgende volgorde worden opgenomen: Prioriteit, Gewicht, Poort, Doel. >  Bijvoorbeeld: **Doel**: 100 1 443 sipdir.online.partner.lync.cn. 

>  Variatie voor **Prioriteit**, **Gewicht** en **Poort**: sommige DNS-host bieden enkele, maar niet alle vereiste velden apart. Voor deze DNS-hostsites host geeft u de waarden die niet afzonderlijk worden weergegeven als een gecombineerde tekenreeks op, in de juiste volgorde, bij de waarde **Doel** van de record. (Opmerking: Afhankelijk van uw DNS-host kan het veld **Doel** anders heten, als **Inhoud**, **IP-adres** of **Doelhost**.) Voor het instellen van de gecombineerde waarde maakt u één tekenreeks voor de velden die niet afzonderlijk worden weergegeven, waarin de waarden van elkaar zijn gescheiden door spaties. De waarden moeten worden opgenomen *in de juiste volgorde*, waarbij waarden waarvoor afzonderlijke velden beschikbaar zijn, worden weggelaten: Prioriteit, Gewicht, Poort, Doel. >  Wanneer er voor Prioriteit bijvoorbeeld een apart veld is, voegt u alleen de waarden voor Gewicht, Poort en Doel samen: **Doel**: 1 443 sipdir.online.partner.lync.cn 

>  Voor **TTL**: stel deze waarde in op **1 uur** of op het equivalent in minuten (**60**), seconden (**3600**), enzovoort. 
  
2. Sla de records op als u klaar bent.
    
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
::: moniker-end

## <a name="more-about-updating-dns-records"></a>Meer informatie over het bijwerken van DNS-records
<a name="BKMK_MoreAbout"> </a>

 **Als u weet hoe u DNS-records moet bijwerken bij de DNS-host van uw domein**, gebruikt u de DNS-waarden in Office 365 om records te bewerken bij de DNS-host van uw domein, bijvoorbeeld om een MX-record of SPF-record in te stellen. Zoek de specifieke waarden die u moet gebruiken door [deze stappen te volgen](../get-help-with-domains/information-for-dns-records.md) of bekijk ze in de wizard voor het instellen van domeinen terwijl u de wizard doorloopt.
  
 Zie [Uw domein instellen (host-specifieke instructies)](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions?view=o365-worldwide), **als u hulp nodig hebt bij het toevoegen van de vereiste DNS-records**, moet u eerst [de informatie verzamelen die u nodig hebt om DNS-records voor Office 365 te maken](../get-help-with-domains/information-for-dns-records.md). Gebruik vervolgens de algemene stappen in dit onderwerp om de DNS-records van uw domein in te stellen, zodat u uw domein kunt gebruiken met Office 365-services, als e-mail.
  
 **Als u nog geen website gebruikt voor uw aangepaste domein**, kunt u Office 365 DNS-records voor uw domein laten instellen en beheren in plaats van dat u het zelf doet. Meer informatie over de [twee opties voor het instellen en beheren van DNS-records voor een aangepast domein](https://support.office.com/article/5980474a-097f-4f21-a864-21245314957f.aspx) in Office 365. 
  

