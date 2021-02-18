---
title: Uw Microsoft 365-tenant configureren voor betere beveiliging
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
description: In dit onderwerp vindt u informatie over de aanbevolen configuratie voor tenantinstellingen die van invloed zijn op de beveiliging van uw Microsoft 365-omgeving.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6eff529a4ab2271df30579af227fe0c28691ae58
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286343"
---
# <a name="configure-your-microsoft-365-tenant-for-increased-security"></a>Uw Microsoft 365-tenant configureren voor betere beveiliging

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In dit onderwerp vindt u informatie over de aanbevolen configuratie voor tenantinstellingen die van invloed zijn op de beveiliging van uw Microsoft 365-omgeving. Uw beveiligingsbehoeften vereisen mogelijk meer of minder beveiliging. Gebruik deze aanbevelingen als uitgangspunt.

## <a name="check-office-365-secure-score"></a>Secure Score van Office 365 controleren

Office 365 Secure Score analyseert de beveiliging van uw organisatie op basis van uw reguliere activiteiten en beveiligingsinstellingen en wijst een score toe. Noteer eerst uw huidige score. Als u bepaalde instellingen voor de hele tenant aanpast, wordt uw score hoger. Het doel is niet de maximale score te bereiken, maar u moet rekening houden met mogelijkheden om uw omgeving te beschermen die de productiviteit van uw gebruikers niet negatief beïnvloeden. Zie [Microsoft Secure Score.](../mtp/microsoft-secure-score.md)

## <a name="tune-threat-management-policies-in-the-microsoft-365-security-center"></a>Beleid voor risicobeheer afstemmen in het Microsoft 365-beveiligingscentrum

Het Microsoft 365-beveiligingscentrum bevat mogelijkheden die uw omgeving beschermen. Het bevat ook rapporten en dashboards die u kunt gebruiken om toezicht te houden en actie te ondernemen. Bij sommige gebieden worden standaardbeleidsconfiguraties gebruikt. Sommige gebieden bevatten geen standaardbeleid of regels. Ga naar dit beleid onder bedreigingsbeheer om instellingen voor risicobeheer af te stemmen voor een veiligere omgeving.

****

