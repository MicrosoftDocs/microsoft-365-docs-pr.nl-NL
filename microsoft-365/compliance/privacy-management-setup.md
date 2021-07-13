---
title: Aan de slag met Microsoft Privacy Management (preview)
f1.keywords:
- CSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- M365-privacy-management
search.appverid:
- MOE150
- MET150
description: Informatie over het instellen van privacybeheer voor uw organisatie, het instellen van rollen en machtigingen en het configureren van belangrijke instellingen.
ms.openlocfilehash: 5199cf96e9ede3287dc9ac33e26388c065189748
ms.sourcegitcommit: 022d9d91263994c48efcebe08a84319573dc3a8c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "53378501"
---
# <a name="get-started-with-privacy-management-preview"></a>Aan de slag met privacybeheer (voorbeeld)

In dit artikel vindt u informatie over het instellen van  toegang tot **privacybeheer** voor uw organisatie, hoe u aan de slag kunt met het evalueren van uw gegevens en hoe u belangrijke instellingen **kunt verwerken.**

## <a name="sign-up"></a>Aanmelden

Privacybeheer is beschikbaar binnen de Microsoft 365-compliancecentrum. Het openbare voorbeeld van privacybeheer is beschikbaar voor organisaties met E1-, E3- en E5-Office 365 en Microsoft 365 enterprise-licenties. Nadat het privacybeheer algemeen beschikbaar is, moeten organisaties een nieuwe licentie verkrijgen.

Houd er rekening mee dat het openbare voorbeeld van privacybeheer niet beschikbaar is voor klanten van de Amerikaanse overheidsgemeenschap (GCC) Moderate, GCC High of Department of Defense (DoD).

Als u wilt beginnen met het openbare voorbeeld, haalt u het preview-abonnement op in het beheercentrum. Als u de licentie nog niet hebt wanneer u voor het eerst privacybeheer selecteert in het compliancecentrum, wordt u doorgestuurd naar het beheercentrum om aan de slag te gaan. We raden de globale beheerder aan zich aan te melden en gebruikersmachtigingen in te stellen, zoals hieronder wordt beschreven bij het voor het eerst bezoeken van privacybeheer. Als u niet de vereiste rol hebt om het abonnement te verkrijgen of als u akkoord gaat met de voorwaarden voor het gebruik van privacybeheer, wordt u gevraagd contact op te nemen met uw globale beheerder voor hulp.

Als u bevestigt dat u wilt beginnen met het gebruik van de signalen voor privacybeheer, gaat u akkoord met de voorwaarden en het evaluatieproces voor persoonlijke gegevens. U kunt de opgegeven koppelingen volledig bekijken voordat u verdergaat.

## <a name="set-user-permissions-and-assign-roles"></a>Gebruikersmachtigingen instellen en rollen toewijzen

Privacybeheer gebruikt een RBAC-machtigingsmodel (Role-Based Access Control). Alleen gebruikers aan wie een rol is toegewezen, hebben toegang tot privacybeheer en de acties die door elke gebruiker zijn toegestaan, worden beperkt per roltype.

Machtigingen en roltoewijzingen voor privacybeheer kunnen als volgt Microsoft 365-compliancecentrum worden afgehandeld. Houd er rekening mee dat rollen die specifiek zijn voor privacybeheer, niet worden weergegeven in Azure Active Directory.

### <a name="in-the-microsoft-365-compliance-center"></a>In de Microsoft 365-compliancecentrum

- Selecteer Machtigingen in de linkernavigatie.
- Vouw Compliancecentrum uit en selecteer Rollen. De volledige lijst met rollengroepen wordt weergegeven. 
- Blader naar de privacybeheergroepen of zoek op trefwoord, bijvoorbeeld 'privacy'.
- Selecteer de relevante rollengroep om een beschrijving, de toegewezen rollen en een lijst met leden te zien.
- Gebruik de koppeling Bewerken naast deze secties om gebruikers toe te voegen of te wijzigen of de instellingen te bewerken.

### <a name="learn-about-role-groups-and-roles"></a>Meer informatie over rollengroepen en rollen

In deze sectie worden de rollengroepen en rollen beschreven die relevant zijn voor privacybeheer. Leden moeten worden toegewezen aan rollengroepen door de beheerder op het hoogste niveau, afhankelijk van welke taken ze moeten uitvoeren en welk niveau van bestandstoegang geschikt is. Elke rollengroep bevat een of meer rollen. Deze rollen kunnen betrekking hebben op specifieke privacybeheertaken of kunnen overeenkomen met belangrijke functies die zijn ingeschakeld of beperkt voor de leden van die groep.

