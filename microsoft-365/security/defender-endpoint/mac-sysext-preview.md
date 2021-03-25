---
title: Microsoft Defender ATP voor Mac - systeemextensies (Preview)
description: Dit artikel bevat instructies voor het testen van de systeemextensiesfunctionaliteit van Microsoft Defender ATP voor Mac. Deze functionaliteit is momenteel beschikbaar in een openbaar voorbeeld.
keywords: microsoft, defender, atp, mac, kernel, systeem, extensies, catalina
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
ROBOTS: noindex,nofollow
ms.technology: mde
ms.openlocfilehash: 6becdd995d70c0b8193e8df097c9256dc38c72a2
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185895"
---
# <a name="microsoft-defender-for-endpoint-for-mac---system-extensions-public-preview"></a>Microsoft Defender voor Eindpunt voor Mac - openbare voorbeeld van systeemextensies)

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

In overeenstemming met de ontwikkeling van macOS bereiden we een Defender voor Endpoint voor Mac-update voor die gebruik maakt van systeemextensies in plaats van kernelextensies. Deze update is alleen van toepassing op macOS Catalina (10.15.4) en latere versies van macOS.

Deze functionaliteit is momenteel beschikbaar in een openbaar voorbeeld. In dit artikel wordt beschreven hoe u deze functionaliteit op uw apparaat kunt inschakelen. U kunt deze functie lokaal uitproberen op uw eigen apparaat of op afstand configureren via een beheerhulpmiddel.

In deze stappen wordt ervan uitgenomen dat Defender for Endpoint al op uw apparaat wordt uitgevoerd. Zie deze pagina voor [meer informatie.](microsoft-defender-endpoint-mac.md)

## <a name="known-issues"></a>Bekende problemen

- We hebben rapporten ontvangen over de netwerkextensie die de Apple SSO Kerberos-extensie verstoort.
- De huidige versie van het product installeert nog steeds een kernelextensie. De kernelextensie wordt alleen gebruikt als een fallback-mechanisme en wordt verwijderd voordat deze functie een openbare preview bereikt.
- We werken nog steeds aan een productversie die correct wordt geïmplementeerd en werkt op macOS 11 Big Sur.

## <a name="deployment-prerequisites"></a>Implementatie-vereisten

