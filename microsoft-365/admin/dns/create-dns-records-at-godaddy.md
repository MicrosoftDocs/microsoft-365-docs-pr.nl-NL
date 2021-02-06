---
title: DNS-records bij GoDaddy maken voor Microsoft
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
ms.custom:
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: Meer informatie over het verifiëren van uw domein en het instellen van DNS-records voor e-mail, Skype voor Bedrijven Online en andere services bij GoDaddy voor Microsoft.
ms.openlocfilehash: 2b53985dc17f3d124ec2b37dbf0047bce229385c
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126447"
---
# <a name="create-dns-records-at-godaddy-for-microsoft"></a>DNS-records bij GoDaddy maken voor Microsoft

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt.

Als GoDaddy uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online enzovoort in te stellen.

Nadat u deze records bij GoDaddy hebt toevoegt, is uw domein ingesteld voor gebruik met Microsoft-services.

> [!NOTE]
> Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).

## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie
<a name="BKMK_verify"> </a>

Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.

> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.

Voer de onderstaande stappen uit:

1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij GoDaddy via [deze koppeling](https://account.godaddy.com/products/?go_redirect=disabled). U wordt gevraagd u aan te melden.

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. Selecteer **dns onder** Domeinen onder het domein dat u wilt bewerken.

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. Kies **Toevoegen**.

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. Kies **TXT (Text)** in de vervolgkeuzelijst. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.

    |**Recordtype** |**Host**|**TXT-waarde**|**TTL** |
    |:-----|:-----|:-----|:-----|
    |TXT (Text)|@|MS=ms *XXXXXXXX*<br>**Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel. [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)|1 uur  <br>(Selecteer een waarde in de vervolgkeuzelijst.)|

      ![GoDaddy-BP-Verify-1-0](../../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. Kies **Opslaan**.

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

1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij GoDaddy via [deze koppeling](https://account.godaddy.com/products/?go_redirect=disabled). U wordt gevraagd u aan te melden.

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. Selecteer **dns onder** Domeinen onder het domein dat u wilt bewerken.

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. Kies **Toevoegen**.

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. Kies **MX (Mail Exchanger)** in de vervolgkeuzelijst.

    ![GoDaddy-BP-Configure-2-0](../../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.

    (Kies de **TTL-waarde** in de vervolgkeuzelijst.)

    |**Recordtype**|**Host**|**Verwijst naar**|**Priority**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX (Mail Exchanger)  <br/> |@  <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **Opmerking:** Kom uit  *\<domain-key\>*  uw Microsoft-account.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |10  <br/> Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit.    <br/> |1 uur  <br/> |

6. Kies **Opslaan**.

## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>De CNAME-records toevoegen die zijn vereist voor Microsoft
<a name="BKMK_add_CNAME"> </a>

Voer de onderstaande stappen uit:

1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij GoDaddy via [deze koppeling](https://account.godaddy.com/products/?go_redirect=disabled). U wordt gevraagd u aan te melden.

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. Selecteer **dns onder** Domeinen onder het domein dat u wilt bewerken.

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. Kies **Toevoegen**.

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. Kies **CNAME (Alias)** in de vervolgkeuzelijst.

    ![GoDaddy-BP-Configure-3-0](../../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. Maak de eerste CNAME-record.

    Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in de vakken voor de nieuwe record.

    (Kies de **TTL-waarde** in de vervolgkeuzelijst.)

    |**Recordtype**|**Host**|**Verwijst naar**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME (alias)  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |1 uur  <br/> |
    |CNAME (alias)  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |1 uur  <br/> |
    |CNAME (alias)  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |1 uur  <br/> |
    |CNAME (alias)  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |1 uur  <br/> |
    |CNAME (alias)  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment.manage.microsoft.com  <br/> |1 uur  <br/> |



6. Herhaal deze stappen om de volgende CNAME-record toe te voegen totdat u alle zes CNAME-records hebt gemaakt.

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Een TXT-record voor SPF toevoegen om spam tegen te gaan
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft. In plaats daarvan voegt u de vereiste Microsoft-waarden toe aan de huidige record, zodat u beschikt over één  SPF-record die beide sets met waarden bevat.

Voer de onderstaande stappen uit:

1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij GoDaddy via [deze koppeling](https://account.godaddy.com/products/?go_redirect=disabled). U wordt gevraagd u aan te melden.

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. Selecteer **dns onder** Domeinen onder het domein dat u wilt bewerken.

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. Kies **Toevoegen**.

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. Kies **TXT (Text)** in de vervolgkeuzelijst.

    ![GoDaddy-BP-Configure-4-0](../../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. Typ of kopieer en plak de volgende waarden in de vakken voor de nieuwe record.

    (Kies de **TTL-waarde** in de vervolgkeuzelijsten.)

    |**Recordtype**|**Host**|**TXT-waarde**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |TXT (Text)  <br/> |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.           |1 uur  <br/> |

    ![GoDaddy-BP-Configure-4-1](../../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. Kies **Opslaan**.


## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>De twee SRV-records toevoegen die zijn vereist voor Microsoft
<a name="BKMK_add_SRV"> </a>

Voer de onderstaande stappen uit:

1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij GoDaddy via [deze koppeling](https://account.godaddy.com/products/?go_redirect=disabled). U wordt gevraagd u aan te melden.

    ![GoDaddy-BP-Configure-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. Selecteer **dns onder** Domeinen onder het domein dat u wilt bewerken.

    ![GoDaddy-BP-Configure-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. Kies **Toevoegen**.

    ![GoDaddy-BP-Configure-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. Kies **SRV (Service)** in de vervolgkeuzelijst.

    ![GoDaddy-BP-Configure-5-0](../../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. Maak de eerste SRV-record.

    Typ of kopieer en plak de waarden uit de eerste rij van de volgende tabel in de vakken voor de nieuwe record.

    (Kies in **de vervolgkeuzelijsten** het recordtype en de **TTL-waarden.)**

    |**Recordtype**|**Naam**|**Doel**|**Protocol**|**Service**|**Prioriteit**|**Gewicht**|**Poort**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV (service)  <br/> |@  <br/> |sipdir.online.lync.com  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1 uur  <br/> |
    |SRV (service)  <br/> |@  <br/> |sipfed.online.lync.com  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1 uur  <br/> |

    ![GoDaddy-BP-Configure-5-1](../../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. Herhaal **stap 5 om** de andere SRV-record te maken.

7. Kies **Opslaan**.

> [!NOTE]
> Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).
