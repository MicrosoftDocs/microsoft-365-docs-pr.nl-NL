---
title: Ervoor zorgen dat spam wordt doorgestuurd naar de map Ongewenste e-mail van elke gebruiker
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 7/16/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Beheerders kunnen in Exchange Online Protection leren hoe ze spam kunnen doorsturen naar map ongewenste e-mail van gebruikers.
ms.openlocfilehash: 6d1fd625669e8b638a408b2db1993f45fa653ffb
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42806096"
---
# <a name="ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Ervoor zorgen dat spam wordt doorgestuurd naar de map Ongewenste e-mail van elke gebruiker

> [!IMPORTANT]
> Dit onderwerp is alleen van toepassing op EOP-klanten (Exchange Online Protection) die postvakken on-premises hosten in een hybride implementatie. Exchange Online-klanten van wie de postvakken volledig zijn gehost in Office 365, hoeven deze opdrachten niet uit te voeren.

De standaard anti-spam actie voor EOP-klanten is om spamberichten te verplaatsen naar de map Ongewenste e-mail van de ontvangers. Als u deze actie wilt uitvoeren met on-premises postvakken, moet u Exchange-mailstroomregels (ook wel transportregels genoemd) configureren op uw on-premises Edge- of Hub-servers om spamkoppen te detecteren die door EOP zijn toegevoegd. Deze regels voor e-mailstroom bepalen het spamvertrouwensniveau (SCL) dat wordt gebruikt door de eigenschap SclJunkThreshold van de cmdlet Set-OrganizationConfig om spam naar de map Ongewenste e-mail van elk postvak te verplaatsen.

### <a name="to-add-mail-flow-rules-to-ensure-spam-is-moved-to-the-junk-email-folder-by-using-windows-powershell"></a>Regels voor e-mailstromen toevoegen om ervoor te zorgen dat spam wordt verplaatst naar de map Ongewenste e-mail met Windows PowerShell

1. Toegang tot de Exchange Management Shell voor uw on-premises Exchange-server. Zie De **Shell openen**voor meer informatie over het openen van de Exchange Management Shell in uw on-premises Exchange-organisatie.

2. Voer de volgende opdracht uit om door inhoud gefilterde spamberichten door te sturen naar de map Ongewenste e-mail:

   ```Powershell
   New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
   ```

   Waar _NameForRule_ de naam is voor de nieuwe regel, bijvoorbeeld JunkContentFilteredMail.

3. Voer de volgende opdracht uit om berichten die als spam zijn gemarkeerd, te routeren voordat u het inhoudsfilter naar de map Ongewenste e-mail bereikt:

   ```Powershell
   New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
   ```

   Waar _NameForRule_ de naam is voor de nieuwe regel, bijvoorbeeld JunkMailBeforeReachingContentFilter.

4. Voer de volgende opdracht uit om ervoor te zorgen dat berichten van afzenders in een bloklijst in het beleid voor spamfilters, zoals de lijst **met afzenderblokken,** worden doorgestuurd naar de map Ongewenste e-mail:

   ```Powershell
   New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
   ```

   Waar _NameForRule_ de naam is voor de nieuwe regel, bijvoorbeeld JunkMailInSenderBlockList.

Als u het mapbericht Verplaatsen naar **ongewenste e-mail** niet wilt gebruiken, u een andere actie kiezen in uw inhoudsfilterbeleid in het Exchange-beheercentrum. Zie [Beleid voor spamfilters configureren](configure-your-spam-filter-policies.md)voor meer informatie. Zie [Kopteksten voor antispamberichten](anti-spam-message-headers.md)voor meer informatie over deze velden in de koptekst van het bericht.

> [!TIP]
> Als u het actie bericht verplaatsen naar **ongewenste e-mail** niet wilt gebruiken, u een andere actie kiezen in uw inhoudsfilterbeleid in het Exchange-beheercentrum. Zie [Beleid voor spamfilters configureren](configure-your-spam-filter-policies.md)voor meer informatie. Zie [Kopteksten voor antispamberichten](anti-spam-message-headers.md)voor meer informatie over deze velden in de koptekst van het bericht.

## <a name="see-also"></a>Zie ook

[Nieuwe transportregel](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule)
