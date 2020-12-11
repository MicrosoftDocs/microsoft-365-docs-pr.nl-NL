---
title: Machtigingen in de beveiligings- en compliancecentra van Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Via het Microsoft 365-beveiligingscentrum of het Microsoft 365-compliancecentrum kunt u machtigingen centraal beheren voor alle taken die zijn gerelateerd aan beveiliging of naleving.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 266d8184db5ebc79609c0a5f27c7511087ea42d0
ms.sourcegitcommit: 21b0ea5715e20b4ab13719eb18c97fadb49b563d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/11/2020
ms.locfileid: "49624718"
---
# <a name="permissions-in-the-microsoft-365-compliance-center-and-microsoft-365-security-center"></a>Machtigingen in het Microsoft 365-compliancecentrum en het Microsoft 365-beveiligingscentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Uw organisatie moet de beveiligings- en compliance-scenario's beheren met betrekking tot alle services van Microsoft 365. En u hebt de flexibiliteit nodig om de juiste beheerdersmachtigingen aan de juiste personen in de IT-groep van uw organisatie te geven. Via het Microsoft 365-beveiligingscentrum of het Microsoft 365-compliancecentrum kunt u machtigingen centraal beheren voor alle taken die zijn gerelateerd aan beveiliging of naleving.

Nadat de globale beheerder gebruikers toevoegt aan deze beheerdersrollen, heeft deze beheerder toegang tot functies en gegevens in alle services in Microsoft 365, zoals Microsoft 365-beveiligingscentrum, Microsoft 365-compliancecentrum, Azure, Office 365 en Enterprise Mobility + Security.

## <a name="what-the-microsoft-365-roles-are"></a>Wat zijn de Microsoft 365-rollen?

De rollen die worden weergegeven in het Microsoft 365-compliancecentrum en het Microsoft 365-beveiligingscentrum zijn Azure Active Directory-rollen. Deze rollen zijn ontworpen om te worden samengevoegd met functies in de IT-groep van uw organisatie, zodat u een persoon gemakkelijk alle benodigde machtigingen kunt geven om hun werk te doen.

****

