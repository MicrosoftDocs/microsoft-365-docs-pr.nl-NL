---
title: Microsoft 365 naamgevingsbeleid voor groepen
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
recommendations: false
description: Meer informatie over het maken van een naamgevingsbeleid voor Microsoft 365 groepen.
ms.openlocfilehash: 5ab5f252e2b81470413b4efea17b131613aabc18
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538169"
---
# <a name="microsoft-365-groups-naming-policy"></a>Microsoft 365 naamgevingsbeleid voor groepen

U kunt een naamgevingsbeleid voor groepen gebruiken om een consistente naamgevingsstrategie af te dwingen voor groepen die zijn gemaakt door gebruikers in uw organisatie. Een naamgevingsbeleid kan u en uw gebruikers helpen bij het identificeren van de functie van de groep, het lidmaatschap, de geografische regio of de persoon die de groep heeft gemaakt. Het naamgevingsbeleid kan ook helpen bij het categoriseren van groepen in het adresboek. U kunt het beleid gebruiken om te blokkeren dat specifieke woorden worden gebruikt in groepsnamen en aliassen.

Het naamgevingsbeleid wordt toegepast op groepen die worden gemaakt in alle groepen werkbelastingen (zoals Outlook, Microsoft Teams, SharePoint, Planner, Yammer, enzovoort). Deze wordt toegepast op zowel de groepsnaam als de groepsalias. Het wordt ook toegepast wanneer een gebruiker een groep maakt en wanneer de groepsnaam, alias, beschrijving of avatar wordt bewerkt voor een bestaande groep.

> [!TIP]
> Een Microsoft 365 groepsbeleid is alleen van toepassing op Microsoft 365 groepen. Het is niet van toepassing op distributiegroepen die zijn gemaakt in Exchange Online. Zie Een naamgevingsbeleid voor distributiegroepen maken als u een [naamgevingsbeleid voor](/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy)distributiegroepen wilt maken.

Het groepsnaambeleid bestaat uit de volgende functie:

- **Naamgevingsbeleid** voor voorvoegsel: u kunt voorvoegsels of achtervoegsels gebruiken om de naamgevingsconventie van groepen te definiëren (bijvoorbeeld: 'US \_ My Group \_ Engineering'). De voorvoegsels/achtervoegsels kunnen bestaan uit vaste tekenreeksen of gebruikerskenmerken (zoals [Department]) die worden vervangen op basis van de gebruiker die de groep maakt.

- **Aangepaste geblokkeerde woorden:** u kunt een set geblokkeerde woorden uploaden die specifiek zijn voor uw organisatie en die worden geblokkeerd in groepen die door gebruikers zijn gemaakt. (Bijvoorbeeld: 'CEO, Salarisadministratie, HR').

## <a name="licensing-requirements"></a>Licentievereisten

Voor het gebruik van Azure AD-naamgevingsbeleid voor Microsoft 365 Groepen moet u een Azure Active Directory Premium P1-licentie of Azure AD Basic EDU-licentie toewijzen voor elke unieke gebruiker (inclusief gasten) die lid is van een of meer Microsoft 365-groepen.

Dit is ook vereist voor de beheerder die het naamgevingsbeleid voor groepen maakt.

## <a name="prefix-suffix-naming-policy"></a>Prefix-Suffix naamgevingsbeleid

Voorvoegsels en achtervoegsels kunnen vaste tekenreeksen of gebruikerskenmerken zijn.

### <a name="fixed-strings"></a>Vaste tekenreeksen

U kunt korte tekenreeksen gebruiken om groepen te onderscheiden in de gal en linkernavigatie van de groepswerkbelastingen. Enkele algemene voorvoegsels zijn trefwoorden zoals 'Grp \_ Name', \# 'Name', ' Name' en \_ 'Name'

### <a name="attributes"></a>Kenmerken

U kunt kenmerken gebruiken om te bepalen wie de groep heeft gemaakt, zoals [Afdeling] en waar deze is gemaakt, zoals [Land].

Voorbeelden:

- Beleid = "GRP [GroupName] [Department]"
- Afdeling van de gebruiker = Engineering
- Gemaakte groepsnaam = "GRP My Group Engineering"

Ondersteunde Azure Active Directory (Azure AD) kenmerken zijn [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion] en [Title].

- Niet-ondersteunde gebruikerskenmerken worden beschouwd als vaste tekenreeksen, bijvoorbeeld [postcode].

- Extensiekenmerken en aangepaste kenmerken worden niet ondersteund.

