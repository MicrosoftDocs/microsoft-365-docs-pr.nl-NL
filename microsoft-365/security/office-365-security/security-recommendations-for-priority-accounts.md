---
title: Beveiligingsaanbevelingen voor prioriteitsaccounts in Microsoft 365, prioriteitsaccounts, prioriteitsaccounts in Office 365 en prioriteitsaccounts in Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-protecthve
description: Beheerders kunnen meer informatie krijgen over het verbeteren van de beveiligingsinstellingen en het gebruik van rapporten, waarschuwingen en onderzoeken voor prioriteitsaccounts in hun Microsoft 365-organisaties.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 814ca47ee48e844e313f7d75640643a0b659c527
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166367"
---
# <a name="security-recommendations-for-priority-accounts-in-microsoft-365"></a>Beveiligingsaanbevelingen voor prioriteitsaccounts in Microsoft 365

Niet alle gebruikersaccounts hebben toegang tot dezelfde bedrijfsgegevens. Sommige accounts hebben toegang tot gevoelige informatie, zoals financiële gegevens, informatie over productontwikkeling, partnertoegang tot kritieke buildsystemen en meer. Als ze worden gehackt, vormen accounts die toegang hebben tot zeer vertrouwelijke informatie een ernstige bedreiging. Dit worden accounts met _prioriteitaccounts noemen._ Prioriteitsaccounts zijn onder andere CEOs, CISOs, CFOS's, infrastructuurbeheerdersaccounts, systeemaccounts maken en meer.

Voor kwaadwillende gebruikers zijn normale phishing-aanvallen die een willekeurig net voor gewone of onbekende gebruikers laten zien, niet efficiënt. Aan de andere kant zijn _phishing-_ of _whaling-aanvallen_ van doelprioriteitsaccounts zeer lonend voor aanvallers. Prioriteitsaccounts vereisen dus sterker dan gewone beveiliging om het gekrom van accounts te voorkomen.

Microsoft 365 en Microsoft Defender voor Office 365 bevatten verschillende belangrijke functies die extra beveiligingslagen bieden voor uw prioriteitsaccounts. In dit artikel worden deze mogelijkheden beschreven en wordt beschreven hoe u deze kunt gebruiken.

![Overzicht van de beveiligingsaanbevelingen in pictogramformulier](../../media/security-recommendations-for-priority-users.png)

****

