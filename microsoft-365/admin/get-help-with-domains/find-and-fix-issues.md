---
title: Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd in Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: Leer eventuele problemen op te sporen die u tegenkomt tijdens het instellen van een aangepast domein door ervoor te zorgen dat de DNS-records correct zijn ingesteld.
ms.openlocfilehash: 277e87ad6b06db0b1ef3b3cb5eaaa45a2e77ed6f
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42805377"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records-in-office-365"></a>Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd in Office 365

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Het kan lastig zijn om uw domein in te stellen voor gebruik met Office 365. Bij het werken met het DNS-systeem is het belangrijk dat alle waarden correct worden ingevoerd, want de DNS-instellingen voor uw domein zijn van invloed op belangrijke zakelijke activiteiten, zoals e-mail.

> [!NOTE]
> U controleren op problemen met uw domein door de status ervan te controleren. Ga naar > **Instellingendomeinen** en bekijk de meldingen in de kolom **Status.** **Settings** Als u een probleem ziet, selecteert u Meer acties (drie puntjes) en kiest u **De status controleren**. In het deelvenster dat wordt geopend, worden eventuele problemen met uw domein beschreven.
  
## <a name="whats-going-on"></a>Wat gebeurt er?

- [u uw domein niet verifiëren?](#cant-verify-your-domain)
    
- [Werkt Outlook niet?](#outlook-isnt-working)
    
- [Ieders e-mail is overgeschakeld naar Office 365 en u wilde alleen uw e-mail om te schakelen?](#everyones-email-got-switched-to-office-365-and-you-only-wanted-your-email-to-switch)

- [u de status van non-profit- of schoolaccount niet bevestigen?](#cant-confirm-non-profit-or-school-account-status)

- [Services die niet met uw domein werken?](#services-not-working-with-your-domain)
    
- [Toegang tot uw website werkt niet?](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a>U kunt uw domein niet verifiëren?
<a name="BKMK_verify"> </a>

Er zijn enkele veelvoorkomende redenen waarom de verificatie van een domein niet werkt zoals het zou moeten:
  
1. **De waarde van de verificatierecord is niet helemaal juist.** Controleer goed of u de exacte waarde naar de TXT-record voor verificatie bij uw DNS-host hebt gekopieerd en geplakt. Een veelvoorkomende fout is dat het gedeelte 'MS=' van de record niet mee is gekopieerd. Maar dat hebben we ook nodig! 
    
2. **De record is niet opgeslagen.** Bij sommige DNS-hosts moet u een extra stap nemen om het zonebestand (waarin de DNS-record wordt opgeslagen) op te slaan zodat dit overal op internet wordt bijgewerkt. Controleer of u de wijzigingen hebt opgeslagen zodat Office 365 de record kan waarnemen en controleren. 
    
3. **De record is niet bijgewerkt op het internet.** Het duurt meestal slechts een paar minuten voor ons in staat zijn om de nieuwe record te zien, maar af en toe kan het zo lang duren als een paar uur. 
    
## <a name="outlook-isnt-working"></a>Outlook werkt niet?
<a name="BKMK_OutlookBroken"> </a>

Als u uw MX-record en andere DNS-records correct hebt ingesteld voor uw domein, maar e-mail niet werkt, kunnen wij u helpen [uw Outlook-problemen op te lossen](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx).
  
## <a name="everyones-email-got-switched-to-office-365-and-you-only-wanted-your-email-to-switch"></a>Ieders e-mail is overgeschakeld naar Office 365 en u wilde alleen uw e-mail om te schakelen?
<a name="BKMK_EmailSwitched"> </a>

Wanneer u uw domein toevoegt aan Office 365, wordt de MX-record van uw domein meestal bijgewerkt (door u of Office 365) om naar Office 365 te wijzen en alle e-mails die naar dat domein worden verzonden, worden naar Office 365 verzonden. Zorg ervoor dat u postvakken hebt gemaakt in Office 365 voor iedereen die e-mail op uw domein heeft voordat u de MX-record wijzigt.
  
Wat moet u doen als u e-mail niet voor iedereen in uw domein wilt verplaatsen naar Office 365? U kunt [stappen uitvoeren om Office 365 in plaats daarvan met slechts een paar e-mailadressen te testen](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx).
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a>u de status van non-profit- of schoolaccount niet bevestigen?
<a name="BKMK_validateAcct"> </a>

Er zijn een paar scenario's waarin u alleen het domein van uw organisatie hoeft te verifiëren en geen services hoeft in te stellen. Bijvoorbeeld om aan Office 365 te bewijzen dat uw organisatie in aanmerking komt voor een schoolabonnement.
  
Bekijk de richtlijnen in [Uw Office 365-domein verifiëren om de eigendoms-, non-profit- of onderwijsstatus te bewijzen of Yammer te activeren](https://support.office.com/article/87d1844e-aa47-4dc0-a61b-1b773fd4e590) om ervoor te zorgen dat u alle vereiste stappen hebt voltooid. Het is een beetje anders voor elke situatie. 
  
## <a name="services-not-working-with-your-domain"></a>Zijn er services die niet werken met uw domein?
<a name="BKMK_Test"> </a>

We kunnen u helpen bij het opsporen van problemen met de DNS-installatie van uw domein. De probleemoplosser voor domeinen in Office 365 toont u alle records die moeten worden hersteld en waar de records precies op moeten worden ingesteld. 

> [!TIP]
> Hebt u uw DNS-correct ingesteld, maar werkt e-mail niet in Outlook op uw desktopcomputer? Bekijk de [andere mogelijke scenario's voor e-mailstromen in Office 365](https://go.microsoft.com/fwlink/?LinkId=787530) om te controleren of u alles correct hebt ingesteld voor uw bedrijf. Meer hulp bij het oplossen van problemen met e-mail vindt u hier: [Problemen met Outlook oplossen](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx). 
  
## <a name="accessing-your-website-isnt-working"></a>U krijgt geen toegang tot uw website?
<a name="BKMK_Website"> </a>

Als u DNS-problemen hebt opgelost en nog steeds problemen ondervindt, probeer dan een van de volgende opties.
  
- Personen kunnen uw website op www.mijndomein.com niet bereiken: [Websiteproblemen opsporen](https://support.office.com/article/61f34ca1-ca7f-4a65-9348-def20db09ddf.aspx)
    
- U kunt uw A-record of CNAME-record niet bijwerken zodat deze verwijst naar uw website: [Aangepaste DNS-records bijwerken in Office 365](../dns/add-or-edit-custom-dns-records.md)
    
