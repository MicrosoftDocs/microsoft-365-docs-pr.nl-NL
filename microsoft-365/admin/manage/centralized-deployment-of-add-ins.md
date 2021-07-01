---
title: Bepalen of gecentraliseerde implementatie van invoegvoegingen werkt voor uw organisatie
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: Bepaal of uw tenant en gebruikers aan de vereisten voldoen, zodat u gecentraliseerde implementatie kunt gebruiken om Office te implementeren.
ms.openlocfilehash: 5d6f225acb56d1ec092046297d708444bb8d93d2
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227954"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a>Bepalen of gecentraliseerde implementatie van invoegvoegingen werkt voor uw organisatie

Gecentraliseerde implementatie is de aanbevolen en meest uitgebreide manier voor de meeste klanten om Office te implementeren voor gebruikers en groepen binnen uw organisatie. Als u een beheerder bent, gebruikt u deze richtlijnen om te bepalen of uw organisatie en gebruikers voldoen aan de vereisten, zodat u gecentraliseerde implementatie kunt gebruiken.

Gecentraliseerde implementatie biedt de volgende voordelen:

- Een globale beheerder kan een invoegvoeging rechtstreeks toewijzen aan een gebruiker, aan meerdere gebruikers via een groep of aan iedereen in de organisatie.

- Wanneer de desbetreffende Office wordt gestart, wordt de invoegtoepassing automatisch gedownload. Als de invoegtoepassing invoegopdrachten ondersteunt, wordt de invoegtoepassing automatisch weergegeven op het lint in de Office toepassing.

- Invoegvoegingen worden niet meer weergegeven voor gebruikers als de beheerder de invoeging uit- of verwijdert, of als de gebruiker wordt verwijderd uit Azure Active Directory of uit een groep aan wie de invoegvoeging is toegewezen.

Gecentraliseerde implementatie ondersteunt drie bureaubladplatforms Windows, Mac en Online Office apps. Gecentraliseerde implementatie ondersteunt ook iOS en Android (Outlook alleen mobiele invoegvoegingen).

Het kan maximaal 24 uur duren voordat een invoegtoepassing aan alle gebruikers wordt weergegeven.

## <a name="before-you-begin"></a>Voordat u begint

