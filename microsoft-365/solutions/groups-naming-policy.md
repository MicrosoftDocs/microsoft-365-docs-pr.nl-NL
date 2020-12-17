---
title: Naam beleid voor Microsoft 365-groepen
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: Leer hoe u een naamgevingsbeleid maakt voor Microsoft 365-groepen.
ms.openlocfilehash: 9bc0a4c7e1ae6ad532c97b442a2bc50880a942fc
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698673"
---
# <a name="microsoft-365-groups-naming-policy"></a>Naam beleid voor Microsoft 365-groepen

U kunt een Groepsbeleid gebruiken om een consistente naam strategie af te dwingen voor groepen die zijn gemaakt door gebruikers in uw organisatie. Met behulp van een naamgevingsbeleid kunt u en uw gebruikers de functie van de groep, het lidmaatschap, de geografische regio of de groep die de groep heeft gemaakt, identificeren. Met behulp van het naamgevingsbeleid kunt u groepen in het adresboek ook categoriseren. U kunt het beleid gebruiken om te voorkomen dat bepaalde woorden worden gebruikt in namen en aliassen van groepen.

De naamgevings beleidsregels worden toegepast op groepen die zijn gemaakt in alle groepen belastingen (zoals Outlook, Microsoft teams, SharePoint, planner, Yammer, enzovoort). De app wordt toegepast op de groepsnaam en de alias van de groep. Dit wordt toegepast wanneer een gebruiker een groep maakt en wanneer de groepsnaam of alias voor een bestaande groep wordt bewerkt.

> [!TIP]
> Een Microsoft 365-naamgevingsbeleid voor groepen geldt alleen voor Microsoft 365-groepen. Deze functie is niet van toepassing op distributiegroepen die zijn gemaakt in Exchange Online. Zie [een naam beleid voor distributiegroepen maken](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy)voor informatie over het maken van een naamgevingsbeleid voor distributiegroepen.

Het groepsnaambeleid bestaat uit de volgende functie:

- **Naamgeving van voorvoegsels/achtervoegsels**: u kunt voorvoegsels of achtervoegsels gebruiken om de naamgevingsconventie van de groepen te definiëren (bijvoorbeeld: ' US \_ My Group \_ engineering '). De voorvoegsels/achtervoegsels kunnen bestaan uit vaste tekenreeksen of gebruikerskenmerken (zoals [Department]) die worden vervangen op basis van de gebruiker die de groep maakt.

- **Aangepaste, geblokkeerde woorden**: u kunt een set geblokkeerde woorden die specifiek zijn voor uw organisatie uploaden naar een groep die wordt geblokkeerd in groepen die door gebruikers zijn gemaakt. (Bijvoorbeeld: "CEO, Payroll, HR").

## <a name="licensing-requirements"></a>Licentievereisten

Als u Azure AD namebeleid voor Microsoft 365-groepen gebruikt, moet u beschikken over een licentie voor Azure Active Directory Premium P1 of een Azure AD Basic EDU-licentie voor elke unieke gebruiker (met inbegrip van gasten) die lid is van een of meer Microsoft 365-groepen.

Dit is ook vereist voor de beheerder die het naamgevingsbeleid voor groepen maakt.

## <a name="prefix-suffix-naming-policy"></a>Naam beleid Prefix-Suffix

Voorvoegsels en achtervoegsels kunnen vaste tekenreeksen of gebruikerskenmerken zijn.

### <a name="fixed-strings"></a>Vaste tekenreeksen

U kunt gebruik maken van korte tekenreeksen die u kunnen helpen om onderscheid te maken tussen groepen in de algemene GAL-en linkermenubalk van de groepswerk. Enkele van de veelvoorkomende achtervoegsels voor updates zijn trefwoorden zoals ' GRP \_ name ', ' \# name ', ' \_ name '

### <a name="attributes"></a>Kenmerken

U kunt kenmerken gebruiken waarmee u kunt vaststellen wie de groep heeft gemaakt, bijvoorbeeld [Department], en waar de groep is gemaakt, bijvoorbeeld [Country].

Voorbeelden:

- Beleid = "GRP [GroupName] [Department]"
- Afdeling van de gebruiker = Engineering
- Gemaakte groepsnaam = "GRP My Group Engineering"

Ondersteunde Azure Active Directory (Azure AD)-kenmerken zijn [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion] en [title].

- Niet-ondersteunde gebruikerskenmerken worden beschouwd als vaste tekenreeksen, bijvoorbeeld [Postcode].

- Extensiekenmerken en aangepaste kenmerken worden niet ondersteund.

