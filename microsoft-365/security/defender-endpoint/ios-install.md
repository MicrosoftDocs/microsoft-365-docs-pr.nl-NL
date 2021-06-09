---
title: App-implementatie voor Microsoft Defender voor Eindpunt op iOS
ms.reviewer: ''
description: Beschrijft hoe u Microsoft Defender voor Eindpunt implementeert in iOS met een app
keywords: microsoft, defender, Microsoft Defender for Endpoint, ios, app, installation, deploy, uninstallation, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 371208433cbb0f65ab5a2808318c03dae6bb6d8b
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842292"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-ios"></a>Microsoft Defender voor eindpunt implementeren in iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

In dit onderwerp wordt beschreven hoe u Defender voor Eindpunt implementeert op iOS op Intune-bedrijfsportal geregistreerde apparaten. Zie [IOS/iPadOS-apparaten registreren in Intune](/mem/intune/enrollment/ios-enroll)voor meer informatie over intune-apparaatinschrijvingen.

## <a name="before-you-begin"></a>Voordat u begint

- Zorg ervoor dat u toegang hebt tot [het Beheercentrum voor Microsoft Endpoint Manager.](https://go.microsoft.com/fwlink/?linkid=2109431)

- Zorg ervoor dat iOS-registratie is gedaan voor uw gebruikers. Gebruikers moeten een Defender voor Eindpunt-licentie hebben toegewezen om Defender voor Eindpunt in iOS te kunnen gebruiken. Raadpleeg [Licenties toewijzen aan gebruikers voor](/azure/active-directory/users-groups-roles/licensing-groups-assign) instructies over het toewijzen van licenties.

> [!NOTE]
> Microsoft Defender voor Eindpunt voor iOS is beschikbaar in de [Apple App Store.](https://aka.ms/mdatpiosappstore)

## <a name="deployment-steps"></a>Implementatiestappen

Deploy Defender for Endpoint on iOS via Intune-bedrijfsportal.

### <a name="add-ios-store-app"></a>IOS Store-app toevoegen

1. Ga [in het Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431)naar **Apps**  ->  **iOS/iPadOS**  ->    ->  **IOS Store-app** toevoegen en klik op **Selecteren.**

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager beheercentrum1](images/ios-deploy-1.png)

1. Klik op de pagina App toevoegen op **Zoeken in de App Store** en typ Microsoft **Defender-eindpunt** in de zoekbalk. Klik in de sectie zoekresultaten op *Microsoft Defender-eindpunt en* klik op **Selecteren.**

1. Selecteer **iOS 11.0 als** het besturingssysteem Minimum. Bekijk de rest van de informatie over de app en klik op **Volgende.**

1. Ga in *de sectie Opdrachten* naar de sectie **Vereist** en selecteer **Groep toevoegen.** U kunt vervolgens de gebruikersgroep(s) kiezen die u wilt richten op Defender voor Eindpunt in de iOS-app. Klik **op Selecteren** en vervolgens op **Volgende.**

    > [!NOTE]
    > De geselecteerde gebruikersgroep moet bestaan uit intune geregistreerde gebruikers.

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager beheercentrum2](images/ios-deploy-2.png)

1. Controleer in *de sectie Controleren +* maken of alle ingevoerde gegevens juist zijn en selecteer vervolgens **Maken.** Over een paar minuten moet de Defender voor Eindpunt-app worden gemaakt en wordt er een melding weergegeven in de rechterbovenhoek van de pagina.

1. Selecteer op de pagina met app-informatie die wordt weergegeven in de sectie Monitor de **status** apparaatinstallatie om te controleren of de installatie van het apparaat is voltooid. 

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager beheercentrum3](images/ios-deploy-3.png)

## <a name="auto-onboarding-of-vpn-profile-simplified-onboarding"></a>Auto-Onboarding van VPN-profiel (Vereenvoudigde onboarding)

Beheerders kunnen de automatische installatie van VPN-profiel configureren. Hiermee wordt het VPN-profiel van Defender voor Eindpunt automatisch ingesteld zonder dat de gebruiker dit hoeft te doen tijdens onboarding. Houd er rekening mee dat VPN wordt gebruikt om de functie Webbeveiliging te bieden. Dit is geen gewone VPN en is een lokale/self-looping VPN die geen verkeer buiten het apparaat neemt.

1. Ga [in het Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431)naar Profiel maken van   ->    ->  **apparatenconfiguratieprofielen.**
1. Kies **Platform** als **iOS/iPadOS** en **Profieltype** als **VPN.** Klik op **Maken**.
1. Typ een naam voor het profiel en klik op **Volgende.**
1. Selecteer **Aangepaste VPN** voor verbindingstype en voer in de sectie Base **VPN** het volgende in:
    - Naam van verbinding = Microsoft Defender voor eindpunt
    - VPN-serveradres = 127.0.0.1
    - Auth method = "Gebruikersnaam en wachtwoord"
    - Splits tunneling = Uitschakelen
    - VPN-id = com.microsoft.scmx
    - Voer in de sleutel-waardeparen de sleutel **AutoOnboard in** en stel de waarde in op **Waar.**
    - Type automatische VPN = ON-demand VPN
    - Klik **op Toevoegen** voor **Regels** op aanvraag en selecteer Ik wil het volgende doen **= VPN** instellen, ik wil beperken tot = Alle **domeinen**.

    ![Een schermafbeelding van vpn-profielconfiguratie](images/ios-deploy-8.png)

