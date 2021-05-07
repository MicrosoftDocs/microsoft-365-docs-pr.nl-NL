---
title: Versleuteling in Microsoft 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/15/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 0a322724-08ca-43db-b69a-afbfa20484cd
ms.collection:
- M365-security-compliance
- Strat_O365_IP
- m365solution-mip
- m365initiative-compliance
description: Met Office 365 wordt uw inhoud in rust en onderweg versleuteld met de sterkste versleuteling, protocollen en technologieën die beschikbaar zijn. Krijg een overzicht van versleuteling in Office 365.
ms.openlocfilehash: c54508434c5ae5126a79eba1cb6dab3851d8f746
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162153"
---
# <a name="encryption"></a>Versleuteling

Versleuteling is een belangrijk onderdeel van uw strategie voor bestandsbeveiliging en informatiebeveiliging. In dit artikel vindt u een overzicht van versleuteling voor Office 365. Krijg hulp bij versleutelingstaken, zoals het instellen van versleuteling voor uw organisatie en het beveiligen van wachtwoorden voor Office documenten.
  
- Zie Technische informatie over versleuteling [in](technical-reference-details-about-encryption.md)Office 365 voor informatie over certificaten en technologieën zoals TLS.

- Zie Versleuteling instellen in een Office 365 Enterprise voor informatie over het configureren of instellen van [versleuteling voor uw organisatie.](set-up-encryption.md)

## <a name="what-is-encryption-and-how-does-it-work-in-office-365"></a>Wat is versleuteling en hoe werkt dit in Office 365?

Het versleutelingsproces codeert uw gegevens (ook wel plaintext genoemd) in codetekst. In tegenstelling tot tekst zonder tekst kan codetekst niet worden gebruikt door personen of computers, tenzij en totdat de cijfertekst is ontsleuteld. Voor ontsleuteling is een versleutelingssleutel vereist die alleen geautoriseerde gebruikers hebben. Versleuteling helpt ervoor te zorgen dat alleen geautoriseerde geadresseerden uw inhoud kunnen ontsleutelen. Inhoud bevat bestanden, e-mailberichten, agenda-items, en meer.
  
Versleuteling op zich voorkomt niet dat inhoud wordt onderschept. Versleuteling maakt deel uit van een grotere strategie voor informatiebeveiliging voor uw organisatie. Door versleuteling te gebruiken, zorgt u ervoor dat alleen geautoriseerde partijen de versleutelde gegevens kunnen gebruiken.
  
U kunt meerdere versleutelingslagen tegelijk hebben. U kunt bijvoorbeeld e-mailberichten versleutelen en ook de communicatiekanalen waarmee uw e-mailberichten stromen. Met Office 365 worden uw gegevens in rust en onderweg versleuteld, met behulp van verschillende sterke versleutelingsprotocollen en technologieën zoals Transport Layer Security/Secure Sockets Layer (TLS/SSL), Internet Protocol Security (IPSec) en Advanced Encryption Standard (AES).
  
## <a name="encryption-for-data-at-rest-and-data-in-transit"></a>Versleuteling voor gegevens in rust en gegevens die onderweg zijn

  Voorbeelden van gegevens in rust zijn bestanden die u hebt geüpload naar een SharePoint-bibliotheek, Project Online-gegevens, documenten die u hebt geüpload in een Skype voor Bedrijven-vergadering, e-mailberichten en bijlagen die u hebt opgeslagen in mappen in uw postvak en bestanden die u hebt geüpload naar OneDrive voor Bedrijven.
  
 **Voorbeelden van gegevens die onderweg** zijn, zijn e-mailberichten die worden bezorgd of gesprekken die plaatsvinden in een onlinevergadering. In Office 365 zijn gegevens onderweg wanneer het apparaat van een gebruiker communiceert met een Microsoft-server of wanneer een Microsoft-server communiceert met een andere server.
  
Met Office 365 werken meerdere lagen en soorten versleuteling samen om uw gegevens te beveiligen. De volgende tabel bevat enkele voorbeelden, met koppelingen naar aanvullende informatie.
  
