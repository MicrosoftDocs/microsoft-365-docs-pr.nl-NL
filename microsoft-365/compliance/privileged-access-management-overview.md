---
title: Meer informatie over Privileged Access Management
description: In dit artikel vindt u een overzicht van bevoorrecht toegangsbeheer in Microsoft 365, inclusief antwoorden op veelgestelde vragen (veelgestelde vragen).
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
f1.keywords:
- NOCSH
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.openlocfilehash: 059e1653d7db9140dbc80fd69fe36e95a744b079
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/06/2021
ms.locfileid: "52161687"
---
# <a name="learn-about-privileged-access-management"></a>Meer informatie over Privileged Access Management

Met bevoorrecht toegangsbeheer kunt u gedetailleerde toegangsbeheer over bevoorrechte beheertaken in Office 365. Het kan uw organisatie helpen beschermen tegen inbreuken die gebruikmaken van bestaande bevoorrechte beheerdersaccounts met permanente toegang tot gevoelige gegevens of toegang tot kritieke configuratie-instellingen. Voor bevoorrecht toegangsbeheer moeten gebruikers just-in-time toegang aanvragen om verhoogde en geprivilegieerde taken te voltooien via een zeer bereik en tijdgebonden goedkeuringswerkstroom. Deze configuratie biedt gebruikers net voldoende toegang om de taak bij de hand uit te voeren, zonder dat ze risico lopen op blootstelling van gevoelige gegevens of kritieke configuratie-instellingen. Door het inschakelen van bevoorrecht toegangsbeheer in Microsoft 365 kan uw organisatie werken met nul staande bevoegdheden en een verdedigingslaag bieden tegen permanente beveiligingslekken voor beheerderstoegang.

