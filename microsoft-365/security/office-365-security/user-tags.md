---
title: Gebruikerslabels in Microsoft Defender voor Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Beheerders kunnen in Microsoft Defender voor Office 365 Abonnement 2 specifieke groepen gebruikers identificeren met gebruikerstags. Filteren van tags is beschikbaar voor waarschuwingen, rapporten en onderzoeken in Microsoft Defender voor Office 365 om snel de gelabelde gebruikers te identificeren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 62d858fe5962b94f536d4ccbd712e21bdd5caa57
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290127"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a>Gebruikerslabels in Microsoft Defender voor Office 365

> [!NOTE]
> De functie voor gebruikerstags is beschikbaar in het voorbeeldvenster, is niet voor iedereen beschikbaar en kan worden gewijzigd. Bekijk de routekaart voor [Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap)voor informatie over het releaseschema.

Gebruikerslabels zijn id's voor specifieke groepen gebruikers in [Microsoft Defender voor Office 365.](office-365-atp.md) Er zijn twee typen gebruikerstags:

- **Systeemlabels:** Op dit moment is [Prioriteit-accounts](../../admin/setup/priority-accounts.md) het enige type systeemcode.
- **Aangepaste tags:** u maakt deze gebruikerstags zelf.

Als uw organisatie beschikt over Defender voor Office 365 Abonnement 2 (inbegrepen in uw abonnement of als een invoegcode), kunt u niet alleen de tag voor prioriteitsaccounts gebruiken, maar ook aangepaste gebruikerstags maken.

Nadat u systeemcodes of aangepaste tags hebt toegepast op gebruikers, kunt u deze tags gebruiken als filters in waarschuwingen, rapporten en onderzoeken:

- [Waarschuwingen in het beveiligings- & compliancecentrum](alerts.md)
- [Bedreigingsverkenner en realtime detecties](threat-explorer.md)
- [Statusrapport bedreigingsbeveiliging](view-email-security-reports.md#threat-protection-status-report)
- [Campagneweergaven](campaigns.md)
- Voor prioriteitsaccounts kunt u het rapport [E-mailproblemen voor prioriteitsaccounts](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in het Exchange-beheercentrum (EAC) gebruiken.

In dit artikel wordt uitgelegd hoe u gebruikerstags configureert in het & compliancecentrum. Er zijn geen cmdlets in & compliancecentrum voor het beheren van gebruikerslabels.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de pagina **Gebruikerstags wilt** gaan, opent u <https://protection.office.com/userTags> .

- Je moet beschikken over toegewezen machtigingen voor het uitvoeren van de procedures in dit onderwerp:
  - Als u gebruikerstags wilt maken, wijzigen en verwijderen, moet  u lid zijn van de rollengroepen **Organisatiebeheer** of Beveiligingsbeheerder.
  - Als u leden aan bestaande gebruikerstags wilt toevoegen of eruit  **wilt** verwijderen, moet u lid zijn van de rollengroepen Organisatiebeheer, Beveiligingsbeheerder of Beveiligingsoperator.
  - Voor alleen-lezen toegang tot gebruikerstags moet u  lid zijn van de rollengroepen Globale lezer of **Beveiligingslezer.**

  Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

  **Opmerkingen**:

  - Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen in het Beveiligings- en compliancecentrum _en_ machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.
  - Het beheer van gebruikerstags wordt beheerd door de rollen **Taglezer,** **Tag-medewerker** en **Tagbeheer.**

- U kunt ook prioriteitsaccounts beheren en controleren in het Microsoft 365-beheercentrum. Zie Accounts met prioriteit [beheren en controleren voor instructies.](../../admin/setup/priority-accounts.md)

## <a name="use-the-security-center-to-create-user-tags"></a>Het beveiligingscentrum gebruiken om gebruikerstags te maken

1. Ga in het beveiligingscentrum naar **Gebruikerstags voor** \> **bedreigingsbeheer.**

2. Klik op **de pagina Gebruikerstags** die wordt geopend op **Tag maken.**

3. De **wizard Label** maken wordt geopend in een nieuwe fly-out. Configureer **de volgende instellingen** op de pagina Label definiëren:
   - **Naam:** voer een unieke, beschrijvende naam voor de tag in. Dit is de waarde die u ziet en gebruikt.
   - **Beschrijving:** voer een optionele beschrijving voor de tag in.

   Klik op Volgende wanneer u klaar **bent.**

4. Ga op **de pagina Gebruikers** toewijzen op een van de volgende stappen te werk:

   - Klik **op Gebruikers toevoegen.** In het fly-out dat verschijnt, gaat u op een van de volgende stappen te werk om afzonderlijke gebruikers of groepen toe te voegen:
     - Klik in het vak en blader door de lijst om een gebruiker of groep te selecteren.
     - Klik in het vak en begin te typen om de lijst te filteren en selecteer een gebruiker of groep.
     - Als u extra waarden wilt toevoegen, klikt u in een leeg gebied in het vak.
     - Als u afzonderlijke items uit het vak wilt verwijderen, klikt u op **het** pictogram Verwijderen voor ![ de gebruiker of groep in het ](../../media/scc-remove-icon.png) vak.
     - Als u bestaande items wilt verwijderen uit de lijst onder het vak, klikt u op **het** pictogram ![ Verwijderen van de ](../../media/scc-remove-icon.png) vermelding.

     Klik op Toevoegen wanneer u **klaar bent.**

   - Klik **op Importeren** om een tekstbestand te selecteren dat de e-mailadressen van de gebruikers of groepen bevat. Zorg ervoor dat het tekstbestand één vermelding per regel bevat.

   Klik op Volgende wanneer u klaar **bent.**

5. Controleer de **instellingen op de** tagpagina Controleren. U kunt in **de specifieke** sectie op Bewerken klikken om wijzigingen aan te brengen.

   Klik op Verzenden wanneer u **klaar bent.**

## <a name="use-the-security-center-to-view-user-tags"></a>Gebruikerstags bekijken via het beveiligingscentrum

1. Ga in het beveiligingscentrum naar **Gebruikerstags voor** \> **bedreigingsbeheer.**

2. Selecteer op **de pagina Gebruikerstags** die wordt geopend, de gebruikerstag die u wilt bekijken (klik niet op het selectievakje).

3. Bekijk de instellingen in de alleen-lezen details die worden weergegeven.

   Klik op **Sluiten** wanneer u gereed bent.

## <a name="use-the-security-center-to-modify-user-tags"></a>Het beveiligingscentrum gebruiken om gebruikerstags te wijzigen

1. Ga in het beveiligingscentrum naar **Gebruikerstags voor** \> **bedreigingsbeheer.**

2. Selecteer op **de pagina Gebruikerstags** die wordt geopend, de gebruikerstag die u wilt bekijken en klik op **Tag bewerken.**

3. De wizard Beleid wordt geopend in **een fly-out label** bewerken. Klik **op Volgende** om de instellingen te controleren en te wijzigen.

   Klik op Verzenden wanneer u **klaar bent.**

## <a name="use-the-security-center-to-remove-user-tags"></a>Het beveiligingscentrum gebruiken om gebruikerstags te verwijderen

**Opmerking:** u kunt de ingebouwde tag van het **Priority-account niet** verwijderen.

1. Ga in het beveiligingscentrum naar **Gebruikerstags voor** \> **bedreigingsbeheer.**

2. Selecteer op **de** pagina gebruikerstags die wordt geopend, de gebruikerstag die u wilt verwijderen, klik op Tag verwijderen en selecteer vervolgens **Ja,** verwijderen in de waarschuwing die wordt weergegeven.
