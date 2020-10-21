---
title: DNS-records bij eNomCentral maken voor Microsoft
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
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: Lees hoe u uw domein verifieert en DNS-records instelt voor e-mail, Skype voor bedrijven online en andere services op eNomCentral voor Microsoft.
ms.openlocfilehash: c60c33f4be94e2f7719fdfc583500c6d1164991d
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646161"
---
# <a name="create-dns-records-at-enomcentral-for-microsoft"></a>DNS-records bij eNomCentral maken voor Microsoft

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.

Als eNomCentral uw DNS-hostingprovider is, voert u de stappen in dit artikel uit om uw domein te verifiëren en DNS-records voor e-mail, Skype voor Bedrijven Online, enzovoort in te stellen.

Nadat u deze records bij eNomCentral hebt toegevoegd, is uw domein ingesteld voor gebruik met Microsoft-services.

> [!NOTE]
> Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).

## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie
<a name="BKMK_verify"> </a>

Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.

> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.

Volg onderstaande stappen of [bekijk de video (start op 0:46)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).

1. Als u wilt beginnen, gaat u [via deze koppeling](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) naar uw pagina met domeinen bij eNom Central. U wordt gevraagd u aan te melden.

   ![eNom voor 1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. Selecteer onder **My Domains**de naam van het domein dat u wilt bewerken.

   ![eNom voor 1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. Kies in de vervolgkeuzelijst **Manage Domain** de optie **Host Records**.

   ![eNom voor 1-1](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)

4. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.

   Kies in de vervolgkeuzelijst de waarde **record type** .

   |Host name|Recordtype|Adres|
   |---|---|---|
   |@|TXT|MS=ms *XXXXXXXX*  <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel. [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)|

   ![eNom voor 1-2](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)

5. Selecteer **Opslaan**.

   ![eNom voor 1-3](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)

6. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.

Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft 365 en vraagt u of Microsoft 365 naar de record wil zoeken.

Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.

1. Ga in het Microsoft-beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.

2. Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.

3. Kies **Start setup** op de pagina **Setup**.

4. Kies **Verifiëren** op de pagina **Domein verifiëren**.

> [!NOTE]
> Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden
<a name="BKMK_add_MX"> </a>

Volg onderstaande stappen of [bekijk de video (start op 3:40)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).

1. Als u wilt beginnen, gaat u [via deze koppeling](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) naar uw pagina met domeinen bij eNom Central. U wordt gevraagd u aan te melden.

   ![eNom voor 1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. Selecteer onder **My Domains**de naam van het domein dat u wilt bewerken.

   ![eNom voor 1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. Kies in de vervolgkeuzelijst **Manage Domain** de optie **Email Settings**.

   ![eNom voor 1-3](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)

4. Kies in de vervolgkeuzelijst **Service Selection** de optie **User (MX)**.

   ![eNom voor 1-4](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)

5. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.

   |Host name|Adres|Pref|
   |---|---|---|
   |@| *\<domain-key\>*  . mail.protection.outlook.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> **Opmerking:** Neem uw  *\<domain-key\>*  van uw Microsoft-account. [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)|10  <br/> Zie [Wat is MX-prioriteit?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) voor meer informatie over prioriteit.   |

   ![eNom voor 2-1](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)

6. Selecteer **Opslaan**.

   ![eNom voor 2-2](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)

7. Als er andere MX-records zijn, schakelt u de selectievakjes voor deze records in om deze te selecteren.

   ![eNom voor 2-3](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)

8. Selecteer **Delete checked**.

   ![eNom voor 2-4](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)

## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>De CNAME-records toevoegen die zijn vereist voor Microsoft
<a name="BKMK_add_CNAME"> </a>

Volg onderstaande stappen of [bekijk de video (start op 4:24)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).

1. Als u wilt beginnen, gaat u [via deze koppeling](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) naar uw pagina met domeinen bij eNom Central. U wordt gevraagd u aan te melden.

   ![eNom voor 1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. Selecteer onder **My Domains**de naam van het domein dat u wilt bewerken.

   ![eNom voor 1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. Kies in de vervolgkeuzelijst **Manage Domain** de optie **Host Records**.

   ![eNom voor 1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. Selecteer **nieuwe rij**.

   ![eNom voor 3-1](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)

5. Typ of kopieer en plak de volgende waarden in de vakken voor de zes nieuwe records.

   Kies in de vervolgkeuzelijst de waarde **record type** .

   |Host name|Recordtype|Adres|
   |---|---|---|
   |autodiscover|CNAME (alias)|autodiscover.outlook.com.  <br/> **Deze waarde MOET eindigen op een punt (.)**|
   |sip|CNAME (alias)|sipdir.online.lync.com.  <br/> **Deze waarde MOET eindigen op een punt (.)**|
   |lyncdiscover|CNAME (alias)|webdir.online.lync.com.  <br/> **Deze waarde MOET eindigen op een punt (.)**|
   |enterpriseregistration|CNAME (alias)|enterpriseregistration.windows.net.  <br/> **Deze waarde MOET eindigen op een punt (.)**|
   |enterpriseenrollment|CNAME (alias)|enterpriseenrollment-s.manage.microsoft.com.  <br/> **Deze waarde MOET eindigen op een punt (.)**|

   ![eNom voor 3-2](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)

6. Selecteer **Opslaan**.

   ![eNom voor 3-3](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Een TXT-record voor SPF toevoegen om spam tegen te gaan
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> U kunt maximaal 1 TXT-record hebben voor SPF voor een domein. Als uw domein meer dan één SPF-record heeft, kan dit resulteren in e-mailfouten, evenals leverings- en spamclassificatieproblemen. Als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe te maken voor Microsoft. In plaats daarvan voegt u de vereiste Microsoft-waarden toe aan de huidige record, zodat u  *één*  SPF-record hebt die beide sets met waarden bevat.

Volg onderstaande stappen of [bekijk de video (start op 5:12)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).

1. Als u wilt beginnen, gaat u [via deze koppeling](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) naar uw pagina met domeinen bij eNom Central. U wordt gevraagd u aan te melden.

   ![eNom voor 1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. Selecteer onder **My Domains**de naam van het domein dat u wilt bewerken.

   ![eNom voor 1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. Kies in de vervolgkeuzelijst **Manage Domain** de optie **Host Records**.

   ![eNom voor 1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.

   Kies in de vervolgkeuzelijst de waarde **record type** .

   |Host name|Recordtype|Adres|
   |---|---|---|
   |@|TXT|v=spf1 include:spf.protection.outlook.com -all  <br/>**Opmerking:** het is raadzaam dit item te kopiëren en te plakken, zodat het spatiegebruik ongewijzigd blijft.|

   ![eNom voor 4-1](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)

5. Selecteer **Opslaan**.

   ![eNom voor 4-2](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)

## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>De twee SRV-records toevoegen die zijn vereist voor Microsoft
<a name="BKMK_add_SRV"> </a>

Volg onderstaande stappen of [bekijk de video (start op 5:50)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).

1. Als u wilt beginnen, gaat u [via deze koppeling](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered) naar uw pagina met domeinen bij eNom Central. U wordt gevraagd u aan te melden.

   ![eNom voor 1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. Selecteer onder **My Domains**de naam van het domein dat u wilt bewerken.

   ![eNom voor 1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. Kies in de vervolgkeuzelijst **Manage Domain** de optie **Host Records**.

   ![eNom voor 1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. Selecteer aan de rechterkant van **nieuwe rij**de optie **SRV-of SPF-record toevoegen**.

   ![eNom voor 5-1](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)

5. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de twee nieuwe records.

   |Service|Protocol|Priority|Dikte|Poort|Doel (hostnaam)|
   |---|---|---|---|---|---|
   |_sip|_tls|100|1|443|sipdir.online.lync.com.  <br/> **Deze waarde MOET eindigen op een punt (.)**|
   |_sipfederationtls|_tcp|100|1|5061|sipfed.online.lync.com.  <br/> **Deze waarde MOET eindigen op een punt (.)**|

   ![eNom voor 5-2](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)

6. Selecteer **Opslaan** .

   ![eNom voor 5-3](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)

> [!NOTE]
> Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).
