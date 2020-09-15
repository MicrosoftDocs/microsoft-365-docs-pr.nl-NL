---
title: API voor update van incidenten
description: Informatie over het bijwerken van incidenten met Microsoft Threat Protection API
keywords: Update, API, incident
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: e790f4f415575323cfdd5fc15db41baa8b59c7f6
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650226"
---
# <a name="update-incidents-api"></a>API voor update van incidenten

**Van toepassing op:**
- Microsoft Threat Protection

>[!IMPORTANT] 
>Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd. Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.


## <a name="api-description"></a>API-beschrijving
Hiermee worden de eigenschappen van een bestaand incident bijgewerkt.
<br>Bijwerkbare eigenschappen zijn: ```status``` , ```determination``` , ```classification``` ```assignedTo``` en ```tags``` .


## <a name="limitations"></a>Beperkingen
1. Tarief beperkingen voor deze API zijn 50 oproepen per minuut en 1500-oproepen per uur.
2. U kunt instellen ```determination``` dat alleen als de classificatie is ingesteld op TruePositive.


## <a name="permissions"></a>Machtigingen
U moet een van de volgende machtigingen hebben om deze API te kunnen bellen. Voor meer informatie, waaronder de manier waarop u machtigingen kiest, raadpleegt u [de Api's Microsoft Threat Protection openen](api-access.md).

Type machtiging |   Machtigingsset  |   Weergavenaam van de machtiging
:---|:---|:---
Toepassing |   Incident. ReadWrite. all |    ' Alle incidenten lezen en schrijven '
Gedelegeerd (werk-of schoolaccount) | Incident. ReadWrite | ' Lees-en schrijf incident '

>[!NOTE]
> Bij het verkrijgen van een token met behulp van gebruikersreferenties:
>- De gebruiker moet zijn gemachtigd om het incident in de portal bij te werken.


## <a name="http-request"></a>HTTP-aanvraag

```
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a>Kopteksten aanvragen

Naam | Type | Beschrijving
:---|:---|:---
Bevoegdheid | Tekenreeks | Bearer {token}. **Vereist**.
Inhouds type | Tekenreeks | Application/JSON. **Vereist**.


## <a name="request-body"></a>Aanvraagtekst
Geef in de hoofdtekst van de aanvraag de waarden op voor de relevante velden die moeten worden bijgewerkt.
<br>Bestaande eigenschappen die niet zijn opgenomen in de aanvraagtekst, behouden hun vorige waarden of worden herberekend op basis van wijzigingen in andere eigenschapswaarden. 
<br>Voor de beste prestaties mag u geen bestaande waarden opnemen die niet zijn gewijzigd.

Eigenschap | Type | Beschrijving
:---|:---|:---
status | Opsommings | Geeft de huidige status van de waarschuwing op. Mogelijke waarden zijn: ```Active``` , ```Resolved``` en ```Redirected``` .
ToegewezenAan | tekenreeks | Eigenaar van het incident.
Contactpersoonclassificatie | Opsommings | Specificatie van de waarschuwing. Mogelijke waarden zijn: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .
relevant | Opsommings | Hiermee geeft u het bepalen van de waarschuwing op. Mogelijke waarden zijn: ```NotAvailable``` , ```Apt``` ,,, ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` , ```UnwantedSoftware``` , ```Other``` .
Tags | Lijst met tekenreeksen | Lijst met incident Tags.



## <a name="response"></a>Na
Als dit is gelukt, retourneert deze methode 200 OK en de entiteit van het incident in de tekst van het antwoord met de bijgewerkte eigenschappen. If incident met de opgegeven id niet gevonden-404 is niet gevonden.


## <a name="example"></a>Voorbeeld

**Webonderdeelverzoek**

Hier ziet u een voorbeeld van de aanvraag.

```
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```


## <a name="related-topic"></a>Verwante onderwerpen
- [Api's voor incidenten](api-incident.md)
- [Lijst incidenten](api-list-incidents.md)