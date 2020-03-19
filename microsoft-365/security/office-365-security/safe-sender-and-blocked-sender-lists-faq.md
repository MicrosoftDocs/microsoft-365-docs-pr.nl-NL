---
title: Lijsten met afzenders en geblokkeerde afzenders in Exchange Online
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 111ab6b0-2dd2-4a87-a928-4931df6b3c4d
ms.collection:
- M365-security-compliance
description: Als Beheerder van Exchange Online of Exchange Online Protection (Exchange Online Protection) u ervoor zorgen dat een e-mailbericht dat via de service reist, niet als spam wordt gemarkeerd. Een manier om dit te doen is door veilige afzender- en geblokkeerde afzenderlijsten te maken voor de mensen in uw organisatie.
ms.openlocfilehash: 959af558c32e71e5a4cede2aff7bbcd1dbb092e2
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42809181"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a>Lijsten met afzenders en geblokkeerde afzenders in Exchange Online

Als Beheerder van Exchange Online of Exchange Online Protection (Exchange Online Protection) u ervoor zorgen dat een e-mailbericht dat via de service reist, niet als spam wordt gemarkeerd. Een manier om dit te doen is door veilige afzender- en geblokkeerde afzenderlijsten te maken voor de mensen in uw organisatie.

*Bekijk de bijgewerkte versie van de tips en procedures voor het werken met deze lijsten als beheerder in* Hoe [voorkom je dat goede e-mail wordt gemarkeerd als spam in Office 365](prevent-email-from-being-marked-as-spam.md).

Als u geen beheerder bent en u alleen uw eigen ongewenste e-mail in Outlook wilt beheren met behulp van een lijst met veilige afzenders, bekijkt u de stappen in het[overzicht van het filter ongewenste e-mail](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).

## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a>Wat zijn de veilige en geblokkeerde verzendlimieten in Exchange Online?

De limieten voor veilige en geblokkeerde afzenders in Exchange Online verschillen van de limieten voor Active Directory en Outlook. Ze zijn:

- Veilige verzendlimiet: 1.024

- Geblokkeerde afzenderlimiet: 500

Opmerking:

U de fout ervaren die wordt beschreven in [KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app). Schakel het selectievakje E-mails van mijn contactpersonen in vertrouwen uit om dit probleem op te lossen. U ook de hoeveelheid e-mailadressen die zich in uw standaardmap Contactpersonen bevinden, verkleinen om deze binnen de maximaal toegestane limiet van 1024 in Exchange Online te brengen die is ingesteld op het kenmerk 'MaxSafeSenders'. Zie het volgende onderwerp voor meer informatie over dit kenmerk en de cmdlet Set-Mailbox:

[Postvak instellen](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)

## <a name="see-also"></a>Zie ook

[Afzenderfiltering in Exchange Server](https://docs.microsoft.com/exchange/antispam-and-antimalware/antispam-protection/sender-filtering)
