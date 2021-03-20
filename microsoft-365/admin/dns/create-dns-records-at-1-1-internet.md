---
title: DNS-records maken op 1&1 IONOS voor Microsoft
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
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: Informatie over het verifiëren van uw domein en het instellen van DNS-records voor e-mail, Skype voor Bedrijven Online en andere services op 1&1 IONOS voor Microsoft.
ms.openlocfilehash: 123abd6d1d93f80eb73f187b7ff75ccd90d02980
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910556"
---
# <a name="create-dns-records-at-11-ionos-for-microsoft"></a>DNS-records maken op 1&1 IONOS voor Microsoft

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt. 
  
> [!CAUTION]
> Met 1&1 IONOS kan een domein niet zowel een MX-record als een CNAME-record op het hoogste niveau hebben. Dit beperkt de manieren waarop u Exchange Online voor Microsoft kunt configureren. Er is een tijdelijke oplossing, maar  we raden u aan deze alleen te gebruiken als u al ervaring hebt met het maken van subdomeinen op 1&1 IONOS. > Als u ondanks deze [servicebeperking](../setup/domains-faq.yml) ervoor kiest om uw eigen Microsoft DNS-records te beheren op 1&1 IONOS, volgt u de stappen in dit artikel om uw domein te verifiëren en DNS-records in te stellen voor e-mail, Skype voor Bedrijven Online, en ga zo maar door. 
  
Nadat u deze records hebt&1 IONOS, is uw domein ingesteld voor gebruik met Microsoft-services.
  
  
> [!NOTE]
> Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie

Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
Volg onderstaande stappen of [bekijk de video (start op 0:42)]().
  
