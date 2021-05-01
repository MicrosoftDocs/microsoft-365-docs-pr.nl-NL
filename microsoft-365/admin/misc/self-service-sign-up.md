---
title: Selfservice-aanmelding gebruiken in uw organisatie
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
ms.custom:
- AdminSurgePortfolio
- okr_SMB
- commerce_signup
- PPM_pablom
ms.reviewer: seemg
search.appverid:
- MET150
description: Meer informatie over Microsoft 365 selfservice-aanmelding en beschikbare selfserviceprogramma's zoals Microsoft Power Apps, Microsoft Flow en Dynamics 365 voor Financiën.
ms.date: 03/17/2021
ms.openlocfilehash: a3257cf57d3a2579a250f90811c1bd644cd0d27d
ms.sourcegitcommit: 794f9767aaebe13ab1aead830b214ea674289d19
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/30/2021
ms.locfileid: "52107410"
---
# <a name="using-self-service-sign-up-in-your-organization"></a>Selfservice-aanmelding gebruiken in uw organisatie

Selfservice-aanmelding maakt het gemakkelijker voor gebruikers in uw organisatie om zich aan te melden voor onlineservices van Microsoft. We noemen dit aanmeldingsproces 'selfservice-aanmelding', omdat uw gebruikers zich kunnen registreren om services te gebruiken die door uw abonnement zijn betaald of gratis services kunnen gebruiken, zonder u te vragen actie te ondernemen namens hen.
  
## <a name="how-self-service-sign-up-works"></a>Hoe selfservice-aanmelding werkt

Hieronder volgt een voorbeeld van zelfregistratie bij een onderwijsinstelling. De procedure is dezelfde voor elke organisatie die selfservice-programma's heeft ingeschakeld in de tenant.
  
