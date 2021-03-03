---
title: Microsoft Productiviteitsscore - Privacy
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
description: Hoe privacy wordt beschermd met de productiviteitsscore.
ms.openlocfilehash: b522c40cba746f3a4ede2404cf671607d62a3282
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406558"
---
# <a name="privacy-controls-for-productivity-score"></a>Privacyinstellingen voor productiviteitsscore

Productiviteitsscore biedt inzicht in de digitale transformatie-reis van uw organisatie door het gebruik van Microsoft 365 en de technologie-ervaringen die dit ondersteunen.  De score van uw organisatie weerspiegelt afmetingen voor personen en technologie-ervaring en kan worden vergeleken met benchmarks van organisaties die lijken op die van u. Bekijk het overzicht van de [productiviteitsscore voor meer informatie.](productivity-score.md)

Uw privacy is belangrijk voor Microsoft. Zie de privacyverklaring van Microsoft voor meer informatie over hoe we uw [privacy beschermen.](https://privacy.microsoft.com/privacystatement) Productiviteitsscore biedt u, als IT-beheerder van uw organisatie, toegang tot privacy-instellingen om ervoor te zorgen dat u actie kunt ondernemen op de informatie over de productiviteitsscore die u bekijkt, zonder dat dit ten koste gaat van het vertrouwen van uw organisatie in Microsoft.

In het gebied Met gebruikerservaringen zijn meetwaarden alleen beschikbaar op organisatieniveau. In dit gebied wordt gekeken hoe mensen Microsoft 365 gebruiken door de categorieën samenwerken aan inhoud, mobiliteit, vergaderingen, teamwerk en communicatie te bekijken. We stellen u in staat verschillende controleniveaus in te stellen om u te helpen aan uw interne privacybeleidsbehoeften te voldoen.
Met de besturingselementen hebt u de volgende informatie:

- Flexibele beheerdersrollen om te bepalen wie de informatie in productiviteitsscore kan zien.
- De mogelijkheid om het gebied met gebruikerservaringen af te zien.

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>Flexibele beheerdersrollen om te bepalen wie de informatie in productiviteitsscore kan zien

Als u de volledige productiviteitsscore wilt bekijken, moet u een van de volgende beheerdersrollen hebben:

- Algemeen beheerder
- Exchange-beheerders
- SharePoint-beheerder
- Skype voor Bedrijven-beheerder
- Teams-beheerder
- Algemene lezer
- Rapportenlezer
- Gebruiksoverzicht rapportenlezer

Wijs de rol Rapportenlezer of Overzichtsrapportlezer Gebruiksoverzicht toe aan iedereen die verantwoordelijk is voor wijzigingsbeheer en acceptatie, maar niet per se een IT-beheerder. Met deze rol hebben ze toegang tot de volledige productiviteitsscore in het Microsoft 365-beheercentrum.

De rol Rapportenlezer gebruiksoverzicht moet worden toegewezen via PowerShell-cmdlets totdat deze later in 2020 vanuit het Microsoft 365-beheercentrum kan worden toegewezen.

De rol Rapportenlezer Gebruiksoverzicht toewijzen met PowerShell:

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


## <a name="capability-to-opt-out-of-people-experiences"></a>Mogelijkheid om gebruikerservaringen af te zien

U kunt zich ook af van het gebied met gebruikerservaringen van Productiviteitsscore. Als u dit niet kiest, kan niemand van uw organisatie deze statistieken bekijken en wordt uw organisatie verwijderd uit berekeningen die communicatie, vergaderingen, teamwerk, samenwerking aan inhoud en mobiliteit omvatten. U moet een globale beheerder zijn om uw organisatie af te melden van de rapporten met ervaringen van personen.

Als u zich wilt uiten:

1. Ga in het beheercentrum naar **Instellingen**   >   **voor productiviteitsscore**  >  **organisatie-instellingen.**
2. Vink het selectievakje met de tekst  **'Microsoft 365-gebruiksgegevens** mogen worden gebruikt voor inzichten van personen' uit. Als u wilt weten hoe u instellingen voor het delen van gegevens voor Eindpuntanalyse wijzigt in Intune Configuration Manager, selecteert u **Meer informatie.**
3. Selecteer **Opslaan.**

:::image type="content" source="../../media/orgsettingspageoptout.png" alt-text="Pagina met organisatie-instellingen waar u gebruikerservaringen kunt uitschakelen.":::
