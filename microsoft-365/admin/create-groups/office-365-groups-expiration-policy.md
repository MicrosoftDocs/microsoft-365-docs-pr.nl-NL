---
title: Verloopbeleid van een Office 365 Groep
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
description: Meer informatie over het verloopbeleid voor Office 365-groepen.
ms.openlocfilehash: c4c2f7b98247cc81b3fadc561f92084f9bd39c96
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "42809216"
---
# <a name="office-365-group-expiration-policy"></a>Verloopbeleid van een Office 365 Groep

Met de toename van het gebruik van Office 365-groepen hebben beheerders en gebruikers een manier nodig om ongebruikte groepen op te ruimen. Expiratiebeleid kan helpen bij het verwijderen van inactieve groepen uit het systeem en dingen schoner maken.

Wanneer een groep verloopt, worden ook alle bijbehorende services (het postvak, Planner, SharePoint-site, enz.) verwijderd.

Wanneer een groep verloopt, wordt deze "soft-deleted" wat betekent dat deze nog maximaal 30 dagen kan worden hersteld.

Beheerders kunnen een vervaldatum opgeven en elke inactieve groep die het einde van die periode bereikt en niet wordt verlengd, worden verwijderd. De vervaldatum begint wanneer de groep wordt gemaakt of op de datum waarop deze voor het laatst is verlengd. Groepseigenaren ontvangen automatisch een e-mail voor de vervaldatum, zodat ze de groep kunnen vernieuwen voor een ander verloopinterval. Teams-gebruikers zien aanhoudende meldingen in Teams.

Groepen die actief in gebruik zijn, worden automatisch vernieuwd. Een van de volgende acties zal een groep automatisch vernieuwen:
- SharePoint - bestanden weergeven, bewerken, downloaden, verplaatsen, delen of uploaden.
- Outlook - word lid van groep, lees of schrijf groepsbericht uit de groep en like een bericht (Web versie).
- Teams - een bezoek aan een teamkanaal.

> [!IMPORTANT]
> Wanneer u het verloopbeleid wijzigt, berekent de service de vervaldatum voor elke groep opnieuw. Het begint altijd te tellen vanaf de datum waarop de groep is gemaakt en past vervolgens het nieuwe verloopbeleid toe.

Het is belangrijk om te weten dat de vervaldatum standaard is uitgeschakeld. Beheerders moeten het inschakelen voor hun tenant als ze het willen gebruiken.

> [!NOTE]
> Als u het verloopbeleid voor Office 365-groepen configureert en gebruikt, moet u Azure AD Premium-licenties bezitten, maar niet noodzakelijkerwijs Azure AD Premium-licenties toewijzen voor de leden van alle groepen waarop het verloopbeleid wordt toegepast. Zie voor meer informatie [Aan de slag met Azure Active Directory Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium).

## <a name="who-can-configure-and-use-the-office-365-groups-expiration-policy"></a>Wie kan het verloopbeleid voor Office 365-groepen configureren en gebruiken?

|Rol|Wat ze kunnen doen|
|---------|---------|
|Globale beheerder van Office 365 (in Azure, de beheerder van het bedrijf), gebruikersbeheerder|De instellingen voor het verloop van het verloop van office 365-groepen maken, lezen, bijwerken of verwijderen.|
|Gebruiker|Een Office 365-groep die zij bezitten vernieuwen of [herstellen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted)|

## <a name="how-to-set-the-expiration-policy"></a>Het verloopbeleid instellen

Zoals hierboven vermeld, verloopt verlopen standaard. Een beheerder moet het verloopbeleid inschakelen en de eigenschappen instellen om deze van kracht te laten worden. Als u het inschakelen wilt gaan naar **Aad-groepen** > **van** > Azure Active Directory **(Verlopen.** Hier u de standaardgroepslevensduur instellen en opgeven hoe ver van tevoren u wilt dat de eerste en tweede verloopmeldingen naar de groepseigenaar gaan.

De groepslevensduur wordt opgegeven in dagen en kan worden ingesteld op 180, 365 of op een aangepaste waarde die u opgeeft. De aangepaste waarde moet ten minste 30 dagen zijn.

Als de groep geen eigenaar heeft, gaan de verlopen e-mails naar een opgegeven beheerder.

U het beleid instellen voor al uw groepen, alleen geselecteerde groepen of het volledig uitschakelen door **Geen**te selecteren. Houd er rekening mee dat u momenteel geen ander beleid voor verschillende groepen hebben.

![Schermafbeelding van instellingen voor het verlopen van groepen in Azure Active Directory](../../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a>Hoe expiraal werkt met het bewaarbeleid

Als u een instellingsbeleid hebt in het beveiligings- en nalevingscentrum voor groepen, werkt het verloopbeleid naadloos samen met het bewaarbeleid. Wanneer een groep verloopt, worden de gesprekken van de groep in de postbus en bestanden op de groepssite bewaard in de bewaarcontainer voor het specifieke aantal dagen dat in het bewaarbeleid is gedefinieerd. Gebruikers zien de groep, of de inhoud ervan, echter niet na het verstrijken.

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a>Hoe en wanneer een groepseigenaar erachter komt of zijn groepen verlopen

Groepseigenaren worden alleen per e-mail op de hoogte gebracht. Als de groep is gemaakt via Planner, SharePoint of een andere app, komen de verloopmeldingen altijd via e-mail. Als de groep is gemaakt via Teams, ontvangt de eigenaar van de groep een melding om te verlengen via de activiteitssectie. Het wordt afgeraden om de vervaldatum van een groep in te schakelen als de eigenaar van uw groep geen geldig e-mailadres heeft.

30 dagen voordat de groep verloopt, ontvangen de groepseigenaren (of de e-mailadressen die u hebt opgegeven voor groepen die geen eigenaar hebben) een e-mail waarmee ze de groep eenvoudig kunnen vernieuwen. Als ze het niet verlengen, ontvangen ze 15 dagen voor het verstrijken een andere verlengingse-mail. Als ze het nog steeds niet hebben verlengd, ontvangen ze de dag voor het verstrijken nog een e-mailmelding.

Als om de een of andere reden geen van de eigenaren of beheerders de groep verlengen voordat deze verloopt, kan de beheerder de groep nog steeds tot 30 dagen na het verstrijken herstellen. Zie voor meer informatie: [Een verwijderde Office 365-groep herstellen](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54).

## <a name="related-articles"></a>Verwante artikelen

[Overzicht van bewaarbeleid](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)

[Een nieuwe eigenaar toewijzen aan een groep zonder eigenaar](https://support.office.com/article/86bb3db6-8857-45d1-95c8-f6d540e45732)

[Verlopen van Office 365-groepen configureren](https://docs.microsoft.com/azure/active-directory/active-directory-groups-lifecycle-azure-portal)