|Gebied|Bevat een standaardbeleid|Aanbeveling|
|---|---|---|
|**Anti-phishing**|Ja|Als u een aangepast domein hebt, configureert u het standaard anti-phishingbeleid om de e-mailaccounts van de meest waardevolle gebruikers te beveiligen, zoals uw ceo, en om uw domein te beschermen. <p> Bekijk [het anti-phishingbeleid in Office 365](set-up-anti-phishing-policies.md) en zie [Anti-phishingbeleid configureren in EOP](configure-anti-phishing-policies-eop.md) of [Anti-phishingbeleid configureren in Microsoft Defender voor Office 365.](configure-atp-anti-phishing-policies.md)|
|**Anti-Malware Engine**|Ja| Het standaardbeleid bewerken: <ul><li>Filter algemene bijlagetypen: Selecteren op</li></ul> <p> U kunt ook aangepaste beleidsregels voor malwarefilters maken en deze toepassen op opgegeven gebruikers, groepen of domeinen in uw organisatie. <p> Meer informatie: <ul><li>[Beveiliging tegen malware](anti-malware-protection.md)</li><li>[Beleid tegen malware configureren](configure-anti-malware-policies.md)</li></ul>|
|**Veilige bijlagen in Microsoft Defender voor Office 365**|Nee|Klik op de hoofdpagina voor veilige bijlagen op **Algemene instellingen** en schakel deze instelling in: <ul><li>**Defender voor Office 365 inschakelen voor SharePoint, OneDrive en Microsoft Teams**</li></ul> <p> Maak een beleid voor veilige bijlagen met de volgende instellingen: <ul><li> **Blokkeren:** selecteer **Blokkeren als** het onbekende malware-antwoord.</li><li>**Omleiding inschakelen:** schakel dit selectievakje in en voer een e-mailadres in, zoals een beheerder of quarantaineaccount.</li><li>**Pas de bovenstaande selectie toe als er malware wordt gescand op** bijlagen of als er een fout optreedt: Controleer dit vakje.</li><li>**_Toegepast op:_* **het domein van de ontvanger wordt** uw domein \> geselecteerd.</li></ul> <p> Meer informatie: [Veilige bijlagen voor SharePoint, OneDrive](atp-for-spo-odb-and-teams.md) en Microsoft Teams en beleidsregels [voor veilige bijlagen instellen](set-up-atp-safe-attachments-policies.md)|
|**Veilige koppelingen in Microsoft Defender voor Office 365**|Ja|Klik op de hoofdpagina voor veilige koppelingen op **Algemene instellingen:** <ul><li>**Gebruik veilige koppelingen in: Office 365-toepassingen:** controleer of deze instelling is ingeschakeld.</li><li>**Houd niet bij wanneer gebruikers op veilige koppelingen klikken:** schakel deze instelling uit als u klikken van gebruikers wilt bijhouden.</li></ul> <p> Maak een beleid voor veilige koppelingen met de volgende instellingen: <ul><li>**Selecteer de actie voor onbekende, mogelijk schadelijke URL's in berichten:** Controleer of deze instelling is **aan.**</li><li>Selecteer de actie voor onbekende of mogelijk schadelijke **URL's in Microsoft Teams:** controleer of deze instelling is **aan.**</li><li>**Real-time URL's scannen op verdachte koppelingen en koppelingen die naar bestanden** wijzen: Schakel dit selectievakje in.</li><li>**Wacht totdat het scannen van de URL is voltooid voordat het bericht** wordt weergegeven: Controleer dit vakje.</li><li>**Veilige koppelingen toepassen op e-mailberichten die binnen** de organisatie worden verzonden: Schakel dit selectievakje in</li><li>**Gebruikers niet toestaan door te klikken naar de oorspronkelijke URL:** selecteer dit vakje.</li><li>**Toegepast op:** **het domein van de ontvanger is** uw domein \> selecteren.</li></ul> <p> Meer informatie: [Beleidsregels voor veilige koppelingen instellen.](set-up-atp-safe-links-policies.md)|
|**Antispam (filteren van e-mail)**|Ja| Waar moet ik op letten: <ul><li>Te veel spam: kies de aangepaste instellingen en bewerk het standaardbeleid voor het filteren van ongewenste e-mail.</li><li>Spoof intelligence: bekijk afzenders die uw domein vervalsen. Deze afzenders blokkeren of toestaan.</li></ul> <p> Meer informatie: [Microsoft 365-beveiliging tegen ongewenste e-mail.](anti-spam-protection.md)|
|***E-mailverificatie***|Ja|Voor e-mailverificatie wordt een DNS (Domain Name System) gebruikt om controleerbare informatie over de afzender van een e-mailbericht toe te voegen aan e-mailberichten. Microsoft 365 stelt e-mailverificatie in voor het standaarddomein (onmicrosoft.com), maar Microsoft 365-beheerders kunnen e-mailverificatie ook gebruiken voor aangepaste domeinen. Er worden drie verificatiemethoden gebruikt: <ul><li>Sender Policy Framework (of SPF).</li><ul><li>Zie [SPF in Microsoft 365 instellen om spoofing te helpen voorkomen.](set-up-spf-in-office-365-to-help-prevent-spoofing.md)</li></ul> <li>DomainKeys Identified Mail (DKIM).</li><ul><li>Zie [DKIM gebruiken om uitgaande e-mail te](use-dkim-to-validate-outbound-email.md)valideren die wordt verzonden vanaf uw aangepaste domein.</li><li>Nadat u DKIM hebt geconfigureerd, moet u het inschakelen in het beveiligingscentrum.</li></ul><li>Domain-based Message Authentication, Reporting, and Conformance (DMARC).</li><ul><li>Gebruik DMARC voor het instellen van [DMARC om e-mail te valideren in Microsoft 365.](use-dmarc-to-validate-email.md)</li></ul></ul>|
|

> [!NOTE]
> Voor niet-standaard implementaties van SPF, hybride implementaties en probleemoplossing: Hoe [Microsoft 365 SPF (Sender Policy Framework)](how-office-365-uses-spf-to-prevent-spoofing.md)gebruikt om spoofing te voorkomen.

## <a name="view-dashboards-and-reports-in-the-security-and-compliance-centers"></a>Dashboards en rapporten weergeven in de beveiligings- en compliancecentra

Ga naar deze rapporten en dashboards voor meer informatie over de status van uw omgeving. De gegevens in deze rapporten worden uitgebreid wanneer uw organisatie gebruikmaakt van Office 365-services. Op dit moment bent u bekend met wat u kunt controleren en waar u actie op kunt ondernemen. Zie voor meer informatie: [Rapporten in de Microsoft 365-beveiligings- en compliancecentra.](../../compliance/reports-in-security-and-compliance.md)

****

