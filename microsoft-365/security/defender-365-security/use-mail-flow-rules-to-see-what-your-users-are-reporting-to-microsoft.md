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
description: Beheerders kunnen leren hoe ze regels voor e-mailstroom (ook wel transportregels genoemd) kunnen gebruiken om kopieën te ontvangen van berichten die gebruikers rapporteren aan Microsoft.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5e6428a228ae64562f0b529f6aa90ddc3be46fdc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057210"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>Regels voor e-mailstromen gebruiken om te zien wat je gebruikers melden bij Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken zijn er verschillende manieren voor gebruikers om berichten te rapporteren aan Microsoft voor analyse, zoals beschreven in Berichten en bestanden rapporteren aan [Microsoft.](report-junk-email-messages-to-microsoft.md)

U kunt een regel voor de e-mailstroom maken (ook wel transportregel genoemd) die zoekt naar berichten die gebruikers rapporteren aan Microsoft en u kunt BCC-geadresseerden zo configureren dat kopieën van deze gerapporteerde berichten worden ontvangen.

U kunt de regel voor de e-mailstroom maken in het Exchange-beheercentrum (EAC) en PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U moet machtigingen krijgen toegewezen in Exchange Online of Exchange Online Protection voordat u de procedures in dit artikel kunt uitvoeren. U hebt met name de rol **Transportregels** nodig, die standaard is toegewezen aan de rollengroepen **Organisatiebeheer,** **Compliancebeheer** (globale beheerders) en **Recordsbeheer.**

  Zie de volgende onderwerpen voor meer informatie:

  - [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo)
  - [Machtigingen in standalone EOP](feature-permissions-in-eop.md)
  - [De lijst met leden in rollengroepen wijzigen met het EAC](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Zie [Exchange-beheercentrum in Exchange Online](/Exchange/exchange-admin-center)om het EAC in Exchange Online te openen. Zie [Exchange-beheercentrum in](exchange-admin-center-in-exchange-online-protection-eop.md)zelfstandige EOP om de EAC in zelfstandige EOP te openen.

- Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- Zie de volgende onderwerpen voor meer informatie over e-mailstroomregels in Exchange Online en zelfstandige EOP:
  - [Regels voor e-mailstroom (transportregels) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - [Voorwaarden en uitzonderingen voor e-mailstroomregel (predicaten) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)
  - [Acties voor e-mailstroomregel in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>De EAC gebruiken om een e-mailstroomregel te maken om kopieën van gerapporteerde berichten te ontvangen

1. Ga in het EAC naar **E-mailstroomregels.** \> 

2. Klik **op Pictogram** Toevoegen toevoegen en selecteer vervolgens Een nieuwe regel ![ ](../../media/ITPro-EAC-AddIcon.png) **maken.**

3. Configureer **de volgende instellingen** op de pagina Nieuwe regel die wordt geopend:

   - **Naam:** Voer een unieke, beschrijvende naam in voor de regel. Bijvoorbeeld BCC-berichten die zijn gerapporteerd bij Microsoft.

   - Klik **op Meer opties.**

   - Pas deze regel  toe **als**: Selecteer Het adres van de geadresseerde bevat een van deze woorden: Voer in het dialoogvenster Woorden of woordgroepen opgeven een van de volgende waarden in, klik op Pictogram toevoegen toevoegen en herhaal dit totdat u alle waarden hebt \>    ![ ](../../media/ITPro-EAC-AddIcon.png) ingevoerd.

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `not_junk@office365.microsoft.com`

     Als u een item wilt bewerken, selecteert u deze en klikt **u** op ![ Pictogram Bewerken ](../../media/ITPro-EAC-EditIcon.png) bewerken. Als u een item wilt verwijderen, selecteert u deze en klikt **u op Pictogram** ![ ](../../media/ITPro-EAC-DeleteIcon.png) Verwijderen.

     Wanneer u klaar bent, klikt u op **OK.**

   - **Ga als volgt** te werk: Selecteer **Geadresseerden toevoegen** aan het vak \> **BCC.** Zoek en selecteer de geadresseerden die u wilt toevoegen in het dialoogvenster dat wordt weergegeven. Wanneer u klaar bent, klikt u op **OK.**

4. U kunt extra selecties maken om de regel te controleren, de regel te testen, de regel te activeren tijdens een bepaalde periode en andere instellingen. Het is raadzaam om de regel te testen voordat u deze afdwingt.

5. Klik op **Opslaan** wanneer u gereed bent.

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>PowerShell gebruiken om een e-mailstroomregel te maken om kopieën van gerapporteerde berichten te ontvangen

In dit voorbeeld wordt een nieuwe regel voor de e-mailstroom gemaakt met de naam BCC-berichten die zijn gerapporteerd bij Microsoft en die zoekt naar e-mailberichten die aan Microsoft zijn gerapporteerd met de methoden die in dit artikel worden beschreven, en die de gebruikers laura@contoso.com en julia@contoso.com als BCC-geadresseerden toevoegt.

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

Zie [Nieuwe-Transportregel](/powershell/module/exchange/new-transportrule) voor gedetailleerde syntaxis- en parameterinformatie.

## <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u wilt controleren of u een e-mailstroomregels hebt geconfigureerd om kopieën van gerapporteerde berichten te ontvangen, gaat u als volgt te werk:

- Ga in het EAC naar **E-mailstroomregels** en selecteer de regel op Pictogram Bewerken \>  \> bewerken en \> controleer de  ![ ](../../media/ITPro-EAC-EditIcon.png) instellingen.

- Voer in PowerShell de volgende opdracht uit om de instellingen te verifiëren:

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- Verzend een testberichten naar een van de rapportage-e-mailadressen en controleer de resultaten.