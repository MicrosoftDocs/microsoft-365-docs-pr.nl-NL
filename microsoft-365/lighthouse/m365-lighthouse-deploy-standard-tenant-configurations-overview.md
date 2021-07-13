---
title: Overzicht van het gebruik van basislijnen voor het implementeren van standaardtenderconfiguraties
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Voor beheerde serviceproviders (MSP's) met Microsoft 365 Lighthouse informatie over het gebruik van basislijnen voor het implementeren van standaardtenderconfiguraties.
ms.openlocfilehash: ff3fb21e71195f9614870b8e3c65c92ee11fdf69
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409177"
---
# <a name="overview-of-using-baselines-to-deploy-standard-tenant-configurations"></a>Overzicht van het gebruik van basislijnen voor het implementeren van standaardtenderconfiguraties 

> [!NOTE]
> De functies die in dit artikel worden beschreven, zijn in Preview, kunnen worden gewijzigd en zijn alleen beschikbaar voor partners die aan de vereisten [voldoen.](m365-lighthouse-requirements.md) Als uw organisatie geen Microsoft 365 Lighthouse, zie [Registreren voor Microsoft 365 Lighthouse.](m365-lighthouse-sign-up.md)

Microsoft 365 Lighthouse basislijnen bieden een herhaalbare en schaalbare manier om de beveiligingsinstellingen voor meerdere tenants te beoordelen en Microsoft 365 beheren. Basislijnen helpen ook bij het controleren van kernbeveiligingsbeleid en tenant compliancestandaarden met configuraties die gebruikers, apparaten en gegevens beveiligen.

Ontworpen om partners te helpen bij de acceptatie van beveiliging door klanten in hun eigen tempo, Microsoft 365 Lighthouse biedt een standaardset basislijnparameters en vooraf gedefinieerde configuraties voor Microsoft 365 services. Deze beveiligingsconfiguraties helpen bij het meten van de Microsoft 365 van uw tenants.

U kunt de standaardlijnlijn en de implementatiestappen ervan bekijken vanuit Microsoft 365 Lighthouse. Als u basislijnen wilt toepassen op een tenant, selecteert u **Tenants** in het linkernavigatiedeelvenster en selecteert u vervolgens een tenant. Ga vervolgens naar het tabblad **Implementatieplannen** en implementeert de gewenste basislijn.

## <a name="standard-baseline-security-templates"></a>Standaardbasislijnbeveiligingssjablonen

Microsoft 365 Lighthouse standaard basislijnconfiguraties voor beveiligingswerkbelastingen zijn ontworpen om alle beheerde tenants te helpen een acceptabele beveiligingsdekking en naleving te bereiken.

De basislijnconfiguraties in de volgende tabel worden standaard geleverd Microsoft 365 Lighthouse standaard basislijn.<br><br>

| Basislijnconfiguratie | Omschrijving |
|--|--|
| MFA vereisen voor beheerders | Een beleid voor alleen-rapport Voorwaardelijke toegang waarvoor meervoudige verificatie voor beheerders vereist is. Dit is vereist voor alle cloudtoepassingen. |
| MFA vereisen voor eindgebruikers | Een beleid voor alleen-rapport Voorwaardelijke toegang dat meervoudige verificatie vereist voor gebruikers. Dit is vereist voor alle cloudtoepassingen. |
| Verouderde verificatie blokkeren | Een beleid voor alleen-rapporterende voorwaardelijke toegang om oudere clientverificatie te blokkeren. |
| Apparaten registreren in Microsoft Endpoint Manager : Azure AD Join | Apparaatinschrijving om uw tenantapparaten in te schrijven in Microsoft Endpoint Manager. Dit wordt gedaan door Automatisch registreren in te stellen tussen Azure Active Directory en Microsoft Endpoint Manager. |
| Antivirusbeleidsconfiguratie (AV) | Een apparaatconfiguratieprofiel voor Windows apparaten met vooraf geconfigureerde Microsoft Defender Antivirus instellingen. |
| Beleid voor naleving van venster 10 instellen | Een Windows apparaatbeleid met vooraf geconfigureerde instellingen om te voldoen aan basisvereisten voor naleving. |

## <a name="related-content"></a>Verwante inhoud

[Basislijnen Microsoft 365 Lighthouse implementeren](m365-lighthouse-deploy-baselines.md) (artikel)\
[Microsoft 365 Lighthouse veelgestelde vragen](m365-lighthouse-faq.yml) (artikel)
