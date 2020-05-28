---
title: DNS-records maken bij Netregistry voor Microsoft
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
- BEA160
ms.assetid: 48e09394-2287-4b3c-9853-21eadf61277e
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services bij Netregistry voor Microsoft.
ms.openlocfilehash: c4e81e92b9f86d0a2974e6f95e397f3584c9a01e
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400362"
---
# <a name="create-dns-records-at-netregistry-for-microsoft"></a>DNS-records maken bij Netregistry voor Microsoft

[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md) als u niet kunt vinden wat u zoekt. 
  
Als Netregistry uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.
  
Dit zijn de belangrijkste records om toe te voegen.
  
- [Een TXT-record toevoegen voor verificatie](#add-a-txt-record-for-verification)
    
- [Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)

- [De CNAME-records toevoegen die zijn vereist voor Microsoft](#add-the-cname-records-that-are-required-for-microsoft)
    
- [Een TXT-record voor SPF toevoegen om spam tegen te gaan](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [De twee SRV-records toevoegen die zijn vereist voor Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft)
    
Nadat u deze records bij Netregistry hebt toegevoegd, wordt uw domein ingesteld om te werken met Microsoft-services.
  
  
> [!NOTE]
> Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie
<a name="bkmk_txt"> </a>

Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
1. Ga naar uw domeinpagina van Netregistry via [deze koppeling](https://theconsole.netregistry.com.au/). U wordt gevraagd u aan te melden.
    
    ![Netregistry_login](../../media/ed3c785f-01c3-49e7-affd-c04637c0ffe9.png)
  
2. Selecteer **Manage** (beheren) naast het domein dat u wilt beheren.
    
    ![Netregistry_Manage](../../media/64ad542a-5ec4-4148-96f8-d6e163449352.png)
  
3. Selecteer **Zone Manager**.
    
    ![Netregistry_selectZoneManager](../../media/e18c32f9-c1e7-4aa2-9aa6-8dc9c5ea44af.png)
  
4. Kies **onder Een zonerecord toevoegen**de optie **TXT-record** in de lijst en selecteer **Vervolgens Nieuwe record maken**.
    
    ![Netregistry_TXT_select](../../media/eb1761e6-9deb-4631-8deb-bc5d09926722.png)
  
    > [!NOTE]
    > U moet aanhalingstekens gebruiken voor en na de vermelding in het vak TXT. 
  
    Typ of kopieer en plak de waarden uit de volgende tabel in het formulier **New TXT Record** (nieuwe TXT-record). 
    
    |**Naam**|**TTL (SEC)**|**TXT (Verwijst naar adres of waarde)**|
    |:-----|:-----|:-----|
    |(laat leeg)  <br/> |3600 (seconden)  <br/> |"MS=msXXXXXXXX"  <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel. [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)  |
       
    ![Netregistry_verificationTXTvalues](../../media/cfe8b05a-fa8b-4dba-9554-7a3466e6c012.png)
  
6. Selecteer **Record toevoegen**.
    
Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.
  
Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.
  
1. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.
    
2. Kies op de pagina **Domeinen** de naam van het domein dat u verifieert. 
    
    
  
3. Kies **Start setup** op de pagina **Setup**.
    
    
  
4. Kies **Verifiëren** op de pagina **Domein verifiëren**.
    
    
  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden
<a name="bkmk_mx"> </a>

1. Ga naar uw domeinpagina van Netregistry via [deze koppeling](https://theconsole.netregistry.com.au/). U wordt gevraagd u aan te melden.
    
    ![Netregistry_login](../../media/80277b0e-547e-4635-aa6a-5d8ebe3fba85.png)
  
2. Selecteer **Manage** (beheren) naast het domein dat u wilt beheren.
    
    ![Netregistry_Manage](../../media/96e2c6e4-21fd-4405-a4fe-b1188400b985.png)
  
3. Selecteer **Zone Manager**.
    
    ![Netregistry_selectZoneManager](../../media/914021f6-dff3-4640-84d6-b83cf8f61cf1.png)
  
4. Verwijder **onder Huidige zonerecords**de standaardMX-records door **Verwijderen** naast elke MX-record in de lijst te selecteren. 
    
    ![Netregistry_MX_remove](../../media/494670a9-8b8d-46e5-8136-05e82212a115.png)
  
5. Kies **mx-record** in de lijst **onder Een zonerecord toevoegen**en selecteer Vervolgens Nieuwe record **maken**.
    
    ![Netregistry_MX_select](../../media/29b60eb9-6c40-490f-9669-e65b65962f37.png)
  
6. Typ of kopieer en plak de waarden uit de volgende tabel in het formulier **Nieuwe MX-record.** 
    
    |**Naam**|**TTL (SEC)**|**Exchange (Adres- of waardeaanspraken)**|**Is de host volledig gekwalificeerd?**|**Voorkeur (prioriteit)**|
    |:-----|:-----|:-----|:-----|:-----|
    |(laat leeg)  <br/> |3600 (seconden)  <br/> | *\<domain-key\>*.mail.protection.outlook.com  <br/> **Let op:** Haal uw *\<domain-key\>* van uw Microsoft-account.  [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)      |(schakel het selectievakje in)  <br/> |10  <br/> Zie Wat is MX-prioriteit? voor meer informatie over prioriteit.  <br/> |
       
    ![Netregistry_MX_values](../../media/518b3da6-4055-4e2d-b5ce-44a0fee25419.png)
  
7. Selecteer **Record toevoegen**.
    
    ![Netregistry_MX_values_AddRecord](../../media/8194cb38-afa0-48ac-831c-fd34b6ad652e.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>De CNAME-records toevoegen die zijn vereist voor Microsoft
<a name="bkmk_cname"> </a>

1. Ga naar uw domeinpagina van Netregistry via [deze koppeling](https://theconsole.netregistry.com.au/). U wordt gevraagd u aan te melden.
    
    ![Netregistry_login](../../media/cbf83dce-86d2-4008-9400-56def4b6fcd7.png)
  
2. Selecteer **Manage** (beheren) naast het domein dat u wilt beheren.
    
    ![Netregistry_Manage](../../media/7bee4b0f-2c1d-43ca-b1bb-9b889ca0c5e4.png)
  
3. Selecteer **Zone Manager**.
    
    ![Netregistry_selectZoneManager](../../media/58384add-0a9d-472b-a5d0-51ec8155fd41.png)
  
4. Kies **onder Een zonerecord toevoegen**de optie **CNAME Record** in de lijst en selecteer Vervolgens Nieuwe record **maken**.
    
    ![Netregistry_CNAME_CreateNewRecord](../../media/7b4f133f-45da-48da-93c0-62f57c786165.png)
  
5. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.
    
    |**Name**|**Type**|**TTL**|**HOST (Adreswaarde of adreswaarde)**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |3600 (seconden)  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |3600 (seconden)  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |3600 (seconden)  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |3600 (seconden)  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |3600 (seconden)  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
       
    ![Netregistry_CNAME_values](../../media/93c479f0-3ce2-491a-9113-6dde1cd7131b.png)
      
6. Selecteer **Record toevoegen**.
    
    ![Netregistry_CNAME_values_AddRecord](../../media/046c8c64-ea71-4530-9fc6-69f0c70993b6.png)
  
7. Herhaal de vorige stappen om de vijf andere CNAME-records te maken.
    
    Typ of kopieer en plak voor elke record de waarden uit de volgende rij van de bovenstaande tabel in de velden voor die record.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Een TXT-record voor SPF toevoegen om spam tegen te gaan
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft. Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat.
  
1. Ga naar uw domeinpagina van Netregistry via [deze koppeling](https://theconsole.netregistry.com.au/). U wordt gevraagd u aan te melden.
    
    ![Netregistry_login](../../media/a841f11f-1c0f-4926-acea-a2b8bb083984.png)
  
2. Selecteer **Manage** (beheren) naast het domein dat u wilt beheren.
    
    ![Netregistry_Manage](../../media/4245bbbb-4e2d-49e7-a89c-679949aa3d18.png)
  
3. Selecteer **Zone Manager**.
    
    ![Netregistry_selectZoneManager](../../media/372e5918-b6dc-4268-8f9a-0aa71d65deef.png)
  
4. Kies **onder Een zonerecord toevoegen**de optie **TXT-record** in de lijst en selecteer **Vervolgens Nieuwe record maken**.
    
    ![Netregistry_TXT_select](../../media/a2930d03-853a-4f1e-9205-d00f25bed35f.png)
  
5. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record. 
    
    > [!NOTE]
    > U moet aanhalingstekens gebruiken voor en na de vermelding in het vak TXT. 
  
    |**Name**|**Type**|**TTL**|**TXT-gegevens (doel)**|
    |:-----|:-----|:-----|:-----|
    |(laat leeg)  <br/> |TXT  <br/> |3600 (seconden)  <br/> |"v=spf1 include:spf.protection.outlook.com -all"  <br/> **Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.           |
   
    ![Netregistry_SPF-TXT-waarden](../../media/a369345a-d774-48bc-8160-b628ab8247f9.png)
  
6. Selecteer **Record toevoegen**.
    
    ![Netregistry_SPF-TXTvalues_AddRecord](../../media/063bfbaf-940a-489f-970f-29c026b4b312.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>De twee SRV-records toevoegen die zijn vereist voor Microsoft
<a name="bkmk_srv"> </a>

1. Ga naar uw domeinpagina van Netregistry via [deze koppeling](https://theconsole.netregistry.com.au/). U wordt gevraagd u aan te melden.
    
    ![Netregistry_login](../../media/accf6584-e5f4-4d68-a641-0f8847f8370f.png)
  
2. Selecteer Naast het domein dat u wilt beheren de optie **Beheren**.
    
    ![Netregistry_Manage](../../media/e0ddc79e-0123-4e24-8380-9645bdb41aac.png)
  
3. Selecteer **Zone Manager**.
    
    ![Netregistry_selectZoneManager](../../media/f122888b-3cc5-40ec-adac-0ede04799d9a.png)
  
4. Kies **onder Een zonerecord toevoegen**de optie **SRV-record** in de lijst en selecteer **Vervolgens Nieuwe record maken**.
    
    ![Netregistry_SRV_select](../../media/e5dab850-acd1-48b8-8b4a-e3b9777cf508.png)
  
5. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.
    
    > [!NOTE]
    > Het veld Naam is een combinatie van de service (bijvoorbeeld _sip) en protocol (bijvoorbeeld _tls). 
  
    |**Type**|**Naam**|**TTL (SEC)**|**Prioriteit**|**Gewicht**|**Poort**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV (service)  <br/> |_sip._tls  <br/> |3600 (seconden)  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |SRV (service)  <br/> |_sipfederationtls._tcp  <br/> |3600 (seconden)  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
       
    ![Netregistry_SRV_values](../../media/49292846-1598-4b8c-9940-db6e10675753.png)
  
6. Selecteer **Record toevoegen**.
    
    ![Netregistry_SRV_values_AddRecord](../../media/abc82061-939f-4757-87e4-0e8f9e43ebcb.png)
  
7. Herhaal de vorige stappen om de andere SRV-record te maken.
    
    Typ of kopieer en plak de waarden uit de tweede rij van de bovenstaande tabel in de vakken voor de tweede record.
    
> [!NOTE]
> Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  

