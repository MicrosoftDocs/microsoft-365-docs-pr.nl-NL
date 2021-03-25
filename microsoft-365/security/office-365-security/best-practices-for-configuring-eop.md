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
ms.openlocfilehash: dfd0b7290bdcded887ef6b81d5b0d4acbdd6cddb
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204014"
---
# <a name="best-practices-for-configuring-standalone-eop"></a>Best practices voor het configureren van zelfstandige EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
-  [Zelfstandige Exchange Online Protection](exchange-online-protection-overview.md)

Volg deze aanbevolen aanbevelingen voor zelfstandige Exchange Online Protection (EOP) om uzelf in te stellen voor succes en veelvoorkomende configuratiefouten te voorkomen. In dit onderwerp wordt ervan uitgenomen dat u het installatieproces al hebt voltooid. Zie Uw [EOP-service instellen](set-up-your-eop-service.md)als u de EOP-installatie nog niet hebt voltooid.

## <a name="use-a-test-domain"></a>Een testdomein gebruiken

U wordt aangeraden een testdomein, subdomein of laag volumedomein te gebruiken om servicefuncties uit te proberen voordat u ze implementeert op uw productiedomeinen met een hoger volume.

## <a name="synchronize-recipients"></a>Geadresseerden synchroniseren

Als uw organisatie bestaande gebruikersaccounts heeft in een on-premises Active Directory-omgeving, kunt u deze accounts synchroniseren met Azure Active Directory in de cloud. Het is raadzaam adreslijstsynchronisatie te gebruiken. Zie E-mailgebruikers beheren [in EOP](manage-mail-users-in-eop.md)voor meer informatie over de voordelen van het gebruik van adreslijstsynchronisatie en de stappen voor het instellen ervan.

## <a name="recommended-settings"></a>Aanbevolen instellingen

We stellen beveiligingsbeheerders in staat hun beveiligingsinstellingen aan te passen aan de behoeften van hun organisatie. Hoewel er over het algemeen twee beveiligingsniveaus zijn in EOP en Microsoft Defender voor Office 365 die we aanbevelen: Standaard en Strikt. Deze instellingen worden weergegeven in de aanbevolen [instellingen voor EOP en Microsoft Defender voor Office 365-beveiliging.](recommended-settings-for-eop-and-office365.md)

### <a name="miscellaneousnon-policy-settings"></a>Diverse/niet-beleidsinstellingen

Deze instellingen hebben betrekking op een reeks functies die buiten het beveiligingsbeleid staan.

<br>

****

