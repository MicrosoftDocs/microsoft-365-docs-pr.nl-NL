---
title: Geavanceerd voorbeeld van jagen voor Microsoft Defender voor Office 365
description: Aan de slag met het zoeken naar e-mailbedreigingen met behulp van geavanceerde zoekactie
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, custom detections, schema, kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d3ac49b4afde0951e7a034c5c11114afbc52c293
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/16/2021
ms.locfileid: "52965142"
---
# <a name="advanced-hunting-example-for-microsoft-defender-for-office-365"></a>Geavanceerd voorbeeld van jagen voor Microsoft Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

Wil je aan de slag met het zoeken naar e-maildreigingen met geavanceerde opsporing? Probeer dit:

De sectie [Aan de slag](/microsoft-365/security/office-365-security/defender-for-office-365#getting-started) van het [Artikel over Microsoft Defender voor Office 365](/microsoft-365/security/office-365-security/defender-for-office-365) heeft logische vroege configuratiesegmenten die er als volgt uitzien:

1. Configureer alles met 'Anti' in de naam.
   - Anti-malware
   - Anti-phishing
   - Antispam
2. Stel alles in met 'Safe' in de naam.
   - Veilige koppelingen
   - Veilige bijlagen
3. De werkbelastingen verdedigen (bijv. SharePoint Online, OneDrive en Teams).
4. Beveiligen met auto purge van nul uur.

Samen met de [snelkoppeling](../office-365-security/protect-against-threats.md) om meteen aan de slag te gaan en start de configuratie op Dag 1.

De laatste stap in **Aan de slag** is de bescherming van gebruikers met **Zero-Hour Auto Purge**, ook bekend als ZAP. Het kan heel belangrijk zijn om te weten of jouw inspanningen om verdachte of schadelijke e-mail te zappen na levering succesvol waren of niet.

Een belangrijk voordeel van het samenvoegen van deze twee beveiligingscentra is snelle navigatie naar Kusto querytaal om problemen op te sporen. Beveiligingsteams kunnen ZAP-missers controleren door hun volgende [stappen](https://security.microsoft.com/advanced-hunting)hier onder **Geavanceerd** jagen \> **te volgen.**

1. Klik op de pagina Geavanceerd zoeken op **Query.**
1. Kopieer de query onderaan naar het queryvenster.
1. Selecteer **Query uitvoeren.**

```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfullyconverge-2-endpoints-new.png
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

:::image type="content" source="../../media/converge-13-advanced-hunt-an-email-zap-new.png" alt-text="De pagina Geavanceerd zoeken (onder Jagen) met Query geselecteerd boven aan het queryvenster en het uitvoeren van een Kusto-query om ZAP-acties in de afgelopen 7 dagen vast te leggen.":::

De gegevens van deze query zullen in het resultatenvenster onder de query zelf zichtbaar zijn. Resultaten bevatten informatie zoal 'DeviceName', 'AccountDisplayName' en 'ZapTime' in een resultatenset die kan aangepast worden. Resultaten kunnen geëxporteerd worden voor het archief. Als het om een query gaat die je later opnieuw nodig zult hebben, selecteer dan **Opslaan** > **Opslaan als** en voeg de query toe aan de lijst van query's, gedeeld of community query's.

## <a name="related-information"></a>Gerelateerde informatie
- [Geavanceerde best practices voor jagen](advanced-hunting-best-practices.md)
- [Overzicht - Geavanceerd zoeken](advanced-hunting-overview.md)
