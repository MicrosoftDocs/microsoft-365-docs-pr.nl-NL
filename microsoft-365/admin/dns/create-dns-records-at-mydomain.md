---
title: DNS-records maken op MyDomain voor Office 365
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
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9982191d-ed79-46a9-b2e7-317d1a3a9867
description: Lees hier hoe u uw domein en DNS-records voor e-mail, Skype voor Bedrijven Online en andere service kunt instellen via Mijn domein voor Office 365.
ms.openlocfilehash: c85c04d369add95d3aaa815229257fe90a24fb28
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "42805373"
---
# <a name="create-dns-records-at-mydomain-for-office-365"></a>DNS-records maken op MyDomain voor Office 365


  
 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
> [!CAUTION]
> De website MyDomain ondersteunt geen SRV-records. Dat betekent dat een aantal functies in Skype voor Bedrijven Online en Outlook Web App niet werkt. Als u uw DNS-records beheert via MyDomain, dan gelden er, ongeacht uw Office 365-abonnement, [aanzienlijke servicebeperkingen](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx). U kunt overwegen over te schakelen naar een andere DNS-hostingprovider. 
  
Als u ondanks deze beperkingen uw eigen DNS-records voor Office 365 via MyDomain wilt beheren, volgt u de stappen in dit artikel om uw DNS-records in te stellen voor e-mail, Skype voor Bedrijven Online, enzovoort.
    
Nadat u deze records op MyDomain hebt toegevoegd, is uw domein ingesteld voor gebruik met Office 365-services.
  
Zie [Een openbare website gebruiken met Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9) voor informatie over webhosting en DNS voor websites met Office 365.
  
> [!NOTE]
> Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie
<a name="BKMK_verify"> </a>

