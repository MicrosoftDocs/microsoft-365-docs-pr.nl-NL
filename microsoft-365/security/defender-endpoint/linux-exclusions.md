---
title: Uitsluitingen configureren en valideren voor Microsoft Defender voor Eindpunt op Linux
description: Uitsluitingen opgeven en valideren voor Microsoft Defender voor Eindpunt op Linux. Uitsluitingen kunnen worden ingesteld voor bestanden, mappen en processen.
keywords: microsoft, defender, Microsoft Defender voor Eindpunt, linux, uitsluitingen, scans, antivirus
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: bd506caa041af2585778fb3ecd7a40562463b17e
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346412"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-for-endpoint-on-linux"></a>Uitsluitingen configureren en valideren voor Microsoft Defender voor Eindpunt op Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefversie.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Dit artikel bevat informatie over het definiëren van uitsluitingen die van toepassing zijn op scans op aanvraag en realtime beveiliging en bewaking.

> [!IMPORTANT]
> De uitsluitingen die in dit artikel worden beschreven, zijn niet van toepassing op andere mogelijkheden van Defender voor Eindpunt op Linux, waaronder eindpuntdetectie en -respons (EDR). Bestanden die u uitsluit met behulp van de methoden die in dit artikel worden beschreven, kunnen nog steeds EDR-waarschuwingen en andere detecties activeren.

U kunt bepaalde bestanden, mappen, processen en door processen geopende bestanden uitsluiten van Defender voor Eindpunt op Linux-scans.

Uitsluitingen kunnen handig zijn om onjuiste detecties te voorkomen voor bestanden of software die uniek zijn of zijn aangepast aan uw organisatie. Ze kunnen ook nuttig zijn voor het beperken van prestatieproblemen die worden veroorzaakt door Defender voor Eindpunt op Linux.

> [!WARNING]
> Als u uitsluitingen definieert, wordt de beveiliging verlaagd die wordt geboden door Defender voor Eindpunt op Linux. U moet altijd de risico's evalueren die zijn gekoppeld aan het implementeren van uitsluitingen en u moet alleen bestanden uitsluiten waarvan u zeker weet dat ze niet schadelijk zijn.

## <a name="supported-exclusion-types"></a>Ondersteunde uitsluitingstypen

In de volgende tabel ziet u de uitsluitingstypen die worden ondersteund door Defender voor Eindpunt op Linux.

Uitsluiting | Definitie | Voorbeelden
---|---|---
Bestandsextensie | Alle bestanden met de extensie, waar dan ook op het apparaat | `.test`
Bestand | Een specifiek bestand dat wordt geïdentificeerd door het volledige pad | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
Map | Alle bestanden in de opgegeven map (recursief) | `/var/log/`<br/>`/var/*/`
Proces | Een specifiek proces (opgegeven door het volledige pad of de bestandsnaam) en alle bestanden die door het proces zijn geopend | `/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> De bovenstaande paden moeten harde koppelingen zijn, geen symbolische koppelingen, om met succes te kunnen worden uitgesloten. U kunt controleren of een pad een symbolische koppeling is door `file <path-name>` uit te voeren.

Uitsluitingen van bestanden, mappen en processen ondersteunen de volgende jokertekens:

Jokerteken | Beschrijving | Voorbeeld | Overeenkomsten | Komt niet overeen
---|---|---|---|---
\* |    Komt overeen met een willekeurig aantal tekens, inclusief geen (houd er rekening mee dat wanneer dit jokerteken binnen een pad wordt gebruikt, slechts één map wordt vervangen) | `/var/\*/\*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
? | Komt overeen met een enkel teken | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

## <a name="how-to-configure-the-list-of-exclusions"></a>De lijst met uitsluitingen configureren

### <a name="from-the-management-console"></a>Vanuit de beheerconsole

Zie [Voorkeuren instellen voor Defender voor Eindpunt op Linux](linux-preferences.md)voor meer informatie over het configureren van uitsluitingen van Puppet, Ansible of een andere beheerconsole.

### <a name="from-the-command-line"></a>Vanaf de opdrachtregel

Voer de volgende opdracht uit om de beschikbare opties voor het beheren van uitsluitingen weer te geven:

```bash
mdatp exclusion
```

