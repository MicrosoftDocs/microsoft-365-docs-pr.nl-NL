---
title: Microsoft Productivityity-privacy
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ROBOTS: NOINDEX, NOFOLLOW
description: Hoe de privacy van de productiviteits score wordt beschermd.
ms.openlocfilehash: 62ff3a9f0434421cbe1115f13376e92bd9f3cac9
ms.sourcegitcommit: fa26da0be667d4be0121c52b05488dc76c5d626c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/29/2020
ms.locfileid: "48794975"
---
# <a name="privacy-controls-for-productivity-score"></a>Privacy-instellingen voor de productiviteits Score

Met productiviteits Score kunnen organisaties transformeren hoe werk wordt gedaan met metrieken waarmee u de hoeveelheid werk en de technologie van mensen en technologie kunt meten en verbeteren. U krijgt inzicht in de manier waarop uw organisatie werkt, biedt metrische gegevens waarmee u zich kunt concentreren op het inschakelen van verbeterde functies.  U kunt de metrieken ook verbinden met acties om u te helpen bij het bijwerken van vaardigheden en systemen, zodat iedereen de beste werk kunnen doen. De Score weerspiegelt de prestaties van uw organisatie en stelt u ook in staat uw score veilig te vergelijken met andere organisaties zoals u.  Voor meer informatie raadpleegt u [overzicht van de productiviteits Score](productivity-score.md).

Uw privacy is belangrijk voor ons. Zie [de privacyverklaring van Microsoft](https://privacy.microsoft.com/privacystatement)voor informatie over de bescherming van uw privacy. Productiviteits Score biedt vitale informatie over de manier waarop de personen in uw organisatie samenwerken met besturingselementen, om te controleren of de informatie op de gewenste manier wordt gewijzigd, maar niet in de mate van de vertrouwen in Microsoft.

In het gebied personen ervaring zijn metrische gegevens beschikbaar op organisatieniveau en alle gebruikers in uw Microsoft 365-Tenant inbegrepen. In dit gebied ziet u hoe mensen Microsoft 365 gebruiken door te kijken naar de categorieën voor de samenwerking van inhoud, mobiliteit, vergaderingen, teamwork en communicatie. Om u te helpen met het overstappen op de juiste set personen die mogelijk ondersteuning bieden voor onze producten, hebben we u ook geholpen met informatie over het afzonderlijke niveau. Terwijl we dit niveau van doorzichtigheid bieden, bieden we u ook een aantal besturingselementen aan om u te helpen bij het invoeren van uw interne beleidsbehoeften.
Met de volgende besturingselementen krijgt u:

- Flexibele beheerdersrollen om te bepalen wie de informatie in de productiviteits Score kan zien.
- De mogelijkheid om metrieken op gebruikersniveau te delegeren.
- Mogelijkheid om te profiteren van mensen die zich afmelden.
- De mogelijkheid om af te melden bij het gebied personen

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>Flexibele beheerdersrollen om te bepalen wie de informatie in de productiviteits Score kan zien

Voor het weergeven van de volledige productiviteits Score, waaronder metrische gegevens voor tenantniveau en gegevens per gebruiker, moet u een van de volgende beheerdersrollen maken:

- Algemene beheerder
- Exchange-beheerders
- SharePoint-beheerder
- Skype voor Bedrijven-beheerder
- Teams-beheerder
- Algemene lezer
- Rapporten lezer

Wijs de rol rapporten lezer toe aan iedereen die verantwoordelijk is voor het wijzigen van het beheer en de aanneming. Deze rol biedt gebruikers toegang tot de volledige ervaring, waaronder metrische informatie over tenantniveau en Details per gebruikersniveau.

Het rapport personen ervaring bevat gegevens per activiteit per gebruiker voor elke detailpagina van elke categorie. Wijs een aangepaste rol met de naam Gebruiksoverzicht rapporten (beschikbaar in 29 oktober 2020) toe om toegang te krijgen tot alleen de samengestelde metrische gegevens van de personen ervaring. Deze rol moet via PowerShell-cmdlets worden toegewezen, zodat deze wordt toegewezen via het Microsoft-Beheercentrum op 11/15/2020.

De rol van lezers voor Gebruiksoverzicht van rapporten toewijzen met PowerShell:

- Voer de volgende PowerShell uit:

```powershell
Connect-AzureAD
$role=Get-AzureADDirectoryRole -Filter "roleTemplateId eq '75934031-6c7e-415a-99d7-48dbd49e875e'"
Get-AzureADDirectoryRoleMember -ObjectId $role.ObjectId
$u=Get-AzureADUser -ObjectId <user upn>
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId $u.ObjectId
```

</br>

:::image type="content" source="../../media/communicationspage.jpg" alt-text="Communicatie pagina in productiviteits rapporten.":::

## <a name="de-identification-of-user-level-metrics"></a>De identificatie van gebruikers metrieken

U moet een globale beheerder zijn als u de gegevens die worden verzameld voor alle rapporten anoniem wilt maken. Met deze actie worden identificeerbare informatie zoals namen van gebruikers, groepen en sites in alle rapporten verborgen, waaronder de productiviteits Score en het gebruik van Microsoft 365.

1. Ga in het Beheercentrum naar instellingen voor **Settings**   >   **organisatie** en kies op het tabblad **Services** de optie **rapporten** .
2. Selecteer  **rapporten** en kies vervolgens voor het  **weergeven van anonieme id's voor namen van gebruikers, groepen en sites in de rapporten voor de productiviteits Score en de gebruiksrapporten** . Deze instelling wordt toegepast op de gebruiksrapporten en de sjabloon-app.
3. Selecteer  **Save Changes** .

:::image type="content" source="../../media/orgsettings_anonymous.jpg" alt-text="Communicatie pagina in productiviteits rapporten.":::

## <a name="capability-to-opt-out-of-people-experiences"></a>Mogelijkheid om te profiteren van mensen die zich afmelden

Wanneer de Score van de productiviteit algemeen beschikbaar is, kunt u ook afmelden voor het gebied personen die van de productiviteits Score werken. Als u zich afmeldt, kan niemand van de organisatie deze metrieken zien en uw organisatie wordt verwijderd uit een berekening met communicatie, vergaderingen, teamwerk en de samenwerking van de inhoud.

1. Ga in het Beheercentrum naar instellingen voor **Settings**   >   **organisatie** en kies op het tabblad **Services** de optie **rapporten** .
2. Selecteer  **rapporten** en schakel vervolgens het selectievakje in  **om te voorkomen dat gebruikersgegevens van Microsoft 365 kunnen gebruiken voor gebruikerservaring inzichten.** .. Als u meer wilt weten over het wijzigen van de instellingen voor het delen van gegevens voor eindpunten in de intune Configuration Manager, klikt u op meer **informatie** .
3. Selecteer  **Save Changes** .

:::image type="content" source="../../media/orgsettingspageoptout.jpg" alt-text="Communicatie pagina in productiviteits rapporten.":::