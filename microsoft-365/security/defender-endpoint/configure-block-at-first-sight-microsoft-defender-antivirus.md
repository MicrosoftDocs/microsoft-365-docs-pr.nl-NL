---
title: Blokkeren bij eerste detectie inschakelen om malware binnen enkele seconden te detecteren
description: De blokkeren bij eerste detectiefunctie inschakelen om malware binnen enkele seconden te detecteren en te blokkeren.
keywords: scannen, blokkeren bij eerste detectie, malware, eerste detectie, cloud, defender, antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: marcmcc
manager: dansimp
ms.custom: nextgen
ms.date: 04/28/2021
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ba0f2184ced21aea60b172d44936e3e2d36e5270
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274950"
---
# <a name="turn-on-block-at-first-sight"></a>Blokkeren bij eerste detectie inschakelen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

In dit artikel wordt een antivirus-/antimalwarefunctie beschreven genaamd 'blokkeren bij eerste detectie' en wordt beschreven hoe u blokkeren bij eerste detectie in kunt schakelen voor uw organisatie. 

> [!TIP]
> Dit artikel is bedoeld voor bedrijfsbeheerders en IT-professionals die beveiligingsinstellingen voor organisaties beheren. Zie [Geen ondernemingsbeheerder of IT-professional?](#not-an-enterprise-admin-or-it-pro) als u geen ondernemingsbeheerder of IT-professional bent, maar toch vragen hebt over blokkering bij eerste detectie.

## <a name="what-is-block-at-first-sight"></a>Wat is 'blokkeren bij eerste detectie'?

Blokkeren bij eerste detectie is een bedreigingsbeveiligingsfunctie van volgende generatie-beveiliging waarmee nieuwe malware wordt gedetecteerd en binnen enkele seconden wordt geblokkeerd. Blokkering bij eerste detectie is ingeschakeld wanneer bepaalde beveiligingsinstellingen zijn ingeschakeld. Deze instellingen omvatten:

- cloudbeveiliging; 
- een opgegeven time-out voor sample indienen (zoals 50 seconden); en 
- een hoog bestandsblokkeringsniveau. 

In de meeste ondernemingen zijn de instellingen geconfigureerd die nodig zijn om blokkeren bij eerste detectie mogelijk te maken met implementaties van Microsoft Defender Antivirus. 

## <a name="how-it-works"></a>Hoe het werkt

Als Microsoft Defender Antivirus een verdacht, maar niet-gedetecteerd bestand aantreft, wordt een query uitgevoerd op onze cloudbeveiligingsback-end. In de cloudback-end worden heuristische, machine learning- en geautomatiseerde analyses van het bestand toegepast om te bepalen of de bestanden schadelijk zijn dan wel geen bedreiging vormen.

Microsoft Defender Antivirus gebruikt meerdere technologieën voor detectie en preventie om nauwkeurige, intelligente en realtime bescherming te bieden. 

![Lijst met AV-engines voor Microsoft Defender](images/microsoft-defender-atp-next-generation-protection-engines.png)  

> [!TIP]
> Lees deze blog voor meer informatie: [Maak kennis met de geavanceerde technologieën die de kern vormen van de volgende generatie-beveiliging van Microsoft Defender voor Eindpunt](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).

## <a name="a-few-things-to-know-about-block-at-first-sight"></a>Enkele dingen die u moet weten over blokkeren bij eerste detectie

- In Windows 10, versie 1803 of hoger, kunnen door blokkeren bij eerste detectie niet-draagbare uitvoerbare bestanden (zoals JS-, VBS- of macro's) en uitvoerbare bestanden worden geblokkeerd.

- Blokkeren bij eerste detectie maakt alleen gebruik van de cloudbeveiligingsback-end voor uitvoerbare bestanden en niet-draagbare uitvoerbare bestanden die van het internet worden gedownload of die afkomstig zijn uit de Internetzone. Een hashwaarde van het EXE-bestand wordt gecontroleerd via de cloudback-end om te bepalen of het bestand een eerder niet-gedetecteerd bestand is.

- Als er in de cloudback-end geen bepaling kan worden gemaakt, vergrendelt Microsoft Defender Antivirus het bestand en uploadt het een kopie naar de cloud. De cloud voert meer analyses uit om te bepalen of het bestand kan worden uitgevoerd dan wel dient te worden geblokkeerd in alle toekomstige gevallen, afhankelijk van of het bestand schadelijk is dan wel geen bedreiging vormt.

- In veel gevallen kan dit proces de reactietijd voor nieuwe malware verminderen van uren tot seconden.

- U kunt [opgeven hoelang een bestand niet mag worden uitgevoerd](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) terwijl de cloudbeveiligingsservice het bestand analyseert. En u kunt [het bericht aanpassen dat wordt weergegeven op de desktopcomputers van gebruikers](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) wanneer een bestand wordt geblokkeerd. U kunt de bedrijfsnaam, contactgegevens en bericht-URL wijzigen.

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a>Blokkeren bij eerste detectie inschakelen met Microsoft Intune

> [!TIP]
> Microsoft Intune maakt nu deel uit van Microsoft Endpoint Manager.

1. Navigeer in het beheercentrum van Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) naar **Apparaten** > **Configuratieprofielen**.

2. Selecteer of maak een profiel met het **Apparaatbeperkingen** profieltype.

3. Stel in of bevestig in **Configuratie-instellingen** voor het apparaatbeperkingenprofiel de volgende instellingen onder **Microsoft Defender Antivirus**:

   - **Cloudbeveiliging**: Ingeschakeld
   - **Niveau voor bestandsblokkering**: Hoog
   - **Tijdsextensie voor het scannen van bestanden door de cloud**: 50
   - **Gebruikers vragen vóór sample indienen**: Alle gegevens verzenden zonder te vragen

   ![Intune-configuratie](images/defender/intune-block-at-first-sight.png)

4. Sla de instellingen op.

> [!TIP]
> - Door het niveau voor bestandsblokkering in te stellen op **Hoog** wordt een sterk detectieniveau toegepast. In het onwaarschijnlijke geval dat bestandsblokkering een fout-positieve detectie van legitieme bestanden veroorzaakt, kan uw beveiligingsteam [bestanden in quarantaine herstellen](./restore-quarantined-files-microsoft-defender-antivirus.md).
> - Zie voor meer informatie over het configureren van apparaatbeperkingen voor Microsoft Defender Antivirus in Intune [Instellingen voor apparaatbeperkingen configureren in Microsoft Intune](/intune/device-restrictions-configure).
> - Zie [Apparaatbeperkingsinstellingen in Intune voor Windows 10 (en hoger)](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)voor een lijst met apparaatbeperkingen in Intune voor Microsoft Defender Antivirus.

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a>Blokkeren bij eerste detectie inschakelen met Microsoft Endpoint Manager

> [!TIP]
> Als u op zoek bent naar Microsoft Endpoint Configuration Manager: het maakt nu deel uit van Microsoft Endpoint Manager.

1. Ga in Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) naar **Eindpuntbeveiliging** > **Antivirus**.

