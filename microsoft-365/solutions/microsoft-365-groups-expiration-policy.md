---
title: Microsoft 365 groep verloopbeleid
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
recommendations: false
description: Meer informatie over Microsoft 365 het verloopbeleid voor groepen.
ms.openlocfilehash: 90807d6c178061804e64db4440af42050a1d8e77
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52530848"
---
# <a name="microsoft-365-group-expiration-policy"></a>Microsoft 365 groep verloopbeleid

Met de toename van het gebruik van Microsoft 365 groepen en Microsoft Teams hebben beheerders en gebruikers een manier nodig om ongebruikte groepen en teams op te schonen. Een Microsoft 365 het verloopbeleid voor groepen kan helpen inactieve groepen uit het systeem te verwijderen en dingen schoner te maken.

Wanneer een groep verloopt, worden alle bijbehorende services (het postvak, planner, SharePoint site, team, enzovoort) ook verwijderd.

Wanneer een groep verloopt, is deze 'soft-deleted', wat betekent dat deze nog maximaal 30 dagen kan worden hersteld.

Beheerders kunnen een verloopperiode opgeven en elke inactieve groep die het einde van die periode bereikt en niet wordt verlengd, wordt verwijderd. (Dit geldt ook voor gearchiveerde teams.) De verloopperiode begint wanneer de groep wordt gemaakt of op de datum waarop de groep voor het laatst is verlengd. Groepseigenaars ontvangen automatisch een e-mail vóór de vervaldatum, zodat ze de groep kunnen verlengen voor een ander verloopinterval. Teams gebruikers zien permanente meldingen in Teams.

Groepen die actief worden gebruikt, worden automatisch verlengd. Een van de volgende acties verlengt een groep automatisch:
- SharePoint: bestanden weergeven, bewerken, downloaden, verplaatsen, delen of uploaden. (Het weergeven van SharePoint pagina telt niet als een actie voor automatische verlenging.)
- Outlook: voeg groep toe, lees of schrijf groepsbericht uit de groep en vind een bericht leuk (Outlook op het web).
- Teams - een teamkanaal bezoeken.

Houd er rekening mee dat de enige Yammer activiteit die een automatische groepsvernieuwing activeert, is het uploaden van een document naar SharePoint binnen de community.

> [!IMPORTANT]
> Wanneer u het verloopbeleid wijzigt, wordt de vervaldatum voor elke groep opnieuw berekend door de service. Het begint altijd te tellen vanaf de datum waarop de groep is gemaakt en past vervolgens het nieuwe verloopbeleid toe.

Het is belangrijk om te weten dat vervaldatum standaard is uitgeschakeld. Beheerders moeten deze inschakelen voor hun organisatie als ze deze willen gebruiken.

> [!NOTE]
> Voor het configureren en gebruiken van het verloopbeleid voor Microsoft 365-groepen moet u Azure AD Premium-licenties bezitten, maar niet noodzakelijk toewijzen voor de leden van alle groepen waarop het verloopbeleid wordt toegepast. Zie voor meer informatie [Aan de slag met Azure Active Directory Premium](/azure/active-directory/active-directory-get-started-premium).

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a>Wie kunt u het verloopbeleid voor Microsoft 365 groepen configureren en gebruiken?

|Rol|Wat ze kunnen doen|
|---------|---------|
|Office 365 globale beheerder (in Azure, de beheerder van het bedrijf), Gebruikerbeheerder|De instellingen voor het verloopbeleid voor groepen maken, lezen, bijwerken Microsoft 365 verwijderen.|
|Gebruiker|Een groep [Microsoft 365](/azure/active-directory/users-groups-roles/groups-restore-deleted) of herstellen|

## <a name="how-to-set-the-expiration-policy"></a>Het verloopbeleid instellen

Zoals hierboven vermeld, is de vervaldatum standaard uitgeschakeld. Een beheerder moet het verloopbeleid inschakelen en de eigenschappen instellen die moeten worden doorgevoerd. Als u dit wilt inschakelen, gaat **u naar Azure Active Directory** Verloop van  >    >  **groepen.** Hier kunt u de standaardlevensduur van de groep instellen en opgeven hoe ver van tevoren de eerste en tweede verloopmeldingen naar de groepseigenaar moeten gaan.

De levensduur van de groep wordt opgegeven in dagen en kan worden ingesteld op 180, 365 of op een aangepaste waarde die u opgeeft. De aangepaste waarde moet ten minste 30 dagen zijn.

Als de groep geen eigenaar heeft, gaan de verlopende e-mailberichten naar de opgegeven beheerder.

U kunt het beleid instellen voor al uw groepen, alleen geselecteerde groepen (maximaal 500) of volledig uitschakelen door **Geen te selecteren.** Op dit moment kunt u niet verschillende beleidsregels voor verschillende groepen hebben.

![Schermafbeelding van instellingen voor het verloop van groepen in Azure Active Directory](../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a>Hoe verlopen werkt met het bewaarbeleid

Als u een bewaarbeleid hebt ingesteld voor groepen in het Beveiligings- en compliancecentrum, werkt het verloopbeleid naadloos samen met bewaarbeleid. Wanneer een groep verloopt, worden de postvakgesprekken en bestanden van de groep op de groepssite bewaard in de bewaarcontainer voor het specifieke aantal dagen dat is gedefinieerd in het bewaarbeleid. Gebruikers zien de groep of de inhoud ervan echter niet na verloop van tijd.

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a>Hoe en wanneer een groepseigenaar leert of zijn of haar groepen verlopen

Groepseigenaren ontvangen alleen een melding via e-mail. Als de groep is gemaakt via Planner, SharePoint of een andere app, komen de verloopmeldingen altijd via e-mail. Als de groep is gemaakt via Teams, ontvangt de groepseigenaar een melding om te verlengen via de sectie Activiteit. Het wordt niet aanbevolen dat u verloop van een groep inschakelen als de groepseigenaar geen geldig e-mailadres heeft.

Dertig dagen voordat de groep verloopt, ontvangen de groepseigenaren (of de e-mailadressen die u hebt opgegeven voor groepen die geen eigenaar hebben) een e-mailbericht waarmee ze de groep eenvoudig kunnen verlengen. Als ze het niet verlengen, ontvangen ze 15 dagen voor de vervaldatum nog een verlengings-e-mail. Als ze deze nog steeds niet hebben verlengd, ontvangen ze de dag vóór de vervaldatum nog een e-mailmelding.

Als om de een of andere reden geen van de eigenaren of beheerders de groep verlengt voordat deze verloopt, kan de beheerder de groep nog steeds tot 30 dagen na de vervaldatum herstellen. Zie voor meer informatie: [Een verwijderde Microsoft 365 herstellen.](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54)

## <a name="archiving-group-contents"></a>Groepsinhoud archiveren

Zie [Groepen, teams](end-life-cycle-groups-teams-sites-yammer.md) en Yammer archiveren voor informatie over het exporteren van informatie uit de verschillende groepenservices als u een groep hebt die u niet meer wilt gebruiken, maar de inhoud ervan wilt behouden.

## <a name="related-topics"></a>Verwante onderwerpen

[Planning van samenwerkingsbeheer stap voor stap](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Uw samenwerkingsbeheerplan maken](collaboration-governance-first.md)

[Overzicht van bewaarbeleid](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)

[Een nieuwe eigenaar toewijzen aan een groep zonder eigenaar](https://support.office.com/article/86bb3db6-8857-45d1-95c8-f6d540e45732)

[Verloop van Microsoft 365 groepen configureren](/azure/active-directory/active-directory-groups-lifecycle-azure-portal)
