---
title: Waarschuwingen voor Microsoft Defender voor eindpunten beheren
description: Wijzig de status van waarschuwingen, maak onderdrukkingsregels om waarschuwingen te verbergen, opmerkingen in te dienen en de wijzigingsgeschiedenis voor afzonderlijke waarschuwingen te controleren met het menu Waarschuwing beheren.
keywords: waarschuwingen beheren, beheren, waarschuwingen, status, nieuw, in uitvoering, opgelost, waarschuwingen oplossen, onderdrukken, onderdrukken, onderdrukken, regels, context, geschiedenis, opmerkingen, wijzigingen
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
ms.technology: mde
ms.openlocfilehash: f03c2209b369e6fb9e001452c53073daeb5fe1c6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186999"
---
# <a name="manage-microsoft-defender-for-endpoint-alerts"></a>Waarschuwingen voor Microsoft Defender voor eindpunten beheren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-managealerts-abovefoldlink)

Defender voor Eindpunt meldt u via waarschuwingen over mogelijke schadelijke gebeurtenissen, kenmerken en contextuele informatie. Een overzicht van nieuwe waarschuwingen wordt weergegeven in het **dashboard** Beveiligingsbewerkingen en u hebt toegang tot alle waarschuwingen in de **wachtrij Waarschuwingen.**

U kunt waarschuwingen beheren door een waarschuwing te selecteren in de wachtrij Waarschuwingen **of** op het **tabblad** Waarschuwingen van de pagina Apparaat voor een afzonderlijk apparaat.

Als u een waarschuwing selecteert op een van deze locaties, wordt het deelvenster **Waarschuwingsbeheer weergegeven.**

![Afbeelding van waarschuwingsbeheervenster en waarschuwingenwachtrij](images/atp-alerts-selected.png)

## <a name="link-to-another-incident"></a>Koppeling maken naar een ander incident
U kunt een nieuw incident maken vanuit de waarschuwing of een koppeling naar een bestaand incident. 

## <a name="assign-alerts"></a>Waarschuwingen toewijzen
Als er nog geen waarschuwing is toegewezen, kunt u Toewijzen aan **mij** selecteren om de waarschuwing aan uzelf toe te wijzen.


## <a name="suppress-alerts"></a>Waarschuwingen onderdrukken
Er kunnen scenario's zijn waarin u waarschuwingen wilt onderdrukken die worden weergegeven in het Microsoft Defender-beveiligingscentrum. Met Defender voor Eindpunt kunt u onderdrukkingsregels maken voor specifieke waarschuwingen die onschadelijk zijn, zoals bekende hulpmiddelen of processen in uw organisatie.

Onderdrukkingsregels kunnen worden gemaakt op een bestaande waarschuwing. Ze kunnen zo nodig worden uitgeschakeld en opnieuw worden gebruikt.

Wanneer een onderdrukkingsregel wordt gemaakt, wordt deze van kracht vanaf het moment dat de regel wordt gemaakt. De regel heeft geen invloed op bestaande waarschuwingen die al in de wachtrij staan, voordat de regel wordt gemaakt. De regel wordt alleen toegepast op waarschuwingen die voldoen aan de voorwaarden die zijn ingesteld nadat de regel is gemaakt.

Er zijn twee contexten voor een onderdrukkingsregel waar u uit kunt kiezen:

- **Waarschuwing onderdrukken op dit apparaat**
- **Waarschuwing in mijn organisatie onderdrukken**

Met de context van de regel kunt u aanpassen wat er in de portal wordt opgedoken en ervoor zorgen dat alleen echte beveiligingswaarschuwingen in de portal worden opgedoken.

U kunt de voorbeelden in de volgende tabel gebruiken om de context voor een onderdrukkingsregel te kiezen:

| **Context**                           | **Definitie**                                                                                                                                              | **Voorbeeldscenario's**                                                                                                                                                                                                  |
|:--------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Waarschuwing onderdrukken op dit apparaat**    | Waarschuwingen met dezelfde waarschuwingstitel en alleen op dat specifieke apparaat worden onderdrukt. <br /><br />Alle andere waarschuwingen op dat apparaat worden niet onderdrukt. | <ul><li>Een beveiligingsonderzoeker onderzoekt een schadelijk script dat is gebruikt om andere apparaten in uw organisatie aan te vallen.</li><li>Een ontwikkelaar maakt regelmatig PowerShell-scripts voor zijn of haar team.</li></ul> |
| **Waarschuwing in mijn organisatie onderdrukken** | Waarschuwingen met dezelfde waarschuwingstitel op elk apparaat worden onderdrukt.                                                                                         | <ul><li>Een goedaardig beheerhulpmiddel wordt door iedereen in uw organisatie gebruikt.</li></ul>                                                                                                                               |

### <a name="suppress-an-alert-and-create-a-new-suppression-rule"></a>Een waarschuwing onderdrukken en een nieuwe onderdrukkingsregel maken:
Maak aangepaste regels om te bepalen wanneer waarschuwingen worden onderdrukt of opgelost. U kunt de context bepalen voor wanneer een waarschuwing wordt onderdrukt door de waarschuwingstitel, indicator voor compromissen en de voorwaarden op te geven. Nadat u de context hebt opgegeven, kunt u de actie en het bereik van de waarschuwing configureren. 