> [!TIP]
> Bij het configureren van uitsluitingen met jokertekens plaatst u de parameter tussen dubbele aanhalingstekens om globbing te voorkomen.

Voorbeelden:

- Een uitsluiting toevoegen voor een bestandsextensie:

    ```bash
    mdatp exclusion extension add --name .txt
    ```
    ```Output
    Extension exclusion configured successfully
    ```

- Een uitsluiting toevoegen voor een bestand:

    ```bash
    mdatp exclusion file add --path /var/log/dummy.log
    ```
    ```Output
    File exclusion configured successfully
    ```

- Een uitsluiting toevoegen voor een map:

    ```bash
    mdatp exclusion folder add --path /var/log/
    ```
    ```Output
    Folder exclusion configured successfully
    ```

- Voeg een uitsluiting toe voor een map met een jokerteken:

    ```bash
    mdatp exclusion folder add --path "/var/*/"
    ```

    > [!NOTE]
    > Hiermee worden paden slechts één niveau onder */var/* uitgesloten, maar geen mappen die dieper zijn genest; bijvoorbeeld */var/this-submap/but-not-this-subfolder*.
    
    ```bash
    mdatp exclusion folder add --path "/var/"
    ```
    > [!NOTE]
    > Hiermee worden alle paden uitgesloten waarvan het bovenliggende element */var/*; is. bijvoorbeeld */var/this-submap/and-this-subfolder-as-well*.

    ```Output
    Folder exclusion configured successfully
    ```

- Een uitsluiting toevoegen voor een proces:

    ```bash
    mdatp exclusion process add --name cat
    ```
    ```Output    
    Process exclusion configured successfully
    ```

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a>Uitsluitingslijsten valideren met het EICAR-testbestand

U kunt controleren of uw uitsluitingslijsten werken met behulp van `curl` en een testbestand te downloaden.

Vervang vervolgens het Bash-fragment `test.txt` door een bestand dat voldoet aan uw uitsluitingsregels. Als u bijvoorbeeld de `.testing`-extensie hebt uitgesloten, vervangt u `test.txt` door `test.testing`. Als u een pad test, moet u ervoor zorgen dat u de opdracht binnen dat pad uitvoert.

```bash
curl -o test.txt https://www.eicar.org/download/eicar.com.txt
```

Als Defender voor Eindpunt op Linux malware rapporteert, werkt de regel niet. Als er geen malware wordt gerapporteerd en het gedownloade bestand bestaat, werkt de uitsluiting. U kunt het bestand openen om te bevestigen dat de inhoud hetzelfde is als wat wordt beschreven op de [EICAR-testbestandswebsite](http://2016.eicar.org/86-0-Intended-use.html).

Als u geen internettoegang hebt, kunt u uw eigen EICAR-testbestand maken. Schrijf de EICAR-tekenreeks naar een nieuw tekstbestand met de volgende Bash-opdracht:

```bash
echo 'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*' > test.txt
```

U kunt de tekenreeks ook kopiëren naar een leeg tekstbestand en proberen deze op te slaan met de bestandsnaam of in de map die u probeert uit te sluiten.

## <a name="allow-threats"></a>Bedreigingen toestaan

Naast het uitsluiten dat bepaalde inhoud wordt gescand, kunt u het product ook zo configureren dat bepaalde klassen bedreigingen niet worden gedetecteerd (geïdentificeerd door de bedreigingsnaam). Wees voorzichtig bij het gebruik van deze functionaliteit, omdat uw apparaat hierdoor onbeveiligd kan raken.

Voer de volgende opdracht uit om een bedreigingsnaam toe te voegen aan de lijst met toegestane bedreigingen:

```bash
mdatp threat allowed add --name [threat-name]
```

De bedreigingsnaam die is gekoppeld aan een detectie op uw apparaat, kan worden verkregen met behulp van de volgende opdracht:

```bash
mdatp threat list
```

Als u bijvoorbeeld `EICAR-Test-File (not a virus)` (de bedreigingsnaam die is gekoppeld aan de EICAR-detectie) wilt toevoegen aan de lijst met toegestane bedreigingen, voert u de volgende opdracht uit:

```bash
mdatp threat allowed add --name "EICAR-Test-File (not a virus)"
```
