---
title: DNS-records bij Network Solutions voor Microsoft maken
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
ms.assetid: 1dc55f9f-5309-450f-acc3-b2b4119c8be3
description: Lees hoe u uw domein verifieert en DNS-records instelt voor e-mail, Skype voor bedrijven online en andere services op Network Solutions voor Microsoft.
ms.openlocfilehash: 9cb403bb8b469f2d7f4e6138ba5833120ea53585
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657789"
---
# <a name="create-dns-records-at-network-solutions-for-microsoft"></a>DNS-records bij Network Solutions voor Microsoft maken

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt. 
  
Als Network Solutions uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.
  
Dit zijn de belangrijkste records om toe te voegen. Volg onderstaande stappen of [bekijk de video](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099). 
  
- [Een TXT-record toevoegen voor verificatie](#add-a-txt-record-for-verification)
    
- [Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [De CNAME-records toevoegen die zijn vereist voor Microsoft](#add-the-cname-records-that-are-required-for-microsoft)
    
- [Een TXT-record voor SPF toevoegen om spam tegen te gaan](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [De twee SRV-records toevoegen die zijn vereist voor Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft)
    
Nadat u deze records bij Network Solutions hebt toegevoegd, is uw domein ingesteld voor gebruik met Microsoft-services.
  

  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie
<a name="BKMK_verify"> </a>

Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
Volg onderstaande stappen of [bekijk de video (start op 0:47)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).
  
1. Als u wilt beginnen, gaat u [via deze koppeling](https://www.networksolutions.com/manage-it) naar uw pagina met domeinen bij Network Solutions. U wordt gevraagd u aan te melden.
    
    > [!IMPORTANT]
    > Voordat u de knop **login** selecteert, kiest u eerst **Manage My Domain names** in de vervolgkeuzelijst **Log in to:** . 
  
    ![Mijn domeinnamen beheren kiezen en aanmelden bij Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. Schakel het selectievakje in naast de naam van het domein dat u wilt wijzigen.
    
    ![Het selectievakje voor uw domein selecteren](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. Selecteer **Edit DNS**.
    
    ![Selecteer Edit DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. Selecteer **Manage Advanced DNS records**.
    
    (Mogelijk moet u omlaag schuiven.)
    
    ![Geavanceerde DNS-records beheren selecteren](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. Schuif omlaag naar de sectie **Text (TXT records)** en selecteer vervolgens **Edit TXT records**.
    
    ![Selecteer TXT-records bewerken](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.
    
    |**Host**|**TTL**|**Tekst**|
    |:-----|:-----|:-----|
    |@  <br/> (In het systeem wordt deze waarde gewijzigd in **@ (None)** wanneer u de record opslaat.)  <br/> |3600  <br/> |MS=ms *XXXXXXXX*  <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel.  [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)   |
       
    ![Waarden in de vakken voor de nieuwe recordtypen of plakken](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. Selecteer **Doorgaan**.
    
    ![Selecteer Doorgaan](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. Selecteer **Save Changes**.
    
    ![Selecteer Save Changes.](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.
  
Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.

1. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.
    
2. Kies op de pagina **Domeinen** de naam van het domein dat u verifieert. 
    
    
  
3. Kies **Start setup** op de pagina **Setup**.
    
    
  
4. Kies **Verifiëren** op de pagina **Domein verifiëren**.
    
    
  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden
<a name="BKMK_add_MX"> </a>

Volg onderstaande stappen of [bekijk de video (start op 3:51)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).
  
1. Als u wilt beginnen, gaat u [via deze koppeling](https://www.networksolutions.com/manage-it) naar uw pagina met domeinen bij Network Solutions. U wordt gevraagd u aan te melden.
    
    > [!IMPORTANT]
    > Voordat u de knop **login** selecteert, kiest u eerst **Manage My Domain names** in de vervolgkeuzelijst **Log in to:** . 
  
    ![Mijn domeinnamen beheren kiezen en aanmelden bij Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. Schakel het selectievakje in naast de naam van het domein dat u wilt wijzigen.
    
    ![Het selectievakje voor uw domein selecteren](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. Selecteer **Edit DNS**.
    
    ![Selecteer Edit DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. Selecteer **Manage Advanced DNS records**.
    
    (Mogelijk moet u omlaag schuiven.)
    
    ![Geavanceerde DNS-records beheren selecteren](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. Schuif omlaag naar de sectie **mail servers (MX records)** en selecteer vervolgens **Edit MX records**.
    
    ![MX-records bewerken selecteren](../../media/74b4e412-9073-4d2d-8710-fe340b223798.png)
  
6. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.
    
    |**Prioriteit**|**TTL**|**Mail Server**|
    |:-----|:-----|:-----|
    |10  <br/> Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit.    <br/> |3600  <br/> | *\<domain-key\>*  . mail.protection.outlook.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> **Opmerking:** Neem uw  *\<domain-key\>*  van uw Microsoft-account. [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![Waarden in de vakken voor de nieuwe recordtypen of plakken](../../media/0bb96872-cc6e-4dfa-a649-fb7efbbf0012.png)
  
7. Selecteer **Doorgaan**.
    
    ![Selecteer Doorgaan](../../media/963f758b-e79d-4452-8340-7eba8a3972c9.png)
  
8. Selecteer **Save Changes**.
    
    ![Selecteer Save Changes.](../../media/7c2f784a-6dee-4364-866c-ad7202ef1fc2.png)
  
9. Als er andere MX-records zijn, verwijdert u deze allemaal door voor elke record **Delete** te selecteren. 
    
    ![Select the Delete check box for other MX records](../../media/709d6133-9f5d-490a-a91e-95e21ca94695.png)
  
10. Wanneer deze allemaal zijn geselecteerd, selecteert u **Doorgaan**.
    
    ![Selecteer Doorgaan](../../media/4710f988-0bbc-4ba7-bf31-ca2392b2900e.png)
  
11. Selecteer **Save Changes**.
    
    ![Selecteer Save Changes.](../../media/24432ec6-666b-4612-9488-37c06437959b.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>De CNAME-records toevoegen die zijn vereist voor Microsoft
<a name="BKMK_add_CNAME"> </a>

Volg onderstaande stappen of [bekijk de video (start op 4:43)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).
  
1. Als u wilt beginnen, gaat u [via deze koppeling](https://www.networksolutions.com/manage-it) naar uw pagina met domeinen bij Network Solutions. U wordt gevraagd u aan te melden.
    
    > [!IMPORTANT]
    > Voordat u de knop **login** selecteert, kiest u eerst **Manage My Domain names** in de vervolgkeuzelijst **Log in to:** . 
  
    ![Mijn domeinnamen beheren kiezen en aanmelden bij Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. Schakel het selectievakje in naast de naam van het domein dat u wilt wijzigen.
    
    ![Het selectievakje voor uw domein selecteren](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. Selecteer **Edit DNS**.
    
    ![Selecteer Edit DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. Selecteer **Manage Advanced DNS records**.
    
    (Mogelijk moet u omlaag schuiven.)
    
    ![Geavanceerde DNS-records beheren selecteren](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. Schuif omlaag naar de sectie **Host Aliases (CNAME records)** en selecteer vervolgens **Edit CNAME records**.
    
    ![Selecteer CNAME-records bewerken onder gast aliassen](../../media/2d0a4666-8d40-48f4-886c-64a5157baaf5.png)
  
6. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de vier nieuwe records.
    
    |**Alias**|**TTL**|**Refers to Host Name**|**Other Host          (selecteer het keuzerondje **Other Host**)**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |3600  <br/> |(Geen instelling)  <br/> |autodiscover.outlook.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
    |sip  <br/> |3600  <br/> |(Geen instelling)  <br/> |sipdir.online.lync.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
    |lyncdiscover  <br/> |3600  <br/> |(Geen instelling)  <br/> |webdir.online.lync.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
    |enterpriseregistration  <br/> |3600  <br/> |(Geen instelling)  <br/> |enterpriseregistration.windows.net  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
    |enterpriseenrollment  <br/> |3600  <br/> |(Geen instelling)  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
    
    ![Waarden voor de nieuwe records typen of plakken](../../media/5ce0b30c-b46c-4778-aa5a-fb5e2f0961c1.png)
  
7. Wanneer u alle benodigde CNAME-records hebt toegevoegd, selecteert u **continue**.
    
    ![Selecteer Doorgaan](../../media/4978bd8b-f6a6-458d-9522-ad612b301c4a.png)
  
8. Selecteer **Save Changes**.
    
    ![Selecteer Save Changes.](../../media/f005c38a-0d8d-4c61-bec6-15e60c89aa5a.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Een TXT-record voor SPF toevoegen om spam tegen te gaan
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft. In plaats daarvan voegt u de vereiste Microsoft-waarden toe aan de huidige record, zodat u  *één*  SPF-record hebt die beide sets met waarden bevat. 
  
Volg onderstaande stappen of [bekijk de video (start op 5:35)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).
  
1. Als u wilt beginnen, gaat u [via deze koppeling](https://www.networksolutions.com/manage-it) naar uw pagina met domeinen bij Network Solutions. U wordt gevraagd u aan te melden.
    
    > [!IMPORTANT]
    > Voordat u de knop **login** selecteert, kiest u eerst **Manage My Domain names** in de vervolgkeuzelijst **Log in to:** . 
  
    ![Mijn domeinnamen beheren kiezen en aanmelden bij Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. Schakel het selectievakje in naast de naam van het domein dat u wilt wijzigen.
    
    ![Het selectievakje voor uw domein selecteren](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. Selecteer **Edit DNS**.
    
    ![Selecteer Edit DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. Selecteer **Manage Advanced DNS records**.
    
    (Mogelijk moet u omlaag schuiven.)
    
    ![Geavanceerde DNS-records beheren selecteren](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. Schuif omlaag naar de sectie **Text (TXT records)** en selecteer vervolgens **Edit TXT records**.
    
    ![Selecteer TXT-records bewerken onder tekst](../../media/a69a2631-6da2-4e81-99ab-9a9ab9b30b07.png)
  
6. Typ of kopieer en plak de volgende waarden in de vakken voor de nieuwe record.
    
    |**Host**|**TTL**|**Tekst**|
    |:-----|:-----|:-----|
    |@  <br/> (In het systeem wordt deze waarde gewijzigd in **@ (None)** wanneer u de record opslaat.)  <br/> |3600  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft. |
       
    ![Waarden voor de nieuwe recordtypen of plakken](../../media/11564eca-e2ee-4f17-af2b-a00eb7c157db.png)
  
7. Selecteer **Doorgaan**.
    
    ![Selecteer Doorgaan](../../media/482a8dae-0c79-47c4-8bd8-87965683de24.png)
  
8. Selecteer **Save Changes**.
    
    ![Selecteer Save Changes.](../../media/600b8c6d-184f-4213-a50e-8f119ebf3ff0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>De twee SRV-records toevoegen die zijn vereist voor Microsoft
<a name="BKMK_add_SRV"> </a>

Volg onderstaande stappen of [bekijk de video (start op 6:18)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).
  
1. Als u wilt beginnen, gaat u [via deze koppeling](https://www.networksolutions.com/manage-it) naar uw pagina met domeinen bij Network Solutions. U wordt gevraagd u aan te melden.
    
    > [!IMPORTANT]
    > Voordat u de knop **login** selecteert, kiest u eerst **Manage My Domain names** in de vervolgkeuzelijst **Log in to:** . 
  
    ![Mijn domeinnamen beheren kiezen en aanmelden bij Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. Schakel het selectievakje in naast de naam van het domein dat u wilt wijzigen.
    
    ![Het selectievakje voor uw domein selecteren](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. Selecteer **Edit DNS**.
    
    ![Selecteer Edit DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. Selecteer **Manage Advanced DNS records**.
    
    (Mogelijk moet u omlaag schuiven.)
    
    ![Geavanceerde DNS-records beheren selecteren](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. Schuif omlaag naar de sectie **service (SRV records)** en selecteer vervolgens **Edit SRV records**.
    
    ![Selecteer SRV-records bewerken onder service](../../media/9a9248ea-5de5-4e16-9364-f7600fa371f5.png)
  
6. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de twee nieuwe records.
    
    (Kies in de vervolgkeuzelijsten de waarden **Service** en **Protocol**.) 
    
    |**Service**|**Protocol**|**TTL**|**Prioriteit**|**Gewicht**|**Poort**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |3600  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |3600  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
       
    ![Waarden voor de nieuwe records typen of plakken](../../media/86968d1c-8e43-4e61-aeaa-37fc7d7ef7a7.png)
  
7. Selecteer **Doorgaan**.
    
    ![Selecteer Doorgaan](../../media/bfe2c778-5d2b-4bb6-a79d-c3ff9caf9e1e.png)
  
8. Selecteer **Save Changes**.
    
    ![Selecteer Save Changes.](../../media/6d323126-0ebe-45ab-8567-c234711d84c7.png)
  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
