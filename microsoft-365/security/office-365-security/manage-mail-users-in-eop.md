---
title: E-mailgebruikers beheren in standalone EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Meer informatie over het beheren van gebruikers van e-mailberichten in Exchange Online Protection (EOP), waaronder het gebruik van adreslijstsynchronisatie, SBV en PowerShell voor het beheren van gebruikers.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a8258a63fe0fbf4a6b5641fbdef213f25de2e4dd
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658831"
---
# <a name="manage-mail-users-in-standalone-eop"></a>E-mailgebruikers beheren in standalone EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Gebruikers van een zelfstandige Exchange Online Protection-organisatie (EOP) zonder postvakken van Exchange, zijn e-mail gebruikers het fundamentele type gebruikersaccount. Een e-mail gebruiker heeft accountreferenties in uw zelfstandige EOP-organisatie en kan toegang krijgen tot bronnen (machtigingen toegewezen). Het e-mailadres van een e-mail gebruiker is extern (bijvoorbeeld in uw on-premises e-mail omgeving).

> [!NOTE]
> Wanneer u een e-mail gebruiker maakt, is het bijbehorende gebruikersaccount beschikbaar in het Microsoft 365-Beheercentrum. Wanneer u een gebruikersaccount maakt in het Microsoft 365-Beheercentrum, kunt u dit account niet gebruiken om een e-mail gebruiker te maken.

