---
title: Meer informatie over het Waarschuwingen-dashboard voor preventie van gegevensverlies
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Meer informatie over waarschuwingen voor preventie van gegevensverlies en het dashboard waarschuwingen.
ms.openlocfilehash: b6fd698e535e006149f6ce3a2a5bc57d0c92c7e2
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51760734"
---
# <a name="learn-about-the-data-loss-prevention-alerts-dashboard"></a>Meer informatie over het Waarschuwingen-dashboard voor preventie van gegevensverlies

Wanneer de criteria in een DLP-beleid (Data Loss Prevention) overeenkomen met de acties die een gebruiker op een gevoelig item ondernomen, kan het beleid een waarschuwing genereren. Dit kan leiden tot een groot aantal waarschuwingen. DLP-waarschuwingen worden verzameld in het dashboard waarschuwingen. Het waarschuwingendashboard biedt u één plek om een uitgebreid onderzoek uit te voeren naar alle details met betrekking tot de beleidsmatch.  

<!-- [Microsoft 365 compliance center](https://compliance.microsoft.com/)-->

## <a name="workloads"></a>Werkbelastingen

Het [DLP-waarschuwingsbeheerdashboard](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts), in het [Microsoft 365-compliancecentrum](https://compliance.microsoft.com/), bevat waarschuwingen voor DLP-beleid voor deze werkbelastingen:

- Exchange
- SharePoint
- OneDrive
- Teams
- Windows 10-apparaten 

> [!TIP]
> Klanten die [Endpoint DLP gebruiken](endpoint-dlp-learn-about.md) die in aanmerking komen voor [Teams DLP,](dlp-microsoft-teams.md) zien hun waarschuwingen voor DLP-eindpuntbeleid en Teams DLP-beleidswaarschuwingen in het DLP-waarschuwingsbeheerdashboard.

## <a name="single-alert-and-aggregate-alert"></a>Eén waarschuwings- en statistische waarschuwing

Er zijn twee typen waarschuwingen die kunnen worden geconfigureerd in DLP-beleid.

Waarschuwingen voor een enkele gebeurtenis worden meestal gebruikt in beleidsregels die controleren op zeer gevoelige gebeurtenissen die zich voordoen in een laag volume, zoals één **e-mailbericht** met tien of meer klanttegoednummers die buiten uw organisatie worden verzonden.

**Waarschuwingen voor aggregaatgebeurtenissen** worden meestal gebruikt in beleidsregels die controleren op gebeurtenissen die zich gedurende een bepaalde periode voordoen in een hoger volume. Een statistische waarschuwing kan bijvoorbeeld worden geactiveerd wanneer 10 afzonderlijke e-mailberichten met elk één klanttegoedkaartnummer meer dan 48 uur buiten uw organisatie worden verzonden.

## <a name="types-of-events"></a>Typen gebeurtenissen

Hier zijn enkele gebeurtenissen die zijn gekoppeld aan een waarschuwing. In de gebruikersinterface kunt u een bepaalde gebeurtenis kiezen om de details ervan weer te geven. 

### <a name="event-details"></a>Gebeurtenisdetails

|Eigenschapsnaam  |Beschrijving  |Gebeurtenistypen  |
|---------|---------|---------|
|ID |unieke id die is gekoppeld aan de gebeurtenis |alle gebeurtenissen |
|Locatie |werkbelasting waarbij de gebeurtenis is gedetecteerd|alle gebeurtenissen |
|tijd van activiteit     |tijd van de gebruikersactiviteit die voldoet aan de criteria van het DLP-beleid |

### <a name="impacted-entities"></a>Beïnvloede entiteiten

|Eigenschapsnaam |Beschrijving| Gebeurtenistypen|
|---------|---------|---------|
|gebruiker | gebruiker die de actie heeft ondernomen die de beleidsmatch heeft veroorzaakt | alle gebeurtenissen|
|hostnaam | hostnaam van de computer waarop de DLP-beleidsmatch heeft plaatsgevonden | apparaatgebeurtenissen|
|IP-adres | IP-adres van de computer waarop de DLP-beleidsmatch heeft plaatsgevonden | apparaatgebeurtenissen|
|sha1 |SHA-1 hash van het bestand | apparaatgebeurtenissen|
|sha256 | SHA-256 hash van het bestand | apparaatgebeurtenissen|
|MDATP-apparaat-id | endpoint-apparaat MDATP-id|
|bestandsgrootte | grootte van het bestand| SharePoint-, OneDrive- en apparaatgebeurtenissen|
|bestandspad | het absolute pad van het item dat betrokken is bij het DLP-beleid | Gebeurtenissen in SharePoint, OneDrive en apparaten|
|e-mailontvangers |als een e-mailbericht het gevoelige item was dat overeen kwam met het DLP-beleid, bevat dit veld de geadresseerden van die e-mail| Exchange-gebeurtenissen|
|onderwerp e-mail |onderwerp van het e-mailbericht dat overeen komt met het DLP-beleid |Exchange-gebeurtenissen|
|e-mailbijlagen | namen van de bijlagen in de e-mail die overeenkomen met het DLP-beleid| Exchange-gebeurtenissen|
|site-eigenaar |naam van de site-eigenaar| SharePoint- en OneDrive-gebeurtenissen|
|site-URL |vol met de URL van de SharePoint- of OneDrive-site waar de DLP-beleidsmatch plaatsvond |SharePoint- en OneDrive-gebeurtenissen|
|bestand gemaakt |tijd van het maken van het bestand dat overeenkomen met het DLP-beleid |SharePoint- en OneDrive-gebeurtenissen|
|bestand dat het laatst is gewijzigd | de laatste keer dat het bestand dat overeen kwam met het DLP-beleid is gewijzigd | SharePoint- en OneDrive-gebeurtenissen|
|bestandsgrootte | grootte van het bestand dat overeenkomen met het DLP-beleid |SharePoint- en OneDrive-gebeurtenissen|
|bestandseigenaar |eigenaar van het bestand dat is afgestemd op het DLP-beleid |SharePoint- en OneDrive-gebeurtenissen|  

### <a name="policy-details"></a>Beleidsdetails

|Eigenschapsnaam |Beschrijving |Gebeurtenistypen |
|---------|---------|---------|
|DLP-beleid gematched |naam van het overeenkomende DLP-beleid |alle gebeurtenissen|
|regel die is afgestemd |naam van de overeenkomende DLP-beleidsregel |alle gebeurtenissen|
|gevoelige informatietypen (SIT) gedetecteerd|SIT's die zijn gedetecteerd als onderdeel van het DLP-beleid |alle gebeurtenissen|
|acties uitgevoerd |acties die zijn ondernomen waardoor het DLP-beleid overeen kwam| alle gebeurtenissen|
|actie schenden | actie op het eindpuntapparaat dat de DLP-waarschuwing heeft verhoogd| apparaatgebeurtenissen | 
|beleid voor gebruikers overroeden |heeft de gebruiker het beleid overschrijven via een beleidstip | alle gebeurtenissen|
|uitvulling overschrijven gebruiken |de tekst van de reden die door de gebruiker is opgegeven voor de overschrijven | alle gebeurtenissen|   

## <a name="see-also"></a>Zie ook

- [Aan de slag met het waarschuwingsdashboard voor de preventie van gegevensverlies](dlp-alerts-dashboard-get-started.md)
- [Waar moet ik beginnen met preventie van gegevensverlies](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention)