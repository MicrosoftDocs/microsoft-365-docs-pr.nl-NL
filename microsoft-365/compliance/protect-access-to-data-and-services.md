---
title: Toegang van gebruikers en apparaten beveiligen
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/17/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: Informatie over het beveiligen van gebruikers- en apparaattoegang tot Microsoft 365 en services en beschermen tegen gegevensverlies.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9ff7bd2ff8b4b333eb30a6cc82797a8968941e0b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "52162275"
---
# <a name="protect-user-and-device-access"></a>Toegang van gebruikers en apparaten beveiligen

De toegang tot uw Microsoft 365 en services is van cruciaal belang om u te beschermen tegen cyberaanvallen en om te beschermen tegen gegevensverlies. Dezelfde beveiligingen kunnen worden toegepast op andere SaaS-toepassingen in uw omgeving en zelfs op on-premises toepassingen die zijn gepubliceerd met Azure Active Directory Application Proxy.
  
## <a name="step-1-review-recommendations"></a>Stap 1: Aanbevelingen controleren

Aanbevolen mogelijkheden voor het beschermen van identiteiten en apparaten die toegang krijgen tot Office 365, andere SaaS-Services en on-premises toepassingen die worden gepubliceerd met de Azure AD-toepassingsproxy.
  
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656)  |  [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657)  |  [Meer talen](https://www.microsoft.com/download/details.aspx?id=55032)
  
## <a name="step-2-protect-administrator-accounts-and-access"></a>Stap 2: Beheerdersaccounts en toegang beveiligen
De beheeraccounts die u gebruikt om uw Microsoft 365 beheren, bevatten verhoogde bevoegdheden. Dit zijn waardevolle doelen voor hackers en cyberattackers. 

Gebruik eerst alleen beheerdersaccounts voor beheer. Beheerders moeten een afzonderlijk gebruikersaccount hebben voor regelmatig, niet-administratief gebruik en hun beheeraccount alleen gebruiken wanneer dat nodig is om een taak te voltooien die is gekoppeld aan hun functie.

Bescherm uw beheerdersaccounts met meervoudige verificatie en voorwaardelijke toegang. Zie Beheerdersaccounts beveiligen voor [meer informatie.](../security/defender-365-security/identity-access-prerequisites.md#protecting-administrator-accounts) 

Configureer vervolgens het beheer van geprivilegieerde toegang in Office 365. Met bevoorrecht toegangsbeheer kunt u gedetailleerde toegangsbeheer over bevoorrechte beheertaken in Office 365. Het kan uw organisatie helpen beschermen tegen inbreuken die bestaande bevoorrechte beheerdersaccounts kunnen gebruiken met permanente toegang tot gevoelige gegevens of toegang tot kritieke configuratie-instellingen.

- [Overzicht van bevoorrecht toegangsbeheer](privileged-access-management-overview.md)
- [Bevoorrecht toegangsbeheer configureren](privileged-access-management-configuration.md)

Een andere topaanbeveling is het gebruik van werkstations die speciaal zijn geconfigureerd voor beheerwerk. Dit zijn speciale apparaten die alleen worden gebruikt voor beheertaken. Zie [Geprivilegieerde toegang beveiligen.](/windows-server/identity/securing-privileged-access/securing-privileged-access)

Ten slotte kunt u de impact van onbedoelde afwezigheid van beheerderstoegang beperken door twee of meer accounts voor toegang voor noodgevallen te maken in uw tenant. Zie [Accounts voor toegang voor noodgevallen beheren in Azure AD](/azure/active-directory/users-groups-roles/directory-emergency-access). 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a>Stap 3: Aanbevolen identiteits- en apparaattoegangsbeleid configureren
Multi-factor authentication (MFA) en beleid voor voorwaardelijke toegang zijn krachtige hulpprogramma's om gecompromitteerde accounts en ongeautoriseerde toegang te voorkomen. We raden u aan een set beleidsregels te implementeren die samen zijn getest. Zie Identiteits- en [apparaattoegangsconfiguraties](../security/defender-365-security/microsoft-365-policies-configurations.md)voor meer informatie, inclusief implementatiestappen.

 Met dit beleid worden de volgende mogelijkheden geïmplementeerd:
- Mult-factor-verificatie
- Voorwaardelijke toegang
- Intune-appbeveiliging (app en gegevensbescherming voor apparaten)
- Intune-apparaat compliance
- Azure AD Identity Protection

Voor het implementeren van intune-apparaat compliance is apparaatinschrijving vereist. Als u apparaten beheert, kunt u ervoor zorgen dat ze gezond en compatibel zijn voordat u ze toegang geeft tot resources in uw omgeving. Zie [Apparaten voor beheer registreren in Intune](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)

## <a name="step-4-configure-sharepoint-device-access-policies"></a>Stap 4: Beleid SharePoint apparaattoegang configureren

Microsoft raadt u aan om inhoud op SharePoint sites te beveiligen met gevoelige en sterk gereguleerde inhoud met besturingselementen voor apparaattoegang. Zie Beleidsaanbevelingen voor het beveiligen van SharePoint [sites en bestanden voor meer informatie.](../security/defender-365-security/sharepoint-file-access-policies.md)