|Dashboard|Beschrijving|
|---|---|
|[Dashboard voor bedreigingsbeheer](security-dashboard.md)|Gebruik  dit dashboard in de sectie Bedreigingsbeheer van het beveiligingscentrum om de bedreigingen te zien die al zijn verwerkt en als een handig hulpmiddel voor het rapporteren aan zakelijke besluitvormers over welk bedreigingsonderzoek en welke reactiemogelijkheden al zijn uitgevoerd om uw bedrijf te beveiligen.|
|[Bedreigingsverkenner (of realtime detecties)](threat-explorer.md)|Dit staat ook in de **sectie Bedreigingsbeheer** van het beveiligingscentrum. Als u een aanval op uw tenant onderzoekt of ondervindt, gebruikt u Explorer (of realtime detecties) om bedreigingen te analyseren. Explorer (en het rapport met realtime detecties) toont het aantal aanvallen in de tijd en u kunt deze gegevens analyseren op bedreigingsfamilies, de infrastructuur van de aanvaller en meer. U kunt ook verdachte e-mailberichten markeren voor de lijst met incidenten.|
|Rapporten — Dashboard|Bekijk in **de sectie** Rapporten van het beveiligingscentrum controlerapporten voor uw SharePoint Online- en Exchange Online-organisaties. U hebt ook toegang tot aanmeldingsrapporten van Azure Active Directory (Azure AD) en rapporten over gebruikersactiviteiten en het Azure AD-auditlogboek op de pagina Rapporten **weergeven.**|
|

![Dashboard van beveiligingscentrum](../../media/870ab776-36d2-49c7-b615-93b2bc42fce5.png)

## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>Aanvullende instellingen voor de tenant in de hele Exchange Online configureren

Veel van de besturingselementen voor beveiliging en beveiliging in het Exchange-beheercentrum zijn ook opgenomen in het beveiligingscentrum. U hoeft deze niet op beide locaties te configureren. Hier zijn enkele extra instellingen die worden aanbevolen.

****

|Gebied|Bevat een standaardbeleid|Aanbeveling|
|---|---|---|
|**E-mailstroom** (regels voor de e-mailstroom, ook wel transportregels genoemd)|Nee|Voeg een regel voor de e-mailstroom toe om te beveiligen tegen ransomware door uitvoerbare bestandstypen en Office-bestandstypen met macro's te blokkeren. Zie Regels voor de [e-mailstroom gebruiken om berichtbijlagen in Exchange Online te controleren voor meer informatie.](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments) <p> Zie de volgende aanvullende onderwerpen: <ul><li>[Beveiligen tegen ransomware](../../admin/security-and-compliance/secure-your-business-data.md#5-protect-against-ransomware)</li><li>[Malware- en ransomware-beveiliging in Microsoft 365](https://docs.microsoft.com/compliance/assurance/assurance-malware-and-ransomware-protection)</li><li>[Herstel van een aanval van ransomware in Office 365](recover-from-ransomware.md)</li></ul> <p> Maak een regel voor de e-mailstroom om te voorkomen dat e-mail automatisch wordt doorgestuurd naar externe domeinen. Zie Regels voor externe doorsturen van klanten verminderen [met Secure Score voor meer informatie.](https://docs.microsoft.com/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score) <p> Meer informatie: [E-mailstroomregels (transportregels) in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)|
|**Moderne verificatie inschakelen**|Nee|Moderne verificatie is een vereiste voor het gebruik van multi-factor authentication (MFA). MFA wordt aanbevolen voor het beveiligen van de toegang tot cloudbronnen, waaronder e-mail. <p> Zie de volgende onderwerpen: <ul><li>[Moderne verificatie in- of uitschakelen in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)</li><li>[Skype voor Bedrijven Online: Uw tenant inschakelen voor moderne verificatie](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)</li></ul> <p> Moderne verificatie is standaard ingeschakeld voor Office 2016-clients, SharePoint Online en OneDrive voor Bedrijven. <p> Meer informatie: [Hoe moderne verificatie werkt voor Office 2013- en Office 2016-clientapps](../../enterprise/modern-auth-for-office-2013-and-2016.md)|
|

## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>Beleidsregels voor delen voor de hele tenant configureren in het SharePoint-beheercentrum

Aanbevelingen van Microsoft voor het configureren van SharePoint-teamsites op hogere beschermingsniveaus, te beginnen met basislijnbeveiliging. Zie Beleidsaanbevelingen voor het beveiligen van [SharePoint-sites en -bestanden voor meer informatie.](sharepoint-file-access-policies.md)

SharePoint-teamsites die zijn geconfigureerd op basislijnniveau staan het delen van bestanden met externe gebruikers toe via koppelingen voor anonieme toegang. Deze methode wordt aanbevolen in plaats van bestanden per e-mail te verzenden.

Ter ondersteuning van de doelstellingen voor basislijnbeveiliging configureert u beleidsregels voor delen voor de hele tenant, zoals hier wordt aanbevolen. Instellingen voor delen voor afzonderlijke sites kunnen meer beperkend zijn dan dit beleid voor de hele tenant, maar niet meer ruim.

****

