---
title: Een geïsoleerde SharePoint Online-teamsite beheren
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: Een afzonderlijke SharePoint Online-teamsite beheren, nieuwe gebruikers en groepen toevoegen, gebruikers en groepen verwijderen en een submap documenten met aangepaste machtigingen maken.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 20e354de77b70ea69d69e201bd3b1d40ea32cc5b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289519"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a>Een geïsoleerde SharePoint Online-teamsite beheren

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender voor Office 365-abonnement 1](office-365-atp.md)
- SharePoint Online 

 **Overzicht:** Beheer uw afzonderlijke SharePoint Online-teamsite met deze procedures.

In dit artikel worden veelvoorkomende beheerbewerkingen beschreven voor een afzonderlijke SharePoint Online-teamsite.

## <a name="add-a-new-user"></a>Een nieuwe gebruiker toevoegen

Wanneer iemand nieuw lid wordt van de site, moet u bepalen welk deelnameniveau deze persoon aan de site heeft:

- Beheer: Het nieuwe gebruikersaccount toevoegen aan de toegangsgroep voor sitebeheerders

- Actieve samenwerking: het gebruikersaccount toevoegen aan de groep met siteleden

- Bekijken: Het gebruikersaccount toevoegen aan de toegangsgroep voor sitegebruikers

Als u gebruikersaccounts en -groepen beheert via Active Directory Domain Services (AD DS), voegt u de juiste gebruikers toe aan de juiste toegangsgroepen met behulp van de normale AD DS-gebruikers- en groepsbeheerprocedures en wacht u op synchronisatie met uw abonnement.

Als u gebruikersaccounts en -groepen beheert via Microsoft 365, kunt u het Microsoft 365-beheercentrum of Microsoft PowerShell gebruiken:

- Meld u voor het Microsoft 365-beheercentrum aan met een gebruikersaccount aan welke de rol Gebruikersaccountbeheerder of Bedrijfsbeheerder is toegewezen en gebruik Groepen om de juiste gebruikers toe te voegen aan de juiste toegangsgroepen.

- Maak voor PowerShell eerst [verbinding met de Azure Active Directory PowerShell for Graph-module.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module) Als u een gebruikersaccount wilt toevoegen aan een toegangsgroep met de UPN (User Principal Name), gebruikt u het volgende PowerShell-opdrachtblok:

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

Als u een gebruikersaccount met de weergavenaam wilt toevoegen aan een toegangsgroep, gebruikt u het volgende PowerShell-opdrachtblok:

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a>Een nieuwe groep toevoegen

Als u toegang wilt toevoegen aan een volledige groep, moet u bepalen welk deelnameniveau alle leden van de groep aan de site mogen deelnemen:

- Beheer: De groep toevoegen aan de toegangsgroep voor sitebeheerders

- Actieve samenwerking: de groep toevoegen aan de groep met siteleden

- Bekijken: De groep toevoegen aan de toegangsgroep voor sitekijkers

Als u gebruikersaccounts en -groepen beheert via AD DS, voegt u de juiste groepen toe aan de juiste groepen met behulp van de normale AD DS-gebruikers- en groepsbeheerprocedures en wacht u op synchronisatie met uw abonnement.

Als u gebruikersaccounts en -groepen beheert via Office 365, kunt u het Microsoft 365-beheercentrum of PowerShell gebruiken:

- Meld u voor het Microsoft 365-beheercentrum aan met een gebruikersaccount aan welke de rol Gebruikersaccountbeheerder of Bedrijfsbeheerder is toegewezen en gebruik Groepen om de juiste groepen toe te voegen aan de juiste toegangsgroepen.

