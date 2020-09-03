---
title: Gegevensretentie, verwijdering en vernietiging in Microsoft 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Een overzicht van Microsoft-beleidsregels voor Microsoft 365 met betrekking tot gegevens behoud, verwijdering en vernietiging.
ms.openlocfilehash: 9708ed618528ce0ad5ef8656a85ffd4311395deb
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/02/2020
ms.locfileid: "47331894"
---
# <a name="data-retention-deletion-and-destruction-in-microsoft-365"></a>Gegevensretentie, verwijdering en vernietiging in Microsoft 365

Microsoft heeft een standaardbeleid voor het verwerken van gegevens voor Microsoft 365 waarmee wordt opgegeven hoe lang klantgegevens na verwijdering bewaard blijven. In het algemeen zijn er twee scenario's waarin klantgegevens worden verwijderd:

- **Active**delete: de Tenant heeft een actief abonnement en een gebruiker of beheerder verwijdert gegevens en beheerders verwijdert een gebruiker.
- **Passieve verwijdering**: het Tenant abonnement eindigt op.

## <a name="data-retention"></a>Gegevensretentie

Voor elk van deze verwijderings scenario's bevat de volgende tabel de maximale bewaarperiode voor gegevens, op gegevenscategorie en classificatie:

| Gegevenscategorie | Gegevensclassificatie | Beschrijving | Voorbeelden | Bewaarperiode |
|-----------------|-----------------|-----------------|----------------------------------|-------------------------------|
| Klantgegevens | Klant inhoud| Inhoud rechtstreeks verstrekt/gemaakt door beheerders en gebruikers <br><br> Omvat alle tekst, geluiden, video, afbeeldingsbestanden en software die is gemaakt en opgeslagen in Microsoft datacenters wanneer u de services gebruikt in Microsoft 365 | Voorbeelden van de meest gebruikte Microsoft 365-toepassingen waarmee gebruikersgegevens kunnen maken zoals Word, Excel, PowerPoint, Outlook en OneNote <br><br> Klant inhoud omvat ook klantspecifieke geheimen (wachtwoorden, certificaten, versleutelingssleutels, opslag sleutels) | **Scenario voor actieve verwijdering:** hooguit 30 dagen <br><br> **Scenario voor passieve verwijdering:** 180 dagen |
| Klantgegevens | Identificeerbare informatie voor eindgebruikers (EUII) | Gegevens die de gebruiker van een Microsoft-service identificeren of kunnen gebruiken. EUII bevat geen klant inhoud | Gebruikersnaam of weergavenaam (Domein\gebruikersnaam) <br><br> User Principal Name (name@domain) <br><br>  Gebruikersspecifieke IP-adressen | **Scenario voor actieve verwijdering:** hooguit 180 dagen (alleen een tenantbeheerder actie) <br><br> **Scenario voor passieve verwijdering:** 180 dagen |
| Persoonlijke gegevens <br> (gegevens die niet in de klantgegevens zijn opgenomen) | Door eindgebruikers bepseudoniemde Id's (EUPI) | Een id die is gemaakt door Microsoft gebonden aan de gebruiker van een Microsoft-service. Wanneer deze worden gecombineerd met andere informatie, zoals een toewijzingstabel, identificeert EUPI de eindgebruiker <br><br> EUPI bevat geen gegevens die zijn geüpload of gemaakt door de klant | Gebruikers-GUID'S, PUIDs of Sid's <br><br> Sessie-Id's | **Scenario voor actieve verwijdering:** hooguit 30 dagen <br><br> **Scenario voor passieve verwijdering:** 180 dagen |

## <a name="subscription-retention"></a>Abonnementen bewaren

In de periode van een actief abonnement kan een abonnee klantgegevens openen, ophalen of verwijderen die zijn opgeslagen in Microsoft 365. Als een betaald abonnement eindigt of wordt beëindigd, behoudt Microsoft de klantgegevens die zijn opgeslagen in Microsoft 365 in een account met beperkte functionaliteit gedurende 90 dagen zodat de abonnee de gegevens kan extraheren. Wanneer de bewaarperiode voor 90 dagen eindigt, wordt het account door Microsoft uitgeschakeld en worden de klantgegevens verwijderd. Maximaal 180 dagen na verloop of beëindiging van een abonnement op Microsoft 365 schakelt het account uit en verwijdert alle klantgegevens van het account. Wanneer de maximale bewaarperiode voor alle gegevens is verstreken, worden de gegevens weergegeven als commercieel niet-herstelbaar.

Als u een gratis proefperiode hebt, wordt uw account gedurende 30 dagen in de meeste landen en regio's naar een respijt status verplaatst. Tijdens deze respijtperiode kunt u Microsoft 365 aanschaffen. Als u Microsoft 365 niet wilt kopen, kunt u uw proefabonnement annuleren of de respijtperiode laten verlopen, waarna de gegevens van uw proefaccount worden verwijderd.

## <a name="expedited-deletion"></a>Snelle verwijdering

Voor elk abonnement kan een abonnee contact opnemen met Microsoft ondersteuning en vragen om de inrichting van het abonnement. Bij dit proces worden alle gebruikersgegevens drie dagen nadat de beheerder de vergrendelings code van Microsoft heeft ingevoerd, verwijderd. Dit omvat gegevens in SharePoint Online en Exchange Online, onder wachtstand of opgeslagen in inactieve postvakken.

Zie [uw abonnement opzeggen](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/cancel-your-subscription)voor meer informatie over het versnellen van de inrichting.

## <a name="related-links"></a>Verwante koppelingen

- [Gegevensvernietiging](microsoft-365-data-destruction.md)
- [Immutability in Office 365](microsoft-365-data-immutability.md)
- [Exchange online gegevensverwijdering](microsoft-365-exchange-online-data-deletion.md)
- [SharePoint online gegevensverwijdering](microsoft-365-sharepoint-online-data-deletion.md)
- [Skype voor bedrijven gegevensverwijdering](microsoft-365-skype-data-deletion.md)
