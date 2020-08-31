---
title: Uw Microsoft 365-Tenant configureren voor een betere beveiliging
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/11/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: 8d274fe3-db51-4107-ba64-865e7155b355
ms.custom:
- seo-marvel-apr2020
description: In dit onderwerp wordt u begeleid bij de aanbevolen configuratie voorinstellingen voor de gehele Tenant die van invloed zijn op de beveiliging van uw Microsoft 365-omgeving.
ms.openlocfilehash: 3a69a27aa544880e428562892832b6d33a2508e4
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/29/2020
ms.locfileid: "47308217"
---
# <a name="configure-your-microsoft-365-tenant-for-increased-security"></a>Uw Microsoft 365-Tenant configureren voor een betere beveiliging

In dit onderwerp wordt u begeleid bij de aanbevolen configuratie voorinstellingen voor de gehele Tenant die van invloed zijn op de beveiliging van uw Microsoft 365-omgeving. Voor uw veiligheids behoeften is meer of minder veiligheid nodig. Gebruik deze aanbevelingen als uitgangspunt.

## <a name="check-office-365-secure-score"></a>Beveiligings Score van Office 365 controleren

Secure Score van Office 365 analyse van de beveiliging van uw organisatie op basis van uw regelmatige activiteiten en beveiligingsinstellingen en wijst een score toe. Begin met het noteren van uw huidige score. Door enkele instellingen voor de Tenant te wijzigen, wordt uw score groter. Het doel is niet de maximum score te bereiken, maar u moet rekening houden met verkoopkansen om uw omgeving te beschermen en de productiviteit van uw gebruikers niet negatief beïnvloeden. Zie [Microsoft Secure Score](../mtp/microsoft-secure-score.md).

## <a name="tune-threat-management-policies-in-the-microsoft-365-security-center"></a>Beleidsregels voor risicobeheer in het Microsoft 365-Beveiligingscentrum afstemmen

Het Microsoft 365-Beveiligingscentrum bevat mogelijkheden om uw omgeving te beschermen. Dit omvat ook rapporten en dashboards die u kunt gebruiken om te controleren en actie te ondernemen. Sommige gebieden worden geleverd met standaard beleidsconfiguraties. Voor sommige gebieden gelden geen standaardbeleidsregels of-regels. Ga naar deze beleidsregels onder bedreigings beheer om instellingen voor Threat Management af te stemmen voor een veiliger omgeving.

****

