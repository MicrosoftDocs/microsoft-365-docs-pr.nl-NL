---
title: Prioriteits accounts beheren en controleren
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
description: Controleren van mislukte en vertraagde e-mailberichten die zijn verzonden naar of van accounts die hoge bedrijfsimpact hebben.
ms.openlocfilehash: bc191873b3bbdcd84122a5430adeffe2b8c29fb1
ms.sourcegitcommit: 5ce64d510b15c6e2df32b78e6086f77156731e3c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/30/2020
ms.locfileid: "49477611"
---
# <a name="manage-and-monitor-priority-accounts"></a>Prioriteits accounts beheren en controleren

In elke Microsoft 365-organisatie zijn er personen die essentieel zijn, zoals leidinggevenden, leidinggevenden, managers of andere gebruikers die toegang hebben tot gevoelige informatie.

Om uw organisatie te helpen deze accounts te beschermen, kunt u nu bepaalde gebruikers aanwijzen als prioriteits accounts en app-specifieke functies die ze bieden, extra bescherming bieden. In de toekomst ondersteunen meer apps en functies prioriteits accounts, en om te beginnen met, hebben we twee mogelijkheden aangekondigd: **bescherming van prioriteits account** en een **uitgebreide e-mail stroom**.

- **Accountbeveiliging** voor de prioriteit: Microsoft Defender voor Office 365 (voorheen Office 365 Advanced Threat Protection) ondersteunt prioriteits accounts als tags die kunnen worden gebruikt in filters in waarschuwingen, rapporten en onderzoek. Voor meer informatie raadpleegt u [gebruikers Tags in Microsoft Defender voor Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide).
- De **hoogwaardige e-mail stroom monitoring** -gezonde e-mail stroom kan essentieel zijn voor het succes van een bedrijf, en de bezorgings vertragingen of-storingen kunnen een negatieve invloed hebben op het bedrijf. U kunt een drempel voor mislukte of vertraagde e-mailberichten kiezen, waarschuwingen ontvangen wanneer deze drempel wordt overschreden en een rapport met e-mail problemen voor prioriteit accounts weergeven. Zie voor meer informatie [e-mail problemen voor het rapport met prioriteits accounts in de moderne](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)versie van het Beheercentrum.

## <a name="before-you-begin"></a>Voordat u begint

De functie voor **accountbeveiliging** van de prioriteit die wordt beschreven in dit onderwerp is alleen beschikbaar voor organisaties die aan de volgende vereisten voldoen:

- Microsoft Defender voor Office 365, abonnement 2, waaronder computers met Office 365 E3, Office 365 E5, Microsoft 365 E5 of Microsoft 365 E5-beveiliging.

De **Premium-functie voor het bijhouden van e-mail stromen** die in dit onderwerp wordt beschreven, is alleen beschikbaar voor organisaties die aan de volgende vereisten voldoen:

- Uw organisatie moet een aantal licenties hebben van ten minste 10.000, van een van, of een combinatie van de volgende producten: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5. Uw organisatie kan bijvoorbeeld 3000 Office 365 E3-licenties en 8500 Microsoft 365 E5 voor een totaal van de 11.500-licenties van de in aanmerking komende producten.
- Uw organisatie moet minimaal 50 maand actieve Exchange Online-gebruikers hebben.

> [!NOTE]
> U kunt maximaal 250 prioriteit accounts volgen.

### <a name="add-priority-accounts-from-the-setup-page"></a>Een prioriteit toevoegen aan accounts van de instellings pagina

Voeg prioritaire accounts toe op de **pagina instellingen**.

1. Ga naar het Microsoft 365-Beheercentrum <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Ga naar **Setup**  >  **organisatie kennis** instellen en kies **weergeven** onder **uw belangrijkste accounts bijhouden**.

3. Selecteer **aan de slag** of **beheren**.

4. Typ op de pagina **prioriteits accounts toevoegen** in het veld zoeken de naam of het e-mailadres van de persoon die u wilt toevoegen aan de lijst prioriteits accounts. U kunt ook uw e-mail drempel instellen voor mislukte of vertraagde e-mailberichten en een wekelijks rapport van de problemen met prioriteit accounts krijgen.

5. Selecteer de gebruiker en kies **Opslaan**.

U kunt ook prioriteit accounts toevoegen vanaf de pagina actieve gebruikers.

### <a name="add-priority-accounts-from-active-users-page"></a>Prioriteit accounts toevoegen vanaf de pagina actieve gebruikers

Voeg prioriteit toe aan accounts van de pagina actieve gebruikers.

1. Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

2. Ga naar **gebruikers** met  >  **actieve gebruikers** en kies **...** boven aan de pagina. Selecteer **prioriteit accounts beheren**.

3. Selecteer **accounts toevoegen** en typ in het zoekveld op de pagina **accountnamen toevoegen** de naam van de persoon die u wilt toevoegen aan de lijst prioriteits accounts.

4. Selecteer de gebruiker en kies **Opslaan**.

## <a name="remove-a-user-from-the-priority-accounts-list"></a>Een gebruiker verwijderen uit de lijst met prioriteit accounts

1. Ga naar het Microsoft 365-Beheercentrum <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Ga naar **Setup**  >  **organisatie kennis** instellen en kies **weergeven** onder **uw belangrijkste accounts bijhouden**.

3. Kies op de pagina **uw meeste accounts bewaken** de optie **prioriteit accounts** onder **deze functie beheren**.

4. Selecteer op de pagina **Priority accounts** de gebruikers of gebruikers die u wilt verwijderen uit de lijst en kies **accounts verwijderen**.

## <a name="related-topics"></a>Verwante onderwerpen

[Prioritaire accounts gebruiken in Microsoft 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)