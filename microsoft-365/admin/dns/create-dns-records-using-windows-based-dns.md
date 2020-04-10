---
title: DNS-records voor Office 365 maken met Windows-DNS
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
ms.assetid: 9eec911d-5773-422c-9593-40e1147ffbde
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services op windows-gebaseerde DNS voor Office 365.
ms.openlocfilehash: d33a2f79111f8951c3ec31ca5680877ad2e7d570
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210562"
---
# <a name="create-dns-records-for-office-365-using-windows-based-dns"></a>DNS-records voor Office 365 maken met Windows-DNS

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
   
Als u uw eigen DNS-records met Windows-DNS host, volgt u de stappen in dit artikel voor het instellen van uw records voor e-mail, Skype voor Bedrijven Online, enzovoort.
  
Om aan de slag te gaan, moet u [uw DNS-records vinden in Windows-gebaseerde DNS,](#find-your-dns-records-in-windows-based-dns) zodat u ze bijwerken. Zie [Niet-routeerbaar e-mailadres dat als UPN wordt gebruikt in uw active directory voor het gebruik van vooraf.](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory)
  
Problemen met e-mailstroom of andere problemen na het toevoegen van DNS-records, zie [Problemen oplossen na het wijzigen van uw domeinnaam of DNS-records.](../get-help-with-domains/find-and-fix-issues.md) 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a>Uw DNS-records vinden in Windows-DNS
<a name="BKMK_find_your_dns_1"> </a> Ga naar de pagina met de DNS-records voor uw domein. Als u in Windows Server 2008 werkt, gaat u naar **Uitvoeren starten.** > **Run** Als u in Windows Server 2012 werkt, drukt u op de Windows-toets en **r**. Typ **dnsmgmnt.msc**en selecteer **OK**. Vouw in DNS-beheer ** \<DNS-servernaam\> \> Forward Lookup Zones  **uit. Selecteer uw domein. Nu kunt u de DNS-records gaan maken.
   
## <a name="add-mx-record"></a>MX-record toevoegen
<a name="BKMK_add_MX"> </a>

Voeg een MX-record toe zodat e-mail voor uw domein naar Office 365 wordt verzonden.
- De MX-record die u toevoegt, bevat een waarde (de waarde **Adres waarnaar wordt verwezen**) die er ongeveer zo uitziet: \<MX token\>.mail.protection.outlook.com, waarbij \<MX-token\> een waarde is zoals MSxxxxxxx. 
- Kopieer de waarde die wordt vermeld onder Adres punten naar adres in de rij MX in de sectie Exchange Online van de pagina DNS-records toevoegen in Office 365. U gebruikt deze waarde in de record die u in deze taak maakt. 
- Ga op de pagina DNS-beheer voor het domein naar **Action** > **Mail Exchanger (MX)**. Zie [Uw DNS-records zoeken in windows-gebaseerde DNS](#find-your-dns-records-in-windows-based-dns)voor het domein om deze pagina voor het domein te vinden.  
- Controleer in het dialoogvenster **Nieuwe bronrecord** of de velden zijn ingesteld op precies de volgende waarden: 
    - Host Name:  
    - @Address: Plak hier de adreswaarde aan adres die u zojuist hebt gekopieerd uit Office 365.  
    - Pref: 
- Selecteer **Wijzigingen opslaan**.
- Verouderde MX-records verwijderen. Als u oude MX-records voor dit domein hebt die e-mail ergens anders routeren, schakelt u het selectievakje naast elke oude record in en selecteert u **Ok verwijderen.** > **OK** 
   
## <a name="add-cname-records"></a>CNAME-records toevoegen
<a name="BKMK_add_CNAME"> </a>

Voeg de CNAME-records toe die voor Office 365 zijn vereist. Als er extra CNAME-records worden weergegeven in Office 365, voegt u die toe aan de hand van dezelfde algemene stappen die hier worden weergegeven.
  
> [!IMPORTANT]
> Als u Mobile Device Management (MDM) voor Office 365 hebt, moet u twee extra CNAME-records maken. Volg de stappen die u hebt gevolgd voor de andere vier CNAME-records, maar gebruik de waarden uit de volgende tabel. (Als u geen MDM hebt, u deze stap overslaan.) 

- Ga op de pagina DNS-beheer voor het domein naar **Action** > **CNAME (CNAME).**
- Controleer in het dialoogvenster **Nieuwe bronrecord** of de velden zijn ingesteld op precies de volgende waarden:  
    - Host naam: autodiscover
    - Type: 
    - CNAMEAddress: autodiscover.outlook.com
- Selecteer **O**K.

Voeg de SIP CNAME-record toe. 
- Ga op de pagina DNS-beheer voor het domein naar **Action** \> **CNAME (CNAME).** 
- Controleer in het dialoogvenster **Nieuwe bronrecord** of de velden zijn ingesteld op precies de volgende waarden:  
    - Host naam: sip
    - Type: CNAME
    - Adres: sipdir.online.lync.com
- Kies **OK**.

Voeg de Skype voor Bedrijven Online Autodiscover CNAME-record toe.  
- Ga op de pagina DNS-beheer voor het domein naar **Action** \> **CNAME (CNAME).** Controleer in het dialoogvenster **Nieuwe bronrecord** of de velden zijn ingesteld op precies de volgende waarden:  
    - Host naam: lyncdiscover
    - Type: CNAME
    - Adres: webdir.online.lync.com
- Kies **OK**.
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-office-365"></a>Twee CNAME-records voor MDM (Mobile Device Management) voor Office 365 toevoegen

> [!IMPORTANT]
> Als u Mobile Device Management (MDM) voor Office 365 hebt, moet u twee extra CNAME-records maken. Volg de stappen die u hebt gevolgd voor de andere vier CNAME-records, maar gebruik de waarden uit de volgende tabel. >(Als u geen MDM hebt, u deze stap overslaan.) 
  

Voeg de MDM Enterpriseregistration CNAME-record toe.  
- Ga op de pagina DNS-beheer voor het domein naar **Action** \> **CNAME (CNAME).** 
- Controleer in het dialoogvenster **Nieuwe bronrecord** of de velden zijn ingesteld op precies de volgende waarden:  
- Host name: enterpriseregistration
- Type: CNAME
- Adres: enterpriseregistration.windows.net
- Kies **OK**. 

Voeg de MDM Enterpriseenrollment CNAME-record toe. 
-  Ga op de pagina DNS-beheer voor het domein naar **Action** \> **CNAME (CNAME).** 
-  Controleer in het dialoogvenster **Nieuwe bronrecord** of de velden zijn ingesteld op precies de volgende waarden:  
    - Hostnaam: inschrijving voor ondernemingen
    - Type: CNAME
    - Adres: enterpriseenrollment-s.manage.microsoft.com
- Kies **OK**.
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Een TXT-record voor SPF toevoegen om spam tegen te gaan
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Office 365 te maken. In plaats daarvan voegt u de vereiste Office 365-waarden toe aan de huidige record, zodat u beschikt over  *één*  SPF-record waarin beide sets waarden zijn opgenomen. 
  
Voeg de SPF TXT-record voor uw domein om spam te voorkomen.
  
- Mogelijk hebt u al andere tekenreeksen in de TXT-waarde voor deze record (zoals tekenreeksen voor marketing-e-mail). Dit is geen probleem. Laat deze tekenreeksen staan en voeg deze toe, plaats dubbele aanhalingstekens rond elke tekenreeks om ze te scheiden. 
- Ga op de pagina DNS-beheer voor uw domein naar **Actietekst** \> **(TXT).** 
-  Controleer in het dialoogvenster **Nieuwe bronrecord** of de velden zijn ingesteld op precies de volgende waarden. 
 > [!IMPORTANT]
> In sommige versies van Windows DNS Manager is het mogelijk dat het domein zo is ingesteld dat wanneer u een txt-record maakt, de thuisnaam standaard wordt ingesteld op het bovenliggende domein. Als u in deze situatie een TXT-record toevoegt, stelt u de hostnaam in op leeg (geen waarde) in plaats van op @ of de domeinnaam. 

-  Hosttype: @
-  Recordtype: TXT
-  Adres: v=spf1 include:spf.protection.outlook.com -all 
         
-  Kies **OK**.
   
## <a name="add-srv-records"></a>SRV-records toevoegen
<a name="BKMK_add_SRV"> </a>

Voeg de twee SRV-records toe die voor Office 365 zijn vereist.

Voeg de SIP SRV-record voor Skype voor Bedrijven Online-webconferenties toe.  <br/> 
-  Ga op de pagina DNS-beheer voor uw domein naar **Action** \> **Other New Records**. 
-   Selecteer **servicelocatie (SRV) in**het venster **Resourcerecordtype** en selecteer **Vervolgens Record maken**. 
-   Controleer in het dialoogvenster **Nieuwe bronrecord** of de velden zijn ingesteld op precies de volgende waarden:  
    -  Service: _sip
    -  Protocol: _tls
    -  Prioriteit: 100
    -  Gewicht: 1
    -  Poort: 443
    -  Doel (hostnaam): sipdir.online.lync.com
-  Kies **OK**. 


Voeg de SIP SRV-record voor Skype voor Bedrijven Online-federatie toe.  
-  Ga op de pagina DNS-beheer voor uw domein naar **Action** \> **Other New Records**.  
-  Selecteer **servicelocatie (SRV) in**het venster **Resourcerecordtype** en selecteer **Vervolgens Record maken**. 
-   Controleer in het dialoogvenster **Nieuwe bronrecord** of de velden zijn ingesteld op precies de volgende waarden:  
    -  Service: _sipfederationtls
    -  Protocol: _tcp
    -  Prioriteit: 100
    -  Gewicht: 1
    -  Poort: 5061
    -  Doel (hostnaam): sipfed.online.lync.com
-  Kies **OK**. 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a>Een record toevoegen om te verifiëren dat u eigenaar bent van het domein, als dit nog niet is gedaan
<a name="BKMK_verify"> </a>

Voordat u de DNS-records toevoegt voor het instellen van de Office 365-services, moet door Office 365 worden bevestigd dat u eigenaar bent van het domein dat u toevoegt. Hiertoe voegt u een record toe aan de hand van onderstaande stappen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. 
  

1. Verzamel informatie uit Office 365.  <br/> 
2. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina. 
3. Selecteer op de pagina **Domeinen** in de kolom **Acties** voor het domein dat u verifieert de optie **Setup starten**. 
4. Selecteer **stap 1 starten**op de pagina Een domein toevoegen aan Office **365** . 
5. Kies **op** de pagina Bevestigen dat u eigenaar bent van uw domein de optie Algemene **instructies**in de **vervolgkeuzelijst Zie instructies voor het uitvoeren van deze stap met** de vervolgkeuzelijst . 
6. Kopieer vanuit de tabel de waarde Doel of adres waarnaar wordt verwezen. Deze hebt u nodig voor de volgende stap. Het is raadzaam deze waarde te kopiëren en te plakken, zodat alle spatiëring ongewijzigd blijft.

Voeg een TXT-record toe. 
-  Ga op de pagina DNS-beheer voor uw domein naar **Actietekst** \> **(TXT).** 
-   **Selecteer**bewerken in het dialoogvenster **Nieuwe bronrecord** .  
-  Controleer in het gedeelte **Aangepaste hostnamen** van het dialoogvenster **Nieuwe bronrecord** of de velden zijn ingesteld op precies de volgende waarden. 

> [!IMPORTANT] 
> In sommige versies van Windows DNS Manager is het mogelijk dat het domein zo is ingesteld dat wanneer u een txt-record maakt, de thuisnaam standaard wordt ingesteld op het bovenliggende domein. Als u in deze situatie een TXT-record toevoegt, stelt u de hostnaam in op leeg (geen waarde) in plaats van op @ of de domeinnaam. 

- Host naam: @
- Type: TXT
- Adres: Plak hier de waarde Bestemming of Adres die u zojuist hebt gekopieerd uit Office 365.  
- Selecteer **OK** > **gereed**.

Controleer uw domein in Office 365.  
> [!IMPORTANT]
> Wacht ongeveer 15 minuten voordat u dit doet, zodat de record die u zojuist hebt gemaakt, kan worden bijgewerkt via het internet.       

- Ga terug naar Office 365 en volg de onderstaande stappen om een controle aan te vragen. Er wordt gecontroleerd op de TXT-record die u in de vorige stap hebt toegevoegd. Wanneer de juiste TXT-record wordt gevonden, wordt het domein geverifieerd.  
1. Ga in het beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Setup-domeinen.</a> **Setup**
2. Selecteer op de pagina **Domeinen** in de kolom **Actie** voor het domein dat u verifieert de optie **Installatie starten**. 
3. Selecteer op **de pagina Bevestigen dat u eigenaar bent van uw domein** de optie **Gereed, controleer nu**en selecteer vervolgens in het bevestigingsdialoogvenster **Voltooien**. 
   
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a>Niet-routeerbaar e-mailadres gebruikt als een UPN in de on-premises Active Directory
<a name="BKMK_ADNote"> </a>

Als u van plan bent uw on-premises Active Directory te synchroniseren met Office 365, controleert u dan of het voorvoegsel van de user principal name (UPN-naam) van Active Directory een geldig domeinvoorvoegsel is en geen niet-ondersteund domeinvoorvoegsel, zoals @contoso.local. Als u het UPN-achtervoegsel wilt wijzigen, raadpleegt u [Een niet-routetabel domein voorbereiden voor adressynchronisatie.](https://support.office.com/article/e7968303-c234-46c4-b8b0-b5c93c6d57a7)
  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
