---
title: Geïntegreerde apps en Azure AD voor Microsoft 365-beheerders
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
description: Meer informatie over het registreren en beheren van geïntegreerde apps van Office 365 in azure AD, zodat app-autorisaties kunnen worden toegestaan op het niveau van de globale beheerder.
ms.openlocfilehash: 1e84b5e6f82848bf1d100004bcd2711ad2e9ed39
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384901"
---
# <a name="integrated-apps-and-azure-ad-for-microsoft-365-administrators"></a>Geïntegreerde apps en Azure AD voor Microsoft 365-beheerders

Het is nog meer om geïntegreerde apps te beheren dan alleen [voor het beheren van gebruikers toestemming voor apps](https://docs.microsoft.com/microsoft-365/admin/misc/integrated-apps). Met de komst van de Microsoft 365 REST-Api's kunnen gebruikers apps toegang verlenen tot hun Microsoft 365-gegevens, zoals e-mail, agenda's, contactpersonen, gebruikers, groepen, bestanden en mappen. Standaard moeten gebruikers afzonderlijke machtigingen verlenen voor elke app. 

Dit niet goed is geschaald als u een app één keer op het niveau van de globale beheerder wilt machtigen en deze wilt samenvouwen naar de hele organisatie via het startprogramma voor apps. Hiervoor moet u de app registreren in azure Active Directory (Azure AD). U moet de volgende stappen uitvoeren voordat u een app kunt registreren in azure AD en enige achtergrondinformatie die u moet weten die u kan helpen bij het beheren van apps in uw Microsoft 365-organisatie.
  
## <a name="azure-ad-resources-for-microsoft-365-admins"></a>Azure AD-resources voor Microsoft 365-beheerders

U dient deze twee taken te doen voordat u uw Microsoft 365-apps kunt beheren in azure AD.
  
|Vereisten|Ontvangen|
|:-----|:-----|
|[Uw gratis Azure AD-abonnement gebruiken](https://docs.microsoft.com/microsoft-365/compliance/use-your-free-azure-ad-subscription-in-office-365) <br/> |Elk betaald abonnement op Microsoft 365 is een gratis abonnement op Azure AD. U kunt Azure AD gebruiken voor het beheren van uw apps en het maken en beheren van gebruikers-en groepsaccounts. Als u Azure AD wilt gebruiken, gaat u naar de Azure-Portal op [https://portal.azure.com](https://portal.azure.com) en meldt u zich aan met uw Microsoft 365-account.  <br/> |
|[Gebruikers toestemming voor apps beheren](https://docs.microsoft.com/microsoft-365/admin/misc/integrated-apps) <br/> |U dient de gebruikers toestemming voor apps te beheren om apps van derden toegang te geven tot gegevens van Microsoft 365 en voor het registreren van apps in azure AD. Als bijvoorbeeld iemand een app van derden gebruikt, kan door die app toestemming worden gevraagd voor toegang tot de agenda en het bewerken van bestanden in een OneDrive-map.  <br/> |
   
Voor het beheren van Microsoft 365-apps moet u beschikken over apps in azure AD. Gebruik deze artikelen om u de achtergrond te geven die u nodig hebt.
  
|Artikel|Ontvangen|
|:-----|:-----|
|[Maak kennis met het startprogramma voor apps van Microsoft 365](https://support.microsoft.com/office/meet-the-microsoft-365-app-launcher-79f12104-6fed-442f-96a0-eb089a3f476a) <br/> |Als u nog geen ervaring hebt met het startprogramma voor apps, moet u zich misschien afvragen wat het is en hoe u het kunt gebruiken. Het startprogramma voor apps is bedoeld om u overal in Microsoft 365 toegang te bieden tot uw apps.  <br/> |
|[Overzicht van Office 365 Management Api's](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview) <br/> |Met de Microsoft 365-beheer-Api's kunt u toegang krijgen tot uw Microsoft 365-gegevens, waaronder de belangrijkste punten, de e-mail, agenda's, contactpersonen, gebruikers en groepen, bestanden en mappen. <br/> |
|[Toepassingen integreren in azure AD](https://docs.microsoft.com/azure/active-directory/develop/quickstart-v1-add-azure-ad-app) <br/> | Lees meer over de toepassingen die worden geïntegreerd met Azure AD en hoe u uw toepassing registreert, concepten achter een geregistreerde toepassing, en lees meer over de richtlijnen voor huisstijl voor toepassingen met meerdere tenants.  <br/> |
|[Aangepaste tegels toevoegen aan het startprogramma voor apps](https://docs.microsoft.com/office365/admin/manage/customize-the-app-launcher)  <br/> |Met het startprogramma voor apps in Microsoft 365 kunnen gebruikers makkelijker hun apps vinden en openen. In dit artikel wordt beschreven hoe u als een ontwikkelaar uw apps kan weergeven in de Start Programma's van gebruikers en ze ook een eenmalige aanmelding (SSO) verlenen met behulp van hun referenties van Microsoft 365.  <br/> |
|[Zelfstudies voor Azure AD-integratie](https://docs.microsoft.com/azure/active-directory/saas-apps/tutorial-list) <br/> |Het doel van deze zelfstudies is om u te laten zien hoe u Azure AD SSO kunt configureren voor SaaS-toepassingen van derden.  <br/> |
|[Verificatie scenario's voor Azure AD](https://go.microsoft.com/fwlink/?LinkId=617145) <br/> |Azure AD vergemakkelijkt verificatie voor ontwikkelaars door een identiteit als service te leveren, met ondersteuning voor industrie-standaardprotocollen zoals OAuth 2,0 en OpenID Connect, en open bron bibliotheken voor verschillende platformen waarmee u snel codering kunt starten. Dit document helpt u inzicht te krijgen in de verschillende scenario's die in azure AD worden ondersteund en toont u hoe u aan de slag kunt.  <br/> |
|[Toepassings toegang](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-access-management) <br/> |Azure AD zorgt voor eenvoudige integratie met tal van hedendaagse populaire software als een service (SaaS)-toepassing. Hiermee beschikt u over identiteits-en toegangsbeheer, en wordt er een toegangsvenster geboden voor gebruikers die ze kunnen detecteren welke toepassing ze hebben en wat ze eenmalige aanmelding kunnen gebruiken voor toegang tot hun toepassingen. Dit artikel bevat koppelingen naar de verwante bronnen voor meer informatie over de verbeteringen van toepassings toegang voor Azure AD en de manier waarop u hieraan een bijdrage kunt bieden.  <br/> |
|[Uw Office 365-ervaring personaliseren](https://support.microsoft.com/office/personalize-your-office-365-experience-eb34a21b-52fa-4fbf-a8d5-146132242985) <br/> |U kunt snel toegang krijgen tot de apps die u elke dag gebruikt door apps toe te voegen of te verwijderen in het startprogramma voor apps van Microsoft 365.  <br/> |

