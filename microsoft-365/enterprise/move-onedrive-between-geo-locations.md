---
title: Een OneDrive-site naar een andere geografische locatie verplaatsen
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: Informatie over het verplaatsen van een OneDrive-site naar een andere geografische locatie, waaronder het plannen van site-verplaatsings-en gebruikers vooruitzichten.
ms.openlocfilehash: 59b3fb47fd195967e7af056c7a71fb4e736471d1
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688925"
---
# <a name="move-a-onedrive-site-to-a-different-geo-location"></a>Een OneDrive-site naar een andere geografische locatie verplaatsen 

Met OneDrive geo Move kunt u de OneDrive van een gebruiker naar een andere geografische locatie verplaatsen. OneDrive geo Move voor OneDrive wordt uitgevoerd door de SharePoint Online-beheerder of de globale beheerder van Microsoft 365. Voordat u begint met het verplaatsen van een OneDrive-geografische verplaatsing, moet u de gebruiker op de hoogte stellen van de gebruiker van wie de OneDrive wordt verplaatst en wordt u aangeraden alle bestanden te sluiten gedurende de verhuizing. (Als de gebruiker tijdens de verhuizing een document heeft geopend met de Office-client, moet het document worden opgeslagen op de nieuwe locatie.) U kunt de verhuizing later opnieuw plannen.

De OneDrive-service gebruikt Azure Blob Storage om inhoud op te slaan. De blobopslag van de opslagruimte die gekoppeld is aan de OneDrive van de gebruiker wordt verplaatst van de bron naar het doel geografische gebied binnen 40 dagen van de doel-OneDrive die beschikbaar is voor de gebruiker. De toegang tot de OneDrive van de gebruiker wordt hersteld zodra de beschikbare doel-OneDrive beschikbaar is.

Tijdens OneDrive geo-verhuizings venster (ongeveer 2-6 uur) wordt de OneDrive van de gebruiker ingesteld op alleen-lezen. Gebruikers hebben nog steeds toegang tot hun bestanden via de OneDrive-synchronisatieclient of hun OneDrive-site in SharePoint Online. Nadat OneDrive is verplaatst, wordt de gebruiker automatisch verbonden met hun OneDrive op de doellocatie van de geografische locatie wanneer ze naar OneDrive navigeren in het startprogramma voor apps van Microsoft 365. De synchronisatieclient begint automatisch met synchroniseren vanaf de nieuwe locatie.