|Taak|Alle Office 365 Enterprise-abonnementen|Microsoft 365 E3|Microsoft 365 E5|
|---|:---:|:---:|:---:|
|[De aanmeldingsbeveiliging voor prioriteitaccounts verhogen](#increase-sign-in-security-for-priority-accounts)|![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Strikt vooraf ingestelde beveiligingsbeleid gebruiken voor prioriteitsaccounts](#use-strict-preset-security-policies-for-priority-accounts)|![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Gebruikerslabels toepassen op prioriteitaccounts](#apply-user-tags-to-priority-accounts)|||![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Prioriteitsaccounts controleren in waarschuwingen, rapporten en detecties](#monitor-priority-accounts-in-alerts-reports-and-detections)|||![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Gebruikers wegwijs maken](#train-users)|![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|

## <a name="increase-sign-in-security-for-priority-accounts"></a>De aanmeldingsbeveiliging voor prioriteitaccounts verhogen

Voor prioriteitsaccounts is een betere aanmeldingsbeveiliging vereist. U kunt de aanmeldingsbeveiliging verhogen door meervoudige verificatie (MFA) te vereisen en oudere verificatieprotocollen uit te schakelen.

Zie stap [1 voor instructies. Verhoog de aanmeldingsbeveiliging voor externe medewerkers met MFA.](https://docs.microsoft.com/microsoft-365/solutions/empower-people-to-work-remotely-secure-sign-in) Hoewel dit artikel over externe medewerkers gaat, zijn dezelfde concepten van toepassing op belangrijke gebruikers.

**Opmerking:** we raden u ten zeerste aan oudere verificatieprotocollen voor alle prioriteitsgebruikers uit te schakelen, zoals beschreven in het vorige artikel. Als dit niet is vereist voor uw bedrijf, biedt Exchange Online de volgende besturingselementen om het bereik van verouderde verificatieprotocollen te beperken:

- U kunt [verificatiebeleid](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) en regels voor [clienttoegang](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) in Exchange Online gebruiken om basisverificatie en verouderde verificatieprotocollen zoals POP3, IMAP4 en geverifieerde SMTP voor specifieke gebruikers te blokkeren of toe te staan.

- U kunt POP3- en IMAP4-toegang uitschakelen voor afzonderlijke postvakken. U kunt geverifieerde SMTP op organisatieniveau uitschakelen en inschakelen voor specifieke postvakken waarvoor dit nog steeds is vereist. Zie de volgende onderwerpen voor instructies:
  - [POP3- of IMAP4-toegang voor een gebruiker in- of uitschakelen](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)
  - [Geverifieerde SMTP-indiening (SMTP AUTH) voor geverifieerde client in- of uitschakelen](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission)

Het is ook de moeite waard om te weten dat Basic-verificatie op dit moment wordt afgeschaft in Exchange Online for Exchange Web Services (EWS), Exchange ActiveSync, POP3, IMAP4 en externe PowerShell. Zie dit blogbericht voor [meer informatie.](https://developer.microsoft.com/office/blogs/deferred-end-of-support-date-for-basic-authentication-in-exchange-online/)

## <a name="use-strict-preset-security-policies-for-priority-accounts"></a>Strikt vooraf ingestelde beveiligingsbeleid gebruiken voor prioriteitsaccounts

Prioriteitsgebruikers vereisen striktere acties voor de verschillende beveiligingen die beschikbaar zijn in Exchange Online Protection (EOP) en Defender voor Office 365.

Bijvoorbeeld: in plaats van berichten die als spam zijn geclassificeerd, in de map Ongewenste e-mail te plaatsen, moet u dezelfde berichten in quarantaine plaatsen als deze zijn bedoeld voor prioriteitsaccounts.

U kunt deze strikte benadering voor prioriteitsaccounts implementeren door het profiel Strikt in vooraf ingestelde beveiligingsbeleidsregels te gebruiken.

Vooraf ingestelde beveiligingsbeleidsregels zijn een handige en centrale locatie om de aanbevolen instellingen voor strikt beleid toe te passen voor alle beveiligingen in EOP en Defender voor Office 365. Zie Vooraf ingestelde [beveiligingsbeleidsregels in EOP en Microsoft Defender voor Office 365](preset-security-policies.md)voor meer informatie.

Zie Aanbevolen instellingen voor de beveiliging van EOP en Microsoft Defender voor [Office 365](recommended-settings-for-eop-and-office365-atp.md)voor meer informatie over hoe de instellingen voor strikt beleid verschillen van de standaard- en standaardbeleidsinstellingen.

## <a name="apply-user-tags-to-priority-accounts"></a>Gebruikerslabels toepassen op prioriteitaccounts

Met gebruikerstags in Microsoft Defender voor Office 365 Abonnement 2 (als onderdeel van Microsoft 365 E5 of een invoegabonnement) kunt u specifieke gebruikers of groepen gebruikers snel identificeren en classificeren in rapporten en incidentenonderzoek.

**Prioriteitsaccounts** is een type ingebouwde gebruikerstag (ook wel een systeemtag _genoemd)_ die u kunt gebruiken om incidenten en waarschuwingen te identificeren die betrekking hebben op prioriteitaccounts. Zie Prioriteitsaccounts **beheren** en controleren voor meer informatie over [prioriteitsaccounts.](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)

U kunt ook aangepaste tags maken om uw prioriteitsaccounts verder te identificeren en te classificeren. Zie Gebruikerstags [voor meer informatie.](user-tags.md) U kunt **prioriteitsaccounts** (systeemcodes) in dezelfde interface beheren als aangepaste gebruikerstags.

## <a name="monitor-priority-accounts-in-alerts-reports-and-detections"></a>Prioriteitsaccounts controleren in waarschuwingen, rapporten en detecties

Nadat u uw prioriteitsgebruikers hebt beveiligd en gelabeld, kunt u de beschikbare rapporten, waarschuwingen en onderzoeken in EOP en Defender voor Office 365 gebruiken om snel incidenten of detecties te identificeren die betrekking hebben op prioriteitaccounts. De functies die gebruikerslabels ondersteunen, worden in de volgende tabel beschreven.

<br>

****

|Functie|Beschrijving|
|---|---|
|Waarschuwingen|De gebruikerslabels van betrokken gebruikers zijn  zichtbaar en beschikbaar als filters op de pagina Waarschuwingen weergeven in het & Compliancecentrum. Zie Waarschuwingen weergeven [voor meer informatie.](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#viewing-alerts)|
|Bedreigingsverkenner <p> Detecties in realtime|In  Bedreigingsverkenner (Microsoft Defender voor Office 365 Plan 2) of detecties in realtime (Microsoft Defender voor Office 365 Abonnement 1) zijn gebruikerslabels zichtbaar in de weergave E-mailraster en de flyout **E-maildetails.** Gebruikerslabels zijn ook beschikbaar als een filterbare eigenschap. Zie Labels  [in Bedreigingsverkenner](threat-explorer.md#tags-in-threat-explorer)voor meer informatie.|
|Campagneweergaven|Gebruikerslabels zijn een van de vele filterbare eigenschappen in campagneweergaven in Microsoft Defender voor Office 365 Abonnement 2. Zie Campagneweergaven [voor meer informatie.](campaigns.md)|
|Statusrapport bedreigingsbeveiliging|In vrijwel alle weergaven en detailtabellen in **het** statusrapport Risicobeveiliging kunt u de resultaten filteren op **prioriteitaccounts.** Zie het statusrapport risicobeveiliging voor [meer informatie.](view-email-security-reports.md#threat-protection-status-report)|
|E-mailproblemen voor prioriteitsaccountsrapport|Het **rapport E-mailproblemen** voor prioriteitsaccounts in het Exchange-beheercentrum (EAC) bevat informatie over niet-bezorgde en vertraagde berichten voor **prioriteitaccounts.** Zie E-mailproblemen voor het [rapport Prioriteitsaccounts voor meer informatie.](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)|
|

## <a name="train-users"></a>Gebruikers wegwijs maken

Training van gebruikers met prioriteitsaccounts kan die gebruikers en uw team voor beveiligingsbewerkingen veel tijd en frustratie besparen. Slimme gebruikers openen minder snel bijlagen of klikken op koppelingen in twijfelachtige e-mailberichten en ze vermijden dan waarschijnlijk verdachte websites.

Het handboek [Marketingcampagne](https://www.belfercenter.org/CyberPlaybook) van De Harvard School biedt uitstekende richtlijnen voor het creëren van een sterke cultuur van bekendheid met beveiliging binnen uw organisatie, waaronder training voor het identificeren van phishing-aanvallen.

Microsoft 365 biedt de volgende informatiebronnen om gebruikers in uw organisatie op de hoogte te stellen:

<br>

****

|Concept|Resources|Beschrijving|
|---|---|---|
|Microsoft 365|[Aanpasbare leerroutes](https://docs.microsoft.com/office365/customlearning/)|Deze bronnen kunnen u helpen bij het organiseren van trainingen voor gebruikers in uw organisatie.|
|Microsoft 365-beveiliging|[Leermodule: Uw organisatie beveiligen met ingebouwde, intelligente beveiliging van Microsoft 365](https://docs.microsoft.com/learn/modules/security-with-microsoft-365)|Met deze module kunt u beschrijven hoe Microsoft 365-beveiligingsfuncties samenwerken en de voordelen van deze beveiligingsfuncties duidelijk maken.|
|Meervoudige verificatie|[Verificatie in twee stappen: Wat is de extra verificatiepagina?](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time)|Dit artikel helpt eindgebruikers te begrijpen wat meervoudige verificatie is en waarom deze in uw organisatie wordt gebruikt.|
|Training voor de aanval van de aanval|[Aan de slag met aanvalssimulatietraining](attack-simulation-training-get-started.md)|Met training voor de aanval van een aanval in Microsoft Defender voor Office 365 Plan 2 kan een beheerder gesimuleerde phishing-aanvallen configureren, starten en volgen tegen specifieke groepen gebruikers.|

Daarnaast raadt Microsoft aan dat gebruikers de acties uitvoeren die in dit artikel worden beschreven: Bescherm uw account en apparaten [tegen hackers en malware.](https://support.microsoft.com/office/066d6216-a56b-4f90-9af3-b3a1e9a327d6) Dit zijn onder andere de volgende acties:

- Sterke wachtwoorden gebruiken
- Apparaten beveiligen
- Beveiligingsfuncties inschakelen op Windows 10- en Mac-pc's (voor niet-beherende apparaten)

## <a name="see-also"></a>Zie ook

[Aankondiging van Prioriteitsaccountbeveiliging in Microsoft Defender voor Office 365](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/announcing-priority-account-protection-in-microsoft-defender-for/ba-p/1696385)