|Ziet|Een standaardbeleid bevat|Aanbeveling|
|---|---|---|
|**Anti phishing**|Ja|Als u een aangepast domein hebt, configureert u het standaard anti-phishingfilter, zodat u de e-mailaccounts van uw meest waardevolle gebruikers kunt beschermen, zoals de CEO, en om uw domein te beschermen. Bekijk [anti-phishing-beleid in office 365](set-up-anti-phishing-policies.md) en Zie [anti phishing-beleidsregels configureren in EOP](configure-anti-phishing-policies-eop.md) of een [ATP anti-phishingfilter configureren in Office 365](configure-atp-anti-phishing-policies.md).|
|**Anti malware-engine**|Ja| Het standaardbeleid bewerken: <br/> &ensp;&ensp;* Veelgebruikte typen bijlagen, selecteren aan <br/><br/> U kunt ook aangepaste beleidsregels voor malware-filters maken en deze toepassen op opgegeven gebruikers, groepen of domeinen in uw organisatie. <br/><br/> Meer informatie: <br/> &ensp;&ensp;* [Beveiliging tegen malware](anti-malware-protection.md) <br/> &ensp;&ensp;* [Beleidsregels voor anti malware configureren](configure-anti-malware-policies.md)|
|**Veilige bijlage van ATP**|Nee| Op de hoofdpagina voor veilige bijlagen, moet u bestanden beschermen in SharePoint, OneDrive en Microsoft teams door dit selectievakje in te schakelen: <br/> &ensp;&ensp;* Schakel ATP in voor SharePoint, OneDrive en Microsoft teams <br/><br/> Voeg een nieuw beleid voor veilige bijlagen toe met de volgende instellingen: <br/> &ensp;&ensp;* Blokkeren: de huidige en toekomstige e-mailberichten en bijlagen blokkeren met gedetecteerde malware (Kies deze optie) <br/> &ensp;&ensp;* Schakel omleiding in en voer een e-mailadres in, zoals een beheerders-of quarantaine account. <br/> &ensp;&ensp;* Pas de bovenstaande selectie toe als de malware wordt gescand op bijlagen wanneer een fout optreedt (Schakel dit selectievakje in) <br/> &ensp;&ensp;* Van toepassing op: het domein van de ontvanger is (Selecteer uw domein) <br/><br/>Meer informatie: [Office 365 ATP-beleid voor veilige bijlagen instellen](set-up-atp-safe-attachments-policies.md)|
|**Veilige ATP-koppelingen**|Ja| Deze instelling toevoegen aan het standaardbeleid voor de hele organisatie: <br/> &ensp;&ensp;* Gebruik veilige koppelingen in: Microsoft 365-apps voor Enterprise, Office voor iOS en Android (Selecteer deze optie). <br/><br/>Aanbevolen beleid voor specifieke geadresseerden: <br/> &ensp;&ensp;* Url's worden herschreven en gecontroleerd tegen een lijst met bekende kwaadaardige koppelingen wanneer de gebruiker op de koppeling klikt (Selecteer deze optie). <br/> &ensp;&ensp;* Gebruik veilige bijlagen voor het scannen van downloadbare inhoud (Schakel dit selectievakje in). <br/> &ensp;&ensp;* Van toepassing op: het domein van de ontvanger is (Selecteer uw domein). <br/><br/> Meer informatie: [veilige koppelingen in Office 365 ATP](atp-safe-links.md).|
|**Anti spam (e-mail filtering)**|Ja| U kunt als volgt controleren: <br/> &ensp;&ensp;* Te veel spam: Kies de aangepaste instellingen en bewerk het standaard spamfilter beleid. <br/> &ensp;&ensp;* Spoof informatie: Bestudeer afzenders die uw domein spoofen. Deze afzenders blokkeren of toestaan. <br/><br/>Meer informatie: [Microsoft 365 beveiliging tegen ongewenste e-mail](anti-spam-protection.md).|
|***Verificatie via e-mail***|Ja|E-mail verificatie maakt gebruik van een DNS (Domain Name System) om verifieerbare informatie toe te voegen aan e-mailberichten over de afzender van een e-mailbericht. Microsoft 365 stelt e-mail verificatie in voor het standaarddomein (onmicrosoft.com), maar Microsoft 365-beheerders kunnen ook e-mail verificatie gebruiken voor aangepaste domeinen. U gebruikt drie verificatiemethoden: <br/><br/> &ensp;&ensp;* Framework met verzender beleidsregels (of SPF).<br/>&ensp;&ensp;&ensp;&ensp;Voor de installatie vindt u meer informatie over het [instellen van SPF in Microsoft 365 om spoofing te helpen voorkomen](set-up-spf-in-office-365-to-help-prevent-spoofing.md). <br/> &ensp;&ensp;* DomainKeys geïdentificeerde E-mail (DKIM). <br/> &ensp;&ensp;&ensp;&ensp;-Zie [dkim gebruiken voor het valideren van uitgaande e-mail verzonden vanaf uw aangepaste domein](use-dkim-to-validate-outbound-email.md). <br/>&ensp;&ensp;&ensp;&ensp;-Nadat u DKIM hebt geconfigureerd, kunt u dit inschakelen in het Beveiligingscentrum.<br/> &ensp;&ensp;* Verificatie, rapportage en conformiteit op domeinbasis van domein (DMARC). <br/> &ensp;&ensp;&ensp;&ensp;-Voor DMARC configuratie [gebruik DMARC om e-mail te valideren in Microsoft 365](use-dmarc-to-validate-email.md).|
|

> [!NOTE]
> Voor niet-standaard implementaties van SPF, hybride implementaties en probleemoplossing: [hoe Microsoft 365 gebruikmaakt van SPF (Sender Policy Framework) om spoofing te voorkomen](how-office-365-uses-spf-to-prevent-spoofing.md).

## <a name="view-dashboards-and-reports-in-the-security-and-compliance-centers"></a>Dashboards en rapporten in de beveiligings-en compliance-centra weergeven

Bezoek deze rapporten en dashboards voor meer informatie over de status van uw omgeving. De gegevens in deze rapporten worden uitgebreid naarmate uw organisatie Office 365-Services gebruikt. Wees nu vertrouwd met de functies die u kunt controleren en actie ondernemen. Zie voor meer informatie: [rapporten in de Microsoft 365-Beveiligingscentrum en compliance Center](../../compliance/reports-in-security-and-compliance.md).

****

