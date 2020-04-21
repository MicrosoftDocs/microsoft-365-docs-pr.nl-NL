---
title: DNS-records maken bij Freenom voor Microsoft
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
ms.assetid: d8ff45a2-19e3-413d-aa64-a9982bd6633c
description: Lees uw domein verifiëren en DNS-records instellen voor e-mail, Skype voor Bedrijven Online en andere services bij Freenom voor Microsoft.
ms.openlocfilehash: 828a1728606338017383857e4b59d6a62d087fc7
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629561"
---
# <a name="create-dns-records-at-freenom-for-microsoft"></a>DNS-records maken bij Freenom voor Microsoft

[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md) als u niet kunt vinden wat u zoekt. 
  
> [!CAUTION]
> De Freenom-website biedt geen ondersteuning voor SRV-records, wat betekent dat verschillende functies van Skype voor Bedrijven Online en Outlook Web App niet werken. Het maakt niet uit welk Microsoft-abonnement u gebruikt, er zijn aanzienlijke servicebeperkingen en u overschakelen naar een andere DNS-hostingprovider. 
  
Als u ondanks de servicebeperkingen ervoor kiest om uw eigen Microsoft DNS-records op Freenom te beheren, volgt u de stappen in dit artikel om uw domein te verifiëren en DNS-records in te stellen voor e-mail en andere services.
  
Zie Een openbare website gebruiken met Microsoft voor meer informatie over webhosting en DNS voor websites met [Microsoft.](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx)
  
> [!NOTE]
> Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie
<a name="bkmk_txt"> </a>

