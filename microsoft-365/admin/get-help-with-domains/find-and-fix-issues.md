---
title: Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: Lees hoe u problemen kunt oplossen bij het instellen van een aangepast domein door ervoor te zorgen dat de DNS-records correct zijn ingesteld.
ms.openlocfilehash: 5959cae02b87cf481fc06edd941a6da284b71736
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537545"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a>Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt. 
  
Het kan lastig zijn om uw domein zo in te stellen Microsoft 365 te werken. Bij het werken met het DNS-systeem is het belangrijk dat alle waarden correct worden ingevoerd, want de DNS-instellingen voor uw domein zijn van invloed op belangrijke zakelijke activiteiten, zoals e-mail.

> [!NOTE]
> U kunt controleren op problemen met uw domein door de status ervan te controleren. Ga naar **Domeinen**  >  **instellen** en bekijk de meldingen in de **kolom Status.** Als u een probleem ziet, selecteert u de drie puntjes (meer acties) en kiest u **vervolgens Status controleren.** In het deelvenster dat wordt geopend, worden eventuele problemen met uw domein beschreven.
  
## <a name="whats-going-on"></a>Wat gebeurt er?

- [Kunt u uw domein niet verifiëren?](#cant-verify-your-domain)
    
- [Outlook werkt het niet?](#outlook-isnt-working)
    
- [Iedereens e-mail is overgeschakeld naar Microsoft 365 en u wilde alleen dat uw e-mail werd overgeschakeld?](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [Kunt u de status van het non-profit- of schoolaccount niet bevestigen?](#cant-confirm-non-profit-or-school-account-status)

- [Werken services niet met uw domein?](#services-not-working-with-your-domain)
    
- [Werkt toegang tot uw website niet?](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a>U kunt uw domein niet verifiëren?
<a name="BKMK_verify"> </a>

Er zijn enkele veelvoorkomende redenen waarom de verificatie van een domein niet werkt zoals het zou moeten:
  
1. **De waarde van de verificatierecord is niet helemaal juist.** Controleer goed of u de exacte waarde naar de TXT-record voor verificatie bij uw DNS-host hebt gekopieerd en geplakt. Een veelvoorkomende fout is dat het gedeelte 'MS=' van de record niet mee is gekopieerd. Maar dat hebben we ook nodig! 
    
2. **De record is niet opgeslagen.** Bij sommige DNS-hosts moet u een extra stap nemen om het zonebestand (waarin de DNS-record wordt opgeslagen) op te slaan zodat dit overal op internet wordt bijgewerkt. Zorg ervoor dat u de wijzigingen hebt opgeslagen, zodat Microsoft 365 de record kan zien en controleren. 
    
3. **De record is niet bijgewerkt op internet.** Meestal duurt het slechts enkele minuten voordat we de nieuwe record kunnen zien, maar af en toe kan het enkele uren duren. 
    
## <a name="outlook-isnt-working"></a>Outlook werkt niet?
<a name="BKMK_OutlookBroken"> </a>

Als u uw MX-record en andere DNS-records correct hebt ingesteld voor uw domein, maar e-mail niet werkt, kunnen wij u helpen [uw Outlook-problemen op te lossen](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a>Iedereens e-mail is overgeschakeld naar Microsoft 365 en u wilde alleen dat uw e-mail werd overgeschakeld?
<a name="BKMK_EmailSwitched"> </a>

Wanneer u uw domein toevoegt aan Microsoft 365, wordt de MX-record van uw domein meestal bijgewerkt (door u of Microsoft 365) om naar Microsoft 365 te wijzen en alle e-mail die naar dat domein wordt verzonden, wordt Microsoft 365. Zorg ervoor dat u postvakken hebt gemaakt in Microsoft 365 voor iedereen die e-mail in uw domein heeft voordat u de MX-record wijzigt.
  
Wat gebeurt er als u e-mail voor iedereen in uw domein niet wilt verplaatsen naar Microsoft 365? In plaats daarvan kunt u stappen Microsoft 365 [met slechts een paar e-mailadressen.](../setup/domains-faq.yml)
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a>Kunt u de status van het non-profit- of schoolaccount niet bevestigen?
<a name="BKMK_validateAcct"> </a>

Er zijn een paar scenario's waarin u alleen het domein van uw organisatie hoeft te verifiëren en geen services hoeft in te stellen. Bijvoorbeeld om aan te tonen Microsoft 365 dat uw organisatie in aanmerking komt voor een schoolabonnement.
  
Bekijk de richtlijnen in Uw Microsoft 365 domein [controleren](../setup/domains-faq.yml) om de eigendomsstatus, non-profitstatus of onderwijsstatus te bewijzen of om Yammer te activeren om ervoor te zorgen dat u alle vereiste stappen hebt voltooid. Het is een beetje anders voor elke situatie. 
  
## <a name="services-not-working-with-your-domain"></a>Zijn er services die niet werken met uw domein?
<a name="BKMK_Test"> </a>

We kunnen u helpen bij het vinden van problemen met de DNS-instelling van uw domein. De probleemoplosser voor domeinen in Microsoft 365 toont u alle records die moeten worden opgelost en precies waar de records op moeten worden ingesteld. 

> [!TIP]
> Hebt u uw DNS-correct ingesteld, maar werkt e-mail niet in Outlook op uw desktopcomputer? Bekijk de [verschillende scenario's](/exchange/mail-flow-best-practices/mail-flow-best-practices) voor e-mailstroom die u kunt hebben met Microsoft 365 om ervoor te zorgen dat u de zaken correct hebt ingesteld voor uw bedrijf. Meer hulp bij het oplossen van problemen met e-mail vindt u hier: [Problemen met Outlook oplossen](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues). 
  
## <a name="accessing-your-website-isnt-working"></a>U krijgt geen toegang tot uw website?
<a name="BKMK_Website"> </a>

Als u DNS-problemen hebt opgelost en nog steeds problemen ondervindt, probeer dan een van de volgende opties.
  
- Personen kunnen uw website op www.mijndomein.com niet bereiken: [Websiteproblemen opsporen](../setup/add-domain.md)
    
- U kunt uw A-record of CNAME-record niet bijwerken om naar uw website te wijzen: [Aangepaste DNS-records bijwerken in Microsoft 365](../setup/add-domain.md)

## <a name="related-content"></a>Verwante onderwerpen

[Problemen oplossen: Controlegegevens over geverifieerde domeinwijziging](/azure/active-directory/reports-monitoring/troubleshoot-audit-data-verified-domain)

