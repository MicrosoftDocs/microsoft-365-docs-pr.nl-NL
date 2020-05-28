---
title: DNS-records maken op name.com voor Microsoft
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
ms.assetid: 9ddcc2fc-9433-4335-8192-6ffb1f541087
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services op name.com voor Microsoft.
ms.openlocfilehash: 646f486e73705f4b1e1bab63866fc7601d34cf92
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400398"
---
# <a name="create-dns-records-at-namecom-for-microsoft"></a>DNS-records maken op name.com voor Microsoft

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Als name.com uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online enzovoort in te stellen.
  
Nadat u deze records bij name.com hebt toegevoegd, wordt uw domein ingesteld voor gebruik met Microsoft-services.

  
> [!NOTE]
> Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie
<a name="BKMK_verify"> </a>

Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij name.com via [deze koppeling](https://www.name.com/account/domain). U wordt gevraagd u eerst aan te melden.
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. Selecteer **onder Mijn domeinen**de naam van het domein dat u wilt wijzigen.
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. Selecteer **DNS-records**in de kolom **Details** . 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Type** <br/> |**Host** <br/> |**Antwoord** <br/> |**TTL** <br/> |
    |TXT  <br/> |(Laat dit veld leeg.)  <br/> |MS=ms *XXXXXXXX*  <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |Gebruik de standaardwaarde (300).  <br/> |
   
    ![Afbeelding van het te geven/geeft aan de knop Verifiëren-1-1](../../media/0c352fd3-cf84-439f-a481-0705e225cc54.png)
  
5. Selecteer **Record toevoegen**.
    
    ![Name-BP-Verify-1-2](../../media/816fc60b-17ab-4982-8849-6c3fcf3ca3d6.png)
  
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
<a name="BKMK_add_MX"> </a>

1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij name.com via [deze koppeling](https://www.name.com/account/domain). U wordt gevraagd u eerst aan te melden.
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. Selecteer **onder Mijn domeinen**de naam van het domein dat u wilt wijzigen.
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. Selecteer **DNS-records**in de kolom **Details** . 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
    |**Type**|**Host**|**Antwoord**|**TTL**|**Prio**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX  <br/> |(Laat dit veld leeg.)  <br/> | *\<domain-key\>*.mail.protection.outlook.com  <br/> **Let op:** Haal uw *\<domain-key\>* van uw Microsoft-account.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |Gebruik de standaardwaarde (300).  <br/> |0  <br/> Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit. <br/> |
   
   ![Afbeelding van het te maken](../../media/11ba2160-fc8e-4196-bb15-2b7c6d49c8fc.png)
  
5. Selecteer **Record toevoegen**.
    
    ![Name-BP-Configure-2-2](../../media/fd09f161-7cc4-4723-aec2-5fa801bd19e9.png)
  
6. Als er andere MX-records zijn, verwijdert u deze met behulp van de volgende tweestapsprocedure:
    
    Selecteer **Verwijderen** voor elkaars MX-record in de kolom **Acties.** 
    
    ![Name-BP-Configure-2-3](../../media/16734a98-31c4-4023-a2a5-10b7c95bc58e.png)
  
    Als u elke verwijdering wilt bevestigen, selecteert u **Opnieuw verwijderen** in de kolom **Acties.** 
    
    ![Name-BP-Configure-2-4](../../media/409c21c5-51f4-4244-bb84-5d32084224b2.png)
  
    Herhaal deze tweestapsprocedure tot u alle overige MX-records hebt verwijderd.
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>De CNAME-records toevoegen die zijn vereist voor Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij name.com via [deze koppeling](https://www.name.com/account/domain). U wordt gevraagd u eerst aan te melden.
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. Selecteer **onder Mijn domeinen**de naam van het domein dat u wilt wijzigen.
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. Selecteer **DNS-records**in de kolom **Details** . 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. Voeg de eerste CNAME-record toe.
    
    Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in de velden voor de nieuwe record.
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
    |**Type**|**Host**|**Antwoord**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |Gebruik de standaardwaarde (300).  <br/> |
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |Gebruik de standaardwaarde (300).  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |Gebruik de standaardwaarde (300).  <br/> |
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |Gebruik de standaardwaarde (300).  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |Gebruik de standaardwaarde (300).  <br/> |
   
   ![Afbeelding van het te maken](../../media/4e34caaf-b418-40ec-abfa-fe62175a87c2.png)
  
5. Selecteer **Record toevoegen** om de eerste record toe te voegen. 
    
    ![Name-BP-Configure-3-2](../../media/1053c2a7-07c3-4c1b-b54a-1c02881fb0ec.png)
  
6. Voeg de tweede CNAME-record toe:
    
    Gebruik de waarden uit de tweede rij van de bovenstaande tabel en selecteer **Record toevoegen** om de tweede record toe te voegen. 
    
    Voeg de resterende records op dezelfde manier toe met behulp van de waarden uit de derde, vierde, vijfde en zesde rij van de tabel.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Een TXT-record voor SPF toevoegen om spam tegen te gaan
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft. Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat. 
  
1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij name.com via [deze koppeling](https://www.name.com/account/domain). U wordt gevraagd u eerst aan te melden.
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. Selecteer **onder Mijn domeinen**de naam van het domein dat u wilt wijzigen.

    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. Selecteer **DNS-records**in de kolom **Details** . 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
    |**Type**|**Host**|**Antwoord**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |(Laat dit veld leeg.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.           |Gebruik de standaardwaarde (300).  <br/> |
   
   ![Afbeelding van het te maken](../../media/cbbfc071-840a-4ffa-a59e-0dfce03063cc.png)
  
5. Selecteer **Record toevoegen**.
    
    ![Name-BP-Configure-4-2](../../media/db1e0e09-2b95-4fc1-88bd-e86da536921f.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>De twee SRV-records toevoegen die zijn vereist voor Microsoft
<a name="BKMK_add_SRV"> </a>

1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij name.com via [deze koppeling](https://www.name.com/account/domain). U wordt gevraagd u eerst aan te melden.
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. Selecteer **onder Mijn domeinen**de naam van het domein dat u wilt wijzigen.
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. Selecteer **DNS Records+** in de kolom **Details.** 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. Voeg de eerste SRV-record toe:
    
    Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in de vakken voor de nieuwe record.
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
    |**Type**|**Service**|**Gewicht**|**TTL**|**Prio**|**Protocol**|**Poort**|**Doel**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV|sip|1|Gebruik de standaardwaarde (300).|100|tls|443|sipdir.online.lync.com <br> **Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.           |
    |SRV|sipfederationtls|1|Gebruik de standaardwaarde (300).|100|tcp|5061|sipfed.online.lync.com <br>**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.           |
   
   ![Afbeelding van het te maken](../../media/d9a885fd-7300-45b6-ad4c-0b4bf1067560.png)
  
5. Selecteer **Record toevoegen**.

    ![Name-BP-Configure-5-2](../../media/a804d51d-8f57-4b0b-8bd6-a52eb1c87a97.png)
  
6. Voeg als volgt de tweede SRV-record toe:

Gebruik de waarden uit de volgende rij van de bovenstaande tabel en selecteer **Record toevoegen** om de tweede record toe te voegen.

>[!NOTE]
>Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).
