---
title: Uw Microsoft 365 configureren voor meer beveiliging
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/11/2018
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: 8d274fe3-db51-4107-ba64-865e7155b355
ms.custom:
- seo-marvel-apr2020
description: In dit onderwerp vindt u de aanbevolen configuratie voor instellingen voor tenants die van invloed zijn op de beveiliging van uw Microsoft 365 omgeving.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8a449d9647ae5a8b892967116f28aa6203a5e815
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684169"
---
# <a name="configure-your-microsoft-365-tenant-for-increased-security"></a>Uw Microsoft 365 configureren voor meer beveiliging

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In dit onderwerp vindt u de aanbevolen configuratie voor instellingen voor tenants die van invloed zijn op de beveiliging van uw Microsoft 365 omgeving. Uw beveiligingsbehoeften vereisen mogelijk meer of minder beveiliging. Gebruik deze aanbevelingen als uitgangspunt.

## <a name="check-office-365-secure-score"></a>Veilige Office 365 controleren

Office 365 Secure Score analyseert de beveiliging van uw organisatie op basis van uw normale activiteiten en beveiligingsinstellingen en wijst een score toe. Begin met het noteren van uw huidige score. Als u bepaalde instellingen voor tenants aanpast, wordt de score hoger. Het doel is niet om de maximale score te bereiken, maar om rekening te houden met de mogelijkheden om uw omgeving te beschermen die de productiviteit van uw gebruikers niet negatief beïnvloeden. Zie [Microsoft Secure Score](../defender/microsoft-secure-score.md).

## <a name="tune-threat-management-policies-in-the-microsoft-365-security-center"></a>Beleid voor bedreigingsbeheer afstemmen in Microsoft 365 beveiligingscentrum

Het Microsoft 365 beveiligingscentrum bevat mogelijkheden die uw omgeving beschermen. Het bevat ook rapporten en dashboards die u kunt gebruiken om te controleren en actie te ondernemen. Sommige gebieden zijn standaardbeleidsconfiguraties. Sommige gebieden bevatten geen standaardbeleid of regels. Ga naar dit beleid onder bedreigingsbeheer om de instellingen voor bedreigingsbeheer af te stemmen voor een veiligere omgeving.

<br>

****

|Gebied|Bevat een standaardbeleid|Aanbeveling|
|---|---|---|
|**Anti-phishing**|Ja|<ul><li>Imitatiebeveiliging: als u Defender voor Office 365 en een aangepast domein hebt, configureert u de instellingen voor imitatiebeveiliging in het standaard anti-phishingbeleid om de e-mailaccounts van uw meest waardevolle gebruikers, zoals uw CEO, te beveiligen en uw domein te beschermen. Meer informatie: [Instellingen voor imitatie in anti-phishingbeleid](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) en inzicht in [imitatie](impersonation-insight.md)</li><li>Spoof intelligence: controleer afzenders die uw domein spoofen. Deze afzenders blokkeren of toestaan. Meer informatie: [Inzicht in spoofinformatie in EOP](learn-about-spoof-intelligence.md) en [De lijst tenant toestaan/blokkeren beheren.](tenant-allow-block-list.md)</li></ul>|
|**Anti-Malware Engine**|Ja|Het standaardbeleid bewerken: <ul><li>Selecteer **Het algemene bijlagefilter inschakelen**</li></ul> <p> U kunt ook aangepaste malwarefilterbeleidsregels maken en deze toepassen op opgegeven gebruikers, groepen of domeinen in uw organisatie. <p> Meer informatie: <ul><li>[Beveiliging tegen malware](anti-malware-protection.md)</li><li>[Beleid tegen malware configureren](configure-anti-malware-policies.md)</li></ul>|
|**Safe Bijlagen in Microsoft Defender voor Office 365**|Nee|Klik op de hoofdpagina Safe bijlagen op **Algemene** instellingen en schakel deze instelling in: <ul><li>**Defender voor Office 365 inschakelen voor SharePoint, OneDrive en Microsoft Teams**</li></ul> <p> Maak een Safe bijlagenbeleid met deze instellingen: <ul><li> **Blokkeren:** Selecteer **Blokkeren als** de onbekende malwarerespons.</li><li>**Omleiding inschakelen:** Schakel dit selectievakje in en voer een e-mailadres in, zoals een beheerder of quarantaineaccount.</li><li>**Pas de bovenstaande selectie toe als er malware wordt gescand op** bijlagen of als er een fout optreedt: Selectievakje.</li><li>**_Toegepast op_*: **Het domein van de geadresseerde is** uw domein \> selecteren.</li></ul> <p> Meer informatie: [Safe bijlagen voor SharePoint, OneDrive en Microsoft Teams](mdo-for-spo-odb-and-teams.md) en Het beleid Safe Bijlagen [instellen](set-up-safe-attachments-policies.md)|
|**Safe Koppelingen in Microsoft Defender voor Office 365**|Ja|Klik op de hoofdpagina voor Safe op **Algemene instellingen:** <ul><li>**Gebruik Safe Koppelingen in: Office 365 toepassingen**: Controleer of deze instelling is ingeschakeld.</li><li>**Houd niet bij wanneer gebruikers op koppelingen Safe:** Schakel deze instelling uit om klikken van gebruikers bij te houden.</li></ul> <p> Maak een Safe koppelingenbeleid met deze instellingen: <ul><li>**Selecteer de actie voor onbekende potentieel schadelijke URL's in berichten:** Controleer of deze instelling is **aan.**</li><li>Selecteer de actie voor onbekende of potentieel schadelijke **URL's binnen Microsoft Teams**: Controleer of deze instelling is **aan.**</li><li>**Realtime URL-scan toepassen op verdachte koppelingen en koppelingen** die naar bestanden wijzen: Schakel dit selectievakje in.</li><li>**Wacht totdat URL-scannen is voltooid voordat u het bericht bezorgt:** Selectievakje.</li><li>**Koppelingen Safe toepassen op e-mailberichten die binnen de** organisatie zijn verzonden: Schakel dit selectievakje in</li><li>**Gebruikers mogen niet doorklikken naar de oorspronkelijke URL:** Selectievakje.</li><li>**Toegepast op:** **Het domein van de geadresseerde is** uw domein \> selecteren.</li></ul> <p> Meer informatie: [Beleidsregels Safe koppelingen instellen.](set-up-safe-links-policies.md)|
|**Antispam (e-mailfiltering)**|Ja| Waar moet u op letten: Te veel spam: Kies de aangepaste instellingen en bewerk het standaardbeleid voor spamfilters. Meer informatie: [Microsoft 365 Bescherming tegen ongewenste e-mail](anti-spam-protection.md).|
|***E-mailverificatie***|Ja|Voor e-mailverificatie wordt een DNS (Domain Name System) gebruikt om controleerbare informatie toe te voegen aan e-mailberichten over de afzender van een e-mailbericht. Microsoft 365 e-mailverificatie instellen voor het standaarddomein (onmicrosoft.com), maar Microsoft 365 beheerders kunnen ook e-mailverificatie gebruiken voor aangepaste domeinen. Er worden drie verificatiemethoden gebruikt: <ul><li>Sender Policy Framework (of SPF).</li><ul><li>Zie SPF instellen in een Microsoft 365 om [spoofing te voorkomen.](set-up-spf-in-office-365-to-help-prevent-spoofing.md)</li></ul> <li>DomainKeys Identified Mail (DKIM).</li><ul><li>Zie [DKIM gebruiken om uitgaande e-mail te valideren die is verzonden vanuit uw aangepaste domein.](use-dkim-to-validate-outbound-email.md)</li><li>Nadat u DKIM hebt geconfigureerd, kunt u deze inschakelen in het beveiligingscentrum.</li></ul><li>Domeingebaseerde berichtverificatie, rapportage en conformatie (DMARC).</li><ul><li>Voor DMARC-instelling [DMARC gebruiken om e-mail te valideren in Microsoft 365.](use-dmarc-to-validate-email.md)</li></ul></ul>|
|

> [!NOTE]
> Voor niet-standaardimplementaties van SPF, hybride implementaties en probleemoplossing: Hoe [Microsoft 365 Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md)gebruikt om spoofing te voorkomen.

## <a name="view-dashboards-and-reports-in-the-security--compliance-center"></a>Dashboards en rapporten weergeven in het beveiligings- & compliancecentrum

Ga naar deze rapporten en dashboards voor meer informatie over de status van uw omgeving. De gegevens in deze rapporten worden uitgebreid naarmate uw organisatie gebruikmaakt van Office 365 services. Wees op dit moment vertrouwd met wat u kunt controleren en actie kunt ondernemen. Zie Rapporten in het beveiligings- & [compliancecentrum voor meer informatie.](../../compliance/reports-in-security-and-compliance.md)

<br>

****

