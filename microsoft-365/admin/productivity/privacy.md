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
description: Hoe de privacy van de productiviteits score wordt beschermd.
ms.openlocfilehash: ceb19fcb7bbf2f6a58e38684604ed3b0dac2a5d4
ms.sourcegitcommit: d859ea36152c227699c1786ef08cda5805ecf7db
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/09/2020
ms.locfileid: "49604324"
---
# <a name="privacy-controls-for-productivity-score"></a>Privacy-instellingen voor de productiviteits Score

Productiviteits Score biedt inzicht in de digitale transformatie van uw organisatie door het gebruik van Microsoft 365 en de technologie ervaring ter ondersteuning van uw organisatie.  De Score van uw organisatie weerspiegelt de maten voor personen en technologieën, en kan worden vergeleken met de Bench maten van organisaties die vergelijkbaar zijn met uw organisatie. Voor meer informatie raadpleegt u het overzicht van de [productiviteits Score](productivity-score.md).

Uw privacy is belangrijk voor Microsoft. Zie [de privacyverklaring van Microsoft](https://privacy.microsoft.com/privacystatement)voor informatie over de bescherming van uw privacy. Met de productiviteits Score kunt u, als de IT-beheerder van uw organisatie, de privacy-instellingen raadplegen, zodat u zeker weet dat de informatie over de productiviteit van uw organisatie in Microsoft optreedt.

In het gebied personen ervaring zijn metrische gegevens alleen op het niveau van de organisatie verkrijgbaar. In dit gebied wordt aangegeven hoe mensen Microsoft 365 gebruiken door te kijken naar de categorieën voor de samenwerking van inhoud, mobiliteit, vergaderingen, teamwork en communicatie. U kunt verschillende niveaus met besturingselementen gebruiken om te voldoen aan de behoeften van uw interne privacybeleid.
Met de besturingselementen krijgt u:

- Flexibele beheerdersrollen om te bepalen wie de informatie in de productiviteits Score kan zien.
- De mogelijkheid om af te melden bij het gebied personen.

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>Flexibele beheerdersrollen om te bepalen wie de informatie in de productiviteits Score kan zien

Als u de volledige productiviteits score wilt bekijken, moet u een van de volgende beheerdersrollen volgen:

- Algemene beheerder
- Exchange-beheerders
- SharePoint-beheerder
- Skype voor Bedrijven-beheerder
- Teams-beheerder
- Algemene lezer
- Rapporten lezer
- Lezer rapporten van Gebruiksoverzicht

Wijs de rol van de rapporten lezer of de functie overzichtsrapporten van Gebruiksoverzicht toe aan iedereen die verantwoordelijk is voor het wijzigen van het beheer en de aanneming, maar niet noodzakelijkerwijs een IT-beheerder. Met deze functie krijgen ze toegang tot de volledige productiviteits ervaring in het Microsoft 365-Beheercentrum.

De naam van de lezer van het gebruiksoverzicht van rapporten moet via de PowerShell-cmdlets worden toegewezen, zodat de inhoud van het Microsoft 365-Beheercentrum later wordt toegewezen via 2020.

De rol van lezers voor Gebruiksoverzicht van rapporten toewijzen met PowerShell:

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


## <a name="capability-to-opt-out-of-people-experiences"></a>Mogelijkheid om te profiteren van mensen die zich afmelden

U kunt ook afmelden voor het gebied personen van de productiviteits Score. Als u zich afmeldt, kan niemand van uw organisatie deze metrische gegevens weergeven en wordt uw organisatie verwijderd uit eventuele berekeningen waarvoor communicatie, vergaderingen, teamwerk en de samenwerking van inhoud is vereist. U moet een globale beheerder zijn om u te laten weten dat uw organisatie aan de hand van de rapporten van mensen kan deelnemen.

Als u wilt deelnemen aan een plaats:

1. Ga in het Beheercentrum naar instellingen voor **Settings**   >   **organisatie** en selecteer **rapporten** op het tabblad **Services** .
2. Schakel het selectievakje uit dat  **Microsoft 365 gebruiksgegevens mogen worden gebruikt voor mensen ervaring inzichten**. Als u meer wilt weten over het wijzigen van instellingen voor het delen van gegevens voor eindpunten in de intune Configuration Manager, selecteert u meer **informatie**.
3. Selecteer  **Opslaan**.

:::image type="content" source="../../media/orgsettingspageoptout.png" alt-text="Pagina met instellingen voor organisatie waar u zich kunt afmelden voor personen in de organisatie.":::