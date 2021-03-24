---
title: Gebeurtenissen en fouten controleren met Behulp van Gebeurtenisviewer
description: Hier worden beschrijvingen en verdere stappen voor probleemoplossing (indien vereist) weergegeven voor alle gebeurtenissen die zijn gerapporteerd door de Microsoft Defender voor Eindpunt-service.
keywords: probleemoplosser, gebeurtenisviewer, logboekoverzicht, foutcode, mislukt, Microsoft Defender voor Endpoint-service, kan niet starten, niet starten, niet starten
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
ms.topic: article
ms.date: 05/21/2018
ms.technology: mde
ms.openlocfilehash: 98c0f790c228989b261b95f3b87cdc9d18e4fa76
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060553"
---
# <a name="review-events-and-errors-using-event-viewer"></a>Gebeurtenissen en fouten controleren met Behulp van Gebeurtenisviewer

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- Gebeurtenisviewer
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

U kunt gebeurtenis-ID's in de [Gebeurtenisviewer op](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) afzonderlijke apparaten bekijken.

Als apparaten bijvoorbeeld niet worden weergegeven in de lijst **Apparaten,** moet u mogelijk zoeken naar gebeurtenis-ID's op de apparaten. Vervolgens kunt u deze tabel gebruiken om verdere stappen voor het oplossen van problemen te bepalen.

**Open Gebeurtenisviewer en zoek het gebeurtenislogboek van de Microsoft Defender for Endpoint-service:**

1. Klik **op Start** in het Windows-menu, typ **Gebeurtenisviewer** en druk op **Enter.**

2. Schuif in de logboeklijst onder **Logboekoverzicht** door totdat u **Microsoft-Windows-SENSE/Operationeel ziet.** Dubbelklik op het item om het logboek te openen.

   a.  U kunt het logboek ook openen door toepassingen en **serviceslogboeken** van Microsoft Windows SENSE uit te breiden  >    >    >   en op Operationeel **te klikken.**

   > [!NOTE]
   > SENSE is de interne naam die wordt gebruikt om te verwijzen naar de gedrags sensor die Microsoft Defender voor Eindpunt aandreed.

3. Gebeurtenissen die door de service zijn geregistreerd, worden weergegeven in het logboek. Zie de volgende tabel voor een lijst met gebeurtenissen die zijn vastgelegd door de service.

<table>
<tbody style="vertical-align:top;">
<tr>
<th>Gebeurtenis-id</th>
<th>Bericht</th>
<th>Beschrijving</th>
<th>Actie</th>
</tr>
<tr>
<td>1</td>
<td>Microsoft Defender for Endpoint-service gestart <code>variable</code> (versie).</td>
<td>Dit gebeurt tijdens het starten van het systeem, tijdens het afsluiten en tijdens het onbboarden.</td>
<td>Normale bedrijfsmelding; geen actie vereist.</td>
</tr>
<tr>
<td>2</td>
<td>Microsoft Defender for Endpoint service shutdown.</td>
<td>Dit gebeurt wanneer het apparaat is uitgeschakeld of buiten gebruik wordt gezet.</td>
<td>Normale bedrijfsmelding; geen actie vereist.</td>
</tr>
<tr>
<td>3</td>
<td>Microsoft Defender voor Endpoint-service kan niet worden begonnen. Foutcode: <code>variable</code> .</td>
<td>Service is niet begonnen.</td>
<td>Controleer andere berichten om mogelijke oorzaak- en probleemoplossingsstappen te bepalen.</td>
</tr>
<tr>
<td>4</td>
<td>Microsoft Defender for Endpoint-service heeft contact opgenomen met de server op <code>variable</code> .</td>
<td>Variabele = URL van de defender voor eindpuntverwerkingsservers.<br>
Deze URL komt overeen met die in de firewall- of netwerkactiviteit.</td>
<td>Normale bedrijfsmelding; geen actie vereist.</td>
</tr>
<tr>
<td>5</td>
<td>Microsoft Defender for Endpoint-service kan geen verbinding maken met de server op <code>variable</code> .</td>
<td>Variabele = URL van de defender voor eindpuntverwerkingsservers.<br>
De service kan geen contact opnemen met de externe verwerkingsservers op die URL.</td>
<td>Controleer de verbinding met de URL. Zie <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Proxy en internetverbinding configureren.</a></td>
</tr>
<tr>
<td>6</td>
<td>Microsoft Defender voor Endpoint-service is niet onboarded en er zijn geen onboarding-parameters gevonden.</td>
<td>Het apparaat is niet correct aan boord en rapporteert niet aan de portal.</td>
<td>Onboarding moet worden uitgevoerd voordat u de service start.<br>
Controleer of de onboarding-instellingen en scripts correct zijn geïmplementeerd. Probeer de configuratiepakketten opnieuw te configureren.<br>
Zie <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10-apparaten</a>.</td>
</tr>
<tr>
<td>7</td>
<td>Microsoft Defender voor Endpoint-service kan de onboarding-parameters niet lezen. Fout: <code>variable</code> .</td>
<td>Variabele = gedetailleerde foutbeschrijving. Het apparaat is niet correct aan boord en rapporteert niet aan de portal.</td>
<td>Controleer of de onboarding-instellingen en scripts correct zijn geïmplementeerd. Probeer de configuratiepakketten opnieuw te configureren.<br>
Zie <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10-apparaten</a>.</td>
</tr>
<tr>
<td>8</td>
<td>De configuratie van de Microsoft Defender for Endpoint-service is niet op te schonen. Foutcode: <code>variable</code> .</td>
<td><b>Tijdens onboarding:</b> De service heeft de configuratie tijdens de onboarding niet schoon kunnen maken. Het onboardingproces wordt voortgezet. <br><br> <b>Tijdens offboarding:</b> De service heeft de configuratie tijdens het offboarden niet schoon kunnen maken. Het offboarding-proces is voltooid, maar de service blijft actief.
 </td>
<td><b>Onboarding:</b> Geen actie vereist. <br><br> <b>Offboarding:</b> Start het systeem opnieuw op.<br>
Zie <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10-apparaten</a>.</td>
</tr>
<tr>
<td>9</td>
<td>Het begintype van de Microsoft Defender voor Eindpunt-service is niet gewijzigd. Foutcode: <code>variable</code> .</td>
<td><b>Tijdens onboarding:</b> Het apparaat is niet correct aan boord en rapporteert niet aan de portal. <br><br><b>Tijdens offboarding:</b> Kan het begintype van de service niet wijzigen. Het offboardingproces wordt voortgezet. </td>
<td>Controleer of de onboarding-instellingen en scripts correct zijn geïmplementeerd. Probeer de configuratiepakketten opnieuw te configureren.<br>
Zie <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10-apparaten</a>.</td>
</tr>
<tr>
<td>10</td>
<td>Microsoft Defender voor Endpoint-service kan de onboarding-informatie niet blijven gebruiken. Foutcode: <code>variable</code> .</td>
<td>Het apparaat is niet correct aan boord en rapporteert niet aan de portal.</td>
<td>Controleer of de onboarding-instellingen en scripts correct zijn geïmplementeerd. Probeer de configuratiepakketten opnieuw te configureren.<br>
Zie <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10-apparaten</a>.</td>
</tr>
<tr>
<td>11</td>
<td>Onboarding or re-onboarding of Defender for Endpoint service completed.</td>
<td>Het apparaat is correct aan boord.</td>
<td>Normale bedrijfsmelding; geen actie vereist.<br>
Het kan enkele uren duren voordat het apparaat in de portal wordt weergegeven.</td>
</tr>
<tr>
<td>12</td>
<td>Microsoft Defender voor Eindpunt kan de standaardconfiguratie niet toepassen.</td>
<td>Service kon de standaardconfiguratie niet toepassen.</td>
<td>Deze fout moet na een korte periode worden opgelost.</td>
</tr>
<tr>
<td>13</td>
<td>Microsoft Defender voor endpoint-apparaat-id berekend: <code>variable</code> .</td>
<td>Normaal besturingssysteem.</td>
<td>Normale bedrijfsmelding; geen actie vereist.</td>
</tr>
<tr>
<td>15</td>
<td>Microsoft Defender voor Eindpunt kan het opdrachtkanaal niet starten met URL: <code>variable</code> .</td>
<td>Variabele = URL van de defender voor eindpuntverwerkingsservers.<br>
De service kan geen contact opnemen met de externe verwerkingsservers op die URL.</td>
<td>Controleer de verbinding met de URL. Zie <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Proxy en internetverbinding configureren.</a></td>
</tr>
<tr>
<td>17</td>
<td>Microsoft Defender voor Endpoint-service kan de verbonden gebruikerservaringen en telemetrieservicelocatie niet wijzigen. Foutcode: <code>variable</code> .</td>
<td>Er is een fout opgetreden bij de Windows-telemetrieservice.</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Controleer of de diagnostische gegevensservice is ingeschakeld.</a><br>
Controleer of de onboarding-instellingen en scripts correct zijn geïmplementeerd. Probeer de configuratiepakketten opnieuw te configureren.<br>
Zie <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10-apparaten</a>.</td>
</tr>
<tr>
<td>18</td>
<td>OOBE (Windows Welkom) is voltooid.</td>
<td>De service wordt pas begonnen nadat alle Windows-updates zijn geïnstalleerd.</td>
<td>Normale bedrijfsmelding; geen actie vereist.</td>
</tr>
<tr>
<td>19</td>
<td>OOBE (Windows Welcome) is nog niet voltooid.</td>
<td>De service wordt pas begonnen nadat alle Windows-updates zijn geïnstalleerd.</td>
<td>Normale bedrijfsmelding; geen actie vereist.<br>
Als deze fout blijft bestaan nadat een systeem opnieuw is gestart, moet u ervoor zorgen dat alle Windows-updates volledig zijn geïnstalleerd.</td>
</tr>
<tr>
<td>20</td>
<td>Kan niet wachten totdat OOBE (Windows Welcome) is voltooid. Foutcode: <code>variable</code> .</td>
<td>Interne fout.</td>
<td>Als deze fout blijft bestaan nadat een systeem opnieuw is gestart, moet u ervoor zorgen dat alle Windows-updates volledig zijn geïnstalleerd.</td>
</tr>
<tr>
<td>25</td>
<td>De statusstatus van het register is niet opnieuw ingesteld door de Microsoft Defender voor eindpuntservice. Foutcode: <code>variable</code> .</td>
<td>Het apparaat is niet correct aan boord.
De service rapporteert aan de portal, maar de service wordt mogelijk niet weergegeven als geregistreerd in SCCM of het register.</td>
<td>Controleer of de onboarding-instellingen en scripts correct zijn geïmplementeerd. Probeer de configuratiepakketten opnieuw te configureren.<br>
Zie <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10-apparaten</a>.</td>
</tr>
<tr>
<td>26</td>
<td>Microsoft Defender voor Eindpunt-service kan de onboarding-status niet instellen in het register. Foutcode: <code>variable</code> .</td>
<td>Het apparaat is niet correct aan boord.<br>
De service rapporteert aan de portal, maar de service wordt mogelijk niet weergegeven als geregistreerd in SCCM of het register.</td>
<td>Controleer of de onboarding-instellingen en scripts correct zijn geïmplementeerd. Probeer de configuratiepakketten opnieuw te configureren.<br>
Zie <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10-apparaten</a>.</td>
</tr>
<tr>
<td>27</td>
<td>Microsoft Defender for Endpoint-service kan de sense aware-modus niet inschakelen in Microsoft Defender Antivirus. Onboarding is mislukt. Foutcode: <code>variable</code> .</td>
<td>Normaal gesproken voert Microsoft Defender Antivirus een speciale passieve status in als een ander antimalwareproduct in realtime correct wordt uitgevoerd op het apparaat en het apparaat rapporteert aan Defender voor Eindpunt.</td>
<td>Controleer of de onboarding-instellingen en scripts correct zijn geïmplementeerd. Probeer de configuratiepakketten opnieuw te configureren.<br>
Zie <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10-apparaten</a>.<br>
Zorg ervoor dat antimalwarebeveiliging in realtime correct wordt uitgevoerd.</td>
</tr>
<tr>
<td>28</td>
<td>Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration failed. Foutcode: <code>variable</code> .</td>
<td>Er is een fout opgetreden bij de Windows-telemetrieservice.</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Controleer of de diagnostische gegevensservice is ingeschakeld.</a><br>
Controleer of de onboarding-instellingen en scripts correct zijn geïmplementeerd. Probeer de configuratiepakketten opnieuw te configureren.<br>
Zie <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10-apparaten</a>.</td>
</tr>
<tr>
<td>29</td>
<td>Kan de offboarding-parameters niet lezen. Fouttype: %1, Foutcode: %2, Beschrijving: %3 </td>
<td>Deze gebeurtenis treedt op wanneer het systeem&#39;de offboarding-parameters kan lezen.</td>
<td>Controleer of het apparaat internettoegang heeft en voer vervolgens het hele offboarding-proces opnieuw uit. Controleer of het offboarding-pakket niet is verlopen.</td>
</tr>
<tr>
<td>30</td>
<td>Microsoft Defender for Endpoint-service kan de sense aware-modus niet uitschakelen in Microsoft Defender Antivirus. Foutcode: <code>variable</code> .</td>
<td>Normaal gesproken voert Microsoft Defender Antivirus een speciale passieve status in als een ander antimalwareproduct in realtime correct wordt uitgevoerd op het apparaat en het apparaat rapporteert aan Defender voor Eindpunt.</td>
<td>Controleer of de onboarding-instellingen en scripts correct zijn geïmplementeerd. Probeer de configuratiepakketten opnieuw te configureren.<br>
Zie <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10-apparaten</a><br>
Zorg ervoor dat antimalwarebeveiliging in realtime correct wordt uitgevoerd.</td>
</tr>
<tr>
<td>31</td>
<td>Microsoft Defender for Endpoint Connected User Experiences and Telemetry service unregistration failed.Microsoft Defender for Endpoint Connected User Experiences and Telemetry service unregistration failed. Foutcode: <code>variable</code> .</td>
<td>Er is een fout opgetreden bij de Windows-telemetrieservice tijdens onboarding. Het offboardingproces wordt voortgezet.</td>
<td><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Controleer op fouten met de Windows-telemetrieservice.</a></td>
</tr>
<tr>
<td>32</td>
<td>Microsoft Defender for Endpoint-service heeft niet gevraagd om zichzelf te stoppen na het offboarden. Foutcode: %1</td>
<td>Er is een fout opgetreden tijdens het offboarden.</td>
<td>Start het apparaat opnieuw op.</td>
</tr>
<tr>
<td>33</td>
<td>Microsoft Defender for Endpoint-service kan SENSE GUID niet aanhouden. Foutcode: <code>variable</code> .</td>
<td>Er wordt een unieke id gebruikt voor elk apparaat dat rapporteert aan de portal.<br>
Als de id niet blijft bestaan, wordt hetzelfde apparaat mogelijk tweemaal weergegeven in de portal.</td>
<td>Controleer de registermachtigingen op het apparaat om ervoor te zorgen dat de service het register kan bijwerken.</td>
</tr>
<tr>
<td>34</td>
<td>Microsoft Defender voor Endpoint-service kan zichzelf niet toevoegen als afhankelijkheid van de verbonden gebruikerservaringen en telemetrieservice, waardoor het onboardingproces mislukt. Foutcode: <code>variable</code> .</td>
<td>Er is een fout opgetreden bij de Windows-telemetrieservice.</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Controleer of de diagnostische gegevensservice is ingeschakeld.</a><br>
Controleer of de onboarding-instellingen en scripts correct zijn geïmplementeerd. Probeer de configuratiepakketten opnieuw te configureren.<br>
Zie <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10-apparaten</a>.</td>
</tr>
<tr>
<td>35</td>
<td>Microsoft Defender for Endpoint-service kan zichzelf niet verwijderen als afhankelijkheid van de verbonden gebruikerservaringen en telemetrieservice. Foutcode: <code>variable</code> .</td>
<td>Er is een fout opgetreden bij de Windows-telemetrieservice tijdens het offboarden. Het offboardingproces wordt voortgezet.
</td>
<td>Controleer op fouten met de Windows-diagnostische gegevensservice.</td>
</tr>
<tr>
<td>36</td>
<td>Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration succeeded. Voltooiingscode: <code>variable</code> .</td>
<td>Het registreren van Defender voor Eindpunt met de verbonden gebruikerservaringen en telemetrieservice is voltooid.</td>
<td>Normale bedrijfsmelding; geen actie vereist.</td>
</tr>
<tr>
<td>37</td>
<td>Microsoft Defender voor eindpunt Een module staat op het punt het quotum te overschrijden. Module: %1, Quotum: {%2} {%3}, Percentage van quotumgebruik: %4.</td>
<td>Het apparaat heeft het toegewezen quotum van het huidige venster van 24 uur bijna gebruikt. Het wordt nu beperkt.</td>
<td>Normale bedrijfsmelding; geen actie vereist.</td>
</tr>
<tr>
<td>38</td>
<td>Netwerkverbinding wordt als laag aangemerkt. Microsoft Defender voor Eindpunt neemt elke %1 minuten contact op met de server. Verbinding met dataverbinding: %2, internet beschikbaar: %3, gratis netwerk beschikbaar: %4.</td>
<td>Het apparaat gebruikt een netwerk met een datameter en neemt minder vaak contact op met de server.</td>
<td>Normale bedrijfsmelding; geen actie vereist.</td>
</tr>
<tr>
<td>39</td>
<td>Netwerkverbinding wordt als normaal aangemerkt. Microsoft Defender voor Eindpunt neemt elke %1 minuten contact op met de server. Verbinding met dataverbinding: %2, internet beschikbaar: %3, gratis netwerk beschikbaar: %4.</td>
<td>Het apparaat gebruikt geen verbinding met een datameter en neemt zoals gewoonlijk contact op met de server.</td>
<td>Normale bedrijfsmelding; geen actie vereist.</td>
</tr>
<tr>
<td>40</td>
<td>De batterijtoestand wordt als laag aangeduid. Microsoft Defender voor Eindpunt neemt elke %1 minuten contact op met de server. Batterijtoestand: %2.</td>
<td>Het apparaat heeft een laag batterijniveau en neemt minder vaak contact op met de server.</td>
<td>Normale bedrijfsmelding; geen actie vereist.</td>
</tr>
<tr>
<td>41</td>
<td>De batterijtoestand wordt als normaal aangeduid. Microsoft Defender voor Eindpunt neemt elke %1 minuten contact op met de server. Batterijtoestand: %2.</td>
<td>Het apparaat heeft geen laag batterijniveau en neemt zoals gewoonlijk contact op met de server.</td>
<td>Normale bedrijfsmelding; geen actie vereist.</td>
</tr>
<tr>
<td>42</td>
<td>Microsoft Defender for Endpoint WDATP-component kan geen actie uitvoeren. Component: %1, Actie: %2, Uitzonderingstype: %3, Uitzonderingsbericht: %4</td>
<td>Interne fout. De service kan niet worden begonnen.</td>
<td>Als deze fout blijft bestaan, neem dan contact op met ondersteuning.</td>
</tr>
<tr>
<td>43</td>
<td>Microsoft Defender for Endpoint WDATP-component kan geen actie uitvoeren. Component: %1, Actie: %2, Uitzonderingstype: %3, Uitzonderingsfout: %4, Uitzonderingsbericht: %5</td>
<td>Interne fout. De service kan niet worden begonnen.</td>
<td>Als deze fout blijft bestaan, neem dan contact op met ondersteuning.</td>
</tr>
<tr>
<td>44</td>
<td>Offboarding of Defender for Endpoint service completed.</td>
<td>De service is buiten het bord gezet.</td>
<td>Normale bedrijfsmelding; geen actie vereist.</td>
</tr>
<tr>
<td>45</td>
<td>Kan zich niet registreren en de gebeurtenis traceersessie starten [%1]. Foutcode: %2</td>
<td>Er is een fout opgetreden bij het opstarten van de service tijdens het maken van ETW-sessie. Hierdoor is het starten van een service mislukt.</td>
<td>Als deze fout blijft bestaan, neem dan contact op met ondersteuning.</td>
</tr>
<tr>
<td>46</td>
<td>Kan de gebeurtenis traceersessie niet registreren en starten [%1] vanwege een gebrek aan resources. Foutcode: %2. Dit komt waarschijnlijk omdat er te veel actieve gebeurtenis tracesessies zijn. De service wordt binnen 1 minuut opnieuw proberen.</td>
<td>Er is een fout opgetreden bij het opstarten van de service tijdens het maken van ETW-sessie vanwege een gebrek aan resources. De service is gestart en wordt uitgevoerd, maar meldt geen sensorgebeurtenis totdat de ETW-sessie is gestart.</td>
<td>Normale bedrijfsmelding; geen actie vereist. De service probeert de sessie elke minuut te starten.</td>
</tr>
<tr>
<td>47</td>
<td>De gebeurtenis trace-sessie is geregistreerd en gestart- hersteld na eerdere mislukte pogingen.</td>
<td>Deze gebeurtenis volgt de vorige gebeurtenis na het starten van de ETW-sessie.</td>
<td>Normale bedrijfsmelding; geen actie vereist.</td>
</tr>
<tr>
<td>48</td>
<td>Kan geen provider [%1] toevoegen aan gebeurtenis traceersessie [%2]. Foutcode: %3. Dit betekent dat gebeurtenissen van deze provider niet worden gerapporteerd.</td>
<td>Het is niet gelukt om een provider toe te voegen aan ETW-sessie. Hierdoor worden de providergebeurtenissen niet gerapporteerd.</td>
<td>Controleer de foutcode. Als de fout zich blijft voordoen, neem dan contact op met ondersteuning.</td>
</tr>
</tr>
</tbody>
</table>

>Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a>Verwante onderwerpen
- [Onboard Windows 10-apparaten](configure-endpoints.md)
- [Instellingen voor apparaatproxy en internetverbinding configureren](configure-proxy-internet.md)
- [Problemen met Microsoft Defender voor eindpunt oplossen](troubleshoot-onboarding.md)
