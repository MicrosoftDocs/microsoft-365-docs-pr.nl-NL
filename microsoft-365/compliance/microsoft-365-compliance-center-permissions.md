---
title: Machtigingen in het Microsoft 365 compliancecentrum
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.service: O365-seccomp
audience: ITPro
ms.topic: article
localization_priority: Normal
description: Meer informatie over het beheren van machtigingen in Microsoft 365 compliancecentrum.
ms.collection: M365-security-compliance
ms.openlocfilehash: 7038863c0cbcaf99cf07072445a3b001e7b8ca0b
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782847"
---
# <a name="permissions-in-the-microsoft-365-compliance-center"></a>Machtigingen in het Microsoft 365 compliancecentrum

Het Microsoft 365 compliancecentrum is onlangs bijgewerkt en ondersteunt nu rechtstreeks het beheren van machtigingen voor gebruikers die compliancetaken uitvoeren in Microsoft 365. Deze update betekent dat u het beveiligings- Office 365 compliancecentrum & niet meer hoeft te gebruiken om machtigingen voor complianceoplossingen te beheren. Met de  nieuwe pagina Machtigingen in het Microsoft 365 compliancecentrum kunt u machtigingen voor gebruikers beheren voor compliancetaken in functies zoals apparaatbeheer, preventie van gegevensverlies, eDiscovery, insiderrisicobeheer, bewaring en vele andere. Gebruikers kunnen alleen de nalevingstaken uitvoeren die u hen expliciet toegang verleent.

Als u het tabblad Machtigingen wilt weergeven in het Microsoft 365 compliancecentrum, moeten gebruikers  een globale beheerder zijn of de  rol Rollenbeheer krijgen toegewezen (een rol wordt alleen toegewezen aan de rollengroep Organisatiebeheer).  Met *de rol* Rollenbeheer kunnen gebruikers rollengroepen weergeven, maken en wijzigen.

![Pagina Machtigingen in Microsoft 365 compliancecentrum](../media/m365-compliance-center-permissions.png)

Machtigingen in het Microsoft 365 compliancecentrum zijn gebaseerd op het RBAC-machtigingsmodel (Role Based Access Control). RBAC is hetzelfde machtigingsmodel dat wordt gebruikt door de meeste Microsoft 365-services, dus als u bekend bent met de machtigingsstructuur in deze services, is het verlenen van machtigingen in het Microsoft 365 compliancecentrum bekend. Het is belangrijk om te onthouden dat de machtigingen die in het Microsoft 365 compliancecentrum worden beheerd, niet betrekking hebben op het beheer van alle machtigingen die nodig zijn voor elke afzonderlijke service. U moet nog steeds bepaalde servicespecifieke machtigingen beheren in het beheercentrum voor de specifieke service. Als u bijvoorbeeld machtigingen moet toewijzen voor archiverings-, audit- en MRM-bewaarbeleid, moet u deze machtigingen beheren in het Exchange beheercentrum.

## <a name="relationship-of-members-roles-and-role-groups"></a>Relatie van leden, rollen en rollengroepen

Een rol verleent machtigingen om een set taken uit te voeren. Met de rol Case Management kunnen gebruikers bijvoorbeeld met eDiscovery-zaken werken.

Een rollengroep is een set rollen waarmee gebruikers hun taken kunnen doen via complianceoplossingen in het Microsoft 365 compliancecentrum. Door bijvoorbeeld gebruikers toe te voegen aan de rollengroep *Insider Risk Management,* worden aangewezen beheerders, analisten, onderzoeker en auditors geconfigureerd voor de benodigde machtigingen voor insiderrisicobeheer in één groep. Het Microsoft 365 compliancecentrum bevat standaardrolgroepen voor taken en functies voor elke complianceoplossing aan wie u personen moet toewijzen. Over het algemeen raden we u aan om zo nodig afzonderlijke gebruikers als leden toe te voegen aan de standaardrolgroepen voor naleving.

