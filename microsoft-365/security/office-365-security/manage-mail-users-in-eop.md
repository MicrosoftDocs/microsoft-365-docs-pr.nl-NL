---
title: E-mailgebruikers beheren in EOP
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Het definiëren van e-mailgebruikers is een belangrijk onderdeel van het beheer van de Exchange Online Protection (EOP)-service.
ms.openlocfilehash: bdbc3cd54901d53b4a7d01bcf513a9b9a0df1c01
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42810950"
---
# <a name="manage-mail-users-in-eop"></a>E-mailgebruikers beheren in EOP

Het definiëren van e-mailgebruikers is een belangrijk onderdeel van het beheer van de Exchange Online Protection (EOP)-service. Er zijn verschillende manieren waarop u gebruikers beheren in EOP:

- **Adreslijstsynchronisatie gebruiken om e-mailgebruikers te beheren:** als uw bedrijf bestaande gebruikersaccounts heeft in een on-premises Active Directory-omgeving, u deze accounts synchroniseren met Azure Active Directory (AD), waar een kopie van de accounts in de cloud is opgeslagen. Wanneer u uw bestaande gebruikersaccounts synchroniseert met Azure Active Directory, u deze gebruikers weergeven in het deelvenster **Geadresseerden** van het Exchange-beheercentrum (EAC). Het gebruik van adreslijstsynchronisatie wordt aanbevolen.

- **Gebruik de EAC om e-mailgebruikers te beheren:** E-mailgebruikers rechtstreeks toevoegen en beheren in de EAC. Dit is de eenvoudigste manier om e-mailgebruikers toe te voegen en is handig voor het toevoegen van één gebruiker tegelijk.

- **Gebruik PowerShell om e-mailgebruikers te beheren:** E-mailgebruikers toevoegen en beheren in Exchange Online Protection PowerShell. Deze methode is handig voor het toevoegen van meerdere records en het maken van scripts.

> [!NOTE]
> U gebruikers toevoegen in het Microsoft 365-beheercentrum, maar deze gebruikers kunnen niet worden gebruikt als e-mailontvangers.

## <a name="before-you-begin"></a>Voordat u begint

- Zie [Exchange-beheercentrum in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md)als u het Exchange-beheercentrum wilt openen.

- U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren. Zie het item 'Gebruikers, contactpersonen en rolgroepen' in [Functiemachtigingen in EOP](feature-permissions-in-eop.md)om te zien welke machtigingen u nodig hebt.

- Houd er rekening mee dat bij het maken van e-mailgebruikers met Exchange Online Protection PowerShell-cmdlets u mogelijk throttling tegenkomen.

- De PowerShell-opdrachten in dit onderwerp gebruiken een batchverwerkingsmethode die resulteert in een propagatievertraging van enkele minuten voordat de resultaten van de opdrachten zichtbaar zijn.

- Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)voor meer informatie over het gebruik van Windows PowerShell om verbinding te maken met Exchange Online Protection.

