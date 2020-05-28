---
title: DNS-records maken op Register.com voor Microsoft
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
ms.assetid: 55bd8c38-3316-48ae-a368-4959b2c1684e
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services op Register.com voor Microsoft.
ms.openlocfilehash: 7b2353b4b6832c9316e302ace4db948e2550a28f
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400326"
---
# <a name="create-dns-records-at-registercom-for-microsoft"></a>DNS-records maken op Register.com voor Microsoft

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Als Register.com uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.
  
Dit zijn de belangrijkste records om toe te voegen. Volg onderstaande stappen of [bekijk de video](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).
  
- [Een TXT-record toevoegen op Register.com om te bevestigen dat u eigenaar van het domein bent](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [De CNAME-records toevoegen die zijn vereist voor Microsoft](#add-the-cname-records-that-are-required-for-microsoft)
    
- [Een TXT-record voor SPF toevoegen om spam tegen te gaan](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [De twee SRV-records toevoegen die zijn vereist voor Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft)
    
Nadat u deze records op Register.com hebt toegevoegd, wordt uw domein ingesteld voor gebruik met Microsoft-services.
  

  
> [!NOTE]
> Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a>Een TXT-record toevoegen op Register.com om te bevestigen dat u eigenaar van het domein bent
<a name="BKMK_verify"> </a>

Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
Volg onderstaande stappen of [bekijk de video (start op 0:44)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Als u wilt beginnen, gaat u [via deze koppeling](https://www.register.com/myaccount/) naar uw pagina met domeinen bij Register.com. U wordt gevraagd u aan te melden.
    
2. Selecteer **Domeinen**.
    
3. Selecteer **Beheren**.
    
4. Zoek de rij met de naam van het domein dat u wilt wijzigen. en selecteer vervolgens in die rij **Beheren**.
    
5. Schuif omlaag naar de sectie **Geavanceerde technische instellingen** en selecteer Vervolgens **TXT Records (SPF) bewerken.**
    
6. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.
    
    |||
    |:-----|:-----|
    |**Host Name** <br/> |**TXT Record** <br/> |
    |@  <br/> |MS=ms *XXXXXXXX*  <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel. [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |
   
7. Selecteer **Doorgaan**.
    
8. Selecteer op de volgende pagina **opnieuw doorgaan** om uw wijzigingen te bevestigen. 
    
9. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft en vraagt u de record aan.
  
Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.
  
1. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.
    
2. Kies op de pagina **Domeinen** de naam van het domein dat u verifieert. 
    
3. Kies **Start setup** op de pagina **Setup**.
    
4. Kies **Verifiëren** op de pagina **Domein verifiëren**.
    
> [!NOTE]
> Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden
<a name="BKMK_add_MX"> </a>

Volg onderstaande stappen of [bekijk de video (start op 3:32)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Als u wilt beginnen, gaat u [via deze koppeling](https://www.register.com/myaccount/) naar uw pagina met domeinen bij Register.com. U wordt gevraagd u aan te melden.
    
2. Selecteer **Domeinen**.
    
3. Selecteer **Beheren**.
    
4. Zoek de rij met de naam van het domein dat u wilt wijzigen. en selecteer vervolgens in die rij **Beheren**.
    
5. Schuif naar de sectie **Geavanceerde technische instellingen** en selecteer Vervolgens Records voor Mail **Exchanger bewerken**.
    
    ![Selecteer Records voor Mail Exchanger bewerken](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.
    
    (Kies de **waarde Prioriteit** in de vervolgkeuzelijst.) 
    
    |****Hostnaam****|****Priority****|****Mail Server****|
    |:-----|:-----|:-----|
    |@  <br/> |High  <br/> Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit.    <br/> | *\<domain-key\>*.mail.protection.outlook.com  <br/>  <br/>**Let op:** Haal uw \<*domain-key*\> van uw Microsoft-account. <br> [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![De waarde uit de tabel kopiëren en plakken](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. Als er al andere MX-records staan vermeld, selecteert u elk van deze records om ze te verwijderen.
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. Selecteer **Doorgaan**.
    
    ![Selecteer Doorgaan](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. Selecteer op de volgende pagina **Opnieuw doorgaan** om uw wijzigingen te bevestigen en op te slaan. 
    
    ![Selecteer Doorgaan](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>De CNAME-records toevoegen die zijn vereist voor Microsoft
<a name="BKMK_add_CNAME"> </a>

Volg onderstaande stappen of [bekijk de video (start op 4:23)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Als u wilt beginnen, gaat u [via deze koppeling](https://www.register.com/myaccount/) naar uw pagina met domeinen bij Register.com. U wordt gevraagd u aan te melden.
    
2. Selecteer **Domeinen**.
    
3. Selecteer **Beheren**.
    
4. Zoek de rij met de naam van het domein dat u wilt wijzigen. en selecteer vervolgens in die rij **Beheren**.
    
5. Schuif naar de sectie **Geavanceerde technische instellingen** en selecteer Vervolgens **Domeinaliasrecords bewerken**.
    
    ![Domeinaliasrecords bewerken selecteren](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. Selecteer **Meer domeinaliassen toevoegen**.
    
    ![Meer domeinenaliassen toevoegen selecteren](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. De vereiste CNAME-records toevoegen.
    
    Typ of kopieer en plak de waarden uit de eerste rij in de volgende tabel in de velden voor de nieuwe record.
    
    |****Eerste veld (zonder label)****|****Verwijst naar****|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com  <br/>  <br/> |
    |sip  <br/> |sipdir.online.lync.com  <br/>  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com <br/>  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/>  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/>  <br/> |
   
     ![De DNS-waarden uit de tabel kopiëren en plakken](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. Wanneer u alle CNAME-records hebt toegevoegd die u nodig hebt, selecteert u **Doorgaan**.
    
    ![Selecteer Doorgaan](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. Selecteer op de volgende pagina **Opnieuw doorgaan** om uw wijzigingen te bevestigen en op te slaan. 
    
    ![Selecteer Doorgaan](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Een TXT-record voor SPF toevoegen om spam tegen te gaan
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft. In plaats hiervan voegt u de vereiste Microsoft-waarden toe aan de huidige record, zodat u beschikt over één SPF-record waarin beide sets waarden zijn opgenomen.  
  
Volg onderstaande stappen of [bekijk de video (start op 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Als u wilt beginnen, gaat u [via deze koppeling](https://www.register.com/myaccount/) naar uw pagina met domeinen bij Register.com. U wordt gevraagd u aan te melden.
    
2. Selecteer **Domeinen**.
    
3. Selecteer **Beheren**.
    
4. Zoek de rij met de naam van het domein dat u wilt wijzigen. en selecteer vervolgens in die rij **Beheren**.
    
5. Schuif naar de sectie **Geavanceerde technische instellingen** en selecteer Vervolgens **TXT Records (SPF) bewerken.**
    
    ![TXT-records bewerken (SPF) selecteren](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.
    
    |****Host Name****|****TXT Record****|
    |:-----|:-----|
    |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.  |
   
     ![De waarden uit de tabel kopiëren en plakken](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. Selecteer **Doorgaan**.
    
    ![Selecteer Doorgaan](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. Selecteer op de volgende pagina **Opnieuw doorgaan** om uw wijzigingen te bevestigen en op te slaan. 
    
    ![Selecteer Doorgaan](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>De twee SRV-records toevoegen die zijn vereist voor Microsoft
<a name="BKMK_add_SRV"> </a>

Volg onderstaande stappen of [bekijk de video (start op 5:55)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Als u wilt beginnen, gaat u [via deze koppeling](https://www.register.com/myaccount/) naar uw pagina met domeinen bij Register.com. U wordt gevraagd u aan te melden.
    
2. Selecteer **Domeinen**.
    
3. Selecteer **Beheren**.
    
4. Zoek de rij met de naam van het domein dat u wilt wijzigen. en selecteer vervolgens in die rij **Beheren**.
    
5. Schuif naar de sectie **Geavanceerde technische instellingen** en selecteer Vervolgens **SRV-records bewerken**.
    
    ![SRV-records bewerken selecteren](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. Voeg als volgt de eerste van de twee SRV-records toe:
    
    Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in de vakken voor de nieuwe record.
    
    (Kies de **waarde Prioriteit** in de vervolgkeuzelijst.) 
    
    |****Service****|****Proto****|****Name****|****Priority****|****Gewicht****|****Port****|****Target****|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |@  <br/> |High  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/>  <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |@  <br/> |High  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/>  <br/> |
   
    ![De waarden uit de tabel kopiëren en plakken](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. Selecteer **Meer SRV-records toevoegen**.
    
    ![Meer SRV-records toevoegen selecteren](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. Voeg als volgt de tweede SRV-record toe:
    
    Typ of kopieer en plak de waarden uit de tweede rij van de bovenstaande tabel in de velden van de tweede record.
    
9. Wanneer u beide SRV-records hebt toegevoegd, selecteert u **Doorgaan**.
    
    ![Selecteer Doorgaan](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. Selecteer op de volgende pagina **Opnieuw doorgaan** om uw wijzigingen te bevestigen en op te slaan. 
    
    ![Selecteer Doorgaan](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md). 
  
