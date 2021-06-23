---
title: Beleidsregels Safe Koppelingen instellen in Microsoft Defender voor Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: Beheerders kunnen informatie krijgen over het weergeven, maken, wijzigen en verwijderen van Safe Koppelingenbeleid en algemene Safe Koppelingen-instellingen in Microsoft Defender voor Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d1e0257fd124a53b2191ad8025ce42dc13a2e23e
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096766"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a>Beleidsregels Safe Koppelingen instellen in Microsoft Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Dit artikel is bedoeld voor zakelijke klanten die [Microsoft Defender voor Office 365](defender-for-office-365.md) hebben. Als u een thuisgebruiker bent die informatie zoekt over Safelinks in Outlook, gaat u naar [Advanced Outlook.com-beveiliging.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)

Safe Koppelingen in [Microsoft Defender voor Office 365](defender-for-office-365.md) biedt URL-scan van binnenkomende e-mailberichten in de e-mailstroom en het tijdstip van klikverificatie van URL's en koppelingen in e-mailberichten en op andere locaties. Zie Koppelingen in Microsoft Defender voor Safe voor [meer Office 365.](safe-links.md)

Er is geen ingebouwd of standaardkoppelingsbeleid Safe koppelingen. Als u Safe koppelingen van URL's wilt scannen, moet u een of meer Safe Koppelingenbeleid maken, zoals in dit artikel wordt beschreven.

> [!NOTE]
>
> U configureert de algemene instellingen voor Safe koppelingen **buiten** Safe koppelingenbeleid. Zie Algemene instellingen [configureren voor Safe koppelingen in Microsoft Defender](configure-global-settings-for-safe-links.md)voor Office 365.
>
> Beheerders moeten rekening houden met de verschillende configuratie-instellingen voor Safe koppelingen. Een van de beschikbare opties is het opnemen van gebruikersgegevens in Safe Koppelingen. Met deze functie kunnen *Beveiligingsops-teams* mogelijke gebruikerscompromitteerden onderzoeken, corrigerende actie ondernemen en dure inbreuken beperken.

U kunt Safe Koppelingen-beleid configureren in de Microsoft 365 Defender-portal of in PowerShell (Exchange Online PowerShell voor in aanmerking komende Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken, maar met Microsoft Defender voor Office 365-invoegabonnementen).

De basiselementen van een Safe koppelingenbeleid zijn:

- Het beleid voor veilige **koppelingen:** schakel Safe Koppelingenbeveiliging in, schakel realtime URL-scan in, geef op of het scannen in realtime moet worden voltooid voordat het bericht wordt verzonden, schakel het scannen van interne berichten in, geef op of gebruikers klikken op URL's moeten bijhouden en geef op of gebruikers mogen klikken op de oorspronkelijke URL.
- **De regel veilige koppelingen:** hiermee geeft u de prioriteits- en geadresseerdefilters op (op wie het beleid van toepassing is).

Het verschil tussen deze twee elementen is niet duidelijk wanneer u het beleid Safe Koppelingen in de Microsoft 365 Defender beheren:

- Wanneer u een Safe koppelingenbeleid maakt, maakt u tegelijkertijd een veilige koppelingsregel en het bijbehorende beleid voor veilige koppelingen met dezelfde naam voor beide.
- Wanneer u een Safe koppelingenbeleid wijzigt, wijzigen instellingen met betrekking tot de naam, prioriteit, ingeschakeld of uitgeschakeld en geadresseerdefilters de regel voor veilige koppelingen. Alle andere instellingen wijzigen het beleid voor gekoppelde veilige koppelingen.
- Wanneer u een Safe koppelingenbeleid verwijdert, worden de regel voor veilige koppelingen en het bijbehorende beleid voor veilige koppelingen verwijderd.

In Exchange Online PowerShell of standalone EOP PowerShell beheert u het beleid en de regel afzonderlijk. Zie de sectie Gebruik Exchange Online PowerShell of zelfstandige [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) voor het configureren Safe koppelingenbeleid verderop in dit artikel voor meer informatie.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent de Microsoft 365 Defender-portal bij <https://security.microsoft.com/>. Als u rechtstreeks naar de pagina Safe **koppelingen wilt** gaan, gebruikt <https://security.microsoft.com/safelinksv2> u .

- Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- U moet machtigingen hebben toegewezen voordat u de procedures in dit artikel kunt uitvoeren:
  - Als u beleidsregels voor Safe-koppelingen wilt maken, wijzigen en  verwijderen,  moet u lid zijn van de rollengroepen Organisatiebeheer of Beveiligingsbeheerder in de Microsoft 365 Defender-portal en lid zijn van de rollengroep Organisatiebeheer in Exchange Online.  
  - Voor alleen-lezen toegang tot Safe koppelingenbeleid, moet u lid  zijn van de rollengroepen Globale lezer of **Beveiligingslezer.**

  Zie Machtigingen [in de](permissions-microsoft-365-security-center.md) Microsoft 365 Defender portal en [Machtigingen in](/exchange/permissions-exo/permissions-exo)Exchange Online.

  > [!NOTE]
  >
  > - Gebruikers toevoegen aan de bijbehorende Azure Active Directory rol in de Microsoft 365-beheercentrum geeft gebruikers de vereiste machtigingen in de _Microsoft 365 Defender-portal_ en machtigingen voor andere functies in Microsoft 365. Raadpleeg [Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.
  . - De **rollengroep Alleen-weergeven voor** organisatiebeheer [in](/Exchange/permissions-exo/permissions-exo#role-groups) Exchange Online biedt ook alleen-lezen toegang tot de functie.

- Zie voor onze aanbevolen instellingen voor Safe [Koppelingenbeleid Safe Beleidsinstellingen voor koppelingen.](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)

- Maximaal 30 minuten toestaan dat een nieuw of bijgewerkt beleid wordt toegepast.

- [Er worden voortdurend nieuwe functies toegevoegd aan Microsoft Defender voor Office 365.](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365) Als er nieuwe functies worden toegevoegd, moet u mogelijk uw bestaande Safe koppelingenbeleid aanpassen.

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-links-policies"></a>Gebruik de Microsoft 365 Defender portal om Safe koppelingenbeleid te maken

Als u een aangepast Safe koppelingenbeleid maakt in de Microsoft 365 Defender portal, worden de regels voor veilige koppelingen en het bijbehorende beleid voor veilige koppelingen tegelijk gemaakt met dezelfde naam voor beide.

1. Ga in Microsoft 365 Defender portal naar De sectie **Beleidsregels & beleidsregels** voor bedreigingsbeleid \>  \>  \> **Safe Koppelingen.**

2. Klik op **Safe pagina Koppelingen** op Pictogram Maken ![ ](../../media/m365-cc-sc-create-icon.png) **maken.**

3. De **wizard Nieuw Safe koppelingen wordt** geopend. Configureer **op de pagina** Naam uw beleid de volgende instellingen:

   - **Naam**: een unieke beschrijvende naam voor het beleid.
   - **Beschrijving**: voer een optionele beschrijving in voor het beleid.

   Wanneer u gereed bent, klikt u op **Volgende**.

4. Identificeer op **de pagina Gebruikers** en domeinen die wordt weergegeven de interne geadresseerden op wie het beleid van toepassing is (voorwaarden voor geadresseerden):
   - **Gebruikers**: de opgegeven postvakken, e-mailgebruikers or e-mailcontactpersonen binnen uw organisatie.
   - **Groepen**: de opgegeven distributiegroepen, beveiligingsgroepen met e-mail of Microsoft 365-groepen binnen uw organisatie.
   - **Domeinen**: alle geadresseerden in de opgegeven [geaccepteerde domeinen](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) binnen uw organisatie.

   Klik in het juiste vak, begin een waarde te typen en selecteer de gewenste waarde in de resultaten. Herhaal deze stap zo vaak als nodig is. Als u een bestaande waarde wilt verwijderen, klikt u op verwijderen ![Pictogram Verwijderen](../../media/m365-cc-sc-remove-selection-icon.png) naast de waarde.

   Voor gebruikers of groepen kunt u de meeste id's (naam, weergavenaam, alias, e-mailadres, accountnaam, enzovoort) gebruiken, maar de bijbehorende weergavenaam wordt weergegeven in de resultaten. Voer voor gebruikers een enkel sterretje (\*) in om alle beschikbare waarden weer te geven.

   Meerdere waarden in dezelfde voorwaarde: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_). Verschillende voorwaarden: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).

   - **Deze gebruikers, groepen** en domeinen uitsluiten: Als u uitzonderingen wilt toevoegen voor de interne geadresseerden waar het beleid op van toepassing is (uitzonderingen voor geadresseerden), selecteert u deze optie en configureert u de uitzonderingen. De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.

   Wanneer u gereed bent, klikt u op **Volgende**.