Het wordt aangeraden kenmerken te gebruiken met waarden die voor alle gebruikers in uw organisatie zijn ingevuld en geen kenmerken met lange waarden te gebruiken.

### <a name="things-to-look-out-for"></a>Dingen om op te kijken

- Bij het maken van beleid mag de totale tekenreekslengte van voor- en achtervoegsel niet langer zijn dan 53 tekens.

- Voor- en achtervoegsels kunnen speciale tekens bevatten die voor de groepsnaam en de groepsalias worden ondersteund. Wanneer de voor- en achtervoegsels speciale tekens bevatten die niet zijn toegestaan in de groepsalias, worden ze alleen toegepast op de groepsnaam. In dit geval zouden de voor- en achtervoegsels die op de groepsnaam worden toegepast verschillen van degene die op de groepsalias worden toegepast.

  > [!NOTE]
  > Een punt (.) of een afbreekstreester (-) is overal in de groepsnaam toegestaan, behalve aan het begin of einde van de naam. Een onderstrepingsteken (_) is overal in de groepsnaam toegestaan, ook aan het begin of einde van de naam.

- Als u Yammer Office 365 groepen gebruikt, vermijdt u het gebruik van de volgende tekens in uw naamgevingsbeleid: @, \# , \[ , , \] \<, and \> . Als deze tekens in het naamgevingsbeleid staan, kunnen Yammer gebruikers geen groepen maken.

> [!Tip]
> - Gebruik korte tekenreeksen als achtervoegsel.
> - Gebruik kenmerken met waarden.
> - Wees niet te creatief, de totale naamlengte heeft een maximum van 264 tekens.
> - Upload uw organisatie specifieke geblokkeerde woorden om het gebruik te beperken.

## <a name="custom-blocked-words"></a>Aangepaste geblokkeerde woorden

U kunt een door komma's gescheiden lijst met geblokkeerde woorden invoeren die worden geblokkeerd in groepsnamen en aliassen.

Er worden geen subreekszoekingen uitgevoerd. een exacte overeenkomst tussen de ingevoerde naam van de gebruiker en de aangepaste geblokkeerde woorden is vereist om een fout te activeren.

**Dingen om op te kijken:**

- De geblokkeerde woorden zijn hoofdlettergevoelig.

- Als er een geblokkeerd woord wordt ingevoerd, wordt een foutbericht met het geblokkeerde woord erin weergegeven.

- Er bestaan geen restricties op tekens in het gebruikte geblokkeerde woord.

- Er is een limiet van 5000 woorden die kunnen worden ingesteld als geblokkeerde woorden.

## <a name="admin-override"></a>Overschrijven door beheerder

Sommige beheerders zijn vrijgesteld van dit beleid, voor alle groepswerkbelastingen en eindpunten, zodat ze groepen kunnen maken met deze geblokkeerde woorden en met de gewenste naamgevingsconventies. Hierna volgt een lijst van beheerdersrollen die zijn vrijgesteld van het groepsnaambeleid.

- Globale beheerder

- Partnerondersteuning voor laag 1

- Partnerondersteuning voor laag 2

- Beheerder van het gebruikersaccount

## <a name="how-to-set-up-the-naming-policy"></a>Het naamgevingsbeleid instellen

Een naamgevingsbeleid instellen:

1. Klik [Azure Active Directory](https://aad.portal.azure.com)onder **Beheren** op **Groepen.**
2. Klik **onder Instellingen** op **Naamgevingsbeleid**.
3. Kies het **tabblad Groepnaamgevingsbeleid.**
4. Kies **onder Huidig** beleid of u een voorvoegsel of achtervoegsel of beide wilt vereisen en schakel de juiste selectievakjes in.
5. Kies tussen **Kenmerk** en **Tekenreeks** voor elke regel en geef vervolgens het kenmerk of de tekenreeks op.
6. Wanneer u de voor- en achtervoegsels hebt toegevoegd die u nodig hebt, klikt u op **Opslaan.**

![Schermafbeelding van de instellingen voor het naamgevingsbeleid van groepen in Azure Active Directory](../media/groups-naming-policy-azure.png)

## <a name="related-topics"></a>Verwante onderwerpen

[Planning van samenwerkingsbeheer stap voor stap](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Uw samenwerkingsbeheerplan maken](collaboration-governance-first.md)

[Azure Active Directory cmdlets voor het configureren van groepsinstellingen](/azure/active-directory/enterprise-users/groups-settings-cmdlets)