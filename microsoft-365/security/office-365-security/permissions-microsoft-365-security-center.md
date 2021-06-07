---
title: Machtigingen in het Microsoft 365-beveiligingscentrum
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
ms.audience: Admin
ms.topic: article
audience: Admin
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Beheerders kunnen informatie krijgen over het beheren van machtigingen in het Microsoft 365-beveiligingscentrum voor alle taken met betrekking tot beveiliging.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9c2d28510c25290921084e6a238fa8c781c35624
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772465"
---
# <a name="permissions-in-the-microsoft-365-security-center"></a>Machtigingen in het Microsoft 365-beveiligingscentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

U moet beveiligingsscenario's beheren voor alle Microsoft 365-services. En u hebt de flexibiliteit nodig om de juiste beheerdersmachtigingen aan de juiste personen uw organisatie te geven.

Het Microsoft 365-beveiligingscentrum op <https://security.microsoft.com> biedt ondersteuning voor het rechtstreeks beheren van machtigingen voor gebruikers die beveiligingstaken uitvoeren in Microsoft 365. Door het beveiligingscentrum te gebruiken voor het beheren van machtigingen, kunt u machtigingen centraal beheren voor alle taken met betrekking tot beveiliging.

Ga naar **Machtigingen en rollen** of <https://security.microsoft.com/securitypermissions> om machtigingen in het beveiligingscentrum te beheren. U moet een **globale beheerder** zijn of lid zijn van de rollengroep **Organisatiebeheer** in het beveiligingscentrum. Met name de rol **Rollenbeheer** stelt gebruikers in staat om rollengroepen in het beveiligingscentrum te bekijken, te maken en te wijzigen. Standaard wordt die rol alleen toegewezen aan de rollengroep **Organisatiebeheer**.

## <a name="relationship-of-members-roles-and-role-groups"></a>Relatie van leden, rollen en rollengroepen

Machtigingen in het beveiligingscentrum zijn gebaseerd op het machtigingsmodel voor toegangsbeheer op basis van rollen (RBAC). RBAC is hetzelfde machtigingsmodel dat wordt gebruikt door de meeste Microsoft 365-services. Als u bekend bent met de machtigingsstructuur in deze services, zal het verlenen van machtigingen in het beveiligingscentrum u bekend voorkomen.

Een **rol** verleent de machtigingen om een reeks taken uit te voeren.

Een **rollengroep** is een set rollen waarmee personen hun werk kunnen doen in het beveiligingscentrum. De rollengroep Beheerders Aanvalssimulatie bevat bijvoorbeeld de rol Beheerder Aanvalssimulatie om alle aspecten van aanvalssimulatietraining te maken en te beheren.

Het beveiligingscentrum bevat standaard rollenroepen voor de meest voorkomende taken en functies die u moet toewijzen. Over het algemeen raden we u aan alleen individuele gebruikers als **leden** aan de standaard rollengroepen toe te voegen.

![Diagram met de relatie van rollengroepen met rollen en leden](../../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)

## <a name="roles-and-role-groups-in-the-security-center"></a>Rollen en rollengroepen in het beveiligingscentrum

De volgende typen rollen en rollengroepen zijn beschikbaar in **Machtigingen en rollen** in het beveiligingscentrum:

- **Microsoft Azure AD-rollen**: U kunt de rollen en toegewezen gebruikers weergeven, maar u kunt ze niet rechtstreeks in het beveiligingscentrum beheren. Azure AD-rollen zijn centrale rollen die machtigingen toewijzen voor **alle** Microsoft 365-services.

- **E-mail- en samenwerkingsrollen**: dit zijn dezelfde rollengroepen die beschikbaar zijn in het Beveiligings- en compliancecentrum, maar u kunt ze rechtstreeks in het beveiligingscentrum beheren. De machtigingen die u hier toewijst, zijn specifiek voor het Microsoft 365-beveiligingscentrum, het Microsoft 365-compliancecentrum en het Beveiligings- en compliancecentrum. Ze omvatten niet alle machtigingen die nodig zijn in andere Microsoft 365-werkbelastingen.

![Pagina Machtigingen & rollen in het Microsoft 365-beveiligingscentrum](../../media/m365-sc-permissions-and-roles-page.png)

### <a name="azure-ad-roles-in-the-security-center"></a>Microsoft Azure AD-rollen in het beveiligingscentrum