5. Configureer **de volgende** instellingen op de pagina Beveiligingsinstellingen die wordt weergegeven:
   - **Selecteer de actie voor onbekende potentieel schadelijke URL's in** berichten: Selecteer **Aan** om Safe koppelingen in te stellen voor koppelingen in e-mailberichten. Als u deze instelling in wilt stellen, zijn de volgende instellingen beschikbaar:
     - **Realtime URL-scan toepassen** op verdachte koppelingen en koppelingen die naar bestanden wijzen: Selecteer deze optie om het scannen van koppelingen in e-mailberichten in realtime in te stellen. Als u deze instelling in de volgende instelling in zet, is deze beschikbaar:
       - **Wacht totdat URL-scannen is** voltooid voordat u het bericht bezorgt: Selecteer deze optie om te wachten totdat het scannen van url's in realtime is voltooid voordat het bericht wordt weergegeven.
     - **De Safe koppelingen** toepassen op e-mailberichten die binnen de organisatie zijn verzonden: Selecteer deze optie om het Safe Koppelingen-beleid toe te passen op berichten tussen interne afzenders en interne geadresseerden.
   - Selecteer de actie voor onbekende of potentieel schadelijke **URL's** in Microsoft Teams : Selecteer **Aan** om de beveiliging van koppelingen in te Safe koppelingen in Teams.
   - **Gebruikersklikken niet bijhouden:** laat deze instelling niet geselecteerd om het bijhouden van gebruikersklikken op URL's in e-mailberichten in te stellen.
   - **Gebruikers mogen niet doorklikken** naar de oorspronkelijke URL: Selecteer deze optie om te blokkeren dat gebruikers doorklikken naar de oorspronkelijke URL op [waarschuwingspagina's.](safe-links.md#warning-pages-from-safe-links)
   - **De volgende URL's niet** opnieuw schrijven: Hiermee krijgt u toegang tot de opgegeven URL's die anders door Safe worden geblokkeerd.

     Typ in het vak de URL of waarde die u wilt gebruiken en klik vervolgens op **Toevoegen.** Herhaal deze stap zo vaak als nodig is.

     Als u een bestaand item wilt verwijderen, klikt u op ![Pictogram Verwijderen](../../media/m365-cc-sc-remove-selection-icon.png) naast het item.

     Zie De syntaxis van de vermelding voor de lijst 'De volgende URL's niet opnieuw [schrijven'.](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)

   Zie voor meer informatie over deze [instellingen de instellingen Safe Koppelingen](safe-links.md#safe-links-settings-for-email-messages) voor e-mailberichten en Safe Koppelingen voor [Microsoft Teams.](safe-links.md#safe-links-settings-for-microsoft-teams)

   Zie voor meer informatie over de aanbevolen waarden voor standaard- en strikte beleidsinstellingen [Safe Beleidsinstellingen koppelingen.](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)

   Wanneer je klaar bent, klik je op **Volgende**.

6. Selecteer op **de** pagina Melding die wordt weergegeven een van de volgende waarden voor Hoe wilt u uw gebruikers **op de hoogte stellen?**:
   - **De standaardmeldingstekst gebruiken**
   - **Aangepaste meldingstekst gebruiken:** als u deze waarde selecteert (de lengte mag niet groter zijn dan 200 tekens), worden de volgende instellingen weergegeven:
     - **Gebruik Microsoft Translator voor automatische lokalisatie**
     - **Aangepaste meldingstekst:** Voer de aangepaste meldingstekst in dit vak in.

   Wanneer je klaar bent, klik je op **Volgende**.

7. Controleer uw instellingen op de pagina **Controleren** die wordt weergegeven. U kunt in elke sectie **Bewerken** selecteren om de instellingen in de sectie te wijzigen. U kunt ook op **Terug** klikken of de specifieke pagina in de wizard selecteren.

   Wanneer u klaar bent, klikt u op **Verzenden.**

8. Klik op de bevestigingspagina die wordt weergegeven op **Gereed**.

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-links-policies"></a>Gebruik de Microsoft 365 Defender portal om de Safe koppelingen weer te Safe

1. Ga in Microsoft 365 Defender portal naar De sectie **Beleidsregels & beleidsregels** voor bedreigingsbeleid \>  \>  \> **Safe Koppelingen.**

2. Op de **Safe pagina Koppelingen** worden de volgende eigenschappen weergegeven in de lijst met Safe Koppelingenbeleid:
   - **Naam**
   - **Status**
   - **Prioriteit**

3. Wanneer u een beleid selecteert door op de naam te klikken, worden de beleidsinstellingen weergegeven in een flyout.

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-links-policies"></a>Gebruik de Microsoft 365 Defender portal om het beleid voor koppelingen Safe wijzigen

1. Ga in Microsoft 365 Defender portal naar De sectie **Beleidsregels & beleidsregels** voor bedreigingsbeleid \>  \>  \> **Safe Koppelingen.**

2. Selecteer op **Safe pagina Koppelingen** een beleid in de lijst door op de naam te klikken.

3. U kunt in de flyout met beleidsdetails in elke sectie de optie **Bewerken** selecteren om de instellingen in de sectie te wijzigen. Zie de vorige portal De [](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies) portal Microsoft 365 Defender gebruiken om Safe koppelingenbeleid te maken in dit artikel voor meer informatie over de instellingen.  

Zie de volgende secties als u een beleid wilt in- of uitschakelen of de beleidsprioriteitsvolgorde wilt instellen.

### <a name="enable-or-disable-safe-links-policies"></a>Beleidsregels voor koppelingen in- Safe uitschakelen

1. Ga in Microsoft 365 Defender portal naar **E-mail & samenwerkingsbeleid** & \> **beleidsregels** voor bedreigingsbeleidsregels Safe \>  \>  \> **Koppelingen.**

2. Selecteer op **Safe pagina Koppelingen** een beleid in de lijst door op de naam te klikken.

3. Boven aan de flyout met beleidsdetails die wordt weergegeven, ziet u een van de volgende waarden:
   - **Beleid uitgeschakeld**: als u het beleid wilt inschakelen, klikt u op ![Pictogram inschakelen](../../media/m365-cc-sc-turn-on-off-icon.png) **Inschakelen** .
   - **Beleid ingeschakeld**: als u het beleid wilt uitschakelen, klikt u op ![Pictogram uitschakelen](../../media/m365-cc-sc-turn-on-off-icon.png) **Uitschakelen**.

4. Klik in het bevestigingsvenster dat wordt weergegeven op **Inschakelen** of **Uitschakelen**.

5. Klik in de flyout met beleidsdetails op **Sluiten**.

Op de hoofdbeleidspagina wordt de waarde **Status** van het beleid weergegeven als **Ingeschakeld** of **Uitgeschakeld**.

### <a name="set-the-priority-of-safe-links-policies"></a>De prioriteit instellen van Safe koppelingenbeleid

Standaard krijgen Safe koppelingen een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere beleidsregels hebben een lagere prioriteit dan oudere beleidsregels). Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit). Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.

Als u de prioriteit van een beleid wilt wijzigen, klikt u op **Prioriteit verhogen** of **Prioriteit verlagen** in de eigenschappen van het beleid (u kunt het **Prioriteitsnummer** niet rechtstreeks wijzigen in de Microsoft 365 Defender-portal). Het wijzigen van de prioriteit van een beleid is alleen zinvol als u meerdere beleidsregels hebt.

**Opmerking**:

- In de Microsoft 365 Defender portal kunt u alleen de prioriteit van het Safe koppelingen wijzigen nadat u deze hebt gemaakt. In PowerShell kunt u de standaardprioriteit overschrijven wanneer u de regel veilige koppelingen maakt (die van invloed kan zijn op de prioriteit van bestaande regels).
- Safe Koppelingenbeleid wordt verwerkt in de volgorde waarin ze worden weergegeven (het eerste beleid heeft de **waarde** Prioriteit 0). Voor meer informatie over de prioriteitvolgorde en het evalueren en toepassen van een beleid, raadpleegt u [volgorde en prioriteit van e-mailbeveiliging](how-policies-and-protections-are-combined.md).

1. Ga in Microsoft 365 Defender portal naar **E-mail & samenwerkingsbeleid** & \> **beleidsregels** voor bedreigingsbeleidsregels Safe \>  \>  \> **Koppelingen.**

2. Selecteer op **Safe pagina Koppelingen** een beleid in de lijst door op de naam te klikken.

3. Boven aan de flyout met beleidsgegevens die wordt weergegeven, ziet u **Prioriteit verhogen** of **Prioriteit verlagen** op basis van de huidige prioriteitswaarde en het aantal aangepaste beleidsregels:
   - Het beleid met **prioriteitswaarde** **0** heeft alleen de **optie Prioriteit verlagen** beschikbaar.
   - Het beleid met de laagste **prioriteitswaarde** (bijvoorbeeld **3)** heeft alleen de optie **Prioriteit verhogen** beschikbaar.
   - Als u drie of meer beleidsregels hebt, hebben de  beleidsregels  tussen de waarden met de hoogste en laagste prioriteit zowel de opties Prioriteit verhogen als Prioriteit verlagen beschikbaar.

   Klik op het ![pictogram Prioriteit verhogen](../../media/m365-cc-sc-increase-icon.png) **Prioriteit verhogen** of ![Pictogram Prioriteit verlagen](../../media/m365-cc-sc-decrease-icon.png) **Prioriteit verlagen** om de **Prioriteitswaarde** te wijzigen.

4. Wanneer u klaar bent, klikt u in de flyout met beleidsdetails op **Sluiten**.

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-links-policies"></a>Gebruik de Microsoft 365 Defender portal om het beleid voor koppelingen Safe verwijderen

1. Ga in Microsoft 365 Defender portal naar **E-mail & samenwerkingsbeleid** & \> **beleidsregels** voor bedreigingsbeleidsregels Safe \>  \>  \> **Koppelingen.**

2. Selecteer op **Safe pagina Koppelingen** een beleid in de lijst door op de naam te klikken. Klik boven aan de flyout met beleidsdetails die wordt weergegeven, op het ![pictogram Meer acties](../../media/m365-cc-sc-more-actions-icon.png) **Meer acties** \> ![Pictogram Beleid verwijderen](../../media/m365-cc-sc-delete-icon.png) **Beleid verwijderen**.

3. Klik in het bevestigingsvenster dat wordt weergegeven op **Ja**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a>Gebruik Exchange Online PowerShell of zelfstandige EOP PowerShell om Safe koppelingenbeleid te configureren

Zoals eerder beschreven, Safe beleid voor koppelingen bestaat uit een beleid voor veilige koppelingen en een regel voor veilige koppelingen.

In PowerShell is het verschil tussen beleidsregels voor veilige koppelingen en regels voor veilige koppelingen duidelijk. U beheert beleidsregels voor veilige koppelingen met behulp van **\* de cmdlets -SafeLinksPolicy** en u beheert regels voor veilige koppelingen met behulp van **\* de cmdlets -SafeLinksRule.**

- In PowerShell maakt u eerst het beleid voor veilige koppelingen en vervolgens maakt u de regel voor veilige koppelingen waarin het beleid wordt aangegeven waar de regel op van toepassing is.
- In PowerShell wijzigt u de instellingen in het beleid voor veilige koppelingen en de regel voor veilige koppelingen afzonderlijk.
- Wanneer u een beleid voor veilige koppelingen uit PowerShell verwijdert, wordt de bijbehorende regel voor veilige koppelingen niet automatisch verwijderd en omgekeerd.

### <a name="use-powershell-to-create-safe-links-policies"></a>PowerShell gebruiken om Safe koppelingen te maken

Het maken Safe beleid voor koppelingen in PowerShell is een proces in twee stappen:

1. Maak het beleid voor veilige koppelingen.
2. Maak de regel veilige koppelingen die het beleid voor veilige koppelingen aangeeft waar de regel op van toepassing is.

> [!NOTE]
>
> - U kunt een nieuwe regel voor veilige koppelingen maken en er een bestaand, niet-verbonden beleid voor veilige koppelingen aan toewijzen. Een veilige koppelingsregel kan niet worden gekoppeld aan meer dan één beleid voor veilige koppelingen.
>
> - U kunt de volgende instellingen configureren voor nieuwe beleidsregels voor veilige koppelingen in PowerShell die pas beschikbaar zijn in de Microsoft 365 Defender portal nadat u het beleid hebt gemaakt:
>   - Het nieuwe beleid maken als uitgeschakeld (_ingeschakeld op_ `$false` de cmdlet **Nieuw-SafeLinksRule).**
>   - Stel de prioriteit van het beleid in tijdens het maken _(Prioriteit)_ _\<Number\>_ op de cmdlet **Nieuw-SafeLinksRule).**
>
> - Een nieuw beleid voor veilige koppelingen dat u in PowerShell maakt, is pas zichtbaar in de Microsoft 365 Defender portal als u het beleid aan een regel voor veilige koppelingen toewijst.

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a>Stap 1: PowerShell gebruiken om een beleid voor veilige koppelingen te maken