![Diagram met de relatie van rollengroepen met rollen en leden](../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)

## <a name="permissions-needed-to-use-features-in-the-microsoft-365-compliance-center"></a>Machtigingen die nodig zijn voor het gebruik van functies in het Microsoft 365 compliancecentrum

Als u alle standaardrolgroepen wilt weergeven die beschikbaar zijn in het Microsoft 365 compliancecentrum en de rollen die standaard aan de rollengroepen zijn toegewezen, gaat u naar de machtigingen in het [beveiligings- & compliancecentrum.](/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)

Als u machtigingen in het Microsoft 365 compliancecentrum beheert, hebben gebruikers alleen toegang tot de compliancefuncties die beschikbaar zijn in het Microsoft 365 compliancecentrum. Als u machtigingen wilt verlenen voor andere functies die zich niet in het Microsoft 365-compliancecentrum, zoals Exchange-regels voor e-mailstroom (ook wel transportregels genoemd), moet u het Exchange-beheercentrum gebruiken.

## <a name="azure-roles-in-the-microsoft-365-compliance-center"></a>Azure-rollen in het Microsoft 365 compliancecentrum

De rollen die worden weergegeven in de **sectie Azure AD** Roles op de pagina machtigingen Microsoft 365 compliancecentrum zijn Azure Active Directory  >   rollen.  Deze rollen zijn ontworpen om te worden samengevoegd met functies in de IT-groep van uw organisatie, zodat u een persoon gemakkelijk alle benodigde machtigingen kunt geven om hun werk te doen. U kunt de gebruikers bekijken die momenteel aan elke rol zijn toegewezen door een beheerdersrol te selecteren en de details van het rollenpaneel weer te geven. Als u leden van een Azure AD-rol wilt beheren, selecteert u Leden beheren in Azure AD. Met deze keuze wordt u omgeleid naar de Azure-beheerportal.

