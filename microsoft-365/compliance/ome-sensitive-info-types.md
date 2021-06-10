---
title: Een beleid voor het type gevoelige informatie maken met Office 365-berichtversleuteling
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_Enterprise
description: Meer informatie over het maken van een beleid voor het type gevoelige informatie voor uw organisatie met Office 365-berichtversleuteling.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ad570f64122aecd245b912b1b6545a5950e838cc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162169"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-message-encryption"></a>Een beleid voor het type gevoelige informatie voor uw organisatie maken met behulp van berichtversleuteling

U kunt de regels Exchange e-mailstroom of DLP (Data Loss Prevention) gebruiken om een beleid voor gevoelige informatie te maken met Office 365-berichtversleuteling. Als u een Exchange e-mailstroomregel wilt maken, kunt u het EAC -beheercentrum (EAC) of PowerShell Exchange gebruiken.

## <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a>Het beleid maken met behulp van e-mailstroomregels in het EAC

Meld u aan bij het Exchange-beheercentrum (EAC) en ga naar **E-mailstroomregels.**  >   Maak op de pagina Regels een regel die van toepassing is op Office 365-berichtversleuteling. U kunt een regel maken op basis van voorwaarden, zoals de aanwezigheid van bepaalde trefwoorden of gevoelige informatietypen in het bericht of de bijlage.

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a>Het beleid maken met behulp van e-mailstroomregels in PowerShell

Gebruik een werk- of schoolaccount met globale beheerdersmachtigingen in uw organisatie, start een Windows PowerShell en maak verbinding met Exchange Online. Zie [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor instructies. Gebruik de Set-IRMConfiguration en New-TransportRule cmdlets om het beleid te maken.

## <a name="example-mail-flow-rule-created-with-powershell"></a>Voorbeeld van een e-mailstroomregel die is gemaakt met PowerShell

Voer de volgende opdrachten uit in PowerShell om een Exchange-mailstroomregel te maken die automatisch e-mailberichten versleutelt die buiten uw organisatie worden verzonden met de optie alleen-versleutelen als de e-mailberichten of hun bijlagen de volgende typen gevoelige informatie bevatten:

- ABA-routeringsnummer
- Creditcardnummer
- Nummer van Het Bureau voor drugshandhaving (DEA)
- V.S. / VK paspoortnummer
- Amerikaans bankrekeningnummer
- U.S. Individual Taxpayer Identification Number (ITIN)
- U.S. Social Security Number (SSN)

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

Zie Set-IRMConfiguration and New-TransportRule [(Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) and [New-TransportRule)](/powershell/module/exchange/new-transportrule)voor meer informatie.

## <a name="how-recipients-access-attachments"></a>Hoe geadresseerden bijlagen openen

Nadat Microsoft een bericht versleutelt, hebben geadresseerden onbeperkte toegang tot bijlagen wanneer ze hun versleutelde e-mail openen en openen.

## <a name="to-prepare-for-this-change"></a>Voorbereidingen treffen voor deze wijziging

Mogelijk wilt u alle toepasselijke documentatie en trainingsmateriaal voor eindgebruikers bijwerken om personen in uw organisatie voor te bereiden op deze wijziging. Deel deze Office 365-berichtversleuteling resources met uw gebruikers:

- [Versleutelde berichten verzenden, weergeven en beantwoorden in Outlook pc](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [Microsoft 365 Essentials Video: Office Berichtversleuteling](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a>Deze wijzigingen weergeven in het auditlogboek

Microsoft 365 deze activiteit controleert en deze beschikbaar stelt voor beheerders. De bewerking is 'New-TransportRule' en een fragment van een voorbeeldauditinvoer uit het auditlogboek zoeken in & compliancecentrum is hieronder:

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications"…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a>Het beleid voor gevoelige informatietypen uitschakelen of aanpassen

Nadat u de Exchange-mailstroomregel hebt gemaakt, [](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) kunt u de regel uitschakelen of bewerken door naar E-mailstroomregels in het Exchange-beheercentrum (EAC) te gaan en de regel ' Uitgaande gevoelige e-mailberichten  >   versleutelen *(standaardregel)* uit te schakelen'.