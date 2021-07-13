---
title: Naamservers wijzigen voor het instellen van Microsoft 365 domeinregistrar
f1.keywords:
- CSH
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- okr_smb
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: Meer informatie over het toevoegen en instellen van uw domein in Microsoft 365 zodat uw services zoals e-mail en Skype voor Bedrijven Online uw eigen domeinnaam gebruiken.
ms.openlocfilehash: c2de2d8b75aaf50bd1d19d3fd3b507fd476d4847
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393929"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a>Naamservers wijzigen voor het instellen van Microsoft 365 domeinregistrar

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt.

Volg deze instructies voor het toevoegen en instellen van uw domein in Microsoft 365 zodat uw services zoals e-mail en Teams uw eigen domeinnaam gebruiken. Hiervoor verifieert u uw domein en wijzigt u de naamservers van uw domein in Microsoft 365 zodat de juiste DNS-records voor u kunnen worden ingesteld. Volg deze stappen als in de volgende instructies uw situatie wordt beschreven:

- U hebt uw eigen domein en wilt dit instellen voor het werken met Microsoft 365.

- U wilt Microsoft 365 dns-records voor u beheren. (Als u wilt, kunt u [uw eigen DNS-records beheren](../setup/add-domain.md).)

## <a name="add-a-txt-or-mx-record-for-verification"></a>Een TXT- of MX-record toevoegen voor verificatie

> [!NOTE]
> U hoeft standaard slechts een van deze records te maken. De voorkeur gaat uit naar het recordtype TXT, maar deze wordt niet door alle DNS-hostingproviders ondersteund. In dat geval kunt u in plaats hiervan een MX-record maken.

Voordat u uw domein met Microsoft 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft 365 bewezen.

> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen.

### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a>Zoek het gebied op de website van uw DNS-hostingprovider waar u een nieuwe record kunt maken

1. Meld u aan bij de website van uw DNS-hostingprovider.

2. Selecteer uw domein.

3. Zoek de pagina waarop u DNS-records voor uw domein kunt bewerken.

### <a name="create-the-record"></a>De record maken

Voer een van de volgende handelingen uit, afhankelijk van of u een TXT-record of een MX-record maakt:

**Als u een TXT-record maakt, gebruikt u deze waarden:**

<br>

****

|Record type|Alias of hostnaam|Waarde|TTL|
|---|---|---|---|
|TXT|Voer een van de volgende handelingen uit: Typ **@** of laat het veld leeg, of typ de naam van uw domein.  <p> **Opmerking:** Verschillende DNS-hosts hebben verschillende vereisten voor dit veld.|MS=ms *XXXXXXXX* <p> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Microsoft 365. [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)|Stel deze waarde in op **1 uur** of op het equivalent in minuten ( **60** ), seconden ( **3600** ) enzovoort.|
|||||

**Als u een MX-record maakt, gebruikt u deze waarden:**

<br>

****

|Record type|Alias of hostnaam|Waarde|Priority|TTL|
|---|---|---|---|---|
|MX|Typ **@** of uw domeinnaam. |MS=ms *XXXXXXXX* **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Microsoft 365. [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)|Gebruik een lagere prioriteit dan de prioriteit voor bestaande MX-records voor **Prioriteit** om conflicten met de MX-record voor de e-mailstroom te voorkomen. Zie [Wat is MX-prioriteit?](../setup/domains-faq.yml) voor meer informatie over prioriteit.|Stel deze waarde in op **1 uur** of op het equivalent in minuten ( **60** ), seconden ( **3600** ) enzovoort.|
||||||

### <a name="save-the-record"></a>De record opslaan

Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft 365 en vraagt u of Microsoft 365 naar de record wil zoeken.

Wanneer in Microsoft 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.

1. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.

2. Kies op de pagina **Domeinen** de naam van het domein dat u verifieert.

3. Kies **Start setup** op de pagina **Setup**.

4. Kies **Verifiëren** op de pagina **Domein verifiëren**.

> [!NOTE]
> Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md).

## <a name="change-your-domains-nameserver-ns-records"></a>De naamserverrecords (NS-records) van uw domein wijzigen

Wanneer u bij de laatste stap van de wizard Domeinen instellen in Microsoft 365, hebt u nog één taak over. Als u uw domein wilt instellen met Microsoft 365-services, zoals e-mail, wijzigt u de naamserverrecords van uw domein (of NS) bij uw domeinregistrar om te wijzen naar de Microsoft 365 primaire en secundaire naamservers. Omdat u Microsoft 365 DNS host, worden de vereiste DNS-records voor uw services automatisch voor u ingesteld. U kunt de naamserverrecords zelf bijwerken door de stappen in de Help-inhoud te volgen die uw domeinregistrar op de website heeft geplaatst. Als u niet bekend bent met DNS, neemt u contact op met de ondersteuning van de domeinregistrar.

::: moniker range="o365-worldwide"

Als u de naamservers van het domein zelf wilt wijzigen op de website van de domeinregistrar, volgt u deze stappen:

1. Zoek het gebied op de website van de domeinregistrar waar u de naamservers voor uw domein of een gebied kunt wijzigen waar u aangepaste naamservers kunt gebruiken.

2. Maak naamserverrecords of bewerk de bestaande naamserverrecords om aan de volgende waarden te komen:

    - Voornaamserver: ns1.bdm.microsoftonline.com
    - Tweede naamserver: ns2.bdm.microsoftonline.com
    - Derde naamserver: ns3.bdm.microsoftonline.com
    - Vierde naamserver: ns4.bdm.microsoftonline.com

   > [!TIP]
   > Het is het beste om alle vier records toe te voegen, maar als uw registrar slechts twee records ondersteunt, voegt u ns1.bdm.microsoftonline.com **en** **ns2.bdm.microsoftonline.com.**

