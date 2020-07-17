---
title: Naamgevingsbeleid voor groepen
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
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
- MST160
- MET150
- MOE150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: Meer informatie over het maken van een naamgevingsbeleid voor Microsoft 365-groepen.
ms.openlocfilehash: ae216d0d8f3319e9633d300d785b4a8c31702798
ms.sourcegitcommit: 3274b65a3932288721541d2b3fa5ecbf4c51e1ab
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/11/2020
ms.locfileid: "44702546"
---
# <a name="groups-naming-policy"></a>Naamgevingsbeleid voor groepen

U gebruikt een beleid voor groepsnaamgeving om een consistente naamgevingsstrategie af te dwingen voor groepen die zijn gemaakt door gebruikers in uw organisatie. Met een naamgevingsbeleid kunnen u en uw gebruikers de functie van de groep, het lidmaatschap, de geografische regio of de groep identificeren. Het naamgevingsbeleid kan ook helpen bij het categoriseren van groepen in het adresboek. U het beleid gebruiken om te voorkomen dat specifieke woorden worden gebruikt in groepsnamen en aliassen.

Het naamgevingsbeleid wordt toegepast op groepen die zijn gemaakt voor alle groepswerkbelastingen (zoals Outlook, Microsoft Teams, SharePoint, Planner, Yammer, enz.). Het wordt toegepast op zowel de groepsnaam als de groepsalias. Het wordt toegepast wanneer een gebruiker een groep maakt en wanneer groepsnaam of alias wordt bewerkt voor een bestaande groep.

> [!TIP]
> Een microsoft 365-groepnaamgevingsbeleid is alleen van toepassing op Microsoft 365-groepen. Het is niet van toepassing op distributiegroepen die zijn gemaakt in Exchange Online. Zie Een [naamgevingsbeleid voor distributiegroepen maken als](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy)u een naamgevingsbeleid voor distributiegroepen wilt maken.

Het groepsnaambeleid bestaat uit de volgende functie:

- **Voorvoegsel-achtervoegsel naamgevingsbeleid**: U voorvoegsels of achtervoegsels gebruiken om de naamgevingsconventie van groepen te definiëren (bijvoorbeeld: US \_ My Group \_ Engineering). De voorvoegsels/achtervoegsels kunnen bestaan uit vaste tekenreeksen of gebruikerskenmerken (zoals [Department]) die worden vervangen op basis van de gebruiker die de groep maakt.

- **Aangepaste geblokkeerde woorden:** u een set geblokkeerde woorden uploaden die specifiek zijn voor uw organisatie en die worden geblokkeerd in groepen die door gebruikers zijn gemaakt. (Bijvoorbeeld: "CEO, Payroll, HR").

## <a name="licensing-requirements"></a>Vergunningsvereisten

Als u azure AD-naamgevingsbeleid voor Microsoft 365-groepen gebruikt, moet u een Azure Active Directory Premium P1-licentie of Azure AD AD EDU-licentie voor elke unieke gebruiker (inclusief gasten) die lid is van een of meer Microsoft 365-groepen, beschikken, maar niet noodzakelijkerwijs toewijzen.

Dit is ook vereist voor de beheerder die het naamgevingsbeleid groepen maakt.

## <a name="prefix-suffix-naming-policy"></a>Beleid voor naamgevingsbeleid voor voorvoegsel

Voorvoegsels en achtervoegsels kunnen vaste tekenreeksen of gebruikerskenmerken zijn.

### <a name="fixed-strings"></a>Vaste tekenreeksen

U korte tekenreeksen gebruiken waarmee u groepen onderscheiden in de GAL- en linkernavigatie van de groepsworkloads. Enkele van de gemeenschappelijke voorvoegsels achtervoegsels zijn zoekwoorden als 'Grp \_ Name' , \# 'Name', \_ 'Name'

### <a name="attributes"></a>Kenmerken

U kenmerken gebruiken waarmee u bepalen wie de groep heeft gemaakt, zoals [Afdeling] en waar deze is gemaakt vanuit like [Land].

|||
|:-----|:-----|
|**Voorbeelden**|Beleid = "GRP [GroupName] [Department]"|
||Afdeling van de gebruiker = Engineering|
||Gemaakte groepsnaam = "GRP My Group Engineering"|

Ondersteunde Azure Active Directory (Azure AD) kenmerken zijn [Afdeling], [Bedrijf], [Office], [StateOrProvince], [CountryOrRegion], en [Titel].

- Niet-ondersteunde gebruikerskenmerken worden als vaste tekenreeksen beschouwd. Bijvoorbeeld "[postalCode]"

- Extensiekenmerken en aangepaste kenmerken worden niet ondersteund.

