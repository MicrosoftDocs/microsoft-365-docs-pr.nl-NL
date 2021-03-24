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
description: Microsoft 365-beheerders kunnen leren hoe ze kunnen herstellen van een ransomware-aanval.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 242a4a2f43bd91d75caeaeaa0488f23a5ba4319d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059837"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a>Herstellen van een ransomware-aanval in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Zelfs als u alle voorzorgsmaatregelen neemt om uw organisatie te beschermen, kunt u nog steeds het slachtoffer worden van [een ransomware-aanval.](/windows/security/threat-protection/intelligence/ransomware-malware) Ransomware is belangrijk en de aanvallen zijn zeer geavanceerd.

De stappen in dit artikel geven u de beste kans om gegevens te herstellen en de interne verspreiding van infectie te stoppen. Voordat u aan de slag gaat, moet u rekening houden met de volgende items:

- Er is geen garantie dat het betalen van het losprijs de toegang tot uw bestanden zal retourneren. In feite kan het betalen van het rantsoen u een doel maken voor meer ransomware.

  Als u al hebt betaald, maar u hebt hersteld zonder de oplossing van de aanvaller te gebruiken, neem dan contact op met uw bank om te kijken of deze de transactie kan blokkeren.

  U wordt ook aangeraden de ransomware-aanval te melden bij de ordehandhavers, websites voor oplichtingsrapportage en Microsoft, zoals verder wordt beschreven in dit artikel.

- Het is belangrijk dat u snel reageert op de aanval en de gevolgen ervan. Hoe langer u wacht, hoe kleiner de kans dat u de betreffende gegevens kunt herstellen.

## <a name="step-1-verify-your-backups"></a>Stap 1: Uw back-ups controleren

Als u offlineback-ups hebt, kunt u  waarschijnlijk de versleutelde gegevens herstellen nadat u de ransomware payload (malware) uit uw omgeving hebt verwijderd.

Als u geen back-ups hebt of als uw back-ups ook zijn beïnvloed door de ransomware, kunt u deze stap overslaan.

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a>Stap 2: Exchange ActiveSync en OneDrive-synchronisatie uitschakelen

Het belangrijkste punt hier is om de verspreiding van gegevensversleuteling door de ransomware te stoppen.

Als u vermoedt dat e-mail een doel is van de ransomware-versleuteling, schakelt u de toegang van gebruikers tot postvakken tijdelijk uit. Exchange ActiveSync synchroniseert gegevens tussen apparaten en Exchange Online-postvakken.

