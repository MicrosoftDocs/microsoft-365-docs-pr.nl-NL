---
title: Voorbereidingen treffen voor adreslijstsynchronisatie om Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Hier wordt beschreven hoe u gebruikers kunt voorbereiden op Microsoft 365 gebruik te maken van adreslijstsynchronisatie en de voordelen op lange termijn van het gebruik van deze methode.
ms.openlocfilehash: ee6cfe9adfe029e620d2465f08a3fbe1e9290503
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229765"
---
# <a name="prepare-for-directory-synchronization-to-microsoft-365"></a>Voorbereidingen treffen voor adreslijstsynchronisatie om Microsoft 365

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

De voordelen voor hybride identiteits- en adreslijstsynchronisatie van uw organisatie zijn:

- De beheerprogramma's in uw organisatie verminderen
- Optioneel een enkel aanmeldingsscenario inschakelen
- Accountwijzigingen automatiseren in Microsoft 365

Zie hybride identiteit met Azure Active Directory [(Azure AD)](/azure/active-directory/hybrid/whatis-hybrid-identity) en hybride identiteit voor Microsoft 365 voor meer informatie over de voordelen van het gebruik van [adreslijstsynchronisatie.](plan-for-directory-synchronization.md)

Adreslijstsynchronisatie vereist echter planning en voorbereiding om ervoor te zorgen dat uw AD DS (Active Directory Domain Services) wordt gesynchroniseerd met de Azure AD-tenant van uw Microsoft 365-abonnement met een minimum aan fouten.

Volg deze stappen om de beste resultaten te krijgen.

## <a name="1-directory-cleanup-tasks"></a>1. Adreslijst opschoningstaken

Voordat u uw AD DS synchroniseert met uw Azure AD-tenant, moet u uw AD DS ops schonen.

> [!IMPORTANT]
> Als u geen AD DS-opschoning voert voordat u synchroniseert, kan dit leiden tot een aanzienlijke negatieve invloed op het implementatieproces. Het kan dagen of zelfs weken duren om door de cyclus van adreslijstsynchronisatie te lopen, fouten te identificeren en opnieuw te synchroniseren.

Voltooi in uw AD DS de volgende opruimtaken voor elk gebruikersaccount dat een licentie Microsoft 365 gebruikersaccount:

1. Controleer een geldig en uniek e-mailadres in het **kenmerk proxyAddresses.**

2. Verwijder dubbele waarden in het **kenmerk proxyAddresses.**

3. Zorg indien mogelijk voor een geldige en unieke waarde voor het **userPrincipalName-kenmerk** in het **gebruikersobject** van de gebruiker. Zorg ervoor dat de AD DS UPN overeenkomt met de Azure AD UPN voor de beste synchronisatieervaring. Als een gebruiker geen waarde heeft voor het **kenmerk userPrincipalName,** moet het **gebruikersobject** een geldige en unieke waarde bevatten voor het **kenmerk sAMAccountName.** Verwijder eventuele dubbele waarden in het **userPrincipalName-kenmerk.**

4. Zorg ervoor dat de informatie in de volgende kenmerken van het AD DS-gebruikersaccount correct is voor optimaal gebruik van de algemene adreslijst (GAL):

   - givenName
   - achternaam
   - displayName
   - Functie
   - Department
   - Office
   - Zakelijk nummer
   - Mobiel nummer
   - Faxnummer
   - Adres van straat
   - Plaats
   - Provincie
   - Postcode
   - Land of regio

## <a name="2-directory-object-and-attribute-preparation"></a>2. Voorbereiding van adreslijstobjecten en kenmerken

Succesvolle adreslijstsynchronisatie tussen uw AD DS en Microsoft 365 vereist dat uw AD DS-kenmerken goed zijn voorbereid. U moet er bijvoorbeeld voor zorgen dat bepaalde tekens niet worden gebruikt in bepaalde kenmerken die worden gesynchroniseerd met de Microsoft 365 omgeving. Onverwachte tekens leiden er niet toe dat adreslijstsynchronisatie mislukt, maar kan een waarschuwing retourneren. Ongeldige tekens zorgen ervoor dat adreslijstsynchronisatie mislukt.

Adreslijstsynchronisatie mislukt ook als sommige AD DS-gebruikers een of meer dubbele kenmerken hebben. Elke gebruiker moet unieke kenmerken hebben.

De kenmerken die u moet voorbereiden, worden hier weergegeven:

- **displayName**

  - Als het kenmerk bestaat in het gebruikersobject, wordt het gesynchroniseerd met Microsoft 365.
  - Als dit kenmerk bestaat in het gebruikersobject, moet er een waarde voor het object zijn. Dat wil zeggen dat het kenmerk niet leeg mag zijn.
  - Maximum aantal tekens: 256