- Maak voor PowerShell eerst [verbinding met de Azure Active Directory PowerShell for Graph-module.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
 Gebruik vervolgens de volgende PowerShell-opdrachten:

```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a>Een gebruiker verwijderen

Wanneer iemands toegang van de site moet worden verwijderd, verwijdert u deze persoon uit de toegangsgroep waarvoor hij of zij momenteel lid is op basis van zijn of haar deelname aan de site:

- Beheer: Het gebruikersaccount verwijderen uit de toegangsgroep voor sitebeheerders

- Actieve samenwerking: het gebruikersaccount verwijderen uit de groep met siteleden

- Weergeven: Het gebruikersaccount verwijderen uit de toegangsgroep voor sitegebruikers

Als u gebruikersaccounts en -groepen beheert via AD DS, verwijdert u de juiste gebruikers uit de juiste toegangsgroepen met behulp van de normale AD DS-gebruikers- en groepsbeheerprocedures en wacht u op synchronisatie met uw abonnement.

Als u gebruikersaccounts en -groepen beheert via Office 365, kunt u het Microsoft 365-beheercentrum of PowerShell gebruiken:

- Meld u voor het Microsoft 365-beheercentrum aan met een gebruikersaccount aan welke de rol Gebruikersaccountbeheerder of Bedrijfsbeheerder is toegewezen en gebruik Groepen om de juiste gebruikers uit de juiste toegangsgroepen te verwijderen.

- Maak voor PowerShell eerst [verbinding met de Azure Active Directory PowerShell for Graph-module.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
Als u een gebruikersaccount wilt verwijderen uit een toegangsgroep met de UPN, gebruikt u het volgende PowerShell-opdrachtblok:

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

Als u een gebruikersaccount wilt verwijderen uit een toegangsgroep met de weergavenaam, gebruikt u het volgende PowerShell-opdrachtblok:

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a>Een groep verwijderen

Als u de toegang voor een hele groep wilt verwijderen, verwijdert u de groep uit de toegangsgroep waarvoor ze momenteel lid zijn op basis van hun deelname aan de site:

- Beheer: De groep verwijderen uit de toegangsgroep voor sitebeheerders

- Actieve samenwerking: de groep verwijderen uit de toegangsgroep voor siteleden

- Bekijken: De groep verwijderen uit de toegangsgroep voor sitekijkers

Als u gebruikersaccounts en -groepen beheert via Windows Server Active Directory, verwijdert u de juiste groepen uit de juiste toegangsgroepen met behulp van de gebruikelijke AD DS-gebruikers- en groepsbeheerprocedures en wacht u op synchronisatie met uw abonnement.

Als u gebruikersaccounts en -groepen beheert via Office 365, kunt u het Microsoft 365-beheercentrum of PowerShell gebruiken:

- Meld u voor het Microsoft 365-beheercentrum aan met een gebruikersaccount aan welke de rol Gebruikersaccountbeheerder of Bedrijfsbeheerder is toegewezen en gebruik Groepen om de juiste groepen uit de juiste toegangsgroepen te verwijderen.

- Maak voor PowerShell eerst [verbinding met de Azure Active Directory PowerShell for Graph-module.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
Als u een groep wilt verwijderen uit een toegangsgroep met de weergavenamen, gebruikt u het volgende PowerShell-opdrachtblok:

```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a>Een submap documenten met aangepaste machtigingen maken

In sommige gevallen heeft een deel van de personen die in een geïsoleerd gebied werken, een meer persoonlijke locatie nodig om samen te werken. Voor SharePoint Online-sites kunt u een submap maken in de map Documenten van de site en aangepaste machtigingen toewijzen. Personen zonder machtigingen zien de submap niet.

Ga als volgt te werk om een submap met documenten met aangepaste machtigingen te maken:

1. Meld u aan bij een account dat lid is van de beheerderstoegangsgroep voor de site. Zie [Waar kan ik me aanmelden in Microsoft 365?](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) voor hulp.

2. Ga naar de geïsoleerde teamsite en klik op **Documenten.**

3. Blader naar de map in de map met documenten met de submap met aangepaste machtigingen, maak de map en open deze.

4. Klik **op Delen.**

5. Klik **op Gedeeld met > Geavanceerd.**

6. Klik **op Overnemen van machtigingen** stoppen en klik vervolgens op **OK.**

7. Klik **op Delen.**

8. Klik **op Gedeeld met > Geavanceerd.**

9. Klik **op Machtigingen verlenen > gedeeld met > Geavanceerd.**

10. Klik op de pagina Machtigingen op **\<site name> Leden in de lijst.**

11. Schakel op **\<site name> de** pagina Leden het vinkje in naast de toegangsgroep voor siteleden, klik op **Acties,** klik op Gebruikers uit groep verwijderen en klik vervolgens op **OK.**

12. Als u specifieke leden wilt toevoegen aan deze submap, klikt u op **> Gebruikers toevoegen.**

13. Typ in **het** dialoogvenster Delen de namen van de gebruikersaccounts die kunnen samenwerken aan bestanden in de submap en klik op **Delen.**

14. Vernieuw de webpagina om de nieuwe resultaten te zien.

15. Klik **onder** Groepen in het **\<site name>** linkernavigatievenster op de groep Bezoekers en gebruik stap 11-14 om de set gebruikersaccounts op te geven die de bestanden in de submap kunnen bekijken (waar nodig).

16. Klik **onder** Groepen in het **\<site name>** linkernavigatievenster op de groep Eigenaren en gebruik stap 11-14 om de set gebruikersaccounts op te geven waarmee u de machtigingen in de submap kunt beheren (waar nodig).

17. Sluit het **tabblad Personen en** groepen in uw browser.

## <a name="see-also"></a>Zie ook

[Geïsoleerde SharePoint Online-teamsites](isolated-sharepoint-online-team-sites.md)

[Een geïsoleerde SharePoint Online-teamsite ontwerpen](design-an-isolated-sharepoint-online-team-site.md)

[Een geïsoleerde SharePoint Online-teamsite implementeren](deploy-an-isolated-sharepoint-online-team-site.md)
