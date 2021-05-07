---
title: Beleidsregels voor informatiebarrière beheren
description: Meer informatie over het bewerken of verwijderen van beleidsregels voor informatiebarrières.
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
ms.openlocfilehash: 668ca8e26371d80f068c2723357ce3ee407db03a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162105"
---
# <a name="manage-information-barrier-policies"></a>Beleidsregels voor informatiebarrière beheren

Nadat u [beleidsregels voor informatiebarrières](information-barriers-policies.md)hebt gedefinieerd, moet u mogelijk wijzigingen aanbrengen in dit beleid [of](information-barriers-troubleshooting.md) in uw gebruikerssegmenten, als onderdeel van het oplossen van problemen of als regelmatig onderhoud. Gebruik dit artikel als handleiding.

## <a name="what-do-you-want-to-do"></a>Wat wilt u doen?

|**Actie**|**Beschrijving**|
|:---------|:--------------|
| [Kenmerken van gebruikersaccounts bewerken](#edit-user-account-attributes) | Vul kenmerken in Azure Active Directory die kunnen worden gebruikt om segmenten te definiëren.<br/>Bewerk gebruikersaccountkenmerken wanneer gebruikers niet worden opgenomen in segmenten die ze moeten zijn, om te wijzigen in welke segmenten gebruikers zich in of om segmenten te definiëren met behulp van verschillende kenmerken. |
| [Een segment bewerken](#edit-a-segment) | Segmenten bewerken wanneer u wilt wijzigen hoe een segment wordt gedefinieerd. <br/>U hebt bijvoorbeeld mogelijk oorspronkelijk gedefinieerde segmenten met Behulp van *Afdeling* en wilt nu een ander kenmerk gebruiken, zoals *MemberOf.* |
| [Een beleid bewerken](#edit-a-policy) | Bewerk een beleid voor informatiebarrière wanneer u de manier waarop een beleid werkt wilt wijzigen.<br/>In plaats van de communicatie tussen twee segmenten te blokkeren, kunt u bijvoorbeeld besluiten dat communicatie alleen tussen bepaalde segmenten mag plaatsvinden. |
| [Een beleid instellen op inactieve status](#set-a-policy-to-inactive-status) |Stel een beleid in op inactieve status wanneer u wijzigingen wilt aanbrengen in een beleid of wanneer u niet wilt dat een beleid van kracht wordt. |
| [Een beleid verwijderen](#remove-a-policy) | Verwijder een beleid voor informatiebarrière wanneer u een bepaald beleid niet meer nodig hebt. |
| [Een beleidstoepassing stoppen](#stop-a-policy-application) | Neem deze actie wanneer u het toepassen van beleidsregels voor informatiebarrières wilt stoppen.<br/> Het stoppen van een beleidstoepassing is niet direct en het maakt geen beleid ongedaan dat al op gebruikers is toegepast. |
| [Beleid definiëren voor informatiebarrières](information-barriers-policies.md) | Definieer een beleid voor informatiebarrières wanneer u dergelijke beleidsregels nog niet hebt en u moet de communicatie tussen specifieke groepen gebruikers beperken of beperken. |
| [Problemen met informatiebelemmeringen oplossen](information-barriers-troubleshooting.md) | Raadpleeg dit artikel wanneer u onverwachte problemen met informatiebarrières tegen komt. |

> [!IMPORTANT]
> Als u de taken wilt uitvoeren die in dit artikel worden beschreven, moet u een passende rol krijgen, zoals een van de volgende taken:<br/>- Microsoft 365 Enterprise globale beheerder<br/>- Globale beheerder<br/>- Compliancebeheerder<br/>- IB Compliance Management (dit is een nieuwe rol!)<br><br>Zie Vereisten [(voor informatiebarrièrebeleid)](information-barriers-policies.md#prerequisites)voor meer informatie over vereisten voor informatiebarrières.<br><br> Zorg ervoor dat u [verbinding maakt met het beveiligingscentrum & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).

## <a name="edit-user-account-attributes"></a>Kenmerken van gebruikersaccounts bewerken

Gebruik deze procedure om kenmerken te bewerken die worden gebruikt voor het segmenteren van gebruikers. Als u bijvoorbeeld een department-kenmerk gebruikt en een of meer gebruikersaccounts momenteel geen waarden voor Afdeling bevatten, moet u deze gebruikersaccounts bewerken om afdelingsgegevens op te nemen. Gebruikersaccountkenmerken worden gebruikt voor het definiëren van segmenten, zodat beleidsregels voor informatiebarrière kunnen worden toegewezen.

1. Als u details wilt weergeven voor een specifiek gebruikersaccount, zoals kenmerkwaarden en toegewezen segmenten, gebruikt u de **cmdlet Get-InformationBarrierRecipientStatus** met identiteitsparameters.

    |**Syntaxis**|**Voorbeeld**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> U kunt elke waarde gebruiken die elke gebruiker uniek identificeert, zoals naam, alias, voornaam, canonieke domeinnaam, e-mailadres of GUID. <p> (U kunt deze cmdlet ook voor één gebruiker gebruiken: `Get-InformationBarrierRecipientStatus -Identity <value>` ) |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> In dit voorbeeld verwijzen we naar twee gebruikersaccounts in Office 365: *meganb* voor *Megan* en *alexw* voor *Alex*. |

2. Bepaal welk kenmerk u wilt bewerken voor uw gebruikersaccountprofiel(en). Zie Kenmerken voor informatiebarrièrebeleid voor meer [informatie.](information-barriers-attributes.md) 

3. Bewerk een of meer gebruikersaccounts om waarden op te nemen voor het kenmerk dat u hebt geselecteerd in de vorige stap. Gebruik een van de volgende procedures om deze actie uit te voeren:

    - Zie Profielgegevens van een gebruiker toevoegen of [bijwerken](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)met behulp van Azure Active Directory.

    - Zie Eigenschappen van gebruikersaccounts configureren met powershell als u meerdere Office 365 accounts wilt bewerken (of PowerShell wilt gebruiken om één account [te bewerken).](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)

## <a name="edit-a-segment"></a>Een segment bewerken

Gebruik deze procedure om de definitie van een gebruikerssegment te bewerken. U kunt bijvoorbeeld de naam van een segment wijzigen of het filter dat wordt gebruikt om te bepalen wie in het segment is opgenomen.

1. Als u alle bestaande segmenten wilt weergeven, gebruikt u de **cmdlet Get-OrganizationSegment.**

    Syntaxis: `Get-OrganizationSegment`

    U ziet een lijst met segmenten en details voor elk segmenttype, zoals het segmenttype, de waarde UserGroupFilter, wie deze heeft gemaakt of voor het laatst heeft gewijzigd, GUID, en ga zo maar door.

    > [!TIP]
    > Druk de lijst met segmenten af of sla deze later op. Als u bijvoorbeeld een segment wilt bewerken, moet u de naam weten of de waarde identificeren (dit wordt gebruikt met de parameter Identiteit).

2. Als u een segment wilt bewerken, gebruikt u de cmdlet **Set-OrganizationSegment** met de parameter **Identiteit** en relevante details.

    |**Syntaxis**|**Voorbeeld**|
    |:---------|:----------|
    | `Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"` |`Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"` <p> In dit voorbeeld, voor het segment met de GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd,* hebben we de afdelingsnaam bijgewerkt naar 'HRDept'. |

Wanneer u klaar bent met het bewerken van [](#edit-a-policy) segmenten voor uw organisatie, kunt u [beleidsregels](information-barriers-policies.md#part-2-define-information-barrier-policies) voor informatiebarrière definiëren of bewerken.

## <a name="edit-a-policy"></a>Een beleid bewerken

1. Gebruik de **cmdlet Get-InformationBarrierPolicy** om een lijst met huidige beleidsregels voor informatiebarrières weer te geven.

    Syntaxis: `Get-InformationBarrierPolicy`

    Identificeer in de lijst met resultaten het beleid dat u wilt wijzigen. Let op de GUID en naam van het beleid.

2. Gebruik de **cmdlet Set-InformationBarrierPolicy** met een **identity-parameter** en geef de wijzigingen op die u wilt aanbrengen.

    Voorbeeld: Stel dat er een beleid is gedefinieerd om te blokkeren dat het *segment* Onderzoek communiceert met de *segmenten Verkoop* en *Marketing.* Het beleid is gedefinieerd met behulp van deze cmdlet: `New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`

    Stel dat we deze willen wijzigen, zodat personen in het segment *Onderzoek* alleen kunnen communiceren met personen in het *HR-segment.* Om deze wijziging aan te brengen, gebruiken we deze cmdlet: `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`

    In dit voorbeeld hebben we 'Segmenten geblokkeerd' gewijzigd in 'Segmentenallowed' en het *HR-segment* opgegeven.

3. Wanneer u klaar bent met het bewerken van een beleid, moet u de wijzigingen toepassen. (Zie [Beleidsregels voor informatiebarrière toepassen](information-barriers-policies.md#part-3-apply-information-barrier-policies).)

## <a name="set-a-policy-to-inactive-status"></a>Een beleid instellen op inactieve status

1. Gebruik de **cmdlet Get-InformationBarrierPolicy** om een lijst met huidige beleidsregels voor informatiebarrières weer te geven.

    Syntaxis: `Get-InformationBarrierPolicy`

    Identificeer in de lijst met resultaten het beleid dat u wilt wijzigen (of verwijderen). Let op de GUID en naam van het beleid.

2. Als u de status van het beleid wilt instellen op inactief, gebruikt u de cmdlet **Set-InformationBarrierPolicy** met een parameter Identiteit en de parameter State ingesteld op Inactief.

    |**Syntaxis**|**Voorbeeld**|
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Inactive` | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive` <p> In dit voorbeeld stellen we een informatiebarrièrebeleid in met GUID *43c37853-ea10-4b90-a23d-ab8c9377247* op een inactieve status. |

3. Als u uw wijzigingen wilt toepassen, gebruikt u de **cmdlet Start-InformationBarrierPoliciesApplication.**

    Syntaxis: `Start-InformationBarrierPoliciesApplication`

    Wijzigingen worden toegepast, gebruiker per gebruiker, voor uw organisatie. Als uw organisatie groot is, kan het 24 uur (of meer) duren voordat dit proces is voltooid. (Als algemene richtlijn duurt het ongeveer een uur om 5.000 gebruikersaccounts te verwerken.)

Op dit moment is een of meer beleidsregels voor informatiebarrière ingesteld op inactieve status. Hier kunt u een van de volgende acties uitvoeren:

- Houd het zoals het is (een beleid ingesteld op inactieve status heeft geen effect op gebruikers)
- [Een beleid bewerken](#edit-a-policy) 
- [Een beleid verwijderen](#remove-a-policy)

## <a name="remove-a-policy"></a>Een beleid verwijderen

1. Gebruik de **cmdlet Get-InformationBarrierPolicy** om een lijst met huidige beleidsregels voor informatiebarrières weer te geven.

    Syntaxis: `Get-InformationBarrierPolicy`

    Identificeer in de lijst met resultaten het beleid dat u wilt verwijderen. Let op de GUID en naam van het beleid. Zorg ervoor dat het beleid is ingesteld op inactieve status.

2. Gebruik de **cmdlet Remove-InformationBarrierPolicy** met een identity-parameter.

    |**Syntaxis**|**Voorbeeld**|
    |:---------|:----------|
    | `Remove-InformationBarrierPolicy -Identity GUID` | `Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471` <p> In dit voorbeeld verwijderen we het beleid met GUID *43c37853-ea10-4b90-a23d-ab8c93772471.* |

    Bevestig de wijziging wanneer u daarom wordt gevraagd.

3. Herhaal stap 1-2 voor elk beleid dat u wilt verwijderen.

4. Wanneer u klaar bent met het verwijderen van beleidsregels, moet u de wijzigingen toepassen. Gebruik de cmdlet **Start-InformationBarrierPoliciesApplication** om deze actie uit te voeren.

    Syntaxis: `Start-InformationBarrierPoliciesApplication`

    Wijzigingen worden toegepast, gebruiker per gebruiker, voor uw organisatie. Als uw organisatie groot is, kan het 24 uur (of meer) duren voordat dit proces is voltooid.

## <a name="stop-a-policy-application"></a>Een beleidstoepassing stoppen

Nadat u bent begonnen met het toepassen van beleidsregels voor informatiebarrières, gebruikt u de volgende procedure als u wilt voorkomen dat dit beleid wordt toegepast. Het duurt ongeveer 30-35 minuten voordat het proces is begonnen.

1. Gebruik de **cmdlet Get-InformationBarrierPoliciesApplicationStatus** om de status van de meest recente toepassing voor het informatiebarrièrebeleid weer te geven.

    Syntaxis: `Get-InformationBarrierPoliciesApplicationStatus`

    Let op de GUID van de toepassing.

2. Gebruik de **cmdlet Stop-InformationBarrierPoliciesApplication** met een parameter Identity.

    |**Syntaxis**|**Voorbeeld**|
    |:---------|:----------|
    | `Stop-InformationBarrierPoliciesApplication -Identity GUID` | `Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1` <p> In dit voorbeeld wordt voorkomen dat beleidsregels voor informatiebarrières worden toegepast. |

## <a name="resources"></a>Resources

- [Een overzicht krijgen van informatiebarrières](information-barriers.md)
- [Beleid definiëren voor informatiebarrières](information-barriers-policies.md)
- [Meer informatie over informatiebarrières in Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Meer informatie over informatiebarrières in SharePoint Online](/sharepoint/information-barriers)
- [Meer informatie over informatiebarrières in OneDrive](/onedrive/information-barriers)
- [Kenmerken voor het beleid voor informatiebelemmering](information-barriers-attributes.md)
- [Problemen met informatiebelemmeringen oplossen](information-barriers-troubleshooting.md)