|Gebied|Bevat een standaardbeleid|Aanbeveling|
|---|---|---|
|**Delen** (SharePoint Online en OneDrive voor Bedrijven)|Ja|Extern delen is standaard ingeschakeld. Deze instellingen worden aanbevolen: <ul><li>Delen toestaan voor geverifieerde externe gebruikers en het gebruik van koppelingen voor anonieme toegang (standaardinstelling).</li><li>Anonieme toegangskoppelingen verlopen over zoveel dagen. Voer desgewenst een getal in, bijvoorbeeld 30 dagen.</li><li>Standaardkoppelingstype: intern selecteren (alleen personen in de organisatie). Gebruikers die via anonieme koppelingen willen delen, moeten deze optie kiezen in het menu Delen.</li></ul> <p> Meer informatie: [Overzicht van extern delen](https://docs.microsoft.com/sharepoint/external-sharing-overview)|
|

In het SharePoint-beheercentrum en het OneDrive voor Bedrijven-beheercentrum zijn dezelfde instellingen op te nemen. De instellingen in het beheercentrum zijn van toepassing op beide.

## <a name="configure-settings-in-azure-active-directory"></a>Instellingen configureren in Azure Active Directory

Bezoek deze twee gebieden in Azure Active Directory om de installatie voor veiligere omgevingen voor de hele tenant te voltooien.

### <a name="configure-named-locations-under-conditional-access"></a>Benoemde locaties configureren (onder voorwaardelijke toegang)

Als uw organisatie kantoren met beveiligde netwerktoegang bevat, voegt u de vertrouwde IP-adresbereiken toe aan Azure Active Directory als benoemde locaties. Met deze functie kunt u het aantal gerapporteerde fout-positieven voor gebeurtenissen met aanmeldingsrisico's verminderen.

Zie: [Benoemde locaties in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-named-locations)

### <a name="block-apps-that-dont-support-modern-authentication"></a>Apps blokkeren die geen ondersteuning bieden voor moderne verificatie

Voor meervoudige verificatie zijn apps vereist die moderne verificatie ondersteunen. Apps die geen ondersteuning bieden voor moderne verificatie kunnen niet worden geblokkeerd met behulp van regels voor voorwaardelijke toegang.

Schakel in veilige omgevingen verificatie uit voor apps die geen ondersteuning bieden voor moderne verificatie. U kunt dit doen in Azure Active Directory met een besturingselement dat binnenkort beschikbaar komt.

Gebruik ondertussen een van de volgende methoden om dit voor SharePoint Online en OneDrive voor Bedrijven te doen:

- Gebruik PowerShell, zie [Apps blokkeren die geen moderne verificatie (ADAL) gebruiken.](https://docs.microsoft.com/mem/intune/protect/app-modern-authentication-block)

- Configureer dit in het SharePoint-beheercentrum op de pagina Apparaattoegang: 'Toegang beheren vanuit apps die geen moderne verificatie gebruiken'. Kies Blokkeren.

## <a name="get-started-with-cloud-app-security-or-office-365-cloud-app-security"></a>Aan de slag met Cloud-app-beveiliging of Beveiliging van Office 365 Cloud-apps

Gebruik Office 365 Cloud App Security om risico's te evalueren, om u te waarschuwen voor verdachte activiteiten en om automatisch actie te ondernemen. Hiervoor is een Office 365 E5-abonnement vereist.

Of gebruik Microsoft Cloud App Security voor een betere zichtbaarheid, zelfs nadat toegang is verleend, uitgebreide besturingselementen en verbeterde beveiliging voor al uw cloudtoepassingen, inclusief Office 365.

Omdat deze oplossing het EMS E5-abonnement aanbeveelt, raden we u aan te beginnen met Cloud App Security, zodat u deze kunt gebruiken met andere SaaS-toepassingen in uw omgeving. Begin met standaardbeleid en -instellingen.

Meer informatie:

- [Cloud App Security implementeren](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)

- [Meer informatie over Microsoft Cloud App Security](https://www.microsoft.com/cloud-platform/cloud-app-security)

- [Wat is Cloud-app-beveiliging?](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)

![Cloud App Security-dashboard](../../media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)

## <a name="additional-resources"></a>Aanvullende bronnen

Deze artikelen en handleidingen bevatten aanvullende beschrijvende informatie voor het beveiligen van uw Microsoft 365-omgeving:

- [Microsoft-beveiligings richtlijnen voor campagnecampagnes,](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) non-profitorganisaties en andere Agile-organisaties (u kunt deze aanbevelingen gebruiken in elke omgeving, met name in cloudomgevingen)

- [Aanbevolen beveiligingsbeleid en configuraties voor identiteiten en apparaten](microsoft-365-policies-configurations.md) (deze aanbevelingen bevatten help voor AD FS-omgevingen)
