---
title: Uw Microsoft 365-tenant configureren voor meer beveiliging
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
description: In dit onderwerp wordt u door de aanbevolen configuratie voor tenantbrede instellingen gewandeld die van invloed zijn op de beveiliging van uw Microsoft 365-omgeving.
ms.openlocfilehash: 5e02a871385deb2bae9e788eacd772c08af1d972
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588050"
---
# <a name="configure-your-microsoft-365-tenant-for-increased-security"></a>Uw Microsoft 365-tenant configureren voor meer beveiliging

In dit onderwerp wordt u door de aanbevolen configuratie voor tenantbrede instellingen gewandeld die van invloed zijn op de beveiliging van uw Microsoft 365-omgeving. Voor uw beveiligingsbehoeften is mogelijk meer of minder beveiliging nodig. Gebruik deze aanbevelingen als uitgangspunt.

## <a name="check-office-365-secure-score"></a>Veilige score van Office 365 controleren

Office 365 Secure Score analyseert de beveiliging van uw organisatie op basis van uw reguliere activiteiten en beveiligingsinstellingen en wijst een score toe. Begin met het noteren van uw huidige score. Als u bepaalde instellingen voor de hele tenant aanpast, verhoogt u de score. Het doel is niet om de maximale score te bereiken, maar om zich bewust te zijn van mogelijkheden om uw omgeving te beschermen die de productiviteit voor uw gebruikers niet negatief beïnvloeden. Zie [Microsoft Secure Score](../mtp/microsoft-secure-score.md).

## <a name="tune-threat-management-policies-in-the-microsoft-365-security-center"></a>Beheerbeleid voor bedreigingen afstemmen in het Microsoft 365-beveiligingscentrum

Het Microsoft 365-beveiligingscentrum bevat mogelijkheden die uw omgeving beschermen. Het bevat ook rapporten en dashboards die u gebruiken om te controleren en actie te ondernemen. Sommige gebieden worden geleverd met standaardbeleidsconfiguraties. Sommige gebieden bevatten geen standaardbeleid of -regels. Bezoek dit beleid onder bedreigingsbeheer om instellingen voor bedreigingsbeheer af te stemmen op een veiligere omgeving.