De aanbevolen methode voor het maken en beheren van e-mail gebruikers in standalone EOP is door gebruik te maken van adreslijstsynchronisatie, zoals beschreven in de sectie [e-mail gebruikers van e-mailberichten beheren](#use-directory-synchronization-to-manage-mail-users) verderop in dit artikel.

Voor zelfstandige EOP-organisaties met een klein aantal gebruikers, kunt u e-mail gebruikers toevoegen en beheren in het Exchange-Beheercentrum (Microsoft) of in een zelfstandige EOP-PowerShell zoals in dit artikel wordt beschreven.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Exchange-Beheercentrum door het Exchange- [Beheercentrum in zelfstandige EOP](exchange-admin-center-in-exchange-online-protection-eop.md).

- Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- Wanneer u e-mail gebruikers maakt in EOP PowerShell, kan dat leiden tot vertraging. Daarnaast wordt in de EOP PowerShell-cmdlets een batch verwerkingsmethode gebruikt die de vertraging van een paar minuten oplevert voordat de resultaten van de opdrachten zichtbaar zijn.

- U moet machtigingen zijn toegewezen in Exchange Online Protection voordat u de procedures in dit artikel kunt uitvoeren. Specifiek hebt u de **e-mailadressen voor de ontvangers van e-mailberichten** (maken) en **e-mail geadresseerden** (wijzigen) nodig die zijn toegewezen aan het **Organisatiebeheer** (globale beheerders) en rollen groepen voor **geadresseerden** . Zie voor meer informatie [machtigingen in zelfstandige EOP](feature-permissions-in-eop.md) en [Gebruik de lijst met wijzigingen in de lijst met leden van rollen groepen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Zie toetscombinaties [voor het Exchange-Beheercentrum in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)voor informatie over toetscombinaties die van toepassing kunnen zijn op de procedures in dit artikel.

> [!TIP]
> Problemen? Hulp vragen op de Exchange-forums. Bezoek het forum [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a>Het Exchange-Beheercentrum gebruiken voor het beheren van e-mail gebruikers

### <a name="use-the-eac-to-create-mail-users"></a>Het Exchange-Beheercentrum gebruiken om e-mail gebruikers te maken

1. Ga in het Exchange-beheer  centrum naar \> **contacten** met geadresseerden

2. Klik op **Nieuw** ![ pictogram nieuw ](../../media/ITPro-EAC-AddIcon.png) . Configureer de volgende instellingen op de pagina **nieuwe e-mail gebruiker** die wordt geopend. Instellingen die zijn gemarkeerd met een <sup>\*</sup> zijn vereist.

   - **Voornaam**

   - **Initialen**: de initiaal van de persoon.

   - **Achternaam**

   - <sup>\*</sup>**Weergavenaam**: in dit vak worden standaard de waarden in de vakken **voornaam**, **initialen** en **Achternaam** weergegeven. U kunt deze waarde accepteren of wijzigen. De waarde moet uniek zijn en mag maximaal 64 tekens lang zijn.

   - <sup>\*</sup>**Alias**: Voer een unieke alias in met tot 64 tekens voor de gebruiker

   - **Extern e-mailadres**: Voer het e-mailadres van de gebruiker in. Het domein moet buiten de Cloud organisatie liggen.

   - <sup>\*</sup>**Gebruikers-id**: Voer het account in dat door de persoon wordt gebruikt om u aan te melden bij de service. De gebruikers-ID bestaat uit een gebruikersnaam aan de linkerkant van het apenstaartje (@) en een domein aan de rechterkant.

   - <sup>\*</sup>**Nieuw wachtwoord** en <sup>\*</sup> **Bevestig uw wachtwoord**: Voer het accountwachtwoord in en voer deze opnieuw in. Controleer of het wachtwoord voldoet aan de vereisten voor de lengte en complexiteit van het wachtwoord en de geschiedenis van uw organisatie.

3. Wanneer u klaar bent, klikt u op **Opslaan** om de e-mail gebruiker te maken.

### <a name="use-the-eac-to-modify-mail-users"></a>Het Exchange-Beheercentrum gebruiken om e-mail gebruikers te wijzigen

1. Ga in het Exchange-beheer  centrum naar \> **contactpersonen** met geadresseerden.

2. Selecteer de e-mail gebruiker die u wilt wijzigen en klik vervolgens  op het ![ pictogram bewerken bewerken ](../../media/ITPro-EAC-AddIcon.png) .

3. Op de pagina met de gebruikerseigenschappen van de e-mail die wordt geopend, klikt u op een van de volgende tabbladen om de eigenschappen weer te geven of te wijzigen.

   Klik op **Opslaan** wanneer u gereed bent.

#### <a name="general"></a>Algemeen

Gebruik het tabblad **Algemeen** om basisinformatie over de e-mail gebruiker weer te geven of te wijzigen.

- **Voornaam**

- **Initialen**

- **Achternaam**

- **Weergavenaam**: deze naam wordt weergegeven in het adresboek van uw organisatie, op de regel aan: en van: en in de lijst met contactpersonen in het Exchange-Beheercentrum. Deze naam mag geen lege spaties voor of na de weergavenaam bevatten.

- **Gebruikers-id**: dit is het account van de gebruiker in microsoft 365. U kunt deze waarde hier niet wijzigen.

#### <a name="contact-information"></a>Contact gegevens

Gebruik het tabblad **contact gegevens** om de contact gegevens van de gebruiker weer te geven of te wijzigen. De informatie op deze pagina wordt weergegeven in het adresboek.

- **Naam**
- **Plaats**
- **Provincie**
- **Postcode**
- **Land/regio**
- **Telefoon werk**
- **Mobiele telefoon**
- **Fax**
- **Meer opties**

  - **Office**
  - **Telefoon thuis**
  - **Webpagina**
  - **Opmerkingen**

#### <a name="organization"></a>Organisatie

Via het tabblad **organisatie** kunt u gedetailleerde informatie over de rol van de gebruiker in de organisatie opnemen.

- **Title**
- **Afdeling**
- **Company**

### <a name="use-the-eac-to-remove-mail-users"></a>Het Exchange-Beheercentrum gebruiken om e-mail gebruikers te verwijderen

1. Ga in het Exchange-beheer  centrum naar \> **contactpersonen** met geadresseerden.

2. Selecteer de e-mail gebruiker die u wilt verwijderen en **Klik op het** ![ pictogram verwijderen ](../../media/ITPro-EAC-RemoveIcon.gif) .

## <a name="use-powershell-to-manage-mail-users"></a>PowerShell gebruiken voor het beheren van e-mail gebruikers

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a>Standalone EOP PowerShell gebruiken om e-mail gebruikers weer te geven

Voer de volgende opdracht uit als u een overzicht wilt weergeven van alle e-mail gebruikers in een zelfstandige EOP PowerShell:

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

Als u gedetailleerde informatie over een specifieke e-mail gebruiker wilt bekijken, vervangt u \<MailUserIdentity\> de naam, alias of accountnaam van de e-mail gebruiker en voert u de volgende opdrachten uit:

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

Zie [Get-verplaatsings-](https://docs.microsoft.com/powershell/module/exchange/get-recipient) en [Get-gebruiker](https://docs.microsoft.com/powershell/module/exchange/get-user)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a>Standalone EOP PowerShell gebruiken om e-mail gebruikers te maken

Gebruik de volgende syntaxis om e-mail gebruikers te maken in zelfstandige EOP PowerShell:

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

**Opmerkingen**:

- De _naam_ parameter is vereist, mag maximaal 64 tekens lang zijn en moet uniek zijn. Als u de parameter _DisplayName_ niet gebruikt, wordt de waarde van de parameter _name_ gebruikt voor de weergavenaam.
- Als u de parameter _alias_ niet gebruikt, wordt de linkerkant van de _MicrosoftOnlineServicesID_ -parameter gebruikt voor de alias.
- Als u de parameter _ExternalEmailAddress_ niet gebruikt, wordt de _MicrosoftOnlineServicesID_ -waarde gebruikt voor het externe e-mailadres.

In het volgende voorbeeld wordt een e-mail gebruiker gemaakt met de volgende instellingen:

- De naam is JeffreyZeng en de weergavenaam is Jeffrey Zeng.
- De voornaam is Jeffrey en de naam van de achternaam is Zeng.
- De alias is jeffreyz.
- Het externe e-mailadres is jzeng@tailspintoys.com.
- De accountnaam is jeffreyz@contoso.onmicrosoft.com.
- Het wachtwoord is PA $ $word 1.

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

Zie [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a>Zelfstandige EOP PowerShell gebruiken voor het wijzigen van e-mail gebruikers

Gebruik de volgende syntaxis om bestaande e-mail gebruikers van zelfstandige EOP PowerShell te wijzigen:

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

In dit voorbeeld wordt het externe e-mailadres voor Pilar Pinilla.

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

In dit voorbeeld wordt de eigenschap Company voor alle e-mail gebruikers ingesteld op contoso.

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

Zie [set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a>Standalone EOP PowerShell gebruiken om e-mail gebruikers te verwijderen

Als u e-mail gebruikers wilt verwijderen uit zelfstandige EOP PowerShell, vervangt u \<MailUserIdentity\> de naam, alias of accountnaam van de e-mail gebruiker en voert u de volgende opdracht uit:

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

In dit voorbeeld wordt de e-mail gebruiker verwijderd voor Jeffrey Zeng.

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

Zie [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser)voor gedetailleerde syntaxis-en parameterinformatie.

## <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Ga op een van de volgende manieren te werk om te controleren of u e-mail gebruikers met een zelfstandige EOP hebt gemaakt, gewijzigd of verwijderd.

- Ga in het Exchange-beheer  centrum naar \> **contactpersonen** met geadresseerden. Controleer of de e-mail gebruiker wordt weergegeven (of niet wordt weergegeven). Selecteer e-mail gebruiker en Bekijk de informatie in het detailvenster of Klik  op ![ bewerkingspictogram bewerken ](../../media/ITPro-EAC-AddIcon.png) om de instellingen weer te geven.

- Voer in standalone EOP PowerShell de volgende opdracht uit om te controleren of de e-mail gebruiker wordt weergegeven (of wordt niet weergegeven):

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- Vervang de \<MailUserIdentity\> naam, alias of accountnaam van de e-mail gebruiker en voer de volgende opdrachten uit om de instellingen te controleren:

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a>Adreslijstsynchronisatie gebruiken voor het beheren van e-mail gebruikers

Directory-synchronisatie via zelfstandige EOP is beschikbaar voor klanten met een on-premises Active Directory. U kunt deze accounts synchroniseren met Azure Active Directory (Azure AD), waar kopieën van de accounts in de cloud worden opgeslagen. Wanneer u uw bestaande gebruikersaccounts synchroniseert met Azure Active Directory, kunt u deze gebruikers weergeven in het deelvenster **geadresseerden** van het Exchange-Beheercentrum (SBV) of in een zelfstandige EOP PowerShell.

**Opmerkingen**:

- Als u adreslijstsynchronisatie gebruikt om geadresseerden te beheren, kunt u nog steeds gebruikers toevoegen en beheren in het Microsoft 365-Beheercentrum, maar deze worden niet gesynchroniseerd met uw on-premises Active Directory. Dit komt omdat adreslijstsynchronisatie alleen geadresseerden van uw on-premises Active Directory synchroniseert naar de Cloud.

- Het gebruik van adreslijstsynchronisatie wordt aanbevolen voor gebruik met de volgende functies:

  - Lijsten met **veilige afzenders van Outlook en geblokkeerde lijsten van afzenders**: wanneer u de service synchroniseert, hebben deze lijsten voorrang op het filteren van ongewenste e-mail in de service. Hiermee kunnen gebruikers hun eigen lijst met veilige afzenders en lijst met geblokkeerde afzenders beheren met individuele items voor de afzender en het domein. Zie [Instellingen voor ongewenste e-mail configureren voor Exchange Online-postvakken](configure-junk-email-settings-on-exo-mailboxes.md) voor meer informatie.

  - **Op mappen gebaseerde rand blokkeren (DBEB)**: Zie voor meer informatie over DBEB voor meer informatie over [het gebruik van op mappen gebaseerde blokken blokkeren om berichten die naar ongeldige geadresseerden zijn verzonden, af te](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)wijzen.

  - **Eindgebruikers toegang tot Quarantine**: de geadresseerden moeten een geldige gebruikers-id en een geldig wachtwoord in de service hebben om toegang te krijgen tot de berichten in quarantaine. Zie geplaatste [berichten in quarantaine plaatsen en vrijgeven als een gebruiker](find-and-release-quarantined-messages-as-a-user.md)voor meer informatie over quarantaine.

  - **Regels voor e-mail stroom (ook wel transport-regels genoemd)**: wanneer u adreslijstsynchronisatie gebruikt, worden uw bestaande Active Directory-gebruikers en-groepen automatisch geüpload naar de Cloud, en kunt u vervolgens een e-mail stroom regel maken die specifieke gebruikers en/of groepen bedoelt, zonder dat u ze handmatig hoeft toe te voegen aan de service. Houd er rekening mee dat [dynamische distributiegroepen](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) niet kunnen worden gesynchroniseerd via adreslijstsynchronisatie.

Zorg dat u de benodigde machtigingen hebt en voorbereiding voor adreslijstsynchronisatie, zoals wordt beschreven in [Wat is hybride identiteit met Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a>Directory's synchroniseren met Azure Active Directory Connect (AAD Connect)

1. Active Directory-synchronisatie activeren zoals beschreven in [Azure AD Connect-synchronisatie: de synchronisatie begrijpen en aanpassen](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).

2. Installeer en configureer een on-premises computer om AAD Connect uit te voeren, zoals is beschreven in [vereisten voor Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).

3. [Selecteer welk type installatie u wilt gebruiken in azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation):

   - [Express](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [Gemaakte](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [Pass-through-verificatie](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> Wanneer u de wizard Configuratie van Azure Active Directory-synchronisatie hebt voltooid, wordt het **MSOL_AD_Sync** -account gemaakt in het Active Directory-forest. Dit account wordt gebruikt voor het lezen en synchroniseren van uw on-premises Active Directory-informatie. Zorg ervoor dat de TCP 443 op de lokale adreslijstsynchronisatie server is geopend, zodat de adreslijstsynchronisatie naar behoren werkt.

Voordat u de synchronisatie hebt geconfigureerd, controleert u of de AAD-verbinding correct wordt gesynchroniseerd. Ga in het Exchange-beheer  centrum naar \> **contactpersonen** van geadresseerden en bekijk dat de lijst met gebruikers correct is gesynchroniseerd vanuit uw on-premises omgeving.
