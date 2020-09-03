---
title: Microsoft 365 data Immutability
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
description: Meer informatie over hoe Microsoft 365 gegevens bewaart in het herstelbare formulier om reglementaire compliance, interne governance-vereisten en geschillen Risico's te behouden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ce3b3f0f5036ab76be714747d7e95fe86139dd75
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/02/2020
ms.locfileid: "47331918"
---
# <a name="immutability-in-microsoft-365"></a>Immutability in Microsoft 365

Compliance Compliance, interne governance-vereisten of geschillen Risico's vereisen organisaties dat organisaties e-mail en gekoppelde gegevens in een detectie formulier moeten bewaren. Alle gegevens in het systeem moeten kunnen worden gevonden en geen ervan kan worden verwijderd of gewijzigd. De industrie-standaardperiode voor dit is ' immutability '.

Traditionele methoden voor immutability worden meestal bewerkt door e-mailberichten te verplaatsen naar een andere opslaglocatie met het kenmerk alleen-lezen. Hoewel deze systemen betrekking hebben op het behouden van Postvak items voor ontdekking, vaak beïnvloeden ze de gebruikerservaring door geconserveerde items uit de aangepaste dagelijkse werkstroom te verwijderen. Voor IT-professionals is voor deze immutability-aanpak de implementatie en voortdurende onderhoud van een afzonderlijke server en opslaginfrastructuur vereist. Detectie wordt uitgevoerd met hulpprogramma's buiten het e-mailsysteem en bevat bijbehorende implementatie-en onderhoudskosten.

Met functies voor bewaarbeleid en behoud van de beleidsregels voor archivering in Microsoft 365 en de bijbehorende services kunt u veel klassen van inkomende, interne en uitgaande gegevens behouden en bewaren. Dit omvat:

- Inkomende en uitgaande e-mail communicatie
- Boeken en records in een e-mailbericht of in gedeelde online documenten
- Vergaderverzoeken
- Verzenden
- Chatberichten
- Documenten gedeeld tijdens onlinevergaderingen
- Voicemails

Daarnaast heeft Microsoft functies voor invoegtoepassingen ontwikkeld voor het toestaan [van archivering van gegevens](https://support.office.com/article/Archiving-third-party-data-in-Office-365-0ce338d5-3666-4a18-86ab-c6910ff408cc) uit andere bronnen, via integratie met gegevens van derden voor het vastleggen en beheren van gegevens van derden. Na het importeren van gegevens van derden kunt u nalevings functies van Microsoft 365 toepassen op de gegevens, waaronder:

- [Bewaring van een zaak](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold)
- [In-place eDiscovery en bewaring](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)
- [Zoekopdracht voor compliance](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)
- [In-place archivering](https://docs.microsoft.com/microsoft-365/compliance/enable-archive-mailboxes)
- [Postvakcontrole](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing)
- [Bewaarbeleid](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)

Wanneer u bijvoorbeeld een postvak plaatst op de plaats van de geschillen, blijft gegevens van derden behouden. U kunt zoeken naar gegevens van derden met in-place eDiscovery of de zoekfunctie voor compliance. U kunt ook een archief-en bewaarbeleid toepassen op gegevens van derden, net zoals u dat voor Microsoft-gegevens kunt gebruiken. Archivering van gegevens van derden in Microsoft 365 helpt uw organisatie in overeenstemming te blijven met het beleid voor overheid en regulering.

Archivering in Microsoft 365 biedt effecten en Exchange Commission (SEC) regel 17a-4-compatibele opslag. Microsoft 365 behoudt permanente bestanden met alle gegevens die worden verzameld in een niet-herschrijfbare, niet-herschrijfbare indeling waarbij het bewaarbeleid en het bewaarbeleid voorbehoud en behoud van behoud wordt gehandhaafd.

Precies

- Alle records die zijn opgeslagen met behulp van het bovenstaande bewaarbeleid, blijven behouden in een specifiek opslaggebied uit de purview van de gewone gebruiker. Alleen geautoriseerde gebruikers hebben toegang tot deze records en kunnen deze niet wijzigen of wissen.
- Metagegevens voor elk item bevatten een tijdstempel die wordt gebruikt in de berekening van de Bewaar duur. Tijdstempels worden toegepast wanneer een nieuw item wordt ontvangen of gemaakt en kan niet worden gewijzigd of verwijderd uit de metagegevens.
- Met archivering in Microsoft 365 kunnen gebruikers verschillende bewaarbeleid en acties vasthouden maken om granulair bewaarbeleid te maken. Deze beleidsregels definiëren het type of de locatie van de items die worden bewaard en de behoud van de duur.
- Met de functie voorbehoud van behoud kunnen gebruikers kiezen of ze het beleid beperkt willen maken van het beleid. Met een beperkingsbeleid kunt u voorkomen dat anderen het bewaarbeleid kunnen verwijderen, uitschakelen of wijzigen. Dit betekent dat na behoud van behoud van behoud van behoud van behoud de vergrendelings vergrendeling niet kan worden uitgeschakeld, geen enkel mechanisme bestaat waarvan gegevens van bestaande bewaarders die door het bewaarbeleid zijn verzameld, kunnen worden overschreven, gewijzigd, gewist of verwijderd. Verder wordt de bewaarperiode die is ingesteld met behoud van behoud, niet ingekort Dit kan echter, wanneer het gaat om het behoud van de behoud van de opgeslagen gegevens, zoals hierboven is ingegaan, worden verlengd. Met behoud van behoud van de behoud van behoud van geen enkele, niet even beheerders of personen met bepaalde toegangsrechten, kunnen de instellingen wijzigen of gegevens overschrijven of wissen, zodat de archivering in Microsoft 365 in de regel wordt ingeschakeld met de richtlijnen in de 2003-release van SEC regel 17a-4.

Als u wilt weten hoe Microsoft 365 u helpt bij het voldoen aan wettelijke verplichtingen, met name de regel 17a-4, raadpleegt u het [White Paper](https://www.microsoft.com/microsoft-365/blog/wp-content/uploads/2015/11/Microsoft-EOA-White-Paper.pdf) voor Exchange Online Archiving, SharePoint Online, OneDrive voor bedrijven en Skype voor bedrijven. Het Witboek biedt ook een uitgebreide analyse van Microsoft 365-archiveringsfuncties en functionele functies tegen elk van de vereisten onder de SEC regel 17a-4 en toont aan gereguleerde klanten hoe Microsoft 365 Archiving kan voldoen aan deze vereisten.
