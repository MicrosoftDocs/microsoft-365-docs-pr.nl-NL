---
title: DNS-records maken bij Google Domains voor Microsoft
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: Lees informatie over het verifiëren van uw domein en het instellen van DNS-records voor e-mail, Lync en andere services bij Google Domains voor Microsoft.
ms.openlocfilehash: 6bfe32ba8f77adec97f4ab5ee40e92126be91f10
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049009"
---
# <a name="create-dns-records-at-google-domains-for-microsoft"></a>DNS-records maken bij Google Domains voor Microsoft

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Als Google Domains uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Lync enzovoort in te stellen.
  
Nadat u deze records hebt toegevoegd bij Google Domains, wordt uw domein ingesteld voor gebruik met Microsoft-services.
  

  
> [!NOTE]
> Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Zie Problemen zoeken en oplossen na het toevoegen van [uw domein- of DNS-records in Microsoft](../get-help-with-domains/find-and-fix-issues.md)als u problemen ondervindt met e-mailstroom of andere problemen na het toevoegen van DNS-records. 
  
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie
<a name="BKMK_verify"> </a>

Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
1. Ga eerst naar de pagina met domeinen bij Google Domains via [deze koppeling](https://domains.google.com/registrar). U wordt gevraagd om u aan te melden. U gaat hiervoor als volgt te werk:
    
1. Selecteer **Aanmelden**.
    
2. Voer uw inloggegevens in en selecteer **Opnieuw Aanmelden**.
    
2. Zoek op de pagina **Mijn domeinen** het domein dat u met Microsoft wilt gebruiken en selecteer de koppeling **MANAGE** ernaast. Selecteer IN de linkernavigatie de optie **DNS**.
    
3. Typ of kopieer en plak de waarden uit de volgende tabel in de sectie **Custom resource records** in de vakken voor de nieuwe record. 
    
    (Mogelijk moet u omlaag schuiven.)
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Name** <br/> |**Type** <br/> |**TTL** <br/> |**Data** <br/> |
    |@  <br/> |TXT  <br/> |1H  <br/> |MS=ms *XXXXXXXX*  <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel. [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |
   
4. Kies **Toevoegen**.
    
5. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.
  
Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.
  
1. Ga in het Microsoft-beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.

    
2. Kies op de pagina **Domeinen** de naam van het domein dat u verifieert. 
    
3. Kies **Start setup** op de pagina **Setup**.
    
4. Kies **Verifiëren** op de pagina **Domein verifiëren**.
    
> [!NOTE]
> Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md). 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden
<a name="BKMK_add_MX"> </a>

1. Ga eerst naar de pagina met domeinen bij Google Domains via [deze koppeling](https://domains.google.com/registrar). U wordt gevraagd om u aan te melden. U gaat hiervoor als volgt te werk:
    
2. Selecteer **Aanmelden**.
    
3. Voer uw inloggegevens in en selecteer **Opnieuw Aanmelden**.
4. Selecteer **op** de pagina Domeinen in de sectie **Domein** de optie **DNS configureren** voor het domein dat u wilt bewerken.
    
    > [!IMPORTANT]
    > Als u een G Suite-e-mailaccount hebt, moet u eerst de aan dit account gekoppelde MX-records verwijderen. De G Suite MX-records voorkomen dat u andere MX-records toevoegt, inclusief die welke voor Microsoft vereist zijn. Als u de Suite G-records verwijdert, wordt uw G Suite-account niet verwijderd. Voer de volgende stappen uit als u de MX-records voor G Suite wilt verwijderen. 
  
5. Selecteer in de sectie **Synthetische records** in het gebied **G Suite** de optie **Verwijderen**.
    
    (Mogelijk moet u omlaag schuiven.)
    
    ![Selecteren in de sectie Synthetische records](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. Selecteer **Verwijderen**.
    
    ![Selecteren Verwijderen](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. Typ of kopieer en plak de waarden uit de volgende tabel in de sectie **Custom resource records** in de vakken voor de nieuwe record. 
    
    (Mogelijk moet u omlaag schuiven.)
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
    |**Name**|**Type**|**TTL**|**Data**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |1H  <br/> |0  *\<domeinsleutel\>*  .mail.protection.outlook.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> De **0** is de MX-prioriteitwaarde. Voeg deze toe aan het begin van de MX-waarde, van de rest van de waarde gescheiden door een spatie.  <br/> **Opmerking**: Uw \<*domeinsleutel*\> kunt u ophalen uit uw Microsoft-account.  [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit. <br/> |
   
    ![Waarden typen of plakken in de sectie Aangepaste resourcerecords](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. Kies **Toevoegen**.
    
    ![Selecteer Toevoegen](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. Als er andere aangepaste MX-records zijn, verwijdert u deze.
    
1. Selecteer **Bewerken** in de rij MX-record. 
    
    ![Selecteer Bewerken in de rij MX-record](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. Selecteer voor elk van de andere Aangepaste MX-records de vermelding in het vak **Gegevens** en druk vervolgens op **delete** op het toetsenbord om die record te verwijderen. 
    
    Ga door totdat u de **Data**-vermelding voor alle andere MX-records hebt verwijderd. 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. Wanneer u de **gegevensvermelding** voor elk van de andere MX-records hebt verwijderd, selecteert u **Opslaan** om uw wijzigingen op te slaan. 
    
    ![Selecteer Opslaan](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a>Voeg de vijf CNAME-records toe die nodig zijn voor Microsoft

1. Ga naar de pagina [Google Domeinen]https://domains.google.com/registrar) en meld u aan om aan de slag te gaan.
    
2. Selecteer **op** de pagina Domeinen in de sectie **Domein** de optie **DNS configureren** voor het domein dat u wilt bewerken. 
    
3. Voeg de eerste CNAME-record toe.
    
    Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in de sectie **Custom resource records** in de vakken voor de nieuwe record. 
    
    (Mogelijk moet u omlaag schuiven.)
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
    |**Name**|**Type**|**TTL**|**Data**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |1H  <br/> |autodiscover.outlook.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
    |sip  <br/> |CNAME  <br/> |1H  <br/> |sipdir.online.lync.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |1H  <br/> |webdir.online.lync.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |1H  <br/> |enterpriseregistration.windows.net.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |1H  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
   
    ![Waarden typen of plakken in de sectie Aangepaste resourcerecords](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. Kies **Toevoegen**.
    
    ![Selecteer Toevoegen](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. Voeg de andere vier CNAME-records toe.
    
    Maak in de sectie **Aangepaste resourcerecords** een record met de waarden uit de volgende rij in de tabel en selecteer vervolgens opnieuw **Toevoegen** om die record te voltooien. 
    
    Herhaal dit proces totdat u alle vereiste CNAME-records hebt gemaakt.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Een TXT-record voor SPF toevoegen om spam tegen te gaan

> [!IMPORTANT]
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft. In plaats hiervan voegt u de vereiste Microsoft-waarden toe aan de huidige record, zodat u beschikt over één SPF-record waarin beide sets waarden zijn opgenomen. Hebt u voorbeelden nodig? Bekijk deze [Externe Domain Name System-records voor Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords). Voor het valideren van uw SPF-record, kunt u een van deze [SPF-validatiehulpmiddelen](../setup/domains-faq.md) gebruiken. 
  
1. Ga eerst naar de pagina met domeinen bij Google Domains via [deze koppeling](https://domains.google.com/registrar). U wordt gevraagd om u aan te melden. U gaat hiervoor als volgt te werk:
    
1. Selecteer **Aanmelden**.
    
2. Voer uw inloggegevens in en selecteer **Opnieuw Aanmelden**.
    
3. Selecteer **op** de pagina Domeinen in de sectie **Domein** de optie **DNS configureren** voor het domein dat u wilt bewerken. 
    
4. Selecteer in de sectie **Aangepaste resourcerecords** in de rij TXT-record de optie **Bewerken**. 
    
    > [!IMPORTANT]
    > Google Domains slaat MX-records op als een set die meerdere records kan bevatten. Wanneer u minimaal één andere TXT-record hebt, zoals de TXT-record die u hebt gebruikt om uw domein te verifiëren, moet u de nieuwe TXT-records aan deze recordset toevoegen. Als u extra TXT-records als afzonderlijke vermeldingen probeert toe te voegen, wordt het foutbericht **Duplicate record** (Dubbele record) weergegeven. 
  
    ![Bewerken selecteren in de rij TXT-record](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. Selecteer het **besturingselement (+).** 
    
    ![Het plusbesturingselement selecteren](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.
    
    (Mogelijk moet u omlaag schuiven.)
    
    |**Data**|
    |:-----|
    |v=spf1 include:spf.protection.outlook.com -all  <br/> 

    > [!NOTE]
    > Het is raadzaam dit item te kopiëren en te plakken, zodat alle spatiëring ongewijzigd blijft.           
   
   ![Waarden typen of plakken in de sectie Aangepaste resourcerecords](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. Kies **Opslaan**.
    
    ![Selecteer Opslaan](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>De twee SRV-records toevoegen die zijn vereist voor Microsoft
<a name="BKMK_add_SRV"> </a>

1. Ga eerst naar de pagina met domeinen bij Google Domains via [deze koppeling](https://domains.google.com/registrar). U wordt gevraagd om u aan te melden. U gaat hiervoor als volgt te werk:
    
2. Selecteer **Aanmelden**.
    
3. Voer uw inloggegevens in en selecteer **Opnieuw Aanmelden**.
    
4. Selecteer **op** de pagina Domeinen in de sectie **Domein** de optie **DNS configureren** voor het domein dat u wilt bewerken. 
    
5. Voeg de eerste SRV-record toe.
    
    Typ of kopieer en plak de waarden uit de volgende tabel in de sectie **Custom resource records** in de vakken voor de nieuwe record. 
    
    (Mogelijk moet u omlaag schuiven.)
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
    |**Name**|**Type**|**TTL**|**Data**|
    |:-----|:-----|:-----|:-----|
    |_sip._tls|SRV|1H|100 1 443 sipdir.online.lync.com. **Deze waarde MOET eindigen met een periode (.)** **Let op:** We raden u aan dit item te kopiëren en te plakken, zodat alle afstand correct blijft.           |
    |_sipfederationtls._tcp|SRV|1H|100 1 5061 sipfed.online.lync.com. **Deze waarde MOET eindigen op een punt (.)**

    Het is raadzaam dit item te kopiëren en te plakken, zodat alle spatiëring ongewijzigd blijft.       
   
    ![Waarden typen of plakken in de sectie Aangepaste resourcerecords](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. Kies **Toevoegen**.
    
    ![Selecteer Toevoegen](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. Voeg de andere SRV-record toe.
    
    Maak in de sectie **Aangepaste resourcerecords** een record met de waarden uit de tweede rij in de tabel en selecteer vervolgens opnieuw **Toevoegen** om die record te voltooien. 
    
    > [!NOTE]
    > Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md). 
  