- Minimale macOS-besturingssysteemversie: **10.15.4**
- Minimale productversie: **101.03.73**
- Uw apparaat moet zich in het **Insider Fast-updatekanaal hebben.** U kunt het updatekanaal controleren met de volgende opdracht:

  ```bash
  mdatp health --field release_ring
  ```

  Als uw apparaat zich nog niet in het Insider Fast-updatekanaal heeft, voert u de volgende opdracht uit vanuit de Terminal. De kanaalupdate wordt van kracht wanneer het product de volgende keer wordt gestart (wanneer de volgende productupdate is geïnstalleerd of wanneer het apparaat opnieuw wordt opgestart).

  ```bash
  defaults write com.microsoft.autoupdate2 ChannelName -string Beta
  ```

  Als u zich in een beheerde omgeving (JAMF of Intune) hebt, kunt u het updatekanaal ook op afstand configureren. Zie Updates voor Microsoft Defender ATP voor Mac implementeren voor meer [informatie: De kanaalnaam instellen.](mac-updates.md#set-the-channel-name)

## <a name="deployment-steps"></a>Implementatiestappen

Volg de implementatiestappen die overeenkomen met uw omgeving en de gewenste methode om deze functie uit te proberen.

### <a name="manual-deployment"></a>Handmatige implementatie

#### <a name="approve-the-system-extensions-and-enable-the-network-extension"></a>De systeemextensies goedkeuren en de netwerkextensie inschakelen

1. Nadat aan alle implementatievoorwaarden is voldaan, start u het apparaat opnieuw op om de goedkeuring en activering van de systeemextensie te starten.

   U ziet een reeks systeemprompts om de systeemextensies van Defender voor Eindpunt goed te keuren. U moet alle **aanwijzingen** uit de reeks goedkeuren, omdat voor macOS een expliciete goedkeuring is vereist voor elke extensie die Defender voor Eindpunt voor Mac op het apparaat installeert.
   
   Voor elke goedkeuring selecteert u **Beveiligingsvoorkeuren** openen en **selecteert** u Toestaan dat de systeemextensie wordt uitgevoerd.

   > [!IMPORTANT]
   > U moet het beveiligingsvenster voor **systeemvoorkeuren**& tussen de volgende goedkeuringen sluiten en  >   opnieuw openen. Anders wordt de volgende goedkeuring niet weergegeven in MacOS.

   > [!IMPORTANT]
   > Er is een time-out van één minuut voordat het product terugvalt naar de kernelextensie. Dit zorgt ervoor dat het apparaat is beveiligd.
   >
   > Als er meer dan één minuut verstreken is, start u de daemon opnieuw op door het apparaat opnieuw op te starten of door de goedkeuringsstroom opnieuw `sudo killall -9 wdavdaemon` te activeren.

   ![Pop-up voor goedkeuring van systeemextensie](images/mac-system-extension-approval.png)

   ![Goedkeuringsvenster systeemextensie](images/mac-system-extension-pref.png)

1. Nadat de systeemextensies zijn goedgekeurd, wordt in MacOS gevraagd of het netwerkverkeer moet worden gefilterd. Klik **op Toestaan.**

   ![Pop-up voor goedkeuring van netwerkextensie](images/mac-system-extension-filter.png)

#### <a name="grant-full-disk-access-to-the-endpoint-security-system-extension"></a>Volledige schijftoegang verlenen aan de systeemextensie Endpoint Security

Open het **tabblad Privacy** privacy & systeemvoorkeuren en verleen volledige schijftoegang aan de  >    >   Microsoft Defender **Endpoint-beveiligingsextensie.** 

![Volledige schijftoegang voor systeemextensie endpointbeveiliging](images/mac-system-extension-fda.png)

#### <a name="reboot-your-device"></a>Uw apparaat opnieuw opstarten

Om de wijzigingen van kracht te laten worden, moet u het apparaat opnieuw opstarten.

#### <a name="verify-that-the-system-extensions-are-running"></a>Controleren of de systeemextensies worden uitgevoerd

Voer vanuit de Terminal de volgende opdracht uit:

```bash
mdatp health --field real_time_protection_subsystem
```

`endpoint_security_extension`Terminaluitvoer geeft aan dat het product de functionaliteit voor systeemextensies gebruikt.

### <a name="managed-deployment"></a>Beheerde implementatie

Raadpleeg [Nieuwe configuratieprofielen voor macOS Catalina](mac-sysext-policies.md#jamf) en nieuwere versies van macOS: JAMF voor de nieuwe configuratieprofielen die u moet implementeren voor deze nieuwe functie.

Naast deze profielen moet u de doelapparaten configureren in het Insider Fast-updatekanaal, zoals wordt beschreven in [implementatievoorwaarden.](#deployment-prerequisites)

Voer de volgende opdracht uit op een apparaat waar aan alle vereisten is voldaan en de nieuwe configuratieprofielen zijn geïmplementeerd:

```bash
$ mdatp health --field real_time_protection_subsystem
```

Als deze opdracht wordt `endpoint_security_extension` afgedrukt, gebruikt het product de systeemextensiesfunctionaliteit.

## <a name="validate-basic-scenarios"></a>Basisscenario's valideren

1. Test de EICAR-detectie (European Institute for Computer Antivirus Research). Voer vanuit een terminalvenster de volgende opdracht uit:

   ```bash
   curl -o eicar.txt https://secure.eicar.org/eicar.com.txt
   ```

   Controleer of het EICAR-bestand in quarantaine is geplaatst. U kunt de status van het bestand controleren op de pagina Beschermingsgeschiedenis in de gebruikersinterface of vanaf een opdrachtregel met de volgende opdracht:

    ```bash
    mdatp threat list
    ```

2. Test het scenario Endpoint Detection and Response (EDR). Voer vanuit een terminalvenster de volgende opdracht uit:

   ```bash
   curl -o "MDATP MacOS DIY.zip" https://aka.ms/mdatpmacosdiy
   ```

   Controleer of er twee waarschuwingen zijn weergegeven in de portal op de computerpagina voor EICAR- en EDR-doe-het-zelfscenario's.

## <a name="frequently-asked-questions"></a>Veelgestelde vragen

- V: Waarom zie ik nog steeds `kernel_extension` wanneer ik `mdatp health --field real_time_protection_subsystem` voer?

    A: Ga terug naar de sectie [Implementatie-vereisten](#deployment-prerequisites) en controleer of aan alle vereisten is voldaan. Als aan alle vereisten is voldaan, start u het apparaat opnieuw op en controleert u het opnieuw.

- V: Wanneer wordt macOS 11 Big Sur ondersteund?

    A: We werken actief aan het toevoegen van ondersteuning voor macOS 11. We plaatsen meer informatie op de nieuwe pagina Wat [is er](mac-whatsnew.md) nieuw.
