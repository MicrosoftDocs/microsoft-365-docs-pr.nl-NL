---
title: Aanbevolen procedures voor het configureren van EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: Volg deze aanbevolen aanbevelingen voor zelfstandige Exchange Online Protection (EOP) om uzelf in te stellen voor succes en veelvoorkomende configuratiefouten te voorkomen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c64a9592d93ef046ad1c023a49bf378ccf6cf503
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290831"
---
# <a name="best-practices-for-configuring-standalone-eop"></a>Best practices voor het configureren van zelfstandige EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
-  [Zelfstandige versie van Exchange Online Protection](exchange-online-protection-overview.md)

Volg deze aanbevolen aanbevelingen voor zelfstandige Exchange Online Protection (EOP) om uzelf in te stellen voor succes en veelvoorkomende configuratiefouten te voorkomen. In dit onderwerp wordt ervan uitgenomen dat u het installatieproces al hebt voltooid. Zie Uw EOP-service instellen als u de [EOP-service nog](set-up-your-eop-service.md)niet hebt ingesteld.

## <a name="use-a-test-domain"></a>Een testdomein gebruiken

Het is raadzaam om een testdomein, subdomein of laag volumedomein te gebruiken om servicefuncties uit te proberen voordat u deze implementeert in uw productiedomeinen met een hoger volume.

## <a name="synchronize-recipients"></a>Geadresseerden synchroniseren

Als uw organisatie bestaande gebruikersaccounts heeft in een on-premises Active Directory-omgeving, kunt u deze accounts synchroniseren met Azure Active Directory in de cloud. Het is raadzaam adreslijstsynchronisatie te gebruiken. Zie E-mailgebruikers beheren [in EOP](manage-mail-users-in-eop.md)voor meer informatie over de voordelen van adreslijstsynchronisatie en de stappen voor het instellen ervan.

## <a name="recommended-settings"></a>Aanbevolen instellingen

We stellen beveiligingsbeheerders in staat om hun beveiligingsinstellingen aan te passen aan de behoeften van hun organisatie. Als algemene regel gelden er echter twee beveiligingsniveaus in EOP en Microsoft Defender voor Office 365 die we aanraden: Standaard en Strikt. Deze instellingen worden weergegeven in de aanbevolen instellingen voor de beveiliging van EOP en Microsoft Defender voor [Office 365.](recommended-settings-for-eop-and-office365-atp.md)

### <a name="miscellaneousnon-policy-settings"></a>Diverse/niet-beleidsinstellingen

Deze instellingen hebben betrekking op een reeks functies die buiten het beveiligingsbeleid liggen.

****

|Naam van beveiligingsfunctie|Standard|Strikt|Opmerking|
|---|---|---|---|
|[SPF instellen om adresvervalsing te helpen voorkomen](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|Ja|Ja||
|[DKIM gebruiken om uitgaande e-mail te valideren die wordt verzonden vanuit uw aangepaste domein in Office 365](use-dkim-to-validate-outbound-email.md)|Ja|Ja||
|[DMARC gebruiken om e-mail in Office 365 te valideren](use-dmarc-to-validate-email.md)|Ja|Ja|Gebruik `action=quarantine` deze voor Standaard en voor `action=reject` Strikt.|
|De [invoegapp Bericht rapporteren](enable-the-report-message-add-in.md) of de invoegvoegapp [Phishing melden](enable-the-report-phish-add-in.md) implementeren om de rapportage van verdachte e-mailberichten door eindgebruikers te verbeteren|Ja|Ja||
|Malware- en spamrapporten plannen|Ja|Ja||
|Automatisch doorsturen naar externe domeinen is niet toegestaan of gecontroleerd|Ja|Ja||
|Geïntegreerde controle moet zijn ingeschakeld|Ja|Ja||
|[IMAP-connectiviteit met postvak](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Uitgeschakeld|Uitgeschakeld||
|[POP-verbinding met postvak](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Uitgeschakeld|Uitgeschakeld||
|Geverifieerde SMTP-inzending|Uitgeschakeld|Uitgeschakeld|Voor POP3- en IMAP4-clients is geverifieerde SMTP-inzending via de client (ook wel SMTP-indiening of SMTP-AUTH genoemd) vereist voor POP3- en IMAP4-clients.|
|EWS-connectiviteit met postvak|Uitgeschakeld|Uitgeschakeld||
|[PowerShell-connectiviteit](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)|Uitgeschakeld|Uitgeschakeld|Beschikbaar voor postvakgebruikers of e-mailgebruikers (gebruikersobjecten die worden geretourneerd door de cmdlet [Get-User).](https://docs.microsoft.com/powershell/module/exchange/get-user)|
|Spoof [Intelligence gebruiken om](learn-about-spoof-intelligence.md) afzenders toe te voegen aan uw lijst met toegestane afzenders|Ja|Ja||
|[Randblokkering op basis van adreslijst (DBEB)](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|Ingeschakeld|Ingeschakeld|Domeintype = Gezaghebbend|
|[Meervoudige verificatie instellen voor alle beheerdersaccounts](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)|Ingeschakeld|Ingeschakeld||
|

## <a name="troubleshooting"></a>Problemen oplossen

Los algemene problemen en trends op met behulp van de rapporten in het beheercentrum. Zoek specifieke gegevens over een bericht met behulp van de functie Bericht traceren. Meer informatie over rapportage bij [Rapportage en bericht traceren in Exchange Online Protection.](reporting-and-message-trace-in-exchange-online-protection.md) Meer informatie over het hulpprogramma voor bericht traceren [op Bericht traceren in het & Compliancecentrum.](message-trace-scc.md)

## <a name="report-false-positives-and-false-negatives-to-microsoft"></a>Fout-positieven en fout-negatieven rapporteren aan Microsoft

Om spamfilters in de service voor iedereen te verbeteren, moet u fout-positieven (goede e-mail gemarkeerd als slecht) en fout-negatieven (slechte e-mail toegestaan) rapporteren aan Microsoft voor analyse. Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="create-mail-flow-rules"></a>Regels voor de e-mailstroom maken

Maak regels voor de e-mailstroom (ook wel transportregels genoemd) of aangepaste filters om te voldoen aan de behoeften van uw bedrijf.

Wanneer u een nieuwe regel voor de productie implementeert, selecteert u eerst een van de testmodi om het effect van de regel te bekijken. Zodra u tevreden bent dat de regel werkt zoals bedoeld, wijzigt u de regelmodus in **Afdwingen.**

Wanneer u nieuwe regels implementeert, kunt u overwegen de extra actie van **Het incidentenrapport** genereren toe te voegen om de regel in de gaten te houden.

In hybride omgevingen waarin uw organisatie zowel on-premises Exchange als Exchange Online bevat, moet u rekening houden met de voorwaarden die u gebruikt in regels voor de e-mailstroom. Als u de regels wilt toepassen op de hele organisatie, moet u voorwaarden gebruiken die beschikbaar zijn in zowel on-premises Exchange als Exchange Online. Hoewel de meeste voorwaarden beschikbaar zijn in beide omgevingen, zijn er een paar die alleen beschikbaar zijn in de ene omgeving of de andere. Meer informatie over [regels voor de e-mailstroom (transportregels) in Exchange Online.](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
