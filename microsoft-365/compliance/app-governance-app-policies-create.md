---
title: App-beleid maken
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: App-beleid maken.
ms.openlocfilehash: 66d8dda7c9cd768d6971e2b58dca4c9c5437e5bb
ms.sourcegitcommit: 2fd60871975d61e60d4827b36cd689021fd2a4c8
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53438058"
---
# <a name="create-app-policies"></a>App-beleid maken

>*[Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](https://aka.ms/ComplianceSD).*

Naast een ingebouwde set mogelijkheden om afwijkend app-gedrag te detecteren en waarschuwingen te genereren, geeft app-beleid in Microsoft app-governance u de volgende mogelijkheden:

- Geef voorwaarden op waarmee app-governance u kan waarschuwen voor app-gedrag voor automatisch of handmatig herstel.
- Beheer het beveiligings- en nalevingsbeleid voor uw organisatie.

U kunt app-beleid maken op basis van opgegeven sjablonen die kunnen worden aangepast of u kunt uw eigen aangepaste app-beleid maken.

Als u nieuw app-beleid wilt maken, gaat u naar **Microsoft 365-compliancecentrum > App-governance > Overzichtspagina > Beleidsregels**:

- Als u een nieuw app-beleid wilt maken met sjablonen die zijn ontworpen voor app-gebruik, selecteert u **Beleid maken** onder **Een app-gebruiksbeleid maken**.
- Als u een nieuw app-beleid wilt maken met sjablonen die zijn ontworpen voor app-machtigingen, selecteert u **Beleid maken** onder **Een machtigingsbeleid maken**.
- Als u een nieuw app-beleid wilt maken voor app-certificering of voor een aangepast beleid, selecteert u **Nieuwe maken**.

## <a name="app-policy-templates"></a>App-beleidssjablonen

Als u een nieuw app-beleid wilt maken op basis van een app-beleidssjabloon, selecteert u op de pagina **Sjabloon voor app-beleid kiezen** een categorie app-sjabloon, selecteert u de naam van de sjabloon en selecteert u vervolgens **Volgende**.

App-governance heeft drie categorieën app-beleidssjablonen.

### <a name="app-users-and-data-access"></a>App-gebruikers en gegevenstoegang

App-governance bevat deze sjablonen om waarschuwingen voor app-gebruik te genereren.

| Sjabloonnaam | Omschrijving |
|:-------|:-----|
| Nieuwe app met veel gegevenstoegang | Markeert alle recent geregistreerde apps met toegang tot grote hoeveelheden gegevens om ervoor te zorgen dat die gegevenspatronen worden verwacht. <br><br> Dit beleid markeert standaard alle apps die in de afgelopen zeven dagen zijn geregistreerd en die gedurende die periode meer dan 1 GB aan gegevenstoegang hebben gehad. Dit beleid kan met meer voorwaarden en acties worden aangepast. |
|||

### <a name="app-permissions"></a>App-machtigingen

App-beheer bevat deze sjablonen voor het genereren van waarschuwingen voor app-machtigingen.

| Sjabloonnaam | Omschrijving |
|:-------|:-----|
| Apps met te veel machtigingen | Markeert alle apps met meer verleende machtigingen dan die door die apps worden gebruikt om mogelijkheden voor mogelijke vermindering van machtigingen te identificeren. <br><br> Dit beleid markeert standaard alle apps die zijn gemarkeerd als Overprivileged als ze 90 dagen niet worden gebruikt. Dit tijdsperiodefilter kan worden aangepast met meer voorwaarden en acties. |
| Nieuwe app met machtigingen met hoge bevoegdheden | Markeert alle nieuwe apps met machtigingen met hoge bevoegdheden om potentiële apps met een grote footprint te identificeren die mogelijk nader moeten worden onderzocht. <br><br> Dit beleid markeert standaard alle apps die in de afgelopen zeven dagen zijn geregistreerd en die hoge machtigingen hebben. |
|||

### <a name="app-certification"></a>App-certificering

App-governance bevat deze sjablonen voor het genereren van waarschuwingen voor app-machtigingen.

| Sjabloonnaam | Omschrijving |
|:-------|:-----|
| Nieuwe niet-gecertificeerde app | Dit beleid markeert nieuwe apps die het app-certificeringsproces niet hebben doorlopen om ervoor te zorgen dat ze worden verwacht in de Tenant. <br><br> Standaard worden in dit beleid alle apps gemarkeerd die in de afgelopen zeven dagen zijn geregistreerd en die niet zijn gecertificeerd. |
|||

## <a name="custom-app-policies"></a>Aangepast app-beleid

Gebruik een aangepast app-beleid wanneer u iets moet doen dat nog niet door een van de ingebouwde sjablonen is uitgevoerd.

Als u een nieuw aangepast app-beleid wilt maken, selecteert u eerst **Nieuwe maken** op de pagina **Beleidsregels**. Selecteer op de **pagina Sjabloon voor app-beleid kiezen** de categorie **Aangepast**, de sjabloon **Aangepast beleid** en selecteer vervolgens **Volgende**.

Vul op de pagina **Naam en beschrijving** de volgende velden in:

- Beleidsnaam

- Beleidsbeschrijving

- Selecteer de ernst van het beleid, waarmee de ernst wordt ingesteld van waarschuwingen die door dit beleid worden gegenereerd.

  - Hoog
  - Gemiddeld
  - Laag

Selecteer op de pagina **Beleidsinstellingen en -voorwaarden kiezen** voor **Kies op welke apps dit beleid van toepassing is**:

- Alle apps
- Specifieke apps kiezen

  In een deelvenster kunt u een of meer apps selecteren.
  Kies **Toevoegen**.

Selecteer **Volgende**.

Selecteer op de pagina **Beleidsinstellingen en -voorwaarden kiezen** de optie **Nieuwe voorwaarden instellen voor** en selecteer vervolgens **Volgende**.

In het deelvenster **Regel maken** kunt u voorwaarden voor een nieuwe regel selecteren. Selecteer **Voorwaarde toevoegen**, selecteer in de lijst met voorwaarden en geef vervolgens de waarde van de voorwaarde op. U kunt meerdere voorwaarden toevoegen.

Hier zijn de beschikbare voorwaarden voor een aangepast app-beleid.

|Voorwaarde | Geaccepteerde voorwaarden | Meer informatie |
|:-------|:-----|:-------|
| Leeftijd van app-registratie | Binnen de afgelopen X dagen |  |
| App-certificering | Basisnaleving, MCAS-naleving of n.v.t. | [Microsoft 365-certificering](https://docs.microsoft.com/microsoft-365-app-certification/docs/enterprise-app-certification-guide) |
| Verificatie van uitgever | Ja of nee | [Verificatie van uitgever](https://docs.microsoft.com/azure/active-directory/develop/publisher-verification-overview) |
| Toepassingsmachtiging | Selecteer een of meer API-machtigingen in de lijst | [naslaginformatie over Microsoft Graph machtigingen](https://docs.microsoft.com/graph/permissions-reference) |
| Gedelegeerde machtiging | Selecteer een of meer API-machtigingen in de lijst | [naslaginformatie over Microsoft Graph machtigingen](https://docs.microsoft.com/graph/permissions-reference) |
| Hoge bevoegdheid | Ja of nee | Dit is een interne aanduiding op basis van dezelfde logica die door MCAS wordt gebruikt. |
| App met te veel machtigingen | Ja of nee | Apps met meer machtigingen dan door die apps worden gebruikt. |
| Toegang tot app-gegevens | Meer dan X GB gegevenstoegang per uur |  |
| Trend voor toegang tot app-gegevens | X% toename van het gegevensgebruik in de afgelopen zeven dagen |  |
| Toegang tot app-API | Groter dan X API-aanroepen per uur |  |
| Trend van API-toegang voor app | X% toename in API-aanroepen in de afgelopen zeven dagen     |  |
| Gebruikers die toestemming hebben verleend | (Groter dan of Kleiner dan) X gebruikers die toestemming hebben verleend |  |
| Gebruiker met prioriteit heeft toestemming verleend | Ja of nee | Een gebruiker met een [prioriteitsaccount](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts). |
| App-toestemming gegeven door | Gebruiker(s) selecteren in lijst |  |
| De rol van de gebruiker die toestemming geeft | Selecteer een of meer opties: Teams-beheerder, adreslijstlezer, beveiligingslezer, nalevingsbeheerder, beveiligingsbeheerder, helpdeskbeheerder, SharePoint-beheerder, Exchange-beheerder, globale lezer, globale beheerder, beheerder van nalevingsgegevens, gebruikersbeheerder, serviceondersteuningsbeheerder | Meerdere selecties toegestaan. <br><br> Elke Azure AD-rol met toegewezen lid moet beschikbaar worden gemaakt in deze lijst. |
| Werkbelasting geopend | OneDrive en/of SharePoint en/of Exchange | Meerdere selecties toegestaan. |
| Foutpercentage | Foutpercentage is in de afgelopen zeven dagen groter dan X%, waarbij X een door de beheerder gedefinieerde waarde is |  |
||||

<!--
NOTE TO WRITER: Replace X in the above table with correct values.
-->

Aan alle opgegeven voorwaarden moet worden voldaan om dit app-beleid van toepassing te laten zijn.

Wanneer u klaar bent met het opgeven van de voorwaarden, selecteert u **Opslaan** en selecteert u vervolgens **Volgende**.

Selecteer op de pagina **Beleidsacties definiëren** de optie **App uitschakelen** als u wilt dat app-governance de app uitschakelt wanneer een waarschuwing op basis van dit beleid wordt gegenereerd, en selecteer vervolgens **Volgende**.

Selecteer op de pagina **Beleidsstatus definiëren** een van de volgende opties:

- **Auditmodus**: beleidsregels worden geëvalueerd, maar geconfigureerde acties worden niet uitgevoerd. De beleidsregels voor de auditmodus worden weergegeven met de status **Audit** in de lijst met beleidsregels.
- **Actief**: beleidsregels worden geëvalueerd en geconfigureerde acties worden uitgevoerd.
- **Inactief**: beleidsregels worden niet geëvalueerd en geconfigureerde acties worden niet uitgevoerd.

<!--
## Configure a user-based policy

## Create an app metadata-based policy

Publish metadata-based policies

## Configure access permissions
-->

## <a name="test-and-monitor-your-new-app-policy"></a>Uw nieuwe app-beleid testen en bewaken

Nu uw app-beleid is gemaakt, moet u het controleren op de pagina **Beleid** om ervoor te zorgen dat het een verwacht aantal actieve waarschuwingen en het totale aantal waarschuwingen registreert tijdens het testen. 

![De overzichtspagina van MAPG-beleidsregels in het Microsoft 365-compliancecentrum met een gemarkeerd beleid](..\media\manage-app-protection-governance\mapg-cc-policies-policy.png)

Als het aantal waarschuwingen een onverwacht lage waarde heeft, bewerkt u de instellingen van het app-beleid om ervoor te zorgen dat u deze correct hebt geconfigureerd voordat u de status instelt.

Hier is een voorbeeld van een proces om een nieuw beleid te maken, het te testen en vervolgens te activeren:

1. Maak het nieuwe beleid met de ernst, apps, voorwaarden en acties ingesteld op beginwaarden en de status ingesteld op **Auditmodus**.
2. Controleer op verwacht gedrag, zoals gegenereerde waarschuwingen.
3. Als het gedrag niet wordt verwacht, bewerkt u indien nodig de beleidsapps, voorwaarden en actie-instellingen en gaat u terug naar stap 2.
4. Als het gedrag wordt verwacht, bewerkt u het beleid en wijzigt u de status ervan in **Actief**.

![De werkstroom voor het maken van app-beleid](../media/manage-app-protection-governance/mapg-create-new-policy-process.png)

## <a name="next-step"></a>Volgende stap

[Uw app-beleid beheren.](app-governance-app-policies-manage.md)