- Zie [Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in dit onderwerp.

> [!TIP]
> Heb je problemen? Vraag om hulp op het [Exchange Online Protection-forum.](https://go.microsoft.com/fwlink/p/?linkId=285351)

## <a name="use-directory-synchronization-to-manage-mail-users"></a>Adreslijstsynchronisatie gebruiken om e-mailgebruikers te beheren

In deze sectie vindt u informatie over het beheren van e-mailgebruikers met behulp van adreslijstsynchronisatie.

**Toelichting :**

- Als u adreslijstsynchronisatie gebruikt om uw geadresseerden te beheren, u nog steeds gebruikers toevoegen en beheren in het Microsoft 365-beheercentrum, maar deze worden niet gesynchroniseerd met uw on-premises Active Directory. Dit komt omdat adreslijstsynchronisatie alleen ontvangers **synchroniseert vanuit** uw on-premises Active Directory **naar** de cloud.

- Adreslijstsynchronisatie wordt aanbevolen voor gebruik met de volgende functies:

  - **Lijsten met veilige afzenders en geblokkeerde afzenders**in Outlook: Wanneer deze lijsten zijn gesynchroniseerd met de service, hebben deze lijsten voorrang op spamfiltering in de service. Hiermee kunnen gebruikers hun eigen veilige afzender en geblokkeerde afzenderlijsten per gebruiker of per domein beheren.

  - **Directory Based Edge Blocking (DBEB)**: Zie [Directory Based Edge Blocking gebruiken om berichten die naar ongeldige geadresseerden worden verzonden, te weigeren.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)

  - **Spamquarantaine voor eindgebruikers**: Om toegang te krijgen tot de spamquarantaine van de eindgebruiker, moeten eindgebruikers in het beschikken over een geldige Office 365-gebruikersnaam en -wachtwoord. EOP-klanten die on-premises postvakken beschermen, moeten geldige e-mailgebruikers zijn.

  - **Regels voor e-mailstroom:** Wanneer u adreslijstsynchronisatie gebruikt, worden uw bestaande Active Directory-gebruikers en -groepen automatisch geüpload naar de cloud en u vervolgens regels voor e-mailstroom (ook wel transportregels genoemd) maken die zich richten op specifieke gebruikers en/of groepen zonder ze handmatig toe te voegen via de EAC of Exchange Online Protection PowerShell. Houd er rekening mee dat [dynamische distributiegroepen](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) niet kunnen worden gesynchroniseerd via adreslijstsynchronisatie.

Ontvang de benodigde machtigingen en bereid u voor op adreslijstsynchronisatie, zoals beschreven in [Wat is hybride identiteit met Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).

### <a name="to-synchronize-user-directories-with-azure-active-directory-connect-aad-connect"></a>Gebruikersmappen synchroniseren met Azure Active Directory Connect (AAD Connect)

Als u gebruikers wilt synchroniseren met Azure Active Directory (AAD), moet u eerst **adreslijstsynchronisatie activeren**, zoals beschreven in [Azure AD Connect-synchronisatie: synchronisatie begrijpen en aanpassen](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).

Vervolgens is de installatie en configuratie van een on-premises computer om AAD Connect uit te voeren (als u er nog geen hebt - iets dat de moeite waard is om van tevoren te controleren). In het onderwerp [AAD Connect instellen, het onderwerp expresmanier,](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express) wordt uitgelegd hoe u uw accounts instellen en synchroniseren van on-premises naar Azure AD met AAD Connect.

Maar voordat u dat werk doet, moet u ervoor zorgen dat [u aan de vereisten voldoet](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)en uw [installatietype kiezen.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation) De eerdere link is naar een kort artikel voor express installeert. U ook artikelen vinden over [aangepaste installaties](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)of [doorgeefverificatie](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start) als ze nodig zijn.

> [!IMPORTANT]
> Wanneer u de wizard Configuratie van Azure Active Directory-synchronisatieprogramma's hebt voltooid, wordt het **MSOL_AD_SYNC-account** gemaakt in uw Active Directory-forest. Dit account wordt gebruikt om uw on-premises Active Directory-gegevens te lezen en te synchroniseren. Zorg ervoor dat TCP 443 op uw lokale mapsynchronisatieserver is geopend om de synchronisatie van de map correct te laten werken.

Nadat u uw synchronisatie hebt geconfigureerd, moet u controleren of EOP correct synchroniseert. Ga in de EAC naar **Geadresseerden** \> **contactpersonen** en bekijk dat de lijst met gebruikers correct is gesynchroniseerd vanuit uw on-premises omgeving.

## <a name="use-the-eac-to-manage-mail-users"></a>De EAC gebruiken om e-mailgebruikers te beheren

In deze sectie vindt u informatie over het rechtstreeks toevoegen en beheren van e-mailgebruikers in de EAC.

### <a name="use-the-eac-to-add-a-mail-user"></a>De EAC gebruiken om een e-mailgebruiker toe te voegen

1. Maak een e-mailgebruiker door naar **Geadresseerden** \> **contactpersonen** in de EAC te gaan en vervolgens op **Nieuw +**.

2. Voer op de pagina **Nieuwe e-mailgebruiker** de gegevens van de gebruiker in, waaronder:

   ****

   |**Eigenschap E-mailgebruiker**|**Beschrijving**|
   |:-----|:-----|
   |**Voornaam**, **Initialen**en **Achternaam**|Typ de volledige naam van de gebruiker in de juiste vakken.|
   |**Weergavenaam**|Typ een naam met maximaal 64 tekens. Standaard worden in dit vak de namen weergegeven in de vakken **Voornaam,** **Initialen**en **Achternaam.** De weergavenaam is vereist.|
   |**Alias**|Typ een unieke alias met maximaal 64 tekens voor de gebruiker. De alias is vereist.|
   |**Extern e-mailadres**|Typ het externe e-mailadres van de gebruiker.|
   |**Gebruikersnaam**|Typ de naam die de e-mailgebruiker zal gebruiken om zich aan te melden bij de service. De aanmeldingsnaam van de gebruiker bestaat uit een gebruikersnaam aan de linkerkant van het at (@) symbool en een achtervoegsel aan de rechterkant. Meestal is het achtervoegsel de domeinnaam waarin het gebruikersaccount zich bevindt.|
   |**Nieuw wachtwoord**|Typ het wachtwoord dat de e-mailgebruiker gebruikt om zich aan te melden bij de service. Zorg ervoor dat het wachtwoord dat u verstrekt voldoet aan de wachtwoordlengte, complexiteit en geschiedenisvereisten van het domein waarin u het gebruikersaccount maakt.|
   |**Wachtwoord bevestigen**|Typ het wachtwoord opnieuw om het te bevestigen.|

3. Klik **op Opslaan** om de nieuwe e-mailgebruiker te maken. De nieuwe gebruiker moet worden weergegeven in de lijst met gebruikers.

### <a name="use-the-eac-to-edit-or-remove-a-mail-user"></a>De EAC gebruiken om een e-mailgebruiker te bewerken of te verwijderen

- Ga in de EAC naar **Contactpersonen voor geadresseerden** \> **Contacts**. Klik in de lijst met gebruikers op de gebruiker die **Edit** ![u wilt weergeven of wijzigen en selecteer vervolgens het pictogram](../../media/ITPro-EAC-EditIcon.gif) Bewerken bewerken om de gebruikersinstellingen zo nodig bij te werken. U de naam, alias of contactgegevens van de gebruiker wijzigen en u gedetailleerde informatie opnemen over de rol van de gebruiker in de organisatie. U ook een gebruiker **Remove** ![selecteren](../../media/ITPro-EAC-RemoveIcon.gif) en vervolgens pictogram Verwijderen kiezen om deze te verwijderen.

## <a name="use-exchange-online-protection-powershell-to-manage-mail-users"></a>Exchange Online Protection PowerShell gebruiken om e-mailgebruikers te beheren

In deze sectie vindt u informatie over het toevoegen en beheren van e-mailgebruikers met behulp van externe Windows PowerShell.

### <a name="use-eop-powershell-to-add-a-mail-user"></a>EOP PowerShell gebruiken om een e-mailgebruiker toe te voegen

In dit voorbeeld wordt de cmdlet [Nieuw-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-eopmailuser) gebruikt om een gebruikersaccount met e-mail voor Jeffrey Zeng in EOP te maken met de volgende details:

- De voornaam is Jeffrey en de achternaam is Zeng.

- De naam is Jeffrey en de display naam is Jeffrey Zeng.

- De alias is jeffreyz.

- Het externe e-mailadres is jzeng@tailspintoys.com.

- De naam van het Office 365-aanmeldingsteken is jeffreyz@contoso.onmicrosoft.com.

- Het wachtwoord is Pa$$word1.

```PowerShell
New-EOPMailUser -LastName Zeng -FirstName Jeffrey -DisplayName "Jeffrey Zeng" -Name Jeffrey -Alias jeffreyz -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -ExternalEmailAddress jeffreyz@tailspintoys.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force)
```

Voer de volgende opdracht uit om informatie over nieuwe e-mailgebruiker Jeffrey Zeng weer te geven om te controleren of dit werkt:

```PowerShell
Get-User -Identity "Jeffrey Zeng"
```

Zie [Gebruiker worden opdoen](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-eop-powershell-to-edit-the-properties-of-a-mail-user"></a>EOP PowerShell gebruiken om de eigenschappen van een e-mailgebruiker te bewerken

Gebruik de [cmdlets Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) en [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopmailuser) om eigenschappen voor e-mailgebruikers weer te geven of te wijzigen.

In dit voorbeeld wordt het externe e-mailadres voor Pilar Pinilla ingesteld.

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

In dit voorbeeld wordt de eigenschap Bedrijf ingesteld voor alle e-mailgebruikers op Contoso.

```PowerShell
$Recip = Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')}
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

Als u wilt controleren of dit heeft gewerkt, gebruikt u de cmdlet [Ontvangen om](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) de wijzigingen te verifiëren. (Houd er rekening mee dat u meerdere eigenschappen voor meerdere e-mailcontactpersonen weergeven.)

```PowerShell
Get-Recipient -Identity "Pilar Pinilla" | Format-List
```

Voer in het vorige voorbeeld, waar de eigenschap Bedrijf is ingesteld op Contoso voor alle e-mailgebruikers, de volgende opdracht uit om de wijzigingen te verifiëren:

```PowerShell
Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')} | Format-List Name,Company
```

> [!IMPORTANT]
> Deze cmdlet maakt gebruik van een batchverwerkingsmethode die resulteert in een propagatievertraging van enkele minuten voordat de resultaten van de cmdlet zichtbaar zijn.

### <a name="use-eop-powershell-to-remove-a-mail-user"></a>EOP PowerShell gebruiken om een e-mailgebruiker te verwijderen

In dit voorbeeld wordt de cmdlet [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopmailuser) gebruikt om gebruiker Jeffrey Zeng te verwijderen:

```PowerShell
Remove-EOPMailUser -Identity Jeffrey
```
Voer de cmdlet [Ontvangen-ontvanger](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) uit om te controleren of de e-mailgebruiker niet meer bestaat.

```PowerShell
Get-Recipient Jeffrey | Format-List
```