2. Selecteer een bestaand beleid of maak een nieuw beleid met het **Microsoft Defender Antivirus**-profieltype.

3. Stel de volgende configuratie-instellingen in of bevestig deze:

   - **Cloudbeveiliging inschakelen**: Ja
   - **Cloudbeveiligingsniveau**: Hoog
   - **Defender Cloud Extended Timeout in seconden**: 50

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="Blokkeren bij eerste detectie-instellingen in Endpoint Manager":::

4. Pas het Microsoft Defender Antivirus-profiel toe op een groep, zoals **Alle gebruikers**, **Alle apparaten** of **Alle gebruikers en apparaten**.

## <a name="turn-on-block-at-first-sight-with-group-policy"></a>Blokkeren bij eerste detectie inschakelen met Groepsbeleid

> [!NOTE]
> U wordt aangeraden Intune of Microsoft Endpoint Manager te gebruiken om blokkeren bij eerste detectie in te schakelen. 

1. Open op uw computer voor groepsbeleidsbeheer de [Groepsbeleidsbeheerconsole](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer **Bewerken**. 

2. Met de **Groepsbeleidsbeheerseditor** gaat u naar **Computerconfiguratie** > **Beheersjablonen** > **Windows Components** > **Microsoft Defender Antivirus** > **MAPS**. 

3. Dubbelklik in de sectie MAPS op **De functie 'Blokkeren bij eerste detectie' configureren**, stel deze in op **Ingeschakeld** en selecteer vervolgens **OK**.

    > [!IMPORTANT]
    > Als u **Altijd vragen (0)** inschakelt, wordt de beveiligingstoestand van het apparaat verlaagd. Instellen op **Verzend nooit (2)** betekent dat blokkeren bij eerste detectie niet werkt.

4. Dubbelklik in de sectie MAPS op **Bestandsvoorbeelden verzenden wanneer verdere analyse vereist is** en stel dit in op **Ingeschakeld**. Selecteer **Bestandsvoorbeelden verzenden wanneer verdere analyse vereist is** **Alle voorbeelden verzenden** en selecteer vervolgens **OK**.

5. Implementeer uw groepsbeleidsobject opnieuw in uw netwerk, zoals u dat gewoonlijk doet.

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-client-devices"></a>Bevestigen dat blokkeren bij eerste detectie is ingeschakeld op afzonderlijke clientapparaten

U kunt met de app voor Windows-beveiliging bevestigen dat blokkeren bij eerste detectie is ingeschakeld op afzonderlijke clientapparaten. Blokkeren bij eerste detectie wordt automatisch ingeschakeld mits **Cloudbeveiliging** en **Automatisch sample indienen** beide zijn ingeschakeld.

1. Open de app voor Windows-beveiliging.

2. Selecteer **Beveiliging tegen virussen en bedreigingen** en selecteer vervolgens onder **Instellingen voor virus- en bedreigingsbeveiliging** de optie **Instellingen beheren**.

   ![Schermafbeelding van het instellingenlabel voor virus- en bedreigingsbeveiliging in de app voor Windows-beveiliging](images/defender/wdav-protection-settings-wdsc.png)

3. Controleer of **Cloudbeveiliging** en **Automatisch sample indienen** beide zijn ingeschakeld.

> [!NOTE]
> - Als de vereiste instellingen zijn geconfigureerd en geïmplementeerd via groepsbeleid, worden de instellingen die in deze sectie worden beschreven, grijs gemaakt en zijn ze niet beschikbaar voor gebruik op afzonderlijke eindpunten. 
> - Wijzigingen die zijn aangebracht via een groepsbeleidsobject, moeten eerst worden geïmplementeerd op afzonderlijke eindpunten voordat de instelling wordt bijgewerkt in de Windows-instellingen.

## <a name="validate-block-at-first-sight-is-working"></a>Controleren of blokkeren bij eerste detectie werkt

Als u wilt controleren of de functie werkt, volgt u de richtlijnen in [Verbindingen tussen uw netwerk en de cloud valideren](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).

## <a name="turn-off-block-at-first-sight"></a>Blokkeren bij eerste detectie uitschakelen

> [!CAUTION]
> Als u blokkeren bij eerste detectie uitschakelt, wordt de beveiligingstoestand van uw apparaat(en) en uw netwerk verlaagd.

U kunt blokkering bij eerste detectie uitschakelen als u de vereiste instellingen wilt behouden zonder daadwerkelijk blokkering bij eerste detectie te gebruiken. U kunt blokkeren bij eerste detectie tijdelijk uitschakelen om te zien wat de invloed van deze functie is op uw netwerk. Het wordt echter afgeraden de blokkeren bij eerste detectiebeveiliging permanent uit te uitschakelen.

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a>Blokkeren bij eerste detectie uitschakelen met Microsoft Endpoint Manager

1. Ga naar het Beheercentrum van Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) en meld u aan.

