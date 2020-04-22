---
title: Aanbevolen procedures voor het configureren van EOP en ATP
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
ms.openlocfilehash: 69d069377a061c440c22b7a00dd43795597c50e9
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638534"
---
# <a name="best-practices-for-configuring-eop-and-atp"></a>Aanbevolen procedures voor het configureren van EOP en ATP

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
|[SPF instellen om spoofing te voorkomen](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|Ja|Ja||
|[DKIM gebruiken om uitgaande e-mail te valideren die wordt verzonden vanuit uw aangepaste domein in Office 365](use-dkim-to-validate-outbound-email.md)|Ja|Ja||
|[DMARC gebruiken om e-mail in Office 365 te valideren](use-dmarc-to-validate-email.md)|Ja|Ja|Gebruik action=quarantine voor Standaard en action=reject voor Strict.|
|Add-on rapportbericht implementeren om de melding van verdachte e-mails van eindgebruikers te verbeteren|Ja|Ja||
|Malware- en spamrapporten plannen|Ja|Ja||
|Automatisch doorsturen naar externe domeinen moet worden geweigerd of gecontroleerd|Ja|Ja||
|Unified Auditing moet worden ingeschakeld|Ja|Ja||
|[IMAP-connectiviteit met postvak](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Handicap|Handicap||
|[POP-connectiviteit met postvak](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Handicap|Handicap||
|SMTP-geverifieerde indiening in postvak|Handicap|Handicap||
|EWS-connectiviteit met postvak|Handicap|Handicap||
|[PowerShell-connectiviteit](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)|Handicap|Handicap|Beschikbaar voor postvakgebruikers of e-mailgebruikers (gebruikersobjecten die worden geretourneerd door de cmdlet [Get-User).](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user)|
|Gebruik [spoofinformatie](learn-about-spoof-intelligence.md) om afzenders waar mogelijk op de witte lijst te zetten|Ja|Ja||
|Op directory gebaseerde randblokkering (DBEB)|Ingeschakeld|Ingeschakeld|Domeintype = Gezaghebbend|
|[Meervoudige verificatie instellen voor alle beheerdersaccounts](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)|Ingeschakeld|Ingeschakeld||

## <a name="troubleshooting"></a>Problemen oplossen

Los algemene problemen en trends op door de rapporten in het beheercentrum te gebruiken. Zoek specifieke gegevens over een bericht met één punt met behulp van het hulpprogramma berichttracering. Meer informatie over rapporteren bij [Rapportage en berichttracering in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md). Meer informatie over het hulpprogramma voor berichttracering in [Berichttracering in het Security & Compliance Center](message-trace-scc.md).

## <a name="report-false-positive-and-false-negatives-to-microsoft"></a>Valse positieve en valse negatieven melden aan Microsoft

Om spamfiltering in de service voor iedereen te verbeteren, moet u valse positieven (goede e-mail gemarkeerd als slecht) en valse negatieven (slechte e-mail toegestaan) melden aan Microsoft voor analyse. Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="create-mail-flow-rules"></a>Regels voor e-mailstromen maken

Maak regels voor e-mailstromen of aangepaste filters om aan uw bedrijfsbehoeften te voldoen.

Wanneer u een nieuwe regel in productie implementeert, selecteert u eerst een van de testmodi om het effect van de regel te zien. Zodra u ervan overtuigd bent dat de regel werkt op de beoogde wijze, wijzigt u de regelmodus in **Handhaving**.

Wanneer u nieuwe regels implementeert, u overwegen de extra actie van **IncidentReport genereren** toe te voegen om de regel in actie te controleren.

Houd in hybride omgevingen waar uw organisatie zowel on-premises Exchange als Office 365 omvat, rekening met de voorwaarden die u gebruikt in de regels voor e-mailstromen. Als u wilt dat de regels van toepassing zijn op de hele organisatie, moet u voorwaarden gebruiken die beschikbaar zijn in zowel on-premises Exchange als in Office 365. Hoewel de meeste omstandigheden beschikbaar zijn in beide omgevingen, zijn er een paar die alleen beschikbaar zijn in de ene omgeving of de andere. Meer informatie bij [Mail flow rules (transport regels) in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).
