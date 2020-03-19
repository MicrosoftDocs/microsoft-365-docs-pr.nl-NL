---
title: Ongeldige tekens in uw spamfilterregels en het beleid voor spamfilters voorkomen
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 09/24/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Biedt hulp voor beheerders die ongeldige tekens in hun antispamconfiguratie hebben &amp; en problemen ondervinden wanneer ze het Security Compliance Center proberen te gebruiken.
ms.openlocfilehash: f1841eb86583a48acecde0770f030b626323fa8e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42810418"
---
# <a name="avoid-invalid-characters-in-your-spam-filter-rules-and-spam-filter-policy"></a>Ongeldige tekens in uw spamfilterregels en het beleid voor spamfilters voorkomen 

Voorheen hebben Office 365-beheerders regels voor spamfilters en het spamfilterbeleid ingesteld en geconfigureerd met behulp van het Exchange-beheercentrum (EAC). U gebruikt nu &amp; het Security Compliance Center om uw antispamconfiguratie te beheren. De volgende tekens worden ondersteund in de EAC, maar &amp; worden niet ondersteund voor gebruik in het Security Compliance Center.  

**Ongeldige tekens:**
  
```\ % & * + / = ? { } | < > ( ) ; : , [ ] "```

Als uw spamfilterregels of uw spamfilterbeleid een van de ongeldige tekens bevatten, u een of meer van deze problemen tegenkomen:
- Het is mogelijk dat u het beleid &amp; of de regels niet vinden in het Security Compliance Center.
- Mogelijk ontvangt u fouten wanneer u de regels of het beleid probeert te krijgen met Windows PowerShell.
- Mogelijk wordt het beleid of de instellingen niet uitgevoerd of uitgevoerd zoals verwacht.

## <a name="remove-the-invalid-characters-from-the-spam-filter-policy-and-rules"></a>De ongeldige tekens verwijderen uit het beleid en de regels voor spamfilters

Zodra u het beleid en de regels hebt geïdentificeerd die ongeldige tekens bevatten, u de namen wijzigen met behulp van de Windows PowerShell-cmdlets. 

1. [Maak verbinding met Exchange Online via Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).
    
2. Als u de naam van het spamfilterbeleid wilt wijzigen, voert u de cmdlet Set-HostedContentFilterPolicy als volgt uit:
    
    ```powershell
    Set-HostedContentFilterPolicy -Identity "Old policy name" -Name "New policy name"
    ```  

3. Als u de naam van een spamfilterregel wilt wijzigen, voert u de cmdlet Set-HostedContentFilterRule als volgt uit:
    
    ```powershell
    Set-HostedContentFilterRule -Identity "Old rule name" -Name "New rule name"
    ```  

  
 ## <a name="for-more-information"></a>Voor meer informatie

[Bedreigingsbeheer in &amp; het Security Compliance Center](protect-against-threats.md)
  
[Beleid voor set-hostedcontentfilter](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy)

[Regel van set-hostedcontentfilterregel](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule)
