---
title: Verloopbeleid voor groepen
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
description: Meer informatie over verloopbeleid voor Microsoft 365-groepen.
ms.openlocfilehash: bda4bfbbef4e0d145c55b2a49b4d1203c6a7b1f0
ms.sourcegitcommit: 4f82fa7270e7ec6c6dd80329f28612e1f3289b22
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/05/2020
ms.locfileid: "46572137"
---
# <a name="microsoft-365-group-expiration-policy"></a>Verloopbeleid voor groepen Microsoft 365-groep

Met de toename van het gebruik van Microsoft 365-groepen kunnen beheerders en gebruikers ongebruikte groepen op een andere manier wissen. Met een verloopbeleid kunt u inactief groepen verwijderen uit het systeem en de kenmerken opschonen.

Wanneer een groep vervalt, worden ook alle bijbehorende services (het postvak, planner, SharePoint-site, team, etc.) verwijderd.

Wanneer een groep verloopt, betekent dit dat deze gedurende 30 dagen nog langer kan worden hersteld.

Beheerders kunnen een verloopperiode opgeven en alle inactieve groepen die het einde van die periode bereiken en niet worden vernieuwd. De verloopperiode begint wanneer de groep is gemaakt, of op de datum waarop deze het laatst is vernieuwd. Groepseigenaren ontvangen automatisch een e-mailbericht vóór de vervaldatum, zodat ze de groep kunnen verlengen met een ander verloopinterval. Teams-gebruikers zien permanente meldingen in teams.

Groepen die actief worden gebruikt, worden automatisch verlengd. Een groep wordt automatisch verlengd met een van de volgende acties:
- SharePoint: weergeven, bewerken, downloaden, verplaatsen, delen of uploaden van bestanden.
- Outlook: u kunt deelnemen aan een groep of een groepsbericht lezen of schrijven in de groep, en bijvoorbeeld een bericht (de webversie van Outlook).
- Teams: u bezoekt een team kanaal.

> [!IMPORTANT]
> Als u het verloopbeleid wijzigt, wordt de vervaldatum voor elke groep opnieuw berekend door de service. Wanneer de groep is gemaakt, wordt deze altijd vanaf de datum geteld en wordt het nieuwe verloopbeleid toegepast.

Het is belangrijk om te weten dat de vervaldatum standaard is uitgeschakeld. Beheerders moeten hun organisatie voor hun organisatie inschakelen als ze het willen gebruiken.

> [!NOTE]
> Als u het verloopbeleid voor Microsoft 365-groepen configureert en gebruikt, is het raadzaam om Azure AD Premium-licenties toe te wijzen aan de leden van alle groepen waarop u het verloopbeleid wilt toepassen. Zie voor meer informatie [Aan de slag met Azure Active Directory Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium).

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a>Wie kan het verloopbeleid voor Microsoft 365-groepen configureren en gebruiken?

|Rol|Wat ze kunnen doen|
|---------|---------|
|Globale beheerder (in azure, de beheerder van het bedrijf), gebruikersbeheerder|U kunt de instellingen voor het verloopbeleid van Microsoft 365-groepen maken, lezen, bijwerken of verwijderen.|
|Gebruiker|Een Microsoft 365-groep vernieuwen of [herstellen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted) waarvan hij of zij de eigenaar is|

## <a name="how-to-set-the-expiration-policy"></a>Het verloopbeleid instellen

Zoals hierboven aangegeven, is vervaldatum standaard uitgeschakeld. Een beheerder dient het verloopbeleid in te schakelen en de eigenschappen in te stellen dat deze van kracht worden. Als u dit wilt inschakelen, gaat u naar de groepen van **Azure Active Directory (Aad)**  >  **Groups**  >  **verloopt**. U kunt hier de standaardlevensduur voor groepen instellen en opgeven hoe ver van tevoren u de eerste en tweede verloop bevestiging wilt naar de eigenaar van de groep.

