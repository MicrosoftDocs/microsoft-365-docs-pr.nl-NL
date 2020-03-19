---
title: Aanbevolen procedures voor het configureren van EOP en Office 365 ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: Volg deze aanbevolen aanbevelingen voor Exchange Online Protection (EOP) om uzelf voor succes op te stellen en veelvoorkomende configuratiefouten te voorkomen.
ms.openlocfilehash: b4b1f02e3b034b7e89d605a2164b6add3f20dae5
ms.sourcegitcommit: 3d17c1d6b80672719b1878e2f321f0de39595226
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/11/2020
ms.locfileid: "42811307"
---
# <a name="best-practices-for-configuring-eop-and-office-365-atp"></a>Aanbevolen procedures voor het configureren van EOP en Office 365 ATP

Volg deze aanbevolen aanbevelingen voor Exchange Online Protection (EOP) om uzelf voor succes op te stellen en veelvoorkomende configuratiefouten te voorkomen. In dit onderwerp wordt ervan uitgegaan dat u het installatieproces al hebt voltooid. Zie Uw [EOP-service instellen](set-up-your-eop-service.md)als u de EOP-installatie nog niet hebt voltooid.

## <a name="use-a-test-domain"></a>Een testdomein gebruiken

We raden u aan een testdomein, subdomein of domein met een laag volume te gebruiken voor het uitproberen van servicefuncties voordat u deze implementeert op uw productiedomeinen met een hoger volume.

## <a name="synchronize-recipients"></a>Geadresseerden synchroniseren

Als uw organisatie bestaande gebruikersaccounts heeft in een on-premises Active Directory-omgeving, u deze accounts synchroniseren met Azure Active Directory in de cloud. Het gebruik van adreslijstsynchronisatie wordt aanbevolen. Zie [E-mailgebruikers beheren in EOP](manage-mail-users-in-eop.md)voor meer informatie over de voordelen van het gebruik van adreslijstsynchronisatie en de stappen voor het instellen ervan.

## <a name="recommended-settings"></a>Aanbevolen instellingen

We stellen beveiligingsbeheerders in staat om hun beveiligingsinstellingen aan te passen aan de behoeften van hun organisatie. Hoewel er in de regel twee beveiligingsniveaus zijn in EOP en Office 365 ATP die we aanbevelen: Standaard en Strikt. Deze instellingen worden weergegeven in de [aanbevolen instellingen voor EOP- en Office 365 ATP-beveiliging.](recommended-settings-for-eop-and-office365-atp.md)

### <a name="miscellaneousnon-policy-settings"></a>Diverse/niet-beleidsinstellingen

Deze instellingen hebben betrekking op een reeks functies die buiten het beveiligingsbeleid vallen.

|Naam beveiligingsfunctie|Standaard|Strikte|Opmerking|
|---------|---------|---------|---------|
|[Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) (SPF in Office 365 instellen om spoofing te helpen voorkomen)|Ja|Ja||
|[DKIM gebruiken om uitgaande e-mail die vanuit uw aangepaste domein in Office 365 wordt verzonden, te valideren](use-dkim-to-validate-outbound-email.md)|Ja|Ja||
|[DMARC gebruiken om e-mail te valideren in Office 365](use-dmarc-to-validate-email.md)|Ja|Ja|Gebruik action=quarantine voor Standaard en action=reject voor Strict.|
|Add-on rapportbericht implementeren om de melding van verdachte e-mails van eindgebruikers te verbeteren|Ja|Ja||
|Malware- en spamrapporten plannen|Ja|Ja||
|Automatisch doorsturen naar externe domeinen moet worden geweigerd of gecontroleerd|Ja|Ja||
|Unified Auditing moet worden ingeschakeld|Ja|Ja||
|[IMAP-connectiviteit met postvak](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Handicap|Handicap||
|[POP-connectiviteit met postvak](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Handicap|Handicap||
|SMTP-geverifieerde indiening in postvak|Handicap|Handicap||
|EWS-connectiviteit met postvak|Handicap|Handicap||
|[PowerShell-connectiviteit](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)|Handicap|Handicap|Beschikbaar voor postvakgebruikers of e-mailgebruikers (gebruikersobjecten die worden geretourneerd door de cmdlet [Get-User).](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user)|
|Spoofinformatie gebruiken om afzenders zoveel mogelijk op de witte lijst te zetten|Ja|Ja||
|Op directory gebaseerde randblokkering (DBEB)|Ingeschakeld|Ingeschakeld|Domeintype = Gezaghebbend|
|[Meervoudige verificatie instellen voor alle beheerdersaccounts](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)|Ingeschakeld|Ingeschakeld||

## <a name="troubleshooting"></a>Problemen oplossen

Los algemene problemen en trends op door de rapporten in het beheercentrum te gebruiken. Zoek specifieke gegevens over een bericht met één punt met behulp van het hulpprogramma berichttracering. Meer informatie over rapporteren bij [Rapportage en berichttracering in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md). Meer informatie over het hulpprogramma voor berichttracering in [Berichttracering in het Security & Compliance Center](message-trace-scc.md).

## <a name="reporting-false-positive-and-false-negatives-to-microsoft"></a>Melding van false positive en false negatives aan Microsoft

Beheerders dienen valse negatieven (spam) en false positives (niet-spam) bij Microsoft in te dienen via onze portal voor beheerdersinzendingen. E-mails, bestanden en URL's kunnen worden ingediend om beheerders te helpen bepalen waarom we al dan niet berichten aan eindgebruikers hebben geleverd. Zie [Vermoedelijke spam, phish, URL's en bestanden indienen bij Microsoft voor het scannen van Office 365 voor](admin-submission.md)meer informatie.

Eindgebruikers kunnen ook direct valse negatieven (spam) en false positives (non-spam) melden bij Microsoft voor analyse wanneer ze het niet eens zijn met gegeven uitspraken. Zie [Spam, niet-spam en phishing-scamberichten verzenden voor analyse voor meer informatie.](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)

## <a name="create-mail-flow-rules"></a>Regels voor e-mailstromen maken

Maak regels voor e-mailstromen of aangepaste filters om aan uw bedrijfsbehoeften te voldoen.

Wanneer u een nieuwe regel in productie implementeert, selecteert u eerst een van de testmodi om het effect van de regel te zien. Zodra u ervan overtuigd bent dat de regel werkt op de beoogde wijze, wijzigt u de regelmodus in **Handhaving**.

Wanneer u nieuwe regels implementeert, u overwegen de extra actie van **IncidentReport genereren** toe te voegen om de regel in actie te controleren.

Houd in hybride omgevingen waar uw organisatie zowel on-premises Exchange als Office 365 omvat, rekening met de voorwaarden die u gebruikt in de regels voor e-mailstromen. Als u wilt dat de regels van toepassing zijn op de hele organisatie, moet u voorwaarden gebruiken die beschikbaar zijn in zowel on-premises Exchange als in Office 365. Hoewel de meeste omstandigheden beschikbaar zijn in beide omgevingen, zijn er een paar die alleen beschikbaar zijn in de ene omgeving of de andere. Meer informatie bij [Mail flow rules (transport regels) in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).