3. Sla uw wijzigingen op.

> [!CAUTION]
> Wanneer u de NS-records van uw domein wijzigt om te wijzen naar de Microsoft 365 naamservers, worden alle services beïnvloed die momenteel aan uw domein zijn gekoppeld. Als u een of meer stappen van de wizard hebt overgeslagen, zoals het toevoegen van e-mailadressen, of als u uw domein gebruikt voor blogs, winkelwagentjes of andere services, zijn er extra stappen nodig. De kans bestaat namelijk dat de overgang uitvaltijd van de service tot gevolg heeft, en dat u bijvoorbeeld geen toegang meer heeft tot uw e-mail of dat uw huidige website ontoegankelijk wordt.

::: moniker-end

::: moniker range="o365-21vianet"

1. Zoek het gedeelte op de website van de domeinregistrar waarop u de naamservers voor uw domein kunt wijzigen.

2. Maak twee naamserverrecords, of bewerk de bestaande naamserverrecords zodat ze overeenkomen met de volgende waarden:

   - Voornaamserver: ns1.dns.partner.microsoftonline.cn
   - Tweede naamserver: ns2.dns.partner.microsoftonline.cn

   > [!TIP]
   > U moet ten minste twee naamserverrecords gebruiken. Als er andere naamservers worden vermeld, kunt u deze verwijderen of wijzigen in ns3.dns.partner.microsoftonline.cn **en** **ns4.dns.partner.microsoftonline.cn.**

3. Sla uw wijzigingen op.

> [!CAUTION]
> Wanneer u de NS-records van uw domein wijzigt om te wijzen naar de Office 365 beheerd door 21Vianet-naamservers, worden alle services beïnvloed die momenteel aan uw domein zijn gekoppeld. Als u een of meer stappen van de wizard hebt overgeslagen, zoals het toevoegen van e-mailadressen, of als u uw domein gebruikt voor blogs, winkelwagentjes of andere services, zijn er extra stappen nodig. De kans bestaat namelijk dat de overgang uitvaltijd van de service tot gevolg heeft, en dat u bijvoorbeeld geen toegang meer heeft tot uw e-mail of dat uw huidige website ontoegankelijk wordt.

::: moniker-end

Hierna volgt een voorbeeld van extra stappen die mogelijk zijn vereist voor de hosting van e-mail en websites:

- Verplaats alle e-mailadressen die uw domein gebruiken naar Microsoft 365 voordat u uw NS-records wijzigt.

- Wilt u een domein toevoegen dat momenteel wordt gebruikt met een websiteadres, zoals www.fourthcoffee.com? U kunt onderstaande stappen ondernemen terwijl u het domein toevoegt om de website gehost te houden op de locatie waar de site nu wordt gehost, zodat personen nog steeds naar de website kunnen gaan nadat u de NS-records van het domein hebt gewijzigd om te wijzen naar Microsoft 365.

1. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.

2. Selecteer een domein op de pagina **Domeinen**.

3. Selecteer op de pagina domeindetails het **tabblad DNS-records.**

4. Selecteer **Record toevoegen.**

5. Selecteer in **het deelvenster Een aangepaste DNS-record** toevoegen in de vervolgkeuzelijst **Type** de optie **A (adres).**

6. Typ in **het vak Hostnaam** of Alias **@** .

7. Typ in **het vak IP-adres** het statische IP-adres voor de website waarop het momenteel wordt gehost. Bijvoorbeeld 172.16.140.1.

   > [!IMPORTANT]
   > Dit moet een statisch _IP-adres_ voor de website zijn, geen _dynamisch_ IP-adres. Neem contact op met de site die uw website host om te controleren of u een statisch IP-adres voor uw openbare website kunt krijgen.

8. Als u de TTL-instelling voor de record wilt wijzigen, selecteert u een nieuwe tijdsduur in de **vervolgkeuzelijst TTL.** Ga anders verder met stap 9.

9. Selecteer **Opslaan**.

U kunt eveneens een CNAME-record maken om klanten te helpen bij het zoeken van uw website.

1. Selecteer **Record toevoegen.**
2. Selecteer in **het deelvenster Een aangepaste DNS-record** toevoegen in de vervolgkeuzelijst **Type** de optie **CNAME (Alias).**
3. Typ www in het vak Hostnaam **of** **Alias.**
4. Typ in **het vak** Adrespunten de volledig gekwalificeerde domeinnaam (FQDN) voor uw website. Bijvoorbeeld **contoso.5om**.
5. Als u de TTL-instelling voor de record wilt wijzigen, selecteert u een nieuwe tijdsduur in de **vervolgkeuzelijst TTL.** Ga anders verder met stap 6.
6. Kies **Opslaan**.

Nadat de naamserverrecords zijn bijgewerkt om naar Microsoft te wijzen, is uw domeinconfiguratie voltooid. E-mail wordt doorgeleid naar Microsoft en het verkeer naar uw websiteadres blijft naar uw huidige websitehost gaan.'

> [!NOTE]
> Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd. Vervolgens zijn uw e-mail en andere services van Microsoft ingesteld voor gebruik met uw domein.

## <a name="related-content"></a>Verwante inhoud

[DNS-records toevoegen om uw domein te verbinden](create-dns-records-at-any-dns-hosting-provider.md) (artikel)\
[Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](find-and-fix-issues.md) (artikel)\
[Domeinen beheren](index.yml) (koppelingspagina)
