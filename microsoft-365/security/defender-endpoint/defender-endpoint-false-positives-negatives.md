---
title: Vals-positieven/-negatieven in Microsoft Defender voor Eindpunt aanpakken
description: Meer informatie over het verwerken van fout-positieven of onwaar negatieven in Microsoft Defender voor Eindpunt.
keywords: antivirus, uitzondering, uitsluiting, Microsoft Defender voor Eindpunt, false positive, false negative, geblokkeerd bestand, geblokkeerde url
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
- m365solution-scenario
- m365scenario-fpfn
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs, yonghree, jcedola
ms.custom: FPFN
ms.openlocfilehash: 368de770f772dc75a366b2120c8824fda6a7ba11
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933587"
---
# <a name="address-false-positivesnegatives-in-microsoft-defender-for-endpoint"></a>Vals-positieven/-negatieven in Microsoft Defender voor Eindpunt aanpakken

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op**

- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2146806)

In oplossingen voor eindpuntbeveiliging is een fout-positief een entiteit, zoals een bestand of een proces, die is gedetecteerd en geïdentificeerd als schadelijk, ook al is de entiteit geen bedreiging. Een onwaar negatief is een entiteit die niet is gedetecteerd als een bedreiging, ook al is deze in feite schadelijk. False positives/negatives can occur with any threat protection solution, including [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md).

![Definitie van onwaar-positieve en negatieven in Defender voor Eindpunt](images/false-positives-overview.png)

Gelukkig kunnen er stappen worden ondernomen om dit soort problemen op te lossen en te beperken. Als u onwaar positieve/negatieven ziet in uw [Microsoft Defender-beveiligingscentrum,](../defender/microsoft-365-security-center-mde.md)kunnen uw beveiligingsbewerkingen stappen ondernemen om deze aan te pakken met behulp van het volgende proces:

