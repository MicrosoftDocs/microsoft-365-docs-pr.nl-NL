---
title: Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd
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
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: Leer problemen op te sporen die u tegenkomt tijdens het instellen van een aangepast domein door ervoor te zorgen dat de DNS-records correct zijn ingesteld.
ms.openlocfilehash: 0a315be243395940146479e05de2c7044a5a36ab
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560249"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a>Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Het kan een uitdaging zijn om uw domein in te stellen met Microsoft 365. Bij het werken met het DNS-systeem is het belangrijk dat alle waarden correct worden ingevoerd, want de DNS-instellingen voor uw domein zijn van invloed op belangrijke zakelijke activiteiten, zoals e-mail.

> [!NOTE]
> U controleren op problemen met uw domein door de status ervan te controleren. Ga **Setup**naar  >  **Domeinen** instellen en bekijk de meldingen in de kolom **Status.** Als u een probleem ziet, selecteert u Meer acties (drie puntjes) en kiest **u De status controleren**. In het deelvenster dat wordt geopend, worden eventuele problemen met uw domein beschreven.
  
## <a name="whats-going-on"></a>Wat gebeurt er?

- [u uw domein niet verifiëren?](#cant-verify-your-domain)
    
- [Werkt Outlook niet?](#outlook-isnt-working)
    
- [Iedereen e-mail werd overgeschakeld naar Microsoft 365 en je wilde alleen uw e-mail over te schakelen?](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [u de status van een account zonder winstoogmerk of school niet bevestigen?](#cant-confirm-non-profit-or-school-account-status)

- [Services die niet met uw domein werken?](#services-not-working-with-your-domain)
    
- [Toegang tot uw website werkt niet?](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a>U kunt uw domein niet verifiëren?
<a name="BKMK_verify"> </a>

Er zijn enkele veelvoorkomende redenen waarom de verificatie van een domein niet werkt zoals het zou moeten:
  
1. **De waarde van de verificatierecord is niet helemaal juist.** Controleer goed of u de exacte waarde naar de TXT-record voor verificatie bij uw DNS-host hebt gekopieerd en geplakt. Een veelvoorkomende fout is dat het gedeelte 'MS=' van de record niet mee is gekopieerd. Maar dat hebben we ook nodig! 
    
2. **De record is niet opgeslagen.** Bij sommige DNS-hosts moet u een extra stap nemen om het zonebestand (waarin de DNS-record wordt opgeslagen) op te slaan zodat dit overal op internet wordt bijgewerkt. Zorg ervoor dat u uw wijzigingen hebt opgeslagen, zodat Microsoft 365 de record kan zien en verifiëren. 
    
3. **De record is niet bijgewerkt op het internet.** Het duurt meestal slechts een paar minuten voor ons in staat zijn om de nieuwe plaat te zien, maar af en toe kan het zo lang duren als een paar uur. 
    
## <a name="outlook-isnt-working"></a>Outlook werkt niet?
<a name="BKMK_OutlookBroken"> </a>

Als u uw MX-record en andere DNS-records correct hebt ingesteld voor uw domein, maar e-mail niet werkt, kunnen wij u helpen [uw Outlook-problemen op te lossen](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a>Iedereen e-mail werd overgeschakeld naar Microsoft 365 en je wilde alleen uw e-mail over te schakelen?
<a name="BKMK_EmailSwitched"> </a>

Wanneer u uw domein toevoegt aan Microsoft 365, wordt de MX-record van uw domein meestal bijgewerkt (door u of Microsoft 365) om naar Microsoft 365 te wijzen en alle e-mail die naar dat domein wordt verzonden, komt naar Microsoft 365. Zorg ervoor dat u postvakken in Microsoft 365 hebt gemaakt voor iedereen die e-mail op uw domein heeft voordat u de MX-record wijzigt.
  
Wat als u geen e-mail voor iedereen in uw domein wilt verplaatsen naar Microsoft 365? U stappen ondernemen om [Microsoft 365 te besturen met slechts een paar e-mailadressen.](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a>u de status van een account zonder winstoogmerk of school niet bevestigen?
<a name="BKMK_validateAcct"> </a>

Er zijn een paar scenario's waarin u alleen het domein van uw organisatie hoeft te verifiëren en geen services hoeft in te stellen. Bijvoorbeeld om aan Microsoft 365 te bewijzen dat uw organisatie in aanmerking komt voor een schoolabonnement.
  
Bekijk de richtlijnen in [Uw Microsoft 365-domein verifiëren om de status van eigendom, non-profitorganisatie of onderwijs te bewijzen of om Yammer te activeren](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) om ervoor te zorgen dat u alle vereiste stappen hebt uitgevoerd. Het is een beetje anders voor elke situatie. 
  
## <a name="services-not-working-with-your-domain"></a>Zijn er services die niet werken met uw domein?
<a name="BKMK_Test"> </a>

Wij kunnen u helpen problemen op te sporen met de DNS-installatie van uw domein. De probleemoplosser voor domeinen in Microsoft 365 toont u alle records die moeten worden hersteld en waar de records precies op moeten worden ingesteld. 

> [!TIP]
> Hebt u uw DNS-correct ingesteld, maar werkt e-mail niet in Outlook op uw desktopcomputer? Bekijk de [verschillende e-mailstroomscenario's die u met Microsoft 365 hebben](https://docs.microsoft.com/exchange/mail-flow-best-practices/mail-flow-best-practices) om ervoor te zorgen dat u dingen correct hebt ingesteld voor uw bedrijf. Meer hulp bij het oplossen van problemen met e-mail vindt u hier: [Problemen met Outlook oplossen](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues). 
  
## <a name="accessing-your-website-isnt-working"></a>U krijgt geen toegang tot uw website?
<a name="BKMK_Website"> </a>

Als u DNS-problemen hebt opgelost en nog steeds problemen ondervindt, probeer dan een van de volgende opties.
  
- Personen kunnen uw website op www.mijndomein.com niet bereiken: [Websiteproblemen opsporen](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)
    
- U uw A-record of CNAME-record niet bijwerken om naar uw website te verwijzen: [Aangepaste DNS-records bijwerken in Microsoft 365](../dns/add-or-edit-custom-dns-records.md)
    
