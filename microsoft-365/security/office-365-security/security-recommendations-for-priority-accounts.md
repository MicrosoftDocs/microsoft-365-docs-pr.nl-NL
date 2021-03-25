---
title: Beveiligingsaanbevelingen voor prioriteitsaccounts in Microsoft 365, prioriteitsaccounts, prioriteitsaccounts in Office 365, prioriteitsaccounts in Microsoft 365
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
description: Beheerders kunnen leren hoe ze de beveiligingsinstellingen kunnen verbeteren en rapporten, waarschuwingen en onderzoeken kunnen gebruiken voor prioriteitsaccounts in hun Microsoft 365-organisaties.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9bb2586c11a22286bde5be01f1e9b3e5e0d981ac
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204679"
---
# <a name="security-recommendations-for-priority-accounts-in-microsoft-365"></a>Beveiligingsaanbevelingen voor prioriteitsaccounts in Microsoft 365

Niet alle gebruikersaccounts hebben toegang tot dezelfde bedrijfsgegevens. Sommige accounts hebben toegang tot gevoelige informatie, zoals financiële gegevens, productontwikkelingsgegevens, partnertoegang tot kritieke buildsystemen en meer. Accounts die toegang hebben tot zeer vertrouwelijke informatie vormen een ernstige bedreiging als ze worden gecompromitteerd. We noemen dit type accounts _prioriteitsaccounts._ Prioriteitsaccounts omvatten (maar zijn niet beperkt tot) CEO's, CISO's, CFO's, infrastructuurbeheerdersaccounts, systeemaccounts maken en meer.

Voor aanvallers zijn gewone phishingaanvallen die een willekeurig net voor gewone of onbekende gebruikers casten, niet efficiënt. Aan de andere kant zijn _phishing- of_ _whaling-aanvallen_ die gericht zijn op prioriteitsaccounts zeer lonend voor aanvallers. Prioriteitsaccounts hebben dus meer dan gewone beveiliging nodig om accountcompromitteerden te voorkomen.

Microsoft 365 en Microsoft Defender voor Office 365 bevatten verschillende belangrijke functies die extra beveiligingslagen bieden voor uw prioriteitsaccounts. In dit artikel worden deze mogelijkheden beschreven en hoe u deze kunt gebruiken.

![Overzicht van de beveiligingsaanbevelingen in pictogramformulier](../../media/security-recommendations-for-priority-users.png)

****