1.  [Waarschuwingen controleren en classificeren](#part-1-review-and-classify-alerts) 
2.  [Herstelacties bekijken die zijn ondernomen](#part-2-review-remediation-actions)
3.  [Uitsluitingen controleren en definiëren](#part-3-review-or-define-exclusions)
4.  [Een entiteit verzenden voor analyse](#part-4-submit-a-file-for-analysis)
5.  [Uw instellingen voor bedreigingsbeveiliging controleren en aanpassen](#part-5-review-and-adjust-your-threat-protection-settings)

U kunt hulp krijgen als u nog steeds problemen hebt met fout-positieve/negatieven na het uitvoeren van de taken die in dit artikel worden beschreven. Zie [Nog steeds hulp nodig?](#still-need-help)

![Stappen om onwaar positieven en negatieven aan te pakken](images/false-positives-step-diagram.png)

> [!NOTE]
> Dit artikel is bedoeld als richtlijnen voor beveiligingsoperatoren en beveiligingsbeheerders die [Microsoft Defender voor Eindpunt gebruiken.](microsoft-defender-endpoint.md)

## <a name="part-1-review-and-classify-alerts"></a>Deel 1: Waarschuwingen controleren en classificeren

Als u een [waarschuwing ziet](alerts.md) die is geactiveerd omdat er iets is gedetecteerd als schadelijk of verdacht dat niet had moeten zijn, kunt u de waarschuwing voor die entiteit onderdrukken. U kunt ook waarschuwingen onderdrukken die niet per se onwaar-positieven zijn, maar die niet belangrijk zijn. We raden u aan waarschuwingen ook te classificeren. 

Het beheren van uw waarschuwingen en het classificeren van waar-/onwaar-positieven helpt bij het trainen van uw oplossing voor bedreigingsbeveiliging en kan het aantal fout-positieven of onwaar negatieven in de tijd verminderen. Als u deze stappen ondernomen, kunt u ook de ruis in het dashboard voor beveiligingsbewerkingen verminderen, zodat uw beveiligingsteam zich kan richten op werkitems met een hogere prioriteit.

### <a name="determine-whether-an-alert-is-accurate"></a>Bepalen of een waarschuwing juist is

Voordat u een waarschuwing classificeert of onderdrukt, bepaalt u of de waarschuwing juist, onwaar positief of goedaardig is.

1. Ga naar het Microsoft Defender-beveiligingscentrum [https://securitycenter.windows.com](https://securitycenter.windows.com) () en meld u aan.

2. Kies in het navigatiedeelvenster **de optie Waarschuwingenwachtrij**.

3. Selecteer een waarschuwing voor meer informatie over de waarschuwing. (Zie [Waarschuwingen controleren in Microsoft Defender voor Eindpunt](review-alerts.md).)

4. Volg de stappen die in de volgende tabel worden beschreven, afhankelijk van de status van de waarschuwing: 

| Status van waarschuwing | Wat moet u doen? |
|:---|:---|
| De waarschuwing is nauwkeurig | Wijs de waarschuwing toe en [onderzoek deze](investigate-alerts.md) verder. |
| De waarschuwing is een onwaar positief | 1. [Classificeer de waarschuwing](#classify-an-alert) als een onwaar positief. <br/>2. [De waarschuwing onderdrukken](#suppress-an-alert). <br/> 3. [Maak een indicator voor](#indicators-for-microsoft-defender-for-endpoint) Microsoft Defender voor Eindpunt. <br/> 4. [Stuur een bestand naar Microsoft voor analyse](#part-4-submit-a-file-for-analysis). |
| De waarschuwing is nauwkeurig, maar goedaardig (onbelangrijk) | [Classificeer de waarschuwing](#classify-an-alert) als een echte positieve en onderdrukt [de waarschuwing.](#suppress-an-alert) |

### <a name="classify-an-alert"></a>Een waarschuwing classificeren

Waarschuwingen kunnen worden geclassificeerd als false positives of true positives in het Microsoft Defender Security Center. Als u waarschuwingen classificeert, kunt u Microsoft Defender voor Eindpunt trainen, zodat u na een tijd meer waargebeurde waarschuwingen en minder foutmeldingen ziet.

1. Ga naar het Microsoft Defender-beveiligingscentrum [https://securitycenter.windows.com](https://securitycenter.windows.com) () en meld u aan.

2. Selecteer **Waarschuwingenwachtrij** en selecteer vervolgens een waarschuwing.

3. Selecteer acties beheren voor de geselecteerde  >  **waarschuwing.** Er wordt een flyoutvenster geopend.

4. Selecteer in **de sectie Waarschuwing** beheren de optie **Waarmelding** **of Foutmelding.** (Gebruik **een onwaar waarschuwing om** een onwaar positief te classificeren.)

> [!TIP]
> Zie Microsoft Defender voor eindpuntwaarschuwingen beheren voor meer informatie over het onderdrukken van [waarschuwingen.](/microsoft-365/security/defender-endpoint/manage-alerts) En als uw organisatie een SIEM-server (Security Information and Event Management) gebruikt, moet u daar ook een onderdrukkingsregel definiëren. 

### <a name="suppress-an-alert"></a>Een waarschuwing onderdrukken

Als u waarschuwingen hebt die onwaar positieven zijn of die echte positieven zijn, maar voor onbelangrijke gebeurtenissen, kunt u deze waarschuwingen onderdrukken in het Microsoft Defender-beveiligingscentrum. Door waarschuwingen te onderdrukken, vermindert u ruis in het dashboard voor beveiligingsbewerkingen. 

1. Ga naar het Microsoft Defender-beveiligingscentrum [https://securitycenter.windows.com](https://securitycenter.windows.com) () en meld u aan.

2. Selecteer waarschuwingenwachtrij in **het navigatiedeelvenster.**

3. Selecteer een waarschuwing die u wilt onderdrukken om het deelvenster **Details te** openen.

4. Kies in **het** deelvenster Details het beletselteken (**...**) en vervolgens **Een onderdrukkingsregel maken.**

5. Geef alle instellingen op voor de onderdrukkingsregel en kies **opslaan.**

> [!TIP]
> Hulp nodig bij het onderdrukken van regels? Zie [Een waarschuwing onderdrukken en een nieuwe onderdrukkingsregel maken.](/microsoft-365/security/defender-endpoint/manage-alerts#suppress-an-alert-and-create-a-new-suppression-rule)

## <a name="part-2-review-remediation-actions"></a>Deel 2: Herstelacties controleren

[Herstelacties](manage-auto-investigation.md#remediation-actions), zoals het verzenden van een bestand naar quarantaine of het stoppen van een proces, worden ondernomen op entiteiten (zoals bestanden) die worden gedetecteerd als bedreigingen. Verschillende soorten herstelacties vinden automatisch plaats via geautomatiseerd onderzoek en Microsoft Defender Antivirus:   
- Een bestand in quarantaine plaatsen
- Een registersleutel verwijderen
- Een proces om te laten gaan
- Een service stoppen
- Een stuurprogramma uitschakelen
- Een geplande taak verwijderen

Andere acties, zoals het starten van een antivirusscan of het verzamelen van een onderzoekspakket, vinden handmatig of via [Live Response plaats.](live-response.md) Acties die zijn ondernomen via Live Response, kunnen niet ongedaan worden gemaakt.

Nadat u uw waarschuwingen hebt bekeken, is de volgende stap het controleren [van herstelacties.](manage-auto-investigation.md) Als er acties zijn ondernomen als gevolg van onwaar positieven, kunt u de meeste soorten herstelacties ongedaan maken. U kunt het volgende doen:

- [Een in quarantaine geplaatst bestand terugzetten vanuit het Actiecentrum](#restore-a-quarantined-file-from-the-action-center)
- [Meerdere acties tegelijk ongedaan maken](#undo-multiple-actions-at-one-time)
- [Verwijder een bestand uit quarantaine op meerdere apparaten.](#remove-a-file-from-quarantine-across-multiple-devices)  en 
- [Bestand in quarantaine herstellen](#restore-file-from-quarantine)

Wanneer u klaar bent met het controleren en ongedaan maken van acties die zijn uitgevoerd als gevolg van onwaar positieven, gaat u verder met het controleren of [definiëren van uitsluitingen.](#part-3-review-or-define-exclusions)

### <a name="review-completed-actions"></a>Voltooide acties controleren

1. Ga naar het Actiecentrum [https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center) () en meld u aan. 

2. Selecteer het **tabblad Geschiedenis** om een lijst met acties te bekijken die zijn ondernomen.  

3. Selecteer een item om meer details weer te geven over de herstelactie die is ondernomen.

### <a name="restore-a-quarantined-file-from-the-action-center"></a>Een in quarantaine geplaatst bestand terugzetten vanuit het Actiecentrum

1. Ga naar het Actiecentrum [https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center) () en meld u aan.

2. Selecteer op **het** tabblad Geschiedenis een actie die u ongedaan wilt maken.

3. Selecteer ongedaan maken in het deelvenster Flyout. Als de actie niet ongedaan kan worden gemaakt met deze methode, ziet u geen knop **Ongedaan** maken. (Zie Voltooide acties ongedaan maken voor [meer informatie](manage-auto-investigation.md#undo-completed-actions).)

### <a name="undo-multiple-actions-at-one-time"></a>Meerdere acties tegelijk ongedaan maken

1. Ga naar het Actiecentrum [https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center) () en meld u aan.

2. Selecteer op **het** tabblad Geschiedenis de acties die u ongedaan wilt maken.

3. Selecteer Ongedaan maken in het deelvenster aan de rechterkant van **het scherm.**

### <a name="remove-a-file-from-quarantine-across-multiple-devices"></a>Een bestand uit quarantaine verwijderen op meerdere apparaten 

> [!div class="mx-imgBorder"]
> ![Quarantainebestand](images/autoir-quarantine-file-1.png)

1. Ga naar het Actiecentrum [https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center) () en meld u aan.

2. Selecteer op **het** tabblad Geschiedenis een bestand met het bestand Actietype **Quarantaine**.

3. Selecteer in het deelvenster aan de rechterkant van het scherm meer exemplaren van dit bestand toepassen op **X** en selecteer **vervolgens Ongedaan maken.**

### <a name="restore-file-from-quarantine"></a>Bestand in quarantaine herstellen

U kunt een bestand terugdraaien en verwijderen uit quarantaine als u na een onderzoek hebt vastgesteld dat het bestand schoon is. Voer de volgende opdracht uit op elk apparaat waarop het bestand in quarantaine is geplaatst.

1. Open een opdrachtregelprompt met verhoogde opdracht op het apparaat:

   1. Ga naar **Start** en typ _cmd._

   1. Klik met de rechtermuisknop **op Opdrachtprompt** en selecteer **Uitvoeren als beheerder.**

2. Voer de volgende opdracht in en druk op **Enter:**

    ```console
    "ProgramFiles%\Windows Defender\MpCmdRun.exe" –Restore –Name EUS:Win32/CustomEnterpriseBlock –All
    ```

    > [!NOTE]
    > In sommige scenario's kan **threatname** worden weergegeven als: `EUS:Win32/
CustomEnterpriseBlock!cl` . Defender voor Eindpunt herstelt alle aangepaste geblokkeerde bestanden die in quarantaine zijn geplaatst op dit apparaat in de afgelopen 30 dagen.

    > [!IMPORTANT]
    > Een bestand dat in quarantaine is geplaatst als een potentiële netwerkdreiging, kan mogelijk niet worden hersteld. Als een gebruiker het bestand na quarantaine probeert te herstellen, is dat bestand mogelijk niet toegankelijk. Dit kan worden veroorzaakt doordat het systeem geen netwerkreferenties meer heeft om toegang te krijgen tot het bestand. Dit is meestal het gevolg van een tijdelijk aanmelden bij een systeem of gedeelde map en de toegangstokens zijn verlopen.

3. Selecteer in het deelvenster aan de rechterkant van het scherm meer exemplaren van dit bestand toepassen op **X** en selecteer **vervolgens Ongedaan maken.** 


## <a name="part-3-review-or-define-exclusions"></a>Deel 3: Uitsluitingen controleren of definiëren

Een uitsluiting is een entiteit, zoals een bestand of URL, die u opgeeft als uitzondering op herstelacties. De uitgesloten entiteit kan nog steeds worden gedetecteerd, maar er worden geen herstelacties voor die entiteit ondernomen. Dat wil zeggen dat het gedetecteerde bestand of proces niet wordt gestopt, naar quarantaine wordt verzonden, wordt verwijderd of anderszins wordt gewijzigd door Microsoft Defender voor Eindpunt. 

Als u uitsluitingen in Microsoft Defender voor Eindpunt wilt definiëren, voert u de volgende taken uit:
- [Uitsluitingen definiëren voor Microsoft Defender Antivirus](#exclusions-for-microsoft-defender-antivirus)
- [Indicatoren voor toestaan maken voor Microsoft Defender voor eindpunt](#indicators-for-microsoft-defender-for-endpoint)

> [!NOTE]
> Microsoft Defender Antivirus-uitsluitingen zijn alleen van toepassing op antivirusbeveiliging, niet in andere mogelijkheden van Microsoft Defender voor eindpunten. Als u bestanden breed wilt uitsluiten, gebruikt u uitsluitingen voor Microsoft Defender Antivirus en [aangepaste indicatoren](/microsoft-365/security/defender-endpoint/manage-indicators) voor Microsoft Defender voor Eindpunt.

In de procedures in deze sectie wordt beschreven hoe u uitsluitingen en indicatoren kunt definiëren.

### <a name="exclusions-for-microsoft-defender-antivirus"></a>Uitsluitingen voor Microsoft Defender Antivirus

Over het algemeen hoeft u geen uitsluitingen voor Microsoft Defender Antivirus te definiëren. Zorg ervoor dat u uitsluitingen spaarzaam definieert en dat u alleen de bestanden, mappen, processen en proces geopende bestanden optelt die resulteren in fout-positieven. Controleer bovendien regelmatig uw gedefinieerde uitsluitingen. We raden u [aan Microsoft Endpoint Manager te gebruiken om](/mem/endpoint-manager-overview) uw antivirusuitsluitingen te definiëren of te bewerken. U kunt echter andere methoden gebruiken, zoals [Groepsbeleid](/azure/active-directory-domain-services/manage-group-policy) (zie [Microsoft Defender voor eindpunt beheren).](manage-atp-post-migration.md)

> [!TIP]
> Hulp nodig bij antivirusuitsluitingen? Zie [Uitsluitingen configureren en valideren voor Microsoft Defender Antivirus scans.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)

#### <a name="use-microsoft-endpoint-manager-to-manage-antivirus-exclusions-for-existing-policies"></a>Microsoft Endpoint Manager gebruiken om antivirusuitsluitingen te beheren (voor bestaand beleid)

1. Ga naar het Microsoft Endpoint Manager-beheercentrum [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () en meld u aan.

2. Kies **Endpoint Security**  >  **Antivirus** en selecteer vervolgens een bestaand beleid. (Als u geen bestaand beleid hebt of als u een nieuw beleid wilt maken, gaat u verder [met de volgende procedure).](#use-microsoft-endpoint-manager-to-create-a-new-antivirus-policy-with-exclusions)

3. Kies **Eigenschappen** en kies naast **Configuratie-instellingen** de optie **Bewerken.**

4. Vouw **Microsoft Defender Antivirus Exclusions uit** en geef vervolgens uw uitsluitingen op.

5. Kies **Controleren+ opslaan** en kies vervolgens **Opslaan.**

#### <a name="use-microsoft-endpoint-manager-to-create-a-new-antivirus-policy-with-exclusions"></a>Microsoft Endpoint Manager gebruiken om een nieuw antivirusbeleid te maken met uitsluitingen

1. Ga naar het Microsoft Endpoint Manager-beheercentrum [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () en meld u aan.

2. Kies **Endpoint security**  >  **Antivirus**  >  **+ Create Policy**. 

3. Selecteer een platform (zoals **Windows 10 en hoger**, **macOS** of **Windows 10 en Windows Server).**

4. Selecteer **voor** Profiel **Microsoft Defender Antivirus-uitsluitingen** en kies vervolgens **Maken.**

5. Geef een naam en beschrijving op voor het profiel en kies **volgende**.

6. Geef op **het tabblad Configuratie-instellingen** uw antivirusuitsluitingen op en kies **volgende**.

7. Geef op **het tabblad Bereiklabels,** als u bereiklabels in uw organisatie gebruikt, bereiklabels op voor het beleid dat u maakt. (Zie [Bereiklabels](/mem/intune/fundamentals/scope-tags).)

8. Geef op **het tabblad** Opdrachten de gebruikers en groepen op waarop uw beleid moet worden toegepast en kies **volgende**. (Zie Gebruikers- en apparaatprofielen toewijzen [in Microsoft Intune](/mem/intune/configuration/device-profile-assign)als u hulp nodig hebt bij opdrachten .)

9. Controleer op **het tabblad Controleren +** maken de instellingen en kies vervolgens **Maken.**

### <a name="indicators-for-microsoft-defender-for-endpoint"></a>Indicatoren voor Microsoft Defender voor eindpunt

[Met](/microsoft-365/security/defender-endpoint/manage-indicators) indicatoren (met name indicatoren voor compromissen of IOC's) kan uw beveiligingsteam de detectie, preventie en uitsluiting van entiteiten definiëren. U kunt bijvoorbeeld bepaalde bestanden opgeven die moeten worden weggelaten bij scans en herstelacties in Microsoft Defender voor Eindpunt. U kunt ook indicatoren gebruiken om waarschuwingen te genereren voor bepaalde bestanden, IP-adressen of URL's.

Als u entiteiten wilt opgeven als uitsluitingen voor Microsoft Defender voor Eindpunt, maakt u indicatoren voor toestaan voor deze entiteiten. Dergelijke 'toestaan'-indicatoren in Microsoft Defender voor Eindpunt zijn van toepassing op de volgende generatie [beveiliging,](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)eindpuntdetectie en -reactie [en](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)geautomatiseerde & [herstel.](/microsoft-365/security/defender-endpoint/automated-investigations)

'Toestaan'-indicatoren kunnen worden gemaakt voor:

- [Bestanden](#indicators-for-files)
- [IP-adressen, URL's en domeinen](#indicators-for-ip-addresses-urls-or-domains)
- [Toepassingscertificaten](#indicators-for-application-certificates)

![Diagram indicatortypen](images/false-positives-indicators.png)

#### <a name="indicators-for-files"></a>Indicatoren voor bestanden

Wanneer u [een indicator 'toestaan'](/microsoft-365/security/defender-endpoint/indicator-file)maakt voor een bestand, zoals een uitvoerbaar bestand, voorkomt u dat bestanden die uw organisatie gebruikt, worden geblokkeerd. Bestanden kunnen draagbare uitvoerbare (PE-) bestanden bevatten, zoals `.exe` en `.dll` bestanden. 

Voordat u indicatoren voor bestanden maakt, moet u ervoor zorgen dat aan de volgende vereisten wordt voldaan:
- Microsoft Defender Antivirus is geconfigureerd met cloudbeveiliging ingeschakeld (zie [Beveiliging in de cloud beheren)](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)
- Antimalware-clientversie is 4.18.1901.x of hoger 
- Op apparaten wordt Windows 10, versie 1703 of hoger uitgevoerd. Windows Server 2016; of Windows Server 2019 
- De [functie Blokkeren of toestaan is ingeschakeld](/microsoft-365/security/defender-endpoint/advanced-features) 

#### <a name="indicators-for-ip-addresses-urls-or-domains"></a>Indicatoren voor IP-adressen, URL's of domeinen

Wanneer u een indicator 'toestaan' maakt voor een [IP-adres, URL](/microsoft-365/security/defender-endpoint/indicator-ip-domain)of domein, voorkomt u dat de sites of IP-adressen die uw organisatie gebruikt, worden geblokkeerd.

Voordat u indicatoren maakt voor IP-adressen, URL's of domeinen, moet u ervoor zorgen dat aan de volgende vereisten wordt voldaan:
- Netwerkbeveiliging in Defender voor Eindpunt is ingeschakeld in de blokmodus (zie [Netwerkbeveiliging inschakelen)](/microsoft-365/security/defender-endpoint/enable-network-protection)
- Antimalware-clientversie is 4.18.1906.x of hoger 
- Apparaten hebben Windows 10, versie 1709 of hoger 

Aangepaste netwerkindicatoren zijn ingeschakeld in het Microsoft Defender-beveiligingscentrum (zie [Geavanceerde functies](/microsoft-365/security/defender-endpoint/advanced-features))   

#### <a name="indicators-for-application-certificates"></a>Indicatoren voor toepassingscertificaten 

Wanneer u [een indicator 'toestaan'](/microsoft-365/security/defender-endpoint/indicator-certificates)maakt voor een toepassingscertificaat, voorkomt u dat toepassingen, zoals intern ontwikkelde toepassingen, die door uw organisatie worden gebruikt, worden geblokkeerd. `.CER` of `.PEM` bestandsextensies worden ondersteund.   

Voordat u indicatoren voor toepassingscertificaten maakt, moet u ervoor zorgen dat aan de volgende vereisten wordt voldaan:
- Microsoft Defender Antivirus is geconfigureerd met cloudbeveiliging ingeschakeld (zie [Beveiliging in de cloud beheren)](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)
- Antimalware-clientversie is 4.18.1901.x of hoger 
- Op apparaten wordt Windows 10, versie 1703 of hoger uitgevoerd. Windows Server 2016; of Windows Server 2019 
- Definities van virus- en bedreigingsbeveiliging zijn up-to-date  

> [!TIP]
> Wanneer u indicatoren maakt, kunt u deze een voor een definiëren of meerdere items tegelijk importeren. Houd er rekening mee dat er een limiet is van 15.000 indicatoren voor één tenant. En mogelijk moet u eerst bepaalde details verzamelen, zoals informatie over bestandshash. Controleer de vereisten voordat u [indicatoren maakt.](manage-indicators.md) 

## <a name="part-4-submit-a-file-for-analysis"></a>Deel 4: Een bestand verzenden voor analyse

U kunt entiteiten, zoals bestanden en bestandsloze detecties, voor analyse naar Microsoft verzenden. Beveiligingsonderzoekers van Microsoft analyseren alle inzendingen en de resultaten helpen Microsoft Defender te informeren over de mogelijkheden voor bescherming tegen endpoint-bedreigingen. Wanneer u zich aan meld bij de inzendingssite, kunt u uw inzendingen bijhouden.

### <a name="submit-a-file-for-analysis"></a>Een bestand verzenden voor analyse

Als u een bestand hebt dat ten onrechte is gedetecteerd als schadelijk of is gemist, volgt u deze stappen om het bestand voor analyse in te dienen.

1. Bekijk hier de richtlijnen: [Bestanden indienen voor analyse.](/windows/security/threat-protection/intelligence/submission-guide)

2. Ga naar de Microsoft Security Intelligence-inzendingssite [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission) () en verzend uw bestand(en).

### <a name="submit-a-fileless-detection-for-analysis"></a>Een bestandsloze detectie indienen voor analyse

Als er iets is gedetecteerd als malware op basis van gedrag en u geen bestand hebt, kunt u uw bestand indienen `Mpsupport.cab` voor analyse. U kunt het *.cab-bestand* downloaden met behulp van het hulpprogramma Command-Line Hulpprogramma (MPCmdRun.exe) van Microsoft Malware Protection in Windows 10.

1.  Ga naar ` C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` en voer vervolgens als beheerder `MpCmdRun.exe` uit.

2.  Typ `mpcmdrun.exe -GetFiles` en druk vervolgens op **Enter.**
   Er wordt een CAB-bestand gegenereerd dat verschillende diagnostische logboeken bevat. De locatie van het bestand wordt opgegeven in de uitvoer van de opdrachtprompt. Standaard is de locatie `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab` .

3.  Bekijk hier de richtlijnen: [Bestanden indienen voor analyse.](/windows/security/threat-protection/intelligence/submission-guide)

4.  Ga naar de Microsoft Security Intelligence-inzendingssite [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission) () en verzend uw .cab-bestanden.

### <a name="what-happens-after-a-file-is-submitted"></a>Wat gebeurt er nadat een bestand is ingediend?

Uw inzending wordt onmiddellijk gescand door onze systemen om u de meest recente bepaling te geven, zelfs voordat een analist uw zaak gaat behandelen. Het is mogelijk dat een bestand al is ingediend en verwerkt door een analist. In die gevallen wordt snel een bepaling gemaakt.

Voor inzendingen die nog niet zijn verwerkt, worden ze als volgt geprioriteerd voor analyse:

- Veel voorkomende bestanden die van invloed kunnen zijn op grote aantallen computers, krijgen een hogere prioriteit.
- Geverifieerde klanten, met name zakelijke klanten met geldige [Software Assurance-ID's (SAID's),](https://www.microsoft.com/licensing/licensing-programs/software-assurance-default.aspx)krijgen een hogere prioriteit.
- Inzendingen die door SAID-houders als hoge prioriteit worden gemarkeerd, krijgen onmiddellijk de aandacht.

Als u wilt controleren op updates met betrekking tot uw inzending, meld u zich aan bij de [Microsoft Security Intelligence-inzendingssite.](https://www.microsoft.com/wdsi/filesubmission) 

> [!TIP]
> Zie Bestanden verzenden [voor analyse voor meer informatie.](/windows/security/threat-protection/intelligence/submission-guide#how-does-microsoft-prioritize-submissions)

## <a name="part-5-review-and-adjust-your-threat-protection-settings"></a>Deel 5: Uw instellingen voor bedreigingsbeveiliging controleren en aanpassen

Microsoft Defender voor Eindpunt biedt een groot aantal opties, waaronder de mogelijkheid om instellingen voor verschillende functies en mogelijkheden aan te passen. Als u meerdere fout-positieven krijgt, controleert u de instellingen voor bedreigingsbeveiliging van uw organisatie. Mogelijk moet u het volgende aanpassen:

- [Cloudbeveiliging](#cloud-delivered-protection)
- [Herstel van potentieel ongewenste toepassingen](#remediation-for-potentially-unwanted-applications)
- [Geautomatiseerd onderzoek en herstel](#automated-investigation-and-remediation)

### <a name="cloud-delivered-protection"></a>Cloudbeveiliging

Controleer uw beveiligingsniveau in de cloud voor Microsoft Defender Antivirus. Standaard is beveiliging in de cloud ingesteld op Niet **geconfigureerd,** wat overeenkomt met een normaal beveiligingsniveau voor de meeste organisaties. Als de beveiliging in de cloud is ingesteld op **Hoog,** **Hoog +** of Nul **tolerantie,** kan het aantal fout-positieven hoger zijn.

> [!TIP]
> Zie Het door de cloud geleverde beveiligingsniveau opgeven voor meer informatie over het configureren van uw door de [cloud geleverde beveiliging.](/windows/security/threat-protection/microsoft-defender-antivirus/specify-cloud-protection-level-microsoft-defender-antivirus)

We raden u [aan Microsoft Endpoint Manager te gebruiken om](/mem/endpoint-manager-overview) uw beveiligingsinstellingen in de cloud te bewerken of in te stellen. U kunt echter andere methoden gebruiken, zoals [Groepsbeleid](/azure/active-directory-domain-services/manage-group-policy) (zie [Microsoft Defender voor eindpunt beheren).](manage-atp-post-migration.md)

#### <a name="use-microsoft-endpoint-manager-to-review-and-edit-cloud-delivered-protection-settings-for-existing-policies"></a>Microsoft Endpoint Manager gebruiken om beveiligingsinstellingen in de cloud te bekijken en te bewerken (voor bestaand beleid)

1. Ga naar het Microsoft Endpoint Manager-beheercentrum [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () en meld u aan.

2. Kies **Endpoint Security**  >  **Antivirus** en selecteer vervolgens een bestaand beleid. (Als u geen bestaand beleid hebt of als u een nieuw beleid wilt maken, gaat u verder [met de volgende procedure).](#use-microsoft-endpoint-manager-to-set-cloud-delivered-protection-settings-for-a-new-policy)

3. Selecteer **onder** Beheren de optie **Eigenschappen.** Kies vervolgens naast **Configuratie-instellingen** de optie **Bewerken.**

4. Vouw **Cloudbeveiliging uit** en bekijk uw huidige instelling in de rij **Beveiligingsniveau** van de cloud. We raden u aan de beveiliging die door de cloud wordt geleverd in te stellen op Niet **geconfigureerd,** wat een sterke beveiliging biedt en tegelijkertijd de kans op fout-positieven verkleint.

5. Kies **Controleren+ opslaan** en vervolgens **Opslaan.**

#### <a name="use-microsoft-endpoint-manager-to-set-cloud-delivered-protection-settings-for-a-new-policy"></a>Microsoft Endpoint Manager gebruiken om beveiligingsinstellingen voor de cloud in te stellen (voor een nieuw beleid)

1. Ga naar het Microsoft Endpoint Manager-beheercentrum [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () en meld u aan.

2. Kies **Endpoint security**  >  **Antivirus**  >  **+ Create policy**.

3. Selecteer **voor Platform** een optie en selecteer vervolgens voor Profiel **Antivirus** of Microsoft **Defender Antivirus** (de specifieke optie is afhankelijk van wat u hebt geselecteerd voor **Platform**.) Kies vervolgens **Maken.**

4. Geef op **het** tabblad Basisbeginselen een naam en beschrijving op voor het beleid. Kies vervolgens **Volgende**.

5. Vouw op **het tabblad Configuratie-instellingen** **cloudbeveiliging uit** en geef de volgende instellingen op:
   - Stel **Beveiliging in de cloud in op** **Ja.**
   - Stel **beveiligingsniveau in de cloud in** op Niet **geconfigureerd.** (Dit niveau biedt standaard een sterk beschermingsniveau, terwijl de kans op fout-positieven wordt verkleind.)

6. Geef op **het tabblad Bereiklabels,** als u bereiklabels in uw organisatie gebruikt, bereiklabels op voor het beleid. (Zie [Bereiklabels](/mem/intune/fundamentals/scope-tags).)

7. Geef op **het tabblad** Opdrachten de gebruikers en groepen op waarop uw beleid moet worden toegepast en kies **volgende**. (Zie Gebruikers- en apparaatprofielen toewijzen [in Microsoft Intune](/mem/intune/configuration/device-profile-assign)als u hulp nodig hebt bij opdrachten .)

8. Controleer op **het tabblad Controleren +** maken de instellingen en kies vervolgens **Maken.**  

### <a name="remediation-for-potentially-unwanted-applications"></a>Herstel van potentieel ongewenste toepassingen

Potentieel ongewenste toepassingen (PUA) zijn een categorie software die ervoor kan zorgen dat apparaten langzaam worden uitgevoerd, onverwachte advertenties kunnen weergeven of andere software kunnen installeren die onverwacht of ongewenst kan zijn. Voorbeelden van PUA zijn reclamesoftware, bundelingssoftware en ontwijkingssoftware die zich anders gedraagt met beveiligingsproducten. Hoewel PUA niet wordt beschouwd als malware, zijn sommige soorten software PUA op basis van hun gedrag en reputatie.

> [!TIP]
> Zie Potentieel ongewenste toepassingen detecteren en [blokkeren](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)voor meer informatie over PUA.
 
Afhankelijk van de apps die uw organisatie gebruikt, krijgt u mogelijk onwaar positieven als gevolg van uw PUA-beveiligingsinstellingen. Als dat nodig is, kunt u overwegen om PUA-beveiliging een tijdje in de auditmodus uit te voeren of PUA-beveiliging toe te passen op een subset apparaten in uw organisatie. PUA-beveiliging kan worden geconfigureerd voor de Microsoft Edge-browser en voor Microsoft Defender Antivirus.

We raden u [aan Microsoft Endpoint Manager te gebruiken om](/mem/endpoint-manager-overview) PUA-beveiligingsinstellingen te bewerken of in te stellen. U kunt echter andere methoden gebruiken, zoals [Groepsbeleid](/azure/active-directory-domain-services/manage-group-policy) (zie [Microsoft Defender voor eindpunt beheren).](manage-atp-post-migration.md)

#### <a name="use-microsoft-endpoint-manager-to-edit-pua-protection-for-existing-configuration-profiles"></a>Microsoft Endpoint Manager gebruiken om PUA-beveiliging te bewerken (voor bestaande configuratieprofielen)

1. Ga naar het Microsoft Endpoint Manager-beheercentrum [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () en meld u aan.

2. Kies   >  **Apparatenconfiguratieprofielen** en selecteer vervolgens een bestaand beleid. (Als u geen bestaand beleid hebt of als u een nieuw beleid wilt maken, gaat u verder [met de volgende procedure](#use-microsoft-endpoint-manager-to-set-pua-protection-for-a-new-configuration-profile).)

3. Kies **onder** Beheren de optie **Eigenschappen** en kies vervolgens naast **Configuratie-instellingen** de optie **Bewerken.**

4. Schuif op **het tabblad Configuratie-instellingen** omlaag en vouw **Microsoft Defender Antivirus uit.**

5. Stel **Mogelijk ongewenste toepassingen detecteren in** op **Audit.** (U kunt het uitschakelen, maar met behulp van de auditmodus kunt u detecties zien.)

6. Kies **Controleren+ opslaan** en kies vervolgens **Opslaan.**

#### <a name="use-microsoft-endpoint-manager-to-set-pua-protection-for-a-new-configuration-profile"></a>Microsoft Endpoint Manager gebruiken om PUA-beveiliging in te stellen (voor een nieuw configuratieprofiel)

1. Ga naar het Microsoft Endpoint Manager-beheercentrum [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () en meld u aan.

2. Kies   >  **Apparatenconfiguratieprofielen**  >  **+ Profiel maken.**

3. Kies voor **het platform** **Windows 10 en hoger** en selecteer voor **Profiel** **apparaatbeperkingen.**

4. Geef op **het** tabblad Basisbeginselen een naam en beschrijving op voor uw beleid. Kies vervolgens **Volgende**.

5. Schuif op **het tabblad Configuratie-instellingen** omlaag en vouw **Microsoft Defender Antivirus uit.**

6. Stel **Mogelijk ongewenste toepassingen detecteren in** op **Audit** en kies vervolgens **Volgende.** (U kunt PUA-beveiliging uitschakelen, maar met de auditmodus kunt u detecties zien.)

7. Geef op **het tabblad** Opdrachten de gebruikers en groepen op waarop uw beleid moet worden toegepast en kies **volgende**. (Zie Gebruikers- en apparaatprofielen toewijzen [in Microsoft Intune](/mem/intune/configuration/device-profile-assign)als u hulp nodig hebt bij opdrachten .)

8. Geef op **het tabblad Toepassingsregels** de besturingssysteemeditie of -versies op die u wilt opnemen of uitsluiten van het beleid. U kunt bijvoorbeeld instellen dat het beleid wordt toegepast op alle apparaten die bepaalde versies van Windows 10 hebben. Kies vervolgens **Volgende**.

9. Controleer op **het tabblad Controleren +** maken uw instellingen en kies vervolgens **Maken.**

### <a name="automated-investigation-and-remediation"></a>Geautomatiseerd onderzoek en herstel

[Geautomatiseerde mogelijkheden voor onderzoek en](automated-investigations.md) herstel (AIR) zijn ontworpen om waarschuwingen te onderzoeken en onmiddellijk actie te ondernemen om inbreuken op te lossen. Wanneer waarschuwingen worden geactiveerd en een geautomatiseerd onderzoek wordt uitgevoerd, wordt een vonnis gegenereerd voor elk bewijs dat wordt onderzocht. Vonnissen kunnen *Schadelijk,* *Verdacht* of *Geen bedreigingen zijn gevonden.* 

Afhankelijk van het [automatiseringsniveau](/microsoft-365/security/defender-endpoint/automation-levels) dat is ingesteld voor uw organisatie en andere beveiligingsinstellingen, worden  herstelacties ondernomen op artefacten die als schadelijk of verdacht *worden beschouwd.* In sommige gevallen worden herstelacties automatisch uitgevoerd. in andere gevallen worden herstelacties handmatig of alleen uitgevoerd na goedkeuring door uw beveiligingsteam. 

- [Meer informatie over automatiseringsniveaus;](/microsoft-365/security/defender-endpoint/automation-levels) en vervolgens 
- [Air-mogelijkheden configureren in Defender voor Eindpunt.](/microsoft-365/security/defender-endpoint/configure-automated-investigations-remediation)

> [!IMPORTANT]
> We raden u aan *volledige automatisering te gebruiken* voor geautomatiseerd onderzoek en herstel. Schakel deze mogelijkheden niet uit vanwege een onwaar positief. Gebruik in plaats daarvan ['toestaan'-indicatoren](#indicators-for-microsoft-defender-for-endpoint)om uitzonderingen te definiëren en laat automatisch onderzoek en herstel instellen om automatisch de juiste acties uit te voeren. Als [u deze richtlijnen](automation-levels.md#levels-of-automation) volgt, vermindert u het aantal waarschuwingen dat uw beveiligingsbewerkingsteam moet verwerken. 

## <a name="still-need-help"></a>Meer hulp nodig?

Als u alle stappen in dit artikel hebt doorlopen en nog steeds hulp nodig hebt, neemt u contact op met de technische ondersteuning.

1. Ga naar het Microsoft Defender-beveiligingscentrum [https://securitycenter.windows.com](https://securitycenter.windows.com) () en meld u aan.

2. Selecteer in de rechterbovenhoek het vraagteken (**?**) en selecteer **vervolgens Microsoft-ondersteuning.**

3. Beschrijf het **probleem** in het venster Ondersteuningsassistent en verzend uw bericht. Hier kunt u een serviceaanvraag openen.  

## <a name="see-also"></a>Zie ook

[Microsoft Defender voor eindpunt beheren](manage-atp-post-migration.md)

[Overzicht van Microsoft Defender-beveiligingscentrum](/microsoft-365/security/defender-endpoint/use) 
