---
title: Zelfregistratie gebruiken in uw organisatie
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 4f8712ff-9346-4c6c-bb63-a21ad7a62cbd
description: Meer informatie over de office 365-zelfservice-aanmelding strekken en beschikbare selfserviceprogramma's zoals Microsoft Power Apps, Microsoft Flow en Dynamics 365 voor Financials.
ms.custom: okr_SMB
ms.openlocfilehash: fa7e6dcb4c40a7a41599b7c1a81fa596868d8e2d
ms.sourcegitcommit: e695bcfc69203da5d3d96f3d6a891664a0e27ae2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2020
ms.locfileid: "43106110"
---
# <a name="using-self-service-sign-up-in-your-organization"></a>Zelfregistratie gebruiken in uw organisatie

We luisteren naar uw feedback en hebben het eenvoudiger gemaakt voor gebruikers in uw organisatie om zich aan te melden voor online services van Microsoft. We noemen dit nieuwe proces 'zelfregistratie' omdat uw gebruikers zich kunnen aanmelden voor services waarvoor wordt betaald met uw abonnement, of gratis services kunnen gebruiken zonder dat u namens hen actie hoeft te ondernemen.
  
## <a name="how-self-service-sign-up-works"></a>Hoe werkt zelfregistratie

Hieronder volgt een voorbeeld van zelfregistratie bij een onderwijsinstelling. De procedure is dezelfde voor elke organisatie die selfservice-programma's heeft ingeschakeld in de tenant.
  
1. Leerlingen, studenten en faculteitsleden hebben een e-mailadres dat duidelijk maakt dat ze verbonden zijn aan uw instelling. Het e-mailadres jakob@uw.edu kan bijvoorbeeld aangeven dat het hier gaat om een student aan de University of Washington.

