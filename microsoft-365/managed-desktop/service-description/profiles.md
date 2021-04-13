---
title: Apparaatprofielen begrijpen
description: De verschillende profielen die beheerders aan apparaten kunnen toewijzen
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: e6b0c96d4e145a2e5df7c7555e262aefe891e483
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690617"
---
# <a name="device-profiles"></a>Apparaatprofielen

U kunt verschillende vooraf ingesteld configuraties ('apparaatprofielen') toewijzen aan apparaten, die elk zijn geoptimaliseerd voor de behoeften van specifieke typen gebruikers. Er zijn drie apparaatprofielen beschikbaar:

- Standard
- Gevoelige gegevens
- Power-gebruiker

U kunt apparaatprofielen zien als onderdeel van een hiërarchie van apparaatconfiguratieopties.

:::image type="content" source="../../media/mmd-profile-options-heirarchy.png" alt-text="Apparaatconfiguraties die worden weergegeven als een piramide. Beschrijving volgt":::

In principe heeft elk Microsoft Managed Desktop-apparaat een basis die een standaard beveiligingslijn, compliancebeleid, Windows Update-instellingen en groepen bevat. Als u wilt werken met Beheerd bureaublad van Microsoft, moet elk apparaat al deze elementen bevatten, die niet kunnen worden gewijzigd door beheerders zonder een aanvraag voor Microsoft Managed Desktop.

Apparaatprofielen worden weergegeven op het volgende hogere niveau. Aan elk Microsoft Managed Desktop-apparaat moet één (en slechts één) profiel zijn toegewezen. Beheerders kunnen kiezen welk profiel aan een apparaat is toegewezen.

Op een nog hoger niveau zijn extra [aanpassingen.](customizing.md) Elk apparaat kan een of meer (of geen) aanpassingen hebben. Ze kunnen een laag op een lager niveau (apparaatprofielen of de basisconfiguratie) wijzigen of een geheel nieuwe aanvraag zijn die boven op de standaardconfiguratie wordt gelegd.

Bovenaan staan uw eigen wijzigingen, zoals netwerkdetails of toepassingen. Een apparaat kan een aantal van deze wijzigingen hebben, die niet worden beheerd of geblokkeerd door Microsoft Managed Desktop.


## <a name="device-profile-details"></a>Apparaatprofielgegevens

De volgende tabel bevat een overzicht van de instellingen en de standaardwaarden voor elke instelling die is geconfigureerd met apparaatprofielen. (Achter de schermen worden deze instellingen geconfigureerd met OMA-URIs aangepaste configuratieprofielen in Microsoft Endpoint Manager.)

| Functie | Gevoelige gegevens | Power User | Standard |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------|------------------------|-----------------------|
| **Externe opslag blokkeren**                                                                                                                               | Ja                       | Ja                   | Nee                   |
| **[Cloudblokniveau](https://docs.microsoft.com/graph/api/resources/intune-deviceconfig-defendercloudblockleveltype)** | Hoog                      | Hoog                  | Hoog                 |
| **Microsoft-accounts uitschakelen**                                                                                                                           | Ja                       | Ja                   | Nee                   |
| **Persoonlijke OneDrive uitschakelen**                                                                                                                            | Ja                       | Ja                   | Nee                   |
| **Overschakelen naar een beveiligd bureaublad voor hoogte**                                                                                                               | Nee                        | Ja                   | Nee                   |
| **Microsoft Defender voor Endpoint Device Tag**                                                                                                           | M365Managed-SensitiveData | M365Managed-PowerUser | M365Managed-Standard |
| **Beheerder op het apparaat?**                                                                                                                                 | Nee                        | Ja                   | Nee                   |
| **Autopilot-profiel**                                                                                                                                     | MMD-standaard               | MMD Power User         | MMD-standaard          |
| **AppLocker**                                                                                                                                            | Ja                       | Nee                    | Nee                   |
| **Openbare winkel blokkeren**                                                                                                                                   | Ja                       | Ja                   | Nee                   |

Elk apparaatprofiel bevat ook de volgende items:

- Een AAD-apparaatgroep (Dynamic Membership Azure Active Directory)
- Een statische AAD-apparaatgroep voor lidmaatschap
- Een Configuratieprofiel van Microsoft Endpoint Manager

> [!IMPORTANT]
> Wijzig het lidmaatschap van deze groepen niet rechtstreeks. Gebruik de interface zoals beschreven in [Profielen opnieuw toewijzen.](../working-with-managed-desktop/change-device-profile.md)

## <a name="limitations"></a>Beperkingen

U kunt uitzonderingen op de apparaatprofielen en hun gegevens aanvragen, net zoals bij elk ander beleid. Houd er rekening mee dat u slechts één van elk apparaatprofiel in uw Azure Active Directory-organisatie ("tenant") kunt hebben. U kunt bijvoorbeeld niet aanvragen dat appLocker voor slechts enkele gebruikers wordt uitgeschakeld door het profiel van het gevoelige gegevensapparaat. Alle apparaten met het profiel Gevoelige gegevens moeten dezelfde configuratie hebben.

Elk apparaat kan slechts één profiel hebben. Als een bepaald apparaat door meer dan één gebruiker wordt gebruikt, hebben alle gebruikers op dat apparaat dezelfde configuratie.