1. Als u wilt beginnen, gaat u via deze [koppeling](https://my.1and1.com/)naar uw domeinenpagina op 1&1 IONOS. U wordt gevraagd u aan te melden.
    
2. Selecteer **Domeinen beheren.**
    
3. Zoek op **de pagina Domain Center** het domein dat u wilt bijwerken en selecteer vervolgens het besturingselement **Panel** **(v)** voor dat domein.
    
4. Selecteer **dns-instellingen** bewerken in het gebied **Domeininstellingen.**
    
5. Selecteer in **de sectie TXT- en SRV-records** de optie **Record toevoegen.**
    
6. Ga naar het gebied **Add Record**. In de vakken voor de nieuwe record in dit gebied kunt u vervolgens de waarden uit de volgende tabel typen of kopiëren en plakken. 
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
    ||||
    |:-----|:-----|:-----|
    |**Type** <br/> |**Voorvoegsel** <br/> |**Naamwaarde** <br/> |
    |TXT  <br/> |(Laat dit veld leeg)  <br/> |MS=ms *XXXXXXXX*  <br/> OPMERKING: Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel. [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |
   
7. Kies **Opslaan**.
    
8. Selecteer **Opnieuw** opslaan. 
    
9. Selecteer ja in het dialoogvenster **DNS-instellingen** **bewerken.**
    
10. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft 365 en vraagt u of Microsoft 365 naar de record wil zoeken.
  
Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.
  
1. Ga in het Microsoft-beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.

    
2. Kies op de pagina **Domeinen** de naam van het domein dat u verifieert. 
    
3. Kies **Start setup** op de pagina **Setup**.
    
4. Kies **Verifiëren** op de pagina **Domein verifiëren**.
    
> [!NOTE]
> Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden
<a name="BKMK_add_MX"> </a>

Volg onderstaande stappen of [bekijk de video (start op 3:22)]().
  
> [!NOTE]
> Als u zich hebt geregistreerd bij 1und1.de, [meld u dan hier aan.](https://go.microsoft.com/fwlink/?linkid=859152) 
  
1. Als u wilt beginnen, gaat u via deze [koppeling](https://my.1and1.com/)naar uw domeinenpagina op 1&1 IONOS. U wordt gevraagd u aan te melden.
    
2. Selecteer **Domeinen beheren.**
    
3. Zoek op **de pagina Domain Center** het domein dat u wilt bijwerken en selecteer vervolgens het besturingselement **Panel** **(v)** voor dat domein.
    
4. Selecteer **dns-instellingen** bewerken in het gebied **Domeininstellingen.**
    
5. Selecteer in **de sectie MX Records** in het gebied Mail **Exchanger (MX Record)** de optie **Andere e-mailserver**.<br/>(Mogelijk moet u omlaag schuiven.)<br/>![1 &amp; 1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png) <br/>
  
6. Als er al MX-records worden vermeld, verwijdert u deze door de records te selecteren en op de toets **Delete** op het toetsenbord te drukken.<br/>(Als er nog geen MX-records worden vermeld, gaat u verder met de volgende stap.)<br/>![1 &amp; 1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)<br/>
  
7. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de **MX 1**-record. 
    
    |**MX 1**|**Prioriteit**|
    |:-----|:-----|
    | *\<domain-key\>*  .mail.protection.outlook.com  <br/>  OPMERKING: Haal uw \<domain-key\> uit uw Microsoft-account. [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |10  <br/> Zie [Wat is MX-prioriteit?](../setup/domains-faq.yml) voor meer informatie over prioriteit.    <br/> | 
    
    ![1 en 1 - 2 en 3 configureren](../../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. Kies **Opslaan**.<br/>(Mogelijk moet u omlaag schuiven.)<br/>![1 &amp; 1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)
  
9. Selecteer ja in het dialoogvenster **DNS-instellingen** **bewerken.**<br/>![Ja selecteren in het dialoogvenster DNS-instellingen bewerken](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Voeg de zes CNAME-records toe die vereist zijn voor Microsoft
<a name="BKMK_add_CNAME"> </a>

1&1 IONOS vereist een tijdelijke oplossing, zodat u een MX-record kunt gebruiken samen met de CNAME-records die zijn vereist voor e-mailservices van Microsoft. Voor deze tijdelijke oplossing moet u een set subdomeinen maken op 1&1 IONOS en deze toewijzen aan CNAME-records.
  
> [!IMPORTANT]
> Zorg dat u ten minste twee beschikbare subdomeinen hebt voordat u deze procedure begint. We raden deze oplossing alleen aan als u al ervaring hebt met het maken van subdomeinen op 1&1 IONOS. 
  
### <a name="basic-cname-records"></a>Basis-CNAME-records

Volg onderstaande stappen of [bekijk de video (start op 3:57)]().
  
> [!NOTE]
> Als u zich hebt geregistreerd bij 1und1.de, [meld u dan hier aan.](https://go.microsoft.com/fwlink/?linkid=859152) 
  
1. Als u wilt beginnen, gaat u via deze [koppeling](https://my.1and1.com/)naar uw domeinenpagina op 1&1 IONOS. U wordt gevraagd u aan te melden.
    
2. Selecteer **Domeinen beheren.**
    
3. Zoek op **de pagina Domain Center** het domein dat u wilt bijwerken en selecteer vervolgens **Subdomeinen beheren.**<br/>![1 &amp; 1-BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png) <br/>Nu maakt u twee subdomeinen en stelt u voor elk subdomein een **Alias**-waarde in.<br/>(Dit is vereist omdat 1&1 IONOS slechts één CNAME-record op het hoogste niveau ondersteunt, maar Microsoft meerdere CNAME-records nodig heeft.)<br/>Eerst maakt u het autodiscover-subdomein.
    
4. Selecteer **subdomein maken** in de sectie **Subdomeinoverzicht.**
    
    ![1&amp;1-BP-Configure-3-1](../../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. Typ of kopieer en plak in het vak **Create Subdomain** voor het nieuwe subdomein alleen de waarde voor **Create Subdomain** uit de volgende tabel. (De **Alias**-waarde voegt u in een latere stap toe.)

    |**Create Subdomain**|**Alias**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com   | 

    ![1 &amp; 1-BP-Configure-3-2](../../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. Selecteer **Subdomein maken.**<br/>![1 &amp; 1-BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)
  
7. Zoek in **de sectie Subdomeinoverzicht** het **autodiscover-subdomein** dat u zojuist hebt gemaakt en selecteer vervolgens het besturingselement **Panel (v)** voor dat subdomein. <br/>![1 &amp; 1-BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)
  
8. Selecteer **dns-instellingen** bewerken in het gebied **Subdomeininstellingen.** <br/>![1 &amp; 1-BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)
  
9. Selecteer CNAME in de sectie **A/AAAA Records (IP-adressen)** in het **gebied IP-adres (A** **Record).**<br/>![1 &amp; 1-BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)
  
10. Typ of kopieer en plak alleen de **Alias**-waarde uit de volgende tabel in het vak **Alias:**.<br/> 
    
    |**Create Subdomain**|**Alias**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com   |

    ![1 &amp; 1-BP-Configure-3-7](../../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. Schakel het selectievakje in voor de vrijwaring **I am aware**.<br/>![1 &amp; 1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)
  
12. Kies **Opslaan**.<br/>![1 &amp; 1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)
  
  
### <a name="additional-cname-records"></a>Extra CNAME-records

Met de extra CNAME-records die in de volgende procedure worden gemaakt, worden Skype voor Bedrijven Online-services ingeschakeld. U gebruikt dezelfde stappen die u eerder hebt gebruikt om de twee CNAME-records te maken.
  
1. Maak het derde subdomein (Lyncdiscover).<br/>Selecteer **subdomein maken** in de sectie **Subdomeinoverzicht.**
    
2. Typ of kopieer en plak in het vak **Create Subdomain** voor het nieuwe subdomein alleen de waarde voor **Create Subdomain** uit de volgende tabel. (De **Alias**-waarde voegt u in een latere stap toe.)<br/> 
    
    |**Create Subdomain**|**Alias**|
    |:-----|:-----|
    |lyncdiscover   |webdir.online.lync.com  |
   
3. Selecteer **Subdomein maken.**
    
4. Selecteer op **de pagina Domeincentrum** **de optie Subdomeinen beheren.**
    
5. Zoek in **de sectie Subdomeinoverzicht** het **lyncdiscover-subdomein** dat u zojuist hebt gemaakt en selecteer vervolgens het besturingselement **Panel (v)** voor dat subdomein. <br/>Selecteer **dns-instellingen** bewerken in het gebied **Subdomeininstellingen.**
    
6. Selecteer CNAME in de sectie **A/AAAA Records (IP-adressen)** in het **gebied IP-adres (A** **Record).**
    
7. Typ of kopieer en plak alleen de **Alias**-waarde uit de volgende tabel in het vak **Alias:**. <br/>
    
    |**Create Subdomain**|**Alias**|
    |:-----|:-----|
    |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |
   
8. Schakel het selectievakje in voor de vrijwaring **ik ben op de** hoogte en selecteer opslaan. 
    
9. Selecteer ja in het dialoogvenster **DNS-instellingen** **bewerken.**
    
10. Maak als volgt het vierde subdomein (SIP): <br/>Selecteer **subdomein maken** in de sectie **Subdomeinoverzicht.**
    
11. Typ of kopieer en plak in het vak **Create Subdomain** voor het nieuwe subdomein alleen de waarde voor **Create Subdomain** uit de volgende tabel. (De **Alias**-waarde voegt u in een latere stap toe.)<br/>
    
    |**Create Subdomain**|**Alias**|
    |:-----|:-----|
    |sip  <br/> |sipdir.online.lync.com  <br/> |
   
12. Selecteer **Subdomein maken.**
    
13. Selecteer op **de pagina Domeincentrum** **de optie Subdomeinen beheren.**
    
14. Zoek in **de sectie Subdomeinoverzicht** het **sip-subdomein** dat u zojuist hebt gemaakt en selecteer vervolgens het besturingselement Panel **(v)** voor dat subdomein. <br/>Selecteer **dns-instellingen** bewerken in het gebied **Subdomeininstellingen.**
    
15. Selecteer CNAME in de sectie **A/AAAA Records (IP-adressen)** in het **gebied IP-adres (A** **Record).**
    
16. Typ of kopieer en plak alleen de **Alias**-waarde uit de volgende tabel in het vak **Alias:**. 
    
    |**Create Subdomain**|**Alias**|
    |:-----|:-----|
    |sip  <br/> |sipdir.online.lync.com  <br/> |
   
17. Schakel het selectievakje in voor de vrijwaring **ik ben op de** hoogte en selecteer opslaan. 
    
18. Selecteer ja in het dialoogvenster **DNS-instellingen** **bewerken.**
    
### <a name="cname-records-needed-for-mdm"></a>CNAME-records die nodig zijn voor MDM

> [!IMPORTANT]
> Volg de stappen die u hebt gevolgd voor de andere vier CNAME-records, maar gebruik de waarden uit de volgende tabel. 
  
|**Create Subdomain**|**Alias**|
|:-----|:-----|
|enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |
|enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Een TXT-record voor SPF toevoegen om spam tegen te gaan

> [!IMPORTANT]
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft. Voeg in plaats daarvan de vereiste Microsoft-waarden  toe aan de huidige record, zodat u één SPF-record hebt met beide sets waarden. Hebt u voorbeelden nodig? Bekijk deze [Externe Domain Name System-records voor Microsoft](../../enterprise/external-domain-name-system-records.md). Als u uw SPF-record wilt valideren, kunt u een van deze[SPF-validatiehulpmiddelen gebruiken.](../setup/domains-faq.yml) 
  
Volg onderstaande stappen of [bekijk de video (start op 5:09)]().
  
> [!NOTE]
> Als u zich hebt geregistreerd bij 1und1.de, [meld u dan hier aan.](https://go.microsoft.com/fwlink/?linkid=859152) 
  
1. Als u wilt beginnen, gaat u via deze [koppeling](https://my.1and1.com/)naar uw domeinenpagina op 1&1 IONOS. U wordt gevraagd u aan te melden.
    
2. Selecteer **Domeinen beheren.**
    
3. Zoek op **de pagina Domain Center** het domein dat u wilt bijwerken en selecteer vervolgens het besturingselement **Panel** **(v)** voor dat domein.
    
4. Selecteer **dns-instellingen** bewerken in het gebied **Domeininstellingen.**
    
5. Selecteer in **de sectie TXT- en SRV-records** de optie **Record toevoegen.** <br/>(Mogelijk moet u omlaag schuiven.)
    
6. Ga naar het gebied **Add Record**. In de vakken voor de nieuwe record in dit gebied kunt u vervolgens de waarden uit de volgende tabel typen of kopiëren en plakken. <br/>(Kies in de vervolgkeuzelijst de waarde **Type**). <br/>
    
    |**Type**|**Voorvoegsel**|**Naamwaarde**|
    |:-----|:-----|:-----|
    |TXT  <br/> |(Laat dit veld leeg.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.           | 
    
    ![TXT-record](../../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. Kies **Opslaan**.<br/>![Add record](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)
  
8. Kies **Opslaan**.<br/>![Save record](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)
  
9. Selecteer ja in het dialoogvenster **DNS-instellingen** **bewerken.**<br/>![Ja selecteren in het dialoogvenster DNS-instellingen bewerken](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>De twee SRV-records toevoegen die zijn vereist voor Microsoft

Volg onderstaande stappen of [bekijk de video (start op 5:51)]().
  
> [!NOTE]
> Als u zich hebt geregistreerd bij 1und1.de, [meld u dan hier aan.](https://go.microsoft.com/fwlink/?linkid=859152) 
  
1. Als u wilt beginnen, gaat u via deze [koppeling](https://my.1and1.com/)naar uw domeinenpagina op 1&1 IONOS. U wordt gevraagd u aan te melden.
    
2. Selecteer **Domeinen beheren.**
    
3. Zoek op **de pagina Domain Center** het domein dat u wilt bijwerken en selecteer vervolgens het besturingselement **Panel** **(v)** voor dat domein.
    
4. Selecteer **dns-instellingen** bewerken in het gebied **Domeininstellingen.**
    
5. Selecteer in **de sectie TXT- en SRV-records** de optie **Record toevoegen.**
    
6. Voeg de eerste van de twee SRV-records toe.<br/>Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in het gebied **Add Record** in de vakken voor de nieuwe record. <br/>(Kies de **waarden Type** en **TTL** in de vervolgkeuzelijst.) 
    
    |**Type**|**Service**|**Protocol**|**Naam**|**Host**|**Prioriteit**|**Gewicht**|**Poort**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV  <br/> |sip  <br/> |tls  <br/> |(Laat dit veld leeg.)  <br/> |sipdir.online.lync.com  <br/> |100  <br/> |1  <br/> |443  <br/> |3600 (1 uur)  <br/> |
    |SRV  <br/> |sipfederationtls  <br/> |tcp  <br/> |(Laat dit veld leeg.)  <br/> |sipfed.online.lync.com  <br/> |100  <br/> |1  <br/> |5061  <br/> |3600 (1 uur)  <br/> |  
    
    ![1 &amp; 1-BP-Configure-5-1](../../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. Kies **Opslaan**. <br/>![1 &amp; 1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)
  
8. Kies **Opslaan**. <br/>![1 &amp; 1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)
  
9. Selecteer ja in het dialoogvenster **DNS-instellingen** **bewerken.** <br/>![Ja selecteren in het dialoogvenster DNS-instellingen bewerken](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)
  
10. Voeg de andere SRV-record toe. <br/>Selecteer in **de sectie TXT- en SRV-records** de optie **Record toevoegen.** <br/>Maak in **het gebied Record** toevoegen een record met de waarden uit de andere rij in de tabel en selecteer vervolgens opnieuw **Toevoegen,** Opslaan **en** **Ja** om de record te voltooien. 
    
> [!NOTE]
> Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md). 
