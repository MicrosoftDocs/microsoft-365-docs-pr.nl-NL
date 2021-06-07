---
title: Beveiligingsinstellingen beveiligen tegen onrechtmatig wijzigen
ms.reviewer: shwjha, hayhov
manager: dansimp
description: Gebruik tamperbeveiliging om te voorkomen dat schadelijke apps belangrijke beveiligingsinstellingen wijzigen.
keywords: malware, defender, antivirus, tamper protection
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.date: 05/17/2021
ms.openlocfilehash: 2d212bedf9033b0824d32e7f42afea3944d9ca67
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782811"
---
# <a name="protect-security-settings-with-tamper-protection"></a>Beveiligingsinstellingen beveiligen tegen onrechtmatig wijzigen

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

Beveiligingsbeveiliging voor tamper is beschikbaar voor apparaten met een van de volgende versies van Windows:

- Windows 10
- Windows Server 2019
- Windows Server, versie 1803 of hoger
- Windows Server 2016

## <a name="overview"></a>Overzicht

Tijdens sommige soorten cyberaanvallen proberen slechte spelers beveiligingsfuncties, zoals antivirusbeveiliging, uit te schakelen op uw machines. Slechte spelers willen uw beveiligingsfuncties uitschakelen om gemakkelijker toegang te krijgen tot uw gegevens, om malware te installeren of om op een andere manier uw gegevens, identiteit en apparaten te misbruiken. Met tamperbeveiliging kunt u voorkomen dat dit soort dingen voorkomen.

Met de beveiliging van fraude kunnen schadelijke apps geen acties uitvoeren, zoals:

- Virus- en bedreigingsbeveiliging uitschakelen
- Realtime beveiliging uitschakelen
- Gedragscontrole uitschakelen
- Antivirusprogramma's uitschakelen (zoals IOfficeAntivirus (IOAV))
- Beveiliging in de cloud uitschakelen
- Beveiligingsinformatie-updates verwijderen

### <a name="how-it-works"></a>Hoe het werkt

Met de beveiliging van tamper worden Microsoft Defender Antivirus en voorkomt u dat uw beveiligingsinstellingen worden gewijzigd via apps en methoden, zoals:

- Instellingen configureren in registereditor op uw Windows apparaat
- Instellingen wijzigen via PowerShell-cmdlets
- Beveiligingsinstellingen bewerken of verwijderen via groepsbeleid

Beveiliging van tamper voorkomt niet dat u uw beveiligingsinstellingen kunt bekijken. En tamperbeveiliging heeft geen invloed op de manier waarop antivirus-apps van derden zich registreren met de Windows-beveiliging app. Als uw organisatie E5 Windows 10 Enterprise gebruiken, kunnen afzonderlijke gebruikers de instelling voor de beveiliging van tamper niet wijzigen. in die gevallen wordt de beveiliging van de tamper beheerd door uw beveiligingsteam.

### <a name="what-do-you-want-to-do"></a>Wat wilt u doen?

