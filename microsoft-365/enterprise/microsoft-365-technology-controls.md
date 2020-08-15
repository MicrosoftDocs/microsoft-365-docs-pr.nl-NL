---
title: Microsoft 365-technologie besturingselementen
ms.author: josephd
author: JoeDavies-MSFT
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
ms.custom:
- seo-marvel-apr2020
description: Dit artikel bevat een overzicht van de hulpmiddelen en technologieën in Microsoft voor Technology Control in Microsoft 365.
ms.openlocfilehash: 53b7a05dba52fbe8c3bb8502441c67bd2be1957d
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688961"
---
# <a name="microsoft-365-technology-controls"></a>Microsoft 365-technologie besturingselementen 

Microsoft gebruikt meerdere hulpprogramma's en technologieën om toegang te beheren, te beheren en te controleren op klantgegevens in de Online Services. Dit geldt voor Exchange Online, SharePoint Online, lockbox en Customer lockbox, meervoudige verificatie en meer. Yammer maakt gebruik van vergelijkbare besturingselementen die worden beschreven in [Enterprise Access-besturingselementen](microsoft-365-yammer-enterprise-access-controls.md).

Microsoft 365-technici hebben geen permanente toegang tot klantgegevens van Microsoft 365. Technici moeten een Microsoft-goedkeuringsproces doorlopen voordat toegang tot klantgegevens voor serviceactiviteiten plaatsvindt. Als de klant-lockbox-functie voor Exchange Online en SharePoint Online wordt gebruikt voor de klant, moet de klant goedkeuring van de klant hebben. Nadat deze is goedgekeurd, worden de service-specifieke beheeraccounts uitsluitend in de tijd toegankelijk gemaakt voor taken die door de serviceaanvraag worden vereist.

## <a name="lockbox-and-customer-lockbox"></a>Lockbox en Customer lockbox

Hoewel een klant geen ondersteuning kon aanvragen van Microsoft die de inhoud van een klant aan een Microsoft-engineer biedt. Voor het beheren van de toegang tot Exchange Online wordt door Microsoft een systeem met de naam lockbox van het Access-besturingssysteem gebruikt. Voordat een Microsoft-engineer een Exchange Online-of SharePoint Online-systeem of-gegevens opent, moet ze een toegangsaanvraag indienen via de lockbox. Alle serviceaanvragen voor Exchange Online en SharePoint Online worden door het lockbox-systeem verwerkt. Met zowel lockbox als Customer Lockbox kan alle goedgekeurde gebruikers traceren aan een unieke gebruiker, zodat ze rekening kunnen trekken met hun administratie van klantgegevens.

> [!NOTE]
> Exchange Online bevat alle Skype voor bedrijven-gegevens die zijn opgeslagen in postvakken van gebruikers. Skype voor bedrijven-afdekking omvat geen Skype Meeting broadcast-opnamen of inhoud geüpload naar vergaderingen door gebruikers. SharePoint Online bevat OneDrive voor bedrijven.

Lockbox verwerkt aanvragen voor machtigingen waarbij de technici de mogelijkheid hebben de functies voor het uitvoeren van functies en beheerders binnen de service uit te voeren. Technici aanvragen indienen via lockbox en een Microsoft-manager moet de aanvraag goedkeuren voordat de ingenieur toegang kan krijgen tot klantgegevens. Na goedkeuring van de Manager heeft de ingenieur beperkte toegang tot klantgegevens, zodat deze aan het probleem van de klant werken.

Met klanten-lockbox voor Microsoft 365 kunt u aan nalevings verplichtingen voldoen als u procedures nodig hebt voor expliciete autorisatie van gegevenstoegang. Dit is een vereiste voor enkele nalevings normen, zoals FedRAMP en HIPAA. Klanten-lockbox voegt u in voor het goedkeuringsproces van de lockbox en biedt u de mogelijkheid de autorisatie van Microsoft Access voor Exchange Online of SharePoint Online-inhoud voor servicebewerkingen te beheren.

In het zeldzame geval dat wanneer een Microsoft-service-engineer toegang tot uw gegevens nodig heeft, alleen toegang is verleend tot gegevens die nodig zijn voor het oplossen van het probleem en voor een beperkte periode. Als u een verzoek om toegang weigert, hebben Microsoft-technici geen toegang tot uw inhoud en kunnen deze geen serviceactiviteiten voltooien. Als u de aanvraag goedkeurt, hebben Microsoft-technici de mogelijkheid om toegang te krijgen tot uw inhoud met behulp van begeleide en beperkte beheerinterfaces.

