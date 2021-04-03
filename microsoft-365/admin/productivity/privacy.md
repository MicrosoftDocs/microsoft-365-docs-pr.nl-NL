---
title: Microsoft Productiviteitsscore - Privacy
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
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
description: Hoe privacy wordt beschermd met de productiviteitsscore.
ms.openlocfilehash: 5b5997532ddcd1fdf43b4124f8e2d8183bb3d89e
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579168"
---
# <a name="privacy-controls-for-productivity-score"></a>Privacybesturingselementen voor productiviteitsscore

Productiviteitsscore biedt inzicht in de digitale transformatie van uw organisatie via het gebruik van Microsoft 365 en de technologieervaringen die dit ondersteunen.  De score van uw organisatie weerspiegelt metingen voor mensen en technologieervaringen en kan worden vergeleken met benchmarks van organisaties die vergelijkbaar zijn met die van u. Bekijk het overzicht productiviteitsscore voor meer [informatie.](productivity-score.md)

Uw privacy is belangrijk voor Microsoft. Zie de privacyverklaring van Microsoft voor meer informatie over het beschermen [van uw privacy.](https://privacy.microsoft.com/privacystatement) Productiviteitsscore biedt u, als IT-beheerder van uw organisatie, toegang tot privacy-instellingen om ervoor te zorgen dat de productiviteitsscoregegevens die u bekijkt, kunnen worden gebruikt, zonder dat dit ten koste gaat van het vertrouwen dat uw organisatie in Microsoft stelt.

In het gebied met ervaringen van personen zijn alleen meetwaarden beschikbaar op organisatieniveau. In dit gebied wordt bekeken hoe mensen Microsoft 365 gebruiken door te kijken naar de categorieën samenwerking, mobiliteit, vergaderingen, teamwerk en communicatie. We stellen u in staat met verschillende niveaus van besturingselementen om u te helpen aan uw interne privacybeleidsbehoeften te voldoen.
De besturingselementen geven u het volgende:

- Flexibele beheerdersrollen om te bepalen wie de informatie kan zien in productiviteitsscore.
- De mogelijkheid om af te zien van het gebied met ervaringen van personen.

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>Flexibele beheerdersrollen om te bepalen wie de informatie kan zien in productiviteitsscore

Als u de volledige productiviteitsscore wilt weergeven, moet u een van de volgende beheerdersrollen hebben:

- Algemeen beheerder
- Exchange-beheerders
- SharePoint-beheerder
- Skype voor Bedrijven-beheerder
- Teams-beheerder
- Algemene lezer
- Rapportenlezer
- Gebruiksoverzicht rapportenlezer

Wijs de rol Rapportenlezer of de rol Overzichtsrapporten voor gebruik toe aan iedereen die verantwoordelijk is voor wijzigingsbeheer en -acceptatie, maar niet per se een IT-beheerder. Met deze rol hebben ze toegang tot de volledige productiviteitsscore in het Microsoft 365-beheercentrum.

De rol Gebruikersoverzichtsrapportenlezer moet worden toegewezen via PowerShell-cmdlets totdat deze later in 2020 vanuit het Microsoft 365-beheercentrum kan worden toegewezen.

De rol Overzichtsrapporten voor gebruik toewijzen met PowerShell:

- Voer de volgende PowerShell uit:

```powershell
Connect-AzureAD
Enable-AzureADDirectoryRole -RoleTemplateId '75934031-6c7e-415a-99d7-48dbd49e875e'
$role=Get-AzureADDirectoryRole -Filter "roleTemplateId eq '75934031-6c7e-415a-99d7-48dbd49e875e'"
Get-AzureADDirectoryRoleMember -ObjectId $role.ObjectId
$u=Get-AzureADUser -ObjectId <user upn>
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId $u.ObjectId
```

</br>


## <a name="capability-to-opt-out-of-people-experiences"></a>Mogelijkheid om af te zien van ervaringen met personen

U kunt zich ook voor het gebied van productiviteitsscore voor personen afkissen. Als u zich afket, kan niemand van uw organisatie deze metrische gegevens bekijken en wordt uw organisatie verwijderd uit berekeningen die betrekking hebben op communicatie, vergaderingen, teamwerk, samenwerking met inhoud en mobiliteit. U moet een globale beheerder zijn om uw organisatie af te melden van de rapporten met gebruikerservaringen.

Als u zich wilt opt-outen:

1. Ga in het beheercentrum naar **Instellingen**   >   **Organisatie-instellingen**  >  **Productiviteitsscore**.
2. Vink het selectievakje uit met de tekst  **Toestaan dat Microsoft 365-gebruiksgegevens** worden gebruikt voor mensen die inzichten ervaren. Als u wilt weten hoe u instellingen voor het delen van gegevens wijzigt voor Endpoint Analytics in de Configuratiebeheer van Intune, selecteert u **Meer informatie.**
3. Selecteer **Opslaan.**

:::image type="content" source="../../media/orgsettingspageoptout.png" alt-text="Pagina met organisatieinstellingen waar u zich kunt afkissen van ervaringen met personen.":::