|Rol|Beschrijving|
|---|---|
|**Globale beheerder**|Gebruikers met deze rol hebben toegang tot alle beheerfuncties in alle Microsoft 365-services. Alleen globale beheerders kunnen andere beheerdersrollen toewijzen. Zie [Globale beheerder/Bedrijfsbeheerder](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference#global-administrator--company-administrator) voor meer informatie.|
|**Beheerder van nalevingsgegevens**|Houd de gegevens van uw organisatie bij in Microsoft 365, zorg ervoor dat de organisatie beveiligd is en krijg inzicht in eventuele problemen om risico's te beperken. Zie [Beheerder van nalevingsgegevens](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference#compliance-data-administrator) voor meer informatie.|
|**Beheerder voor naleving**|Help uw organisatie bij de naleving van wettelijke vereisten, het beheren van eDiscovery-aanvragen en het beheren van beleidsregels voor gegevensbeheer met betrekking tot Microsoft 365-locaties, -identiteiten en -apps. Zie [Beheerder voor naleving](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference#compliance-administrator) voor meer informatie.|
|**Beveiligingsoperator**|Bekijk, onderzoek en reageer op actieve bedreigingen van uw Microsoft 365-gebruikers, -apparaten en -inhoud. Zie [Beveiligingsoperator](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference#security-operator) voor meer informatie.|
|**Beveiligingslezer**|Bekijk en onderzoek actieve bedreigingen voor uw Microsoft 365-gebruikers, -apparaten en -inhoud, maar u hebt (in tegenstelling tot de beveiligingsoperator) geen machtiging om te reageren door actie te ondernemen. Zie [Beveiligingslezer](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference#security-reader) voor meer informatie.|
|**Beveiligingsbeheerder**|Controleer de algehele beveiliging van uw organisatie door beveiligingsbeleid te beheren, de beveiligingsanalyse en rapporten in de Microsoft 365-producten te evalueren en op de hoogte te blijven van mogelijke dreigingen. Zie [Beveiligingsbeheerder](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference#security-administrator) voor meer informatie.|
|**Globale lezer**|De alleen-lezen versie van de rol **Globale beheerder**. Bekijk alle instellingen en administratieve informatie in Microsoft 365. Zie [Globale lezer](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference#global-reader) voor meer informatie.|
|

## <a name="global-administrators-can-manage-roles-in-azure-active-directory"></a>Globale beheerders kunnen rollen beheren in Azure Active Directory

Wanneer u in het Microsoft 365-compliancecentrum en het Microsoft 365-beveiligingscentrum een rol selecteert, kunt u de bijbehorende toewijzingen bekijken. Als u deze toewijzingen echter wilt beheren, moet u naar de Azure Active Directory gaan.

Zie [Beheerdersrollen bekijken en toewijzen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal) voor meer informatie.

![Link voor het beheren van machtigingen in Azure Active Directory](../../media/permissions-manage-in-azure-ad-link.png)

## <a name="managing-roles-in-a-service-instead-of-azure-active-directory"></a>Rollen in een service beheren in plaats van Azure Active Directory

De rollen die worden weergegeven in het Microsoft 365-compliancecentrum en het Microsoft 365-beveiligingscentrum, worden ook weergegeven in de services waar ze machtigingen hebben. Zo kunt u deze rollen bijvoorbeeld zien in het Beveiligings- en compliancecentrum.

![Rollen in Beveiligings- en compliancecentrum](../../media/m365-roles-in-o365-scc.png)

Zie [Machtigingen in het beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie over hoe deze rollen worden gebruikt in het Beveiligings- en compliancecentrum.

### <a name="breaking-inheritance"></a>Overname doorbreken

Het is belangrijk om te weten dat u deze rollen in Azure Active Directory centraal beheert voor **alle** Microsoft 365-services. Wanneer u echter een rol in een specifieke service beheert, zoals het Beveiligings- en compliancecentrum, beheert u de rol **alleen** voor die specifieke service. De toewijzingen en machtigingen voor een rol in een service vervangen alle machtigingen die zijn verleend aan de Azure Active Directory-rol.

Dit kan handig zijn. Wanneer een persoon bijvoorbeeld wordt toegewezen aan de rol van Beveiligingsbeheerder, is deze persoon niet gemachtigd om incidenten te beheren. Maar u kunt de machtigingen in Microsoft Defender voor Eindpunt gebruiken om hen de specifieke machtiging voor het beheren van incidenten in die service te geven.

## <a name="where-to-find-role-information-for-each-microsoft-365-service"></a>Waar vind ik informatie over rollen voor elke Microsoft 365-service?

Als u een gebruiker toewijst aan een van de beheerdersrollen voor naleving of beveiliging in Microsoft 365, geeft u die gebruiker machtigingen voor een aantal Microsoft 365-services. Gebruik de onderstaande links voor meer informatie over de specifieke machtigingen voor een rol in elke service.

****

|Microsoft 365-service|Informatie over rollen|
|---|---|
|Beheerdersrollen in abonnementen voor Office 365- en Microsoft 365 voor Bedrijven|[Microsoft 365-beheersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|Azure Active Directory (Azure AD) en Azure AD Identity Protection|[Azure AD-beheerdersrollen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Microsoft Defender for Identity|[Microsoft Defender for Identity-rolgroepen](https://docs.microsoft.com/azure-advanced-threat-protection/atp-role-groups)|
|Azure Information Protection|[Azure AD-beheerdersrollen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Compliancebeheer|[Compliancebeheer](https://docs.microsoft.com/microsoft-365/compliance/compliance-manager-setup#set-user-permissions-and-assign-roles)|
|Exchange Online|[Toegangsbeheer in Exchange op basis van rollen](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)|
|Intune|[Toegangsbeheer in Intune op basis van rollen](https://docs.microsoft.com/intune/role-based-access-control)|
|Managed Desktop|[Azure AD-beheerdersrollen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Microsoft Cloud App Security|[Toegangsbeheer op basis van rollen](https://docs.microsoft.com/cloud-app-security/manage-admins)|
|Beveiligings- en compliancecentrum|[Microsoft 365-beheersrollen](permissions-in-the-security-and-compliance-center.md)|
|Privileged Identity Management|[Azure AD-beheerdersrollen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Secure Score|[Azure AD-beheerdersrollen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|SharePoint Online|[Azure AD-beheerdersrollen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) <p> [Over de SharePoint-beheerdersrollen in Office 365](https://docs.microsoft.com/sharepoint/sharepoint-admin-role)|
|Teams/Skype voor Bedrijven|[Azure AD-beheerdersrollen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Microsoft Defender for Endpoint|[Op rollen gebaseerd Microsoft Defender voor Eindpunt-toegangsbeheer](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/rbac-windows-defender-advanced-threat-protection)|
|

## <a name="coming-soon"></a>Binnenkort beschikbaar

We werken nog steeds aan machtigingen in het Microsoft 365-compliancecentrum en Microsoft 365-beveiligingscentrum. Zo werken we momenteel bijvoorbeeld aan ondersteuning voor de mogelijkheid om:

- De rollen die worden weergegeven in het Microsoft 365-compliancecentrum en het Microsoft 365-beveiligingscentrum te beheren, in plaats van dat u naar het Azure Active Directory moet gaan.
- Rollen aan te passen door specifieke machtigingen toe te voegen of te verwijderen.
- Aangepaste rollen te maken met machtigingen die u zelf kiest.
