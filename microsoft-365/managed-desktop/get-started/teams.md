---
title: Microsoft Teams
description: Hoe teams op apparaten wordt geïnstalleerd en daarna later worden bijgewerkt
keywords: Microsoft Managed Desktop, Microsoft 365, service, Documentatie, apps, line-of-Business-Apps, LOB-apps
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: ITPro
ms.openlocfilehash: ea2ef7637a8d360e3b598aec4852425d977ae4ec
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950915"
---
# <a name="microsoft-teams"></a>Microsoft Teams

[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) is een [Berichten-app](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) voor uw organisatie die ook een werkruimte biedt voor samenwerking in realtime en communicatie, vergaderingen en het delen van bestanden en apps.

## <a name="initial-deployment"></a>Eerste implementatie

Voor de meeste hardwareleveranciers zijn er nog geen teams opgenomen als onderdeel van hun afbeeldingen, zodat Microsoft Managed Desktop teams implementeert op uw apparaten via Microsoft intune. Voor alle beheerde apparaten is het [pakket teams. msi](https://docs.microsoft.com/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) geïnstalleerd, zodat alle gebruikers die zich aanmelden bij een apparaat, al Microsoft teams kunnen gebruiken. Wanneer het pakket eerst is geïnstalleerd, wordt in teams automatisch een snelkoppeling naar het bureaublad toegevoegd.

### <a name="microsoft-intune-changes"></a>Microsoft intune-wijzigingen

Microsoft Managed Desktop voegt twee toepassingen toe aan uw Azure AD-organisatie voor Microsoft teams. Ze worden gedistribueerd naar 64-bits-of 32-bits-clients, wat van toepassing is op het apparaat:  

- Modern Workplace-teams machine Wide Installer x64  
- Modern Workplace: teams-hele Installer x32

## <a name="updates"></a>Updates

Teams volgt een apart update traject in Microsoft 365-apps voor Enterprise en de bureaublad client werkt automatisch. Teams controleert om de paar uur een update voor updates, downloadt ze en vervalt de computer totdat de computer inactief is voordat de update is geïnstalleerd.  

Met de productgroep teams kunnen beheerders geen updates beheren, zodat Microsoft Managed Desktop gebruikmaakt van het [standaardkanaal voor automatische updates](https://docs.microsoft.com/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating).

### <a name="manually-updating-teams"></a>Teams handmatig bijwerken

Individuele gebruikers kunnen ook updates downloaden door **controleren op updates**te selecteren   in de vervolgkeuzelijst **profiel**rechtsboven in   de app. Als er een update beschikbaar is, wordt deze gedownload en op de achtergrond geïnstalleerd wanneer de computer inactief is.

## <a name="delivery-optimization-of-updates"></a>Delivery Optimization-updates

Delivery Optimizing voor team updates is standaard ingeschakeld en is geen actie van beheerders of gebruikers vereist. 