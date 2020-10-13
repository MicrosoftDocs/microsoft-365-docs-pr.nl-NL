---
title: Herstel na een ransomware-aanval
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Microsoft 365-beheerders kunnen leren hoe ze kunnen worden hersteld via een Ransomware-aanval.
ms.openlocfilehash: c9a8e1035e00509f5c57b8699966544b60b7f9c1
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430607"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a>Herstel van een Ransomware aanval in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Zelfs als u om de bescherming van uw organisatie te beschermen, kunt u nog steeds slachtoffer [van een aanval](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) doen. Ransomware is Big Business en de aanvallen zijn uitgebreid.

Met de stappen in dit onderwerp krijgt u de beste kans om gegevens te herstellen die zijn versleuteld met de Ransomware, en om de verspreiding van de infectie binnen uw organisatie te voorkomen. Houd rekening met de volgende punten voordat u aan de slag gaat:

- Er is geen garantie voor het betalen van de Ransom om toegang te krijgen tot uw bestanden. Met de Ransom kunt u in feite een doelwit maken van een meer Ransomware. Als u al hebt betaald, maar u hebt uw bestanden wel hersteld zonder dat u de resolutie van de aanvaller hoeft te gebruiken, belt u de Bank om te zien of ze de transactie kunnen blokkeren. We raden u ook aan om de fraude aanval aan te melden, websites met uitlichting en Microsoft te melden zoals verderop in dit artikel wordt beschreven.

- Het is heel belangrijk dat u snel aan de aanval antwoordt en de gevolgen hiervan. Hoe meer u wacht, hoe minder waarschijnlijk u de betrokken gegevens kunt herstellen.

## <a name="step-1-verify-your-backups"></a>Stap 1: uw back-ups controleren

Als u offline back-ups hebt, kunt u de versleutelde gegevens waarschijnlijk terugzetten **nadat** u de nettolading van Ransomware (malware) van uw omgeving hebt verwijderd.

U kunt deze stap overslaan als u geen back-ups hebt, of als de back-up ook van invloed zijn op de back-up.

## <a name="step-2-disable-activesync-and-onedrive-sync"></a>Stap 2: ActiveSync en OneDrive-synchronisatie uitschakelen

Met het hoofdpunt kunt u het versleutelen van gegevensversleuteling door de Ransomware beëindigen.

Als u vermoedt dat e-mail een doel is, dient u gebruikers toegang tot postvakken tijdelijk uit te schakelen. Exchange ActiveSync wordt door mobiele apparaten gebruikt voor het synchroniseren van gegevens tussen het apparaat en het Exchange Online-postvak.