Rolgroepen kunnen indien nodig worden aangepast. Om onbedoeld toegangsverlies te voorkomen, raden we u aan een kopie te maken van de bestaande rollengroep die u wilt aanpassen, de kopie een identificeerbare naam te geven, uw wijzigingen in de nieuwe groep aan te brengen en te verifiëren en personen aan de nieuwe groep toe te wijzen.

**Privacybeheer:** deze groep bevat alle machtigingsrollen voor privacybeheer in één groep. Dit is de eenvoudigste manier om snel aan de slag te gaan met privacybeheer en toegangsbeheer te beheren voor andere groepen die gebruikmaken van privacybeheer. Het past ook goed bij organisaties die geen afzonderlijke machtigingen nodig hebben die zijn gedefinieerd voor afzonderlijke groepen gebruikers.

**Beheerders** van privacybeheer: leden van deze rollengroep richten zich op configuratie- en beheertaken en hebben brede toegang tot privacybeheerfuncties, zoals het maken, lezen, bijwerken en verwijderen van privacybeheerbeleid, aanvragen voor onderwerprechten, privacybeheermachtigingen en privacybeheerinstellingen.

**Privacy Management Analysts:** Leden van deze rollengroep fungeren als privacymanagementcaseanalisten. Ze kunnen beleids matches onderzoeken, bestandsmetagegevens bekijken en herstelacties uitvoeren. Deze groep heeft geen toegang tot volledige bestanden via de Inhoudsverkenner.

**Privacybeheeronderzoekers:** leden van deze groep fungeren als privacybeheergegevensonderzoekers. Ze kunnen beleidswedstrijden onderzoeken, de bijbehorende bestandsinhoud bekijken en herstelacties uitvoeren. Deze groep heeft toegang tot bestanden via de Inhoudsverkenner.

**Privacybeheerviewer:** leden van deze groep kunnen analytische informatie bekijken in privacybeheer, zoals het overzicht, het gegevensprofiel en rapporten over onderwerpverzoeken.

**Beheerders van aanvraag voor onderwerprechten:** leden van deze groep hebben volledige toegang tot het beheren en maken van aanvragen voor onderwerprechten.

**Inzenders voor privacybeheer:** leden van deze groep hebben inzendertoegang tot verzoeken om rechten.

Zie de volgende tabel als u de specifieke rollen in elke rollengroep wilt zien.

| **Rollengroep**      | **Rollen opgenomen**                        |
|:-- |:--|
| Privacybeheer  | Case Management                           |
|                     | Inhoudsviewer voor gegevensclassificatie        |
|                     | Gegevensclassificatielijstviewer           |
|                     | Beheerder van privacybeheer                  |
|                     | Privacybeheeranalyse               |
|                     | Privacybeheeronderzoek          |
|                     | Permanente bijdrage voor privacybeheer |
|                     | Tijdelijke bijdrage privacybeheer |
|                     | Privacybeheerviewer                 |
|                     | Beheerder van aanvraag voor onderwerprechten              |
|                     | View-Only Case                            |
| Beheerder van privacybeheer | Case Management                      |
|                          | Beheerder van privacybeheer             |
|                          | View-Only Case                       |
| Privacymanagementanalisten | Case Management                   |
|                             | Gegevensclassificatielijstviewer   |
|                             | Privacybeheeranalyse       |
|                             | View-Only Case                    |
| Privacybeheeronderzoekers | Case Management              |
|                                  | Inhoudsviewer voor gegevensclassificatie |
|                                  | Gegevensclassificatielijstviewer    |
|                                  | Privacybeheeronderzoek   |
|                                  | View-Only Case                     |
| Privacybeheerviewer        | Privacybeheerviewer          |
| Beheerder van aanvraag voor onderwerprechten | Beheerder van aanvraag voor onderwerprechten   |
|Inzenders voor privacybeheer       | Tijdelijke bijdrage privacybeheer |
|                                      | Permanente bijdrage voor privacybeheer |

## <a name="configure-settings"></a>Instellingen configureren

De Instellingen pagina is toegankelijk via het tandwiel in de rechterbovenhoek van de hoofdpagina's van privacybeheer. Hiermee kunnen beheerders van privacybeheer essentiële eigenschappen configureren voor privacybeheer. De volgende opties zijn:

### <a name="anonymization"></a>Anonimiseren

Met deze functie kunt u geanonimiseerde versies van gebruikersnamen in privacybeheerfuncties laten zien aan gebruikers in bepaalde rollen. Hiermee worden herkenbare weergavenamen zoals 'Grace Taylor' vervangen door een algemeen label zoals 'AnonyIS8-988' om de identiteit van uw gebruikers te maskeren tijdens het controleren van gevoelige gegevens. Deze optie is niet van toepassing op de module aanvraag voor onderwerprechten.

### <a name="user-notification-emails"></a>E-mailberichten over gebruikersmeldingen

