---
title: Microsoft Teams
description: Hoe Teams wordt geïnstalleerd op apparaten en daarna wordt bijgewerkt
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie, apps, line-of-business-apps, LOB-apps
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: ITPro
ms.openlocfilehash: 01a3adc7829bbb94f36649f69ba6ef15dbe6b3c2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920654"
---
# <a name="microsoft-teams"></a>Microsoft Teams

[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) is een [berichten-app](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) voor uw organisatie die ook een werkruimte biedt voor realtime samenwerking en communicatie, vergaderingen en het delen van bestanden en apps.

## <a name="initial-deployment"></a>Eerste implementatie

De meeste hardwareleveranciers bevatten Teams nog niet als onderdeel van hun afbeeldingen, dus Microsoft Managed Desktop implementeert Teams apparaten met behulp van Microsoft Intune. Op alle beheerde apparaten [is het Teams .msi](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) geïnstalleerd, zodat alle gebruikers die zich aanmelden bij een apparaat, Microsoft Teams klaar zijn voor gebruik. Wanneer het pakket voor het eerst is geïnstalleerd, Teams automatisch gestart en wordt er een snelkoppeling toegevoegd aan het bureaublad.

### <a name="microsoft-intune-changes"></a>Microsoft Intune wijzigingen

Microsoft Managed Desktop voegt twee toepassingen toe aan uw Azure AD-organisatie voor Microsoft Teams. Ze worden geïmplementeerd voor 64-bits of 32-bits clients, zoals geschikt voor het apparaat:  

- Moderne werkplek : Teams Machine Wide Installer x64  
- Moderne werkplek : Teams Machine Wide Installer x32

## <a name="updates"></a>Updates

Teams volgt een afzonderlijk updatepad van Microsoft 365-apps voor ondernemingen en wordt de bureaubladclient automatisch bijgewerkt. Teams controleert om de paar uur op updates, downloadt ze en wacht totdat de computer inactief is voordat u de update in stilte installeert.  

De Teams productgroep staat beheerders niet toe updates te beheren, dus Microsoft Managed Desktop het standaardkanaal voor automatische [update gebruikt.](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating)

### <a name="manually-updating-teams"></a>Handmatig bijwerken van Teams

Afzonderlijke gebruikers kunnen ook updates downloaden door **Controleren op updates** te selecteren in de    ****   vervolgkeuzelijst Profiel rechtsboven in de app. Als er een update beschikbaar is, wordt deze gedownload en geruisloos geïnstalleerd wanneer de computer inactief is.

## <a name="delivery-optimization-of-updates"></a>Leveringsoptimalisatie van updates

Leveringsoptimalisatie Teams updates is standaard ingeschakeld en vereist geen actie van beheerders of gebruikers.