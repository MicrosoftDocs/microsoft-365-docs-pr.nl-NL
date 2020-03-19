---
title: Windows 10 Enterprise implementeren voor nieuwe apparaten met Windows Autopilot
description: Biedt richtlijnen voor het configureren en implementeren van Windows 10 Enterprise met Windows Autopilot.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365-documentatie, Windows 10 Enterprise, implementatie, Windows Autopilot
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2018
f1.keywords:
- NOCSH
ms.author: greglin
ms.openlocfilehash: ba5804d3065dcb01d85d457df7555a642d6f2839
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42807295"
---
# <a name="step-3-deploy-windows-10-enterprise-for-new-devices-with-windows-autopilot"></a>Stap 3: Windows 10 Enterprise implementeren voor nieuwe apparaten met Windows Autopilot

*Dit artikel is van toepassing op zowel de E3- als de E5-versies van Microsoft 365 Enterprise*

![Fase 3: Windows 10 Enterprise](../media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Als u nieuwe Windows 10-pc's hebt, u Windows Autopilot gebruiken om de out-of-box-experience (OOBE) voor uw organisatie aan te passen en een nieuw systeem te implementeren met apps en instellingen die al zijn geconfigureerd. Er zijn geen afbeeldingen te implementeren, geen drivers te injecteren, en geen infrastructuur te beheren. Gebruikers kunnen het implementatieproces zelfstandig doorlopen, zonder dat ze hun IT-beheerder hoeven te raadplegen.

U nieuwe Windows 10-apparaten instellen en vooraf configureren en ze klaarmaken voor productief gebruik met Windows Autopilot. Zie [Overzicht van Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-Autopilot/windows-10-Autopilot)voor meer informatie over Windows Autopilot, inclusief voordelen en Windows Autopilot-scenario's. Volg deze onderdelen wanneer u klaar bent om nieuwe apparaten in te stellen.

## <a name="the-windows-autopilot-deployment-process-poster"></a>De poster voor het implementatieproces van Windows Autopilot

De Windows Autopilot poster is twee pagina's in portretmodus (11x17). Klik op de afbeelding hieronder om een PDF in uw browser te bekijken. 

[![Windows 10 implementeren met Autopilot-poster](../media/windows10-deploy-autopilot/windows10-autopilot-flowchart.png)](https://docs.microsoft.com/windows/deployment/media/Windows10AutopilotFlowchart.pdf)

U deze poster ook downloaden in [PDF-](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10AutopilotFlowchart.pdf) of [Visio-indeling.](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10Autopilotflowchart.vsdx)

## <a name="part-1-start-windows-autopilot-deployment"></a>Deel 1: Windows Autopilot-implementatie starten
Zie [Overzicht van Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-Autopilot/windows-10-Autopilot) om:

1. Meer informatie over en voltooien van de vereisten voor windows autopilot-implementatie. De voorwaarden zijn onder meer:
    - **Apparaatregistratie en OOBE-aanpassing**

        Om apparaten te registreren, moet u hun hardware-ID aanschaffen en deze registreren. We werken actief samen met verschillende hardwareleveranciers om hen in staat te stellen de vereiste informatie aan u te verstrekken of namens u te uploaden. U hebt ook de mogelijkheid om deze informatie zelf vast te leggen met behulp van een PowerShell-script dat een CSV-bestand genereert met de hardware-id van het apparaat.

        Zodra apparaten zijn geregistreerd, zijn er OOBE-aanpassingsopties die u configureren, waaronder het overslaan van privacy-instellingen en EULA.

    - **Bedrijfsbranding voor OOBE**

        Hiermee u branding toevoegen om te verschijnen tijdens apparaat OOBE.

    - **MDM-automatische inschrijving in Microsoft Intune**
        
        Met automatische inschrijving kunnen gebruikers hun Windows 10-apparaten inschrijven in Intune voor apparaatbeheer wanneer ze hun apparaten verbinden met Azure AD. Als u zich wilt inschrijven, voegen gebruikers hun werkaccount toe aan hun persoonlijke apparaten of nemen ze deel aan apparaten die eigendom zijn van bedrijven in Azure AD. Op de achtergrond is het apparaat ook ingeschreven voor beheer met Intune.

    - **Netwerkconnectiviteit met cloudservices die worden gebruikt door Windows Autopilot**

        Het Windows Autopilot Deployment Program maakt gebruik van een aantal cloudservices om uw apparaten productief te maken en deze services moeten toegankelijk zijn vanaf apparaten die zijn geregistreerd als Windows Autopilot-apparaten. 

    - **Apparaten moeten vooraf zijn geïnstalleerd met Windows 10, versie 1703 of hoger**

2. Meer informatie over en selecteer het Windows Autopilot Deployment Program voor uw organisatie. U kiezen uit deze implementatieprogramma's:
    - **Microsoft Store voor Bedrijven**
    - **Microsoft Intune**
    - **Partnercentrum**

## <a name="part-2-set-up-a-windows-10-device-for-microsoft-365"></a>Deel 2: Een Windows 10-apparaat instellen voor Microsoft 365
Voordat u Windows-apparaten voor Microsoft 365-gebruikers instellen, moet u ervoor zorgen dat alle Windows-apparaten Windows 10, versie 1703 (Creators Update) of hoger gebruiken.

Nadat alle Windows-apparaten in uw organisatie zijn geüpgraded naar Windows 10 Creators Update of al Windows 10 Creators Update hebben uitgevoerd, u deze apparaten aansluiten bij de Azure Active Directory van uw organisatie.

### <a name="set-up-a-brand-new-or-newly-upgraded-windows-10-device"></a>Een gloednieuw of nieuw verbeterd Windows 10-apparaat instellen
Volg deze stappen om een apparaat in te stellen met de Windows 10 OOBE op een gloednieuw apparaat met Windows 10 Creators Update (of hoger) of op een apparaat dat is geüupgradet naar Windows 10 Creators Update (of hoger), maar niet is uitgevoerd door out-of-box setup.

1. Als u geen draadloos netwerk hebt geconfigureerd, moet u het apparaat via een bekabelde of Ethernet-verbinding met het internet verbinden.
2. Ga door de Windows-apparaatinstallatie-ervaring. Op een nieuw of opnieuw ingesteld apparaat begint de installatie-ervaring met de **regio Laten we beginnen met regio. Klopt dit?** Scherm.
3. Doorloop de apparaatinstellingen voor Windows 10 totdat u de pagina **Hoe wilt u instellen?** op uw scherm ziet. Selecteer hier **Instellen voor een organisatie**.
4. Meld u aan met het account en wachtwoord van de Microsoft 365-gebruiker. Afhankelijk van de instelling van het gebruikerswachtwoord wordt u mogelijk gevraagd het wachtwoord bij te werken. 
5. Voltooi de apparaatinstellingen voor Windows 10.

Nadat u klaar bent, wordt het apparaat verbonden met het Azure AD van uw organisatie.

### <a name="set-up-a-device-that-has-already-completed-out-of-box-setup"></a>Een apparaat instellen dat de installatie buiten de doos al heeft voltooid
Als uw apparaat Windows 10 Creators Update (of hoger) heeft en al de out-of-box-installatie heeft doorlopen, voert u deze stappen uit.

1. Selecteer op de Windows-pc van uw gebruiker waarop Windows 10, versie 1703 (Creators Update) wordt uitgevoerd, het **Windows-logo** en selecteer vervolgens het pictogram **Instellingen.**
2. Ga in **Instellingen** naar **Accounts**
3. Selecteer op de pagina **Uw info** de optie Werk **of school** > **verbinding maken**.
4. Selecteer in het dialoogvenster **Een werk- of schoolaccount instellen** onder **Alternatieve acties**de optie Dit apparaat deelnemen aan Azure **Active Directory**.
5. Voer op de **pagina Laten we je aan- en aan-huis,** voer je werk- of schoolaccount in en selecteer **Volgende**.
6. Voer **op** de pagina Wachtwoord invoeren uw wachtwoord in en selecteer **Aanmelden**.
7. Controleer op de pagina **Controleren of dit uw organisatie is,** of de gegevens juist zijn en selecteer **Deelnemen**.
8. Op de **You're all set!** pagina, selecteer **Gereed**.

Nadat u klaar bent, wordt de gebruiker verbonden met het Azure AD van uw organisatie.

### <a name="verify-the-device-is-connected-to-azure-ad"></a>Controleren of het apparaat is verbonden met Azure AD
Volg deze stappen om de synchronisatiestatus van het apparaat met Azure AD te verifiëren en vervolgens uw Microsoft 365-account op het apparaat te gebruiken. 

1. **Instellingen openen**.
2. Selecteer **op** de pagina Toegang werk of school het gebied Verbonden **met <organization name> ** de knoppen **Info** en **Verbreken**.
3. Selecteer **Info** om uw synchronisatiestatus op te halen.
4. Selecteer **op** de pagina Synchronisatie de optie **Synchroniseren** om het nieuwste beleid voor het beheer van mobiele apparaten op de pc te krijgen.
5. Als u het Microsoft 365-account wilt gebruiken, gaat u naar de knop **Windows Start,** klikt u met de rechtermuisknop op de afbeelding van uw huidige account en selecteert u **Switch-account.**
6. Meld u aan met het e-mailadres en wachtwoord van uw organisatie.

Als u problemen ondervindt bij het gebruik van Windows 10 in een bedrijfsomgeving, u [de belangrijkste Microsoft Support-oplossingen raadplegen voor de meest voorkomende problemen.](https://docs.microsoft.com/windows/client-management/windows-10-support-solutions) Deze bronnen omvatten KB-artikelen, updates en bibliotheekartikelen.

Als tussencontrolepunt ziet u de [exitcriteria](windows10-exit-criteria.md#crit-windows10-step3) die overeenkomen met deze stap.

## <a name="next-step"></a>Volgende stap

|||
|:-------|:-----|
|![Stap 4](../media/stepnumbers/Step4.png)| [De status en naleving van het apparaat controleren](windows10-enable-windows-analytics.md) |
