---
title: Nieuwe functies in Microsoft Defender voor Eindpunt op Mac
description: Meer informatie over de belangrijkste wijzigingen voor eerdere versies van Microsoft Defender voor Eindpunt op Mac.
keywords: microsoft, Defender, Microsoft Defender voor Eindpunt, Mac, installatie, macos, whatsnew
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
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
ms.openlocfilehash: 6348d688103c51176fbed36c923a660c77a2258d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842780"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-mac"></a>Nieuwe functies in Microsoft Defender voor Eindpunt op Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> Voor macOS 11 (Big Sur) vereist Microsoft Defender voor Eindpunt extra configuratieprofielen. Als u een bestaande klant bent die upgradet van eerdere versies van macOS, moet u de extra configuratieprofielen implementeren die op [deze pagina worden vermeld.](mac-sysext-policies.md)

## <a name="1012964-20121042129640"></a>101.29.64 (20.121042.12964.0)

- Vanaf deze versie worden bedreigingen die zijn gedetecteerd tijdens on-demand antivirusscans die worden geactiveerd via de opdrachtregelclient, automatisch verwijderd. Bedreigingen die zijn gedetecteerd tijdens scans die via de gebruikersinterface worden geactiveerd, vereisen nog steeds handmatige actie.
- `mdatp diagnostic real-time-protection-statistics` ondersteunt nu twee extra schakelopties:
  - `--sort`: sorteert de uitvoer aflopend op het totale aantal gescande bestanden
  - `--top N`: geeft de hoogste N-resultaten weer (werkt alleen als `--sort` deze ook is opgegeven)
- Prestatieverbeteringen (met name voor wanneer ERWD wordt gebruikt) & oplossingen

## <a name="1012750-20121022127500"></a>101.27.50 (20.121022.12750.0)

- Fix to accommodate for Apple certificate expiration for macOS Catalina and earlier. Met deze oplossing wordt de functionaliteit & Vulnerability Management (TVM) hersteld.

## <a name="1012569-20121022125690"></a>101.25.69 (20.121022.12569.0)

- Microsoft Defender voor Eindpunt op macOS is nu beschikbaar in preview voor klanten van de Amerikaanse overheid. Zie Microsoft [Defender for Endpoint voor klanten](gov.md)van de Amerikaanse overheid voor meer informatie.
- Prestatieverbeteringen (met name voor de situatie waarin de XCode Simulator-app wordt gebruikt) & problemen.

## <a name="1012364-20121021123640"></a>101.23.64 (20.121021.12364.0)

- Er is een nieuwe optie toegevoegd aan het opdrachtregelprogramma om informatie over de laatste scan op aanvraag weer te geven. Als u informatie wilt weergeven over de laatste scan op aanvraag, voer dan `mdatp health --details antivirus`
- Prestatieverbeteringen & oplossingen voor fouten

## <a name="1012279-20121012122790"></a>101.22.79 (20.121012.12279.0)

- Prestatieverbeteringen & oplossingen voor fouten

## <a name="1011988-20121011119880"></a>101.19.88 (20.121011.11988.0)

- Prestatieverbeteringen & oplossingen voor fouten

## <a name="1011948-20120121119480"></a>101.19.48 (20.120121.11948.0)