2. Ga naar **Eindpuntbeveiliging** > **Antivirus** en selecteer vervolgens uw Microsoft Defender Antivirus-beleid.

3. Klik onder **Beheren** op **Eigenschappen**.

4. Kies na **Configuratie-instellingen** de optie **Bewerken**.

5. Wijzig een of meer van de volgende instellingen:

   - Zet **Cloudbeveiliging instellen** op **Nee** of **Niet geconfigureerd**.
   - Stel **Cloudbeveiligingsniveau** in op **Niet geconfigureerd**.
   - Schakel het selectievakje uit voor **Defender Cloud Extended Timeout in seconden**.

6. Controleer uw instellingen en sla deze op.

### <a name="turn-off-block-at-first-sight-with-group-policy"></a>Blokkeren bij eerste detectie uitschakelen met Groepsbeleid

1. Open op uw computer voor groepsbeleidsbeheer de [Groepsbeleidsbeheerconsole](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), klik met de rechtermuisknop op het groepsbeleidsobject dat u wilt configureren en selecteer vervolgens **Bewerken**.

2. Ga via **Groepsbeleidsbeheereditor** naar **Computerconfiguratie** en selecteer **Beheersjablonen**.

3. Vouw de boomstructuur uit via **Windows-onderdelen** > **Microsoft Defender Antivirus** > **MAPS**.