Gecentraliseerde implementatie van invoegvoegingen vereist dat de gebruikers Microsoft 365 Enterprise SKU's gebruiken: E3/E5/F3 of Zakelijke SKU's: Business Basic, Business Standard, Business Premium (en zijn aangemeld bij Office met hun organisatie-id) en hebben Exchange Online en actieve Exchange Online-postvakken. Uw abonnementsmap moet zijn opgenomen of federatief zijn Azure Active Directory.
U kunt hieronder specifieke vereisten voor Office en Exchange of de compatibiliteitscontrole voor gecentraliseerde implementatie [gebruiken.](#centralized-deployment-compatibility-checker)

Gecentraliseerde implementatie biedt geen ondersteuning voor het volgende:

- Invoegtoepassingen die zijn gericht op Word, Excel of PowerPoint in Office 2013
- Een on-premises adreslijstservice
- Implementatie van invoeggebruik in een Exchange postvak on-prem
- Implementatie van invoegtoepassingen op SharePoint
- Teams apps
- Implementatie van componentobjectmodel (COM) of Visual Studio hulpprogramma's voor Office (VSTO) invoegingen.
- Implementaties van Microsoft 365 die geen Exchange Online zoals SKU's: Microsoft 365-apps voor Bedrijven en Microsoft 365-apps voor Enterprise.

### <a name="office-requirements"></a>Office Vereisten

- Voor Word, Excel en PowerPoint moeten uw gebruikers een van de volgende gebruiken:
  - Op een Windows apparaat, versie 1704 of hoger van Microsoft 365 Enterprise SKU's: E3/E5/F3 of Zakelijke SKU's: Business Basic, Business Standard, Business Standard, Premium.
  - Op een Mac, versie 15.34 of hoger.

- Voor Outlook moeten uw gebruikers een van de volgende opties gebruiken:
  - Versie 1701 of hoger van Microsoft 365 Enterprise SKU's: E3/E5/F3 of Zakelijke SKU's: Business Basic, Business Standard, Premium.
  - Versie 1808 of hoger van Office Professional Plus 2019 of Office Standard 2019.
  - Versie 16.0.4494.1000 of hoger van Office Professional Plus 2016 (MSI) of Office Standard 2016 (MSI)\*
  - Versie 15.0.4937.1000 of hoger van Office Professional Plus 2013 (MSI) of Office Standard 2013 (MSI)\*
  - Versie 16.0.9318.1000 of hoger van Office 2016 voor Mac
- Versie 2.75.0 of hoger van Outlook mobiel voor iOS
- Versie 2.2.145 of hoger van Outlook voor Android

    *MSI-versies van Outlook worden door beheerders geïnstalleerde invoegvoegingen weergegeven op het Outlook lint, niet in de sectie 'Mijn invoegvoegingen'.

### <a name="exchange-online-requirements"></a>Exchange Online vereisten

Microsoft Exchange slaat de invoegtoepassingsmanifesten op in de tenant van uw organisatie. De beheerder die invoegvoegingen implementeert en de gebruikers die deze invoegvoegingen ontvangen, moeten zich op een versie van Exchange Online die OAuth-verificatie ondersteunt.

Vraag de Exchange-beheerder van uw organisatie welke configuratie in gebruik is. OAuth-connectiviteit per gebruiker kan worden geverifieerd door de PowerShell-cmdlet [Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity) te gebruiken.


### <a name="centralized-deployment-compatibility-checker"></a>Gecentraliseerde compatibiliteitscontrole voor implementatie

Met de compatibiliteitscontrole voor gecentraliseerde implementatie kunt u controleren of de gebruikers in uw tenant zijn ingesteld voor het gebruik van Gecentraliseerde implementatie voor Word, Excel en PowerPoint. De compatibiliteitscontrole is niet vereist voor ondersteuning voor Outlook. Download de [compatibiliteitscontrole](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).

#### <a name="run-the-compatibility-checker"></a>De compatibiliteitscontrole uitvoeren

1. Start een verhoogd PowerShell.exe-venster.

2. Voer de volgende opdracht uit:

   ```powershell
   Import-Module O365CompatibilityChecker
   ```

3. Voer de **opdracht Invoke-CompatabilityCheck** uit:

   ```powershell
   Invoke-CompatibilityCheck
   ```
   Met deze opdracht wordt u gevraagd  *_om TenantDomain_* (bijvoorbeeld *TailspinToysIncorporated.onmicrosoft. </span> com*) en  *_TenantAdmin-referenties_* (gebruik uw globale beheerdersreferenties) en vraagt vervolgens toestemming.

   > [!NOTE]
   > Afhankelijk van het aantal gebruikers in uw tenant, kan het afronden van de controle minuten of uren in beslag nemen.

Als het hulpprogramma is uitgevoerd, wordt een uitvoerbestand gegenereerd in een CSV-indeling (door komma's gescheiden). Het bestand wordt standaard **opgeslagen in C:\windows\system32.** Het uitvoerbestand bevat de volgende gegevens:

- Gebruikersnaam

- Gebruikers-id (e-mailadres van de gebruiker)

- Geschikt voor Gecentraliseerde implementatie (als de overige items waar zijn)

- Office plan - Het plan van Office waar ze een licentie voor hebben

- Office geactiveerd (als Office is geactiveerd)

- Ondersteund postvak (als er een OAuth-postvak wordt gebruikt)

> [!NOTE]
> Meervoudige verificatie wordt niet ondersteund wanneer u de PowerShell-module voor centrale implementatie gebruikt. De module werkt alleen met Basisverificatie.

## <a name="user-and-group-assignments"></a>Toewijzingen van gebruikers en groepen

De functie Gecentraliseerde implementatie ondersteunt momenteel de meeste groepen die door Azure Active Directory worden ondersteund, Microsoft 365 groepen, distributielijsten en beveiligingsgroepen.

> [!NOTE]
> Niet door e-mail ingeschakelde beveiligingsgroepen worden momenteel niet ondersteund.

Gecentraliseerde implementatie ondersteunt opdrachten aan afzonderlijke gebruikers, groepen en iedereen in de tenant. Gecentraliseerde implementatie ondersteunt gebruikers in groepen op het hoogste niveau of groepen zonder bovenliggende groepen, maar niet gebruikers in geneste groepen of groepen die bovenliggende groepen hebben.

Bekijk het volgende voorbeeld, waarin Femke, Assia en de groep Verkoopafdeling zijn toegewezen aan een invoegtoepassing. Omdat de afdeling Verkoop regio West een geneste groep is, zijn Jaap en Roelf niet toegewezen aan een invoegtoepassing.

![Diagram van verkoopafdeling](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)


### <a name="find-out-if-a-group-contains-nested-groups"></a>Controleren of een groep geneste groepen bevat

De gemakkelijkste manier om te controleren of een groep geneste groepen bevat, is het visitekaartje van de groep in Outlook te bekijken. Als u de naam  van de groep in het veld Aan van een e-mailbericht op typt en vervolgens de groepsnaam selecteert wanneer deze is opgelost, wordt in de groep de naam van de groep besleed als deze gebruikers of geneste groepen bevat. In het onderstaande voorbeeld toont het tabblad **Leden** van het Outlook-visitekaartje voor de Testgroep geen gebruikers en slechts twee subgroepen.

![Tabblad Leden van Outlook visitekaartje](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)

U kunt de tegenovergestelde query uitvoeren door de groep om te zetten om te zien of deze een lid van een groep is. In het onderstaande voorbeeld kunt u op het tabblad **Lidmaatschap** van het Outlook-visitekaartje zien dat Subgroep 1 een lid van de Testgroep is.

![Tabblad Lidmaatschap van het Outlook visitekaartje](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)

U kunt ook de Azure Active Directory Graph API gebruiken voor het uitvoeren van query's om de lijst met groepen in een groep te vinden. Zie [Bewerkingen op groepen | Graph API-verwijzing](/previous-versions/azure/ad/graph/api/groups-operations) voor meer informatie.

### <a name="contacting-microsoft-for-support"></a>Contact opnemen met Microsoft voor ondersteuning

Als u of uw gebruikers problemen ondervinden bij het laden van de invoegservice tijdens het gebruik van Office-apps voor het web (Word, Excel, enzovoort), die centraal zijn geïmplementeerd, moet u mogelijk contact opnemen met microsoft-ondersteuning[(meer](../../business-video/get-help-support.md)informatie). Geef de volgende informatie over uw Microsoft 365 in het ondersteuningsticket.

|**Platform**|**Foutopsporingsgegevens**|
|:-----|:-----|
|Office  <br/> | Charles/Fiddler-logboeken  <br/>  Tenant-id[(meer informatie)](/onedrive/find-your-office-365-tenant-id)  <br/>  CorrelationID. Bekijk de bron van een van de office-pagina's en zoek naar de waarde Correlatie-id en stuur deze naar ondersteuning:  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|Uitgebreide clients (Windows, Mac)  <br/> | Charles/Fiddler-logboeken  <br/>  Build numbers of the client app (preferably as a screenshot from **File/Account**)  <br/> |

## <a name="related-content"></a>Verwante inhoud

[Invoegvoegingen implementeren in het beheercentrum](../manage/manage-deployment-of-add-ins.md) (artikel)\
[Invoegvoegingen beheren in het beheercentrum](manage-addins-in-the-admin-center.md) (artikel)\
[Veelgestelde vragen over gecentraliseerde](../manage/centralized-deployment-faq.md) implementatie (artikel)\
[Uw Microsoft 365 voor zakelijke gebruikers upgraden naar de](../setup/upgrade-users-to-latest-office-client.md) nieuwste Office client (artikel)
 