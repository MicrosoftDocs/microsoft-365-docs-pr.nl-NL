---
title: Zelfregistratie gebruiken in uw organisatie
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- okr_SMB
search.appverid:
- MET150
ms.assetid: 4f8712ff-9346-4c6c-bb63-a21ad7a62cbd
description: Lees meer over het aanmelden bij Microsoft 365 selfservice en beschikbare selfservice Programma's zoals Microsoft Power apps, Microsoft flow en Dynamics 365 voor financiering.
ms.openlocfilehash: 21e41661141a817a1751c80608035d839d2e3952
ms.sourcegitcommit: 7355cc8871cde5fac6d7d6dcecc3e41e35601623
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/04/2020
ms.locfileid: "48906571"
---
# <a name="using-self-service-sign-up-in-your-organization"></a>Zelfregistratie gebruiken in uw organisatie

Met selfservice registratie kunnen gebruikers in uw organisatie zich makkelijker registreren voor online services van Microsoft. We bellen u dit abonnement "selfservice voor eenmalige aanmelding", omdat uw gebruikers zich kunnen registreren voor het gebruik van services die door uw abonnement zijn betaald, of het gebruik van gratis services, zonder dat u om namens de actie hoeft te ondernemen.
  
## <a name="how-self-service-sign-up-works"></a>Hoe werkt selfservice registratie?

Hieronder volgt een voorbeeld van zelfregistratie bij een onderwijsinstelling. De procedure is dezelfde voor elke organisatie die selfservice-programma's heeft ingeschakeld in de tenant.
  
