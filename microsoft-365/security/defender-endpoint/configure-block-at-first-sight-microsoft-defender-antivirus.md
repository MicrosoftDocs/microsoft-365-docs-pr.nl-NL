---
title: Blok op het eerste gezicht inschakelen om malware binnen enkele seconden te detecteren
description: Schakel het blok op het eerste gezicht in om malware binnen enkele seconden te detecteren en te blokkeren.
keywords: scannen, blokkeren op het eerste gezicht, malware, first sight, cloud, defender, antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: marcmcc
manager: dansimp
ms.custom: nextgen
ms.date: 04/28/2021
ms.technology: mde
ms.openlocfilehash: d4db3549d04e5883f02ba263c06371371d385022
ms.sourcegitcommit: 8c89bc1d106b4716b07a1977d57e4d9ef98aecb3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/29/2021
ms.locfileid: "52079201"
---
# <a name="turn-on-block-at-first-sight"></a>Blokkeren op het eerste gezicht inschakelen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

In dit artikel wordt een antivirus-/antimalwarefunctie beschreven die 'blok op het eerste gezicht' wordt genoemd en wordt beschreven hoe u blokkering op het eerste gezicht voor uw organisatie kunt inschakelen. 

> [!TIP]
> Dit artikel is bedoeld voor bedrijfsbeheerders en IT-professionals die beveiligingsinstellingen voor organisaties beheren. Als u geen beheerder of IT-beheerder bent, maar u op het eerste gezicht vragen hebt over blokkering, zie Geen ondernemingsbeheerder of [IT-professional?](#not-an-enterprise-admin-or-it-pro).

## <a name="what-is-block-at-first-sight"></a>Wat is 'blok op het eerste gezicht'?

Blokkering op het eerste gezicht is een bedreigingsbeveiligingsfunctie van de volgende generatie die nieuwe malware detecteert en deze binnen enkele seconden blokkeert. Blokkeren op het eerste gezicht is ingeschakeld wanneer bepaalde beveiligingsinstellingen zijn ingeschakeld. Deze instellingen zijn:

- Beveiliging in de cloud; 
- Een opgegeven voorbeeldinzendings time-out (zoals 50 seconden); en 
- Een bestandsblokkeringsniveau van hoog. 

In de meeste bedrijfsorganisaties zijn de instellingen die nodig zijn om blokkering op het eerste gezicht in te stellen, geconfigureerd met Microsoft Defender Antivirus-implementaties. 

## <a name="how-it-works"></a>Hoe het werkt

Wanneer Microsoft Defender Antivirus een verdacht, maar niet-gedetecteerd bestand tegenkomt, wordt de back-over van onze cloudbeveiliging opgevraagd. Met de cloudbackend worden heuristiek, machine learning en geautomatiseerde analyse van het bestand toegepast om te bepalen of de bestanden schadelijk zijn of niet.

Microsoft Defender Antivirus gebruikt meerdere detectie- en preventietechnologieën om nauwkeurige, intelligente en realtime beveiliging te bieden. 

![Lijst met MICROSOFT Defender AV-engines](images/microsoft-defender-atp-next-generation-protection-engines.png)  

> [!TIP]
> Zie deze blog voor meer informatie: Maak kennis met de geavanceerde technologieën die centraal staan in de volgende generatie beveiliging van Microsoft Defender voor [Endpoint.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)

## <a name="a-few-things-to-know-about-block-at-first-sight"></a>Een paar dingen die u moet weten over blokkeren op het eerste gezicht

- In Windows 10, versie 1803 of hoger, kan blokkering op het eerste gezicht niet-draagbare uitvoerbare bestanden (zoals JS, VBS of macro's) en uitvoerbare bestanden blokkeren.

- Blokkeren gebruikt op het eerste gezicht alleen de back-mail voor cloudbeveiliging voor uitvoerbare bestanden en niet-draagbare uitvoerbare bestanden die van internet worden gedownload of die afkomstig zijn uit de internetzone. Een hashwaarde van het EXE-bestand wordt gecontroleerd via de back-mail van de cloud om te bepalen of het bestand een eerder niet-gedetecteerd bestand is.

- Als de cloudback-up geen bepaling kan maken, wordt het bestand vergrendeld door Microsoft Defender Antivirus en wordt een kopie naar de cloud geüpload. De cloud voert meer analyses uit om tot een bepaling te komen voordat het bestand kan worden uitgevoerd of blokkeert in alle toekomstige ontmoetingen, afhankelijk van of het bestand schadelijk is of niet een bedreiging.

- In veel gevallen kan dit proces de reactietijd voor nieuwe malware beperken van uren tot seconden.

- U kunt [opgeven hoelang een bestand niet mag](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) worden uitgevoerd terwijl het bestand wordt geanalyseerd door de beveiligingsservice in de cloud. En u kunt het bericht aanpassen dat op de [bureaubladen](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) van gebruikers wordt weergegeven wanneer een bestand wordt geblokkeerd. U kunt de bedrijfsnaam, contactgegevens en bericht-URL wijzigen.

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a>Blok op het eerste gezicht in- en uit- zetten met Microsoft Intune

> [!TIP]
> Microsoft Intune maakt nu deel uit van Microsoft Endpoint Manager.

1. Navigeer in het Microsoft Endpoint Manager-beheercentrum [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () naar   >  **Apparatenconfiguratieprofielen.**

2. Selecteer of maak een profiel met het **profieltype Apparaatbeperkingen.**

3. Stel in **de configuratie-instellingen** voor het apparaatbeperkingenprofiel de volgende instellingen in of bevestig deze onder **Microsoft Defender Antivirus:**

   - **Beveiliging in de cloud:** ingeschakeld
   - **Bestandsblokkeringsniveau:** hoog
   - **Tijdsextensie voor het scannen van bestanden door de cloud:** 50
   - **Gebruikers vragen vóór voorbeeldinzending:** Alle gegevens verzenden zonder dat u daarom wordt gevraagd

   ![Config in Intune](images/defender/intune-block-at-first-sight.png)

4. Sla uw instellingen op.

> [!TIP]
> - Als u het blokkeringsniveau voor bestanden **instelt op Hoog,** wordt een sterk detectieniveau toegepast. In het onwaarschijnlijke geval dat bestandsblokkering een fout-positieve detectie van legitieme bestanden veroorzaakt, kan uw beveiligingsteam in quarantaine geplaatste bestanden [herstellen.](./restore-quarantined-files-microsoft-defender-antivirus.md)
> - Zie Apparaatbeperkingen configureren in Microsoft Intune voor meer informatie over het configureren van beperkingen voor Microsoft Defender [Antivirus-apparaten in Intune.](/intune/device-restrictions-configure)
> - Zie Apparaatbeperkingen voor [Windows 10 (en nieuwere) instellingen in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)voor een lijst met beperkingen voor Microsoft Defender Antivirus-apparaten in Intune.

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a>Blok op het eerste gezicht in- en uit- zetten met Microsoft Endpoint Manager

> [!TIP]
> Als u op zoek bent naar Microsoft Endpoint Configuration Manager, is het nu onderdeel van Microsoft Endpoint Manager.

1. Ga in Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) naar **Endpoint security**  >  **Antivirus**.

2. Selecteer een bestaand beleid of maak een nieuw beleid met het **profieltype Microsoft Defender Antivirus.**

3. Stel de volgende configuratie-instellingen in of bevestig deze:

   - **Beveiliging in de cloud in- en uit-** zetten: Ja
   - **Beveiligingsniveau in de cloud:** hoog
   - **Defender Cloud Extended Timeout in Seconds**: 50

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="Instellingen blokkeren op het eerste gezicht in Endpoint Manager":::

4. Het Microsoft Defender Antivirus-profiel toepassen op een groep, zoals **Alle gebruikers,** **Alle apparaten** of Alle gebruikers **en apparaten.**

## <a name="turn-on-block-at-first-sight-with-group-policy"></a>Blok op het eerste gezicht in- en uit- zetten met Groepsbeleid

> [!NOTE]
> Het is raadzaam Intune of Microsoft Endpoint Manager te gebruiken om blok op het eerste gezicht in te zetten. 

1. Open op de computer groepsbeleidsbeheer de console Groepsbeleidsbeheer, klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **Bewerken.** [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)) 

2. Ga met **de Editor voor groepsbeleidsbeheer** naar **Beheersjablonen voor**  >    >  **computerconfiguratie Windows Components** Microsoft Defender  >  **Antivirus**  >  **MAPS**. 

3. Dubbelklik in de sectie KAARTEN op De functie **Blokkeren** op het eerste gezicht configureren en stel deze in op **Ingeschakeld** en selecteer **OK.**

    > [!IMPORTANT]
    > Als u **de instelling Altijd vragen (0) instelt,** wordt de beveiligingstoestand van het apparaat lager. Instelling voor **Nooit verzenden (2)** betekent dat blok op het eerste gezicht niet werkt.

4. Dubbelklik in de sectie KAARTEN op Bestandsvoorbeelden verzenden wanneer verdere analyse **is** vereist en stel deze in op **Ingeschakeld.** Selecteer **onder Bestandsvoorbeelden verzenden wanneer verdere analyse is vereist** de optie Alle **steekproeven verzenden** en selecteer **ok.**

5. U kunt het groepsbeleidsobject opnieuw in uw netwerk herschikken, zoals u gewoonlijk doet.

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-client-devices"></a>Op het eerste gezicht bevestigen dat blok is ingeschakeld op afzonderlijke clientapparaten

U kunt bevestigen dat blok op het eerste gezicht is ingeschakeld op afzonderlijke clientapparaten met de Windows Security-app. Blok op het eerste gezicht wordt automatisch ingeschakeld, zolang beveiliging in de **cloud** en Automatische **voorbeeldinzending** beide zijn ingeschakeld.

1. Open de Windows Security-app.

2. Selecteer **Virusbeveiliging & bedreiging** en selecteer vervolgens onder **Virusbeveiliging**& instellingen voor bedreigingsbeveiliging de optie **Instellingen beheren.**

   ![Schermafbeelding van het label & beveiligingsinstellingen voor virussen in de Windows Security-app](images/defender/wdav-protection-settings-wdsc.png)

3. Controleer of **beveiliging in de cloud en** Automatische **voorbeeldinzending** beide zijn ingeschakeld.

> [!NOTE]
> - Als de vereiste instellingen zijn geconfigureerd en geïmplementeerd met groepsbeleid, zijn de instellingen die in deze sectie worden beschreven grijs en niet beschikbaar voor gebruik op afzonderlijke eindpunten. 
> - Wijzigingen die zijn aangebracht via een groepsbeleidsobject, moeten eerst worden geïmplementeerd op afzonderlijke eindpunten voordat de instelling wordt bijgewerkt in Windows-instellingen.

## <a name="validate-block-at-first-sight-is-working"></a>Blok op het eerste gezicht valideren werkt

Als u wilt controleren of de functie werkt, volgt u de richtlijnen in Verbindingen tussen uw netwerk en [de cloud valideren.](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)

## <a name="turn-off-block-at-first-sight"></a>Blok op het eerste gezicht uitschakelen

> [!CAUTION]
> Als u blokkering op het eerste gezicht uit schakelen, wordt de beveiligingstoestand van uw apparaat(en) en uw netwerk lager.

U kunt blokkering op het eerste gezicht uitschakelen als u de vereiste instellingen wilt behouden zonder blokkering op het eerste gezicht te gebruiken. U kunt blokkering op het eerste gezicht tijdelijk uitschakelen om te zien hoe deze functie van invloed is op uw netwerk. Het is echter niet raadzaam om blokkering op het eerste gezicht permanent uit te uitschakelen.

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a>Blok op het eerste gezicht uitschakelen met Microsoft Endpoint Manager

1. Ga naar het Microsoft Endpoint Manager-beheercentrum [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () en meld u aan.

2. Ga naar **Endpoint Security**  >  **Antivirus** en selecteer vervolgens uw Microsoft Defender Antivirusbeleid.

3. Kies **onder** Beheren de optie **Eigenschappen.**

4. Kies naast **Configuratie-instellingen** de optie **Bewerken.**

5. Een of meer van de volgende instellingen wijzigen:

   - Stel **Beveiliging in de cloud in op** **Nee** of **Niet geconfigureerd.**
   - Stel **beveiligingsniveau in de cloud in** op Niet **geconfigureerd.**
   - Het selectievakje voor **defender cloud verlengde time-out in** seconden uit.

6. Controleer uw instellingen en sla deze op.

### <a name="turn-off-block-at-first-sight-with-group-policy"></a>Blok op het eerste gezicht uitschakelen met Groepsbeleid

1. Open op uw groepsbeleidscomputer de console Groepsbeleidsbeheer, [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **bewerken.**

2. Ga met **de Editor voor groepsbeleidsbeheer** naar **Computerconfiguratie** en selecteer **Beheersjablonen.**

3. Vouw de boom uit via **Windows-onderdelen**  >  **Microsoft Defender Antivirus**  >  **MAPS.**

4. Dubbelklik op **De functie 'Blokkeren op het eerste gezicht' configureren** en stel de optie in op **Uitgeschakeld.**

    > [!NOTE]
    > Door blokkering op het eerste gezicht uit te schakelen, wordt het vereiste groepsbeleid niet uitgeschakeld of gewijzigd.

## <a name="not-an-enterprise-admin-or-it-pro"></a>Geen ondernemingsbeheerder of IT-professional?

Als u geen ondernemingsbeheerder of IT-professional bent, maar u op het eerste gezicht vragen hebt over blokkering, is deze sectie voor u. Blokkering op het eerste gezicht is een functie voor bedreigingsbeveiliging waarmee malware binnen enkele seconden wordt gedetecteerd en geblokkeerd. Hoewel er op het eerste gezicht geen specifieke instelling met de naam 'Blokkeren' is, is de functie ingeschakeld wanneer bepaalde instellingen zijn geconfigureerd op uw apparaat.

### <a name="how-to-manage-block-at-first-sight-on-or-off-on-your-own-device"></a>Blok beheren op het eerste gezicht in of uit op uw eigen apparaat

Als u een persoonlijk apparaat hebt dat niet door een organisatie wordt beheerd, vraagt u zich misschien af hoe u blok op het eerste gezicht in- of uit kunt schakelen. U kunt de Windows Security-app gebruiken om blok op het eerste gezicht te beheren.

1. Open de Windows Security-app op uw Windows 10-computer.

2. Selecteer **Virusbeveiliging & bedreiging**.

3. Selecteer **onder Virusbeveiliging & instellingen** voor bedreigingsbeveiliging de optie **Instellingen beheren.**

4. Volg een van de volgende stappen:

   - Als u blok op het eerste  gezicht wilt inschakelen, moet u ervoor zorgen dat zowel cloudbeveiliging als Automatische **voorbeeldinzending** beide zijn ingeschakeld.

   - Als u blokkering op het eerste gezicht wilt uitschakelen, schakelt u **beveiliging in** de cloud of **Automatische voorbeeldinzending uit.** <br/>
    
     > [!CAUTION]
     > Als u blok op het eerste gezicht uit wilt schakelen, wordt het beveiligingsniveau voor uw apparaat verlaagd. Het is niet raadzaam blok op het eerste gezicht permanent uit te uitschakelen. 


## <a name="see-also"></a>Zie ook

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Beveiliging via de cloud inschakelen](enable-cloud-protection-microsoft-defender-antivirus.md)
- [Beschermd blijven met Windows-beveiliging](https://support.microsoft.com/windows/stay-protected-with-windows-security-2ae0363d-0ada-c064-8b56-6a39afb6a963)