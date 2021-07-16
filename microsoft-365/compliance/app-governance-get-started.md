---
title: Aan de slag met app-beheer
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Ga aan de slag met mogelijkheden voor app-beheer om uw apps te beheren.
ms.openlocfilehash: 58f3bab9f8c5e28ce921ab244b23c49682394795
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430706"
---
# <a name="get-started-with-app-governance-in-preview"></a>Aan de slag met app-governance (in preview)

Ga als volgt te werk om de functie voor app-governance te gebruiken voor Microsoft Cloud App Security:

1. Controleer of uw account het juiste licentieniveau heeft. App-beheer is een invoegtoepassingsfunctie voor Microsoft Cloud App Security (MCAS) en daarom moet MCAS aanwezig zijn in uw account als zelfstandig product of als onderdeel van de verschillende licentiepakketten die hieronder worden vermeld.
1. U moet een van de onderstaande beheerdersrollen hebben om toegang te krijgen tot de pagina's voor app-beheer in de portal.

## <a name="licensing-for-app-governance"></a>Licenties voor app-beheer

Voordat u aan de slag gaat met app-beheer, moet u uw [Microsoft 365-abonnement](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) en eventuele invoegtoepassingen bevestigen. Voor toegang tot en gebruik van app-beheer moet uw organisatie een van de volgende abonnementen of invoegtoepassingen hebben:

- Microsoft Cloud App Security
- Microsoft 365 E5
- Microsoft 365 E5 Compliance
- Microsoft 365 E5 Developer (zonder Windows en Audiovergadering)
- Microsoft 365 E5 Gegevensbeveiliging en -beheer
- Microsoft 365 E5 Security
- Microsoft 365 A5 met belminuten
- Microsoft 365 E5 zonder Audiovergadering
- Microsoft 365 A5 Compliance voor onderwijsmedewerkers
- Microsoft 365 A5 Compliance voor leerlingen en studenten
- Microsoft 365 A5 voor onderwijsmedewerkers
- Microsoft 365 A5 voor leerlingen en studenten
- Microsoft 365 A5 Gegevensbeveiliging en -beheer voor onderwijsmedewerkers
- Microsoft 365 A5 Gegevensbeveiliging en -beheer voor leerlingen en studenten
- Microsoft 365 A5-beveiliging voor onderwijsmedewerkers
- Microsoft 365 A5-beveiliging voor leerlingen en studenten
- Gebruiksvoordeel Microsoft 365 A5 voor leerlingen en studenten
- Microsoft 365 A5 met belminuten voor onderwijsmedewerkers
- Microsoft 365 A5 met belminuten voor leerlingen en studenten
- Microsoft 365 A5 zonder Audiovergadering voor onderwijsmedewerkers
- Microsoft 365 A5 zonder Audiovergadering voor leerlingen en studenten
- Gebruiksvoordeel Microsoft 365 A5 zonder Audiovergadering voor leerlingen en studenten

## <a name="administrator-roles"></a>Beheerdersrollen

Een van de volgende beheerdersrollen is vereist om app-beheerpagina's te zien of beleidsregels en -instellingen te beheren:

- Toepassingsbeheerder
- Cloudtoepassingsbeheerder
- Bedrijfsbeheerder
- Nalevingsbeheerder
- Beheerder van nalevingsgegevens
- Nalevingslezer (alleen-lezen)
- Algemene lezer
- Beveiligingsbeheerder
- Beveiligingsoperator
- Beveiligingslezer (alleen-lezen)

Dit zijn de mogelijkheden voor elke rol.

| Rol | Het dashboard lezen | Alle apps lezen |Beleid lezen | Beleid maken, bijwerken of verwijderen | Waarschuwingen lezen | Waarschuwingen bijwerken | Instellingen lezen | Instellingen bijwerken | Herstel lezen | Herstel bijwerken |
|:-------|:-----|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
| Toepassingsbeheerder | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) |
| Cloudtoepassingsbeheerder | ![Vinkje](..\media\checkmark.png) | | | | | | | | | |
| Bedrijfsbeheerder | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) |
| Nalevingsbeheerder | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) |  | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | |
| Beheerder van nalevingsgegevens | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) |  | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | |
| Nalevingslezer | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) |  | ![Vinkje](..\media\checkmark.png) |  | ![Vinkje](..\media\checkmark.png) |  | | |
| Algemene lezer  | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) |  | ![Vinkje](..\media\checkmark.png) |  | ![Vinkje](..\media\checkmark.png) |  | | |
| Beveiligingsbeheerder | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) |  | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | |
| Beveiligingsoperator | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | |
| Beveiligingslezer  | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) |  | ![Vinkje](..\media\checkmark.png) |  | ![Vinkje](..\media\checkmark.png) |  | ![Vinkje](..\media\checkmark.png) | |
|||||||||| | |

Zie [Machtigingen voor beheerdersrollen](/azure/active-directory/roles/permissions-reference)voor meer informatie over elke rol.

## <a name="add-app-governance-to-your-microsoft-365-account"></a>App-beheer toevoegen aan uw Microsoft 365-account

Voor bestaande Microsoft 365-klanten:

1. Navigeer in uw [Microsoft 365-beheercentrum](https://admin.microsoft.com)naar **Facturering - Services kopen** en klik op **Invoegtoepassingen**.
1. Klik in de kaart voor app-beheer op **Details**.
1. Klik op **Gratis proefversie starten**.
1. Voltooi de gevraagde informatie om app-beheer toe te voegen aan de geselecteerde tenant. Als u een nieuwe klant bent, moet u eerst informatie verstrekken om een account aan te maken en een tenant aan te maken voor uw proefperiode. Zodra dit is gebeurd, kunt u app-beheer toevoegen aan de proefversie.

Voor nieuwe Microsoft 365-klanten:

1. Klik boven aan deze pagina op de knop **Gratis account**.
1. Klik onder **Probeer Microsoft 365 voor Bedrijven** op **Probeer 1 maand gratis**.

Voor beide:

1. Geef in de aanmeldingsportal uw e-mailadres op dat u voor de proefversie wilt gebruiken. Als u een bestaande klant bent, gebruikt u het e-mailadres dat is gekoppeld aan uw account. Klik op **Volgende**.
1. Nadat u zich hebt aangemeld, klikt u op **Probeer nu** om de gratis proefversie te downloaden.
1. Klik op **Doorgaan** om de pagina te sluiten en de installatie van de proefversie te starten. Voor nieuwe app-beheerklanten duurt het tot twee uur voordat uw app-beheerexemplaar beschikbaar is. Voor bestaande klanten is er geen onderbreking van bestaande services.
  > [!NOTE]
Als u nog geen account hebt, wordt u gevraagd een nieuw account in te stellen voordat u kunt doorgaan met de proefversie.

1. Voer een beschikbare domeinnaam in voor uw AAD-tenant en klik op **Beschikbaarheid controleren**. Er wordt automatisch een beheerdersrol toegewezen (als u geen bestaande rol voor app-beheer hebt) en u kunt later de domeinnaam altijd wijzigen en/of meer tenants aanschaffen via het Microsoft 365-beheercentrum.
1. Voer de gebruikersnaam en het wachtwoord in die u wilt gebruiken om u aan te melden bij uw account. Klik op **Registeren**.
1. Klik op **Aan de slag** om naar de portal voor app-beheer te gaan of op **Uw abonnement beheren** om naar het Microsoft 365-beheercentrum te gaan.