Voordat u uw domein met Office 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Office 365 bewezen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
1. Ga eerst naar de pagina met domeinen bij MyDomain via [deze koppeling](https://www.mydomain.com/controlpanel). U wordt gevraagd u eerst aan te melden.
    
2. Kies in de sectie **Mijn favorieten** de optie **Domain Central**.
    
3. Kies onder **Domein** de naam van het domein dat u wilt bewerken.
    
4. Kies in de rij **Overzicht** de optie **DNS**.
    
5. Kies in de vervolgkeuzelijst **Wijzigen** de optie **TXT/SPF-record**.
    
6. Typ of kopieer en plak de waarden uit de volgende tabel in het vak voor de nieuwe record onder **Content**.
    
    ||
    |:-----|
    |**Content** <br/> |
    |MS=ms *XXXXXXXX*  <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365. [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |
   
7. Kies **Toevoegen**.
    
8. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Office 365 en vraagt u of Office 365 naar de record wil zoeken.
  
Wanneer in Office 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.
  
1. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.
    
2. Kies op de pagina **Domeinen** de naam van het domein dat u verifieert. 
    
3. Kies **Start setup** op de pagina **Setup**.
    
4. Kies **Verifiëren** op de pagina **Domein verifiëren**.
    
> [!NOTE]
> Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Een MX-record toevoegen zodat e-mail voor uw domein bij Office 365 terechtkomt
<a name="BKMK_add_MX"> </a>

1. Ga eerst naar de pagina met domeinen bij MyDomain via [deze koppeling](https://www.mydomain.com/controlpanel). U wordt gevraagd u eerst aan te melden.
    
2. Kies in de sectie **Mijn favorieten** de optie **Domain Central**.
    
3. Kies onder **Domein** de naam van het domein dat u wilt bewerken.
    
4. Kies in de rij **Overzicht** de optie **DNS**.
    
5. Kies in de vervolgkeuzelijst **Modify** de optie **MX Record**.
    
    ![MyDomain-BP-Configure-2-1](../../media/bbfba978-8c53-471b-8c9e-8ae62e559d15.png)
  
6. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.
    
    |**Prioriteit**|**Host**|**Points To:**|
    |:-----|:-----|:-----|
    |0  <br/> Zie [Wat is MX-prioriteit?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) voor meer informatie over prioriteit. <br/> |@  <br/> | *\<domeinsleutel\>*  .mail.protection.outlook.com  <br/> **Opmerking**: Uw \<*domeinsleutel*\> kunt u ophalen uit uw Office 365-account. > [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![MyDomain-BP-Configure-2-2](../../media/3e19cec3-7f3b-493d-81f7-cda30ba007d5.png)
  
7. Kies **Toevoegen**.
    
    ![MyDomain-BP-Configure-2-3](../../media/1a1951a8-11d7-405d-bef5-285bbb053ce8.png)
  
8. Als er andere MX-records aanwezig zijn, selecteert u **Remove** in de kolom **Action** voor elke te verwijderen record. 
    
    ![MyDomain-BP-Configure-2-4](../../media/42576149-e056-4a81-a5fd-2c5dfac44e2e.png)
  
9. Kies **OK**.
    
    ![MyDomain-BP-Configure-2-5](../../media/d6b70eb7-b79c-499e-82ff-ecef2e300368.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a>De CNAME-records toevoegen die voor Office 365 vereist zijn
<a name="BKMK_add_CNAME"> </a>

1. Ga eerst naar de pagina met domeinen bij MyDomain via [deze koppeling](https://www.mydomain.com/controlpanel). U wordt gevraagd u eerst aan te melden.
    
2. Kies in de sectie **Mijn favorieten** de optie **Domain Central**.
    
3. Kies onder **Domein** de naam van het domein dat u wilt bewerken.
    
4. Kies in de rij **Overzicht** de optie **DNS**.
    
5. Kies in de vervolgkeuzelijst **Modify** de optie **CNAME Alias**.
    
    ![MyDomain-BP-Configure-3-1](../../media/628267fc-d37b-42ef-bb92-265284e339ac.png)
  
6. Voeg de eerste CNAME-record toe.
    
    Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in de velden voor de nieuwe record.
    
    |**Host**|**Points To:**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![MyDomain-BP-Configure-3-2](../../media/3c8660b3-40bb-453d-8b99-4d22032bc4b3.png)
  
7. Kies **Toevoegen** om een eerste record toe te voegen. 
    
    ![MyDomain-BP-Configure-3-3](../../media/103a1d99-70da-4fdf-9291-7dd058ec6c4a.png)
  
8. Voeg de tweede CNAME-record toe:
    
    Gebruik de waarden uit de tweede rij van de bovenstaande tabel en kies vervolgens **Toevoegen** om de tweede record toe te voegen. 
    
    Voeg de resterende records op dezelfde manier toe met behulp van de waarden uit de derde, vierde, vijfde en zesde rij van de tabel.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Een TXT-record voor SPF toevoegen om spam tegen te gaan
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Office 365 te maken. In plaats daarvan voegt u de vereiste Office 365-waarden toe aan de huidige record, zodat u beschikt over één SPF-record waarin beide sets waarden zijn opgenomen. Hebt u voorbeelden nodig? Bekijk deze [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords). Voor het valideren van uw SPF-record, kunt u een van deze [SPF-validatiehulpmiddelen](../setup/domains-faq.md) gebruiken. 
  
1. Ga eerst naar de pagina met domeinen bij MyDomain via [deze koppeling](https://www.mydomain.com/controlpanel). U wordt gevraagd u eerst aan te melden.
    
2. Kies in de sectie **Mijn favorieten** de optie **Domain Central**.
    
3. Kies onder **Domein** de naam van het domein dat u wilt bewerken.
    
4. Kies in de rij **Overzicht** de optie **DNS**.
    
5. Kies in de vervolgkeuzelijst **Modify** de optie **TXT/SPF Record**.
    
    ![MyDomain-BP-Configure-4-1](../../media/c461c762-52e6-4fde-b5bc-4dd5e5d62ed3.png)
  
6. Typ of kopieer en plak de waarden uit de volgende tabel in het vak voor de nieuwe record onder **Content**.
    
    |**Content**|
    |:-----|
    |v=spf1 include:spf.protection.outlook.com -all  <br/> **Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.           |
   
    ![MyDomain-BP-Configure-4-2](../../media/17d43106-88e6-47e5-aeba-0f18484acf3e.png)
  
7. Kies **Toevoegen**.
    
    ![MyDomain-BP-Configure-4-3](../../media/b3670563-b620-470c-a42b-2c77888981f8.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>De twee SRV-records toevoegen die voor Office 365 vereist zijn
<a name="BKMK_add_SRV"> </a>

> [!CAUTION]
> De website MyDomain ondersteunt geen SRV-records. Dat betekent dat een aantal functies in Skype voor Bedrijven Online en Outlook Web App niet werkt. Als u uw DNS-records beheert via MyDomain, dan gelden er, ongeacht uw Office 365-abonnement, [aanzienlijke servicebeperkingen](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx). U kunt overwegen over te schakelen naar een andere DNS-hostingprovider. 
  
> [!NOTE]
> Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
