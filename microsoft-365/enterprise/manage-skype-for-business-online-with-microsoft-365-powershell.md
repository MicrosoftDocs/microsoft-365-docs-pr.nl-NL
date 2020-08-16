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
description: 'Overzicht: Gebruik PowerShell voor Microsoft 365 om beleidsregels voor Skype voor Bedrijven Online, beleid per gebruiker en vergaderingsinstellingen te beheren.'
ms.openlocfilehash: aea78d135a5d7ffbb5d8480c549d0fdee88f7d51
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689403"
---
# <a name="manage-skype-for-business-online-with-powershell"></a>Skype voor Bedrijven Online beheren met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Een van de belangrijkste taken van een beheerder van Skype voor Bedrijven Online is beleidsbeheer. Hoewel u sommige van deze taken kunt uitvoeren in het Microsoft 365-beheercentrum, is het uitvoeren van andere taken veel sneller en eenvoudiger in PowerShell. 

## <a name="before-you-start"></a>Voordat u van start gaat

Download en installeer de [Skype voor Business Online-connectormodule](https://www.microsoft.com/download/details.aspx?id=39366) en start vervolgens uw computer opnieuw op.


## <a name="connect-using-a-skype-for-business-online-administrator-account-name-and-password"></a>Verbinding maken met een administrator-accountnaam en wachtwoord voor Skype voor Bedrijven Online

1. Open een opdrachtprompt van Windows PowerShell en voer de volgende opdrachten uit: 
    
   ```powershell
   Import-Module SkypeOnlineConnector
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

2. Typ in het dialoogvenster **Referentieaanvraag voor Windows PowerShell** uw administrator-accountnaam en wachtwoord voor Skype voor Bedrijven Online en klik vervolgens op **OK**.


## <a name="connect-using-a-skype-for-business-online-administrator-account-with-multi-factor-authentication"></a>Verbinding maken met een administrator-account voor Skype voor Bedrijven Online met meervoudige verificatie

1. Open een opdrachtprompt van Windows PowerShell en voer de volgende opdrachten uit:

   ```powershell
   Import-Module SkypeOnlineConnector
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

2. Voer uw administrator-accountnaam voor Skype voor Bedrijven Online in wanneer de **New-CsOnlineSession**-opdracht u hierom vraagt.

3. Typ in het dialoogvenster **Aanmelden bij uw account** uw administrator-wachtwoord voor Skype voor Bedrijven Online en klik vervolgens op **Aanmelden**.

4. Volg de instructies in het dialoogvenster **Aanmelden bij uw account** om aanvullende verificatiegegevens op te geven, zoals een verificatiecode, en klik vervolgens op **Bevestigen**.

Zie de volgende onderwerpen voor meer informatie:
  
- [Beleidsregels voor Skype voor Bedrijven Online beheren met PowerShell](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
- [Beleidsregels per gebruiker toewijzen voor Skype voor Bedrijven Online met PowerShell](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
## <a name="see-also"></a>Zie ook

[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)

[PowerShell-cmdlet-verwijzingen voor Skype voor Bedrijven](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)