|Dashboard|Beschrijving|
|---|---|
|[Threat Management Dashboard](security-dashboard.md)|In de sectie **Threat Management** van het Beveiligingscentrum, gebruikt u dit dashboard om bedreigingen te zien die al zijn afgehandeld en als handige functie voor het melden van de professionele besluitvormings functies voor de beveiliging van uw bedrijf.|
|[Bedreigingsverkenner (of realtime detecties)](threat-explorer.md)|Dit is ook de sectie **Threat Management** van het Beveiligingscentrum. Als u een aanval ter onderzoek doet of een aanval uitvoert tegen uw Tenant, gebruikt u de Verkenner (of realtime detectie) om bedreigingen te analyseren. Explorer (en het rapport realtime detectie) laat u gedurende een bepaalde periode het volume van een aanval zien en u kunt deze gegevens analyseren op bedreigings families, infrastructuur van kwaadwillenden en meer. U kunt ook verdachte e-mail markeren voor de lijst met incidenten.|
|Rapporten: Dashboard|In het gedeelte **rapporten** van Beveiligingscentrum bekijkt u controlerapporten voor uw SharePoint Online-en Exchange Online-organisaties. U kunt aanmeldings rapporten van gebruikers van Azure Active Directory (Azure AD), rapporten van gebruikersactiviteiten en het Azure AD auditlogboek ook openen via de pagina **rapporten weergeven** .|
|

![Dashboard voor het Beveiligingscentrum](../../media/870ab776-36d2-49c7-b615-93b2bc42fce5.png)

## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>Extra instellingen voor de Tenant van Exchange Online configureren

Veel van de besturingselementen voor beveiliging en beveiliging in het Exchange-Beheercentrum worden ook opgenomen in het Beveiligingscentrum. U hoeft dit niet op beide locaties te configureren. Hier volgen een paar extra instellingen die worden aanbevolen.

****

|Ziet|Een standaardbeleid bevat|Aanbeveling|
|---|---|---|
|**E-mail stroom** (e-mail stroom regels, ook wel een zogenaamde transportregels genoemd)|Nee|Voeg een e-mail stroom regel toe om u te helpen beschermen tegen Ransomware door uitvoerbare bestandstypen en typen Office-bestanden met macro's te blokkeren. Zie voor meer informatie de [regels voor e-mail stroom gebruiken om berichten bijlagen te controleren in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments). <br/><br/> Bekijk de volgende aanvullende onderwerpen: <br/>* [Beveilig tegen Ransomware](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware)<br/>* [Malware en Ransomware-beveiliging in Office 365](https://docs.microsoft.com/Office365/Enterprise/office-365-malware-and-ransomware-protection) <br/>* [Herstel van een Ransomware aanval in Office 365](recover-from-ransomware.md) <br/><br/> Maak een e-mail stroom regel om het automatisch doorsturen van e-mail naar externe domeinen te voorkomen. Zie voor meer informatie het artikel [beperken van externe doorstuurregels van clients met een beveiligde Score](https://docs.microsoft.com/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score). <br/><br/> Meer informatie: [e-mail stroom regels (transportregels) in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)|
|**Moderne verificatie inschakelen**|Nee|Moderne verificatie is een vereiste voor het gebruik van multi-factor Authentication (MFA). MFA wordt aanbevolen voor het beveiligen van de toegang tot Cloud bronnen, waaronder e-mail. <br/><br/> Zie de volgende onderwerpen: <br/>* [Moderne verificatie in-of uitschakelen in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) <br/>* [Skype voor bedrijven online: uw Tenant inschakelen voor moderne verificatie](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) <br/><br/> Moderne verificatie is standaard ingeschakeld voor Office 2016-clients, SharePoint Online en OneDrive voor bedrijven. <br/><br/> Meer informatie: de werking [van moderne verificatie voor office 2013 en office 2016-clienttoepassingen](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016)|
|

## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>Beleidsregels voor het delen van de gehele Tenant configureren in het SharePoint-Beheercentrum

