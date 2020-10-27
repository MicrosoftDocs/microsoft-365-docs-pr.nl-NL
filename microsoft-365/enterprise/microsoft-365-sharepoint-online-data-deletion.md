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
ms.openlocfilehash: 888ee807e6cd4ddc435c1df86a63502a617d6cb8
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769040"
---
# <a name="sharepoint-online-data-deletion-in-microsoft-365"></a>SharePoint Online-gegevensverwijdering in Microsoft 365

In SharePoint Online worden objecten als een abstracte code in toepassingsdatabases opgeslagen. Wanneer een gebruiker een bestand uploadt naar SharePoint Online, wordt dit bestand ontleed en vertaald in meerdere tabellen voor meerdere databases. In SharePoint Online wordt alle inhoud die een klant uploadt, verbroken in segmenten, versleuteld (met een of meer AES 256-bits) en verspreid over het datacenter. 

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
