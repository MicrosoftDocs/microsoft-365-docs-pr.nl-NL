---
title: Voorwaardelijke toegang configureren in Microsoft Defender voor eindpunt
description: Meer informatie over de stappen die u moet uitvoeren in Intune, Microsoft Defender-beveiligingscentrum azure om voorwaardelijke toegang te implementeren
keywords: voorwaardelijke toegang, voorwaardelijke toegang, toegang, apparaatrisico, risiconiveau, integratie, intune-integratie
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ceb69d59dc5208c0908e33d0880d9352562ec140
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843972"
---
# <a name="configure-conditional-access-in-microsoft-defender-for-endpoint"></a>Voorwaardelijke toegang configureren in Microsoft Defender voor eindpunt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

In deze sectie wordt u begeleid bij alle stappen die u moet uitvoeren om Voorwaardelijke toegang correct te implementeren.

### <a name="before-you-begin"></a>Voordat u begint
>[!WARNING]
>Het is belangrijk om te weten dat geregistreerde Azure AD-apparaten in dit scenario niet worden ondersteund.</br>
>Alleen aangemelde Intune-apparaten worden ondersteund.


U moet ervoor zorgen dat al uw apparaten zijn geregistreerd in Intune. U kunt een van de volgende opties gebruiken om apparaten in te schrijven in Intune:


