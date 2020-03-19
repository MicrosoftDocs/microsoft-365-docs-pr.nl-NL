---
title: Melding van ongewenste e-mail uitschakelen in de webversie van Outlook
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 8d57fe9e-57b8-4884-9317-80b380804b4a
ms.collection:
- M365-security-compliance
description: Als Office 365-beheerder u de mogelijkheid uitschakelen waarop mensen e-mail als ongewenste e-mail kunnen melden.
ms.openlocfilehash: 0bca03786d0335c24e48340e588510f09d6f6a7e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42812062"
---
# <a name="turn-off-junk-email-reporting-in-outlook-on-the-web"></a>Melding van ongewenste e-mail uitschakelen in de webversie van Outlook

U ongewenste, phishing- en niet-ongewenste berichten naar Microsoft verzenden voor analyse met behulp van de webopties voor ongewenste e-mail (voorheen bekend als Outlook Web App), zoals beschreven in De rapportageopties voor [ongewenste e-mail melden en phishing in het web van Outlook.](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) Als u deze opties niet wilt gebruiken, kunnen beheerders deze uitschakelen via de cmdlet [Set-OwaMailboxPolicy.](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?
<a name="sectionSection0"> </a>

- Geschatte tijd om te voltooien: 5 minuten

- U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren. Zie het item 'Outlook in het webpostvakbeleid' in [Exchange Online-machtigingen](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions#exchange-online-permissions)om te zien welke machtigingen u nodig hebt.

- Zie Verbinding maken met [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)als u verbinding wilt maken met Exchange Online PowerShell.

## <a name="turn-off-junk-phishing-and-not-junk-reporting-to-microsoft"></a>Ongewenste e-mail, phishing en geen ongewenste rapportage aan Microsoft uitschakelen
<a name="sectionSection1"> </a>

Voer eerst de volgende opdracht uit om de namen van uw beschikbare Outlook in het webpostvakbeleid op te halen:

```
Get-OwaMailboxPolicy | Format-Table Name
```

Gebruik vervolgens de volgende syntaxis om ongewenste e-mail in te schakelen of uit te schakelen en geen ongewenste rapportage aan Microsoft in de webversie van Outlook:

```
Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
```

In dit voorbeeld wordt rapportage uitgeschakeld in het standaardpostvakbeleid van Outlook-webapp:

```
Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
```

Zie [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) en [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy)voor gedetailleerde syntaxis- en parametergegevens.

## <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?
<a name="sectionSection2"> </a>

**Voer Get-OWAMailboxPolicy** uit om de parameterwaarden te controleren en open Outlook op het web voor een getroffen gebruiker (die het beleid van Outlook op het webpostvak op hen heeft toegepast) en controleer of de opties voor het melden van ongewenste, phishing en niet-ongewenste berichten niet beschikbaar zijn. U berichten nog steeds markeren als ongewenste e-mail, phishing en niet als ongewenste e-mail, maar u ze niet melden.
