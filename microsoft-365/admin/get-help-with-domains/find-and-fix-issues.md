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
description: Leer hoe u eventuele problemen die zich voordoen bij het instellen van een aangepast domein kunt bijhouden door te controleren of de DNS-records correct zijn ingesteld.
ms.openlocfilehash: 8d46d681e44a0bebd0a9571d18ffa95e1e554dc8
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295044"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a>Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Uw domein instellen voor gebruik met Microsoft 365 kan lastig zijn. Bij het werken met het DNS-systeem is het belangrijk dat alle waarden correct worden ingevoerd, want de DNS-instellingen voor uw domein zijn van invloed op belangrijke zakelijke activiteiten, zoals e-mail.

> [!NOTE]
> U kunt controleren op problemen met uw domein door de status ervan te controleren. Ga naar **Setup**  >  **Domains** en Bekijk de meldingen in de kolom **status** . Als u een probleem ziet, selecteert u meer acties (drie puntjes) en kiest u vervolgens **status controleren**. In het deelvenster dat wordt geopend, worden problemen beschreven die zich voordoen bij uw domein.
  
## <a name="whats-going-on"></a>Wat gebeurt er?

- [Kunt u uw domein niet verifiëren?](#cant-verify-your-domain)
    
- [Outlook werkt niet?](#outlook-isnt-working)
    
- [De e-mail van iedereen is overgeschakeld naar Microsoft 365 en u wilt dat alleen uw e-mail doorsturen?](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [Kan de status van niet-winstgevende of schoolaccount niet bevestigen?](#cant-confirm-non-profit-or-school-account-status)

- [Zijn er services die niet werken met uw domein?](#services-not-working-with-your-domain)
    
- [U krijgt geen toegang tot uw website?](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a>U kunt uw domein niet verifiëren?
<a name="BKMK_verify"> </a>

Er zijn enkele veelvoorkomende redenen waarom de verificatie van een domein niet werkt zoals het zou moeten:
  
1. **De waarde van de verificatierecord is niet helemaal juist.** Controleer goed of u de exacte waarde naar de TXT-record voor verificatie bij uw DNS-host hebt gekopieerd en geplakt. Een veelvoorkomende fout is dat het gedeelte 'MS=' van de record niet mee is gekopieerd. Maar dat hebben we ook nodig! 
    
2. **De record is niet opgeslagen.** Bij sommige DNS-hosts moet u een extra stap nemen om het zonebestand (waarin de DNS-record wordt opgeslagen) op te slaan zodat dit overal op internet wordt bijgewerkt. Zorg ervoor dat u de wijzigingen hebt opgeslagen, zodat Microsoft 365 de record kan zien en verifiëren. 
    
3. **De record wordt niet bijgewerkt via internet.** Het duurt meestal maar een paar minuten voordat de nieuwe record kan worden weergegeven, maar soms kan het even duren voordat het een paar uur duurt. 
    
## <a name="outlook-isnt-working"></a>Outlook werkt niet?
<a name="BKMK_OutlookBroken"> </a>

Als u uw MX-record en andere DNS-records correct hebt ingesteld voor uw domein, maar e-mail niet werkt, kunnen wij u helpen [uw Outlook-problemen op te lossen](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a>De e-mail van iedereen is overgeschakeld naar Microsoft 365 en u wilt dat alleen uw e-mail doorsturen?
<a name="BKMK_EmailSwitched"> </a>

Wanneer u uw domein toevoegt aan Microsoft 365, wordt de MX-record van uw domein meestal bijgewerkt (door u of Microsoft 365) zodat deze verwijst naar Microsoft 365, en alle e-mail die naar dit domein is verzonden, wordt verzonden naar Microsoft 365. Zorg dat u postvakken hebt gemaakt in Microsoft 365 voor iedereen die e-mail in uw domein heeft voordat u de MX-record wijzigt.
  
Wat moet u doen als u e-mail niet voor iedereen in uw domein wilt verplaatsen naar Microsoft 365? U kunt stappen uitvoeren om [Microsoft 365 met slechts een paar e-mailadressen te testen](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a>Kan de status van niet-winstgevende of schoolaccount niet bevestigen?
<a name="BKMK_validateAcct"> </a>

Er zijn een paar scenario's waarbij u het domein van uw organisatie alleen moet verifiëren en geen Services hoeft in te stellen. Als u bijvoorbeeld Microsoft 365 wilt bewijzen dat uw organisatie in aanmerking komt voor een school abonnement.
  
Bekijk de richtlijnen in [uw Microsoft 365-domein verifiëren voor de eigendomsrechten voor de non-profit organisatie of voor onderwijsinstellingen, of om Yammer te activeren](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) om ervoor te zorgen dat u alle benodigde stappen hebt uitgevoerd. Het is een beetje verschillend voor elke situatie. 
  
## <a name="services-not-working-with-your-domain"></a>Zijn er services die niet werken met uw domein?
<a name="BKMK_Test"> </a>

We kunnen u helpen problemen op te sporen met de DNS-instellingen van uw domein. In de probleemoplosser voor domeinen in Microsoft 365 worden de records weergegeven die moeten worden verholpen, en exact waarop de records moeten worden ingesteld. 

> [!TIP]
> Hebt u uw DNS-correct ingesteld, maar werkt e-mail niet in Outlook op uw desktopcomputer? Bekijk de [verschillende scenario's voor de e-mail stroom van Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/mail-flow-best-practices) om te controleren of u de juiste functies hebt ingesteld voor uw bedrijf. Meer hulp bij het oplossen van problemen met e-mail vindt u hier: [Problemen met Outlook oplossen](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues). 
  
## <a name="accessing-your-website-isnt-working"></a>U krijgt geen toegang tot uw website?
<a name="BKMK_Website"> </a>

Als u DNS-problemen hebt opgelost en nog steeds problemen ondervindt, probeer dan een van de volgende opties.
  
- Personen kunnen uw website op www.mijndomein.com niet bereiken: [Websiteproblemen opsporen](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)
    
- U kunt uw A-record of CNAME-record niet bijwerken zodat deze verwijst naar uw website: [aangepaste DNS-records bijwerken in Microsoft 365](../dns/add-or-edit-custom-dns-records.md)

## <a name="related-content"></a>Verwante onderwerpen

[Problemen oplossen: gegevens controleren over gecontroleerd domein wijzigen](https://docs.microsoft.com/azure/active-directory/reports-monitoring/troubleshoot-audit-data-verified-domain)

    
