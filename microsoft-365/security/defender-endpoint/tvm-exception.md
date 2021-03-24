---
title: Uitzonderingen maken en weergeven voor beveiligingsaanbevelingen - bedreigings- en kwetsbaarheidsbeheer
description: Maak en controleer uitzonderingen voor beveiligingsaanbevelingen in bedreigings- en kwetsbaarheidsbeheer.
keywords: microsoft defender atp tvm remediation, mdatp tvm, threat and vulnerability management, threat & vulnerability management, threat & vulnerability management remediation, tvm remediation intune, tvm remediation sccm
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c8ad69930ce4faecbffbc6d2fab59bbe2cac06fa
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058145"
---
# <a name="create-and-view-exceptions-for-security-recommendations---threat-and-vulnerability-management"></a>Uitzonderingen maken en weergeven voor beveiligingsaanbevelingen - bedreigings- en kwetsbaarheidsbeheer

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Bedreigings- en kwetsbaarheidsbeheer](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Als alternatief voor een herstelaanvraag wanneer een aanbeveling op dit moment niet relevant is, kunt u uitzonderingen maken voor aanbevelingen. Als uw organisatie apparaatgroepen heeft, kunt u de uitzondering op specifieke apparaatgroepen bereiken. Uitzonderingen kunnen worden gemaakt voor geselecteerde apparaatgroepen, of voor alle apparaatgroepen van vroeger en nu.  

Wanneer een uitzondering wordt gemaakt voor een aanbeveling, is de aanbeveling pas actief na het einde van de duur van de uitzondering. De aanbevelingstoestand wordt gewijzigd in **Volledige uitzondering** of **Gedeeltelijke uitzondering** (per apparaatgroep).

## <a name="permissions"></a>Machtigingen

Alleen gebruikers met machtigingen voor het verwerken van uitzonderingen kunnen uitzonderingen beheren (waaronder het maken of annuleren). [Meer informatie over RBAC-rollen.](user-roles.md)

![Weergave van machtigingen voor het afhandelen van uitzonderingen.](images/tvm-exception-permissions.png)

## <a name="create-an-exception"></a>Een uitzondering maken

Selecteer een beveiligingsaanbeveling voor wie u een uitzondering wilt maken en selecteer vervolgens **Opties** voor uitzondering en vul het formulier in.  

![Hier wordt weergegeven waar de knop voor 'uitzonderingsopties' zich bevindt in een flyout voor beveiligingsaanbeveling.](images/tvm-exception-options.png)

### <a name="exception-by-device-group"></a>Uitzondering per apparaatgroep

Pas de uitzondering toe op alle huidige apparaatgroepen of kies specifieke apparaatgroepen. Toekomstige apparaatgroepen worden niet opgenomen in de uitzondering. Apparaatgroepen die al een uitzondering hebben, worden niet weergegeven in de lijst. Als u alleen bepaalde apparaatgroepen selecteert, verandert de aanbevelingstoestand van 'actief' in 'gedeeltelijke uitzondering'. De status wordt gewijzigd in 'volledige uitzondering' als u alle apparaatgroepen selecteert.

![De vervolgkeuzekeuze van de apparaatgroep weergeven.](images/tvm-exception-device-group-500.png)

#### <a name="filtered-views"></a>Gefilterde weergaven

Als u op een van de pagina's voor bedreigings- en kwetsbaarheidsbeheer op apparaatgroep hebt gefilterd, worden alleen de gefilterde apparaatgroepen weergegeven als opties.

Dit is de knop om te filteren op apparaatgroep op een van de pagina's voor bedreigings- en kwetsbaarheidsbeheer: 

![Filter geselecteerde apparaatgroepen weergeven.](images/tvm-selected-device-groups.png)

Uitzonderingsweergave met gefilterde apparaatgroepen:

![De vervolgkeuzekeuze van de gefilterde apparaatgroep weergeven.](images/tvm-exception-device-filter500.png)

#### <a name="large-number-of-device-groups"></a>Groot aantal apparaatgroepen

Als uw organisatie meer dan 20 apparaatgroepen heeft, **selecteert** u Bewerken naast de optie gefilterde apparaatgroep.

![Hier wordt weergegeven hoe u grote aantallen groepen bewerkt.](images/tvm-exception-edit-groups.png)

Er wordt een flyout weergegeven waarin u apparaatgroepen kunt zoeken en kiezen die u wilt gebruiken. Selecteer het vinkje onder Zoeken om alles te controleren/uit te checken.

![Flyout voor grote apparatengroep weergeven.](images/tvm-exception-device-group-flyout-400.png)

### <a name="global-exceptions"></a>Globale uitzonderingen

Als u globale beheerdersmachtigingen hebt (microsoft Defender ATP-beheerder genoemd), kunt u een globale uitzondering maken en annuleren. Dit is van **invloed op** alle huidige en toekomstige apparaatgroepen in uw organisatie, en alleen een gebruiker met vergelijkbare machtigingen kan deze wijzigen. De aanbevelingstoestand verandert van 'actief' in 'volledige uitzondering'.

![De optie Globale uitzondering weergeven.](images/tvm-exception-global.png)

Enkele dingen waar u rekening mee moet houden:

- Als een aanbeveling een globale uitzondering is, worden nieuwe uitzonderingen voor apparaatgroepen opgeschort totdat de algemene uitzondering is verlopen of geannuleerd. Daarna worden de uitzonderingen voor de nieuwe apparaatgroep van kracht totdat ze verlopen.
- Als een aanbeveling al uitzonderingen voor specifieke apparaatgroepen heeft en er een algemene uitzondering wordt gemaakt, wordt de uitzondering voor de apparaatgroep opgeschort totdat deze verloopt of wordt de globale uitzondering geannuleerd voordat deze verloopt.

### <a name="justification"></a>Uitvulling

Selecteer uw rechtvaardiging voor de uitzondering die u moet indienen in plaats van de beveiligingsaanbeveling in kwestie te corrigeren. Vul de uitvullingscontext in en stel de duur van de uitzondering in.

In de volgende lijst worden de argumenten achter de uitzonderingsopties begegevens weergegeven:

- **Controle door derden** - Een product of software van derden heeft al een adres voor deze aanbeveling- Als u dit type uitvulling kiest, wordt uw blootstellingsscore lager en verhoogt u uw veilige score omdat uw risico is beperkt
- **Alternatieve mitigatie** - Een intern hulpmiddel heeft al een oplossing voor deze aanbeveling: als u dit type rechtvaardiging kiest, wordt uw blootstellingsscore lager en verhoogt u de veilige score omdat uw risico is beperkt
- **Risico geaccepteerd:** een laag risico en/of het implementeren van de aanbeveling is te duur
- **Geplande herstel (respijt)** - Al gepland, maar wacht op uitvoering of autorisatie

## <a name="view-all-exceptions"></a>Alle uitzonderingen weergeven

Ga naar het **tabblad Uitzonderingen** op **de pagina** Herstel. U kunt filteren op uitvulling, type en status.

 Selecteer een uitzondering om een flyout te openen met meer informatie. Uitzonderingen per apparatengroep hebben een lijst met elke apparaatgroep die de uitzonderingsdekking heeft, die u kunt exporteren. U kunt ook de gerelateerde aanbeveling bekijken of de uitzondering annuleren.

![Het tabblad Uitzonderingen weergeven op de pagina Herstel.](images/tvm-exception-view.png)

## <a name="how-to-cancel-an-exception"></a>Een uitzondering annuleren

Als u een uitzondering wilt annuleren, gaat u naar het tabblad **Uitzonderingen** op de **pagina** Herstel. Selecteer de uitzondering.

Als u de uitzondering voor alle apparaatgroepen of voor een algemene uitzondering wilt annuleren, selecteert u de knop Uitzondering **annuleren voor alle apparaatgroepen.** U kunt alleen uitzonderingen annuleren voor apparaatgroepen waar u machtigingen voor hebt.

![De knop Annuleren.](images/tvm-exception-cancel.png)

### <a name="cancel-the-exception-for-a-specific-device-group"></a>De uitzondering voor een specifieke apparaatgroep annuleren

Selecteer de specifieke apparaatgroep om de uitzondering te annuleren. Er wordt een flyout weergegeven voor de apparaatgroep en u kunt **Uitzondering annuleren selecteren.**

![Hier wordt weergegeven hoe u een specifieke apparaatgroep selecteert.](images/tvm-exception-device-group-hover.png)

## <a name="view-impact-after-exceptions-are-applied"></a>Impact weergeven nadat uitzonderingen zijn toegepast

Selecteer op de pagina  Beveiligingsaanbevelingen de optie Kolommen aanpassen en schakel de selectievakjes Voor Blootgestelde apparaten **(na uitzonderingen)** en **Impact (na uitzonderingen) in.**

![Opties voor kolommen aanpassen weergeven.](images/tvm-after-exceptions.png)

In de kolom Blootgestelde apparaten (na uitzonderingen) worden de overige apparaten getoond die nog steeds aan beveiligingsproblemen worden blootgesteld nadat uitzonderingen zijn toegepast. Uitzonderingsgronden die van invloed zijn op de blootstelling, zijn onder meer 'third party control' en 'alternate mitigation'. Andere redenen beperken de blootstelling van een apparaat niet en worden nog steeds als blootgesteld beschouwd.

Het effect (na uitzonderingen) toont de resterende invloed op de blootstellingsscore of de veilige score nadat uitzonderingen zijn toegepast. Uitzonderingsuitvullingen die van invloed zijn op de scores zijn 'third party control' en 'alternate mitigation'. Andere rechtvaardigingen beperken de blootstelling van een apparaat niet, zodat de belichtingsscore en de veilige score niet veranderen.

![De kolommen in de tabel weergeven.](images/tvm-after-exceptions-table.png)

## <a name="related-topics"></a>Verwante onderwerpen

- [Overzicht van bedreigings- en kwetsbaarheidsbeheer](next-gen-threat-and-vuln-mgt.md)
- [Beveiligingslekken herstellen](tvm-remediation.md)
- [Beveiligingsaanbevelingen](tvm-security-recommendation.md)
- [Blootstellingsscore](tvm-exposure-score.md)
- [Microsoft Secure Score voor apparaten](tvm-microsoft-secure-score-devices.md)
