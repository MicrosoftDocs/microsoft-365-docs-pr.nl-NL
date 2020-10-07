---
title: Verloopbeleid voor groepen Microsoft 365-groep
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
description: Meer informatie over verloopbeleid voor Microsoft 365-groepen.
ms.openlocfilehash: 8fc9c48d5a86c68eabd4139ad0a2d0dc1e83da0f
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377221"
---
# <a name="microsoft-365-group-expiration-policy"></a>Verloopbeleid voor groepen Microsoft 365-groep

Met de toename van het gebruik van Microsoft 365-groepen en Microsoft teams hebben beheerders en gebruikers een manier nodig om ongebruikte groepen en teams op te ruimen. Met een Microsoft 365-groep verloopbeleid kunt u inactieve groepen van het systeem verwijderen en wat duidelijker maken.

Wanneer een groep vervalt, worden ook alle bijbehorende services (het postvak, planner, SharePoint-site, team, etc.) verwijderd.

Wanneer een groep verloopt, betekent dit dat deze gedurende 30 dagen nog langer kan worden hersteld.

Beheerders kunnen een verloopperiode opgeven en alle inactieve groepen die het einde van die periode bereiken en niet worden vernieuwd. (Inclusief gearchiveerde teams) De verloopperiode begint wanneer de groep is gemaakt, of op de datum waarop deze het laatst is vernieuwd. Groepseigenaren ontvangen automatisch een e-mailbericht vóór de vervaldatum, zodat ze de groep kunnen verlengen met een ander verloopinterval. Teams-gebruikers zien permanente meldingen in teams.

Groepen die actief worden gebruikt, worden automatisch verlengd. Een groep wordt automatisch verlengd met een van de volgende acties:
- SharePoint: weergeven, bewerken, downloaden, verplaatsen, delen of uploaden van bestanden.
- Outlook: u kunt deelnemen aan een groep of een groepsbericht lezen of schrijven in de groep, en bijvoorbeeld een bericht (de webversie van Outlook).
- Teams: u bezoekt een team kanaal.

> [!IMPORTANT]
> Als u het verloopbeleid wijzigt, wordt de vervaldatum voor elke groep opnieuw berekend door de service. Wanneer de groep is gemaakt, wordt deze altijd vanaf de datum geteld en wordt het nieuwe verloopbeleid toegepast.

Het is belangrijk om te weten dat de vervaldatum standaard is uitgeschakeld. Beheerders moeten de functie inschakelen voor hun organisatie als ze deze willen gebruiken.

> [!NOTE]
> Als u het verloopbeleid voor Microsoft 365-groepen configureert en gebruikt, is het raadzaam om Azure AD Premium-licenties toe te wijzen aan de leden van alle groepen waarop u het verloopbeleid wilt toepassen. Zie voor meer informatie [Aan de slag met Azure Active Directory Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium).

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a>Wie kan het verloopbeleid voor Microsoft 365-groepen configureren en gebruiken?

|Rol|Wat ze kunnen doen|
|---------|---------|
|Globale beheerder van Office 365 (in azure, de beheerder van het bedrijf), gebruikersbeheerder|U kunt de instellingen voor het verloopbeleid van Microsoft 365-groepen maken, lezen, bijwerken of verwijderen.|
|Gebruiker|Een Microsoft 365-groep vernieuwen of [herstellen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted) waarvan hij of zij de eigenaar is|

## <a name="how-to-set-the-expiration-policy"></a>Het verloopbeleid instellen

Zoals hierboven aangegeven, is vervaldatum standaard uitgeschakeld. Een beheerder dient het verloopbeleid in te schakelen en de eigenschappen in te stellen dat deze van kracht worden. Als u dit wilt inschakelen, wordt het naar **Azure Active Directory**-  >  **groepen**  >  **verloopt**. U kunt hier de standaardlevensduur voor groepen instellen en opgeven hoe ver van tevoren u de eerste en tweede verloop bevestiging wilt naar de eigenaar van de groep.

De levensduur van de groep wordt in dagen opgegeven en kan worden ingesteld op 180, 365 of op een aangepaste waarde die u opgeeft. De aangepaste waarde moet ten minste 30 dagen bedragen.

Als de groep geen eigenaar heeft, wordt de vervaldatum van de e-mail naar de opgegeven beheerder verzonden.

U kunt het beleid instellen voor al uw groepen, alleen geselecteerde groepen of het geheel uitschakelen door **geen**te selecteren. U kunt momenteel geen verschillende beleidsregels voor verschillende groepen hebben.

![Schermafbeelding van instellingen voor groeps verloop in azure Active Directory](../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a>Hoe vervaldatum werkt met het bewaarbeleid

Als u een bewaarbeleid voor groepen in het beveiligings-en nalevings centrum hebt ingesteld, werkt het verloopbeleid naadloos met het bewaarbeleid. Wanneer een groep verloopt, worden de gesprekken en bestanden in het postvak van de groep in de groepssite bewaard in de Bewaar container voor het specifieke aantal dagen dat is gedefinieerd in het bewaarbeleid. Gebruikers zien de groep niet, of de inhoud ervan, na verloop.

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a>Hoe en wanneer de eigenaar van een groep weet of hun groepen verloopt

Groepseigenaren worden alleen via e-mail op de hoogte gesteld. Als de groep is gemaakt via planner, SharePoint of een andere app, worden de verval meldingen altijd via e-mail weergegeven. Als de groep is gemaakt via teams ontvangt de groepseigenaar een melding voor het verlengen via de sectie activiteit. Het wordt afgeraden om het verloop van een groep in te schakelen als de eigenaar van de groep geen geldig e-mailadres heeft.

Dertig dagen voordat de groep vervalt, ontvangt de eigenaren van de groep (of de e-mailadressen die u hebt opgegeven voor groepen die geen eigenaar zijn) een e-mailbericht zodat ze de groep gemakkelijk kunnen verlengen. Als ze het niet verlengen, ontvangen ze een ander e-mailadres van 15 dagen voordat het verloopt. Als het nog steeds niet wordt vernieuwd, ontvangen ze nog één e-mail melding voor de dag voordat het verloopt.

Als geen van de eigenaren of beheerders de groep verlengt voordat deze verloopt, kan de beheerder de groep nog maar dertig dagen na verloop herstellen. Zie voor meer informatie: [een verwijderde Microsoft 365-groep herstellen](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54).

## <a name="archiving-group-contents"></a>De inhoud van de groep archiveren

Als u een groep hebt die u niet meer wilt gebruiken, maar u wilt de inhoud behouden, raadpleegt u [Archief groepen, teams en Yammer](end-life-cycle-groups-teams-sites-yammer.md) voor informatie over het exporteren van gegevens uit de verschillende groepen-Services.

## <a name="related-articles"></a>Verwante artikelen

[Overzicht van bewaarbeleid](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)

[Een nieuwe eigenaar toewijzen aan een groep zonder eigenaar](https://support.office.com/article/86bb3db6-8857-45d1-95c8-f6d540e45732)

[Verloopt Microsoft 365 groepen configureren](https://docs.microsoft.com/azure/active-directory/active-directory-groups-lifecycle-azure-portal)
