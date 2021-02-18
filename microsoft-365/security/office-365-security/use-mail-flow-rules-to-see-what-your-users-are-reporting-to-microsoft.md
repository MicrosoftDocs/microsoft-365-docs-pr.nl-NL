---
title: Regels voor e-mailstromen gebruiken om te zien wat je gebruikers melden bij Microsoft
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Beheerders kunnen informatie krijgen over het gebruik van regels voor de e-mailstroom (ook wel transportregels genoemd) om kopieën te ontvangen van berichten die gebruikers rapporteren aan Microsoft.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 40e87fec3bfd8ed4402713ca7ec45499bb50c68e
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287603"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>Regels voor e-mailstromen gebruiken om te zien wat je gebruikers melden bij Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken zijn er verschillende manieren waarop gebruikers berichten kunnen rapporteren aan Microsoft voor analyse, zoals beschreven in rapportberichten en bestanden [bij Microsoft.](report-junk-email-messages-to-microsoft.md)

U kunt een e-mailstroomregel (ook wel transportregel genoemd) maken die zoekt naar berichten die gebruikers rapporteren aan Microsoft en u kunt BCC-geadresseerden zo configureren dat kopieën van deze gerapporteerde berichten worden ontvangen.

U kunt de regel voor de e-mailstroom maken in het Exchange-beheercentrum (EAC) en PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Postvakken van Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U moet machtigingen toegewezen krijgen in Exchange Online of Exchange Online Protection voordat u de procedures in dit artikel kunt uitvoeren. U hebt met name de rol **Transportregels** nodig, die standaard is toegewezen aan de rollengroepen **Organisatiebeheer,** **Compliancebeheer** (globale beheerders) en **Recordbeheer.**

  Zie de volgende onderwerpen voor meer informatie:

  - [Machtigingen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [Machtigingen in standalone EOP](feature-permissions-in-eop.md)
  - [De lijst met leden in rollengroepen wijzigen met het EAC](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Als u het Exchange-beheercentrum wilt openen in Exchange Online, gaat u naar [het Exchange-beheercentrum in Exchange Online.](https://docs.microsoft.com/Exchange/exchange-admin-center) Zie het Exchange-beheercentrum in de zelfstandige EOP om het Exchange-beheercentrum [te openen in de zelfstandige EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- Zie de volgende onderwerpen voor meer informatie over regels voor de e-mailstroom in Exchange Online en de zelfstandige EOP:
  - [E-mailstroomregels (transportregels) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - [Voorwaarden en uitzonderingen voor e-mailstroomregel (predicaten) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)
  - [Acties voor e-mailstroomregel in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Het EAC gebruiken om een regel voor de e-mailstroom te maken voor het ontvangen van kopieën van gerapporteerde berichten

1. Ga in het EAC naar **Regels voor e-mailstroom.** \> 

2. Klik **op het** pictogram Toevoegen en selecteer een nieuwe regel ![ ](../../media/ITPro-EAC-AddIcon.png) **maken.**

3. Configureer **de volgende instellingen** op de pagina Nieuwe regel die wordt geopend:

   - **Naam:** voer een unieke, beschrijvende naam voor de regel in. Bijvoorbeeld BCC-berichten gerapporteerd bij Microsoft.

   - Klik **op Meer opties.**

   - Pas deze regel  toe **als:** Selecteer het adres van de geadresseerde bevat een van deze woorden: Voer in het dialoogvenster Woorden of woordgroepen opgeven dat wordt weergegeven een van de volgende waarden in, klik op Pictogram toevoegen en herhaal dit totdat u alle waarden hebt \>    ![ ](../../media/ITPro-EAC-AddIcon.png) ingevoerd.

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `not_junk@office365.microsoft.com`

     Als u een item wilt bewerken, selecteert u dit en klikt u op **het pictogram** ![ ](../../media/ITPro-EAC-EditIcon.png) Bewerken. Als u een vermelding wilt verwijderen, selecteert u deze en klikt u **op pictogram** ![ ](../../media/ITPro-EAC-DeleteIcon.png) Verwijderen.

     Klik op OK wanneer u **klaar bent.**

   - **Ga als volgt te** werk: **selecteer Geadresseerden toevoegen** aan het vak \> **BCC.** Zoek en selecteer de geadresseerden die u wilt toevoegen in het dialoogvenster dat wordt weergegeven. Klik op OK wanneer u **klaar bent.**

4. U kunt extra selecties maken om de regel te controleren, de regel te testen, de regel te activeren tijdens een bepaalde periode en andere instellingen. Het is raadzaam de regel te testen voordat u deze afdwingt.

5. Klik op **Opslaan** wanneer u gereed bent.

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>PowerShell gebruiken om een regel voor de e-mailstroom te maken om kopieën van gerapporteerde berichten te ontvangen

In dit voorbeeld wordt een nieuwe regel voor de e-mailstroom gemaakt met de naam BCC-berichten gerapporteerd bij Microsoft, die zoekt naar e-mailberichten die aan Microsoft zijn gerapporteerd aan de hand van de methoden die in dit artikel worden beschreven, en die de gebruikers laura@contoso.com en julia@contoso.com toevoegt als BCC-geadresseerden.

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

Zie [Nieuwe-Transportregel](https://docs.microsoft.com/powershell/module/exchange/new-transportrule) voor gedetailleerde syntaxis- en parameterinformatie.

## <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u wilt controleren of u een regels voor de e-mailstroom hebt geconfigureerd om kopieën van gerapporteerde berichten te ontvangen, gaat u op een van de volgende stappen te werk:

- Ga in het EAC naar Regels voor **e-mailstroom** selecteer de regel en klik op het pictogram \>  \> Bewerken bewerken en \> controleer  ![ de ](../../media/ITPro-EAC-EditIcon.png) instellingen.

- Voer in PowerShell de volgende opdracht uit om de instellingen te controleren:

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- Stuur een testmelding naar een van de e-mailadressen van de rapportage en controleer de resultaten.
