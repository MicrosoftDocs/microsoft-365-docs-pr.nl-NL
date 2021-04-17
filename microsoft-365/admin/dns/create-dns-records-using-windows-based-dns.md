---
title: DNS-records voor Microsoft maken met windows-DNS
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
description: Informatie over het verifiëren van uw domein en het instellen van DNS-records voor e-mail, Skype voor Bedrijven Online en andere services bij windows-DNS voor Microsoft.
ms.openlocfilehash: fd7c56b6db9fe5f5dbb0637ad5abcb40a64bef8f
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876347"
---
# <a name="create-dns-records-for-microsoft-using-windows-based-dns"></a>DNS-records voor Microsoft maken met windows-DNS

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt. 
   
Als u uw eigen DNS-records met Windows-DNS host, volgt u de stappen in dit artikel voor het instellen van uw records voor e-mail, Skype voor Bedrijven Online, enzovoort.
  
Om aan de slag te gaan, moet u [uw DNS-records zoeken in windows-DNS,](#find-your-dns-records-in-windows-based-dns) zodat u ze kunt bijwerken. Als u van plan bent uw on-premises Active Directory te synchroniseren met Microsoft, zie Niet-routable email address used as a [UPN in your on-prem Active Directory](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory).
  
Problemen met de e-mailstroom of andere problemen na het toevoegen van DNS-records, zie Problemen oplossen na het wijzigen van uw domeinnaam [of DNS-records.](../get-help-with-domains/find-and-fix-issues.md) 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a>Uw DNS-records vinden in Windows-DNS
<a name="BKMK_find_your_dns_1"></a> Ga naar de pagina met de DNS-records voor uw domein. Als u in een Windows Server 2008 werkt, gaat u naar **Start**  >  **Run**. Als u werkt in Windows Server 2012, drukt u op de Windows-toets en **r**. Typ **dnsmgmnt.msc** en selecteer **OK.** Vouw in DNS Manager **\<DNS server name\> \> opzoekzones doorsturen uit.** Selecteer uw domein. Nu kunt u de DNS-records gaan maken.
   
## <a name="add-mx-record"></a>MX-record toevoegen
<a name="BKMK_add_MX"> </a>

Voeg een MX-record toe, zodat e-mail voor uw domein naar Microsoft komt.
- De MX-record die u toevoegt, bevat een waarde (de waarde Punten naar adres) die er zo uitziet: .mail.protection.outlook.com, waarbij een waarde is zoals  \<MX token\> \<MX token\> MSxxxxxxxxx. 
- Kopieer in de rij MX in de sectie Exchange Online van de pagina DNS-records toevoegen in Microsoft de waarde die wordt vermeld onder Punten naar adres. U gebruikt deze waarde in de record die u in deze taak maakt. 
- Ga op de pagina DNS Manager voor het domein naar **Action**  >  **Mail Exchanger (MX)**. Zie Uw [DNS-records zoeken in windows-DNS](#find-your-dns-records-in-windows-based-dns)als u deze pagina voor het domein wilt zoeken.  
- Zorg er **in het dialoogvenster** Nieuwe resourcerecord voor dat de velden precies zijn ingesteld op de volgende waarden: 
    - Hostnaam:  
    - @Address: Plak hier de waarde punten naar adres die u zojuist vanuit Microsoft hebt gekopieerd.  
    - Pref: 
- Selecteer **Wijzigingen opslaan.**
- Verouderde MX-records verwijderen. Als u oude MX-records voor dit domein hebt die e-mail ergens anders naartoe sturen, schakel dan het selectievakje naast elke oude record in en selecteer **vervolgens**  >  **OK verwijderen.** 
   
## <a name="add-cname-records"></a>CNAME-records toevoegen
<a name="BKMK_add_CNAME"> </a>

Voeg de CNAME-records toe die vereist zijn voor Microsoft. Als er extra CNAME-records worden weergegeven in Microsoft, voegt u deze toe volgens dezelfde algemene stappen die hier worden weergegeven.
  
> [!IMPORTANT]
> Als u Mobile Device Management (MDM) voor Microsoft hebt, moet u twee extra CNAME-records maken. Volg de stappen die u hebt gevolgd voor de andere vier CNAME-records, maar gebruik de waarden uit de volgende tabel. (Als u geen MDM hebt, kunt u deze stap overslaan.) 

- Ga op de pagina DNS Manager voor het domein naar **Actie**  >  **CNAME (CNAME)**.
- Zorg er **in het dialoogvenster** Nieuwe resourcerecord voor dat de velden precies zijn ingesteld op de volgende waarden:  
    - Host name: autodiscover
    - Typ: 
    - CNAMEAddress: autodiscover.outlook.com
- Selecteer **O** K.

Voeg de SIP CNAME-record toe. 
- Ga op de pagina DNS Manager voor het domein naar **Actie** \> **CNAME (CNAME)**. 
- Zorg er **in het dialoogvenster** Nieuwe resourcerecord voor dat de velden precies zijn ingesteld op de volgende waarden:  
    - Hostnaam: sip
    - Type: CNAME
    - Adres: sipdir.online.lync.com
- Selecteer **OK**.

Voeg de Skype voor Bedrijven Online Autodiscover CNAME-record toe.  
- Ga op de pagina DNS Manager voor het domein naar **Actie** \> **CNAME (CNAME)**. Zorg er **in het dialoogvenster** Nieuwe resourcerecord voor dat de velden precies zijn ingesteld op de volgende waarden:  
    - Hostnaam: lyncdiscover
    - Type: CNAME
    - Adres: webdir.online.lync.com
- Selecteer **OK**.
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-microsoft"></a>Twee CNAME-records toevoegen voor Mobile Device Management (MDM) voor Microsoft

> [!IMPORTANT]
> Als u Mobile Device Management (MDM) voor Microsoft hebt, moet u twee extra CNAME-records maken. Volg de stappen die u hebt gevolgd voor de andere vier CNAME-records, maar gebruik de waarden uit de volgende tabel. >(Als u geen MDM hebt, kunt u deze stap overslaan.) 
  

Voeg de MDM Enterpriseregistration CNAME-record toe.  
- Ga op de pagina DNS Manager voor het domein naar **Actie** \> **CNAME (CNAME)**. 
- Zorg er **in het dialoogvenster** Nieuwe resourcerecord voor dat de velden precies zijn ingesteld op de volgende waarden:  
- Hostnaam: enterpriseregistration
- Type: CNAME
- Adres: enterpriseregistration.windows.net
- Selecteer **OK**. 

Voeg de MDM Enterpriseenrollment CNAME-record toe. 
-  Ga op de pagina DNS Manager voor het domein naar **Actie** \> **CNAME (CNAME)**. 
-  Zorg er **in het dialoogvenster** Nieuwe resourcerecord voor dat de velden precies zijn ingesteld op de volgende waarden:  
    - Hostnaam: enterpriseenrollment
    - Type: CNAME
    - Adres: enterpriseenrollment-s.manage.microsoft.com
- Selecteer **OK**.
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Een TXT-record voor SPF toevoegen om spam tegen te gaan
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft. Voeg in plaats daarvan de vereiste Microsoft-waarden  toe aan de huidige record, zodat u één SPF-record hebt met beide sets waarden. 
  
Voeg de SPF TXT-record voor uw domein om spam te voorkomen.
  
- Mogelijk hebt u al andere tekenreeksen in de TXT-waarde voor deze record (zoals tekenreeksen voor marketing-e-mail). Dit is geen probleem. Laat deze tekenreeksen staan en voeg deze toe, plaats dubbele aanhalingstekens rond elke tekenreeks om ze te scheiden. 
- Ga op de pagina DNS Manager  voor uw domein naar \> **Actietekst (TXT)**. 
-  Zorg er **in het dialoogvenster** Nieuwe resourcerecord voor dat de velden precies zijn ingesteld op de volgende waarden. 
 > [!IMPORTANT]
> In sommige versies van Windows DNS Manager is het domein mogelijk zo ingesteld dat wanneer u een txt-record maakt, de thuisnaam standaard wordt gebruikt voor het bovenliggende domein. Als u in deze situatie een TXT-record toevoegt, stelt u de hostnaam in op leeg (geen waarde) in plaats van op @ of de domeinnaam. 

-  Hosttype: @
-  Recordtype: TXT
-  Adres: v=spf1 include:spf.protection.outlook.com -all 
         
-  Selecteer **OK**.
   
## <a name="add-srv-records"></a>SRV-records toevoegen
<a name="BKMK_add_SRV"> </a>

Voeg de twee SRV-records toe die vereist zijn voor Microsoft.

Voeg de SIP SRV-record voor Skype voor Bedrijven Online-webconferenties toe.  <br/> 
-  Ga op de pagina DNS Manager voor uw domein naar **Actie** \> **andere nieuwe records.** 
-   Selecteer in **het venster Resourcerecordtype** de optie **Servicelocatie (SRV)** en selecteer **vervolgens Record maken.** 
-   Zorg er **in het dialoogvenster** Nieuwe resourcerecord voor dat de velden precies zijn ingesteld op de volgende waarden:  
    -  Service: _sip
    -  Protocol: _tls
    -  Prioriteit: 100
    -  Gewicht: 1
    -  Poort: 443
    -  Doel (Hostnaam): sipdir.online.lync.com
-  Selecteer **OK**. 


Voeg de SIP SRV-record voor Skype voor Bedrijven Online-federatie toe.  
-  Ga op de pagina DNS Manager voor uw domein naar **Actie** \> **andere nieuwe records.**  
-  Selecteer in **het venster Resourcerecordtype** de optie **Servicelocatie (SRV)** en selecteer **vervolgens Record maken.** 
-   Zorg er **in het dialoogvenster** Nieuwe resourcerecord voor dat de velden precies zijn ingesteld op de volgende waarden:  
    -  Service: _sipfederationtls
    -  Protocol: _tcp
    -  Prioriteit: 100
    -  Gewicht: 1
    -  Poort: 5061
    -  Doel (hostnaam): sipfed.online.lync.com
-  Selecteer **OK**. 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a>Een record toevoegen om te verifiëren dat u eigenaar bent van het domein, als dit nog niet is gedaan
<a name="BKMK_verify"> </a>

Voordat u de DNS-records toevoegt om uw Microsoft-services in te stellen, moet Microsoft bevestigen dat u de eigenaar bent van het domein dat u toevoegt. Hiertoe voegt u een record toe aan de hand van onderstaande stappen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. 
  

1. Verzamel informatie van Microsoft.  <br/> 
2. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina. 
3. Selecteer op **de pagina** Domeinen in de kolom **Acties** voor het domein dat u verifieert de optie **Installatie starten.** 
4. Selecteer op **de pagina Een domein toevoegen aan Microsoft** stap **1 starten.** 
5. Kies op **de pagina Bevestigen** dat  u de eigenaar bent van uw domein de optie Algemene instructies in de vervolgkeuzelijst Zie instructies voor het uitvoeren van **deze stap.** 
6. Kopieer vanuit de tabel de waarde Doel of adres waarnaar wordt verwezen. Deze hebt u nodig voor de volgende stap. Het is raadzaam deze waarde te kopiëren en te plakken, zodat alle spatiëring ongewijzigd blijft.

Voeg een TXT-record toe. 
-  Ga op de pagina DNS Manager  voor uw domein naar \> **Actietekst (TXT)**. 
-   Selecteer bewerken **in het** dialoogvenster Nieuwe **resourcerecord.**  
-  Zorg ervoor **dat de** velden in het gebied Aangepaste hostnamen van het dialoogvenster **Nieuwe resourcerecord** precies zijn ingesteld op de volgende waarden. 

> [!IMPORTANT] 
> In sommige versies van Windows DNS Manager is het domein mogelijk zo ingesteld dat wanneer u een txt-record maakt, de thuisnaam standaard wordt gebruikt voor het bovenliggende domein. Als u in deze situatie een TXT-record toevoegt, stelt u de hostnaam in op leeg (geen waarde) in plaats van op @ of de domeinnaam. 

- Hostnaam: @
- Type: TXT
- Adres: Plak hier de waarde Doel of Adres die u zojuist vanuit Microsoft hebt gekopieerd.  
- Selecteer **OK**  >  **gedaan.**

Controleer uw domein in Microsoft.  
> [!IMPORTANT]
> Wacht ongeveer 15 minuten voordat u dit doet, zodat de record die u zojuist hebt gemaakt, via internet kan worden bijgewerkt.       

- Ga terug naar Microsoft en volg de onderstaande stappen om een verificatiecontrole aan te vragen. Er wordt gecontroleerd op de TXT-record die u in de vorige stap hebt toegevoegd. Wanneer de juiste TXT-record wordt gevonden, wordt het domein geverifieerd.  
1. Ga in het beheercentrum naar de **pagina Domeinen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"></a> instellen.
2. Selecteer op **de pagina** Domeinen in de kolom **Actie** voor het domein dat u verifieert de optie **Setup starten.** 
3. Selecteer op **de pagina Bevestigen** dat u de eigenaar bent van uw domein de optie **Klaar,** controleer nu en selecteer vervolgens in het bevestigingsdialoogvenster **Voltooien.** 
   
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a>Niet-routeerbaar e-mailadres gebruikt als een UPN in de on-premises Active Directory
<a name="BKMK_ADNote"> </a>

Als u van plan bent uw on-premises Active Directory te synchroniseren met Microsoft, moet u ervoor zorgen dat het UPN-achtervoegsel (Active Directory user principal name) een geldig domeinachtervoegsel is en niet een niet-ondersteund domeinachtervoegsel, zoals @contoso.local. Zie Een [niet-routable domain](../../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md)voorbereiden voor adreslijstsynchronisatie als u het UPN-achtervoegsel wilt wijzigen.
  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 

## <a name="related-content"></a>Verwante onderwerpen

[Een domein overbrengen van Micrsoft 365 naar een andere host](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host) (artikel)

[Test Microsoft 365 vanuit mijn aangepaste domein](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain) (artikel)

[Veelgestelde vragen over domeinen](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) (artikel)