Wanneer u naar **E-mail- en samenwerkingsrollen** \> **Machtigingen en rollen** \> **Microsoft Azure AD-rollen** \> **Rollen** (of rechtstreeks naar <https://security.microsoft.com/aadpermissions>) gaat, ziet u de Microsoft Azure AD-rollen die in deze sectie worden beschreven.

Wanneer u een rol selecteert, verschijnt er een vervolgmenu met de beschrijving van de rol en de gebruikerstoewijzingen. Maar als u deze opdrachten wilt beheren, klikt u op **Leden beheren in Microsoft Azure AD** in het vervolgmenu.

![Koppeling voor het beheren van machtigingen in Azure Active Directory](../../media/permissions-manage-in-azure-ad-link.png)

Zie [Beheerdersrollen bekijken en toewijzen in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal) voor meer informatie.

<br>

****

|Rol|Beschrijving|
|---|---|
|**Globale beheerder**|Gebruikers met deze rol hebben toegang tot alle beheerfuncties in alle Microsoft 365-services. Alleen globale beheerders kunnen andere beheerdersrollen toewijzen. Zie [Globale beheerder/Bedrijfsbeheerder](/azure/active-directory/roles/permissions-reference#global-administrator--company-administrator) voor meer informatie.|
|**Beheerder van nalevingsgegevens**|Houd de gegevens van uw organisatie bij in Microsoft 365, zorg ervoor dat de organisatie beveiligd is en krijg inzicht in eventuele problemen om risico's te beperken. Zie [Beheerder van nalevingsgegevens](/azure/active-directory/roles/permissions-reference#compliance-data-administrator) voor meer informatie.|
|**Beheerder voor naleving**|Help uw organisatie bij de naleving van wettelijke vereisten, het beheren van eDiscovery-aanvragen en het beheren van beleidsregels voor gegevensbeheer met betrekking tot Microsoft 365-locaties, -identiteiten en -apps. Zie [Beheerder voor naleving](/azure/active-directory/roles/permissions-reference#compliance-administrator) voor meer informatie.|
|**Beveiligingsoperator**|Bekijk, onderzoek en reageer op actieve bedreigingen van uw Microsoft 365-gebruikers, -apparaten en -inhoud. Zie [Beveiligingsoperator](/azure/active-directory/roles/permissions-reference#security-operator) voor meer informatie.|
|**Beveiligingslezer**|Bekijk en onderzoek actieve bedreigingen voor uw Microsoft 365-gebruikers, -apparaten en -inhoud, maar u hebt (in tegenstelling tot de beveiligingsoperator) geen machtiging om te reageren door actie te ondernemen. Zie [Beveiligingslezer](/azure/active-directory/roles/permissions-reference#security-reader) voor meer informatie.|
|**Beveiligingsbeheerder**|Controleer de algehele beveiliging van uw organisatie door beveiligingsbeleid te beheren, de beveiligingsanalyse en rapporten in de Microsoft 365-producten te evalueren en op de hoogte te blijven van mogelijke dreigingen. Zie [Beveiligingsbeheerder](/azure/active-directory/roles/permissions-reference#security-administrator) voor meer informatie.|
|**Globale lezer**|De alleen-lezen versie van de rol **Globale beheerder**. Bekijk alle instellingen en administratieve informatie in Microsoft 365. Zie [Globale lezer](/azure/active-directory/roles/permissions-reference#global-reader) voor meer informatie.|
|**Beheerder voor aanvalssimulatie**|Creëer en beheer alle aspecten van het maken van [aanvalssimulaties](attack-simulation-training.md), het starten/plannen van een simulatie en het beoordelen van simulatieresultaten. Zie voor meer informatie de [Simulatiebeheerder voor aanvallen](/azure/active-directory/roles/permissions-reference#attack-simulation-administrator).|
|**Auteur nettolading aanvallen**|Maak nettoladingen voor aanvallen, maar start of plan ze niet. Zie voor meer informatie [Auteur nettolading aanvallen](/azure/active-directory/roles/permissions-reference#attack-payload-author).|
|

### <a name="email--collaboration-roles-in-the-security-center"></a>E-mail- en samenwerkingsrollen in het beveiligingscentrum

Wanneer u naar **E-mail- en samenwerkingsrollen** \> **Machtigingen en rollen** \> **E-mail- en samenwerkingsrollen** \> **Rollen** (of rechtstreeks naar <https://security.microsoft.com/emailandcollabpermissions>) gaat, ziet u dezelfde rollengroepen die beschikbaar zijn in het Beveiligings- en compliancecentrum.

Voor volledige informatie over deze rolgroepen, zie [Machtigingen in het Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md)

#### <a name="modify-email--collaboration-role-membership-in-the-security-center"></a>Lidmaatschap van E-mail- en samenwerkingsrollen wijzigen in het beveiligingscentrum

1. Ga in het beveiligingscentrum naar **E-mail- en samenwerkingsrollen** \> **Machtigingen en rollen** \> **E-mail- en samenwerkingsrollen** \> **Rollen**.

2. Selecteer op de pagina **Machtigingen** die wordt geopend de rollengroep die u wilt wijzigen in de lijst. U kunt op de kolomkop **Naam** klikken om de lijst op naam te sorteren, of u kunt op **Zoeken** ![Pictogram Zoeken](../../media/m365-cc-sc-search-icon.png) klikken om de rollengroep te vinden.

3. Klik in het vervolgmenu met details van rollengroep dat wordt weergegeven op **Bewerken** in het gedeelte **Leden**.

4. Voer een van de volgende stappen uit op de pagina **Leden kiezen bewerken** die wordt weergegeven:
   - Als er geen leden van de rollengroep zijn, klikt u op **Leden kiezen**.
   - Als er bestaande leden van de rollengroep zijn, klikt u op **Bewerken**

5. Voer een van de volgende stappen uit in het vervolgmenu **Leden kiezen** dat wordt weergegeven:

   - Klik op **Toevoegen**. Selecteer een of meer gebruikers in de lijst met gebruikers die wordt weergegeven. U kunt ook klikken op het ![Zoekpictogram](../../media/m365-cc-sc-search-icon.png) **Zoeken** om gebruikers te zoeken en te selecteren.

     Wanneer u de gebruikers hebt geselecteerd die u wilt toevoegen, klikt u op **Toevoegen**.

   - Klik op **Verwijderen**. Selecteer een of meer bestaande leden. U kunt ook klikken op het ![Zoekpictogram](../../media/m365-cc-sc-search-icon.png) **Zoeken** om leden te zoeken en te selecteren.

     Wanneer u de gebruikers hebt geselecteerd die u wilt verwijderen, klikt u op **Verwijderen**.

6. Klik in het vervolgmenu **Leden kiezen** op **Klaar**.

7. Klik op de pagina **Bewerken leden kiezen** op **Opslaan**.

8. Klik in het vervolgmenu met details van de rollengroep op **Klaar**.
