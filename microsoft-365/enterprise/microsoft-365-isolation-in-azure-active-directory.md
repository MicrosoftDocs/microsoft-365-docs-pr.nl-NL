---
title: Microsoft 365-isolatie en toegangsbeheer in azure Active Directory
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: In dit artikel vindt u meer informatie over de manier waarop de gegevens worden geïsoleerd en van toegangsbeheer voor meerdere tenants geïsoleerd binnen Azure Active Directory.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 79cfa23b788342ec533ce4f8a2f9c63ee0836c20
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689429"
---
# <a name="microsoft-365-isolation-and-access-control-in-azure-active-directory"></a>Microsoft 365-isolatie en toegangsbeheer in azure Active Directory

Azure Active Directory (Azure AD) is ontworpen om meerdere tenants op een zeer veilige manier te hosten door middel van logische gegevensisolatie. Toegang tot Azure AD wordt via een autorisatie slaag gegatedd. Azure AD isoleert klanten met Tenant containers als beveiligingsbeperkingen om de inhoud van een klant te beschermen, zodat de inhoud niet kan worden geopend of gemanipuleerd door collega's. De autorisatie slaag van Azure AD wordt uitgevoerd door drie controles:

- Is de principal ingeschakeld voor toegang tot Azure AD-Tenant?
- Is de principal ingeschakeld voor toegang tot gegevens in deze Tenant?
- Is de rol van de principal in deze Tenant geautoriseerd voor het type gegevenstoegang aangevraagd?

Er kan geen toepassing, gebruiker, server of service toegang krijgen tot Azure AD zonder de juiste verificatie en het juiste token of certificaat. Aanvragen worden afgewezen als ze niet zijn bijgevoegd via de juiste referenties.

Met een effectieve, Azure AD-host voor elke Tenant in de eigen beveiligde container, met beleidsregels en machtigingen voor en binnen de container, uitsluitend eigendom en beheerd door de Tenant.
 
![Azure-container](../media/office-365-isolation-azure-container.png)

Het concept van Tenant containers is diep gekorreld in de Directory service van alle lagen, van portalen, ongeacht de manier waarop u permanent gaat opslaan. Zelfs wanneer meerdere Azure AD-metagegevens van de Tenant op dezelfde fysieke schijf zijn opgeslagen, is er geen relatie tussen de containers die zijn gedefinieerd door de adreslijstservice, die op zijn beurt wordt bepaald door de tenantbeheerder. U kunt geen directe verbinding maken met Azure AD-opslag vanaf elke gewenste toepassing of service zonder dat u eerst de autorisatie slaag hoeft te passeren.

In het onderstaande voorbeeld hebben Contoso en fabrikam allebei aparte, gespecialiseerde containers en hoewel deze containers een deel van dezelfde onderliggende infrastructuur kunnen delen, zoals servers en opslag, blijven ze gescheiden en geïsoleerd van elkaar, en worden geauthenticeerd door lagen van autorisatie en toegangsbeheer.
 
![Azure-speciale containers](../media/office-365-isolation-azure-dedicated-containers.png)

Daarnaast zijn er geen toepassingsonderdelen die kunnen worden uitgevoerd vanuit Azure AD, en is het niet mogelijk om met één Tenant de integriteit van een andere Tenant te schenden, toegangs versleutelingssleutels van een andere Tenant of voor onbewerkte gegevens van de server te lezen.

In azure AD worden alle bewerkingen die zijn verleend door identiteiten in andere tenants, standaard niet toegestaan. Elke Tenant wordt logischerwijze geïsoleerd in azure AD via toegangsbeheer op basis van claims. Lees-en schrijfbewerkingen van directorygegevens zijn beperkt tot Tenant containers en worden geclassificeerd door een interne abstracte laag en een RBAC-laag (Role-based Access Control), waarbij de Tenant gezamenlijk wordt afgedwongen als beveiligingsgrens. Elke aanvraag voor toegang tot een gegevens toegangsaanvraag wordt verwerkt door deze lagen en elke toegangsaanvraag in Microsoft 365 wordt uitgevoerd door de logica hierboven.

Azure AD heeft Noord-Amerika, Amerikaanse overheid, Europese Unie, Duitsland en wereldwijde partities. Er bestaat een Tenant in één partitie, en partities kunnen meerdere tenants bevatten. De partitiegegevens worden bij de gebruikers van de gebruikers weer afgeleid. Een bepaalde partitie (met inbegrip van alle tenants erin) wordt gerepliceerd naar meerdere datacenters. De partitie voor een Tenant wordt geselecteerd op basis van de eigenschappen van de Tenant (bijvoorbeeld de landcode). Geheimen en andere gevoelige informatie in elke partitie worden versleuteld met een speciale sleutel. De sleutels worden automatisch gegenereerd wanneer er een nieuwe partitie wordt gemaakt.

Azure AD-systeemfuncties vormen een unieke instantie van elke gebruikerssessie. Daarnaast worden in azure AD versleutelings technologieën gebruikt voor de beveiliging van gedeelde systeembronnen op netwerkniveau om onbevoegde en onbedoelde overdracht van gegevens te voorkomen.
