---
title: Gebruikerslabels in Microsoft Defender voor Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 04/21/2021
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe u specifieke groepen gebruikers kunt identificeren met gebruikerslabels in Microsoft Defender voor Office 365 plan 2. Tagfiltering is beschikbaar in waarschuwingen, rapporten en onderzoeken in Microsoft Defender voor Office 365 om snel de gelabelde gebruikers te identificeren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3ac53891e0eb106ab3681251cc4cb8c969b51f8a
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083114"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a>Gebruikerslabels in Microsoft Defender voor Office 365

> [!NOTE]
> De functie gebruikerslabels is beschikbaar in Preview, is niet voor iedereen beschikbaar en kan worden gewijzigd. Voor meer informatie over de releaseplanning raadpleegt u [de Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).

Gebruikerslabels zijn id's voor specifieke groepen gebruikers in [Microsoft Defender voor Office 365.](defender-for-office-365.md) Er zijn twee typen gebruikerslabels:

- **Systeemlabels:** Momenteel is [Prioriteitsaccounts](../../admin/setup/priority-accounts.md) het enige type systeemlabel.
- **Aangepaste tags:** u maakt deze gebruikerslabels zelf.

Als uw organisatie Defender voor Office 365 abonnement 2 (inbegrepen in uw abonnement of als een invoegvoeggebruik) heeft, kunt u naast het gebruik van de tag prioriteitsaccounts ook aangepaste gebruikerslabels maken.

> [!NOTE]
> Momenteel kunt u alleen gebruikerslabels toepassen op postvakgebruikers.

Nadat u systeemlabels of aangepaste tags op gebruikers hebt toegepast, kunt u deze tags gebruiken als filters in waarschuwingen, rapporten en onderzoeken:

