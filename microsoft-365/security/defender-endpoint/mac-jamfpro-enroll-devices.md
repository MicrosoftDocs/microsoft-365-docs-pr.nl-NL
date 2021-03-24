---
title: Microsoft Defender ATP voor macOS-apparaten registreren bij Jamf Pro
description: Microsoft Defender ATP voor macOS-apparaten registreren bij Jamf Pro
keywords: microsoft, defender, atp, mac, installatie, implementeren, verwijderen, intune, jamfpro, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4dcaa8063ea11ab2ca43330a761783fead829d3e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060086"
---
# <a name="enroll-microsoft-defender-for-endpoint-for-macos-devices-into-jamf-pro"></a>Microsoft Defender voor eindpunt voor macOS-apparaten registreren bij Jamf Pro 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="enroll-macos-devices"></a>MacOS-apparaten registreren

Er zijn meerdere methoden om u te laten inschrijven bij JamF.

In dit artikel worden twee methoden beschreven:

- [Methode 1: Uitnodigingen voor inschrijving](#enrollment-method-1-enrollment-invitations)
- [Methode 2: Inschrijving vooraf](#enrollment-method-2-prestage-enrollments)

Zie Over [computerinschrijving](https://docs.jamf.com/9.9/casper-suite/administrator-guide/About_Computer_Enrollment.html)voor een volledige lijst.


## <a name="enrollment-method-1-enrollment-invitations"></a>Inschrijvingsmethode 1: Uitnodigingen voor inschrijving

1. Navigeer in het dashboard Van Jamf Pro naar **Uitnodigingen voor inschrijving.**

    ![Afbeelding van configuratie-instellingen1](images/a347307458d6a9bbfa88df7dbe15398f.png)

2. Selecteer **+ Nieuw**.

    ![Een close-up van een automatisch gegenereerde logobeschrijving](images/b6c7ad56d50f497c38fc14c1e315456c.png)

3. Voer **in Geadresseerden opgeven voor** de > onder **E-mailadressen** het e-mailadres(es) van de geadresseerden in.

    ![Afbeelding van configuratie-instellingen2](images/718b9d609f9f77c8b13ba88c4c0abe5d.png)

    ![Afbeelding van configuratie-instellingen3](images/ae3597247b6bc7c5347cf56ab1e820c0.png)

    Bijvoorbeeld: janedoe@contoso.com

    ![Afbeelding van configuratie-instellingen4](images/4922c0fcdde4c7f73242b13bf5e35c19.png)

4. Configureer het bericht voor de uitnodiging.

    ![Afbeelding van configuratie-instellingen5](images/ce580aec080512d44a37ff8e82e5c2ac.png)

    ![Afbeelding van configuratie-instellingen6](images/5856b765a6ce677caacb130ca36b1a62.png)

    ![Afbeelding van configuratie-instellingen7](images/3ced5383a6be788486d89d407d042f28.png)

    ![Afbeelding van configuratie-instellingen8](images/54be9c6ed5b24cebe628dc3cd9ca4089.png)

## <a name="enrollment-method-2-prestage-enrollments"></a>Inschrijvingsmethode 2: Inschrijving vooraf

1. Navigeer in het Dashboard van Jamf Pro naar **Inschrijvingen vooraf.**

    ![Afbeelding van configuratie-instellingen9](images/6fd0cb2bbb0e60a623829c91fd0826ab.png)

2. Volg de instructies in [Computer PreStage Enrollments](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html).

## <a name="enroll-macos-device"></a>MacOS-apparaat registreren

1. Selecteer **Doorgaan** en installeer het CA-certificaat in een **venster Systeemvoorkeuren.**

    ![Afbeelding van de registratie van Jamf Pro1](images/jamfpro-ca-certificate.png)

2. Nadat het CA-certificaat is geïnstalleerd, gaat u terug naar het browservenster en **selecteert u Doorgaan** en installeert u het MDM-profiel. 

    ![Afbeelding van de registratie van Jamf Pro2](images/jamfpro-install-mdm-profile.png)

3. Selecteer **Toestaan** om te downloaden van JAMF.

    ![Afbeelding van de registratie van Jamf Pro3](images/jamfpro-download.png)

4. Selecteer **Doorgaan om** door te gaan met de installatie van het MDM-profiel. 

    ![Afbeelding van de registratie van Jamf Pro4](images/jamfpro-install-mdm.png)

5. Selecteer **Doorgaan** om het MDM-profiel te installeren.

    ![Afbeelding van de registratie van Jamf Pro5](images/jamfpro-mdm-unverified.png)

6. Selecteer **Doorgaan**  om de configuratie te voltooien. 

    ![Afbeelding van de registratie van Jamf Pro6](images/jamfpro-mdm-profile.png)
