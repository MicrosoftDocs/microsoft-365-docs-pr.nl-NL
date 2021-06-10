---
title: Windows 10 locatieservice
description: Locatieservices voor uw apparaten Windows ingeschakeld
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
ms.openlocfilehash: 210356dd21b36efbb27d8faa4f8616145584159c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929476"
---
# <a name="windows-10-location-service"></a>Windows 10 locatieservice

Apparaten in Microsoft Managed Desktop worden geregistreerd met behulp van Windows Autopilot. Met dit proces kunnen we ze beheren met Azure Active Directory en Microsoft Intune. Standaard is de Windows 10-locatieservice uitgeschakeld wanneer een apparaat voor het eerst is ingeschakeld, tenzij deze functie is ingeschakeld in de Privacy-instellingen tijdens de 'out-of-box-ervaring'. Deze instellingen zijn verborgen tijdens de autopilot-inschrijving in Microsoft Managed Desktop. Zie [First-run experience with Autopilot and the Enrollment Status Page](esp-first-run.md)voor meer informatie over hoe Autopilot is ingesteld.

Daarom kunnen Microsoft Managed Desktop apparaten hun apparaatlocatie niet verkrijgen, waardoor de functionaliteit van verschillende Windows functies, zoals tijdzones, wordt beperkt. Voor meer informatie over de Windows 10 locatieservice, [zie Windows 10 locatieservice en privacy.](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)

U hoeft de locatieservice niet te gebruiken om deel te nemen aan Microsoft Managed Desktop, maar de gebruikerservaring wordt beperkt. Apparaten kunnen bijvoorbeeld niet automatisch bepalen in welke tijdzone ze zich bevindt wanneer uw gebruikers in een andere tijdzone werken.

## <a name="enable-the-location-service"></a>De locatieservice inschakelen

U kunt zich aanmelden voor het gebruik van de locatieservice wanneer u apparaten inschrijft voor de Microsoft Managed Desktop-service of u kunt de service in- of uitschakelen na de registratie.

### <a name="opt-in-during-enrollment"></a>Aanmelden tijdens inschrijving

U kunt de Microsoft Managed Desktop de locatieservice inschakelen. Tijdens de inschrijvingsreeks wordt u gevraagd te selecteren of u wilt toestaan dat de Windows 10 locatieservice op apparaten is ingeschakeld.

### <a name="control-the-location-service-after-enrollment"></a>De locatieservice na inschrijving bepalen

U kunt de locatieservice op elk moment in- of uitschakelen door een [ondersteuningsaanvraag](../working-with-managed-desktop/admin-support.md) in te dienen via de [beheerportal.](access-admin-portal.md)

## <a name="how-microsoft-managed-desktop-configures-the-windows-10-location-service"></a>Hoe Microsoft Managed Desktop de locatieservice Windows 10 configureren

Als u ervoor kiest om de locatieservice te gebruiken, gebruiken we de minimale instellingen die nodig zijn zonder dat dit van invloed is op de privacy van gebruikers. Zie voor meer informatie [Windows 10 locatieservice en privacy.](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)

Microsoft Managed Desktop de **privacyinstelling Locatie** in Windows **instellingen in staat** om toegang tot locatie op dit apparaat toe te **staan.** De gebruikersinterface ziet er als volgende uit:

 :::image type="content" source="../../media/MMD-location-services-UI.png" alt-text="Locatie-instellingen in Windows instellingen":::

> [!NOTE]
> Als u ervoor kiest om de locatieservice te gebruiken, geldt dit alleen voor het Windows besturingssysteem zelf. Apps zijn niet toegestaan om locatieservices te gebruiken. Elke gebruiker kan kiezen of apps toegang mogen krijgen tot hun locatie.