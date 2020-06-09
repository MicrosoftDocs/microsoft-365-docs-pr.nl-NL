---
title: Regels voor e-mailstromen gebruiken om te zien wat uw gebruikers melden bij Microsoft
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe ze regels voor e-mailstroom (ook wel transportregels genoemd) kunnen gebruiken om kopieën te ontvangen van berichten die gebruikers aan Microsoft rapporteren.
ms.openlocfilehash: d50a0f02dd3d65b8576261fc2332aba86d55df56
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616788"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>Regels voor e-mailstromen gebruiken om te zien wat uw gebruikers melden bij Microsoft

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken, zijn er meerdere manieren voor gebruikers om berichten te rapporteren aan Microsoft voor analyse zoals beschreven in [Rapportberichten en bestanden aan Microsoft](report-junk-email-messages-to-microsoft.md).

U een e-mailstroomregel (ook wel een transportregel genoemd) maken die zoekt naar berichten die gebruikers aan Microsoft rapporteren en u BCC-ontvangers configureren om kopieën van deze gerapporteerde berichten te ontvangen.

U de mailstroomregel maken in het Exchange-beheercentrum (EAC) en PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; standalone EOP PowerShell voor organisaties zonder Exchange Online-postvakken).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U moet machtigingen krijgen toegewezen in Exchange Online of EOP voordat u deze procedures uitvoeren. In het bijzonder moet u de rol **Transportregels** toegewezen krijgen, die standaard is toegewezen aan de rollen **Organisatiebeheer,** **Compliance Management**en **Records Management.** Zie [Rolgroepen beheren in Exchange Online voor](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)meer informatie.

- Zie [Exchange-beheercentrum in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center) of [Exchange-beheercentrum in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md)om de EAC te openen.

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.

- Zie de volgende onderwerpen voor meer informatie over regels voor e-mailstromen in Exchange Online en standalone EOP:

  - [Regels voor e-mailstroom (transportregels) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Voorwaarden en uitzonderingen voor e-mailstroomregel in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Acties van de mailstroomregel in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>De EAC gebruiken om een e-mailstroomregel te maken om kopieën van gerapporteerde berichten te ontvangen

1. Ga in de EAC naar **Regels voor e-mailstromen** \> **Rules**.

2. Klik **op** ![ pictogram Toevoegen en selecteer ](../../media/ITPro-EAC-AddIcon.png) **vervolgens Een nieuwe regel maken**.

3. Configureer op de pagina **Nieuwe regel** die wordt geopend de volgende instellingen:

   - **Naam**: Voer een unieke, beschrijvende naam voor de regel in. Bcc-berichten gerapporteerd aan Microsoft.

   - Klik op **Meer opties**.

   - **Pas deze regel toe als:** Selecteer Het adres van **de geadresseerde** \> **bevat een van deze woorden:** Voer in het dialoogvenster **Woorden of zinnen opgeven** die wordt weergegeven een van de volgende waarden in, klik op Pictogram **toevoegen** en herhaal totdat u alle waarden ![ hebt ](../../media/ITPro-EAC-AddIcon.png) ingevoerd.

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     Als u een item wilt bewerken, selecteert u het item en **klikt** u op ![ pictogram Bewerken ](../../media/ITPro-EAC-EditIcon.png) bewerken . Als u een item wilt **Remove** verwijderen, selecteert u deze en klikt u op ![ pictogram Verwijderen verwijderen ](../../media/ITPro-EAC-DeleteIcon.png) .

     Klik op **OK**als u klaar bent.

   - **Ga als volgt te**werk : **Selecteer Geadresseerden toevoegen** aan het vak \> **BCC**. Zoek en selecteer in het dialoogvenster dat wordt weergegeven de geadresseerden die u wilt toevoegen. Klik op **OK**als u klaar bent.

4. U extra selecties maken om de regel te controleren, de regel te testen, de regel te activeren tijdens een bepaalde periode en andere instellingen. We raden u aan de regel te testen voordat u deze afdwingt.

5. Klik op **Opslaan** wanneer u gereed bent.

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>PowerShell gebruiken om een e-mailstroomregel te maken om kopieën van gerapporteerde berichten te ontvangen

In dit voorbeeld wordt een nieuwe e-mailstroomregel gemaakt met de naam BCC-berichten gerapporteerd aan Microsoft die zoekt naar e-mailberichten die aan Microsoft worden gerapporteerd met behulp van de methoden die in dit onderwerp worden beschreven, en voegt de gebruikers toe laura@contoso.com en julia@contoso.com als BCC-ontvangers.

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

Zie [Nieuwe-Transportregel](https://docs.microsoft.com/powershell/module/exchange/new-transportrule) voor gedetailleerde syntaxis- en parameterinformatie.

## <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Als u wilt controleren of u een e-mailstroomregels hebt geconfigureerd om kopieën van gerapporteerde berichten te ontvangen, voert u een van de volgende stappen uit:

- Ga in de EAC naar **E-mailstroomregels** \> **Rules** \> selecteer de regel \> klik op **Edit** ![ pictogram Bewerken ](../../media/ITPro-EAC-EditIcon.png) bewerken en controleer de instellingen.

- Voer in PowerShell de volgende opdracht uit om de instellingen te verifiëren:

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- Stuur een testbericht naar een van de e-mailadressen van de rapportage en controleer de resultaten.
