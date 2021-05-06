---
title: Serviceversleuteling
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.date: 10/3/2019
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Overzicht: Inzicht in gegevensweerbaarheid in Microsoft Office 365.'
ms.openlocfilehash: 89f3fbcc90cee0ad822156014ee4ac9e04fe3371
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/30/2021
ms.locfileid: "52161680"
---
# <a name="service-encryption"></a>Serviceversleuteling

Naast het gebruik van volumeversleuteling, Exchange Online, Microsoft Teams, SharePoint Online en OneDrive voor Bedrijven ook serviceversleuteling gebruiken om klantgegevens te versleutelen. Serviceversleuteling biedt twee belangrijke beheeropties:

## <a name="microsoft-managed-keys"></a>Door Microsoft beheerde sleutels
Microsoft beheert alle cryptografische sleutels, inclusief de hoofdsleutels voor serviceversleuteling. Deze optie is momenteel standaard ingeschakeld voor Exchange Online, SharePoint Online, OneDrive voor Bedrijven. Door Microsoft beheerde sleutels bieden standaardserviceversleuteling, tenzij u besluit om aan boord te gaan met de klantsleutel. Als u op een later tijdstip besluit de klantsleutel niet meer te gebruiken zonder het pad voor gegevensre purge te volgen, blijven uw gegevens versleuteld met behulp van de door Microsoft beheerde sleutels. Uw gegevens worden altijd minimaal op dit standaardniveau versleuteld. 

## <a name="customer-key"></a>Klantsleutel
U levert hoofdsleutels die worden gebruikt met serviceversleuteling en u beheert deze sleutels met Azure Key Vault. Microsoft beheert alle andere sleutels. Deze optie heet Klantsleutel en is momenteel beschikbaar voor Exchange Online, SharePoint Online en OneDrive voor Bedrijven. (Eerder geavanceerde versleuteling genoemd met BYOK. Zie [Meer transparantie en controle voor Office 365 klanten](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) voor de oorspronkelijke aankondiging.)

Serviceversleuteling biedt meerdere voordelen:

- Biedt een extra beveiligingslaag boven aan BitLocker.

- Biedt scheiding van Windows besturingssysteembeheerders van toegang tot toepassingsgegevens die zijn opgeslagen of verwerkt door het besturingssysteem.

- Bevat een optie Klantsleutel waarmee multi-tenantservices per tenant sleutelbeheer kunnen bieden.

- Verbetert de mogelijkheid om te Microsoft 365 voldoen aan de vereisten van klanten die specifieke compliancevereisten hebben met betrekking tot versleuteling.

Met klantsleutel kunt u uw eigen cryptografische sleutels genereren met een on-premises Hardware Service Module (HSM) of Azure Key Vault (AKV). Ongeacht hoe u de sleutel genereert, gebruikt u AKV om de cryptografische sleutels te beheren die door Office 365. Wanneer uw sleutels zijn opgeslagen in AKV, kunnen ze worden gebruikt als de hoofdmap van een van de sleutelhangers waarmee uw postvakgegevens of bestanden worden versleuteld.

Een ander voordeel van Customer Key is de controle die u hebt over de mogelijkheid van Microsoft om uw gegevens te verwerken. Als u gegevens wilt verwijderen uit Office 365, bijvoorbeeld als u de service bij Microsoft wilt beëindigen of een deel van uw gegevens wilt verwijderen dat is opgeslagen in de cloud, kunt u dit doen en Klantcode gebruiken als een technisch beheer. Als u gegevens verwijdert, kan niemand, inclusief Microsoft, de gegevens openen of verwerken. Klantcode is bovendien een aanvulling op het Klantenvergrendelingsvak dat u gebruikt om de toegang tot uw gegevens door Microsoft-personeel te bepalen.

Zie deze artikelen voor informatie over het instellen van klantcode voor Microsoft 365 voor Exchange Online, Microsoft Teams, SharePoint Online, inclusief teamsites en OneDrive voor Bedrijven:

- [Serviceversleuteling met klantsleutel](customer-key-overview.md)

- [Klantsleutel instellen](customer-key-set-up.md)

- [Klantcode beheren](customer-key-manage.md)

- [Een klantsleutel of een beschikbaarheidssleutel rollen of draaien](customer-key-availability-key-roll.md)

- [De beschikbaarheidscode begrijpen](customer-key-availability-key-understand.md)
