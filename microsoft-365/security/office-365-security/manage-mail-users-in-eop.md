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
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Meer informatie over het beheren van e-mailgebruikers in Exchange Online Protection (EOP), met inbegrip van adreslijstsynchronisatie, EAC en PowerShell om gebruikers te beheren.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 863bde5ef860ee980f768ddc085379180e6a71aa
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203985"
---
# <a name="manage-mail-users-in-standalone-eop"></a>E-mailgebruikers beheren in standalone EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
-  [Zelfstandige Exchange Online Protection](exchange-online-protection-overview.md)

In zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken zijn e-mailgebruikers het basistype van het gebruikersaccount. Een e-mailgebruiker heeft accountreferenties in uw zelfstandige EOP-organisatie en heeft toegang tot resources (er zijn machtigingen toegewezen). Het e-mailadres van een e-mailgebruiker is extern (bijvoorbeeld in uw on-premises e-mailomgeving).

> [!NOTE]
> Wanneer u een e-mailgebruiker maakt, is het bijbehorende gebruikersaccount beschikbaar in het Microsoft 365-beheercentrum. Wanneer u een gebruikersaccount maakt in het Microsoft 365-beheercentrum, kunt u dat account niet gebruiken om een e-mailgebruiker te maken.

De aanbevolen methode voor het maken en beheren van e-mailgebruikers in zelfstandige EOP is het gebruik van adreslijstsynchronisatie zoals beschreven in de sectie [Adreslijstsynchronisatie](#use-directory-synchronization-to-manage-mail-users) gebruiken om e-mailgebruikers verderop in dit artikel te beheren.

Voor zelfstandige EOP-organisaties met een klein aantal gebruikers kunt u e-mailgebruikers toevoegen en beheren in het Exchange-beheercentrum (EAC) of in zelfstandige EOP PowerShell, zoals in dit artikel wordt beschreven.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Zie Exchange-beheercentrum in zelfstandige [EOP](exchange-admin-center-in-exchange-online-protection-eop.md)om het Exchange-beheercentrum (EAC) te openen.

- Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- Wanneer u e-mailgebruikers maakt in EOP PowerShell, ondervindt u mogelijk beperking. De EOP PowerShell-cmdlets gebruiken ook een batchverwerkingsmethode die resulteert in een doorloopvertraging van enkele minuten voordat de resultaten van de opdrachten zichtbaar zijn.

- U moet machtigingen krijgen toegewezen in Exchange Online Protection voordat u de procedures in dit artikel kunt uitvoeren. U hebt met  name de rollen E-mailontvangers (maken) en E-mailontvangers (wijzigen) nodig, die standaard zijn toegewezen aan de rollengroepen Organisatiebeheer **(globale** beheerders) en  **Geadresseerdenbeheer.** Zie Machtigingen in zelfstandige [EOP](feature-permissions-in-eop.md) en Gebruik de EAC om de lijst met [leden in rollengroepen te wijzigen voor meer informatie.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Zie Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in [dit artikel.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> Hebt u problemen? Vraag om hulp in de Exchange-forums. Ga naar [het Exchange Online Protection-forum.](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a>Het Exchange-beheercentrum gebruiken om e-mailgebruikers te beheren

### <a name="use-the-eac-to-create-mail-users"></a>EAC gebruiken om e-mailgebruikers te maken

1. Ga in het EAC naar **Contactpersonen voor** \> **geadresseerden**

2. Klik **op Nieuw** nieuw pictogram ![ ](../../media/ITPro-EAC-AddIcon.png) . Configureer **de volgende instellingen** op de pagina Nieuwe e-mailgebruiker die wordt geopend. Instellingen die zijn gemarkeerd met <sup>\*</sup> een zijn vereist.

   - **Voornaam**

   - **Initialen:** de middelste initialen van de persoon.

   - **Achternaam**

   - <sup>\*</sup>**Weergavenaam:** In dit vak worden standaard de waarden weergegeven uit de vakken **Voornaam,** **Initialen** en **Achternaam.** U kunt deze waarde accepteren of wijzigen. De waarde moet uniek zijn en een maximale lengte van 64 tekens hebben.

   - <sup>\*</sup>**Alias:** Voer een unieke alias in met maximaal 64 tekens voor de gebruiker

   - **Extern e-mailadres:** Voer het e-mailadres van de gebruiker in. Het domein moet extern zijn voor uw cloudorganisatie.

   - <sup>\*</sup>**Gebruikers-id:** Voer het account in dat de persoon gebruikt om zich aan te melden bij de service. De gebruikers-id bestaat uit een gebruikersnaam aan de linkerkant van het @-symbool (@) en een domein aan de rechterkant.

   - <sup>\*</sup>**Nieuw wachtwoord** en <sup>\*</sup> **Wachtwoord bevestigen:** Voer het accountwachtwoord in en voer het opnieuw in. Controleer of het wachtwoord voldoet aan de wachtwoordlengte, complexiteit en geschiedenisvereisten van uw organisatie.

3. Wanneer u klaar bent, klikt u op **Opslaan om** de e-mailgebruiker te maken.

### <a name="use-the-eac-to-modify-mail-users"></a>EAC gebruiken om e-mailgebruikers te wijzigen

1. Ga in het EAC naar **Contactpersonen voor** \> **geadresseerden.**

2. Selecteer de e-mailgebruiker die u wilt wijzigen en klik vervolgens op **Pictogram** ![ Bewerken ](../../media/ITPro-EAC-AddIcon.png) bewerken.

3. Klik op de pagina eigenschappen van e-mailgebruikers die wordt geopend op een van de volgende tabbladen om eigenschappen weer te geven of te wijzigen.

   Klik op **Opslaan** wanneer u gereed bent.

#### <a name="general"></a>Algemeen

Gebruik het **tabblad** Algemeen om basisgegevens over de e-mailgebruiker weer te geven of te wijzigen.

- **Voornaam**

- **Initialen**

- **Achternaam**

- **Weergavenaam:** Deze naam wordt weergegeven in het adresboek van uw organisatie, op de regels Aan: en Van: in e-mail en in de lijst met contactpersonen in het EAC. Deze naam mag geen lege spaties voor of na de weergavenaam bevatten.

- **Gebruikers-id:** dit is het account van de gebruiker in Microsoft 365. U kunt deze waarde hier niet wijzigen.

#### <a name="contact-information"></a>Contactgegevens

Gebruik het **tabblad Contactgegevens** om de contactgegevens van de gebruiker weer te geven of te wijzigen. De informatie op deze pagina wordt weergegeven in het adresboek.

- **Straat**
- **Plaats**
- **Staat/provincie**
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

Gebruik het **tabblad Organisatie** om gedetailleerde informatie over de rol van de gebruiker in de organisatie op te nemen.

- **Title**
- **Afdeling**
- **Company**

### <a name="use-the-eac-to-remove-mail-users"></a>EAC gebruiken om e-mailgebruikers te verwijderen

1. Ga in het EAC naar **Contactpersonen voor** \> **geadresseerden.**

2. Selecteer de e-mailgebruiker die u wilt verwijderen en klik vervolgens **op Pictogram** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Verwijderen.

## <a name="use-powershell-to-manage-mail-users"></a>PowerShell gebruiken om e-mailgebruikers te beheren

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a>Zelfstandige EOP PowerShell gebruiken om e-mailgebruikers weer te geven

Voer de volgende opdracht uit als u een overzichtslijst wilt retourneren van alle e-mailgebruikers in zelfstandige EOP PowerShell:

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

Als u gedetailleerde informatie over een specifieke e-mailgebruiker wilt weergeven, vervangt u de naam, alias of accountnaam van de e-mailgebruiker en voert u \<MailUserIdentity\> de volgende opdrachten uit:

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

Zie Get-Recipient and Get-User [(Get-Recipient](/powershell/module/exchange/get-recipient) and [Get-User)](/powershell/module/exchange/get-user)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a>Zelfstandige EOP PowerShell gebruiken om e-mailgebruikers te maken

Als u e-mailgebruikers wilt maken in zelfstandige EOP PowerShell, gebruikt u de volgende syntaxis:

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

**Opmerkingen**:

- De _parameter_ Naam is vereist, heeft een maximale lengte van 64 tekens en moet uniek zijn. Als u de parameter _DisplayName_ niet gebruikt, wordt de waarde van de parameter _Naam_ gebruikt voor de weergavenaam.
- Als u de _parameter Alias_ niet gebruikt, wordt de linkerkant van de _parameter MicrosoftOnlineServicesID_ gebruikt voor de alias.
- Als u de parameter _ExternalEmailAddress_ niet gebruikt, wordt de _waarde MicrosoftOnlineServicesID_ gebruikt voor het externe e-mailadres.

In dit voorbeeld wordt een e-mailgebruiker gemaakt met de volgende instellingen:

- De naam is JeffreyZeng en de weergavenaam is Jeffrey Zeng.
- De voornaam is Jeffrey en de achternaam is Zeng.
- De alias is jeffreyz.
- Het externe e-mailadres is jzeng@tailspintoys.com.
- De accountnaam is jeffreyz@contoso.onmicrosoft.com.
- Het wachtwoord is Pa$$word 1.

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

Zie [New-EOPMailUser (Nieuw-EOPMailUser) voor](/powershell/module/exchange/new-eopmailuser)gedetailleerde syntaxis- en parametergegevens.

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a>Zelfstandige EOP PowerShell gebruiken om e-mailgebruikers te wijzigen

Als u bestaande e-mailgebruikers wilt wijzigen in zelfstandige EOP PowerShell, gebruikt u de volgende syntaxis:

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

In dit voorbeeld wordt het externe e-mailadres voor Pilar Pinilla instellen.

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

In dit voorbeeld stelt u de eigenschap Bedrijf voor alle e-mailgebruikers in op Contoso.

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

Zie [Set-EOPMailUser voor](/powershell/module/exchange/set-eopmailuser)gedetailleerde syntaxis- en parametergegevens.

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a>Zelfstandige EOP PowerShell gebruiken om e-mailgebruikers te verwijderen

Als u e-mailgebruikers in zelfstandige EOP PowerShell wilt verwijderen, vervangt u door de naam, alias of accountnaam van de e-mailgebruiker en voer u \<MailUserIdentity\> de volgende opdracht uit:

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

In dit voorbeeld wordt de e-mailgebruiker voor Jeffrey Zeng verwijderd.

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

Zie [Remove-EOPMailUser (Verwijderen-EOPMailUser)](/powershell/module/exchange/remove-eopmailuser)voor gedetailleerde syntaxis- en parametergegevens.

## <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Als u wilt controleren of u e-mailgebruikers hebt gemaakt, gewijzigd of verwijderd in zelfstandige EOP, gebruikt u een van de volgende procedures:

- Ga in het EAC naar **Contactpersonen voor** \> **geadresseerden.** Controleer of de e-mailgebruiker wordt vermeld (of niet wordt vermeld). Selecteer de e-mailgebruiker en bekijk de informatie in het deelvenster Details of klik op **Pictogram** ![ Bewerken bewerken om de instellingen weer te ](../../media/ITPro-EAC-AddIcon.png) geven.

- Voer in zelfstandige EOP PowerShell de volgende opdracht uit om te controleren of de e-mailgebruiker wordt vermeld (of niet wordt vermeld):

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- Vervang \<MailUserIdentity\> deze door de naam, alias of accountnaam van de e-mailgebruiker en voer de volgende opdrachten uit om de instellingen te verifiëren:

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a>Adreslijstsynchronisatie gebruiken om e-mailgebruikers te beheren

In zelfstandige EOP is adreslijstsynchronisatie beschikbaar voor klanten met on-premises Active Directory. U kunt deze accounts synchroniseren met Azure Active Directory (Azure AD), waar kopieën van de accounts worden opgeslagen in de cloud. Wanneer u uw bestaande **gebruikersaccounts** synchroniseert met Azure Active Directory, kunt u deze gebruikers bekijken in het deelvenster Geadresseerden van het Exchange-beheercentrum (EAC) of in zelfstandige EOP PowerShell.

**Opmerkingen**:

- Als u adreslijstsynchronisatie gebruikt om uw geadresseerden te beheren, kunt u nog steeds gebruikers toevoegen en beheren in het Microsoft 365-beheercentrum, maar ze worden niet gesynchroniseerd met uw on-premises Active Directory. Dit komt omdat adreslijstsynchronisatie alleen geadresseerden synchroniseert van uw on-premises Active Directory naar de cloud.

- Het gebruik van adreslijstsynchronisatie wordt aanbevolen voor gebruik met de volgende functies:

  - **Lijsten met veilige afzenders** van Outlook en lijsten met geblokkeerde afzenders: wanneer deze worden gesynchroniseerd met de service, hebben deze lijsten voorrang op spamfilters in de service. Hierdoor kunnen gebruikers hun eigen lijst met veilige afzenders en lijst met geblokkeerde afzenders beheren met afzonderlijke afzenders en domeingegevens. Zie [Instellingen voor ongewenste e-mail configureren voor Exchange Online-postvakken](configure-junk-email-settings-on-exo-mailboxes.md) voor meer informatie.

  - **Directory Based Edge Blocking (DBEB)**: Zie Directory Based Edge Blocking (Directory Based Edge Blocking) voor meer informatie over DBEB om berichten te weigeren die naar [ongeldige geadresseerden zijn verzonden.](/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)

  - **Toegang van eindgebruikers tot quarantaine:** geadresseerden moeten een geldige gebruikers-id en een geldig wachtwoord in de service hebben om toegang te krijgen tot hun in quarantaine geplaatste berichten. Zie Berichten in quarantaine zoeken en vrijgeven als gebruiker voor [meer informatie over quarantaine.](find-and-release-quarantined-messages-as-a-user.md)

  - Regels voor e-mailstroom (ook wel transportregels **genoemd)**: Wanneer u adreslijstsynchronisatie gebruikt, worden uw bestaande Active Directory-gebruikers en -groepen automatisch geüpload naar de cloud en kunt u vervolgens regels voor de e-mailstroom maken die gericht zijn op specifieke gebruikers en/of groepen zonder ze handmatig toe te voegen aan de service. Dynamische [distributiegroepen kunnen](/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) niet worden gesynchroniseerd via adreslijstsynchronisatie.

Krijg de benodigde machtigingen en bereid u voor op adreslijstsynchronisatie, zoals beschreven in [Wat is hybride identiteit met Azure Active Directory?](/azure/active-directory/hybrid/whatis-hybrid-identity).

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a>Mappen synchroniseren met Azure Active Directory Connect (AAD Connect)

1. Adreslijstsynchronisatie activeren zoals beschreven in [Azure AD Connect-synchronisatie: Synchronisatie](/azure/active-directory/hybrid/how-to-connect-sync-whatis)begrijpen en aanpassen.

2. Installeer en configureer een on-premises computer om AAD Connect uit te voeren, zoals beschreven in [Vereisten voor Azure AD Connect.](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)

3. [Selecteer welk installatietype u wilt gebruiken voor Azure AD Connect:](/azure/active-directory/hybrid/how-to-connect-install-select-installation)

   - [Express](/azure/active-directory/hybrid/how-to-connect-install-express)

   - [Aangepast](/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [Pass-through-verificatie](/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> Wanneer u de configuratiewizard van het Azure Active Directory-synchronisatieprogramma hebt uitgevoerd, **wordt MSOL_AD_SYNC** account gemaakt in uw Active Directory-forest. Dit account wordt gebruikt om uw on-premises Active Directory-gegevens te lezen en te synchroniseren. Zorg ervoor dat TCP 443 op uw lokale adreslijstsynchronisatieserver is geopend om ervoor te zorgen dat adreslijstsynchronisatie correct werkt.

Controleer na het configureren van de synchronisatie of AAD Connect correct wordt gesynchroniseerd. Ga in het EAC naar **Contactpersonen** voor geadresseerden en bekijk of de lijst met gebruikers correct is \>  gesynchroniseerd vanuit uw on-premises omgeving.