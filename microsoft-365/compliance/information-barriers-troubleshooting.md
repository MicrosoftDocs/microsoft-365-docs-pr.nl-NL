---
title: Problemen met informatiebelemmeringen oplossen
description: Gebruik dit artikel als handleiding voor het oplossen van informatiebarrières.
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: de415ba7b68df786ead038bb72465c445a86ba5a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162261"
---
# <a name="troubleshooting-information-barriers"></a>Problemen met informatiebelemmeringen oplossen

[Informatiebarrières](information-barriers.md) kunnen ervoor zorgen dat uw organisatie voldoet aan wettelijke vereisten en branchevoorschriften. Met informatiebarrières kunt u bijvoorbeeld de communicatie tussen specifieke groepen gebruikers beperken om conflicten of andere problemen te voorkomen. (Zie Beleidsregels definiëren voor informatiebarrières voor meer informatie over het instellen van [informatiebarrières](information-barriers-policies.md).)

In het geval dat mensen onverwachte problemen krijgen nadat er informatiebarrières zijn, kunt u enkele stappen ondernemen om deze problemen op te lossen. Gebruik dit artikel als handleiding.

> [!IMPORTANT]
> Als u de taken wilt uitvoeren die in dit artikel worden beschreven, moet u een passende rol krijgen, zoals een van de volgende taken:<br/>- Microsoft 365 Enterprise globale beheerder<br/>- globale beheerder<br/>- Compliancebeheerder<br/>- IB Compliance Management (dit is een nieuwe rol!)<p>Zie Vereisten [(voor informatiebarrièrebeleid)](information-barriers-policies.md#prerequisites)voor meer informatie over vereisten voor informatiebarrières.<p>Zorg ervoor dat u [verbinding maakt met Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).

## <a name="issue-users-are-unexpectedly-blocked-from-communicating-with-others-in-microsoft-teams"></a>Probleem: Gebruikers worden onverwacht geblokkeerd voor communicatie met anderen in Microsoft Teams 

In dit geval melden personen onverwachte problemen met de communicatie met anderen in Microsoft Teams. Enkele voorbeelden zijn:

- Een gebruiker zoekt naar een andere gebruiker in de Microsoft Teams.
- Een gebruiker kan een andere gebruiker in de Microsoft Teams.
- Een gebruiker kan een andere gebruiker zien, maar kan geen berichten verzenden naar die andere gebruiker in Microsoft Teams.

### <a name="what-to-do"></a>Wat moet u doen?

Bepaal of de gebruikers worden beïnvloed door een beleid voor informatiebarrière. Afhankelijk van hoe beleidsregels zijn geconfigureerd, werken informatiebarrières mogelijk zoals verwacht. Of misschien moet u het beleid van uw organisatie verfijnen.

1. Gebruik de **cmdlet Get-InformationBarrierRecipientStatus** met de parameter Identiteit. 

    |**Syntaxis**|**Voorbeeld**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity` <p> U kunt elke identiteitswaarde gebruiken die elke geadresseerde uniek identificeert, zoals Naam, Alias, DN(Distinguished name), Canonical DN, E-mailadres of GUID. |`Get-InformationBarrierRecipientStatus -Identity meganb` <p> In dit voorbeeld gebruiken we een alias *(meganb)* voor de parameter Identiteit. Deze cmdlet retourneert informatie die aangeeft of de gebruiker wordt beïnvloed door een beleid voor informatiebarrière. (Zoek naar *ExoPolicyId: \<GUID> .) |

    **Als de gebruikers niet zijn opgenomen in het beleid voor informatiebarrières, neem dan contact op met ondersteuning.** Ga anders verder met de volgende stap.

2. Ontdek welke segmenten zijn opgenomen in een informatiebarrièrebeleid. Gebruik hiervoor de `Get-InformationBarrierPolicy` cmdlet met de parameter Identiteit. 

    |**Syntaxis**|**Voorbeeld**|
    |:---------|:----------|
    | `Get-InformationBarrierPolicy` <p> Gebruik details, zoals de beleids-GUID (ExoPolicyId) die u tijdens de vorige stap hebt ontvangen, als identiteitswaarde. | `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f` <p> In dit voorbeeld krijgen we gedetailleerde informatie over het informatiebarrièrebeleid met ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*. |

    Nadat u de cmdlet hebt uitgevoerd, gaat u in de resultaten op zoek naar de waarden **Toegewezensegment,** **SegmentenAllowed** en **Segmenten geblokkeerd.**

    Na het uitvoeren van de cmdlet zagen we bijvoorbeeld het `Get-InformationBarrierPolicy` volgende in onze lijst met resultaten:

    ```powershell
    AssignedSegment : Sales
    SegmentsAllowed : {}
    SegmentsBlocked : {Research}
    ```

    In dit geval kunnen we zien dat een informatiebarrièrebeleid van invloed is op personen in de segmenten Verkoop en Onderzoek. In dit geval kunnen personen in Sales niet communiceren met personen in Onderzoek.

    Als dit correct lijkt, werken informatiebarrières zoals verwacht. Als dit niet het beste is, gaat u verder met de volgende stap.

3. Zorg ervoor dat de segmenten correct zijn gedefinieerd. Gebruik hiervoor de `Get-OrganizationSegment` cmdlet en bekijk de lijst met resultaten.

    |**Syntaxis**|**Voorbeeld**|
    |:---------|:----------|
    | `Get-OrganizationSegment`<p> Gebruik deze cmdlet met een identiteitsparameter. | `Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd` <p> In dit voorbeeld krijgen we informatie over het segment met GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*. |

    Bekijk de details van het segment. Bewerk indien [nodig een segment](information-barriers-edit-segments-policies.md#edit-a-segment)en gebruik de `Start-InformationBarrierPoliciesApplication` cmdlet opnieuw.

    **Als u nog steeds problemen hebt met uw beleid voor informatiebarrière, neem dan contact op met ondersteuning.**

## <a name="issue-communications-are-allowed-between-users-who-should-be-blocked-in-microsoft-teams"></a>Probleem: Communicatie is toegestaan tussen gebruikers die moeten worden geblokkeerd in Microsoft Teams

Hoewel informatiebarrières zijn gedefinieerd, actief en toegepast, kunnen personen die niet met elkaar kunnen communiceren op de een of andere manier met elkaar chatten en bellen in Microsoft Teams.

### <a name="what-to-do"></a>Wat moet u doen?

Controleer of de gebruikers in kwestie zijn opgenomen in een beleid voor informatiebarrière. 

1. Gebruik de **cmdlet Get-InformationBarrierRecipientStatus** met identiteitsparameters.

    |**Syntaxis** _|_ *Voorbeeld**|
    |:----------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> U kunt elke waarde gebruiken die elke gebruiker uniek identificeert, zoals naam, alias, voornaam, canonieke domeinnaam, e-mailadres of GUID. |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> In dit voorbeeld verwijzen we naar twee gebruikersaccounts in Office 365: *meganb* voor *Megan* en *alexw* voor *Alex*. |

    > [!TIP]
    > U kunt deze cmdlet ook voor één gebruiker gebruiken: `Get-InformationBarrierRecipientStatus -Identity <value>`

2. Bekijk de bevindingen. De **cmdlet Get-InformationBarrierRecipientStatus** retourneert informatie over gebruikers, zoals kenmerkwaarden en beleidsregels voor informatiebarrières die worden toegepast.

    Bekijk de resultaten en volg de volgende stappen, zoals beschreven in de volgende tabel:

    |**Resultaten**|**Wat moet u nu doen?**|
    |:----------|:------------------|
    | Er worden geen segmenten weergegeven voor de geselecteerde gebruiker(en) | Voer een van de volgende handelingen uit:<br/>- Gebruikers toewijzen aan een bestaand segment door hun gebruikersprofielen te bewerken in Azure Active Directory. (Zie [Eigenschappen van gebruikersaccounts configureren met Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md).)<br/>- Een segment definiëren met behulp van [een ondersteund kenmerk voor informatiebarrières.](information-barriers-attributes.md) Definieer [vervolgens een nieuw beleid of](information-barriers-policies.md#part-2-define-information-barrier-policies) [bewerk een bestaand beleid om](information-barriers-edit-segments-policies.md#edit-a-policy) dat segment op te nemen. |
    | Segmenten worden vermeld, maar er worden geen beleidsregels voor informatiebarrières toegewezen aan die segmenten | Voer een van de volgende handelingen uit:<br/>- [Een nieuw beleid voor informatiebarrière definiëren](information-barriers-policies.md#part-2-define-information-barrier-policies) voor elk segment in kwestie <br/>- [Een bestaand beleid voor informatiebarrière bewerken](information-barriers-edit-segments-policies.md#edit-a-policy) om het toe te wijzen aan het juiste segment |
    | Segmenten worden weergegeven en elk segment wordt opgenomen in een informatiebarrièrebeleid | - Voer de `Get-InformationBarrierPolicy` cmdlet uit om te controleren of beleidsregels voor informatiebarrières actief zijn<br/>- Voer de `Get-InformationBarrierPoliciesApplicationStatus` cmdlet uit om te bevestigen dat het beleid wordt toegepast<br/>- Voer de `Start-InformationBarrierPoliciesApplication` cmdlet uit om alle beleidsregels voor actieve informatiebarrière toe te passen |

## <a name="issue-i-need-to-remove-a-single-user-from-an-information-barrier-policy"></a>Probleem: Ik moet één gebruiker verwijderen uit een beleid voor informatiebarrière

In dit geval is het beleid voor informatiebarrières van kracht en wordt een of meer gebruikers onverwacht geblokkeerd voor communicatie met anderen in Microsoft Teams. In plaats van het beleid voor informatiebarrières helemaal te verwijderen, kunt u een of meer afzonderlijke gebruikers verwijderen uit beleidsregels voor informatiebarrière.

### <a name="what-to-do"></a>Wat moet u doen?

Informatiebarrièrebeleid wordt toegewezen aan segmenten van gebruikers. Segmenten worden gedefinieerd met behulp van [bepaalde kenmerken in gebruikersaccountprofielen.](information-barriers-attributes.md) Als u een beleid van één gebruiker moet verwijderen, kunt u overwegen het profiel van die gebruiker in Azure Active Directory zodanig te bewerken dat de gebruiker niet meer wordt opgenomen in een segment dat wordt beïnvloed door informatiebarrières.

1. Gebruik de **cmdlet Get-InformationBarrierRecipientStatus** met identiteitsparameters. Deze cmdlet retourneert informatie over gebruikers, zoals kenmerkwaarden en beleidsregels voor informatiebarrière die worden toegepast.

    |**Syntaxis**|**Voorbeeld**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> U kunt elke waarde gebruiken die elke gebruiker uniek identificeert, zoals naam, alias, voornaam, canonieke domeinnaam, e-mailadres of GUID. | `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> In dit voorbeeld verwijzen we naar twee gebruikersaccounts in Office 365: *meganb* voor *Megan* en *alexw* voor *Alex*.          |
    | `Get-InformationBarrierRecipientStatus -Identity <value>` <p> U kunt elke waarde gebruiken die de gebruiker uniek identificeert, zoals naam, alias, voorname, canonieke domeinnaam, e-mailadres of GUID.|`Get-InformationBarrierRecipientStatus -Identity jeanp`<p> In dit voorbeeld verwijzen we naar één account in Office 365: *jeanp*. |

2. Bekijk de resultaten om te zien of er beleidsregels voor informatiebarrières zijn toegewezen en aan welk segment(en) de gebruiker(s) behoort.

3. Als u een gebruiker wilt verwijderen uit een segment dat wordt beïnvloed door informatiebarrières, moet u de profielgegevens van de gebruiker [bijwerken in Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

4. Wacht ongeveer 30 minuten totdat FwdSync wordt uitgevoerd. Of voer de `Start-InformationBarrierPoliciesApplication` cmdlet uit om alle beleidsregels voor actieve informatiebarrière toe te passen.

## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a>Probleem: De toepassing van de informatiebarrière duurt te lang

Nadat u de **cmdlet Start-InformationBarrierPoliciesApplication** heeft uitgevoerd, duurt het erg lang voordat het proces is afgelopen.

### <a name="what-to-do"></a>Wat moet u doen?

Houd er rekening mee dat wanneer u de cmdlet beleidstoepassing uit te voeren, beleidsregels voor informatiebarrière worden toegepast (of verwijderd), gebruiker per gebruiker, voor alle accounts in uw organisatie. Als u veel gebruikers hebt, duurt het even voordat u de procedure hebt verwerkt. (Als algemene richtlijn duurt het ongeveer een uur om 5.000 gebruikersaccounts te verwerken.)

1. Gebruik de **cmdlet Get-InformationBarrierPoliciesApplicationStatus** om de status van de meest recente beleidstoepassing te controleren.

    |**De meest recente beleidstoepassing weergeven**|**Status weergeven voor alle beleidstoepassingen**|
    |:---------------------------------------------|:---------------------------------------------|
    | `Get-InformationBarrierPoliciesApplicationStatus` | `Get-InformationBarrierPoliciesApplicationStatus -All $true` |

    Hier wordt informatie weergegeven over of de beleidstoepassing is voltooid, mislukt of wordt uitgevoerd.

2. Volg een van de volgende stappen, afhankelijk van de resultaten van de vorige stap:
  
    |**Status**|**Volgende stap**|
    |:---------|:------------|
    | **Niet gestart** | Als het meer dan 45 minuten geleden is dat de cmdlet **Start-InformationBarrierPoliciesApplication** is uitgevoerd, controleert u het auditlogboek om te zien of er fouten zijn in beleidsdefinities of een andere reden waarom de toepassing niet is gestart. |
    | **Mislukt** | Als de toepassing is mislukt, controleert u het auditlogboek. Bekijk ook uw segmenten en beleidsregels. Zijn er gebruikers toegewezen aan meer dan één segment? Zijn er segmenten toegewezen aan meer dan één beleid? Bewerk indien [nodig segmenten](information-barriers-edit-segments-policies.md#edit-a-segment) en/of [](information-barriers-edit-segments-policies.md#edit-a-policy)bewerk beleidsregels en voer vervolgens de cmdlet **Start-InformationBarrierPoliciesApplication** opnieuw uit. |
    | **In uitvoering** | Als de toepassing nog steeds wordt uitgevoerd, kunt u meer tijd toestaan om de toepassing te voltooien. Als het enkele dagen geleden is, verzamelt u uw auditlogboeken en neem dan contact op met de ondersteuning. |

## <a name="issue-information-barrier-policies-are-not-being-applied-at-all"></a>Probleem: Beleid voor informatiebarrière wordt helemaal niet toegepast

In dit geval hebt u segmenten gedefinieerd, beleidsregels voor informatiebarrières gedefinieerd en hebt u geprobeerd deze beleidsregels toe te passen. Wanneer u de `Get-InformationBarrierPoliciesApplicationStatus` cmdlet echter uit runt, ziet u dat de beleidstoepassing is mislukt.

### <a name="what-to-do"></a>Wat moet u doen?

Zorg ervoor dat uw organisatie geen [adresboekbeleid Exchange](/exchange/address-books/address-book-policies/address-book-policies) hebben. Dit beleid voorkomt dat beleidsregels voor informatiebarrières worden toegepast.

1. Verbinding maken [powershell Exchange Online gebruiken.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Voer de [cmdlet Get-AddressBookPolicy](/powershell/module/exchange/get-addressbookpolicy) uit en bekijk de resultaten.

    |**Resultaten**|**Volgende stap**|
    |:----------|:------------|
    | Exchange adresboekbeleid worden weergegeven | [Adresboekbeleid verwijderen](/exchange/address-books/address-book-policies/remove-an-address-book-policy) |
    | Er bestaan geen adresboekbeleidsregels |Controleer uw auditlogboeken om erachter te komen waarom beleidstoepassing mislukt |

3. [Status van gebruikersaccounts, segmenten, beleidsregels of beleidstoepassing weergeven.](information-barriers-policies.md#view-status-of-user-accounts-segments-policies-or-policy-application)

## <a name="issue-information-barrier-policy-not-applied-to-all-designated-users"></a>Probleem: Het beleid voor informatiebarrière is niet toegepast op alle aangewezen gebruikers

Nadat u segmenten hebt gedefinieerd, beleidsregels voor informatiebarrières hebt gedefinieerd en hebt geprobeerd dit beleid toe te passen, is het mogelijk dat het beleid van toepassing is op sommige geadresseerden, maar niet op andere.
Wanneer u de `Get-InformationBarrierPoliciesApplicationStatus` cmdlet uitvoert, zoekt u in de uitvoer naar tekst zoals deze.

> Identiteit: `<application guid>`
>
> Totaal aantal geadresseerden: 81527
>
> Mislukte geadresseerden: 2
>
> Foutcategorie: Geen
>
> Status: Voltooid

### <a name="what-to-do"></a>Wat moet u doen?

1. Zoek in het auditlogboek naar `<application guid>` . U kunt deze PowerShell-code kopiëren en wijzigen voor uw variabelen.

```powershell
$DetailedLogs = Search-UnifiedAuditLog -EndDate <yyyy-mm-ddThh:mm:ss>  -StartDate <yyyy-mm-ddThh:mm:ss> -RecordType InformationBarrierPolicyApplication -ResultSize 1000 |?{$_.AuditData.Contains(<application guid>)} 
```

2. Controleer de gedetailleerde uitvoer van het auditlogboek op de waarden van de `"UserId"` velden en de `"ErrorDetails"` waarden. Dit geeft u de reden voor de fout. U kunt deze PowerShell-code kopiëren en wijzigen voor uw variabelen.

```powershell
   $DetailedLogs[1] |fl
```

Bijvoorbeeld:

> 'UserId': Gebruiker1
>
>"ErrorDetails":"Status: IBPolicyConflict. Fout: IB-segment 'segment-id1' en IB-segment 'segment-id2' heeft een conflict en kan niet worden toegewezen aan de ontvanger.

3. Meestal zult u merken dat een gebruiker is opgenomen in meer dan één segment. U kunt dit oplossen door de waarde `-UserGroupFilter` bij te werken in `OrganizationSegments` .

4. Beleid voor informatiebarrières opnieuw toepassen met behulp van deze procedures [Beleid voor informatiebarrières](information-barriers-policies.md#part-3-apply-information-barrier-policies).

## <a name="resources"></a>Resources

- [Beleid definiëren voor informatiebarrières in Microsoft Teams](information-barriers-policies.md)
- [Informatiebelemmeringen](information-barriers.md)