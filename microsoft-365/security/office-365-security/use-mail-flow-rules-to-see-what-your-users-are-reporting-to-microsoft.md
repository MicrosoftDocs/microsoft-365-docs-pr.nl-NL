---
title: Regels voor e-mailstromen gebruiken om te zien wat uw gebruikers melden bij Microsoft
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Beheerders kunnen informatie over het gebruik van e-mail stroom regels (ook wel transport-regels genoemd) gebruiken om kopieën te ontvangen van berichten die gebruikers naar Microsoft melden.
ms.openlocfilehash: 9798e808470a506da3d6dff65a5ea91934c1690d
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195865"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>Regels voor e-mailstromen gebruiken om te zien wat uw gebruikers melden bij Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken zijn er meerdere manieren waarop gebruikers berichten kunnen rapporteren aan Microsoft voor analyse zoals beschreven in [berichten en bestanden aan Microsoft rapporteren](report-junk-email-messages-to-microsoft.md).

U kunt een e-mail stroom regel (ook wel een transportregel genoemd) maken waarmee berichten die gebruikers naar Microsoft rapporteren, kunnen worden weergegeven en dat er kopieën van deze gerapporteerde berichten kunnen worden ontvangen.

U kunt de e-mail stroom regel maken in het Exchange Admin Center (SBV) en PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder postvakken van Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U moet machtigingen toegewezen hebben in Exchange Online of EOP voordat u deze procedures kunt uitvoeren. Specifiek moet u de rol van **transport regels** toewijzen, die aan de rollen voor **Organisatiebeheer**, **Compliance Management**, en het **beheer van recordbeheer** standaard is toegewezen. Zie [rollen groepen beheren in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)voor meer informatie.

- Zie [Exchange-Beheercentrum in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center) of [Exchange-Beheercentrum in zelfstandige EOP](exchange-admin-center-in-exchange-online-protection-eop.md)u het menu wilt openen.

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.

- Zie de volgende onderwerpen voor meer informatie over regels voor e-mail stroom in Exchange Online en zelfstandige EOP:

  - [Regels voor e-mail stroom (transportregels) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Voorwaarden voor de e-mail stroom regels en uitzonderingen (predikaten) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Acties voor e-mail stroom regels in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Gebruik de functie SBV om een e-mail stroom regel te maken om kopieën van gerapporteerde berichten te ontvangen

1. Ga in het Exchange-Beheercentrum naar de regels voor de **e-mail stroom** \> **Rules**.

2. Klik **op** ![ pictogram toevoegen ](../../media/ITPro-EAC-AddIcon.png) en selecteer vervolgens **een nieuwe regel maken**.

3. Configureer de volgende instellingen op de pagina **nieuwe regel** die wordt geopend:

   - **Naam**: Typ een unieke, beschrijvende naam voor de regel. BCC-berichten die naar Microsoft zijn gerapporteerd, bijvoorbeeld

   - Klik op **meer opties**.

   - **Deze regel toepassen als**: Selecteer het adres van **de ontvanger** \> **bevat een of meer van deze woorden**: Typ een van de volgende waarden in het dialoogvenster **woorden of woordgroepen opgeven** dat wordt weergegeven, klik op **Add** ![ pictogram toevoegen ](../../media/ITPro-EAC-AddIcon.png) en herhaal dit tot u alle waarden hebt ingevoerd.

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     Als u een vermelding wilt bewerken, selecteert u **Edit** deze en klikt u op ![ pictogram bewerken bewerken ](../../media/ITPro-EAC-EditIcon.png) . Als u een vermelding wilt verwijderen, selecteert u deze **en klikt u** op het ![ pictogram verwijderen ](../../media/ITPro-EAC-DeleteIcon.png) .

     Wanneer u klaar bent, klikt u op **OK**.

   - **Ga als volgt**te werk: Selecteer **geadresseerden toevoegen** \> **aan het vak BCC**. In het dialoogvenster dat wordt weergegeven, zoekt en selecteert u de geadresseerden die u wilt toevoegen. Wanneer u klaar bent, klikt u op **OK**.

4. U kunt extra keuzes maken om de regel te controleren, de regel te testen, de regel te activeren gedurende een specifieke periode en andere instellingen. U wordt aangeraden de regel te testen voordat u deze afdwingt.

5. Klik op **Opslaan** wanneer u gereed bent.

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>PowerShell gebruiken om een e-mail stroom regel te maken om kopieën van gerapporteerde berichten te ontvangen

In dit voorbeeld wordt een nieuwe e-mail stroom regel met de naam BCC-berichten gerapporteerd aan Microsoft waarmee wordt gezocht naar e-mailberichten die bij Microsoft worden gerapporteerd met behulp van de methoden die in dit onderwerp worden beschreven, en voegt u de gebruikers laura@contoso.com en julia@contoso.com toe als BCC-geadresseerden.

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

Zie [Nieuwe-Transportregel](https://docs.microsoft.com/powershell/module/exchange/new-transportrule) voor gedetailleerde syntaxis- en parameterinformatie.

## <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Voer een van de volgende stappen uit om te controleren of u een e-mail stroom regels hebt geconfigureerd om kopieën van gerapporteerde berichten te ontvangen:

- Ga in het Exchange-Beheercentrum naar **e-mail stroom** \> **regels** \> , selecteer de regel Klik op bewerkings \> pictogram **bewerken** ![ ](../../media/ITPro-EAC-EditIcon.png) en controleer de instellingen.

- In PowerShell voert u de volgende opdracht uit om de instellingen te controleren:

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- Verzend een testbericht naar een van de e-mailadressen van de rapporten en controleer de resultaten.