|Naam van beveiligingsfunctie|Standard|Strikt|Opmerking|
|---|---|---|---|
|[SPF instellen om adresvervalsing te helpen voorkomen](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|Ja|Ja||
|[DKIM gebruiken om uitgaande e-mail te valideren die wordt verzonden vanuit uw aangepaste domein in Office 365](use-dkim-to-validate-outbound-email.md)|Ja|Ja||
|[DMARC gebruiken om e-mail in Office 365 te valideren](use-dmarc-to-validate-email.md)|Ja|Ja|Gebruik `action=quarantine` voor Standaard en voor `action=reject` Strikt.|
|De [invoegapp Rapportbericht](enable-the-report-message-add-in.md) of de invoeging [Phishing melden](enable-the-report-phish-add-in.md) implementeren om de rapportage van verdachte e-mail door eindgebruikers te verbeteren|Ja|Ja||
|Malware- en spamrapporten plannen|Ja|Ja||
|Automatisch doorsturen naar externe domeinen moet worden afgekeurd of gecontroleerd|Ja|Ja||
|Unified Auditing moet zijn ingeschakeld|Ja|Ja||
|[IMAP-connectiviteit met postvak](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Uitgeschakeld|Uitgeschakeld||
|[POP-connectiviteit met postvak](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Uitgeschakeld|Uitgeschakeld||
|Geverifieerde SMTP-inzending|Uitgeschakeld|Uitgeschakeld|Geverifieerde SMTP-clientinzending (ook wel SMTP-clientinzending of SMTP AUTH genoemd) is vereist voor POP3- en IMAP4-clients en -toepassingen en -apparaten die e-mail genereren en verzenden. <p> Zie [Geverifieerde SMTP-inzending](/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission)voor klanten in Exchange Online in- of uitschakelen voor instructies voor het globaal of selectief inschakelen en uitschakelen van SMTP AUTH.|
|EWS-connectiviteit met postvak|Uitgeschakeld|Uitgeschakeld|Outlook gebruikt Exchange Web Services voor gratis/bezet, out-of-office-instellingen en het delen van agenda's. Als u EWS niet globaal kunt uitschakelen, hebt u de volgende opties: <ul><li>Gebruik [verificatiebeleid om](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) te voorkomen dat EWS basisverificatie gebruikt als uw clients moderne verificatie (moderne auth) ondersteunen.</li><li>Gebruik [clienttoegangsregels om](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) EWS te beperken tot specifieke gebruikers of bron-IP-adressen.</li><li>Beheer EWS-toegang tot specifieke toepassingen globaal of per gebruiker. Zie Toegang tot [EWS in Exchange](/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange)voor instructies.</li></ul> <p> In [de invoegvoegapp](enable-the-report-message-add-in.md) Rapportbericht en de [phishing-invoegapp](enable-the-report-phish-add-in.md) Rapport wordt STANDAARD REST gebruikt in ondersteunde omgevingen, maar wordt teruggeplaatst naar EWS als REST niet beschikbaar is. De ondersteunde omgevingen die REST gebruiken zijn:<ul><li>Exchange Online</li><li>Exchange 2019 of Exchange 2016</li><li>Huidige Outlook voor Windows via een Microsoft 365-abonnement of een een-time aankoop van Outlook 2019.</li><li>Huidige Outlook voor Mac via een Microsoft 365-abonnement of een een-time aankoop van Outlook voor Mac 2016 of hoger.</li><li>Outlook voor iOS en Android</li><li>De webversie van Outlook</li></ul>|
|[PowerShell-connectiviteit](/powershell/exchange/disable-access-to-exchange-online-powershell)|Uitgeschakeld|Uitgeschakeld|Beschikbaar voor postvakgebruikers of e-mailgebruikers (gebruikersobjecten die worden geretourneerd door de [cmdlet Get-User).](/powershell/module/exchange/get-user)|
|Spoof [intelligence gebruiken om](learn-about-spoof-intelligence.md) afzenders toe te voegen aan uw lijst met toegestane gegevens|Ja|Ja||
|[Directory-based Edge Blocking (DBEB)](/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|Ingeschakeld|Ingeschakeld|Domeintype = Gezaghebbend|
|[Meervoudige verificatie instellen voor alle beheerdersaccounts](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)|Ingeschakeld|Ingeschakeld||
|

## <a name="troubleshooting"></a>Problemen oplossen

U kunt algemene problemen en trends oplossen met behulp van de rapporten in het beheercentrum. Zoek specifieke gegevens over een bericht met behulp van het hulpmiddel Bericht traceren. Meer informatie over rapportage bij [Reporting and message trace in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md). Meer informatie over het hulpprogramma bericht traceren bij [Bericht traceren in het & Compliancecentrum](message-trace-scc.md).

## <a name="report-false-positives-and-false-negatives-to-microsoft"></a>Fout-positieven en onwaar negatieven rapporteren aan Microsoft

Als u spamfilters in de service voor iedereen wilt verbeteren, moet u fout-positieven (goede e-mail die als slecht is gemarkeerd) en foute negatieven (slechte e-mail toegestaan) rapporteren aan Microsoft voor analyse. Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="create-mail-flow-rules"></a>Regels voor e-mailstroom maken

Maak regels voor e-mailstroom (ook wel transportregels genoemd) of aangepaste filters om aan uw zakelijke behoeften te voldoen.

Wanneer u een nieuwe regel implementeert voor de productie, selecteert u eerst een van de testmodi om het effect van de regel te zien. Zodra u tevreden bent dat de regel werkt op de beoogde manier, wijzigt u de regelmodus in **Afdwingen.**

Wanneer u nieuwe regels implementeert, kunt u overwegen om de extra actie van **Incidentrapport** genereren toe te voegen om de regel in actie te controleren.

In hybride omgevingen waarin uw organisatie zowel on-premises Exchange als Exchange Online omvat, moet u rekening houden met de voorwaarden die u gebruikt in regels voor e-mailstroom. Als u wilt dat de regels van toepassing zijn op de hele organisatie, moet u voorwaarden gebruiken die beschikbaar zijn in zowel on-premises Exchange als in Exchange Online. Hoewel de meeste voorwaarden beschikbaar zijn in beide omgevingen, zijn er enkele die alleen beschikbaar zijn in de ene of de andere omgeving. Zie [E-mailstroomregels (transportregels) in Exchange Online voor meer informatie.](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)