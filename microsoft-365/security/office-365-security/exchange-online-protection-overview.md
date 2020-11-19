---
title: Overzicht van Exchange Online Protection (EOP)
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 09/18/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: Lees hoe Exchange Online Protection (EOP) u kan helpen uw on-premises e-mail organisatie te beschermen in zelfstandige en hybride omgevingen.
ms.openlocfilehash: 997f157432dced474ccc17bf47cf9af68f4b8c08
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356713"
---
# <a name="exchange-online-protection-overview"></a>Overzicht Exchange Online Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Exchange Online Protection (EOP) is de service voor filteren op de Cloud waarmee u uw organisatie kunt beschermen tegen spam en malware. EOP is opgenomen in alle Microsoft 365-organisaties met postvakken van Exchange Online. EOP is echter ook beschikbaar in de volgende on-premises scenario's:

- **In een standalone scenario**: EOP biedt cloudbeveiliging voor de on-premises Exchange-organisatie of voor andere on-premises SMTP-e-mail oplossingen.

- **In een hybride implementatie**: EOP kan worden geconfigureerd om uw e-mail omgeving te beschermen en e-mail routering te bepalen wanneer u een combinatie van on-premises en Cloud postvakken hebt.

In deze scenario's kan EOP het beheer van uw e-mail omgeving vereenvoudigen en veel van de lasten van het onderhoud van on-premises hardware en software.

In de rest van dit onderwerp wordt uitgelegd hoe EOP werkt in zelfstandige en hybride omgevingen.

## <a name="how-eop-works"></a>Hoe EOP werkt

Om inzicht te krijgen in de werking van EOP, is het handig om te zien hoe het e-mailbericht inkomende e-mail verwerkt:

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="Afbeelding van de e-mail van Internet of feedback van klanten die aan EOP en via de verbinding, anti-malware, e-mail regels en het filteren van de inhoud voor de verdict van ongewenste e-mail of Quarantine, of de e-mail bezorging van de eindgebruikers.":::

- Wanneer een inkomend bericht wordt ingevoerd in EOP, wordt het in eerste instantie door het filteren van verbindingen verzonden en wordt de reputatie van de afzender gecontroleerd. Het merendeel van de spam wordt op dit moment stopgezet en afgekeurd door EOP. Zie [Verbindingsfiltering configureren](configure-the-connection-filter-policy.md) voor meer informatie.

- Het bericht is gecontroleerd op tekenen van malware. Als er malware wordt gevonden in het bericht of de bijlage (n), wordt het bericht gerouteerd naar een quarantaine archief van alleen de beheerder. U vindt [hier](configure-anti-malware-policies.md)meer informatie over het configureren van anti malware.

- Berichten doorgaan met het filteren van beleidsregels, waarbij ze worden geëvalueerd voor aangepaste e-mail stroom regels (ook wel een transportregel genoemd) die u maakt of afdwingt van een sjabloon. U kunt bijvoorbeeld een regel die een melding naar een manager verzendt wanneer e-mail wordt ontvangen van een specifieke afzender. Controles van preventie van gegevensverlies (DLP) doen ook plaats (Exchange Enterprise-licentieverlening met Services).

- Vervolgens wordt het bericht doorgestuurd via het filteren van inhoud (ook wel anti spam genoemd). Een bericht waarin wordt aangegeven dat het filter spam *of phishing* is, kan worden verzonden naar Quarantine, of naar de map Ongewenste e-mail van een gebruiker, onder andere opties. Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) en [anti phishings beleid configureren](configure-anti-phishing-policies-eop.md)voor meer informatie.

Elk bericht waarmee al deze beveiligingslagen worden doorgestuurd, wordt bezorgd bij de geadresseerde.

Zie voor meer informatie de [volgorde en prioriteit van e-mail beveiliging](how-policies-and-protections-are-combined.md).

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a>EOP-abonnementen en-functies voor on-premises e-mail organisaties

Dit zijn de beschikbare EOP-abonnementen:

- **Zelfstandige** versie van EOP: u registreert zich in EOP om uw on-premises e-mail organisatie te beschermen.

- **EOP-functies in Exchange Online**: elk abonnement met Exchange Online (standalone of als onderdeel van microsoft 365) maakt gebruik van EOP om uw postvakken van Exchange Online te beveiligen.

- **Exchange Enterprise CAL met Services**: als u een on-premises Exchange-organisatie hebt waarop u extra Exchange Enterprise-licentieverlening met Services-licenties hebt aangeschaft, maakt EOP deel uit van de opgenomen services.

Zie de beschrijving van de [Exchange Online Protection Service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)voor informatie over vereisten, belangrijke grenzen en de beschikbaarheid van functies in alle EOP-abonnementen.

## <a name="setting-up-eop-for-on-premises-email-organizations"></a>EOP instellen voor on-premises e-mail organisaties

Het instellen van EOP kan eenvoudig zijn, met name in het geval van een kleine organisatie met een aantal compliance-regels. Als u echter een grote organisatie met meerdere domeinen, aangepaste nalevings regels of hybride e-mail stroom hebt, kan het instellen van meer planning en tijd duren.

Als u uw EOP al hebt gekocht, raadpleegt u [uw EOP-service instellen](set-up-your-eop-service.md) om ervoor te zorgen dat u alle benodigde stappen voor het configureren van EOP voor de bescherming van uw berichtenomgeving.

### <a name="eop-datacenters"></a>EOP-datacenters

