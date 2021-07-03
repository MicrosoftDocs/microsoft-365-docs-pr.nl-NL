---
title: Beleid voor informatiebelemmering definiëren
description: Meer informatie over het definiëren van beleidsregels voor informatiebarrières in Microsoft Teams.
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: eec4869c5ff0b4caeedc52891a56d604c4b54348
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286031"
---
# <a name="define-information-barrier-policies"></a>Beleid voor informatiebelemmering definiëren

Met informatiebarrières kunt u beleidsregels definiëren die zijn ontworpen om te voorkomen dat bepaalde segmenten van gebruikers met elkaar communiceren of specifieke segmenten toestaan alleen met bepaalde andere segmenten te communiceren. Informatiebarrièrebeleid kan uw organisatie helpen de naleving van relevante industriestandaarden en -voorschriften te handhaven en mogelijke conflicten te voorkomen. Zie Informatiebarrières voor [meer informatie.](information-barriers.md)

In dit artikel wordt beschreven hoe u beleidsregels voor informatiebarrières kunt plannen, definiëren, implementeren en beheren. Er zijn verschillende stappen betrokken en de werkstroom is onderverdeeld in verschillende onderdelen. Lees de vereisten [](#prerequisites) en het hele proces door voordat u beleidsregels voor informatiebarrière gaat definiëren (of bewerken).

> [!TIP]
> Dit artikel bevat een [voorbeeldscenario](#example-contosos-departments-segments-and-policies) en een downloadbare [Excel werkmap](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx) om u te helpen bij het plannen en definiëren van uw beleid voor informatiebarrière.

## <a name="concepts-of-information-barrier-policies"></a>Concepten van beleidsregels voor informatiebarrières

Wanneer u beleid voor informatiebarrières definieert, werkt u met gebruikersaccountkenmerken, segmenten, 'blokkeren' en/of 'toestaan'-beleid en beleidstoepassing.

- Gebruikersaccountkenmerken worden gedefinieerd in Azure Active Directory (of Exchange Online). Deze kenmerken kunnen afdeling, functie, locatie, teamnaam en andere functieprofielgegevens bevatten. 
- Segmenten zijn sets gebruikers die zijn gedefinieerd in het beveiligings- & compliancecentrum met een geselecteerd **gebruikersaccountkenmerk.** (Zie de [lijst met ondersteunde kenmerken](information-barriers-attributes.md).)
- Beleidsregels voor informatiebarrière bepalen communicatielimieten of -beperkingen. Wanneer u beleidsregels voor informatiebarrières definieert, kiest u uit twee soorten beleid:
  - 'Blokkeringsbeleid' voorkomt dat het ene segment met een ander segment communiceert.
  - Met 'Toestaan'-beleid kan één segment alleen met bepaalde andere segmenten communiceren.
- Beleidstoepassing wordt uitgevoerd nadat alle beleidsregels voor informatiebarrière zijn gedefinieerd en u klaar bent om deze toe te passen in uw organisatie.

## <a name="the-work-flow-at-a-glance"></a>De werkstroom in één oogopslag

| Fase | Wat is er bij betrokken? |
|:--------|:------------------|
| [Zorg ervoor dat aan de vereisten wordt voldaan](#prerequisites) | - Controleer of u de vereiste [licenties en machtigingen hebt](information-barriers.md#required-licenses-and-permissions)<br/>- Controleer of uw adreslijst gegevens bevat voor het segmenteren van gebruikers<br/>- Zoek naar adressenlijst met bereik inschakelen voor Microsoft Teams<br/>- Controleer of auditregistratie is ingeschakeld<br/>- Zorg ervoor dat er Exchange adresboekbeleid is<br/>- PowerShell gebruiken (voorbeelden zijn beschikbaar)<br/>- Beheerder toestemming geven voor Microsoft Teams (stappen zijn inbegrepen) |
| [Deel 1: Gebruikers segmenteren in uw organisatie](#part-1-segment-users) | - Bepalen welke beleidsregels nodig zijn<br/>- Een lijst maken met segmenten die u wilt definiëren<br/>- Bepalen welke kenmerken moeten worden gebruikt<br/>- Segmenten definiëren in termen van beleidsfilters |
| [Deel 2: Beleid voor informatiebarrière definiëren](#part-2-define-information-barrier-policies) | - Uw beleid definiëren (nog niet van toepassing)<br/>- Kies uit twee soorten (blokkeren of toestaan) |
| [Deel 3: Beleidsregels voor informatiebarrière toepassen](#part-3-apply-information-barrier-policies) | - Beleid instellen op actieve status<br/>- De beleidstoepassing uitvoeren<br/>- Beleidsstatus weergeven |
| (Indien nodig) [Een segment of beleid bewerken](information-barriers-edit-segments-policies.md) | - Een segment bewerken<br/>- Een beleid bewerken of verwijderen<br/>- De beleidstoepassing opnieuw gebruiken<br/>- Beleidsstatus weergeven |
| (Indien nodig) [Problemen oplossen](information-barriers-troubleshooting.md)| - Actie ondernemen als dingen niet werken zoals verwacht|

## <a name="prerequisites"></a>Vereisten

Zorg er naast [de vereiste licenties en machtigingen](information-barriers.md#required-licenses-and-permissions)voor dat aan de volgende vereisten wordt voldaan:

- Adreslijstgegevens: zorg ervoor dat de structuur van uw organisatie wordt weerspiegeld in adreslijstgegevens. Als u deze actie wilt ondernemen, moet u ervoor zorgen dat gebruikersaccountkenmerken, zoals groepslidmaatschap, afdelingsnaam, enzovoort, correct worden ingevuld in Azure Active Directory (of Exchange Online). Zie de volgende bronnen voor meer informatie:
  - [Kenmerken voor het beleid voor informatiebelemmering](information-barriers-attributes.md)
  - [Profielgegevens van een gebruiker toevoegen of bijwerken met Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)
  - [Eigenschappen van gebruikersaccounts configureren met Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)

- Zoeken in adreslijst met bereik: voordat u het eerste beleid voor de informatiebarrière van uw organisatie definieert, moet u zoeken met een bereik [inschakelen in Microsoft Teams.](/MicrosoftTeams/teams-scoped-directory-search) Wacht ten minste 24 uur na het inschakelen van zoekactie met een bereik voordat u beleidsregels voor informatiebarrière in- of definieert.

- EXO-licentie : IB-beleid werkt alleen als aan de doelgebruikers een EXO-licentie is toegewezen.

- Auditregistratie: om de status van een beleidstoepassing op te zoeken, moet auditregistratie zijn ingeschakeld. U wordt aangeraden de controle in te stellen voordat u segmenten of beleidsregels gaat definiëren. Zie Zoeken in het [auditlogboek in- of uitschakelen voor meer informatie.](turn-audit-log-search-on-or-off.md)

- Geen adresboekbeleid: voordat u beleidsregels voor informatiebarrières definieert en toe te passen, moet Exchange adresboekbeleid zijn toegepast. Informatiebarrières zijn gebaseerd op adresboekbeleid, maar de twee soorten beleidsregels zijn niet compatibel. Als u dergelijke beleidsregels hebt, moet u eerst [uw adresboekbeleid verwijderen.](/exchange/address-books/address-book-policies/remove-an-address-book-policy) Wanneer beleidsregels voor informatiebarrière zijn ingeschakeld en u een hiërarchisch adresboek hebt ingeschakeld, zien alle gebruikers die niet zijn opgenomen ***in*** een informatiebarrièresegment het hiërarchische adresboek [in](/exchange/address-books/hierarchical-address-books/hierarchical-address-books) Exchange online.

- PowerShell: op dit moment worden beleidsregels voor informatiebarrières gedefinieerd en beheerd in het Office 365 Beveiligingscentrum & PowerShell-cmdlets. Hoewel in dit artikel verschillende voorbeelden worden gegeven, moet u bekend zijn met PowerShell-cmdlets en -parameters. U hebt ook de module Azure PowerShell nodig.
  - [Verbinding maken met Beveiligings- en compliancecentrum van Powershell](/powershell/exchange/connect-to-scc-powershell)
  - [De module Azure PowerShell installeren](/powershell/azure/install-az-ps)

- Toestemming van beheerder voor informatiebarrières in Microsoft Teams: wanneer uw IB-beleid van de hand is, kunnen niet-IB-compliancegebruikers worden verwijderd uit groepen (dat wil zeggen Teams-kanalen, die zijn gebaseerd op groepen). Met deze configuratie kunt u ervoor zorgen dat uw organisatie voldoet aan beleidsregels en voorschriften. Gebruik de volgende procedure om het beleid voor informatiebarrières te laten werken zoals verwacht in Microsoft Teams.

   1. Voorwaarde: Installatie Azure PowerShell installatie van [Azure PowerShell.](/powershell/azure/install-az-ps)

   1. Voer de volgende PowerShell-cmdlets uit:

      ```powershell
      Connect-AzAccount -Tenant "<yourtenantdomain.com>"  //for example: Connect-AzAccount -Tenant "Contoso.onmicrosoft.com"
      $appId="bcf62038-e005-436d-b970-2a472f8c1982" 
      $sp=Get-AzADServicePrincipal -ServicePrincipalName $appId
      if ($sp -eq $null) { New-AzADServicePrincipal -ApplicationId $appId }
      Start-Process  "https://login.microsoftonline.com/common/adminconsent?client_id=$appId"
      ```

   1. Meld u aan met uw werk- of schoolaccount als u daarom wordt gevraagd Office 365.

   1. Controleer de **gegevens** in het dialoogvenster Aangevraagde machtigingen en kies **accepteren.** De machtigingen die door de App zijn aangevraagd, worden hieronder weergegeven.

      > [!div class="mx-imgBorder"]
      > ![afbeelding](https://user-images.githubusercontent.com/8932063/107690955-b1772300-6c5f-11eb-9527-4235de860b27.png)

Wanneer aan alle vereisten is voldaan, gaat u verder met de volgende sectie.

> [!TIP]
> Om u te helpen bij het voorbereiden van uw plan, wordt een voorbeeldscenario opgenomen in dit artikel. [Zie De afdelingen, segmenten](#example-contosos-departments-segments-and-policies)en beleidsregels van Contoso.<p>Daarnaast is er een downloadbare Excel beschikbaar om u te helpen uw segmenten en beleidsregels te plannen en te definiëren (en uw PowerShell-cmdlets te maken). [De werkmap downloaden.](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx)

## <a name="part-1-segment-users"></a>Deel 1: Gebruikers segmenteren

In deze fase bepaalt u welk beleid voor informatiebarrières nodig is, maakt u een lijst met segmenten die u wilt definiëren en definieert u vervolgens uw segmenten.

### <a name="determine-what-policies-are-needed"></a>Bepalen welke beleidsregels nodig zijn

Overweegt u wettelijke en branchevoorschriften, wie zijn de groepen binnen uw organisatie die beleid voor informatiebarrière nodig hebben? Maak een lijst. Zijn er groepen die niet met een andere groep mogen communiceren? Zijn er groepen die alleen mogen communiceren met een of twee andere groepen? Denk na over het beleid dat u nodig hebt als lid van een van de twee groepen:

- 'Blokkeringsbeleid' voorkomt dat de ene groep met een andere groep communiceert.
- Met 'Toestaan'-beleid kan een groep alleen communiceren met bepaalde andere, specifieke groepen.

Wanneer u de eerste lijst met groepen en beleidsregels hebt, gaat u verder met het identificeren van de segmenten die u nodig hebt.

### <a name="identify-segments"></a>Segmenten identificeren

Maak naast de eerste lijst met beleidsregels een lijst met segmenten voor uw organisatie. Gebruikers die worden opgenomen in beleidsregels voor informatiebarrières, moeten deel uitmaken van een segment. Plan uw segmenten zorgvuldig als een gebruiker slechts in één segment kan zijn. Voor elk segment kan slechts één beleid voor informatiebarrière worden toegepast.

> [!IMPORTANT]
> Een gebruiker kan slechts in één segment zijn.

Bepaal welke kenmerken in de adreslijstgegevens van uw organisatie u gebruikt om segmenten te definiëren. U kunt *Afdeling,* *LidVan* of een van de ondersteunde kenmerken gebruiken. Zorg ervoor dat u waarden hebt in het kenmerk dat u selecteert voor gebruikers. [Zie de lijst met ondersteunde kenmerken voor informatiebarrières.](information-barriers-attributes.md)

> [!IMPORTANT]
> **Voordat u naar de volgende sectie gaat, moet** u ervoor zorgen dat uw adreslijstgegevens waarden bevatten voor kenmerken die u kunt gebruiken om segmenten te definiëren. Als uw adreslijstgegevens geen waarden hebben voor de kenmerken die u wilt gebruiken, moeten de gebruikersaccounts worden bijgewerkt om deze gegevens op te nemen voordat u verdergaat met informatiebarrières. Zie de volgende bronnen voor hulp bij dit artikel:<br/>- [Eigenschappen van gebruikersaccounts configureren met Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)<br/>- [Profielgegevens van een gebruiker toevoegen of bijwerken met Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

### <a name="define-segments-using-powershell"></a>Segmenten definiëren met PowerShell

Het definiëren van segmenten heeft geen invloed op gebruikers. Hiermee wordt alleen het stadium voor het definiëren en vervolgens toepassen van beleidsregels voor informatiebarrières bepaald.

1. Gebruik de **cmdlet New-OrganizationSegment** met de parameter **UserGroupFilter** die overeenkomt met het [kenmerk](information-barriers-attributes.md) dat u wilt gebruiken.

    | Syntaxis | Voorbeeld |
    |:---------|:----------|
    | `New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"` |`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` <p>In dit voorbeeld wordt een segment met de naam *HR* gedefinieerd met *HR*, een waarde in het *kenmerk Afdeling.* Het **-eq-gedeelte** van de cmdlet verwijst naar 'gelijk'. (U kunt ook **-ne** gebruiken om 'niet gelijk aan' te betekenen. Zie ['gelijken' en 'niet gelijk' gebruiken in segmentdefinities](#using-equals-and-not-equals-in-segment-definitions).) |

    Nadat u elke cmdlet hebt uitgevoerd, ziet u een lijst met details over het nieuwe segment. Details zijn het type segment, wie het segment heeft gemaakt of het laatst heeft gewijzigd, en ga zo maar door. 

2. Herhaal dit proces voor elk segment dat u wilt definiëren.

    > [!IMPORTANT]
    > **Zorg ervoor dat de segmenten elkaar niet overlappen.** Elke gebruiker die wordt beïnvloed door informatiebarrières, moet deel uitmaken van één (en slechts één) segment. Geen gebruiker mag tot twee of meer segmenten behoren. (Zie [Voorbeeld: de gedefinieerde segmenten van Contoso](#contosos-defined-segments) in dit artikel.)

Nadat u de segmenten hebt gedefinieerd, gaat u verder met [het definiëren van beleidsregels voor informatiebarrières.](#part-2-define-information-barrier-policies)

### <a name="using-equals-and-not-equals-in-segment-definitions"></a>Het gebruik van 'gelijken' en 'niet gelijk' in segmentdefinities

In het volgende voorbeeld definiëren we een segment zodanig dat 'Afdeling gelijk is aan HR'. 

| Voorbeeld | Opmerking |
|:----------|:-------|
|`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` | In dit voorbeeld bevat de segmentdefinitie een parameter 'gelijk' die wordt aangeduid als **-eq.** |

U kunt segmenten ook definiëren met een parameter 'niet gelijk aan', aangeduid als **-ne,** zoals wordt weergegeven in de volgende tabel:

| Syntaxis | Voorbeeld |
|:---------|:----------|
| `New-OrganizationSegment -Name "NotSales" -UserGroupFilter "Department -ne 'Sales'"` | In dit voorbeeld hebben we een segment met de naam *NotSales* gedefinieerd dat iedereen omvat die niet in *Verkoop staat.* Het **ne-gedeelte** van de cmdlet verwijst naar 'not equals'. |

Naast het definiëren van segmenten met 'gelijken' of 'niet gelijk aan', kunt u een segment definiëren met zowel 'gelijk' als 'niet gelijk aan'-parameters. U kunt ook complexe groepsfilters definiëren met behulp van logische *EN-* *en OF-operatoren.*

| Syntaxis | Voorbeeld |
|:---------|:----------|
| `New-OrganizationSegment -Name "LocalFTE" -UserGroupFilter "Location -eq 'Local'" -and "Position -ne 'Temporary'"` | In dit voorbeeld hebben we een segment met de naam *LocalFTE* gedefinieerd met personen die zich lokaal bevinden en waarvan de posities niet als Tijdelijk worden *vermeld.* |
| `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "MemberOf -eq 'group1@contoso.com'' -and MemberOf -ne 'group3@contoso.com'"`| In dit voorbeeld hebben we een segment met de naam *Segment1* gedefinieerd dat personen bevat die lid zijn van group1@contoso.com en niet lid zijn van group3@contoso.com. |
| `New-OrganizationSegment -Name "Segment2" -UserGroupFilter "MemberOf -eq 'group2@contoso.com' -or MemberOf -ne 'group3@contoso.com'"` | In dit voorbeeld hebben we een segment gedefinieerd met de naam *Segment2,* dat personen bevat die lid zijn van group2@contoso.com en niet lid zijn van group3@contoso.com. |
| `New-OrganizationSegment -Name "Segment1and2" -UserGroupFilter "(MemberOf -eq 'group1@contoso.com' -or MemberOf -eq 'group2@contoso.com') -and MemberOf -ne 'group3@contoso.com'"`| In dit voorbeeld hebben we een segment met de naam *Segment1and2* gedefinieerd met personen die lid zijn van group1@contoso.com en group2@contoso.com en niet leden van group3@contoso.com. |

> [!TIP]
> Gebruik indien mogelijk segmentdefinities die '-eq' of '-ne' bevatten. Probeer geen complexe segmentdefinities te definiëren.

## <a name="part-2-define-information-barrier-policies"></a>Deel 2: Beleid voor informatiebarrière definiëren

Bepaal of u communicatie tussen bepaalde segmenten moet voorkomen of dat u de communicatie tot bepaalde segmenten wilt beperken. In het ideale kader gebruikt u het minimum aantal beleidsregels om ervoor te zorgen dat uw organisatie voldoet aan wettelijke en branchevereisten.

Met uw lijst met gebruikerssegmenten en het beleid voor informatiebarrière dat u wilt definiëren, selecteert u een scenario en volgt u de stappen.

- [Scenario 1: Communicatie tussen segmenten blokkeren](#scenario-1-block-communications-between-segments)
- [Scenario 2: Toestaan dat een segment slechts met één ander segment communiceert](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)

> [!IMPORTANT]
> **Zorg ervoor dat wanneer u beleid definieert, u** niet meer dan één beleid aan een segment toewijst. Als u bijvoorbeeld één beleid definieert voor een segment met de naam *Verkoop,* definieert u geen extra beleid voor *Verkoop.*<p> Terwijl u beleidsregels voor informatiebarrières definieert, moet u deze beleidsregels bovendien instellen op inactieve status totdat u ze wilt toepassen. Het definiëren (of bewerken van) beleid heeft geen invloed op gebruikers totdat deze beleidsregels zijn ingesteld op actieve status en vervolgens worden toegepast.

(Zie [Voorbeeld: Het informatiebarrièrebeleid van Contoso](#contosos-information-barrier-policies) in dit artikel.)

### <a name="scenario-1-block-communications-between-segments"></a>Scenario 1: Communicatie tussen segmenten blokkeren

Wanneer u wilt blokkeren dat segmenten met elkaar communiceren, definieert u twee beleidsregels: één voor elke richting. Elk beleid blokkeert communicatie op één manier.

Stel dat u de communicatie tussen segment A en segment B wilt blokkeren. In dit geval definieert u één beleid dat verhindert dat segment A communiceert met segment B en definieert u vervolgens een tweede beleid om te voorkomen dat segment B communiceert met segment A.

1. Als u het eerste blokkeringsbeleid wilt definiëren, gebruikt u de cmdlet **New-InformationBarrierPolicy** met de parameter **Segmenten geblokkeerd.**

    | Syntaxis | Voorbeeld |
    |:--------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsBlocked "segment2name"` | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> In dit voorbeeld hebben we een beleid met de naam *Sales-Research gedefinieerd* voor een segment met de naam *Verkoop.* Wanneer dit beleid actief en toegepast is, voorkomt u dat personen in *Sales* communiceren met personen in een segment met de naam *Onderzoek.* |

2. Als u het tweede blokkeringssegment wilt definiëren, gebruikt u de cmdlet **New-InformationBarrierPolicy** opnieuw met de parameter **Segmenten** geblokkeerd, ditmaal met de segmenten omgekeerd.

    | Voorbeeld | Opmerking |
    |:----------|:-------|
    |`New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` | In dit voorbeeld hebben we een beleid met de naam *Research-Sales gedefinieerd om* te *voorkomen* dat onderzoek communiceert met *Verkoop.* |

3. Ga naar een van de volgende acties:

   - (Indien nodig) [Een beleid definiëren om een segment toe te](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment) staan alleen met één ander segment te communiceren 
   - (Nadat al uw beleidsregels zijn gedefinieerd) [Beleidsregels voor informatiebarrière toepassen](#part-3-apply-information-barrier-policies)

### <a name="scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment"></a>Scenario 2: Toestaan dat een segment slechts met één ander segment communiceert

1. Als u wilt toestaan dat één segment met slechts één ander segment kan communiceren, gebruikt u de cmdlet **New-InformationBarrierPolicy** met de parameter **SegmentsAllowed.**

    | Syntaxis | Voorbeeld |
    |:----------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name","segment1name"` | `New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Manufacturing" -State Inactive` <p> In dit voorbeeld hebben we een beleid met de naam *Manufacturing-HR* gedefinieerd voor een segment genaamd *Manufacturing*. Wanneer dit beleid actief en toegepast is, kunnen personen in *productie alleen* communiceren met personen in een segment met de naam *HR.* (In dit geval kan *Manufacturing* niet communiceren met gebruikers die geen deel uitmaken van *HR*.) |

    **U kunt indien nodig meerdere segmenten opgeven met deze cmdlet, zoals wordt weergegeven in het volgende voorbeeld.**

    | Syntaxis | Voorbeeld |
    |:---------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name", "segment3name","segment1name"` | `New-InformationBarrierPolicy -Name "Research-HRManufacturing" -AssignedSegment "Research" -SegmentsAllowed "HR","Manufacturing","Research" -State Inactive` <p> In dit voorbeeld hebben we een beleid gedefinieerd waarmee het segment *Onderzoek* kan communiceren met alleen *HR* en *Productie*. |

    Herhaal deze stap voor elk beleid dat u wilt definiëren, zodat specifieke segmenten alleen met bepaalde specifieke segmenten kunnen communiceren.

2. Ga naar een van de volgende acties:

   - (Indien nodig) [Een beleid definiëren om communicatie tussen segmenten te blokkeren](#scenario-1-block-communications-between-segments) 
   - (Nadat al uw beleidsregels zijn gedefinieerd) [Beleidsregels voor informatiebarrière toepassen](#part-3-apply-information-barrier-policies)

## <a name="part-3-apply-information-barrier-policies"></a>Deel 3: Beleidsregels voor informatiebarrière toepassen

Beleidsregels voor informatiebarrières zijn pas van kracht als u ze hebt ingesteld op actieve status en vervolgens het beleid toepassen.

1. Gebruik de **cmdlet Get-InformationBarrierPolicy** om een lijst met beleidsregels weer te geven die zijn gedefinieerd. Noteer de status en identiteit (GUID) van elk beleid.

    Syntaxis: `Get-InformationBarrierPolicy`

2. Als u een beleid wilt instellen op actieve status, gebruikt u de cmdlet **Set-InformationBarrierPolicy** met een parameter **Identity** en de parameter **State** ingesteld op **Actief**. 

    | Syntaxis | Voorbeeld |
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Active` | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active` <p> In dit voorbeeld stellen we een informatiebarrièrebeleid in met de GUID *43c37853-ea10-4b90-a23d-ab8c93772471* op actieve status. |

    Herhaal deze stap zo nodig voor elk beleid.

3. Wanneer u klaar bent met het instellen van uw beleid voor informatiebarrière op actieve status, gebruikt u de **cmdlet Start-InformationBarrierPoliciesApplication** in het Beveiligings- & Compliancecentrum.

    Syntaxis: `Start-InformationBarrierPoliciesApplication`

    Nadat u het systeem hebt uitgevoerd, kunt u 30 minuten toestaan dat het beleid `Start-InformationBarrierPoliciesApplication` wordt toegepast. Het systeem past beleidsregels per gebruiker toe. Het systeem verwerkt ongeveer 5.000 gebruikersaccounts per uur.

## <a name="view-status-of-user-accounts-segments-policies-or-policy-application"></a>Status van gebruikersaccounts, segmenten, beleidsregels of beleidstoepassing weergeven

Met PowerShell kunt u de status van gebruikersaccounts, segmenten, beleidsregels en beleidstoepassing weergeven, zoals vermeld in de volgende tabel.

| Deze informatie weergeven | Deze actie ondernemen |
|:---------------|:----------|
| Gebruikersaccounts | Gebruik de **cmdlet Get-InformationBarrierRecipientStatus** met identiteitsparameters. <p> Syntaxis: `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> U kunt elke waarde gebruiken die elke gebruiker uniek identificeert, zoals naam, alias, voornaam, canonieke domeinnaam, e-mailadres of GUID. <p> Voorbeeld: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> In dit voorbeeld verwijzen we naar twee gebruikersaccounts in Office 365: *meganb* voor *Megan* en *alexw* voor *Alex*. <p> (U kunt deze cmdlet ook voor één gebruiker gebruiken: `Get-InformationBarrierRecipientStatus -Identity <value>` ) <p> Deze cmdlet retourneert informatie over gebruikers, zoals kenmerkwaarden en beleidsregels voor informatiebarrière die worden toegepast.|
| Segmenten | Gebruik de **cmdlet Get-OrganizationSegment.**<p> Syntaxis: `Get-OrganizationSegment` <p> In deze cmdlet wordt een lijst weergegeven met alle segmenten die voor uw organisatie zijn gedefinieerd. |
| Beleid voor informatiebarrière | Gebruik de **cmdlet Get-InformationBarrierPolicy.** <p> Syntaxis: `Get-InformationBarrierPolicy` <p> Deze cmdlet toont een lijst met beleidsregels voor informatiebarrière die zijn gedefinieerd en de status. |
| De meest recente toepassing van het informatiebarrièrebeleid | Gebruik de **cmdlet Get-InformationBarrierPoliciesApplicationStatus.** <p> Syntaxis: `Get-InformationBarrierPoliciesApplicationStatus`<p> In deze cmdlet wordt informatie weergegeven over of de beleidstoepassing is voltooid, mislukt of wordt uitgevoerd. |
| Alle beleidstoepassingen voor informatiebarrière|Gebruik `Get-InformationBarrierPoliciesApplicationStatus -All`<p> In deze cmdlet wordt informatie weergegeven over of de beleidstoepassing is voltooid, mislukt of wordt uitgevoerd.|

<!-- IN the " The most recent information barrier policy application, add link to troubleshooting topic -->

## <a name="what-if-i-need-to-remove-or-change-policies"></a>Wat moet ik doen als ik beleid moet verwijderen of wijzigen?

Er zijn bronnen beschikbaar om u te helpen bij het beheren van uw beleid voor informatiebarrière.

- Zie Problemen met informatiebarrières oplossen als er iets misgaat met [informatiebarrières.](information-barriers-troubleshooting.md)
- Zie Een beleidstoepassing stoppen om te voorkomen dat beleid [wordt toegepast.](information-barriers-edit-segments-policies.md#stop-a-policy-application)
- Zie Een beleid verwijderen als u een beleid voor [informatiebarrières wilt verwijderen.](information-barriers-edit-segments-policies.md#remove-a-policy)
- Zie Beleidsregels voor informatiebarrières bewerken [(of verwijderen)](information-barriers-edit-segments-policies.md)als u wijzigingen wilt aanbrengen in segmenten of beleidsregels.

## <a name="example-contosos-departments-segments-and-policies"></a>Voorbeeld: De afdelingen, segmenten en beleidsregels van Contoso

Als u wilt zien hoe een organisatie segmenten en beleidsregels kan definiëren, bekijkt u het volgende voorbeeld.

### <a name="contosos-departments-and-plan"></a>De afdelingen en het plan van Contoso

Contoso heeft vijf afdelingen: HR, Sales, Marketing, Research en Manufacturing. Om aan de branchevoorschriften te voldoen, mogen personen op sommige afdelingen niet communiceren met andere afdelingen, zoals vermeld in de volgende tabel:

| Segment | Kan praten met | Kan niet praten met |
|:----------|:--------------|:-----------------|
| HR | Iedereen | (geen beperkingen) |
| Verkoop | HR, Marketing, Productie | Onderzoek |
| Marketing | Iedereen | (geen beperkingen) |
| Onderzoek | HR, Marketing, Productie | Verkoop |
| Productie | HR, Marketing | Iedereen anders dan HR of Marketing |

Voor deze structuur bevat het plan van Contoso drie beleidsregels voor informatiebarrière:

1. Een beleid dat is ontworpen om te voorkomen dat Verkoop communiceert met Onderzoek (en een ander beleid om te voorkomen dat onderzoek communiceert met Verkoop).

2. Een beleid dat is ontworpen om productie alleen te laten communiceren met HR en Marketing.

In dit scenario hoeft u geen beleid voor HR of Marketing te definiëren.

### <a name="contosos-defined-segments"></a>Gedefinieerde segmenten van Contoso

Contoso gebruikt het kenmerk Afdeling in Azure Active Directory om segmenten als volgt te definiëren:

| Department | Segmentdefinitie |
|:-------------|:---------------------|
| HR | `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` |
| Verkoop | `New-OrganizationSegment -Name "Sales" -UserGroupFilter "Department -eq 'Sales'"` |
| Marketing | `New-OrganizationSegment -Name "Marketing" -UserGroupFilter "Department -eq 'Marketing'"` |
| Onderzoek | `New-OrganizationSegment -Name "Research" -UserGroupFilter "Department -eq 'Research'"` |
| Productie | `New-OrganizationSegment -Name "Manufacturing" -UserGroupFilter "Department -eq 'Manufacturing'"` |

Als de segmenten zijn gedefinieerd, gaat Contoso verder met het definiëren van beleid.

### <a name="contosos-information-barrier-policies"></a>Het beleid voor informatiebarrière van Contoso

Contoso definieert drie beleidsregels, zoals beschreven in de volgende tabel:

| Beleid | Beleidsdefinitie |
|:---------|:--------------------|
| **Beleid 1: Voorkomen dat verkoop communiceert met onderzoek** | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> In dit voorbeeld wordt het beleid voor de informatiebarrière *Verkoop-onderzoek genoemd.* Wanneer dit beleid actief en toegepast is, voorkomt u dat gebruikers in het segment Verkoop communiceren met gebruikers in het segment Onderzoek. Dit beleid is een eenwegbeleid. Hiermee wordt niet voorkomen dat Onderzoek communiceert met Verkoop. Daar is Beleid 2 voor nodig. |
| **Beleid 2: Voorkomen dat onderzoek communiceert met Verkoop** | `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p> In dit voorbeeld wordt het informatiebarrièrebeleid *Research-Sales genoemd.* Wanneer dit beleid actief en toegepast is, voorkomt u dat gebruikers in het segment Onderzoek communiceren met gebruikers in het segment Verkoop. |
| **Beleid 3: Toestaan dat productie alleen met HR en Marketing kan communiceren** | `New-InformationBarrierPolicy -Name "Manufacturing-HRMarketing" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Marketing","Manufacturing" -State Inactive` <p> In dit geval wordt het informatiebarrièrebeleid *Manufacturing-HRMarketing genoemd.* Wanneer dit beleid actief en toegepast is, kan Manufacturing alleen communiceren met HR en Marketing. HR en Marketing worden niet beperkt tot het communiceren met andere segmenten. |

Wanneer segmenten en beleidsregels zijn gedefinieerd, past Contoso het beleid toe door de **cmdlet Start-InformationBarrierPoliciesApplication** uit te voeren.

Wanneer de cmdlet is gefinisht, voldoet Contoso aan de wettelijke en industriële vereisten.

## <a name="resources"></a>Middelen

- [Een overzicht krijgen van informatiebarrières](information-barriers.md)
- [Meer informatie over informatiebarrières in Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Meer informatie over informatiebarrières in SharePoint Online](/sharepoint/information-barriers)
- [Meer informatie over informatiebarrières in OneDrive](/onedrive/information-barriers)