Microsoft aanbevelingen voor het configureren van SharePoint-Team sites bij een betere beveiliging, te beginnen met basislijn beveiliging. Zie [SharePoint Online-sites en-bestanden beveiligen](https://docs.microsoft.com/microsoft-365-enterprise/secure-sharepoint-online-sites-and-files) voor meer informatie.

SharePoint-Team sites die zijn geconfigureerd op het basisniveau, delen bestanden met externe gebruikers met behulp van koppelingen voor anonieme toegang. Deze methode wordt aanbevolen in plaats van bestanden per e-mail te verzenden.

Voor de ondersteuning van de doelstellingen voor basisbeveiliging configureert u beleidsregels voor het delen van de Tenant. Instellingen voordelen voor afzonderlijke sites zijn beperkt tot het beleid voor de gehele Tenant, maar niet meer beperkt.

****

|Ziet|Een standaardbeleid bevat|Aanbeveling|
|---|---|---|
|**Delen** (SharePoint Online en OneDrive voor bedrijven)|Ja|Extern delen is standaard ingeschakeld. U wordt aangeraden deze instellingen te volgen: <br/>* Delen met geverifieerde externe gebruikers en gebruiken van koppelingen voor anonieme toegang toestaan (standaardinstelling). <br/> * Koppelingen voor anonieme toegang verlopen dit aantal dagen. Voer indien nodig een nummer in, bijvoorbeeld 30 dagen. <br/>* Standaardkoppelingstype: Selecteer intern (alleen voor personen in de organisatie). Gebruikers die willen delen met anonieme koppelingen, moeten deze optie kiezen in het menu delen. <br/><br/> Meer informatie: [overzicht van extern delen](https://docs.microsoft.com/sharepoint/external-sharing-overview)|
|

Het SharePoint-Beheercentrum en het Beheercentrum voor OneDrive voor bedrijven bevatten dezelfde instellingen. De instellingen in beide beheer centra zijn van toepassing op beide.

## <a name="configure-settings-in-azure-active-directory"></a>Instellingen configureren in azure Active Directory

Zorg ervoor dat u deze twee gebieden in azure Active Directory bezoekt voor het voltooien van de instellingen voor de gehele Tenant voor veiligere omgevingen.

### <a name="configure-named-locations-under-conditional-access"></a>Benoemde locaties configureren (onder voorwaardelijke toegang)

Als uw organisatie kantoren met beveiligde netwerktoegang bevat, voegt u de vertrouwde IP-adresbereiken toe aan Azure Active Directory als benoemde locaties. Met deze functie kunt u het aantal gerapporteerde fout-positieven voor gebeurtenissen bij aanmelding verminderen.

Zie: [benoemde locaties in azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-named-locations)

### <a name="block-apps-that-dont-support-modern-authentication"></a>Apps blokkeren die moderne verificatie niet ondersteunen

Meervoudige verificatie vereist apps die ondersteuning bieden voor moderne verificatie. Apps die moderne verificatie niet ondersteunen, kunnen niet worden geblokkeerd met behulp van regels voor voorwaardelijke toegang.

Voor beveiligde omgevingen dient u eerst verificatie uit te schakelen voor apps die moderne verificatie niet ondersteunen. U kunt dit doen in azure Active Directory met een besturingselement dat binnenkort beschikbaar is.

Gebruik ondertussen een van de volgende methoden om dit voor SharePoint Online en OneDrive voor bedrijven uit te voeren:

- Gebruik PowerShell, Zie [apps blokkeren die geen moderne verificatie gebruiken (ADAL)](https://docs.microsoft.com/mem/intune/protect/app-modern-authentication-block).

- Configureer dit in het SharePoint-Beheercentrum op de pagina ' apparaat toegang ', ' toegang beheren vanuit apps die geen moderne verificatie gebruiken. ' Kies blokkeren.

## <a name="get-started-with-cloud-app-security-or-office-365-cloud-app-security"></a>Aan de slag met de beveiliging van Cloud apps of Office 365 Cloud app-beveiliging

Gebruik de beveiliging van de Cloud-app van Office 365 om risico te evalueren, te waarschuwen voor verdachte activiteiten en om automatisch actie te ondernemen. Hiervoor is Office 365 E5-abonnement vereist.

U kunt ook de beveiliging van de Microsoft Cloud-app gebruiken om meer inzicht te krijgen, zelfs als de toegang is verleend, uitgebreide besturingselementen en verbeterde beveiliging van alle Cloud toepassingen, waaronder Office 365.

Omdat deze oplossing het EMS E5-abonnement adviseert, raden we u aan de Cloud app-beveiliging te starten, zodat u dit kunt gebruiken met andere SaaS-toepassingen in uw omgeving. Begin met standaardbeleid en-instellingen.

Meer informatie:

- [Cloud App Security implementeren](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)

- [Meer informatie over Microsoft Cloud App Security](https://www.microsoft.com/cloud-platform/cloud-app-security)

- [Wat is de beveiliging van Cloud apps?](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)

![Cloud App Security-dashboard](../../media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)

## <a name="additional-resources"></a>Overige informatiebronnen

Deze artikelen en richtlijnen maken extra uitgebreide informatie voor het beveiligen van uw Microsoft 365-omgeving:

- [Microsoft Security Guidance voor politieke campagnes, non-profit organisaties en andere Agile-organisaties](https://docs.microsoft.com/microsoft-365/security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o) (u kunt deze aanbevelingen in elke gewenste omgeving gebruiken, met name Cloud omgevingen)

- [Aanbevolen beveiligingsbeleid en-configuraties voor identiteiten en apparaten](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-365-policies-configurations) (deze aanbevelingen bevatten ondersteuning voor AD FS-omgevingen)
