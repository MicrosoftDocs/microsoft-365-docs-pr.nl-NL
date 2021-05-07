---
title: Meer informatie over informatiebarrières in Microsoft 365
description: Gebruik informatiebarrières om ervoor te zorgen dat communicatie Microsoft Teams binnen uw organisatie.
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4ef3fce82a10792c8289a4a3c4e3cb5639a4d178
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "52162284"
---
# <a name="learn-about-information-barriers-in-microsoft-365"></a>Meer informatie over informatiebarrières in Microsoft 365

Microsoft-cloudservices bevatten krachtige communicatie- en samenwerkingsmogelijkheden. Maar stel dat u de communicatie en samenwerking tussen twee groepen wilt beperken om te voorkomen dat er een conflict van belang is in uw organisatie. Of misschien wilt u de communicatie en samenwerking tussen bepaalde personen binnen uw organisatie beperken om interne informatie te beschermen. Microsoft 365 communicatie en samenwerking tussen groepen en organisaties mogelijk, dus is er een manier om de communicatie en samenwerking tussen specifieke groepen gebruikers zo nodig te beperken? Met informatiebarrières kunt u dat!

Microsoft Teams, SharePoint Online en OneDrive voor Bedrijven ondersteunen informatiebarrières. Ervan uitgaande dat uw [abonnement](#required-licenses-and-permissions) informatiebarrières bevat, kan een compliancebeheerder of informatiebarrièrebeheerder beleidsregels definiëren om communicatie tussen groepen gebruikers in Microsoft Teams. Beleid voor informatiebarrière kan worden gebruikt voor situaties zoals deze:

- Gebruiker in de groep van de daghandelaar mag geen bestanden communiceren of delen met het marketingteam
- Financieel personeel dat werkt aan vertrouwelijke bedrijfsgegevens mag geen bestanden communiceren of delen met bepaalde groepen binnen hun organisatie
- Een intern team met handelsgeheim materiaal mag niet online bellen of chatten met personen in bepaalde groepen binnen hun organisatie
- Een onderzoeksteam mag alleen online bellen of chatten met een productontwikkelingsteam
- Een site voor dagtradergroep mag niet worden gedeeld of toegankelijk door iemand buiten de daghandelaargroep

> [!IMPORTANT]
> Informatiebarrières ***ondersteunen alleen** beperkingen in twee-weg. Beperkingen op een bepaalde manier, zoals marketing, kunnen communiceren en samenwerken met daghandelaars, maar daghandelaars kunnen niet communiceren en samenwerken met marketing _*_wordt_ niet ondersteund **.

Voor al deze voorbeeldscenario's (en meer) kunnen beleidsregels voor informatiebarrière worden gedefinieerd om communicatie en samenwerking te voorkomen of toe te staan in Microsoft Teams, SharePoint Online en OneDrive. Dergelijke beleidsregels kunnen voorkomen dat personen bellen of chatten met personen die ze niet mogen bellen of kunnen communiceren met specifieke groepen in Microsoft Teams. Wanneer het beleid voor informatiebarrière van kracht is, worden SharePoint Online- of OneDrive-controles uitgevoerd om communicatie en samenwerking te voorkomen (of toe te staan) (zoals gedefinieerd in beleidsregels voor informatiebarrière) wanneer gebruikers die onder dit beleid vallen, proberen te communiceren en samen te werken met anderen in Microsoft Teams.

Zie voor meer informatie over de gebruikerservaring met informatiebarrières:

- [Informatiebarrières in Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Informatiebarrières in SharePoint Online](/sharepoint/information-barriers)
- [Informatiebarrières in OneDrive](/onedrive/information-barriers)

> [!IMPORTANT]
> Op dit moment gelden er geen informatiebarrières voor e-mailcommunicatie. Daarnaast zijn informatiebarrières onafhankelijk van [compliancegrenzen.](set-up-compliance-boundaries.md)<p> Voordat u beleidsregels voor informatiebarrières definieert en toe te passen, moet u ervoor zorgen dat uw organisatie geen beleid Exchange adresboek [van](/exchange/address-books/address-book-policies/address-book-policies) kracht is. (Informatiebarrières zijn gebaseerd op adresboekbeleid.)

## <a name="what-happens-with-information-barriers"></a>Wat gebeurt er met informatiebarrières

Wanneer er beleidsregels voor informatiebarrière zijn, kunnen personen die geen bestanden mogen communiceren of delen met andere specifieke gebruikers deze gebruikers niet vinden, selecteren, chatten of bellen. Met informatiebarrières worden controles uitgevoerd om ongeautoriseerde communicatie en samenwerking te voorkomen. 

Informatiebarrières gelden voor Microsoft Teams (chats en kanalen), SharePoint Online en OneDrive. In Microsoft Teams informatiebarrièrebeleid de volgende soorten ongeautoriseerde communicatie bepalen en voorkomen:

- Een gebruiker zoeken
- Een lid toevoegen aan een team
- Een chatsessie met iemand starten
- Een groepschat starten
- Iemand uitnodigen om deel te nemen aan een vergadering
- Een scherm delen
- Een gesprek plaatsen
- Een bestand delen met een andere gebruiker
- Toegang tot bestand via koppeling voor delen

Als de betrokkenen zijn opgenomen in een informatiebarrièrebeleid om de activiteit te voorkomen, kunnen ze niet doorgaan. Bovendien kan iedereen die deel uit maakt van een informatiebarrièrebeleid, worden geblokkeerd voor communicatie met anderen in Microsoft Teams. Wanneer personen die te maken hebben met beleidsregels voor informatiebarrière, deel uitmaken van hetzelfde team of groepschat, kunnen ze worden verwijderd uit die chatsessies en is verdere communicatie met de groep mogelijk niet toegestaan.

Zie informatiebarrières in Microsoft Teams voor meer informatie over de [gebruikerservaring met informatiebarrières.](/MicrosoftTeams/information-barriers-in-teams)

In SharePoint Online en OneDrive, bepalen en voorkomen gegevensbarrièrebeleid de volgende soorten niet-geautoriseerde samenwerkingen:

- Een lid toevoegen aan een site
- Toegang tot site of inhoud door een gebruiker
- Site of inhoud delen met een andere gebruiker
- Een site zoeken

Zie informatiebarrières in SharePoint Online voor meer informatie [over de gebruikerservaring met informatiebarrières](/sharepoint/information-barriers)

## <a name="required-licenses-and-permissions"></a>Vereiste licenties en machtigingen

Er worden nu informatiebarrières uitgerold en zijn opgenomen in abonnementen, zoals:

- Microsoft 365 E5/A5
- Office 365 E5/A5
- Office 365 Advanced Compliance
- Microsoft 365 Compliance E5/A5
- Microsoft 365 Insider Risk Management

Zie voor meer informatie [Microsoft 365 licentie-richtlijnen voor beveiligings- & naleving.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)

Als [u beleidsregels voor informatiebarrières](information-barriers-policies.md)wilt definiëren of bewerken, moet u een van de volgende rollen krijgen:

- Microsoft 365 globale beheerder
- Office 365 globale beheerder
- Beheerder voor naleving
- IB Compliance Management

(Zie Machtigingen in het Office 365 [beveiligingscentrum & compliancecentrum](../security/defender-365-security/permissions-in-the-security-and-compliance-center.md)voor meer informatie over rollen en machtigingen.)

U moet bekend zijn met PowerShell-cmdlets om beleidsregels voor informatiebarrières te definiëren, te valideren of te bewerken. Hoewel we verschillende voorbeelden van PowerShell-cmdlets in het [how-to-artikel](information-barriers-policies.md)geven, moet u andere details kennen, zoals parameters, voor uw organisatie.

## <a name="next-steps"></a>Volgende stappen

- [Meer informatie over informatiebarrières in Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Meer informatie over informatiebarrières in SharePoint Online](/sharepoint/information-barriers)
- [Meer informatie over informatiebarrières in OneDrive](/onedrive/information-barriers)
- [Bekijk de kenmerken die kunnen worden gebruikt voor beleidsregels voor informatiebarrière](information-barriers-attributes.md)
- [Beleid definiëren voor informatiebarrières](information-barriers-policies.md)
- [Beleid voor informatiebarrière bewerken (of verwijderen)](information-barriers-edit-segments-policies.md)