- [Waarschuwingen](alerts.md)
- [Aangepast waarschuwingsbeleid](../../compliance/alert-policies.md#viewing-alerts)
- [Threat Explorer en realtime detecties](threat-explorer.md)
- [Entiteitspagina van e-mail](mdo-email-entity-page.md#other-innovations)
- [Statusrapport bedreigingsbeveiliging](view-email-security-reports.md#threat-protection-status-report)
- [Campagneweergaven](campaigns.md)
- Voor prioriteitsaccounts kunt u het rapport [E-mailproblemen voor prioriteitsaccounts](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) gebruiken in Exchange beheercentrum (EAC).

In dit artikel wordt uitgelegd hoe u gebruikerslabels configureert in de Microsoft 365 Defender portal. Er zijn geen cmdlets in Microsoft 365 Defender portal om gebruikerslabels te beheren.

Zie Beveiligingsaanbevelingen voor [prioriteitsaccounts in](security-recommendations-for-priority-accounts.md)Microsoft 365.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent de Microsoft 365 Defender-portal bij <https://security.microsoft.com/>. Als u rechtstreeks naar de pagina **Gebruikerslabels wilt** gaan, opent u <https://security.microsoft.com/securitysettings/userTags> .

- U moet machtigingen krijgen toegewezen in de Microsoft 365 Defender portal voordat u de procedures in dit artikel kunt uitvoeren:
  - Als u gebruikerslabels wilt maken, wijzigen en verwijderen, moet  u lid zijn van de rollengroepen **Organisatiebeheer** of Beveiligingsbeheerder.
  - Als u leden wilt toevoegen en verwijderen uit bestaande gebruikerslabels, moet u lid zijn van de rollengroepen Organisatiebeheer, **Beveiligingsbeheerder** of Beveiligingsoperator 
  - Voor alleen-lezen toegang tot gebruikerslabels moet u lid zijn van de rollengroepen **Globale** lezer of **Beveiligingslezer.**

  Zie [Machtigingen in de Microsoft 365 Defender-portal](permissions-microsoft-365-security-center.md) voor meer informatie.

  > [!NOTE]
  >
  > - Gebruikers toevoegen aan de bijbehorende Azure Active Directory rol in de Microsoft 365-beheercentrum geeft gebruikers de vereiste machtigingen in de _Microsoft 365 Defender-portal_ en machtigingen voor andere functies in Microsoft 365. Raadpleeg [Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.
  >
  > - Gebruikerslabelbeheer wordt beheerd door de rollen **Tag Reader** en **Tag Manager.**

- U kunt ook prioriteitsaccounts in de Microsoft 365-beheercentrum. Zie Prioriteitsaccounts beheren [en controleren voor instructies.](../../admin/setup/priority-accounts.md)

- Zie dit onderwerp voor informatie over het _beveiligen_ van bevoorrechte accounts [(beheerdersaccounts).](/azure/architecture/framework/security/critical-impact-accounts)

## <a name="use-the-microsoft-365-defender-portal-to-create-user-tags"></a>Gebruik de Microsoft 365 Defender portal om gebruikerslabels te maken

1. Ga in Microsoft 365 Defender portal naar  Instellingen \> **e-mail & samenwerking** \> **Gebruikerslabels**.

2. Klik op **de pagina Gebruikerslabels** op ![ Tagpictogram maken Tag ](../../media/m365-cc-sc-create-icon.png) **maken.**

3. De **wizard Tag maken** wordt geopend in een nieuwe flyout. Configureer **op de pagina Label** definiëren de volgende instellingen:
   - **Naam:** Voer een unieke, beschrijvende naam in voor de tag. Dit is de waarde die u ziet en gebruikt. Houd er rekening mee dat u de naam van een tag niet kunt wijzigen nadat u deze hebt maken.
   - **Beschrijving:** Voer een optionele beschrijving voor de tag in.

   Wanneer je klaar bent, klik je op **Volgende**.

4. Ga op **de pagina Leden** toewijzen naar een van de volgende stappen:
   - Klik ![ op Pictogram Leden toevoegen Leden ](../../media/m365-cc-sc-create-icon.png) **toevoegen.** Ga als volgt te werk om afzonderlijke gebruikers of groepen toe te voegen in de fly-out die wordt weergegeven:
     - Klik in het vak en blader door de lijst om een gebruiker of groep te selecteren.
     - Klik in het vak en begin te typen om de lijst te filteren en selecteer een gebruiker of groep.
     - Als u extra waarden wilt toevoegen, klikt u in een leeg gebied in het vak.
     - Als u afzonderlijke items wilt verwijderen, klikt u op ![Pictogram Item verwijderen](../../media/m365-cc-sc-remove-selection-icon.png) naast het item in het vak.
     - Als u alle items wilt verwijderen, klikt u op Invoerpictogram verwijderen in het item Geselecteerde nn-gebruikers en ![ ](../../media/m365-cc-sc-remove-selection-icon.png) **nn-groepen** onder het vak.

     Wanneer u klaar bent, klikt u op **Toevoegen.**

     Terug op de **pagina Leden toewijzen** kunt u ook items verwijderen door te klikken op Pictogram Verwijderen naast het ![ ](../../media/m365-cc-sc-delete-icon.png) item.

   - Klik **op Importeren** om een tekstbestand te selecteren dat de e-mailadressen van de gebruikers of groepen bevat. Zorg ervoor dat het tekstbestand één invoer per regel bevat.

   Wanneer je klaar bent, klik je op **Volgende**.

5. Controleer de **instellingen op** de pagina Tag controleren die wordt weergegeven. U kunt in elke sectie **Bewerken** selecteren om de instellingen in de sectie te wijzigen. U kunt ook op **Terug** klikken of de specifieke pagina in de wizard selecteren.

   Wanneer u klaar bent, klikt u op **Verzenden** en klikt u vervolgens op **Gereed.**

## <a name="use-the-microsoft-365-defender-portal-to-view-user-tags"></a>Gebruik de Microsoft 365 Defender portal om gebruikerslabels te bekijken

1. Ga in Microsoft 365 Defender portal naar  Instellingen \> **e-mail & samenwerking** \> **Gebruikerslabels**.

2. Op de **pagina Gebruikerslabels** worden de volgende eigenschappen weergegeven in de lijst met gebruikerslabels:

   - **Tag:** De naam van de gebruikerstag. Houd er rekening mee dat dit de ingebouwde **systeemtag Priority-account** bevat.
   - **Toegepast op**: Het aantal leden
   - **Laatst gewijzigd**
   - **Gemaakt op**

3. Wanneer u een gebruikerslabel selecteert door op de naam te klikken, worden de details weergegeven in een flyout.

## <a name="use-the-microsoft-365-defender-portal-to-modify-user-tags"></a>Gebruik de Microsoft 365 Defender portal om gebruikerslabels te wijzigen

1. Ga in Microsoft 365 Defender portal naar  Instellingen \> **e-mail & samenwerking** \> **Gebruikerslabels**.

2. Selecteer op **de pagina Gebruikerslabels** de gebruikerstag in de lijst en klik vervolgens op ![ Tagpictogram bewerken Tag ](../../media/m365-cc-sc-edit-icon.png) **bewerken.**

3. In de flyout details die wordt weergegeven, zijn dezelfde wizard en instellingen beschikbaar als beschreven in de portal Gebruik [de Microsoft 365 Defender om](#use-the-microsoft-365-defender-portal-to-create-user-tags) eerder in dit artikel gebruikerslabels te maken.

   **Opmerkingen**:

   - De **pagina Label definiëren** is niet beschikbaar voor de ingebouwde systeemtag Priority-account, dus u kunt de naam van deze tag niet wijzigen of de beschrijving wijzigen. 
   - U kunt de naam van een aangepaste tag niet wijzigen, maar u kunt de beschrijving wel wijzigen.

## <a name="use-the-microsoft-365-defender-portal-to-remove-user-tags"></a>Gebruik de Microsoft 365 Defender portal om gebruikerslabels te verwijderen

> [!NOTE]
> U kunt de ingebouwde systeemtag **Priority-account** niet verwijderen.

1. Ga in Microsoft 365 Defender portal naar  Instellingen \> **e-mail & samenwerking** \> **Gebruikerslabels**.

2. Selecteer op **de pagina Gebruikerslabels** de gebruikerstag in de lijst en klik vervolgens op ![ Labelpictogram verwijderen Tag ](../../media/m365-cc-sc-delete-icon.png) **verwijderen.**

3. Lees de waarschuwing in het bevestigingsdialoogvenster dat wordt weergegeven en klik op **Ja, verwijderen.**
