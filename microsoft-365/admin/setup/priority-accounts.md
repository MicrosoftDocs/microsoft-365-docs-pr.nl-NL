---
title: Prioriteitsaccounts beheren en bewaken
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
ms.custom: AdminSurgePortfolio
description: Controleren mislukt en vertraagde e-mailberichten die zijn verzonden naar of van accounts met een hoge zakelijke impact.
ms.openlocfilehash: 2a58f4090244fc6d68be69cf6b3c8ab6e00874fa
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535804"
---
# <a name="manage-and-monitor-priority-accounts"></a>Prioriteitsaccounts beheren en bewaken

In elke Microsoft 365 zijn er mensen die essentieel zijn, zoals leidinggevenden, leidinggevenden, managers of andere gebruikers die toegang hebben tot gevoelige, eigendomsgebonden of hoge prioriteitsinformatie.

Als u uw organisatie wilt helpen deze accounts te beveiligen, kunt u nu specifieke gebruikers aanwijzen als prioriteitsaccounts en gebruikmaken van app-specifieke functies die hen extra bescherming bieden. In de toekomst ondersteunen meer apps en functies prioriteitsaccounts en om te  beginnen hebben we twee mogelijkheden aangekondigd: prioriteitsaccountbeveiliging en premium **e-mailstroomcontrole.**

- **Prioriteitsaccountbeveiliging:** Microsoft Defender voor Office 365 (voorheen Office 365 Advanced Threat Protection) ondersteunt prioriteitsaccounts als tags die kunnen worden gebruikt in filters in waarschuwingen, rapporten en onderzoeken. Zie Gebruikerslabels [in Microsoft Defender voor](../../security/office-365-security/user-tags.md)meer Office 365.

  Een natuurlijke vraag is: 'Zijn niet alle gebruikers een prioriteit? Waarom worden niet alle gebruikers aangewezen als prioriteitsaccounts? Ja, alle gebruikers hebben een prioriteit, maar accountbeveiliging met prioriteit biedt de volgende extra voordelen:

  - **Extra heuristische functies:** Onze analyse van de e-mailstroom in de Microsoft-datacenters geeft aan dat de e-mailstroompatronen voor leidinggevenden van het bedrijf verschillen van de gemiddelde werknemer. Prioriteitsaccountbeveiliging biedt extra heuristische functies die specifiek zijn afgestemd op leidinggevenden van het bedrijf die niet ten goede komen aan een gewone werknemer.
  - **Extra zichtbaarheid in rapportage:** In feite is informatie voor alle gebruikers (of alle betrokken gebruikers) al beschikbaar in waarschuwingen, rapporten en onderzoeken. Met de tag prioriteitsaccounts als filter kunt u uw onderzoeken specifiek richten.

- **Premium Mail Flow Monitoring:** een gezonde e-mailstroom kan van essentieel belang zijn voor bedrijfssucces en vertragingen of storingen van bezorging kunnen een negatieve invloed hebben op het bedrijf. U kunt een drempel voor mislukte of vertraagde e-mailberichten kiezen, waarschuwingen ontvangen wanneer deze drempel wordt overschreden en een rapport bekijken met e-mailproblemen voor prioriteitsaccounts. Zie E-mailproblemen voor het rapport [Prioriteitsaccounts in](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) het moderne EAC voor meer informatie.

Zie Beveiligingsaanbevelingen voor prioriteitsaccounts voor aanbevolen beveiligingsprocedures [voor prioriteitsaccounts.](../../security/office-365-security/security-recommendations-for-priority-accounts.md)

## <a name="before-you-begin"></a>Voordat u begint

De **functie Accountbeveiliging prioriteit** die in dit onderwerp wordt beschreven, is alleen beschikbaar voor organisaties die aan de volgende vereisten voldoen:

- Microsoft Defender voor Office 365 abonnement 2, inclusief personen met Office 365 E3, Office 365 E5, Microsoft 365 E5 of Microsoft 365 E5 Security.

De **functie Premium Mail Flow monitoring** die in dit onderwerp wordt beschreven, is alleen beschikbaar voor organisaties die voldoen aan de volgende vereisten:

- Uw organisatie moet een licentie tellen van ten minste 10.000, van een van of een combinatie van de volgende producten: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5. Uw organisatie kan bijvoorbeeld 3000 Office 365 E3-licenties en 8500 Microsoft 365 E5 hebben, voor in totaal 11.500 licenties van de in aanmerking komende producten.
- Je organisatie heeft ten minste 50 maandelijks actieve Exchange Online-gebruikers nodig.

> [!NOTE]
> U kunt maximaal 250 prioriteitsaccounts controleren.

Wanneer u prioriteitsaccountbeveiliging op een postvak gebruikt, moet u ook prioriteitsaccountbeveiliging toepassen op gebruikers die toegang hebben tot het postvak (bijvoorbeeld de CEO en de executive assistant van de CEO die de agenda van de CEO beheert).

### <a name="add-priority-accounts-from-the-setup-page"></a>Prioriteitsaccounts toevoegen vanaf de pagina Setup

Voeg prioriteitsaccounts toe vanaf **de pagina Setup.**

1. Ga naar het Microsoft 365 beheercentrum op <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Ga naar  >  **Organisatiekennis instellen** en kies **Weergeven** onder Uw belangrijkste **accounts controleren.**

3. Selecteer **Aan de slag** of **Beheren.**

4. Typ op **de pagina Prioriteitsaccounts** toevoegen in het zoekveld de naam of het e-mailadres van de persoon die u wilt toevoegen aan de lijst met prioriteitsaccounts. U kunt ook de drempel voor e-mail instellen voor mislukte of vertraagde e-mailberichten en een wekelijks rapport krijgen van problemen voor prioriteitsaccounts.

5. Selecteer de gebruiker en kies **Opslaan.**

U kunt ook prioriteitsaccounts toevoegen vanaf de pagina Actieve gebruikers.

### <a name="add-priority-accounts-from-active-users-page"></a>Prioriteitsaccounts toevoegen vanaf de pagina Actieve gebruikers

Voeg prioriteitsaccounts toe vanaf de pagina Actieve gebruikers.

1. Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

2. Ga naar **Gebruikers**  >  **Actieve gebruikers** en selecteer de drie puntjes (meer acties) boven aan de pagina. Selecteer **Prioriteitsaccounts beheren.**

3. Selecteer **Accounts toevoegen** en typ op de pagina **Prioriteitsaccounts** toevoegen in het zoekveld de naam van de persoon die u wilt toevoegen aan de lijst met prioriteitsaccounts.

4. Selecteer de gebruiker en kies **Opslaan.**

## <a name="remove-a-user-from-the-priority-accounts-list"></a>Een gebruiker verwijderen uit de lijst met prioriteitsaccounts

1. Ga naar het Microsoft 365 beheercentrum op <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Ga naar  >  **Organisatiekennis instellen** en kies **Weergeven** onder Uw belangrijkste **accounts controleren.**

3. Kies op **de pagina Uw meeste accounts controleren** de optie **Prioriteitsaccounts** onder **Deze functie beheren.**

4. Selecteer op **de pagina Prioriteitsaccounts** de gebruiker of gebruikers die u uit de lijst wilt verwijderen en kies Accounts **verwijderen.**

## <a name="related-topics"></a>Verwante onderwerpen

[Prioriteitsaccounts gebruiken in Microsoft 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)
