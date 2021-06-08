---
title: Host firewall reporting in Microsoft Defender for Endpoint
description: Firewallrapportage hosten en weergeven in Microsoft 365 beveiligingscentrum.
keywords: Windows Defender, firewall
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 0289d6f920fd6ff35fd446f9c2b8c5516883a4d2
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809253"
---
# <a name="host-firewall-reporting-in-microsoft-defender-for-endpoint"></a>Host firewall reporting in Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Als u een beheerder bent, kunt u nu firewallrapportage hosten [Microsoft 365 beveiligingscentrum.](https://security.microsoft.com) Met deze functie kunt u de Windows 10 en Windows Server 2019-firewallrapportage bekijken vanaf een gecentraliseerde locatie. 

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint? 

- U moet server 2019 Windows 10 of Windows uitvoeren.
- Als u apparaten wilt onboarden bij de Microsoft Defender for Endpoint-service, zie [hier](onboard-configure.md). 
- Als Microsoft 365 beveiligingscentrum de gegevens wilt ontvangen, moet u **Auditgebeurtenissen** inschakelen Windows Defender Firewall geavanceerde beveiliging: 
    - [Controlefilterplatformpakket neerzetten](/windows/security/threat-protection/auditing/audit-filtering-platform-packet-drop)
    - [Audit Filtering Platform Connection](/windows/security/threat-protection/auditing/audit-filtering-platform-connection) 
- Schakel deze gebeurtenissen in met groepsbeleidsobjecteditor, lokaal beveiligingsbeleid of de auditpol.exe opdrachten. Zie hier voor meer [informatie.](/windows/win32/fwp/auditing-and-logging) 
    - De twee PowerShell-opdrachten zijn:
        - **auditpol /set /subcategorie:"Filtering Platform Packet Drop" /failure:enable** 
        - **auditpol /set /subcategorie:"Filterplatformverbinding" /failure:enable** 

## <a name="the-process"></a>Het proces
> [!NOTE]
> Zorg ervoor dat u de instructies uit de bovenstaande sectie volgt en uw apparaten correct configureert voor de eerste preview-deelname.

- Nadat u de gebeurtenissen inschakelen, Microsoft 365 beveiligingscentrum de gegevens controleren.
    - Externe IP, Externe poort, Lokale poort, Lokale IP, Computernaam, Proces tussen binnenkomende en uitgaande verbindingen.
- Beheerders kunnen nu hier Windows hostfirewallactiviteit [zien.](https://security.microsoft.com/firewall)
    - Aanvullende rapportage kan worden vergemakkelijkt door het script Aangepaste rapportage te [downloaden](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) om de Windows Defender Firewall activiteiten met behulp van Power BI. 
    - Het kan tot 12 uur duren voordat de gegevens worden weergegeven.

## <a name="supported-scenarios"></a>Ondersteunde scenario's
De volgende scenario's worden ondersteund tijdens Ring0 Preview. 

### <a name="firewall-reporting-in-security-center"></a>Firewallrapportage in beveiligingscentrum

Hier zijn een paar voorbeelden van de firewallrapportpagina's. Hier vindt u een overzicht van de inkomende, uitgaande en toepassingsactiviteit. U kunt deze pagina rechtstreeks openen door naar https://security.microsoft.com/firewall . 

> [!div class="mx-imgBorder"]
> ![Rapportpagina hostfirewall](\images\host-firewall-reporting-page.png)

U kunt deze rapporten ook openen door naar **Rapporten**  >  **Beveiligingsrapportapparaten**  >   (sectie) te gaan onder aan de **kaart Geblokkeerde** binnenkomende verbindingen van firewall.

### <a name="from-computers-with-a-blocked-connection-to-device"></a>Van 'Computers met een geblokkeerde verbinding' naar apparaat

Kaarten ondersteunen interactieve objecten. U kunt inzoomen op de activiteit van een apparaat door op de naam van het apparaat te klikken, die wordt weergegeven op een nieuw tabblad, en u rechtstreeks naar het tabblad https://securitycenter.microsoft.com **Apparaattijdlijn te** gaan. 

> [!div class="mx-imgBorder"]
> ![Computers met een geblokkeerde verbinding](\images\firewall-reporting-blocked-connection.png)

U kunt nu het tabblad **Tijdlijn** selecteren, waarmee u een lijst krijgt met gebeurtenissen die aan dat apparaat zijn gekoppeld. 

Nadat u op de knop **Filters** in de rechterbovenhoek van het weergavevenster hebt geklikt, selecteert u het type gebeurtenis dat u wilt. Selecteer in dit geval **Firewallgebeurtenissen** en het deelvenster wordt gefilterd op firewallgebeurtenissen. 

> [!div class="mx-imgBorder"]
> ![Knop Filters](\images\firewall-reporting-filters-button.png)

### <a name="drill-into-advanced-hunting-preview-refresh"></a>Inzoomen op geavanceerd zoeken (preview vernieuwen)

Firewallrapporten ondersteunen het boren van de kaart rechtstreeks naar **Geavanceerd zoeken** door op de knop Geavanceerd zoeken **openen te** klikken. De query wordt vooraf ingevuld. 

> [!div class="mx-imgBorder"]
> ![Knop Geavanceerd zoeken openen](\images\firewall-reporting-advanced-hunting.png)

De query kan nu worden uitgevoerd en alle gerelateerde firewallgebeurtenissen van de afgelopen 30 dagen kunnen worden verkend. 

Voor extra rapportages of aangepaste wijzigingen kan de query worden geëxporteerd naar Power BI voor verdere analyse. Aangepaste rapportage kan worden vergemakkelijkt door het script Aangepaste rapportage te [downloaden](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) om de Windows Defender Firewall activiteiten met behulp van Power BI. 

 