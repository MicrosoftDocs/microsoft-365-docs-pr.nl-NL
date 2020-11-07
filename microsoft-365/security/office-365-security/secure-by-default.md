---
title: Standaard veilig in Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Meer informatie over de standaardinstelling veilig in Exchange Online Protection (EOP)
ms.openlocfilehash: 50d1c64e4d8343fdb9b25bfcbeee5d988ddc6b8a
ms.sourcegitcommit: 9dbc6a08177aaca112e84d30dbaa79a0a8e9dbf8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2020
ms.locfileid: "48945328"
---
# <a name="secure-by-default-in-office-365"></a>Standaard veilig in Office 365

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

' Veilig standaard ' is een term die wordt gebruikt voor het definiëren van de standaardinstellingen die zo veilig mogelijk zijn.

De beveiliging moet echter worden gesaldeerd met productiviteit. Dit kan gelden voor de volgende taken:

- Bruikbaarheids functie: de instellingen zijn niet te vinden in de manier van gebruikers productiviteit.
- Risico: beveiliging kan belangrijke activiteiten blokkeren.
- Verouderde instellingen: sommige configuraties voor oudere producten en functies kunnen worden bijgehouden voor zakelijke redenen, zelfs als nieuwe, moderne instellingen zijn verbeterd.

Microsoft 365-organisaties met postvakken in Exchange Online zijn beveiligd via Exchange Online Protection (EOP). Deze bescherming omvat:

1. E-mail met verdachte malware wordt automatisch in quarantaine geplaatst en geadresseerden ontvangen een melding. Zie [anti-malwarebeleid in EOP configureren](configure-anti-malware-policies.md).
1. Malafide e-mailadres dat is aangeduid als ' hoge betrouwbaarheid ' wordt verwerkt overeenkomstig de actie tegen antispambeleid. Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md).

Aangezien Microsoft onze klanten de mogelijkheid geeft standaard te beschermen, worden sommige tenants overschreven voor malware of een hoge betrouwbaarheid. Deze overschrijvingen zijn:

- Lijsten met toegestane afzenders of toegestane domeinen (Antispambeleid)
- Veilige afzenders van Outlook
- Lijst met toegestane IP-adressen (verbindingen filteren)

Meer informatie over deze overschrijvingen vindt u in [lijsten met veilige afzenders maken](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).

Deze instelling is standaard veilig en is niet een instelling die kan worden in-of uitgeschakeld, maar de manier waarop onze filters van het vak werken, om ongewenste berichten in uw postvakken te houden. Malware en kwaliteit van hoge betrouwbaarheid worden naar Quarantine verzonden. Alleen beheerders kunnen berichten beheren die zijn gequarantined als malware of phishing van hoge betrouwbaarheid, en kunnen ze ook fout-positieven naar Microsoft melden. Zie voor meer informatie geplaatste [berichten en bestanden beheren als beheerder in EOP](manage-quarantined-messages-and-files.md)

## <a name="exceptions"></a>Ring

De enige overschrijving waarmee alle filters worden overgeslagen omvat:

- Exchange-Transport regels (ETR toe)/mail-stroom regels. Met behulp van regels voor e-mail stroom kunt u het betrouwbaarheidsniveau voor ongewenste e-mail (SCL) instellen in berichten in EOP.
- Tenant accepteren/blokkeren: Url's en bestanden beheren in de lijst Tenant toestaan/blokkeren.

Dit soort overschrijvingen is handig voor:

- Phishing-simulaties: gesimuleerde aanvallen kunnen u helpen gevoelige gebruikers te identificeren voordat een echte aanval van invloed is op uw organisatie.
- Beveiligings-SecOps-postvakken: speciale postvakken die door beveiligings teams worden gebruikt om ongefilterde berichten te ontvangen (zowel goed als slecht). Teams kan vervolgens controleren of ze schadelijke inhoud bevatten.
- Filters van derden: sommige leveranciers van derden adviseren om EOP (SCL =-1) uit te schakelen als het filter van een derde partij de filtering voor e-mail beheert. Microsoft adviseert om EOP uit te schakelen als EOP is vereist voor Defender voor Office 365.
- Foutberichten: u kunt bepaalde berichten die nog door Microsoft worden geanalyseerd, toestaan door de [admin-inzendingen](admin-submission.md). Net als met alle overschrijvingen, is het raadzaam dat ze tijdelijk zijn.
