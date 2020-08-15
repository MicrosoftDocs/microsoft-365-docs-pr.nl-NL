---
title: Gebruik Lean popouts om geheugen te verminderen voor het lezen van e-mailberichten
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a6d6ba01-2562-4c3d-a8f1-78748dd506cf
f1.keywords:
- NOCSH
description: Dit artikel bevat informatie over het gebruik van Lean popouts voor het verbeteren van de prestaties van het downloaden van berichten in de webversie van Outlook.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7bf53464ac6b2783fbbfc335fd4ff73dbe4435fb
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689438"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a>Gebruik Lean popouts om geheugen te verminderen voor het lezen van e-mailberichten

Dit artikel bevat informatie over het verbeteren van de downloadprestaties van berichten in de webversie van Outlook. Dit artikel maakt deel uit van het project [netwerk planning en prestaties optimaliseren voor Office 365](https://aka.ms/tune) .
  
Als globale beheerder van Office 365 kunt u de webversie van Outlook configureren voor het leveren van _Lean popouts_, een kleinere en minder geheugenintensief versie van bepaalde e-mailberichten in Microsoft Edge of Internet Explorer. Wanneer Lean popouts is geconfigureerd voor de webversie van Outlook, worden op de server gegenereerde onderdelen geladen die de prestaties optimaliseren.
  
> [!NOTE]
> Met ingang van maart 2018 zijn Lean popouts niet beschikbaar voor berichten waarin beperkingen gelden voor gebruiksrechten, zoals Information Rights Management (IRM).
  
Deze functies werken nog steeds in het hoofdvenster, maar zijn niet beschikbaar in Lean popouts:
  
- Outlook-invoegtoepassingen
  
- Aanwezigheidsgegevens voor Skype voor bedrijven
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a>De kanbanschemagroepen van de popouts configureren voor alle gebruikers binnen uw Office 365-organisatie
  
1. [Maak verbinding met Exchange Online via externe PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx ).
  
2. Voer de cmdlet [set-OrganizationConfig](https://technet.microsoft.com/library/aa997443%28v=exchg.160%29.aspx) uit met de parameter LeanPopoutEnabled als volgt:

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  Als u bijvoorbeeld de popouts voor alle gebruikers in uw organisatie wilt inschakelen:
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  U schakelt de popouts voor alle gebruikers in uw organisatie als volgt uit:

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```
