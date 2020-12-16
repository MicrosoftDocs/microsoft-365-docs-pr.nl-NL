---
title: Aanvullende informatie over Azure Active Directory voor de migratie van Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/15/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Overzicht: aanvullende Azure Active Directory-informatie wanneer u overstapt van Microsoft Cloud Duitsland (Microsoft Cloud Deutschland) naar Office 365-Services in het nieuwe Duitse datacenter-gebied.'
ms.openlocfilehash: 4fc5dda95e5e7afc4d69141a9a4debd0a74c492b
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688743"
---
# <a name="additional-azure-active-directory-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Aanvullende informatie over Azure Active Directory voor de migratie van Microsoft Cloud Deutschland

Voor het voltooien van de overstap vanuit de Azure Cloud Cloud naar de openbare cloud van Azure, raden we u aan dat het eindpunt voor verificatie, Azure Active Directory (Azure AD), en MS-grafiek eindpunten voor uw toepassingen wordt bijgewerkt naar die van de commerciële Cloud wanneer het OpenID Connect (OIDC)-eindpunten worden `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` gerapporteerd. 
 
**Wanneer moet ik deze wijziging aanbrengen?**

U ontvangt een melding in azure/Office Portal wanneer uw Tenant migratie van de Duitse Cloud naar de commerciële Cloud voltooit. U hebt 30 dagen na ontvangst van deze melding om deze updates te voltooien, zodat de app blijft werken voor tenants die worden gemigreerd van Azure Duitsland Cloud naar Azure Public Cloud.
 
Er zijn drie voorwaarden voor het bijwerken van uw aanmeldings autoriteit:

 - Detectie-eindpunten voor OIDC voor uw Tenant `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` retourneren openbare Cloud eindpunten in azure AD.

 - Als uw Tenant is geconfigureerd voor Federatie, wordt AD FS (Active Directory Federation Services) bijgewerkt en gesynchroniseerd met Azure Active Directory-publiek. U kunt de instructies volgen om de instellingen van Azure AD Connect bij te werken om deze wijziging door te voeren.

 - De resource toepassingen, indien van toepassing, worden door uw toepassingen gewijzigd in het accepteren van tokens die door beide Azure AD Duitsland en Azure AD openbaar zijn ondertekend.
 
**Welke soorten toepassingen?**

Een toepassing kan een van de volgende oorzaken hebben:

