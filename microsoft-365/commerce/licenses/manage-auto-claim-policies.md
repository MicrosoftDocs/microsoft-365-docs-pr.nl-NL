---
title: Beleidsregels voor automatisch claimen beheren
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
description: Meer informatie over het maken en beheren van beleidsregels voor automatische claimen die automatisch licenties toewijzen aan gebruikers voor bepaalde apps.
ms.custom:
- AdminSurgePortfolio
- commerce
search.appverid:
- MET150
ms.openlocfilehash: c1715d2420315c6e645303c959512a45d47fddfe
ms.sourcegitcommit: bf9e0091e5bdc78d9b23be64583eb816bb059eb2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/12/2021
ms.locfileid: "50759204"
---
# <a name="manage-auto-claim-policies"></a>Beleidsregels voor automatisch claimen beheren

Met een beleid voor automatisch claimen kunnen gebruikers automatisch een licentie claimen voor een product wanneer ze zich voor het eerst aanmelden bij een app. Als beheerder wijst u licenties meestal handmatig toe aan gebruikers of met behulp van licenties op basis van groepen. Door beleidsregels voor automatisch claimen te gebruiken, beheert u de producten waarvoor gebruikers automatisch licenties kunnen claimen. U kunt ook bepalen van welke producten deze licenties afkomstig zijn.

Nadat u een beleid voor automatisch claimen hebt uitgevoerd, kunt u de volgende taken uitvoeren om het beleid te beheren:

- [Het beleid in- of uitschakelen](#turn-a-policy-on-or-off)
- [De beleidsvriendelijke naam bewerken](#edit-the-policy-friendly-name)
- [Back-upproducten toevoegen of verwijderen](#add-or-remove-backup-products)
- [Apps en services toewijzen beheren](#change-the-assigning-apps-and-services)
- [De toewijzingsorder wijzigen](#change-the-assigning-order-for-backup-products)
- [Een beleidsrapport weergeven](#view-an-auto-claim-policy-report)

> [!IMPORTANT]
> Beleidsregels voor automatisch claimen zijn momenteel alleen beschikbaar voor Microsoft Teams. Er zijn in de toekomst meer producten beschikbaar die u kunt gebruiken.

## <a name="before-you-begin"></a>Voordat u begint

U moet een globale, facturerings- of gebruikersbeheerder zijn om beleidsregels voor automatisch claimen te maken en te beheren. Zie [Over beheerdersrollen in Microsoft 365](../../admin/add-users/about-admin-roles.md) voor meer informatie.

## <a name="turn-the-auto-claim-policy-feature-on-or-off"></a>De functie beleid voor automatisch claimen in- of uitschakelen

Standaard is de functie beleid voor automatisch claimen uitgeschakeld. Voordat u de functie kunt gebruiken, moet u deze eerst in- en uit- zetten. Nadat u de functie hebt in- of uit- of nadat u de functie hebt in- of uit te voeren, kunt u een beleid voor automatisch claimen maken.

### <a name="turn-on-auto-claim-policies"></a>Beleid voor automatisch claimen in- en uitlijnen

1. Ga in het beheercentrum naar de pagina  \> **Factureringslicenties** en selecteer vervolgens het <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">tabblad Beleid voor</a> automatisch claimen.
2. Selecteer de knop Instelling in het midden van de **pagina.**

### <a name="turn-off-auto-claim-policies"></a>Beleid voor automatisch claimen uitschakelen

1. Ga in het beheercentrum naar de pagina **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">organisatie-instellingen.</a>
2. Selecteer apps en services die eigendom zijn van **gebruikers onder aan de tabel.**
3. In het rechterdeelvenster kunt u het vakje uitschakelen voor Gebruikers automatisch licenties laten claimen wanneer ze zich de eerste keer **aanmelden.**

Als u al een actief beleid hebt, maar u niet wilt dat meer gebruikers licenties claimen, kunt u [het beleid uitschakelen.](#turn-a-policy-on-or-off) Wanneer u een beleid voor automatisch claimen uit schakelen, kunnen vanaf dat moment geen gebruikers meer een licentie claimen. Gebruikers die al een licentie hebben aangevraagd, raken hun licentie niet kwijt.

## <a name="create-an-auto-claim-policy"></a>Een beleid voor automatisch claimen maken

Het <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">tabblad Beleid voor automatisch claimen</a> bevat het beleid dat u maakt. Op dit tabblad ziet u: de naam van het beleid, de app die is gekoppeld aan het beleid, het product dat is toegewezen aan het beleid, het aantal beschikbare licenties en de status van het beleid.

Wanneer u een beleid voor automatisch claimen maakt, kunt u er een back-upproduct aan toevoegen. Als het primaire product geen licenties meer heeft, wordt het back-upproduct gebruikt om licenties toe te wijzen aan gebruikers. U kunt maximaal vier back-upproducten toevoegen en [de volgorde wijzigen waarin ze worden gebruikt.](#change-the-assigning-order-for-backup-products) Zie Back-upproducten [toevoegen of verwijderen voor meer informatie.](#add-or-remove-backup-products)

> [!NOTE]
> Op dit moment kunt u slechts één beleid voor automatisch claimen maken. Het aantal beleidsregels dat u kunt maken, wordt groter naarmate meer producten deze functie kunnen gebruiken.

1. Ga in het beheercentrum naar de pagina  \> **Factureringslicenties** en selecteer vervolgens het <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">tabblad Beleid voor</a> automatisch claimen.
2. Selecteer **Een beleid toevoegen.**
3. Voer op de pagina Naam van dit **autoclaimbeleid** een naam voor het beleid in en selecteer **Volgende**.
4. Selecteer op **de pagina Een auto-claim-app** en -product instellen een app en het abonnement waar u licenties van wilt toewijzen.
5. Als u een back-upproduct wilt toevoegen, selecteert u **Een back-upproduct toevoegen aan dit** beleid en selecteert u het product in de lijst.
6. Selecteer **Volgende**.
7. Schakel op **de pagina Apps** selecteren de vakken uit of selecteer de vakken voor de apps die u wilt uitsluiten of opnemen met de licentie en selecteer vervolgens **Volgende.**
8. Als u een of meer back-upproducten hebt toegevoegd, herhaalt u stap 7 voor elk product. Ga anders naar stap 9.
9. Controleer op **de pagina Controleren** en voltooien de nieuwe beleidsgegevens, pas de benodigde wijzigingen aan en selecteer beleid **maken.**
10. Selecteer **Sluiten**.

## <a name="turn-a-policy-on-or-off"></a>Een beleid in- of uitschakelen

Wanneer u een beleid uit schakelen, kunnen geen gebruikers meer licenties claimen onder dat beleid. De wijziging is niet van invloed op gebruikers die al licenties hebben aangevraagd onder dat beleid.

1. Ga in het beheercentrum naar de pagina  \> **Factureringslicenties** en selecteer vervolgens het <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">tabblad Beleid voor</a> automatisch claimen.
2. Selecteer het beleid dat u wilt bewerken.
3. Schakel in het detailvenster onder **Dit beleid in-** of uitschakelen het selectievakje in of uit.
4. Selecteer **Opslaan om** het detailvenster te sluiten.

## <a name="edit-the-policy-friendly-name"></a>De beleidsvriendelijke naam bewerken

1. Ga in het beheercentrum naar de pagina  \> **Factureringslicenties** en selecteer vervolgens het <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">tabblad Beleid voor</a> automatisch claimen.
2. Selecteer het beleid dat u wilt bewerken.
3. Selecteer bewerken in het detailvenster in **de** sectie **Beleidsnaam.**
4. Voer een nieuwe beleidsnaam in en selecteer **Opslaan.**
5. Selecteer **Opslaan om** het detailvenster te sluiten.

## <a name="add-or-remove-backup-products"></a>Back-upproducten toevoegen of verwijderen

Wanneer u een beleid maakt, voegt u er een product aan toe. Licenties worden vervolgens automatisch toegewezen aan gebruikers uit die groep licenties. U kunt op elk moment producten toevoegen of verwijderen voor een beleid voor automatisch claimen. Als u al één product aan het beleid hebt gekoppeld, worden producten die u toevoegt beschouwd als back-upproducten. Wanneer het beschikbare aantal licenties van het eerste product is opgebruikt, wordt in het beleid het volgende back-upproduct in de lijst gebruikt om licenties toe te wijzen. U [kunt de volgorde van de lijst met producten naar](#change-the-assigning-apps-and-services) eigen goed gebruik wijzigen.

Wanneer u een back-upproduct verwijdert, wordt het niet meer gebruikt om licenties toe te wijzen. Gebruikers met een bestaande licentie hebben die licentie nog steeds, maar geen nieuwe gebruikers kunnen licenties voor dat product ontvangen.

> [!NOTE]
> Een autoclaimbeleid moet ten minste één product bevatten. U kunt niet alle producten uit een beleid verwijderen. Als u geen licenties meer wilt toewijzen vanuit een specifiek beleid voor automatisch claimen, kunt u [het beleid uitschakelen.](#view-an-auto-claim-policy-report)

### <a name="add-a-backup-product"></a>Een back-upproduct toevoegen

1. Ga in het beheercentrum naar de pagina  \> **Factureringslicenties** en selecteer vervolgens het <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">tabblad Beleid voor</a> automatisch claimen.
2. Selecteer het beleid dat u wilt bewerken.
3. Selecteer in het detailvenster onderaan De optie **Een back-upproduct toevoegen aan dit beleid.**
    > [!NOTE]
    > Als u deze koppeling niet ziet, is dit omdat er slechts één product aan uw account is gekoppeld.
4. Gebruik in **het deelvenster Een product** toevoegen de vervolgkeuzelijn om een product te kiezen dat u wilt toevoegen aan het beleid en selecteer vervolgens **Toevoegen.**
5. Selecteer **Opslaan om** het detailvenster te sluiten.

### <a name="remove-a-backup-product"></a>Een back-upproduct verwijderen

1. Ga in het beheercentrum naar de pagina  \> **Factureringslicenties** en selecteer vervolgens het <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">tabblad Beleid voor</a> automatisch claimen.
2. Selecteer het beleid dat u wilt bewerken.
3. Selecteer in het detailvenster onder aan de optie **Een product verwijderen.**
4. Schakel in **het deelvenster Een product verwijderen uit** het beleidsvenster het selectievakje in voor het beleid dat u wilt verwijderen en selecteer **opslaan.**
5. Sluit het detailvenster.

## <a name="change-the-assigning-apps-and-services"></a>De toewijzing van apps en services wijzigen

Aan elk product is een verzameling apps en services gekoppeld.
Voor elk product in uw beleid voor automatisch claimen kunt u opgeven welke apps en services moeten worden gebruikt wanneer een gebruiker automatisch een licentie aan dat product wordt toegewezen.

1. Ga in het beheercentrum naar de pagina  \> **Factureringslicenties** en selecteer vervolgens het <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">tabblad Beleid voor</a> automatisch claimen.
2. Selecteer het beleid dat u wilt bewerken.
3. Selecteer bewerken in het detailvenster onder **Apps en services.**
4. Selecteer in **het deelvenster Apps** en services in de vervolgkeuzekeuzepagina **Product** één product of selecteer **Alle producten.**
5. De selectievakjes voor apps en services die gebruikers al dan niet mogen gebruiken, in- of uit.
6. Wanneer u klaar bent, selecteert u **Opslaan** en sluit u het detailvenster.

## <a name="change-the-assigning-order-for-backup-products"></a>De toewijzingsorder voor back-upproducten wijzigen

Als u back-upproducten hebt toegewezen aan het beleid, kunt u de volgorde wijzigen waarin ze worden gebruikt voor het toewijzen van licenties wanneer gebruikers zich aanmelden bij de app.

1. Ga in het beheercentrum naar de pagina  \> **Factureringslicenties** en selecteer vervolgens het <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">tabblad Beleid voor</a> automatisch claimen.
2. Selecteer het beleid dat u wilt bewerken.
3. Schakel in het detailvenster in de sectie **Productlicenties** het vakje in naast het product dat u wilt verplaatsen en selecteer vervolgens **Omhoog** of **Omlaag gaan.**
4. Herhaal stap 3 voor elk product dat u opnieuw wilt ordenen.
5. Wanneer u klaar bent met het opnieuw ordenen van de producten, **selecteert** u Opslaan om het detailvenster te sluiten.

## <a name="view-an-auto-claim-policy-report"></a>Een rapport over het beleid voor automatisch claimen weergeven

1. Ga in het beheercentrum naar de pagina  \> **Factureringslicenties** en selecteer vervolgens het <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">tabblad Beleid voor</a> automatisch claimen.
2. Selecteer **Rapport weergeven.** Op **de pagina Beleidsbeleid voor automatisch claimen** worden alle licenties weergegeven die zijn toegewezen aan elk beleid in de afgelopen 90 dagen. Standaard wordt op de pagina de afgelopen 90 dagen weergegeven.
3. Als u de weergegeven periode wilt wijzigen, selecteert u de vervolgkeuzelijst Afgelopen **30** dagen. U kunt rapporten van de afgelopen 1, 7, 30 en 90 dagen bekijken.

## <a name="next-steps"></a>Volgende stappen

U kunt regelmatig terugkeren naar het tabblad **Beleid** voor automatisch claimen om een lijst weer te geven met gebruikers die licenties hebben aangevraagd onder het beleid dat u hebt gemaakt.

## <a name="related-content"></a>Verwante onderwerpen

[Licenties toewijzen aan gebruikers](../../admin/manage/assign-licenses-to-users.md) (artikel)\
[Abonnementslicenties kopen](buy-licenses.md) of verwijderen (artikel)\
[Abonnementen en licenties begrijpen](subscriptions-and-licenses.md) (artikel)
