---
title: Aanvullende algemene informatie over de migratie van Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
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
description: 'Overzicht: aanvullende algemene informatie over services wanneer u overstapt van Microsoft Cloud Duitsland (Microsoft Cloud Deutschland) naar Office 365-Services in het nieuwe Duitse datacenter-gebied.'
ms.openlocfilehash: 93692200f2519dbc647bb4e81b4bd8c646815858
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558428"
---
# <a name="additional-general-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Aanvullende algemene informatie over de migratie van Microsoft Cloud Deutschland

In de volgende secties vindt u aanvullende informatie over services, voorwerkings overwegingen en de ervaring met klanten.

## <a name="azure-active-directory"></a>Microsoft Azure Active Directory

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

    - [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-2.8.0&viewFallbackFrom=azurermps-5.6.0)
    - [Azure AD PowerShell (MSOnline)](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)
    - [Azure AD PowerShell (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0)
    - [Azure CLI](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest)
 
**Hoe zit het met toepassingen die ik publiceer?**

Als u een toepassing publiceert die beschikbaar is voor gebruikers die zich buiten de Tenant bevinden, moet u mogelijk de registratie van de toepassing wijzigen om zo de continuïteit te waarborgen. Andere tenants die uw toepassing gebruiken, kunnen op een ander moment worden verplaatst dan de Tenant. Als u er zeker van wilt zijn dat ze geen toegang meer hebben tot de toepassing, moet u toestemming verlenen voor het synchroniseren van de app van Azure Duitsland naar Azure public.

### <a name="additional-considerations"></a>Aanvullende overwegingen

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

## <a name="exchange-online"></a>Exchange Online 

- `myaccount.msft.com` functioneert alleen na de cutover van Office 365. Koppelingen maken een foutmelding ' er is een fout opgetreden ' wordt weergegeven tot die tijd.

- Gebruikers van Outlook Web app die toegang krijgen tot een gedeeld postvak in de andere omgeving (bijvoorbeeld een gebruiker in de Duitse omgeving opent een gedeeld postvak in de algemene omgeving), wordt u gevraagd om een tweede keer te verifiëren. De gebruiker moet zich eerst verifiëren en toegang tot zijn postvak in `outlook.office.de` , en dan het gedeelde postvak openen `outlook.office365.com` . De persoon moet een tweede keer verifiëren wanneer ze toegang krijgen tot gedeelde bronnen die worden gehost in de andere service.

- Voor bestaande klanten van Microsoft Cloud Deutschland of deze in overgang, wanneer een gedeeld postvak wordt toegevoegd aan Outlook met behulp van **bestand > informatie > account toevoegen**, mislukt het weergeven van Agendamachtigingen (de Outlook-client probeert de rest-API te gebruiken `https://outlook.office.de/api/v2.0/Me/Calendars` ). Klanten die een account willen toevoegen om Agendamachtigingen weer te geven, kunnen de registersleutel toevoegen, zoals beschreven in [wijzigingen in de gebruikerservaring voor het delen van een agenda in Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) om ervoor te zorgen dat deze actie mislukt. Met deze registersleutel kunt u de hele organisatie implementeren met behulp van Groepsbeleid.

- Tijdens de migratie fase, met behulp van de PowerShell-cmdlets **New-migrationEndpoint**, **set-migrationEndpoint** en **test-MigrationsServerAvailability** kunnen fouten veroorzaken (fout op proxy). Dit gebeurt wanneer het arbitrage postvak naar de wereld is gemigreerd, maar het postvak van de beheerder niet al dan niet is omgekeerd. U kunt dit oplossen door tijdens het maken van de Tenant PowerShell-sessie het arbitrage postvak als de routerings Hint in de **ConnectionUri** te gebruiken. Voorbeeld: `New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de" -Credential $UserCredential -Authentication Basic -AllowRedirection`

- Als u Exchange Online hybride gebruikt:

    - U moet de wizard hybride configuratie (HCW) opnieuw uitvoeren om on-premises configuratie bij te werken bij Microsoft Cloud Deutschland vóór de overgang, en de HCW opnieuw te uitvoeren bij het opschonen van Office 365-Services. Als u aangepaste domeinen gebruikt, zijn er mogelijk extra DNS-updates vereist.

Zie de sectie Exchange Online van [acties en effecten voor migratie fasen](ms-cloud-germany-transition-phases.md#exchange-online)voor meer informatie over acties die moeten worden uitgevoerd tijdens de migratie fase van deze werkbelasting of over de gevolgen voor beheer of gebruik.

## <a name="office-services"></a>Office-services

De MRU-service (most recently used) in Office is een cutover van de Duitse service voor Office 365-Services, geen migratie. Alleen MRU-koppelingen uit de kant van Office 365-Services zijn zichtbaar na de migratie van de portal van Office.com. MRU-koppelingen uit de Duitsland-service zijn niet zichtbaar als MRU-koppelingen in Office 365-Services. In Office 365 zijn de MRU-koppelingen alleen toegankelijk nadat de Tenant migratie is voltooid.

## <a name="sharepoint-online-and-onedrive"></a>SharePoint Online en OneDrive

- Na voltooiing van de SharePoint Online-migratie naar de Duitse regio, worden gegevens indexen opnieuw opgebouwd. Functies die afhankelijk zijn van zoekindexen, kunnen worden beïnvloed wanneer u de indexering opnieuw uitvoert.

- Als in uw organisatie nog steeds SharePoint 2010-werkstromen worden gebruikt, werken ze niet meer na 31 december 2021. SharePoint 2013-werkstromen blijven ondersteund, alhoewel dit standaard is uitgeschakeld voor nieuwe tenants vanaf 1 november 2020. Na de migratie naar de SharePoint Online-service is het raadzaam om over te stappen op geautomatiseerde of andere ondersteunde oplossingen.

- Na voltooiing van de OneDrive-migratie naar de Duitse regio, worden gegevens indexen opnieuw opgebouwd. Functies die afhankelijk zijn van zoekindexen, kunnen worden beïnvloed wanneer opnieuw indexeren wordt uitgevoerd.


## <a name="more-information"></a>Meer informatie

Aan de slag:

- [Migratie van Microsoft Cloud Deutschland naar Office 365-Services in de nieuwe Duitse datacenter gebieden](ms-cloud-germany-transition.md)
- [Migratie ondersteuning voor Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Hoe kan ik me aanmelden voor migratie?](ms-cloud-germany-migration-opt-in.md)
- [Gebruikerservaring tijdens de migratie](ms-cloud-germany-transition-experience.md)

Door de overgang navigeren:

- [Acties en effecten bij migratie fasen](ms-cloud-germany-transition-phases.md)
- [Extra vooraf werken](ms-cloud-germany-transition-add-pre-work.md)
- Aanvullende informatie over [Services](ms-cloud-germany-transition-add-general.md), [apparaten](ms-cloud-germany-transition-add-devices.md), [ervaringen](ms-cloud-germany-transition-add-experience.md)en [AD FS](ms-cloud-germany-transition-add-adfs.md).

Cloud-apps:

- [Dynamics 365-migratieprogramma gegevens](https://aka.ms/d365ceoptin)
- [Informatie over migratieprogramma's voor Power BI](https://aka.ms/pbioptin)
- [Aan de slag met uw upgrade naar Microsoft teams](https://aka.ms/SkypeToTeams-Home)