1. Leerlingen, studenten en faculteitsleden hebben een e-mailadres dat duidelijk maakt dat ze verbonden zijn aan uw instelling. Het e-mailadres van jakob@uw.edu kan bijvoorbeeld een student aan de Universiteit van Washington aangeven.
2. Studenten en onderwijsmedewerkers gaan naar [onze website](https://go.microsoft.com/fwlink/p/?LinkId=536628)en gebruiken hun e-mailadres om zich aan te melden voor de services die uw organisatie aanbiedt, zoals Microsoft 365-apps voor ondernemingen. Ze kunnen zich ook aanmelden voor gratis services die we bieden.
3. We valideren hun e-mailadres en vervolgens kunnen ze direct beginnen met Microsoft 365, Power BI of andere services.
4. Als bedrijfsbeheerder kunt u zien wie zich heeft aangemeld voor  een abonnement door het abonnement te selecteren op de pagina Licenties in het Microsoft 365 beheercentrum. Op deze manier kunt u zien wanneer er nieuwe of niet-herkende licenties voor services in uw tenant zijn. Als u wilt bepalen of gebruikers zich kunnen registreren voor selfservice-abonnementen, gebruikt u de PowerShell-cmdlet [Set-MsolCompanySettings](/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0&preserve-view=true) met de **parameter AllowAdHocSubscriptions.** Zie Hoe beheer ik [selfservice-instellingen?](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings) voor meer informatie.

## <a name="available-self-service-programs"></a>Beschikbare selfservice-programma 's

Hier volgen de selfservice-programma's die momenteel beschikbaar zijn Deze lijst wordt bijgewerkt wanneer er nieuwe programma's worden toegevoegd.
  
| Programma <br/> | Beschrijving <br/> | Aanvullende informatie <br/> | Website voor selfservice-aanmelding <br/> |
|:-----|:-----|:-----|:-----|
|Office 365 A1**** <br/> |Elke leerling of docent kan een e-mailadres van een school gebruiken om zich gratis Office 365 aan te melden en Office-apps voor het web te downloaden, 1 TB OneDrive cloudopslag en SharePoint Online voor klas-, team- en projectsites.  <br/> |[Office 365 Education - veelgestelde technische vragen](/microsoft-365/education/deploy/office-365-education-self-sign-up) <br/> |[Office 365 Education](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Office 365 A1 Plus** <br/> |In aanmerking komende leerlingen en studenten en docenten kunnen zich registreren voor Office 365 A1 Plus, met alle bovenstaande plus Microsoft 365-apps voor ondernemingen. Microsoft 365-apps voor ondernemingen is productiviteitssoftware, waaronder Word, PowerPoint, Excel, Outlook, OneNote, Publisher, Access en Skype voor Bedrijven, die is geïnstalleerd op uw desktop- of laptopcomputer.  <br/> |[Office 365 Education - veelgestelde technische vragen](/microsoft-365/education/deploy/office-365-education-self-sign-up) <br/> |[Office 365 Education](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Power BI** <br/> |Power BI stelt gebruikers in staat om gegevens te visualiseren, ontdekkingen te delen en op intuïtieve nieuwe manieren samen te werken. <br/> Als uw organisatie al een abonnement heeft, ziet u mogelijk ook licenties voor 'Power BI Pro Individual User Trial', die gebruikers beperkte, gratis toegang bieden tot geavanceerde mogelijkheden.  <br/> |[Power BI in uw organisatie](./power-bi-in-your-organization.md) <br/> |[Microsoft Power BI](https://go.microsoft.com/fwlink/p/?LinkId=536629) <br/> |
|**Rights Management Services (RMS)** <br/> |RMS voor personen is een gratis selfservice-abonnement voor gebruikers in een organisatie die vertrouwelijke bestanden hebben ontvangen die zijn beveiligd met Azure Rights Management (Azure RMS), maar hun IT-afdeling heeft Azure Rights Management (Azure RMS) of Active Directory Rights Management Services (AD RMS) niet geïmplementeerd.  <br/> |[RMS voor personen en Azure Information Protection](/azure/information-protection/rms-for-individuals) <br/> |[Microsoft Rights Management portal](https://portal.azure.com/) zodat u kunt controleren of u een bepaald met toegangsrechten beveiligd document kunt openen.  <br/> |
|**Microsoft PowerApps** <br/> |In PowerApps kunt u organisatiegegevens beheren door een app uit te voeren die u hebt gemaakt, of die iemand anders heeft gemaakt en met u heeft gedeeld. Apps worden uitgevoerd op mobiele apparaten zoals telefoons, maar u kunt ze ook uitvoeren in een browser door Dynamics 365 te openen. U kunt allerlei verschillende soorten apps maken, zonder dat u een programmeertaal zoals C# hoeft te leren.  <br/> |[Aanmelding voor PowerApps via selfservice](/powerapps/maker/signup-for-powerapps) <br/> |[Microsoft PowerApps](https://go.microsoft.com/fwlink/p/?linkid=841462) <br/> |
|**Dynamics 365 for Financials** <br/> |Een complete oplossing voor zakelijk en financieel beheer voor kleine en middelgrote bedrijven. Met Dynamics 365 for Financials kunt u vanaf dag één eenvoudiger inkopen, verkopen, factureren en rapporteren.  <br/> |[Microsoft Dynamics 365 for Financials](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |[Microsoft Dynamics 365 for Financials](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |
|**Microsoft Dynamics 365 for Operations** <br/> |Verhoog de snelheid van zakendoen. De uitgebreide ERP-hulpmiddelen in 365 Dynamics for Operations bieden globale schaalbaarheid en digitale bedrijfsinformatie waarmee uw organisatie in het gewenste tempo kan groeien.  <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |
|**Microsoft AppSource** <br/> |Microsoft AppSource is een verzameling zakelijke SaaS-apps (Software as a Service) die zijn gebaseerd op het Microsoft-cloudplatform. AppSource bevat honderden apps, invoegtoepassingen en inhoudspakketten waarmee de functionaliteit van Microsoft-producten zoals Azure, Dynamics 365, Office 365 en Power BI.  <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |
|**Microsoft Partner Network** <br/> |Het Microsoft Partner Network biedt drie typen lidmaatschappen. Elk type biedt een aantal voordelen om uw bedrijf te helpen groeien. Naarmate u uw doelstellingen realiseert, kunt u deelnemen aan het programma op het niveau dat aansluit bij uw unieke behoeften om zo toegang te krijgen tot meer voordelen en uw relatie met ons en met andere partners in het netwerk te verdiepen.  <br/> |[Microsoft Partner Network](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |[Microsoft Partner Network](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |
|**Microsoft Business Center** <br/> |Het Microsoft Business Center is de portal voor klanten die aankopen hebben gedaan via de Microsoft Products and Services Agreement (MPSA). <br/> |[Quick Start: Register for the Microsoft Business Center](https://go.microsoft.com/fwlink/p/?linkid=841479) (Snel aan de slag: Registreren voor het Microsoft Business Center) <br/> |[Microsoft Business Center](https://go.microsoft.com/fwlink/p/?linkid=841470) <br/> |
|**Microsoft Volume License Service Center** <br/> |In het Microsoft Volume License Service Center worden licenties weergegeven die zijn gekocht onder Enterprise, Select, Education (Campus of School), Open Value, Open License en ISV Royalty-overeenkomsten.  <br/> |[VLSC-training en -resources](https://www.microsoft.com/en-us/Licensing/existing-customer/vlsc-training-and-resources.aspx) <br/> |[Volumelicentieservicecentrum](https://www.microsoft.com/Licensing/servicecenter/default.aspx) <br/> |
|**Minecraft Education Edition** <br/> |Door Minecraft in te zetten als een onderwijsplatform kan het onderwijzend personeel leerlingen en studenten motiveren en inspireren om meer te bereiken. Daarnaast kan op deze manier een passie voor leren worden ontwikkeld. Word lid van een community van docenten en ontdek hoe u met Minecraft de mogelijkheden van leerlingen en studenten optimaal kunt benutten.  <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841480) <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841471) <br/> |
|**Microsoft Stream** <br/> |Upload en deel video's binnen uw organisatie om verbeteringen te realiseren op het gebied van communicatie, participatie en leren.  <br/> |[Sign up &amp; Day 0 experience](https://go.microsoft.com/fwlink/p/?linkid=841472) <br/> |[Microsoft Stream](https://go.microsoft.com/fwlink/p/?linkid=841473) <br/> |
|**Power Automate** <br/> |Power Automate is een product om u te helpen bij het instellen van geautomatiseerde werkstromen tussen uw favoriete apps en services om bestanden te synchroniseren, meldingen op te halen, gegevens te verzamelen en meer.  <br/> |[Meld u aan en meld u aan voor Power Automate](/power-automate/sign-up-sign-in) <br/> |[Power Automate](https://go.microsoft.com/fwlink/p/?linkid=841465) <br/> |
|**Power Virtual Agents** <br/> |Power Virtual Agents stelt teams in staat om eenvoudig krachtige bots te maken met behulp van een geleide grafische interface zonder code zonder dat gegevenswetenschappers of ontwikkelaars nodig hebben. Power Virtual Agents veel van de belangrijkste problemen met het bouwen van bot in de industrie van vandaag. De kloof tussen de experts van het onderwerp en de ontwikkelteams die de bots maken, en de lange latentie tussen teams die een probleem herkennen en het bijwerken van de bot om dit aan te pakken, wordt weggewerkt.  <br/> |[Licentie- en toegangsgegevens](/power-virtual-agents/requirements-licensing) <br/> |[Registreren voor Power Virtual Agents](https://aka.ms/TryPVA) <br/> |
|**Azure AD B2B** <br/> |Azure Active Directory (Azure AD) business-to-business (B2B) samenwerking kunt u externe gebruikers (of 'gastgebruikers') uitnodigen om uw betaalde Azure AD-services te gebruiken. Sommige functies zijn gratis, maar voor betaalde Azure AD-functies kunt u maximaal vijf gastgebruikers uitnodigen voor elke Azure AD edition-licentie die u bezit voor een werknemer of een niet-gastgebruiker in uw tenant. <br/> |[Selfservice voor azure AD B2B-samenwerkingsinvoeging](/azure/active-directory/b2b/self-service-portal) <br/> |[Azure Active Directory B2B-richtlijnen voor samenwerkingslicenties](/azure/active-directory/b2b/licensing-guidance) <br/> |