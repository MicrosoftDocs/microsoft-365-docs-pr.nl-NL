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
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: Beheer een geïsoleerde SharePoint Online-teamsite, voeg nieuwe gebruikers en groepen toe, verwijder gebruikers en groepen en maak een submap voor documenten met aangepaste machtigingen.
ms.openlocfilehash: 43329aa72b3729200007441ce73838a7d6a60f55
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755376"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a>Een geïsoleerde SharePoint Online-teamsite beheren

 **Samenvatting:** Beheer uw geïsoleerde SharePoint Online-teamsite met deze procedures.
  
In dit artikel worden algemene beheerbewerkingen voor een geïsoleerde SharePoint Online-teamsite beschreven.
  
## <a name="add-a-new-user"></a>Een nieuwe gebruiker toevoegen

Wanneer iemand nieuw lid wordt van de site, moet u beslissen hun niveau van deelname aan de site:
  
- Beheer: het nieuwe gebruikersaccount toevoegen aan de toegangsgroep sitebeheerders
    
- Actieve samenwerking: het gebruikersaccount toevoegen aan de toegangsgroep voor siteleden
    
- Bekijken: het gebruikersaccount toevoegen aan de groep die kijkers van de site openen
    
Als u gebruikersaccounts en groepen beheert via Active Directory Domain Services (AD DS), voegt u de juiste gebruikers toe aan de juiste toegangsgroepen met behulp van uw normale AD DS-gebruikers- en groepsbeheerprocedures en wacht u op synchronisatie met uw abonnement.
  
Als u gebruikersaccounts en groepen beheert via Microsoft 365, u het Microsoft 365-beheercentrum of Microsoft PowerShell gebruiken:
  
- Meld u voor het Microsoft 365-beheercentrum aan met een gebruikersaccount waaraan de rol Beheerder van gebruikersaccount of bedrijfsbeheerder is toegewezen en gebruik Groepen om de juiste gebruikers toe te voegen aan de juiste toegangsgroepen.
    
- Maak voor PowerShell eerst [verbinding met de module Azure Active Directory PowerShell voor Grafiek](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module). Als u een gebruikersaccount wilt toevoegen aan een toegangsgroep met de gebruikersnaam (UPN), gebruikt u het volgende PowerShell-opdrachtblok:
    
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

Als u een gebruikersaccount wilt toevoegen aan een toegangsgroep met de weergavenaam, gebruikt u het volgende PowerShell-opdrachtblok:

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a>Een nieuwe groep toevoegen

Als u toegang wilt toevoegen tot een hele groep, moet u het deelnameniveau van alle leden van de groep op de site bepalen:
  
- Beheer: de groep toevoegen aan de toegangsgroep sitebeheerders
    
- Actieve samenwerking: de groep toevoegen aan de toegangsgroep voor siteleden
    
- Bekijken: de groep toevoegen aan de groep die kijkers van de site openen
    
Als u gebruikersaccounts en groepen beheert via AD DS, voegt u de juiste groepen toe aan de juiste groepen met behulp van uw normale AD DS-gebruikers- en groepsbeheerprocedures en wacht u op synchronisatie met uw abonnement.
  
Als u gebruikersaccounts en -groepen beheert via Office 365, u het Microsoft 365-beheercentrum of PowerShell gebruiken:
  
- Meld u voor het Microsoft 365-beheercentrum aan met een gebruikersaccount waaraan de rol Beheerder van gebruikersaccount of bedrijfsbeheerder is toegewezen en gebruik Groepen om de juiste groepen toe te voegen aan de juiste toegangsgroepen.
    
- Maak voor PowerShell eerst [verbinding met de module Azure Active Directory PowerShell voor Grafiek](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).
 Gebruik vervolgens de volgende PowerShell-opdrachten:
 
