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
description: Lees meer over het beheren van e-mailgebruikers in Exchange Online Protection (EOP), inclusief het gebruik van adreslijstsynchronisatie, EAC en PowerShell om gebruikers te beheren.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 34edafea7567da04094ea386d469d3d27937eee5
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166391"
---
# <a name="manage-mail-users-in-standalone-eop"></a>E-mailgebruikers beheren in standalone EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
-  [Zelfstandige versie van Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)

In zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken zijn e-mailgebruikers het fundamentele type gebruikersaccount. Een e-mailgebruiker heeft accountreferenties in uw zelfstandige EOP-organisatie en heeft toegang tot resources (met machtigingen toegewezen). Het e-mailadres van een e-mailgebruiker is extern (bijvoorbeeld in uw on-premises e-mailomgeving).

> [!NOTE]
> Wanneer u een e-mailgebruiker maakt, is het bijbehorende gebruikersaccount beschikbaar in het Microsoft 365-beheercentrum. Wanneer u een gebruikersaccount maakt in het Microsoft 365-beheercentrum, kunt u dat account niet gebruiken om een e-mailgebruiker te maken.

De aanbevolen methode voor het maken en beheren van e-mailgebruikers in zelfstandige EOP is het gebruik van adreslijstsynchronisatie zoals wordt beschreven in de sectie Adreslijstsynchronisatie gebruiken voor het beheren van [e-mailgebruikers](#use-directory-synchronization-to-manage-mail-users) verderop in dit artikel.

Voor zelfstandige EOP-organisaties met een klein aantal gebruikers kunt u e-mailgebruikers toevoegen en beheren in het Exchange-beheercentrum (EAC) of in zelfstandige EOP PowerShell, zoals wordt beschreven in dit artikel.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Als u het Exchange-beheercentrum (EAC) wilt openen, gaat u naar [het Exchange-beheercentrum in de zelfstandige EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- Wanneer u e-mailgebruikers maakt in EOP PowerShell, kan er beperkingen worden aangetroffen. Bovendien wordt in de EOP PowerShell-cmdlets een batchverwerkingsmethode gebruikt die resulteert in een doorloopvertraging van een paar minuten voordat de resultaten van de opdrachten zichtbaar zijn.

- U moet machtigingen toegewezen krijgen in Exchange Online Protection voordat u de procedures in dit artikel kunt uitvoeren. U hebt met  name de rollen E-mailontvanger nodig (maken) en E-mailontvangers (wijzigen), die standaard zijn toegewezen aan de rollengroepen Organisatiebeheer **(globale** beheerders) en **Recipient Management.**  Zie Machtigingen in zelfstandige EOP en gebruik het [EAC](feature-permissions-in-eop.md) om de lijst met leden [in rollengroepen te wijzigen voor meer informatie.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Zie Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor informatie over [sneltoetsen](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)die van toepassing kunnen zijn op de procedures in dit artikel.

> [!TIP]
> Hebt u problemen? Vraag om hulp op de Exchange-forums. Ga naar het [forum van Exchange Online Protection.](https://go.microsoft.com/fwlink/p/?linkId=285351)

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a>Het Exchange-beheercentrum gebruiken om e-mailgebruikers te beheren

### <a name="use-the-eac-to-create-mail-users"></a>Het EAC gebruiken om e-mailgebruikers te maken

1. Ga in het EAC naar **Contactpersonen van** \> **geadresseerden**

2. Klik **op het** pictogram ![ Nieuw. ](../../media/ITPro-EAC-AddIcon.png) Configureer **de volgende instellingen op** de pagina Nieuwe e-mailgebruiker die wordt geopend. Instellingen die zijn gemarkeerd met een <sup>\*</sup> zijn vereist.

   - **Voornaam**

   - **Initialen:** de middelste initialen van de persoon.

   - **Achternaam**

   - <sup>\*</sup>**Weergavenaam:** dit vak bevat standaard de waarden uit de vakken **Voornaam,** **Initialen** en **Achternaam.** U kunt deze waarde accepteren of wijzigen. De waarde moet uniek zijn en een maximumlengte van 64 tekens hebben.

   - <sup>\*</sup>**Alias:** Voer een unieke alias in voor de gebruiker met maximaal 64 tekens

   - **Extern e-mailadres:** Voer het e-mailadres van de gebruiker in. Het domein moet buiten uw organisatie in de cloud zijn.

   - <sup>\*</sup>**Gebruikers-id:** voer het account in dat de persoon gebruikt om zich aan te melden bij de service. De gebruikers-id bestaat uit een gebruikersnaam aan de linkerkant van het @-symbool (@) en een domein aan de rechterkant.

   - <sup>\*</sup>**Nieuw wachtwoord** en wachtwoord <sup>\*</sup> **bevestigen:** voer het accountwachtwoord in en voer het opnieuw in. Controleer of het wachtwoord aan de wachtwoordlengte, complexiteit en geschiedenisvereisten van uw organisatie voldoet.

3. Wanneer u klaar bent, klikt u op **Opslaan om** de e-mailgebruiker te maken.

### <a name="use-the-eac-to-modify-mail-users"></a>Het EAC gebruiken om e-mailgebruikers te wijzigen

1. Ga in het EAC naar **Contactpersonen van** \> **geadresseerden.**

2. Selecteer de e-mailgebruiker die u wilt wijzigen en klik op **het pictogram** ![ ](../../media/ITPro-EAC-AddIcon.png) Bewerken.

3. Klik op de pagina eigenschappen van e-mailgebruiker die wordt geopend op een van de volgende tabbladen om eigenschappen weer te geven of te wijzigen.

   Klik op **Opslaan** wanneer u gereed bent.

#### <a name="general"></a>Algemeen

Gebruik het **tabblad Algemeen** om basisinformatie over de e-mailgebruiker weer te geven of te wijzigen.

- **Voornaam**

- **Initialen**

- **Achternaam**

- **Weergavenaam:** deze naam wordt weergegeven in het adresboek van uw organisatie, op de regels Aan: en Van: in e-mail en in de lijst met contactpersonen in het EAC. Deze naam mag geen lege spaties voor of na de weergavenaam bevatten.

- **Gebruikers-id:** dit is het account van de gebruiker in Microsoft 365. U kunt deze waarde hier niet wijzigen.

#### <a name="contact-information"></a>Contactgegevens

Gebruik het **tabblad Contactgegevens** om de contactgegevens van de gebruiker weer te geven of te wijzigen. De informatie op deze pagina wordt weergegeven in het adresboek.

- **Straat**
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

Gebruik het **tabblad Organisatie** om gedetailleerde informatie op te nemen over de rol van de gebruiker in de organisatie.

- **Title**
- **Afdeling**
- **Company**

### <a name="use-the-eac-to-remove-mail-users"></a>Het EAC gebruiken om e-mailgebruikers te verwijderen

1. Ga in het EAC naar **Contactpersonen van** \> **geadresseerden.**

2. Selecteer de e-mailgebruiker die u wilt verwijderen en klik op **het pictogram** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Verwijderen.

## <a name="use-powershell-to-manage-mail-users"></a>PowerShell gebruiken om e-mailgebruikers te beheren

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a>Zelfstandige EOP PowerShell gebruiken om e-mailgebruikers weer te geven

Voer de volgende opdracht uit om een overzichtslijst met alle e-mailgebruikers in zelfstandige EOP PowerShell te retourneren:

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

Als u gedetailleerde informatie over een specifieke e-mailgebruiker wilt bekijken, vervangt u deze door de naam, de alias of de accountnaam van de e-mailgebruiker en voert u \<MailUserIdentity\> de volgende opdrachten uit:

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

Zie Get-Recipient en [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-recipient) voor gedetailleerde syntaxis- en [parameterinformatie.](https://docs.microsoft.com/powershell/module/exchange/get-user)

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a>Zelfstandige EOP PowerShell gebruiken om e-mailgebruikers te maken

Gebruik de volgende syntaxis om e-mailgebruikers te maken in zelfstandige EOP PowerShell:

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

**Opmerkingen**:

- De  parameter Name is vereist, heeft een maximumlengte van 64 tekens en moet uniek zijn. Als u de parameter _DisplayName_ niet gebruikt, wordt de waarde van de parameter _Name_ gebruikt voor de weergavenaam.
- Als u de _aliasparameter_ niet gebruikt, wordt de linkerkant van de parameter _MicrosoftOnlineServicesID_ gebruikt voor de alias.
- Als u de parameter _ExternalEmailAddress_ niet gebruikt, wordt de waarde _MicrosoftOnlineServicesID_ gebruikt voor het externe e-mailadres.

In dit voorbeeld wordt een e-mailgebruiker gemaakt met de volgende instellingen:

- De naam is JeffreyZeng en de weergavenaam is Jeffrey Zeng.
- De voornaam is Jeffrey en de achternaam is Zeng.
- De alias is jeffreyz.
- Het externe e-mailadres wordt jzeng@tailspintoys.com.
- De accountnaam is jeffreyz@contoso.onmicrosoft.com.
- Het wachtwoord is Pa$$word 1.

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

Zie [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser)voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a>Zelfstandige EOP PowerShell gebruiken om e-mailgebruikers te wijzigen

Gebruik de volgende syntaxis om bestaande e-mailgebruikers in zelfstandige EOP PowerShell te wijzigen:

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

In dit voorbeeld wordt de eigenschap Bedrijf voor alle e-mailgebruikers op Contoso stelt.

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

Zie [Set-EOPMailUser voor gedetailleerde syntaxis- en parameterinformatie.](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser)

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a>Zelfstandige EOP PowerShell gebruiken om e-mailgebruikers te verwijderen

Als u e-mailgebruikers in zelfstandige EOP PowerShell wilt verwijderen, vervangt u door de naam, alias of accountnaam van de e-mailgebruiker en voer u \<MailUserIdentity\> de volgende opdracht uit:

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

In dit voorbeeld wordt de e-mailgebruiker voor Jeffrey Zeng verwijderd.

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

Zie [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser)voor gedetailleerde syntaxis- en parameterinformatie.

## <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Gebruik een van de volgende procedures om te controleren of u e-mailgebruikers hebt gemaakt, gewijzigd of verwijderd in de zelfstandige EOP:

- Ga in het EAC naar **Contactpersonen van** \> **geadresseerden.** Controleer of de e-mailgebruiker wordt weergegeven (of niet wordt weergegeven). Selecteer de e-mailgebruiker en bekijk de  informatie in het detailvenster of klik op het pictogram ![ Bewerken om de instellingen weer te ](../../media/ITPro-EAC-AddIcon.png) geven.

- Voer in zelfstandige EOP PowerShell de volgende opdracht uit om te controleren of de e-mailgebruiker wordt vermeld (of niet wordt weergegeven):

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- Vervang \<MailUserIdentity\> door de naam, alias of accountnaam van de e-mailgebruiker en voer de volgende opdrachten uit om de instellingen te controleren:

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a>Adreslijstsynchronisatie gebruiken om e-mailgebruikers te beheren

In zelfstandige EOP is adreslijstsynchronisatie beschikbaar voor klanten met on-premises Active Directory. U kunt deze accounts synchroniseren met Azure Active Directory (Azure AD), waar kopieën van de accounts worden opgeslagen in de cloud. Wanneer u uw bestaande **gebruikersaccounts** synchroniseert met Azure Active Directory, kunt u deze gebruikers weergeven in het deelvenster Ontvangers van het Exchange-beheercentrum (EAC) of in zelfstandige EOP PowerShell.

**Opmerkingen**:

- Als u adreslijstsynchronisatie gebruikt om uw geadresseerden te beheren, kunt u nog steeds gebruikers toevoegen en beheren in het Microsoft 365-beheercentrum, maar ze worden niet gesynchroniseerd met uw on-premises Active Directory. Dit komt omdat met adreslijstsynchronisatie alleen geadresseerden vanuit uw on-premises Active Directory worden gesynchroniseerd met de cloud.

- Het gebruik van adreslijstsynchronisatie wordt aanbevolen voor gebruik met de volgende functies:

  - **Lijsten met veilige afzenders** en lijsten met geblokkeerde afzenders in Outlook: wanneer deze worden gesynchroniseerd met de service, hebben deze lijsten voorrang op spamfilters in de service. Hierdoor kunnen gebruikers hun eigen lijst met veilige afzenders en lijst met geblokkeerde afzenders met afzonderlijke afzenders en domeingegevens beheren. Zie [Instellingen voor ongewenste e-mail configureren voor Exchange Online-postvakken](configure-junk-email-settings-on-exo-mailboxes.md) voor meer informatie.

  - **Op directory gebaseerde randblokkering (DBEB:** zie [Op](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)directory gebaseerde randblokkering gebruiken om berichten te weigeren die naar ongeldige geadresseerden zijn verzonden) voor meer informatie over DBEB.

  - **Toegang tot quarantaine door eindgebruikers:** geadresseerden moeten een geldige gebruikers-id en een geldig wachtwoord in de service hebben om in quarantaine te kunnen worden geplaatst. Zie Berichten in quarantaine zoeken en vrijgeven als gebruiker voor meer informatie [over quarantaine.](find-and-release-quarantined-messages-as-a-user.md)

  - Regels voor e-mailstromen (ook wel **transportregels genoemd).** Wanneer u adreslijstsynchronisatie gebruikt, worden uw bestaande Active Directory-gebruikers en -groepen automatisch geüpload naar de cloud. Vervolgens kunt u regels voor de e-mailstroom maken die zijn gericht op specifieke gebruikers en/of groepen zonder ze handmatig toe te voegen aan de service. Dynamische [distributiegroepen kunnen](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) niet worden gesynchroniseerd via adreslijstsynchronisatie.

Vraag de benodigde machtigingen op en bereid u voor op adreslijstsynchronisatie, zoals wordt beschreven in [Wat is hybride identiteit met Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity)

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a>Adreslijst synchroniseren met Azure Active Directory Connect (AAD Connect)

1. Activeer adreslijstsynchronisatie zoals wordt beschreven in [Azure AD Connect-synchronisatie: Synchronisatie](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)begrijpen en aanpassen.

2. Installeer en configureer een on-premises computer om AAD Connect uit te voeren zoals beschreven in Vereisten [voor Azure AD Connect.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)

3. [Selecteer het installatietype dat u wilt gebruiken voor Azure AD Connect:](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation)

   - [Express](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [Aangepast](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [Pass-through-verificatie](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> Wanneer u de wizard Configuratie van het hulpprogramma Azure Active Directory-synchronisatie **hebt** uitgevoerd, MSOL_AD_SYNC account gemaakt in uw Active Directory-forest. Dit account wordt gebruikt voor het lezen en synchroniseren van uw on-premises Active Directory-gegevens. Zorg ervoor dat TCP 443 op de lokale adreslijstsynchronisatieserver is geopend om adreslijstsynchronisatie correct te laten werken.

Controleer na het configureren van de synchronisatie of AAD Connect correct wordt gesynchroniseerd. Ga in het EAC naar contactpersonen van geadresseerden en bekijk dat de lijst met gebruikers juist is gesynchroniseerd  \>  vanuit uw on-premises omgeving.
