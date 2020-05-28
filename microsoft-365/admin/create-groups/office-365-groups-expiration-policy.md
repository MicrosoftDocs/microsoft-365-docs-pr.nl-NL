---
title: Verloopbeleid groepen
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Meer informatie over het vervaldatumbeleid van Microsoft 365-groepen.
ms.openlocfilehash: 00dfb09cdf4fe3f70344152444e7433c1de8a8c2
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400723"
---
# <a name="microsoft-365-group-expiration-policy"></a>Microsoft 365-groepsvervaldatumbeleid

Met de toename van het gebruik van Microsoft 365-groepen hebben beheerders en gebruikers een manier nodig om ongebruikte groepen op te schonen. Verloopbeleid kan helpen bij het verwijderen van inactieve groepen uit het systeem en dingen schoner maken.

Wanneer een groep verloopt, worden ook alle bijbehorende services (het postvak, Planner, SharePoint-site, team, enz.) verwijderd.

Wanneer een groep verloopt is het "soft-verwijderd", wat betekent dat het nog steeds kan worden hersteld voor maximaal 30 dagen.

Beheerders kunnen een vervaldatum opgeven en elke inactieve groep die het einde van die periode bereikt en niet wordt verlengd, wordt verwijderd. De vervaldatum begint wanneer de groep wordt gemaakt of op de datum waarop de groep voor het laatst is verlengd. Groepseigenaren ontvangen automatisch een e-mail vóór het verstrijken, zodat ze de groep opnieuw kunnen verlengen voor een ander verloopinterval. Teams-gebruikers zien permanente meldingen in Teams.

Groepen die actief in gebruik zijn, worden automatisch vernieuwd. Een van de volgende acties zal een groep automatisch vernieuwen:
- SharePoint - bestanden bekijken, bewerken, downloaden, verplaatsen, delen of uploaden.
- Outlook - word lid van groeps-, lees- of schrijfgroepsbericht van de groep en vind een bericht leuk (versie van Outlook op de webversie).
- Teams - een bezoek aan een teams kanaal.

> [!IMPORTANT]
> Wanneer u het verloopbeleid wijzigt, berekent de service de vervaldatum voor elke groep opnieuw. Het begint altijd te tellen vanaf de datum waarop de groep is gemaakt en past vervolgens het nieuwe verloopbeleid toe.

Het is belangrijk om te weten dat de vervaldatum standaard is uitgeschakeld. Beheerders moeten het inschakelen voor hun organisatie als ze het willen gebruiken.

> [!NOTE]
> Voor het configureren en gebruiken van het verloopbeleid voor Microsoft 365-groepen moet u Azure AD Premium-licenties bezitten, maar niet noodzakelijkerwijs toewijzen voor de leden van alle groepen waarop het verloopbeleid wordt toegepast. Zie voor meer informatie [Aan de slag met Azure Active Directory Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium).

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a>Wie kan het expiratiebeleid van Microsoft 365-groepen configureren en gebruiken?

|Rol|Wat ze kunnen doen|
|---------|---------|
|Globale beheerder (in Azure, de bedrijfsbeheerder), Gebruikersbeheerder|De beleidsinstellingen voor het verlopen van Microsoft 365-groepen maken, lezen, bijwerken of verwijderen.|
|Gebruiker|Een Microsoft 365-groep die ze bezitten, vernieuwen of [herstellen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted)|

## <a name="how-to-set-the-expiration-policy"></a>Het verloopbeleid instellen

Zoals hierboven vermeld, is het verlopen standaard uitgeschakeld. Een beheerder moet het verloopbeleid inschakelen en de eigenschappen instellen om deze in werking te laten treden. Ga naar **Azure Active Directory (AAD)-groepen**  >  **Groups**  >  **verlopen**in. Hier u de standaardgroepslevensduur instellen en opgeven hoe ver u van tevoren wilt dat de eerste en tweede vervaldatummeldingen naar de groepseigenaar gaan.

De groepslevensduur wordt in dagen opgegeven en kan worden ingesteld op 180, 365 of op een aangepaste waarde die u opgeeft. De aangepaste waarde moet ten minste 30 dagen zijn.

Als de groep geen eigenaar heeft, gaan de vervaldatum-e-mails naar een opgegeven beheerder.

U het beleid instellen voor al uw groepen, alleen geselecteerde groepen of het volledig uitschakelen door **Geen te**selecteren. Houd er rekening mee dat u momenteel geen ander beleid voor verschillende groepen hebben.

![Schermafbeelding van de vervaldatumsinstellingen van groepen in Azure Active Directory](../../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a>Hoe verlopen werkt met het bewaarbeleid

Als u het bewaarbeleid voor instellingen hebt in het beveiligings- en nalevingscentrum voor groepen, werkt het verloopbeleid naadloos samen met het bewaarbeleid. Wanneer een groep verloopt, worden de gesprekken van de groep in het postvak en de bestanden op de groepssite bewaard in de retentiecontainer voor het specifieke aantal dagen dat in het bewaarbeleid is gedefinieerd. Gebruikers zien de groep of de inhoud ervan echter niet na afloop.

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a>Hoe en wanneer een groepseigenaar hoort of zijn of haar groepen verlopen

Groepseigenaren worden alleen via e-mail op de hoogte gebracht. Als de groep is gemaakt via Planner, SharePoint of een andere app, komen de vervaldatummeldingen altijd via e-mail. Als de groep is gemaakt via Teams, ontvangt de eigenaar van de groep een melding om te verlengen via de activiteitssectie. Het wordt niet aanbevolen om vervaldatum in een groep in te schakelen als de eigenaar van de groep geen geldig e-mailadres heeft.

30 dagen voordat de groep verloopt, ontvangen de groepseigenaren (of de e-mailadressen die u hebt opgegeven voor groepen die geen eigenaar hebben) een e-mail waarmee ze de groep eenvoudig kunnen vernieuwen. Als ze deze niet verlengen, ontvangen ze 15 dagen voor het verstrijken van de looptijd nog een e-mail met verlenging. Als ze het nog steeds niet hebben verlengd, ontvangen ze de dag voor het verstrijken nog een e-mailmelding.

Als om de een of andere reden geen van de eigenaren of beheerders de groep verlengt voordat deze verloopt, kan de beheerder de groep nog steeds tot 30 dagen na afloop herstellen. Zie voor meer informatie: [Een verwijderde Microsoft 365-groep herstellen](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group).

## <a name="related-articles"></a>Verwante artikelen

[Overzicht van bewaarbeleid](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)

[Een nieuwe eigenaar toewijzen aan een groep zonder eigenaar](https://support.microsoft.com/en-us/office/assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732)

[Microsoft 365-groepen configureren die verlopen](https://docs.microsoft.com/azure/active-directory/active-directory-groups-lifecycle-azure-portal) '
