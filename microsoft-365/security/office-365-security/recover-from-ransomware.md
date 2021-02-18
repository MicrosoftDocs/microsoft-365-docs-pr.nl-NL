---
title: Herstel na een ransomware-aanval
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft 365-beheerders kunnen informatie krijgen over het herstellen van een ransomware-aanval.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 120dd9ae71f04d6921fae95965f56f0a08f1280c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289303"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a>Herstel van een ransomware-aanval in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Zelfs als u alle voorzorgsmaatregelen treffen om uw organisatie te beschermen, kunt u nog steeds het slachtoffer worden van een [aanval van ransomware.](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) Ransomware is een grote onderneming en de aanvallen zijn zeer geavanceerd.

Met de stappen in dit artikel krijgt u de beste kans om gegevens te herstellen en de interne verspreiding van de instopstop te stoppen. Kijk eens naar de volgende items voordat u aan de slag gaat:

- Er is geen garantie dat het betalen van de garantie weer toegang geeft tot uw bestanden. In feite kan het betalen van de kosten ervoor zorgen dat u een doel wordt voor meer ransomware.

  Als u al hebt betaald, maar u het herstel hebt hersteld zonder de oplossing van de aanvaller te gebruiken, neem dan contact op met uw bank om te kijken of deze de transactie kan blokkeren.

  U wordt ook aangeraden de ransomware-aanval te melden aan de advocatenkantoor, websites voor het melden van oplichtingspraktijken en Microsoft, zoals verderhand in dit artikel wordt beschreven.

- Het is belangrijk dat u snel reageert op de aanval en de gevolgen ervan. Hoe langer u wacht, hoe minder waarschijnlijk het is dat u de betrokken gegevens kunt herstellen.

## <a name="step-1-verify-your-backups"></a>Stap 1: Uw back-ups controleren

Als u offlineback-ups hebt, kunt u  de versleutelde gegevens waarschijnlijk herstellen nadat u de ransomware(malware) uit uw omgeving hebt verwijderd.

Als u geen back-ups hebt of als uw back-ups ook door ransomware zijn beïnvloed, kunt u deze stap overslaan.

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a>Stap 2: Exchange ActiveSync en OneDrive-synchronisatie uitschakelen

Het belangrijkste punt hier is om de verspreiding van gegevensversleuteling door de ransomware te stoppen.

Als u vermoedt dat e-mail een doel is van de ransomware-versleuteling, schakelt u de gebruikerstoegang tot postvakken tijdelijk uit. Exchange ActiveSync synchroniseert gegevens tussen apparaten en Postvakken van Exchange Online.