Zie deze video over Customer Lockbox en privileged access management voor een kort overzicht van de geïntegreerde werkstroom Customer Lockbox en [privileged access management.](https://go.microsoft.com/fwlink/?linkid=2066800)

## <a name="layers-of-protection"></a>Lagen van beveiliging

Bevoorrecht toegangsbeheer vormt een aanvulling op andere gegevens- en toegangsfunctiebeveiligingen binnen de Microsoft 365 beveiligingsarchitectuur. Het gebruik van bevoorrecht toegangsbeheer als onderdeel van een geïntegreerde en gelaagde beveiligingsbenadering biedt een beveiligingsmodel dat de bescherming van gevoelige informatie en Microsoft 365 configuratie-instellingen maximaliseert. Zoals wordt weergegeven in het diagram, wordt het bevoorrechte toegangsbeheer gebaseerd op de bescherming die wordt geboden met native versleuteling van Microsoft 365-gegevens en het beveiligingsmodel voor toegangscontrole op basis van rollen van Microsoft 365 services. Wanneer deze twee [functies](/azure/active-directory/active-directory-privileged-identity-management-configure)worden gebruikt Privileged Identity Management Azure AD-Privileged Identity Management, bieden deze twee functies toegangsbeheer met just-in-time toegang tot verschillende bereiken.

![Gelaagde beveiliging in Microsoft 365](../media/pam-layered-protection.png)

Bevoorrecht toegangsbeheer is  gedefinieerd en is een bereik op taakniveau, terwijl Azure AD Privileged Identity Management beveiliging op rollenniveau met de mogelijkheid om meerdere taken uit te voeren.  Azure AD Privileged Identity Management in de eerste plaats het beheren van toegangen voor AD-rollen en -rollengroepen, terwijl het beheer van geprivilegieerde toegang in Microsoft 365 alleen op taakniveau van toepassing is.

- **Bevoorrecht toegangsbeheer inschakelen terwijl u Azure AD-Privileged Identity Management:** Het toevoegen van bevoorrecht toegangsbeheer biedt een andere gedetailleerde laag beveiligings- en auditmogelijkheden voor bevoorrechte toegang tot Microsoft 365 gegevens.

- **Azure AD-Privileged Identity Management inschakelen terwijl u al bevoorrecht toegangsbeheer gebruikt in Office 365:**  Als u Azure AD-Privileged Identity Management voor bevoorrecht toegangsbeheer toevoegt, kan de bevoorrechte toegang worden uitgebreid tot gegevens buiten Microsoft 365 die hoofdzakelijk worden gedefinieerd door gebruikersrollen of identiteiten.  

## <a name="privileged-access-management-architecture-and-process-flow"></a>Architectuur en processtroom met bevoorrecht toegangsbeheer

Elk van de volgende processtromen beschrijft de architectuur van bevoorrechte toegang en de interactie met de substraat Microsoft 365 substraat, auditing en de Exchange management runspace.

### <a name="step-1-configure-a-privileged-access-policy"></a>Stap 1: Een beleid voor geprivilegieerde toegang configureren

Wanneer u een beleid voor geprivilegieerde toegang configureert met het Microsoft 365-beheercentrum [of](https://admin.microsoft.com) het Exchange Management PowerShell, definieert u het beleid en de bevoorrechte toegangsfunctieprocessen en de beleidskenmerken in de Microsoft 365 substraat. De activiteiten worden geregistreerd in het Beveiligings &amp; compliancecentrum. Het beleid is nu ingeschakeld en klaar om binnenkomende aanvragen voor goedkeuringen te verwerken.

![Stap 1: Beleidscreatie](../media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a>Stap 2: Access-aanvraag

In het [Microsoft 365 beheercentrum](https://admin.microsoft.com) of met Exchange Management PowerShell kunnen gebruikers toegang aanvragen tot verhoogde of bevoorrechte taken. Met de functie voor bevoorrechte toegang wordt de aanvraag naar het substraat Microsoft 365 voor verwerking met het geconfigureerde toegangsbeleid voor bevoegdheden en worden de activiteiten in de logboeken van het Beveiligings &amp; compliancecentrum opgeslagen.

![Stap 2: Access-aanvraag](../media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a>Stap 3: Goedkeuring van Access

Er wordt een goedkeuringsaanvraag gegenereerd en de melding van de aanvraag in behandeling wordt per e-mail verzonden naar goedkeurders. Als dit is goedgekeurd, wordt de aanvraag voor geprivilegieerde toegang verwerkt als een goedkeuring en is de taak gereed om te worden voltooid. Als de taak wordt geweigerd, wordt de taak geblokkeerd en wordt er geen toegang verleend aan de indiener van de aanvraag. De aanmelder wordt via een e-mailbericht op de hoogte gesteld van de goedkeuring of weigering van de aanvraag.

![Stap 3: Goedkeuring van Access](../media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a>Stap 4: Access-verwerking

Voor een goedgekeurde aanvraag wordt de taak verwerkt door de Exchange Runspace Management. De goedkeuring wordt gecontroleerd op basis van het beleid voor bevoorrechte toegang en wordt verwerkt door Microsoft 365 substraat. Alle activiteiten voor de taak worden geregistreerd in het Beveiligings &amp; compliancecentrum.

![Stap 4: Access-verwerking](../media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a>Veelgestelde vragen

### <a name="what-skus-can-use-privileged-access-in-office-365"></a>Welke SKU's kunnen geprivilegieerde toegang gebruiken in Office 365?

Privileged access management is beschikbaar voor klanten voor een breed scala aan Microsoft 365 en Office 365 en invoegtoepassingen. Zie [Aan de slag met bevoorrecht toegangsbeheer](privileged-access-management-configuration.md) voor meer informatie.

### <a name="when-will-privileged-access-support-office-365-workloads-beyond-exchange"></a>Wanneer worden bevoorrechte toegangsrechten Office 365 werkbelastingen buiten Exchange?

Bevoorrecht toegangsbeheer is binnenkort beschikbaar in andere Office 365 werkbelastingen. Ga naar [Microsoft 365 routekaart voor](https://www.microsoft.com/microsoft-365/roadmap) meer informatie.

### <a name="my-organization-needs-more-than-30-privileged-access-policies-will-this-limit-be-increased"></a>Mijn organisatie heeft meer dan 30 beleidsregels voor geprivilegieerde toegang nodig, wordt deze limiet dan verhoogd?

Ja, het verhogen van de huidige limiet van 30 beleidsregels voor bevoorrechte toegang per organisatie staat op de routekaart voor functies.

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a>Moet ik een globale beheerder zijn om geprivilegieerde toegang te beheren in Office 365?

Nee, u hebt de rol Exchange rollenbeheer die is toegewezen aan accounts die geprivilegieerde toegang beheren in Office 365. Als u de rol Rollenbeheer niet wilt configureren als een op zichzelf staand accountmachtiging, bevat de rol Globale beheerder deze rol standaard en kan u bevoorrechte toegang beheren. Gebruikers die deel uit maken van een groep goedkeurders hoeven geen globale beheerder te zijn of de rol Rollenbeheer te hebben toegewezen om aanvragen met PowerShell te controleren en goed te keuren.

### <a name="how-is-privileged-access-management-related-to-customer-lockbox"></a>Hoe is privileged access management gerelateerd aan Customer Lockbox?

[Customer Lockbox](/office365/admin/manage/customer-lockbox-requests) biedt een niveau van toegangsbeheer voor organisaties wanneer Microsoft toegang heeft tot gegevens. Bevoorrecht toegangsbeheer biedt gedetailleerde toegangsbeheer binnen een organisatie voor alle Microsoft 365 bevoorrechte taken.

## <a name="ready-to-get-started"></a>Klaar om aan de slag te gaan?

Start [met het configureren van uw organisatie voor bevoorrecht toegangsbeheer.](privileged-access-management-configuration.md)

## <a name="learn-more"></a>Meer informatie

[Interactieve handleiding: beheerderstaken bewaken en beheren met bevoorrecht toegangsbeheer](https://content.cloudguides.com/guides/Privileged%20Access%20Management)