| Als u deze taak wilt uitvoeren... | Zie deze sectie... |
|:---|:---|
| Beveiliging van manipulaties in uw tenant beheren <p>Gebruik de Microsoft Defender-beveiligingscentrum om de beveiliging van de tamper in of uit te schakelen | [Beveiliging van fraude voor uw organisatie beheren met behulp van de Microsoft Defender-beveiligingscentrum](#manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center) |
| Beveiligingsinstellingen voor tampers in uw organisatie aanpassen <p>Gebruik Intune (Microsoft Endpoint Manager) om tamperbeveiliging in of uit te schakelen. Met deze methode kunt u de beveiligingsbeveiliging voor sommige of alle gebruikers configureren. | [Beveiliging van fraude voor uw organisatie beheren met Intune](#manage-tamper-protection-for-your-organization-using-intune) |
| Beveiligingsbeveiliging voor tamper in- of uitschakelen voor uw organisatie met Configuration Manager | [Beveiliging van fraude voor uw organisatie beheren met tenant attach met Configuration Manager, versie 2006](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006) |
| Beveiligingsbeveiliging voor een afzonderlijk apparaat in- of uitschakelen | [Beveiliging van manipulaties beheren op een afzonderlijk apparaat](#manage-tamper-protection-on-an-individual-device) |
| Details weergeven over pogingen tot geknoei op apparaten | [Informatie weergeven over pogingen tot geknoei](#view-information-about-tampering-attempts) |
| Uw beveiligingsaanbevelingen bekijken | [Beveiligingsaanbevelingen controleren](#review-your-security-recommendations) |
| Bekijk de lijst met veelgestelde vragen (veelgestelde vragen) | [Door de veelgestelde vragen bladeren](#view-information-about-tampering-attempts) |

Afhankelijk van de methode of het beheerprogramma dat u gebruikt om tamper-beveiliging in te stellen, is er mogelijk een afhankelijkheid van KAARTEN (beveiliging in de cloud). 

In de volgende tabel vindt u informatie over de methoden, hulpmiddelen en afhankelijkheden.

| De manier waarop beveiliging van Tamper is ingeschakeld  | Afhankelijkheid van KAARTEN (beveiliging in de cloud)    |
|:----|:----|
| Microsoft Intune  | Nee |
| Microsoft Endpoint Configuration Manager + Tenant Attach  |     Nee  |
| Microsoft Defender-beveiligingscentrum ( [https://securitycenter.microsoft.com](https://securitycenter.microsoft.com) )    |     Ja |
| Microsoft 365 beveiligingscentrum ( [https://security.microsoft.com](https://security.microsoft.com) )  |     Ja  |

## <a name="manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center"></a>Beveiliging van fraude voor uw organisatie beheren met behulp van de Microsoft Defender-beveiligingscentrum

Met de Microsoft Defender-beveiligingscentrum ( ) kunt u de beveiliging van tampers in- of uitschakelen voor uw [https://securitycenter.windows.com](https://securitycenter.windows.com) tenant. Hier zijn een paar punten waar u rekening mee moet houden:

- Momenteel is de optie voor het beheren van de beveiliging van Microsoft Defender-beveiligingscentrum standaard ingeschakeld voor nieuwe implementaties. Voor bestaande implementaties is tamperbeveiliging beschikbaar op basis van een opt-in, met plannen om in de nabije toekomst te kiezen voor de standaardmethode. (Als u wilt kiezen, kiest u in Microsoft Defender-beveiligingscentrum de **Instellingen**  >  **Geavanceerde functies**  >  **Tamper-beveiliging**.) 

- Wanneer u de Microsoft Defender-beveiligingscentrum voor het beheren van de beveiliging van de tamper, hoeft u Intune of de tenant attach-methode niet te gebruiken.

- Wanneer u de beveiliging van de tamper in de Microsoft Defender-beveiligingscentrum beheert, wordt de instelling breed toegepast op de tenant, wat van invloed is op al uw apparaten waarop Windows 10, Windows Server 2016 of Windows Server 2019 wordt uitgevoerd. Gebruik [Intune](#manage-tamper-protection-for-your-organization-using-intune) of Configuration Manager met tenant attach om de beveiliging van de manipulaties (zoals het hebben van beveiliging tegen geknoei op sommige apparaten, maar voor andere apparaten) te [finetunen.](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)

- Als u een hybride omgeving hebt, hebben beveiligingsinstellingen die zijn geconfigureerd in Intune voorrang op instellingen die zijn geconfigureerd in de Microsoft Defender-beveiligingscentrum. 

### <a name="requirements-for-managing-tamper-protection-in-the-microsoft-defender-security-center"></a>Vereisten voor het beheren van de beveiliging van tamper in de Microsoft Defender-beveiligingscentrum

- U moet over de juiste [machtigingen zijn,](/microsoft-365/security/defender-endpoint/assign-portal-access)zoals globale beheerder, beveiligingsbeheerder of beveiligingsbewerkingen.

- Op Windows apparaten moet een van de volgende versies van Windows:
   - Windows 10
   - [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
   - Windows Server, versie [1803](/windows/release-health/status-windows-10-1803) of hoger
   - [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)
   - Zie voor meer informatie over releases [Windows 10 releasegegevens.](/windows/release-health/release-information)

- Uw apparaten moeten zijn [onboarded bij Microsoft Defender voor Eindpunt.](/microsoft-365/security/defender-endpoint/onboarding)

- Uw apparaten moeten versie 4.18.2010.7 (of hoger) en anti-malware-engine versie 1.1.17600.5 (of hoger) gebruiken. ([Beheer Microsoft Defender Antivirus updates en pas basislijnen toe](manage-updates-baselines-microsoft-defender-antivirus.md).)

- [Beveiliging in de cloud](enable-cloud-protection-microsoft-defender-antivirus.md) moet zijn ingeschakeld.

### <a name="turn-tamper-protection-on-or-off-in-the-microsoft-defender-security-center"></a>Beveiligingsbeveiliging voor tamper in- of uitschakelen in de Microsoft Defender-beveiligingscentrum 

![Beveiligingsbeveiliging voor tamper in de Microsoft Defender-beveiligingscentrum](images/mde-turn-tamperprotect-on.png)

1. Ga naar het Microsoft Defender-beveiligingscentrum ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) en meld u aan.

2. Kies **Instellingen**.

3. Ga naar **Algemene**  >  **geavanceerde functies** en schakel de beveiliging van de tamper in.

## <a name="manage-tamper-protection-for-your-organization-using-intune"></a>Beveiliging van fraude voor uw organisatie beheren met Intune

Als u deel uitmaakt van het beveiligingsteam van uw organisatie en uw abonnement [Intune](/intune/fundamentals/what-is-intune)bevat, kunt u de beveiliging van tamper in- of uitschakelen voor uw organisatie in het Microsoft Endpoint Manager-beheercentrum ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ). Gebruik Intune als u de beveiligingsinstellingen voor geknoeidheid wilt aanpassen. Als u bijvoorbeeld de beveiliging van manipulaties op sommige apparaten wilt inschakelen, maar niet alle apparaten, gebruikt u Intune.

### <a name="requirements-for-managing-tamper-protection-in-intune"></a>Vereisten voor het beheren van beveiliging tegen geknoei in Intune

- U moet over de juiste [machtigingen zijn,](/microsoft-365/security/defender-endpoint/assign-portal-access)zoals globale beheerder, beveiligingsbeheerder of beveiligingsbewerkingen.

- Uw organisatie gebruikt [Intune om apparaten te beheren.](/intune/fundamentals/what-is-device-management) ([Intune-licenties](/intune/fundamentals/licenses) zijn vereist; Intune is opgenomen in Microsoft 365 E5.)

- Uw Windows apparaten moeten worden uitgevoerd Windows 10 OS [1709,](/windows/release-health/status-windows-10-1709) [1803,](/windows/release-health/status-windows-10-1803) [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019) of hoger. (Zie voor meer informatie over releases [Windows 10 releasegegevens](/windows/release-health/release-information).)

- U moet de beveiliging Windows [](https://www.microsoft.com/wdsi/definitions) beveiligingsinformatie die is bijgewerkt naar versie 1.287.60.0 (of hoger).

- Uw apparaten moeten versie 4.18.1906.3 (of hoger) en anti-malware-engine versie 1.1.15500.X (of hoger) gebruiken. ([Beheer Microsoft Defender Antivirus updates en pas basislijnen toe](manage-updates-baselines-microsoft-defender-antivirus.md).)

### <a name="turn-tamper-protection-on-or-off-in-intune"></a>Beveiliging voor geknoei in -of uitschakelen in Intune

![Beveiliging voor geknoei in- en uit te zetten met Intune](images/turnontamperprotect-MEM.png)

1. Ga naar het [Microsoft Endpoint Manager beheercentrum en](https://endpoint.microsoft.com) meld u aan met uw werk- of schoolaccount.

2. Selecteer   >  **Configuratieprofielen voor apparaten.**

3. Maak een profiel met de volgende instellingen:
    - **Platform: Windows 10 en hoger**
    - **Profieltype: Endpoint-beveiliging**
    - **Categorie: Microsoft Defender-beveiligingscentrum**
    - **Beveiliging van tamper: ingeschakeld**

4. Wijs het profiel toe aan een of meer groepen.

### <a name="are-you-using-windows-os-1709-1803-or-1809"></a>Gebruikt u Windows OS 1709, 1803 of 1809?

Als u Windows 10 OS [1709,](/windows/release-health/status-windows-10-1709) [1803](/windows/release-health/status-windows-10-1803)of [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019)gebruikt, ziet u geen Tamper **Protection** in de Windows-beveiliging app. In plaats daarvan kunt u PowerShell gebruiken om te bepalen of beveiliging van een tamper is ingeschakeld.

#### <a name="use-powershell-to-determine-whether-tamper-protection-is-turned-on"></a>PowerShell gebruiken om te bepalen of tamperbeveiliging is ingeschakeld

1. Open de Windows PowerShell app.

2. Gebruik de [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus?preserve-view=true&view=win10-ps) PowerShell-cmdlet.

3. Zoek in de lijst met resultaten `IsTamperProtected` naar . (Een waarde van *waar betekent* dat tamperbeveiliging is ingeschakeld.)

## <a name="manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006"></a>Beveiliging van fraude voor uw organisatie beheren met Configuration Manager, versie 2006

Als u versie [2006](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2006)van Configuration Manager gebruikt, kunt u beveiligingsinstellingen voor geknoeid beheren op Windows 10, Windows Server 2016 en Windows Server 2019 met behulp van de methode *tenant attach*. Met Tenant attach kunt u uw on-premises Configuration Manager-apparaten synchroniseren met het Microsoft Endpoint Manager-beheercentrum en vervolgens beveiligingsconfiguratiebeleid voor eindpunten leveren aan on-premises verzamelingen & apparaten.

:::image type="content" source="images/win-security- exp-policy-endpt-security.png" alt-text="Windows-beveiliging ervaring in Endpoint Manager":::

> [!NOTE]
> De procedure kan worden gebruikt om de beveiliging van tamper uit te breiden naar apparaten met Windows 10 en Windows Server 2019. Controleer de vereisten en andere informatie in de bronnen die in deze procedure worden vermeld.

1. Tenant attach instellen. Zie voor meer informatie [Microsoft Endpoint Manager tenant attach: Apparaatsynchronisatie en apparaatacties.](/mem/configmgr/tenant-attach/device-sync-actions)

2. Ga in [Microsoft Endpoint Manager beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431)naar **Endpoint security**  >  **Antivirus** en kies + Beleid **maken.**<br/> 
   - Selecteer in **de lijst Platform** Windows 10 en Windows Server **(ConfigMgr)**.  
   - Selecteer in **de** lijst Profiel **Windows-beveiliging ervaring (voorbeeld)**. <br/>

3. Implementeer het beleid naar uw apparaatverzameling.

### <a name="need-help-with-this-method"></a>Hulp nodig bij deze methode? 

Zie de volgende bronnen:

- [Instellingen voor het Windows-beveiliging ervaringsprofiel in Microsoft Intune](/mem/intune/protect/antivirus-security-experience-windows-settings)
- [Tech Community Blog: Tamper Protection aankondigen voor Configuration Manager Tenant Attach clients](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

## <a name="manage-tamper-protection-on-an-individual-device"></a>Beveiliging van manipulaties beheren op een afzonderlijk apparaat

> [!NOTE]
> Beveiligingsblokken voor tamper proberen de instellingen Microsoft Defender Antivirus via het register te wijzigen.
>
> Ga naar Windows-beveiliging en werk Beveiligingsintelligentie bij naar versie 1.287.60.0 of hoger om ervoor te zorgen dat beveiligingsbeveiliging geen invloed heeft op beveiligingsproducten van derden of bedrijfsinstallatiescripts die deze **instellingen** wijzigen.  (Zie [Beveiligingsinformatieupdates](https://www.microsoft.com/wdsi/definitions).)
>
> Nadat u deze update hebt uitgebracht, blijft de beveiliging van de tamper uw registerinstellingen beveiligen en worden logboeken geprobeerd deze te wijzigen zonder fouten te retourneren.

Als u een thuisgebruiker bent of als u niet onderworpen bent aan instellingen die worden beheerd door een beveiligingsteam, kunt u de Windows-beveiliging gebruiken om de beveiliging van tampers te beheren. U moet over de juiste beheerdersmachtigingen op uw apparaat zijn om de beveiligingsinstellingen te kunnen wijzigen, zoals beveiliging tegen geknoei.

Dit ziet u in de Windows-beveiliging app:

![Beveiliging van tamper is ingeschakeld in Windows 10 Home](images/tamperprotectionturnedon.png)

1. Selecteer **Start** en begin beveiliging te *typen.* Selecteer in de zoekresultaten **Windows-beveiliging.**

2. Selecteer **Virusbeveiliging &**  >  **bedreigingsbeveiliging & beveiligingsinstellingen voor bedreigingen.**

3. Beveiligingsbeveiliging **voor Tamper instellen** op **Aan** of **Uit.**

## <a name="view-information-about-tampering-attempts"></a>Informatie weergeven over pogingen tot geknoei

Pogingen tot geknoei geven meestal grotere cyberaanvallen aan. Slechte actors proberen de beveiligingsinstellingen te wijzigen als een manier om te blijven bestaan en niet te worden gedetecteerd. Als u deel uitmaakt van het beveiligingsteam van uw organisatie, kunt u informatie over dergelijke pogingen bekijken en vervolgens passende acties ondernemen om bedreigingen te beperken.

Wanneer er een poging tot geknoei wordt gedetecteerd, wordt er een waarschuwing in de Microsoft Defender-beveiligingscentrum [(](/microsoft-365/security/defender-endpoint/portal-overview) [https://securitycenter.windows.com](https://securitycenter.windows.com) ).

![Microsoft Defender-beveiligingscentrum](images/tamperattemptalert.png)

Met [eindpuntdetectie en -respons](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) en [geavanceerde zoekmogelijkheden](/microsoft-365/security/defender-endpoint/advanced-hunting-overview) in Microsoft Defender voor Eindpunt kan uw beveiligingsteam dergelijke pogingen onderzoeken en aanpakken.

## <a name="review-your-security-recommendations"></a>Uw beveiligingsaanbevelingen bekijken

Tamperbeveiliging is geïntegreerd met [de mogelijkheden & Beveiligingsprobleembeheer.](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) [Beveiligingsaanbevelingen](/microsoft-365/security/defender-endpoint/tvm-security-recommendation) zijn onder andere om ervoor te zorgen dat de beveiliging van de tamper is ingeschakeld. U kunt bijvoorbeeld zoeken in *tamper,* zoals wordt weergegeven in de volgende afbeelding:

![Tamperbeveiliging resulteert in beveiligingsaanbevelingen](/images/securityrecs-tamperprotect.jpg)

In de resultaten kunt u Beveiliging voor **geknoeid in-** en uit- en in-/uit-/uit- of in- of uit- en uit- of uit- of uit- en

![Beveiligingsbeveiliging voor geknoeid in- en uit-](images/tamperprotectsecurityrecos.png)

Zie [Threat & Vulnerability Management in](/microsoft-365/security/defender-endpoint/tvm-dashboard-insights#threat--vulnerability-management-in-microsoft-defender-security-center)Microsoft Defender-beveiligingscentrum voor meer informatie over Threat & Vulnerability Management .

## <a name="frequently-asked-questions"></a>Veelgestelde vragen

### <a name="to-which-windows-os-versions-is-configuring-tamper-protection-is-applicable"></a>Op welke Windows besturingssysteemversies is het configureren van tamperbeveiliging van toepassing?

Windows 10 OS [1709](/windows/release-health/status-windows-10-1709), [1803](/windows/release-health/status-windows-10-1803), [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019)of hoger, samen met [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint).

Als u Configuration Manager, versie 2006, met tenant attach gebruikt, kan de beveiliging van tamper worden uitgebreid tot Windows Server 2019. Zie [Tenant attach: Create and deploy endpoint security Antivirus policy from the admin center (preview)](/mem/configmgr/tenant-attach/deploy-antivirus-policy).

### <a name="will-tamper-protection-have-any-impact-on-third-party-antivirus-registration"></a>Heeft fraudebeveiliging invloed op de registratie van antivirussoftware van derden?

Nee. Antivirusaanbiedingen van derden blijven zich registreren bij de Windows-beveiliging toepassing.

### <a name="what-happens-if-microsoft-defender-antivirus-is-not-active-on-a-device"></a>Wat gebeurt er als Microsoft Defender Antivirus niet actief is op een apparaat?

Apparaten die zijn aan boord van Microsoft Defender voor Eindpunt, hebben Microsoft Defender Antivirus in passieve modus. De beveiliging van tamper blijft de service en de functies ervan beschermen. 

### <a name="how-can-i-turn-tamper-protection-onoff"></a>Hoe kan ik de beveiliging van tamper in-/uitschakelen?

Als u een thuisgebruiker bent, zie [Beveiligingsbeveiliging voor geknoeid beheren op een afzonderlijk apparaat.](#manage-tamper-protection-on-an-individual-device)

Als u een organisatie bent die [Microsoft Defender](/microsoft-365/security/defender-endpoint)voor Eindpunt gebruikt, kunt u de beveiliging van manipulaties in Intune beheren, vergelijkbaar met de manier waarop u andere functies voor eindpuntbeveiliging beheert. Zie de volgende secties van dit artikel: 

- [Beveiliging van fraude beheren met Intune](#manage-tamper-protection-for-your-organization-using-intune)
- [Beveiliging van fraude beheren met Configuration Manager, versie 2006](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)
- [Beveiliging van tamper beheren met behulp van de Microsoft Defender-beveiligingscentrum](#manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center) 

### <a name="how-does-configuring-tamper-protection-in-intune-affect-how-i-manage-microsoft-defender-antivirus-through-my-group-policy"></a>Hoe beïnvloedt het configureren van beveiliging tegen geknoei in Intune de manier waarop ik Microsoft Defender Antivirus mijn groepsbeleid beheer?

Uw normale groepsbeleid is niet van toepassing op beveiliging tegen geknoei en wijzigingen in Microsoft Defender Antivirus instellingen worden genegeerd wanneer de beveiliging van de tamper is ingesteld. 

### <a name="for-microsoft-defender-for-endpoint-is-configuring-tamper-protection-in-intune-targeted-to-the-entire-organization-only"></a>Voor Microsoft Defender voor Eindpunt is het configureren van beveiliging tegen geknoei in Intune alleen bedoeld voor de hele organisatie?

Het configureren van beveiliging tegen manipulaties in Intune of Microsoft Endpoint Manager kan worden gericht op uw hele organisatie en op specifieke apparaten en gebruikersgroepen.

### <a name="can-i-configure-tamper-protection-in-microsoft-endpoint-configuration-manager"></a>Kan ik Tamper Protection configureren in Microsoft Endpoint Configuration Manager?

Als u tenant attach gebruikt, kunt u deze Microsoft Endpoint Configuration Manager. Zie de volgende bronnen:
- [Beveiliging van fraude voor uw organisatie beheren met Configuration Manager, versie 2006](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)
- [Tech Community-blog: Tamper Protection for Configuration Manager Tenant Attach clients aankondigen](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

### <a name="i-have-the-windows-e3-enrollment-can-i-use-configuring-tamper-protection-in-intune"></a>Ik heb de Windows E3-inschrijving. Kan ik in Intune de beveiligingsbeveiliging voor geknoeid configureren?

Op dit moment is het configureren van beveiliging tegen geknoei in Intune alleen beschikbaar voor klanten met [Microsoft Defender voor Eindpunt.](/microsoft-365/security/defender-endpoint)

### <a name="what-happens-if-i-try-to-change-microsoft-defender-for-endpoint-settings-in-intune-microsoft-endpoint-configuration-manager-and-windows-management-instrumentation-when-tamper-protection-is-enabled-on-a-device"></a>Wat gebeurt er als ik microsoft Defender voor eindpuntinstellingen probeer te wijzigen in Intune, Microsoft Endpoint Configuration Manager en Windows Management Instrumentation wanneer Tamper Protection is ingeschakeld op een apparaat?

U kunt de functies die zijn beveiligd door beveiligingsfuncties voor geknoeid, niet wijzigen. dergelijke wijzigingsaanvragen worden genegeerd.

### <a name="im-an-enterprise-customer-can-local-admins-change-tamper-protection-on-their-devices"></a>Ik ben een zakelijke klant. Kunnen lokale beheerders de beveiliging van tamper op hun apparaten wijzigen?

Nee. Lokale beheerders kunnen de beveiligingsinstellingen voor manipulaties niet wijzigen of wijzigen.

### <a name="what-happens-if-my-device-is-onboarded-with-microsoft-defender-for-endpoint-and-then-goes-into-an-off-boarded-state"></a>Wat gebeurt er als mijn apparaat is onboarded met Microsoft Defender voor Endpoint en vervolgens in een niet-boarded toestand wordt gebruikt?

Als een apparaat is uitgeschakeld vanuit Microsoft Defender voor Eindpunt, is de beveiliging van de tamper ingeschakeld, wat de standaardtoestand is voor niet-bemande apparaten. 

### <a name="will-there-be-an-alert-about-tamper-protection-status-changing-in-the-microsoft-defender-security-center"></a>Wordt er een waarschuwing ontvangen over het wijzigen van de status van de beveiligingsstatus van de Microsoft Defender-beveiligingscentrum?

Ja. De waarschuwing wordt weergegeven onder [https://securitycenter.microsoft.com](https://securitycenter.microsoft.com) **Waarschuwingen.**

Uw beveiligingsteam kan ook query's voor het zoeken gebruiken, zoals het volgende voorbeeld:

`DeviceAlertEvents | where Title == "Tamper Protection bypass"`

[Informatie weergeven over pogingen tot geknoei.](#view-information-about-tampering-attempts)

## <a name="see-also"></a>Zie ook

[U kunt Windows pc's beveiligen met Endpoint Protection voor Microsoft Intune](/intune/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)

[Een overzicht krijgen van Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint)

[Samen beter: Microsoft Defender Antivirus en Microsoft Defender voor Eindpunt](why-use-microsoft-defender-antivirus.md)