|Dashboard|Omschrijving|
|---|---|
|[Dashboard Bedreigingsbeheer](security-dashboard.md)|Gebruik  dit dashboard in de sectie Bedreigingsbeheer van het beveiligingscentrum om te zien welke bedreigingen al zijn afgehandeld en als handig hulpmiddel voor het rapporteren aan zakelijke besluitvormers over wat de mogelijkheden voor bedreigingsonderzoek en -reactie al hebben gedaan om uw bedrijf te beveiligen.|
|[Bedreigingsverkenner (of realtime detecties)](threat-explorer.md)|Dit is ook in de **sectie Bedreigingsbeheer** van het beveiligingscentrum. Als u een aanval op uw tenant onderzoekt of ondervindt, gebruikt u Explorer (of realtime detecties) om bedreigingen te analyseren. Explorer (en het realtimedetectierapport) toont het aantal aanvallen in de tijd en u kunt deze gegevens analyseren op bedreigingsfamilies, infrastructuur voor aanvallers en meer. U kunt ook verdachte e-mailberichten markeren voor de lijst Incidenten.|
|Rapporten : Dashboard|Bekijk in **de sectie** Rapporten van het beveiligingscentrum auditrapporten voor uw SharePoint Online en Exchange Online organisaties. U hebt ook toegang tot Azure Active Directory (Azure AD) gebruikersmeldrapporten, gebruikersactiviteitsrapporten en het Azure AD-auditlogboek op de **pagina Rapporten** weergeven.|
|

![Dashboard beveiligingscentrum](../../media/870ab776-36d2-49c7-b615-93b2bc42fce5.png)

## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>Extra instellingen Exchange Online tenants configureren

Veel van de besturingselementen voor beveiliging en beveiliging in het Exchange beheercentrum zijn ook opgenomen in het beveiligingscentrum. U hoeft deze niet op beide plaatsen te configureren. Hier zijn een paar extra instellingen die worden aanbevolen.

<br>

****

|Gebied|Bevat een standaardbeleid|Aanbeveling|
|---|---|---|
|**E-Flow** (regels voor e-mailstroom, ook wel transportregels genoemd)|Nee|Voeg een e-mailstroomregel toe om u te beschermen tegen ransomware door uitvoerbare bestandstypen te blokkeren en Office bestandstypen die macro's bevatten. Zie E-mailstroomregels gebruiken om [berichtbijlagen in](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)Exchange Online. <p> Bekijk deze aanvullende onderwerpen: <ul><li>[Beveiligen tegen ransomware](../../admin/security-and-compliance/secure-your-business-data.md#5-protect-against-ransomware)</li><li>[Malware- en ransomwarebeveiliging in Microsoft 365](/compliance/assurance/assurance-malware-and-ransomware-protection)</li><li>[Herstellen van een ransomware-aanval in Office 365](recover-from-ransomware.md)</li></ul> <p> Maak een e-mailstroomregel om te voorkomen dat e-mail automatisch wordt doorgestuurd naar externe domeinen. Zie [Mitigating Client External Forwarding Rules](/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score)with Secure Score (Regels voor extern doorsturen van client met secure score) voor meer informatie. <p> Meer informatie: [E-mailstroomregels (transportregels) in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)|
|**Moderne verificatie inschakelen**|Nee|Moderne verificatie is een vereiste voor het gebruik van meervoudige verificatie (MFA). MFA wordt aanbevolen voor het beveiligen van toegang tot cloudbronnen, waaronder e-mail. <p> Zie deze onderwerpen: <ul><li>[Moderne verificatie in- of uitschakelen in Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)</li><li>[Skype voor Bedrijven Online: Uw tenant inschakelen voor moderne verificatie](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)</li></ul> <p> Moderne verificatie is standaard ingeschakeld voor Office 2016-clients, SharePoint Online en OneDrive voor Bedrijven. <p> Meer informatie: Hoe moderne verificatie werkt voor [Office 2013 en Office 2016-clientapps](../../enterprise/modern-auth-for-office-2013-and-2016.md)|
|

## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>Beleid voor delen voor tenants configureren in SharePoint beheercentrum

Microsoft-aanbevelingen voor het configureren SharePoint teamsites op een hoger beveiligingsniveau, te beginnen met basislijnbeveiliging. Zie Beleidsaanbevelingen voor het beveiligen van SharePoint [sites en bestanden voor meer informatie.](sharepoint-file-access-policies.md)

SharePoint teamsites die zijn geconfigureerd op basislijnniveau, kunnen bestanden delen met externe gebruikers via anonieme toegangskoppelingen. Deze methode wordt aanbevolen in plaats van bestanden per e-mail te verzenden.

Als u de doelstellingen voor basislijnbeveiliging wilt ondersteunen, configureert u beleid voor delen in de tenant, zoals hier wordt aanbevolen. Instellingen voor delen voor afzonderlijke sites kunnen beperkender zijn dan dit beleid voor de hele tenant, maar niet meer permissief.

<br>

****

|Gebied|Bevat een standaardbeleid|Aanbeveling|
|---|---|---|
|**Delen** (SharePoint Online en OneDrive voor Bedrijven)|Ja|Extern delen is standaard ingeschakeld. Deze instellingen worden aanbevolen: <ul><li>Delen toestaan voor geverifieerde externe gebruikers en het gebruik van anonieme toegangskoppelingen (standaardinstelling).</li><li>Anonieme toegangskoppelingen verlopen in deze vele dagen. Voer desgewenst een getal in, zoals 30 dagen.</li><li>Standaardkoppelingstype: selecteer Intern (alleen personen in de organisatie). Gebruikers die via anonieme koppelingen willen delen, moeten deze optie kiezen in het menu Delen.</li></ul> <p> Meer informatie: [Overzicht van extern delen](/sharepoint/external-sharing-overview)|
|

SharePoint beheercentrum en OneDrive voor Bedrijven beheercentrum bevatten dezelfde instellingen. De instellingen in een van beide beheercentrums zijn op beide van toepassing.

## <a name="configure-settings-in-azure-active-directory"></a>Instellingen configureren in Azure Active Directory

Zorg ervoor dat u deze twee gebieden in Azure Active Directory om de installatie van tenants voor veiligere omgevingen te voltooien.

### <a name="configure-named-locations-under-conditional-access"></a>Benoemde locaties configureren (onder voorwaardelijke toegang)

Als uw organisatie kantoren met beveiligde netwerktoegang bevat, voegt u het vertrouwde IP-adresbereik toe aan Azure Active Directory benoemde locaties. Met deze functie kunt u het aantal gerapporteerde fout-positieven voor aanmeldingsrisicogebeurtenissen verminderen.

Zie: [Benoemde locaties in Azure Active Directory](/azure/active-directory/active-directory-named-locations)

### <a name="block-apps-that-dont-support-modern-authentication"></a>Apps blokkeren die geen ondersteuning bieden voor moderne verificatie

Voor meervoudige verificatie zijn apps vereist die moderne verificatie ondersteunen. Apps die geen moderne verificatie ondersteunen, kunnen niet worden geblokkeerd met behulp van regels voor voorwaardelijke toegang.

Voor veilige omgevingen moet u verificatie uitschakelen voor apps die geen ondersteuning bieden voor moderne verificatie. U kunt dit doen in Azure Active Directory met een besturingselement dat binnenkort beschikbaar is.

Gebruik ondertussen een van de volgende methoden om dit te doen voor SharePoint Online en OneDrive voor Bedrijven:

- Gebruik PowerShell, zie Apps blokkeren die geen moderne verificatie [(ADAL) gebruiken.](/mem/intune/protect/app-modern-authentication-block)

- Configureer dit in SharePoint beheercentrum op de pagina 'Apparaattoegang': 'Toegang beheren vanuit apps die geen moderne verificatie gebruiken'. Kies Blokkeren.

## <a name="get-started-with-cloud-app-security-or-office-365-cloud-app-security"></a>Aan de slag met Cloud App Security of Office 365 Cloud App Security

Gebruik Office 365 Cloud App Security om risico's te evalueren, om verdachte activiteiten te waarschuwen en om automatisch actie te ondernemen. Vereist Office 365 E5-abonnement.

Of gebruik Microsoft Cloud App Security om meer zichtbaarheid te krijgen, zelfs nadat toegang is verleend, uitgebreide besturingselementen en verbeterde beveiliging voor al uw cloudtoepassingen, inclusief Office 365.

Omdat deze oplossing het EMS E5-abonnement aanbeveelt, raden we u aan om te beginnen met Cloud App Security, zodat u deze kunt gebruiken met andere SaaS-toepassingen in uw omgeving. Begin met standaardbeleid en -instellingen.

Meer informatie:

- [Cloud App Security implementeren](/cloud-app-security/getting-started-with-cloud-app-security)
- [Meer informatie over Microsoft Cloud App Security](https://www.microsoft.com/cloud-platform/cloud-app-security)
- [Wat is Cloud App Security?](/cloud-app-security/what-is-cloud-app-security)

![Cloud App Security-dashboard](../../media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)

## <a name="additional-resources"></a>Aanvullende bronnen

Deze artikelen en handleidingen bevatten aanvullende beschrijvende informatie voor het beveiligen van uw Microsoft 365 omgeving:

- [Beveiligingsaanbevelingen van Microsoft voor politieke campagnes,](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) non-profitorganisaties en andere agile-organisaties (u kunt deze aanbeveling gebruiken in elke omgeving, met name in cloudomgevingen)

- [Aanbevolen beveiligingsbeleid en configuraties voor identiteiten en apparaten](microsoft-365-policies-configurations.md) (deze aanbevelingen bevatten help voor AD FS-omgevingen)