```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a>Een gebruiker verwijderen

Wanneer iemands toegang van de site moet worden verwijderd, verwijdert u deze persoon uit de toegangsgroep waarvoor hij of zij momenteel lid is op basis van zijn deelname aan de site:
  
- Beheer: het gebruikersaccount verwijderen uit de toegangsgroep van sitebeheerders
    
- Actieve samenwerking: het gebruikersaccount verwijderen uit de toegangsgroep voor siteleden
    
- Bekijken: het gebruikersaccount verwijderen uit de groep waar kijkers toegang tot hebben
    
Als u gebruikersaccounts en groepen beheert via AD DS, verwijdert u de juiste gebruikers uit de juiste toegangsgroepen met behulp van uw normale AD DS-gebruikers- en groepsbeheerprocedures en wacht u op synchronisatie met uw abonnement.
  
Als u gebruikersaccounts en -groepen beheert via Office 365, u het Microsoft 365-beheercentrum of PowerShell gebruiken:
  
- Meld u voor het Microsoft 365-beheercentrum aan met een gebruikersaccount waaraan de rol Beheerder van gebruikersaccount of bedrijfsbeheerder is toegewezen en gebruik Groepen om de juiste gebruikers uit de juiste toegangsgroepen te verwijderen.
    
- Maak voor PowerShell eerst [verbinding met de module Azure Active Directory PowerShell voor Grafiek](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).
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
  
- Beheer: de groep verwijderen uit de toegangsgroep van sitebeheerders
    
- Actieve samenwerking: de groep verwijderen uit de toegangsgroep voor siteleden
    
- Bekijken: de groep verwijderen uit de groep die kijkers van de site openen
    
Als u gebruikersaccounts en groepen beheert via Windows Server Active Directory, verwijdert u de juiste groepen uit de juiste toegangsgroepen met behulp van uw normale AD DS-gebruikers- en groepsbeheerprocedures en wacht u op synchronisatie met uw abonnement.
  
Als u gebruikersaccounts en -groepen beheert via Office 365, u het Microsoft 365-beheercentrum of PowerShell gebruiken:
  
- Meld u voor het Microsoft 365-beheercentrum aan met een gebruikersaccount waaraan de rol Beheerder van gebruikersaccount of bedrijfsbeheerder is toegewezen en gebruik Groepen om de juiste groepen uit de juiste toegangsgroepen te verwijderen.
    
- Maak voor PowerShell eerst [verbinding met de module Azure Active Directory PowerShell voor Grafiek](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).    
Als u een groep uit een toegangsgroep wilt verwijderen met hun weergavenamen, gebruikt u het volgende PowerShell-opdrachtblok:
    
```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a>Een submap voor documenten maken met aangepaste machtigingen

In sommige gevallen heeft een deelverzameling van de mensen die op de geïsoleerde site werken een meer privéplek nodig om samen te werken. Voor SharePoint Online-sites u een submap maken in de map Documenten van de site en aangepaste machtigingen toewijzen. Degenen zonder machtigingen zien de submap niet.
  
Ga als volgt te werk om een submap voor documenten met aangepaste machtigingen te maken:
  
1. Meld u aan bij een account dat lid is van de beheerderstoegangsgroep voor de site. Zie [Waar kan ik me aanmelden in Microsoft 365?](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) voor hulp.
    
2. Ga naar de geïsoleerde teamsite en klik op **Documenten**.
    
3. Blader naar de map in de map documenten die de submap met aangepaste machtigingen bevat, maak de map en open deze vervolgens.
    
4. Klik op **Delen**.
    
5. Klik **op Gedeeld met > Geavanceerd**.
    
6. Klik **op Overervingsmachtigingen stoppen**en klik vervolgens op **OK**.
    
7. Klik op **Delen**.
    
8. Klik **op Gedeeld met > Geavanceerd**.
    
9. Klik **op Machtigingen verlenen > gedeeld met > Geavanceerd**.
    
10. Klik op de pagina machtigingen op ** \<site name> Leden in de lijst**.
    
11. Selecteer op de pagina ** \<site name> Leden** het vinkje naast de toegangsgroep voor siteleden, klik op **Acties,** klik op **Gebruikers uit de groep verwijderen**en klik vervolgens op **OK**.
    
12. Als u specifieke leden aan deze submap wilt toevoegen, klikt u op **Nieuw > Gebruikers toevoegen**.
    
13. Typ in het dialoogvenster **Delen** de namen van de gebruikersaccounts die kunnen samenwerken aan bestanden in de submap en klik op **Delen**.
    
14. Vernieuw de webpagina om de nieuwe resultaten te bekijken.
    
15. Klik **onder Groepen** in de linkernavigatie op de groep ** \<site name> Bezoekers** en gebruik stappen 11-14 om de set gebruikersaccounts op te geven die de bestanden in de submap kunnen weergeven (indien nodig).
    
16. Klik onder **Groepen** in de linkernavigatie op de groep ** \<site name> Eigenaren** en gebruik stappen 11-14 om de set gebruikersaccounts op te geven die de machtigingen in de submap kan beheren (indien nodig).
    
17. Sluit het tabblad **Personen en groepen** in uw browser.
    
## <a name="see-also"></a>Zie ook

[Geïsoleerde SharePoint Online-teamsites](isolated-sharepoint-online-team-sites.md)
  
[Een geïsoleerde SharePoint Online-teamsite ontwerpen](design-an-isolated-sharepoint-online-team-site.md)

[Een geïsoleerde SharePoint Online-teamsite implementeren](deploy-an-isolated-sharepoint-online-team-site.md)



