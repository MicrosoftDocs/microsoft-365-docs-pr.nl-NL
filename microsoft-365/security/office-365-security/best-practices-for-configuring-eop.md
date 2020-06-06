---
title: Aanbevolen procedures voor het configureren van EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: Volg deze aanbevelingen voor de beste praktijken voor standalone Exchange Online Protection (EOP) om u op te zetten voor succes en veelvoorkomende configuratiefouten te voorkomen.
ms.openlocfilehash: 69b0789612d6490305ff31d89954bc1d9258ac01
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2020
ms.locfileid: "44587530"
---
# <a name="best-practices-for-configuring-standalone-eop"></a>Aanbevolen procedures voor het configureren van standalone EOP

Volg deze aanbevelingen voor de beste praktijken voor standalone Exchange Online Protection (EOP) om u op te zetten voor succes en veelvoorkomende configuratiefouten te voorkomen. In dit onderwerp wordt ervan uitgegaan dat u het installatieproces al hebt voltooid. Zie Uw [EOP-service instellen](set-up-your-eop-service.md)als u de EOP-installatie nog niet hebt voltooid.

## <a name="use-a-test-domain"></a>Een testdomein gebruiken

We raden u aan een testdomein, subdomein of domein met een laag volume te gebruiken voor het uitproberen van servicefuncties voordat u deze implementeert op uw productiedomeinen met een groter volume.

## <a name="synchronize-recipients"></a>Ontvangers synchroniseren

Als uw organisatie bestaande gebruikersaccounts heeft in een on-premises Active Directory-omgeving, u deze accounts synchroniseren met Azure Active Directory in de cloud. Het gebruik van adreslijstsynchronisatie wordt aanbevolen. Zie [EOP beheren](manage-mail-users-in-eop.md)voor meer informatie over de voordelen van het gebruik van adreslijstsynchronisatie en de stappen voor het instellen ervan.

## <a name="recommended-settings"></a>Aanbevolen instellingen

We stellen beveiligingsbeheerders in staat om hun beveiligingsinstellingen aan te passen aan de behoeften van hun organisatie. Hoewel er in de regel twee beveiligingsniveaus in EOP en Office 365 ATP zijn die we aanbevelen: Standaard en Streng. Deze instellingen worden weergegeven in de [aanbevolen instellingen voor EOP- en Office 365 ATP-beveiliging.](recommended-settings-for-eop-and-office365-atp.md)

### <a name="miscellaneousnon-policy-settings"></a>Diverse/niet-beleidsinstellingen

Deze instellingen hebben betrekking op een reeks functies die buiten het beveiligingsbeleid vallen.

|||||
|---|---|---|---|
|**Naam beveiligingsfunctie**|**Standaard**|**Strikte**|**Opmerking**|
|[SPF instellen om adresvervalsing te helpen voorkomen](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|Ja|Ja||
|[DKIM gebruiken om uitgaande e-mail te valideren die wordt verzonden vanuit uw aangepaste domein in Office 365](use-dkim-to-validate-outbound-email.md)|Ja|Ja||
|[DMARC gebruiken om e-mail in Office 365 te valideren](use-dmarc-to-validate-email.md)|Ja|Ja|Gebruik `action=quarantine` voor Standaard, en `action=reject` voor Streng.|
|De [invoegtoepassing Rapportbericht](enable-the-report-message-add-in.md) implementeren om de rapportage van verdachte e-mail door eindgebruikers te verbeteren|Ja|Ja||
|Malware- en spamrapporten plannen|Ja|Ja||
|Automatisch doorsturen naar externe domeinen moet worden geweigerd of gecontroleerd|Ja|Ja||
|Unified Auditing moet worden ingeschakeld|Ja|Ja||
|[IMAP-verbinding met postvak](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Uitgeschakeld|Uitgeschakeld||
|[POP-connectiviteit met postvak](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Uitgeschakeld|Uitgeschakeld||
|Geverifieerde SMTP-indiening|Uitgeschakeld|Uitgeschakeld|Geverifieerde client SMTP indiening (ook bekend als client SMTP indiening of SMTP AUTH) is vereist voor POP3 en IMAP4 klanten om e-mail te sturen.|
|EWS-connectiviteit met postvak|Uitgeschakeld|Uitgeschakeld||
|[PowerShell-connectiviteit](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)|Uitgeschakeld|Uitgeschakeld|Beschikbaar voor postvakgebruikers of [e-mailgebruikers](https://docs.microsoft.com/powershell/module/exchange/get-user) (gebruikersobjecten die worden geretourneerd door de cmdlet van de gebruiker).|
|Gebruik [spoofinformatie](learn-about-spoof-intelligence.md) om afzenders zoveel mogelijk op de witte lijst te zetten|Ja|Ja||
|[Directory-based edge blocking (DBEB)](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|Ingeschakeld|Ingeschakeld|Domeintype = Gezaghebbend|
|[Meervoudige verificatie instellen voor alle beheerdersaccounts](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)|Ingeschakeld|Ingeschakeld||
|

## <a name="troubleshooting"></a>Problemen oplossen

Los algemene problemen en trends op met behulp van de rapporten in het beheercentrum. Zoek specifieke gegevens over één punt over een bericht met behulp van het hulpprogramma voor berichttracering. Meer informatie over rapportage [bij Rapportage en berichttracering in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md). Meer informatie over het hulpprogramma voor berichttracering vindt [plaats in het Security & Compliance Center](message-trace-scc.md).

## <a name="report-false-positives-and-false-negatives-to-microsoft"></a>Valse positieven en valse negatieven melden aan Microsoft

Om te helpen bij het verbeteren van spam filtering in de service voor iedereen, moet u valse positieven (goede e-mail gemarkeerd als slecht) en valse negatieven (slechte e-mail toegestaan) aan Microsoft voor analyse. Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="create-mail-flow-rules"></a>Regels voor e-mailstroom maken

Maak regels voor e-mailstroom (ook wel transportregels genoemd) of aangepaste filters om aan uw bedrijfsbehoeften te voldoen.

Wanneer u een nieuwe regel implementeert voor de productie, selecteert u eerst een van de testmodi om het effect van de regel te zien. Zodra u ervan overtuigd bent dat de regel werkt op de beoogde manier, wijzigt u de regelmodus om af te **dwingen.**

Wanneer u nieuwe regels implementeert, u overwegen de aanvullende actie van **incidentrapport genereren** toe te voegen om de regel in actie te controleren.

Houd in hybride omgevingen waar uw organisatie zowel on-premises Exchange als Exchange Online omvat, rekening met de voorwaarden die u gebruikt in e-mailstroomregels. Als u wilt dat de regels van toepassing zijn op de hele organisatie, moet u de voorwaarden gebruiken die beschikbaar zijn in zowel on-premises Exchange als in Exchange Online. Hoewel de meeste omstandigheden beschikbaar zijn in beide omgevingen, zijn er een paar die alleen beschikbaar zijn in de ene of de andere omgeving. Meer informatie bij [Mail flow rules (transportregels) in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).
