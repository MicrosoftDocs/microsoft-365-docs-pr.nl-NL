---
title: Herstel na een ransomware-aanval
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Microsoft 365-beheerders kunnen leren hoe ze kunnen herstellen van een ransomware-aanval.
ms.openlocfilehash: 29afb66dd90be3917d576a7533900e21a91966c0
ms.sourcegitcommit: 6007dbe2cf758c683de399f94023122c678bcada
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/14/2020
ms.locfileid: "44224707"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a>Herstellen van een ransomware aanval in Microsoft 365

Zelfs als u alle voorzorgsmaatregelen neemt om uw organisatie [ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) te beschermen, u nog steeds het slachtoffer worden van een ransomware-aanval. Ransomware is big business, en de aanvallen zijn te verifiëren geavanceerde.

De stappen in dit onderwerp geeft u de beste kans om gegevens die werd versleuteld door de ransomware te herstellen, en zal helpen stoppen met de verspreiding van de infectie in uw organisatie. Voordat u aan de slag gaat, moet u de volgende items overwegen:

- Er is geen garantie dat het betalen van het losgeld toegang tot uw bestanden zal terugkeren. In feite, het betalen van het losgeld kan je een doelwit voor meer ransomware. Als u al hebt betaald, maar u uw bestanden met succes hebt kunnen herstellen zonder dat u de resolutie van de aanvaller hoeft te gebruiken, moet u uw bank bellen om te zien of ze de transactie kunnen blokkeren. We raden u ook aan de ransomware-aanval te melden aan de rechtshandhaving, scam rapportage websites en Microsoft zoals later beschreven in dit onderwerp.

- Het is heel belangrijk dat je snel reageert op de aanval en de gevolgen ervan. Hoe langer u wacht, hoe kleiner de kans dat u de getroffen gegevens herstellen.

## <a name="step-1-verify-your-backups"></a>Stap 1: Uw back-ups verifiëren

Als u offline back-ups hebt, u waarschijnlijk de versleutelde gegevens herstellen **nadat** u de ransomware payload (malware) uit uw omgeving hebt verwijderd.

Als u geen back-ups hebt, of als uw back-ups ook werden beïnvloed door de ransomware, u deze stap overslaan.

## <a name="step-2-disable-activesync-and-onedrive-sync"></a>Stap 2: ActiveSync en OneDrive-synchronisatie uitschakelen

Het belangrijkste punt hier is om de verspreiding van data-encryptie te stoppen door de ransomware.

Als u vermoedt dat e-mail een doelwit is, moet u de toegang van gebruikers tot postvakken tijdelijk uitschakelen. Exchange ActiveSync wordt door mobiele apparaten gebruikt om gegevens te synchroniseren tussen het apparaat en het Exchange Online-postvak.

