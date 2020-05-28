---
title: DNS-records maken bij Dreamhost voor Microsoft
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
ms.assetid: 9c0812e0-908b-4b41-a64b-77f0dbd3db7a
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services bij Dreamhost voor Microsoft.
ms.openlocfilehash: 4b321138892cb4a7b5f67c37ed66f3baf0f6c45a
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400507"
---
# <a name="create-dns-records-at-dreamhost-for-microsoft"></a>DNS-records maken bij Dreamhost voor Microsoft

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Als DreamHost uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Lync enzovoort in te stellen.
 
Nadat u deze records bij DreamHost hebt toegevoegd, wordt uw domein ingesteld om te werken met Microsoft-services.
  
  
> [!NOTE]
> Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie
<a name="BKMK_verify"> </a>

Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
1. Ga om te beginnen [via deze koppeling](https://panel.dreamhost.com/) naar uw domeinenpagina bij DreamHost. U wordt gevraagd u aan te melden.
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. Selecteer op de pagina **Dashboard** **domeinen**en **beheer domeinen**.
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. Selecteer op de pagina **Domeinen beheren** in de sectie **Domein** de optie **DNS** voor het domein dat u wilt bewerken. 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add a custom DNS record** in de vakken voor de nieuwe record. 
    
    (Mogelijk moet u omlaag schuiven.)
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
    |**Name**|**Type**|**Value**|**Opmerking**|
    |:-----|:-----|:-----|:-----|
    |(Laat dit veld leeg.)  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |(Dit veld is optioneel.)  <br/> |
   
   ![Afbeelding van het te maken](../../media/ed4a7d43-eeeb-4ec8-849c-37f81315dc69.png)
  
5. Selecteer **Nu record toevoegen!**
    
    ![Dreamhost-BP-Verify-1-2](../../media/5b89c89b-3a8e-4624-895a-86f3cc4638f6.png)
  
6. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.
  
Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.
  
1. Ga in het Microsoft-beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.

    
2. Kies op de pagina **Domeinen** de naam van het domein dat u verifieert. 
    
    
  
3. Kies **Start setup** op de pagina **Setup**.
    
    
  
4. Kies **Verifiëren** op de pagina **Domein verifiëren**.
    
    
  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden
<a name="BKMK_add_MX"> </a>

Voer de onderstaande stappen uit:
  
1. Ga om te beginnen [via deze koppeling](https://panel.dreamhost.com/) naar uw domeinenpagina bij DreamHost. U wordt gevraagd u aan te melden.
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. Selecteer op **de** dashboardpagina **E-mail**en vervolgens **Aangepast MX**.
    
    ![Dreamhost-BP-Configure-2-1](../../media/58478679-4018-49cc-9d83-371dc5fa4a22.png)
  
3. Selecteer **bewerken** voor het domein dat u wilt bewerken in de sectie **E-mailbezorging** beheren in de kolom **Acties.** 
    
    ![Dreamhost-BP-Configure-2-2](../../media/6eed0be2-6477-4f49-9f90-39e190499a53.png)
  
4. Typ of kopieer en plak de volgende waarden uit de volgende tabel in het gebied **Custom MX Record** in de vakken voor de nieuwe record. 
    
    (Mogelijk moet u omlaag schuiven.)
    
    (Als er andere bestaande MX-records zijn, markeert u deze records om te worden verwijderd.)
    
    |**MX-record (vereist)**|
    |:-----|
    |*\<domain-key\>* 0,mail.protection.outlook.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> De 0 is de MX-prioriteitwaarde. Voeg deze toe aan het begin van de MX-waarde, van de rest van de waarde gescheiden door een spatie.  <br/> **Let op:** Haal uw *\<domain-key\>* van uw Microsoft-account.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Afbeelding van het te maken dat u afbeelding van het huis hebt](../../media/90da1816-e186-4016-ab22-7962f8b86add.png)
  
5. Selecteer **Dit domein wijzigen om nu aangepaste MX-records te gebruiken!**
    
    ![Dreamhost-BP-Configure-2-4](../../media/3221c767-83d3-4f30-9d08-dc998772d2a3.png)
  
6. Als er andere bestaande MX-records zijn, verwijdert u elke record door deze te selecteren en vervolgens op de toets **Delete** op het toetsenbord te drukken. 
    
    ![Dreamhost-BP-Configure-2-5](../../media/1827733c-3609-4b0f-bba1-531ab090da91.png)
  
7. Als u records hebt verwijderd, selecteert u **Nu uw aangepaste MX-records bijwerken!**
    
    ![Dreamhost-BP-Configure-2-6](../../media/177462be-0686-47b7-a389-025dfc8d6526.png)

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Voeg de zes CNAME-records toe die nodig zijn voor Microsoft
<a name="BKMK_add_CNAME"> </a>

Voer de onderstaande stappen uit:
  
1. Ga om te beginnen [via deze koppeling](https://panel.dreamhost.com/) naar uw domeinenpagina bij DreamHost. U wordt gevraagd u aan te melden.
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. Selecteer op de pagina **Dashboard** **domeinen**en **beheer domeinen**.
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. Selecteer op de pagina **Domeinen beheren** in de sectie **Domein** de optie **DNS** voor het domein dat u wilt bewerken. 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. Typ of kopieer en plak de waarden uit de eerste rij in de volgende tabel in het gebied **Add a custom DNS record** in de vakken voor de nieuwe record. 
    
    (Mogelijk moet u omlaag schuiven.)
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
    |**Name**|**Type**|**Value**|**Opmerking**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |(Dit veld is optioneel.)  <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |(Dit veld is optioneel.)  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |(Dit veld is optioneel.)  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |(Dit veld is optioneel.)  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |(Dit veld is optioneel.)  <br/> |
   
    ![Afbeelding van het te maken:Afbeelding van het te maken](../../media/0c4cc587-ea24-47f2-8dc6-a35735b250e6.png)
  
5. Selecteer **Nu record toevoegen!**
    
    ![Dreamhost-BP-Configure-3-2](../../media/b5d4f939-de6d-4d1f-a20a-4eb5fe715281.png)
  
6. Voeg met de voorgaande twee stappen en de waarden van de andere vijf rijen in de tabel elk van de andere vijf CNAME-records toe.

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Een TXT-record voor SPF toevoegen om spam tegen te gaan
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft. Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat.
  
Voer de onderstaande stappen uit:
  
1. Ga om te beginnen [via deze koppeling](https://panel.dreamhost.com/) naar uw domeinenpagina bij DreamHost. U wordt gevraagd u aan te melden.
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. Selecteer op de pagina **Dashboard** **domeinen**en **beheer domeinen**.
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. Selecteer op de pagina **Domeinen beheren** in de sectie **Domein** de optie **DNS** voor het domein dat u wilt bewerken. 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. Typ of kopieer en plak de waarden uit de eerste rij in de volgende tabel in het gebied **Add a custom DNS record** in de vakken voor de nieuwe record. 
    
    (Mogelijk moet u omlaag schuiven.)
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
    |**Name**|**Type**|**Value**|**Opmerking**|
    |:-----|:-----|:-----|:-----|
    |(Laat dit veld leeg.)  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.           |(Dit veld is optioneel.)  <br/> |
   
   ![Afbeelding van het te maken](../../media/cbc4bbca-bdbc-4dc9-b1b7-b55491eb1e53.png)
  
5. Selecteer **Nu record toevoegen!**
    
    ![Dreamhost-BP-Configure-4-2](../../media/2bd7cae8-1fbc-4407-8dfa-06ce37c586c0.png)
  
6. Met de twee voorgaande stappen en de waarden uit de tweede rij in de tabel, moet u de andere SRV-record toevoegen.
    
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>De twee SRV-records toevoegen die zijn vereist voor Microsoft
<a name="BKMK_add_SRV"> </a>

Voer de onderstaande stappen uit:
  
1. Ga om te beginnen [via deze koppeling](https://panel.dreamhost.com/) naar uw domeinenpagina bij DreamHost. U wordt gevraagd u aan te melden.
    
    ![Dreamhost-BP-Configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. Selecteer op de pagina **Dashboard** **domeinen**en **beheer domeinen**.
    
    ![Dreamhost-BP-Configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. Selecteer op de pagina **Domeinen beheren** in de sectie **Domein** de optie **DNS** voor het domein dat u wilt bewerken. 
    
    ![Dreamhost-BP-Configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. Typ of kopieer en plak de waarden uit de eerste rij in de volgende tabel in het gebied **Add a custom DNS record** in de vakken voor de nieuwe record. 
    
    (Mogelijk moet u omlaag schuiven.)
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
    |**Name**|**Type**|**Value**|**Opmerking**|
    |:-----|:-----|:-----|:-----|
    |_sip._tls  <br/> |SRV  <br/> |100 1 443  <br/> sipdir.online.lync.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |(Dit veld is optioneel.)  <br/> |
    |_sipfederationtls._tcp  <br/> |SRV  <br/> |100 1 5061  <br/> sipfed.online.lync.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |(Dit veld is optioneel.)  <br/> |
   
    ![Afbeelding van het te maken:Afbeelding van het te maken](../../media/934eb79f-3617-4b72-802c-c42c7d165283.png)
  
5. Selecteer **Nu record toevoegen!**.
    
    ![Dreamhost-BP-Configure-5-2](../../media/015bc73c-8f88-49ce-87f9-e5a6ea3e10a8.png)
  
6. Met de twee voorgaande stappen en de waarden uit de tweede rij in de tabel, moet u de andere SRV-record toevoegen.
    
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 

  
