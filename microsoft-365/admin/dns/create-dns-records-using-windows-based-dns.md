---
title: DNS-records voor Microsoft maken met Windows-DNS
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
ms.assetid: 9eec911d-5773-422c-9593-40e1147ffbde
description: Lees hoe u uw domein verifieert en DNS-records instelt voor e-mail, Skype voor bedrijven online en andere services op basis van Windows-DNS voor Microsoft.
ms.openlocfilehash: 471aa0323bd59b09c672431ef39bb33f5c89b555
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645573"
---
# <a name="create-dns-records-for-microsoft-using-windows-based-dns"></a>DNS-records voor Microsoft maken met Windows-DNS

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
   
Als u uw eigen DNS-records met Windows-DNS host, volgt u de stappen in dit artikel voor het instellen van uw records voor e-mail, Skype voor Bedrijven Online, enzovoort.
  
Om aan de slag te gaan, moet u [de DNS-records vinden in Windows-DNS](#find-your-dns-records-in-windows-based-dns) , zodat u deze kunt bijwerken. Als u uw on-premises Active Directory met Microsoft wilt synchroniseren, raadpleegt u [niet-routeerbaar e-mailadres gebruikt als een UPN in de on-premises Active Directory](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory).
  
Problemen met de e-mail stroom of andere problemen nadat u DNS-records hebt toegevoegd, raadpleegt [u problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a>Uw DNS-records vinden in Windows-DNS
<a name="BKMK_find_your_dns_1"> </a> Ga naar de pagina met de DNS-records voor uw domein. Als u met Windows Server 2008 werkt, gaat u naar **Start**  >  **Run**. Als u werkt met Windows Server 2012, drukt u op de Windows-toets en op **r**. Typ **dnsmgmnt. msc**en selecteer **OK**. Vouw in DNS-beheer de optie ** \<DNS server name\> \> zones voor forward lookup  **uit. Selecteer uw domein. Nu kunt u de DNS-records gaan maken.
   
## <a name="add-mx-record"></a>MX-record toevoegen
<a name="BKMK_add_MX"> </a>

Voeg een MX-record toe zodat e-mail voor uw domein bij Microsoft komt.
- De MX-record die u toevoegt, bevat een waarde (de waarde **adres waarnaar wordt verwezen** ) die er ongeveer zo uitziet: \<MX token\> . mail.Protection.Outlook.com, waarin \<MX token\> een waarde is zoals MSxxxxxxx. 
- Vanuit de rij MX in de sectie Exchange Online van de pagina DNS-records toevoegen in Microsoft kopieert u de waarde die wordt vermeld onder adres waarnaar wordt verwezen. U gebruikt deze waarde in de record die u in deze taak maakt. 
- Ga op de pagina DNS-beheer voor het domein naar **Action**  >  **Mail Exchanger (MX)**. Zie [uw DNS-records vinden in Windows-DNS](#find-your-dns-records-in-windows-based-dns)om deze pagina voor het domein te vinden.  
- Controleer in het dialoogvenster **nieuwe bron record** of de velden zijn ingesteld op precies de volgende waarden: 
    - Hostnaam:  
    - @Address: plak de waarde van het adres waarnaar wordt verwezen die u zojuist uit Microsoft hebt gekopieerd.  
    - Pref 
- Selecteer **Save Changes**.
- Verouderde MX-records verwijderen. Als u oude MX-records voor dit domein hebt waarmee e-mail naar een andere locatie wordt doorgestuurd **, schakelt u**het selectievakje naast elke verouderde record in en selecteert u vervolgens  >  **OK**. 
   
## <a name="add-cname-records"></a>CNAME-records toevoegen
<a name="BKMK_add_CNAME"> </a>

Voeg de CNAME-records toe die voor Microsoft vereist zijn. Als er extra CNAME-records worden weergegeven in Microsoft, voegt u de volgende algemene stappen toe.
  
> [!IMPORTANT]
> Als u over MDM (Mobile Device Management) voor Microsoft beschikt, moet u twee extra CNAME-records maken. Volg de stappen die u hebt gevolgd voor de andere vier CNAME-records, maar gebruik de waarden uit de volgende tabel. (Als u geen MDM hebt, kunt u deze stap overslaan.) 

- Ga op de pagina DNS-beheer voor het domein naar **actie**  >  **CNAME (CNAME)**.
- Controleer in het dialoogvenster **nieuwe bron record** of de velden zijn ingesteld op precies de volgende waarden:  
    - Hostnaam: automatisch opsporen
    - Typ 
    - CNAMEAddress: autodiscover.outlook.com
- Selecteer **O**K.

Voeg de SIP CNAME-record toe. 
- Ga op de pagina DNS-beheer voor het domein naar **actie** \> **CNAME (CNAME)**. 
- Controleer in het dialoogvenster **nieuwe bron record** of de velden zijn ingesteld op precies de volgende waarden:  
    - Host name: SIP
    - Type: CNAME
    - Adres: sipdir.online.lync.com
- Selecteer **OK**.

Voeg de Skype voor Bedrijven Online Autodiscover CNAME-record toe.  
- Ga op de pagina DNS-beheer voor het domein naar **actie** \> **CNAME (CNAME)**. Controleer in het dialoogvenster **nieuwe bron record** of de velden zijn ingesteld op precies de volgende waarden:  
    - Host name: lyncdiscover
    - Type: CNAME
    - Adres: webdir.online.lync.com
- Selecteer **OK**.
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-microsoft"></a>Twee CNAME-records voor MDM (Mobile Device Management) voor Microsoft toevoegen

> [!IMPORTANT]
> Als u over MDM (Mobile Device Management) voor Microsoft beschikt, moet u twee extra CNAME-records maken. Volg de stappen die u hebt gevolgd voor de andere vier CNAME-records, maar gebruik de waarden uit de volgende tabel. > (als u geen MDM hebt, kunt u deze stap overslaan.) 
  

Voeg de MDM Enterpriseregistration CNAME-record toe.  
- Ga op de pagina DNS-beheer voor het domein naar **actie** \> **CNAME (CNAME)**. 
- Controleer in het dialoogvenster **nieuwe bron record** of de velden zijn ingesteld op precies de volgende waarden:  
- Host name: enterpriseregistration
- Type: CNAME
- Adres: enterpriseregistration.windows.net
- Selecteer **OK**. 

Voeg de MDM Enterpriseenrollment CNAME-record toe. 
-  Ga op de pagina DNS-beheer voor het domein naar **actie** \> **CNAME (CNAME)**. 
-  Controleer in het dialoogvenster **nieuwe bron record** of de velden zijn ingesteld op precies de volgende waarden:  
    - Host name: enterpriseenrollment
    - Type: CNAME
    - Adres: enterpriseenrollment-s.manage.microsoft.com
- Selecteer **OK**.
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Een TXT-record voor SPF toevoegen om spam tegen te gaan
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft. In plaats daarvan voegt u de vereiste Microsoft-waarden toe aan de huidige record, zodat u  *één*  SPF-record hebt die beide sets met waarden bevat. 
  
Voeg de SPF TXT-record voor uw domein om spam te voorkomen.
  
- Mogelijk hebt u al andere tekenreeksen in de TXT-waarde voor deze record (zoals tekenreeksen voor marketing-e-mail). Dit is geen probleem. Laat deze tekenreeksen staan en voeg deze toe, plaats dubbele aanhalingstekens rond elke tekenreeks om ze te scheiden. 
- Ga op de pagina DNS-beheer voor uw domein naar **actie** \> **tekst (txt)**. 
-  Controleer in het dialoogvenster **nieuwe bron record** of de velden zijn ingesteld op precies de volgende waarden. 
 > [!IMPORTANT]
> In sommige versies van Windows DNS-beheer is het domein mogelijk ingesteld, zodat wanneer u een TXT-record maakt, de naam van het bovenliggende domein standaard wordt ingesteld op de naam van de basismap. Als u in deze situatie een TXT-record toevoegt, stelt u de hostnaam in op leeg (geen waarde) in plaats van op @ of de domeinnaam. 

-  Host type: @
-  Record type: TXT
-  Adres: v = spf1 include:SPF. Protection. Outlook. com-all 
         
-  Selecteer **OK**.
   
## <a name="add-srv-records"></a>SRV-records toevoegen
<a name="BKMK_add_SRV"> </a>

Voeg de twee SRV-records toe die voor Microsoft vereist zijn.

Voeg de SIP SRV-record voor Skype voor Bedrijven Online-webconferenties toe.  <br/> 
-  Ga op de pagina DNS-beheer voor uw domein naar **actie** \> **andere nieuwe records**. 
-   Selecteer in het venster **type bron record** de optie **SRV (Service Location)** en selecteer vervolgens **record maken**. 
-   Controleer in het dialoogvenster **nieuwe bron record** of de velden zijn ingesteld op precies de volgende waarden:  
    -  Service: _sip
    -  Protocol: _tls
    -  Prioriteit: 100
    -  Gewicht: 1
    -  Poort: 443
    -  Doel (hostnaam): sipdir.online.lync.com
-  Selecteer **OK**. 


Voeg de SIP SRV-record voor Skype voor Bedrijven Online-federatie toe.  
-  Ga op de pagina DNS-beheer voor uw domein naar **actie** \> **andere nieuwe records**.  
-  Selecteer in het venster **type bron record** de optie **SRV (Service Location)** en selecteer vervolgens **record maken**. 
-   Controleer in het dialoogvenster **nieuwe bron record** of de velden zijn ingesteld op precies de volgende waarden:  
    -  Service: _sipfederationtls
    -  Protocol: _tcp
    -  Prioriteit: 100
    -  Gewicht: 1
    -  Poort: 5061
    -  Doel (hostnaam): sipfed.online.lync.com
-  Selecteer **OK**. 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a>Een record toevoegen om te verifiëren dat u eigenaar bent van het domein, als dit nog niet is gedaan
<a name="BKMK_verify"> </a>

Voordat u de DNS-records toevoegt voor het instellen van uw Microsoft-services, moet Microsoft bevestigen dat u de eigenaar bent van het domein dat u wilt toevoegen. Hiertoe voegt u een record toe aan de hand van onderstaande stappen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. 
  

1. Gegevens van Microsoft verzamelen.  <br/> 
2. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina. 
3. Selecteer op de pagina **Domains** in de kolom **Actions** de optie **Setup starten**voor het domein dat u wilt verifiëren. 
4. Selecteer op de pagina **een domein toevoegen aan Microsoft** de optie **begin met stap 1**. 
5. Op de pagina **Bevestig dat u de eigenaar bent van uw domein** , in de vervolgkeuzelijst **Zie de instructies voor de uitvoering van deze stap met** , kiest u de optie **algemene instructies**. 
6. Kopieer vanuit de tabel de waarde Doel of adres waarnaar wordt verwezen. Deze hebt u nodig voor de volgende stap. Het is raadzaam deze waarde te kopiëren en te plakken, zodat alle spatiëring ongewijzigd blijft.

Voeg een TXT-record toe. 
-  Ga op de pagina DNS-beheer voor uw domein naar **actie** \> **tekst (txt)**. 
-   Selecteer in het dialoogvenster **nieuwe bron record** de optie **bewerken**.  
-  Controleer in het gebied **Custom host names** van het dialoogvenster **nieuwe bron record** of de velden zijn ingesteld op precies de volgende waarden. 

> [!IMPORTANT] 
> In sommige versies van Windows DNS-beheer is het domein mogelijk ingesteld, zodat wanneer u een TXT-record maakt, de naam van het bovenliggende domein standaard wordt ingesteld op de naam van de basismap. Als u in deze situatie een TXT-record toevoegt, stelt u de hostnaam in op leeg (geen waarde) in plaats van op @ of de domeinnaam. 

- Naam host: @
- Typ: TXT
- Adres: plak de waarde van bestemming of verwijzen naar adres die u zojuist uit Microsoft hebt gekopieerd.  
- Selecteer **OK**  >  **Done**.

Uw domein in Microsoft verifiëren.  
> [!IMPORTANT]
> Wacht ongeveer 15 minuten voordat u dit doet, zodat de record die u zojuist hebt gemaakt op internet kan worden bijgewerkt.       

- Ga terug naar Microsoft en volg de onderstaande stappen om een verificatiecontrole aan te vragen. Er wordt gecontroleerd op de TXT-record die u in de vorige stap hebt toegevoegd. Wanneer de juiste TXT-record wordt gevonden, wordt het domein geverifieerd.  
1. Ga in het Beheercentrum naar de pagina **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domeinen</a> instellen.
2. Selecteer op de pagina **Domains** in de kolom **Action** de optie **Setup starten**voor het domein dat u wilt verifiëren. 
3. Selecteer **gedaan, nu controleren**op de pagina **Bevestig dat u eigenaar bent van uw domein** en selecteer **Voltooien**in het bevestigingsdialoogvenster. 
   
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a>Niet-routeerbaar e-mailadres gebruikt als een UPN in de on-premises Active Directory
<a name="BKMK_ADNote"> </a>

Als u de synchronisatie van uw on-premises Active Directory met Microsoft wilt synchroniseren, moet u ervoor zorgen dat het achtervoegsel van de Active Directory User Principal Name (UPN) een geldig domeinachtervoegsel is en geen niet-ondersteund domeinachtervoegsel, zoals @contoso. local. Als u het UPN-achtervoegsel moet wijzigen, raadpleegt u [een niet-routeerbaar domein voorbereiden op adreslijstsynchronisatie](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).
  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
