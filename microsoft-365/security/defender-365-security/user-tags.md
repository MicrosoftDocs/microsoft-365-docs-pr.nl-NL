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
description: Beheerders kunnen leren hoe u specifieke groepen gebruikers kunt identificeren met gebruikerslabels in Microsoft Defender voor Office 365-abonnement 2. Tagfiltering is beschikbaar in waarschuwingen, rapporten en onderzoeken in Microsoft Defender voor Office 365 om snel de gelabelde gebruikers te identificeren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6f98dcfe3e8c44e852134e7a12def4ff78c1bcdd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057769"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a>Gebruikerslabels in Microsoft Defender voor Office 365

> [!NOTE]
> De functie gebruikerslabels is beschikbaar in Preview, is niet voor iedereen beschikbaar en kan worden gewijzigd. Voor meer informatie over de releaseplanning raadpleegt u de [routekaart voor Microsoft 365.](https://www.microsoft.com/microsoft-365/roadmap)

Gebruikerslabels zijn id's voor specifieke groepen gebruikers in [Microsoft Defender voor Office 365.](defender-for-office-365.md) Er zijn twee typen gebruikerslabels:

- **Systeemlabels:** Momenteel is [Prioriteitsaccounts](../../admin/setup/priority-accounts.md) het enige type systeemlabel.
- **Aangepaste tags:** u maakt deze gebruikerslabels zelf.

Als uw organisatie Defender voor Office 365-abonnement 2 heeft (inbegrepen in uw abonnement of als invoegvoeggebruik), kunt u aangepaste gebruikerslabels maken naast het gebruik van de tag prioriteitsaccounts.

Nadat u systeemlabels of aangepaste tags op gebruikers hebt toegepast, kunt u deze tags gebruiken als filters in waarschuwingen, rapporten en onderzoeken:

- [Waarschuwingen in het beveiligings- & compliancecentrum](alerts.md)
- [Threat Explorer en realtime detecties](threat-explorer.md)
- [Statusrapport bedreigingsbeveiliging](view-email-security-reports.md#threat-protection-status-report)
- [Campagneweergaven](campaigns.md)
- Voor prioriteitsaccounts kunt u het rapport [E-mailproblemen voor prioriteitsaccounts](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) gebruiken in het Exchange-beheercentrum (EAC).

In dit artikel wordt uitgelegd hoe u gebruikerslabels configureert in & Compliancecentrum. Er zijn geen cmdlets in & compliancecentrum om gebruikerslabels te beheren.

Zie Beveiligingsaanbevelingen voor [prioriteitsaccounts in Microsoft 365](security-recommendations-for-priority-accounts.md)als u wilt zien hoe gebruikerslabels deel uitmaken van de strategie voor het beschermen van gebruikersaccounts met een hoge impact.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de pagina **Gebruikerslabels wilt** gaan, opent u <https://protection.office.com/userTags> .

- Je moet beschikken over toegewezen machtigingen voor het uitvoeren van de procedures in dit onderwerp:
  - Als u gebruikerslabels wilt maken, wijzigen en verwijderen, moet  u lid zijn van de rollengroepen **Organisatiebeheer** of Beveiligingsbeheerder.
  - Als u leden wilt toevoegen en verwijderen uit bestaande gebruikerslabels, moet u lid zijn van de rollengroepen Organisatiebeheer, **Beveiligingsbeheerder** of Beveiligingsoperator 
  - Voor alleen-lezen toegang tot gebruikerslabels moet u lid zijn van de rollengroepen **Globale** lezer of **Beveiligingslezer.**

  Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

  **Opmerkingen**:

  - Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen in het Beveiligings- en compliancecentrum _en_ machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.
  - Gebruikerslabelbeheer wordt beheerd door de rollen **Tag Reader** en **Tag Manager.**

- U kunt ook prioriteitsaccounts beheren en controleren in het Microsoft 365-beheercentrum. Zie Prioriteitsaccounts beheren [en controleren voor instructies.](../../admin/setup/priority-accounts.md)

## <a name="use-the-security--compliance-center-to-create-user-tags"></a>Het beveiligings- & compliancecentrum gebruiken om gebruikerslabels te maken

1. Ga in het & Compliancecentrum naar **Gebruikerslabels voor** \> **bedreigingsbeheer.**

2. Klik op **de pagina Gebruikerslabels** die wordt geopend op **Tag maken.**

3. De **wizard Tag maken** wordt geopend in een nieuwe fly-out. Configureer **op de pagina Label** definiëren de volgende instellingen:
   - **Naam:** Voer een unieke, beschrijvende naam in voor de tag. Dit is de waarde die u ziet en gebruikt.
   - **Beschrijving:** Voer een optionele beschrijving voor de tag in.

   Wanneer u klaar bent, klikt u op **Volgende.**

4. Ga op **de pagina Gebruikers toewijzen** naar een van de volgende stappen:

   - Klik **op Gebruikers toevoegen.** Ga als volgt te werk om afzonderlijke gebruikers of groepen toe te voegen in de fly-out die wordt weergegeven:
     - Klik in het vak en blader door de lijst om een gebruiker of groep te selecteren.
     - Klik in het vak en begin te typen om de lijst te filteren en selecteer een gebruiker of groep.
     - Als u extra waarden wilt toevoegen, klikt u in een leeg gebied in het vak.
     - Als u afzonderlijke items uit het vak wilt verwijderen, klikt u op **Pictogram** ![ Verwijderen verwijderen van de gebruiker of groep in het ](../../media/scc-remove-icon.png) vak.
     - Als u bestaande items wilt verwijderen uit de lijst onder het vak, klikt u **op Pictogram** Verwijderen van ![ de ](../../media/scc-remove-icon.png) vermelding.

     Wanneer u klaar bent, klikt u op **Toevoegen.**

   - Klik **op Importeren** om een tekstbestand te selecteren dat de e-mailadressen van de gebruikers of groepen bevat. Zorg ervoor dat het tekstbestand één invoer per regel bevat.

   Wanneer u klaar bent, klikt u op **Volgende.**

5. Controleer op **de pagina Tag** controleren uw instellingen. U kunt in **de specifieke** sectie op Bewerken klikken om wijzigingen aan te brengen.

   Wanneer u klaar bent, klikt u op **Verzenden.**

## <a name="use-the-security--compliance-center-to-view-user-tags"></a>Het beveiligings- & compliancecentrum gebruiken om gebruikerslabels weer te geven

1. Ga in het & Compliancecentrum naar **Gebruikerslabels voor** \> **bedreigingsbeheer.**

2. Selecteer op **de pagina Gebruikerslabels** die wordt geopend de gebruikerstag die u wilt weergeven (klik niet op het selectievakje).

3. Bekijk de instellingen in de alleen-lezen details die worden weergegeven.

   Klik op **Sluiten** wanneer u gereed bent.

## <a name="use-the-security--compliance-center-to-modify-user-tags"></a>Gebruik het beveiligings- & compliancecentrum om gebruikerslabels te wijzigen

1. Ga in het & Compliancecentrum naar **Gebruikerslabels voor** \> **bedreigingsbeheer.**

2. Selecteer op **de pagina Gebruikerslabels** die wordt geopend de gebruikerstag die u wilt weergeven en klik vervolgens op **Tag bewerken.**

3. De wizard Beleid wordt geopend in **een fly-out tag** bewerken. Klik **op Volgende** om de instellingen te bekijken en te wijzigen.

   Wanneer u klaar bent, klikt u op **Verzenden.**

## <a name="use-the-security--compliance-center-to-remove-user-tags"></a>Gebruik het beveiligings- & compliancecentrum om gebruikerslabels te verwijderen

**Opmerking:** U kunt de ingebouwde tag **Priority-account niet** verwijderen.

1. Ga in het & Compliancecentrum naar **Gebruikerslabels voor** \> **bedreigingsbeheer.**

2. Selecteer op **de pagina** Gebruikerslabels die wordt geopend de gebruikerstag die u wilt verwijderen, klik op **Tag** verwijderen en selecteer vervolgens **Ja,** verwijderen in de waarschuwing die wordt weergegeven.