- [App voor één pagina (SPA)](https://docs.microsoft.com/azure/active-directory/develop/scenario-spa-overview)
- [Web-app die zich aanmeldt bij gebruikers](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-app-sign-user-overview)
- [Web-app waarmee u Web-Api's aanroept](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-app-call-api-overview)
- [Beveiligde web-API](https://docs.microsoft.com/azure/active-directory/develop/scenario-protected-web-api-overview)
- [Web-API waarmee Web-Api's worden aangeroepen](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-api-call-api-overview)
- [Bureaublad-app](https://docs.microsoft.com/azure/active-directory/develop/scenario-desktop-overview)
- [Daemon-app](https://docs.microsoft.com/azure/active-directory/develop/scenario-daemon-overview)
- [Mobiele app](https://docs.microsoft.com/azure/active-directory/develop/scenario-mobile-overview)
 
> [!NOTE] 
> Wanneer een toepassing overschakelt naar `login.microsoftonline.com` het gebruik van de autoriteit, worden de tokens ondertekend door deze nieuwe instantie. Als u bronnen toepassingen host die andere apps bellen, moet u de validatie van Lax-tokens toestaan. Dit betekent dat de app tokens moet toestaan die zijn ondertekend met de Clouds van Azure AD Duitsland en Azure AD. Deze Lax-token validatie is vereist totdat alle clienttoepassingen die uw serviceoproepen, volledig zijn gemigreerd naar de openbare Azure AD-Cloud. Na de migratie hoeft de brontoepassing alleen tokens te accepteren die zijn ondertekend met de openbare Azure AD-Cloud.

**Wat moet ik bijwerken?**

1. Als u een toepassing in azure Duitsland host die wordt gebruikt voor de verificatie van Azure Duitsland of Office 365 Duitsland, moet u ervoor zorgen dat deze `https://login.microsoftonline.com` wordt gebruikt als de autoriteit in de verificatiecontext.

    - Zie contexten van Azure AD-verificatie.
    - Dit geldt ook voor verificatie voor uw toepassing en verificatie van alle Api's die uw toepassing kan bellen (dat wil zeggen Microsoft Graph, Azure AD Graph, Azure Resource Manager).

2. Update van Azure AD Graph endpoint `https://graph.windows.net` .

3. Update van MS Graph-eindpunt `https://graph.microsoft.com` .

4. U kunt alle Duitse Cloud eindpunten (zoals deze voor Exchange Online en SharePoint Online) bijwerken die door uw toepassingen worden gebruikt om die van de openbare Cloud te zijn.

5. U kunt als volgt Omgevings parameters bijwerken voor `AzurePublic` (in plaats van `AzureGermany` ) in beheerprogramma's en scripts voor:

    - [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps)
    - [Azure AD PowerShell (MSOnline)](https://docs.microsoft.com/powershell/azure/active-directory/overview)
    - [Azure AD PowerShell (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?)
    - [Azure CLI](https://docs.microsoft.com/cli/azure/install-azure-cli)
 
**Hoe zit het met toepassingen die ik publiceer?**

Als u een toepassing publiceert die beschikbaar is voor gebruikers die zich buiten de Tenant bevinden, moet u mogelijk de registratie van de toepassing wijzigen om zo de continuïteit te waarborgen. Andere tenants die uw toepassing gebruiken, kunnen op een ander moment worden verplaatst dan de Tenant. Als u er zeker van wilt zijn dat ze geen toegang meer hebben tot de toepassing, moet u toestemming verlenen voor het synchroniseren van de app van Azure Duitsland naar Azure public.

## <a name="additional-considerations"></a>Aanvullende overwegingen

Hier volgen enkele aanvullende aandachtspunten voor Azure AD:

- Voor federatieve verificatie:

  - U mag geen federatief domein maken, promoten of verlagen wanneer de overgang van de Tenant in behandeling is. Nadat de migratie naar de Azure AD-service is voltooid (de Tenant is volledig aangevuld), kunt u verdergaan met het beheren van federatieve domeinen.

  - Als u gebruikmaakt van federatieve verificatie met Active Directory Federation Services (AD FS), moet u geen wijzigingen aanbrengen in de namen van uitgevers die worden gebruikt voor authenticatie met uw on-premises Active Directory Domain Services (AD DS) tijdens de migratie. Het wijzigen van de uitgevers van de uitgevers heeft tot Verificatiefouten voor gebruikers in het domein tot gevolg. Uri's van de Issuer kunnen rechtstreeks in AD FS worden gewijzigd of wanneer een domein wordt geconverteerd van beheerd naar Federatie en omgekeerd. Microsoft raadt klanten aan geen federatief domein toe te voegen, te verwijderen of te converteren in de Azure AD-Tenant die wordt gemigreerd. U kunt Uri's van de Issuer wijzigen na voltooiing van de migratie.

- Voor netwerken:

  - Het maken van IPv6-benoemde netwerken werkt niet in de Azure-Portal, `http://portal.microsoftazure.de/` . De Azure-Portal gebruiken `https://portal.azure.com` om IPv6-netwerken te maken.
 
   - U kunt geen vertrouwde IP-adresbereiken maken voor Azure multi-factor Authentication (MFA) service-instellingen van de Microsoft Cloud Deutschland Portal. Met de Azure AD-portal voor Office 365-Services kunt u vertrouwde IP-adresbereiken van Azure MFA maken.


- Voor voorwaardelijke toegang: 

  - Beleidsregels voor voorwaardelijke toegang met de volgende beheerfuncties worden niet ondersteund totdat de migratie naar Office 365-Services is voltooid (na voltooiing van [Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) Migration fase):

    - Compatibel apparaat vereisen
    - Goedgekeurde app vereisen
    - Beleid voor app-beveiliging vereisen
    
  - De interface voor voorwaardelijke toegang geeft een foutmelding over beveiligingsstandaarden die worden ingeschakeld voor de Tenant, ook als deze is uitgeschakeld, en regels voor voorwaardelijke toegang al bestaan voor de Tenant. U moet de waarschuwing negeren of het Office 365 Services-portal gebruiken voor het beheren van regels voor voorwaardelijke toegang. 

- InTune-scenario's worden alleen ondersteund voor wereldwijde eindpunten na het voltooien van de Tenant migratie, waaronder alle migraties van Office-workloads.

- Gebruikers van Microsoft Cloud Deutschland die de meldings methode voor mobiele apps gebruiken voor MFA-aanvragen, zien de ObjectId van de gebruiker in plaats van de UPN (User Principal Name) van de Microsoft Authenticator-app. Na de migratie van de Azure AD-Tenant in Office 365-services worden nieuwe Microsoft Authenticator-activeringen weergegeven van de gebruikers-Upn's. Bestaande Microsoft-Authenticator-accounts blijven de gebruikers-id voor de gebruiker weergeven, maar blijven werken met meldingen voor mobiele apps. 

- Voor tenants die na 22 oktober 2019 worden gemaakt, kunnen de beveiligingsinstellingen voor de Tenant automatisch worden ingeschakeld voor de Tenant wanneer deze wordt gemigreerd naar de Office 365-service. Tenant beheerders kunnen ervoor kiezen om de standaardinstellingen voor de beveiliging in te schakelen en te registreren voor MFA, of ze kunnen de functie uitschakelen. Zie [beveiligingsstandaarden uitschakelen](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults)voor meer informatie. 

  > [!NOTE]
  > Organisaties die niet automatisch worden ingeschakeld tijdens de migratie, kunnen nog steeds automatisch worden ingeschreven in de toekomst als de functie voor het in-of uitschakelen van beveiligingsinstellingen voor de Office 365-service. Beheerders die ervoor kiezen om de standaardinstellingen van de beveiligingsinstellingen in of uit te schakelen, kunnen dit doen door de functie bij te werken onder **Azure Active Directory > eigenschappen**. Wanneer de functie expliciet is ingeschakeld door de beheerder, wordt deze niet automatisch ingeschakeld.

- Er verschijnt een waarschuwing over de versie van Azure AD Connect in de Office 365 Duitsland-Portal en in de Office 365-Portal na migratie van de Tenant. Dit kan worden genegeerd als de waarschuwing na voltooiing van de versie niet meer wordt weergegeven. Als er een waarschuwing is voor of na migratie, moet in de Portal de optie Azure AD Connect worden bijgewerkt. Het waarschuwingsbericht bevat de volgende tekst: ' u hebt vastgesteld dat u een verouderd adreslijstsynchronisatie hulpmiddel gebruikt. We raden u aan om naar het Microsoft Download centrum te gaan om de nieuwste versie van Azure AD Connect te downloaden.

## <a name="more-information"></a>Meer informatie

Aan de slag:

- [Migratie van Microsoft Cloud Deutschland naar Office 365-Services in de nieuwe Duitse datacenter gebieden](ms-cloud-germany-transition.md)
- [Migratie ondersteuning voor Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Hoe kan ik me aanmelden voor migratie?](ms-cloud-germany-migration-opt-in.md)
- [Gebruikerservaring tijdens de migratie](ms-cloud-germany-transition-experience.md)

Door de overgang navigeren:

- [Acties en effecten voor de migratiefasen](ms-cloud-germany-transition-phases.md)
- [Extra vooraf werken](ms-cloud-germany-transition-add-pre-work.md)
- Aanvullende informatie over [Azure AD](ms-cloud-germany-transition-azure-ad.md), [apparaten](ms-cloud-germany-transition-add-devices.md), [ervaringen](ms-cloud-germany-transition-add-experience.md)en [AD FS](ms-cloud-germany-transition-add-adfs.md).

Cloud-apps:

- [Dynamics 365-migratieprogramma gegevens](https://aka.ms/d365ceoptin)
- [Informatie over migratieprogramma's voor Power BI](https://aka.ms/pbioptin)
- [Aan de slag met uw upgrade naar Microsoft teams](https://aka.ms/SkypeToTeams-Home)
