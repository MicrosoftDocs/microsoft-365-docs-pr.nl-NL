---
title: Meer informatie over detectie en herstel van app-bedreigingen
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Meer informatie over detectie en herstel van app-bedreigingen.
ms.openlocfilehash: 574688e67b7562c8df6aec7d2242e68485239479
ms.sourcegitcommit: 2fd60871975d61e60d4827b36cd689021fd2a4c8
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53438046"
---
# <a name="learn-about-app-threat-detection-and-remediation"></a>Meer informatie over detectie en herstel van app-bedreigingen

>*[Richtlijnen voor Microsoft 365-licenties voor beveiliging en naleving](https://aka.ms/ComplianceSD).*

Met Microsoft-appbeheer kunt u het volgende doen:

- Bewaak eenvoudig de bedreigingswaarschuwingen die worden gegenereerd door ingebouwde detectiemethoden voor app-beheer voor schadelijke app-activiteiten en op beleid gebaseerde waarschuwingen die worden gegenereerd door actief app-beleid dat u maakt. Deze waarschuwingen kunnen duiden op afwijkingen in app-activiteit en wanneer niet-compatibele, schadelijke of riskante apps worden gebruikt.  U kunt ook patronen in waarschuwingen gebruiken om nieuw app-beleid te maken of de instellingen van bestaande beleidsregels te wijzigen voor meer beperkende acties.
- Herstel waarschuwingen eenvoudig handmatig na onderzoek of automatisch via de actie-instellingen voor actief app-beleid.


>[!Note]
>Afwijkende activiteiten van alleen-Azure-apps waaraan geen machtigingen zijn verleend voor toegang tot Microsoft 365-informatiebronnen, zijn niet opgenomen in detectie en waarschuwingen voor app-beheer.
>

Zie de [beheerdersrollen](app-governance-get-started.md#administrator-roles) voor welke rollen toegang hebben tot app-beheerpagina's.


## <a name="app-governance-integration-with-azure-active-directory-and-microsoft-cloud-app-security"></a>Integratie van app-beheer met Azure Active Directory en Microsoft Cloud App Security

App-beheer, Azure Active Directory en Microsoft Cloud App Security verzamelen en leveren verschillende gegevenssets:

- App-beheer biedt gedetailleerde informatie over de activiteit van een app op API-niveau.
- Azure AD biedt basismetagegevens voor apps en gedetailleerde informatie over aanmeldingen bij apps.
- Microsoft Cloud App Security biedt informatie over app-risico's.

Door informatie te delen tussen app-governance, Azure AD en Microsoft Cloud App Security, kunt u geaggregeerde informatie in één portal weergeven en eenvoudig een koppeling maken naar een andere portal voor meer informatie. Hier ziet u enkele voorbeelden:

- Aanmeldingsgegevens voor apps in app-beheer:

  Vanuit de portal voor app-beheer kunt u de geaggregeerde aanmeldingsactiviteit voor elke app zien en terugkoppelen naar het Azure Active Directory-beheercentrum voor details van aanmeldingsgebeurtenissen.

- Informatie over het gebruik van app-API in het Azure Active Directory-beheercentrum:

  Vanuit het Azure Active Directory-beheercentrum kunt u de geaggregeerde gegevens over het gebruik van apps bekijken en een koppeling maken naar de app-beheerportal voor details over het app-gebruik.

- API-gebruiksgegevens in de Microsoft Cloud App Security-portal: 

  In de Microsoft Cloud App Security-portal kunt u het API-gebruiksniveau en de geaggregeerde gegevensoverdracht bekijken en voor meer informatie een koppeling maken naar de app-beheerportal.

Hier is een samenvatting van de integratie.

![De integratie van app-beheer met Azure AD en Microsoft Cloud App Security](..\media\manage-app-protection-governance\mapg-integration.png)

Bovendien stuurt app-beheer waarschuwingen als signalen naar Microsoft Cloud App Security en Microsoft 365 Defender, voor een meer gedetailleerde analyse van app-gebaseerde beveiligingsincidenten.

<!--

CFA #3 Scenario 1:  As an admin, I can investigate alerts associated to my M365 apps through MAPG.
CFA #3 Scenario 2: As an admin, I can manually remediate 
CFA #3 Scenario 3: As an admin, I can configure policies to perform automatic 
--> 

## <a name="next-step"></a>Volgende stap

[Aan de slag met detectie en herstel van app-bedreigingen.](app-governance-detect-remediate-get-started.md)
