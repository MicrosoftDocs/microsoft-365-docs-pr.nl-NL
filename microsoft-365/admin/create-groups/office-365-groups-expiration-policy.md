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
description: Meer informatie over het verloopbeleid van Microsoft 365-groepen.
ms.openlocfilehash: 84b7048e414fe37c89a59dd9f282a4b35e0f26c8
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560361"
---
# <a name="microsoft-365-group-expiration-policy"></a>Microsoft 365-groepverloopbeleid

Met de toename van het gebruik van Microsoft 365-groepen hebben beheerders en gebruikers een manier nodig om ongebruikte groepen op te schonen. Expiratiebeleid kan helpen bij het verwijderen van inactieve groepen uit het systeem en het schoner maken van dingen.

Wanneer een groep verloopt, worden ook alle bijbehorende services (het postvak, planner, SharePoint-site, team, enz.) verwijderd.

Wanneer een groep verloopt is het "soft-deleted", wat betekent dat het nog steeds kan worden hersteld voor maximaal 30 dagen.

Beheerders kunnen een verloopperiode opgeven en elke inactieve groep die het einde van die periode bereikt en niet wordt verlengd, wordt verwijderd. De vervaldatum begint wanneer de groep wordt gemaakt of op de datum waarop deze voor het laatst is verlengd. Groepseigenaren ontvangen automatisch een e-mail vóór de vervaldatum waarmee ze de groep kunnen verlengen voor een ander verloopinterval. Teamsgebruikers krijgen permanente meldingen te zien in Teams.

Groepen die actief in gebruik zijn, worden automatisch vernieuwd. Een van de volgende acties wordt automatisch verlengd door een groep:
- SharePoint - bestanden weergeven, bewerken, downloaden, verplaatsen, delen of uploaden.
- Outlook : word lid van groep, lees of schrijf groepsbericht van de groep en vind een bericht leuk (Web outlook).
- Teams - een bezoek aan een team kanaal.

> [!IMPORTANT]
> Wanneer u het vervaldatumbeleid wijzigt, berekent de service de vervaldatum voor elke groep opnieuw. Het begint altijd te tellen vanaf de datum waarop de groep is gemaakt en past vervolgens het nieuwe vervaldatumsbeleid toe.

Het is belangrijk om te weten dat vervaldatum standaard is uitgeschakeld. Beheerders moeten het inschakelen voor hun organisatie als ze het willen gebruiken.

> [!NOTE]
> Als u het vervaldatumbeleid voor Microsoft 365-groepen configureert en gebruikt, moet u Azure AD Premium-licenties bezitten, maar niet noodzakelijkerwijs toewijzen voor de leden van alle groepen waarop het vervaldatumbeleid wordt toegepast. Zie voor meer informatie [Aan de slag met Azure Active Directory Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium).

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a>Wie kan het verloopbeleid van Microsoft 365-groepen configureren en gebruiken?

|Rol|Wat ze kunnen doen|
|---------|---------|
|Globale beheerder (in Azure, de bedrijfsbeheerder), gebruikersbeheerder|Maak, lees, werk of verwijder de instellingen voor het verlopen van Microsoft 365-groepen.|
|Gebruiker|Een Microsoft 365-groep vernieuwen of [herstellen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted) die in hun bezit is|

## <a name="how-to-set-the-expiration-policy"></a>Het verloopbeleid instellen

Zoals hierboven vermeld, is het verlopen standaard uitgeschakeld. Een beheerder moet het vervaldatumbeleid inschakelen en de eigenschappen instellen om deze van kracht te laten worden. Ga naar **Azure Active Directory (AAD)**  >  **Groups**  >  **Expiration**. Hier u de standaardgroepslevensduur instellen en opgeven hoe ver u van tevoren wilt dat de eerste en tweede vervaldatummeldingen naar de groepseigenaar gaan.

De groepslevensduur is opgegeven in dagen en kan worden ingesteld op 180, 365 of op een aangepaste waarde die u opgeeft. De aangepaste waarde moet ten minste 30 dagen zijn.

Als de groep geen eigenaar heeft, gaan de e-mails voor het verlopen naar een opgegeven beheerder.

U het beleid instellen voor al uw groepen, alleen geselecteerde groepen, of het volledig uitschakelen door **Geen**te selecteren. Houd er rekening mee dat je momenteel geen verschillende beleidsregels voor verschillende groepen hebben.

![Schermafbeelding van de verloopinstellingen voor groepen in Azure Active Directory](../../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a>Hoe expirie werkt met het bewaarbeleid

Als u een installatiebehoudsbeleid hebt ingesteld in het beveiligings- en nalevingscentrum voor groepen, werkt het vervaldatumbeleid naadloos samen met het bewaarbeleid. Wanneer een groep verloopt, worden de gesprekken van de groep in de postvak en bestanden op de groepssite bewaard in de bewaarcontainer voor het specifieke aantal dagen dat is gedefinieerd in het bewaarbeleid. Gebruikers zien de groep of de inhoud ervan echter niet na afloop.

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a>Hoe en wanneer een groepseigenaar leert of zijn groepen verlopen

Groepseigenaren worden alleen per e-mail op de hoogte gebracht. Als de groep is gemaakt via Planner, SharePoint of een andere app, komen de vervaldatummeldingen altijd via e-mail. Als de groep is gemaakt via Teams, ontvangt de groepseigenaar een melding om te verlengen via de activiteitssectie. Het wordt afgeraden om verloop van een groep in te schakelen als de eigenaar van de groep geen geldig e-mailadres heeft.

30 dagen voordat de groep verloopt, ontvangen de groepseigenaren (of de e-mailadressen die u hebt opgegeven voor groepen die geen eigenaar hebben) een e-mail waarmee ze de groep eenvoudig kunnen vernieuwen. Als ze het niet verlengen, ontvangen ze 15 dagen voor het verstrijken nog een verlengingse-mail. Als ze het nog steeds niet hebben verlengd, ontvangen ze de dag voor het verstrijken nog een e-mailmelding.

Als om de een of andere reden geen van de eigenaren of beheerders de groep verlengt voordat deze verloopt en automatische verlenging niet plaatsvindt omdat de groep niet automatisch aan de vereisten voldoet die moeten worden verlengd, kan de beheerder de groep nog steeds herstellen tot 30 dagen na afloop. Zie voor meer informatie: [Een verwijderde Microsoft 365-groep herstellen.](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)

## <a name="related-articles"></a>Verwante artikelen

[Overzicht van het bewaarbeleid](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)

[Een nieuwe eigenaar toewijzen aan een groep zonder eigenaar](https://support.microsoft.com/office/86bb3db6-8857-45d1-95c8-f6d540e45732)

[Verlopen verval van Microsoft 365-groepen configureren](https://docs.microsoft.com/azure/active-directory/active-directory-groups-lifecycle-azure-portal)

[Automatische verlenging op basis van activiteiten](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)
