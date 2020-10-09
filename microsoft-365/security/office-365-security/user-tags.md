---
title: Gebruikerslabels in Office 365 ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe ze bepaalde groepen gebruikers identificeren met gebruikers Tags in Office 365 ATP abonnement 2. Labels filteren is beschikbaar via waarschuwingen, rapporten en onderzoeken in Office 365 ATP om snel de gecodeerde gebruikers te identificeren.
ms.openlocfilehash: 16e756b95e16e40f4df738e825e842681c67e22c
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399383"
---
# <a name="user-tags-in-office-365-atp"></a>Gebruikerslabels in Office 365 ATP

Gebruikers Tags zijn id's voor specifieke groepen gebruikers in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md). Er zijn twee soorten gebruikers Tags:

- **Systeem Tags**: momenteel is de [prioriteit accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) het enige type systeemcode.
- **Aangepaste tags**: u kunt deze gebruikers Tags zelf maken.

Als uw organisatie gebruikmaakt van Office 365 ATP (abonnement 2) (opgenomen in uw abonnement of als een invoegtoepassing), kunt u ook aangepaste gebruikers Tags maken en de tag met de prioriteits accounts gebruiken.

Wanneer u systeem Tags of aangepaste tags op gebruikers hebt toegepast, kunt u deze codes gebruiken als filters in waarschuwingen, rapporten en onderzoek:

- [Waarschuwingen in het nalevings centrum voor beveiligings &](alerts.md)
- [Bedreigings Verkenner en real-time ontdekken](threat-explorer.md)
- [Statusrapport bedreigingsbeveiliging](view-email-security-reports.md#threat-protection-status-report)
- [Campagneweergaven](campaigns.md)

In dit artikel wordt uitgelegd hoe u gebruikers Tags kunt configureren in de beveiligings & nalevings centrum. De beveiligings & bevat geen cmdlets voor het beheren van gebruikers Tags.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de pagina **gebruikers Tags** wilt gaan, opent u deze <https://protection.office.com/userTags> .

- Als u **aangepaste gebruikers Tags**wilt maken, wijzigen of verwijderen, moet u lid zijn van de rollen groepen **Organisatiebeheer** of **beveiligingsbeheerder** in het beveiligings & nalevings centrum. Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

- U moet een [globale beheerder](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) of een [Exchange-beheerder](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)zijn als u prioriteit accounts (systeem Tags) wilt configureren.

  U kunt prioriteit accounts ook beheren en controleren in het Microsoft 365-Beheercentrum. Zie [prioriteit accounts beheren en controleren](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)voor instructies.

## <a name="use-the-security-center-to-create-user-tags"></a>Beveiligingscentrum gebruiken om gebruikers Tags te maken

1. Ga in het Beveiligingscentrum naar **Threat management** \> **gebruikers Tags**van Threat Management.

2. Klik op de pagina **gebruikers Tags** die wordt geopend op **tag maken**.

3. De wizard **tag maken** wordt geopend in een nieuwe vlucht. Configureer de volgende instellingen op de pagina **tag definiëren** :

   - **Naam**: Typ een unieke, beschrijvende naam voor de tag. Dit is de waarde die u ziet en gebruikt.

   - **Beschrijving**: Typ een optionele beschrijving voor de tag.

   Wanneer u klaar bent, klikt u op **volgende**.

4. Voer een van de volgende stappen uit op de pagina **postvakken toewijzen** :

   - Klik op **postvakken toevoegen**. Voer een van de volgende stappen uit om afzonderlijke gebruikers of groepen toe te voegen:

     - Klik in het vak en blader door de lijst om een gebruiker of groep te selecteren.
     - Klik in het vak en begin te typen om de lijst te filteren en selecteer een gebruiker of groep.
     - Als u extra waarden wilt toevoegen, klikt u op een leeg gebied in het vak.
     - Als u afzonderlijke vermeldingen uit het vak **wilt verwijderen, klikt u** op ![ het pictogram verwijderen ](../../media/scc-remove-icon.png) van de gebruiker of groep in het vak.
     - Als u bestaande items uit de lijst onder het vak wilt verwijderen **, klikt u** op ![ het pictogram verwijderen verwijderen ](../../media/scc-remove-icon.png) .

     Wanneer u klaar bent, klikt u op **toevoegen**.

   - Klik op **importeren** om een tekstbestand te selecteren dat de e-mailadressen van de gebruikers of groepen bevat. Let op: het tekstbestand bevat één item per regel.

   Wanneer u klaar bent, klikt u op **volgende**.

5. Controleer de instellingen op de pagina **controle-label** . U kunt klikken op **bewerken** in de sectie specifiek om wijzigingen aan te brengen.

   Als u klaar bent, klikt u op **verzenden**.

## <a name="use-the-security-center-to-view-user-tags"></a>Beveiligingscentrum gebruiken om gebruikers Tags weer te geven

1. Ga in het Beveiligingscentrum naar **Threat management** \> **gebruikers Tags**van Threat Management.

2. Selecteer op de pagina **gebruikers Tags** die wordt geopend, de gebruikerscode die u wilt weergeven (Klik op het selectievakje niet).

3. Controleer de instellingen in de alleen-lezen gegevens die worden weergegeven.

   Klik op **Sluiten** wanneer u gereed bent.

## <a name="use-the-security-center-to-modify-user-tags"></a>Beveiligingscentrum gebruiken om gebruikers Tags te wijzigen

1. Ga in het Beveiligingscentrum naar **Threat management** \> **gebruikers Tags**van Threat Management.

2. Selecteer op de pagina **gebruikers Tags** die wordt geopend, de gebruikerscode die u wilt weergeven en klik vervolgens op **code bewerken**.

3. De wizard beleid wordt geopend in een **code bewerken** . Klik op **volgende** om de instellingen te bekijken en te wijzigen.

   Als u klaar bent, klikt u op **verzenden**.

## <a name="use-the-security-center-to-remove-user-tags"></a>Beveiligingscentrum gebruiken om gebruikers Tags te verwijderen

**Opmerking**: u kunt de code van het ingebouwde **prioriteits account** niet verwijderen.

1. Ga in het Beveiligingscentrum naar **Threat management** \> **gebruikers Tags**van Threat Management.

2. Selecteer op de pagina **gebruikers Tags** die wordt geopend, de gebruikerscode die u wilt verwijderen, klik op **markering verwijderen**en selecteer vervolgens **Ja, verwijderen** in de waarschuwing die verschijnt.