De levensduur van de groep wordt in dagen opgegeven en kan worden ingesteld op 180, 365 of op een aangepaste waarde die u opgeeft. De aangepaste waarde moet ten minste 30 dagen bedragen.

Als de groep geen eigenaar heeft, wordt de vervaldatum van de e-mail naar een opgegeven beheerder verzonden.

U kunt het beleid instellen voor al uw groepen, alleen geselecteerde groepen of het geheel uitschakelen door **geen**te selecteren. U kunt momenteel geen verschillende beleidsregels voor verschillende groepen hebben.

![Schermafbeelding van instellingen voor groeps verloop in azure Active Directory](../../media/azure-groups-expiration-settings.png)

## <a name="how-expiration-and-renewal-work"></a>De werking van verlopen en verlengen

Het verloopbeleid werkt als volgt: 

- Over een maand voordat verstrijkt, controleert het systeem of er groepsactiviteit is uitgevoerd sinds de groep is gemaakt of sinds het begin van de huidige verlengings cyclus.

- Als eerdere activiteit wordt gedetecteerd, is de vervaldatum op dat moment uitgebreid met het aantal dagen dat is opgegeven in het verloopbeleid.

- Als de voorafgaande activiteit niet wordt gedetecteerd, wordt het systeem voortgezet voor activiteiten totdat de vervaldatum. Als activiteiten worden gedetecteerd, wordt op dat moment de vervaldatum van het opgegeven bedrag verder gewijzigd.

30 dagen voordat de groep vervalt, ontvangt de eigenaren van de groep (of de e-mailadressen die u hebt opgegeven voor groepen die geen eigenaar zijn) een e-mailbericht waarin staat dat ze de groep gemakkelijk kunnen verlengen. Als ze het niet verlengen, ontvangen ze een ander e-mailadres van 15 dagen voordat het verloopt. Als het nog steeds niet wordt vernieuwd, ontvangen ze nog één e-mail melding voor de dag voordat het verloopt. (Zodra de groep is vernieuwd, worden na het verlengen van de nieuwe vervaldatum geen e-mail meer verzonden.)

Groepseigenaren worden via e-mail op de hoogte gesteld. Als de groep is gemaakt via planner, SharePoint of een andere app, worden de verval meldingen altijd via e-mail weergegeven. Als de groep is gemaakt via teams ontvangt de groepseigenaar een melding voor het verlengen via de sectie activiteit. Het wordt afgeraden om het verloop van een groep in te schakelen als de eigenaar van de groep geen geldig e-mailadres heeft.

Als geen van de eigenaren of beheerders de groep vóór de einddatum verlengt, en automatische verlenging niet wordt uitgevoerd omdat de groep niet voldoet aan de vereisten voor het automatisch verlengen van de vereisten, kan de beheerder de groep nog maar dertig dagen na verloop herstellen. Zie voor meer informatie: [een verwijderde Microsoft 365-groep herstellen](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group).

## <a name="how-expiry-works-with-retention-policies"></a>Hoe vervaldatum werkt met bewaarbeleid

Als u het bewaarbeleid voor beveiliging en compliance voor groepen hebt ingesteld, werkt het verloopbeleid naadloos samen met het bewaarbeleid. Wanneer een groep verloopt, worden de gesprekken van de groep in het vak e-mail en bestanden van de groepssite bewaard in de Bewaar container voor het specifieke aantal dagen dat is gedefinieerd in het bewaarbeleid. Gebruikers zien de groep niet, of de inhoud ervan, na verloop.

## <a name="related-articles"></a>Verwante artikelen

[Overzicht van bewaarbeleid](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)

[Een nieuwe eigenaar toewijzen aan een groep zonder eigenaar](https://support.microsoft.com/office/86bb3db6-8857-45d1-95c8-f6d540e45732)

[Verloopt Microsoft 365 groepen configureren](https://docs.microsoft.com/azure/active-directory/active-directory-groups-lifecycle-azure-portal)

[Automatisch verlengen op basis van activiteiten](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)