||||
|---|---|---|
|**Gebied**|**Bevat een standaardbeleid**|**Aanbeveling**|
|**Anti-phishing**|Ja|Als u een aangepast domein hebt, configureert u het standaardbeleid voor antiphishing om de e-mailaccounts van uw meest waardevolle gebruikers, zoals uw CEO, te beschermen en uw domein te beschermen. Bekijk [antiphishingbeleid in Office 365](set-up-anti-phishing-policies.md) en zie [Anti-phishingbeleid configureren in EOP-](configure-anti-phishing-policies-eop.md) of [ATP-antiphishingbeleid configureren in Office 365](configure-atp-anti-phishing-policies.md).|
|**Anti-Malware Engine**|Ja| Het standaardbeleid bewerken: <br/> &ensp;&ensp;* Gemeenschappelijke bijlagetypenfilter — Selecteer op <br/><br/> U ook aangepaste beleid voor malwarefilters maken en deze toepassen op bepaalde gebruikers, groepen of domeinen in uw organisatie. <br/><br/> Meer informatie: <br/> &ensp;&ensp;* [Bescherming tegen malware](anti-malware-protection.md) <br/> &ensp;&ensp;* [Anti-malwarebeleid configureren](configure-anti-malware-policies.md)|
|**ATP-veilige bijlagen**|Nee| Bescherm bestanden op de hoofdpagina voor veilige bijlagen in SharePoint, OneDrive en Microsoft Teams door dit vak in te schakelen: <br/> &ensp;&ensp;* ATP inschakelen voor SharePoint, OneDrive en Microsoft Teams <br/><br/> Voeg een nieuw veilig bevestigingsbeleid toe met deze instellingen: <br/> &ensp;&ensp;* Blokkeren - Blok de huidige en toekomstige e-mails en bijlagen met gedetecteerde malware (kies deze optie) <br/> &ensp;&ensp;* Omleiding inschakelen — (Schakel dit selectievakje in en voer een e-mailadres in, zoals een beheerders- of quarantaineaccount) <br/> &ensp;&ensp;* Pas de bovenstaande selectie toe als er een keer een keer een fout optreedt voor malwarescannen voor bijlagen (schakel dit selectievakje in) <br/> &ensp;&ensp;* Toegepast op - Het domein van de ontvanger is (selecteer uw domein) <br/><br/>Meer informatie: [Office 365 ATP Safe Attachments-beleid instellen](set-up-atp-safe-attachments-policies.md)|
|**Veilige ATP-koppelingen**|Ja| Voeg deze instelling toe aan het standaardbeleid voor de hele organisatie: <br/> &ensp;&ensp;* Gebruik veilige koppelingen in: Microsoft 365 Apps for enterprise, Office voor iOS en Android (selecteer deze optie). <br/><br/>Aanbevolen beleid voor specifieke ontvangers: <br/> &ensp;&ensp;* URL's worden herschreven en gecontroleerd aan de hand van een lijst met bekende schadelijke koppelingen wanneer de gebruiker op de link klikt (selecteer deze optie). <br/> &ensp;&ensp;* Gebruik veilige bijlagen om downloadbare inhoud te scannen (schakel dit vakje in). <br/> &ensp;&ensp;* Toegepast op - Het domein van de ontvanger is (selecteer uw domein). <br/><br/> Meer informatie: [Office 365 ATP Safe Links](atp-safe-links.md).|
|**Anti-spam (filtering van e-mail)**|Ja| Waar moet je op letten: <br/> &ensp;&ensp;* Te veel spam - Kies de aangepaste instellingen en bewerk het standaardfilterbeleid voor spam. <br/> &ensp;&ensp;* Spoof intelligentie - Review afzenders die spoofing uw domein. Deze afzenders blokkeren of toestaan. <br/><br/>Meer informatie: [Microsoft 365 Email Anti-Spam Protection](anti-spam-protection.md).|
|***E-mailverificatie***|Ja|E-mailverificatie gebruikt een Domain Name System (DNS) om verifieerbare informatie toe te voegen aan e-mailberichten over de afzender van een e-mail. Microsoft 365 stelt e-mailverificatie in voor het standaarddomein (onmicrosoft.com), maar Microsoft 365-beheerders kunnen ook e-mailverificatie gebruiken voor aangepaste domeinen. Er worden drie verificatiemethoden gebruikt: <br/><br/> &ensp;&ensp;* Sender Policy Framework (of SPF).<br/>&ensp;&ensp;&ensp;&ensp;- Zie [SPF instellen in Microsoft 365 om spoofing te voorkomen](set-up-spf-in-office-365-to-help-prevent-spoofing.md)voor installatie. <br/> &ensp;&ensp;* DomainKeys Identified Mail (DKIM). <br/> &ensp;&ensp;&ensp;&ensp;- Zie [DKIM gebruiken om uitgaande e-mail te valideren die vanuit uw aangepaste domein is verzonden.](use-dkim-to-validate-outbound-email.md) <br/>&ensp;&ensp;&ensp;&ensp;- Nadat u DKIM hebt geconfigureerd, schakelt u deze in het beveiligingscentrum in.<br/> &ensp;&ensp;* Op domeinen gebaseerde berichtverificatie, rapportage en conformiteit (DMARC). <br/> &ensp;&ensp;&ensp;&ensp;- Voor DMARC-instellingen [gebruik DMARC om e-mail te valideren in Microsoft 365](use-dmarc-to-validate-email.md).|
|

> [!NOTE]
> Voor niet-standaardimplementaties van SPF, hybride implementaties en probleemoplossing: [hoe Microsoft 365 Sender Policy Framework (SPF) gebruikt om spoofing te voorkomen.](how-office-365-uses-spf-to-prevent-spoofing.md)

## <a name="view-dashboards-and-reports-in-the-security-and-compliance-centers"></a>Dashboards en rapporten weergeven in de beveiligings- en compliancecentra

Ga naar deze rapporten en dashboards voor meer informatie over de gezondheid van uw omgeving. De gegevens in deze rapporten worden rijker naarmate uw organisatie Office 365-services gebruikt. Voor nu, vertrouwd zijn met wat je controleren en actie ondernemen op. Zie : Rapporten [in de beveiligings- en compliancecentra van Microsoft 365](../../compliance/reports-in-security-and-compliance.md)voor meer informatie.