> [!NOTE]
> De syntaxis van het oude opdrachtregelprogramma is afgeschaft met deze release. Zie Resources voor informatie over de nieuwe [syntaxis.](mac-resources.md#configuring-from-the-command-line)

- Er is een nieuwe opdrachtregelknop toegevoegd om de netwerkextensie uit te schakelen: `mdatp system-extension network-filter disable` . Deze opdracht kan handig zijn om problemen met netwerken op te lossen die kunnen worden gerelateerd aan Microsoft Defender voor Eindpunt op Mac
- Prestatieverbeteringen & oplossingen voor fouten

## <a name="1011921-20120101119210"></a>101.19.21 (20.120101.11921.0)

- Bug fixes

## <a name="1011526-20120102115260"></a>101.15.26 (20.120102.11526.0)

- Verbeterde de betrouwbaarheid van de agent bij het uitvoeren van macOS 11 Big Sur
- Een nieuwe opdrachtregelschakelaar () toegevoegd om AV-uitsluitingen `--ignore-exclusions` te negeren tijdens aangepaste scans ( `mdatp scan custom` )
- Prestatieverbeteringen & oplossingen voor fouten

## <a name="1011375-20120101113750"></a>101.13.75 (20.120101.11375.0)

- Verwijderde voorwaarden wanneer Microsoft Defender voor Eindpunt een macOS 11 -bug (Big Sur) activeert die zich manifesteert in een kernel-paniek
- Een geheugenlek in de systeemextensie Endpoint Security opgelost bij het uitvoeren op mac 11 (Big Sur)
- Bug fixes

## <a name="1011072"></a>101.10.72

- Bug fixes

## <a name="1010961"></a>101.09.61

- Een nieuwe beheerde voorkeur voor het [uitschakelen van de optie voor het verzenden van feedback toegevoegd](mac-preferences.md#show--hide-option-to-send-feedback)
- Het pictogram Statusmenu geeft nu een gezonde status weer wanneer de productinstellingen worden beheerd. Voorheen werd in het statusmenupictogram een waarschuwings- of foutstatus weergegeven, ook al zijn de productinstellingen beheerd door de beheerder
- Prestatieverbeteringen & oplossingen voor fouten

## <a name="1010950"></a>101.09.50

- Deze productversie is gevalideerd op macOS Big Sur 11 beta 9

- De nieuwe syntaxis voor het `mdatp` opdrachtregelhulpmiddel is nu de standaard syntaxis. Zie Resources [for Microsoft Defender for Endpoint on macOS](mac-resources.md#configuring-from-the-command-line) (Bronnen voor Microsoft Defender voor eindpunt op macOS) voor meer informatie over de nieuwe syntaxis.

  > [!NOTE]
  > De syntaxis van het oude opdrachtregelprogramma wordt op 1 januari **2021** uit het product verwijderd.

- Uitgebreid met een nieuwe parameter ( ) waarmee de diagnostische `mdatp diagnostic create` `--path [directory]` logboeken kunnen worden opgeslagen in een andere adreslijst
- Prestatieverbeteringen & oplossingen voor fouten

## <a name="1010949"></a>101.09.49

- Verbeteringen in de gebruikersinterface om onderscheid te maken tussen uitsluitingen die worden beheerd door de IT-beheerder en uitsluitingen die door de lokale gebruiker zijn gedefinieerd
- Verbeterde CPU-gebruik tijdens scans op aanvraag
- Prestatieverbeteringen & oplossingen voor fouten

## <a name="1010723"></a>101.07.23

- Nieuwe velden toegevoegd aan de uitvoer van voor het controleren van de status van de passieve modus en `mdatp --health` de EDR groep-id

  > [!NOTE]
  > `mdatp --health` wordt vervangen door `mdatp health` in een toekomstige productupdate.

- Een fout opgelost waarbij automatische voorbeeldinzending niet is gemarkeerd als beheerd in de gebruikersinterface
- Er zijn nieuwe instellingen toegevoegd voor het beheren van het bewaren van items in de antivirusscangeschiedenis. U kunt nu het aantal dagen opgeven om items in de [scangeschiedenis](mac-preferences.md#antivirus-scan-history-retention-in-days) te behouden en het maximum aantal items in de [scangeschiedenis opgeven](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)
- Bug fixes

## <a name="1010663"></a>101.06.63

- Er is een prestatieregressie aangepakt die in versie is `101.05.17` geïntroduceerd. De regressie is geïntroduceerd met de fix om de kernel-paniek te elimineren die sommige klanten hebben waargenomen bij het openen van SMB-aandelen. We hebben deze codewijziging teruggedraaid en onderzoeken alternatieve manieren om de kernelpaniek te voorkomen.

## <a name="1010517"></a>101.05.17

> [!IMPORTANT]
> We werken aan een nieuwe en verbeterde syntaxis voor het `mdatp` opdrachtregelhulpmiddel. De nieuwe syntaxis is momenteel de standaardinstelling in de Insider Fast- en Insider Slow-updatekanalen. We raden u aan om uzelf te famliliariseren met deze nieuwe syntaxis.
> 
> We blijven de oude syntaxis ondersteunen in parallel met de nieuwe syntaxis en zorgen voor meer communicatie rond het afbouwplan voor de oude syntaxis in de komende maanden.

- Adresseerde een kernel-paniek die zich soms voordeed bij het openen van SMB-bestandsaandelen
- Prestatieverbeteringen & oplossingen voor fouten

## <a name="1010516"></a>101.05.16

- Verbeteringen in de logica voor snelle scannen om het aantal gescande bestanden aanzienlijk te verminderen
- Ondersteuning [voor automatisch aanvullen toegevoegd](mac-resources.md#how-to-enable-autocompletion) voor het opdrachtregelhulpmiddel
- Bug fixes

## <a name="1010312"></a>101.03.12

- Prestatieverbeteringen & oplossingen voor fouten

## <a name="1010154"></a>101.01.54

- Verbeteringen rond compatibiliteit met Time Machine
- Toegankelijkheidsverbeteringen
- Prestatieverbeteringen & oplossingen voor fouten

## <a name="1010031"></a>101.00.31

- Verbeterde [onboarding-ervaring voor Intune-gebruikers](/mem/intune/apps/apps-advanced-threat-protection-macos)
- [Antivirusuitsluitingen ondersteunen nu jokertekens](mac-exclusions.md#supported-exclusion-types)
- De mogelijkheid toegevoegd om antivirusscans te activeren vanuit het contextmenu van macOS. U kunt nu met de rechtermuisknop op een bestand of map in Finder klikken en **Scannen met Microsoft Defender voor eindpunt selecteren**
- In-place product downgrades worden nu expliciet afgekeurd door het installatieprogramma. Als u wilt downgraden, moet u eerst de bestaande versie verwijderen en uw apparaat opnieuw configureren
- Andere prestatieverbeteringen & bug fixes

## <a name="1009027"></a>100.90.27

- U kunt nu [een updatekanaal voor](mac-updates.md#set-the-channel-name) Microsoft Defender voor Eindpunt instellen voor macOS dat verschilt van het systeembrede updatekanaal
- Pictogram Nieuw product
- Andere verbeteringen in de gebruikerservaring
- Bug fixes

## <a name="1008692"></a>100.86.92

- Verbeteringen rond compatibiliteit met Time Machine
- Een probleem opgelost waarbij het product soms niet alle bestanden onder tijdens het verwijderen `/Library/Application Support/Microsoft/Defender` opsschoonde
- Minder CPU-gebruik van het product wanneer Microsoft-producten worden bijgewerkt via Microsoft AutoUpdate
- Andere prestatieverbeteringen & bug fixes

## <a name="1008691"></a>100.86.91

> [!CAUTION]
> Als u de meest volledige beveiliging wilt garanderen voor uw macOS-apparaten en in overeenstemming met apple die de levering van macOS-beveiligingsupdates stopt voor besturingssysteemversies ouder dan [huidige – 2], worden MDATP voor Mac-implementatie en -updates niet meer ondersteund op macOS Sierra [10.12]. MDATP updates en verbeteringen voor Mac worden geleverd op apparaten met versies Catalina [10.15], Mojave [10.14] en High Sierra [10.13]. 
>
> Als u al MDATP voor Mac hebt geïmplementeerd op uw Sierra [10.12]-apparaten, kunt u een upgrade uitvoeren naar de nieuwste macOS-versie om het risico op verlies van beveiliging te voorkomen.

- Prestatieverbeteringen & oplossingen voor fouten

## <a name="1008373"></a>100.83.73

- Meer besturingselementen voor IT-beheerders toegevoegd rond het beheer van [uitsluitingen,](mac-preferences.md#exclusion-merge-policy) [het beheer](mac-preferences.md#threat-type-settings-merge-policy)van instellingen voor bedreigingstype en [niet-toegestaan bedreigingsacties](mac-preferences.md#disallowed-threat-actions)
- Wanneer Volledige schijftoegang niet is ingeschakeld op het apparaat, wordt er nu een waarschuwing weergegeven in het statusmenu
- Prestatieverbeteringen & oplossingen voor fouten

## <a name="1008260"></a>100.82.60

- Er is een probleem opgelost waarbij het product niet na een definitieupdate kan beginnen.

## <a name="1008042"></a>100.80.42

- Bug fixes

## <a name="1007942"></a>100.79.42

- Er is een probleem opgelost waarbij Microsoft Defender voor Eindpunt op Mac soms tijdmachine verstoort
- Een nieuwe schakelknop toegevoegd aan het hulpprogramma voor de opdrachtregel voor het testen van de connectiviteit met de backend-service
  ```bash
  mdatp connectivity test
  ```
- Extra mogelijkheid om de volledige bedreigingsgeschiedenis in de gebruikersinterface weer te geven (kan worden bekeken vanuit de **weergave Beveiligingsgeschiedenis)**
- Prestatieverbeteringen & oplossingen voor fouten

## <a name="1007215"></a>100.72.15

- Bug fixes

## <a name="1007099"></a>100.70.99

- Er is een probleem opgelost dat van invloed is op de mogelijkheid van sommige gebruikers om een upgrade uit te voeren naar macOS Catalina wanneer realtimebeveiliging is ingeschakeld. Dit sporadische probleem is veroorzaakt door Microsoft Defender voor het vergrendelen van bestanden in het Catalina-upgradepakket tijdens het scannen op bedreigingen, wat leidde tot fouten in de upgradevolgorde.

## <a name="1006899"></a>100.68.99

- De mogelijkheid toegevoegd om de antivirusfunctionaliteit te configureren voor gebruik in [de passieve modus](mac-preferences.md#enable--disable-passive-mode)
- Prestatieverbeteringen & oplossingen voor fouten

## <a name="1006528"></a>100.65.28

- Ondersteuning voor macOS Catalina toegevoegd

  > [!CAUTION]
  > macOS 10.15 (Catalina) bevat nieuwe beveiligings- en privacyverbeteringen. Vanaf deze versie hebben toepassingen standaard geen toegang tot bepaalde locaties op schijf (zoals Documenten, Downloads, Bureaublad, enzovoort) zonder expliciete toestemming. Bij afwezigheid van deze toestemming kan Microsoft Defender voor Eindpunt uw apparaat niet volledig beveiligen.
  >
  > Het mechanisme voor het verlenen van deze toestemming is afhankelijk van de manier waarop u Microsoft Defender voor Eindpunt hebt geïmplementeerd:
  >
  > - Zie de bijgewerkte instructies in het onderwerp Handmatige implementatie voor [handmatige](mac-install-manually.md#how-to-allow-full-disk-access) implementatie.
  > - Zie de bijgewerkte instructies in de op [JAMF gebaseerde](mac-install-with-jamf.md) implementatie- en Microsoft Intune [implementatieonderwerpen](mac-install-with-intune.md#create-system-configuration-profiles) voor beheerde implementaties.

- Prestatieverbeteringen & oplossingen voor fouten