Het wordt aangeraden kenmerken te gebruiken met waarden die voor alle gebruikers in uw organisatie zijn ingevuld en geen kenmerken met lange waarden te gebruiken.

### <a name="things-to-look-out-for"></a>Dingen om op te letten

- Bij het maken van beleid mag de totale tekenreekslengte van voor- en achtervoegsel niet langer zijn dan 53 tekens.

- Voor- en achtervoegsels kunnen speciale tekens bevatten die voor de groepsnaam en de groepsalias worden ondersteund. Wanneer de voorvoegsels en achtervoegsels speciale tekens bevatten die niet zijn toegestaan in de groepsalias, worden ze alleen toegepast op de groepsnaam. In dit geval zouden de voor- en achtervoegsels die op de groepsnaam worden toegepast verschillen van degene die op de groepsalias worden toegepast.

  > [!NOTE]
  > Een periode (.) of een koppelteken (-) is overal in de groepsnaam toegestaan, behalve aan het begin of einde van de naam. Een underscore (_) is overal in de groepsnaam toegestaan, ook aan het begin of einde van de naam.

- Als u verbonden yammer Microsoft 365-verbonden groepen gebruikt, vermijd dan het gebruik van de volgende tekens in uw naamgevingsbeleid: @, \# , , , , \[ \] \<, and \> . Als deze tekens in het naamgevingsbeleid staan, kunnen gewone Yammer-gebruikers geen groepen maken.

## <a name="custom-blocked-words"></a>Aangepaste geblokkeerde woorden

U een lijst met geblokkeerde woorden invoeren die worden geblokkeerd in groepsnamen en aliassen.

Er worden geen subreekszoekopdrachten uitgevoerd; specifiek, een exacte overeenkomst tussen de gebruiker ingevoerde naam en de aangepaste geblokkeerde woorden is vereist om een fout te activeren. Sub-string zoeken wordt niet gedaan, zodat gebruikers kunnen een aantal van de gemeenschappelijke woorden zoals 'Klasse' te gebruiken, zelfs als 'kont' is een geblokkeerd woord.

**Dingen om op te letten:**

- De geblokkeerde woorden zijn hoofdlettergevoelig.

- Als er een geblokkeerd woord wordt ingevoerd, wordt een foutbericht met het geblokkeerde woord erin weergegeven.

- Er bestaan geen restricties op tekens in het gebruikte geblokkeerde woord.

- Er is een limiet van 5000 woorden die kunnen worden ingesteld als geblokkeerde woorden.

## <a name="admin-override"></a>Overschrijven door beheerder

Bepaalde beheerders zijn voor alle groepswerkbelastingen en eindpunten vrijgesteld van dit beleid, zodat ze groepen kunnen maken met deze geblokkeerde woorden en met eigen naamgevingsconventies. Hierna volgt een lijst van beheerdersrollen die zijn vrijgesteld van het groepsnaambeleid.

- Globale beheerder

- Partnerondersteuning voor laag 1

- Partnerondersteuning voor laag 2

- Beheerder van het gebruikersaccount

- Schrijvers van adreslijsten

## <a name="how-to-set-up-the-naming-policy"></a>Het naamgevingsbeleid instellen

Ga als u een naamgevingsbeleid instellen:

1. Klik in [Azure Active Directory](https://aad.portal.azure.com)onder **Beheren**op **Groepen**.
2. Klik **onder Instellingen**op **Naamgevingsbeleid**.
3. Kies het tabblad **Groepnaambeleid.**
4. Kies onder **Huidig beleid**of u een voorvoegsel of achtervoegsel of beide nodig wilt hebben en schakel de juiste selectievakjes in.
5. Kies tussen **Kenmerk** en **tekenreeks** voor elke regel en geef vervolgens het kenmerk of de tekenreeks op.
6. Wanneer u de voorvoegsels en achtervoegsels hebt toegevoegd die u nodig hebt, klikt u op **Opslaan.**

![Schermafbeelding van de beleidsinstellingen voor groepen in Azure Active Directory](../../media/groups-naming-policy-azure.png)

> [!NOTE]
> StaffHub-teams volgen het naamgevingsbeleid niet, maar de onderliggende Microsoft 365-groep wel. StaffHub-teamnaam past de voorvoegsels en achtervoegsels niet toe en controleert niet op aangepaste geblokkeerde woorden. Maar StaffHub past wel de voorvoegsels en achtervoegsels toe en verwijdert geblokkeerde woorden uit de onderliggende Microsoft 365-groep.

## <a name="more-articles-on-naming-policy"></a>Meer artikelen over naamgevingsbeleid

[Een naamgevingsbeleid voor Microsoft 365-groepen afdwingen in Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=868340)

[Azure Active Directory-cmdlets voor het configureren van groepsinstellingen](https://go.microsoft.com/fwlink/?linkid=868341)