|||
|---|---|
|**Dashboard**|**Beschrijving**|
|[Dashboard voor bedreigingsbeheer](security-dashboard.md)|In het gedeelte **Bedreigingsbeheer** van het beveiligingscentrum gebruikt u dit dashboard om bedreigingen te zien die al zijn afgehandeld en als een handig hulpmiddel om aan zakelijke besluitvormers te rapporteren over wat mogelijkheden voor bedreigingsonderzoek en -reactie al hebben gedaan om uw bedrijf te beveiligen.|
|[Bedreigingsverkenner (of realtime detecties)](threat-explorer.md)|Dit is ook in de **Threat management** sectie van het beveiligingscentrum. Als u een aanval op uw tenant onderzoekt of ondervindt, gebruikt u Explorer (of realtime detecties) om bedreigingen te analyseren. Explorer (en het real-time detectierapport) toont u het aantal aanvallen in de loop van de tijd en u deze gegevens analyseren op bedreigingsfamilies, infrastructuur voor aanvallers en meer. U ook verdachte e-mails markeren voor de lijst Incidenten.|
|Rapporten — Dashboard|Bekijk in het gedeelte **Rapporten** van het beveiligingscentrum controlerapporten voor uw SharePoint Online- en Exchange Online-organisaties. U hebt ook toegang tot aanmeldingsrapporten van Azure Active Directory (Azure AD), gebruikersactiviteitsrapporten en het Azure AD-controlelogboek vanaf de pagina **Rapporten weergeven.**|
|

![Dashboard van het beveiligingscentrum](../../media/870ab776-36d2-49c7-b615-93b2bc42fce5.png)

## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>Aanvullende exchange online-tenantbrede instellingen configureren

Veel van de besturingselementen voor beveiliging en beveiliging in het Exchange-beheercentrum zijn ook opgenomen in het beveiligingscentrum. U hoeft deze niet op beide plaatsen te configureren. Hier zijn een paar extra instellingen die worden aanbevolen.

||||
|---|---|---|
|**Gebied**|**Bevat een standaardbeleid**|**Aanbeveling**|
|**E-mailstroom** (regels voor e-mailstroom, ook wel transportregels genoemd)|Nee|Voeg een e-mailstroomregel toe om te helpen beschermen tegen ransomware door uitvoerbare bestandstypen en Office-bestandstypen die macro's bevatten te blokkeren. Zie [Regels voor e-mailstroom gebruiken om berichtbijlagen in Exchange Online te inspecteren](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)voor meer informatie. <br/><br/> Bekijk deze aanvullende onderwerpen: <br/>* [Beschermen tegen ransomware](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware)<br/>* [Bescherming tegen malware en ransomware in Office 365](https://docs.microsoft.com/Office365/Enterprise/office-365-malware-and-ransomware-protection) <br/>* [Herstellen van een ransomware-aanval in Office 365](recover-from-ransomware.md) <br/><br/> Maak een e-mailstroomregel om automatische doorschakeling van e-mail naar externe domeinen te voorkomen. Zie Externe [doorschakelregels voor extern doorsturen van clients met veilige score](https://docs.microsoft.com/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score)voor meer informatie. <br/><br/> Meer informatie: [Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)|
|**Moderne verificatie inschakelen**|Nee|Moderne verificatie is een voorwaarde voor het gebruik van multi-factor authenticatie (MFA). MFA wordt aanbevolen voor het beveiligen van toegang tot cloudbronnen, waaronder e-mail. <br/><br/> Bekijk deze onderwerpen: <br/>* [Moderne verificatie in Exchange Online in- of uitschakelen](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) <br/>* [Skype voor Bedrijven Online: uw tenant inschakelen voor moderne verificatie](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) <br/><br/> Moderne verificatie is standaard ingeschakeld voor Office 2016-clients, SharePoint Online en OneDrive voor Bedrijven. <br/><br/> Meer informatie: [hoe moderne verificatie werkt voor Office 2013- en Office 2016-client-apps](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)|
|

## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>Beleid voor delen voor het delen van huurders configureren in het SharePoint-beheercentrum

