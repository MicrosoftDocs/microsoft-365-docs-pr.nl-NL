---
title: Configureer groepen en gebruikers voor een ontwikkel-/testomgeving voor politieke campagnes
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 0e22bcf3-bad3-42a4-b44f-276e0cf4790f
description: 'Overzicht: maak proefabonnementen voor Office 365 en Enterprise Mobility + Security (EMS) met gebruikers en groepen voor een ontwikkel-/testomgeving voor politieke campagnes.'
ms.openlocfilehash: a61cc21b67cafd213d47076698929d0aa2644d08
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42810937"
---
# <a name="configure-groups-and-users-for-a-political-campaign-devtest-environment"></a>Configureer groepen en gebruikers voor een ontwikkel-/testomgeving voor politieke campagnes

 **Overzicht:** maak proefabonnementen voor Office 365 en Enterprise Mobility + Security (EMS) met gebruikers en groepen voor een ontwikkel-/testomgeving voor politieke campagnes.

Gebruik de instructies in dit artikel om een ontwikkel-/testomgeving te maken met vereenvoudigde gebruikersaccounts en groepen voor de [Microsoft-beveiligingsrichtlijnen voor politieke campagnes, non-profitorganisaties en andere agile organisaties](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md).

## <a name="phase-1-create-your-office-365-devtest-environment"></a>Fase 1: creëer uw ontwikkel-/testomgeving voor Office 365

In deze fase creëert u proefabonnementen voor Office 365 E5 en Enterprise Mobility + Security (EMS) E5 voor een fictieve organisatie die een politieke campagne vertegenwoordigt.

Volg eerst de instructies in **fase 2** van de [ontwikkel-/testomgeving voor Office 365](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment).

Meld u vervolgens aan voor het proefabonnement EMS E5 en voeg het toe aan dezelfde organisatie als uw proefabonnement op Office 365.

1. Indien nodig meldt u zich aan bij het beheercentrum met de inloggegevens van het algemene beheerdersaccount van uw proefabonnement. Zie [Waar kan ik me aanmelden in Office 365?](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) voor hulp.

2. Klik op de tegel **Beheerder**.

3. Klik op het tabblad **Microsoft 365-beheercentrum** in uw browser in de linkernavigatiebalk op **Facturering >** Services.

4. Zoek op de pagina **Services aanschaffen** naar het item **Enterprise Mobility + Security E5**. Plaats de muisaanwijzer erop en klik op **gratis proefversie**.

5. Kies op de pagina **Uw bestelling bevestigen** de optie **Nu proberen**.

6. Klik op de pagina **Ontvangst bestelling** op **Doorgaan**.

Activeer vervolgens de EMS E5-licentie voor uw globale beheerdersaccount.

1. Klik op het tabblad **Microsoft 365-beheercentrum** in uw browser in de linkernavigatiebalk op **Gebruikers > Actieve gebruikers**.

2. Klik op uw globale beheerdersaccount en klik vervolgens op **bewerken** voor **productlicenties**.

3. Schakel in het deelvenster **productlicenties** de productlicentie voor **Enterprise Mobility + Security E5** **in**, klik op **opslaan** en klik tweemaal op **sluiten**.

## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups"></a>Fase 2: uw Microsoft Azure AD-groepen (Active Directory) maken en configureren

In deze fase maakt en configureert u de Microsoft Azure AD-groepen voor uw campagne.

Maak eerst een set groepen voor een normale politieke campagne met de Microsoft Azure-portal.

