---
title: Geïntegreerde apps en Azure AD voor Microsoft 365 beheerders
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection: M365-subscription-management
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: cb2250e3-451e-416f-bf4e-363549652c2a
description: Meer informatie over het registreren en beheren Office 365 geïntegreerde apps in Azure AD, zodat app-autorisaties kunnen worden uitgevoerd op het niveau van de globale beheerder.
ms.openlocfilehash: 0b7392984b77b01abb0992fea5db62b80ed9fb6c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909772"
---
# <a name="integrated-apps-and-azure-ad-for-microsoft-365-administrators"></a>Geïntegreerde apps en Azure AD voor Microsoft 365 beheerders

Geïntegreerde apps beheren is meer dan alleen het beheren [van gebruikers toestemming voor apps.](../admin/misc/user-consent.md) Met de komst van de MICROSOFT 365 REST-API's kunnen gebruikers apps toegang verlenen tot hun Microsoft 365-gegevens, zoals e-mail, agenda's, contactpersonen, gebruikers, groepen, bestanden en mappen. Gebruikers moeten standaard voor elke app afzonderlijk machtigingen verlenen. 

Maar dit wordt niet goed geschaald als u een app eenmaal wilt machtigen op het niveau van de globale beheerder en deze wilt uitrollen naar uw hele organisatie via het start startmodel voor apps. Hiervoor moet u de app registreren in Azure Active Directory (Azure AD). Er zijn enkele stappen die u moet uitvoeren voordat u een app kunt registreren in Azure AD en enkele achtergrondinformatie die u moet weten waarmee u apps in uw organisatie Microsoft 365 beheren.
  
## <a name="azure-ad-resources-for-microsoft-365-admins"></a>Azure AD-bronnen voor Microsoft 365 beheerders

U moet deze twee taken uitvoeren voordat u uw Microsoft 365 kunt beheren in Azure AD.
  
|Vereisten|Opmerkingen|
|:-----|:-----|
|[Uw gratis Azure AD-abonnement gebruiken](../compliance/use-your-free-azure-ad-subscription-in-office-365.md) <br/> |Elk betaald abonnement op Microsoft 365 wordt geleverd met een gratis abonnement op Azure AD. U kunt Azure AD gebruiken om uw apps te beheren en gebruikers- en groepsaccounts te maken en te beheren. Als u Azure AD wilt gebruiken, gaat u naar de Azure-portal bij en meldt u zich [https://portal.azure.com](https://portal.azure.com) aan met uw Microsoft 365 account.  <br/> |
|[Gebruikers toestemming voor apps beheren](../admin/misc/user-consent.md) <br/> |U moet de toestemming van gebruikers voor apps beheren om apps van derden toegang te geven tot gebruikersgegevens Microsoft 365 en om apps te registreren in Azure AD. Als bijvoorbeeld iemand een app van derden gebruikt, kan door die app toestemming worden gevraagd voor toegang tot de agenda en het bewerken van bestanden in een OneDrive-map.  <br/> |
   
Voor Microsoft 365 apps moet u kennis hebben van apps in Azure AD. Gebruik deze artikelen om u de achtergrond te geven die u nodig hebt.
  
|Artikel|Opmerkingen|
|:-----|:-----|
|[Maak kennis met Microsoft 365 start- en app](https://support.microsoft.com/office/meet-the-microsoft-365-app-launcher-79f12104-6fed-442f-96a0-eb089a3f476a) <br/> |Als u nieuw bent in het start start- en start- en gebruiksdatum voor apps, vraagt u zich misschien af wat het is en hoe u het kunt gebruiken. Het starthulp voor apps is ontworpen om u te helpen bij uw apps te komen vanaf elke locatie in Microsoft 365.  <br/> |
|[Office 365 overzicht van beheer-API's](/office/office-365-management-api/office-365-management-apis-overview) <br/> |Met de Microsoft 365-beheer-API's kunt u toegang geven tot uw Microsoft 365-gegevens, inclusief de dingen die ze het belangrijkst vinden: hun e-mail, agenda's, contactpersonen, gebruikers en groepen, bestanden en mappen. <br/> |
|[Toepassingen integreren in Azure AD](/azure/active-directory/develop/quickstart-v1-add-azure-ad-app) <br/> | Meer informatie over toepassingen die zijn geïntegreerd met Azure AD, hoe u uw toepassing registreert, concepten begrijpt achter een geregistreerde toepassing en meer informatie over huisstijlrichtlijnen voor toepassingen met meerdere tenants.  <br/> |
|[Aangepaste tegels toevoegen aan het start- en start-](/office365/admin/manage/customize-the-app-launcher)  <br/> |Met het start start- en Microsoft 365 kunnen gebruikers hun apps gemakkelijker vinden en openen. In dit artikel worden de manieren beschreven waarop u als ontwikkelaar uw apps kunt laten verschijnen in de start-programma's voor apps van gebruikers en ze ook eenmalige aanmeldingservaring (SSO) kunt bieden met hun Microsoft 365 referenties.  <br/> |
|[Zelfstudies voor Azure AD-integratie](/azure/active-directory/saas-apps/tutorial-list) <br/> |Het doel van deze zelfstudies is om u te laten zien hoe u Azure AD SSO configureert voor SaaS-toepassingen van derden.  <br/> |
|[Verificatiescenario's voor Azure AD](/azure/active-directory/develop/authentication-vs-authorization) <br/> |Azure AD vereenvoudigt verificatie voor ontwikkelaars door identiteit als service aan te bieden, met ondersteuning voor industriestandaardprotocollen zoals OAuth 2.0 en OpenID-Verbinding maken, en open source-bibliotheken voor verschillende platforms, zodat u snel kunt beginnen met coderen. Dit document helpt u inzicht te krijgen in de verschillende scenario's die Azure AD ondersteunt en laat zien hoe u aan de slag kunt.  <br/> |
|[Toepassingstoegang](/azure/active-directory/manage-apps/what-is-access-management) <br/> |Azure AD maakt eenvoudige integratie mogelijk met veel van de populaire software-as-a-servicetoepassingen van vandaag. Het biedt identiteits- en toegangsbeheer en biedt een Access Panel voor gebruikers waar ze kunnen ontdekken welke toepassingstoegang ze hebben en waar ze SSO kunnen gebruiken om toegang te krijgen tot hun toepassingen. In dit artikel vindt u koppelingen naar de gerelateerde bronnen waarmee u meer informatie kunt krijgen over de uitbreidingen voor toepassingstoegang voor Azure AD en hoe u hieraan kunt bijdragen.  <br/> |
|[Uw persoonlijke ervaring Office 365 personaliseren](https://support.microsoft.com/office/personalize-your-office-365-experience-eb34a21b-52fa-4fbf-a8d5-146132242985) <br/> |U kunt snel toegang krijgen tot de apps die u elke dag gebruikt door apps toe te voegen of te verwijderen in Microsoft 365 start- en Microsoft 365 apps.  <br/> |