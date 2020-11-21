---
title: Ontdekte bedreigingen controleren en actie ondernemen
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
description: Meer informatie over het controleren en beheren van bedreigingen die zijn gedetecteerd door Microsoft Defender antivirus op uw Windows 10-apparaten.
ms.openlocfilehash: 21830b91bfbb88fdd5d5139ee07c4dfb35f5b875
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376686"
---
# <a name="review-detected-threats-and-take-action"></a>Ontdekte bedreigingen controleren en actie ondernemen

Zodra een schadelijk bestand of software is gedetecteerd, blokkeert Microsoft Defender antivirus het en zorgt u ervoor dat de toepassing niet wordt uitgevoerd. En met de ingeschakelde bescherming van de cloud worden de nieuw ontdekte bedreigingen toegevoegd aan de antivirus-en antimalware-engine, zodat uw andere apparaten en gebruikers ook worden beveiligd.

Microsoft Defender Antivirus detecteert en beveiligt de volgende soorten bedreigingen:

- Virussen, malware en internetbedreigingen op apparaten
- Phishing-pogingen
- Pogingen tot gegevensdiefstal

Als IT-medewerker/beheerder kunt u informatie weergeven over de detectie van bedreiging op [Windows 10-apparaten die zijn ingeschreven in intune](/mem/intune/enrollment/device-enrollment) in het microsoft 365-Beheercentrum. U ziet samenvattingsgegevens, zoals:

- Hoeveel apparaten moet antivirusbeveiliging hebben
- Hoeveel apparaten niet voldoen aan beveiligingsbeleid
- Hoeveel bedreigingen zijn momenteel actief, verminderd of opgelost

U hebt verschillende opties voor het weergeven van specifieke informatie over de detectie van bedreigingen en apparaten:

- De pagina **actieve apparaten** in het <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365-Beheercentrum</a>. Zie [bedreigings detectie van de pagina actieve apparaten](#manage-threat-detections-on-the-active-devices-page) in dit artikel beheren.
- De pagina **actieve bedreigingen** in het <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365-Beheercentrum</a>. Zie [bedreigings detectie van de pagina actieve bedreigingen](#manage-threat-detections-on-the-active-threats-page) in dit artikel beheren.
- De pagina met **antivirus software** in <a href="https://endpoint.microsoft.com" target="_blank">Microsoft Endpoint Manager</a>. Zie [bedreigings detectie in Microsoft Endpoint Manager beheren](#manage-threat-detections-in-microsoft-endpoint-manager) in dit artikel.

Zie [bedreigingen gedetecteerd door Microsoft Defender antivirus](threats-detected-defender-av.md)voor meer informatie.

## <a name="manage-threat-detections-on-the-active-devices-page"></a>Detectie van bedreigings informatie op de pagina met **actieve apparaten** beheren

De volgende procedure is van toepassing op klanten met Microsoft 365 Business Premium.

1. Ga naar het Microsoft 365-Beheercentrum <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> en meld u aan.

2. **Selecteer op** de navigatiepagina de optie  >  **actieve apparaten**. U ziet een lijst met actieve apparaten en Details, zoals de beveiligingsstatus, de antivirus status beveiliging en het aantal actieve bedreigingen dat wordt gedetecteerd.

3. Selecteer een apparaat om meer informatie over dat apparaat en de beschikbare acties weer te geven. Er verschijnt een flyout met aanbevelingen en de beschikbare acties, zoals **updatebeleid**, het **bijwerken van antivirussoftware**, het **uitvoeren van snelle scan** en het **uitvoeren van volledige scans** en meer.

## <a name="manage-threat-detections-on-the-active-threats-page"></a>Detectie van bedreigings informatie op de pagina **actieve bedreigingen** beheren

De volgende procedure is van toepassing op klanten met Microsoft 365 Business. [Windows 10-apparaten moeten worden beveiligd](/microsoft-365/business/secure-win-10-pcs) en [ingeschreven in intune](/mem/intune/enrollment/windows-enrollment-methods).

> [!NOTE]
> De pagina's **Microsoft Defender antivirus** en **Active Threat** worden in fasen uitgerold, zodat u deze mogelijk niet direct kunt openen.

1. Ga naar het Microsoft 365-Beheercentrum <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> en meld u aan.

2. Selecteer **actieve bedreigingen weergeven** op de kaart **Microsoft Defender antivirus** . (U kunt ook in het navigatiedeelvenster **status**  >  selecteren **Bedreigingen & antivirussoftware**.)

3. Selecteer op de pagina **actieve bedreigingen** een bedreiging voor meer informatie. Er wordt een flyout geopend met meer informatie over die bedreiging, waaronder de apparaten waarop dit van invloed is.

4. Selecteer in het vervolgmenu een apparaat om beschikbare acties weer te geven, zoals **updatebeleid**, **antivirussoftware bijwerken**, **snelle scan uitvoeren** en meer.

## <a name="actions-you-can-take"></a>Acties die u kunt ondernemen

Wanneer u details weergeeft van bepaalde bedreigingen of apparaten, ziet u aanbevelingen en een of meer acties die u kunt uitvoeren. In de volgende tabel worden de acties beschreven die u kunt zien.<br><br>

| Actierij | Beschrijving |
|--|--|
| Beveiliging configureren | Uw beveiligingsbeleid moet zijn geconfigureerd. Selecteer de koppeling om naar de pagina beleid configureren te gaan.<br><br>Hulp nodig? Zie [beveiliging van apparaten beheren met controlepunt beveiligingsbeleid in Microsoft intune](/mem/intune/protect/endpoint-security-policy). |
| Beleidsregels bijwerken | Uw antivirussoftware en het realtime beveiligingsbeleid moeten worden bijgewerkt of geconfigureerd. Selecteer de koppeling om naar de pagina beleid configureren te gaan.<br><br>Hulp nodig? Zie [beveiliging van apparaten beheren met controlepunt beveiligingsbeleid in Microsoft intune](/mem/intune/protect/endpoint-security-policy). |
| Snelle scan uitvoeren | Hiermee start u een snelle antivirus scan op het apparaat om zich te richten op populaire locaties waarop malware kan worden geregistreerd, zoals registersleutels en bekende Windows-opstartmappen. |
| Volledige scan uitvoeren | Hiermee start u een volledige antivirus scan op het apparaat, benadrukt op veelgebruikte locaties waar de malware kan worden geregistreerd, en waaronder elk bestand en elke map op het apparaat. Resultaten worden verzonden naar [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager). |
| Antivirussoftware bijwerken | Het apparaat vereist updates van [Beveiligingsinformatie](https://go.microsoft.com/fwlink/?linkid=2149926) voor antivirussoftware en beveiliging tegen anti malware. |
| Apparaat opnieuw opstarten | Hiermee zorgt u ervoor dat een Windows 10-apparaat binnen vijf minuten opnieuw wordt gestart.<br><br>**Belangrijk:** De eigenaar van het apparaat of de gebruiker wordt niet automatisch op de hoogte gesteld van het opnieuw opstarten en kan niet-opgeslagen werk verliezen. |

## <a name="manage-threat-detections-in-microsoft-endpoint-manager"></a>Detectie van bedreigings informatie in Microsoft Endpoint Manager beheren

U kunt Microsoft Endpoint Manager gebruiken voor het beheren van bedreigings detectie. Windows 10-apparaten moeten zijn [ingeschreven voor intune](/mem/intune/enrollment/windows-enrollment-methods) (onderdeel van Microsoft Endpoint Manager).

1. Ga naar het Microsoft-Beheercentrum voor eindpunten <a href="https://endpoint.microsoft.com" target="_blank">https://endpoint.microsoft.com</a> en meld u aan.

2. Selecteer in het navigatiedeelvenster de optie **Endpoint beveiliging**.

3. Selecteer onder **beheren** de optie **antivirus software**. U ziet meerdere tabbladen, zoals **Samenvatting**, **beschadigde eindpunten voor Windows 10**, en **Windows 10 heeft malware gedetecteerd**.

4. Controleer de gegevens op de beschikbare tabbladen en onderneem de gewenste actie.

Stel dat apparaten worden weergegeven op het tabblad **malware van Windows 10** . Wanneer u een apparaat selecteert, hebt u de beschikking over bepaalde acties, zoals **opnieuw opstarten**, **snel scannen**, **volledig scannen**, **synchroniseren** of **handtekeningen bijwerken**. Selecteer een actie voor dat apparaat.

In de volgende tabel worden de acties beschreven die u mogelijk ziet in Microsoft Endpoint Manager.<br><br>

| Actierij | Beschrijving |
|--|--|
| Hervatten | Hiermee zorgt u ervoor dat een Windows 10-apparaat binnen vijf minuten opnieuw wordt gestart.<br><br>**Belangrijk:** De eigenaar van het apparaat of de gebruiker wordt niet automatisch op de hoogte gesteld van het opnieuw opstarten en kan niet-opgeslagen werk verliezen. |
| Snelle scan | Hiermee start u een snelle antivirus scan op het apparaat om zich te richten op populaire locaties waarop malware kan worden geregistreerd, zoals registersleutels en bekende Windows-opstartmappen. Resultaten worden verzonden naar [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager). |
| Volledige scan | Hiermee start u een volledige antivirus scan op het apparaat, benadrukt op veelgebruikte locaties waar de malware kan worden geregistreerd, en waaronder elk bestand en elke map op het apparaat. Resultaten worden verzonden naar [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager). |
| Synchroniseren | Hiervoor moet een apparaat worden ingecheckt met intune (onderdeel van Microsoft Endpoint Manager). Wanneer het apparaat wordt gecontroleerd, ontvangt het apparaat alle in behandeling zijnde acties of beleidsregels die aan het apparaat zijn toegewezen. |
| Handtekeningen bijwerken | Het apparaat vereist updates van [Beveiligingsinformatie](https://go.microsoft.com/fwlink/?linkid=2149926) voor antivirussoftware en beveiliging tegen anti malware. |

> [!TIP]
> Zie [externe acties voor apparaten](/mem/intune/protect/endpoint-security-manage-devices#remote-actions-for-devices)voor meer informatie.

## <a name="how-to-submit-a-file-for-malware-analysis"></a>Een bestand verzenden voor het analyseren van schadelijke software

Als u een bestand hebt dat u beschouwt als malware, kunt u dat bestand in Microsoft indienen voor de analyse van malware. Gebruikers en IT-beheerders kunnen een bestand voor analyse indienen. Ga naar [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission) .
