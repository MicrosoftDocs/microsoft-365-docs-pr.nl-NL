---
title: E-mailgebruikers beheren in standalone EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Meer informatie over het beheren van e-mailgebruikers in Exchange Online Protection (EOP), inclusief het gebruik van directorysynchronisatie, EAC en PowerShell om gebruikers te beheren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d82170499bcfa6465164ca2644eea43c2558ad18
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616832"
---
# <a name="manage-mail-users-in-standalone-eop"></a>E-mailgebruikers beheren in standalone EOP

In zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken zijn e-mailgebruikers het fundamentele type gebruikersaccount. Een e-mailgebruiker heeft accountreferenties in uw zelfstandige EOP-organisatie en heeft toegang tot bronnen (machtigingen hebben toegewezen). Het e-mailadres van een e-mailgebruiker is extern (bijvoorbeeld in uw on-premises e-mailomgeving).

> [!NOTE]
> Wanneer u een e-mailgebruiker maakt, is het bijbehorende gebruikersaccount beschikbaar in het Microsoft 365-beheercentrum. Wanneer u een gebruikersaccount maakt in het Microsoft 365-beheercentrum, u dat account niet gebruiken om een e-mailgebruiker te maken.

De aanbevolen methode voor het maken en beheren van e-mailgebruikers in standalone EOP is het gebruik van adreslijstsynchronisatie zoals beschreven in de [mapsynchronisatie gebruiken om e-mailgebruikers](#use-directory-synchronization-to-manage-mail-users) later in dit onderwerp te beheren.

Voor zelfstandige EOP-organisaties met een klein aantal gebruikers u e-mailgebruikers toevoegen en beheren in het Exchange-beheercentrum (EAC) of in standalone EOP PowerShell zoals beschreven in dit onderwerp.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Zie [Exchange-beheercentrum in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md)als u het Exchange-beheercentrum (EAC) wilt openen.

- Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.

- Wanneer u e-mailgebruikers maakt in EOP PowerShell, u throttling tegenkomen. Ook gebruiken de EOP PowerShell-cmdlets een batchverwerkingsmethode die resulteert in een propagatievertraging van enkele minuten voordat de resultaten van de opdrachten zichtbaar zijn.

- U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren. In het bijzonder hebt u de rollen voor het maken van e-mailontvangers (maken) en e-mailontvangers (wijzigen) nodig, die standaard zijn toegewezen aan de rolgroepen OrganizationManagement (global admins) en RecipientManagement. Zie [Machtigingen in zelfstandige EOP](feature-permissions-in-eop.md) en Gebruik de EAC voor meer informatie [de lijst met leden in rolgroepen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)wijzigen.

- Zie [Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in dit onderwerp.

> [!TIP]
> Heb je problemen? Vraag om hulp in de Exchange-forums. Ga naar het [Exchange Online Protection-forum.](https://go.microsoft.com/fwlink/p/?linkId=285351)

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a>Het Exchange-beheercentrum gebruiken om e-mailgebruikers te beheren

### <a name="use-the-eac-to-create-mail-users"></a>De EAC gebruiken om e-mailgebruikers te maken

1. Ga in de EAC naar **Contactpersonen voor geadresseerden** \> **Contacts**

2. Klik op **Nieuw** ![ pictogram ](../../media/ITPro-EAC-AddIcon.png) . Configureer de volgende instellingen op de **pagina Nieuwe e-mailgebruikers** die wordt geopend. Instellingen die zijn gemarkeerd met een <sup>\*</sup> zijn vereist.

   - **Voornaam**

   - **Initialen**: De middelste initiaal van de persoon.

   - **Achternaam**

   - <sup>\*</sup>**Weergavenaam**: In dit vak worden standaard de waarden weergegeven uit de vakken **Voornaam,** **Initialen**en **Achternaam.** U deze waarde accepteren of wijzigen. De waarde moet uniek zijn en heeft een maximale lengte van 64 tekens.

   - <sup>\*</sup>**Alias**: Voer een unieke alias in met maximaal 64 tekens voor de gebruiker

   - **Extern e-mailadres**: Voer het e-mailadres van de gebruiker in. Het domein moet extern zijn aan uw cloudorganisatie.

   - <sup>\*</sup>**Gebruikersnaam**: Voer het account in dat de persoon gebruikt om zich aan te melden bij de service. De gebruikersnaam bestaat uit een gebruikersnaam aan de linkerkant van het at (@) symbool (@) en een domein aan de rechterkant.

   - <sup>\*</sup>**Nieuw wachtwoord** en <sup>\*</sup> **Wachtwoord bevestigen**: Voer het accountwachtwoord in en voer deze opnieuw in. Controleer of het wachtwoord voldoet aan de vereisten voor wachtwoordduur, complexiteit en geschiedenis van uw organisatie.

3. Wanneer u klaar bent, klikt u op **Opslaan** om de e-mailgebruiker te maken.

### <a name="use-the-eac-to-modify-mail-users"></a>De EAC gebruiken om e-mailgebruikers te wijzigen

1. Ga in de EAC naar **Contactpersonen voor ontvangers** \> **Contacts**.

2. Selecteer de e-mailgebruiker die u wilt wijzigen en **klik** op ![ pictogram Bewerken ](../../media/ITPro-EAC-AddIcon.png) bewerken .

3. Klik op de pagina eigenschappen van e-mailgebruikers die wordt geopend op een van de volgende tabbladen om eigenschappen weer te geven of te wijzigen.

   Klik op **Opslaan** wanneer u gereed bent.

#### <a name="general"></a>Algemeen

Gebruik het tabblad **Algemeen** om basisgegevens over de e-mailgebruiker weer te geven of te wijzigen.

- **Voornaam**

- **Initialen**

- **Achternaam**

- **Weergavenaam**: deze naam wordt weergegeven in het adresboek van uw organisatie, op het aan: en van: regels in e-mail en in de lijst met contactpersonen in de EAC. Deze naam mag geen lege spaties bevatten voor of na de weergavenaam.

- **Gebruikersnaam**: dit is het account van de gebruiker in Microsoft 365. U deze waarde hier niet wijzigen.

#### <a name="contact-information"></a>Contactgegevens

Gebruik het tabblad **Contactgegevens** om de contactgegevens van de gebruiker weer te geven of te wijzigen. De informatie op deze pagina wordt weergegeven in het adresboek.

- **Street**
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

Gebruik het tabblad **Organisatie** om gedetailleerde informatie op te nemen over de rol van de gebruiker in de organisatie.

- **Title**
- **Afdeling**
- **Company**

### <a name="use-the-eac-to-remove-mail-users"></a>De EAC gebruiken om e-mailgebruikers te verwijderen

1. Ga in de EAC naar **Contactpersonen voor ontvangers** \> **Contacts**.

2. Selecteer de e-mailgebruiker die u wilt verwijderen en **klik** op ![ pictogram Verwijderen verwijderen ](../../media/ITPro-EAC-RemoveIcon.gif) .

## <a name="use-powershell-to-manage-mail-users"></a>PowerShell gebruiken om e-mailgebruikers te beheren

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a>Zelfstandige EOP PowerShell gebruiken om e-mailgebruikers weer te geven

Voer de volgende opdracht uit om een overzichtslijst van alle e-mailgebruikers in standalone EOP PowerShell terug te sturen:

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

Als u gedetailleerde informatie over een specifieke e-mailgebruiker wilt weergeven, vervangt u \<MailUserIdentity\> de naam, alias of accountnaam van de e-mailgebruiker en voert u de volgende opdrachten uit:

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

Zie [Ophalen](https://docs.microsoft.com/powershell/module/exchange/get-recipient) en [Gebruiker](https://docs.microsoft.com/powershell/module/exchange/get-user)ophalen voor gedetailleerde syntaxis en parametergegevens.

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a>Zelfstandige EOP PowerShell gebruiken om e-mailgebruikers te maken

Als u e-mailgebruikers wilt maken in zelfstandige EOP PowerShell, gebruikt u de volgende syntaxis:

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

**Opmerkingen**:

- De parameter _Naam_ is vereist, heeft een maximale lengte van 64 tekens en moet uniek zijn. Als u de parameter _DisplayName_ niet gebruikt, wordt de waarde van de parameter _Name_ gebruikt voor de weergavenaam.
- Als u de parameter _Alias_ niet gebruikt, wordt de linkerkant van de parameter _MicrosoftOnlneServicesID_ gebruikt voor de alias.
- Als u de parameter _ExternalEmailAddress_ niet gebruikt, wordt de _MicrosoftOnlineServicesID-waarde_ gebruikt voor het externe e-mailadres.

In dit voorbeeld wordt een e-mailgebruiker gemaakt met de volgende instellingen:

- De naam is JeffreyZeng en de display naam is Jeffrey Zeng.
- De voornaam is Jeffrey en de achternaam is Zeng.
- De alias is Jeffreyz.
- Het externe e-mailadres wordt jzeng@tailspintoys.com.
- De accountnaam is jeffreyz@contoso.onmicrosoft.com.
- Het wachtwoord is Pa$ $word1.

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

Zie [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser)voor gedetailleerde syntaxis- en parametergegevens .

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a>Zelfstandige EOP PowerShell gebruiken om e-mailgebruikers te wijzigen

Als u bestaande e-mailgebruikers in zelfstandige EOP PowerShell wilt wijzigen, gebruikt u de volgende syntaxis:

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Textg>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

In dit voorbeeld wordt het externe e-mailadres voor Pilar Pinilla ingesteld.

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

In dit voorbeeld wordt de eigenschap Bedrijf voor alle e-mailgebruikers ingesteld op Contoso.

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

Zie [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser)voor gedetailleerde syntaxis- en parametergegevens .

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a>Zelfstandige EOP PowerShell gebruiken om e-mailgebruikers te verwijderen

Als u e-mailgebruikers in zelfstandige EOP PowerShell wilt verwijderen, vervangt u \<MailUserIdentity\> de naam, alias of accountnaam van de e-mailgebruiker en voert u de volgende opdracht uit:

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

In dit voorbeeld wordt de e-mailgebruiker voor Jeffrey Zeng verwijderd.

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

Zie [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser)voor gedetailleerde syntaxis- en parametergegevens .

## <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Als u wilt controleren of u e-mailgebruikers hebt gemaakt, gewijzigd of verwijderd in zelfstandige EOP, gebruikt u een van de volgende procedures:

- Ga in de EAC naar **Contactpersonen voor ontvangers** \> **Contacts**. Controleer of de e-mailgebruiker wordt vermeld (of niet wordt vermeld). Selecteer de e-mailgebruiker en bekijk de informatie in het deelvenster Details of **klik** op pictogram Bewerken bewerken ![ om de instellingen weer te ](../../media/ITPro-EAC-AddIcon.png) geven.

- Voer in standalone EOP PowerShell de volgende opdracht uit om te controleren of de e-mailgebruiker wordt vermeld (of niet wordt vermeld):

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- Vervang \<MailUserIdentity\> de naam, alias of accountnaam van de e-mailgebruiker en voer de volgende opdrachten uit om de instellingen te verifiëren:

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a>Adreslijstsynchronisatie gebruiken om e-mailgebruikers te beheren

In standalone EOP is directorysynchronisatie beschikbaar voor klanten met on-premises Active Directory. U deze accounts synchroniseren met Azure Active Directory (Azure AD), waar kopieën van de accounts in de cloud worden opgeslagen. Wanneer u uw bestaande gebruikersaccounts synchroniseert met Azure Active Directory, u deze gebruikers bekijken in het deelvenster **Geadresseerden** van het Exchange-beheercentrum (EAC) of in zelfstandige EOP PowerShell.

**Opmerkingen**:

- Als u adreslijstsynchronisatie gebruikt om uw ontvangers te beheren, u nog steeds gebruikers toevoegen en beheren in het Microsoft 365-beheercentrum, maar worden ze niet gesynchroniseerd met uw on-premises Active Directory. Dit komt omdat directorysynchronisatie alleen ontvangers van uw on-premises Active Directory synchroniseert met de cloud.

- Het gebruik van adreslijstsynchronisatie wordt aanbevolen voor gebruik met de volgende functies:

  - **Lijsten met veilige afzenders van Outlook en lijsten met geblokkeerde afzenders**: Wanneer deze lijsten worden gesynchroniseerd met de service, hebben deze lijsten voorrang op spamfiltering in de service. Hiermee kunnen gebruikers hun eigen lijst met veilige afzenders en lijst met geblokkeerde afzenders beheren met afzonderlijke afzender- en domeinvermeldingen. Zie [Instellingen voor ongewenste e-mail configureren voor Exchange Online-postvakken](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes) voor meer informatie.

  - **Directory Based Edge Blocking (DBEB)**: Zie [Directory Based Edge Blocking gebruiken om berichten die naar ongeldige ontvangers worden verzonden, te weigeren voor](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)meer informatie over DBEB.

  - **Toegang van eindgebruikers tot quarantaine**: Om toegang te krijgen tot hun berichten in quarantaine, moeten ontvangers een geldige gebruikersnaam en wachtwoord in de service hebben. Zie Berichten [in quarantaine zoeken en vrijgeven als gebruiker voor](https://docs.microsoft.com/microsoft-365/security/office-365-security/find-and-release-quarantined-messages-as-a-user)meer informatie over quarantaine.

  - **Regels voor e-mailstroom (ook wel transportregels genoemd):** Wanneer u adreslijstsynchronisatie gebruikt, worden uw bestaande Active Directory-gebruikers en -groepen automatisch geüpload naar de cloud en u vervolgens regels voor e-mailstroom maken die specifieke gebruikers en/of groepen targeten zonder deze handmatig toe te voegen in de service. Houd er rekening mee dat [dynamische distributiegroepen](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) niet kunnen worden gesynchroniseerd via adreslijstsynchronisatie.

De benodigde machtigingen ophalen en voorbereiden op adreslijstsynchronisatie, zoals beschreven in [Wat is hybride identiteit met Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a>Mappen synchroniseren met Azure Active Directory Connect (AAD Connect)

1. Activeer adreslijstsynchronisatie zoals beschreven in [Azure AD Connect-synchronisatie: synchronisatie begrijpen en aanpassen](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).

2. Installeer en configureer een on-premises computer om AAD Connect uit te voeren zoals beschreven in [Vereisten voor Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).

3. [Selecteer welk installatietype u wilt gebruiken voor Azure AD Connect:](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation)

   - [Express](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [Aangepaste](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [Pass-through-verificatie](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> Wanneer u de wizard Configuratie van het Azure Active Directory-synchronisatiegereedschap hebt voltooid, wordt het **MSOL_AD_SYNC-account** gemaakt in uw Active Directory-forest. Dit account wordt gebruikt om uw on-premises Active Directory-gegevens te lezen en te synchroniseren. Als u ervoor wilt dat adreslijstsynchronisatie correct werkt, moet u ervoor zorgen dat TCP 443 op uw lokale adreslijstsynchronisatieserver is geopend.

Controleer na het configureren van uw synchronisatie of AAD Connect correct synchroniseert. Ga in de EAC naar **Contactpersonen geadresseerden** \> **Contacts** en bekijk dat de lijst met gebruikers correct is gesynchroniseerd vanuit uw on-premises omgeving.