Voor de procedures in dit artikel is de [Microsoft SharePoint Online PowerShell-module](https://www.microsoft.com/download/details.aspx?id=35588)vereist.

## <a name="communicating-to-your-users"></a>Communiceren met uw gebruikers

Als u OneDrive-sites tussen geo-locaties verplaatst, is het belangrijk om te communiceren met uw gebruikers wat u kunt verwachten. Dit kan de gebruikers verwarring en oproepen naar uw helpdesk verminderen. E-mail uw gebruikers voorafgaand aan de verhuizing en laat ze de volgende informatie weten:

- Wanneer de verplaatsing naar verwachting begint en hoe lang deze duurt
- De geografische locatie waarnaar de OneDrive wordt verplaatst, en de URL voor toegang tot de nieuwe locatie
- De persoon moet hun bestanden sluiten en geen wijzigingen aanbrengen tijdens de verhuizing.
- Het is niet mogelijk om bestanden te bewerken en te delen.
- Wat kunt u verwachten van de [gebruikerservaring in een omgeving met meerdere geografische omgevingen](multi-geo-user-experience.md) ?

Zorg ervoor dat u uw gebruikers een e-mailbericht stuurt wanneer de overstap is voltooid, zodat ze verder kunnen werken in OneDrive.

## <a name="scheduling-onedrive-site-moves"></a>OneDrive-site plannen

U kunt instellen dat de OneDrive-site vooraf wordt bewogen (verderop in dit artikel wordt beschreven). We raden u aan te beginnen met een klein aantal gebruikers om uw werkstromen en communicatie strategieën te valideren. Wanneer u vertrouwd bent met het proces, kunt u het volgende plannen:

- U kunt maximaal 4.000 verplaatsen.
- Zoals de verhuizing begint, kunt u meer plannen, met een maximum van 4.000 in behandeling in de wachtrij en op een bepaald moment.
- De maximumgrootte van een OneDrive die kan worden verplaatst, is 1 terabyte (1 TB).

## <a name="moving-a-onedrive-site"></a>Een OneDrive-site verplaatsen

Voor het uitvoeren van een OneDrive-geografische verplaatsing moet de tenantbeheerder eerst de voorkeurs gegevenslocatie (PDL) van de gebruiker instellen op de gewenste geografische locatie. Wanneer de PDL is ingesteld, wacht u minimaal 24 uur voordat de PDL-update via de geo-locaties is gesynchroniseerd voordat u de geografische verhuizing van OneDrive start.

Wanneer u de geo Move-cmdlets gebruikt, kunt u de volgende syntaxis gebruiken om verbinding te maken met de SPO-service op de huidige OneDrive-geografische locatie van de gebruiker:

`Connect-SPOService -url https://<tenantName>-admin.sharepoint.com`

Als u bijvoorbeeld OneDrive van User ' Matt@contosoenergy.onmicrosoft.com ' wilt verplaatsen, maakt u verbinding met het SharePoint-Beheercentrum als de OneDrive van de gebruiker wordt gebruikt in plaats van de geografische locatie van de gebruiker:

`Connect-SPOSservice -url https://contosoenergyeur-admin.sharepoint.com`

![Schermafbeelding van het PowerShell-venster met de cmdlet Connect-sposervice](../media/move-onedrive-between-geo-locations-image1.png)

## <a name="validating-the-environment"></a>De omgeving valideren

U wordt aangeraden om de omgeving te valideren voordat u een OneDrive-geografische verhuizing start.

Voer de volgende opdracht uit om ervoor te zorgen dat alle geo-locaties compatibel zijn:

`Get-SPOGeoMoveCrossCompatibilityStatus`

U ziet een lijst met uw geografische locaties en u kunt de inhoud van de geografische locaties verplaatsten, ongeacht of deze wordt aangeduid als compatibel. Als met de opdracht ' niet-compatibel ' is geretourneerd, probeert u de status op een later tijdstip te valideren.

Als een OneDrive een subsite bevat, kunt u deze bijvoorbeeld niet verplaatsen. U kunt de cmdlet start-SPOUserAndContentMove gebruiken met de parameter-ValidationOnly om te controleren of de OneDrive kan worden verplaatst:

`Start-SPOUserAndContentMove -UserPrincipalName <UPN> -DestinationDataLocation <DestinationDataLocation> -ValidationOnly`

Hierdoor wordt het resultaat weergegeven als de OneDrive klaar is om te worden verplaatst of als er een fout is opgetreden als de verhuizing niet kan worden verplaatst. Nadat u hebt gecontroleerd of de OneDrive klaar is om te worden verplaatst, kunt u beginnen met verplaatsen.

## <a name="start-a-onedrive-geo-move"></a>Een geografische verhuizing van OneDrive starten

Voer de volgende opdracht uit om de verhuizing te starten:  

`Start-SPOUserAndContentMove -UserPrincipalName <UserPrincipalName> -DestinationDataLocation <DestinationDataLocation>`

Met deze parameters:

-   _UserPrincipalName_ : UPN van de gebruiker van wie OneDrive wordt verplaatst.

-   _DestinationDataLocation_ – geografische locatie waar de OneDrive moet worden verplaatst. Dit moet gelijk zijn aan de voorkeur van de gebruikerslocatie van de gebruiker.

Als u bijvoorbeeld de OneDrive van matt@contosoenergy.onmicrosoft.com van EUR naar AUS wilt verplaatsen, voert u de volgende opdracht uit:

`Start-SPOUserAndContentMove -UserPrincipalName matt@contosoenergy.onmicrosoft.com -DestinationDataLocation AUS`

![Schermafbeelding van het PowerShell-venster met de cmdlet start-SPOUserAndContentMove](../media/move-onedrive-between-geo-locations-image2.png)

Gebruik een van de volgende parameters als u een geo-overstap voor een later tijdstip wilt plannen:

-   _PreferredMoveBeginDate_ : de verhuizing gaat waarschijnlijk op deze specifieke tijd. De tijd moet zijn opgegeven in Coordinated Universal Time (UTC).

-   _PreferredMoveEndDate_ : de verhuizing wordt waarschijnlijk op basis van de opgegeven tijd voltooid. De tijd moet zijn opgegeven in Coordinated Universal Time (UTC). 

## <a name="cancel-a-onedrive-geo-move"></a>Een geo-verhuizing van OneDrive opzeggen 

U kunt de geografische verplaatsing van een OneDrive van een gebruiker stoppen, mits de overstap niet wordt uitgevoerd of voltooid met behulp van de cmdlet:

`Stop-SPOUserAndContentMove – UserPrincipalName <UserPrincipalName>`

Waarbij _userPrincipalName_ de UPN is van de gebruiker van wie u de OneDrive-verplaatsing wilt stoppen.

## <a name="determining-current-status"></a>De huidige status bepalen

Met de cmdlet Get-SPOUserAndContentMoveState kunt u de status van een OneDrive-geografische plaats in-of uitzetten.

De verplaatsings status wordt beschreven in de volgende tabel.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Status</strong></th>
<th align="left"><strong>Beschrijving</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">NotStarted</td>
<td align="left">De verhuizing is niet gestart.</td>
</tr>
<tr class="even">
<td align="left">Invoortgang (<em>n</em>/4)</td>
<td align="left">De verplaatsing wordt uitgevoerd in een van de volgende staten: validering (1/4), back-up (2/4), herstellen (3/4), opruimen (4/4).</td>
</tr>
<tr class="odd">
<td align="left">Bevestiging</td>
<td align="left">De verhuizing is voltooid.</td>
</tr>
<tr class="even">
<td align="left">Mislukt</td>
<td align="left">Verplaatsen mislukt.</td>
</tr>
</tbody>
</table>

Als u de status van de verhuizing van een bepaalde gebruiker wilt achterhalen, gebruikt u de parameter UserPrincipalName:

`Get-SPOUserAndContentMoveState -UserPrincipalName <UPN>`

Gebruik de parameter MoveState met een van de volgende waarden als u wilt weten hoe u de status van alle in-en uitnodigingen van de geografische locatie waarmee u bent verbonden wilt achterhalen.

`Get-SPOUserAndContentMoveState -MoveState <value>`

U kunt ook de `-Verbose` parameter toevoegen voor uitgebreide beschrijvingen van de verplaatsings status.

## <a name="user-experience"></a>Gebruikerservaring

Gebruikers van OneDrive moeten minimaal verstoren als hun OneDrive naar een andere geografische locatie wordt verplaatst. Als u tijdens de verhuizing een kortere alleen-lezen status wilt hebben, blijven bestaande koppelingen en machtigingen op de verwachte manier werken als de verplaatsing is voltooid.

### <a name="onedrive-for-business"></a>OneDrive voor Bedrijven

Terwijl de overstap wordt uitgevoerd, wordt de OneDrive van de gebruiker ingesteld op alleen-lezen. Wanneer de overstap is voltooid, wordt de gebruiker doorgestuurd naar zijn of haar OneDrive op de nieuwe geo-locatie wanneer ze naar OneDrive navigeren in het startprogramma voor Microsoft 365-apps of een webbrowser.

### <a name="permissions-on-onedrive-content"></a>Machtigingen voor OneDrive-inhoud

Gebruikers met machtigingen voor OneDrive-inhoud blijven toegang tot de inhoud tijdens de verhuizing en nadat deze is voltooid.

### <a name="onedrive-sync-client"></a>OneDrive-Synchronisatieclient 

Met de synchronisatieclient van OneDrive wordt automatisch het synchroniseren van synchronisatie naar de nieuwe OneDrive-locatie herkend en naadloos overgebracht nadat de geo-verplaatsing van OneDrive is voltooid. De gebruiker hoeft zich niet opnieuw aan te melden of een andere actie te ondernemen.  (Versie 17.3.6943.0625 of hoger van de synchronisatieclient vereist.)

Als een gebruiker een bestand bijwerkt terwijl de geo-verhuizing van OneDrive wordt uitgevoerd, wordt door de synchronisatieclient aangegeven dat het uploaden van bestanden in behandeling is terwijl de verhuizing plaatsvindt.

### <a name="sharing-links"></a>Koppelingen voordelen 

Na voltooiing van OneDrive geo-verhuizing worden de bestaande gedeelde koppelingen voor de bestanden die zijn verplaatst automatisch omgeleid naar de nieuwe geografische locatie.

### <a name="onenote-experience"></a>OneNote-ervaring 

Met de apps van OneNote Win32 client en UWP (Universal) wordt automatisch notitieblokken automatisch opgespoord en naadloos gesynchroniseerd met de nieuwe OneDrive-locatie nadat OneDrive geo Move is voltooid. De gebruiker hoeft zich niet opnieuw aan te melden of een andere actie te ondernemen. De enige zichtbare indicator voor de gebruiker is het synchroniseren van notitieblokken mislukt wanneer OneDrive geo-verplaatsing wordt uitgevoerd. Deze ervaring is beschikbaar in de volgende versies van OneNote-clients:

-   OneNote Win32-versie 16.0.8326.2096 (en later)

-   OneNote UWP: versie 16.0.8431.1006 (en later)

-   App OneNote Mobile: versie 16.0.8431.1011 (en later)

### <a name="teams-app"></a>Teams-app

Na voltooiing van OneDrive geo-verhuizing hebben gebruikers toegang tot hun OneDrive-bestanden in de app teams. Bestanden die worden gedeeld via teams-chat vanuit hun OneDrive voordat u geo-overstap gaat, blijven ook werken na voltooiing van de verhuizing.

### <a name="onedrive-for-business-mobile-app-ios"></a>Mobiele app van OneDrive voor bedrijven (iOS) 

Na voltooiing van OneDrive geo-verhuizing moet de gebruiker zich afmelden en opnieuw aanmelden op de mobiele iOS-app om te synchroniseren met de nieuwe OneDrive-locatie.

### <a name="existing-followed-groups-and-sites"></a>Bestaande gevolgde groepen en sites

Gevolgde sites en groepen worden weergegeven in het OneDrive van de gebruiker, ongeacht de geografische locatie. Sites en groepen die worden gehost op een andere geografische locatie, worden geopend op een apart tabblad.

### <a name="delve-geo-url-updates"></a>Geo-URL'S bijwerken in Delve

Gebruikers worden alleen naar de Delve-geo verzonden die overeenkomen met hun PDL, wanneer hun OneDrive naar de nieuwe geo is verplaatst.