Zie Exchange ActiveSync uitschakelen voor gebruikers in Exchange Online als u Exchange ActiveSync wilt uitschakelen [voor een postvak.](https://support.microsoft.com/help/2795303)

Als u andere soorten toegang tot een postvak wilt uitschakelen, gaat u naar:

- [MAPI voor een postvak in- of uitschakelen.](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)

- [POP3- of IMAP4-toegang voor een gebruiker in- of uitschakelen](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

Door OneDrive-synchronisatie te onderbreken, beschermt u uw cloudgegevens tegen updates door mogelijk geïnfecteerde apparaten. Zie Synchronisatie onderbreken en hervatten [in OneDrive voor meer informatie.](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a>Stap 3: Verwijder de malware van de betreffende apparaten

Voer een volledige, actuele antivirusscan uit op alle verdachte computers en apparaten om de nettolading te detecteren en te verwijderen die is gekoppeld aan de ransomware.

Vergeet niet apparaten te scannen die gegevens synchroniseren, of de doelen van de netwerkstations.

U kunt [Windows Defender of](https://www.microsoft.com/windows/comprehensive-security) (voor oudere clients) Microsoft Security [Essentials gebruiken.](https://www.microsoft.com/download/details.aspx?id=5201)

Een alternatief voor het verwijderen van ransomware of malware is het [Malicious Software Removal Tool (MSRT).](https://www.microsoft.com/download/details.aspx?id=9905)

Als deze opties niet werken, kunt u [Windows Defender Offline](https://support.microsoft.com/help/17466) proberen of problemen oplossen met het detecteren en verwijderen van [malware.](https://support.microsoft.com/help/4466982)

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a>Stap 4: Bestanden herstellen op een opgeschoonde computer of apparaat

Nadat u de vorige stap hebt voltooid om de nettolading van ransomware uit uw omgeving te verwijderen (waardoor ransomware uw bestanden niet kan versleutelen of verwijderen), kunt u Bestandsgeschiedenis [in](https://support.microsoft.com/help/17128) Windows 10 en Windows 8.1 of Systeembeveiliging in Windows 7 gebruiken om te proberen uw lokale bestanden en mappen te herstellen.

**Opmerkingen**:

- Sommige ransomware versleutelen of verwijderen ook de back-upversies, zodat u de bestandsgeschiedenis of systeembeveiliging niet kunt gebruiken om bestanden te herstellen. Als dat gebeurt, moet u back-ups gebruiken op externe stations of apparaten die niet zijn beïnvloed door ransomware of OneDrive, zoals wordt beschreven in de volgende sectie.

- Als een map wordt gesynchroniseerd met OneDrive en u niet de nieuwste versie van Windows gebruikt, kan het gebruik van Bestandsgeschiedenis bepaalde beperkingen hebben.

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a>Stap 5: Uw bestanden herstellen in uw OneDrive voor Bedrijven

Met Bestanden herstellen in OneDrive voor Bedrijven kunt u uw gehele OneDrive herstellen naar het vorige tijdstip in de afgelopen 30 dagen. Zie Uw [OneDrive herstellen voor meer informatie.](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="step-6-recover-deleted-email"></a>Stap 6: Verwijderde e-mail herstellen

In het zeldzame geval dat de ransomware al uw e-mailberichten heeft verwijderd, kunt u de verwijderde items waarschijnlijk herstellen. Zie voor meer informatie:

- [Verwijderde berichten herstellen in het postvak van een gebruiker](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [Verwijderde items herstellen in Outlook voor Windows](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a>Stap 7: Exchange ActiveSync en OneDrive-synchronisatie opnieuw inschakelen

Nadat u uw computers en apparaten hebt opgeschoond en de gegevens hebt hersteld, kunt u Exchange ActiveSync- en OneDrive-synchronisatie, die u eerder in stap 2 hebt uitgeschakeld, [opnieuw inschakelen.](#step-2-disable-exchange-activesync-and-onedrive-sync)

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a>Stap 8 (optioneel): OneDrive-synchronisatie blokkeren voor specifieke bestandsextensies

Nadat u het bestand hebt hersteld, kunt u voorkomen dat OneDrive voor Bedrijven-clients de bestandstypen synchroniseren die door deze ransomware zijn beïnvloed. Zie [Set-SPOTenantSyncClientRestriction voor meer informatie](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)

## <a name="report-the-attack"></a>De aanval melden

### <a name="contact-law-enforcement"></a>Contact opnemen met de wet

Neem contact op met uw lokale of federale advocatenkantoors. Als u zich bijvoorbeeld in de Verenigde Staten hebt, kunt u contact opnemen met het lokale field [office VAN DE(s)](https://www.fbi.gov/contact-us/field) [IC3](http://www.ic3.gov/complaint/default.aspx) of [de geheime service.](http://www.secretservice.gov/)

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a>Een rapport verzenden naar de rapportagewebsite van uw land

Websites voor oplichtingsrapportage bevatten informatie over hoe u oplichtingspraktijken kunt voorkomen en vermijden. Ze bieden ook mechanismen om te melden als u het slachtoffer bent geworden van oplichtingspraktijken.

- Australië: [SCAMwatch](http://www.scamwatch.gov.au/)

- Canada: [Canadees antifraudecentrum](http://www.antifraudcentre-centreantifraude.ca/)

- Frankrijk: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)

- Duitsland: [Vonamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)

- Ierland: [Een Garda Síochána](http://www.garda.ie/)

- Nieuw-Zeeland: [Oplichtingspraktijken in consumentenzaken](http://www.consumeraffairs.govt.nz/scams)

- Verenigd Koninkrijk: [Actiefraude](http://www.actionfraud.police.uk/)

- Verenigde Staten: [In Guard Online](http://www.onguardonline.gov/)

Als uw land niet in de lijst staat, vraagt u dit aan uw lokale of federale advocatenkantoorsinstanties.

### <a name="submit-email-messages-to-microsoft"></a>E-mailberichten verzenden bij Microsoft

U kunt phishing-berichten die ransomware bevatten op een van de verschillende manieren rapporteren. Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="see-also"></a>Zie ook

- [Ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [Antwoord op ransomware: al dan niet te betalen?](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [Norsk Er is een reactie op de aanval van ransomware met transparantie](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [Ransomware-detectie en het herstellen van uw bestanden in OneDrive](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [Microsoft Security Intelligence-rapport](https://www.microsoft.com/securityinsights/)

- [Macro's in Office-bestanden in- of uitschakelen](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [Aanbevolen instellingen voor EOP- en Microsoft Defender voor Office 365-beveiliging](recommended-settings-for-eop-and-office365-atp.md)

- [Een goede upgrade: De beveiliging van de volgende generatie in Windows 10 is bestand tegen ransomware-virussen in 2017](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [No mas, Samas: What's in this ransomware's modus operandi?](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [Locky malware, geluk om dit te vermijden](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [MSRT juli 2016: Cerber-ransomware](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [De drie koppen van de Cerberus-like Cerber ransomware](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [Troldesh-ransomware die zijn beïnvloed door (de) Da Wordt-code](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
