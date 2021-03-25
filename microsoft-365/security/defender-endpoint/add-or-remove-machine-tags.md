---
title: API voor machinetags toevoegen of verwijderen
description: Lees hoe u de API voor machinelabels toevoegen of verwijderen kunt gebruiken om een tag voor een computer toe te voegen of te verwijderen in Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, tags, machinetags
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: 98dd513cc66683ff1b95f66d6d7b89916ce54bab
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199771"
---
# <a name="add-or-remove-machine-tags-api"></a>API voor machinetags toevoegen of verwijderen

**Van toepassing op:**

- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API-beschrijving

Hiermee voegt u tag toe aan een specifieke computer of verwijdert [u deze.](machine.md)

## <a name="limitations"></a>Beperkingen

1. U kunt posten op machines die het laatst zijn gezien op basis van de geconfigureerde bewaarperiode.

2. Tariefbeperkingen voor deze API zijn 100 oproepen per minuut en 1500 oproepen per uur.


## <a name="permissions"></a>Machtigingen

Een van de volgende machtigingen is vereist om deze API te bellen. Zie Defender voor [eindpunt-API's gebruiken](apis-intro.md) voor meer informatie, inclusief het kiezen van machtigingen.

Machtigingstype |    Machtiging    |    Weergavenaam machtiging
:---|:---|:---
Toepassing |    Machine.ReadWrite.All |    'Alle computergegevens lezen en schrijven'
Gedelegeerd (werk- of schoolaccount) | Machine.ReadWrite | 'Machinegegevens lezen en schrijven'

>[!Note]
> Bij het verkrijgen van een token met gebruikersreferenties:
>
>- De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Beveiligingsinstelling beheren'. Voor meer informatie (Zie [Rollen maken en beheren](user-roles.md) voor meer informatie)
>- Gebruiker moet toegang hebben tot de computer, op basis van instellingen voor de machinegroep (Zie [Machinegroepen](machine-groups.md) maken en beheren voor meer informatie)

## <a name="http-request"></a>HTTP-aanvraag

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/tags
```

## <a name="request-headers"></a>Kopteksten aanvragen

Naam | Type | Beschrijving
:---|:---|:---
Autorisatie | Tekenreeks | Bearer {token}. **Vereist**.
Inhoudstype | tekenreeks | toepassing/json. **Vereist**.

## <a name="request-body"></a>Body aanvragen

In de objectaanvraag moet u een JSON-object de volgende parameters geven:

Parameter |    Type    | Beschrijving
:---|:---|:---
Waarde |    Tekenreeks |    De naam van de tag. **Vereist**.
Actie    | Enum |    Toevoegen of verwijderen. Toegestane waarden zijn: 'Toevoegen' of 'Verwijderen'. **Vereist**.


## <a name="response"></a>Antwoord

Als dit is gelukt, retourneert deze methode 200 - Ok-antwoordcode en de bijgewerkte machine in de antwoord body.

## <a name="example"></a>Voorbeeld

**Aanvraag**

Hier is een voorbeeld van een aanvraag die een machinelabel toevoegt.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/tags
```

```json
{
  "Value" : "test Tag 2",
  "Action": "Add"
}
```

- Als u de machinetag wilt verwijderen, stelt u de actie in op 'Verwijderen' in plaats van 'Toevoegen' in de aanvraag.