Zie [Exchange ActiveSync voor gebruikers uitschakelen in Exchange Online voor meer informatie over](https://support.microsoft.com/help/2795303)het uitschakelen van ActiveSync voor een postvak.

Als u andere soorten toegang wilt uitschakelen voor een postvak, raadpleegt u:

- [MAPI voor een postvak in-of uitschakelen](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).

- [POP3-of IMAP4-toegang voor een gebruiker in-of uitschakelen](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

Als u de synchronisatie van OneDrive onderbreekt, wordt de bescherming van uw cloudgegevens verhelpt tegen het bijwerken van mogelijk besmette apparaten. Zie [synchronisatie onderbreken en hervatten in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)voor meer informatie.

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a>Stap 3: Verwijder de malware van de betreffende apparaten

Voer een volledige virusscan uit met de meest recente updates op alle verdachte computers en apparaten om de nettolading te detecteren en te verwijderen die is gekoppeld aan de Ransomware. Vergeet niet om apparaten te gebruiken die gegevens synchroniseren, of het doel van toegewezen netwerkstations (deze computers en apparaten moeten ook worden gescand).

U kunt [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) of (voor oudere clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201)gebruiken.

Een alternatief waarmee u het programma van Ransomware en malware kunt verwijderen is het hulpprogramma voor het verwijderen van [schadelijke software (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).

Als deze opties niet werken, kunt u [Windows Defender offline](https://support.microsoft.com/help/17466) proberen of [problemen oplossen met het detecteren en verwijderen van malware](https://support.microsoft.com/help/4466982).

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a>Stap 4: bestanden herstellen op een geschoonde computer of apparaat

Nadat u de vorige stap hebt uitgevoerd om de een Ransomware-nettolading uit uw omgeving te verwijderen (zodat de software niet uw bestanden kan versleutelen of verwijderen), kunt u de [geschiedenis](https://support.microsoft.com/help/17128) van bestanden in Windows 10 en Windows 8,1 of systeembeveiliging in Windows 7 gebruiken om te proberen om uw lokale bestanden en mappen te herstellen.

**Opmerkingen**:

- U kunt ook de back-upversies van Ransomware versleutelen of verwijderen, zodat u geen bestanden kunt herstellen met bestandsgeschiedenis of systeembeveiliging Als dat het geval is, dan moet u gebruikmaken van back-ups op externe stations of apparaten die niet worden beïnvloed door de Ransomware of OneDrive, zoals beschreven in de volgende sectie.

- Als een map wordt gesynchroniseerd met OneDrive en u niet werkt met de nieuwste versie van Windows, kunnen er enkele beperkingen gelden met de bestandsgeschiedenis.

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a>Stap 5: uw bestanden in OneDrive voor bedrijven herstellen

Met bestanden herstellen in OneDrive voor bedrijven kunt u uw volledige OneDrive herstellen naar een vorig tijdstip in de afgelopen 30 dagen. Zie [uw OneDrive herstellen](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)voor meer informatie.

## <a name="step-6-recover-deleted-email"></a>Stap 6: verwijderde e-mail herstellen

In het zeldzame geval dat de Ransomware al uw e-mail heeft verwijderd, kunt u de verwijderde items waarschijnlijk herstellen. Zie voor meer informatie:

- [Verwijderde berichten herstellen in het postvak van een gebruiker](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [Verwijderde items herstellen in Outlook voor Windows](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a>Stap 7: synchronisatie van Exchange ActiveSync en OneDrive opnieuw inschakelen

Nadat u de computers en apparaten hebt opgeschoond en de gegevens hebt hersteld, kunt u ActiveSync en OneDrive-synchronisatie opnieuw inschakelen die u eerder in [stap 2](#step-2-disable-activesync-and-onedrive-sync)hebt uitgeschakeld.

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a>Stap 8 (optioneel): OneDrive-synchronisatieblok keren voor specifieke bestandsextensies

Wanneer u hebt teruggezet, kunt u voorkomen dat OneDrive voor bedrijven-clients synchroniseren met de bestandstypen die door deze Ransomware werden beïnvloed. Zie [set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction) voor meer informatie.

## <a name="report-the-attack"></a>De aanval melden

### <a name="contact-law-enforcement"></a>Neem contact op met de politie

U dient contact op te nemen met uw lokale of nationale politieautoriteiten. Als u bijvoorbeeld in de Verenigde Staten woont, kunt u contact opnemen met de [FBI Local Field Office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) of [Secret Service](http://www.secretservice.gov/).

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a>Een rapport indienen bij de website voor het rapporteren van de fraude van uw land

Websites voor het rapporteren van de zwendel geven informatie over het voorkomen en vermijden van Scams. Ze bieden ook mechanismen om te rapporteren als u slachtoffer van de zwendel was.

- Australië: [SCAMwatch](http://www.scamwatch.gov.au/)

- Canada: [anti-fraude centrum](http://www.antifraudcentre-centreantifraude.ca/) voor Canada

- Frankrijk: [Agence nationale de la Sécurité des systèmes d'information](http://www.ssi.gouv.fr/)

- Duitsland: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)

- Ierland: [een Garda Síochána](http://www.garda.ie/)

- Nieuw-Zeeland: [fraude zaken](http://www.consumeraffairs.govt.nz/scams)

- Verenigd Koninkrijk: [actie fraude](http://www.actionfraud.police.uk/)

- Verenigde Staten: [online beschermen](http://www.onguardonline.gov/)

Als uw land niet wordt vermeld, vraag dan contact op met uw lokale of nationale politiediensten.

### <a name="submit-email-messages-to-microsoft"></a>E-mailberichten bij Microsoft indienen

U kunt phishing melden met Ransomware met een van de verschillende methoden. Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="see-also"></a>Zie ook

- [Ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [Antwoord op Ransomware – om te betalen of niet te betalen?](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [Noorse hydro reageert op Ransomware-aanval met transparantie](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [Ransomware-detectie en het herstellen van uw bestanden in OneDrive](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [Microsoft Security Intelligence-rapport](https://www.microsoft.com/securityinsights/)

- [Macro's in Office-bestanden in-of uitschakelen](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [Aanbevolen instellingen voor EOP en Office 365 ATP-beveiliging](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp)

- [Een waardevolle-upgrade: beveiliging van volgende generatie voor Windows 10 bewijst krachtig tegen Ransomware-uitbraken in 2017](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [Geen mas, Samas: wat doet zich in de modus operandi van dit Ransomware?](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [Vergrendelings malware, Lucky om dit te voorkomen](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [MSRT juli 2016: Cerber Ransomware](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [De drie koppen van de Cerberus-like Cerber Ransomware](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [Troldeshe Ransomware beïnvloed door (de) da Vinci](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
