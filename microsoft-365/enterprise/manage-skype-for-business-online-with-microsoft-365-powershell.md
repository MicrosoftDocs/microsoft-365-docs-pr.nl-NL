---
title: Skype voor Bedrijven Online beheren met PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: 054c16e6-9fd1-4e85-a0e6-81788b8410ea
description: Gebruik PowerShell voor Microsoft 365 om beleidsregels voor Skype voor Bedrijven Online, beleidsregels per gebruiker en vergaderingsinstellingen te beheren.
ms.openlocfilehash: 1992edfb6d1c141c7ed4db22064960873b768865
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/06/2021
ms.locfileid: "50514954"
---
# <a name="manage-skype-for-business-online-with-powershell"></a>Skype voor Bedrijven Online beheren met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

De beheerders van Skype voor Bedrijven Online zijn verantwoordelijk voor het beleidsbeheer. Sommige van deze taken zijn uit te voeren in het Microsoft 365-beheercentrum. Andere taken zijn gemakkelijker uit te voeren in PowerShell.

## <a name="before-you-start"></a>Voordat u van start gaat

  > [!Note]
   > Skype voor Bedrijven Online-connector maakt momenteel deel uit van de nieuwste Teams PowerShell-module. Als u de meest recente openbare versie van Teams PowerShell gebruikt, hoeft u de Skype voor Bedrijven Online-connector niet te installeren.
   
Installeer de [Teams PowerShell-module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).


## <a name="connect-using-admin-credentials"></a>Verbinding maken met beheerdersreferenties.

1. Open een opdrachtpromptvenster van Windows PowerShell en voer de volgende opdrachten uit:
    
   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

2. Voer in het dialoogvenster **Referentieaanvraag voor Windows PowerShell** de naam en het wachtwoord van uw administrator-account en selecteer **OK**.


## <a name="connect-using-an-admin-account-with-multi-factor-authentication"></a>Verbinding maken met een beheerdersaccount met meervoudige verificatie

1. Open een Windows PowerShell-opdrachtpromptvenster en voer de volgende opdrachten uit:

   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

2. Voer uw administrator-accountnaam voor Skype voor Bedrijven Online in wanneer u hierom wordt gevraagd.

3. Voer in het dialoogvenster **Aanmelden bij uw account** uw administrator-wachtwoord voor Skype voor Bedrijven Online en klik op **Aanmelden**.

4. Volg de instructies in het dialoogvenster **Aanmelden bij uw account** om verificatiegegevens toe te voegen, zoals een verificatiecode. Klik vervolgens op **Bevestigen**.

Zie voor meer informatie:
  
- [Beleidsregels voor Skype voor Bedrijven Online beheren met PowerShell](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
- [Beleidsregels per gebruiker toewijzen voor Skype voor Bedrijven Online met PowerShell](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
## <a name="see-also"></a>Zie ook

[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)

[PowerShell-cmdlet-verwijzingen voor Skype voor Bedrijven](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)