- **givenName**

  - Als het kenmerk bestaat in het gebruikersobject, wordt het gesynchroniseerd met Microsoft 365, maar Microsoft 365 het niet vereist of gebruikt.
  - Maximum aantal tekens: 64

- **e-mail**

  - De kenmerkwaarde moet uniek zijn in de adreslijst.

    > [!NOTE]
    > Als er dubbele waarden zijn, wordt de eerste gebruiker met de waarde gesynchroniseerd. Volgende gebruikers worden niet weergegeven in Microsoft 365. U moet de waarde in Microsoft 365 of beide waarden in AD DS wijzigen, zodat beide gebruikers in de Microsoft 365.

- **mailNickname** (Exchange alias)

  - De kenmerkwaarde kan niet beginnen met een punt (.).
  - De kenmerkwaarde moet uniek zijn in de adreslijst.

    > [!NOTE]
    > Onderstrepingstekens ("_") in de gesynchroniseerde naam geven aan dat de oorspronkelijke waarde van dit kenmerk ongeldige tekens bevat. Zie het aliaskenmerk [Exchange meer informatie](/powershell/module/exchange/set-mailbox)over dit kenmerk.
    >

- **proxyAddresses**

  - Kenmerk met meerdere waarden
  - Maximum aantal tekens per waarde: 256
  - De kenmerkwaarde mag geen spatie bevatten.
  - De kenmerkwaarde moet uniek zijn in de adreslijst.
  - Ongeldige tekens: \< \> ( ) ; , [ ] "

    Houd er rekening mee dat de ongeldige tekens van toepassing zijn op de tekens na het type scheidingsteken en ':', zodat SMTP:User@contso.com is toegestaan, maar SMTP:user:M@contoso.com niet.

    > [!IMPORTANT]
    > Alle SMTP-adressen (Simple Mail Transport Protocol) moeten voldoen aan de standaarden voor e-mailberichten. Verwijder dubbele of ongewenste adressen als deze bestaan.