EOP wordt uitgevoerd in een wereldwijd netwerk van datacenters die zijn ontworpen om de beste beschikbaarheid te bieden. Als een datacenter niet meer beschikbaar is, worden e-mailberichten automatisch doorgestuurd naar een ander datacenter zonder onderbreking in de service. Servers in elk datacenter accepteren berichten namens u, met een afscheids scheiding tussen uw organisatie en Internet, zodat de belasting van uw servers minder wordt. Via dit hoogst beschikbare netwerk kan Microsoft ervoor zorgen dat e-mail op een redelijke manier binnen uw organisatie terechtkomt.

EOP voert werklastverdeling uit tussen datacenters, maar alleen binnen een regio. Als u in één regio bent ingericht, worden al uw berichten verwerkt met de e-mail routering voor die regio. In de volgende lijst ziet u hoe regionale e-mail Routering werkt voor de EOP-datacenters:

- In Europa, het Midden-Oosten en Afrika (EMEA), vindt u alle Exchange Online-postvakken in EMEA-datacenters en worden alle berichten gerouteerd via de EMEA-datacenters voor EOP filteren.

- In Asia-Pacific (APAC) bevinden alle Exchange Online-postvakken zich in APAC-datacenters en worden berichten momenteel gerouteerd via APAC-datacenters voor EOP filteren.

- In het continent voor de services worden de services op de volgende locaties gedistribueerd:

  - Zuid-Amerika: postvakken van Exchange Online bevinden zich in de datacenters in Brazilië en Chili. Alle berichten worden gerouteerd via lokale datacenters voor EOP filteren. Berichten in quarantaine zijn opgeslagen in het datacenter waar zich de Tenant bevindt.

  - Canada: postvakken van Exchange Online bevinden zich in de datacenters in Canada. Alle berichten worden gerouteerd via lokale datacenters voor EOP filteren. Berichten in quarantaine zijn opgeslagen in het datacenter waar zich de Tenant bevindt.

  - Verenigde Staten: postvakken van Exchange Online bevinden zich in de VS-datacenters. Alle berichten worden gerouteerd via lokale datacenters voor EOP filteren. Berichten in quarantaine zijn opgeslagen in het datacenter waar zich de Tenant bevindt.

- Voor de Government Community Cloud (GCC) bevinden alle Exchange Online-postvakken zich in de VS-datacenters en worden alle berichten gerouteerd via de VS-datacenters voor EOP filteren.

## <a name="eop-help-for-admins"></a>EOP Help voor beheerders

De Help-inhoud voor EOP-beheerders bestaat uit de volgende categorieën op het hoogste niveau:

- [CONFIGUREER EOP, dag 1, voor Microsoft Defender for Office 365-beheerders](protect-against-threats.md): Configureer EOP Protection en Detection Programma's met de kern van Microsoft Defender for Office 365.

- [Functies in EOP](eop-features.md): bevat een lijst met functies die beschikbaar zijn in EOP.

- [Uw EOP-service instellen](set-up-your-eop-service.md): dit bevat stappen voor het instellen van uw EOP-service en koppelingen naar aanvullende informatie.

- [Overstappen op EOP van Google Postini, The Barracuda Spam en virus firewall, of Cisco IronPort](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md): beschrijving van het proces voor het overstappen op EOP van een ander e-mail beveiligings product.

- [Geadresseerden beheren in zelfstandige EOP](manage-recipients-in-eop.md): hier wordt beschreven hoe u e-mail gebruikers en groepen beheert in EOP.

- [E-mail stroom in EOP](mail-flow-in-eop.md): hierin wordt beschreven hoe u aangepaste e-mail stroom scenario's configureert met behulp van connectors, hoe u domeinen beheert die aan de service zijn gekoppeld en hoe u de functie voor het inschakelen van de op mappen gebaseerde functie voor Edge blocking (DBEB)

- [Aanbevolen procedures voor het configureren van EOP](best-practices-for-configuring-eop.md): hierin worden aanbevolen configuratie-instellingen en overwegingen beschreven voor de manier waarop u uw service hebt ingesteld en ingericht.

- [Controlerapporten in zelfstandige EOP](auditing-reports-in-eop.md): hierin wordt beschreven hoe u controlerapporten gebruikt om configuratiewijzigingen in de service bij te houden.

- [Anti-spam en beveiliging tegen malware in EOP](anti-spam-and-anti-malware-protection.md): Hier vindt u een beschrijving van het filteren van ongewenste e-mail en het filteren van malware en toont hoe u deze kunt aanpassen aan de behoeften van uw organisatie. Beschrijft ook taken die beheerders en eindgebruikers kunnen uitvoeren op berichten in quarantaine.

- [Rapporten en berichten traceren in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md): hierin worden de beschikbare hulpmiddelen voor rapporten en probleemoplossing beschreven.

- [Exchange-Beheercentrum in zelfstandige EOP](exchange-admin-center-in-exchange-online-protection-eop.md): hierin wordt beschreven hoe u toegang krijgt tot en navigeert door de beheerinterface van het Exchange-Beheercentrum (de beheerinterface voor Exchange-Beheercentrum) om uw EOP-service te beheren.

- [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell): biedt informatie over externe PowerShell waarmee u de EOP-service vanaf de opdrachtregel kunt beheren.

- [Help en ondersteuning voor EOP](help-and-support-for-eop.md) Dit artikel bevat informatie over het verkrijgen van hulp en technische ondersteuning.