Zie Exchange [ActiveSync uitschakelen voor gebruikers in Exchange Online](https://support.microsoft.com/help/2795303/how-to-disable-exchange-activesync-for-users-in-office-365)als u ActiveSync voor een postvak wilt uitschakelen.

Zie als:

- [MAPI in- of uitschakelen voor een postvak](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).

- [POP3- of IMAP4-toegang voor een gebruiker in- of uitschakelen](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

Als u OneDrive-synchronisatie pauzeert, u voorkomen dat uw cloudgegevens worden bijgewerkt door mogelijk geïnfecteerde apparaten. Zie [Synchronisatie onderbreken en hervatten in OneDrive](https://support.office.com/article/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)voor meer informatie.

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a>Stap 3: Verwijder de malware van de getroffen apparaten

Voer een volledige antivirusscan uit met de nieuwste updates op alle verdachte computers en apparaten om de payload te detecteren en te verwijderen die is gekoppeld aan de ransomware. Vergeet niet apparaten die gegevens synchroniseren, of het doel van toegewezen netwerkstations (die computers en apparaten moeten ook worden gescand).

U [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) of (voor oudere clients) Microsoft Security [Essentials](https://www.microsoft.com/download/details.aspx?id=5201)gebruiken.

Een alternatief dat u ook zal helpen ransomware of malware te verwijderen is de [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).

Als deze opties niet werken, u [Windows Defender Offline](https://support.microsoft.com/help/17466/windows-defender-offline-help-protect-my-pc) proberen of problemen met het detecteren en verwijderen van malware [oplossen.](https://support.microsoft.com/help/4466982/windows-10-troubleshoot-problems-with-detecting-and-removing-malware)

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a>Stap 4: Bestanden herstellen op een opgeschoonde computer of apparaat

Nadat u de vorige stap hebt voltooid om de ransomware-payload uit uw omgeving te verwijderen (waardoor de ransomware uw bestanden niet kan versleutelen of verwijderen), u [bestandsgeschiedenis](https://support.microsoft.com/help/17128/windows-8-file-history) gebruiken in Windows 10 en Windows 8.1 of Systeembeveiliging in Windows 7 om te proberen uw lokale bestanden en mappen te herstellen.

**Opmerkingen**:

- Sommige ransomware zal ook versleutelen of verwijderen van de back-up versies, dus je niet gebruiken Bestandsgeschiedenis of systeembeveiliging om bestanden te herstellen. Als dat gebeurt, moet u back-ups gebruiken op externe schijven of apparaten die niet zijn beïnvloed door de ransomware of OneDrive, zoals beschreven in de volgende sectie.

- Als een map is gesynchroniseerd met OneDrive en u de nieuwste versie van Windows niet gebruikt, zijn er mogelijk enkele beperkingen met bestandsgeschiedenis.

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a>Stap 5: Uw bestanden herstellen in uw OneDrive voor Bedrijven

Met Bestanden herstellen in OneDrive voor Bedrijven u uw volledige OneDrive in de afgelopen 30 dagen naar een eerder tijdstip herstellen. Zie [Uw OneDrive herstellen](https://support.office.com/article/fa231298-759d-41cf-bcd0-25ac53eb8a15)voor meer informatie.

## <a name="step-6-recover-deleted-email"></a>Stap 6: Verwijderde e-mail herstellen

In het zeldzame geval dat de ransomware al uw e-mail verwijderd, u waarschijnlijk herstellen van de verwijderde items. Zie voor meer informatie:

- [Verwijderde berichten herstellen in het postvak van een gebruiker](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [Verwijderde items herstellen in Outlook voor Windows](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a>Stap 7: Exchange ActiveSync en OneDrive-synchronisatie opnieuw inschakelen

Nadat u uw computers en apparaten hebt opgemaakt en uw gegevens hebt hersteld, u activesync en OneDrive-synchronisatie die u eerder hebt uitgeschakeld in [stap 2](#step-2-disable-activesync-and-onedrive-sync)opnieuw inschakelen.

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a>Stap 8 (optioneel): OneDrive-synchronisatie blokkeren voor specifieke bestandsextensies

Nadat u bent hersteld, u voorkomen dat Klanten van OneDrive voor Bedrijven de bestandstypen synchroniseren die door deze ransomware zijn getroffen. Zie [Set-SPOTenantSyncClientRestriction voor](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction) meer informatie

## <a name="report-the-attack"></a>De aanval melden

### <a name="contact-law-enforcement"></a>Neem contact op met de politie

Neem contact op met uw lokale of federale wetshandhavingsinstanties. Als u zich bijvoorbeeld in de Verenigde Staten bevindt, u contact opnemen met het [lokale fieldoffice](https://www.fbi.gov/contact-us/field)van de FBI, [IC3](http://www.ic3.gov/complaint/default.aspx) of [de geheime dienst.](http://www.secretservice.gov/)

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a>Een rapport indienen bij de website van uw land voor het melden van oplichting

Scam rapportage websites bieden informatie over hoe te voorkomen en te voorkomen oplichting. Ze bieden ook mechanismen om te melden als je slachtoffer was van oplichting.

- Australië: [SCAMwatch](http://www.scamwatch.gov.au/)

- Canada: [Canadees Centrum voor fraudebestrijding](http://www.antifraudcentre-centreantifraude.ca/)

- Frankrijk: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)

- Duitsland: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)

- Ierland: [An Garda Síochána](http://www.garda.ie/)

- Nieuw-Zeeland: [Consumentenzaken Oplichting](http://www.consumeraffairs.govt.nz/scams)

- Verenigd Koninkrijk: [Actiefraude](http://www.actionfraud.police.uk/)

- Verenigde Staten: [On Guard Online](http://www.onguardonline.gov/)

Als uw land niet op de lijst staat, vraag het dan aan uw lokale of federale wetshandhavingsinstanties.

### <a name="submit-email-messages-to-microsoft"></a>E-mailberichten verzenden naar Microsoft

U phishing-berichten die ransomware bevatten met behulp van een van de verschillende methoden. Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="see-also"></a>Zie ook

- [Ransomware Ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [Ransomware reactie-te betalen of niet te betalen?](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [Norsk Hydro reageert op ransomware aanval met transparantie](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [Ransomware detectie en het herstellen van uw bestanden in OneDrive](https://support.microsoft.com/en-us/office/ransomware-detection-and-recovering-your-files-0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [Microsoft Security Intelligence-rapport](https://www.microsoft.com/securityinsights/)

- [Macro's in Office-bestanden in- of uitschakelen](https://support.office.com/article/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [Aanbevolen instellingen voor EOP- en Office 365 ATP-beveiliging](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp)

- [Een waardige upgrade: Next-gen beveiliging op Windows 10 blijkt veerkrachtig tegen ransomware uitbraken in 2017](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [Geen mas, Samas: Wat zit er in de modus operandi van deze ransomware?](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [Locky malware, geluk om het te vermijden](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [MSRT juli 2016: Cerber ransomware](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [De drie hoofden van de Cerberus-achtige Cerber ransomware](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [Troldesh ransomware beïnvloed door (de) Da Vinci code](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