- IT-beheerder: Zie Windows [Enrollment](/intune/windows-enroll#enable-windows-10-automatic-enrollment) voor meer informatie over het inschakelen van automatische inschrijving
- Eindgebruiker: Zie Uw Windows 10 in Intune registreren voor meer informatie over het registreren van uw Windows 10 apparaat [in Intune](/intune/quickstart-enroll-windows-device)
- Alternatief voor eindgebruikers: Zie How to: Plan your Azure AD join implementation (Uw [Azure AD join-implementatie](/azure/active-directory/devices/azureadjoin-plan)plannen) voor meer informatie over het deelnemen aan een Azure AD-domein.



Er zijn stappen die u moet uitvoeren in Microsoft Defender-beveiligingscentrum, de Intune-portal en de Azure AD-portal.

Het is belangrijk om de vereiste rollen op te merken om toegang te krijgen tot deze portals en Voorwaardelijke toegang te implementeren:
- **Microsoft Defender-beveiligingscentrum:** u moet zich aanmelden bij de portal met een globale beheerdersrol om de integratie in te zetten.
- **Intune:** u moet zich aanmelden bij de portal met beveiligingsbeheerdersrechten met beheermachtigingen. 
- **Azure AD-portal:** u moet zich aanmelden als globale beheerder, beveiligingsbeheerder of beheerder van voorwaardelijke toegang.


> [!NOTE]
> U hebt een Microsoft Intune nodig, met intune beheerde en Azure AD-Windows 10 apparaten.

Ga als volgt te werk om Voorwaardelijke toegang in te stellen:
- Stap 1: Schakel de Microsoft Intune verbinding in Microsoft Defender-beveiligingscentrum
- Stap 2: De integratie van Defender voor eindpunten in Intune in-
- Stap 3: Het compliancebeleid maken in Intune
- Stap 4: Het beleid toewijzen 
- Stap 5: Een Azure AD-beleid voor voorwaardelijke toegang maken


### <a name="step-1-turn-on-the-microsoft-intune-connection"></a>Stap 1: De Microsoft Intune in
1. Selecteer in het navigatiedeelvenster **Instellingen**  >  **Geavanceerde functies Microsoft Intune**  >  **verbinding.**
2. Schakel de instelling Microsoft Intune in op **Aan**.
3. Klik **op Voorkeuren opslaan.**


### <a name="step-2-turn-on-the-defender-for-endpoint-integration-in-intune"></a>Stap 2: De integratie van Defender voor eindpunten in Intune in-
1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Apparaat compliance**  >  **Microsoft Defender ATP.**
3. Stel **Verbinding maken Windows 10.0.15063+** apparaten in op Microsoft Defender Advanced Threat Protection op **Aan.**
4. Klik op **Opslaan**.


### <a name="step-3-create-the-compliance-policy-in-intune"></a>Stap 3: Het compliancebeleid maken in Intune
1. Selecteer in [de Azure-portal](https://portal.azure.com) **Alle services**, filter op **Intune** en selecteer **Microsoft Intune.**
2. Selecteer **Apparaat**  >  **compliancebeleid Beleid**  >  **maken**.
3. Voer een **naam en** **beschrijving in.**
4. Selecteer **in Platform** de Windows 10 en **hoger.**
5. Stel in **de instellingen voor** Apparaattoestand De instelling Vereisen dat het apparaat zich op of onder het **apparaatrisiconiveau** op het gewenste niveau moet hebben ingesteld:

   - **Beveiligd:** dit niveau is het veiligst. Het apparaat kan geen bestaande bedreigingen hebben en heeft nog steeds toegang tot bedrijfsresources. Als er bedreigingen worden gevonden, wordt het apparaat geëvalueerd als niet-compatibel.
   - **Laag:** Het apparaat voldoet als er alleen bedreigingen op laag niveau zijn. Apparaten met een gemiddeld of hoog bedreigingsniveau voldoen niet.
   - **Medium:** Het apparaat voldoet als de bedreigingen op het apparaat laag of gemiddeld zijn. Als er bedreigingen op hoog niveau worden gedetecteerd, wordt het apparaat bepaald als niet-compatibel.
   - **Hoog:** Dit niveau is het minst veilig en staat alle bedreigingsniveaus toe. Apparaten met een hoog, gemiddeld of laag bedreigingsniveau worden dus als compatibel beschouwd.

6. Selecteer **OK** en Maken **om** uw wijzigingen op te slaan (en het beleid te maken).

### <a name="step-4-assign-the-policy"></a>Stap 4: Het beleid toewijzen
1. Selecteer in [de Azure-portal](https://portal.azure.com) **Alle services**, filter op **Intune** en selecteer **Microsoft Intune.**
2. Selecteer **Apparaat**  >  **compliancebeleid>** microsoft Defender voor endpoint compliancebeleid te selecteren.
3. Kies **Opdrachten**.
4. Neem uw Azure AD-groepen op of sluit deze uit om ze het beleid toe te wijzen.
5. Als u het beleid wilt implementeren voor de groepen, selecteert u **Opslaan.** De gebruikersapparaten die het doel zijn van het beleid, worden geëvalueerd op naleving.

### <a name="step-5-create-an-azure-ad-conditional-access-policy"></a>Stap 5: Een Azure AD-beleid voor voorwaardelijke toegang maken
1. Open in [de Azure-portal](https://portal.azure.com) **het Azure Active Directory**  >  **Voorwaardelijke toegang** nieuw  >  **beleid**.
2. Voer een **beleidsnaam in** en selecteer **Gebruikers en groepen.** Gebruik de opties Opnemen of Uitsluiten om uw groepen toe te voegen voor het beleid en selecteer **Klaar.**
3. Selecteer **Cloud-apps** en kies welke apps u wilt beveiligen. Kies bijvoorbeeld Apps **selecteren** en selecteer Office 365 SharePoint **Online** en **Office 365 Exchange Online.** Selecteer **Klaar om** uw wijzigingen op te slaan.

4. Selecteer **Voorwaarden**  >  **Client-apps om** het beleid toe te passen op apps en browsers. Selecteer bijvoorbeeld **Ja** en schakel vervolgens **Browser-** en **Mobiele apps en bureaubladcl clients in.** Selecteer **Klaar om** uw wijzigingen op te slaan.

5. Selecteer **Verlenen om** Voorwaardelijke toegang toe te passen op basis van apparaat compliance. Selecteer bijvoorbeeld Toegang verlenen **Apparaat vereisen** dat apparaat moet worden gemarkeerd  >  **als compatibel**. Kies **Selecteren om** uw wijzigingen op te slaan.

6. Selecteer **Beleid inschakelen** en vervolgens **Maken om** uw wijzigingen op te slaan.

Zie Naleving afdwingen voor Microsoft Defender voor Eindpunt met [Voorwaardelijke toegang in Intune](/intune/advanced-threat-protection)voor meer informatie.

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-belowfoldlink)