1. Klik op Volgende en wijs het profiel toe aan gerichte gebruikers.
1. Controleer in *de sectie Controleren +* maken of alle ingevoerde gegevens juist zijn en selecteer vervolgens **Maken.**

## <a name="complete-onboarding-and-check-status"></a>De onboarding- en controlestatus voltooien

1. Zodra Defender voor Eindpunt op iOS is geïnstalleerd op het apparaat, ziet u het app-pictogram.

    ![Een schermafbeelding van een beschrijving van een smartphone die automatisch wordt gegenereerd](images/41627a709700c324849bf7e13510c516.png)

2. Tik op het pictogram van de Defender voor eindpunt-app (MSDefender) en volg de instructies op het scherm om de onboarding-stappen uit te voeren. De details omvatten de acceptatie door eindgebruikers van iOS-machtigingen die vereist zijn door Defender voor Eindpunt in iOS.

3. Na succesvolle onboarding wordt het apparaat weergegeven in de lijst Apparaten in Microsoft Defender-beveiligingscentrum.

    > [!div class="mx-imgBorder"]
    > ![Een schermafbeelding van een beschrijving van een mobiele telefoon die automatisch wordt gegenereerd](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)

## <a name="configure-microsoft-defender-for-endpoint-for-supervised-mode"></a>Microsoft Defender voor eindpunt configureren voor modus onder toezicht

De Microsoft Defender for Endpoint-app voor iOS heeft een speciale mogelijkheid op gecontroleerde iOS-/iPadOS-apparaten, gezien de verbeterde beheermogelijkheden die het platform biedt op dit type apparaten. Als u van deze mogelijkheden wilt profiteren, moet de Defender voor Eindpunt-app weten of een apparaat in de modus Onder toezicht staat.

### <a name="configure-supervised-mode-via-intune"></a>Modus onder toezicht configureren via Intune

Met Intune kunt u de Defender voor iOS-app configureren via een beleid voor app-configuratie.

   > [!NOTE]
   > Dit app-configuratiebeleid voor apparaten met toezicht is alleen van toepassing op beheerde apparaten en moet als beste zijn gericht op alle beheerde iOS-apparaten.

1. Meld u aan bij het [Microsoft Endpoint Manager beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) en ga naar **Het configuratiebeleid** voor Apps  >  **App**  >  **Toevoegen.** Klik op **Beheerde apparaten.**

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager beheercentrum4](images/ios-deploy-4.png)

1. Geef op *de pagina Configuratiebeleid voor* apps maken de volgende informatie op:
    - Naam van beleid
    - Platform: selecteer iOS/iPadOS
    - Targeted app: Selecteer **Microsoft Defender Endpoint** in de lijst

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager beheercentrum5](images/ios-deploy-5.png)

1. Selecteer configuratieontwerper gebruiken als **opmaak** in het volgende scherm. Geef de volgende eigenschap op:
    - Configuratiesleutel: wordt onder toezicht
    - Waardetype: tekenreeks
    - Configuratiewaarde: {{issupervised}}
    
    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager beheercentrum6](images/ios-deploy-6.png)

1. Klik **op Volgende** om de pagina **Bereiklabels te** openen. Bereiklabels zijn optioneel. Klik **op Volgende om** door te gaan.

1. Selecteer op **de pagina** Opdrachten de groepen die dit profiel ontvangen. Voor dit scenario is het de beste manier om alle apparaten **te targeten.** Zie Gebruikers- en apparaatprofielen toewijzen voor meer informatie over het toewijzen [van profielen.](/mem/intune/configuration/device-profile-assign)

   Bij het implementeren naar gebruikersgroepen moet een gebruiker zich aanmelden bij een apparaat voordat het beleid van toepassing is.

   Klik op **Volgende**.

1. Kies op **de pagina Controleren +** maken de optie Maken als u klaar **bent.** Het nieuwe profiel wordt weergegeven in de lijst met configuratieprofielen.

1. Vervolgens kunt u een aangepast profiel implementeren op de gecontroleerde iOS-apparaten voor uitgebreide anti-phishing-mogelijkheden. Volg de onderstaande stappen:
    - Het config-profiel downloaden van [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)
    - Ga naar **Apparaten**  ->  **iOS/iPadOS-configuratieprofielen**  ->    ->  **Profiel maken**

    > [!div class="mx-imgBorder"]
    > ![Afbeelding van Microsoft Endpoint Manager beheercentrum7](images/ios-deploy-7.png)

    - Geef een naam op van het profiel. Wanneer u wordt gevraagd een configuratieprofielbestand te importeren, selecteert u het profiel dat hierboven is gedownload.
    - Selecteer in **de** sectie Toewijzing de apparaatgroep waarop u dit profiel wilt toepassen. Dit moet worden toegepast op alle beheerde iOS-apparaten. Klik op **Volgende**.
    - Kies op **de pagina Controleren +** maken de optie Maken als u klaar **bent.** Het nieuwe profiel wordt weergegeven in de lijst met configuratieprofielen.

## <a name="next-steps"></a>Volgende stappen

[Defender voor eindpunt configureren voor iOS-functies](ios-configure-features.md)
