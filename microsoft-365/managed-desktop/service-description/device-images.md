---
title: Afbeeldingen van apparaten
description: Afbeeldingsvereisten bij het bestellen van nieuwe apparaten of het hergebruiken van bestaande apparaten
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
ms.openlocfilehash: 211e26035ad8bdf73defde85c33a631af3a193d0
ms.sourcegitcommit: 17d82e5617f0466eb825e15ab88594afcdaf4437
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/06/2021
ms.locfileid: "53300101"
---
# <a name="device-images"></a>Afbeeldingen van apparaten


Of u nu nieuwe [](#existing-devices) [apparaten bestelt](#new-devices) of bestaande apparaten opnieuw gebruikt, u hebt verschillende opties om ervoor te zorgen dat de afbeelding op het apparaat voldoet aan onze [apparaatvereisten.](device-requirements.md#check-hardware-requirements)

## <a name="new-devices"></a>Nieuwe apparaten
Wanneer u een nieuw [](device-requirements.md#minimum-requirements)apparaat bij een goedgekeurde fabrikant bestelt, volgt u deze stappen om ervoor te zorgen dat ze apparaten verzenden met de juiste Microsoft Managed Desktop afbeelding en softwareconfiguratie. Wanneer u van plan bent een bepaald apparaatmodel voor de eerste keer in te schrijven in de service, moet u een voorbeeld testen om ervoor te zorgen dat het de gebruikerservaring biedt die u verwacht. Zie Nieuwe apparaten [valideren voor meer informatie.](/microsoft-365/managed-desktop/get-started/validate-device)

### <a name="dell"></a>Dell
Werk rechtstreeks samen met de vertegenwoordiger van Dell, die ervoor zorgt dat de afbeelding die is goedgekeurd door Microsoft Managed Desktop wordt toegepast op apparaten voor uw bestelling. Neem voor meer vragen over Dell-apparaten, de afbeelding en het bestelproces contact op met MMD_at_dell@dell.com.

### <a name="hp"></a>HP 
Wanneer u nieuwe apparaten bij HP [bestelt,](https://www.microsoft.com/windowsforbusiness/view-all-devices#view-all-filter) moet u de specifieke SKU gebruiken die wordt vermeld in de sectie Aanvullende vereisten voor elk model dat wordt gevonden op de site Met zakelijke apparaten winkelen Windows 10 Pro (filter de weergave om de Microsoft Managed Desktop-apparaten weer te geven).

Als u een apparaat bestelt bij HP dat [](customizing.md) als uitzondering is goedgekeurd, maar momenteel niet wordt weergegeven op de pagina Apparaatlijst, moet u de SKU vragen om voor uw model te worden gebruikt. We werken samen met HP om u deze informatie te geven met behulp van uw uitzonderingsaanvraag. U kunt ook rechtstreeks contact opnemen met HP voor vragen over apparaten en instructies voor het bestellen van apparaten met behulp van deze adressen:
 
- Amerika: mmd-americas@hp.com
- Europa/Midden-Oosten/Afrika: mmd-emea@hp.com
- Asia Pacific/Japan: mmd-apj@hp.com
- Globaal: mmd@hp.com

### <a name="lenovo"></a>Lenovo
Wanneer u apparaten bij Lenovo bestelt voor gebruik in Microsoft Managed Desktop, moet u een specifiek onderdeelnummer aangeven dat deel uitmaakt van de bestelling. Neem contact op met uw vertegenwoordiger van Lenovo of Lenovo Channel Partner en vraag hen om een *speciaal* biedmodel te maken met een systeem dat voldoet aan onze [apparaatvereisten.](device-requirements.md#minimum-requirements) Als u een vooraf geladen afbeelding wilt opnemen die compatibel is met Microsoft Managed Desktop, vraagt u de verkoper om te verwijzen naar het nummer *SBB0Q94938 - MMD Enablement* van het systeemgebouw.

De volgende producten zijn momenteel ingeschakeld voor Microsoft Managed Desktop ondersteuning:

- L13 Gen 1
- L13 Yoga Gen 1
- L14 Gen 1 (Intel)
- L14 Gen 1 (AMD)
- L15 Gen 1 (Intel)
- L15 Gen 1 (AMD)
- X1 Carbon Gen 8
- X1 Yoga Gen 5
- T14 Gen 1 (Intel)
- T14 Gen 1 (AMD)
- T15 Gen 1
- X13 Gen 1 (Intel)


### <a name="microsoft"></a>Microsoft
Alle Microsoft-apparaten die voldoen aan apparaatvereisten, hebben een afbeelding die werkt met Microsoft Managed Desktop. Er zijn geen andere stappen vereist.

Als u de nieuwste afbeelding in de fabriek op een Microsoft-apparaat wilt hebben, werkt u samen met uw Surface-specialist om het Surface-proces 'Gepengeerde PO' te gebruiken.

## <a name="existing-devices"></a>Bestaande apparaten

U kunt bestaande apparaten opnieuw gebruiken zolang ze voldoen aan zowel de [apparaatvereisten](device-requirements.md#minimum-requirements) als de [softwarevereisten.](device-requirements.md#installed-software) Volg de stappen die relevant zijn voor uw fabrikant.

U kunt apparaten opnieuw maken met een afbeelding van de fabrikant of met de Microsoft Managed Desktop 'universele afbeelding'. Als u een geschikte fabrikantafbeelding wilt krijgen, kunt u ten minste één nieuw apparaat bestellen [van](#new-devices) het model dat u opnieuw gebruikt. Vervolgens kunt u de afbeelding van dat apparaat verkrijgen en deze toepassen op andere apparaten van exact hetzelfde model.

> [!NOTE]
> U bent verantwoordelijk voor het maken, testen en implementeren van afbeeldingen. We raden u ook aan waar mogelijk de juiste afbeeldingen van de fabrikant te gebruiken in plaats van aangepaste afbeeldingen, inclusief de 'universele afbeelding'.

### <a name="hp"></a>HP

Commerciële HP-pc's die zijn verzonden met de HP Corporate Ready Image, bevatten een . WIM-bestand voor herstel. U kunt deze afbeelding gebruiken om de fabrieksherstelafbeelding toe te passen op andere apparaten van hetzelfde model.

Met deze stappen worden alle gegevens op het apparaat verwijderd, dus voordat u begint, moet u een back-up maken van alle gegevens die u wilt bewaren.

1. [Maak een opstartbaar USB-station](/windows-hardware/manufacture/desktop/winpe-create-usb-bootable-drive) met WinPE.
2. Kopieer deze bestanden van C: \\ BRONNEN naar het USB-station:
    - Het WIM-bestand voor fabrieksherstel (bijvoorbeeld HP \_ EliteBook \_ 840 \_ G7 \_ Notebook PC CR \_ \_ \_ 2004.wim)
    - IMPLEMENTEREN. CMD
    - ReCreatePartitions.txt
3. [Het apparaat opstarten op WinPE](https://store.hp.com/us/en/tech-takes/how-to-boot-from-usb-drive-on-windows-10-pcs) USB-station.
4. Voer in een opdrachtprompt [Diskpart.exe. ](/windows-server/administration/windows-commands/diskpart#additional-references)
5. Voer in Diskpart het nummer van de primaire opslagschijf `list disk` (meestal Schijf 0) uit.
6. Sluit Diskpart af door te `exit` typen.
7. Voer in de opdrachtprompt uit , waarbij sys_disk het schijfnummer is van de primaire opslagschijf die u zojuist hebt bepaald en recovery_wim de bestandsnaam van de `deploy.cmd <sys_disk> <recovery_wim>` .   WIM-bestand dat u eerder hebt gekopieerd.
8. Verwijder het USB-station en start het apparaat opnieuw.

### <a name="microsoft"></a>Microsoft 

Microsoft Surface-apparaten bevatten afbeeldingen met 'bare metal recovery' [die](https://support.microsoft.com/en-us/surfacerecoveryimage) specifiek zijn voor elk model. U kunt deze afbeeldingen gebruiken om apparaten opnieuw te maken.

Deze afbeeldingen gebruiken de Windows Herstelomgeving (WinRE) en dit is een handmatig proces (niet geautomatiseerd). Volg de stappen in [Het maken en gebruiken van een USB-herstelstation voor Surface.](https://support.microsoft.com/surface/creating-and-using-a-usb-recovery-drive-for-surface-677852e2-ed34-45cb-40ef-398fc7d62c07)


### <a name="universal-image"></a>Universele afbeelding
Microsoft Managed Desktop heeft een afbeelding gemaakt met Windows 10 Pro en Microsoft 365-apps voor Enterprise die u kunt gebruiken met Microsoft Managed Desktop. U kunt echter het beste afbeeldingen gebruiken die geschikt zijn voor Microsoft Managed Desktop die door de fabrikant worden geleverd, zelfs als dat een oudere Windows-versie betekent die vervolgens moet worden bijgewerkt zodra de gebruiker zich aandient. Het gebruik Microsoft Managed Desktop universele afbeelding moet een laatste optie zijn.

- We werken de afbeelding bij met Windows maandelijkse kwaliteitsupdates om de 30-60 dagen en Microsoft 365-apps voor Enterprise-updates ten minste twee keer per jaar.
- De afbeelding bevat een herstel inrichtingspakket om ervoor te zorgen dat Microsoft 365-apps enterprise wordt hersteld na Windows herstelscenario's.
- U kunt de afbeelding implementeren met USB-stations. Het bevat een scriptable proces voor het invoegen van stuurprogramma's (beschreven in de documentatie die bij de afbeelding is opgenomen).
- U kunt de opgenomen scripts en mappen wijzigen voor gebruik met andere aanpassingen, zoals het toevoegen van specifieke cumulatieve updates, het kopiëren van bestanden of het uitvoeren van andere controles.
- Stuurprogramma's en kwaliteitsupdates worden toegevoegd aan Windows tijdens de implementatie vanaf het USB-station.

> [!NOTE]
> Het is uw verantwoordelijkheid om alle benodigde stuurprogramma's toe te voegen, alle tests uit te voeren en ervoor te zorgen dat er geen problemen zijn met de uiteindelijk geïmplementeerde afbeelding. We bieden de universele afbeelding 'as-is' maar bieden technische richtlijnen en beantwoorden vragen. Contact MMDImage@microsoft.com.

Verzend aanvragen voor de universele afbeeldingsinhoud en -documentatie door een wijzigingsaanvraag te maken op de [beheerportal.](../get-started/access-admin-portal.md)


