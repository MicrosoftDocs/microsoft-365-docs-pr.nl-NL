---
title: Een Advanced eDiscovery instellen in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: In dit artikel wordt beschreven hoe u een Advanced eDiscovery zo kunt instellen dat u zaken kunt maken en beheren. Ook worden de vereiste Microsoft-abonnementen en -licenties beschreven. Nadat u een paar snelle stappen hebt voltooid, is Advanced eDiscovery klaar voor gebruik.
ms.openlocfilehash: 6c6aed482da8f203154d94313ec04519d6a330ea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161983"
---
# <a name="set-up-microsoft-365-advanced-ediscovery"></a>Een Microsoft 365 Advanced eDiscovery

Advanced eDiscovery in Microsoft 365 biedt een end-to-end werkstroom voor het bewaren, verzamelen, controleren, analyseren en exporteren van gegevens die reageren op interne en externe onderzoeken van uw organisatie. Er is niets nodig om Advanced eDiscovery te implementeren, maar er zijn enkele vereiste taken die een IT-beheerder en eDiscovery-manager moeten uitvoeren voordat uw organisatie kan beginnen met het maken en gebruiken van Advanced eDiscovery-zaken om uw onderzoeken te beheren.

In dit artikel worden de volgende stappen beschreven die nodig zijn voor het instellen van Advanced eDiscovery.

![Stappen voor het instellen van Advanced eDiscovery](../media/set-up-advanced-ediscovery.png)

Dit omvat het waarborgen van de juiste licenties die nodig zijn voor toegang tot Advanced eDiscovery en het toevoegen van voogden aan zaken, en het toewijzen van machtigingen aan uw juridische en onderzoeksteam, zodat ze zaken kunnen openen en beheren.

## <a name="step-1-verify-and-assign-appropriate-licenses"></a>Stap 1: De juiste licenties controleren en toewijzen

Licenties voor Advanced eDiscovery vereist het juiste organisatieabonnement en licenties per gebruiker. Zie Abonnementen en licenties voor een lijst met licentievereisten voor Advanced eDiscovery [licenties.](overview-ediscovery-20.md#subscriptions-and-licensing)

## <a name="step-2-assign-ediscovery-permissions"></a>Stap 2: eDiscovery-machtigingen toewijzen

Als u toegang Advanced eDiscovery of toegevoegd als lid van een Advanced eDiscovery geval, moet aan een gebruiker de juiste machtigingen zijn toegewezen. Een gebruiker moet met name worden toegevoegd als lid van de rollengroep eDiscovery Manager in het beveiligings- & Compliancecentrum. Leden van deze rollengroep kunnen een aantal Advanced eDiscovery maken en beheren. Ze kunnen leden toevoegen en verwijderen, beheerders en inhoudslocaties in de wacht zetten, meldingen over juridische wacht houden beheren, zoekopdrachten maken en bewerken die aan een zaak zijn gekoppeld, zoekresultaten toevoegen aan een revisieset, gegevens analyseren in een revisieset en exporteren en downloaden vanuit een Advanced eDiscovery-zaak.

Volg de volgende stappen om gebruikers toe te voegen aan de rollengroep eDiscovery Manager:

1. Ga naar <https://protection.office.com/permissions> en meld u aan met de referenties voor een beheerdersaccount in uw Microsoft 365 organisatie.

2. Selecteer op **de pagina** Machtigingen de **rollengroep eDiscovery Manager.**

3. Klik op de flyoutpagina van eDiscovery Manager op **Bewerken** naast de **sectie eDiscovery Manager.**

4. Klik op **de pagina eDiscovery Manager** kiezen in de wizard Rollengroep bewerken op **EDiscovery Manager kiezen.**

5. Klik **op** Toevoegen en schakel het selectievakje in voor alle gebruikers die u wilt toevoegen aan de rollengroep.

6. Klik **op Toevoegen** om de geselecteerde gebruikers toe te voegen en klik vervolgens op **Klaar.**

7. Klik **op** Opslaan om de gebruikers toe te voegen aan de rollengroep en klik vervolgens op **Sluiten** om de stap te voltooien.

### <a name="more-information-about-the-ediscovery-manager-role-group"></a>Meer informatie over de rollengroep eDiscovery Manager

Er zijn twee subgroepen in de rollengroep eDiscovery Manager. Het verschil tussen deze subgroepen is gebaseerd op bereik.

- **eDiscovery Manager:** kan de verschillende Advanced eDiscovery die ze maken of lid zijn van weergeven en beheren. Als een andere eDiscovery Manager een zaak maakt, maar geen tweede eDiscovery Manager toevoegt als lid van die zaak, kan de tweede eDiscovery Manager de zaak niet weergeven of openen op de pagina Advanced eDiscovery in het compliancecentrum. Over het algemeen kunnen de meeste personen in uw organisatie worden toegevoegd aan de subgroep eDiscovery Manager.

- **eDiscovery-beheerder:** kan alle casebeheertaken uitvoeren die een eDiscovery Manager kan uitvoeren. Bovendien kan een eDiscovery-beheerder:

  - Bekijk alle zaken die worden weergegeven op de Advanced eDiscovery pagina.
  
  - Beheer hoe dan ook in de organisatie nadat ze zichzelf hebben toevoegen als lid van de zaak.

  - Toegang tot en export van casegegevens voor elk geval in de organisatie.

  Vanwege het grote bereik van toegang moet een organisatie slechts een paar beheerders hebben die lid zijn van de subgroep eDiscovery-beheerders.

Zie eDiscovery-machtigingen toewijzen voor meer informatie over [eDiscovery-machtigingen](assign-ediscovery-permissions.md)en een beschrijving van elke rol die is toegewezen aan de rollengroep eDiscovery Manager.

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a>Stap 3: Algemene instellingen configureren voor Advanced eDiscovery

De laatste stap die moet worden voltooid voordat personen in uw organisatie zaken gaan maken en gebruiken, is het configureren van algemene instellingen die van toepassing zijn op alle zaken in uw organisatie. Op dit moment is de enige globale instelling de detectie van *advocaten-clientvoorrechten* (in de toekomst zijn er meer algemene instellingen beschikbaar). Met deze instelling kan het privilegemodel voor advocatenclient worden uitgevoerd wanneer u gegevens in een revisieset analyseert. Het model maakt gebruik van machine learning om de kans te bepalen dat een document inhoud bevat die juridisch van aard is. Ook worden de deelnemers aan documenten vergeleken met een advocatenlijst (die u indient bij het instellen van het model) om te bepalen of een document ten minste één deelnemer heeft die een advocaat is.

Zie Detectie van advocaten-clientvoorrechten instellen in Advanced eDiscovery voor meer informatie over het instellen en gebruiken van het detectiemodel voor [advocaten-clientrechten.](attorney-privilege-detection.md)

> [!NOTE]
> Dit is een optionele stap die u op elk gewenst moment kunt uitvoeren. Als u het detectiemodel voor advocaten-clientvoorrechten niet implementeert, kunt u geen nieuwe Advanced eDiscovery maken.

## <a name="next-steps"></a>Volgende stappen

Nadat u een Advanced eDiscovery hebt ingesteld, kunt u een [zaak maken.](create-and-manage-advanced-ediscoveryv2-case.md)