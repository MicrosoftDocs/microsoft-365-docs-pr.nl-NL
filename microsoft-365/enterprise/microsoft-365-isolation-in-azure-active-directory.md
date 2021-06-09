---
title: Microsoft 365 Isolatie en Toegangsbeheer in Azure Active Directory
ms.author: robmazz
author: robmazz
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
description: In dit artikel leert u hoe Isolatie en Toegangsbeheer werken om gegevens voor meerdere tenants binnen een Azure Active Directory.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 198e1f37a7378d14d5a4ad28d5bce9d480b2c49e
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332410"
---
# <a name="microsoft-365-isolation-and-access-control-in-azure-active-directory"></a>Microsoft 365 Isolatie en Toegangsbeheer in Azure Active Directory

Azure Active Directory (Azure AD) is ontworpen om meerdere tenants op een zeer veilige manier te hosten via logische gegevensisolatie. Toegang tot Azure AD wordt afgesloten door een autorisatielaag. Azure AD isoleert klanten die tenantcontainers gebruiken als beveiligingsgrenzen om de inhoud van een klant te beschermen, zodat de inhoud niet kan worden toegankelijk of gecompromitteerd door co-tenants. Drie controles worden uitgevoerd door de autorisatielaag van Azure AD:

- Is de principal ingeschakeld voor toegang tot Azure AD-tenant?
- Is de principal ingeschakeld voor toegang tot gegevens in deze tenant?
- Is de rol van de principal in deze tenant geautoriseerd voor het type gegevenstoegang dat wordt aangevraagd?

Geen enkele toepassing, gebruiker, server of service heeft toegang tot Azure AD zonder de juiste verificatie en token of certificaat. Aanvragen worden geweigerd als ze niet vergezeld gaan van de juiste referenties.

In azure AD wordt elke tenant in een eigen beveiligde container host, met beleidsregels en machtigingen voor en binnen de container die alleen eigendom is van en wordt beheerd door de tenant.
 
![Azure-container](../media/office-365-isolation-azure-container.png)

Het concept tenantcontainers is diep ingebakken in de adreslijstservice op alle lagen, van portals tot permanente opslag. Zelfs wanneer meerdere Azure AD-tenantmetagegevens zijn opgeslagen op dezelfde fysieke schijf, is er geen relatie tussen de containers anders dan wat is gedefinieerd door de adreslijstservice, die op zijn beurt wordt gedicteerd door de tenantbeheerder. Er kunnen geen directe verbindingen met Azure AD-opslag zijn vanuit een aanvraag voor toepassingen of service zonder eerst door de autorisatielaag te gaan.

In het onderstaande voorbeeld hebben Contoso en Fabrikam beide afzonderlijke, speciale containers. Hoewel deze containers mogelijk dezelfde onderliggende infrastructuur delen, zoals servers en opslag, blijven ze gescheiden en geïsoleerd van elkaar en worden ze afgesloten door lagen van autorisatie en toegangsbeheer.
 
![Speciale Azure-containers](../media/office-365-isolation-azure-dedicated-containers.png)

Bovendien zijn er geen toepassingsonderdelen die kunnen worden uitgevoerd vanuit Azure AD en is het niet mogelijk dat een tenant met geweld de integriteit van een andere tenant schendt, versleutelingssleutels van een andere tenant kan openen of onbewerkte gegevens van de server kan lezen.

In Azure AD worden standaard alle bewerkingen die zijn uitgegeven door identiteiten in andere tenants, afgekeurd. Elke tenant is logisch geïsoleerd in Azure AD via toegangsbesturingselementen op basis van claims. Lees- en schrijfgegevens van adreslijstgegevens zijn beperkt tot tenantcontainers en worden gegated door een interne abstractielaag en een RBAC-laag (Role-Based Access Control), die samen de tenant afdwingen als beveiligingsgrens. Elke aanvraag voor toegang tot adreslijstgegevens wordt door deze lagen verwerkt en elke toegangsaanvraag in Microsoft 365 wordt volgens de bovenstaande logica gemonitord.

Azure AD heeft Noord-Amerika, de Amerikaanse overheid, de Europese Unie, Duitsland en world wide partitions. Een tenant bestaat in één partitie en partities kunnen meerdere tenants bevatten. Partitiegegevens worden verwijderd van gebruikers. Een bepaalde partitie (inclusief alle tenants daarin) wordt gerepliceerd naar meerdere datacenters. De partitie voor een tenant wordt gekozen op basis van eigenschappen van de tenant (bijvoorbeeld de landcode). Geheimen en andere gevoelige informatie in elke partitie worden versleuteld met een speciale sleutel. De toetsen worden automatisch gegenereerd wanneer er een nieuwe partitie wordt gemaakt.

Azure AD-systeemfunctionaliteiten zijn een uniek exemplaar voor elke gebruikerssessie. Daarnaast gebruikt Azure AD versleutelingstechnologieën om gedeelde systeembronnen op netwerkniveau te isoleren om ongeautoriseerde en onbedoelde overdracht van gegevens te voorkomen.
