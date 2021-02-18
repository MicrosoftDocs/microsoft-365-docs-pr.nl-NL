---
title: Ongewenste e-mail en phishing-e-mail melden in Outlook voor iOS en Android
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Beheerders kunnen meer informatie krijgen over de ingebouwde opties voor het rapporteren van ongewenste e-mail, geen ongewenste e-mail en phishing-e-mail in Outlook voor iOS en Android.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e3e3a2d77c978649e7496d09f78301add397fb9d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289171"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a>Ongewenste e-mail en phishing-e-mail melden in Outlook voor iOS en Android in Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In Microsoft 365-organisaties met postvakken in Exchange Online of on-premises postvakken die gebruikmaken van hybride [moderne](../../enterprise/hybrid-modern-auth-overview.md)verificatie, kunt u de ingebouwde rapportageopties in Outlook voor iOS en Android gebruiken om fout-positieven (goede e-mail gemarkeerd als spam), fout-negatieven (slechte e-mail toegestaan) en phishingberichten naar Exchange Online Protection (EOP) te verzenden.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint

- Voor de beste gebruikersverzending wordt u aangeraden het rapportbericht en de phishing-invoegvoegingen te gebruiken. Zie [De invoegapp Bericht rapporteren inschakelen](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) en [De invoegapp Phishing melden inschakelen](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-phish-add-in) voor meer informatie.

- Als u een beheerder bent in een organisatie met Exchange Online-postvakken, raden we u aan de portal Voorzendingen te gebruiken in het & compliancecentrum. Zie Inzending door beheerders gebruiken om [verdachte spam, phish, URL's](admin-submission.md)en bestanden bij Microsoft in te dienen.

- U kunt gerapporteerde berichten configureren om te worden gekopieerd of omgeleid naar een postvak dat u opgeeft. Zie beleidsregels voor [gebruikersinzending voor meer informatie.](user-submission.md)

- Zie Berichten en bestanden rapporteren bij Microsoft voor meer informatie over het rapporteren van berichten [naar Microsoft.](report-junk-email-messages-to-microsoft.md)

  > [!NOTE]
  > Als rapportage van ongewenste e-mail is uitgeschakeld voor Outlook in het beleid voor het indienen van gebruikers, worden ongewenste e-mail of phishingberichten verplaatst naar de map Ongewenste e-mail en niet gerapporteerd aan uw beheerder of Microsoft.