Zie Exchange ActiveSync uitschakelen voor gebruikers in Exchange Online als u Exchange ActiveSync voor een postvak [wilt uitschakelen.](https://support.microsoft.com/help/2795303)

Zie andere typen toegang tot een postvak uitschakelen:

- [MAPI voor een postvak in- of uitschakelen.](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)

- [POP3- of IMAP4-toegang in- of uitschakelen voor een gebruiker](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

Als u OneDrive-synchronisatie pauzeert, kunt u uw cloudgegevens beter beschermen tegen updates door mogelijk geïnfecteerde apparaten. Zie Synchronisatie onderbreken en [hervatten in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)voor meer informatie.

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a>Stap 3: De malware van de betreffende apparaten verwijderen

Voer een volledige, huidige antivirusscan uit op alle verdachte computers en apparaten om de payload te detecteren en te verwijderen die is gekoppeld aan de ransomware.

Vergeet niet om apparaten te scannen die gegevens synchroniseren of de doelen van netwerkstations.

U kunt [Windows Defender of](https://www.microsoft.com/windows/comprehensive-security) (voor oudere clients) Microsoft Security [Essentials gebruiken.](https://www.microsoft.com/download/details.aspx?id=5201)

Een alternatief waarmee u ook ransomware of malware kunt verwijderen, is het hulpprogramma voor het verwijderen van schadelijke [software (MSRT).](https://www.microsoft.com/download/details.aspx?id=9905)

Als deze opties niet werken, kunt u [Windows Defender offline](https://support.microsoft.com/help/17466) proberen of problemen met het opsporen en verwijderen van malware [oplossen.](https://support.microsoft.com/help/4466982)

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a>Stap 4: Bestanden herstellen op een opgeschoonde computer of apparaat

Nadat u de vorige stap hebt voltooid om de ransomware-payload uit uw omgeving te verwijderen (waardoor de ransomware uw bestanden niet kan versleutelen of verwijderen), kunt u Bestandsgeschiedenis [gebruiken](https://support.microsoft.com/help/17128) in Windows 10 en Windows 8.1 of Systeembeveiliging in Windows 7 om te proberen uw lokale bestanden en mappen te herstellen.

**Opmerkingen**:

- Sommige ransomware versleutelt of verwijdert ook de back-upversies, zodat u bestandsgeschiedenis of systeembeveiliging niet kunt gebruiken om bestanden te herstellen. Als dat gebeurt, hebt u back-ups nodig op externe stations of apparaten die niet zijn beïnvloed door de ransomware of OneDrive, zoals beschreven in de volgende sectie.

- Als een map wordt gesynchroniseerd met OneDrive en u niet de nieuwste versie van Windows gebruikt, kunnen er enkele beperkingen zijn met behulp van Bestandsgeschiedenis.

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a>Stap 5: Uw bestanden herstellen in uw OneDrive voor Bedrijven

Met Bestanden herstellen in OneDrive voor Bedrijven kunt u uw hele OneDrive binnen de afgelopen 30 dagen terugzetten naar een eerder tijdstip. Zie Uw [OneDrive herstellen voor meer informatie.](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="step-6-recover-deleted-email"></a>Stap 6: Verwijderde e-mail herstellen

In het zeldzame geval dat de ransomware al uw e-mail heeft verwijderd, kunt u waarschijnlijk de verwijderde items herstellen. Zie voor meer informatie:

- [Verwijderde berichten in het postvak van een gebruiker herstellen](/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [Verwijderde items herstellen in Outlook voor Windows](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a>Stap 7: Exchange ActiveSync en OneDrive-synchronisatie opnieuw inschakelen

Nadat u uw computers en apparaten hebt opgeruimd en uw gegevens hebt hersteld, kunt u Exchange ActiveSync en OneDrive-synchronisatie die u eerder hebt uitgeschakeld, opnieuw inschakelen in [stap 2.](#step-2-disable-exchange-activesync-and-onedrive-sync)

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a>Stap 8 (optioneel): OneDrive-synchronisatie blokkeren voor specifieke bestandsextensies

Nadat u bent hersteld, kunt u voorkomen dat OneDrive voor Bedrijven-clients de bestandstypen synchroniseren die door deze ransomware zijn beïnvloed. Zie [Set-SPOTenantSyncClientRestriction (Set-SPOTenantSyncClientRestriction) voor meer informatie.](/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)

## <a name="report-the-attack"></a>De aanval rapporteren

### <a name="contact-law-enforcement"></a>Neem contact op met de ordehandhavers

Neem contact op met uw lokale of federale agentschappen voor rechtshandhaving. Als u bijvoorbeeld in de Verenigde Staten bent, kunt u contact opnemen met het lokale veldkantoor van de [FBI,](https://www.fbi.gov/contact-us/field) [ic3](http://www.ic3.gov/complaint/default.aspx) of [geheime dienst.](http://www.secretservice.gov/)

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a>Een rapport indienen bij de website voor scamrapportage van uw land

Websites voor scamrapportage bieden informatie over het voorkomen en voorkomen van oplichting. Ze bieden ook mechanismen om te rapporteren als u het slachtoffer bent van oplichting.

- Australië: [SCAMwatch](http://www.scamwatch.gov.au/)

- Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)

- Frankrijk: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)

- Duitsland: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)

- Ierland: [An Garda Síochána](http://www.garda.ie/)

- Nieuw-Zeeland: [Oplichting bij consumentenzaken](http://www.consumeraffairs.govt.nz/scams)

- Verenigd Koninkrijk: [Actiefraude](http://www.actionfraud.police.uk/)

- Verenigde Staten: [On Guard Online](http://www.onguardonline.gov/)

Als uw land niet wordt vermeld, vraagt u uw lokale of federale agentschappen voor rechtshandhaving.

### <a name="submit-email-messages-to-microsoft"></a>E-mailberichten verzenden bij Microsoft

U kunt phishingberichten die ransomware bevatten rapporteren met behulp van een van de verschillende methoden. Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="see-also"></a>Zie ook

- [Ransomware](/windows/security/threat-protection/intelligence/ransomware-malware)

- [Ransomware antwoord- om te betalen of niet te betalen?](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [Norsk Hydro reageert op ransomware-aanval met transparantie](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [Ransomware-detectie en het herstellen van uw bestanden in OneDrive](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [Microsoft Security Intelligence Report](https://www.microsoft.com/securityinsights/)

- [Macro's in- of uitschakelen in Office-bestanden](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [Aanbevolen instellingen voor EOP- en Microsoft Defender-beveiliging voor Office 365](recommended-settings-for-eop-and-office365.md)

- [Een waardige upgrade: beveiliging van de volgende generatie in Windows 10 is bestand tegen ransomware-uitbraken in 2017](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [Geen mas, Samas: Wat is er in de modus operandi van deze ransomware?](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [Locky malware, gelukkig om dit te voorkomen](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [MSRT juli 2016: Cerber ransomware](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [De drie hoofden van de Cerberus-achtige Cerber-ransomware](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [Troldesh ransomware beïnvloed door (de) Da Vinci-code](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)