4. Dubbelklik op **De functie 'Blokkeren bij eerste detectie' configureren** en stel de optie in op **Uitgeschakeld**.

    > [!NOTE]
    > Als u blokkeren bij eerste detectie uitschakelt, wordt het vereiste groepsbeleid niet uitgeschakeld of gewijzigd.

## <a name="not-an-enterprise-admin-or-it-pro"></a>Bent u geen ondernemingsbeheerder of IT-professional?

Als u geen ondernemingsbeheerder of IT-professional bent, maar vragen hebt over blokkeren bij eerste detectie, is deze sectie iets voor u. Blokkeren bij eerste detectie is een bedreigingsbeveiligingsfunctie waarmee malware wordt gedetecteerd en geblokkeerd binnen enkele seconden. Hoewel er geen specifieke instelling met de naam 'Blokkeren bij eerste detectie' is, is de functie ingeschakeld wanneer bepaalde instellingen op uw apparaat zijn geconfigureerd.

### <a name="how-to-manage-block-at-first-sight-on-or-off-on-your-own-device"></a>Blokkeren bij eerste detectie met of zonder uw eigen apparaat beheren

Als u een persoonlijk apparaat hebt dat niet wordt beheerd door een organisatie, vraagt u zich misschien af hoe u blokkeren bij eerste detectie in- of uit moet schakelen. U kunt blokkeren bij eerste detectie beheren met de app voor Windows-beveiliging.

1. Open de app voor Windows-beveiliging op uw Windows 10-computer.

2. Selecteer **Virus- & bedreigingsbeveiliging**.

3. Selecteer onder **Virus- & bedreigingsbeveiliging**,**Instellingen beheren**.

4. Voer een van de volgende stappen uit:

   - Als u blokkeren bij eerste detectie wilt inschakelen, moet u er voor zorgen dat **Cloudbeveiliging** en **Automatisch sample indienen** beide zijn ingeschakeld.

   - Als u blokkeren bij eerste detectie wilt uitschakelen, schakelt u **Cloudbeveiliging** of **Automatisch sample indienen** uit. <br/>
    
     > [!CAUTION]
     > Door blokkeren bij eerste detectie uit te schakelen, verlaagt u het beveiligingsniveau voor uw apparaat. Het wordt echter afgeraden blokkeren bij eerste detectie permanent uit te uitschakelen. 


## <a name="see-also"></a>Zie ook

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Cloudbeveiliging inschakelen](enable-cloud-protection-microsoft-defender-antivirus.md)
- [Beveiligd blijven met Windows-beveiliging](https://support.microsoft.com/windows/stay-protected-with-windows-security-2ae0363d-0ada-c064-8b56-6a39afb6a963)