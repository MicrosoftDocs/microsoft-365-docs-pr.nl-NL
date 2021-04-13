---
title: Problemen met de integratie van SIEM-hulpprogramma's oplossen in Microsoft Defender voor Eindpunt
description: Problemen oplossen die zich kunnen voordoen bij het gebruik van SIEM-hulpprogramma's met Microsoft Defender voor Eindpunt.
keywords: probleemoplossing, siem, clientgeheim, geheim
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 60220d00ca1b612564b72103b9206e3d6d89dc60
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689447"
---
# <a name="troubleshoot-siem-tool-integration-issues"></a>Problemen met de integratie van SIEM-hulpprogramma's oplossen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

Mogelijk moet u problemen oplossen tijdens het trekken van detecties in uw SIEM-hulpprogramma's.

Deze pagina bevat gedetailleerde stappen om problemen op te lossen die u mogelijk ondervindt.


## <a name="learn-how-to-get-a-new-client-secret"></a>Meer informatie over het krijgen van een nieuw clientgeheim
Als uw clientgeheim verloopt of als u de verstrekte kopie verkeerd hebt geplaatst wanneer u de siem-hulpprogrammatoepassing inschakelen, moet u een nieuw geheim krijgen.

1. Meld u aan bij [de Azure-beheerportal.](https://portal.azure.com)

2. Selecteer **Azure Active Directory**.

3. Selecteer uw tenant.

4. Klik **op App-registraties.** Selecteer vervolgens in de lijst met toepassingen de toepassing.

5. Selecteer **de** sectie Sleutels en geef vervolgens een sleutelbeschrijving op en geef de geldigheidsduur van de sleutel op.

6. Klik op **Opslaan**. De sleutelwaarde wordt weergegeven.

7. Kopieer de waarde en sla deze op een veilige plaats op.


## <a name="error-when-getting-a-refresh-access-token"></a>Fout bij het verkrijgen van een vernieuwingstoegangs token
Als u een fout ondervindt bij het gebruik van de hulpprogramma's threat intelligence API of SIEM, moet u antwoord-URL toevoegen voor relevante toepassing in Azure Active Directory.

1. Meld u aan bij [de Azure-beheerportal.](https://ms.portal.azure.com)

2. Selecteer **Azure Active Directory**.

3. Selecteer uw tenant.

4. Klik **op App-registraties.** Selecteer vervolgens in de lijst met toepassingen de toepassing.

5. Voeg de volgende URL toe:
   - Voor de Europese Unie: `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`
   - Voor het Verenigd Koninkrijk: `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`
   - Voor de Verenigde Staten:  `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback` .
 
6. Klik op **Opslaan**.

## <a name="error-while-enabling-the-siem-connector-application"></a>Fout bij het inschakelen van de SIEM-verbindingstoepassing
Als er een fout is opgetreden bij het inschakelen van de SIEM-verbindingstoepassing, controleert u de pop-upblokkeringsinstellingen van uw browser. Mogelijk wordt het nieuwe venster geblokkeerd wanneer u de functie inschakelen.




>Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshootsiem-belowfoldlink) 

## <a name="related-topics"></a>Verwante onderwerpen
- [SIEM-integratie inschakelen in Microsoft Defender voor Eindpunt](enable-siem-integration.md)
- [ArcSight configureren om Microsoft Defender te gebruiken voor eindpuntdetecties](configure-arcsight.md)
- [Detecties naar uw SIEM-hulpprogramma's trekken](configure-siem.md)
- [Microsoft Defender voor eindpuntdetectievelden](api-portal-mapping.md)
- [Microsoft Defender voor eindpuntdetecties trekken met REST API](pull-alerts-using-rest-api.md)