1. Open een afzonderlijk tabblad in uw browser en ga naar de Microsoft Azure-portal op [https://portal.azure.com](https://portal.azure.com). Indien nodig meldt u zich aan met de inloggegevens van het algemene beheerdersaccount van uw proefabonnement op Office 365 E5.

2. Klik in de Microsoft Azure-portal op **Azure Active Directory > gebruikers en groepen > alle groepen**.

3. Voer de volgende stappen uit voor elke groepsnaam in deze lijst:

   - Senior en strategisch personeel

   - IT-personeel

   - Analytisch personeel

   - Normaal kernpersoneel

   - Operationeel personeel

   - Veldmedewerkers

1. Klik in de blade **Alle groepen** op **+ Nieuwe groep**.

2. Typ de naam van de groep in de lijst in **naam**.

3. Selecteer **dynamische gebruiker** voor **lidmaatschap**.

4. Klik op **ja** voor **Office-functies inschakelen**.

5. Klik op **dynamische query toevoegen**.

6. Selecteer voor **gebruikers toevoegen waar**de optie **afdeling**.

7. Selecteer in het volgende veld **is gelijk aan**.

8. Typ de groepsnaam uit de lijst in het volgende veld.

9. Klik op **query toevoegen**en klik vervolgens op **maken**.

10. Klik op **gebruikers en groepen: alle groepen**.

Vervolgens configureert u de groepen zo dat er automatisch Office 365 E5- en EMS E5-licenties worden toegewezen aan leden.

1. Klik in de Microsoft Azure-portal op **licenties voor Azure Active Directory > alle producten**.

2. Selecteer in de lijst zowel **Enterprise Mobility + Security E5** als **Office 365 Enterprise E5**en klik vervolgens op **+ Toewijzen**.

3. Klik in de blade **Licentie toewijzen** op ** Gebruikers en groepen**.

4. In de lijst met groepen selecteert u het volgende:

   - Analytisch personeel

   - Veldmedewerkers

   - IT-personeel

   - Operationeel personeel

   - Normaal kernpersoneel

   - Senior en strategisch personeel

5. Klik op **Selecteren** en klik vervolgens op **Toewijzen**.

6. Sluit het tabblad Microsoft Azure-portal in uw browser.

## <a name="phase-3-add-your-user-accounts"></a>Fase 3: uw gebruikersaccounts toevoegen

In deze fase voegt u de voorbeeldgebruikersaccounts voor uw politieke campagne toe.

Eerst maakt u [Verbinding met de Windows PowerShell voor Graph-module van Azure Active Directory](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).

Vervolgens vult u de naam van uw organisatie in, uw locatie en een gemeenschappelijk wachtwoord in en voert u vervolgens deze opdrachten uit in de opdrachtprompt van Windows PowerShell of de Integrated Scripting Environment (ISE):

```powershell
$orgName="<organization name, such as contoso for the contoso.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$deptName="Senior and strategic staff"
$userNames=@("Candidate","ChiefOfStaff","Strategic1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="IT staff"
$userNames=@("ITAdmin1","ITAdmin2")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Analytics staff"
$userNames=@("DataScientist1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Regular core staff"
$userNames=@("Regular1","Regular2")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Operations staff"
$userNames=@("Operations1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Field staff"
$userNames=@("FieldConsultant1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
```

> [!IMPORTANT]
> U gebruikt hier een gemeenschappelijk wachtwoord voor automatisering en configuratiegemak in een ontwikkel-/testomgeving. Dit wordt afgeraden voor productie-omgevingen. Als u zich aanmeldt met een van deze nieuwe gebruikersaccounts, wordt u gevraagd het wachtwoord te wijzigen.

Gebruik deze stappen om te controleren of lidmaatschap van een dynamische groep en groepsgebaseerde licenties correct werken.

1. Klik in het tabblad **Microsoft Office voor Thuisgebruik** van uw browser op de tegel **Beheerder**.

2. Klik in het nieuwe tabblad **Microsoft 365-beheercentrum** van uw browser op **Gebruikers**.

3. Klik in de lijst met gebruikers op **gegadigde**.

4. Controleer in het deelvenster met de eigenschappen van het **kandidaat**-gebruikersaccount of:

   - Het lid is van de groep **Senior en strategisch personeel** (in **groepslidmaatschappen**).

   - Het de licenties **Enterprise Mobility + Security E5** en **Office 365 Enterprise E5** heeft toegewezen gekregen (in **productlicenties**).

5. Sluit het deelvenster voor het gebruikersaccount **gegadigde**.

## <a name="record-values-for-future-reference"></a>Noteer waarden voor toekomstig gebruik

Noteer deze waarden voor het werken met de proefabonnementen voor Office 365 en EMS voor deze ontwikkel- en testomgeving:

- De naam van de organisatie voor uw proefabonnement: ![Onderstrepen](../../media/Common-Images/TableLine.png)

  Voor de domeinnaam van het proefabonnement van contoso.onmicrosoft.com is de naam van de organisatie 'contoso'.

- De naam van de globale beheerder van Office 365: ![Onderstrepen](../../media/Common-Images/TableLine.png).onmicrosoft.com

  Sla het wachtwoord voor dit account en het algemene wachtwoord voor de andere gebruikersaccounts op een veilige locatie op.

## <a name="next-step"></a>Volgende stap

Maak de vier verschillende soorten SharePoint Online-teamsites in deze ontwikkel-/testomgeving met [teamsites maken in een ontwikkel-en testomgeving voor politieke campagnes](create-team-sites-in-a-political-campaign-dev-test-environment.md).

## <a name="see-also"></a>Zie ook

[Microsoft-beveiligingsrichtlijnen voor politieke campagnes, non-profitorganisaties en andere flexibele organisaties](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)

[Team sites maken in een ontwikkel-en testomgeving voor politieke campagnes](create-team-sites-in-a-political-campaign-dev-test-environment.md)

[Testlabrichtlijnen voor cloudacceptatie (TLG's)](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)

[Cloudacceptatie en hybride oplossingen](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
