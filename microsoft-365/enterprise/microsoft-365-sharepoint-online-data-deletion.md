---
title: Microsoft 365 SharePoint Online gegevens verwijderen
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
- SPO_Content
f1.keywords:
- NOCSH
description: Meer informatie over hoe u de verwijdering van gegevens kunt gebruiken in SharePoint Online, bijvoorbeeld waar verwijderde inhoud is opgeslagen en voor hoelang.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e914e84f3679483e5030b7f2a06913cb052e5411
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332722"
---
# <a name="sharepoint-online-data-deletion-in-microsoft-365"></a>SharePoint Online-gegevensverwijdering in Microsoft 365

In SharePoint Online worden objecten als een abstracte code in toepassingsdatabases opgeslagen. Wanneer een gebruiker een bestand uploadt naar SharePoint Online, wordt dit bestand ontleed en vertaald in meerdere tabellen voor meerdere databases. In SharePoint Online wordt alle inhoud die een klant uploadt, verbroken in segmenten, versleuteld (mogelijk met meerdere AES 256-bits) en over het datacenter gedistribueerd. Zie [versleuteling in de Microsoft-Cloud](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-in-the-microsoft-cloud-overview)voor specifieke informatie over het proces van segmenteren en versleutelen. 

In SharePoint Online worden items gedurende 93 dagen bewaard vanaf het moment dat u ze verwijdert van de oorspronkelijke locatie. De persoon blijft in de Prullenbak van de site het hele tijdstip verlaten, tenzij iemand deze verwijdert. In dat geval gaan de items naar de Prullenbak van de siteverzameling, waar ze de rest van de 93 dagen blijven. Zie [items in de Prullenbak van een SharePoint-site terugzetten](https://support.office.com/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
) en [Verwijderde items terugzetten uit de Prullenbak voor siteverzamelingen](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b)voor informatie over het herstellen van verwijderde items. De bewaartijd voor de prullenbak kan niet worden geconfigureerd in SharePoint Online.

Wanneer u een siteverzameling verwijdert, verwijdert u ook de hiërarchie van sites in de verzameling en de inhoud ervan.

- Documenten en documentbibliotheken
- Lijsten en lijstgegevens
- Configuratie-instellingen van site
- Rollen en beveiligingsgegevens die zijn gerelateerd aan de site of de subsites
- Subsites van de website op het hoogste niveau, de bijbehorende inhoud en gebruikersgegevens

Als u per ongeluk een siteverzameling verwijdert, kan deze door een globale beheerder of SharePoint-beheerder worden hersteld via het SharePoint-Beheercentrum.

Verwijderde siteverzamelingen worden gedurende 93 dagen bewaard. Na 93 dagen worden sites en al hun inhoud en instellingen definitief verwijderd, inclusief lijsten, bibliotheken, pagina's en subsites.

Permanent verwijderen wordt uitgevoerd wanneer een gebruiker de verwijderde items uit de Prullenbak van de siteverzameling verwijdert, wanneer de bewaarperiode en de back-up van de back-upperioden zijn verlopen of wanneer een beheerder de siteverzameling permanent verwijdert met behulp van de [Remove-SPODeletedSite-cmdlet](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps). Wanneer een gebruiker de inhoud permanent verwijdert (permanent verwijdert of verwijdert) uit SharePoint Online, worden alle versleutelingssleutels voor de verwijderde segmenten ook verwijderd. De blokken op de schijven die eerder de verwijderde segmenten hebben opgeslagen, zijn gemarkeerd als niet-gebruikt en beschikbaar voor hergebruik.
