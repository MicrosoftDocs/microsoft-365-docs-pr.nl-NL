---
title: Gedetecteerde bedreigingen bekijken en actie ondernemen
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Informatie over het controleren en beheren van bedreigingen die zijn gedetecteerd door Microsoft Defender Antivirus op uw Windows 10-apparaten.
ms.openlocfilehash: 15e99fb75e4a3ac1af842ca7d0b900e02cbc6bd4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912784"
---
# <a name="review-detected-threats-and-take-action"></a>Gedetecteerde bedreigingen bekijken en actie ondernemen

Zodra een schadelijk bestand of software wordt gedetecteerd, blokkeert Microsoft Defender Antivirus het bestand en voorkomt u dat het wordt uitgevoerd. En als beveiliging in de cloud is ingeschakeld, worden nieuw gedetecteerde bedreigingen toegevoegd aan de antivirus- en antimalware-engine, zodat uw andere apparaten en gebruikers ook worden beveiligd.

Microsoft Defender Antivirus detecteert en beschermt tegen de volgende soorten bedreigingen:

- Virussen, malware en op het web gebaseerde bedreigingen op apparaten
- Phishingpogingen
- Pogingen tot gegevensdiefstal

Als IT-professional/beheerder kunt u informatie bekijken over bedreigingsdetecties op [Windows 10-apparaten](/mem/intune/enrollment/device-enrollment) die zijn geregistreerd in Intune in het Microsoft 365-beheercentrum. U ziet overzichtsgegevens, zoals:

- Hoeveel apparaten hebben antivirusbeveiliging nodig
- Hoeveel apparaten voldoen niet aan het beveiligingsbeleid
- Hoeveel bedreigingen momenteel actief, beperkt of opgelost zijn

U hebt verschillende opties om specifieke informatie over bedreigingsdetecties en -apparaten weer te geven:

