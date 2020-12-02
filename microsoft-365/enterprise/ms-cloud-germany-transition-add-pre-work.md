---
title: Aanvullende gegevens van vóór het werk voor de migratie van Microsoft Cloud Deutschland
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
description: 'Overzicht: aanvullende informatie over voorwerkers wanneer u overstapt van Microsoft Cloud Duitsland (Microsoft Cloud Deutschland) naar Office 365-Services in het nieuwe Duitse datacenter-gebied.'
ms.openlocfilehash: 41953aa9d91faa91bd983fbbc8d93baf08c172ed
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551706"
---
# <a name="additional-pre-work-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Aanvullende gegevens van vóór het werk voor de migratie van Microsoft Cloud Deutschland

| Stap (s) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Zorg ervoor dat de netwerkverbinding met de [url's en IP-adressen van Office 365 Services](https://aka.ms/o365urls)vervalt. | Alle clients en services die worden gehost door de klant die worden gebruikt voor toegang tot de Office 365-service, moeten toegang hebben tot de Office 365 service-eindpunten. | Alle overgangs klanten en klanten met netwerktoegang beperkt tot Microsoft Cloud Deutschland. | Vereiste actie. Inactief kan leiden tot storing van de service of clientsoftware. |
| Controleren en voorbereiden op migratie-gerelateerde DNS-wijzigingen. | Klant bereidt DNS-vermeldingen voor voor Exchange Online en Exchange Online Protection (MX-record, enzovoort). | Exchange Online-klanten | Dit is een aanbevolen actie. Geen actie betekent dat het e-mailadres van een gemigreerde klant kan worden gerouteerd via Microsoft Cloud Deutschland totdat de Microsoft Cloud Deutschland-service is uitgeschakeld. |
| Controleren en voorbereiden op migratie-gerelateerde DNS-wijzigingen. | DNS-zonewijzigingen van klanten in Skype voor bedrijven online. | Skype voor bedrijven online-klanten | -Het is raadzaam dat u de TTL (time to Live) van de DNS-records van de klant tot 5 minuten bijwerkt, zodat het vernieuwen van DNS-records versneld wordt. Het door Microsoft beheerde cutover dat is gekoppeld aan deze DNS-wijziging, kan echter op elk moment plaatsvinden binnen het opgegeven venster van 24 uur wijzigen. <br><br> Onderbreking van de service is in de toekomst mogelijk. Gebruikers kunnen zich niet aanmelden bij Skype voor bedrijven en worden doorgestuurd naar de gemigreerde teams-ervaring in de Office 365-Services. |
| Het trainen en voorbereiden van end gebruikers en beheer voorbereiden voor de overstap naar Microsoft teams. | Succesvol over de overgang van Skype naar teams door de communicatie en voorbereiding van gebruikers te plannen. | Skype voor bedrijven online-klanten | -Clients moeten op de hoogte zijn van de nieuwe services en hoe deze worden gebruikt wanneer hun services worden overgezet naar Office 365-Services. <br><br> -Nadat DNS-wijzigingen zijn doorgevoerd voor zowel de klant werden omgezet domains als het eerste domein, meldt u zich aan bij Skype voor bedrijven en ziet u dat ze nu worden gemigreerd naar teams. Hiermee kunt u ook de desktopclient voor teams downloaden op de achtergrond. |
| Training voor eindgebruikers en beheer voorbereiden van gebruikers die hun account verwijderen en opnieuw toevoegen aan Microsoft Outlook voor iOS en Android. | Microsoft Outlook voor iOS-en Android-accounts die zijn geconfigureerd voor postvakken in Microsoft Cloud Deutschland, kunnen worden verwijderd en opnieuw toegevoegd aan Outlook om de nieuwe configuratie van Office 365-services correct te synchroniseren. | Microsoft Outlook voor iOS-en Android-klanten | Outlook-postvakken die eerder zijn geconfigureerd voor Microsoft Cloud Deutschland, leveren mogelijk niet de nieuwe configuratie van Office 365-Services op, leiden tot fouten en verminderde prestaties van andere gebruikerservaringen. IT-beheerders wordt aangemoedigd documentatie te geven waarmee gebruikers in proactief hun accounts te verwijderen en opnieuw toe te voegen aan Microsoft Outlook voor iOS en Android als er problemen optreden bij het aanmelden of het synchroniseren van e-mailberichten die na de migratie plaatsvinden. |
| Voorbereidingen treffen om gebruikers te informeren over het opnieuw opstarten en aanmelden bij en na de migratie. | Client Licensing van Office wordt overgezet van Microsoft Cloud Deutschland naar Office 365-Services in de migratie. Klanten trekken een nieuwe geldige licentie na het aanmelden bij en bij Office-clients. | Klanten van Microsoft 365-apps |  De Office-producten van gebruikers moeten licenties vernieuwen van Office 365-Services. Als licenties niet worden vernieuwd, kunnen Office-producten problemen met de licentie validatie veroorzaken. |
| Een proefabonnement annuleren. | Proefabonnementen worden niet gemigreerd en zullen de overdracht van betaalde abonnementen blokkeren. | Alle klanten | Proef Services zijn verlopen en werken niet als gebruikers na hun opzegging door gebruikers worden geopend. |
| Implementeer teams-bureaubladclient voor gebruikers die in Duitsland toegang hebben tot Skype voor bedrijven. | Bij de migratie worden gebruikers verplaatst naar teams voor samenwerking, bellen en chatten. Implementeer de desktopclient van de teams-desktop of zorg ervoor dat er een ondersteunde browser beschikbaar is. | Skype voor bedrijven-klanten | Inactief maakt de samenwerkingsservices van teams niet in de beschikbaarheid. |
| Verschillen in licentie functies analyseren tussen Microsoft Cloud Deutschland en Office 365-Services. | Services van Office 365 bevatten extra functies en services die niet beschikbaar zijn in de huidige Microsoft Cloud Deutschland. Tijdens de overdracht van een abonnement zijn er nieuwe functies beschikbaar voor gebruikers. | Alle klanten | -Analyseer de verschillende functies van de licenties voor Microsoft Cloud Deutschland en Office 365-Services. Begin met de [service beschrijving van het Office 365-platform](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description). <br><br> -Bepaal of nieuwe functies van Office 365-Services in eerste instantie moeten worden uitgeschakeld om gevolgen te krijgen voor gebruikers of voor wijzigingsbeheer van gebruikers, en om gebruikerslicentie toewijzingen te wijzigen. <br><br> : U kunt gebruikers en helpdesk-medewerkers voorbereiden voor nieuwe services en functies die beschikbaar zijn in Office 365-Services. |
| Maak [beleidsregels voor bewaarbeleid](https://docs.microsoft.com/microsoft-365/compliance/retention) om te beschermen tegen onbedoelde verwijdering van inhoud tijdens migraties.  | -Om ervoor te zorgen dat de inhoud niet per ongeluk wordt verwijderd door eindgebruikers tijdens de migratie, kunnen klanten kiezen voor het inschakelen van een bewaarbeleid voor de gehele organisatie. <br><br> -Hoewel bewaren niet vereist is, omdat er tijdens de migratie op elk moment rekening wordt gehouden met een bewaarbeleid, is dit een back-up van het veiligheids mechanisme. Tegelijkertijd mag een bewaarbeleid niet door alle klanten worden gebruikt, met name degene die zich zorgen maken over behoud. | Office-klanten | Als u een bewaarbeleid wilt toepassen, zoals beschreven in [informatie over bewaarbeleid en labels voor bewaarbeleid](https://docs.microsoft.com/microsoft-365/compliance/retention-policies). |
| [Back-up maken van een AD FS-Farm (Active Directory Federation Services)](ms-cloud-germany-transition-add-adfs.md#backup) voor scenario's voor herstel na herstel. | Klanten moeten eerst een back-up van de AD FS-farm maken om ervoor te zorgen dat de vertrouwensrelaties van de vertrouwende partij voor globale & Duitsland-eindpunten kunnen worden hersteld zonder dat de certificerings URI van de domeinen wordt verraak. Microsoft raadt u aan gebruik te maken van AD FS snel herstellen voor een back-up van de farm en de bijbehorende herstelservice, indien nodig. | Organisaties voor Federatie verificatie | Vereiste actie. Inactief maakt een service-impact tijdens de migratie als de AD FS-Farm van de klant mislukt. |


## <a name="exchange-online"></a>Exchange Online

| Stap (s) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Stel externe partners op de hoogte van de komende overgang naar Office 365-Services. | Met configuraties voor beschikbaarheidsinfo kunt u beschikbaarheidsinfo delen met Office 365. | Exchange Online-klanten die het delen van de agenda en de beschikbaarheid hebben ingeschakeld. | Vereiste actie.  U kunt dit probleem mogelijk veroorzaakt door een latere fase van de klant migratie. |
|||||

Als u een hybride uitwisseling hebt:

| Stap (s) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Verwijder eerdere versies van de wizard hybride configuratie (HCW) en installeer en voer vervolgens de nieuwste versie, 17.0.5378.0, van af [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) . | De nieuwste versie van de HCW bevat benodigde updates voor de ondersteuning van klanten die overstappen van Microsoft Cloud Deutschland naar Office 365-Services. <br><br> Updates bevatten wijzigingen in on-premises certificaatinstellingen voor verbindingslijn verzenden en ontvangen. | Exchange Online-klanten die Hybrid Deployment uitvoeren | Vereiste actie. Er kan geen service of clientstoring optreden. |
|||||

## <a name="sharepoint-online"></a>SharePoint Online

Als u SharePoint 2013 hebt:

| Stap (s) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| U kunt SharePoint 2013-werkstromen beperken en gebruiken tijdens de migratie van SharePoint Online. | Maak werkstromen van SharePoint 2013 en voer binnen de vlucht-werkstromen vóór overgangen in. | SharePoint Online-klanten | Inactief kan leiden tot een andere gebruiker en een helpdesk. |
|||||

<!--
[Reference:  If Pre-Work][ SharePoint 2013 ]
--> 

## <a name="mobile"></a>Mobile

Als u gebruikmaakt van een MDM-oplossing (Mobile Device Management) van derden:

| Stap (s) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Bepalen of een herconfiguratie vereist is na de migratie. | MDM-oplossingen kunnen `outlook.de` eindpunten bereiken. In deze overgang naar Office 365-services moeten Clientprofielen worden bijgewerkt naar de URL van Office 365-Services `outlook.office365.com` . | Gebruikers van Exchange Online en MDM | Clients kunnen blijven werken terwijl het `outlook.de` eindpunt toegankelijk is, maar het lukt niet als Microsoft Cloud Deutschland-eindpunten niet langer beschikbaar zijn. |
|||||

<!--
[Reference:  If Pre-Work][ Mobile]
-->             

## <a name="line-of-business-apps"></a>Line-of-Business-Apps

Als u een service van derden of line-of-business-toepassingen (LOB) gebruikt die zijn geïntegreerd in Office 365, doet u het volgende: 

| Stap (s) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Bepalen of een herconfiguratie vereist is na de migratie. | Services en toepassingen van derden die zijn geïntegreerd met Office 365, kunnen worden gecodeerd met de verwachte IP-adressen en Url's van Microsoft Cloud Deutschland. | Alle klanten | Vereiste actie. Inactief kan leiden tot storing van de service of clientsoftware. |
|||||

<!--
[Reference:  If Pre-Work][ LOB]
--> 

## <a name="azure"></a>Azure 

| Stap (s) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Bepaal welke Azure-Services worden gebruikt en voorbereiden voor toekomstige migratie van Duitsland naar de Office 365 service-Tenant door samen te werken met uw partners. Voer de stappen uit die worden beschreven in de [Azure Migration Playbook](https://docs.microsoft.com/azure/germany/germany-migration-main). | De migratie van Azure-resources is een verantwoordelijkheid voor de klant en vereist handmatige activiteiten na de vastgestelde stappen. In dit voorbeeld is de implementatie van Azure-Services op basis van een succesvolle migratie van Azure-Services. <br><br> Voor klanten van Office 365 Duitsland met een Azure-abonnement onder dezelfde identiteits partitie (organisatie) moet de door Microsoft vastgestelde volgorde volgen wanneer ze de migratie van abonnementen en services kunnen starten. | Azure-klanten | -Klanten kunnen meerdere Azure-abonnementen hebben, elk abonnement met infrastructuur, services en platform onderdelen. <br><br> -Beheerders moeten abonnementen en belanghebbenden identificeren om ervoor te zorgen dat de migratie en validatie van de gebruiker kunnen worden ingeschakeld als onderdeel van deze migratie gebeurtenis. <br><br> Het voltooien van de migratie van deze abonnementen en Azure-onderdelen binnen de vereiste tijdlijn is van invloed op het voltooien van de overgang van Office en Azure AD naar Office 365-Services en kan leiden tot verlies van gegevens.  <br><br> -Met een bericht in het berichtencentrum wordt het tijdstip aangegeven waarop een door de klant geactiveerde migratie kan beginnen. |
|||||

<!--
[Reference:  If Azure Pre-Work][ Azure]
-->  

## <a name="dynamics-365"></a>Dynamics 365

| Stap (s) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Download de productieomgeving van de Dynamics SQL-instantie van uw Dynamics 365-abonnement in Microsoft Cloud Deutschland voor de sandbox-abonnementen voor Dynamics 365. De nieuwste productie back-up moet worden teruggezet in de sandbox vóór de sandbox-migratie. | Voor de migratie van Dynamics 365 moet klanten ervoor zorgen dat de sandbox-omgeving wordt vernieuwd met de nieuwste productiedatabase. | Microsoft Dynamics-klanten | Het FastTrack-team helpt klanten bij het uitvoeren van droge versies om de versie-upgrade van 8. x tot en met 9.1. x te valideren. |
|||||

<!--
[Reference: Prework][Dynamics]
-->             

## <a name="power-bi"></a>Power BI

| Stap (s) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Verwijderen van objecten uit Power BI-abonnementen die niet worden gemigreerd van Power BI Microsoft Cloud Deutschland naar Office 365-Services. | Voor de migratie van Power BI-Services moet de actie klant zijn gebruikt om bepaalde artefacten, zoals gegevenssets en dashboards, te verwijderen. | Power BI-klanten | Beheerders moeten mogelijk de volgende items van hun abonnement verwijderen: <br> -Real-Time datasets (bijvoorbeeld streaming of push datasets) <br> -Power BI on-premises configuratie van gegevens gateway en gegevensbron |
|||||

<!--
[Reference: Prework][Power BI]
--> 

## <a name="dns"></a>Server

| Stap (s) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| DNS-wijziging nakijken en voorbereiden als de huidige DNS een MSOID-CName-vermelding heeft. | Gewijzigde DNS-zone van klant | Klanten van Office-client services | Werk de TTL (time to Live) voor klant-DNS-records bij tot 5 minuten als er een MSOID CName bestaat. |
|||||

<!--
[Reference: Prework][DNS]
-->             

## <a name="federated-identity"></a>Federatieve identiteit

| Stap (s) | Beschrijving | Van toepassing op | Gevolg |
|:-------|:-----|:-------|:-------|
| Genereer een vertrouwensrelatie van een vertrouwensrelatie voor globale Azure AD-eindpunten. | Klanten moeten handmatig een RPT (RPT) voor een vertrouwensrelatie (RPT) maken voor [globale](https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml) eindpunten. U kunt dit doen door een nieuwe RPT via de GEBRUIKERSINTERFACE toe te voegen, door gebruik te maken van de URL van de Global Federatie metagegevens en vervolgens [Azure AD rap-claim regels](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator#:~:text=%20Azure%20AD%20RPT%20Claim%20Rules%20%201,Azure%20AD.%20This%20will%20be%20what...%20More%20) (in de Help van AD FS) te gebruiken om de claimregels te genereren en deze te importeren in de RPT. | Organisaties voor Federatie verificatie | Vereiste actie. Inactief maakt een service-impact tijdens de migratie. |
|||||

<!--
[Reference: Prework][Federation]
-->  

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