|Rol|Beschrijving|
|:---|:----------|
|**Globale beheerder**|Gebruikers met deze rol hebben toegang tot alle beheerfuncties in alle Microsoft 365-services. Alleen globale beheerders kunnen andere beheerdersrollen toewijzen. Zie [Globale beheerder/Bedrijfsbeheerder](/azure/active-directory/roles/permissions-reference#global-administrator--company-administrator) voor meer informatie.|
|**Beheerder van nalevingsgegevens**|Houd de gegevens van uw organisatie bij in Microsoft 365, zorg ervoor dat de organisatie beveiligd is en krijg inzicht in eventuele problemen om risico's te beperken. Zie [Beheerder van nalevingsgegevens](/azure/active-directory/roles/permissions-reference#compliance-data-administrator) voor meer informatie.|
|**Beheerder voor naleving**|Help uw organisatie bij de naleving van wettelijke vereisten, het beheren van eDiscovery-aanvragen en het beheren van beleidsregels voor gegevensbeheer met betrekking tot Microsoft 365-locaties, -identiteiten en -apps. Zie [Beheerder voor naleving](/azure/active-directory/roles/permissions-reference#compliance-administrator) voor meer informatie.|
|**Beveiligingsoperator**|Bekijk, onderzoek en reageer op actieve bedreigingen van uw Microsoft 365-gebruikers, -apparaten en -inhoud. Zie [Beveiligingsoperator](/azure/active-directory/roles/permissions-reference#security-operator) voor meer informatie.|
|**Beveiligingslezer**|Bekijk en onderzoek actieve bedreigingen voor uw Microsoft 365-gebruikers, -apparaten en -inhoud, maar u hebt (in tegenstelling tot de beveiligingsoperator) geen machtiging om te reageren door actie te ondernemen. Zie [Beveiligingslezer](/azure/active-directory/roles/permissions-reference#security-reader) voor meer informatie.|
|**Beveiligingsbeheerder**|Controleer de algehele beveiliging van uw organisatie door beveiligingsbeleid te beheren, de beveiligingsanalyse en rapporten in de Microsoft 365-producten te evalueren en op de hoogte te blijven van mogelijke dreigingen. Zie [Beveiligingsbeheerder](/azure/active-directory/roles/permissions-reference#security-administrator) voor meer informatie.|
|**Globale lezer**|De alleen-lezen versie van de rol **Globale beheerder**. Bekijk alle instellingen en administratieve informatie in Microsoft 365. Zie [Globale lezer](/azure/active-directory/roles/permissions-reference#global-reader) voor meer informatie.|
|**Aanvalssimulatiebeheerder**|Maak en beheer alle aspecten van het maken van een aanvalssimulatie, het starten/plannen van een simulatie en het bekijken van de resultaten van de simulatie. Zie Aanvalssimulatiebeheerder voor meer [informatie.](/azure/active-directory/roles/permissions-reference#attack-simulation-administrator)|
|**Auteur van aanvalslading**|Maak aanvalsladingen, maar start ze niet echt of plan ze niet. Zie Attack Payload Author voor [meer informatie.](/azure/active-directory/roles/permissions-reference#attack-payload-author)|
|

## <a name="add-users-to-a-compliance-role-group"></a>Gebruikers toevoegen aan een compliancerolgroep

Volg de volgende stappen om gebruikers toe te voegen aan een compliancerolgroep:

1. Meld u aan bij het machtigingsgebied van het [Microsoft 365 compliancecentrum](https://compliance.microsoft.com/permissions) met referenties voor een beheerdersaccount in uw Microsoft 365 organisatie.
2. Ga in Microsoft 365 compliancecentrum naar **Machtigingen.** Selecteer de koppeling voor het weergeven en beheren van compliancerollen in Microsoft 365.
3. Vouw de **sectie Compliancecentrum** uit en selecteer **Rollen.**
4. Selecteer op **de pagina Rollen in** het compliancecentrum een compliancerolgroep aan wie u gebruikers wilt toevoegen en selecteer vervolgens **Rollengroep** bewerken in het detailvenster.
5. Selecteer **Leden kiezen** in het linkernavigatiedeelvenster en selecteer vervolgens **Bewerken.**
6. Selecteer **Toevoegen** en schakel het selectievakje in voor alle gebruikers die u wilt toevoegen aan de rollengroep.
7. Selecteer **Toevoegen** en selecteer vervolgens **Klaar.**
8. Selecteer **Opslaan om** de gebruikers toe te voegen aan de rollengroep. Selecteer **Sluiten om** de stappen uit te voeren.

## <a name="remove-users-from-a-compliance-role-group"></a>Gebruikers verwijderen uit een compliancerolgroep

Volg de volgende stappen om gebruikers uit een compliancerolgroep te verwijderen:

1. Meld u aan bij het machtigingsgebied van het [Microsoft 365 compliancecentrum](https://compliance.microsoft.com/permissions) met referenties voor een beheerdersaccount in uw Microsoft 365 organisatie.
2. Ga in Microsoft 365 compliancecentrum naar **Machtigingen.** Selecteer de koppeling voor het weergeven en beheren van compliancerollen in Microsoft 365.
3. Vouw de sectie Compliancecentrum uit en selecteer **Rollen.**
4. Selecteer op **de pagina Rollen** in het compliancecentrum een compliancerolgroep waaruit u gebruikers wilt verwijderen en selecteer vervolgens **Rollengroep** bewerken in het detailvenster.
5. Selecteer **Leden kiezen** in het linkernavigatiedeelvenster en selecteer vervolgens **Bewerken.**
6. Selecteer **Verwijderen** en schakel het selectievakje in voor alle gebruikers die u uit de rollengroep wilt verwijderen.
7. Selecteer **Verwijderen** en selecteer vervolgens **Klaar.**
8. Selecteer **Opslaan om** de gebruikers uit de rollengroep te verwijderen. Selecteer **Sluiten om** de stappen uit te voeren.
