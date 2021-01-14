---
title: Aanbevolen procedures voor het configureren van EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: Volg deze aanbevolen aanbevelingen voor standalone Exchange Online Protection (EOP) om ervoor te zorgen dat er geen veelvoorkomende configuratiefouten zijn opgetreden.
ms.openlocfilehash: a229f8a269037296fa2b97ff7211343549b33685
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/14/2021
ms.locfileid: "49864886"
---
# <a name="best-practices-for-configuring-standalone-eop"></a>Aanbevolen procedures voor het configureren van zelfstandige EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Volg deze aanbevolen aanbevelingen voor standalone Exchange Online Protection (EOP) om ervoor te zorgen dat er geen veelvoorkomende configuratiefouten zijn opgetreden. In dit onderwerp wordt ervan uitgegaan dat u het installatieproces al hebt voltooid. Als u EOP niet hebt geïnstalleerd, raadpleegt u [uw EOP-service instellen](set-up-your-eop-service.md).

## <a name="use-a-test-domain"></a>Een test domein gebruiken

U wordt geadviseerd om een test domein, subdomein of volume met een laag volume te gebruiken voor het uitvoeren van servicefuncties voordat u deze implementeert op een groter volume, productie domeinen.

## <a name="synchronize-recipients"></a>Geadresseerden synchroniseren

Als uw organisatie bestaande gebruikersaccounts bevat in een on-premises Active Directory-omgeving, kunt u deze accounts synchroniseren met Azure Active Directory in de Cloud. Het gebruik van adreslijstsynchronisatie is aanbevolen. Zie [e-mail gebruikers beheren in EOP](manage-mail-users-in-eop.md)voor meer informatie over de voordelen van het gebruik van adreslijstsynchronisatie en de stappen voor het instellen hiervan.

## <a name="recommended-settings"></a>Aanbevolen instellingen

Beveiligingsbeheerders worden geadviseerd hun beveiligingsinstellingen aan te passen en te voldoen aan de behoeften van hun organisatie. Hoewel het in de regel algemeen een regel is, zijn er twee beveiligingsniveaus in EOP en Microsoft Defender voor Office 365 die wij aanraden: Standard en strict. Deze instellingen worden weergegeven in de [Aanbevolen instellingen voor EOP en Microsoft Defender voor Office 365-beveiliging](recommended-settings-for-eop-and-office365-atp.md).

### <a name="miscellaneousnon-policy-settings"></a>Diversen/niet-beleidsinstellingen

Met deze instellingen wordt een reeks functies besproken die buiten het beveiligingsbeleid vallen.

****

|Naam van beveiligingsfunctie|Standard|Klep|Opmerking|
|---|---|---|---|
|[SPF instellen om adresvervalsing te helpen voorkomen](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|Ja|Ja||
|[DKIM gebruiken om uitgaande e-mail te valideren die wordt verzonden vanuit uw aangepaste domein in Office 365](use-dkim-to-validate-outbound-email.md)|Ja|Ja||
|[DMARC gebruiken om e-mail in Office 365 te valideren](use-dmarc-to-validate-email.md)|Ja|Ja|Gebruik `action=quarantine` voor standaard en `action=reject` voor strikte uitvoering.|
|De [invoegtoepassing bericht melden](enable-the-report-message-add-in.md) of de [invoegtoepassing](enable-the-report-phish-add-in.md) voor het melden van de eindgebruikers van verdachte e-mailberichten verbeteren|Ja|Ja||
|Rapporten van malware en spam plannen|Ja|Ja||
|Automatisch doorsturen naar externe domeinen moet zijn toegestaan of gecontroleerd|Ja|Ja||
|Unified audit moet worden ingeschakeld|Ja|Ja||
|[IMAP-connectiviteit met Postvak](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Uitgeschakeld|Uitgeschakeld||
|[POP-verbinding met Postvak](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Uitgeschakeld|Uitgeschakeld||
|Geverifieerde SMTP-verzending|Uitgeschakeld|Uitgeschakeld|Authenticatie van geverifieerde client (ook wel bekend als client SMTP Submission of SMTP-AUTH) is vereist voor POP3-en IMAP4-clients om e-mail te verzenden.|
|EWS-verbinding met Postvak|Uitgeschakeld|Uitgeschakeld||
|[PowerShell-connectiviteit](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)|Uitgeschakeld|Uitgeschakeld|Beschikbaar voor Postvak gebruikers of e-mail gebruikers (gebruikersobjecten die worden geretourneerd door de cmdlet [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user) ).|
|Gebruik [spoof Intelligence](learn-about-spoof-intelligence.md) om afzenders toe te voegen aan uw lijst toestaan|Ja|Ja||
|[Op mappen gebaseerde rand blokkeren (DBEB)](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|Ingeschakeld|Ingeschakeld|Domein type = gezaghebbend|
|[Meervoudige verificatie instellen voor alle beheerdersaccounts](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)|Ingeschakeld|Ingeschakeld||
|

## <a name="troubleshooting"></a>Problemen oplossen

Algemene problemen en trends oplossen met behulp van de rapporten in het Beheercentrum. Zoek met behulp van het hulpprogramma voor bericht tracering enkele punten met bepaalde gegevens over een bericht. Meer informatie over rapporteren bij [rapportage en bericht traceren in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md). Meer informatie over het hulpprogramma voor bericht tracering vindt u [in het artikel over de beveiligings & nalevings centrum](message-trace-scc.md).

## <a name="report-false-positives-and-false-negatives-to-microsoft"></a>Negatieve en onjuiste negatieven rapporteren aan Microsoft

Als u het filteren van ongewenste e-mail in de service voor iedereen wilt verbeteren, meldt u fout-positieven (goede e-mailberichten die als beschadigd zijn gemarkeerd) en onjuiste negatieven (onjuiste e-mail toegestaan) aan Microsoft voor analyse. Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="create-mail-flow-rules"></a>Regels voor e-mail stroom maken

Maak regels voor de e-mail stroom (ook wel een transportregel genoemd) of aangepaste filters om aan uw bedrijfsbehoeften te voldoen.

Wanneer u een nieuwe regel implementeert voor de productie, selecteert u eerst een van de test modi om het effect van de regel te zien. Wanneer u hebt nagegaan dat de regel op de juiste manier functioneert, moet u de regelmodus wijzigen in **afdwingen**.

Wanneer u nieuwe regels implementeert, kunt u overwegen om de extra actie voor het **genereren van incidenten** toe te voegen om de regel in actie te volgen.

In hybride omgevingen waarbij uw organisatie zowel on-premises Exchange als Exchange Online bevat, kunt u de voorwaarden in de e-mail stroom regels gebruiken. Als u de regels wilt toepassen op de hele organisatie, moet u ervoor zorgen dat voorwaarden worden gebruikt die beschikbaar zijn in de on-premises Exchange-versie en in Exchange Online. Hoewel de meeste voorwaarden in beide omgevingen beschikbaar zijn, zijn er slechts enkele in één omgeving te vinden. Meer informatie vindt u [in e-mail stroom regels (transportregels) in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).