Het wordt aangeraden kenmerken te gebruiken met waarden die voor alle gebruikers in uw organisatie zijn ingevuld en geen kenmerken met lange waarden te gebruiken.

### <a name="things-to-look-out-for"></a>Wat u moet nakijken voor

- Bij het maken van beleid mag de totale tekenreekslengte van voor- en achtervoegsel niet langer zijn dan 53 tekens.

- Voor- en achtervoegsels kunnen speciale tekens bevatten die voor de groepsnaam en de groepsalias worden ondersteund. Wanneer de voorvoegsels en achtervoegsels speciale tekens bevatten die niet zijn toegestaan in de groepsalias, worden deze alleen toegepast op de naam van de groep. In dit geval zouden de voor- en achtervoegsels die op de groepsnaam worden toegepast verschillen van degene die op de groepsalias worden toegepast.

  > [!NOTE]
  > Een punt (.) of een afbreekstreepje (-) is toegestaan op een willekeurige plaats in de naam van de groep, behalve aan het begin of einde van de naam. Een onderstrepingsteken (_) is op een willekeurige plaats in de naam van de groep toegestaan, waaronder aan het begin of einde van de naam.

- Als u gebruikmaakt van met Yammer Office 365 gekoppelde groepen, vermijdt u de volgende tekens in uw naamgevingsbeleid: @, \# , \[ , \] , \<, and \> . Als u de tekens in het naamgevingsbeleid gebruikt, kunnen reguliere Yammer-gebruikers geen groepen maken.

> [!Tip]
> - Gebruik korte tekenreeksen als suffix.
> - Gebruik kenmerken met waarden.
> - Te niet te veel niet, maar de lengte van de totale naam mag maximaal 264 tekens bevatten.
> - Upload uw organisatie specifiek geblokkeerde woorden om het gebruik te beperken.

## <a name="custom-blocked-words"></a>Aangepaste, geblokkeerde woorden

U kunt een door komma's gescheiden lijst met geblokkeerde woorden invoeren die worden geblokkeerd in groepsnamen en aliassen.

Er worden geen zoekresultaten van subtekenreeksen uitgevoerd; met name een exacte overeenkomst tussen de ingevoerde naam van de gebruiker en de aangepaste, geblokkeerde woorden is vereist om een fout te activeren.

**Let op**:

- De geblokkeerde woorden zijn hoofdlettergevoelig.

- Als er een geblokkeerd woord wordt ingevoerd, wordt een foutbericht met het geblokkeerde woord erin weergegeven.

- Er bestaan geen restricties op tekens in het gebruikte geblokkeerde woord.

- Het aantal woorden in 5000 kan worden ingesteld op geblokkeerde woorden.

## <a name="admin-override"></a>Overschrijven door beheerder

Sommige beheerders worden vrijgemaakt van deze polissen voor alle bewerkings-en eindpunten van de groep, zodat ze groepen met deze geblokkeerde woorden en met hun naamconventies kunnen maken. Hierna volgt een lijst van beheerdersrollen die zijn vrijgesteld van het groepsnaambeleid.

- Globale beheerder

- Partnerondersteuning voor laag 1

- Partnerondersteuning voor laag 2

- Beheerder van het gebruikersaccount

## <a name="how-to-set-up-the-naming-policy"></a>Het naamgevingsbeleid instellen

Een naamgevingsbeleid instellen:

1. Klik in [Azure Active Directory](https://aad.portal.azure.com)onder **beheren** op **groepen**.
2. Klik onder **instellingen** op **naam beleid**.
3. Kies het tabblad **naam beleid voor groepen** .
4. Kies onder **huidig beleid**, als u een voor-of achtervoegsel of beide wilt vereisen, en schakel de gewenste selectievakjes in.
5. Kies voor elke regel een van de **kenmerken** en de **tekenreeks** en geef vervolgens het kenmerk of de tekenreeks op.
6. Wanneer u de voorvoegsels en achtervoegsels hebt toegevoegd die u nodig hebt, klikt u op **Opslaan**.

![Schermafbeelding van de instellingen voor het wijzigen van de naam van een Groepsbeleid in azure Active Directory](../media/groups-naming-policy-azure.png)

## <a name="related-topics"></a>Verwante onderwerpen

[Stapsgewijze planning voor samenwerking](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Uw plan voor samenwerking maken](collaboration-governance-first.md)

[Azure Active Directory-cmdlets voor het configureren van instellingen voor groepen](https://go.microsoft.com/fwlink/?linkid=868341)