- De **pagina Actieve apparaten** in het Microsoft <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">365-beheercentrum</a>. Zie [Bedreigingsdetecties beheren op de pagina Actieve apparaten](#manage-threat-detections-on-the-active-devices-page) in dit artikel.
- De **pagina Actieve bedreigingen** in het <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365-beheercentrum.</a> Zie [Bedreigingsdetecties beheren op de pagina Actieve bedreigingen](#manage-threat-detections-on-the-active-threats-page) in dit artikel.
- De **pagina Antivirus** in Microsoft <a href="https://go.microsoft.com/fwlink/p/?linkid=2150463" target="_blank">Endpoint Manager.</a> Zie [Bedreigingsdetecties beheren in Microsoft Endpoint Manager](#manage-threat-detections-in-microsoft-endpoint-manager) in dit artikel.

Zie Bedreigingen gedetecteerd door Microsoft Defender Antivirus voor [meer informatie.](threats-detected-defender-av.md)

## <a name="manage-threat-detections-on-the-active-devices-page"></a>Bedreigingsdetecties beheren op de pagina **Actieve apparaten**

De volgende procedure is van toepassing op klanten met Microsoft 365 Business Premium.

1. Ga naar het Microsoft 365-beheercentrum bij <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> en meld u aan.

2. Selecteer apparaten met actieve apparaten **op** de  >  **navigatiepagina.** U ziet een lijst met actieve apparaten en details, zoals de beveiligingsstatus, de antivirusstatus en het aantal gedetecteerde actieve bedreigingen.

3. Selecteer een apparaat om meer informatie over dat apparaat en beschikbare acties weer te geven. Er wordt een flyout geopend met aanbevelingen en beschikbare acties, zoals **Updatebeleid,** **Antivirus bijwerken,** Snelle **scan** uitvoeren, Volledige **scan** uitvoeren en meer.

## <a name="manage-threat-detections-on-the-active-threats-page"></a>Bedreigingsdetecties beheren op de pagina **Actieve bedreigingen**

De volgende procedure is van toepassing op klanten met Microsoft 365 Business Premium. [Windows 10-apparaten moeten zijn beveiligd en](./secure-win-10-pcs.md) geregistreerd in [Intune.](/mem/intune/enrollment/windows-enrollment-methods)

> [!NOTE]
> De **microsoft Defender Antiviruskaart** en **de pagina Actieve** bedreigingen worden gefaseerd uitgerold, zodat u mogelijk niet direct toegang tot de kaart hebt.

1. Ga naar het Microsoft 365-beheercentrum bij <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> en meld u aan.

2. Selecteer actieve **bedreigingen** weergeven op de Microsoft Defender **Antivirus-kaart.** (U kunt ook in het navigatiedeelvenster Status **selecteren**  >  **Bedreigingen & antivirus**.)

3. Selecteer op **de** pagina Actieve bedreigingen een gedetecteerde bedreiging voor meer informatie. Er wordt een flyout geopend met details over die bedreiging, waaronder welke apparaten worden beïnvloed.

4. Selecteer in de flyout een apparaat om beschikbare acties weer te geven, zoals **Updatebeleid,** **Antivirus bijwerken,** **Snel scannen** uitvoeren en meer.

## <a name="actions-you-can-take"></a>Acties die u kunt uitvoeren

Wanneer u details over specifieke bedreigingen of apparaten bekijkt, ziet u aanbevelingen en een of meer acties die u kunt uitvoeren. In de volgende tabel worden acties beschreven die u mogelijk ziet.<br><br>

| Actie | Beschrijving |
|--|--|
| Beveiliging configureren | Uw beleid voor bedreigingsbeveiliging moet worden geconfigureerd. Selecteer de koppeling om naar uw beleidsconfiguratiepagina te gaan.<br><br>Hulp nodig? Zie [Apparaatbeveiliging beheren met endpoint-beveiligingsbeleid in Microsoft Intune](/mem/intune/protect/endpoint-security-policy). |
| Updatebeleid | Uw antivirus- en realtimebeveiligingsbeleid moet worden bijgewerkt of geconfigureerd. Selecteer de koppeling om naar de pagina beleidsconfiguratie te gaan.<br><br>Hulp nodig? Zie [Apparaatbeveiliging beheren met endpoint-beveiligingsbeleid in Microsoft Intune](/mem/intune/protect/endpoint-security-policy). |
| Snelle scan uitvoeren | Start een snelle antivirusscan op het apparaat, met de focus op veelgebruikte locaties waar malware kan worden geregistreerd, zoals registersleutels en bekende opstartmappen van Windows. |
| Volledige scan uitvoeren | Start een volledige antivirusscan op het apparaat, met de focus op veelgebruikte locaties waar malware kan worden geregistreerd, en met inbegrip van elk bestand en elke map op het apparaat. Resultaten worden verzonden [naar Microsoft Endpoint Manager.](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) |
| Antivirusprogramma's bijwerken | Vereist dat het apparaat [beveiligingsinformatie-updates ontvangt](https://go.microsoft.com/fwlink/?linkid=2149926) voor antivirus- en antimalwarebeveiliging. |
| Apparaat opnieuw starten | Een Windows 10-apparaat moet binnen vijf minuten opnieuw worden gestart.<br><br>**BELANGRIJK:** De eigenaar of gebruiker van het apparaat wordt niet automatisch op de hoogte gesteld van het opnieuw opstarten en kan niet-opgeslagen werk verliezen. |

## <a name="manage-threat-detections-in-microsoft-endpoint-manager"></a>Bedreigingsdetecties beheren in Microsoft Endpoint Manager

U kunt Microsoft Endpoint Manager gebruiken om detecties van bedreigingen te beheren. Windows 10-apparaten moeten [zijn geregistreerd in Intune](/mem/intune/enrollment/windows-enrollment-methods) (onderdeel van Microsoft Endpoint Manager).

1. Ga naar het Microsoft Endpoint Manager-beheercentrum bij <a href="https://go.microsoft.com/fwlink/p/?linkid=2150463" target="_blank">https://endpoint.microsoft.com</a> en meld u aan.

2. Selecteer in het navigatiedeelvenster **Endpoint-beveiliging**.

3. Selecteer **onder** Beheren de optie **Antivirus.** U ziet verschillende tabbladen, zoals **Samenvatting,** **Windows 10** ongezonde eindpunten en **Windows 10 gedetecteerde malware.**

4. Controleer de informatie op de beschikbare tabbladen en onderneemt vervolgens de benodigde actie.

Stel dat apparaten worden vermeld op het tabblad Gedetecteerde malware in **Windows 10.** Wanneer u een apparaat selecteert, zijn er bepaalde acties beschikbaar, zoals Opnieuw **starten,** Snel **scannen,** Volledig **scannen,** Synchroniseren **of** Handtekeningen **bijwerken.** Selecteer een actie voor dat apparaat.

In de volgende tabel worden de acties beschreven die u mogelijk ziet in Microsoft Endpoint Manager.<br><br>

| Actie | Beschrijving |
|--|--|
| Opnieuw starten | Een Windows 10-apparaat moet binnen vijf minuten opnieuw worden gestart.<br><br>**BELANGRIJK:** De eigenaar of gebruiker van het apparaat wordt niet automatisch op de hoogte gesteld van het opnieuw opstarten en kan niet-opgeslagen werk verliezen. |
| Snel scannen | Start een snelle antivirusscan op het apparaat, met de focus op veelgebruikte locaties waar malware kan worden geregistreerd, zoals registersleutels en bekende opstartmappen van Windows. Resultaten worden verzonden [naar Microsoft Endpoint Manager.](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) |
| Volledige scan | Start een volledige antivirusscan op het apparaat, met de focus op veelgebruikte locaties waar malware kan worden geregistreerd, en met inbegrip van elk bestand en elke map op het apparaat. Resultaten worden verzonden [naar Microsoft Endpoint Manager.](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) |
| Synchroniseren | Vereist een apparaat om in te checken met Intune (onderdeel van Microsoft Endpoint Manager). Wanneer het apparaat wordt incheckt, ontvangt het apparaat alle acties of beleid in behandeling die aan het apparaat zijn toegewezen. |
| Handtekeningen bijwerken | Vereist dat het apparaat [beveiligingsinformatie-updates ontvangt](https://go.microsoft.com/fwlink/?linkid=2149926) voor antivirus- en antimalwarebeveiliging. |

> [!TIP]
> Zie Externe acties voor apparaten voor meer [informatie.](/mem/intune/protect/endpoint-security-manage-devices#remote-actions-for-devices)

## <a name="how-to-submit-a-file-for-malware-analysis"></a>Een bestand indienen voor malwareanalyse

Als u een bestand hebt dat volgens u is gemist of ten onrechte als malware is geclassificeerd, kunt u dat bestand voor malwareanalyse indienen bij Microsoft. Gebruikers en IT-beheerders kunnen een bestand voor analyse indienen. Ga [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission) naar .