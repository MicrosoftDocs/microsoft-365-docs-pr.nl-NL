---
title: Berichten handmatig verzenden naar Microsoft voor analyse
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 'U en uw gebruikers kunnen valse negatieve en fout-positieve spamberichten naar Microsoft sturen voor analyse. '
ms.openlocfilehash: f6dbd808fac54ae273c21773bf8caeabce09b7fb
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631239"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>Berichten handmatig verzenden naar Microsoft voor analyse

> [!NOTE]
> Als u een beheerder bent in een Microsoft 365-organisatie met Exchange Online-postvakken, raden we u aan de portal Inzendingen te gebruiken in het Beveiligings- & Compliance Center. Zie [Het indienen van beheerders gebruiken om vermoedelijke spam, phish, URL's en bestanden in te dienen bij Microsoft.](admin-submission.md)

Het kan frustrerend zijn wanneer gebruikers in uw organisatie ongewenste berichten (spam) of phishingberichten ontvangen in hun Postvak IN, of als ze geen legitiem e-mailbericht ontvangen omdat het is gemarkeerd als ongewenste e-mail. We verfijnen onze spamfilters voortdurend om nauwkeuriger te zijn.

U en uw gebruikers kunnen dit proces helpen door false positives (goede e-mail gemarkeerd als slecht), valse negatieven (slechte e-mail toegestaan) en phishing-berichten bij Microsoft in te dienen voor analyse.

> [!NOTE]
> Vanwege het grote aantal inzendingen dat we ontvangen, kunnen we mogelijk niet alle verzoeken om analyse beantwoorden.

## <a name="submit-false-negatives-to-microsoft"></a>Valse negatieven verzenden bij Microsoft

> [!TIP]
> In plaats van de volgende procedures te gebruiken om valse negatieven te melden, kunnen gebruikers in de webversie van Outlook en Outlook (voorheen Outlook Web App) de invoegtoepassing Berichtrapport voor Microsoft Outlook gebruiken. Zie [Invoegtoepassing Rapportbericht inschakelen](enable-the-report-message-add-in.md)voor informatie over het installeren en gebruiken van deze tool.

Als u een bericht ontvangt dat door spamfiltering is verzonden en dat als spam of phishing had moeten worden geïdentificeerd, u het bericht naar gelang van het geval indienen bij de microsoft spamanalyse- en Microsoft Phishing-analyseteams. De analisten zullen het bericht bekijken en toevoegen aan de servicebrede filters als het voldoet aan de classificatiecriteria.

1. Maak een nieuw, leeg e-mailbericht met een van de volgende ontvangers:

   - **Junk**:`junk@office365.microsoft.com`

   - **Phishing**:`phish@office365.microsoft.com`

2. Sleep en drop de ongewenste of phishing-bericht in het nieuwe bericht. Dit zal de junk of phishing-bericht op te slaan als een bijlage in het nieuwe bericht. Kopieer en plak de inhoud van het bericht niet of stuur het bericht door (we hebben het oorspronkelijke bericht nodig zodat we de berichtkoppen kunnen inspecteren).

   > [!NOTE]
   > <ul><li>U meerdere berichten toevoegen in het nieuwe bericht. Zorg ervoor dat alle berichten hetzelfde type zijn: phishing-scamberichten of ongewenste e-mailberichten.</li><li>Laat het lichaam van het nieuwe bericht leeg.</li><li>Gebruik .msg (standaardOutlook-indeling) of .eml (standaard Outlook op de webindeling) voor de bijgevoegde berichten.</li></ul>

3. Klik op **Verzenden**als u klaar bent.

> [!TIP]
> Beheerders hebben verschillende manieren om specifieke berichten te blokkeren die verkeerd worden geïdentificeerd als spam. Zie Lijsten [met geblokkeerde afzenders maken in Office 365](create-block-sender-lists-in-office-365.md)voor meer informatie.

## <a name="submit-false-positives-to-microsoft"></a>Valse positieven verzenden bij Microsoft

> [!TIP]
> In plaats van de volgende procedures te gebruiken om fout-positieven te melden, kunnen gebruikers in de webversie van Outlook en Outlook de invoegtoepassing Rapportbericht voor Microsoft Outlook gebruiken. Zie [Invoegtoepassing Rapportbericht inschakelen](enable-the-report-message-add-in.md)voor informatie over het installeren en gebruiken van deze tool.

Als een bericht ten onrechte is geïdentificeerd als spam, u het bericht indienen bij het Microsoft Spam Analysis Team. De analisten evalueren het bericht en (afhankelijk van de resultaten van de analyse) kunnen de servicebrede filters worden aangepast om het bericht door te laten gaan.

1. Maak een nieuw, leeg `not_junk@office365.microsoft.com` e-mailbericht met als ontvanger:

2. Sleep en laat het verkeerd geïdentificeerde bericht in het nieuwe bericht vallen. Hiermee wordt het verkeerd geïdentificeerde bericht opgeslagen als bijlage in het nieuwe bericht. Kopieer en plak de inhoud van het bericht niet of stuur het bericht door (we hebben het oorspronkelijke bericht nodig zodat we de berichtkoppen kunnen inspecteren).

   > [!NOTE]
   > <ul><li>U meerdere berichten toevoegen in het nieuwe bericht. Zorg ervoor dat alle berichten hetzelfde type zijn: phishingberichten of ongewenste e-mailberichten.</li><li>Laat het lichaam van het nieuwe bericht leeg.</li><li>Gebruik .msg (standaardOutlook-indeling) of .eml (standaard Outlook op de webindeling) voor de bijgevoegde berichten.</li></ul>

3. Klik op **Verzenden**als u klaar bent.

> [!TIP]
> Beheerders hebben verschillende manieren om specifieke berichten toe te staan spamfilters over te slaan. Zie Lijsten [met veilige afzenders maken in Office 365](create-safe-sender-lists-in-office-365.md)voor meer informatie.

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>Een e-mailstroomregel maken om kopieën te ontvangen van berichten die aan Microsoft worden gerapporteerd

U een regel voor e-mailstroom (ook wel een transportregel genoemd) maken die zoekt naar e-mailberichten die aan Microsoft worden gerapporteerd met behulp van de methoden die in dit onderwerp zijn beschreven, en u BCC-ontvangers configureren om kopieën van deze gerapporteerde berichten te ontvangen.

U de regel voor e-mailstroom maken in het Exchange-beheercentrum (EAC) en PowerShell (Exchange Online PowerShell voor Microsoft 365-klanten. Exchange Online Protection PowerShell voor zelfstandige EOP-klanten).

### <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U moet machtigingen in Exchange Online krijgen toegewezen voordat u deze procedures uitvoeren. U moet in het bijzonder de rol **Transportregels** toegewezen krijgen, die standaard is toegewezen aan de rollen **Organisatiebeheer,** **Compliancebeheer**en **Records Management.** Zie [Rolgroepen beheren in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)voor meer informatie .

- Zie [Exchange-beheercentrum in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center)als u de EAC in Exchange Online wilt openen.

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone Exchange Online Protection PowerShell.

- Zie de volgende onderwerpen voor meer informatie over regels voor e-mailstromen in Exchange Online en zelfstandige EOP:

  - [Regels voor e-mailstroom (transportregels) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Voorwaarden en uitzonderingen voor e-mailstroomregels (predicaten) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Acties voor e-mailstroomregel in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

### <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>De EAC gebruiken om een e-mailstroomregel te maken om kopieën van gerapporteerde berichten te ontvangen

1. Ga in de EAC naar **Mail flow** \> **Rules**.

2. Klik **op** ![](../../media/ITPro-EAC-AddIcon.png) Pictogram Toevoegen toevoegen en selecteer **vervolgens Een nieuwe regel maken**.

3. Configureer op de pagina **Nieuwe regel** die wordt geopend de volgende instellingen:

   - **Naam:** Voer een unieke, beschrijvende naam voor de regel in. Bijvoorbeeld, BCC Berichten Gerapporteerd aan Microsoft.

   - Klik **op Meer opties**.

   - **Deze regel toepassen als**: **Selecteer Het geadresseerdeadres** \> **bevat een van deze woorden:** Voer in het dialoogvenster](../../media/ITPro-EAC-AddIcon.png)Woorden of zinnen **opgeven** dat wordt weergegeven een van de volgende waarden in, klik op Pictogram **toevoegen** ![en herhaal totdat u alle waarden hebt ingevoerd.

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     Als u een item wilt **Edit** ![bewerken, selecteert](../../media/ITPro-EAC-EditIcon.png)u het item en klikt u op pictogram Bewerken bewerken . Als u een item wilt **Remove** ![verwijderen,](../../media/ITPro-EAC-DeleteIcon.png)selecteert u het item en klikt u op Pictogram Verwijderen .

     Klik op **OK**als u klaar bent.

   - **Ga als volgt**te werk : Selecteer **Geadresseerden** \> toevoegen **aan het vak BCC**. Zoek en selecteer in het dialoogvenster dat wordt weergegeven de geadresseerden die u wilt toevoegen. Klik op **OK**als u klaar bent.

4. U extra selecties maken om de regel te controleren, de regel te testen, de regel te activeren gedurende een bepaalde periode en andere instellingen. We raden u aan de regel te testen voordat u deze afdwingt.

5. Klik op **Opslaan** wanneer u gereed bent.

### <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>PowerShell gebruiken om een e-mailstroomregel te maken om kopieën van gerapporteerde berichten te ontvangen

In dit voorbeeld wordt een nieuwe regel voor e-mailstroom gemaakt met de naam BCC-berichten die aan Microsoft worden gerapporteerd en die wordt gerapporteerd met behulp van de methoden die in dit onderwerp zijn beschreven, en worden de gebruikers laura@contoso.com en julia@contoso.com toegevoegd als BCC-ontvangers.

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

Zie [Nieuwe-Transportregel](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule) voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Ga een van de volgende stappen uit om te controleren of u een e-mailstroomregels hebt geconfigureerd om kopieën van gerapporteerde berichten te ontvangen:

- Ga in de EAC naar **EAC-regels** \> **Rules** \> en selecteer](../../media/ITPro-EAC-EditIcon.png)de regel \> klik op Pictogram Bewerken **bewerken** ![en controleer de instellingen.

- Voer in PowerShell de volgende opdracht uit om de instellingen te verifiëren:

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- Stuur een testbericht naar een van de rapportage-e-mailadressen en verifieer de resultaten.
