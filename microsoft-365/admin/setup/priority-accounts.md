---
title: Prioriteitsaccounts beheren en controleren
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
description: Controleer mislukte en vertraagde e-mailberichten die zijn verzonden naar of van accounts die grote gevolgen hebben voor het bedrijf.
ms.openlocfilehash: dbdd692a41d341564376960788054e70623daf5a
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233360"
---
# <a name="manage-and-monitor-priority-accounts"></a>Prioriteitsaccounts beheren en controleren

In elke Microsoft 365-organisatie zijn er essentiële personen, zoals leidinggevenden, leidinggevenden, managers of andere gebruikers, die toegang hebben tot gevoelige, eigendomsinformatie of informatie met hoge prioriteit.

Om uw organisatie te helpen deze accounts te beveiligen, kunt u nu specifieke gebruikers als prioriteitsaccounts aanwijzen en app-specifieke functies gebruiken die hen extra beveiliging bieden. In de toekomst ondersteunen meer apps en functies prioriteitsaccounts. Om te  beginnen hebben we twee mogelijkheden aangekondigd: prioriteitsaccountbeveiliging en **premium-e-mailstroomcontrole.**

- **Prioriteitsaccountbeveiliging:** Microsoft Defender voor Office 365 (voorheen Office 365 Advanced Threat Protection) ondersteunt prioriteitsaccounts als tags die kunnen worden gebruikt in filters in waarschuwingen, rapporten en onderzoeken. Bekijk gebruikerstags in Microsoft Defender voor [Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags)voor meer informatie.
- **Premium Mail Flow Monitoring:** een goede e-mailstroom kan essentieel zijn voor bedrijfssuccessen en bezorgingsvertra laten of mislukte bezorging kunnen een negatieve invloed hebben op het bedrijf. U kunt een drempelwaarde kiezen voor mislukte of vertraagde e-mailberichten, waarschuwingen ontvangen wanneer deze drempel wordt overschreden en een rapport bekijken van e-mailproblemen voor prioriteitsaccounts. Raadpleeg het rapport [E-mailproblemen voor prioriteitaccounts in](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) het moderne EAC voor meer informatie

Zie Beveiligingsaanbevelingen voor prioriteitsaccounts voor aanbevolen beveiligingsprocedures [voor prioriteitsaccounts.](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-recommendations-for-priority-accounts)

## <a name="before-you-begin"></a>Voordat u begint

De **functie Accountbeveiliging met** prioriteit die in dit onderwerp wordt beschreven, is alleen beschikbaar voor organisaties die aan de volgende vereisten voldoen:

- Microsoft Defender voor Office 365 Abonnement 2, inclusief personen met Office 365 E3, Office 365 E5, Microsoft 365 E5 of Microsoft 365 E5-beveiliging.

De **functie Premium e-mailstroomcontrole** die in dit onderwerp wordt beschreven, is alleen beschikbaar voor organisaties die aan de volgende vereisten voldoen:

- Uw organisatie moet het aantal licenties hebben van ten minste 10.000, van een of meer, of een combinatie van de volgende producten: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5. Uw organisatie kan bijvoorbeeld 3000 Office 365 E3-licenties en 8500 Microsoft 365 E5 hebben voor een totaal van 11.500 licenties van de in aanmerking komende producten.
- Je organisatie heeft ten minste 50 maandelijks actieve Exchange Online-gebruikers nodig.

> [!NOTE]
> U kunt maximaal 250 accounts met prioriteit controleren.

### <a name="add-priority-accounts-from-the-setup-page"></a>Prioriteitsaccounts toevoegen vanaf de pagina Setup

Voeg prioriteitsaccounts toe op de **pagina Setup.**

1. Ga naar het Microsoft 365-beheercentrum op <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Ga naar **Kennis over** de  >  **organisatie instellen** en kies **Weergeven** onder Uw belangrijkste **accounts controleren.**

3. Selecteer **Aan de slag** of **Beheren.**

4. Typ op **de pagina Prioriteitsaccounts** toevoegen in het zoekveld de naam of het e-mailadres van de persoon die u wilt toevoegen aan de lijst met prioriteitsaccounts. U kunt ook uw e-mail drempelwaarde instellen voor mislukte of vertraagde e-mailberichten en een wekelijks rapport ontvangen van problemen voor prioriteitsaccounts.

5. Selecteer de gebruiker en kies **Opslaan.**

U kunt ook prioriteitsaccounts toevoegen vanaf de pagina Actieve gebruikers.

### <a name="add-priority-accounts-from-active-users-page"></a>Pagina Prioriteitsaccounts toevoegen van de pagina Actieve gebruikers

Voeg prioriteitsaccounts toe op de pagina Actieve gebruikers.

1. Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

2. Ga naar **Gebruikers**  >  **actieve gebruikers** en kies **...** boven aan de pagina. Selecteer **Prioriteitsaccounts beheren.**

3. Selecteer **Accounts toevoegen** en  typ op de pagina Prioriteitsaccounts toevoegen in het zoekveld de naam van de persoon die u wilt toevoegen aan de lijst met prioriteitsaccounts.

4. Selecteer de gebruiker en kies **Opslaan.**

## <a name="remove-a-user-from-the-priority-accounts-list"></a>Een gebruiker verwijderen uit de lijst met prioriteitsaccounts

1. Ga naar het Microsoft 365-beheercentrum op <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Ga naar **Kennis over** de  >  **organisatie instellen** en kies **Weergeven** onder Uw belangrijkste **accounts controleren.**

3. Kies op **de pagina Uw meeste accounts controleren** de optie **Prioriteitsaccounts** onder **Deze functie beheren.**

4. Selecteer op **de pagina Prioriteit-accounts** de gebruiker of gebruikers die u wilt verwijderen uit de lijst en kies **Accounts verwijderen.**

## <a name="related-topics"></a>Verwante onderwerpen

[Prioriteitsaccounts gebruiken in Microsoft 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)