Voordat u uw domein bij Microsoft gebruikt, moeten we ervoor zorgen dat u eigenaar bent. Uw mogelijkheid om in te loggen op uw account bij uw domeinregistrar en de DNS-record te maken bewijst microsoft dat u eigenaar bent van het domein.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
1. Ga om te beginnen naar de pagina domeinen in Freenom via [deze link.](https://my.freenom.com/) U wordt gevraagd u aan te melden.
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Selecteer **Services**en selecteer **Mijn domeinen**.
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. Selecteer **Domein beheren**voor het domein dat u wilt bewerken.
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Selecteer **Freenom DNS beheren**.
    
    ![Freenom Manage Freenom DNS](../../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. Ga onder **Add Record** naar de kolom **Type** en kies **TXT** in de lijst. 
    
    ![Freenom Add Record type TXT](../../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record. 
    
    |**Name**|**Type**|**TTL**|**Doel**|
    |:-----|:-----|:-----|:-----|
    |(laat leeg)  <br/> |TXT  <br/> |3600 (seconden)  <br/> |MS=msXXXXXXXX  <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de waarde van uw specifieke **bestemming of adrespunt** in de tabel.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Freenom TXT values for verification](../../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. Selecteer **Wijzigingen opslaan**.
    
    ![Freenom TXT record Save Changes](../../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
Nu u de record op de site van uw domeinregistrar hebt toegevoegd, gaat u terug naar Microsoft en vraagt u de record aan.
  
Wanneer Microsoft de juiste TXT-record vindt, wordt uw domein geverifieerd.
  
1. Ga in het Microsoft-beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Instellingendomeinen.</a> **Settings**

    
2. Kies op de pagina **Domeinen** de naam van het domein dat u verifieert. 
    
    
  
3. Kies **Start setup** op de pagina **Setup**.
    
    
  
4. Kies **Verifiëren** op de pagina **Domein verifiëren**.
    
    
  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Voeg een MX-record toe, zodat e-mail voor uw domein naar Microsoft komt
<a name="bkmk_mx"> </a>

1. Ga om te beginnen naar de pagina domeinen in Freenom via [deze link.](https://my.freenom.com/) U wordt gevraagd u aan te melden.
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Selecteer **Services**en selecteer **Mijn domeinen**.
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. Selecteer **Domein beheren**voor het domein dat u wilt bewerken.
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Stel de naam dient voor uw domein op de standaard Freenom-naamservers. Selecteer **Beheerhulpprogramma's**en selecteer **vervolgens Nameservers**.
    
    ![Freenom Nameservers setting](../../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. Controleer of **Standaardnaamservers gebruiken** is geselecteerd en selecteer **Naamservers wijzigen**.
    
    ![Freenom Change Nameservers](../../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. Selecteer **Freenom DNS beheren**.
    
    ![Freenom selecteert Freenom DNS beheren](../../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. Ga onder **Add Record** naar de kolom **Type** en kies **MX** in de lijst. 
    
    ![Freenom Add Record type MX](../../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in de velden voor de nieuwe record. 
    
    |**Name**|**Type**|**TTL**|**Doel**|**Priority**|
    |:-----|:-----|:-----|:-----|:-----|
    |(laat leeg)  <br/> |MX (Mail Exchanger)  <br/> |3600 (seconden)  <br/> |\<domeinsleutel\>.mail.protection.outlook.com  <br/> **Let op:** Haal uw * \<domeinsleutel\> * uit uw Microsoft-account.   [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |10  <br/> Zie [What is MX priority?](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9) voor meer informatie over prioriteit.    <br/> |
   
   ![Freenom MX record](../../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. Selecteer **Wijzigingen opslaan**.
    
    ![Freenom MX record Save Changes](../../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. Als er andere MX-records zijn, verwijdert u ze allemaal. Selecteer Voor elke record **Delete**. Wanneer het bericht Wilt u dit item echt **OK** **verwijderen?**
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>De CNAME-records toevoegen die voor Microsoft vereist zijn
<a name="bkmk_cname"> </a>

1. Ga om te beginnen naar de pagina domeinen in Freenom via [deze link.](https://my.freenom.com/) U wordt gevraagd u aan te melden.
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Selecteer **Services**en selecteer **Mijn domeinen**.
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. Selecteer **Domein beheren**voor het domein dat u wilt bewerken.
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Selecteer **Freenom DNS beheren**.
    
    ![Freenom selecteert Freenom DNS beheren](../../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. Ga onder **Add Record** naar de kolom **Type** en kies **CNAME** in de lijst. 
    
    ![Freenom Add Record type CNAME](../../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. Maak de eerste CNAME-record. Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in de vakken voor de nieuwe record. 
    
    |**Naam**|**Recordtype**|**TTL**|**Doel**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |3600 (seconden)  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |3600 (seconden)  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |3600 (seconden)  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |3600 (seconden)  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |3600 (seconden)  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![Freenom CNAME values](../../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. Selecteer **Wijzigingen opslaan**.
    
    ![Freenom CNAME Save Changes](../../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. Herhaal de vorige stappen om de vijf andere CNAME-records te maken. 
    
    Typ of kopieer en plak voor elke record de waarden uit de volgende rij van de bovenstaande tabel in de velden voor die record.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Een TXT-record voor SPF toevoegen om spam tegen te gaan
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, maakt u geen nieuwe voor Microsoft. Voeg in plaats daarvan de vereiste Microsoft-waarden toe aan de huidige record, zodat u *één* SPF-record hebt die beide waardensets bevat. 

1. Ga om te beginnen naar de pagina domeinen in Freenom via [deze link.](https://my.freenom.com/) U wordt gevraagd u aan te melden.
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Selecteer **Services**en selecteer **Mijn domeinen**.
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. Selecteer **Domein beheren**voor het domein dat u wilt bewerken.
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Selecteer **Freenom DNS beheren**.
    
    ![Freenom selecteert Freenom DNS beheren](../../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. Ga onder **Add Record** naar de kolom **Type** en kies **TXT** in de lijst. 
    
    ![Freenom Add Record type TXT](../../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. Typ of kopieer en plak de volgende waarden in de vakken voor de nieuwe record. 
    
    |**Naam**|**Recordtype**|**TTL**|**Doel**|
    |:-----|:-----|:-----|:-----|
    |(laat leeg)  <br/> |TXT  <br/> |3600 (seconden)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.           |
   
    ![Freenom TXT values for SPF](../../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. Selecteer **Wijzigingen opslaan**.
    
    ![Freenom TXT record for SPF Save Changes](../../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
  