1. Selecteer de waarschuwing die u wilt onderdrukken. Hiermee wordt het deelvenster **Waarschuwingsbeheer** weergegeven.

2.  Selecteer **Een onderdrukkende regel maken.**

    U kunt een onderdrukkingsvoorwaarde maken met behulp van deze kenmerken. Er wordt een OPERATOR AND toegepast tussen elke voorwaarde, dus onderdrukking vindt alleen plaats als aan alle voorwaarden wordt voldaan.
    
    * Bestand SHA1
    * Bestandsnaam - jokerteken ondersteund
    * Mappad - jokerteken ondersteund
    * IP-adres
    * URL - jokerteken ondersteund
    * Opdrachtregel - jokerteken ondersteund

3. Selecteer het **IOC activeren.**
    
4. Geef de actie en het bereik van de waarschuwing op. <br>
   U kunt een waarschuwing automatisch oplossen of verbergen in de portal. Waarschuwingen die automatisch worden opgelost, worden weergegeven in de opgeloste sectie van de waarschuwingenwachtrij, waarschuwingspagina en apparaattijdlijn en worden weergegeven als opgelost in defender voor eindpunt-API's. <br><br> Waarschuwingen die zijn gemarkeerd als verborgen, worden vanaf het hele systeem onderdrukt, zowel op de bijbehorende waarschuwingen van het apparaat als vanuit het dashboard en worden niet gestreamd via API's van Defender voor eindpunten.


5. Voer een regelnaam en een opmerking in.

6. Klik op **Opslaan**.

#### <a name="view-the-list-of-suppression-rules"></a>De lijst met onderdrukkingsregels weergeven

1. Selecteer in het navigatiedeelvenster **Instellingen**  >  **Waarschuwingsonderdrukking**.

2. De lijst met onderdrukkingsregels bevat alle regels die gebruikers in uw organisatie hebben gemaakt.

Zie Onderdrukkingsregels beheren voor meer informatie over het beheren van [onderdrukkingsregels.](manage-suppression-rules.md)

## <a name="change-the-status-of-an-alert"></a>De status van een waarschuwing wijzigen

U kunt waarschuwingen categoriseren **(als Nieuw**, **In uitvoering** of **Opgelost)** door de status van de waarschuwingen te wijzigen naarmate het onderzoek vordert. Op deze manier kunt u organiseren en beheren hoe uw team kan reageren op waarschuwingen.

Een teamleider kan bijvoorbeeld alle nieuwe waarschuwingen **bekijken** en deze toewijzen aan de wachtrij **In voortgang** voor verdere analyse.

De teamleider kan de waarschuwing ook  toewijzen aan de wachtrij Opgelost als deze weet dat de waarschuwing goedaardig is, afkomstig is van een apparaat dat niet relevant is (zoals een van een beveiligingsbeheerder) of wordt afgehandeld via een eerdere waarschuwing.



## <a name="alert-classification"></a>Waarschuwingsclassificatie
U kunt ervoor kiezen geen classificatie in te stellen of op te geven of een waarschuwing een echte waarschuwing of een onwaar waarschuwing is. Het is belangrijk om de classificatie van waar positief/onwaar positief te geven. Deze classificatie wordt gebruikt om de kwaliteit van waarschuwingen te controleren en waarschuwingen nauwkeuriger te maken. Het veld 'bepaling' definieert extra fidelity voor een 'true positive' classificatie. 

## <a name="add-comments-and-view-the-history-of-an-alert"></a>Opmerkingen toevoegen en de geschiedenis van een waarschuwing weergeven
U kunt opmerkingen toevoegen en historische gebeurtenissen bekijken over een waarschuwing om eerdere wijzigingen in de waarschuwing weer te geven.

Wanneer een wijziging of opmerking wordt aangebracht in een waarschuwing, wordt deze opgenomen in de sectie **Opmerkingen en geschiedenis.**

Toegevoegde opmerkingen worden direct weergegeven in het deelvenster.


## <a name="related-topics"></a>Verwante onderwerpen
- [Onderdrukkende regels beheren](manage-suppression-rules.md)
- [De wachtrij waarschuwingen voor Microsoft Defender voor eindpunten weergeven en ordenen](alerts-queue.md)
- [Microsoft Defender onderzoeken voor eindpuntwaarschuwingen](investigate-alerts.md)
- [Een bestand onderzoeken dat is gekoppeld aan een waarschuwing van Microsoft Defender voor eindpunt](investigate-files.md)
- [Apparaten onderzoeken in de lijst Microsoft Defender voor eindpuntapparaten](investigate-machines.md)
- [Een IP-adres onderzoeken dat is gekoppeld aan een waarschuwing van Microsoft Defender voor eindpunt](investigate-ip.md)
- [Een domein onderzoeken dat is gekoppeld aan een waarschuwing van Microsoft Defender voor eindpunt](investigate-domain.md)
- [Een gebruikersaccount onderzoeken in Microsoft Defender voor Eindpunt](investigate-user.md)
