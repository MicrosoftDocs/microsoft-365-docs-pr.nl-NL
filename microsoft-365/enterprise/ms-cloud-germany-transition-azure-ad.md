---
title: Aanvullende Azure Active Directory voor de migratie van Microsoft Cloud Deutschland
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
description: 'Overzicht: Aanvullende Azure Active Directory informatie bij het verplaatsen van Microsoft Cloud Germany (Microsoft Cloud Deutschland) naar Office 365 services in de nieuwe Duitse datacenterregio.'
ms.openlocfilehash: 1e3871dc5a8a8a9ecbef29df21431aa3707871d0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923848"
---
# <a name="additional-azure-active-directory-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Aanvullende Azure Active Directory voor de migratie van Microsoft Cloud Deutschland

Als u de overstap van de Azure German-cloud naar de openbare Azure-cloud wilt voltooien, raden we u aan dat het eindpunt voor verificatie, Azure Active Directory (Azure AD) Graph en MS Graph-eindpunten voor uw toepassingen worden bijgewerkt naar die van de commerciële cloud wanneer het OpenID Verbinding maken-eindpunt (OIDC) (OpenID) wordt gestart met het rapporteren van commerciële `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` cloud-eindpunten. 
 
**Wanneer moet ik deze wijziging aan brengen?**

U ontvangt een melding in Azure/Office portal wanneer uw tenant de migratie van de Duitse cloud naar de commerciële cloud voltooit. U hebt 30 dagen na het ontvangen van deze melding de tijd om deze updates te voltooien, zodat uw app blijft werken voor tenants die zijn gemigreerd vanuit de Azure Germany-cloud naar Azure Public Cloud.
 
Er zijn drie voorwaarden voor het bijwerken van uw aanmeldingsinstantie:

 - OIDC discovery endpoint for your tenant returns Azure AD public cloud endpoints.OIDC discovery endpoint for your tenant `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` returns Azure AD public cloud endpoints.

 - Als uw tenant is ingesteld voor federatie, wordt Active Directory Federation Services (AD FS) bijgewerkt om te synchroniseren met Azure AD Public. U kunt instructies volgen voor het bijwerken van Azure AD-Verbinding maken instellingen voor het maken van deze wijziging.

 - Resourcetoepassingen die door uw toepassingen worden gebruikt, worden gewijzigd om tokens te accepteren die zijn ondertekend door zowel Azure AD Germany als Azure AD Public.
 
**Wat voor soort toepassingen?**

Een toepassing kan een van de volgende opties zijn:

- [App met één pagina (SPA)](/azure/active-directory/develop/scenario-spa-overview)
- [Web-app waarmee gebruikers worden aangegeven](/azure/active-directory/develop/scenario-web-app-sign-user-overview)
- [Web-app waarmee web-API's worden gebeld](/azure/active-directory/develop/scenario-web-app-call-api-overview)
- [Beveiligde web-API](/azure/active-directory/develop/scenario-protected-web-api-overview)
- [Web-API die web-API's aanroept](/azure/active-directory/develop/scenario-web-api-call-api-overview)
- [Bureaublad-app](/azure/active-directory/develop/scenario-desktop-overview)
- [Daemon-app](/azure/active-directory/develop/scenario-daemon-overview)
- [Mobiele app](/azure/active-directory/develop/scenario-mobile-overview)
 
> [!NOTE] 
> Wanneer een toepassing overschakelt naar het gebruik als uw autoriteit, worden de `login.microsoftonline.com` tokens ondertekend door deze nieuwe instantie. Als u resourcetoepassingen host die door andere apps worden ingesproken, moet u lax tokenvalidatie toestaan. Dit betekent dat uw app tokens moet toestaan die zijn ondertekend door de openbare Azure AD Germany- en Azure AD-cloud. Deze lax-tokenvalidatie is nodig totdat alle clienttoepassingen die uw service bellen, volledig zijn gemigreerd naar de openbare Azure AD-cloud. Na de migratie hoeft uw resourcetoepassing alleen tokens te accepteren die zijn ondertekend door de openbare Azure AD-cloud.

**Wat moet ik bijwerken?**

1. Als u een toepassing host in Azure Germany die wordt gebruikt om Gebruikers van Azure Germany Office 365 Duitsland te verifiëren, moet u ervoor zorgen dat deze wordt gebruikt als de autoriteit in de `https://login.microsoftonline.com` verificatiecontext.

    - Zie Azure AD-verificatiecontexten.
    - Dit geldt zowel voor verificatie voor uw toepassing als voor verificatie voor api's die door uw toepassing worden gebeld (dat wil zeggen Microsoft Graph, Azure AD Graph, Azure Resource Manager).

2. Werk Azure AD Graph eindpunt bij `https://graph.windows.net` als .

3. Ms-Graph eindpunt bijwerken als `https://graph.microsoft.com` .

4. Werk alle Duitse cloud-eindpunten bij (zoals die voor Exchange Online en SharePoint Online) die door uw toepassingen worden gebruikt als die van de openbare cloud.

5. Omgevingsparameters bijwerken `AzurePublic` die moeten worden `AzureGermany` (in plaats van) in beheerhulpmiddelen en scripts voor:

    - [Azure PowerShell](/powershell/azure/install-az-ps)
    - [Azure AD PowerShell (MSOnline)](/powershell/azure/active-directory/overview)
    - [Azure AD PowerShell (AzureAD)](/powershell/azure/active-directory/install-adv2)
    - [Azure CLI](/cli/azure/install-azure-cli)
 
**Hoe zit het met toepassingen die ik publiceer?**

Als u een toepassing publiceert die beschikbaar is voor gebruikers buiten uw tenant, moet u mogelijk uw toepassingsregistratie wijzigen om de continuïteit te waarborgen. Andere tenants die uw toepassing gebruiken, kunnen op een ander tijdstip worden verplaatst dan uw tenant. Om ervoor te zorgen dat ze nooit toegang tot uw toepassing verliezen, moet u toestemming geven dat uw app wordt gesynchroniseerd van Azure Germany naar Azure public.

## <a name="additional-considerations"></a>Aanvullende overwegingen

Hier zijn enkele extra aandachtspunten voor Azure AD:

- Voor federatief verificatie:

  - U mag geen federatief domein maken, promoten of degraderen terwijl de tenantovergang bezig is. Nadat de migratie naar de Azure AD-service is voltooid (de tenant is volledig voltooid), kunt u het beheer van federatief domeinen hervatten.

  - Als u federatieverificatie gebruikt met AD FS (Active Directory Federation Services), moet u tijdens de migratie geen wijzigingen aanbrengen in url's van de probleemgever die voor alle verificatie met uw on-premises Active Directory Domain Services (AD DS) wordt gebruikt. Als u url's voor uitgevende gebruikers verandert, kan dit leiden tot verificatiefouten voor gebruikers in het domein. U kunt URL's voor uitgevende uitgeven rechtstreeks wijzigen in AD FS of wanneer een domein wordt geconverteerd van beheerd naar federatief en omgekeerd. Microsoft raadt klanten aan geen federatief domein toe te voegen, te verwijderen of te converteren in de Azure AD-tenant die wordt gemigreerd. U kunt URL's voor uitgevende uri's wijzigen nadat de migratie volledig is voltooid.

- Voor netwerken:

  - Het maken van IPv6-netwerken werkt niet in de Azure-portal, `http://portal.microsoftazure.de/` . Gebruik de Azure-portal bij `https://portal.azure.com` om IPv6-netwerken te maken.
 
   - U kunt geen vertrouwde IP-adresbereiken maken voor MFA-serviceinstellingen (Azure Multi-Factor Authentication) vanuit de Microsoft Cloud Deutschland-portal. Gebruik de Azure AD-portal voor Office 365 services om vertrouwde IP-adresbereiken voor Azure MFA te maken.


- Voor voorwaardelijke toegang: 

  - Beleid voor voorwaardelijke toegang met de volgende grant-besturingselementen wordt pas ondersteund nadat de migratie naar Office 365 services is voltooid (na de fase [Azure AD-migratie](ms-cloud-germany-transition.md#how-is-the-migration-organized) voltooien):

    - Compatibel apparaat vereisen
    - Goedgekeurde app vereisen
    - App-beveiligingsbeleid vereisen
    
  - De beleidsinterface Voorwaardelijke toegang geeft een foutieve waarschuwing over beveiligings defaults die zijn ingeschakeld voor de tenant, zelfs wanneer deze is uitgeschakeld en beleid voor voorwaardelijke toegang al bestaat voor de tenant. U moet de waarschuwing negeren of de serviceportal Office 365 gebruiken om beleidsregels voor voorwaardelijke toegang te beheren. 

- Intune-scenario's worden alleen ondersteund tegen wereldwijde eindpunten nadat de tenantmigratie is voltooid, inclusief alle migraties van office-werkbelastingen.

- Gebruikers van Microsoft Cloud Deutschland die de methode Mobile App Notification gebruiken voor MFA-aanvragen, zien de ObjectId (een GUID) van de gebruiker in plaats van de naam van de gebruikershoofdnaam (UPN) in de Microsoft Authenticator app. Nadat de migratie van de Azure AD-tenant is voltooid en wordt gehost in Office 365 services, worden Microsoft Authenticator activeringen van gebruikers weergegeven. Bestaande Microsoft Authenticator accounts blijven de gebruiker ObjectId weergeven, maar ze blijven werken voor meldingen van mobiele apps. 

- Voor tenants die na 22 oktober 2019 zijn gemaakt, kunnen beveiligings defaults automatisch worden ingeschakeld voor de tenant wanneer deze wordt gemigreerd naar de Office 365 service. Tenantbeheerders kunnen ervoor kiezen om beveiligingsinstellingen ingeschakeld te laten en zich te registreren voor MFA, of ze kunnen de functie uitschakelen. Zie Beveiligingsinstellingen uitschakelen voor meer [informatie.](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults) 

  > [!NOTE]
  > Organisaties die niet automatisch zijn ingeschakeld tijdens de migratie, kunnen in de toekomst nog steeds automatisch worden geregistreerd, omdat de functie voor het inschakelen van beveiligings defaults wordt uitgerold in de Office 365 service. Beheerders die ervoor kiezen om beveiligingsinstellingen expliciet uit te schakelen of in te schakelen, kunnen dit doen door de functie bij te werken onder **Azure Active Directory > Eigenschappen.** Nadat de functie expliciet is ingeschakeld door de beheerder, wordt deze niet automatisch ingeschakeld.

- Er wordt een waarschuwing gegeven over de versie van Azure AD Verbinding maken in de Office 365 Germany-portal en in de Office 365 portal zodra de tenant is gemigratied. Dit kan worden genegeerd als de waarschuwing voor de versie niet meer wordt weergegeven nadat de migratie is voltooid. Als er een waarschuwing is, vóór of na de migratie, moet Azure AD Verbinding maken worden bijgewerkt. In het waarschuwingsbericht staat: 'We hebben gedetecteerd dat u een verouderd hulpprogramma voor adreslijstsynchronisatie gebruikt. We raden u aan naar het Microsoft Downloadcentrum te gaan om de nieuwste versie van Azure AD-Verbinding maken.

## <a name="more-information"></a>Meer informatie

Aan de slag:

- [Migratie van Microsoft Cloud Deutschland naar Office 365 services in de nieuwe Duitse datacenterregio's](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland-migratiehulp](https://aka.ms/germanymigrateassist)
- [Opt-in voor migratie](ms-cloud-germany-migration-opt-in.md)
- [Klantervaring tijdens de migratie](ms-cloud-germany-transition-experience.md)

Door de overgang lopen:

- [Acties en effecten voor de migratiefasen](ms-cloud-germany-transition-phases.md)
- [Extra pre-work](ms-cloud-germany-transition-add-pre-work.md)
- Aanvullende informatie voor [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [apparaten,](ms-cloud-germany-transition-add-devices.md) [ervaringen](ms-cloud-germany-transition-add-experience.md)en [AD FS.](ms-cloud-germany-transition-add-adfs.md)

Cloud-apps:

- [Dynamics 365-migratieprogrammagegevens](/dynamics365/get-started/migrate-data-german-region)
- [Power BI migratieprogrammagegevens](/power-bi/admin/service-admin-migrate-data-germany)
- [Aan de slag met uw Microsoft Teams upgrade](/microsoftteams/upgrade-start-here)