1. Leerlingen, studenten en faculteitsleden hebben een e-mailadres dat duidelijk maakt dat ze verbonden zijn aan uw instelling. In het e-mailadres jakob@uw.edu kan bijvoorbeeld een leerling/student voor de University of Washington aangeven.
2. Leerlingen en studenten gaan naar [onze](https://go.microsoft.com/fwlink/p/?LinkId=536628)website en gebruiken hun e-mailadres om u aan te melden voor de services die door uw organisatie worden aangeboden, zoals microsoft 365-apps voor ondernemingen. Ze kunnen zich ook aanmelden voor gratis services die we bieden.
3. U valideert hun e-mailadres en ze kunnen direct Microsoft 365, Power BI of andere services gaan gebruiken.
4. Als bedrijfsbeheerder kunt u zien wie zich heeft geregistreerd voor een abonnement door het abonnement te selecteren op de pagina **licentie** in het microsoft 365-Beheercentrum. Op deze manier kunt u zien wanneer er nieuwe of niet-herkende licenties zijn voor services in uw Tenant. Als u wilt instellen of gebruikers zich kunnen registreren voor selfservice abonnementen, gebruikt u de PowerShell [-cmdlet Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) met de parameter **AllowAdHocSubscriptions** . Voor meer informatie raadpleegt [u hoe kan ik selfservice-instellingen beheren?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="available-self-service-programs"></a>Beschikbare selfservice-programma 's

Hieronder vindt u de beschikbare selfservice Programma's. Deze lijst wordt bijgewerkt wanneer nieuwe Programma's worden toegevoegd.
  
| Programma <br/> | Beschrijving <br/> | Aanvullende informatie <br/> | Website voor zelfregistratie <br/> |
|:-----|:-----|:-----|:-----|
|Office 365 a1 * * * * <br/> |Leerlingen en studenten kunnen een e-mailadres van school gebruiken om u aan te melden voor gratis Office 365 en Office-apps voor het web te downloaden, 1 TB OneDrive-cloudopslag en SharePoint Online voor klas-, team-en projectsites.  <br/> |[Office 365 Education - veelgestelde technische vragen](https://go.microsoft.com/fwlink/p/?LinkId=536625) <br/> |[Office 365 Education](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Office 365 a1 plus** <br/> |In aanmerking komende studenten en docenten kunnen zich registreren voor Office 365 a1 plus, waaronder alles wat hierboven wordt genoemd plus Microsoft 365-apps voor Enterprise. Microsoft 365-apps voor Enterprise is productiviteitssoftware, waaronder Word, PowerPoint, Excel, Outlook, OneNote, Publisher, Access en Skype voor bedrijven, die op uw desktop-of laptopcomputer is geïnstalleerd.  <br/> |[Office 365 Education - veelgestelde technische vragen](https://go.microsoft.com/fwlink/p/?LinkId=536625) <br/> |[Office 365 Education](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Power BI** <br/> |Met Power BI kunnen gebruikersgegevens visualiseren, ontdekkingen delen en samenwerken op intuïtieve nieuwe manieren. <br/> Als u al een abonnement hebt op uw organisatie, kunt u ook licenties voor ' Power BI Pro voor individuele gebruikers proefversies ' weergeven, waarin gebruikers beperkte, gratis toegang krijgen tot geavanceerde mogelijkheden.  <br/> |[Power BI in uw organisatie](https://go.microsoft.com/fwlink/p/?LinkId=536626) <br/> |[Microsoft Power BI](https://go.microsoft.com/fwlink/p/?LinkId=536629) <br/> |
|**Rights Management Services (RMS)** <br/> |RMS voor personen is een gratis selfservice-abonnement voor gebruikers in een organisatie die vertrouwelijke bestanden hebben ontvangen die zijn beveiligd met Azure Rights Management (Azure RMS), maar hun IT-afdeling heeft Azure Rights Management (Azure RMS) of Active Directory Rights Management Services (AD RMS) niet geïmplementeerd.  <br/> |[RMS voor personen en Azure Information Protection](https://go.microsoft.com/fwlink/p/?LinkId=536627) <br/> |[Microsoft Rights Management portal](https://portal.azure.com/) zodat u kunt controleren of u een bepaald met toegangsrechten beveiligd document kunt openen.  <br/> |
|**Microsoft PowerApps** <br/> |In PowerApps kunt u organisatiegegevens beheren door een app uit te voeren die u hebt gemaakt, of die iemand anders heeft gemaakt en met u heeft gedeeld. Apps worden uitgevoerd op mobiele apparaten zoals telefoons, maar u kunt ze ook uitvoeren in een browser door Dynamics 365 te openen. U kunt allerlei verschillende soorten apps maken, zonder dat u een programmeertaal zoals C# hoeft te leren.  <br/> |[Aanmelding voor PowerApps via selfservice](https://go.microsoft.com/fwlink/p/?linkid=841461) <br/> |[Microsoft PowerApps](https://go.microsoft.com/fwlink/p/?linkid=841462) <br/> |
|**Dynamics 365 for Financials** <br/> |Een complete oplossing voor zakelijk en financieel beheer voor kleine en middelgrote bedrijven. Met Dynamics 365 for Financials kunt u vanaf dag één eenvoudiger inkopen, verkopen, factureren en rapporteren.  <br/> |[Microsoft Dynamics 365 for Financials](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |[Microsoft Dynamics 365 for Financials](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |
|**Microsoft Dynamics 365 for Operations** <br/> |Verhoog de snelheid van zakendoen. De uitgebreide ERP-hulpmiddelen in 365 Dynamics for Operations bieden globale schaalbaarheid en digitale bedrijfsinformatie waarmee uw organisatie in het gewenste tempo kan groeien.  <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |
|**Microsoft AppSource** <br/> |Microsoft AppSource is een verzameling zakelijke SaaS-apps (Software as a Service) die zijn gebaseerd op het Microsoft-cloudplatform. AppSource biedt honderden apps, invoegtoepassingen en inhoudspakketten die de functionaliteit van Microsoft-producten zoals Azure, Dynamics 365, Office 365 en Power BI verlengen.  <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |
|**Microsoft Partner Network** <br/> |Het Microsoft Partner Network biedt drie typen lidmaatschappen. Elk type biedt een aantal voordelen om uw bedrijf te helpen groeien. Naarmate u uw doelstellingen realiseert, kunt u deelnemen aan het programma op het niveau dat aansluit bij uw unieke behoeften om zo toegang te krijgen tot meer voordelen en uw relatie met ons en met andere partners in het netwerk te verdiepen.  <br/> |[Microsoft Partner Network](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |[Microsoft Partner Network](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |
|**Microsoft Business Center** <br/> |Microsoft Business Center is de portal voor klanten die aankopen hebben gedaan via de Microsoft Products and Services Agreement (MPSA). <br/> |[Quick Start: Register for the Microsoft Business Center](https://go.microsoft.com/fwlink/p/?linkid=841479) (Snel aan de slag: Registreren voor het Microsoft Business Center) <br/> |[Microsoft Business Center](https://go.microsoft.com/fwlink/p/?linkid=841470) <br/> |
|**Microsoft volume licentie service centrum** <br/> |Het Microsoft volume licentie service centrum toont licenties die zijn aangeschaft onder Enterprise, SELECT, education (school of school), Open Value, open licentie en ISV Royalty's overeenkomsten.  <br/> |[VLSC-training en-bronnen](https://www.microsoft.com/en-us/Licensing/existing-customer/vlsc-training-and-resources.aspx) <br/> |[Service Centrum voor volume licenties](https://www.microsoft.com/Licensing/servicecenter/default.aspx) <br/> |
|**Minecraft Education Edition** <br/> |Door Minecraft in te zetten als een onderwijsplatform kan het onderwijzend personeel leerlingen en studenten motiveren en inspireren om meer te bereiken. Daarnaast kan op deze manier een passie voor leren worden ontwikkeld. Word lid van een community van docenten en ontdek hoe u met Minecraft de mogelijkheden van leerlingen en studenten optimaal kunt benutten.  <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841480) <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841471) <br/> |
|**Microsoft Stream** <br/> |Upload en deel video's binnen uw organisatie om verbeteringen te realiseren op het gebied van communicatie, participatie en leren.  <br/> |[Sign up &amp; Day 0 experience](https://go.microsoft.com/fwlink/p/?linkid=841472) <br/> |[Microsoft Stream](https://go.microsoft.com/fwlink/p/?linkid=841473) <br/> |
|**Automatisch aan de macht** <br/> |Automatisch automatiseren is een product voor het instellen van geautomatiseerde werkstromen tussen uw favoriete apps en services voor het synchroniseren van bestanden, het ontvangen van meldingen, het verzamelen van gegevens en nog veel meer.  <br/> |[Registreren en aanmelden voor automatisch aan/uit](https://docs.microsoft.com/power-automate/sign-up-sign-in) <br/> |[Automatisch aan de macht](https://go.microsoft.com/fwlink/p/?linkid=841465) <br/> |
|**Power virtuele agenten** <br/> |Met Power Point kunt u in een handomdraai met behulp van een begeleide, niet-gecodeerde grafische interface, zonder dat u gegevens wetenschappers of ontwikkelaars hebt, eenvoudig krachtige bots maken. Met Power virtuele agenten wordt een groot aantal belangrijke problemen met bot gebouwd in de branche besproken. Met deze functie wordt de opening geëlimineerd tussen de technici van de materie en de ontwikkelteams die de bots samenstellen, en de lange latentie tussen teams die een probleem erkennen en de bot bijwerken om dit op te lossen.  <br/> |[Licentie-en toegangsgegevens](https://go.microsoft.com/fwlink/?linkid=2113708) <br/> |[Registreren voor Power virtuele agenten](https://aka.ms/TryPVA) <br/> |
|**Azure AD B2B** <br/> |Met de samenwerking van Azure Active Directory (Azure AD) Business-to-Business (B2B) kunt u externe gebruikers (of gastgebruikers) uitnodigen om uw betaalde Azure AD-services te gebruiken. Sommige functies zijn gratis, maar voor elke betaalde Azure AD-functies kunt u maximaal vijf gastgebruikers uitnodigen voor elke Azure AD-licentie die u bezit voor een werknemer of een niet-gastgebruiker in uw Tenant. <br/> |[Self-service voor Azure AD B2B-samenwerking registreren](https://docs.microsoft.com/azure/active-directory/b2b/self-service-portal) <br/> |[Licentie-instructies voor de Azure Active Directory B2B-samenwerking](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) <br/> |
