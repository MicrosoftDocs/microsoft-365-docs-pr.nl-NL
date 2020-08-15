---
title: Directory-synchronisatie voorbereiden op Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
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
description: In dit artikel wordt uitgelegd hoe u gebruikers kunt inrichten voor Microsoft 365 met behulp van adreslijstsynchronisatie en de lange termijn voordelen van het gebruik van deze methode.
ms.openlocfilehash: cf5afc05b8273974c069662c2b887092fdd20b96
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695725"
---
# <a name="prepare-for-directory-synchronization-to-microsoft-365"></a>Directory-synchronisatie voorbereiden op Microsoft 365

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Microsoft 365 Enterprise.*

De voordelen van Hybrid Identity en adreslijstsynchronisatie uw organisatie omvat:
  
- De beheerprogramma's in uw organisatie verminderen
- Optioneel scenario voor eenmalige aanmelding inschakelen
- Account wijzigingen automatiseren in Microsoft 365
    
Voor meer informatie over de voordelen van het gebruik van adreslijstsynchronisatie raadpleegt u [routekaart voor adreslijstsynchronisatie]( https://go.microsoft.com/fwlink/p/?LinkId=525398) en [Hybrid Identity voor Microsoft 365](plan-for-directory-synchronization.md).

Adreslijstsynchronisatie vereist echter planning en voorbereidingen om ervoor te zorgen dat uw Active Directory Domain Services (AD DS) wordt gesynchroniseerd met de Azure AD-Tenant (Azure Active Directory) van uw micro 365 Soft-abonnement met een minimum aan fouten. 

Voer de volgende stappen uit om de beste resultaten te voorkomen.
  
## <a name="1-directory-cleanup-tasks"></a>1. taken in de Directory opschonen

Voordat u de AD DS synchroniseert met een Azure AD-Tenant, moet u de AD DS opschonen.

> [!IMPORTANT]
> Als u het opruimen van AD DS niet uitvoert voordat u de synchronisatie uitvoert, kan er sprake zijn van een aanzienlijk negatief effect op het implementatieproces. Het kan dagen duren voor de adreslijstsynchronisatie, het identificeren van fouten en het opnieuw synchroniseren van een week. 
  
Voer in uw AD DS de volgende opschoningstaken uit voor elk gebruikersaccount waaraan een Microsoft 365-licentie is toegewezen:
  
1. Zorg voor een geldig en uniek e-mailadres in het **proxyAddresses** -kenmerk. 
  
2. Verwijder alle dubbele waarden in het kenmerk **proxyAddresses** . 
    
3.  Controleer indien mogelijk een geldige en unieke waarde voor het kenmerk **userPrincipalName** in het **gebruikers** object van de gebruiker. Voor de beste synchronisatie ervaring zorgt u ervoor dat de AD DS-UPN overeenkomt met de Azure AD-UPN. Als een gebruiker geen waarde heeft voor het kenmerk **userPrincipalName** , moet het **gebruikers** object een geldige en unieke waarde voor het kenmerk **sAMAccountName** bevatten. Verwijder alle dubbele waarden in het kenmerk **userPrincipalName** . 
    
4. Voor optimaal gebruik van de algemene adreslijst (GAL) zorgt u ervoor dat de informatie in de volgende kenmerken van het AD DS-gebruikersaccount correct is:
    
  - voor benaming
  - achternaam
  - Weergave
  - Functie
  - Department
  - Office
  - Zakelijk nummer
  - Mobiel nummer
  - Faxnummer
  - Adres
  - Plaats
  - Provincie
  - Post code
  - Land of regio
    
## <a name="2-directory-object-and-attribute-preparation"></a>2. mapobject en kenmerk voorbereiding

Als u wilt dat de adreslijstsynchronisatie mislukt tussen uw Active Directory-en Microsoft 365, moet u de kenmerken van de AD DS-kenmerken voorbereidingen hebben U moet bijvoorbeeld ervoor zorgen dat specifieke tekens niet worden gebruikt in bepaalde kenmerken die worden gesynchroniseerd met de Microsoft 365-omgeving. Onverwachte tekens zorgen er niet voor dat de adreslijstsynchronisatie mislukt maar u kunt een waarschuwing retourneren. Ongeldige tekens zorgen voor Directory-synchronisatie mislukt.
  
Directory-synchronisatie mislukt ook als sommige van uw AD DS-gebruikers een of meer dubbele kenmerken hebben. Elke gebruiker moet unieke kenmerken hebben.
  
De kenmerken die u moet voorbereiden, vindt u hier:
  
- **Weergave**
    
  - Als het kenmerk bestaat in het gebruikersobject, wordt het kenmerk gesynchroniseerd met Microsoft 365.
  - Als dit kenmerk bestaat in het gebruikersobject, moet er een waarde bestaan voor dit kenmerk. Dat wil zeggen dat het kenmerk niet leeg mag zijn.
  - Maximum aantal tekens: 256
    
- **voor benaming**
    
  - Als het kenmerk bestaat in het gebruikersobject, wordt het gesynchroniseerd met Microsoft 365, maar Microsoft 365 maakt geen gebruik van dit kenmerk.
  - Maximum aantal tekens: 64
    
- **e-mail**
    
  - De kenmerkwaarde moet uniek zijn binnen de adreslijst.
    
    > [!NOTE]
    > Als er dubbele waarden zijn, wordt de eerste gebruiker met de waarde gesynchroniseerd. De volgende gebruikers worden niet weergegeven in Microsoft 365. U moet de waarde in Microsoft 365 wijzigen of beide waarden in AD DS wijzigen, zodat beide gebruikers in Microsoft 365 worden weergegeven. 
  
- **mailNickname** (Exchange-alias) 
    
  - De kenmerkwaarde mag niet beginnen met een punt (.).
  - De kenmerkwaarde moet uniek zijn binnen de adreslijst.
  
    > [!NOTE]
    > Onderstrepingstekens ("_") in de gesynchroniseerde naam geven aan dat de oorspronkelijke waarde van dit kenmerk ongeldige tekens bevat. Zie voor meer informatie over dit kenmerk [Exchange-alias kenmerk](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps).
    >
      
- **proxyAddresses**
    
  - Kenmerk met meerdere waarden
  - Maximum aantal tekens per waarde: 256
  - De kenmerkwaarde mag geen spatie bevatten.
  - De kenmerkwaarde moet uniek zijn binnen de adreslijst.
  - Ongeldige tekens: \< \> ();, [] ""
    
    Houd er rekening mee dat de ongeldige tekens van toepassing zijn op de tekens die volgen op het type scheidingsteken en ': ', zodat de SMTP:User@contso.com is toegestaan, maar SMTP:user:M@contoso.com niet.
    
    > [!IMPORTANT]
    > Alle SMTP-adressen (Simple Mail Transport Protocol) moeten voldoen aan de standaarden voor e-mailberichten. Raadpleeg het Help-onderwerp [voor het verwijderen van dubbele en ongewenste proxy-adressen in Exchange](https://go.microsoft.com/fwlink/?LinkId=293860)als er dubbele of ongewenste adressen bestaan. 
  
- **sAMAccountName**
    
  - Maximum aantal tekens: 20
  - De kenmerkwaarde moet uniek zijn binnen de adreslijst.
  - Ongeldige tekens: [\ "|,/: \< \> + =;? \* ']
  - Als een gebruiker een ongeldig **sAMAccountName** -kenmerk heeft, maar beschikt over een geldig **userPrincipalName** -kenmerk, wordt het gebruikersaccount gemaakt in Microsoft 365. 
  - Als zowel **sAMAccountName** als **userPrincipalName** ongeldig is, moet het kenmerk AD DS **userPrincipalName** worden bijgewerkt. 
    
- **sn** (achternaam) 
    
  - Als het kenmerk bestaat in het gebruikersobject, wordt het gesynchroniseerd met Microsoft 365, maar Microsoft 365 maakt geen gebruik van dit kenmerk.
    
- **targetAddress**
    
    U moet het kenmerk **targetAddress** (bijvoorbeeld SMTP:Tom@contoso.com) dat voor de gebruiker is ingevuld, worden weergegeven in de microsoft 365 Gal. Voor de scenario van een externe communicatie met berichten migratie is hiervoor de Microsoft 365-schema-uitbreiding voor de AD DS vereist. Met de Microsoft 365-schema extensie worden ook andere nuttige kenmerken toegevoegd voor het beheren van Microsoft 365-objecten die worden gevuld met behulp van een adreslijstsynchronisatie vanuit AD DS. Het kenmerk **msExchHideFromAddressLists** voor het beheren van verborgen postvakken of distributiegroepen werd bijvoorbeeld toegevoegd. 
   
  - Maximum aantal tekens: 256
  - De kenmerkwaarde mag geen spatie bevatten.
  - De kenmerkwaarde moet uniek zijn binnen de adreslijst.
  - Ongeldige tekens: \ \< \> ();, [] "
  - Alle SMTP-adressen (Simple Mail Transport Protocol) moeten voldoen aan de standaarden voor e-mailberichten.
    
- **userPrincipalName**
    
  - De aanmeldings opmaak van het **userPrincipalName** -kenmerk moet de Internet stijl hebben, waarbij de gebruikersnaam wordt gevolgd door het apenstaartje (@) en een domeinnaam: bijvoorbeeld user@contoso.com. Alle SMTP-adressen (Simple Mail Transport Protocol) moeten voldoen aan de standaarden voor e-mailberichten.
  - Het maximum aantal tekens voor het kenmerk **userPrincipalName** is 113. U kunt als volgt een specifiek aantal tekens voor en na het apenstaartje (@) zijn toegestaan: 
  - Het maximum aantal tekens voor de gebruikersnaam vóór het apenstaartje (@): 64
  - Het maximum aantal tekens voor de domeinnaam na het apenstaartje (@): 48
  - Ongeldige tekens: \% &amp; \* +/=? { } | \< \> ( ) ; : , [ ] " '
  - Een umlaut is ook een ongeldig teken.
  - Het teken @ is vereist voor elke **userPrincipalName** -waarde. 
  - Het teken @ mag niet het eerste teken in een **userPrincipalName** -waarde zijn. 
  - De gebruikersnaam mag niet eindigen op een punt (.), een &amp; en-teken (), een spatie of een apenstaartje (@).
  - De gebruikersnaam mag geen spaties bevatten.
  - Routeerbaar domein moet worden gebruikt; lokale of interne domeinen kunnen bijvoorbeeld niet worden gebruikt.
  - Unicode wordt geconverteerd naar onderstrepingstekens.
  - **userPrincipalName** mag geen dubbele waarden in de adreslijst bevatten. 
    
## <a name="3-prepare-the-userprincipalname-attribute"></a>3. het kenmerk userPrincipalName voorbereiden

Active Directory is bedoeld voor de eindgebruikers in uw organisatie waarmee ze zich kunnen aanmelden bij uw adreslijst met behulp van **sAMAccountName** of **userPrincipalName**. Eindgebruikers kunnen zich ook aanmelden bij Microsoft 365 met behulp van de UPN (User Principal Name) van hun werk-of schoolaccount. Adreslijstsynchronisatie probeert nieuwe gebruikers te maken in azure Active Directory met behulp van dezelfde UPN in uw AD DS. De UPN wordt opgemaakt als een e-mailadres. 

In Microsoft 365 is de UPN het standaardkenmerk dat wordt gebruikt voor het genereren van het e-mailadres. U kunt in de proxyAddresses **-app** en het primaire e-mailadres in **proxyAddresses** op verschillende waarden instellen. Wanneer ze zijn ingesteld op verschillende waarden, kan dit leiden tot verwarring voor beheerders en eindgebruikers. 
  
U kunt deze kenmerken het best uitlijnen om verwarring te beperken. Om te voldoen aan de vereisten van eenmalige aanmelding met Active Directory Federation Services (AD FS) 2,0, moet u ervoor zorgen dat de Upn's in azure Active Directory en de AD DS overeenkomen met een geldige domeinnaam ruimte.
  
## <a name="4-add-an-alternative-upn-suffix-to-ad-ds"></a>4. een alternatief UPN-achtervoegsel toevoegen aan AD DS

Het kan zijn dat u een alternatief UPN-achtervoegsel moet toevoegen om de bedrijfsreferenties van de gebruiker te koppelen aan de Microsoft 365-omgeving. Een UPN-achtervoegsel is het onderdeel van een UPN rechts van het teken @. UPN-namen die worden gebruikt voor eenmalige aanmelding kunnen letters, cijfers, punten, streepjes en onderstrepingstekens bevatten, maar geen andere typen tekens.
  
Zie voor meer informatie over het toevoegen van een alternatief UPN-achtervoegsel aan Active Directory voor meer informatie over het [voorbereiden van adreslijstsynchronisatie]( https://go.microsoft.com/fwlink/p/?LinkId=525430).
  
## <a name="5-match-the-ad-ds-upn-with-the-microsoft-365-upn"></a>5. overeen met de AD DS-UPN met de Microsoft 365-UPN

Als u al adreslijstsynchronisatie hebt ingesteld, komt de UPN van de gebruiker voor Microsoft 365 mogelijk niet overeen met de AD DS-UPN van de gebruiker die is gedefinieerd in uw AD DS. Dit kan zich voordoen wanneer aan een gebruiker een licentie is toegewezen voordat het domein is geverifieerd. U kunt dit oplossen door [PowerShell te gebruiken voor het herstellen](https://go.microsoft.com/fwlink/p/?LinkId=396730) van de UPN van de gebruiker om ervoor te zorgen dat de UPN van microsoft 365 overeenkomt met de naam en het domein van de zakelijke gebruiker. Als u de UPN in de AD DS bijwerkt en deze wilt synchroniseren met de Azure Active Directory-identiteit, moet u de licentie van de gebruiker verwijderen in Microsoft 365 voordat u wijzigingen aanbrengt in AD DS. 
  
Zie ook [een niet-routeerbaar domein (zoals. lokaal) voorbereiden op adreslijstsynchronisatie](prepare-a-non-routable-domain-for-directory-synchronization.md).

## <a name="next-steps"></a>Volgende stappen

Als u de stappen 1 tot en met 5 hierboven hebt uitgevoerd, raadpleegt u [adreslijstsynchronisatie instellen](set-up-directory-synchronization.md).