- **sAMAccountName**

  - Maximum aantal tekens: 20
  - De kenmerkwaarde moet uniek zijn in de adreslijst.
  - Ongeldige tekens: [ \ " | , / : \< \> + = ; ? \* ']
  - Als een gebruiker een ongeldig **sAMAccountName-kenmerk** heeft, maar een geldig **userPrincipalName-kenmerk** heeft, wordt het gebruikersaccount gemaakt in Microsoft 365.
  - Als zowel **sAMAccountName** als **userPrincipalName** ongeldig zijn, moet het AD DS **userPrincipalName-kenmerk** worden bijgewerkt.

- **sn** (achternaam)

  - Als het kenmerk bestaat in het gebruikersobject, wordt het gesynchroniseerd met Microsoft 365, maar Microsoft 365 het niet vereist of gebruikt.

- **targetAddress**

    Het is vereist dat het **targetAddress-kenmerk** (bijvoorbeeld SMTP:tom@contoso.com) dat voor de gebruiker wordt ingevuld, moet worden weergegeven in de Microsoft 365 GAL. In scenario's voor berichtenmigratie van derden is hiervoor de Microsoft 365 voor de AD DS vereist. De Microsoft 365 schemaextensie voegt ook andere nuttige kenmerken toe om Microsoft 365 objecten te beheren die worden ingevuld met behulp van een hulpprogramma voor adreslijstsynchronisatie van AD DS. Het **msExchHideFromAddressLists-kenmerk** voor het beheren van verborgen postvakken of distributiegroepen wordt bijvoorbeeld toegevoegd.

  - Maximum aantal tekens: 256
  - De kenmerkwaarde mag geen spatie bevatten.
  - De kenmerkwaarde moet uniek zijn in de adreslijst.
  - Ongeldige tekens: \ \< \> ( ) ; , [ ] "
  - Alle SMTP-adressen (Simple Mail Transport Protocol) moeten voldoen aan de standaarden voor e-mailberichten.

- **userPrincipalName**

  - Het **userPrincipalName-kenmerk** moet zich in de aanmeldingsindeling voor internetstijl hebben, waarbij de gebruikersnaam wordt gevolgd door het at sign (@) en een domeinnaam: bijvoorbeeld user@contoso.com. Alle SMTP-adressen (Simple Mail Transport Protocol) moeten voldoen aan de standaarden voor e-mailberichten.
  - Het maximum aantal tekens voor het **userPrincipalName-kenmerk** is 113. Een bepaald aantal tekens is voor en na het bijteken (@) als volgt toegestaan:
  - Maximum aantal tekens voor de gebruikersnaam die zich vóór het bijteken (@): 64
  - Maximum aantal tekens voor de domeinnaam na het bijteken (@): 48
  - Ongeldige tekens: \ % &amp; \* + / = ? { } | \< \> ( ) ; : , [ ] "
  - Tekens toegestaan: A – Z, a - z, 0 – 9, ' . - _ ! # ^ ~
  - Letters met diakritische tekens, zoals umlauts, accenten en tildes, zijn ongeldige tekens.
  - Het @-teken is vereist voor elke **gebruikerPrincipalName-waarde.**
  - Het @-teken kan niet het eerste teken zijn in elke **gebruikerPrincipalName-waarde.**
  - De gebruikersnaam kan niet eindigen met een punt (.), een ampersand ( &amp; ), een spatie of een bijteken (@).
  - De gebruikersnaam mag geen spaties bevatten.
  - Routable domains must be used; lokale of interne domeinen kunnen bijvoorbeeld niet worden gebruikt.
  - Unicode wordt geconverteerd naar onderstrepingstekens.
  - **userPrincipalName** mag geen dubbele waarden in de adreslijst bevatten.

## <a name="3-prepare-the-userprincipalname-attribute"></a>3. Het userPrincipalName-kenmerk voorbereiden

Active Directory is zo ontworpen dat eindgebruikers in uw organisatie zich kunnen aanmelden bij uw adreslijst met **sAMAccountName** of **userPrincipalName.** Op dezelfde manier kunnen eindgebruikers zich aanmelden bij Microsoft 365 met de gebruikersnaam (UPN) van hun werk- of schoolaccount. Adreslijstsynchronisatie probeert nieuwe gebruikers te maken in Azure Active Directory met dezelfde UPN als in uw AD DS. De UPN is opgemaakt als een e-mailadres.

In Microsoft 365 is de UPN het standaardkenmerk dat wordt gebruikt om het e-mailadres te genereren. Het is eenvoudig om **userPrincipalName** (in AD DS en in Azure AD) en het primaire e-mailadres in **proxyAddresses** op verschillende waarden in te stellen. Wanneer ze zijn ingesteld op verschillende waarden, kan er verwarring ontstaan voor beheerders en eindgebruikers.

U kunt deze kenmerken het beste uitlijnen om verwarring te voorkomen. Als u wilt voldoen aan de vereisten van één aanmelding met Ad FS 2.0 (Active Directory Federation Services), moet u ervoor zorgen dat de UPN's in Azure Active Directory en uw AD DS overeenkomen en een geldige domeinnaamruimte gebruiken.

## <a name="4-add-an-alternative-upn-suffix-to-ad-ds"></a>4. Een alternatief UPN-achtervoegsel toevoegen aan AD DS

Mogelijk moet u een alternatief UPN-achtervoegsel toevoegen om de bedrijfsreferenties van de gebruiker te koppelen aan de Microsoft 365 omgeving. Een UPN-achtervoegsel is het deel van een UPN rechts van het @-teken. UPN's die worden gebruikt voor een enkele aanmelding kunnen letters, cijfers, perioden, streepjes en onderstrepingstekens bevatten, maar geen andere typen tekens.

Zie Voorbereiden op [adreslijstsynchronisatie](https://go.microsoft.com/fwlink/p/?LinkId=525430)voor meer informatie over het toevoegen van een alternatief UPN-achtervoegsel aan Active Directory.

## <a name="5-match-the-ad-ds-upn-with-the-microsoft-365-upn"></a>5. Koppel de AD DS UPN aan de Microsoft 365 UPN

Als u adreslijstsynchronisatie al hebt ingesteld, komt de UPN voor Microsoft 365 van de gebruiker mogelijk niet overeen met de AD DS UPN van de gebruiker die is gedefinieerd in uw AD DS. Dit kan gebeuren wanneer aan een gebruiker een licentie is toegewezen voordat het domein is geverifieerd. Als u dit wilt oplossen, [gebruikt u PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396730) om dubbele UPN op te lossen om de UPN van de gebruiker bij te werken om ervoor te zorgen dat de Microsoft 365 UPN overeenkomt met de zakelijke gebruikersnaam en het domein. Als u de UPN in de AD DS bij wilt werken en deze wilt synchroniseren met de Azure Active Directory-identiteit, moet u de licentie van de gebruiker in Microsoft 365 verwijderen voordat u de wijzigingen in AD DS aan gaat brengen.

Zie Ook [Een niet-routable domain (zoals .local domain) voorbereiden voor adreslijstsynchronisatie.](prepare-a-non-routable-domain-for-directory-synchronization.md)

## <a name="next-steps"></a>Volgende stappen

Zie Adreslijstsynchronisatie instellen als u stappen 1 tot en met 5 [hierboven hebt uitgevoerd.](set-up-directory-synchronization.md)