2. Studenten en docenten gaan naar [onze website](https://go.microsoft.com/fwlink/p/?LinkId=536628)en gebruiken hun e-mailadres om zich aan te melden voor de services die uw organisatie aanbiedt, zoals Office 365 ProPlus. Ze kunnen zich ook aanmelden voor gratis services die we bieden.

3. We valideren hun e-mailadres en vervolgens kunnen ze meteen Office 365, Power BI of andere services gebruiken.

4. Als bedrijfsbeheerder ziet u wie zich heeft aangemeld voor een abonnement door de pagina **Producten & services** in het beheercentrum te bekijken. Op deze manier u zien wanneer er nieuwe of niet-herkende licenties voor services in uw tenant zijn. Als u wilt bepalen of gebruikers zich kunnen aanmelden voor selfservice-abonnementen, gebruikt u de [PowerShell-cmdlet Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) met de parameter **AllowAdHocSubscriptions.** Zie [Hoe beheer ik selfservice-instellingen?](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/self-service-purchase-faq?view=o365-worldwide)

## <a name="available-self-service-programs"></a>Beschikbare selfservice-programma 's

Hier volgen de selfservice-programma's die momenteel beschikbaar zijn Deze lijst wordt bijgewerkt wanneer er nieuwe programma's worden toegevoegd.
  
|||||
|:-----|:-----|:-----|:-----|
|**Programma** <br/> |**Beschrijving** <br/> |**Aanvullende informatie** <br/> |****Website voor zelfregistratie**** <br/> |
|Office 365 A1**** <br/> |Elke student of docent kan een e-mailadres van een school gebruiken om zich gratis aan te melden voor Office 365 en Office-apps voor het web, 1 TB OneDrive-cloudopslag en SharePoint Online voor klas-, team- en projectsites.  <br/> |[Office 365 Education - veelgestelde technische vragen](https://go.microsoft.com/fwlink/p/?LinkId=536625) <br/> |[Office 365 Education](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Office 365 A1 Plus** <br/> |In aanmerking komende leerlingen, studenten en docenten kunnen zich registreren voor Office 365 A1 Plus. Ze krijgen dan de beschikking over alle bovengenoemde onderdelen, plus Office 365 ProPlus. Office 365 ProPlus is productiviteitssoftware en omvat onder andere Word, PowerPoint, Excel, Outlook, OneNote, Publisher, Access en Skype voor Bedrijven. Deze software wordt geïnstalleerd op uw pc of laptop.  <br/> |[Office 365 Education - veelgestelde technische vragen](https://go.microsoft.com/fwlink/p/?LinkId=536625) <br/> |[Office 365 Education](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Power BI** <br/> |Power BI stelt gebruikers in staat om gegevens te visualiseren, ontdekkingen te delen en op intuïtieve nieuwe manieren samen te werken. <br/> Als uw organisatie zich al abonneert op Office 365, ziet u mogelijk ook licenties voor 'Power BI Pro Individual User Trial', die gebruikers beperkte, gratis toegang bieden tot geavanceerde mogelijkheden.  <br/> |[Power BI in uw organisatie](https://go.microsoft.com/fwlink/p/?LinkId=536626) <br/> |[Microsoft Power BI](https://go.microsoft.com/fwlink/p/?LinkId=536629) <br/> |
|**Rights Management Services (RMS)** <br/> |RMS voor personen is een gratis selfservice-abonnement voor gebruikers in een organisatie die vertrouwelijke bestanden hebben ontvangen die zijn beveiligd met Azure Rights Management (Azure RMS), maar hun IT-afdeling heeft Azure Rights Management (Azure RMS) of Active Directory Rights Management Services (AD RMS) niet geïmplementeerd.  <br/> |[RMS voor personen en Azure Information Protection](https://go.microsoft.com/fwlink/p/?LinkId=536627) <br/> |[Microsoft Rights Management portal](https://portal.azure.com/) zodat u kunt controleren of u een bepaald met toegangsrechten beveiligd document kunt openen.  <br/> |
|**Microsoft PowerApps** <br/> |In PowerApps kunt u organisatiegegevens beheren door een app uit te voeren die u hebt gemaakt, of die iemand anders heeft gemaakt en met u heeft gedeeld. Apps worden uitgevoerd op mobiele apparaten zoals telefoons, maar u kunt ze ook uitvoeren in een browser door Dynamics 365 te openen. U kunt allerlei verschillende soorten apps maken, zonder dat u een programmeertaal zoals C# hoeft te leren.  <br/> |[Aanmelding voor PowerApps via selfservice](https://go.microsoft.com/fwlink/p/?linkid=841461) <br/> |[Microsoft PowerApps](https://go.microsoft.com/fwlink/p/?linkid=841462) <br/> |
|**Dynamics 365 for Financials** <br/> |Een complete oplossing voor zakelijk en financieel beheer voor kleine en middelgrote bedrijven. Met Dynamics 365 for Financials kunt u vanaf dag één eenvoudiger inkopen, verkopen, factureren en rapporteren.  <br/> |[Microsoft Dynamics 365 for Financials](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |[Microsoft Dynamics 365 for Financials](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |
|**Microsoft Dynamics 365 for Operations** <br/> |Verhoog de snelheid van zakendoen. De uitgebreide ERP-hulpmiddelen in 365 Dynamics for Operations bieden globale schaalbaarheid en digitale bedrijfsinformatie waarmee uw organisatie in het gewenste tempo kan groeien.  <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |
|**Microsoft AppSource** <br/> |Microsoft AppSource is een verzameling zakelijke SaaS-apps (Software as a Service) die zijn gebaseerd op het Microsoft-cloudplatform. Op AppSource vindt u honderden apps, invoegtoepassingen en inhoudspakketten waarmee u de functionaliteit kunt uitbreiden van Microsoft-producten, zoals Azure, Microsoft Dynamics 365, Office 365 en Power BI.  <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |
|**Microsoft Partner Network** <br/> |Het Microsoft Partner Network biedt drie typen lidmaatschappen. Elk type biedt een aantal voordelen om uw bedrijf te helpen groeien. Naarmate u uw doelstellingen realiseert, kunt u deelnemen aan het programma op het niveau dat aansluit bij uw unieke behoeften om zo toegang te krijgen tot meer voordelen en uw relatie met ons en met andere partners in het netwerk te verdiepen.  <br/> |[Microsoft Partner Network](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |[Microsoft Partner Network](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |
|**Microsoft Business Center** <br/> |Het Microsoft Business Center is de portal voor klanten die aankopen hebben gedaan via de Microsoft Products and Services Agreement (MPSA). <br/> |[Quick Start: Register for the Microsoft Business Center](https://go.microsoft.com/fwlink/p/?linkid=841479) (Snel aan de slag: Registreren voor het Microsoft Business Center) <br/> |[Microsoft Business Center](https://go.microsoft.com/fwlink/p/?linkid=841470) <br/> |
|**Microsoft Volume License Service Center** <br/> |In het Microsoft Volume License Service Center worden licenties weergegeven die zijn aangeschaft onder overeenkomsten voor Enterprise, Select, Education (Campus of School), Open Value, Open License en ISV Royalty.  <br/> |[VLSC Training en Middelen](https://www.microsoft.com/en-us/Licensing/existing-customer/vlsc-training-and-resources.aspx) <br/> |[Servicecentrum voor volumelicentie](https://www.microsoft.com/Licensing/servicecenter/default.aspx) <br/> |
|**Minecraft Education Edition** <br/> |Door Minecraft in te zetten als een onderwijsplatform kan het onderwijzend personeel leerlingen en studenten motiveren en inspireren om meer te bereiken. Daarnaast kan op deze manier een passie voor leren worden ontwikkeld. Word lid van een community van docenten en ontdek hoe u met Minecraft de mogelijkheden van leerlingen en studenten optimaal kunt benutten.  <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841480) <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841471) <br/> |
|**Microsoft Stream** <br/> |Upload en deel video's binnen uw organisatie om verbeteringen te realiseren op het gebied van communicatie, participatie en leren.  <br/> |[Sign up &amp; Day 0 experience](https://go.microsoft.com/fwlink/p/?linkid=841472) <br/> |[Microsoft Stream](https://go.microsoft.com/fwlink/p/?linkid=841473) <br/> |
|**Power automatiseren** <br/> |Power Automate is een product waarmee u geautomatiseerde workflows instellen tussen uw favoriete apps en services om bestanden te synchroniseren, meldingen te ontvangen, gegevens te verzamelen en meer.  <br/> |[Aanmelden en aanmelden voor Power Automate](https://docs.microsoft.com/power-automate/sign-up-sign-in) <br/> |[Power automatiseren](https://go.microsoft.com/fwlink/p/?linkid=841465) <br/> |
|**Power Virtual Agents** <br/> |Power Virtual Agents stelt teams in staat om eenvoudig krachtige bots te maken met behulp van een begeleide, no-code grafische interface zonder dat gegevenswetenschappers of ontwikkelaars nodig zijn. Power Virtual Agents pakt veel van de belangrijkste problemen met bot gebouw in de industrie vandaag. Het elimineert de kloof tussen het onderwerp deskundigen en de ontwikkeling teams het bouwen van de bots, en de lange latentie tussen teams herkennen van een probleem en het bijwerken van de bot om het aan te pakken.  <br/> |[Licentie- en toegangsgegevens](https://go.microsoft.com/fwlink/?linkid=2113708) <br/> |[Meld u aan voor Power Virtual Agents](https://aka.ms/TryPVA) <br/> |