Wanneer we een overeenkomst voor uw beleid voor gegevensafhandeling detecteren, kan privacybeheer een e-mail verzenden naar de getroffen gebruikers met corrigerende acties die moeten worden ondernomen en een koppeling naar privacytraining. In Instellingen kunt u de mogelijkheid voor e-mailmeldingen van privacybeheer als geheel in- of uitschakelen. U kunt afzonderlijke meldingen activeren, e-mailfrequentie instellen en een trainings-URL opgeven wanneer u een beleid maakt of bewerkt. Als de meldingsfunctie is uitgeschakeld in Instellingen, wordt elke configuratie op beleidsniveau voor specifieke meldingsberichten uitgeschakeld. Zie Beleid maken en beheren voor meer informatie over [beleid.](privacy-management-policies.md)

### <a name="teams-collaboration"></a>Teams samenwerking

Integreer Microsoft Teams mogelijkheden met privacybeheer om de samenwerking met belanghebbenden te verbeteren. Telkens als er een aanvraag voor onderwerprechten wordt gemaakt, wordt er een gekoppeld team gemaakt. Gebruikers kunnen worden toegevoegd aan een team via het tabblad Medewerkers van de aanvraag. Zie Aanvragen voor onderwerprechten beheren voor meer informatie over aanvragen voor [onderwerprechten.](privacy-management-subject-rights-requests.md)

### <a name="power-automate-flows"></a>Power Automate stromen

Gebruik Power Automate om automatisch privacygerelateerde processen en taken te beheren. U kunt stromen maken in Instellingen sectie met ingebouwde privacybeheersjablonen of de console Power Automate gebruiken om aangepaste stromen te maken. Voor meer informatie over Power Automate, bekijkt u [de Power Automate](/power-automate/) documentatie.

### <a name="data-matching"></a>Gegevensmatching

Gebruik deze sectie om gegevensschema's te uploaden waarin kenmerken van uw gegevensonderwerpen worden beschreven, waarmee u de juiste gegevenspersoon kunt identificeren bij het zoeken naar persoonlijke gegevens in uw Microsoft 365 omgeving. Schema's en regelpakketten worden gemaakt en geüpload in XML-indeling. Onder Uploaden van persoonlijke gegevens kunt u ook persoonlijke gegevens indienen die overeenkomt met een opgegeven schema. U kunt uw eigen bestand maken en uploaden of ervoor kiezen om persoonlijke gegevens te uploaden vanuit Azure. Zie Aanvragen voor onderwerprechten beheren voor meer informatie over aanvragen voor [onderwerprechten.](privacy-management-subject-rights-requests.md)

### <a name="data-retention-periods"></a>Bewaarperioden voor gegevens

Kies voor aanvragen voor onderwerprechten hoe lang u de uiteindelijke gegevens wilt bewaren die zijn verzameld en rapporteren nadat een aanvraag is gesloten. U kunt kiezen tussen 30 of 90 dagen. Zie Aanvragen voor onderwerprechten beheren voor meer informatie over aanvragen voor [onderwerprechten.](privacy-management-subject-rights-requests.md)

### <a name="data-review-tags"></a>Gegevensbeoordelingslabels

Beheer de tags die u gebruikt om bestanden te markeren die zijn opgehaald in een aanvraag voor onderwerprechten. In deze sectie kunt u de namen en beschrijvingen voor aangepaste tags bewerken. U kunt ook tagbeschrijvingen bewerken voor de ingebouwde tags die door het systeem worden geleverd. Namen voor systeemlabels kunnen niet worden gewijzigd. Zie Aanvragen voor onderwerprechten beheren voor meer informatie over aanvragen voor [onderwerprechten.](privacy-management-subject-rights-requests.md)

## <a name="get-initial-data-insights"></a>Eerste gegevensinzichten krijgen

Nadat u zich hebt aanmelden bij privacybeheer, komt u op de pagina **Overzicht.** Deze pagina bevat dynamische inzichten over de persoonlijke gegevens die zijn opgeslagen in uw Microsoft 365 omgeving, zodat u snel problemen kunt vinden, risico-indicatoren kunt identificeren en actie kunt ondernemen om problemen op te lossen. Uw overzicht moet binnen de eerste 24 uur na de aanmelding gevuld zijn met eerste inzichten. Terwijl u privacybeheer blijft gebruiken, wordt de overzichtspagina vernieuwd om actuele informatie te blijven verstrekken.

Voor meer inzicht in uw gegevens  in de tijd, biedt uw pagina Gegevensprofiel meer visualisaties en analyses en krijgt u een overzicht op hoog niveau van de gegevens van uw organisatie op geografische locatie en per Microsoft 365 service.

Zie Uw gegevens zoeken en visualiseren voor [meer informatie over deze pagina's.](privacy-management-data-profile.md)