Gebruik de volgende syntaxis om een beleid voor veilige koppelingen te maken:

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
>
> - Zie De [syntaxis](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)van de vermelding voor de volgende URL's niet opnieuw schrijven voor meer informatie over de syntaxis van de invoer die u wilt gebruiken voor de parameter _DoNotRewriteUrls._
>
> - Zie de sectie [PowerShell](#use-powershell-to-modify-safe-links-policies) gebruiken om beleidsregels voor veilige koppelingen te wijzigen verderop in dit artikel voor aanvullende syntaxis die u kunt gebruiken voor de parameter _DoNotRewriteUrls_ wanneer u bestaande beleidsregels voor veilige koppelingen wijzigt met de cmdlet **Set-SafeLinksPolicy.**

In dit voorbeeld wordt een beleid voor veilige koppelingen met de naam Contoso All gemaakt met de volgende waarden:

- Schakel URL's scannen en herschrijven in e-mailberichten in.
- URL's scannen in Teams in (alleen TAP Preview).
- Schakel realtime scannen in van geklikte URL's, inclusief geklikte koppelingen die naar bestanden wijzen.
- Wacht totdat URL-scannen is voltooid voordat u het bericht bezorgt.
- Schakel URL's scannen en herschrijven in voor interne berichten.
- Gebruikersklikken bijhouden met betrekking tot Safe Koppelingenbeveiliging (we gebruiken de parameter _DoNotTrackUserClicks_ niet en de standaardwaarde is $false, wat betekent dat gebruikersklikken worden bijgepuurd).
- Gebruikers mogen niet doorklikken naar de oorspronkelijke URL.

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

Zie [Nieuw-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy)voor gedetailleerde syntaxis- en parametergegevens.

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a>Stap 2: PowerShell gebruiken om een regel voor veilige koppelingen te maken

Als u een regel voor veilige koppelingen wilt maken, gebruikt u de volgende syntaxis:

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

In dit voorbeeld wordt een veilige koppelingsregel met de naam Contoso All gemaakt met de volgende voorwaarden:

- De regel is gekoppeld aan het beleid voor veilige koppelingen met de naam Contoso All.
- De regel is van toepassing op alle geadresseerden in het contoso.com domein.
- Omdat we de parameter Prioriteit niet _gebruiken,_ wordt de standaardprioriteit gebruikt.
- De regel is ingeschakeld (we gebruiken de parameter _Ingeschakeld_ niet en de standaardwaarde is `$true` ).

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Zie [Nieuw-SafeLinksRule](/powershell/module/exchange/new-safelinksrule)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-view-safe-links-policies"></a>PowerShell gebruiken om beleidsregels voor veilige koppelingen weer te geven

Gebruik de volgende syntaxis als u bestaand beleid voor veilige koppelingen wilt weergeven:

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In dit voorbeeld wordt een overzichtslijst met alle beleidsregels voor veilige koppelingen weergegeven.

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

Dit voorbeeld retourneert gedetailleerde informatie voor het beleid voor veilige koppelingen met de naam Contoso Executives.

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

Zie [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-view-safe-links-rules"></a>PowerShell gebruiken om regels voor veilige koppelingen weer te geven

Als u bestaande regels voor veilige koppelingen wilt weergeven, gebruikt u de volgende syntaxis:

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In dit voorbeeld wordt een overzichtslijst met alle regels voor veilige koppelingen weergegeven.

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

Voer de volgende opdrachten uit om de lijst te filteren op ingeschakelde en uitgeschakelde regels:

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

Dit voorbeeld retourneert gedetailleerde informatie voor de regel voor veilige koppelingen met de naam Contoso Executives.

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

Zie [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-modify-safe-links-policies"></a>PowerShell gebruiken om beleidsregels voor veilige koppelingen te wijzigen

U kunt de naam van een beleid voor veilige koppelingen niet wijzigen in PowerShell (de cmdlet **Set-SafeLinksPolicy** heeft geen _naamparameter)._ Wanneer u de naam van een Safe koppelingenbeleid in de Microsoft 365 Defender portal wijzigt, wijzigt u alleen de naam van de regel voor veilige _koppelingen._

De enige extra overweging voor het wijzigen van beleidsregels voor veilige koppelingen in PowerShell is de beschikbare syntaxis voor de parameter _DoNotRewriteUrls_ (de lijst 'De volgende URL's niet [herschrijven'):](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- Als u waarden wilt toevoegen die bestaande vermeldingen vervangen, gebruikt u de volgende syntaxis: `"Entry1","Entry2,..."EntryN"` .
- Als u waarden wilt toevoegen of verwijderen zonder dat dit van invloed is op andere bestaande vermeldingen, gebruikt u de volgende syntaxis: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`

Anders zijn dezelfde instellingen beschikbaar wanneer u een beleid voor veilige koppelingen maakt, zoals beschreven in stap [1: PowerShell](#step-1-use-powershell-to-create-a-safe-links-policy) gebruiken om eerder in dit artikel een beleidssectie voor veilige koppelingen te maken.

Als u een beleid voor veilige koppelingen wilt wijzigen, gebruikt u de volgende syntaxis:

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

Zie [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-modify-safe-links-rules"></a>PowerShell gebruiken om regels voor veilige koppelingen te wijzigen

De enige instelling die niet beschikbaar is wanneer u een regel voor veilige koppelingen in PowerShell wijzigt, is de _parameter_ Ingeschakeld waarmee u een uitgeschakelde regel kunt maken. Zie de volgende sectie als u bestaande regels voor veilige koppelingen wilt in- of uitschakelen.

Anders zijn dezelfde instellingen beschikbaar wanneer u een regel maakt zoals beschreven in stap [2: PowerShell](#step-2-use-powershell-to-create-a-safe-links-rule) gebruiken om eerder in dit artikel een sectie met veilige koppelingen te maken.

Als u een regel voor veilige koppelingen wilt wijzigen, gebruikt u de volgende syntaxis:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

Zie [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a>PowerShell gebruiken om regels voor veilige koppelingen in of uit te schakelen

Als u een regel voor veilige koppelingen in PowerShell in- of uitschakelen, wordt het hele Safe-koppelingenbeleid (de regel voor veilige koppelingen en het toegewezen beleid voor veilige koppelingen) in- of uitgeschakeld.

Als u een regel voor veilige koppelingen in PowerShell wilt in- of uitschakelen, gebruikt u de volgende syntaxis:

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

In dit voorbeeld wordt de regel voor veilige koppelingen met de naam Marketingafdeling uitgeschakeld.

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

In dit voorbeeld wordt dezelfde regel ingeschakeld.

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

Zie Enable-SafeLinksRule and Disable-SafeLinksRule [(Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule)](/powershell/module/exchange/disable-safelinksrule)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a>PowerShell gebruiken om de prioriteit van regels voor veilige koppelingen in te stellen

De hoogste prioriteit die u in kunt stellen op een regel is 0. De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels. Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken. Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels. Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.

Als u de prioriteit van een regel voor veilige koppelingen in PowerShell wilt instellen, gebruikt u de volgende syntaxis:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2. Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> Als u de prioriteit van een nieuwe regel wilt instellen wanneer u deze maakt, gebruikt u in plaats daarvan de parameter _Prioriteit_ op de **cmdlet Nieuw-SafeLinksRule.**

Zie [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-remove-safe-links-policies"></a>PowerShell gebruiken om beleidsregels voor veilige koppelingen te verwijderen

Wanneer u PowerShell gebruikt om een beleid voor veilige koppelingen te verwijderen, wordt de bijbehorende regel voor veilige koppelingen niet verwijderd.

Als u een beleid voor veilige koppelingen in PowerShell wilt verwijderen, gebruikt u de volgende syntaxis:

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

In dit voorbeeld wordt het beleid voor veilige koppelingen met de naam Marketingafdeling verwijderd.

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

Zie [Remove-SafeLinksPolicy (Verwijderen-SafeLinksPolicy)](/powershell/module/exchange/remove-safelinkspolicy)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-remove-safe-links-rules"></a>PowerShell gebruiken om regels voor veilige koppelingen te verwijderen

Wanneer u PowerShell gebruikt om een veilige koppelingsregel te verwijderen, wordt het bijbehorende beleid voor veilige koppelingen niet verwijderd.

Als u een regel voor veilige koppelingen in PowerShell wilt verwijderen, gebruikt u de volgende syntaxis:

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

In dit voorbeeld wordt de regel voor veilige koppelingen met de naam Marketingafdeling verwijderd.

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

Zie [Remove-SafeLinksRule voor](/powershell/module/exchange/remove-safelinksrule)gedetailleerde syntaxis- en parametergegevens.

Als u wilt controleren Safe koppelingen berichten scannen, controleert u de beschikbare Microsoft Defender voor Office 365 rapporten. Zie Rapporten weergeven voor [Defender](view-reports-for-mdo.md) voor Office 365 En Verkenner gebruiken in de [Microsoft 365 Defender portal voor meer informatie.](threat-explorer.md)

## <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Als u wilt controleren of u beleidsregels voor koppelingen hebt gemaakt, gewijzigd of Safe hebt verwijderd, gaat u als volgt te werk:

- Ga in Microsoft 365 Defender portal naar **Beleidsregels &** \> **bedreigingsbeleid** \> **Safe Koppelingen.** Controleer de lijst met beleidsregels, de **statuswaarden** en de **prioriteitswaarden.** Als u meer details wilt weergeven, selecteert u het beleid in de lijst en bekijkt u de details in de fly-out.

- Vervang Exchange Online PowerShell of Exchange Online Protection PowerShell door de naam van het beleid of de regel, voer de volgende opdracht uit en controleer \<Name\> de instellingen:

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