|Taak|Alle Office 365 Enterprise-abonnementen|Microsoft 365 E3|Microsoft 365 E5|
|---|:---:|:---:|:---:|
|[Aanmeldingsbeveiliging voor prioriteitsaccounts verhogen](#increase-sign-in-security-for-priority-accounts)|![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Strikt vooraf ingesteld beveiligingsbeleid gebruiken voor prioriteitsaccounts](#use-strict-preset-security-policies-for-priority-accounts)|![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Gebruikerslabels toepassen op prioriteitsaccounts](#apply-user-tags-to-priority-accounts)|||![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Prioriteitsaccounts controleren in waarschuwingen, rapporten en detecties](#monitor-priority-accounts-in-alerts-reports-and-detections)|||![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Gebruikers wegwijs maken](#train-users)|![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Inbegrepen](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|

## <a name="increase-sign-in-security-for-priority-accounts"></a>Aanmeldingsbeveiliging voor prioriteitsaccounts verhogen

Prioriteitsaccounts vereisen meer aanmeldingsbeveiliging. U kunt de aanmeldingsbeveiliging verhogen door meervoudige verificatie (MFA) te vereisen en oudere verificatieprotocollen uit te schakelen.

Zie Stap [1 voor instructies. De aanmeldingsbeveiliging voor externe werknemers verhogen met MFA.](../../solutions/empower-people-to-work-remotely-secure-sign-in.md) Hoewel dit artikel over externe werknemers gaat, gelden dezelfde concepten voor gebruikers met prioriteit.

**Opmerking:** We raden u ten zeerste aan oudere verificatieprotocollen voor alle prioriteitsgebruikers uit te schakelen, zoals in het vorige artikel is beschreven. Als u dit niet kunt doen door uw zakelijke vereisten, biedt Exchange Online de volgende besturingselementen om het bereik van oudere verificatieprotocollen te beperken:

- U kunt [verificatiebeleid](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) en [Clienttoegangsregels](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) in Exchange Online gebruiken om basisverificatie- en oudere verificatieprotocollen zoals POP3, IMAP4 en geverifieerde SMTP voor specifieke gebruikers te blokkeren of toe te staan.

- U kunt POP3- en IMAP4-toegang uitschakelen voor afzonderlijke postvakken. U kunt geverifieerde SMTP op organisatieniveau uitschakelen en deze inschakelen voor specifieke postvakken waarvoor dit nog nodig is. Zie de volgende onderwerpen voor instructies:
  - [POP3- of IMAP4-toegang in- of uitschakelen voor een gebruiker](/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)
  - [Geverifieerde SMTP-inzending (SMTP AUTH) in- of uitschakelen](/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission)

Het is ook vermeldenswaard dat basisverificatie wordt afgeschaft in Exchange Online voor Exchange Web Services (EWS), Exchange ActiveSync, POP3, IMAP4 en externe PowerShell. Zie dit blogbericht voor [meer informatie.](https://developer.microsoft.com/office/blogs/deferred-end-of-support-date-for-basic-authentication-in-exchange-online/)

## <a name="use-strict-preset-security-policies-for-priority-accounts"></a>Strikt vooraf ingesteld beveiligingsbeleid gebruiken voor prioriteitsaccounts

Gebruikers met prioriteit vereisen strengere acties voor de verschillende beveiligingen die beschikbaar zijn in Exchange Online Protection (EOP) en Defender voor Office 365.

In plaats van berichten te verzenden die als spam zijn geclassificeerd in de map Ongewenste e-mail, moet u dezelfde berichten in quarantaine plaatsen als ze zijn bedoeld voor prioriteitsaccounts.

U kunt deze strikte benadering voor prioriteitsaccounts implementeren met behulp van het profiel Strikt in vooraf ingestelde beveiligingsbeleidsregels.

Vooraf ingestelde beveiligingsbeleidsregels zijn een handige en centrale locatie om onze aanbevolen strikte beleidsinstellingen toe te passen voor alle beveiligingen in EOP en Defender voor Office 365. Zie Vooraf ingestelde beveiligingsbeleidsregels [in EOP en Microsoft Defender voor Office 365](preset-security-policies.md)voor meer informatie.

Zie Aanbevolen instellingen voor EOP en Microsoft Defender voor [Office 365-beveiliging](recommended-settings-for-eop-and-office365.md)voor meer informatie over hoe de strikte beleidsinstellingen verschillen van de standaard- en standaardbeleidsinstellingen.

## <a name="apply-user-tags-to-priority-accounts"></a>Gebruikerslabels toepassen op prioriteitsaccounts

Gebruikerslabels in Microsoft Defender voor Office 365 Plan 2 (als onderdeel van Microsoft 365 E5 of een invoegabonnement) zijn een manier om specifieke gebruikers of groepen gebruikers snel te identificeren en te classificeren in rapporten en incidenten.

**Prioriteitsaccounts** is een type ingebouwde gebruikerstag (ook wel een _systeemlabel_ genoemd) dat u kunt gebruiken om incidenten en waarschuwingen te identificeren die betrekking hebben op prioriteitsaccounts. Zie Prioriteitsaccounts **beheren** en controleren voor meer informatie over [prioriteitsaccounts.](../../admin/setup/priority-accounts.md)

U kunt ook aangepaste tags maken om uw prioriteitsaccounts verder te identificeren en te classificeren. Zie Gebruikerslabels voor [meer informatie.](user-tags.md) Houd er rekening mee dat u **prioriteitsaccounts** (systeemlabels) kunt beheren in dezelfde interface als aangepaste gebruikerslabels.

## <a name="monitor-priority-accounts-in-alerts-reports-and-detections"></a>Prioriteitsaccounts controleren in waarschuwingen, rapporten en detecties

Nadat u uw prioriteitsgebruikers hebt beveiligd en taggen, kunt u de beschikbare rapporten, waarschuwingen en onderzoeken in EOP en Defender voor Office 365 gebruiken om snel incidenten of detecties te identificeren die betrekking hebben op prioriteitsaccounts. De functies die gebruikerslabels ondersteunen, worden beschreven in de volgende tabel.

<br>

****

|Functie|Beschrijving|
|---|---|
|Waarschuwingen|De gebruikerslabels van getroffen gebruikers zijn zichtbaar en beschikbaar als filters op de **pagina** Waarschuwingen weergeven in het beveiligings- & Compliancecentrum. Zie Waarschuwingen [weergeven voor meer informatie.](../../compliance/alert-policies.md#viewing-alerts)|
|Bedreigingsverkenner <p> Detecties in realtime|In **Threat Explorer** (Microsoft Defender voor Office 365-abonnement 2) of realtimedetecties (Microsoft Defender voor Office 365 Abonnement 1) zijn gebruikerslabels zichtbaar in de weergave E-mailraster en de flyout **E-maildetails.** Gebruikerslabels zijn ook beschikbaar als een filterbare eigenschap. Zie Tags [in Threat Explorer voor meer informatie.](threat-explorer.md#tags-in-threat-explorer)|
|Campagneweergaven|Gebruikerslabels zijn een van de vele filterbare eigenschappen in campagneweergaven in Microsoft Defender voor Office 365 Plan 2. Zie [Campagneweergaven voor meer informatie.](campaigns.md)|
|Statusrapport bedreigingsbeveiliging|In vrijwel alle weergaven en detailtabellen in het statusrapport Bedreigingsbeveiliging **kunt** u de resultaten filteren op **prioriteitsaccounts.** Zie Rapport [bedreigingsbeveiligingsstatus voor](view-email-security-reports.md#threat-protection-status-report)meer informatie.|
|E-mailproblemen voor het rapport Prioriteitsaccounts|Het **rapport E-mailproblemen** voor prioriteitsaccounts in het Exchange-beheercentrum (EAC) bevat informatie over niet-bezorgde en vertraagde berichten voor **prioriteitsaccounts.** Zie E-mailproblemen [voor het rapport Prioriteitsaccounts](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)voor meer informatie.|
|

## <a name="train-users"></a>Gebruikers wegwijs maken

Gebruikers met prioriteitsaccounts trainen kan deze gebruikers en uw beveiligingsteam veel tijd en frustratie besparen. Slimme gebruikers openen minder snel bijlagen of klikken op koppelingen in twijfelachtige e-mailberichten en voorkomen eerder verdachte websites.

De Harvard Kennedy School [Cyberbeveiligingscampagnehandboek](https://www.belfercenter.org/CyberPlaybook) biedt uitstekende richtlijnen voor het tot stand brengen van een sterke cultuur van beveiligingsbewustzijn binnen uw organisatie, inclusief training voor gebruikers om phishingaanvallen te identificeren.

Microsoft 365 bevat de volgende bronnen om gebruikers in uw organisatie te informeren:

<br>

****

|Concept|Resources|Beschrijving|
|---|---|---|
|Microsoft 365|[Aanpasbare leerpaden](/office365/customlearning/)|Deze bronnen kunnen u helpen bij het maken van trainingen voor gebruikers in uw organisatie.|
|Microsoft 365-beveiliging|[Leermodule: Uw organisatie beveiligen met ingebouwde, intelligente beveiliging van Microsoft 365](/learn/modules/security-with-microsoft-365)|Met deze module kunt u beschrijven hoe beveiligingsfuncties van Microsoft 365 samenwerken en de voordelen van deze beveiligingsfuncties duidelijk maken.|
|Meervoudige verificatie|[Verificatie in twee stappen: Wat is de extra verificatiepagina?](/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time)|In dit artikel kunnen eindgebruikers begrijpen wat meervoudige verificatie is en waarom het wordt gebruikt in uw organisatie.|
|Training voor aanvalssimulatie|[Aan de slag met aanvalssimulatietraining](attack-simulation-training-get-started.md)|Met training voor aanvalssimulatie in Microsoft Defender voor Office 365 Plan 2 kan de beheerder gesimuleerde phishingaanvallen configureren, starten en bijhouden tegen specifieke groepen gebruikers.|

Daarnaast raadt Microsoft aan dat gebruikers de acties uitvoeren die in dit artikel worden beschreven: Bescherm uw account en [apparaten tegen hackers en malware.](https://support.microsoft.com/office/066d6216-a56b-4f90-9af3-b3a1e9a327d6) Deze acties omvatten:

- Sterke wachtwoorden gebruiken
- Apparaten beveiligen
- Beveiligingsfuncties inschakelen op Windows 10- en Mac-pc's (voor niet-verantwoordelijke apparaten)

## <a name="see-also"></a>Zie ook

[Aankondiging van Prioriteitsaccountbeveiliging in Microsoft Defender voor Office 365](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/announcing-priority-account-protection-in-microsoft-defender-for/ba-p/1696385)