Acties die worden uitgevoerd door de ondersteuningstechnicus worden geregistreerd voor controledoeleinden en zijn toegankelijk via de [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis) en het [beveiligings-en compliance Center](https://protection.office.com/).

>[!NOTE]
> Customer lockbox is beschikbaar in [Microsoft 365 E5](https://products.office.com/business/office-365-enterprise-e5-business-software) als aankoop. Zie [Microsoft 365 Customer lockbox-aanvragen](https://support.office.com/article/Office-365-Customer-Lockbox-Requests-36f9cdd1-e64c-421b-a7e4-4a54d16440a2)voor meer informatie.

## <a name="just-in-time-access"></a>Alleen-in-time toegang

Microsoft gebruikt het JIT-toegangs principe voor Microsoft 365 om de referentie voor Risico's en zijdelingse aanvallen te beperken. JIT verwijdert permanente beheerderstoegang tot services en vervangt rechten door de mogelijkheid om op aanvraag te overgaan. Door permanente toegangsrechten te verwijderen van beheerders zorgt u ervoor dat de referenties alleen beschikbaar zijn wanneer ze nodig zijn en minder risico voor de diefstal van de referenties.

Voor het JIT-toegangsmodel moeten ingenieurs een beperkte periode aanvragen voor het uitvoeren van beheerdersrechten. Daarnaast gebruiken technici tijdelijke accounts die zijn gemaakt met door de computer gegenereerde complexe wachtwoorden en worden alleen die rollen verleend waarmee ze de benodigde taken kunnen uitvoeren. Voorbeeld van de aangevraagde toegang tot een standaardbeheerder is de hoeveelheid tijd gebonden en de hoeveelheid tijd die toegang heeft gekregen. Met een ingenieur wordt de duur van de benodigde tijd voor toegang in de aanvraag voor het lockbox-systeem aangegeven. Het lockbox-systeem weigert aanvragen wanneer de gevraagde tijd langer is dan de toegestane maximumtijd voor de verhoging. Na verloop wordt de beheerder verwijderd en wordt het tijdelijke account verloopt.

Wanneer de technici geautoriseerd en goedgekeurd zijn, ontvangen technici een eenmalige beheerder met een wachtwoord dat door het autorisatie systeem is gegenereerd. Nieuwe wachtwoorden worden gegenereerd wanneer een aanvraag voor toegang tot verhoging wordt goedgekeurd. Het wachtwoord wordt gekopieerd naar een wachtwoord dat veilig is, is niet hetzelfde als de referenties van de ingenieur voor de Microsoft-bedrijfsomgeving, en is alleen geschikt voor de goedgekeurde toegangs sessie.

## <a name="constrained-management-interfaces"></a>Beheer interfaces met beperkte beperkingen

Technici gebruiken twee beheerinterfaces om beheertaken uit te voeren: extern bureaublad via beveiligde Terminal Service gateways (TSGs) en Remote PowerShell. Binnen deze beheerinterfaces gelden beleidsregels en toegangsbeheer beperkingen voor de toepassing van toepassingen en welke opdrachten en cmdlets beschikbaar zijn.

Microsoft 365-servers beperken gelijktijdige sessies tot één team beheerder per service, per server. TSGs biedt slechts één gelijktijdige sessie voor gebruikers en mag niet meerdere sessies toestaan. Met behulp van een enkele sessie per server TSGs kunnen Microsoft 365-team beheerdersverbinding maken met meerdere servers, zodat beheerders hun functie effectief kunnen uitvoeren. Service team-beheerders hebben geen machtigingen voor de TSGs zelf. De TSG wordt alleen gebruikt voor het afdwingen van multi-factor Authentication (MFA) en coderingsvereisten. Wanneer de service team beheerder verbinding maakt met een specifieke server via een TSG, wordt een sessielimiet van een beheerder per beheerder afgedwongen door de specifieke server.

Gebruiksbeperkingen en de verbindings-en configuratievereisten voor Microsoft 365-medewerkers worden vastgesteld door het Active Directory-groepsbeleid. Dit beleid bevat de volgende kenmerken:

- TSGs gebruiken alleen met [FIPS](https://www.microsoft.com/TrustCenter/Compliance/FIPS) 140-2 gevalideerde versleuteling.
- TSG sessies verbreken na 30 minuten inactiviteit.
- TSG-sessies worden na 24 uur automatisch afgemeld.

Voor verbindingen met TSGs is ook MFA vereist met een aparte fysieke smartcard en een apart account van de Microsoft-bedrijfsreferenties van de ingenieur. Technici maken verschillende smartcards voor diverse platforms en geheimen voor geheimen voor het veilig opslaan van referenties. TSGs gebruikt Active Directory-groepsbeleid om te bepalen wie er kan aanmelden bij externe servers, met het aantal toegestane sessies en de instellingen voor de instellingen voor inactief. Met extra beleidsregels wordt de toegang tot toegestane toepassingen beperkt en wordt de toegang tot internet beperkt.

Met Exchange Online kunnen gebruikers met de functie van de service-engineer en de rol van service-engineer ook toegang krijgen tot bepaalde beheerfuncties op productieservers via Remote PowerShell. Hiervoor moet de gebruiker gemachtigd worden voor alleen-lezen toegang tot de Microsoft 365-productieomgeving. Bevoegdheden voor escalatie van bevoegdheden is op dezelfde manier ingeschakeld voor TSGs met behulp van de lockbox-procedure.

Voor externe toegang heeft elk datacenter een virtueel IP-evenwicht dat fungeert als één toegangspunt. De beschikbare Remote PowerShell-cmdlets zijn gebaseerd op het bevoegdheidsniveau dat is opgegeven in de toegangs claim die wordt verkregen tijdens verificatie. Deze cmdlets geven de enige beheerfunctionaliteit aan die toegankelijk is voor gebruikers die verbinding maken met deze methode. Extern PowerShell beperkt het bereik van opdrachten die beschikbaar zijn voor de engineer en die is gebaseerd op het niveau van toegang dat via het lockbox-proces is toegestaan. In Exchange Online kan de Get-mailbox bijvoorbeeld beschikbaar zijn, maar instellen-postvak niet.