|**Soorten inhoud**|**Versleutelingstechnologieën**|**Informatiebronnen**|
|:-----|:-----|:-----|
|Bestanden op een apparaat. Deze bestanden kunnen e-mailberichten bevatten die zijn opgeslagen in een map, Office documenten die zijn opgeslagen op een computer, tablet of telefoon of gegevens die zijn opgeslagen in de Microsoft-cloud.  <br/> |BitLocker in Microsoft-datacenters. BitLocker kan ook worden gebruikt op clientcomputers, zoals Windows computers en tablets  <br/> Distributed Key Manager (DKM) in Microsoft-datacenters  <br/> Klantcode voor Microsoft 365  <br/> |[Windows IT-centrum: BitLocker](/windows/device-security/bitlocker/bitlocker-overview) <br/> [Microsoft Trust Center: Versleuteling](https://www.microsoft.com/TrustCenter/Security/Encryption) <br/> [Reeks beveiligingsbesturingselementen voor de cloud: Gegevens versleutelen bij rest](https://blogs.microsoft.com/microsoftsecure/2015/09/10/cloud-security-controls-series-encrypting-data-at-rest) <br/> [Hoe Exchange Online uw e-mailgeheimen kan beveiligen](exchange-online-secures-email-secrets.md) <br/> [Serviceversleuteling met klantsleutel](customer-key-overview.md) <br/> |
|Bestanden die tussen gebruikers worden overgeslagen. Deze bestanden kunnen bestaan uit Office documenten of SharePoint lijstitems die tussen gebruikers worden gedeeld.  <br/> |TLS voor bestanden die onderweg zijn  <br/> |[Data Encryption in OneDrive for Business and SharePoint Online](data-encryption-in-odb-and-spo.md) <br/> [Skype voor Bedrijven Online: Beveiliging en archivering](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features) <br/> |
|E-mail die tussen geadresseerden wordt verzonden. Deze e-mail bevat e-mail die wordt gehost door Exchange Online.  <br/> |Office 365-berichtversleuteling met Azure Rights Management, S/MIME en TLS voor e-mail die onderweg is  <br/> |[Office 365-berichtversleuteling (OME)](ome.md) <br/> [E-mailversleuteling in Office 365](email-encryption.md) <br/> [Hoe Exchange Online TLS gebruikt voor het beveiligen van e-mailverbindingen in Office 365](exchange-online-uses-tls-to-secure-email-connections.md) <br/> |
|Chats, berichten en bestanden die worden verzonden tussen geadresseerden met Microsoft Teams. <br/> |Teams gebruikt TLS en MTLS om chatberichten te versleutelen. Mediaverkeer wordt versleuteld met Secure RTP (SRTP). Teams maakt gebruik van compatibele FIPS-algoritmen (Federal Information Processing Standard) voor het uitwisselen van versleutelingssleutels. <br/> |[Versleuteling voor Teams](/microsoftteams/teams-security-guide#encryption-for-teams) <br/> |

## <a name="what-if-i-need-more-control-over-encryption-to-meet-security-and-compliance-requirements"></a>Wat moet ik doen als ik meer controle nodig heb over versleuteling om te voldoen aan beveiligings- en compliancevereisten?

Microsoft 365 biedt door Microsoft beheerde oplossingen voor volumeversleuteling, bestandsversleuteling en postvakversleuteling in Office 365. Daarnaast biedt Microsoft versleutelingsoplossingen die u kunt beheren en beheren. Deze versleutelingsoplossingen zijn gebaseerd op Azure.
  
Zie de volgende bronnen voor meer informatie:
  
- [Wat is Azure Rights Management?](/information-protection/understand-explore/what-is-azure-rms)

- [Rights Management activeren in het beheercentrum](../enterprise/activate-rms-in-microsoft-365.md)

- [Set up Information Rights Management (IRM) in SharePoint admin center](set-up-irm-in-sp-admin-center.md)

- [Serviceversleuteling met klantsleutel in Office 365](customer-key-overview.md)

- [Dubbele sleutelversleuteling voor Microsoft 365](double-key-encryption.md)

## <a name="how-do-i"></a>Hoe kan ik...

|**Deze taak uitvoeren**|**Bekijk deze bronnen**|
|:-----|:-----|
|Versleuteling instellen voor mijn organisatie  <br/> |[Versleuteling instellen in Office 365 Enterprise](set-up-encryption.md) <br/> |
|Details weergeven over certificaten, technologieën en TLS-coderingssuites <br/> |[Technische details over versleuteling](technical-reference-details-about-encryption.md) <br/> |
|Werken met versleutelde berichten op een mobiel apparaat  <br/> |[Versleutelde berichten weergeven op uw Android-apparaat](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> [Versleutelde berichten weergeven op uw iPhone of iPad](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |
|Een document versleutelen met wachtwoordbeveiliging  <br/><br/>  Wachtwoordbeveiliging wordt niet ondersteund in een browser. Gebruik bureaubladversies van Word, Excel en PowerPoint voor wachtwoordbeveiliging. |[Beveiliging toevoegen of verwijderen in uw document, werkmap of presentatie](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) <br/> Kies een **sectie Beveiliging toevoegen** en zie Vervolgens **Versleutelen met wachtwoord.**  |
|Versleuteling uit een document verwijderen  <br/> |[Beveiliging toevoegen of verwijderen in uw document, werkmap of presentatie](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) <br/> Kies een **sectie Beveiliging verwijderen** en zie Wachtwoordversleuteling **verwijderen.**  |


## <a name="related-topics"></a>Verwante onderwerpen

[Plannen voor Microsoft 365 beveiligings- en informatiebeveiligingsmogelijkheden](plan-for-security-and-compliance.md)

[Top 10 manieren om uw Microsoft 365 zakelijke abonnementen te beveiligen](/office365/admin/security-and-compliance/secure-your-business-data)

[Versleuteling en afspeelstroom van Microsoft Stream Video](/stream/network-overview#video-level-encryption-and-playback-flow)