Microsoft-aanbevelingen voor het configureren van SharePoint-teamsites op een hoger beschermingsniveau, te beginnen met basislijnbeveiliging. Zie Sites en bestanden beveiligen voor [SharePoint Online](https://docs.microsoft.com/microsoft-365-enterprise/secure-sharepoint-online-sites-and-files) voor meer informatie

SharePoint-teamsites die zijn geconfigureerd op basislijnniveau, maken het delen van bestanden met externe gebruikers mogelijk via anonieme toegangskoppelingen. Deze aanpak wordt aanbevolen in plaats van het verzenden van bestanden in e-mail.

Als u de doelen voor basislijnbeveiliging wilt ondersteunen, configureert u tenantbreedingsbeleid zoals hier wordt aanbevolen. Instellingen voor delen voor afzonderlijke sites kunnen restrictiever zijn dan dit tenantbrede beleid, maar niet toleranter.

||||
|---|---|---|
|**Gebied**|**Bevat een standaardbeleid**|**Aanbeveling**|
|**Delen** (SharePoint Online en OneDrive voor Bedrijven)|Ja|Extern delen is standaard ingeschakeld. Deze instellingen worden aanbevolen: <br/>* Delen toestaan aan geverifieerde externe gebruikers en anonieme toegangskoppelingen gebruiken (standaardinstelling). <br/> * Anonieme toegang links verlopen in deze vele dagen. Voer indien gewenst een getal in, bijvoorbeeld 30 dagen. <br/>* Standaardkoppelingstype — selecteer Intern (alleen personen in de organisatie). Gebruikers die anoniem willen delen, moeten deze optie kiezen in het deelmenu. <br/><br/> Meer informatie: [Overzicht extern delen](https://docs.microsoft.com/sharepoint/external-sharing-overview)|
|

SharePoint-beheercentrum en Het Beheercentrum van OneDrive voor Bedrijven bevatten dezelfde instellingen. De instellingen in beide beheerderscentrum zijn op beide van toepassing.

## <a name="configure-settings-in-azure-active-directory"></a>Instellingen configureren in Azure Active Directory

Zorg ervoor dat u deze twee gebieden in Azure Active Directory bezoekt om de installatie voor tenantbrede instellingen voor veiligere omgevingen te voltooien.

### <a name="configure-named-locations-under-conditional-access"></a>Benoemde locaties configureren (onder voorwaardelijke toegang)

Als uw organisatie kantoren met beveiligde netwerktoegang bevat, voegt u de vertrouwde IP-adresbereiken toe aan Azure Active Directory als benoemde locaties. Deze functie helpt het aantal gerapporteerde fout-positieven voor aanmeldingsrisicogebeurtenissen te verminderen.

Zie: [Benoemde locaties in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-named-locations)

### <a name="block-apps-that-dont-support-modern-authentication"></a>Apps blokkeren die geen moderne verificatie ondersteunen

Voor meervoudige verificatie zijn apps vereist die moderne verificatie ondersteunen. Apps die geen moderne verificatie ondersteunen, kunnen niet worden geblokkeerd met behulp van regels voor voorwaardelijke toegang.

Voor veilige omgevingen moet u verificatie uitschakelen voor apps die geen moderne verificatie ondersteunen. U dit doen in Azure Active Directory met een besturingselement dat binnenkort beschikbaar is.

Gebruik in de tussentijd een van de volgende methoden om dit voor SharePoint Online en OneDrive voor Bedrijven te bereiken:

- Gebruik PowerShell, zie [Apps blokkeren die geen moderne verificatie gebruiken (ADAL).](https://docs.microsoft.com/mem/intune/protect/app-modern-authentication-block)

- Configureer dit in het SharePoint-beheercentrum op de pagina 'Apparaattoegang' - 'Beheer de toegang van apps die geen moderne verificatie gebruiken'. Kies Blokkeren.

## <a name="get-started-with-cloud-app-security-or-office-365-cloud-app-security"></a>Aan de slag met Cloud App Security of Beveiliging van Office 365 Cloud App

Gebruik Office 365 Cloud App Security om risico's te evalueren, verdachte activiteiten te waarschuwen en automatisch actie te ondernemen. Vereist Office 365 E5-abonnement.

Of gebruik Microsoft Cloud App Security om meer zichtbaarheid te krijgen, zelfs nadat toegang is verleend, uitgebreide besturingselementen en verbeterde beveiliging voor al uw cloudtoepassingen, waaronder Office 365.

Omdat deze oplossing het EMS E5-plan aanbeveelt, raden we u aan om te beginnen met Cloud App Security, zodat u dit gebruiken met andere SaaS-toepassingen in uw omgeving. Begin met standaardbeleid en -instellingen.

Meer informatie:

- [Cloud App Security implementeren](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)

- [Meer informatie over Microsoft Cloud App Security](https://www.microsoft.com/cloud-platform/cloud-app-security)

- [Wat is Cloud App Security?](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)

![Cloud App Security-dashboard](../../media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)

## <a name="additional-resources"></a>Overige informatiebronnen

Deze artikelen en handleidingen bieden aanvullende voorgeschreven informatie voor het beveiligen van uw Microsoft 365-omgeving:

- [Microsoft-beveiligingsrichtlijnen voor politieke campagnes, non-profitorganisaties en andere flexibele organisaties](https://docs.microsoft.com/microsoft-365/security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o) (u deze aanbevelingen gebruiken in elke omgeving, met name cloudomgevingen)

- [Aanbevolen beveiligingsbeleid en -configuraties voor identiteiten en apparaten](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-365-policies-configurations) (deze aanbevelingen omvatten hulp voor AD FS-omgevingen)
